---
title: Обновление данных в мониторе репликации | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- refreshing data
ms.assetid: e9582244-7d00-45f4-be16-020a65c76a5e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2f097dea21b06540293e9b60b7de9315323b4168
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750728"
---
# <a name="refresh-data-in-replication-monitor"></a><span data-ttu-id="c8b00-102">Обновление данных в мониторе репликации</span><span class="sxs-lookup"><span data-stu-id="c8b00-102">Refresh Data in Replication Monitor</span></span>
  <span data-ttu-id="c8b00-103">В мониторе репликации главное окно и окна сведений (окна, запущенные из главного окна) могут быть обновлены автоматически или вручную.</span><span class="sxs-lookup"><span data-stu-id="c8b00-103">In Replication Monitor, the main window and detail windows (those windows launched from the main window) can be refreshed automatically or manually.</span></span> <span data-ttu-id="c8b00-104">Чтобы обновить окно вручную, нажмите F5.</span><span class="sxs-lookup"><span data-stu-id="c8b00-104">To refresh a window manually, press F5.</span></span> <span data-ttu-id="c8b00-105">По умолчанию главное окно обновляется автоматически каждые пять секунд. Частота обновления может быть установлена для каждого издателя.</span><span class="sxs-lookup"><span data-stu-id="c8b00-105">By default, the main window is refreshed automatically every five seconds; the rate can be customized for each Publisher.</span></span>  
  
 <span data-ttu-id="c8b00-106">Данные, отображаемые в мониторе репликации, запрашиваются из кэша. Сведения о связи между кэшем и обновлением монитора репликации см. в статье [Кэширование, обновление и производительность монитора репликации](caching-refresh-and-replication-monitor-performance.md).</span><span class="sxs-lookup"><span data-stu-id="c8b00-106">The data displayed in Replication Monitor is queried from a cache; for information about the relationship between the cache and refreshing Replication Monitor, see [Caching, Refresh, and Replication Monitor Performance](caching-refresh-and-replication-monitor-performance.md).</span></span> <span data-ttu-id="c8b00-107">Сведения о запуске монитора репликации см. в [этой статье](start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="c8b00-107">For information about starting Replication Monitor, see [Start the Replication Monitor](start-the-replication-monitor.md).</span></span>  
  
### <a name="to-set-refresh-options-for-replication-monitor"></a><span data-ttu-id="c8b00-108">Установка параметров обновления монитора репликации</span><span class="sxs-lookup"><span data-stu-id="c8b00-108">To set refresh options for Replication Monitor</span></span>  
  
1.  <span data-ttu-id="c8b00-109">Щелкните правой кнопкой мыши издатель в левой панели окна монитора репликации, затем щелкните **Настройки издателя**.</span><span class="sxs-lookup"><span data-stu-id="c8b00-109">Right-click a Publisher in the left pane of Replication Monitor, and then click **Publisher Settings**.</span></span>  
  
2.  <span data-ttu-id="c8b00-110">В диалоговом окне **Настройки издателя** установите параметры **Автоматическое обновление** и **Частота обновления** .</span><span class="sxs-lookup"><span data-stu-id="c8b00-110">In the **Publisher Settings** dialog box, set the **Auto refresh** and **Refresh rate** options.</span></span> <span data-ttu-id="c8b00-111">Настройка **Автоматическое обновление** влияет на главное окно монитора репликации.</span><span class="sxs-lookup"><span data-stu-id="c8b00-111">The **Auto refresh** setting affects the main window in Replication Monitor.</span></span> <span data-ttu-id="c8b00-112">Настройка **Частота обновления** также влияет на любое окно сведений, для которого включено автоматическое обновление (изменения настроек окна сведений вступят в силу только после последующего открытия окна).</span><span class="sxs-lookup"><span data-stu-id="c8b00-112">The **Refresh rate** setting also affects any detail windows that are set to refresh automatically (changes to the setting only affect the detail windows opened after the change).</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-specify-that-a-detail-window-should-automatically-refresh"></a><span data-ttu-id="c8b00-113">Установка автоматического обновления окна сведений</span><span class="sxs-lookup"><span data-stu-id="c8b00-113">To specify that a detail window should automatically refresh</span></span>  
  
1.  <span data-ttu-id="c8b00-114">Откройте окно сведений в мониторе репликации.</span><span class="sxs-lookup"><span data-stu-id="c8b00-114">Open a detail window in Replication Monitor.</span></span> <span data-ttu-id="c8b00-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="c8b00-115">For example:</span></span>  
  
    1.  <span data-ttu-id="c8b00-116">Раскройте на левой панели группу издателей, раскройте издатель и выберите нужную публикацию.</span><span class="sxs-lookup"><span data-stu-id="c8b00-116">Expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
    2.  <span data-ttu-id="c8b00-117">Перейдите на вкладку **Все подписки** .</span><span class="sxs-lookup"><span data-stu-id="c8b00-117">Click the **All Subscriptions** tab.</span></span>  
  
    3.  <span data-ttu-id="c8b00-118">Щелкните правой кнопкой мыши подписку, а затем выберите **Просмотреть сведения**.</span><span class="sxs-lookup"><span data-stu-id="c8b00-118">Right-click a subscription, and then click **View Details**.</span></span>  
  
2.  <span data-ttu-id="c8b00-119">В окне сведений **Подписка \<SubscriptionName>** щелкните **Действие**, а затем щелкните **Автоматическое обновление**.</span><span class="sxs-lookup"><span data-stu-id="c8b00-119">In the **Subscription \<SubscriptionName>** detail window, click **Action**, and then click **Auto Refresh**.</span></span> <span data-ttu-id="c8b00-120">Частота обновления определяется настройкой **Частота обновления** в диалоговом окне **Настройки издателя** .</span><span class="sxs-lookup"><span data-stu-id="c8b00-120">The refresh rate is determined by the **Refresh rate** setting in the **Publisher Settings** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8b00-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="c8b00-121">See Also</span></span>  
 [<span data-ttu-id="c8b00-122">Наблюдение за репликацией</span><span class="sxs-lookup"><span data-stu-id="c8b00-122">Monitoring Replication</span></span>](../monitoring-replication.md)  
  
  
