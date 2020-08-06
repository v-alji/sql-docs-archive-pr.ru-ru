---
title: Подключение к источнику данных (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- checking connection states
- ODBC data sources, connections
- data sources [SQL Server Native Client]
- SQLBrowseConnect function
- ODBC applications, connections
- ODBC applications, data sources
- connections [SQL Server Native Client]
- SQLConnect function
- SQLDriveConnect function
- verifying connection states
- SQL Server Native Client ODBC driver, data sources
- SQL Server Native Client ODBC driver, connections
ms.assetid: ae30dd1d-06ae-452b-9618-8fd8cd7ba074
author: rothja
ms.author: jroth
ms.openlocfilehash: 25ce5954e45bb8070b5e99d8ebb7bfa9ad149c3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664163"
---
# <a name="connecting-to-a-data-source-odbc"></a><span data-ttu-id="bb14c-102">Соединение с источником данных (ODBC)</span><span class="sxs-lookup"><span data-stu-id="bb14c-102">Connecting to a Data Source (ODBC)</span></span>
  <span data-ttu-id="bb14c-103">После определения среды и дескрипторов соединения, а также установки любых атрибутов соединения приложение устанавливает соединение с источником данных или драйвером.</span><span class="sxs-lookup"><span data-stu-id="bb14c-103">After allocating environment and connection handles and setting any connection attributes, the application connects to the data source or driver.</span></span> <span data-ttu-id="bb14c-104">Существует три функции, которые можно использовать для установки соединения:</span><span class="sxs-lookup"><span data-stu-id="bb14c-104">There are three functions you can use to connect:</span></span>  
  
-   <span data-ttu-id="bb14c-105">**SQLConnect**</span><span class="sxs-lookup"><span data-stu-id="bb14c-105">**SQLConnect**</span></span>  
  
-   <span data-ttu-id="bb14c-106">**SQLDriverConnect**</span><span class="sxs-lookup"><span data-stu-id="bb14c-106">**SQLDriverConnect**</span></span>  
  
-   <span data-ttu-id="bb14c-107">**SQLBrowseConnect**</span><span class="sxs-lookup"><span data-stu-id="bb14c-107">**SQLBrowseConnect**</span></span>  
  
 <span data-ttu-id="bb14c-108">Дополнительные сведения о подключении к источнику данных, включая различные доступные параметры строки подключения, см. в разделе [Использование ключевых слов строки подключения с SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="bb14c-108">For more information about making connections to a data source, including the various connection string options available, see [Using Connection String Keywords with SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
## <a name="sqlconnect"></a><span data-ttu-id="bb14c-109">SQLConnect</span><span class="sxs-lookup"><span data-stu-id="bb14c-109">SQLConnect</span></span>  
 <span data-ttu-id="bb14c-110">**SQLConnect** — это простейшая функция подключения.</span><span class="sxs-lookup"><span data-stu-id="bb14c-110">**SQLConnect** is the simplest connection function.</span></span> <span data-ttu-id="bb14c-111">Она принимает три параметра: имя источника данных, идентификатор пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="bb14c-111">It accepts three parameters: a data source name, a user ID, and a password.</span></span> <span data-ttu-id="bb14c-112">Используйте **SQLConnect** , если эти три параметра содержат всю информацию, необходимую для подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="bb14c-112">Use **SQLConnect** when these three parameters contain all the information needed to connect to the database.</span></span> <span data-ttu-id="bb14c-113">Для этого создайте список источников данных с помощью **SQLDataSources**; запрашивать у пользователя источник данных, идентификатор пользователя и пароль; затем вызовите **SQLConnect**.</span><span class="sxs-lookup"><span data-stu-id="bb14c-113">To do this, build a list of data sources using **SQLDataSources**; prompt the user for a data source, user ID, and password; and then call **SQLConnect**.</span></span>  
  
 <span data-ttu-id="bb14c-114">**SQLConnect** предполагает, что имя источника данных, идентификатор пользователя и пароль достаточно для подключения к источнику данных и что источник данных ODBC содержит все остальные сведения, необходимые драйверу ODBC для подключения.</span><span class="sxs-lookup"><span data-stu-id="bb14c-114">**SQLConnect** assumes that a data source name, user ID, and password are sufficient to connect to a data source and that the ODBC data source contains all other information the ODBC driver needs to make the connection.</span></span> <span data-ttu-id="bb14c-115">В отличие от [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) и [SQLBrowseConnect](../native-client-odbc-api/sqlbrowseconnect.md), **SQLConnect** не использует строку подключения.</span><span class="sxs-lookup"><span data-stu-id="bb14c-115">Unlike [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) and [SQLBrowseConnect](../native-client-odbc-api/sqlbrowseconnect.md), **SQLConnect** does not use a connection string.</span></span>  
  
## <a name="sqldriverconnect"></a><span data-ttu-id="bb14c-116">SQLDriverConnect</span><span class="sxs-lookup"><span data-stu-id="bb14c-116">SQLDriverConnect</span></span>  
 <span data-ttu-id="bb14c-117">**SQLDriverConnect** используется, если требуется получить больше информации, чем имя источника данных, идентификатор пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="bb14c-117">**SQLDriverConnect** is used when more information than the data source name, user ID, and password is required.</span></span> <span data-ttu-id="bb14c-118">Одним из параметров **SQLDriverConnect** является строка подключения, содержащая сведения, относящиеся к драйверу.</span><span class="sxs-lookup"><span data-stu-id="bb14c-118">One of the parameters to **SQLDriverConnect** is a connection string containing driver-specific information.</span></span> <span data-ttu-id="bb14c-119">Вы можете использовать **SQLDriverConnect** вместо **SQLConnect** по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="bb14c-119">You might use **SQLDriverConnect** instead of **SQLConnect** for the following reasons:</span></span>  
  
-   <span data-ttu-id="bb14c-120">для указания специфической для драйвера информации во время подключения;</span><span class="sxs-lookup"><span data-stu-id="bb14c-120">To specify driver-specific information at connect time.</span></span>  
  
-   <span data-ttu-id="bb14c-121">для запроса, который драйвер направляет пользователю для получения информации о соединении;</span><span class="sxs-lookup"><span data-stu-id="bb14c-121">To request that the driver prompt the user for connection information.</span></span>  
  
-   <span data-ttu-id="bb14c-122">для соединения без использования источника данных ODBC.</span><span class="sxs-lookup"><span data-stu-id="bb14c-122">To connect without using an ODBC data source.</span></span>  
  
 <span data-ttu-id="bb14c-123">Строка подключения **SQLDriverConnect** содержит ряд пар "ключевое слово-значение", которые указывают все сведения о соединении, поддерживаемые драйвером ODBC.</span><span class="sxs-lookup"><span data-stu-id="bb14c-123">The **SQLDriverConnect** connection string contains a series of keyword-value pairs that specify all connection information supported by an ODBC driver.</span></span> <span data-ttu-id="bb14c-124">Каждый драйвер поддерживает стандартные ключевые слова ODBC (DSN, FILEDSN, DRIVER, UID, PWD и SAVEFILE) в дополнение к специальным ключевым словам драйвера для указания всей информации о соединении, поддерживаемой драйвером.</span><span class="sxs-lookup"><span data-stu-id="bb14c-124">Each driver supports the standard ODBC keywords (DSN, FILEDSN, DRIVER, UID, PWD, and SAVEFILE) in addition to driver-specific keywords for all connection information supported by the driver.</span></span> <span data-ttu-id="bb14c-125">**SQLDriverConnect** можно использовать для подключения без источника данных.</span><span class="sxs-lookup"><span data-stu-id="bb14c-125">**SQLDriverConnect** can be used to connect without a data source.</span></span> <span data-ttu-id="bb14c-126">Например, приложение, которое предназначено для создания подключения "без DSN" к экземпляру, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] может вызывать **SQLDriverConnect** со строкой подключения, определяющей идентификатор входа, пароль, сетевую библиотеку, имя сервера для подключения и используемую базой данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bb14c-126">For example, an application that is designed to make a "DSN-less" connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can call **SQLDriverConnect** with a connection string that defines the login ID, password, network library, server name to connect to, and default database to use.</span></span>  
  
 <span data-ttu-id="bb14c-127">При использовании **SQLDriverConnect**существует два варианта запроса сведений о подключении для пользователя.</span><span class="sxs-lookup"><span data-stu-id="bb14c-127">When using **SQLDriverConnect**, there are two options for prompting the user for any needed connection information:</span></span>  
  
-   <span data-ttu-id="bb14c-128">Диалоговое окно приложения</span><span class="sxs-lookup"><span data-stu-id="bb14c-128">Application dialog box</span></span>  
  
     <span data-ttu-id="bb14c-129">Можно создать диалоговое окно приложения, в котором запрашиваются сведения о соединении, а затем вызывает **SQLDriverConnect** с нулевым маркером окна, а *DriverCompletion* — значением SQL_DRIVER_NOPROMPT.</span><span class="sxs-lookup"><span data-stu-id="bb14c-129">You can create an application dialog box that prompts for connection information, and then calls **SQLDriverConnect** with a NULL window handle and *DriverCompletion* set to SQL_DRIVER_NOPROMPT.</span></span> <span data-ttu-id="bb14c-130">Эти параметры предотвращают открытие драйвером ODBC собственного диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="bb14c-130">These parameter settings prevent the ODBC driver from opening its own dialog box.</span></span> <span data-ttu-id="bb14c-131">Этот метод используется, когда важно управлять пользовательским интерфейсом приложения.</span><span class="sxs-lookup"><span data-stu-id="bb14c-131">This method is used when it is important to control the user interface of the application.</span></span>  
  
-   <span data-ttu-id="bb14c-132">Диалоговое окно драйвера</span><span class="sxs-lookup"><span data-stu-id="bb14c-132">Driver dialog box</span></span>  
  
     <span data-ttu-id="bb14c-133">Можно создать код приложения, чтобы передать допустимый обработчик окна в **SQLDriverConnect** и установить параметр *DriverCompletion* в значение SQL_DRIVER_COMPLETE, SQL_DRIVER_PROMPT или SQL_DRIVER_COMPLETE_REQUIRED.</span><span class="sxs-lookup"><span data-stu-id="bb14c-133">You can code the application to pass a valid window handle to **SQLDriverConnect** and set the *DriverCompletion* parameter to SQL_DRIVER_COMPLETE, SQL_DRIVER_PROMPT, or SQL_DRIVER_COMPLETE_REQUIRED.</span></span> <span data-ttu-id="bb14c-134">Затем драйвер формирует диалоговое окно для получения от пользователя информации о соединении.</span><span class="sxs-lookup"><span data-stu-id="bb14c-134">The driver then generates a dialog box to prompt the user for connection information.</span></span> <span data-ttu-id="bb14c-135">Этот метод упрощает код приложения.</span><span class="sxs-lookup"><span data-stu-id="bb14c-135">This method simplifies the application code.</span></span>  
  
## <a name="sqlbrowseconnect"></a><span data-ttu-id="bb14c-136">SQLBrowseConnect</span><span class="sxs-lookup"><span data-stu-id="bb14c-136">SQLBrowseConnect</span></span>  
 <span data-ttu-id="bb14c-137">**SQLBrowseConnect**, например **SQLDriverConnect**, использует строку подключения.</span><span class="sxs-lookup"><span data-stu-id="bb14c-137">**SQLBrowseConnect**, like **SQLDriverConnect**, uses a connection string.</span></span> <span data-ttu-id="bb14c-138">Однако с помощью **SQLBrowseConnect**приложение может итеративно создавать полную строку соединения с источником данных во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="bb14c-138">However, by using **SQLBrowseConnect**, an application can construct a complete connection string iteratively with the data source at run time.</span></span> <span data-ttu-id="bb14c-139">Это позволяет приложению:</span><span class="sxs-lookup"><span data-stu-id="bb14c-139">This allows the application to do two things:</span></span>  
  
-   <span data-ttu-id="bb14c-140">строить собственные диалоговые окна для запроса этой информации, сохраняя таким образом управление своим пользовательским интерфейсом;</span><span class="sxs-lookup"><span data-stu-id="bb14c-140">Build its own dialog boxes to prompt for this information, thereby retaining control over its user interface.</span></span>  
  
-   <span data-ttu-id="bb14c-141">просматривать систему в поисках источников данных, которые может использовать конкретный драйвер, возможно, за несколько шагов.</span><span class="sxs-lookup"><span data-stu-id="bb14c-141">Browse the system for data sources that can be used by a particular driver, possibly in several steps.</span></span>  
  
     <span data-ttu-id="bb14c-142">Например, пользователь может сначала просмотреть серверы в сети, а после выбора сервера с помощью драйвера просмотреть доступные базы данных этого сервера.</span><span class="sxs-lookup"><span data-stu-id="bb14c-142">For example, the user might first browse the network for servers and, after choosing a server, browse the server for databases accessible by the driver.</span></span>  
  
 <span data-ttu-id="bb14c-143">Когда **SQLBrowseConnect** завершает успешное подключение, он возвращает строку подключения, которую можно использовать при последующих вызовах **SQLDriverConnect**.</span><span class="sxs-lookup"><span data-stu-id="bb14c-143">When **SQLBrowseConnect** completes a successful connection, it returns a connection string that can be used on subsequent calls to **SQLDriverConnect**.</span></span>  
  
 <span data-ttu-id="bb14c-144">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Драйвер ODBC для собственного клиента всегда возвращает SQL_SUCCESS_WITH_INFO для успешных **SQLConnect**, **SQLDriverConnect**или **SQLBrowseConnect**.</span><span class="sxs-lookup"><span data-stu-id="bb14c-144">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver always returns SQL_SUCCESS_WITH_INFO on a successful **SQLConnect**, **SQLDriverConnect**, or **SQLBrowseConnect**.</span></span> <span data-ttu-id="bb14c-145">Когда приложение ODBC вызывает **SQLGetDiagRec** после получения SQL_SUCCESS_WITH_INFO, оно может получать следующие сообщения:</span><span class="sxs-lookup"><span data-stu-id="bb14c-145">When an ODBC application calls **SQLGetDiagRec** after getting SQL_SUCCESS_WITH_INFO, it can receive the following messages:</span></span>  
  
 <span data-ttu-id="bb14c-146">5701</span><span class="sxs-lookup"><span data-stu-id="bb14c-146">5701</span></span>  
 <span data-ttu-id="bb14c-147">Показывает, что [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] помещает пользовательский контекст в базу данных по умолчанию, которая определена в источнике данных, или в базу данных, определенную для идентификатора входа, который использовался в соединении, если источник данных не имеет базы данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bb14c-147">Indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] put the user's context into the default database defined in the data source, or into the default database defined for the login ID used in the connection if the data source did not have a default database.</span></span>  
  
 <span data-ttu-id="bb14c-148">5703</span><span class="sxs-lookup"><span data-stu-id="bb14c-148">5703</span></span>  
 <span data-ttu-id="bb14c-149">Обозначает язык, используемый на сервере.</span><span class="sxs-lookup"><span data-stu-id="bb14c-149">Indicates the language being used on the server.</span></span>  
  
 <span data-ttu-id="bb14c-150">В следующих примерах показано сообщение, которое возвращается системным администратором при успешном соединении:</span><span class="sxs-lookup"><span data-stu-id="bb14c-150">The following example shows the message returned on a successful connection by the system administrator:</span></span>  
  
```  
szSqlState = "01000", *pfNativeError = 5701,  
szErrorMsg="[Microsoft][SQL Server Native Client][SQL Server]  
       Changed database context to 'pubs'."  
szSqlState = "01000", *pfNativeError = 5703,  
szErrorMsg="[Microsoft][SQL Server Native Client][SQL Server]  
       Changed language setting to 'us_english'."  
```  
  
 <span data-ttu-id="bb14c-151">Можно не обрабатывать сообщения 5701 и 5703; они всего лишь информационные.</span><span class="sxs-lookup"><span data-stu-id="bb14c-151">You can ignore messages 5701 and 5703; they are only informational.</span></span> <span data-ttu-id="bb14c-152">Однако не следует пропускать код возврата SQL_SUCCESS_WITH_INFO, так как сообщения, отличные от 5701 и 5703, могут быть возвращены.</span><span class="sxs-lookup"><span data-stu-id="bb14c-152">You should not, however, ignore a SQL_SUCCESS_WITH_INFO return code because messages other than 5701 or 5703 may be returned.</span></span> <span data-ttu-id="bb14c-153">Например, если драйвер подключается к серверу, на котором выполняется экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с устаревшими хранимыми процедурами каталога, одна из ошибок, возвращаемых через **SQLGetDiagRec** после SQL_SUCCESS_WITH_INFO:</span><span class="sxs-lookup"><span data-stu-id="bb14c-153">For example, if a driver connects to a server running an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with outdated catalog stored procedures, one of the errors returned through **SQLGetDiagRec** after a SQL_SUCCESS_WITH_INFO is:</span></span>  
  
```  
SqlState:   01000  
pfNative:   0  
szErrorMsg: "[Microsoft][SQL Server Native Client]The ODBC  
            catalog stored procedures installed on server  
            my65server are version 06.50.0193; version 07.00.0205  
            or later is required to ensure proper operation.  
            Please contact your system administrator."  
```  
  
 <span data-ttu-id="bb14c-154">Функция обработки ошибок приложения для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] подключений должна вызывать **SQLGetDiagRec** до тех пор, пока не вернет SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="bb14c-154">The error handling function of an application for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connections should call **SQLGetDiagRec** until it returns SQL_NO_DATA.</span></span> <span data-ttu-id="bb14c-155">Затем он должен работать с любыми сообщениями, кроме тех, с *pfNative* кодом 5701 или 5703.</span><span class="sxs-lookup"><span data-stu-id="bb14c-155">It should then act on any messages other than the ones with a *pfNative* code of 5701 or 5703.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb14c-156">См. также:</span><span class="sxs-lookup"><span data-stu-id="bb14c-156">See Also</span></span>  
 [<span data-ttu-id="bb14c-157">Взаимодействие с SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="bb14c-157">Communicating with SQL Server &#40;ODBC&#41;</span></span>](communicating-with-sql-server-odbc.md)  
  
  
