---
title: MSSQLSERVER_8992 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8992 (Database Engine error)
ms.assetid: 68467e6a-09d8-478f-8bd9-3bb09453ada3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: adcf914accab43202cf148fe852b334c9b078287
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669414"
---
# <a name="mssqlserver_8992"></a><span data-ttu-id="68b17-102">MSSQLSERVER_8992</span><span class="sxs-lookup"><span data-stu-id="68b17-102">MSSQLSERVER_8992</span></span>
    
## <a name="details"></a><span data-ttu-id="68b17-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="68b17-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="68b17-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="68b17-104">Product Name</span></span>|<span data-ttu-id="68b17-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="68b17-105">SQL Server</span></span>|  
|<span data-ttu-id="68b17-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="68b17-106">Event ID</span></span>|<span data-ttu-id="68b17-107">8992</span><span class="sxs-lookup"><span data-stu-id="68b17-107">8992</span></span>|  
|<span data-ttu-id="68b17-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="68b17-108">Event Source</span></span>|<span data-ttu-id="68b17-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="68b17-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="68b17-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="68b17-110">Component</span></span>|<span data-ttu-id="68b17-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="68b17-111">SQLEngine</span></span>|  
|<span data-ttu-id="68b17-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="68b17-112">Symbolic Name</span></span>|<span data-ttu-id="68b17-113">DBCC3_CHECK_CATALOG</span><span class="sxs-lookup"><span data-stu-id="68b17-113">DBCC3_CHECK_CATALOG</span></span>|  
|<span data-ttu-id="68b17-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="68b17-114">Message Text</span></span>|<span data-ttu-id="68b17-115">Проверьте сообщение каталога ERROR, уровень LEVEL, состояние STATE: MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="68b17-115">Check Catalog Msg ERROR Level LEVEL State STATE: MESSAGE.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="68b17-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="68b17-116">Explanation</span></span>  
 <span data-ttu-id="68b17-117">Инструкции DBCC CHECKCATALOG или DBCC CHECKDB обнаружили несогласованность в системных таблицах метаданных для указанного объекта.</span><span class="sxs-lookup"><span data-stu-id="68b17-117">DBCC CHECKCATALOG or DBCC CHECKDB found an inconsistency in the system metadata tables for the specified object.</span></span> <span data-ttu-id="68b17-118">То есть существует несогласованность между записанным идентификатором объекта и объектом, указанным в сообщении об ошибке.</span><span class="sxs-lookup"><span data-stu-id="68b17-118">That is, there is an inconsistency between the recorded object ID and the object specified in error message.</span></span>  
  
 <span data-ttu-id="68b17-119">Эта ошибка может произойти, если одна или несколько системных таблиц были обновлены вручную, в результате чего возникла несогласованность в системных метаданных.</span><span class="sxs-lookup"><span data-stu-id="68b17-119">This error can occur when one or more system tables has been manually updated in a way that creates an inconsistency in the system metadata.</span></span> <span data-ttu-id="68b17-120">Например, пользователь мог вручную удалить объект из таблицы **sysobjects**, не удалив связанные строки в других таблицах (например, **sysindexes** или **syscolumns**).</span><span class="sxs-lookup"><span data-stu-id="68b17-120">For example, a user may have manually deleted an object from the **sysobjects** table without removing associated rows in other tables such as **sysindexes** and **syscolumns**.</span></span>  
  
 <span data-ttu-id="68b17-121">Эта ошибка могла произойти при выполнении инструкции DBCC CHECKDB для базы данных, которая была обновлена с SQL Server 2000 до SQL Server 2005 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="68b17-121">This error can occur when running DBCC CHECKDB against a database that has been upgraded from SQL Server 2000 to SQL Server 2005 or later.</span></span> <span data-ttu-id="68b17-122">В SQL Server 2000 инструкция DBCC CHECKDB не включает функциональность DBCC CHECKCATALOG, таким образом, ошибка не будет выявлена до обновления, пока не будет специально выполнена инструкция DBCC CHECKCATALOG для базы данных SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="68b17-122">In SQL Server 2000, DBCC CHECKDB did not include DBCC CHECKCATALOG functionality, so the error would not be caught before upgrade unless DBCC CHECKCATALOG was specifically executed against the database in SQL Server 2000.</span></span>  
  
 <span data-ttu-id="68b17-123">Пользователь может видеть любую из следующих ошибок совместно с ошибкой 8992:</span><span class="sxs-lookup"><span data-stu-id="68b17-123">You may see any of the following errors in conjunction with error 8992:</span></span>  
  
 <span data-ttu-id="68b17-124">Сообщение 3851: недопустимая строка (%ls) обнаружена в системной таблице sys.%ls%ls.</span><span class="sxs-lookup"><span data-stu-id="68b17-124">Msg 3851 - An invalid row (%ls) was found in the system table sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="68b17-125">Сообщение 3852: строка (%ls) в sys.%ls%ls не имеет совпадающей строки (%ls) в sys.%ls%ls.</span><span class="sxs-lookup"><span data-stu-id="68b17-125">Msg 3852 - Row (%ls) in sys.%ls%ls does not have a matching row (%ls) in sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="68b17-126">3853: атрибут (%ls) строки (%ls) в sys.%ls%ls не имеет совпадающей строки (%ls) в sys.%ls%ls.</span><span class="sxs-lookup"><span data-stu-id="68b17-126">3853 - Attribute (%ls) of row (%ls) in sys.%ls%ls does not have a matching row (%ls) in sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="68b17-127">3854: атрибут (%ls) строки (%ls) в sys.%ls%ls имеет недопустимую совпадающую строку (%ls) в sys.%ls%ls.</span><span class="sxs-lookup"><span data-stu-id="68b17-127">3854 - Attribute (%ls) of row (%ls) in sys.%ls%ls has a matching row (%ls) in sys.%ls%ls that is invalid.</span></span>  
  
 <span data-ttu-id="68b17-128">3855: атрибут (%ls) существует без строки (%ls) в sys.%ls%ls.</span><span class="sxs-lookup"><span data-stu-id="68b17-128">3855 - Attribute (%ls) exists without a row (%ls) in sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="68b17-129">3856: атрибут (%ls) существует, но не должен существовать для строки (%ls) в sys.%ls%ls.</span><span class="sxs-lookup"><span data-stu-id="68b17-129">3856 - Attribute (%ls) exists but should not for row (%ls) in sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="68b17-130">3857: атрибут (%ls) необходим, но отсутствует для строки (%ls) в sys.%ls%ls.</span><span class="sxs-lookup"><span data-stu-id="68b17-130">3857 - The attribute (%ls) is required but is missing for row (%ls) in sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="68b17-131">3858: атрибут (%ls) строки (%ls) в sys.%ls%ls имеет недопустимое значение.</span><span class="sxs-lookup"><span data-stu-id="68b17-131">3858 - The attribute (%ls) of row (%ls) in sys.%ls%ls has an invalid value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="68b17-132">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="68b17-132">User Action</span></span>  
  
### <a name="drop-and-re-create-the-specified-object"></a><span data-ttu-id="68b17-133">Удалить и повторно создать указанный объект</span><span class="sxs-lookup"><span data-stu-id="68b17-133">Drop and Re-create the Specified Object</span></span>  
 <span data-ttu-id="68b17-134">Если возможно, удалите и повторно создайте указанный объект.</span><span class="sxs-lookup"><span data-stu-id="68b17-134">If possible, drop and recreate the specified object.</span></span> <span data-ttu-id="68b17-135">Например, если объект является хранимой процедурой или определяемым пользователем типом, повторное создание объекта может разрешить проблему.</span><span class="sxs-lookup"><span data-stu-id="68b17-135">For example, if the object is a stored procedure or user-defined type, recreating the object may resolve the problem.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="68b17-136">Восстановление из резервной копии</span><span class="sxs-lookup"><span data-stu-id="68b17-136">Restore from Backup</span></span>  
 <span data-ttu-id="68b17-137">Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.</span><span class="sxs-lookup"><span data-stu-id="68b17-137">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span> <span data-ttu-id="68b17-138">Это действие применимо, только если резервная копия не содержит ошибки метаданных.</span><span class="sxs-lookup"><span data-stu-id="68b17-138">This action is only applicable if the backup does not contain the metadata error.</span></span>  
  
### <a name="export-the-data-to-a-new-database"></a><span data-ttu-id="68b17-139">Экспорт данных в новую базу данных</span><span class="sxs-lookup"><span data-stu-id="68b17-139">Export the Data to a New Database</span></span>  
 <span data-ttu-id="68b17-140">Если резервная копия также содержит несогласованные метаданные, необходимо создать новую базу данных и экспортировать содержимое существующей базы данных в новую базу данных.</span><span class="sxs-lookup"><span data-stu-id="68b17-140">If the backup also contains the metadata inconsistency, you need to create a new database and export the contents of the existing database to the new database.</span></span>  
  
### <a name="dbcc-checkdb-cannot-repair-this-error"></a><span data-ttu-id="68b17-141">Операция DBCC CHECKDB не может исправить эту ошибку.</span><span class="sxs-lookup"><span data-stu-id="68b17-141">DBCC CHECKDB Cannot Repair This Error</span></span>  
 <span data-ttu-id="68b17-142">Эту ошибку исправить невозможно.</span><span class="sxs-lookup"><span data-stu-id="68b17-142">This error cannot be repaired.</span></span>  <span data-ttu-id="68b17-143">Если восстановить базу данных из резервной копии не удается, свяжитесь со службой поддержки пользователей [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="68b17-143">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
### <a name="do-not-manually-update-system-tables"></a><span data-ttu-id="68b17-144">Не обновляйте системные таблицы вручную</span><span class="sxs-lookup"><span data-stu-id="68b17-144">Do Not Manually Update System Tables</span></span>  
 <span data-ttu-id="68b17-145">Не вносите изменения в системные таблицы вручную.</span><span class="sxs-lookup"><span data-stu-id="68b17-145">Do not make manual updates to system tables.</span></span> <span data-ttu-id="68b17-146">SQL Server не поддерживает внесенных вручную каких-либо изменений в системные базы данных.</span><span class="sxs-lookup"><span data-stu-id="68b17-146">SQL Server does not support any manual changes to system databases.</span></span> <span data-ttu-id="68b17-147">В случае обновления системной таблицы в базе данных SQL Server в журнале регистрируются два события (идентификаторы событий 17659 и 3859).</span><span class="sxs-lookup"><span data-stu-id="68b17-147">If you update a system table in a SQL Server database, two events (event ID 17659 and event ID 3859) are logged.</span></span> <span data-ttu-id="68b17-148">Дополнительные сведения см. в статье базы знаний 2688307 «При обновлении системных таблиц в базе данных SQL Server регистрируются события с идентификаторами 17659 и 3859».</span><span class="sxs-lookup"><span data-stu-id="68b17-148">For more information, see KB article 2688307, "Event ID 17659 and event ID 3859 are logged when you update system tables in a SQL Server database".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68b17-149">См. также:</span><span class="sxs-lookup"><span data-stu-id="68b17-149">See Also</span></span>  
 <span data-ttu-id="68b17-150">[При обновлении системных таблиц в базе данных SQL Server в журнале регистрируются события с идентификаторами 17659 и 3859](https://support.microsoft.com/kb/2688307/EN-US).</span><span class="sxs-lookup"><span data-stu-id="68b17-150">[Event ID 17659 and event ID 3859 are logged when you update system tables in a SQL Server database](https://support.microsoft.com/kb/2688307/EN-US)</span></span>  
  
  
