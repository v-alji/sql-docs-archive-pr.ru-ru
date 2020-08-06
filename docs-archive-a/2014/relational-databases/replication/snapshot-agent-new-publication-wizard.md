---
title: Агент моментальных снимков (мастер создания публикаций) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newpubwizard.configuresnapshotagent.f1
ms.assetid: 0257d4ee-1f7b-49fd-b4ef-65bfc1ef6951
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c45fa3444fb2f81436a40a2bfb80519aea105c47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668762"
---
# <a name="snapshot-agent-new-publication-wizard"></a><span data-ttu-id="2cc27-102">Агент моментальных снимков (мастер создания публикаций)</span><span class="sxs-lookup"><span data-stu-id="2cc27-102">Snapshot Agent (New Publication Wizard)</span></span>
  <span data-ttu-id="2cc27-103">Агент моментальных снимков создает файлы, содержащие схему публикации и данные для инициализации новых подписок.</span><span class="sxs-lookup"><span data-stu-id="2cc27-103">The Snapshot Agent creates files containing the publication schema and data that are used to initialize new subscriptions.</span></span> <span data-ttu-id="2cc27-104">По умолчанию агент моментальных снимков запускается сразу же после создания публикации в мастере создания публикаций.</span><span class="sxs-lookup"><span data-stu-id="2cc27-104">By default, the Snapshot Agent runs immediately after the publication is created in the New Publication Wizard.</span></span> <span data-ttu-id="2cc27-105">Впоследствии этот агент запускается по указанному расписанию.</span><span class="sxs-lookup"><span data-stu-id="2cc27-105">Subsequently, the agent runs according to a schedule you specify.</span></span> <span data-ttu-id="2cc27-106">Будет ли этот агент создавать новые файлы моментальных снимков при каждом запуске, зависит от типа репликации и выбранных параметров.</span><span class="sxs-lookup"><span data-stu-id="2cc27-106">Whether the agent creates new snapshot files each time it runs depends on the type of replication and options chosen.</span></span> <span data-ttu-id="2cc27-107">Дополнительные сведения см. в статье [Создание и применение моментального снимка](create-and-apply-the-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="2cc27-107">For more information, see [Create and Apply the Snapshot](create-and-apply-the-snapshot.md).</span></span>  
  
 <span data-ttu-id="2cc27-108">Для публикаций слиянием, использующих параметризованные фильтры, необходимо создать моментальный снимок для каждой секции данных после завершения снимка публикации.</span><span class="sxs-lookup"><span data-stu-id="2cc27-108">For merge publications that use parameterized filters, you must create a snapshot for each partition of data after the publication snapshot has completed.</span></span> <span data-ttu-id="2cc27-109">Дополнительные сведения см. в статье [Snapshots for Merge Publications with Parameterized Filters](snapshots-for-merge-publications-with-parameterized-filters.md).</span><span class="sxs-lookup"><span data-stu-id="2cc27-109">For more information, see [Snapshots for Merge Publications with Parameterized Filters](snapshots-for-merge-publications-with-parameterized-filters.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="2cc27-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="2cc27-110">Options</span></span>  
 <span data-ttu-id="2cc27-111">**Создать моментальный снимок немедленно** (репликация слиянием) или **Создать моментальный снимок немедленно и обеспечить доступ к нему для инициализации подписок** (репликация транзакций)</span><span class="sxs-lookup"><span data-stu-id="2cc27-111">**Create a snapshot immediately** (merge replication) or **Create a snapshot immediately and keep the snapshot available to initialize subscriptions** (transactional replication)</span></span>  
 <span data-ttu-id="2cc27-112">Установите этот флажок для немедленного создания моментального снимка по завершении работы мастера создания публикаций.</span><span class="sxs-lookup"><span data-stu-id="2cc27-112">Select this check box to create a snapshot immediately after the New Publication Wizard is completed.</span></span> <span data-ttu-id="2cc27-113">Снимите этот флажок, если планируете изменить свойства моментального снимка в диалоговом окне **Свойства публикации** перед созданием снимка или если будете инициализировать подписчик без моментального снимка.</span><span class="sxs-lookup"><span data-stu-id="2cc27-113">Clear this check box if you plan to change snapshot properties in the **Publication Properties** dialog box before generating a snapshot, or if you will initialize the Subscriber without a snapshot.</span></span> <span data-ttu-id="2cc27-114">Дополнительные сведения см. в статье [Инициализация подписки на публикацию транзакций без моментального снимка](initialize-a-transactional-subscription-without-a-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="2cc27-114">For more information, see [Initialize a Transactional Subscription Without a Snapshot](initialize-a-transactional-subscription-without-a-snapshot.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2cc27-115">Мастер может запросить соединение с распространителем, чтобы запустить соответствующее задание для агента распространителя или агента слияния.</span><span class="sxs-lookup"><span data-stu-id="2cc27-115">The wizard might prompt for a connection to the Distributor in order to start the appropriate job for the Distribution Agent or Merge Agent.</span></span>  
  
 <span data-ttu-id="2cc27-116">**Запланировать запуск агента моментальных снимков в следующее время**</span><span class="sxs-lookup"><span data-stu-id="2cc27-116">**Schedule the Snapshot Agent to run at the following times**</span></span>  
 <span data-ttu-id="2cc27-117">Примите расписание по умолчанию для запусков агента моментальных снимков или нажмите кнопку **Изменить** , чтобы задать собственное расписание.</span><span class="sxs-lookup"><span data-stu-id="2cc27-117">Accept the default schedule for running the Snapshot Agent, or click **Change** to specify a schedule.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cc27-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="2cc27-118">See Also</span></span>  
 <span data-ttu-id="2cc27-119">[Create a Publication](publish/create-a-publication.md) </span><span class="sxs-lookup"><span data-stu-id="2cc27-119">[Create a Publication](publish/create-a-publication.md) </span></span>  
 <span data-ttu-id="2cc27-120">[Создание и применение исходного моментального снимка](create-and-apply-the-initial-snapshot.md) </span><span class="sxs-lookup"><span data-stu-id="2cc27-120">[Create and Apply the Initial Snapshot](create-and-apply-the-initial-snapshot.md) </span></span>  
 <span data-ttu-id="2cc27-121">[Просмотр и изменение свойств публикации](publish/view-and-modify-publication-properties.md) </span><span class="sxs-lookup"><span data-stu-id="2cc27-121">[View and Modify Publication Properties](publish/view-and-modify-publication-properties.md) </span></span>  
 <span data-ttu-id="2cc27-122">[Инициализация подписки с помощью моментального снимка](initialize-a-subscription-with-a-snapshot.md) </span><span class="sxs-lookup"><span data-stu-id="2cc27-122">[Initialize a Subscription with a Snapshot](initialize-a-subscription-with-a-snapshot.md) </span></span>  
 <span data-ttu-id="2cc27-123">[Публикация данных и объектов базы данных](publish/publish-data-and-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="2cc27-123">[Publish Data and Database Objects](publish/publish-data-and-database-objects.md) </span></span>  
 [<span data-ttu-id="2cc27-124">Replication Agents Overview</span><span class="sxs-lookup"><span data-stu-id="2cc27-124">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
