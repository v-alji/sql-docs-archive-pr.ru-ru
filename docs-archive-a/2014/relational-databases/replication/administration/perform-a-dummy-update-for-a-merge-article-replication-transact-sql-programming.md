---
title: Выполнить фиктивное обновление для статьи публикации слиянием (программирование репликации на языке Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- sp_mergedummyupdate
- dummy updates [SQL Server replication]
ms.assetid: 2f339210-4d85-4843-bd94-e86f7100d3ef
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 07fa0f868b2c3f98496046b138424d7d3a2fa2fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736272"
---
# <a name="perform-a-dummy-update-for-a-merge-article-replication-transact-sql-programming"></a><span data-ttu-id="4029f-102">выполнить фиктивное обновление для статьи репликации слиянием (программирование репликации на языке Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4029f-102">Perform a Dummy Update for a Merge Article (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="4029f-103">Триггеры являются частью процесса репликации слиянием. При обновлении опубликованной таблицы, срабатывают триггеры Update.</span><span class="sxs-lookup"><span data-stu-id="4029f-103">Merge replication uses triggers as part of the replication process; when an update is made to published table, an update trigger fires.</span></span> <span data-ttu-id="4029f-104">В некоторых случаях данные могут обновляться без срабатывания триггеров, например, при выполнении операций WRITETEXT и UPDATETEXT.</span><span class="sxs-lookup"><span data-stu-id="4029f-104">In some cases, data can be updated without the trigger firing, such as during the WRITETEXT and UPDATETEXT operations.</span></span> <span data-ttu-id="4029f-105">В таких случаях для репликации изменения необходимо явно добавить фиктивную инструкцию UPDATE.</span><span class="sxs-lookup"><span data-stu-id="4029f-105">In these cases, you need to add a dummy UPDATE statement explicitly to replicate the change.</span></span> <span data-ttu-id="4029f-106">Это можно сделать с помощью хранимых процедур репликации.</span><span class="sxs-lookup"><span data-stu-id="4029f-106">You can add a dummy UPDATE statement using replication stored procedures.</span></span>  
  
### <a name="to-add-a-dummy-update-statement"></a><span data-ttu-id="4029f-107">Добавление фиктивной инструкции UPDATE</span><span class="sxs-lookup"><span data-stu-id="4029f-107">To add a dummy UPDATE statement</span></span>  
  
1.  <span data-ttu-id="4029f-108">Выполните операцию (например UPDATETEXT) для строки таблицы, опубликованной в репликации слияния, требующую фиктивного обновления.</span><span class="sxs-lookup"><span data-stu-id="4029f-108">Execute the operation (for example, UPDATETEXT) on a row in a merge published table  that requires a dummy update.</span></span>  
  
2.  <span data-ttu-id="4029f-109">На сервере (издателя или подписчика) в той базе данных, где было сделано изменение, выполните процедуру [sp_mergedummyupdate &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-mergedummyupdate-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4029f-109">At the server (Publisher or Subscriber) on the database where the change was made, execute [sp_mergedummyupdate &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-mergedummyupdate-transact-sql).</span></span> <span data-ttu-id="4029f-110">Укажите таблицу, в которой было внесено изменение **@source_object** , и уникальный идентификатор измененной строки для **@rowguid** .</span><span class="sxs-lookup"><span data-stu-id="4029f-110">Specify the table on which the change was made for **@source_object**, and the unique identifier of the changed row for **@rowguid**.</span></span>  
  
3.  <span data-ttu-id="4029f-111">Синхронизируйте подписку для репликации измененной строки.</span><span class="sxs-lookup"><span data-stu-id="4029f-111">Synchronize the subscription to replicate the changed row.</span></span>  
  
  
