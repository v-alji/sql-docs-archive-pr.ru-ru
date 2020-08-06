---
title: Редактор источника SAP BW (страница "Вывод ошибок") | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: b6e23b0c-949a-46d1-8424-4dc3d9035e79
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1a4ad2d02d3f5ec5c1a786019e18fa01665fdc0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728534"
---
# <a name="sap-bw-source-editor-error-output-page"></a><span data-ttu-id="85053-102">Редактор источников SAP BW (страница «Вывод ошибок»)</span><span class="sxs-lookup"><span data-stu-id="85053-102">SAP BW Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="85053-103">Используйте страницу **Вывод ошибок** **Редактора источников SAP BW** для выбора параметров обработки ошибок и задания свойств выходных столбцов ошибок.</span><span class="sxs-lookup"><span data-stu-id="85053-103">Use the **Error Output** page of the **SAP BW Source Editor** to select error handling options and to set properties on error output columns.</span></span>  
  
 <span data-ttu-id="85053-104">Для получения дополнительных сведений о компоненте источника SAP BW для [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 для SAP BW см. раздел [Источник SAP BW](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="85053-104">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="85053-105">Документация по Microsoft Connector 1.1 для SAP BW предполагает, что читатель знаком со средой SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="85053-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="85053-106">Дополнительные сведения о SAP Netweaver BW или сведения о настройке объектов и процессов SAP Netweaver BW см. в документации SAP.</span><span class="sxs-lookup"><span data-stu-id="85053-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="85053-107">Для извлечения данных из SAP Netweaver BW требуется дополнительная лицензия SAP.</span><span class="sxs-lookup"><span data-stu-id="85053-107">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="85053-108">Обратитесь к SAP, чтобы уточнить требования.</span><span class="sxs-lookup"><span data-stu-id="85053-108">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="85053-109">**Открытие страницы «Вывод ошибок»**</span><span class="sxs-lookup"><span data-stu-id="85053-109">**To open the Error Output page**</span></span>  
  
1.  <span data-ttu-id="85053-110">В [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте пакет [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий источник SAP BW.</span><span class="sxs-lookup"><span data-stu-id="85053-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="85053-111">На вкладке **Поток данных** дважды щелкните источник SAP BW.</span><span class="sxs-lookup"><span data-stu-id="85053-111">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="85053-112">В окне **Редактор источников SAP BW**щелкните **Вывод ошибок** , чтобы открыть страницу редактора **Вывод ошибок** .</span><span class="sxs-lookup"><span data-stu-id="85053-112">In the **SAP BW Source Editor**, click **Error Output** to open the **Error Output** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="85053-113">Параметры</span><span class="sxs-lookup"><span data-stu-id="85053-113">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="85053-114">Если вы не знаете все значения, необходимые для настройки источника, может потребоваться связаться с администратором SAP.</span><span class="sxs-lookup"><span data-stu-id="85053-114">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="85053-115">**Вход или выход**</span><span class="sxs-lookup"><span data-stu-id="85053-115">**Input or Output**</span></span>  
 <span data-ttu-id="85053-116">Просмотр имени источника данных.</span><span class="sxs-lookup"><span data-stu-id="85053-116">View the name of the data source.</span></span>  
  
 <span data-ttu-id="85053-117">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="85053-117">**Column**</span></span>  
 <span data-ttu-id="85053-118">Просмотрите внешние (исходные) столбцы, выбранные на странице **Столбцы** диалогового окна **Редактор источников SAP BW** .</span><span class="sxs-lookup"><span data-stu-id="85053-118">View the external (source) columns that you selected on the **Columns** page of the **SAP BW Source Editor** dialog box.</span></span> <span data-ttu-id="85053-119">Дополнительные сведения об этом диалоговом окне см. в разделе [Редактор источника SAP BW (страница "Столбцы")](sap-bw-source-editor-columns-page.md).</span><span class="sxs-lookup"><span data-stu-id="85053-119">For more information about this dialog box, see [SAP BW Source Editor &#40;Columns Page&#41;](sap-bw-source-editor-columns-page.md).</span></span>  
  
 <span data-ttu-id="85053-120">**Ошибка**</span><span class="sxs-lookup"><span data-stu-id="85053-120">**Error**</span></span>  
 <span data-ttu-id="85053-121">Укажите действия компонента источника SAP BW при возникновении ошибки: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="85053-121">Specify what the SAP BW source component should do when there is an error: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="85053-122">**Усечение**</span><span class="sxs-lookup"><span data-stu-id="85053-122">**Truncation**</span></span>  
 <span data-ttu-id="85053-123">Укажите действия компонента источника SAP BW при выполнении усечения: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="85053-123">Specify what the SAP BW source component should do when a truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="85053-124">**Описание**</span><span class="sxs-lookup"><span data-stu-id="85053-124">**Description**</span></span>  
 <span data-ttu-id="85053-125">Просмотреть описание ошибки.</span><span class="sxs-lookup"><span data-stu-id="85053-125">View the description of the error.</span></span>  
  
 <span data-ttu-id="85053-126">**Присвоить указанное значение выбранным ячейкам**</span><span class="sxs-lookup"><span data-stu-id="85053-126">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="85053-127">Укажите действия для компонента источника SAP BW, которые необходимо выполнить со всеми выбранными ячейками при возникновении ошибки или усечения: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="85053-127">Specify what the SAP BW source component should do to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="85053-128">**Применить**</span><span class="sxs-lookup"><span data-stu-id="85053-128">**Apply**</span></span>  
 <span data-ttu-id="85053-129">Применить параметр обработки ошибок к выбранным ячейкам.</span><span class="sxs-lookup"><span data-stu-id="85053-129">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85053-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="85053-130">See Also</span></span>  
 <span data-ttu-id="85053-131">[Редактор источника SAP BW (страница "Диспетчер подключений")](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="85053-131">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="85053-132">[Редактор источника SAP BW (страница "Столбцы")](sap-bw-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="85053-132">[SAP BW Source Editor &#40;Columns Page&#41;](sap-bw-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="85053-133">[Редактор источника SAP BW (страница "Дополнительно")](sap-bw-source-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="85053-133">[SAP BW Source Editor &#40;Advanced Page&#41;](sap-bw-source-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="85053-134">Справка F1 по Microsoft Connector 1.1 для SAP BW</span><span class="sxs-lookup"><span data-stu-id="85053-134">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
