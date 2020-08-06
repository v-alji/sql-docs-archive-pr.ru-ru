---
title: Диалоговое окно «Добавление издателя»
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.addpublisher.f1
helpviewer_keywords:
- Add Publisher dialog box
ms.assetid: 4b57e298-655f-42c2-82bc-25cdad94a194
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5c7e607c04aa74db7e5facf13051bf0c47c9dae0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655674"
---
# <a name="sql-server-replication-add-publisher-dialog-box"></a><span data-ttu-id="7307c-102">Репликация SQL Server диалоговое окно "Добавление издателя"</span><span class="sxs-lookup"><span data-stu-id="7307c-102">SQL Server Replication 'Add Publisher' dialog box</span></span> 
  <span data-ttu-id="7307c-103">Диалоговое окно **Добавление издателя** позволяет добавить одного или несколько издателей в левую панель монитора репликации.</span><span class="sxs-lookup"><span data-stu-id="7307c-103">The **Add Publisher** dialog box allows you to add to one or more Publishers to the left pane of Replication Monitor.</span></span> <span data-ttu-id="7307c-104">После добавления издателя в правой панели отображаются сведения об издателе, выбранном в левой панели.</span><span class="sxs-lookup"><span data-stu-id="7307c-104">After adding a Publisher, selecting the Publisher in the left pane shows information on the Publisher in the right pane.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7307c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7307c-105">Options</span></span>  
 <span data-ttu-id="7307c-106">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="7307c-106">**Add**</span></span>  
 <span data-ttu-id="7307c-107">Нажмите, чтобы выбрать тип добавляемого издателя, после чего откроется диалоговое окно **Соединение с сервером** .</span><span class="sxs-lookup"><span data-stu-id="7307c-107">Click to select a type of Publisher to add, which launches the **Connect to Server** dialog box.</span></span> <span data-ttu-id="7307c-108">Доступны следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="7307c-108">The options are:</span></span>  
  
-   <span data-ttu-id="7307c-109">**Добавить SQL Serverный издатель...**</span><span class="sxs-lookup"><span data-stu-id="7307c-109">**Add SQL Server Publisher...**</span></span>  
  
     <span data-ttu-id="7307c-110">Подключить к издателю с помощью диалогового окна **Соединение с сервером** .</span><span class="sxs-lookup"><span data-stu-id="7307c-110">Connect to the Publisher using the **Connect to Server** dialog box.</span></span>  
  
-   <span data-ttu-id="7307c-111">**Добавить издатель Oracle...**</span><span class="sxs-lookup"><span data-stu-id="7307c-111">**Add Oracle Publisher...**</span></span>  
  
     <span data-ttu-id="7307c-112">Подключить к распространителю [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], связанному с издателем Oracle, с помощью диалогового окна **Соединение с сервером**.</span><span class="sxs-lookup"><span data-stu-id="7307c-112">Connect to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributor associated with the Oracle Publisher using the **Connect to Server** dialog box.</span></span>  
  
-   <span data-ttu-id="7307c-113">**Укажите распространителя и добавьте его издателей...**</span><span class="sxs-lookup"><span data-stu-id="7307c-113">**Specify a Distributor and Add Its Publishers...**</span></span>  
  
     <span data-ttu-id="7307c-114">Подключить к распространителю [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , связанному с одним или несколькими издателями, с помощью диалогового окна **Соединение с сервером** .</span><span class="sxs-lookup"><span data-stu-id="7307c-114">Connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributor associated with one or more Publishers using the **Connect to Server** dialog box.</span></span>  
  
 <span data-ttu-id="7307c-115">После успешного подключения к издателю или распространителю в сетке, расположенной в верхней части диалогового окна, отображаются имена всех издателей и их распространителей.</span><span class="sxs-lookup"><span data-stu-id="7307c-115">After successfully connecting to the Publisher or Distributor, the name of each Publisher and its Distributor are displayed in the grid at the top of the dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7307c-116">Зачастую распространитель и издатель работают на одном экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], но распространитель может работать и на другом экземпляре (такую конфигурацию называют удаленным распространителем).</span><span class="sxs-lookup"><span data-stu-id="7307c-116">The Distributor and Publisher often run on the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], but the Distributor can run on another instance (this configuration is referred to as a remote Distributor).</span></span>  
  
 <span data-ttu-id="7307c-117">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="7307c-117">**Remove**</span></span>  
 <span data-ttu-id="7307c-118">Чтобы удалить издатель из списка добавляемых издателей, выберите издателя в сетке, расположенной в верхней части диалогового окна, и нажмите кнопку **Удалить** .</span><span class="sxs-lookup"><span data-stu-id="7307c-118">Select a Publisher in the grid at the top of the dialog box, and click **Remove** to remove the Publisher from the list of Publishers to be added.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7307c-119">Эту кнопку нельзя использовать для удаления издателя, если он отображается в мониторе репликации.</span><span class="sxs-lookup"><span data-stu-id="7307c-119">This button cannot be used to remove a Publisher that is already displayed in Replication Monitor.</span></span> <span data-ttu-id="7307c-120">Чтобы удалить такого издателя, щелкните правой кнопкой мыши издателя в левой панели монитора репликации и выберите в контекстном меню пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="7307c-120">To remove a Publisher that is already displayed right-click the Publisher in the left pane of Replication Monitor and click **Remove**.</span></span>  
  
 <span data-ttu-id="7307c-121">**Соединяться автоматически, когда запускается монитор репликации**</span><span class="sxs-lookup"><span data-stu-id="7307c-121">**Connect automatically when Replication Monitor starts**</span></span>  
 <span data-ttu-id="7307c-122">Выберите этот параметр, чтобы разрешить монитору репликации автоматически соединяться с распространителем и извлекать сведения о состоянии издателя, выбранного в сетке в верхней части диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="7307c-122">Select to allow Replication Monitor to automatically connect to the Distributor and retrieve status information for the Publisher selected in the grid at the top of the dialog box.</span></span> <span data-ttu-id="7307c-123">Если этот флажок снят, то после запуска монитора репликации необходимо установить соединение вручную: щелкните правой кнопкой мыши значок издателя на левой панели монитора репликации и выберите пункт меню **Подключить**.</span><span class="sxs-lookup"><span data-stu-id="7307c-123">If this checkbox is cleared, you must manually connect after launching Replication Monitor: right-click the Publisher in the left pane of Replication Monitor, and click **Connect**.</span></span>  
  
 <span data-ttu-id="7307c-124">**Автоматически обновлять состояние этого издателя и его публикаций**</span><span class="sxs-lookup"><span data-stu-id="7307c-124">**Automatically refresh the status of this Publisher and its publications**</span></span>  
 <span data-ttu-id="7307c-125">Выберите этот параметр, чтобы разрешить монитору репликации автоматически обновлять состояние издателя, выбранного в сетке в верхней части диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="7307c-125">Select to allow Replication Monitor to automatically refresh status for the Publisher selected in the grid at the top of the dialog box.</span></span> <span data-ttu-id="7307c-126">Если выбран этот параметр, то монитор репликации опрашивает распространитель для получения сведений о состоянии издателя и его публикаций.</span><span class="sxs-lookup"><span data-stu-id="7307c-126">If this option is selected, Replication Monitor polls the Distributor for status information on the Publisher and its publications.</span></span> <span data-ttu-id="7307c-127">Интервал опроса задается параметром **Частота обновления** .</span><span class="sxs-lookup"><span data-stu-id="7307c-127">The polling interval is set by the **Refresh rate** option.</span></span> <span data-ttu-id="7307c-128">Дополнительные сведения об обновлении в мониторе репликации см. в статье [Кэширование, обновление и производительность монитора репликации](monitor/caching-refresh-and-replication-monitor-performance.md).</span><span class="sxs-lookup"><span data-stu-id="7307c-128">For more information on refresh in Replication Monitor, see [Caching, Refresh, and Replication Monitor Performance](monitor/caching-refresh-and-replication-monitor-performance.md).</span></span>  
  
 <span data-ttu-id="7307c-129">**Частота обновления**</span><span class="sxs-lookup"><span data-stu-id="7307c-129">**Refresh rate**</span></span>  
 <span data-ttu-id="7307c-130">Введите значение (в секундах), указывающее, как часто монитор репликации должен опрашивать распространитель для получения сведений о состоянии.</span><span class="sxs-lookup"><span data-stu-id="7307c-130">Enter a value (in seconds) to specify how frequently Replication Monitor should poll the Distributor for status.</span></span> <span data-ttu-id="7307c-131">Чем ниже значения, тем чаще производится опрос, что может снизить производительность распространителя, если производится наблюдение за большим числом издателей.</span><span class="sxs-lookup"><span data-stu-id="7307c-131">Lower values result in more frequent polling, which can affect performance at the Distributor if you are monitoring a large number of Publishers.</span></span> <span data-ttu-id="7307c-132">Рекомендуется проверить систему для определения подходящего значения.</span><span class="sxs-lookup"><span data-stu-id="7307c-132">It is recommended that you test your system to determine an appropriate value.</span></span> <span data-ttu-id="7307c-133">Параметр **Частота обновления** используется также и при включении режима **Автоматическое обновление** в любом окне сведений монитора репликации.</span><span class="sxs-lookup"><span data-stu-id="7307c-133">The **Refresh rate** setting is also used if you select **Auto Refresh** in any of the detail windows in Replication Monitor.</span></span>  
  
 <span data-ttu-id="7307c-134">**Показывать этот издатель в следующей группе**</span><span class="sxs-lookup"><span data-stu-id="7307c-134">**Show this Publisher in the following group**</span></span>  
 <span data-ttu-id="7307c-135">Выберите группу издателей из списка.</span><span class="sxs-lookup"><span data-stu-id="7307c-135">Select a Publisher group from the list.</span></span> <span data-ttu-id="7307c-136">Издатель отображается в свой группе в левой панели.</span><span class="sxs-lookup"><span data-stu-id="7307c-136">The Publisher is displayed under this group in the left pane.</span></span> <span data-ttu-id="7307c-137">Группы предоставляют способ упорядочить издателей и не оказывают влияние на работу репликации.</span><span class="sxs-lookup"><span data-stu-id="7307c-137">Groups provide a way to organize Publishers and have no effect on how replication functions.</span></span> <span data-ttu-id="7307c-138">Если группы не определены, для создания новой группы нажмите кнопку **Создать группу**.</span><span class="sxs-lookup"><span data-stu-id="7307c-138">If no groups are defined or you want to create a new one, click **New Group**.</span></span>  
  
 <span data-ttu-id="7307c-139">**Создать группу**</span><span class="sxs-lookup"><span data-stu-id="7307c-139">**New Group**</span></span>  
 <span data-ttu-id="7307c-140">Нажмите эту кнопку для создания новой группы издателей.</span><span class="sxs-lookup"><span data-stu-id="7307c-140">Click to create a new Publisher group.</span></span> <span data-ttu-id="7307c-141">Группа издателей предоставляет удобный способ упорядочить издателей в мониторе репликации.</span><span class="sxs-lookup"><span data-stu-id="7307c-141">A Publisher group provides a convenient way to organize Publishers within Replication Monitor.</span></span> <span data-ttu-id="7307c-142">Группы не оказывают влияние на данные или связи между серверами в топологии репликации.</span><span class="sxs-lookup"><span data-stu-id="7307c-142">Groups do not affect the replication of data or the relationship among servers in a replication topology.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7307c-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="7307c-143">See Also</span></span>  
 <span data-ttu-id="7307c-144">[Запуск монитора репликации](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="7307c-144">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 [<span data-ttu-id="7307c-145">Наблюдение за репликацией</span><span class="sxs-lookup"><span data-stu-id="7307c-145">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
