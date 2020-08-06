---
title: Выполнить массовый загрузку данных в таблицы в публикации слиянием (программирование репликации на языке Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- bulk load [SQL Server replication]
- merge replication bulk loading [SQL Server replication]
- sp_addtabletocontents
ms.assetid: 16e6498a-b449-4051-aec4-ea814a2ad993
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f669a1f7132aa0f588fd89fb9747a7dc9017fcf1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750755"
---
# <a name="bulk-load-data-into-tables-in-a-merge-publication-replication-transact-sql-programming"></a><span data-ttu-id="23f44-102">выполнить массовую загрузку данных в таблицы при публикации слиянием (программирование репликации на языке Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="23f44-102">Bulk-Load Data into Tables in a Merge Publication (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="23f44-103">При загрузке данных в таблицы с использованием методов, описанных в разделе [bcp Utility](../../tools/bcp-utility.md) , или инструкцией [BULK INSERT](/sql/t-sql/statements/bulk-insert-transact-sql) триггеры репликации слиянием, которые обеспечивают отслеживание данных в системной таблице [MSmerge_contents](/sql/relational-databases/system-tables/msmerge-contents-transact-sql) , выполняться не будут.</span><span class="sxs-lookup"><span data-stu-id="23f44-103">When data is loaded into tables using the [bcp Utility](../../tools/bcp-utility.md) or the [BULK INSERT](/sql/t-sql/statements/bulk-insert-transact-sql) command, by default, the merge replication triggers that maintain tracking data in the [MSmerge_contents](/sql/relational-databases/system-tables/msmerge-contents-transact-sql) system table are not fired.</span></span> <span data-ttu-id="23f44-104">В этом случае можно либо принудительно выполнять в процессе загрузки данных триггеры репликации слиянием, либо с помощью хранимых процедур репликации программным путем вставить созданные метаданные репликации после завершения массового копирования.</span><span class="sxs-lookup"><span data-stu-id="23f44-104">You can either force the merge replication triggers to fire as the data is loaded, or you can insert the generated replication metadata programmatically after the bulk copy operation using replication stored procedures.</span></span>  
  
### <a name="to-bulk-load-data-into-tables-published-by-merge-replication-using-the-bcp-utility"></a><span data-ttu-id="23f44-105">Массовая загрузка данных в таблицы, публикуемые в репликации слиянием с помощью программы bcp</span><span class="sxs-lookup"><span data-stu-id="23f44-105">To bulk-load data into tables published by merge replication using the bcp utility</span></span>  
  
1.  <span data-ttu-id="23f44-106">На издателе или на подписчике запустите программу [bcp Utility](../../tools/bcp-utility.md) или выполните инструкцию [BULK INSERT](/sql/t-sql/statements/bulk-insert-transact-sql) , чтобы вставить данные в таблицу, публикуемую в репликации слиянием.</span><span class="sxs-lookup"><span data-stu-id="23f44-106">At either the Publisher or Subscriber, execute the [bcp Utility](../../tools/bcp-utility.md) or [BULK INSERT](/sql/t-sql/statements/bulk-insert-transact-sql) to insert data into a table published using merge replication.</span></span>  
  
2.  <span data-ttu-id="23f44-107">Одним из следующих методов сформируйте для вставленных данных метаданные репликации.</span><span class="sxs-lookup"><span data-stu-id="23f44-107">Use one of the following methods to ensure that replication metadata is generated for the inserted data.</span></span>  
  
    -   <span data-ttu-id="23f44-108">Выполните операцию массового копирования с параметром FIRE_TRIGGERS.</span><span class="sxs-lookup"><span data-stu-id="23f44-108">Execute the bulk copy using the FIRE_TRIGGERS option.</span></span>  
  
    -   <span data-ttu-id="23f44-109">В базе данных, в которую вставлены данные, выполните процедуру [sp_addtabletocontents (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-addtabletocontents-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="23f44-109">On the database into which data was inserted, execute [sp_addtabletocontents &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addtabletocontents-transact-sql).</span></span> <span data-ttu-id="23f44-110">Укажите имя таблицы, в которую вставляются данные **@table_name** .</span><span class="sxs-lookup"><span data-stu-id="23f44-110">Specify the table name into which the data was inserted for **@table_name**.</span></span>  
  
  
