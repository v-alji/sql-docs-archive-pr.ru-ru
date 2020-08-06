---
title: Диалоговое окно «Видимость столбца» (построитель отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10127"
ms.assetid: 0c030cab-6087-45a5-99f0-c7bd693f20a1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4c775734a4dbba2120a2af86e35a3872f5fff718
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730222"
---
# <a name="column-visibility-dialog-box-report-builder"></a><span data-ttu-id="81353-102">Диалоговое окно «Видимость столбцов» (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="81353-102">Column Visibility Dialog Box (Report Builder)</span></span>
  <span data-ttu-id="81353-103">Используйте диалоговое окно **Видимость столбца** , чтобы отобразить или скрыть выбранный столбец при первом запуске отчета либо назначить другой элемент отчета для переключения видимости столбца.</span><span class="sxs-lookup"><span data-stu-id="81353-103">Use the **Column Visibility** dialog box to show or hide the selected column when the report is first run or to use another report item to toggle the visibility of the column.</span></span>  
  
## <a name="options"></a><span data-ttu-id="81353-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="81353-104">Options</span></span>  
 <span data-ttu-id="81353-105">**При первоначальном запуске отчета**</span><span class="sxs-lookup"><span data-stu-id="81353-105">**When the report is initially run**</span></span>  
 <span data-ttu-id="81353-106">Выберите параметр, определяющий, как элемент отчета отображается в отчете первоначально.</span><span class="sxs-lookup"><span data-stu-id="81353-106">Select an option to indicate how the report item is initially displayed in the report.</span></span>  
  
 <span data-ttu-id="81353-107">**Показать**</span><span class="sxs-lookup"><span data-stu-id="81353-107">**Show**</span></span>  
 <span data-ttu-id="81353-108">Выберите этот параметр, чтобы отобразить столбец.</span><span class="sxs-lookup"><span data-stu-id="81353-108">Choose this option to show the column.</span></span>  
  
 <span data-ttu-id="81353-109">**Скрыть**</span><span class="sxs-lookup"><span data-stu-id="81353-109">**Hide**</span></span>  
 <span data-ttu-id="81353-110">Выберите этот параметр, чтобы скрыть столбец.</span><span class="sxs-lookup"><span data-stu-id="81353-110">Choose this option to hide the Column.</span></span>  
  
 <span data-ttu-id="81353-111">**Отображать или скрывать в зависимости от выражения**</span><span class="sxs-lookup"><span data-stu-id="81353-111">**Show or hide based on an expression**</span></span>  
 <span data-ttu-id="81353-112">Этот параметр используется для изменения исходной видимости с помощью выражения.</span><span class="sxs-lookup"><span data-stu-id="81353-112">Choose this option to vary the initial visibility using an expression.</span></span>  
  
 <span data-ttu-id="81353-113">Введите выражение, результат вычисления которого имеет тип `Boolean` (при значении `True` элемент скрыт, а при значении `False` отображается).</span><span class="sxs-lookup"><span data-stu-id="81353-113">Type an expression that evaluates to a `Boolean` value of `True` to hide the item and `False` to show the item.</span></span> <span data-ttu-id="81353-114">Нажмите кнопку Выражение (*FX*), чтобы изменить выражение.</span><span class="sxs-lookup"><span data-stu-id="81353-114">Click the Expression (*fx*) button to edit the expression.</span></span>  
  
 <span data-ttu-id="81353-115">**Отображение может переключаться этим элементом отчета**</span><span class="sxs-lookup"><span data-stu-id="81353-115">**Display can be toggled by this report item**</span></span>  
 <span data-ttu-id="81353-116">Выберите данный параметр для вывода изображения переключателя, который позволяет пользователю отображать или скрывать данный столбец в средстве просмотра отчетов в формате HTML.</span><span class="sxs-lookup"><span data-stu-id="81353-116">Choose this option to display a toggle image that enables the user to show or hide this column in an HTML report viewer.</span></span>  
  
 <span data-ttu-id="81353-117">Введите или выберите имя текстового поля отчета для отображения изображения отчета, например, Textbox1.</span><span class="sxs-lookup"><span data-stu-id="81353-117">Type or select the name of a text box in the report in which to display a toggle image; for example, Textbox1.</span></span> <span data-ttu-id="81353-118">Выбранное текстовое поле должно быть в текущей области или области, содержащей этот элемент отчета.</span><span class="sxs-lookup"><span data-stu-id="81353-118">The text box that you choose must be in the current or containing scope for this report item.</span></span> <span data-ttu-id="81353-119">Например, чтобы включить видимость строк, связанных с дочерней группой, выберите текстовое поле в строке, связанной с родительской группой.</span><span class="sxs-lookup"><span data-stu-id="81353-119">For example, to toggle visibility of rows associated with a child group, select a text box in a row associated with the parent group.</span></span> <span data-ttu-id="81353-120">Чтобы переключить видимость диаграммы, выберите текстовое поле в той же области, где находится эта диаграмма, например, в тексте отчета или в прямоугольнике.</span><span class="sxs-lookup"><span data-stu-id="81353-120">To toggle visibility of a chart, select a text box that is in the same containing scope as the chart; for example, the report body or a rectangle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81353-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="81353-121">See Also</span></span>  
 <span data-ttu-id="81353-122">[Примеры выражений (построитель отчетов и службы SSRS)](report-design/expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="81353-122">[Expression Examples &#40;Report Builder and SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="81353-123">[Добавление действия "развернуть" или "Свернуть" к элементу &#40;построитель отчетов и службам SSRS&#41;](report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="81353-123">[Add an Expand or Collapse Action to an Item &#40;Report Builder and SSRS&#41;](report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="81353-124">[Образы &#40;построитель отчетов и службы SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="81353-124">[Images &#40;Report Builder and SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="81353-125">[Построитель отчетов справки по диалоговым окнам, панелям и мастерам](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="81353-125">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 [<span data-ttu-id="81353-126">Диалоговое окно "Свойства изображения" — "Общие" (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="81353-126">Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../../2014/reporting-services/image-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
