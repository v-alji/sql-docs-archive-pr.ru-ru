---
title: Оптимизация производительности репликации слиянием с помощью отслеживания условного удаления | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- conditional delete tracking [SQL Server replication]
- merge replication [SQL Server replication], conditional delete tracking
- articles [SQL Server replication], conditional delete tracking
ms.assetid: 58f120a3-ea3a-4e97-93f0-0eb4e580ecf2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 46fc189d2a2e0ebf5ea44775585a69d52783a7e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654200"
---
# <a name="optimize-merge-replication-performance-with-conditional-delete-tracking"></a><span data-ttu-id="24ebe-102">Оптимизация производительности репликации слиянием с помощью отслеживания условного удаления</span><span class="sxs-lookup"><span data-stu-id="24ebe-102">Optimize Merge Replication Performance with Conditional Delete Tracking</span></span>
    
> [!NOTE]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../../includes/ssnotedepfutureavoid-md.md)]  
  
 <span data-ttu-id="24ebe-103">При репликации слиянием можно указать, что удаления для одной или нескольких статей не должны отслеживаться триггерами репликации и системными таблицами.</span><span class="sxs-lookup"><span data-stu-id="24ebe-103">With merge replication you can specify that deletes for one or more articles should not be tracked by replication triggers and system tables.</span></span> <span data-ttu-id="24ebe-104">При задании этого параметра для статьи отслеживание удалений не производится, и удаления не реплицируются с издателя или с каких-либо подписчиков.</span><span class="sxs-lookup"><span data-stu-id="24ebe-104">If you specify this option for an article, deletes are not tracked or replicated from the Publisher or any Subscribers.</span></span> <span data-ttu-id="24ebe-105">Этот параметр предназначен для поддержки некоторых прикладных сценариев и для обеспечения оптимизации производительности в случаях, когда репликация удалений не нужна или нежелательна.</span><span class="sxs-lookup"><span data-stu-id="24ebe-105">This option is available to support a number of application scenarios and to provide a performance optimization for cases in which the replication of deletes is not necessary or desirable.</span></span> <span data-ttu-id="24ebe-106">Повышение производительности достигается тремя способами: метаданные для удалений не сохраняются; удаления не перечисляются во время синхронизации; удаления не реплицируются и не применяются на подписчике.</span><span class="sxs-lookup"><span data-stu-id="24ebe-106">Performance is enhanced in three ways: metadata for deletes is not stored; deletes are not enumerated during synchronization; deletes are not replicated to and applied at the Subscriber.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="24ebe-107">Для использования статей, доступных только для загрузки, уровень совместимости публикации должен быть не менее 90RTM.</span><span class="sxs-lookup"><span data-stu-id="24ebe-107">To use download-only articles, the compatibility level of the publication must be at least 90RTM.</span></span>  
  
 <span data-ttu-id="24ebe-108">Этот параметр может быть указан при создании публикации, или он может включаться и выключаться, если для приложения необходимо, чтобы некоторые удаления реплицировались, а другие — нет, например пакетные удаления.</span><span class="sxs-lookup"><span data-stu-id="24ebe-108">The option can be specified when a publication is created or it can be toggled on and off if an application requires that some deletes be replicated and that others not be replicated, such as batch deletes.</span></span> <span data-ttu-id="24ebe-109">В приводимых ниже примерах показаны способы использования этого параметра в приложении:</span><span class="sxs-lookup"><span data-stu-id="24ebe-109">The following examples illustrate ways in which this option might be used in an application:</span></span>  
  
-   <span data-ttu-id="24ebe-110">В приложении для мобильных продавцов обычно имеются таблицы, такие как **SalesOrderHeader**, **SalesOrderDetail** и **Product**.</span><span class="sxs-lookup"><span data-stu-id="24ebe-110">An application for a mobile sales force typically has tables such as **SalesOrderHeader**, **SalesOrderDetail** and **Product**.</span></span> <span data-ttu-id="24ebe-111">Заказы вводятся на подписчике, а затем реплицируются на издателе, который часто предоставляет данные для системы выполнения заказов.</span><span class="sxs-lookup"><span data-stu-id="24ebe-111">Orders are entered at the Subscriber and then replicated to the Publisher, which often supplies data to an order fulfillment system.</span></span> <span data-ttu-id="24ebe-112">Многие сотрудники на выезде используют портативные устройства, возможности хранения в которых ограничены: после получения заказа издателем заказ может быть удален на подписчике.</span><span class="sxs-lookup"><span data-stu-id="24ebe-112">Many mobile workers use handheld devices which have limited storage: after the order is received at the Publisher, it can be deleted at the Subscriber.</span></span> <span data-ttu-id="24ebe-113">Удаление не пересылается издателю, поскольку заказ все еще является активным в системе.</span><span class="sxs-lookup"><span data-stu-id="24ebe-113">The delete is not propagated to the Publisher, because the order is still active in the system.</span></span>  
  
     <span data-ttu-id="24ebe-114">В этом сценарии для таблиц **SalesOrderHeader** и **SalesOrderDetail** отслеживание удалений не производится.</span><span class="sxs-lookup"><span data-stu-id="24ebe-114">In this scenario, deletes would not be tracked for the **SalesOrderHeader** and **SalesOrderDetail** tables.</span></span> <span data-ttu-id="24ebe-115">Удаления отслеживаются для таблицы **Product** , поскольку при удалении продукта на издателе удаление должно быть отправлено подписчику для своевременного обновления списка продуктов.</span><span class="sxs-lookup"><span data-stu-id="24ebe-115">Deletes would be tracked for the **Product** table, because if a product is deleted at the Publisher, the delete should be sent to the Subscriber to keep the product list up to date.</span></span>  
  
-   <span data-ttu-id="24ebe-116">Приложение может сохранять данные за длительный период времени в таблице, такой как **TransactionHistory**, из которой периодически удаляются записи со сроком хранения больше года.</span><span class="sxs-lookup"><span data-stu-id="24ebe-116">An application could store historical data in a table such as **TransactionHistory**, which is periodically purged of records older than a year.</span></span> <span data-ttu-id="24ebe-117">Эту таблицу можно фильтровать таким образом, чтобы подписчики получали только данные о транзакциях, выполненных в текущем месяце.</span><span class="sxs-lookup"><span data-stu-id="24ebe-117">The table could be filtered such that Subscribers only receive data on transactions within the current month.</span></span> <span data-ttu-id="24ebe-118">Ежемесячные пакетные удаления на издателе, которые стирают старые данные, не имеют отношения к подписчикам, но по умолчанию они будут отслеживаться и перечисляться.</span><span class="sxs-lookup"><span data-stu-id="24ebe-118">Monthly batch deletes at the Publisher that purge older data are not relevant to Subscribers, but they would still be tracked and enumerated by default.</span></span>  
  
     <span data-ttu-id="24ebe-119">В этом сценарии перед выполнением пакетной обработки в системе могут быть приостановлены операции, и приложение может отключить отслеживание удалений.</span><span class="sxs-lookup"><span data-stu-id="24ebe-119">In this scenario, before the batch processing occurred, activity could be stopped on the system, and the application could disable the tracking of deletes.</span></span> <span data-ttu-id="24ebe-120">После завершения обработки можно вновь включить отслеживание.</span><span class="sxs-lookup"><span data-stu-id="24ebe-120">After the processing has finished, tracking could again be enabled.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="24ebe-121">Если на издателе продолжается выполнение других операций, необходимо обеспечить, чтобы удаления, которые должны распространяться на подписчики, не происходили при отключенном отслеживании удалений.</span><span class="sxs-lookup"><span data-stu-id="24ebe-121">If other activity continues at the Publisher, you must ensure that deletes that should be propagated to Subscribers do not occur while delete tracking is disabled.</span></span>  
  
 <span data-ttu-id="24ebe-122">**Указание того, что удаления не должны отслеживаться**</span><span class="sxs-lookup"><span data-stu-id="24ebe-122">**To specify that deletes should not be tracked**</span></span>  
  
-   <span data-ttu-id="24ebe-123">Программирование репликации в [!INCLUDE[tsql](../../../includes/tsql-md.md)]: [Отключение отслеживания операций удаления для статей публикации слиянием (программирование репликации на языке Transact-SQL)](..//publish/specify-merge-replication-properties.md#tracking-deletes)</span><span class="sxs-lookup"><span data-stu-id="24ebe-123">Replication [!INCLUDE[tsql](../../../includes/tsql-md.md)] programming: [Specify That Deletes Should Not Be Tracked For Merge Articles &#40;Replication Transact-SQL Programming&#41;](..//publish/specify-merge-replication-properties.md#tracking-deletes)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24ebe-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="24ebe-124">See Also</span></span>  
 <span data-ttu-id="24ebe-125">[Параметры статьи для репликации слиянием](article-options-for-merge-replication.md) </span><span class="sxs-lookup"><span data-stu-id="24ebe-125">[Article Options for Merge Replication](article-options-for-merge-replication.md) </span></span>  
 [<span data-ttu-id="24ebe-126">Оптимизация производительности репликации слиянием при работе со статьями, доступными только для загрузки</span><span class="sxs-lookup"><span data-stu-id="24ebe-126">Optimize Merge Replication Performance with Download-Only Articles</span></span>](optimize-merge-replication-performance-with-download-only-articles.md)  
  
  
