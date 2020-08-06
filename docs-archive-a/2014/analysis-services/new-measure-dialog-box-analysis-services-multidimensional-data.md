---
title: Диалоговое окно «Создание меры» (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.newmeasuredialog.f1
helpviewer_keywords:
- New Measure dialog box
ms.assetid: 86dc9146-cc6d-4cef-b178-9a6b4cf616e8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1fb60bd598257d2de1f60900aafa43b085000fd8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752431"
---
# <a name="new-measure-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="8f8f1-102">Диалоговое окно «Создание меры» (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="8f8f1-102">New Measure Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="8f8f1-103">Используйте диалоговое окно **Создание меры** в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] для добавления новой меры в группу мер конструктора кубов.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-103">Use the **New Measure** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to add a new measure to a measure group in Cube Designer.</span></span> <span data-ttu-id="8f8f1-104">Чтобы отобразить диалоговое окно **Создание меры** , можно:</span><span class="sxs-lookup"><span data-stu-id="8f8f1-104">You can display the **New Measure** dialog box by:</span></span>  
  
-   <span data-ttu-id="8f8f1-105">Щелкнуть **Создать меру** на панели **Панель инструментов** вкладки **Структура куба** в конструкторе кубов.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-105">Clicking **New Measure** in the **Toolbar** pane on the **Cube Structure** tab in Cube Designer.</span></span>  
  
-   <span data-ttu-id="8f8f1-106">Щелкнуть правой кнопкой мыши группу мер или меру на панели **Меры** вкладки **Структура куба** конструктора кубов и выбрать **Создать меру** из контекстного меню.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-106">Right-clicking a measure group or measure in the **Measures** pane on the **Cube Structure** tab in Cube Designer and selecting **New Measure** from the context menu.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8f8f1-107">Варианты</span><span class="sxs-lookup"><span data-stu-id="8f8f1-107">Options</span></span>  
 <span data-ttu-id="8f8f1-108">**Использование**</span><span class="sxs-lookup"><span data-stu-id="8f8f1-108">**Usage**</span></span>  
 <span data-ttu-id="8f8f1-109">Позволяет выбрать статистическую функцию, используемую новым мерам.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-109">Select the aggregation function to be used by the new measure.</span></span>  
  
 <span data-ttu-id="8f8f1-110">**Исходная таблица**</span><span class="sxs-lookup"><span data-stu-id="8f8f1-110">**Source table**</span></span>  
 <span data-ttu-id="8f8f1-111">Позволяет выбрать таблицу, на основе которой будет создана новая мера.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-111">Select the table from which the new measure is to be created.</span></span>  
  
 <span data-ttu-id="8f8f1-112">**Исходный столбец**</span><span class="sxs-lookup"><span data-stu-id="8f8f1-112">**Source column**</span></span>  
 <span data-ttu-id="8f8f1-113">Позволяет выбрать столбец таблицы, выбранной с помощью параметра **Исходная таблица** , на основе которого будет создана новая мера.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-113">Select the column in the table selected in **Source table** on which the new measure is to be based.</span></span>  
  
 <span data-ttu-id="8f8f1-114">**Показать все столбцы**</span><span class="sxs-lookup"><span data-stu-id="8f8f1-114">**Show all columns**</span></span>  
 <span data-ttu-id="8f8f1-115">Позволяет отобразить все столбцы таблицы фактов для группы мер, в которой будет создана новая мера.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-115">Select to display all columns in the fact table for the measure group in which the new measure is to be created.</span></span> <span data-ttu-id="8f8f1-116">Если этот параметр не выбран, в поле **Исходный столбец** отображаются только числовые столбцы, не используемые в качестве логических первичных ключей и не включенные в связи.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-116">If not selected, **Source column** only displays numeric columns that are not used as logical primary keys or involved in relationships.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f8f1-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="8f8f1-117">See Also</span></span>  
 <span data-ttu-id="8f8f1-118">[Структура куба &#40;конструктор кубов&#41; &#40;Analysis Services многомерных данных&#41;](cube-structure-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="8f8f1-118">[Cube Structure &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](cube-structure-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="8f8f1-119">Analysis Services конструкторов и диалоговых окон &#40;многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="8f8f1-119">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
