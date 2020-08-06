---
title: MSSQLSERVER_1222 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1222 (Database Engine error)
ms.assetid: c5b1c2f4-f591-4cc1-aa17-204636a27f29
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ac3fe9314386836633a11f17d6775c75019de93a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654324"
---
# <a name="mssqlserver_1222"></a><span data-ttu-id="3f0f7-102">MSSQLSERVER_1222</span><span class="sxs-lookup"><span data-stu-id="3f0f7-102">MSSQLSERVER_1222</span></span>
    
## <a name="details"></a><span data-ttu-id="3f0f7-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="3f0f7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3f0f7-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="3f0f7-104">Product Name</span></span>|<span data-ttu-id="3f0f7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3f0f7-105">SQL Server</span></span>|  
|<span data-ttu-id="3f0f7-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="3f0f7-106">Event ID</span></span>|<span data-ttu-id="3f0f7-107">1222</span><span class="sxs-lookup"><span data-stu-id="3f0f7-107">1222</span></span>|  
|<span data-ttu-id="3f0f7-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="3f0f7-108">Event Source</span></span>|<span data-ttu-id="3f0f7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3f0f7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3f0f7-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="3f0f7-110">Component</span></span>|<span data-ttu-id="3f0f7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="3f0f7-111">SQLEngine</span></span>|  
|<span data-ttu-id="3f0f7-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="3f0f7-112">Symbolic Name</span></span>|<span data-ttu-id="3f0f7-113">LK_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3f0f7-113">LK_TIMEOUT</span></span>|  
|<span data-ttu-id="3f0f7-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="3f0f7-114">Message Text</span></span>|<span data-ttu-id="3f0f7-115">Истекло время ожидания запроса на блокировку.</span><span class="sxs-lookup"><span data-stu-id="3f0f7-115">Lock request time out period exceeded.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3f0f7-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="3f0f7-116">Explanation</span></span>  
 <span data-ttu-id="3f0f7-117">Другая транзакция удерживает блокировку требуемого ресурса дольше, чем данный запрос может ее ожидать.</span><span class="sxs-lookup"><span data-stu-id="3f0f7-117">Another transaction held a lock on a required resource longer than this query could wait for it.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3f0f7-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="3f0f7-118">User Action</span></span>  
 <span data-ttu-id="3f0f7-119">Для решения проблемы попробуйте выполнить следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="3f0f7-119">Perform the following tasks to alleviate the problem:</span></span>  
  
1.  <span data-ttu-id="3f0f7-120">Если это возможно, найдите на требуемом ресурсе транзакцию, удерживающую эту блокировку.</span><span class="sxs-lookup"><span data-stu-id="3f0f7-120">Locate the transaction that is holding the lock on the required resource, if possible.</span></span> <span data-ttu-id="3f0f7-121">Используйте динамические административные представления **sys.dm_os_waiting_tasks** и **sys.dm_tran_locks**.</span><span class="sxs-lookup"><span data-stu-id="3f0f7-121">Use **sys.dm_os_waiting_tasks** and **sys.dm_tran_locks** dynamic management views.</span></span>  
  
2.  <span data-ttu-id="3f0f7-122">Если транзакция все еще удерживает блокировку, завершите эту транзакцию, если это адекватно.</span><span class="sxs-lookup"><span data-stu-id="3f0f7-122">If the transaction is still holding the lock, terminate that transaction if appropriate.</span></span>  
  
3.  <span data-ttu-id="3f0f7-123">Выполните запрос еще раз.</span><span class="sxs-lookup"><span data-stu-id="3f0f7-123">Execute the query again.</span></span>  
  
 <span data-ttu-id="3f0f7-124">Если данная ошибка возникает часто, измените время ожидания блокировки или вызывающие ошибку транзакции так, чтобы они удерживали блокировку на меньший период времени.</span><span class="sxs-lookup"><span data-stu-id="3f0f7-124">If this error occurs frequently change the lock time-out period or modify the offending transactions so that they hold the lock for less time.</span></span>  
  
  
