---
title: 'Репликация SQL Server: диалоговое окно "Настройки издателя" | Документация Майкрософт'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publishersettings.f1
helpviewer_keywords:
- Publisher Settings dialog box
ms.assetid: 4fb70427-082d-4179-82a1-34b235accc43
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3a9a5ca5b0d7bfae895287708af159f3316e4474
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749708"
---
# <a name="sql-server-replication-publisher-settings-dialog-box"></a><span data-ttu-id="39daf-102">Репликация SQL Server: диалоговое окно "Настройки издателя"</span><span class="sxs-lookup"><span data-stu-id="39daf-102">SQL Server Replication 'Publisher Settings' dialog box</span></span>
  <span data-ttu-id="39daf-103">Диалоговое окно **Настройки издателя** позволяет изменить настройки издателей, добавленных к левой панели монитора репликации.</span><span class="sxs-lookup"><span data-stu-id="39daf-103">The **Publisher Settings** dialog box allows you to change settings for Publishers that have been added to the left pane in Replication Monitor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="39daf-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="39daf-104">Options</span></span>  
 <span data-ttu-id="39daf-105">**Соединение с издателем**</span><span class="sxs-lookup"><span data-stu-id="39daf-105">**Publisher Connection**</span></span>  
 <span data-ttu-id="39daf-106">Выберите этот пункт, чтобы открыть диалоговое окно **Соединение с сервером** , позволяющее просмотреть и изменить свойства соединения и учетные данные, которые монитор репликации использует для соединения с издателем.</span><span class="sxs-lookup"><span data-stu-id="39daf-106">Click to launch the **Connect to Server** dialog box, which allows you to view and change the connection properties and credentials Replication Monitor uses to connect to a Publisher.</span></span>  
  
 <span data-ttu-id="39daf-107">**Соединение с распространителем**</span><span class="sxs-lookup"><span data-stu-id="39daf-107">**Distributor Connection**</span></span>  
 <span data-ttu-id="39daf-108">Параметр доступен, если для издателя используется удаленный распространитель.</span><span class="sxs-lookup"><span data-stu-id="39daf-108">Displayed only if the Publisher uses a remote Distributor.</span></span> <span data-ttu-id="39daf-109">Выберите этот пункт, чтобы открыть диалоговое окно **Соединение с сервером** , позволяющее просмотреть и изменить свойства соединения и учетные данные, которые монитор репликации использует для соединения с удаленным распространителем.</span><span class="sxs-lookup"><span data-stu-id="39daf-109">Click to launch the **Connect to Server** dialog box, which allows you to view and change the connection properties and credentials Replication Monitor uses to connect to the remote Distributor.</span></span>  
  
 <span data-ttu-id="39daf-110">**Соединяться автоматически, когда запускается монитор репликации**</span><span class="sxs-lookup"><span data-stu-id="39daf-110">**Connect automatically when Replication Monitor starts**</span></span>  
 <span data-ttu-id="39daf-111">Выберите этот параметр, чтобы разрешить монитору репликации автоматически соединяться с распространителем и извлекать сведения о состоянии издателя, выбранного в сетке в верхней части диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="39daf-111">Select to allow Replication Monitor to automatically connect to the Distributor and retrieve status information for the Publisher selected in the grid at the top of the dialog box.</span></span> <span data-ttu-id="39daf-112">Если этот флажок снят, то после запуска монитора репликации необходимо установить соединение вручную: щелкните правой кнопкой мыши значок издателя на левой панели монитора репликации и выберите пункт меню **Подключить**.</span><span class="sxs-lookup"><span data-stu-id="39daf-112">If this checkbox is cleared, you must manually connect after launching Replication Monitor: right-click the Publisher in the left pane of Replication Monitor, and click **Connect**.</span></span>  
  
 <span data-ttu-id="39daf-113">**Автоматически обновлять состояние этого издателя и его публикаций**</span><span class="sxs-lookup"><span data-stu-id="39daf-113">**Automatically refresh the status of this Publisher and its publications**</span></span>  
 <span data-ttu-id="39daf-114">Выберите этот параметр, чтобы разрешить монитору репликации автоматически обновлять состояние издателя, выбранного в сетке в верхней части диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="39daf-114">Select to allow Replication Monitor to automatically refresh status for the Publisher selected in the grid at the top of the dialog box.</span></span> <span data-ttu-id="39daf-115">Если выбран этот параметр, то монитор репликации опрашивает распространитель для получения сведений о состоянии издателя и его публикаций.</span><span class="sxs-lookup"><span data-stu-id="39daf-115">If this option is selected, Replication Monitor polls the Distributor for status information on the Publisher and its publications.</span></span> <span data-ttu-id="39daf-116">Интервал опроса задается параметром **Частота обновления** .</span><span class="sxs-lookup"><span data-stu-id="39daf-116">The polling interval is set by the **Refresh rate** option.</span></span> <span data-ttu-id="39daf-117">Дополнительные сведения об обновлении в мониторе репликации см. в статье [Кэширование, обновление и производительность монитора репликации](monitor/caching-refresh-and-replication-monitor-performance.md).</span><span class="sxs-lookup"><span data-stu-id="39daf-117">For more information on refresh in Replication Monitor, see [Caching, Refresh, and Replication Monitor Performance](monitor/caching-refresh-and-replication-monitor-performance.md).</span></span>  
  
 <span data-ttu-id="39daf-118">**Частота обновления**</span><span class="sxs-lookup"><span data-stu-id="39daf-118">**Refresh rate**</span></span>  
 <span data-ttu-id="39daf-119">Введите значение (в секундах), указывающее, как часто монитор репликации должен опрашивать распространитель для получения сведений о состоянии.</span><span class="sxs-lookup"><span data-stu-id="39daf-119">Enter a value (in seconds) to specify how frequently Replication Monitor should poll the Distributor for status.</span></span> <span data-ttu-id="39daf-120">Чем ниже значения, тем чаще производится опрос, что может снизить производительность распространителя, если производится наблюдение за большим числом издателей.</span><span class="sxs-lookup"><span data-stu-id="39daf-120">Lower values result in more frequent polling, which can affect performance at the Distributor if you are monitoring a large number of Publishers.</span></span> <span data-ttu-id="39daf-121">Рекомендуется проверить систему для определения подходящего значения.</span><span class="sxs-lookup"><span data-stu-id="39daf-121">It is recommended that you test your system to determine an appropriate value.</span></span> <span data-ttu-id="39daf-122">Параметр **Частота обновления** используется также и при включении режима **Автоматическое обновление** в любом окне сведений монитора репликации.</span><span class="sxs-lookup"><span data-stu-id="39daf-122">The **Refresh rate** setting is also used if you select **Auto Refresh** in any of the detail windows in Replication Monitor.</span></span>  
  
 <span data-ttu-id="39daf-123">**Показывать этот издатель в следующей группе**</span><span class="sxs-lookup"><span data-stu-id="39daf-123">**Show this Publisher in the following group**</span></span>  
 <span data-ttu-id="39daf-124">Выберите группу издателей из списка.</span><span class="sxs-lookup"><span data-stu-id="39daf-124">Select a Publisher group from the list.</span></span> <span data-ttu-id="39daf-125">Издатель отображается в свой группе в левой панели.</span><span class="sxs-lookup"><span data-stu-id="39daf-125">The Publisher is displayed under this group in the left pane.</span></span> <span data-ttu-id="39daf-126">Группы предоставляют способ упорядочить издателей и не оказывают влияние на работу репликации.</span><span class="sxs-lookup"><span data-stu-id="39daf-126">Groups provide a way to organize Publishers and have no effect on how replication functions.</span></span>  
  
 <span data-ttu-id="39daf-127">**Создать группу**</span><span class="sxs-lookup"><span data-stu-id="39daf-127">**New Group**</span></span>  
 <span data-ttu-id="39daf-128">Нажмите эту кнопку для создания новой группы издателей.</span><span class="sxs-lookup"><span data-stu-id="39daf-128">Click to create a new Publisher group.</span></span> <span data-ttu-id="39daf-129">Группа издателей предоставляет удобный способ упорядочить издателей в мониторе репликации.</span><span class="sxs-lookup"><span data-stu-id="39daf-129">A Publisher group provides a convenient way to organize Publishers within Replication Monitor.</span></span> <span data-ttu-id="39daf-130">Группы не оказывают влияние на данные или связи между серверами в топологии репликации.</span><span class="sxs-lookup"><span data-stu-id="39daf-130">Groups do not affect the replication of data or the relationship among servers in a replication topology.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39daf-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="39daf-131">See Also</span></span>  
 <span data-ttu-id="39daf-132">[Запуск монитора репликации](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="39daf-132">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 [<span data-ttu-id="39daf-133">Наблюдение за репликацией</span><span class="sxs-lookup"><span data-stu-id="39daf-133">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
