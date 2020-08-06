---
title: Диалоговое окно «Поиск таблицы» (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.findtabledialog.f1
helpviewer_keywords:
- Find Table dialog box
ms.assetid: 133d28e8-55eb-4783-bb8b-d3776a95ebda
author: minewiskan
ms.author: owend
ms.openlocfilehash: ee22c912a3121841a7827e31d53f7b8baba72174
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656698"
---
# <a name="find-table-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="172c1-102">Диалоговое окно «Поиск таблицы» (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="172c1-102">Find Table Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="172c1-103">Используйте диалоговое окно **Поиск таблицы** в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] для поиска таблицы в представлении источников данных, связанном с измерением, кубом или структурой интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="172c1-103">Use the **Find Table** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to locate a table in the data source view associated with a dimension, cube, or mining structure.</span></span> <span data-ttu-id="172c1-104">Чтобы открыть это диалоговое окно в среде [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] , выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="172c1-104">You can display this dialog box in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] by:</span></span>  
  
-   <span data-ttu-id="172c1-105">Нажмите кнопку **Найти таблицу** на **Панели инструментов** на странице **Структура измерения** в **Конструкторе измерений**.</span><span class="sxs-lookup"><span data-stu-id="172c1-105">Clicking **Find Table** from the **Toolbar** pane on the **Dimension Structure** page of the **Dimension Designer**.</span></span>  
  
-   <span data-ttu-id="172c1-106">Щелкните правой кнопкой мыши фон панели **Представление источника данных** на странице **Структура измерения** в **конструкторе измерений** и выберите в контекстном меню пункт **Найти таблицу**.</span><span class="sxs-lookup"><span data-stu-id="172c1-106">Right-clicking the background of the **Data Source View** pane on the **Dimension Structure** page of the **Dimension Designer** and selecting **Find Table**.</span></span>  
  
-   <span data-ttu-id="172c1-107">Нажмите кнопку **Найти таблицу** на **Панели инструментов** на странице **Структура куба** в **Конструкторе кубов**.</span><span class="sxs-lookup"><span data-stu-id="172c1-107">Clicking **Find Table** from the **Toolbar** pane on the **Cube Structure** page of the **Cube Designer**.</span></span>  
  
-   <span data-ttu-id="172c1-108">Щелкните правой кнопкой мыши фон панели **Представление источника данных** на странице **Структура куба** в **конструкторе кубов** и выберите в контекстном меню пункт **Найти таблицу**.</span><span class="sxs-lookup"><span data-stu-id="172c1-108">Right-clicking the background of the **Data Source View** pane on the **Cube Structure** page of the **Cube Designer** and selecting **Find Table**.</span></span>  
  
-   <span data-ttu-id="172c1-109">Щелкните правой кнопкой мыши фон панели **Представление источника данных** на странице **Структура интеллектуального анализа данных** в **конструкторе моделей интеллектуального анализа данных** и выберите в контекстном меню пункт **Найти таблицу**.</span><span class="sxs-lookup"><span data-stu-id="172c1-109">Right-clicking the background of the **Data Source View** pane on the **Mining Structure** page of the **Data Mining Model Designer** and selecting **Find Table**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="172c1-110">Варианты</span><span class="sxs-lookup"><span data-stu-id="172c1-110">Options</span></span>  
 <span data-ttu-id="172c1-111">**Выберите таблицу из представления источников данных:**</span><span class="sxs-lookup"><span data-stu-id="172c1-111">**Select a table from data source view**</span></span>  
 <span data-ttu-id="172c1-112">Выберите таблицу для поиска на панели **Представление источника данных** .</span><span class="sxs-lookup"><span data-stu-id="172c1-112">Select the table to find in the **Data Source View** pane.</span></span> <span data-ttu-id="172c1-113">Данный параметр отображает сетку доступных объектов и их типы, совпадающие с фильтром, заданным на странице **Фильтр** (или все таблицы, если **Фильтр** не установлен), которые пока не отображаются в данной диаграмме.</span><span class="sxs-lookup"><span data-stu-id="172c1-113">This option displays a grid of available objects and their types that match the filter set in **Filter** (or all tables if **Filter** is not set) and have not yet been shown in the current diagram.</span></span>  
  
 <span data-ttu-id="172c1-114">**Filter**</span><span class="sxs-lookup"><span data-stu-id="172c1-114">**Filter**</span></span>  
 <span data-ttu-id="172c1-115">Введите фильтр, ограничивающий число объектов в данном списке, затем нажмите эту кнопку для фильтрации таблиц из списка **Выберите таблицу из представления источника данных**.</span><span class="sxs-lookup"><span data-stu-id="172c1-115">Type the filter used to restrict the objects listed, and then click the button to filter the tables listed in **Select a table from data source view**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="172c1-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="172c1-116">See Also</span></span>  
 <span data-ttu-id="172c1-117">[Диалоговое окно "Свойства сборки" &#40;Analysis Services многомерных данных&#41;](assembly-properties-dialog-box-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="172c1-117">[Assembly Properties Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](assembly-properties-dialog-box-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="172c1-118">[Представление источника данных &#40;вкладка «Структура измерения», конструктор измерений&#41; &#40;Analysis Services многомерных данных&#41;](datasource-view-dimension-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="172c1-118">[Data Source View &#40;Dimension Structure Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](datasource-view-dimension-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="172c1-119">Представление источника данных &#40;вкладка «Структура куба», конструктор кубов&#41; &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="172c1-119">Data Source View &#40;Cube Structure Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](data-source-view-cube-designer-analysis-services-multidimensional-data.md)  
  
  
