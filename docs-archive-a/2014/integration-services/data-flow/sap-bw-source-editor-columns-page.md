---
title: Редактор источника SAP BW (страница "Столбцы") | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: c2ec8bb7-be9b-4783-ad88-32512de784b0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ba605360d01abc520cedfbc457dd89319ed83c52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738552"
---
# <a name="sap-bw-source-editor-columns-page"></a><span data-ttu-id="66c92-102">Редактор источников SAP BW (страница «Столбцы»)</span><span class="sxs-lookup"><span data-stu-id="66c92-102">SAP BW Source Editor (Columns Page)</span></span>
  <span data-ttu-id="66c92-103">Страница **Столбцы** диалогового окна **Редактор источников SAP BW** используется для сопоставления выходного столбца с каждым внешним (исходным) столбцом.</span><span class="sxs-lookup"><span data-stu-id="66c92-103">Use the **Columns** page of the **SAP BW Source Editor** to map an output column to each external (source) column.</span></span>  
  
 <span data-ttu-id="66c92-104">Для получения дополнительных сведений о компоненте источника SAP BW для [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 для SAP BW см. раздел [Источник SAP BW](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="66c92-104">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="66c92-105">Документация по Microsoft Connector 1.1 для SAP BW предполагает, что читатель знаком со средой SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="66c92-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="66c92-106">Дополнительные сведения о SAP Netweaver BW или сведения о настройке объектов и процессов SAP Netweaver BW см. в документации SAP.</span><span class="sxs-lookup"><span data-stu-id="66c92-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="66c92-107">Для извлечения данных из SAP Netweaver BW требуется дополнительная лицензия SAP.</span><span class="sxs-lookup"><span data-stu-id="66c92-107">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="66c92-108">Обратитесь к SAP, чтобы уточнить требования.</span><span class="sxs-lookup"><span data-stu-id="66c92-108">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="66c92-109">**Открытие страницы «Столбцы»**</span><span class="sxs-lookup"><span data-stu-id="66c92-109">**To open the Columns page**</span></span>  
  
1.  <span data-ttu-id="66c92-110">В [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте пакет [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий источник SAP BW.</span><span class="sxs-lookup"><span data-stu-id="66c92-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="66c92-111">На вкладке **Поток данных** дважды щелкните источник SAP BW.</span><span class="sxs-lookup"><span data-stu-id="66c92-111">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="66c92-112">В **Редакторе источников SAP BW**щелкните **Столбцы** , чтобы открыть страницу редактора **Столбцы** .</span><span class="sxs-lookup"><span data-stu-id="66c92-112">In the **SAP BW Source Editor**, click **Columns** to open the **Columns** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="66c92-113">Параметры</span><span class="sxs-lookup"><span data-stu-id="66c92-113">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="66c92-114">Если вы не знаете все значения, необходимые для настройки источника, может потребоваться связаться с администратором SAP.</span><span class="sxs-lookup"><span data-stu-id="66c92-114">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="66c92-115">**Доступные внешние столбцы**</span><span class="sxs-lookup"><span data-stu-id="66c92-115">**Available External Columns**</span></span>  
 <span data-ttu-id="66c92-116">Просмотрите список доступных внешних столбцов в источнике данных, а затем выберите столбцы, которые нужно включить в поток данных.</span><span class="sxs-lookup"><span data-stu-id="66c92-116">View the list of available external columns in the data source, and then select the columns to be included in the data flow.</span></span>  
  
 <span data-ttu-id="66c92-117">Чтобы включить столбец в поток данных, установите флажок, соответствующий этому столбцу.</span><span class="sxs-lookup"><span data-stu-id="66c92-117">To include a column in the data flow, select the check box that corresponds to that column.</span></span> <span data-ttu-id="66c92-118">Порядок, в котором устанавливаются флажки, определяет порядок вывода столбцов.</span><span class="sxs-lookup"><span data-stu-id="66c92-118">The order in which you select the check boxes determines the order in which columns will be output.</span></span> <span data-ttu-id="66c92-119">Таким образом, первый установленный флажок будет указывать первый выводимый столбец, второй флажок будет указывать второй выводимый столбец и т. д.</span><span class="sxs-lookup"><span data-stu-id="66c92-119">That is, the first check box that you select will be the first output column, the second check box will be the second output columns, and so on.</span></span>  
  
 <span data-ttu-id="66c92-120">**Внешний столбец**</span><span class="sxs-lookup"><span data-stu-id="66c92-120">**External Column**</span></span>  
 <span data-ttu-id="66c92-121">Просмотрите выбранные внешние (исходные) столбцы.</span><span class="sxs-lookup"><span data-stu-id="66c92-121">View the selected external (source) columns.</span></span> <span data-ttu-id="66c92-122">Выбранные столбцы отобразятся в том порядке, в котором будут отображаться соответствующие выводимые столбцы при настройке компонентов нисходящего потока, использующих данные из этого источника.</span><span class="sxs-lookup"><span data-stu-id="66c92-122">The selected columns appear in the order in which you will see their corresponding output columns when you configure downstream components that consume data from this source.</span></span>  
  
 <span data-ttu-id="66c92-123">Для изменения порядка столбцов в списке **Доступные внешние столбцы** снимите флажки для всех столбцов.</span><span class="sxs-lookup"><span data-stu-id="66c92-123">To change the order of the columns, in the **Available External Columns** list, clear the check boxes for all columns.</span></span> <span data-ttu-id="66c92-124">После этого выберите столбцы в том порядке, в котором они должны отображаться.</span><span class="sxs-lookup"><span data-stu-id="66c92-124">Then, select the columns in the order that you want them to appear.</span></span>  
  
 <span data-ttu-id="66c92-125">**Выходной столбец**</span><span class="sxs-lookup"><span data-stu-id="66c92-125">**Output Column**</span></span>  
 <span data-ttu-id="66c92-126">Введите уникальное имя для каждого выходного столбца.</span><span class="sxs-lookup"><span data-stu-id="66c92-126">Provide a unique name for each output column.</span></span> <span data-ttu-id="66c92-127">По умолчанию используется имя выбранного внешнего (исходного) столбца.</span><span class="sxs-lookup"><span data-stu-id="66c92-127">The default is the name of the selected external (source) column.</span></span> <span data-ttu-id="66c92-128">Однако можно ввести любое уникальное описательное имя.</span><span class="sxs-lookup"><span data-stu-id="66c92-128">However, you can enter any unique, descriptive name.</span></span> [!INCLUDE[ssIS](../../includes/ssis-md.md)] <span data-ttu-id="66c92-129">отобразятся имена **Выходной столбец** при настройке компонентов нисходящего потока, использующих данные из этого источника.</span><span class="sxs-lookup"><span data-stu-id="66c92-129">Designer will display the **Output Column** names for the columns when you configure downstream components that consume data from this source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66c92-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="66c92-130">See Also</span></span>  
 <span data-ttu-id="66c92-131">[Редактор источника SAP BW (страница "Диспетчер подключений")](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="66c92-131">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="66c92-132">[Редактор источника SAP BW (страница "Вывод ошибок")](sap-bw-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="66c92-132">[SAP BW Source Editor &#40;Error Output Page&#41;](sap-bw-source-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="66c92-133">[Редактор источника SAP BW (страница "Дополнительно")](sap-bw-source-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="66c92-133">[SAP BW Source Editor &#40;Advanced Page&#41;](sap-bw-source-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="66c92-134">Справка F1 по Microsoft Connector 1.1 для SAP BW</span><span class="sxs-lookup"><span data-stu-id="66c92-134">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
