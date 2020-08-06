---
title: Диалоговое окно «Отображение таблицы» (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.cubebuilder.showtabledialog.f1
helpviewer_keywords:
- Show Table dialog box
ms.assetid: 4c0bf4fa-5685-4269-bf7d-f0e9802ab4bf
author: minewiskan
ms.author: owend
ms.openlocfilehash: 15d90ccc5773663baf9c780a920d80e4adc38927
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736863"
---
# <a name="show-table-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="34aaf-102">Диалоговое окно «Отображение таблицы» (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="34aaf-102">Show Table Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="34aaf-103">Используйте диалоговое окно **Показать таблицу** в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] для добавления таблиц из представления источников данных, связанных с измерением, кубом или структурой интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="34aaf-103">Use the **Show Table** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to include tables from the data source view associated with a dimension, cube, or mining structure.</span></span> <span data-ttu-id="34aaf-104">Чтобы открыть это диалоговое окно в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="34aaf-104">You can display this dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] by:</span></span>  
  
-   <span data-ttu-id="34aaf-105">Нажмите кнопку **Показать таблицы** на **панели инструментов** страницы **Структура измерений** в **конструкторе измерений**.</span><span class="sxs-lookup"><span data-stu-id="34aaf-105">Clicking **Show Tables** from the **Toolbar** pane on the **Dimension Structure** page of **Dimension Designer**.</span></span>  
  
-   <span data-ttu-id="34aaf-106">Щелкните правой кнопкой мыши фон панели **Представление источника данных** на странице **Структура измерения** в **конструкторе измерений** и выберите в контекстном меню пункт **Показать таблицы**.</span><span class="sxs-lookup"><span data-stu-id="34aaf-106">Right-clicking the background of the **Data Source View** pane on the **Dimension Structure** page of **Dimension Designer** and selecting **Show Tables**.</span></span>  
  
-   <span data-ttu-id="34aaf-107">Нажмите кнопку **Показать таблицы** на **панели инструментов** страницы **Структура куба** в **конструкторе кубов**.</span><span class="sxs-lookup"><span data-stu-id="34aaf-107">Clicking **Show Tables** from the **Toolbar** pane on the **Cube Structure** page of **Cube Designer**.</span></span>  
  
-   <span data-ttu-id="34aaf-108">Щелкните правой кнопкой мыши фон панели **Представление источника данных** на странице **Структура куба** в **конструкторе кубов** и выберите в контекстном меню пункт **Показать таблицы**.</span><span class="sxs-lookup"><span data-stu-id="34aaf-108">Right-clicking the background of the **Data Source View** pane on the **Cube Structure** page of **Cube Designer** and selecting **Show Tables**.</span></span>  
  
-   <span data-ttu-id="34aaf-109">Щелкните правой кнопкой мыши фон панели **Представление источника данных** на странице **Структура интеллектуального анализа данных** в **конструкторе моделей интеллектуального анализа данных** и выберите в контекстном меню пункт **Показать таблицы**.</span><span class="sxs-lookup"><span data-stu-id="34aaf-109">Right-clicking the background of the **Data Source View** pane on the **Mining Structure** page of **Data Mining Model Designer** and selecting **Show Tables**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="34aaf-110">Варианты</span><span class="sxs-lookup"><span data-stu-id="34aaf-110">Options</span></span>  
 <span data-ttu-id="34aaf-111">**Выбор дополнительных таблиц для просмотра**</span><span class="sxs-lookup"><span data-stu-id="34aaf-111">**Select additional tables to be shown**</span></span>  
 <span data-ttu-id="34aaf-112">Выберите таблицы для добавления на панель **Представление источника данных** .</span><span class="sxs-lookup"><span data-stu-id="34aaf-112">Select the tables to add to the **Data Source View** pane.</span></span> <span data-ttu-id="34aaf-113">Данный параметр отображает сетку доступных объектов и их типы, совпадающие с фильтром, заданным на странице **Фильтр** (или все таблицы, если **Фильтр** не установлен), которые пока не отображаются в данной диаграмме.</span><span class="sxs-lookup"><span data-stu-id="34aaf-113">This option displays a grid of available objects and their types that match the filter set in **Filter** (or all tables if **Filter** is not set) and have not yet been shown in the current diagram.</span></span>  
  
 <span data-ttu-id="34aaf-114">**Filter**</span><span class="sxs-lookup"><span data-stu-id="34aaf-114">**Filter**</span></span>  
 <span data-ttu-id="34aaf-115">Задайте фильтр ограничения для объектов в списке, затем нажмите кнопку, чтобы отфильтровать таблицы в списке **Выбор дополнительных таблиц для просмотра**.</span><span class="sxs-lookup"><span data-stu-id="34aaf-115">Type the filter used to restrict the objects listed, and then click the button to filter the tables listed in **Select additional tables to be shown**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34aaf-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="34aaf-116">See Also</span></span>  
 <span data-ttu-id="34aaf-117">[Analysis Services конструкторов и диалоговых окон &#40;многомерных данных&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="34aaf-117">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 <span data-ttu-id="34aaf-118">[Представление источника данных &#40;вкладка «Структура измерения», конструктор измерений&#41; &#40;Analysis Services многомерных данных&#41;](datasource-view-dimension-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="34aaf-118">[Data Source View &#40;Dimension Structure Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](datasource-view-dimension-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="34aaf-119">Представление источника данных &#40;вкладка «Структура куба», конструктор кубов&#41; &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="34aaf-119">Data Source View &#40;Cube Structure Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](data-source-view-cube-designer-analysis-services-multidimensional-data.md)  
  
  
