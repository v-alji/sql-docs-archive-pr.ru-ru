---
title: Настройка параметров сбора данных (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- data collection [SQL Server]
ms.assetid: 850905b6-35d2-4ed1-ab51-de64daa832b2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a8333b47612b4fbd933ef132e886b8125ffb58a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734150"
---
# <a name="configure-data-collection-parameters-transact-sql"></a><span data-ttu-id="120c0-102">Настройка параметров сбора данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="120c0-102">Configure Data Collection Parameters (Transact-SQL)</span></span>
  <span data-ttu-id="120c0-103">Перед созданием пользовательского набора сбора необходимо настроить параметры сбора данных.</span><span class="sxs-lookup"><span data-stu-id="120c0-103">Before you create a custom collection set, you must first configure data collection parameters.</span></span> <span data-ttu-id="120c0-104">Это делается с помощью хранимых процедур, предоставляемых со сборщиком данных.</span><span class="sxs-lookup"><span data-stu-id="120c0-104">You can do this by using the stored procedures that are provided with the data collector.</span></span> <span data-ttu-id="120c0-105">Эта задача решается с помощью редактора запросов в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] для выполнения следующей процедуры.</span><span class="sxs-lookup"><span data-stu-id="120c0-105">Accomplishing this task involves using Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to carry out the following procedure.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="120c0-106">Параметры сбора данных можно настроить только один раз.</span><span class="sxs-lookup"><span data-stu-id="120c0-106">You only configure data collection parameters once.</span></span> <span data-ttu-id="120c0-107">После настройки эти параметры будут использоваться для всех создаваемых дополнительных наборов сбора.</span><span class="sxs-lookup"><span data-stu-id="120c0-107">After configuration, these parameters are used for any additional collection sets that you create.</span></span>  
  
### <a name="configure-data-collection-parameters"></a><span data-ttu-id="120c0-108">Настройка параметров сбора данных</span><span class="sxs-lookup"><span data-stu-id="120c0-108">Configure data collection parameters</span></span>  
  
1.  <span data-ttu-id="120c0-109">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]подключитесь к базе данных, в которой будет создан пользовательский набор сбора.</span><span class="sxs-lookup"><span data-stu-id="120c0-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the database where you want to create a custom collection set.</span></span>  
  
2.  <span data-ttu-id="120c0-110">В редакторе запросов выполните следующие инструкции.</span><span class="sxs-lookup"><span data-stu-id="120c0-110">In Query Editor, issue the following statements.</span></span>  
  
    ```sql  
    USE msdb;  
    EXEC sp_syscollector_set_warehouse_instance_name N'INSTANCE_NAME';-- where instance name is the name of the SQL Server instance  
    EXEC sp_syscollector_set_warehouse_database_name N'MDW';  
    EXEC sp_syscollector_set_cache_directory N'D:\tempdata';  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="120c0-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="120c0-111">See Also</span></span>  
 <span data-ttu-id="120c0-112">[Сбор данных](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="120c0-112">[Data Collection](data-collection.md) </span></span>  
 [<span data-ttu-id="120c0-113">Хранимые процедуры сборщика данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="120c0-113">Data Collector Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql)  
  
  
