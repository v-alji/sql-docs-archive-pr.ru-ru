---
title: Диалоговое окно «Построитель вычисляемых элементов» (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.calculatedmemberbuilderdialog.f1
ms.assetid: 73b89a9f-f403-4ab8-99f7-e3ceb870c260
author: minewiskan
ms.author: owend
ms.openlocfilehash: 240e2f2471bf77c403119fd51278a975badc8358
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656807"
---
# <a name="calculated-member-builder-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="e3e5b-102">Диалоговое окно «Построитель вычисляемых элементов» (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="e3e5b-102">Calculated Member Builder Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="e3e5b-103">Диалоговое окно **Построитель вычисляемых элементов** в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] позволяет построить вычисляемые элементы.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-103">Use the **Calculated Member Builder** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to build a calculated member.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e3e5b-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="e3e5b-104">Options</span></span>  
  
|<span data-ttu-id="e3e5b-105">Термин</span><span class="sxs-lookup"><span data-stu-id="e3e5b-105">Term</span></span>|<span data-ttu-id="e3e5b-106">Определение</span><span class="sxs-lookup"><span data-stu-id="e3e5b-106">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="e3e5b-107">**имя**;</span><span class="sxs-lookup"><span data-stu-id="e3e5b-107">**Name**</span></span>|<span data-ttu-id="e3e5b-108">Введите имя вычисляемого элемента.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-108">Type the name of the calculated member.</span></span>|  
|<span data-ttu-id="e3e5b-109">**Родительская иерархия**</span><span class="sxs-lookup"><span data-stu-id="e3e5b-109">**Parent Hierarchy**</span></span>|<span data-ttu-id="e3e5b-110">Выберите иерархию, в которой должен быть создан вычисляемый элемент.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-110">Select the hierarchy in which to create the calculated member.</span></span>|  
|<span data-ttu-id="e3e5b-111">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="e3e5b-111">**Parent Member**</span></span>|<span data-ttu-id="e3e5b-112">Данный параметр включен, если выбрана родительская иерархия (отличная от измерения `Measures`), имеющая несколько уровней.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-112">This option is enabled if you select a parent hierarchy (other than the `Measures` dimension) that has more than one level.</span></span> <span data-ttu-id="e3e5b-113">Нажмите кнопку с многоточием (**...**), чтобы выбрать родительский элемент.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-113">Click the ellipsis (**...**) button to select a parent member.</span></span> <span data-ttu-id="e3e5b-114">Родительский элемент определяет расположение вычисляемого элемента в структуре измерения.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-114">The parent member determines the location of the calculated member in the dimension structure.</span></span>|  
|<span data-ttu-id="e3e5b-115">**Выражение**</span><span class="sxs-lookup"><span data-stu-id="e3e5b-115">**Expression**</span></span>|<span data-ttu-id="e3e5b-116">Введите многомерное выражение, которое будет использовано.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-116">Type the MDX expression that will be used.</span></span>|  
|<span data-ttu-id="e3e5b-117">**Проверка**</span><span class="sxs-lookup"><span data-stu-id="e3e5b-117">**Check**</span></span>|<span data-ttu-id="e3e5b-118">Нажмите кнопку **Проверить** для выполнения проверки многомерного выражения, определенного в поле **Выражение**.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-118">Click **Check** to test the MDX expression defined in **Expression**.</span></span>|  
|<span data-ttu-id="e3e5b-119">**Метаданные**</span><span class="sxs-lookup"><span data-stu-id="e3e5b-119">**Metadata**</span></span>|<span data-ttu-id="e3e5b-120">Отображает метаданные для текущего объекта служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , который может быть включен в многомерное выражение, определенное в поле **Выражение**.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-120">Displays metadata for the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object that can be included in the MDX expression defined in **Expression**.</span></span><br /><br /> <span data-ttu-id="e3e5b-121">Чтобы скопировать синтаксис многомерного выражения для выбранного элемента, щелкните правой кнопкой мыши этот элемент и выберите команду **Копировать**или перетащите выбранный элемент в поле **Выражение**.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-121">You can copy the MDX syntax for the selected item by right-clicking the item and selecting **Copy**, or by dragging the selected item to **Expression**.</span></span>|  
|<span data-ttu-id="e3e5b-122">**Функции**</span><span class="sxs-lookup"><span data-stu-id="e3e5b-122">**Functions**</span></span>|<span data-ttu-id="e3e5b-123">Отображает доступные функции многомерных выражений для текущего экземпляра служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e3e5b-123">Displays the available MDX functions for the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span> <span data-ttu-id="e3e5b-124">Перечисленные элементы извлекаются из набора строк схемы MDSCHEMA_FUNCTIONS.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-124">The items listed are retrieved from the MDSCHEMA_FUNCTIONS schema rowset.</span></span><br /><br /> <span data-ttu-id="e3e5b-125">Чтобы скопировать синтаксис многомерного выражения для выбранного элемента, щелкните правой кнопкой мыши этот элемент и выберите команду **Копировать**или перетащите выбранный элемент в поле **Выражение**.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-125">You can copy the MDX syntax for the selected item by right-clicking the item and selecting **Copy**, or by dragging the selected item to **Expression**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e3e5b-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="e3e5b-126">See Also</span></span>  
 [<span data-ttu-id="e3e5b-127">Справочник по многомерным выражениям (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="e3e5b-127">Multidimensional Expressions &#40;MDX&#41; Reference</span></span>](/sql/mdx/multidimensional-expressions-mdx-reference)  
  
  
