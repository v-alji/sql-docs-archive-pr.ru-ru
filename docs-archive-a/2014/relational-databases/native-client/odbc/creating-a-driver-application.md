---
title: Создание приложения драйвера SQL Server Native Client ODBC | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC, architecture
- SQL Server Native Client ODBC driver, creating applications
- ODBC function calls
- ODBC, header files
- ODBC applications
- ODBC applications, creating
- SQL Server Native Client ODBC driver, extensions
- applications [SQL Server Native Client]
- SQL Server Native Client ODBC driver, ODBC architecture
- extensions [ODBC]
- ODBC, driver extensions
- function calls [ODBC]
ms.assetid: c83c36e2-734e-4960-bc7e-92235910bc6f
author: rothja
ms.author: jroth
ms.openlocfilehash: c8a1719f8b60885810d9b2f8a1f1023a7ffe6e47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738222"
---
# <a name="creating-a-sql-server-native-client-odbc-driver-application"></a><span data-ttu-id="025a0-102">Создание драйвера ODBC для собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="025a0-102">Creating a SQL Server Native Client ODBC Driver Application</span></span>
  <span data-ttu-id="025a0-103">В архитектуре ODBC имеется четыре компонента, которые выполняют следующие функции.</span><span class="sxs-lookup"><span data-stu-id="025a0-103">ODBC architecture has four components that perform the following functions.</span></span>  
  
|<span data-ttu-id="025a0-104">Компонент</span><span class="sxs-lookup"><span data-stu-id="025a0-104">Component</span></span>|<span data-ttu-id="025a0-105">Функция</span><span class="sxs-lookup"><span data-stu-id="025a0-105">Function</span></span>|  
|---------------|--------------|  
|<span data-ttu-id="025a0-106">Развертывание</span><span class="sxs-lookup"><span data-stu-id="025a0-106">Application</span></span>|<span data-ttu-id="025a0-107">Вызывает функции ODBC для связи с источником данных ODBC, поставляет инструкции SQL и обрабатывает результирующие наборы.</span><span class="sxs-lookup"><span data-stu-id="025a0-107">Calls ODBC functions to communicate with an ODBC data source, submits SQL statements, and processes result sets.</span></span>|  
|<span data-ttu-id="025a0-108">Диспетчер драйверов</span><span class="sxs-lookup"><span data-stu-id="025a0-108">Driver Manager</span></span>|<span data-ttu-id="025a0-109">Управляет связью между приложением и всеми драйверами ODBC, используемыми приложением.</span><span class="sxs-lookup"><span data-stu-id="025a0-109">Manages communication between an application and all ODBC drivers used by the application.</span></span>|  
|<span data-ttu-id="025a0-110">Драйвер</span><span class="sxs-lookup"><span data-stu-id="025a0-110">Driver</span></span>|<span data-ttu-id="025a0-111">Обрабатывает вызовы всех функций ODBC из приложения, передает инструкции SQL из приложения в источник данных и возвращает результаты приложению.</span><span class="sxs-lookup"><span data-stu-id="025a0-111">Processes all ODBC function calls from the application, connects to a data source, passes SQL statements from the application to the data source, and returns results to the application.</span></span> <span data-ttu-id="025a0-112">При необходимости драйвер переводит ODBC SQL из приложения в собственный SQL, используемый источником данных.</span><span class="sxs-lookup"><span data-stu-id="025a0-112">If necessary, the driver translates ODBC SQL from the application to native SQL used by the data source.</span></span>|  
|<span data-ttu-id="025a0-113">Источник данных</span><span class="sxs-lookup"><span data-stu-id="025a0-113">Data source</span></span>|<span data-ttu-id="025a0-114">Содержит все необходимые драйверу сведения для доступа к конкретному экземпляру данных в СУБД.</span><span class="sxs-lookup"><span data-stu-id="025a0-114">Contains all information a driver needs to access a specific instance of data in a DBMS.</span></span>|  
  
 <span data-ttu-id="025a0-115">Приложение, использующее [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] драйвер ODBC собственного клиента для взаимодействия с экземпляром служб, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="025a0-115">An application that uses the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver to communicate with an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] performs the following tasks:</span></span>  
  
-   <span data-ttu-id="025a0-116">соединяется с источником данных;</span><span class="sxs-lookup"><span data-stu-id="025a0-116">Connects with a data source</span></span>  
  
-   <span data-ttu-id="025a0-117">отправляет инструкции SQL в источник данных;</span><span class="sxs-lookup"><span data-stu-id="025a0-117">Sends SQL statements to the data source</span></span>  
  
-   <span data-ttu-id="025a0-118">обрабатывает результаты инструкций из источника данных;</span><span class="sxs-lookup"><span data-stu-id="025a0-118">Processes the results of statements from the data source</span></span>  
  
-   <span data-ttu-id="025a0-119">обрабатывает сообщения об ошибках;</span><span class="sxs-lookup"><span data-stu-id="025a0-119">Processes errors and messages</span></span>  
  
-   <span data-ttu-id="025a0-120">Закрывает соединение с источником данных.</span><span class="sxs-lookup"><span data-stu-id="025a0-120">Terminates the connection to the data source</span></span>  
  
 <span data-ttu-id="025a0-121">Более сложное приложение, написанное для [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] драйвера ODBC для собственного клиента, также может выполнять следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="025a0-121">A more complex application written for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver might also perform the following tasks:</span></span>  
  
-   <span data-ttu-id="025a0-122">использовать курсоры для управления расположением в результирующем наборе;</span><span class="sxs-lookup"><span data-stu-id="025a0-122">Use cursors to control location in a result set</span></span>  
  
-   <span data-ttu-id="025a0-123">запрашивать операции фиксации или отката для управления транзакциями;</span><span class="sxs-lookup"><span data-stu-id="025a0-123">Request commit or rollback operations for transaction control</span></span>  
  
-   <span data-ttu-id="025a0-124">выполнять распределенные транзакции между двумя или несколькими серверами;</span><span class="sxs-lookup"><span data-stu-id="025a0-124">Perform distributed transactions involving two or more servers</span></span>  
  
-   <span data-ttu-id="025a0-125">запускать хранимые процедуры на удаленном сервере;</span><span class="sxs-lookup"><span data-stu-id="025a0-125">Run stored procedures on the remote server</span></span>  
  
-   <span data-ttu-id="025a0-126">вызывать функции каталога для запроса сведений об атрибутах результирующего набора;</span><span class="sxs-lookup"><span data-stu-id="025a0-126">Call catalog functions to inquire about the attributes of a result set</span></span>  
  
-   <span data-ttu-id="025a0-127">выполнять операции массового копирования;</span><span class="sxs-lookup"><span data-stu-id="025a0-127">Perform bulk copy operations</span></span>  
  
-   <span data-ttu-id="025a0-128">Операции управления большими данными (в столбцах**varchar (max)**, **nvarchar (max)** и **varbinary (max)** )</span><span class="sxs-lookup"><span data-stu-id="025a0-128">Manage large data (**varchar(max)**, **nvarchar(max)**, and **varbinary(max)** columns) operations</span></span>  
  
-   <span data-ttu-id="025a0-129">использовать логику повторного соединения для облегчения отработки отказа при настроенном зеркальном отображении базы данных;</span><span class="sxs-lookup"><span data-stu-id="025a0-129">Use reconnection logic to facilitate failover when database mirroring is configured</span></span>  
  
-   <span data-ttu-id="025a0-130">записывать в журнал данные о производительности и о долго выполняемых запросах.</span><span class="sxs-lookup"><span data-stu-id="025a0-130">Log performance data and long-running queries</span></span>  
  
 <span data-ttu-id="025a0-131">Для использования функций ODBC приложение на языке C или C++ должно включать файлы заголовка sql.h, sqlext.h и sqltypes.h.</span><span class="sxs-lookup"><span data-stu-id="025a0-131">To make ODBC function calls, a C or C++ application must include the sql.h, sqlext.h, and sqltypes.h header files.</span></span> <span data-ttu-id="025a0-132">Для использования функций API-интерфейса установщика ODBC, приложение должно включать файл заголовка odbcinst.h.</span><span class="sxs-lookup"><span data-stu-id="025a0-132">To make calls to the ODBC installer API functions, an application must include the odbcinst.h header file.</span></span> <span data-ttu-id="025a0-133">Приложение, использующее ODBC и Юникод, должно включать файл заголовка sqlucode.h.</span><span class="sxs-lookup"><span data-stu-id="025a0-133">A Unicode ODBC application must include the sqlucode.h header file.</span></span> <span data-ttu-id="025a0-134">Приложения ODBC должны быть связаны с файлом odbc32.lib.</span><span class="sxs-lookup"><span data-stu-id="025a0-134">ODBC applications must be linked with the odbc32.lib file.</span></span> <span data-ttu-id="025a0-135">Приложения ODBC, вызывающие функции API-интерфейса установщика ODBC, должны быть связаны с файлом odbccp32.lib.</span><span class="sxs-lookup"><span data-stu-id="025a0-135">ODBC applications that call the ODBC installer API functions must be linked with the odbccp32.lib file.</span></span> <span data-ttu-id="025a0-136">Эти файлы включены в пакет SDK платформы Windows.</span><span class="sxs-lookup"><span data-stu-id="025a0-136">These files are included in the Windows Platform SDK.</span></span>  
  
 <span data-ttu-id="025a0-137">Многие драйверы ODBC, в том числе [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] драйвер ODBC для собственного клиента, предлагают расширения ODBC для конкретного драйвера.</span><span class="sxs-lookup"><span data-stu-id="025a0-137">Many ODBC drivers, including the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver, offer driver-specific ODBC extensions.</span></span> <span data-ttu-id="025a0-138">Чтобы воспользоваться преимуществами [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] РАСШИРЕНИЙ ODBC для собственного клиента, приложение должно включать заголовочный файл sqlncli. h.</span><span class="sxs-lookup"><span data-stu-id="025a0-138">To take advantage of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver-specific extensions, an application should include the sqlncli.h header file.</span></span> <span data-ttu-id="025a0-139">Этот файл заголовка содержит следующее:</span><span class="sxs-lookup"><span data-stu-id="025a0-139">This header file contains:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="025a0-140">Особые атрибуты подключения для драйвера ODBC собственного клиента.</span><span class="sxs-lookup"><span data-stu-id="025a0-140">Native Client ODBC driver-specific connection attributes.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="025a0-141">Атрибуты инструкции, относящиеся к драйверу ODBC для собственного клиента.</span><span class="sxs-lookup"><span data-stu-id="025a0-141">Native Client ODBC driver-specific statement attributes.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="025a0-142">Атрибуты столбца, относящиеся к драйверу ODBC для собственного клиента.</span><span class="sxs-lookup"><span data-stu-id="025a0-142">Native Client ODBC driver-specific column attributes.</span></span>  
  
-   <span data-ttu-id="025a0-143">типы данных, относящиеся к [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)];</span><span class="sxs-lookup"><span data-stu-id="025a0-143">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-specific data types.</span></span>  
  
-   <span data-ttu-id="025a0-144">определяемые пользователем типы данных, относящиеся к [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)];</span><span class="sxs-lookup"><span data-stu-id="025a0-144">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-specific user-defined data types.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="025a0-145">Типы [SQLGetInfo](../../native-client-odbc-api/sqlgetinfo.md) , относящиеся к ДРАЙВЕРу ODBC для собственного клиента.</span><span class="sxs-lookup"><span data-stu-id="025a0-145">Native Client ODBC driver-specific [SQLGetInfo](../../native-client-odbc-api/sqlgetinfo.md) types.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="025a0-146">Поля диагностики драйвера ODBC для собственного клиента.</span><span class="sxs-lookup"><span data-stu-id="025a0-146">Native Client ODBC driver diagnostics fields.</span></span>  
  
-   <span data-ttu-id="025a0-147">диагностические коды динамических функций, относящиеся к [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)];</span><span class="sxs-lookup"><span data-stu-id="025a0-147">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-specific diagnostic dynamic function codes.</span></span>  
  
-   <span data-ttu-id="025a0-148">определения типов C и C++ для собственных типов данных C, зависящие от [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (возвращаются, если столбцы привязаны к типу данных C SQL_C_BINARY);</span><span class="sxs-lookup"><span data-stu-id="025a0-148">C/C++ type definitions for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-specific native C data types (returned when columns bound to C data type SQL_C_BINARY).</span></span>  
  
-   <span data-ttu-id="025a0-149">определение типа для структуры данных SQLPERF;</span><span class="sxs-lookup"><span data-stu-id="025a0-149">Type definition for the SQLPERF data structure.</span></span>  
  
-   <span data-ttu-id="025a0-150">макросы и прототипы массового копирования для поддержки API-интерфейса массового копирования через соединение ODBC;</span><span class="sxs-lookup"><span data-stu-id="025a0-150">Bulk copy macros and prototypes to support bulk copy API usage through an ODBC connection.</span></span>  
  
-   <span data-ttu-id="025a0-151">вызов функций API-интерфейса метаданных распределенного запроса для списков связанных серверов и их каталогов.</span><span class="sxs-lookup"><span data-stu-id="025a0-151">Call the distributed query metadata API functions for lists of linked servers and their catalogs.</span></span>  
  
 <span data-ttu-id="025a0-152">Любое приложение ODBC C или C++, использующее функцию копирования [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] драйвера ODBC собственного клиента, должно быть связано с файлом sqlncli11. lib.</span><span class="sxs-lookup"><span data-stu-id="025a0-152">Any C or C++ ODBC application that uses the bulk copy feature of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver must be linked with the sqlncli11.lib file.</span></span> <span data-ttu-id="025a0-153">Приложения, вызывающие функции API-интерфейса метаданных распределенного запроса, также должны компоноваться с файлом sqlncli11.lib.</span><span class="sxs-lookup"><span data-stu-id="025a0-153">Applications calling the distributed query metadata API functions must also be linked with sqlncli11.lib.</span></span> <span data-ttu-id="025a0-154">Файлы sqlncli. h и sqlncli11. lib распространяются в составе [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] средств разработчика.</span><span class="sxs-lookup"><span data-stu-id="025a0-154">The sqlncli.h and sqlncli11.lib files are distributed as part of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] developer's tools.</span></span> <span data-ttu-id="025a0-155">Каталоги [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Include и Lib должны находиться в пути компилятора INCLUDE и LIB, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="025a0-155">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Include and Lib directories should be in the compiler's INCLUDE and LIB paths as in the following:</span></span>  
  
```  
LIB=c:\Program Files\Microsoft Data Access SDK 2.8\Libs\x86\lib;C:\Program Files\Microsoft SQL Server\100\Tools\SDK\Lib;  
INCLUDE=c:\Program Files\Microsoft Data Access SDK 2.8\inc;C:\Program Files\Microsoft SQL Server\100\Tools\SDK\Include;  
```  
  
 <span data-ttu-id="025a0-156">На раннем этапе разработки приложения необходимо решить, будет ли приложение нуждаться в нескольких одновременных вызовах ODBC.</span><span class="sxs-lookup"><span data-stu-id="025a0-156">One design decision made early in the process of building an application is whether the application needs to have multiple ODBC calls outstanding at the same time.</span></span> <span data-ttu-id="025a0-157">Существует два метода поддержки нескольких одновременных вызовов ODBC. Они описаны в оставшихся разделах этой темы.</span><span class="sxs-lookup"><span data-stu-id="025a0-157">There are two methods for supporting multiple concurrent ODBC calls, which are described in the remaining topics in this section.</span></span> <span data-ttu-id="025a0-158">Дополнительные сведения см. в [справочнике программиста по ODBC](https://go.microsoft.com/fwlink/?LinkId=45250).</span><span class="sxs-lookup"><span data-stu-id="025a0-158">For more information, see the [ODBC Programmer's Reference](https://go.microsoft.com/fwlink/?LinkId=45250).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="025a0-159">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="025a0-159">In This Section</span></span>  
  
-   [<span data-ttu-id="025a0-160">Асинхронный режим и команда SQLCancel</span><span class="sxs-lookup"><span data-stu-id="025a0-160">Asynchronous Mode and SQLCancel</span></span>](../../native-client-odbc-api/sqlcancel.md)  
  
-   [<span data-ttu-id="025a0-161">Многопоточные приложения</span><span class="sxs-lookup"><span data-stu-id="025a0-161">Multithreaded Applications</span></span>](creating-a-driver-application-multithreaded-applications.md)  
  
## <a name="see-also"></a><span data-ttu-id="025a0-162">См. также:</span><span class="sxs-lookup"><span data-stu-id="025a0-162">See Also</span></span>  
 [<span data-ttu-id="025a0-163">SQL Server Native Client (ODBC)</span><span class="sxs-lookup"><span data-stu-id="025a0-163">SQL Server Native Client &#40;ODBC&#41;</span></span>](sql-server-native-client-odbc.md)  
  
  
