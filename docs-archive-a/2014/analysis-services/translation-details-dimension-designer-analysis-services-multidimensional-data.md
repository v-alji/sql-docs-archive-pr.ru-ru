---
title: Сведения о переводе (вкладка «Переводы», конструктор измерений) (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensiondesigner.translations.translationpane.tranlationdetails.f1
ms.assetid: 0aa61df3-f2b0-4703-a63b-124da672dcc3
author: minewiskan
ms.author: owend
ms.openlocfilehash: a7cbe4a3c69111d0f82f96ff5125f80fe0c2c57f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738768"
---
# <a name="translation-details-translations-tab-dimension-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="a3b84-102">Сведения о переводе (вкладка «Переводы», конструктор измерений) (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="a3b84-102">Translation Details (Translations Tab, Dimension Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="a3b84-103">Панель **Подробности перевода** на вкладке **Переводы** окна «Конструктор измерений» позволяет определять переводы для выбранного измерения и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="a3b84-103">Use the **Translation Details** pane on the **Translations** tab of Dimension Designer to define and manage translations for the currently selected dimension.</span></span>  
  
 <span data-ttu-id="a3b84-104">**Отображение панели «Подробности перевода»**</span><span class="sxs-lookup"><span data-stu-id="a3b84-104">**To display the Translations Details pane**</span></span>  
  
1.  <span data-ttu-id="a3b84-105">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , а затем откройте нужное измерение.</span><span class="sxs-lookup"><span data-stu-id="a3b84-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, and then open the dimension that you want.</span></span>  
  
2.  <span data-ttu-id="a3b84-106">Перейдите на вкладку **Переводы** .</span><span class="sxs-lookup"><span data-stu-id="a3b84-106">Click the **Translations** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a3b84-107">Варианты</span><span class="sxs-lookup"><span data-stu-id="a3b84-107">Options</span></span>  
 <span data-ttu-id="a3b84-108">**Язык по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="a3b84-108">**Default Language**</span></span>  
 <span data-ttu-id="a3b84-109">Устанавливает имена объектов измерения на языке по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a3b84-109">Sets the names of the dimension objects in the default language.</span></span>  
  
 <span data-ttu-id="a3b84-110">**Тип объекта**</span><span class="sxs-lookup"><span data-stu-id="a3b84-110">**Object Type**</span></span>  
 <span data-ttu-id="a3b84-111">Отображается свойство, которое будет переведено.</span><span class="sxs-lookup"><span data-stu-id="a3b84-111">Displays the property that will be translated.</span></span> <span data-ttu-id="a3b84-112">Только объекты и свойства, для которых указаны значения, могут быть переведены.</span><span class="sxs-lookup"><span data-stu-id="a3b84-112">Only objects and properties for which values have been specified can be translated.</span></span> <span data-ttu-id="a3b84-113">Следующие свойства могут быть переведены.</span><span class="sxs-lookup"><span data-stu-id="a3b84-113">The following properties can be translated:</span></span>  
  
-   <span data-ttu-id="a3b84-114">Измерение</span><span class="sxs-lookup"><span data-stu-id="a3b84-114">Dimension</span></span>  
  
     <span data-ttu-id="a3b84-115">Свойства `Caption` и `AttributeAllMember`</span><span class="sxs-lookup"><span data-stu-id="a3b84-115">`Caption` and `AttributeAllMember` properties</span></span>  
  
-   <span data-ttu-id="a3b84-116">attribute</span><span class="sxs-lookup"><span data-stu-id="a3b84-116">Attribute</span></span>  
  
     <span data-ttu-id="a3b84-117">Свойства `Caption`, `AttributeHierarchyDisplayFolder` и `NamingTemplate`</span><span class="sxs-lookup"><span data-stu-id="a3b84-117">`Caption`, `AttributeHierarchyDisplayFolder`, and `NamingTemplate` properties</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a3b84-118">Свойство `NamingTemplate` доступно только для родительских атрибутов.</span><span class="sxs-lookup"><span data-stu-id="a3b84-118">The `NamingTemplate` property is available only for parent attributes.</span></span>  
  
-   <span data-ttu-id="a3b84-119">Иерархия</span><span class="sxs-lookup"><span data-stu-id="a3b84-119">Hierarchy</span></span>  
  
     <span data-ttu-id="a3b84-120">Свойства `Caption` и `AllMemberName`</span><span class="sxs-lookup"><span data-stu-id="a3b84-120">`Caption` and `AllMemberName` properties</span></span>  
  
-   <span data-ttu-id="a3b84-121">Level</span><span class="sxs-lookup"><span data-stu-id="a3b84-121">Level</span></span>  
  
     <span data-ttu-id="a3b84-122">Свойство `Caption`</span><span class="sxs-lookup"><span data-stu-id="a3b84-122">`Caption` property</span></span>  
  
 **\<Language>**  
 <span data-ttu-id="a3b84-123">Введите или выберите значение свойства данного объекта измерения на выбранном языке.</span><span class="sxs-lookup"><span data-stu-id="a3b84-123">Type or select the property value of the dimension object in the selected language.</span></span> <span data-ttu-id="a3b84-124">Нажав кнопку с многоточием (**...**) можно открыть дополнительные диалоговые окна, в зависимости от изменяемого свойства.</span><span class="sxs-lookup"><span data-stu-id="a3b84-124">Clicking the ellipsis button (**...**) opens additional dialog boxes, depending on the property being edited:</span></span>  
  
-   <span data-ttu-id="a3b84-125">Свойство `NamingTemplate`</span><span class="sxs-lookup"><span data-stu-id="a3b84-125">`NamingTemplate` property</span></span>  
  
     <span data-ttu-id="a3b84-126">Открывает [Диалоговое окно "Шаблон именования уровней" (службы Analysis Services — многомерные данные)](level-naming-template-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="a3b84-126">Displays the [Level Naming Template Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](level-naming-template-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
-   <span data-ttu-id="a3b84-127">Свойство `Caption` (для атрибутов)</span><span class="sxs-lookup"><span data-stu-id="a3b84-127">`Caption` property (for attributes)</span></span>  
  
     <span data-ttu-id="a3b84-128">Открывает [Диалоговое окно "Перевод данных атрибута" (службы Analysis Services — многомерные данные)](attribute-data-translation-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="a3b84-128">Displays the [Attribute Data Translation Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](attribute-data-translation-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
## <a name="shortcut-menu"></a><span data-ttu-id="a3b84-129">Контекстное меню</span><span class="sxs-lookup"><span data-stu-id="a3b84-129">Shortcut Menu</span></span>  
 <span data-ttu-id="a3b84-130">В контекстном меню, отображаемом при щелчке перевода на панели **Сведения о переводе** правой кнопкой мыши, имеются следующие пункты.</span><span class="sxs-lookup"><span data-stu-id="a3b84-130">The following options are available in the shortcut menu displayed by right-clicking a translation in the **Translation Details** pane:</span></span>  
  
 <span data-ttu-id="a3b84-131">**Новый перевод**</span><span class="sxs-lookup"><span data-stu-id="a3b84-131">**New Translation**</span></span>  
 <span data-ttu-id="a3b84-132">Выберите этот параметр для отображения диалогового окна **Выбор языка** и создания нового перевода.</span><span class="sxs-lookup"><span data-stu-id="a3b84-132">Select to display the **Select Language** dialog box and create a new translation.</span></span> <span data-ttu-id="a3b84-133">Перевод будет отображаться в виде нового столбца в сетке **Сведения о переводе** .</span><span class="sxs-lookup"><span data-stu-id="a3b84-133">The translation will appear as a new column in the **Translation Details** grid.</span></span>  
  
 <span data-ttu-id="a3b84-134">**Удалить перевод**</span><span class="sxs-lookup"><span data-stu-id="a3b84-134">**Delete Translation**</span></span>  
 <span data-ttu-id="a3b84-135">Выберите для удаления выбранного перевода.</span><span class="sxs-lookup"><span data-stu-id="a3b84-135">Select to delete the selected translation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a3b84-136">Этот параметр становится доступен только если щелкнуть ячейку правой кнопкой мыши с целью удаления перевода.</span><span class="sxs-lookup"><span data-stu-id="a3b84-136">The option is enabled only if you right-clicked a cell to delete the translation.</span></span>  
  
 <span data-ttu-id="a3b84-137">**Создать столбец заголовков**</span><span class="sxs-lookup"><span data-stu-id="a3b84-137">**New Caption Column**</span></span>  
 <span data-ttu-id="a3b84-138">Выберите для вывода диалогового окна **Перевод данных атрибута** и для определения нового столбца заголовков при изменении атрибута в сетке **Сведения о переводе** .</span><span class="sxs-lookup"><span data-stu-id="a3b84-138">Select to display the **Attribute Data Translation** dialog box and define a new caption column when you modify an attribute in the **Translation Details** grid.</span></span> <span data-ttu-id="a3b84-139">Чтобы данный параметр был доступен, ячейка в столбце перевода для атрибута должна быть выделена в сетке **Сведения о переводе** .</span><span class="sxs-lookup"><span data-stu-id="a3b84-139">To enable this option, a cell in a translation column for an attribute must be selected in the **Translation Details** grid.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a3b84-140">Этот режим доступен, только щелкнув правой кнопкой мыши ячейку с целью удаления столбца перевода атрибута.</span><span class="sxs-lookup"><span data-stu-id="a3b84-140">The option is enabled only if you right-clicked a cell to delete the translation column of an attribute.</span></span>  
  
 <span data-ttu-id="a3b84-141">**Изменить столбец заголовков**</span><span class="sxs-lookup"><span data-stu-id="a3b84-141">**Edit Caption Column**</span></span>  
 <span data-ttu-id="a3b84-142">Выберите для вывода диалогового окна **Перевод данных атрибута** и изменения существующего столбца заголовков при изменении атрибута в сетке **Сведения о переводе** .</span><span class="sxs-lookup"><span data-stu-id="a3b84-142">Select to display the **Attribute Data Translation** dialog box and modify an existing caption column when you modify an attribute in the **Translation Details** grid.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a3b84-143"> Этот режим доступен только в том случае, если ячейка столбца перевода, содержащего для атрибута столбец заголовков, должна быть выбрана в сетке **Подробности перевода** .</span><span class="sxs-lookup"><span data-stu-id="a3b84-143">The option is enabled only if a cell in a translation column that contains a caption column for an attribute must be selected in the **Translation Details** grid.</span></span>  
  
 <span data-ttu-id="a3b84-144">**Удалить столбец заголовков**</span><span class="sxs-lookup"><span data-stu-id="a3b84-144">**Delete Caption Column**</span></span>  
 <span data-ttu-id="a3b84-145">Выберите для удаления столбца заголовков для выбранного атрибута в сетке **Сведения о переводе** .</span><span class="sxs-lookup"><span data-stu-id="a3b84-145">Select to delete the caption column for the selected attribute in the **Translation Details** grid.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a3b84-146">Этот режим становится доступен только если щелкнуть правой кнопкой мыши ячейку в столбце перевода, содержащего столбец заголовков для атрибута.</span><span class="sxs-lookup"><span data-stu-id="a3b84-146">The option is enabled only if you right-clicked a cell in a translation column that contains a caption column for an attribute.</span></span>  
  
 <span data-ttu-id="a3b84-147">**Показать все атрибуты**</span><span class="sxs-lookup"><span data-stu-id="a3b84-147">**Show All Attributes**</span></span>  
 <span data-ttu-id="a3b84-148">Выберите для включения режима отображения всех атрибутов, определенных для выбранного измерения, включая атрибуты, для которых иерархии атрибутов отключены.</span><span class="sxs-lookup"><span data-stu-id="a3b84-148">Select to toggle the display of all attributes defined for the selected dimension, including attributes for which attribute hierarchies are disabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3b84-149">См. также:</span><span class="sxs-lookup"><span data-stu-id="a3b84-149">See Also</span></span>  
 [<span data-ttu-id="a3b84-150">Переводы &#40;конструктор измерений&#41; &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="a3b84-150">Translations &#40;Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](translations-dimension-designer-analysis-services-multidimensional-data.md)  
  
  
