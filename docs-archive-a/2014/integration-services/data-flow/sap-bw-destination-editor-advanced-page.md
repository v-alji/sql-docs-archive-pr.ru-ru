---
title: Редактор назначения "SAP BW" (страница "Дополнительно") | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 862957db-bbc6-4dda-bc0e-591457f1baa7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0c5ca943b804ad39cc391cb1cf7f06e056ddbe56
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665035"
---
# <a name="sap-bw-destination-editor-advanced-page"></a><span data-ttu-id="d187b-102">Редактор назначений SAP BW (страница «Дополнительно»)</span><span class="sxs-lookup"><span data-stu-id="d187b-102">SAP BW Destination Editor (Advanced Page)</span></span>
  <span data-ttu-id="d187b-103">Используйте страницу **Дополнительно** **редактора назначений SAP BW** , чтобы задать дополнительные параметры, такие как размер пакета и сведения о времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="d187b-103">Use the **Advanced** page of the **SAP BW Destination Editor** to set advanced settings such as package size and time-out information.</span></span>  
  
 <span data-ttu-id="d187b-104">Для получения дополнительных сведений о назначении SAP BW для [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 для SAP BW см. раздел [Назначение SAP BW](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="d187b-104">To learn more about the SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d187b-105">Документация по Microsoft Connector 1.1 для SAP BW предполагает, что читатель знаком со средой SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="d187b-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="d187b-106">Дополнительные сведения о SAP Netweaver BW или сведения о настройке объектов и процессов SAP Netweaver BW см. в документации SAP.</span><span class="sxs-lookup"><span data-stu-id="d187b-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="d187b-107">**Открытие страницы «Дополнительно»**</span><span class="sxs-lookup"><span data-stu-id="d187b-107">**To open the Advanced page**</span></span>  
  
1.  <span data-ttu-id="d187b-108">В [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте пакет [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий назначение SAP BW.</span><span class="sxs-lookup"><span data-stu-id="d187b-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="d187b-109">На вкладке **Поток данных** дважды щелкните назначение SAP BW.</span><span class="sxs-lookup"><span data-stu-id="d187b-109">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="d187b-110">В **Редакторе назначений SAP BW**щелкните **Дополнительно** , чтобы открыть страницу редактора **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="d187b-110">In the **SAP BW Destination Editor**, click **Advanced** to open the **Advanced** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d187b-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="d187b-111">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d187b-112">Если вы не знаете все значения, необходимые для настройки назначения, может потребоваться связаться с администратором SAP.</span><span class="sxs-lookup"><span data-stu-id="d187b-112">If you do not know all the values that are required to configure the destination, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="d187b-113">**Размер пакета**</span><span class="sxs-lookup"><span data-stu-id="d187b-113">**Package size**</span></span>  
 <span data-ttu-id="d187b-114">Укажите, сколько строк данных будут передаваться за один раз.</span><span class="sxs-lookup"><span data-stu-id="d187b-114">Specify how many rows of data will be transferred at a time.</span></span> <span data-ttu-id="d187b-115">Оптимальное значение для этого параметра зависит от системы SAP Netweaver BW и от возможной дополнительной обработки данных.</span><span class="sxs-lookup"><span data-stu-id="d187b-115">The optimal value for this parameter depends on the SAP Netweaver BW system and on additional processing of the data that might occur.</span></span> <span data-ttu-id="d187b-116">Обычно значения от 2000 до 20 000 обеспечивают самую высокую производительность.</span><span class="sxs-lookup"><span data-stu-id="d187b-116">Typically, values between 2000 and 20000 offer the best performance.</span></span>  
  
 <span data-ttu-id="d187b-117">**Запустить цепочку процессов**</span><span class="sxs-lookup"><span data-stu-id="d187b-117">**Trigger process chain**</span></span>  
 <span data-ttu-id="d187b-118">(Необязательно) Укажите имя цепочки процессов, которую нужно активировать после завершения загрузки данных.</span><span class="sxs-lookup"><span data-stu-id="d187b-118">(Optional) Specify the name of a process chain to be triggered after the loading of data is completed.</span></span>  
  
 <span data-ttu-id="d187b-119">**Время ожидания для InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="d187b-119">**Timeout for waiting InfoPackage**</span></span>  
 <span data-ttu-id="d187b-120">Укажите максимальное число секунд, в течение которых назначение должно ожидать завершения InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="d187b-120">Specify the maximum number of seconds that the destination should wait for the InfoPackage to finish.</span></span>  
  
 <span data-ttu-id="d187b-121">**Дождаться завершения передачи данных**</span><span class="sxs-lookup"><span data-stu-id="d187b-121">**Wait for data transfer to finish**</span></span>  
 <span data-ttu-id="d187b-122">Укажите, следует ли назначению ожидать завершения загрузки данных системой SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="d187b-122">Specify whether the destination should wait until the SAP Netweaver BW system has finished loading the data.</span></span>  
  
 <span data-ttu-id="d187b-123">**Не запускать InfoPackage (только ожидание)**</span><span class="sxs-lookup"><span data-stu-id="d187b-123">**No InfoPackage Start (Only Wait)**</span></span>  
 <span data-ttu-id="d187b-124">Укажите, что назначение не инициирует включение InfoPackage, а ожидает уведомления о начале загрузки данных системой SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="d187b-124">Specify that the destination does not trigger an InfoPackage, but just waits for notification that the SAP Netweaver BW system has started loading the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d187b-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="d187b-125">See Also</span></span>  
 <span data-ttu-id="d187b-126">[Редактор назначений SAP BW (страница "Диспетчер подключений")](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="d187b-126">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="d187b-127">[Редактор назначений SAP BW (страница "Сопоставления")](sap-bw-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="d187b-127">[SAP BW Destination Editor &#40;Mappings Page&#41;](sap-bw-destination-editor-mappings-page.md) </span></span>  
 <span data-ttu-id="d187b-128">[Редактор назначений SAP BW (страница "Вывод ошибок")](sap-bw-destination-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="d187b-128">[SAP BW Destination Editor &#40;Error Output Page&#41;](sap-bw-destination-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="d187b-129">Справка F1 по Microsoft Connector 1.1 для SAP BW</span><span class="sxs-lookup"><span data-stu-id="d187b-129">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
