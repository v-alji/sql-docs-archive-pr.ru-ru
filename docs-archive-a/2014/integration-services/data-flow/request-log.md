---
title: Журнал запросов | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 165d3833-0493-490c-9f63-8a134a7fafb8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 024012878ae94c5ba6276648e289e6e6f7c93d7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657171"
---
# <a name="request-log"></a><span data-ttu-id="426dc-102">Журнал запросов</span><span class="sxs-lookup"><span data-stu-id="426dc-102">Request Log</span></span>
  <span data-ttu-id="426dc-103">Используйте диалоговое окно **Журнал запросов** для просмотра событий, зарегистрированных в момент запроса, который выполняется в системе SAP Netweaver BW для образца данных.</span><span class="sxs-lookup"><span data-stu-id="426dc-103">Use the **Request Log** dialog box to view the events that are logged during the request that is made to the SAP Netweaver BW system for sample data.</span></span> <span data-ttu-id="426dc-104">Эти сведения могут быть полезны, если необходимо устранить неисправности в конфигурации источника SAP BW.</span><span class="sxs-lookup"><span data-stu-id="426dc-104">This information can be useful if you have to troubleshoot your configuration of the SAP BW source.</span></span>  
  
 <span data-ttu-id="426dc-105">Для получения дополнительных сведений о компоненте источника SAP BW для [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 для SAP BW см. раздел [Источник SAP BW](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="426dc-105">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="426dc-106">Документация по Microsoft Connector 1.1 для SAP BW предполагает, что читатель знаком со средой SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="426dc-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="426dc-107">Дополнительные сведения о SAP Netweaver BW или сведения о настройке объектов и процессов SAP Netweaver BW см. в документации SAP.</span><span class="sxs-lookup"><span data-stu-id="426dc-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="426dc-108">Для извлечения данных из SAP Netweaver BW требуется дополнительная лицензия SAP.</span><span class="sxs-lookup"><span data-stu-id="426dc-108">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="426dc-109">Обратитесь к SAP, чтобы уточнить требования.</span><span class="sxs-lookup"><span data-stu-id="426dc-109">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="426dc-110">**Открытие диалогового окна «Журнал запросов»**</span><span class="sxs-lookup"><span data-stu-id="426dc-110">**To open the Request Log dialog box**</span></span>  
  
1.  <span data-ttu-id="426dc-111">В [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте пакет [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий источник SAP BW.</span><span class="sxs-lookup"><span data-stu-id="426dc-111">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="426dc-112">На вкладке **Поток данных** дважды щелкните источник SAP BW.</span><span class="sxs-lookup"><span data-stu-id="426dc-112">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="426dc-113">В **Редакторе источника SAP BW**щелкните **Диспетчер соединений** , чтобы открыть страницу редактора **Диспетчер соединений** .</span><span class="sxs-lookup"><span data-stu-id="426dc-113">In the **SAP BW Source Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="426dc-114">После настройки источника SAP BW, нажмите кнопку **Предварительный просмотр** , чтобы просмотреть события в диалоговом окне **Журнал запросов** .</span><span class="sxs-lookup"><span data-stu-id="426dc-114">After you configure the SAP BW source, click **Preview** to preview the events in the **Request Log** dialog box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="426dc-115">Щелчок правой кнопкой мыши **Предварительный просмотр** также открывает диалоговое окно **Предварительный просмотр** .</span><span class="sxs-lookup"><span data-stu-id="426dc-115">Clicking **Preview** also opens the **Preview** dialog box.</span></span> <span data-ttu-id="426dc-116">Дополнительные сведения об этом диалоговом окне см. в разделе [Preview](preview.md).</span><span class="sxs-lookup"><span data-stu-id="426dc-116">For more information about this dialog box, see [Preview](preview.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="426dc-117">Параметры</span><span class="sxs-lookup"><span data-stu-id="426dc-117">Options</span></span>  
 <span data-ttu-id="426dc-118">**Time**</span><span class="sxs-lookup"><span data-stu-id="426dc-118">**Time**</span></span>  
 <span data-ttu-id="426dc-119">Отображает время записи события в журнал.</span><span class="sxs-lookup"><span data-stu-id="426dc-119">Displays the time that the event that was logged.</span></span>  
  
 <span data-ttu-id="426dc-120">**Тип**</span><span class="sxs-lookup"><span data-stu-id="426dc-120">**Type**</span></span>  
 <span data-ttu-id="426dc-121">Указывает тип события, которое было зарегистрировано в журнале.</span><span class="sxs-lookup"><span data-stu-id="426dc-121">Displays the type of the event that was logged.</span></span> <span data-ttu-id="426dc-122">В следующей таблице перечислены возможные типы событий.</span><span class="sxs-lookup"><span data-stu-id="426dc-122">The following table lists the possible event types.</span></span>  
  
|<span data-ttu-id="426dc-123">Значение</span><span class="sxs-lookup"><span data-stu-id="426dc-123">Value</span></span>|<span data-ttu-id="426dc-124">Description</span><span class="sxs-lookup"><span data-stu-id="426dc-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="426dc-125">S</span><span class="sxs-lookup"><span data-stu-id="426dc-125">S</span></span>|<span data-ttu-id="426dc-126">Сообщение об успехе.</span><span class="sxs-lookup"><span data-stu-id="426dc-126">Success message.</span></span>|  
|<span data-ttu-id="426dc-127">E</span><span class="sxs-lookup"><span data-stu-id="426dc-127">E</span></span>|<span data-ttu-id="426dc-128">Сообщение об ошибке</span><span class="sxs-lookup"><span data-stu-id="426dc-128">Error message</span></span>|  
|<span data-ttu-id="426dc-129">W</span><span class="sxs-lookup"><span data-stu-id="426dc-129">W</span></span>|<span data-ttu-id="426dc-130">Предупреждающее сообщение.</span><span class="sxs-lookup"><span data-stu-id="426dc-130">Warning message.</span></span>|  
|<span data-ttu-id="426dc-131">I</span><span class="sxs-lookup"><span data-stu-id="426dc-131">I</span></span>|<span data-ttu-id="426dc-132">Информационное сообщение.</span><span class="sxs-lookup"><span data-stu-id="426dc-132">Informational message.</span></span>|  
|<span data-ttu-id="426dc-133">Объект</span><span class="sxs-lookup"><span data-stu-id="426dc-133">A</span></span>|<span data-ttu-id="426dc-134">Операция была прервана.</span><span class="sxs-lookup"><span data-stu-id="426dc-134">The operation was aborted.</span></span>|  
  
 <span data-ttu-id="426dc-135">**Сообщение**</span><span class="sxs-lookup"><span data-stu-id="426dc-135">**Message**</span></span>  
 <span data-ttu-id="426dc-136">Отображает текст сообщения, связанный с событием, записанным в журнал.</span><span class="sxs-lookup"><span data-stu-id="426dc-136">Displays the message text that is associated with the logged event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="426dc-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="426dc-137">See Also</span></span>  
 <span data-ttu-id="426dc-138">[Редактор источника SAP BW (страница "Диспетчер подключений")](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="426dc-138">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="426dc-139">Справка F1 по Microsoft Connector 1.1 для SAP BW</span><span class="sxs-lookup"><span data-stu-id="426dc-139">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
