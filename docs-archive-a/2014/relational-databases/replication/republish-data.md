---
title: Повторная публикация данных | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- republishing data
- publishing [SQL Server replication], Subscribers
- Subscribers [SQL Server replication], republishing data
ms.assetid: a1485cf4-b1c4-49e9-ab06-8ccfaad998f3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f1e4213266121b3bf55bf2857e15f71f1e94e301
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655030"
---
# <a name="republish-data"></a><span data-ttu-id="b5262-102">Повторная публикация данных</span><span class="sxs-lookup"><span data-stu-id="b5262-102">Republish Data</span></span>
  <span data-ttu-id="b5262-103">В модели переиздания издатель посылает данные подписчику, который затем переиздает данные для других подписчиков.</span><span class="sxs-lookup"><span data-stu-id="b5262-103">In a republishing model, the Publisher sends data to a Subscriber, which then republishes the data to any number of other Subscribers.</span></span> <span data-ttu-id="b5262-104">Эта модель полезна в ситуациях, когда издатель должен отослать данные подписчикам через медленный или дорогостоящий канал передачи данных.</span><span class="sxs-lookup"><span data-stu-id="b5262-104">This is useful when a Publisher must send data to Subscribers over a slow or expensive communications link.</span></span> <span data-ttu-id="b5262-105">Если на другом конце такого канала существует несколько подписчиков, использование переиздающего подписчика позволяет сместить большую часть нагрузки распространения на сторону канала, где находятся подписчики.</span><span class="sxs-lookup"><span data-stu-id="b5262-105">If there are a number of Subscribers on the far side of that link, using a republisher shifts the bulk of the distribution load to that side of the link.</span></span>  
  
 <span data-ttu-id="b5262-106">Переиздание данных включает следующие шаги:</span><span class="sxs-lookup"><span data-stu-id="b5262-106">Republishing data involves the following steps:</span></span>  
  
1.  <span data-ttu-id="b5262-107">Создание публикации на издателе.</span><span class="sxs-lookup"><span data-stu-id="b5262-107">Create a publication at the Publisher.</span></span>  
  
2.  <span data-ttu-id="b5262-108">Создание подписки на публикацию для переиздающего подписчика.</span><span class="sxs-lookup"><span data-stu-id="b5262-108">Create a subscription to the publication for the republishing Subscriber.</span></span>  
  
3.  <span data-ttu-id="b5262-109">Инициализация подписки.</span><span class="sxs-lookup"><span data-stu-id="b5262-109">Initialize the subscription.</span></span> <span data-ttu-id="b5262-110">Подписка должна быть инициализирована до создания публикации на переиздающем подписчике, или репликация завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="b5262-110">The subscription must be initialized before the publication is created at the republishing Subscriber, or replication will fail.</span></span>  
  
4.  <span data-ttu-id="b5262-111">Создание публикации в базе данных подписки на переиздающем подписчике.</span><span class="sxs-lookup"><span data-stu-id="b5262-111">Create a publication in the subscription database at the republishing Subscriber.</span></span>  
  
5.  <span data-ttu-id="b5262-112">Создание подписки на публикацию в переиздающем подписчике для других подписчиков.</span><span class="sxs-lookup"><span data-stu-id="b5262-112">Create subscriptions to the publication at the republishing Subscriber for the other Subscribers.</span></span>  
  
6.  <span data-ttu-id="b5262-113">Инициализация подписок.</span><span class="sxs-lookup"><span data-stu-id="b5262-113">Initialize the subscriptions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b5262-114">При использовании репликации слиянием в топологии переиздания все переиздающие подписчики должны использовать серверные подписки.</span><span class="sxs-lookup"><span data-stu-id="b5262-114">If you use merge replication in a republishing topology, all republishing Subscribers must use server subscriptions.</span></span> <span data-ttu-id="b5262-115">Дополнительные сведения о типах подписок см. в статье [Подписка на публикации](subscribe-to-publications.md).</span><span class="sxs-lookup"><span data-stu-id="b5262-115">For more information about subscription types, see [Subscribe to Publications](subscribe-to-publications.md).</span></span>  
  
 <span data-ttu-id="b5262-116">На следующей иллюстрации и издатель, и переиздающий подписчик действуют как свои собственные локальные распространители.</span><span class="sxs-lookup"><span data-stu-id="b5262-116">In the following illustration, both the Publisher and the republisher are acting as their own local Distributors.</span></span> <span data-ttu-id="b5262-117">Если каждый из них настроен на использование удаленного распространителя, то каждый распространитель должен будет находиться на той же стороне медленного или дорогостоящего канала передачи данных, что и его издатель.</span><span class="sxs-lookup"><span data-stu-id="b5262-117">If each were set up to use a remote Distributor, each Distributor would need to be on the same side of the slow or expensive communications link as its Publisher.</span></span> <span data-ttu-id="b5262-118">Издатели должны быть подключены к удаленным распространителям через надежные высокоскоростные соединения.</span><span class="sxs-lookup"><span data-stu-id="b5262-118">Publishers must be connected to remote Distributors by reliable, high-speed communications links.</span></span>  
  
 <span data-ttu-id="b5262-119">![Повторная публикация данных](media/repl-06a.gif "Повторная публикация данных")</span><span class="sxs-lookup"><span data-stu-id="b5262-119">![Republishing data](media/repl-06a.gif "Republishing data")</span></span>  
  
 <span data-ttu-id="b5262-120">Любой сервер может выступать как в роли издателя, так и в роли подписчика.</span><span class="sxs-lookup"><span data-stu-id="b5262-120">Any server can act as both a Publisher and Subscriber.</span></span> <span data-ttu-id="b5262-121">Например, рассмотрим следующую диаграмму, на которой публикация таблицы находится в Лондоне и должна распространяться в четыре разных города США: Чикаго, Нью-Йорк, Сан-Диего и Сиэтл.</span><span class="sxs-lookup"><span data-stu-id="b5262-121">For example, consider the following diagram in which a publication of a table exists in London and must be distributed to four different cities in the United States: Chicago, New York, San Diego, and Seattle.</span></span> <span data-ttu-id="b5262-122">Сервер в Нью-Йорке выбран для подписки на опубликованную таблицу, созданную в Лондоне, т. к. нью-йоркский сайт удовлетворяет следующим условиям.</span><span class="sxs-lookup"><span data-stu-id="b5262-122">The server in New York is chosen to subscribe to the published table originating in London, because the New York site meets these conditions:</span></span>  
  
-   <span data-ttu-id="b5262-123">Сетевое соединение с Лондоном относительно надежно.</span><span class="sxs-lookup"><span data-stu-id="b5262-123">The network link back to London is relatively reliable.</span></span>  
  
-   <span data-ttu-id="b5262-124">Стоимость связи между Нью-Йорком и Лондоном приемлема.</span><span class="sxs-lookup"><span data-stu-id="b5262-124">The London-to-New York communication costs are acceptable.</span></span>  
  
-   <span data-ttu-id="b5262-125">Между Нью-Йорком и сайтами остальных подписчиков в США имеются хорошие линии связи.</span><span class="sxs-lookup"><span data-stu-id="b5262-125">There are good network communications lines from New York to all other Subscriber sites in the United States.</span></span>  
  
     <span data-ttu-id="b5262-126">![Повторная публикация данных в распределенные расположения](media/repl-06.gif "Повторная публикация данных в распределенные расположения")</span><span class="sxs-lookup"><span data-stu-id="b5262-126">![Republishing data to dispersed locations](media/repl-06.gif "Republishing data to dispersed locations")</span></span>  
  
 <span data-ttu-id="b5262-127">Репликация поддерживает сценарии переиздания, представленные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="b5262-127">Replication supports the republishing scenarios shown in the following table.</span></span>  
  
|<span data-ttu-id="b5262-128">Издатель</span><span class="sxs-lookup"><span data-stu-id="b5262-128">Publisher</span></span>|<span data-ttu-id="b5262-129">переиздающий подписчик</span><span class="sxs-lookup"><span data-stu-id="b5262-129">Publishing Subscriber</span></span>|<span data-ttu-id="b5262-130">Подписчик</span><span class="sxs-lookup"><span data-stu-id="b5262-130">Subscriber</span></span>|  
|---------------|---------------------------|----------------|  
|<span data-ttu-id="b5262-131">Публикация транзакций</span><span class="sxs-lookup"><span data-stu-id="b5262-131">Transactional publication</span></span>|<span data-ttu-id="b5262-132">Подписка на публикацию транзакций или публикация транзакций</span><span class="sxs-lookup"><span data-stu-id="b5262-132">Transactional subscription/transactional publication</span></span>|<span data-ttu-id="b5262-133">Подписка на публикацию транзакций</span><span class="sxs-lookup"><span data-stu-id="b5262-133">Transactional subscription</span></span>|  
|<span data-ttu-id="b5262-134">Публикация транзакций</span><span class="sxs-lookup"><span data-stu-id="b5262-134">Transactional publication</span></span>|<span data-ttu-id="b5262-135">Подписка на публикацию транзакций или публикация слиянием<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b5262-135">Transactional subscription/merge publication<sup>1</sup></span></span>|<span data-ttu-id="b5262-136">Подписка на публикацию слиянием</span><span class="sxs-lookup"><span data-stu-id="b5262-136">Merge subscription</span></span>|  
|<span data-ttu-id="b5262-137">Публикация слиянием</span><span class="sxs-lookup"><span data-stu-id="b5262-137">Merge publication</span></span>|<span data-ttu-id="b5262-138">Подписка на публикацию слиянием или публикация слиянием</span><span class="sxs-lookup"><span data-stu-id="b5262-138">Merge subscription/merge publication</span></span>|<span data-ttu-id="b5262-139">Подписка на публикацию слиянием</span><span class="sxs-lookup"><span data-stu-id="b5262-139">Merge subscription</span></span>|  
|<span data-ttu-id="b5262-140">Публикация слиянием</span><span class="sxs-lookup"><span data-stu-id="b5262-140">Merge publication</span></span>|<span data-ttu-id="b5262-141">Подписка на публикацию слиянием или публикация транзакций</span><span class="sxs-lookup"><span data-stu-id="b5262-141">Merge subscription/transactional publication</span></span>|<span data-ttu-id="b5262-142">Подписка на публикацию транзакций</span><span class="sxs-lookup"><span data-stu-id="b5262-142">Transactional subscription</span></span>|  
  
 <span data-ttu-id="b5262-143"><sup>1</sup> Необходимо задать `@published_in_tran_pub` свойство для публикации слиянием.</span><span class="sxs-lookup"><span data-stu-id="b5262-143"><sup>1</sup>You should set the `@published_in_tran_pub` property on the merge publication.</span></span> <span data-ttu-id="b5262-144">По умолчанию репликация транзакций исключает таблицы на подписчике, которые будут обрабатываться как доступные только для чтения.</span><span class="sxs-lookup"><span data-stu-id="b5262-144">By default, transactional replication expects tables at the Subscriber to be treated as read-only.</span></span> <span data-ttu-id="b5262-145">Если репликация слиянием производит изменения данных в какой-либо таблице подписки на публикацию транзакций, то может возникнуть несогласованность данных.</span><span class="sxs-lookup"><span data-stu-id="b5262-145">If merge replication makes data changes to a table in a transactional subscription, non-convergence of data can occur.</span></span> <span data-ttu-id="b5262-146">Чтобы избежать этой ситуации, рекомендуется, чтобы любые подобные таблицы задавались в публикации слиянием с атрибутом «только для загрузки».</span><span class="sxs-lookup"><span data-stu-id="b5262-146">To avoid this risk, we recommend that any such table be specified as download-only in the merge publication.</span></span> <span data-ttu-id="b5262-147">Это защищает подписчика на публикацию слиянием от передачи измененных данных в таблицу.</span><span class="sxs-lookup"><span data-stu-id="b5262-147">This prevents a merge Subscriber from uploading data changes to the table.</span></span> <span data-ttu-id="b5262-148">Дополнительные сведения см. в статье [Оптимизация производительности репликации слиянием при работе со статьями, доступными только для загрузки](merge/optimize-merge-replication-performance-with-download-only-articles.md).</span><span class="sxs-lookup"><span data-stu-id="b5262-148">For more information, see [Optimize Merge Replication Performance with Download-Only Articles](merge/optimize-merge-replication-performance-with-download-only-articles.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5262-149">См. также:</span><span class="sxs-lookup"><span data-stu-id="b5262-149">See Also</span></span>  
 <span data-ttu-id="b5262-150">[Настройка распространения](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="b5262-150">[Configure Distribution](configure-distribution.md) </span></span>  
 <span data-ttu-id="b5262-151">[Публикация данных и объектов базы данных](publish/publish-data-and-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="b5262-151">[Publish Data and Database Objects](publish/publish-data-and-database-objects.md) </span></span>  
 <span data-ttu-id="b5262-152">[Subscribe to Publications](subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="b5262-152">[Subscribe to Publications](subscribe-to-publications.md) </span></span>  
 <span data-ttu-id="b5262-153">[Инициализация подписки](initialize-a-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="b5262-153">[Initialize a Subscription](initialize-a-subscription.md) </span></span>  
 [<span data-ttu-id="b5262-154">Синхронизация данных</span><span class="sxs-lookup"><span data-stu-id="b5262-154">Synchronize Data</span></span>](synchronize-data.md)  
  
  
