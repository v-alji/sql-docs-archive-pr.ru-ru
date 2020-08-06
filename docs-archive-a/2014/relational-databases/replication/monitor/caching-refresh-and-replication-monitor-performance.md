---
title: Кэширование, обновление и производительность монитора репликации | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server replication], Replication Monitor
- cache [SQL Server], replication
- Replication Monitor, caching
- refreshing data
- Replication Monitor, refreshing
ms.assetid: a2d8b666-ed41-4f86-b2b8-c8e118416ab7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b04a91e971e65d19c66cc36f142d8c4764b1b05a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657652"
---
# <a name="caching-refresh-and-replication-monitor-performance"></a><span data-ttu-id="a18a4-102">Кэширование, обновление и производительность монитора репликации</span><span class="sxs-lookup"><span data-stu-id="a18a4-102">Caching, Refresh, and Replication Monitor Performance</span></span>
  [!INCLUDE[msCoName](../../../includes/msconame-md.md)]<span data-ttu-id="a18a4-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Монитор репликации предназначен для эффективного мониторинга большого количества компьютеров в рабочей системе.</span><span class="sxs-lookup"><span data-stu-id="a18a4-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Replication Monitor is designed to efficiently monitor a large number of computers in a production system.</span></span> <span data-ttu-id="a18a4-104">Запросы, которые монитор репликации использует для выполнения вычислений и сбора данных, периодически кэшируются и обновляются.</span><span class="sxs-lookup"><span data-stu-id="a18a4-104">The queries that Replication Monitor uses to perform calculations and gather data are cached and refreshed on a periodic basis.</span></span> <span data-ttu-id="a18a4-105">Кэширование уменьшает количество запросов и вычислений, необходимых для просмотра разных страниц в мониторе репликации и позволяет вести наблюдение за несколькими пользователями.</span><span class="sxs-lookup"><span data-stu-id="a18a4-105">Caching reduces the number of queries and calculations required as you view different pages in Replication Monitor and allows monitoring to scale well for multiple users.</span></span>  
  
 <span data-ttu-id="a18a4-106">Обновление кэша обрабатывается заданием агента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] — **Обновитель монитора репликации для распространения**.</span><span class="sxs-lookup"><span data-stu-id="a18a4-106">Cache refresh is handled by a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent job, the **Replication monitoring refresher for distribution**.</span></span> <span data-ttu-id="a18a4-107">Задание выполняется постоянно, однако расписание обновления кэша основано на определенном времени ожидания после предыдущего обновления:</span><span class="sxs-lookup"><span data-stu-id="a18a4-107">The job runs continuously, but the cache refresh schedule is based on waiting a certain amount time after the previous refresh:</span></span>  
  
-   <span data-ttu-id="a18a4-108">Если с момента последнего создания кэша происходили изменения в истории агента, время ожидания устанавливается по меньшему из следующих периодов: 4 секунды или длительность создания предыдущей версии кэша.</span><span class="sxs-lookup"><span data-stu-id="a18a4-108">If there were agent history changes since the cache was last created, the wait time is the minimum of: 4 seconds; or the amount of time taken to create the previous cache.</span></span>  
  
-   <span data-ttu-id="a18a4-109">Если с момента последнего создания кэша не было изменений в истории агента (допускаются другие изменения), время ожидания устанавливается по большему из следующих периодов: 30 секунд или длительность создания предыдущей версии кэша.</span><span class="sxs-lookup"><span data-stu-id="a18a4-109">If there were no agent history changes since the cache was last created (there could have been other changes), the wait time is the maximum of: 30 seconds; or the amount of time taken to create the previous cache.</span></span>  
  
## <a name="refreshing-the-replication-monitor-user-interface"></a><span data-ttu-id="a18a4-110">Обновление пользовательского интерфейса монитора репликации</span><span class="sxs-lookup"><span data-stu-id="a18a4-110">Refreshing the Replication Monitor User Interface</span></span>  
 <span data-ttu-id="a18a4-111">Пользовательский интерфейс монитора репликации может обновляться следующими способами:</span><span class="sxs-lookup"><span data-stu-id="a18a4-111">The Replication Monitor user interface can be refreshed in the following ways:</span></span>  
  
-   <span data-ttu-id="a18a4-112">Главное окно монитора репликации (включая все вкладки) по умолчанию обновляется автоматически каждые пять секунд.</span><span class="sxs-lookup"><span data-stu-id="a18a4-112">The main Replication Monitor window (including all tabs), automatically refreshes by default every five seconds.</span></span> <span data-ttu-id="a18a4-113">Автоматические обновления не выполняют принудительного обновления кэша. Пользовательский интерфейс отображает самую последнюю версию данных из кэша.</span><span class="sxs-lookup"><span data-stu-id="a18a4-113">Automatic refreshes do not force a refresh of the cache; the user interface displays the most recent version of the data from the cache.</span></span> <span data-ttu-id="a18a4-114">Настроить частоту обновлений, используемую для всех окон, связанных с издателем, можно с помощью редактирования параметров издателя.</span><span class="sxs-lookup"><span data-stu-id="a18a4-114">You can customize the refresh rate used for all windows associated with a Publisher by editing the Publisher settings.</span></span> <span data-ttu-id="a18a4-115">Можно также отключить автоматические обновления для издателя.</span><span class="sxs-lookup"><span data-stu-id="a18a4-115">You can also disable automatic refreshes for a Publisher.</span></span>  
  
-   <span data-ttu-id="a18a4-116">Окна сведений, запускаемые из монитора репликации (за исключением окон, связанных с синхронизируемыми подписками слиянием), не обновляются по умолчанию автоматически.</span><span class="sxs-lookup"><span data-stu-id="a18a4-116">The detail windows that are launched from Replication Monitor are not automatically refreshed by default, with the exception of windows related to merge subscriptions that are synchronizing.</span></span> <span data-ttu-id="a18a4-117">Если указать, что окна сведений должны обновляться автоматически, они будут обновляться в соответствии с тем же расписанием, что и главное окно монитора репликации.</span><span class="sxs-lookup"><span data-stu-id="a18a4-117">If you specify that detail windows should automatically refresh, they refresh on the same schedule as the main Replication Monitor window.</span></span>  
  
-   <span data-ttu-id="a18a4-118">Все окна можно обновлять вручную. Для этого следует нажать клавишу F5 или щелкнуть правой кнопкой мыши узел в дереве монитора репликации и выбрать **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="a18a4-118">All windows can be manually refreshed by pressing F5 or by right-clicking a node in the Replication Monitor tree and clicking **Refresh**.</span></span> <span data-ttu-id="a18a4-119">Обновления, осуществляемые вручную, выполняют принудительное обновление кэша.</span><span class="sxs-lookup"><span data-stu-id="a18a4-119">Manual refreshes force a refresh of the cache.</span></span>  
  
 <span data-ttu-id="a18a4-120">Дополнительные сведения об обновлении данных в мониторе репликации см. в [этой статье](refresh-data-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="a18a4-120">For more information, see [Refresh Data in Replication Monitor](refresh-data-in-replication-monitor.md).</span></span>  
  
## <a name="performance-considerations"></a><span data-ttu-id="a18a4-121">Вопросы производительности</span><span class="sxs-lookup"><span data-stu-id="a18a4-121">Performance Considerations</span></span>  
 <span data-ttu-id="a18a4-122">Хотя монитор репликации разработан так, чтобы обеспечивать эффективную работу, необходимо придерживаться следующих правил:</span><span class="sxs-lookup"><span data-stu-id="a18a4-122">Although Replication Monitor is designed to run efficiently, be aware of the following:</span></span>  
  
-   <span data-ttu-id="a18a4-123">При наличии большого числа публикаций или подписок рассмотрите возможность установки расписания с более редкими автоматическими обновлениями пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="a18a4-123">If you have a large number of publications or subscriptions, consider setting a less frequent automatic refresh schedule for the user interface.</span></span>  
  
-   <span data-ttu-id="a18a4-124">Избегайте одновременного запуска нескольких экземпляров монитора репликации.</span><span class="sxs-lookup"><span data-stu-id="a18a4-124">Avoid concurrently running multiple instances of Replication Monitor.</span></span>  
  
-   <span data-ttu-id="a18a4-125">Избегайте регистрации большого числа распространителей и установки монитора репликации для автоматического подключения к ним.</span><span class="sxs-lookup"><span data-stu-id="a18a4-125">Avoid registering a large number of Distributors and setting Replication Monitor to automatically connect to all of them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a18a4-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="a18a4-126">See Also</span></span>  
 <span data-ttu-id="a18a4-127">[Запуск задания по обслуживанию репликаций (среда SQL Server Management Studio)](../../../ssms/sql-server-management-studio-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="a18a4-127">[Run Replication Maintenance Jobs &#40;SQL Server Management Studio&#41;](../../../ssms/sql-server-management-studio-ssms.md) </span></span>  
 [<span data-ttu-id="a18a4-128">Наблюдение за репликацией</span><span class="sxs-lookup"><span data-stu-id="a18a4-128">Monitoring Replication</span></span>](../monitoring-replication.md)  
  
  
