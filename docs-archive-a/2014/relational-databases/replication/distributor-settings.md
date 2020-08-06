---
title: Диалоговое окно "Параметры распространителя" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.DistributorSettings.f1
helpviewer_keywords:
- Distributor Settings dialog box
ms.assetid: 8276a521-bdd1-4783-bdb6-7ab43499c0ca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b864620f155e899868c95f58350f98e2b659c4e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655630"
---
# <a name="sql-server-replication-distributor-settings-dialog-box"></a><span data-ttu-id="cf30a-102">Репликация SQL Server диалоговое окно "Параметры распространителя"</span><span class="sxs-lookup"><span data-stu-id="cf30a-102">SQL Server Replication 'Distributor Settings' dialog box</span></span>
  <span data-ttu-id="cf30a-103">В диалоговом окне **Настройки распространителя** можно изменить настройки распространителей, добавленных на левую панель монитора репликации.</span><span class="sxs-lookup"><span data-stu-id="cf30a-103">The **Distributor Settings** dialog box enables you to change settings for Distributors that were added to the left pane in Replication Monitor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="cf30a-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="cf30a-104">Options</span></span>  
 <span data-ttu-id="cf30a-105">**Соединяться автоматически, когда запускается монитор репликации**</span><span class="sxs-lookup"><span data-stu-id="cf30a-105">**Connect automatically when Replication Monitor starts**</span></span>  
 <span data-ttu-id="cf30a-106">Выберите, чтобы разрешить монитору репликации соединяться с распространителем и получать сведения о состоянии.</span><span class="sxs-lookup"><span data-stu-id="cf30a-106">Select to let Replication Monitor connect to the Distributor and retrieve status information.</span></span>  
  
 <span data-ttu-id="cf30a-107">**Соединение**</span><span class="sxs-lookup"><span data-stu-id="cf30a-107">**Connection**</span></span>  
 <span data-ttu-id="cf30a-108">Нажмите, чтобы открыть диалоговое окно **Соединение с сервером** .</span><span class="sxs-lookup"><span data-stu-id="cf30a-108">Click to display the **Connect to Server** dialog box.</span></span> <span data-ttu-id="cf30a-109">Это позволяет просмотреть и изменить свойства соединения и учетные данные, которые монитор репликации использует для соединения с удаленным распространителем.</span><span class="sxs-lookup"><span data-stu-id="cf30a-109">This enables you to view and change the connection properties and credentials that Replication Monitor uses to connect to the Distributor.</span></span>  
  
 <span data-ttu-id="cf30a-110">**Автоматически обновлять состояние этого распространителя и его публикаций**</span><span class="sxs-lookup"><span data-stu-id="cf30a-110">**Automatically refresh the status of this Distributor and its publications**</span></span>  
 <span data-ttu-id="cf30a-111">Выберите, чтобы разрешить монитору репликации автоматически обновлять сведения о состоянии распространителя.</span><span class="sxs-lookup"><span data-stu-id="cf30a-111">Select to let Replication Monitor automatically refresh the status for the Distributor.</span></span> <span data-ttu-id="cf30a-112">Если выбран этот параметр, то монитор репликации опрашивает сведения о состоянии распространителя с интервалом опроса, заданным параметром **Частота обновления** .</span><span class="sxs-lookup"><span data-stu-id="cf30a-112">If this option is selected, Replication Monitor polls the Distributor for status information based on the polling interval set by the **Refresh rate** option.</span></span> <span data-ttu-id="cf30a-113">Дополнительные сведения об обновлении в мониторе репликации см. в разделе [Caching, Refresh, and Replication Monitor Performance](monitor/caching-refresh-and-replication-monitor-performance.md).</span><span class="sxs-lookup"><span data-stu-id="cf30a-113">For more information about refresh in Replication Monitor, see [Caching, Refresh, and Replication Monitor Performance](monitor/caching-refresh-and-replication-monitor-performance.md).</span></span>  
  
 <span data-ttu-id="cf30a-114">**Частота обновления**</span><span class="sxs-lookup"><span data-stu-id="cf30a-114">**Refresh rate**</span></span>  
 <span data-ttu-id="cf30a-115">Введите значение (в секундах), указывающее, как часто монитор репликации должен опрашивать распространитель для получения сведений о состоянии.</span><span class="sxs-lookup"><span data-stu-id="cf30a-115">Enter a value (in seconds) to specify how frequently Replication Monitor should poll the Distributor for status.</span></span> <span data-ttu-id="cf30a-116">Чем меньше значение, тем чаще происходит опрос.</span><span class="sxs-lookup"><span data-stu-id="cf30a-116">Lower values result in more frequent polling.</span></span> <span data-ttu-id="cf30a-117">Это может снизить производительность распространителя, если производится наблюдение за большим числом издателей.</span><span class="sxs-lookup"><span data-stu-id="cf30a-117">This can affect performance at the Distributor if you are monitoring many Publishers.</span></span> <span data-ttu-id="cf30a-118">Рекомендуется протестировать систему для определения подходящего значения.</span><span class="sxs-lookup"><span data-stu-id="cf30a-118">We recommend that you test your system to determine an appropriate value.</span></span> <span data-ttu-id="cf30a-119">Параметр **Частота обновления** используется также и при включении режима **Автоматическое обновление** в любом окне сведений монитора репликации.</span><span class="sxs-lookup"><span data-stu-id="cf30a-119">The **Refresh rate** setting is also used if you select **Auto Refresh** in any of the detail windows in Replication Monitor.</span></span>  
  
 <span data-ttu-id="cf30a-120">**Показать все издатели этого распространителя в следующей группе**</span><span class="sxs-lookup"><span data-stu-id="cf30a-120">**Show all Publishers of this Distributor in the following group**</span></span>  
 <span data-ttu-id="cf30a-121">Выберите группу издателей из списка.</span><span class="sxs-lookup"><span data-stu-id="cf30a-121">Select a Publisher group from the list.</span></span> <span data-ttu-id="cf30a-122">Издатель отображается в свой группе в левой панели.</span><span class="sxs-lookup"><span data-stu-id="cf30a-122">The Publisher is displayed under this group in the left pane.</span></span> <span data-ttu-id="cf30a-123">Группы являются средством упорядочения издателей и не оказывают влияния на работу репликации.</span><span class="sxs-lookup"><span data-stu-id="cf30a-123">Groups provide a way for you to organize Publishers and do not affect how replication functions.</span></span>  
  
 <span data-ttu-id="cf30a-124">**Создать группу**</span><span class="sxs-lookup"><span data-stu-id="cf30a-124">**New Group**</span></span>  
 <span data-ttu-id="cf30a-125">Нажмите эту кнопку для создания новой группы издателей.</span><span class="sxs-lookup"><span data-stu-id="cf30a-125">Click to create a new Publisher group.</span></span> <span data-ttu-id="cf30a-126">Группа издателей представляет собой удобный способ упорядочения издателей в мониторе репликации.</span><span class="sxs-lookup"><span data-stu-id="cf30a-126">A Publisher group provides a way for you to conveniently organize Publishers within Replication Monitor.</span></span> <span data-ttu-id="cf30a-127">Группы не оказывают влияние на данные или связи между серверами в топологии репликации.</span><span class="sxs-lookup"><span data-stu-id="cf30a-127">Groups do not affect the replication of data or the relationship among servers in a replication topology.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf30a-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="cf30a-128">See Also</span></span>  
 <span data-ttu-id="cf30a-129">[Запуск монитора репликации](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="cf30a-129">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 [<span data-ttu-id="cf30a-130">Наблюдение за репликацией</span><span class="sxs-lookup"><span data-stu-id="cf30a-130">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
