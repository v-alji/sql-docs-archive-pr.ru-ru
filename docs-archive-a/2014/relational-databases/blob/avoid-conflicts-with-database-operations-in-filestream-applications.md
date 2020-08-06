---
title: Предотвращение конфликтов при работе с базой данных в приложениях FILESTREAM | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: filestream
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], Win32 and Transact-SQL Conflicts
ms.assetid: 8b1ee196-69af-4f9b-9bf5-63d8ac2bc39b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0ac7e681766396d3a3b4412d91a968b4cdc653c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667248"
---
# <a name="avoid-conflicts-with-database-operations-in-filestream-applications"></a><span data-ttu-id="25b0f-102">Избегание конфликтов в операциях баз данных в приложениях FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="25b0f-102">Avoid Conflicts with Database Operations in FILESTREAM Applications</span></span>
  <span data-ttu-id="25b0f-103">Приложения, использующие функцию SqlOpenFilestream() для открытия дескрипторов файлов Win32 для считывания или записи данных FILESTREAM BLOB, могут столкнуться с конфликтами при работе с инструкциями [!INCLUDE[tsql](../../includes/tsql-md.md)] , использованными в общей транзакции.</span><span class="sxs-lookup"><span data-stu-id="25b0f-103">Applications that use SqlOpenFilestream() to open Win32 file handles for reading or writing FILESTREAM BLOB data can encounter conflict errors with [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that are managed in a common transaction.</span></span> <span data-ttu-id="25b0f-104">Это также относится и к запросам [!INCLUDE[tsql](../../includes/tsql-md.md)] или MARS, выполнение которых занимает много времени.</span><span class="sxs-lookup"><span data-stu-id="25b0f-104">This includes [!INCLUDE[tsql](../../includes/tsql-md.md)] or MARS queries that take a long time to finish execution.</span></span> <span data-ttu-id="25b0f-105">При разработке приложений надо уделить особое внимание предотвращению данных типов конфликтов.</span><span class="sxs-lookup"><span data-stu-id="25b0f-105">Applications must be carefully designed to help avoid these types of conflicts.</span></span>  
  
 <span data-ttu-id="25b0f-106">Если компонент [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] или приложения пытаются открыть объекты FILESTREAM BLOB, то компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] выполнит проверку контекста ассоциированной транзакции.</span><span class="sxs-lookup"><span data-stu-id="25b0f-106">When [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] or applications try to open FILESTREAM BLOBs, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] checks the associated transaction context.</span></span> <span data-ttu-id="25b0f-107">Компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] разрешит или запретит запрос в зависимости от того, работает ли операция открытия с инструкциями DDL, инструкциями DML, получает данные или управляет транзакциями.</span><span class="sxs-lookup"><span data-stu-id="25b0f-107">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] allows or denies the request based on whether the open operation is working with DDL statements, DML statements, retrieving data, or managing transactions.</span></span> <span data-ttu-id="25b0f-108">В следующей таблице показывается, как компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] определяет, следует ли разрешить или запретить инструкцию [!INCLUDE[tsql](../../includes/tsql-md.md)] , основываясь на типе файлов, открытых в транзакции.</span><span class="sxs-lookup"><span data-stu-id="25b0f-108">The following table shows how the [!INCLUDE[ssDE](../../includes/ssde-md.md)] determines whether a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement will be allowed or denied based on the type of files that are open in the transaction.</span></span>  
  
|<span data-ttu-id="25b0f-109">Инструкции Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="25b0f-109">Transact-SQL statements</span></span>|<span data-ttu-id="25b0f-110">Открыты для чтения</span><span class="sxs-lookup"><span data-stu-id="25b0f-110">Opened for read</span></span>|<span data-ttu-id="25b0f-111">Открыты для записи</span><span class="sxs-lookup"><span data-stu-id="25b0f-111">Opened for write</span></span>|  
|------------------------------|---------------------|----------------------|  
|<span data-ttu-id="25b0f-112">Инструкции DDL, работающие с метаданными базы данных, например CREATE TABLE, CREATE INDEX, DROP TABLE и ALTER TABLE.</span><span class="sxs-lookup"><span data-stu-id="25b0f-112">DDL statements that work with database metadata, such as CREATE TABLE, CREATE INDEX, DROP TABLE, and ALTER TABLE.</span></span>|<span data-ttu-id="25b0f-113">Разрешено</span><span class="sxs-lookup"><span data-stu-id="25b0f-113">Allowed</span></span>|<span data-ttu-id="25b0f-114">Заблокированы и завершаются со сбоем по истечении времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="25b0f-114">Are blocked and fail with a time-out.</span></span>|  
|<span data-ttu-id="25b0f-115">Инструкции DML, работающие с данными, хранящимися в базе данных, например UPDATE, DELETE и INSERT.</span><span class="sxs-lookup"><span data-stu-id="25b0f-115">DML statements that work with the data that is stored in the database, such as UPDATE, DELETE, and INSERT.</span></span>|<span data-ttu-id="25b0f-116">Разрешено</span><span class="sxs-lookup"><span data-stu-id="25b0f-116">Allowed</span></span>|<span data-ttu-id="25b0f-117">Запрещены</span><span class="sxs-lookup"><span data-stu-id="25b0f-117">Denied</span></span>|  
|<span data-ttu-id="25b0f-118">SELECT</span><span class="sxs-lookup"><span data-stu-id="25b0f-118">SELECT</span></span>|<span data-ttu-id="25b0f-119">Разрешено</span><span class="sxs-lookup"><span data-stu-id="25b0f-119">Allowed</span></span>|<span data-ttu-id="25b0f-120">Разрешено</span><span class="sxs-lookup"><span data-stu-id="25b0f-120">Allowed</span></span>|  
|<span data-ttu-id="25b0f-121">COMMIT TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="25b0f-121">COMMIT TRANSACTION</span></span>|<span data-ttu-id="25b0f-122">Запрещены\*</span><span class="sxs-lookup"><span data-stu-id="25b0f-122">Denied\*</span></span>|<span data-ttu-id="25b0f-123">Запрещены\*</span><span class="sxs-lookup"><span data-stu-id="25b0f-123">Denied\*.</span></span>|  
|<span data-ttu-id="25b0f-124">SAVE TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="25b0f-124">SAVE TRANSACTION</span></span>|<span data-ttu-id="25b0f-125">Запрещены\*</span><span class="sxs-lookup"><span data-stu-id="25b0f-125">Denied\*</span></span>|<span data-ttu-id="25b0f-126">Запрещены\*</span><span class="sxs-lookup"><span data-stu-id="25b0f-126">Denied\*</span></span>|  
|<span data-ttu-id="25b0f-127">ROLLBACK</span><span class="sxs-lookup"><span data-stu-id="25b0f-127">ROLLBACK</span></span>|<span data-ttu-id="25b0f-128">Разрешено\*</span><span class="sxs-lookup"><span data-stu-id="25b0f-128">Allowed\*</span></span>|<span data-ttu-id="25b0f-129">Разрешено\*</span><span class="sxs-lookup"><span data-stu-id="25b0f-129">Allowed\*</span></span>|  
  
 <span data-ttu-id="25b0f-130">\* Транзакция отменяется, а открытые дескрипторы для контекста транзакции становятся недействительными.</span><span class="sxs-lookup"><span data-stu-id="25b0f-130">\* The transaction is canceled, and open handles for the transaction context are invalidated.</span></span> <span data-ttu-id="25b0f-131">Приложение должно закрыть все открытые дескрипторы.</span><span class="sxs-lookup"><span data-stu-id="25b0f-131">The application must close all open handles.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="25b0f-132">Примеры</span><span class="sxs-lookup"><span data-stu-id="25b0f-132">Examples</span></span>  
 <span data-ttu-id="25b0f-133">В следующих примерах показывается, как могут возникать конфликты при совместном использовании инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] и доступа к FILESTREAM с помощью функций Win32.</span><span class="sxs-lookup"><span data-stu-id="25b0f-133">The following examples show how [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and FILESTREAM Win32 access can cause conflicts.</span></span>  
  
### <a name="a-opening-a-filestream-blob-for-write-access"></a><span data-ttu-id="25b0f-134">A.</span><span class="sxs-lookup"><span data-stu-id="25b0f-134">A.</span></span> <span data-ttu-id="25b0f-135">Открытие объекта FILESTREAM BLOB с доступом на запись</span><span class="sxs-lookup"><span data-stu-id="25b0f-135">Opening a FILESTREAM BLOB for write access</span></span>  
 <span data-ttu-id="25b0f-136">В следующем примере показывается эффект от открытия файла с доступом только на запись.</span><span class="sxs-lookup"><span data-stu-id="25b0f-136">The following example shows the effect of opening a file for write access only.</span></span>  
  
```  
dstHandle =  OpenSqlFilestream(dstFilePath, Write, 0,  
    transactionToken, cbTransactionToken, 0);  
  
//Write some date to the FILESTREAM BLOB.  
WriteFile(dstHandle, updateData, ...);  
  
//DDL statements will be denied.  
//DML statements will be denied.  
//SELECT statements will be allowed. The FILESTREAM BLOB is  
//returned without the modifications that are made by  
//WriteFile(dstHandle, updateData, ...).  
CloseHandle(dstHandle);  
  
//DDL statements will be allowed.  
//DML statements will be allowed.  
//SELECT statements will be allowed. The FILESTREAM BLOB  
//is returned with the updateData applied.  
```  
  
### <a name="b-opening-a-filestream-blob-for-read-access"></a><span data-ttu-id="25b0f-137">Б.</span><span class="sxs-lookup"><span data-stu-id="25b0f-137">B.</span></span> <span data-ttu-id="25b0f-138">Открытие объекта FILESTREAM BLOB с доступом на считывание</span><span class="sxs-lookup"><span data-stu-id="25b0f-138">Opening a FILESTREAM BLOB for read access</span></span>  
 <span data-ttu-id="25b0f-139">В следующем примере показывается эффект от открытия файла с доступом только на считывание.</span><span class="sxs-lookup"><span data-stu-id="25b0f-139">The following example shows the effect of opening a file for read access only.</span></span>  
  
```  
dstHandle =  OpenSqlFilestream(dstFilePath, Read, 0,  
    transactionToken, cbTransactionToken, 0);  
//DDL statements will be denied.  
//DML statements will be allowed. Any changes that are  
//made to the FILESTREAM BLOB will not be returned until  
//the dstHandle is closed.  
//SELECT statements will be allowed.  
CloseHandle(dstHandle);  
  
//DDL statements will be allowed.  
//DML statements will be allowed.  
//SELECT statements will be allowed.  
```  
  
### <a name="c-opening-and-closing-multiple-filestream-blob-files"></a><span data-ttu-id="25b0f-140">В.</span><span class="sxs-lookup"><span data-stu-id="25b0f-140">C.</span></span> <span data-ttu-id="25b0f-141">Открытие и закрытие нескольких файлов FILESTREAM BLOB</span><span class="sxs-lookup"><span data-stu-id="25b0f-141">Opening and closing multiple FILESTREAM BLOB files</span></span>  
 <span data-ttu-id="25b0f-142">Если открыто несколько файлов, то используется правило с наибольшими ограничениями.</span><span class="sxs-lookup"><span data-stu-id="25b0f-142">If multiple files are open, the most restrictive rule is used.</span></span> <span data-ttu-id="25b0f-143">В следующем примере открываются два файла.</span><span class="sxs-lookup"><span data-stu-id="25b0f-143">The following example opens two files.</span></span> <span data-ttu-id="25b0f-144">Первый файл открывается для чтения, а второй — для записи.</span><span class="sxs-lookup"><span data-stu-id="25b0f-144">The first file is opened for read and the second for write.</span></span> <span data-ttu-id="25b0f-145">Инструкции DML будут запрещены, пока не будет открыт второй файл.</span><span class="sxs-lookup"><span data-stu-id="25b0f-145">DML statements will be denied until the second file is opened.</span></span>  
  
```  
dstHandle =  OpenSqlFilestream(dstFilePath, Read, 0,  
    transactionToken, cbTransactionToken, 0);  
//DDL statements will be denied.  
//DML statements will be allowed.  
//SELECT statements will be allowed.  
  
dstHandle1 =  OpenSqlFilestream(dstFilePath1, Write, 0,  
    transactionToken, cbTransactionToken, 0);  
  
//DDL statements will be denied.  
//DML statements will be denied.  
//SELECT statements will be allowed.  
  
//Close the read handle. The write handle is still open.  
CloseHandle(dstHandle);  
//DML statements are still denied because the write handle is open.  
  
//DDL statements will be denied.  
//DML statements will be denied.  
//SELECT statements will be allowed.  
  
CloseHandle(dstHandle1);  
//DDL statements will be allowed.  
//DML statements will be allowed.  
//SELECT statements will be allowed.  
```  
  
### <a name="d-failing-to-close-a-cursor"></a><span data-ttu-id="25b0f-146">Г.</span><span class="sxs-lookup"><span data-stu-id="25b0f-146">D.</span></span> <span data-ttu-id="25b0f-147">Сбой при закрытии курсора</span><span class="sxs-lookup"><span data-stu-id="25b0f-147">Failing to close a cursor</span></span>  
 <span data-ttu-id="25b0f-148">В следующем примере показывается, как незакрытый курсор инструкции может помешать функции `OpenSqlFilestream()` открыть объект BLOB для доступа на запись.</span><span class="sxs-lookup"><span data-stu-id="25b0f-148">The following example shows how a statement cursor that is not closed can prevent `OpenSqlFilestream()` from opening the BLOB for write access.</span></span>  
  
```  
TCHAR *sqlDBQuery =  
TEXT("SELECT GET_FILESTREAM_TRANSACTION_CONTEXT(),")  
TEXT("Chart.PathName() FROM Archive.dbo.Records");  
  
//Execute a long-running Transact-SQL statement. Do not allow  
//the statement to complete before trying to  
//open the file.  
  
SQLExecDirect(hstmt, sqlDBQuery, SQL_NTS);  
  
//Before you call OpenSqlFilestream() any open files  
//that the Cursor the Transact-SQL statement is using  
// must be closed. In this example,  
//SQLCloseCursor(hstmt) is not called so that  
//the transaction will indicate that there is a file  
//open for reading. This will cause the call to  
//OpenSqlFilestream() to fail because the file is  
//still open.  
  
HANDLE srcHandle =  OpenSqlFilestream(srcFilePath,  
     Write, 0,  transactionToken,  cbTransactionToken,  0);  
  
//srcHandle will == INVALID_HANDLE_VALUE because the  
//cursor is still open.  
```  
  
## <a name="see-also"></a><span data-ttu-id="25b0f-149">См. также:</span><span class="sxs-lookup"><span data-stu-id="25b0f-149">See Also</span></span>  
 <span data-ttu-id="25b0f-150">[Доступ к данным FILESTREAM с OpenSqlFilestream](access-filestream-data-with-opensqlfilestream.md) </span><span class="sxs-lookup"><span data-stu-id="25b0f-150">[Access FILESTREAM Data with OpenSqlFilestream](access-filestream-data-with-opensqlfilestream.md) </span></span>  
 [<span data-ttu-id="25b0f-151">Использование множественных активных результирующих наборов (MARS)</span><span class="sxs-lookup"><span data-stu-id="25b0f-151">Using Multiple Active Result Sets &#40;MARS&#41;</span></span>](../native-client/features/using-multiple-active-result-sets-mars.md)  
  
  
