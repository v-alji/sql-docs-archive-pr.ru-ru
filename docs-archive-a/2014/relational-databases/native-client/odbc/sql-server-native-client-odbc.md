---
title: SQL Server Native Client (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLNCLI, ODBC
- SQL Server Native Client ODBC driver, about SQL Server Native Client ODBC driver
- data access [SQL Server Native Client], ODBC
- SQL Server Native Client ODBC driver
- ODBC
- SQL Server Native Client, ODBC
- ODBC, about SQL Server Native Client ODBC driver
ms.assetid: 811d5ba3-a2b8-48c0-adbc-8c91f041f458
author: rothja
ms.author: jroth
ms.openlocfilehash: 16c73966e318ed1e7d326fa77f56195ebbd830df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734026"
---
# <a name="sql-server-native-client-odbc"></a><span data-ttu-id="39c9f-102">Собственный клиент SQL Server (ODBC)</span><span class="sxs-lookup"><span data-stu-id="39c9f-102">SQL Server Native Client (ODBC)</span></span>
  <span data-ttu-id="39c9f-103">ODBC — это стандартное определение прикладного программного интерфейса (API), который используется для доступа к данным в реляционных базах данных и базах данных с индексно-последовательным методом доступа (ISAM).</span><span class="sxs-lookup"><span data-stu-id="39c9f-103">ODBC is a standard definition of an application programming interface (API) used to access data in relational or indexed sequential access method (ISAM) databases.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="39c9f-104">поддерживает ODBC через драйвер ODBC клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client как один из собственных API для написания приложений на языках C и C++, взаимодействующих с [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39c9f-104">supports ODBC, via the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver, as one of the native APIs for writing C and C++ applications that communicate with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="39c9f-105">Программы [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], написанные с помощью драйвера ODBC собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], взаимодействуют с [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] с помощью вызовов функций на языке C.</span><span class="sxs-lookup"><span data-stu-id="39c9f-105">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] programs that are written using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver communicate with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] through C function calls.</span></span> <span data-ttu-id="39c9f-106">Специфичные для [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] версии функций ODBC реализованы в драйвере ODBC собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39c9f-106">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-specific versions of the ODBC functions are implemented in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span> <span data-ttu-id="39c9f-107">Драйвер передает инструкции SQL в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] и возвращает приложению результаты их выполнения.</span><span class="sxs-lookup"><span data-stu-id="39c9f-107">The driver passes SQL statements to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and returns the results of the statements to the application.</span></span>  
  
 <span data-ttu-id="39c9f-108">Драйвер ODBC для собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] соответствует требованиям спецификации Microsoft Win32 ODBC 3.51.</span><span class="sxs-lookup"><span data-stu-id="39c9f-108">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver complies with the Microsoft Win32 ODBC 3.51 specification.</span></span> <span data-ttu-id="39c9f-109">Драйвер поддерживает приложения, написанные с применением более ранних версий ODBC согласно спецификации ODBC 3.51.</span><span class="sxs-lookup"><span data-stu-id="39c9f-109">The driver supports applications written using earlier versions of ODBC in the manner defined in the ODBC 3.51 specification.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="39c9f-110">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="39c9f-110">In This Section</span></span>  
  
-   [<span data-ttu-id="39c9f-111">Имена источников данных и 64-разрядные операционные системы</span><span class="sxs-lookup"><span data-stu-id="39c9f-111">Data Source Names and 64-Bit Operating Systems</span></span>](data-source-names-and-64-bit-operating-systems.md)  
  
-   [<span data-ttu-id="39c9f-112">Создание драйвера ODBC для собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="39c9f-112">Creating a SQL Server Native Client ODBC Driver Application</span></span>](creating-a-driver-application.md)  
  
-   [<span data-ttu-id="39c9f-113">Взаимодействие с SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="39c9f-113">Communicating with SQL Server &#40;ODBC&#41;</span></span>](../../native-client-odbc-communication/communicating-with-sql-server-odbc.md)  
  
-   [<span data-ttu-id="39c9f-114">Выполняя запросы &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="39c9f-114">Executing Queries &#40;ODBC&#41;</span></span>](../../native-client-odbc-queries/executing-queries-odbc.md)  
  
-   [<span data-ttu-id="39c9f-115">Обработка результатов &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="39c9f-115">Processing Results &#40;ODBC&#41;</span></span>](../../native-client-odbc-results/processing-results-odbc.md)  
  
-   [<span data-ttu-id="39c9f-116">Использование курсоров &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="39c9f-116">Using Cursors &#40;ODBC&#41;</span></span>](../../native-client-odbc-cursors/using-cursors-odbc.md)  
  
-   [<span data-ttu-id="39c9f-117">Выполнение транзакций &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="39c9f-117">Performing Transactions &#40;ODBC&#41;</span></span>](../../../database-engine/dev-guide/performing-transactions-odbc.md)  
  
-   [<span data-ttu-id="39c9f-118">Обработка ошибок и сообщений</span><span class="sxs-lookup"><span data-stu-id="39c9f-118">Handling Errors and Messages</span></span>](../../native-client-odbc-error-messages/handling-errors-and-messages.md)  
  
-   [<span data-ttu-id="39c9f-119">Выполнение хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="39c9f-119">Running Stored Procedures</span></span>](../../native-client-odbc-stored-procedures/running-stored-procedures.md)  
  
-   [<span data-ttu-id="39c9f-120">Использование функций каталога</span><span class="sxs-lookup"><span data-stu-id="39c9f-120">Using Catalog Functions</span></span>](using-catalog-functions.md)  
  
-   [<span data-ttu-id="39c9f-121">Выполнение операций с массовым копированием &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="39c9f-121">Performing Bulk Copy Operations &#40;ODBC&#41;</span></span>](../../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md)  
  
-   [<span data-ttu-id="39c9f-122">Управление столбцами text и image</span><span class="sxs-lookup"><span data-stu-id="39c9f-122">Managing Text and Image Columns</span></span>](../../native-client-odbc-text-image-columns/managing-text-and-image-columns.md)  
  
-   [<span data-ttu-id="39c9f-123">Создание профилей производительности драйвера ODBC</span><span class="sxs-lookup"><span data-stu-id="39c9f-123">Profiling ODBC Driver Performance</span></span>](profiling-odbc-driver-performance.md)  
  
-   [<span data-ttu-id="39c9f-124">Возвращающие табличное значение параметры &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="39c9f-124">Table-Valued Parameters &#40;ODBC&#41;</span></span>](../../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md)  
  
-   [<span data-ttu-id="39c9f-125">Улучшения даты и времени &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="39c9f-125">Date and Time Improvements &#40;ODBC&#41;</span></span>](../../native-client-odbc-date-time/date-and-time-improvements-odbc.md)  
  
-   [<span data-ttu-id="39c9f-126">Большие определяемые пользователем типы данных CLR &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="39c9f-126">Large CLR User-Defined Types &#40;ODBC&#41;</span></span>](large-clr-user-defined-types-odbc.md)  
  
-   [<span data-ttu-id="39c9f-127">Поддержка FILESTREAM &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="39c9f-127">FILESTREAM Support &#40;ODBC&#41;</span></span>](filestream-support-odbc.md)  
  
-   [<span data-ttu-id="39c9f-128">Имена участника-службы (SPN) в клиентских соединениях (ODBC)</span><span class="sxs-lookup"><span data-stu-id="39c9f-128">Service Principal Names &#40;SPNs&#41; in Client Connections &#40;ODBC&#41;</span></span>](service-principal-names-spns-in-client-connections-odbc.md)  
  
-   [<span data-ttu-id="39c9f-129">Разреженные столбцы поддерживают &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="39c9f-129">Sparse Columns Support &#40;ODBC&#41;</span></span>](sparse-columns-support-odbc.md)  
  
-   [<span data-ttu-id="39c9f-130">Справочник по SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="39c9f-130">SQL Server Native Client &#40;ODBC&#41; Reference</span></span>](../../../database-engine/dev-guide/sql-server-native-client-odbc-reference.md)  
  
-   [<span data-ttu-id="39c9f-131">ODBC How-to Topics</span><span class="sxs-lookup"><span data-stu-id="39c9f-131">ODBC How-to Topics</span></span>](../../native-client-odbc-how-to/odbc-how-to-topics.md)  
  
## <a name="see-also"></a><span data-ttu-id="39c9f-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="39c9f-132">See Also</span></span>  
 <span data-ttu-id="39c9f-133">[SQL Server Native Client программирование](../sql-server-native-client-programming.md) </span><span class="sxs-lookup"><span data-stu-id="39c9f-133">[SQL Server Native Client Programming](../sql-server-native-client-programming.md) </span></span>  
 [<span data-ttu-id="39c9f-134">Установка собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="39c9f-134">Installing SQL Server Native Client</span></span>](../applications/installing-sql-server-native-client.md)  
  
  
