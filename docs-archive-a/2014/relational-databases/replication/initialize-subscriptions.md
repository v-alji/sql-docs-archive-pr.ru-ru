---
title: Инициализация подписки| Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.initializesubscriptions.f1
ms.assetid: 7b170e4e-470d-4828-a9ed-7435b0b03514
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f8c9388138ddec275dc1abd2b75e0b0c7fc99de4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655584"
---
# <a name="initialize-subscriptions"></a><span data-ttu-id="98210-102">Инициализировать подписки</span><span class="sxs-lookup"><span data-stu-id="98210-102">Initialize Subscriptions</span></span>
  <span data-ttu-id="98210-103">Необходимо инициализировать подписчиков, прежде чем они смогут начать прием реплицируемых данных.</span><span class="sxs-lookup"><span data-stu-id="98210-103">Subscribers must be initialized before they can begin receiving replicated data.</span></span> <span data-ttu-id="98210-104">Начальный набор данных не требуется, но подписчик должен, по крайней мере, обладать схемой для каждого реплицируемого объекта и всеми таблицами метаданных и процедурами, необходимыми для репликации.</span><span class="sxs-lookup"><span data-stu-id="98210-104">An initial dataset is not required, but the Subscriber must at least have the schema for each replicated object and any metadata tables and procedures required by replication.</span></span>  
  
## <a name="options"></a><span data-ttu-id="98210-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="98210-105">Options</span></span>  
 <span data-ttu-id="98210-106">**Свойства подписки**</span><span class="sxs-lookup"><span data-stu-id="98210-106">**Subscription properties**</span></span>  
 <span data-ttu-id="98210-107">Установите флажок в столбце **Инициализировать** для каждого подписчика, требующего наличия начального набора данных.</span><span class="sxs-lookup"><span data-stu-id="98210-107">Select the check box in the **Initialize** column for each Subscriber that requires an initial data set.</span></span> <span data-ttu-id="98210-108">Если флажок не установлен, будут инициализированы только метаданные и процедуры репликации.</span><span class="sxs-lookup"><span data-stu-id="98210-108">If the check box is cleared, only the replication metadata and procedures will be initialized.</span></span> <span data-ttu-id="98210-109">Дополнительные сведения об инициализации подписки без моментального снимка см. в статье [Инициализация подписки на публикацию транзакций без моментального снимка](initialize-a-transactional-subscription-without-a-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="98210-109">For more information about initializing a subscription without a snapshot, see [Initialize a Transactional Subscription Without a Snapshot](initialize-a-transactional-subscription-without-a-snapshot.md).</span></span>  
  
 <span data-ttu-id="98210-110">Выберите пункт **Немедленно** из раскрывающегося списка в столбце **Инициализировать, когда** , чтобы агент слияния или агент распространителя передал файлы моментальных снимков на подписчик по завершении работы мастера.</span><span class="sxs-lookup"><span data-stu-id="98210-110">Select **Immediately** from the drop-down list box in the **Initialize When** column to have the Merge Agent or Distribution Agent transfer snapshot files to the Subscriber after this wizard is completed.</span></span> <span data-ttu-id="98210-111">Выберите пункт **При первой синхронизации** , чтобы агент переслал файлы при следующем запланированном запуске.</span><span class="sxs-lookup"><span data-stu-id="98210-111">Select **At first synchronization** to have the agent transfer the files the next time it is scheduled to run.</span></span> <span data-ttu-id="98210-112">Параметр **Немедленно** недоступен для подписок по запросу на [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98210-112">The **Immediately** option is not available for pull subscriptions to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span> <span data-ttu-id="98210-113">Агент слияния и агент распространителя не работают на экземплярах выпуска [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], поэтому подписка должна быть инициализирована при помощи другого метода.</span><span class="sxs-lookup"><span data-stu-id="98210-113">The Merge Agent and Distribution Agent do not run on instances of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]; therefore the subscription must be initialized through another method.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="98210-114">Мастер может запросить соединение с распространителем, чтобы запустить соответствующее задание для агента распространителя или агента слияния.</span><span class="sxs-lookup"><span data-stu-id="98210-114">The wizard might prompt for a connection to the Distributor in order to start the appropriate job for the Distribution Agent or Merge Agent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98210-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="98210-115">See Also</span></span>  
 <span data-ttu-id="98210-116">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="98210-116">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="98210-117">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="98210-117">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 <span data-ttu-id="98210-118">[Инициализация подписки](initialize-a-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="98210-118">[Initialize a Subscription](initialize-a-subscription.md) </span></span>  
 [<span data-ttu-id="98210-119">Подписка на публикации</span><span class="sxs-lookup"><span data-stu-id="98210-119">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
