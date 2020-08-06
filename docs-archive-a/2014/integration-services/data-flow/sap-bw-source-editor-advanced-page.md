---
title: Редактор источника SAP BW (страница "Дополнительно") | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 44f3c991-9e8f-4126-a9a2-2d9da779fb11
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7c78d40555a30031bf39abda18048fda9c648d01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740196"
---
# <a name="sap-bw-source-editor-advanced-page"></a><span data-ttu-id="a9c52-102">Редактор источников SAP BW (страница «Дополнительно»)</span><span class="sxs-lookup"><span data-stu-id="a9c52-102">SAP BW Source Editor (Advanced Page)</span></span>
  <span data-ttu-id="a9c52-103">Используйте страницу **Дополнительно** **Редактора источников SAP BW** , чтобы указать правило преобразования строк и время ожидания, а также сбросить состояние запроса с определенным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="a9c52-103">Use the **Advanced** page of the **SAP BW Source Editor** to specify the string conversion rule and the time-out period, and also to reset the status of a particular Request ID.</span></span>  
  
 <span data-ttu-id="a9c52-104">Для получения дополнительных сведений о компоненте источника SAP BW для [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 для SAP BW см. раздел [Источник SAP BW](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="a9c52-104">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a9c52-105">Документация по Microsoft Connector 1.1 для SAP BW предполагает, что читатель знаком со средой SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="a9c52-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="a9c52-106">Дополнительные сведения о SAP Netweaver BW или сведения о настройке объектов и процессов SAP Netweaver BW см. в документации SAP.</span><span class="sxs-lookup"><span data-stu-id="a9c52-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a9c52-107">Для извлечения данных из SAP Netweaver BW требуется дополнительная лицензия SAP.</span><span class="sxs-lookup"><span data-stu-id="a9c52-107">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="a9c52-108">Обратитесь к SAP, чтобы уточнить требования.</span><span class="sxs-lookup"><span data-stu-id="a9c52-108">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="a9c52-109">**Открытие страницы «Диспетчер соединений»**</span><span class="sxs-lookup"><span data-stu-id="a9c52-109">**To open the Connection Manager page**</span></span>  
  
1.  <span data-ttu-id="a9c52-110">В [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте пакет [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий источник SAP BW.</span><span class="sxs-lookup"><span data-stu-id="a9c52-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="a9c52-111">На вкладке **Поток данных** дважды щелкните источник SAP BW.</span><span class="sxs-lookup"><span data-stu-id="a9c52-111">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="a9c52-112">В **Редакторе источников SAP BW**щелкните **Дополнительно** , чтобы открыть страницу редактора **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="a9c52-112">In the **SAP BW Source Editor**, click **Advanced** to open the **Advanced** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a9c52-113">Параметры</span><span class="sxs-lookup"><span data-stu-id="a9c52-113">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a9c52-114">Если вы не знаете все значения, необходимые для настройки источника, может потребоваться связаться с администратором SAP.</span><span class="sxs-lookup"><span data-stu-id="a9c52-114">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="a9c52-115">**Преобразование строк**</span><span class="sxs-lookup"><span data-stu-id="a9c52-115">**String Conversion**</span></span>  
 <span data-ttu-id="a9c52-116">Укажите правило для преобразования строк.</span><span class="sxs-lookup"><span data-stu-id="a9c52-116">Specify the rule to apply for string conversion.</span></span>  
  
|<span data-ttu-id="a9c52-117">Параметр</span><span class="sxs-lookup"><span data-stu-id="a9c52-117">Option</span></span>|<span data-ttu-id="a9c52-118">Description</span><span class="sxs-lookup"><span data-stu-id="a9c52-118">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="a9c52-119">**Автоматическое преобразование строк**</span><span class="sxs-lookup"><span data-stu-id="a9c52-119">**Automatic string conversion**</span></span>|<span data-ttu-id="a9c52-120">Преобразовать все строки в `nvarchar`, если система SAP Netweaver BW поддерживает Юникод.</span><span class="sxs-lookup"><span data-stu-id="a9c52-120">Convert all strings to `nvarchar` when the SAP Netweaver BW system is a Unicode system.</span></span> <span data-ttu-id="a9c52-121">В противном случае все строки преобразуются в `varchar`.</span><span class="sxs-lookup"><span data-stu-id="a9c52-121">Otherwise, convert all strings to `varchar`.</span></span>|  
|<span data-ttu-id="a9c52-122">**Преобразование строк в varchar**</span><span class="sxs-lookup"><span data-stu-id="a9c52-122">**Convert strings to varchar**</span></span>|<span data-ttu-id="a9c52-123">Все строки преобразуются в `varchar`.</span><span class="sxs-lookup"><span data-stu-id="a9c52-123">Convert all strings to `varchar`.</span></span>|  
|<span data-ttu-id="a9c52-124">**Преобразование строк в nvarchar**</span><span class="sxs-lookup"><span data-stu-id="a9c52-124">**Convert strings to nvarchar**</span></span>|<span data-ttu-id="a9c52-125">Все строки преобразуются в `nvarchar`.</span><span class="sxs-lookup"><span data-stu-id="a9c52-125">Convert all strings to `nvarchar`.</span></span>|  
  
 <span data-ttu-id="a9c52-126">**Время ожидания (в секундах)**</span><span class="sxs-lookup"><span data-stu-id="a9c52-126">**Timeout (seconds)**</span></span>  
 <span data-ttu-id="a9c52-127">Укажите максимальное число секунд для периода ожидания источника.</span><span class="sxs-lookup"><span data-stu-id="a9c52-127">Specify the maximum number of seconds that the source should wait.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a9c52-128">Этот параметр допустим только в том случае, если выбран параметр **W — ждать уведомления** в качестве значения **Режим выполнения** на странице редактора **Диспетчер соединений** .</span><span class="sxs-lookup"><span data-stu-id="a9c52-128">This option is only valid if you have selected **W - Wait for Notify** as the value of **Execution Mode** on the **Connection Manager** page of the editor.</span></span> <span data-ttu-id="a9c52-129">Дополнительные сведения см. в разделе [Редактор источника SAP BW (страница "Диспетчер подключений")](sap-bw-source-editor-connection-manager-page.md).</span><span class="sxs-lookup"><span data-stu-id="a9c52-129">For more information, see [SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md).</span></span>  
  
 <span data-ttu-id="a9c52-130">**Идентификатор запроса**</span><span class="sxs-lookup"><span data-stu-id="a9c52-130">**Request ID**</span></span>  
 <span data-ttu-id="a9c52-131">Укажите идентификатор запроса, состояние которого необходимо сбрасывать до "G — зеленый" при нажатии кнопки **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="a9c52-131">Specify the Request ID whose status you want to reset to "G - Green" when you click **Reset**.</span></span>  
  
 <span data-ttu-id="a9c52-132">**Сброс**</span><span class="sxs-lookup"><span data-stu-id="a9c52-132">**Reset**</span></span>  
 <span data-ttu-id="a9c52-133">Позволяет сбросить состояние идентификатора запроса до «G — зеленый», после отображения запроса на подтверждение.</span><span class="sxs-lookup"><span data-stu-id="a9c52-133">Lets you reset the status of the specified Request ID to "G - Green", after prompting you for confirmation.</span></span> <span data-ttu-id="a9c52-134">Это может быть полезным, если произошла ошибка и система SAP Netweaver BW отметила запрос с состоянием «Красный» или «Желтый».</span><span class="sxs-lookup"><span data-stu-id="a9c52-134">This can be useful when a problem has occurred, and the SAP Netweaver BW system has flagged the request with a yellow or red status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9c52-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="a9c52-135">See Also</span></span>  
 <span data-ttu-id="a9c52-136">[Редактор источника SAP BW (страница "Диспетчер подключений")](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="a9c52-136">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="a9c52-137">[Редактор источника SAP BW (страница "Столбцы")](sap-bw-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="a9c52-137">[SAP BW Source Editor &#40;Columns Page&#41;](sap-bw-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="a9c52-138">[Редактор источника SAP BW (страница "Вывод ошибок")](sap-bw-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="a9c52-138">[SAP BW Source Editor &#40;Error Output Page&#41;](sap-bw-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="a9c52-139">Справка F1 по Microsoft Connector 1.1 для SAP BW</span><span class="sxs-lookup"><span data-stu-id="a9c52-139">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
