---
title: Обновление ячеек (XMLA) | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- modifying cells
- XMLA, cells
- updating cells
- cells [Analysis Services]
- XML for Analysis, cells
ms.assetid: a1c61496-36ee-4bce-98d9-d13440d349aa
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2c3d9a7c27533666c75102d9eac3b8311bfe4af6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738945"
---
# <a name="updating-cells-xmla"></a><span data-ttu-id="7e415-102">Обновление ячеек (XML для аналитики)</span><span class="sxs-lookup"><span data-stu-id="7e415-102">Updating Cells (XMLA)</span></span>
  <span data-ttu-id="7e415-103">Команду [UpdateCells](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/updatecells-element-xmla) можно использовать для изменения значения одной или нескольких ячеек куба, включенных для обратной записи куба.</span><span class="sxs-lookup"><span data-stu-id="7e415-103">You can use the [UpdateCells](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/updatecells-element-xmla) command to change the value of one or more cells in a cube enabled for cube writeback.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="7e415-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] хранит обновленные сведения в отдельной таблице обратной записи для каждой секции, содержащей обновляемые ячейки.</span><span class="sxs-lookup"><span data-stu-id="7e415-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] stores the updated information in a separate writeback table for each partition that contains cells to be updated.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7e415-105">Команда `UpdateCells` не поддерживает операции выделения памяти во время обратной записи куба.</span><span class="sxs-lookup"><span data-stu-id="7e415-105">The `UpdateCells` command does not support allocations during cube writeback.</span></span> <span data-ttu-id="7e415-106">Чтобы использовать выделенную обратную запись, необходимо использовать команду [инструкции](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/statement-element-xmla) для отправки инструкции UPDATE многомерных выражений (MDX).</span><span class="sxs-lookup"><span data-stu-id="7e415-106">To use allocated writeback, you should use the [Statement](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/statement-element-xmla) command to send a Multidimensional Expressions (MDX) UPDATE statement.</span></span> <span data-ttu-id="7e415-107">Дополнительные сведения см. в разделе [инструкция UPDATE CUBE &#40;&#41;многомерных выражений ](/sql/mdx/mdx-data-manipulation-update-cube).</span><span class="sxs-lookup"><span data-stu-id="7e415-107">For more information, see [UPDATE CUBE Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-update-cube).</span></span>  
  
## <a name="specifying-cells"></a><span data-ttu-id="7e415-108">Указание ячеек</span><span class="sxs-lookup"><span data-stu-id="7e415-108">Specifying Cells</span></span>  
 <span data-ttu-id="7e415-109">Свойство [Cell](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cell-element-xmla) `UpdateCells` команды содержит обновляемые ячейки.</span><span class="sxs-lookup"><span data-stu-id="7e415-109">The [Cell](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cell-element-xmla) property of the `UpdateCells` command contains the cells to be updated.</span></span> <span data-ttu-id="7e415-110">Каждая ячейка в свойстве `Cell` указывается при помощи ее порядкового номера.</span><span class="sxs-lookup"><span data-stu-id="7e415-110">You identify each cell in the `Cell` property using that cell's ordinal number.</span></span> <span data-ttu-id="7e415-111">Концептуально, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ячейки в Кубе нумеруются так, как если бы куб был *p*многомерным массивом, где *p* — это число осей.</span><span class="sxs-lookup"><span data-stu-id="7e415-111">Conceptually, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] numbers cells in a cube as if the cube were a *p*-dimensional array, where *p* is the number of axes.</span></span> <span data-ttu-id="7e415-112">Адресация ячеек осуществляется по строкам.</span><span class="sxs-lookup"><span data-stu-id="7e415-112">Cells are addressed in row-major order.</span></span> <span data-ttu-id="7e415-113">На следующем рисунке показана формула для вычисления порядкового номера ячейки.</span><span class="sxs-lookup"><span data-stu-id="7e415-113">The following illustration shows the formula for calculating the ordinal number of a cell.</span></span>  
  
 <span data-ttu-id="7e415-114">![Формула вычисления порядкового номера ячейки](../../analysis-services/dev-guide/media/cellordinalformula.gif "Формула вычисления порядкового номера ячейки")</span><span class="sxs-lookup"><span data-stu-id="7e415-114">![Formula to calculate the cell ordinal position](../../analysis-services/dev-guide/media/cellordinalformula.gif "Formula to calculate the cell ordinal position")</span></span>  
  
 <span data-ttu-id="7e415-115">Когда вы узнаете порядковый номер ячейки, можно указать предполагаемое значение ячейки в свойстве [значение](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/value-element-xmla) свойства [ячейки](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cell-element-xmla) .</span><span class="sxs-lookup"><span data-stu-id="7e415-115">Once you know a cell's ordinal number, you can indicate the intended value of the cell in the [Value](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/value-element-xmla) property of the [Cell](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cell-element-xmla) property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e415-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="7e415-116">See Also</span></span>  
 <span data-ttu-id="7e415-117">[Элемент Update &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/update-element-xmla) </span><span class="sxs-lookup"><span data-stu-id="7e415-117">[Update Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/update-element-xmla) </span></span>  
 [<span data-ttu-id="7e415-118">Разработка с использованием XMLA в службах Analysis Services</span><span class="sxs-lookup"><span data-stu-id="7e415-118">Developing with XMLA in Analysis Services</span></span>](../multidimensional-models-scripting-language-assl-xmla/developing-with-xmla-in-analysis-services.md)  
  
  
