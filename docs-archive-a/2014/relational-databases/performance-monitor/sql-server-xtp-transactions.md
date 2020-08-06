---
title: Транзакции XTP | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 443d67e4-1c7f-41d7-b18d-2d657f58c22a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 75fa8bc9a673d9e0e018b8578a35af2e46b5044c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730562"
---
# <a name="xtp-transactions"></a><span data-ttu-id="e77c0-102">Транзакции XTP</span><span class="sxs-lookup"><span data-stu-id="e77c0-102">XTP Transactions</span></span>
  <span data-ttu-id="e77c0-103">Объект производительности XTP Transactions содержит счетчики, относящиеся к транзакциям механизма XTP в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e77c0-103">The XTP Transactions performance object contains counters related to XTP engine transactions in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="e77c0-104">В этой таблице перечислены счетчики **XTP-транзакций** .</span><span class="sxs-lookup"><span data-stu-id="e77c0-104">This table describes the **XTP Transactions** counters.</span></span>  
  
|<span data-ttu-id="e77c0-105">Счетчик</span><span class="sxs-lookup"><span data-stu-id="e77c0-105">Counter</span></span>|<span data-ttu-id="e77c0-106">Описание</span><span class="sxs-lookup"><span data-stu-id="e77c0-106">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e77c0-107">**Каскадных прерываний/с**</span><span class="sxs-lookup"><span data-stu-id="e77c0-107">**Cascading aborts/sec**</span></span>|<span data-ttu-id="e77c0-108">Количество транзакций, для которых был сделан откат из-за отката зависимостей фиксации (в среднем), в секунду.</span><span class="sxs-lookup"><span data-stu-id="e77c0-108">The number of transactions that rolled back to due a commit dependency rollback (on average), per second.</span></span>|  
|<span data-ttu-id="e77c0-109">**Зависимостей фиксации принято/с**</span><span class="sxs-lookup"><span data-stu-id="e77c0-109">**Commit dependencies taken/sec**</span></span>|<span data-ttu-id="e77c0-110">Общее число зависимостей фиксации, принятых транзакциями (в среднем) в секунду.</span><span class="sxs-lookup"><span data-stu-id="e77c0-110">The number of commit dependencies taken by transactions (on average), per second.</span></span>|  
|<span data-ttu-id="e77c0-111">**Транзакций в режиме только для чтения подготовлено/с**</span><span class="sxs-lookup"><span data-stu-id="e77c0-111">**Read-only transactions prepared/sec**</span></span>|<span data-ttu-id="e77c0-112">Количество транзакций только для чтения, подготовленных для обработки фиксации, в секунду.</span><span class="sxs-lookup"><span data-stu-id="e77c0-112">The number of read-only transactions that were prepared for commit processing, per second.</span></span>|  
|<span data-ttu-id="e77c0-113">**Обновлений точек сохранения/с**</span><span class="sxs-lookup"><span data-stu-id="e77c0-113">**Save point refreshes/sec**</span></span>|<span data-ttu-id="e77c0-114">Количество случаев, когда точка сохранения была «обновлена» (в среднем), в секунду.</span><span class="sxs-lookup"><span data-stu-id="e77c0-114">The number of times a savepoint was "refreshed", (on average), per second.</span></span> <span data-ttu-id="e77c0-115">Обновление точки сохранения называется сбросом существующей точки сохранения к текущей точке за время существования транзакции.</span><span class="sxs-lookup"><span data-stu-id="e77c0-115">A savepoint refresh is when an existing savepoint is reset to the current point in the transaction's lifetime.</span></span>|  
|<span data-ttu-id="e77c0-116">**Откатов точек сохранения/с**</span><span class="sxs-lookup"><span data-stu-id="e77c0-116">**Save point rollbacks/sec**</span></span>|<span data-ttu-id="e77c0-117">Количество раз, когда произошел откат транзакции к точке сохранения (в среднем), в секунду.</span><span class="sxs-lookup"><span data-stu-id="e77c0-117">The number of times a transaction rolled back to a save point (on average), per second.</span></span>|  
|<span data-ttu-id="e77c0-118">**Создано точек сохранения за секунду**</span><span class="sxs-lookup"><span data-stu-id="e77c0-118">**Save points created /sec**</span></span>|<span data-ttu-id="e77c0-119">Число созданных точек сохранения (в среднем) в секунду.</span><span class="sxs-lookup"><span data-stu-id="e77c0-119">The number of save points created (on average), per second.</span></span>|  
|<span data-ttu-id="e77c0-120">**Ошибок проверки транзакций/с**</span><span class="sxs-lookup"><span data-stu-id="e77c0-120">**Transaction validation failure/sec**</span></span>|<span data-ttu-id="e77c0-121">Общее число транзакций, которые не удалось проверить (в среднем), в секунду.</span><span class="sxs-lookup"><span data-stu-id="e77c0-121">The number of transactions that failed validation processing (on average), per second.</span></span>|  
|<span data-ttu-id="e77c0-122">**Транзакций, прерванных пользователем/с**</span><span class="sxs-lookup"><span data-stu-id="e77c0-122">**Transactions aborted by user/sec**</span></span>|<span data-ttu-id="e77c0-123">Общее число транзакций, которые были прерваны пользователем (в среднем), в секунду.</span><span class="sxs-lookup"><span data-stu-id="e77c0-123">The number of transactions that were aborted by the user (on average), per second.</span></span>|  
|<span data-ttu-id="e77c0-124">**Прервано транзакций/с**</span><span class="sxs-lookup"><span data-stu-id="e77c0-124">**Transactions aborted/sec**</span></span>|<span data-ttu-id="e77c0-125">Число прерванных (как пользователем, так и системой, в среднем) транзакций в секунду.</span><span class="sxs-lookup"><span data-stu-id="e77c0-125">The number of transactions that aborted (both by the user and the system, on average), per second.</span></span>|  
|<span data-ttu-id="e77c0-126">**Создано транзакций/с**</span><span class="sxs-lookup"><span data-stu-id="e77c0-126">**Transactions created/sec**</span></span>|<span data-ttu-id="e77c0-127">Количество транзакций, созданных в системе (в среднем), в секунду</span><span class="sxs-lookup"><span data-stu-id="e77c0-127">The number of transactions created in the system (on average), per second.</span></span><br /><br /> <span data-ttu-id="e77c0-128">Транзакции XTP подсчитываются не так, как дисковые транзакции (как отражено в базах данных: транзакций/с).</span><span class="sxs-lookup"><span data-stu-id="e77c0-128">XTP transactions are counted differently than disk-based transactions (as reflected in Databases:Transactions/sec).</span></span> <span data-ttu-id="e77c0-129">Например, параметр «Созданные транзакции/с» учитывает транзакции чтения, в то время как параметр «Базы данных: транзакций/с» — нет.</span><span class="sxs-lookup"><span data-stu-id="e77c0-129">For example, Transactions created/sec counts read/only transactions, while Databases:Transactions/sec does not.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e77c0-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="e77c0-130">See Also</span></span>  
 [<span data-ttu-id="e77c0-131">Счетчики производительности XTP &#40;в памяти OLTP&#41;</span><span class="sxs-lookup"><span data-stu-id="e77c0-131">XTP &#40;In-Memory OLTP&#41; Performance Counters</span></span>](../../integration-services/performance/performance-counters.md)  
  
  
