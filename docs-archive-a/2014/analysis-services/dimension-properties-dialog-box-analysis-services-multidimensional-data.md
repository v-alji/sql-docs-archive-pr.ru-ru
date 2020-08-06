---
title: Диалоговое окно «Свойства измерения» (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.sqlserverstudio.dimensionproperties.f1
helpviewer_keywords:
- Dimension Properties dialog box
ms.assetid: 7235d443-b2ce-4c53-b2eb-abceb28394bb
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0523220c76c11280165bc825c5c00c5eb9e23be6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669157"
---
# <a name="dimension-properties-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="e446f-102">Диалоговое окно «Свойства измерения» (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="e446f-102">Dimension Properties Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="e446f-103">Используйте диалоговое окно **Свойства измерения** в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , чтобы установить свойства измерения в базе данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e446f-103">Use the **Dimension Properties** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to set the properties of a dimension in an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="e446f-104">Можно отобразить диалоговое окно **Свойства измерения** , щелкнув правой кнопкой мыши измерение в обозревателе объектов и выбрав пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="e446f-104">You can display the **Dimension Properties** dialog box by right-clicking a dimension in Object Explorer and selecting **Properties**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e446f-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="e446f-105">Options</span></span>  
  
|<span data-ttu-id="e446f-106">Термин</span><span class="sxs-lookup"><span data-stu-id="e446f-106">Term</span></span>|<span data-ttu-id="e446f-107">Определение</span><span class="sxs-lookup"><span data-stu-id="e446f-107">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="e446f-108">**имя**;</span><span class="sxs-lookup"><span data-stu-id="e446f-108">**Name**</span></span>|<span data-ttu-id="e446f-109">Показывает имя измерения.</span><span class="sxs-lookup"><span data-stu-id="e446f-109">Displays the name of the dimension.</span></span>|  
|<span data-ttu-id="e446f-110">**Идентификатор**</span><span class="sxs-lookup"><span data-stu-id="e446f-110">**ID**</span></span>|<span data-ttu-id="e446f-111">Показывает идентификатор измерения.</span><span class="sxs-lookup"><span data-stu-id="e446f-111">Displays the identifier of the dimension.</span></span>|  
|<span data-ttu-id="e446f-112">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e446f-112">**Description**</span></span>|<span data-ttu-id="e446f-113">Показывает описание измерения.</span><span class="sxs-lookup"><span data-stu-id="e446f-113">Displays the description of the dimension.</span></span>|  
|<span data-ttu-id="e446f-114">**Отметка времени создания**</span><span class="sxs-lookup"><span data-stu-id="e446f-114">**Create Timestamp**</span></span>|<span data-ttu-id="e446f-115">Отображает дату и время создания измерения.</span><span class="sxs-lookup"><span data-stu-id="e446f-115">Displays the date and time the dimension was created.</span></span>|  
|<span data-ttu-id="e446f-116">**Последнее обновление схемы**</span><span class="sxs-lookup"><span data-stu-id="e446f-116">**Last Schema Update**</span></span>|<span data-ttu-id="e446f-117">Отображает дату и время последнего обновления метаданных для измерения.</span><span class="sxs-lookup"><span data-stu-id="e446f-117">Displays the date and time the metadata for the dimension was last updated.</span></span>|  
|<span data-ttu-id="e446f-118">**Режим обработки**</span><span class="sxs-lookup"><span data-stu-id="e446f-118">**Processing Mode**</span></span>|<span data-ttu-id="e446f-119">Выбирает режим обработки для использования в этом измерении.</span><span class="sxs-lookup"><span data-stu-id="e446f-119">Select the processing mode to use for the dimension.</span></span> <span data-ttu-id="e446f-120">Дополнительные сведения о значениях этого свойства см. в разделе <xref:Microsoft.AnalysisServices.Dimension.ProcessingMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="e446f-120">For more information about the values for this property, see <xref:Microsoft.AnalysisServices.Dimension.ProcessingMode%2A>.</span></span>|  
|<span data-ttu-id="e446f-121">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="e446f-121">**State**</span></span>|<span data-ttu-id="e446f-122">Отображает состояние обработки измерения.</span><span class="sxs-lookup"><span data-stu-id="e446f-122">Displays the processing state of the dimension.</span></span> <span data-ttu-id="e446f-123">Дополнительные сведения о значениях этого свойства см. в разделе <xref:Microsoft.AnalysisServices.ProcessableMajorObject.State%2A>.</span><span class="sxs-lookup"><span data-stu-id="e446f-123">For more information about the values for this property, see <xref:Microsoft.AnalysisServices.ProcessableMajorObject.State%2A>.</span></span>|  
|<span data-ttu-id="e446f-124">**Последняя обработка**</span><span class="sxs-lookup"><span data-stu-id="e446f-124">**Last Processed**</span></span>|<span data-ttu-id="e446f-125">Отображает дату и время последней обработки измерения.</span><span class="sxs-lookup"><span data-stu-id="e446f-125">Displays the date and time the dimension was last processed.</span></span>|  
|<span data-ttu-id="e446f-126">**Текущий режим хранения**</span><span class="sxs-lookup"><span data-stu-id="e446f-126">**Current Storage Mode**</span></span>|<span data-ttu-id="e446f-127">Отображает текущий режим хранения для измерения.</span><span class="sxs-lookup"><span data-stu-id="e446f-127">Displays the current storage mode for the dimension.</span></span> <span data-ttu-id="e446f-128">Дополнительные сведения о значениях этого свойства см. в разделе <xref:Microsoft.AnalysisServices.Dimension.CurrentStorageMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="e446f-128">For more information about the values for this property, see <xref:Microsoft.AnalysisServices.Dimension.CurrentStorageMode%2A>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e446f-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="e446f-129">See Also</span></span>  
 <span data-ttu-id="e446f-130">[Analysis Services конструкторов и диалоговых окон &#40;многомерных данных&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="e446f-130">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="e446f-131">Измерения (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="e446f-131">Dimensions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md)  
  
  
