---
title: Выполнение операций с массовым копированием (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, bulk copy
- bulk copy [ODBC]
- ODBC, bulk copy operations
- minimally logged operations [SQL Server Native Client]
- bulk copy [ODBC], about bulk copy
ms.assetid: 5c793405-487c-4f52-88b8-0091d529afb3
author: rothja
ms.author: jroth
ms.openlocfilehash: f2647ebca703eab46d7be0e1cfc2490a65384ee6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749824"
---
# <a name="performing-bulk-copy-operations-odbc"></a><span data-ttu-id="bff6e-102">Выполнение операций массового копирования (ODBC)</span><span class="sxs-lookup"><span data-stu-id="bff6e-102">Performing Bulk Copy Operations (ODBC)</span></span>
  <span data-ttu-id="bff6e-103">Стандарт ODBC напрямую не поддерживает операции массового копирования [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bff6e-103">The ODBC standard does not directly support [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bulk copy operations.</span></span> <span data-ttu-id="bff6e-104">При соединении с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] версии 7.0 или более поздней, драйвер ODBC собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживает функции библиотеки DB-Library, выполняющие операции массового копирования в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bff6e-104">When connected to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 7.0 or later, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports the DB-Library functions that perform [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bulk copy operations.</span></span> <span data-ttu-id="bff6e-105">Этот собственный модуль драйвера обеспечивает легкий путь обновления для существующих приложений DB-Library, использующих функции массового копирования.</span><span class="sxs-lookup"><span data-stu-id="bff6e-105">This driver-specific extension provides an easy upgrade path for existing DB-Library applications that use bulk copy functions.</span></span> <span data-ttu-id="bff6e-106">Специализированная поддержка массового копирования реализована в следующих файлах.</span><span class="sxs-lookup"><span data-stu-id="bff6e-106">The specialized bulk copy support is in the following files:</span></span>  
  
-   <span data-ttu-id="bff6e-107">sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="bff6e-107">sqlncli.h</span></span>  
  
     <span data-ttu-id="bff6e-108">Включает прототипы функций и определения констант для функций массового копирования.</span><span class="sxs-lookup"><span data-stu-id="bff6e-108">Includes function prototypes and constant definitions for bulk copy functions.</span></span> <span data-ttu-id="bff6e-109">Файл sqlncli.h должен входить в состав приложения ODBC, выполняющего операции массового копирования, и при компиляции приложения должен находиться в пути поиска включаемых файлов.</span><span class="sxs-lookup"><span data-stu-id="bff6e-109">sqlncli.h must be included in the ODBC application performing bulk copy operations and must be in the application's include path when it is compiled.</span></span>  
  
-   <span data-ttu-id="bff6e-110">sqlncli11.lib</span><span class="sxs-lookup"><span data-stu-id="bff6e-110">sqlncli11.lib</span></span>  
  
     <span data-ttu-id="bff6e-111">Должна находиться в пути к библиотекам компоновщика и определена как файл для связывания.</span><span class="sxs-lookup"><span data-stu-id="bff6e-111">Must be in the library path of the linker and specified as a file to be linked.</span></span> <span data-ttu-id="bff6e-112">Файл sqlncli11.lib поставляется вместе с драйвером ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="bff6e-112">sqlncli11.lib is distributed with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
-   <span data-ttu-id="bff6e-113">sqlncli11.dll</span><span class="sxs-lookup"><span data-stu-id="bff6e-113">sqlncli11.dll</span></span>  
  
     <span data-ttu-id="bff6e-114">Необходима во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="bff6e-114">Must be present at execution time.</span></span> <span data-ttu-id="bff6e-115">Файл sqlncli11.dll поставляется вместе с драйвером ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="bff6e-115">sqlncli11.dll is distributed with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bff6e-116">Функция ODBC **SQLBulkOperations** не имеет отношения к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] функциям с массовым копированием.</span><span class="sxs-lookup"><span data-stu-id="bff6e-116">The ODBC **SQLBulkOperations** function has no relationship to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bulk copy functions.</span></span> <span data-ttu-id="bff6e-117">Для выполнения операций массового копирования приложения должны использовать собственные функции массового копирования [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bff6e-117">Applications must use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific bulk-copy functions to perform bulk copy operations.</span></span>  
  
## <a name="minimally-logging-bulk-copies"></a><span data-ttu-id="bff6e-118">Массовое копирование с минимальным ведением журнала</span><span class="sxs-lookup"><span data-stu-id="bff6e-118">Minimally Logging Bulk Copies</span></span>  
 <span data-ttu-id="bff6e-119">В модели полного восстановления все операции вставки строк, выполняемые при массовой загрузке, полностью регистрируются в журнале транзакций.</span><span class="sxs-lookup"><span data-stu-id="bff6e-119">With the Full Recovery model, all row-insert operations performed by bulk load are fully logged in the transaction log.</span></span> <span data-ttu-id="bff6e-120">При загрузке большого количества данных это может привести к быстрому заполнению журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="bff6e-120">For large data loads, this can cause the transaction log to fill rapidly.</span></span> <span data-ttu-id="bff6e-121">При определенных условиях возможно минимальное протоколирование.</span><span class="sxs-lookup"><span data-stu-id="bff6e-121">Under certain conditions, minimally logging is possible.</span></span> <span data-ttu-id="bff6e-122">Минимальное ведение журнала снижает вероятность заполнения журнала в результате массовой загрузки и является также более эффективным, чем полное ведение журнала.</span><span class="sxs-lookup"><span data-stu-id="bff6e-122">Minimal logging reduces the possibility of a bulk load operation filling the log space and is also more efficient than full logging.</span></span>  
  
 <span data-ttu-id="bff6e-123">Сведения об использовании минимального ведения журнала см. [в разделе Предварительные требования для минимального ведения журнала при выполнении массового импорта](../import-export/prerequisites-for-minimal-logging-in-bulk-import.md).</span><span class="sxs-lookup"><span data-stu-id="bff6e-123">For information on using minimal logging, see [Prerequisites for Minimal Logging in Bulk Import](../import-export/prerequisites-for-minimal-logging-in-bulk-import.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bff6e-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="bff6e-124">Remarks</span></span>  
 <span data-ttu-id="bff6e-125">При использовании программы bcp.exe в [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] или более поздних версий могут возникать ошибки в ситуациях, в которых в версиях, предшествующих [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], ошибок не возникало.</span><span class="sxs-lookup"><span data-stu-id="bff6e-125">When using bcp.exe in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later, you might see errors in situations where there were no errors prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="bff6e-126">Это происходит по той причине, что в более поздних версиях программа bcp.exe больше не выполняет явное преобразование типов данных.</span><span class="sxs-lookup"><span data-stu-id="bff6e-126">This is because in the later versions, bcp.exe no longer performs implicit data type conversion.</span></span> <span data-ttu-id="bff6e-127">До версии [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] программа bcp.exe преобразовывала числовые данные в тип money, если целевая таблица имела тип данных money.</span><span class="sxs-lookup"><span data-stu-id="bff6e-127">Prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], bcp.exe converted numeric data to a money data type, if the target table had a money data type.</span></span> <span data-ttu-id="bff6e-128">Однако в этой ситуации программа bcp.exe просто усекала лишние поля.</span><span class="sxs-lookup"><span data-stu-id="bff6e-128">However, in that situation, bcp.exe simply truncated extra fields.</span></span> <span data-ttu-id="bff6e-129">Начиная с версии [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], если типы данных в файле и целевой таблице не совпадают, программа bcp.exe выдает ошибку, если присутствуют данные, которые придется усечь, чтобы поместить в целевую таблицу.</span><span class="sxs-lookup"><span data-stu-id="bff6e-129">Beginning in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], if data types do not match between the file and the target table, bcp.exe will raise an error if there is any data that would have to be truncated to fit into the target table.</span></span> <span data-ttu-id="bff6e-130">Для устранения этой ошибки преобразуйте данные в целевой тип данных.</span><span class="sxs-lookup"><span data-stu-id="bff6e-130">To resolve this error, fix the data to match the target data type.</span></span> <span data-ttu-id="bff6e-131">При необходимости используйте программу bcp.exe версии, предшествующей [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bff6e-131">Optionally, use bcp.exe from a release prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bff6e-132">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="bff6e-132">In This Section</span></span>  
  
-   [<span data-ttu-id="bff6e-133">Использование файлов данных и файлов форматирования</span><span class="sxs-lookup"><span data-stu-id="bff6e-133">Using Data Files and Format Files</span></span>](using-data-files-and-format-files.md)  
  
-   [<span data-ttu-id="bff6e-134">Массовое копирование из переменных приложения</span><span class="sxs-lookup"><span data-stu-id="bff6e-134">Bulk Copying from Program Variables</span></span>](bulk-copying-from-program-variables.md)  
  
-   [<span data-ttu-id="bff6e-135">Управление размером пакета массового копирования</span><span class="sxs-lookup"><span data-stu-id="bff6e-135">Managing Bulk Copy Batch Sizes</span></span>](managing-bulk-copy-batch-sizes.md)  
  
-   [<span data-ttu-id="bff6e-136">Массовое копирование данных text и image</span><span class="sxs-lookup"><span data-stu-id="bff6e-136">Bulk Copying Text and Image Data</span></span>](bulk-copying-text-and-image-data.md)  
  
-   [<span data-ttu-id="bff6e-137">Перевод массового копирования с DB-Library на ODBC</span><span class="sxs-lookup"><span data-stu-id="bff6e-137">Converting from DB-Library to ODBC Bulk Copy</span></span>](converting-from-db-library-to-odbc-bulk-copy.md)  
  
## <a name="see-also"></a><span data-ttu-id="bff6e-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="bff6e-138">See Also</span></span>  
 <span data-ttu-id="bff6e-139">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="bff6e-139">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 [<span data-ttu-id="bff6e-140">Массовый импорт и экспорт данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="bff6e-140">Bulk Import and Export of Data &#40;SQL Server&#41;</span></span>](../import-export/bulk-import-and-export-of-data-sql-server.md)  
  
  
