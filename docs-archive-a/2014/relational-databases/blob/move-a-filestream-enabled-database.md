---
title: Перемещение базы данных с поддержкой FILESTREAM | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], moving a FILESTREAM-enabled database
ms.assetid: dd4d270d-9283-431a-aa6b-e571fced1893
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 79740ee86a89566113650865e3fd6ec54c7cb918
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728370"
---
# <a name="move-a-filestream-enabled-database"></a><span data-ttu-id="a0176-102">переместить базу данных с поддержкой FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="a0176-102">Move a FILESTREAM-Enabled Database</span></span>
  <span data-ttu-id="a0176-103">В этом разделе показано перемещение базы данных с поддержкой FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="a0176-103">This topic shows how to move a FILESTREAM-enabled database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a0176-104">В примерах этого раздела требуется база данных Archive, созданная в разделе [Создание базы данных с поддержкой FILESTREAM](create-a-filestream-enabled-database.md).</span><span class="sxs-lookup"><span data-stu-id="a0176-104">The examples in this topic require the Archive database that is created in [Create a FILESTREAM-Enabled Database](create-a-filestream-enabled-database.md).</span></span>  
  
### <a name="to-move-a-filestream-enabled-database"></a><span data-ttu-id="a0176-105">Перемещение базы данных с поддержкой FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="a0176-105">To move a FILESTREAM-enabled database</span></span>  
  
1.  <span data-ttu-id="a0176-106">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]нажмите кнопку **Создать запрос** , чтобы открыть редактор запросов.</span><span class="sxs-lookup"><span data-stu-id="a0176-106">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], click **New Query** to open the Query Editor.</span></span>  
  
2.  <span data-ttu-id="a0176-107">Скопируйте следующий скрипт [!INCLUDE[tsql](../../includes/tsql-md.md)] в редактор запросов и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="a0176-107">Copy the following [!INCLUDE[tsql](../../includes/tsql-md.md)] script into the Query Editor, and then click **Execute**.</span></span> <span data-ttu-id="a0176-108">Этот скрипт показывает расположение физических файлов базы данных, который использует база данных FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="a0176-108">This script displays the location of the physical database files that the FILESTREAM database uses.</span></span>  
  
    ```sql  
    USE Archive  
    GO  
    SELECT type_desc, name, physical_name from sys.database_files  
    ```  
  
3.  <span data-ttu-id="a0176-109">Скопируйте следующий скрипт [!INCLUDE[tsql](../../includes/tsql-md.md)] в редактор запросов и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="a0176-109">Copy the following [!INCLUDE[tsql](../../includes/tsql-md.md)] script into the Query Editor, and then click **Execute**.</span></span> <span data-ttu-id="a0176-110">Этот код переводит базу данных `Archive` в режим вне сети.</span><span class="sxs-lookup"><span data-stu-id="a0176-110">This code takes the `Archive` database offline.</span></span>  
  
    ```sql  
    USE master  
    EXEC sp_detach_db Archive  
    GO  
    ```  
  
4.  <span data-ttu-id="a0176-111">Создайте папку `C:\moved_location`и переместите в нее файлы и папки, перечисленные на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="a0176-111">Create the folder `C:\moved_location`, and then move the files and folders that are listed in step 2 into it.</span></span>  
  
5.  <span data-ttu-id="a0176-112">Скопируйте следующий скрипт [!INCLUDE[tsql](../../includes/tsql-md.md)] в редактор запросов и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="a0176-112">Copy the following [!INCLUDE[tsql](../../includes/tsql-md.md)] script into the Query Editor, and then click **Execute**.</span></span> <span data-ttu-id="a0176-113">Этот скрипт переводит базу данных `Archive` в режим «в сети».</span><span class="sxs-lookup"><span data-stu-id="a0176-113">This script sets the `Archive` database online.</span></span>  
  
    ```sql  
    CREATE DATABASE Archive ON  
    PRIMARY ( NAME = Arch1,  
        FILENAME = 'c:\moved_location\archdat1.mdf'),  
    FILEGROUP FileStreamGroup1 CONTAINS FILESTREAM( NAME = Arch3,  
        FILENAME = 'c:\moved_location\filestream1')  
    LOG ON  ( NAME = Archlog1,  
        FILENAME = 'c:\moved_location\archlog1.ldf')  
    FOR ATTACH  
    GO  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a0176-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="a0176-114">See Also</span></span>  
 [<span data-ttu-id="a0176-115">sp_detach_db (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a0176-115">sp_detach_db &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-detach-db-transact-sql)  
  
  
