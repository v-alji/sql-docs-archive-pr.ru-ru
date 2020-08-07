---
title: Сведения о публикации, предупреждения (публикация моментальных снимков, SQL Server 2005 и более поздних версий) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.warningsandagents.snapshot.f1
ms.assetid: 7aa2eb52-b6b7-4dd3-8483-8ef00d9f0435
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a3ae662a339e1e211ce4f46a588f4d7de65bf5e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733913"
---
# <a name="publication-information-warnings-snapshot-publication-sql-server-2005-and-later"></a><span data-ttu-id="1f3a6-102">Сведения о публикации, предупреждения (публикация моментального снимка, SQL Server 2005 и более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="1f3a6-102">Publication Information, Warnings (Snapshot Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="1f3a6-103">Вкладка **Предупреждения** доступна для распространителей, работающих с [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] или более поздними версиями.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-103">The **Warnings** tab is available for Distributors that are running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions.</span></span> <span data-ttu-id="1f3a6-104">Вкладка **Предупреждения** позволяет выполнять следующие задачи для выбранных публикаций:</span><span class="sxs-lookup"><span data-stu-id="1f3a6-104">The **Warnings** tab allows you to perform the following tasks for the selected publication:</span></span>  
  
-   <span data-ttu-id="1f3a6-105">включить предупреждения;</span><span class="sxs-lookup"><span data-stu-id="1f3a6-105">Enable warnings.</span></span>  
  
-   <span data-ttu-id="1f3a6-106">указать пороговые значения для предупреждений;</span><span class="sxs-lookup"><span data-stu-id="1f3a6-106">Specify thresholds associated with warnings.</span></span>  
  
-   <span data-ttu-id="1f3a6-107">указать оповещения, связанные с предупреждениями;</span><span class="sxs-lookup"><span data-stu-id="1f3a6-107">Define alerts associated with warnings.</span></span>  
  
## <a name="warnings-thresholds-and-alerts"></a><span data-ttu-id="1f3a6-108">Предупреждения, пороговые значения и оповещения</span><span class="sxs-lookup"><span data-stu-id="1f3a6-108">Warnings, Thresholds, and Alerts</span></span>  
 <span data-ttu-id="1f3a6-109">По умолчанию монитор репликации отображает предупреждения для неинициализированных подписок: состояние **Неинициализированная подписка** отображается в виде предупреждения в столбце **Состояние** страниц, содержащих сведения о подписке.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-109">By default, Replication Monitor displays warnings for uninitialized subscriptions: a status of **Uninitialized subscription** is displayed as a warning in the **Status** column of pages that include subscription information.</span></span> <span data-ttu-id="1f3a6-110">Для публикаций моментальных снимков также можно указать, чтобы при приближении истечения срока действия подписки выдавалось предупреждение посредством установки параметра **Предупреждать, если действие подписки истекает до порогового значения**.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-110">For snapshot publications, you can also specify that imminent subscription expiration results in a warning by setting the option **Warn if a subscription will expire within the threshold**.</span></span> <span data-ttu-id="1f3a6-111">Если указанное пороговое значение достигнуто или превышено, состояние подписки отображается как **Срок действия скоро истекает или истек** (в том случае если не требуется отобразить более важную информацию).</span><span class="sxs-lookup"><span data-stu-id="1f3a6-111">If the specified threshold is met or exceeded, the subscription status is displayed as **Expiring soon/Expired** (unless an issue with a higher priority needs to be displayed).</span></span>  
  
 <span data-ttu-id="1f3a6-112">Достижение порогового значения помимо отображения предупреждения в мониторе репликации может также вызывать системное предупреждение.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-112">In addition to displaying a warning in Replication Monitor, reaching a threshold can also trigger an alert.</span></span> <span data-ttu-id="1f3a6-113">Предупреждения определяются нажатием кнопки **Настройка предупреждений** и указанием сведений в диалоговом окне **Настройка предупреждений репликации** .</span><span class="sxs-lookup"><span data-stu-id="1f3a6-113">Alerts are defined by clicking **Configure Alerts** and providing information in the **Configure Replication Alerts** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1f3a6-114">Параметры</span><span class="sxs-lookup"><span data-stu-id="1f3a6-114">Options</span></span>  
 <span data-ttu-id="1f3a6-115">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="1f3a6-115">**Enabled**</span></span>  
 <span data-ttu-id="1f3a6-116">Выберите, чтобы включить предупреждение и указать пороговое значение.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-116">Select to enable a warning and specify a threshold.</span></span>  
  
 <span data-ttu-id="1f3a6-117">**Предупреждение**</span><span class="sxs-lookup"><span data-stu-id="1f3a6-117">**Warning**</span></span>  
 <span data-ttu-id="1f3a6-118">Описание предупреждения, связанного с пороговым значением.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-118">A description of the warning associated with a threshold.</span></span>  
  
 <span data-ttu-id="1f3a6-119">**Пороговое значение**.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-119">**Threshold**</span></span>  
 <span data-ttu-id="1f3a6-120">Укажите пороговое значение.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-120">Specify a value for the threshold.</span></span>  
  
 <span data-ttu-id="1f3a6-121">**Настройка предупреждений**</span><span class="sxs-lookup"><span data-stu-id="1f3a6-121">**Configure Alerts**</span></span>  
 <span data-ttu-id="1f3a6-122">Выберите строку в сетке **Предупреждения** и нажмите кнопку **Настройка предупреждений** для запуска диалогового окна **Настройка предупреждений репликации** .</span><span class="sxs-lookup"><span data-stu-id="1f3a6-122">Select a row in the **Warnings** grid, and click **Configure Alerts** to launch the **Configure Replication Alerts** dialog box.</span></span> <span data-ttu-id="1f3a6-123">Это диалоговое окно позволяет определить оповещение, связанное с выбранным пороговым значением и предупреждением.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-123">The dialog box allows you to define an alert, which is associated with the selected threshold and warning.</span></span>  
  
 <span data-ttu-id="1f3a6-124">**Отменить изменения**</span><span class="sxs-lookup"><span data-stu-id="1f3a6-124">**Discard Changes**</span></span>  
 <span data-ttu-id="1f3a6-125">Нажмите эту кнопку для отмены всех произведенных изменений предупреждениях и пороговых значениях.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-125">Click to discard any changes to warnings and thresholds.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1f3a6-126">Нажатие кнопки **Отменить изменения** не затрагивает предупреждения, определенные в диалоговом окне **Настройка предупреждений репликации** .</span><span class="sxs-lookup"><span data-stu-id="1f3a6-126">Clicking **Discard Changes** does not affect alerts defined in the **Configure Replication Alerts** dialog box.</span></span>  
  
 <span data-ttu-id="1f3a6-127">**Сохранить изменения**</span><span class="sxs-lookup"><span data-stu-id="1f3a6-127">**Save Changes**</span></span>  
 <span data-ttu-id="1f3a6-128">Нажмите эту кнопку для сохранения всех произведенных изменений предупреждений и пороговых значений.</span><span class="sxs-lookup"><span data-stu-id="1f3a6-128">Click to save any changes to warnings and thresholds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f3a6-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="1f3a6-129">See Also</span></span>  
 <span data-ttu-id="1f3a6-130">[Запуск монитора репликации](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="1f3a6-130">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="1f3a6-131">[Просмотр сведений и выполнение задач с помощью монитора репликации](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="1f3a6-131">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="1f3a6-132">Наблюдение за репликацией</span><span class="sxs-lookup"><span data-stu-id="1f3a6-132">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
