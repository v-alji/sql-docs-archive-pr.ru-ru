---
title: Диалоговое окно «Источник секции» (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitionsourcedialog.f1
ms.assetid: c414dabe-9bad-49b7-9a3c-dfca87fef92b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6732e8f00dc0d01e0d3b708794a1d9c497ae4cf5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727386"
---
# <a name="partition-source-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="28f76-102">Диалоговое окно «Источник секции» (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="28f76-102">Partition Source Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="28f76-103">Используйте диалоговое окно **Источник секции** в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] для задания источника данных таблицы фактов секции.</span><span class="sxs-lookup"><span data-stu-id="28f76-103">Use the **Partition Source** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to specify the source of fact table data for a partition.</span></span> <span data-ttu-id="28f76-104">Открыть диалоговое окно **Источник секции** можно несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="28f76-104">You can display the **Partition Source** dialog box by:</span></span>  
  
-   <span data-ttu-id="28f76-105">Нажав на кнопку **...** в ячейке сетки **Секции** выделенной группы мер на панели **Группы мер** вкладки **Секции** конструктора кубов.</span><span class="sxs-lookup"><span data-stu-id="28f76-105">Clicking the **...** button on a cell from the **Partitions** grid of a selected measure group in the **Measure Groups** pane on the **Partitions** tab in Cube Designer.</span></span>  
  
-   <span data-ttu-id="28f76-106">Нажав на кнопку **...** значения свойства **Источник** объекта **Секция** в окне **Свойства** в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28f76-106">Clicking the **...** button on the **Source** property value of a **Partition** object in the **Properties** window in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="28f76-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="28f76-107">Options</span></span>  
  
|<span data-ttu-id="28f76-108">Параметр</span><span class="sxs-lookup"><span data-stu-id="28f76-108">Option</span></span>|<span data-ttu-id="28f76-109">Определение</span><span class="sxs-lookup"><span data-stu-id="28f76-109">Definition</span></span>|  
|------------|----------------|  
|<span data-ttu-id="28f76-110">**Тип привязки**</span><span class="sxs-lookup"><span data-stu-id="28f76-110">**Binding type**</span></span>|<span data-ttu-id="28f76-111">Выберите тип привязки, который будет применен к источнику указанной секции.</span><span class="sxs-lookup"><span data-stu-id="28f76-111">Select the binding type to use for the source of the specified partition.</span></span> <span data-ttu-id="28f76-112">Доступны следующие варианты:</span><span class="sxs-lookup"><span data-stu-id="28f76-112">The following options are available:</span></span><br /><br /> <span data-ttu-id="28f76-113">**Привязка таблицы**: выберите, чтобы отобразить панель **сведений о привязке таблицы** и указать, что секция привязана к содержимому таблицы в источнике данных или представлении источника данных.</span><span class="sxs-lookup"><span data-stu-id="28f76-113">**Table binding**: Select to display the **Table Binding Detail** pane and indicate that the partition is bound to the contents of a table in a data source or data source view.</span></span> <span data-ttu-id="28f76-114">Дополнительные сведения о панели **Сведения о привязке таблицы** см. в разделе [Сведения о привязке таблицы (диалоговое окно "Источник секции") (службы Analysis Services — многомерные данные)](table-binding-partition-source-dialog-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="28f76-114">For more information about the **Table Binding Detail** pane, see [Table Binding Detail &#40;Partition Source Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;](table-binding-partition-source-dialog-analysis-services-multidimensional-data.md).</span></span><br /><br /> <span data-ttu-id="28f76-115">**Сведения**: выберите, чтобы отобразить панель **сведений о привязке запроса** и указать, что секция привязана к содержимому запроса, выполняемого в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="28f76-115">**Detail**: Select to display the **Query Binding Detail** pane and indicate that the partition is bound to the contents of a query executed on a data source.</span></span> <span data-ttu-id="28f76-116">Дополнительные сведения о панели **Сведения о привязке запроса** см. в разделе [Сведения о привязке запроса (диалоговое окно "Источник секции") (службы Analysis Services — многомерные данные)](query-binding-partition-source-dialog-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="28f76-116">For more information about the **Query Binding Detail** pane, see [Query Binding Detail &#40;Partition Source Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;](query-binding-partition-source-dialog-analysis-services-multidimensional-data.md).</span></span>|  
|<span data-ttu-id="28f76-117">**Подробный сведения**</span><span class="sxs-lookup"><span data-stu-id="28f76-117">**Detail**</span></span>|<span data-ttu-id="28f76-118">Отображает диалоговое окно **Сведения о привязке таблицы** или диалоговое окно **Сведения о привязке запроса** , в зависимости от значения параметра **Тип привязки** .</span><span class="sxs-lookup"><span data-stu-id="28f76-118">Displays either the **Table Binding Detail** dialog box or the **Query Binding Detail** dialog box, depending on the value of the **Binding type** option.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="28f76-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="28f76-119">See Also</span></span>  
 <span data-ttu-id="28f76-120">[Секции &#40;конструктор кубов&#41; &#40;Analysis Services многомерных данных&#41;](partitions-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="28f76-120">[Partitions &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](partitions-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="28f76-121">Analysis Services конструкторов и диалоговых окон &#40;многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="28f76-121">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
