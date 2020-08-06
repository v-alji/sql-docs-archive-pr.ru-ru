---
title: Диалоговое окно «Фильтрация элементов» (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensiondesigner.filtermembers.f1
helpviewer_keywords:
- Filter Members dialog box
ms.assetid: 52c6da1d-9fb5-4dbc-bffa-248d11cd337c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 66980b1afe9d4eed353ae18c37ed1fdd052e62b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654571"
---
# <a name="filter-members-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="9f151-102">Диалоговое окно «Фильтрация элементов» (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="9f151-102">Filter Members Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="9f151-103">Используйте диалоговое окно **Фильтрация элементов** в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] для фильтрации элементов измерения по заголовку элемента, имени элемента, уникальному имени элемента, значению ключевого столбца или значению столбца значений для текущего уровня при просмотре измерения на вкладке **Браузер** в **Конструктор измерений**.</span><span class="sxs-lookup"><span data-stu-id="9f151-103">Use the **Filter Members** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to filter dimension members by member caption, member name, member unique name, key column value, or value column value for the current level while browsing a dimension in the **Browser** tab of **Dimension Designer**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9f151-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="9f151-104">Options</span></span>  
  
|<span data-ttu-id="9f151-105">Термин</span><span class="sxs-lookup"><span data-stu-id="9f151-105">Term</span></span>|<span data-ttu-id="9f151-106">Определение</span><span class="sxs-lookup"><span data-stu-id="9f151-106">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="9f151-107">**Выражение фильтра**</span><span class="sxs-lookup"><span data-stu-id="9f151-107">**Filter expression**</span></span>|<span data-ttu-id="9f151-108">Позволяет отображать сетку свойств, операторов и значений, используемых для создания критерия фильтра.</span><span class="sxs-lookup"><span data-stu-id="9f151-108">Displays a grid of properties, operators, and values used to construct a filter expression.</span></span> <span data-ttu-id="9f151-109">Помните, что после добавления строки ее нельзя удалить.</span><span class="sxs-lookup"><span data-stu-id="9f151-109">Note that after a row is added, it cannot be removed.</span></span> <span data-ttu-id="9f151-110">Для задания нового критерия фильтра это диалоговое окно необходимо закрыть и открыть вновь.</span><span class="sxs-lookup"><span data-stu-id="9f151-110">You must close and reopen the dialog box to specify a new filter expression.</span></span> <span data-ttu-id="9f151-111">Сетка содержит следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="9f151-111">The grid contains the following columns:</span></span><br /><br /> <span data-ttu-id="9f151-112">**Свойство**: выберите свойство элемента, которое будет использоваться для критерия фильтра.</span><span class="sxs-lookup"><span data-stu-id="9f151-112">**Property**: Select the property of the member to use for the filter expression.</span></span><br /><br /> <span data-ttu-id="9f151-113">**Оператор**: выберите оператор, используемый для критерия фильтра.</span><span class="sxs-lookup"><span data-stu-id="9f151-113">**Operator**: Select the operator to use for the filter expression.</span></span><br /><br /> <span data-ttu-id="9f151-114">**Значение**: введите значение свойства, выбранного в поле **свойство** , для вычисления с помощью оператора, указанного в **операторе**.</span><span class="sxs-lookup"><span data-stu-id="9f151-114">**Value**: Type the value of the property selected in **Property** to evaluate using the operator specified in **Operator**.</span></span>|  
|<span data-ttu-id="9f151-115">**Область тестирования**</span><span class="sxs-lookup"><span data-stu-id="9f151-115">**Test pane**</span></span>|<span data-ttu-id="9f151-116">При нажатии кнопки **Тест** на этой панели отображаются элементы, возвращенные критерием фильтра.</span><span class="sxs-lookup"><span data-stu-id="9f151-116">When **Test** is clicked, this pane displays the members returned by the filter expression.</span></span> <span data-ttu-id="9f151-117">Если при использовании критериев, заданных в поле **Критерий фильтра**, не возвращаются никакие элементы, то отображается предупреждение.</span><span class="sxs-lookup"><span data-stu-id="9f151-117">If no members are returned using the criteria specified in **Filter expression**, a warning is displayed.</span></span>|  
|<span data-ttu-id="9f151-118">**Тест**</span><span class="sxs-lookup"><span data-stu-id="9f151-118">**Test**</span></span>|<span data-ttu-id="9f151-119">Нажмите эту кнопку для тестирования критериев, заданных в поле **Критерий фильтра**.</span><span class="sxs-lookup"><span data-stu-id="9f151-119">Click to test the criteria specified in **Filter expression**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9f151-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="9f151-120">See Also</span></span>  
 <span data-ttu-id="9f151-121">[Analysis Services конструкторов и диалоговых окон &#40;многомерных данных&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="9f151-121">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="9f151-122">Конструктор измерений &#40;конструктора&#41; &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="9f151-122">Browser &#40;Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](browser-dimension-designer-analysis-services-multidimensional-data.md)  
  
  
