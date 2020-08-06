---
title: Анализ потока данных | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5654cb30-cad2-470c-97b3-59cb331033e5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 184b53d3e982cd80d7c9c0909538a751585ae21d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657242"
---
# <a name="analysis-of-data-flow"></a><span data-ttu-id="7ed2f-102">Анализ потока данных</span><span class="sxs-lookup"><span data-stu-id="7ed2f-102">Analysis of Data Flow</span></span>
  <span data-ttu-id="7ed2f-103">[catalog.execution_data_statistics](../relational-databases/statistics/statistics.md) `SSISDB` Для анализа потока данных пакетов можно использовать представление базы данныхcatalog.execution_data_statistics.</span><span class="sxs-lookup"><span data-stu-id="7ed2f-103">You can use the [catalog.execution_data_statistics](../relational-databases/statistics/statistics.md)`SSISDB` database view to analyze the data flow of packages.</span></span> <span data-ttu-id="7ed2f-104">Это представление отображает строку каждый раз, когда компонент потока данных передает данные в компонент, находящийся ниже в иерархии.</span><span class="sxs-lookup"><span data-stu-id="7ed2f-104">This view displays a row each time a data flow component sends data to a downstream component.</span></span> <span data-ttu-id="7ed2f-105">Подобная информация дает полное представление о строках, отправляемых для каждого компонента.</span><span class="sxs-lookup"><span data-stu-id="7ed2f-105">The information can be used to gain a deeper understanding of the rows that are sent to each component.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7ed2f-106">Чтобы получать необходимые сведения с помощью представления catalog.execution_data_statistics, уровнем ведения журнала должен быть **Подробно** .</span><span class="sxs-lookup"><span data-stu-id="7ed2f-106">The logging level must be set to **Verbose** in order to capture information with the catalog.execution_data_statistics view.</span></span>  
  
 <span data-ttu-id="7ed2f-107">В следующем примере отображается число строк, отправленных компонентами пакета.</span><span class="sxs-lookup"><span data-stu-id="7ed2f-107">The following example displays the number of rows sent between components of a package.</span></span>  
  
```  
use SSISDB  
select package_name, task_name, source_component_name, destination_component_name, rows_sent  
from catalog.execution_data_statistics  
where execution_id = 132  
order by source_component_name, destination_component_name  
  
```  
  
 <span data-ttu-id="7ed2f-108">В следующем примере подсчитывается количество строк, отправляемых в миллисекунду каждым компонентом при конкретном запуске пакета.</span><span class="sxs-lookup"><span data-stu-id="7ed2f-108">The following example calculates the number of rows per millisecond sent by each component for a specific execution.</span></span> <span data-ttu-id="7ed2f-109">Вычисляются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="7ed2f-109">The calculated values are:</span></span>  
  
-   <span data-ttu-id="7ed2f-110">**total_rows** — сумма всех строк, отправленных компонентом</span><span class="sxs-lookup"><span data-stu-id="7ed2f-110">**total_rows** - the sum of all the rows sent by the component</span></span>  
  
-   <span data-ttu-id="7ed2f-111">**wall_clock_time_ms** — общее время выполнения каждого компонента, в миллисекундах</span><span class="sxs-lookup"><span data-stu-id="7ed2f-111">**wall_clock_time_ms** - the total elapsed execution time, in milliseconds, for each component</span></span>  
  
-   <span data-ttu-id="7ed2f-112">**num_rows_per_millisecond** — количество строк, отправляемых каждым компонентом в миллисекунду</span><span class="sxs-lookup"><span data-stu-id="7ed2f-112">**num_rows_per_millisecond** - the number of rows per millisecond sent by each component</span></span>  
  
 <span data-ttu-id="7ed2f-113">`HAVING`Предложение используется для предотвращения ошибки деления на ноль в вычислениях.</span><span class="sxs-lookup"><span data-stu-id="7ed2f-113">The `HAVING` clause is used to prevent a divide-by-zero error in the calculations.</span></span>  
  
```  
use SSISDB  
select source_component_name, destination_component_name,  
    sum(rows_sent) as total_rows,  
    DATEDIFF(ms,min(created_time),max(created_time)) as wall_clock_time_ms,  
    ((0.0+sum(rows_sent)) / (datediff(ms,min(created_time),max(created_time)))) as [num_rows_per_millisecond]  
from [catalog].[execution_data_statistics]  
where execution_id = 132  
group by source_component_name, destination_component_name  
having (datediff(ms,min(created_time),max(created_time))) > 0  
order by source_component_name desc  
  
```  
  
## <a name="related-tasks"></a><span data-ttu-id="7ed2f-114">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="7ed2f-114">Related Tasks</span></span>  
 [<span data-ttu-id="7ed2f-115">Отладка потока данных</span><span class="sxs-lookup"><span data-stu-id="7ed2f-115">Debugging Data Flow</span></span>](troubleshooting/debugging-data-flow.md)  
  
 [<span data-ttu-id="7ed2f-116">Устранение неполадок инструментов с помощью отчетов</span><span class="sxs-lookup"><span data-stu-id="7ed2f-116">Troubleshooting Tools for Package Execution</span></span>](troubleshooting/troubleshooting-tools-for-package-execution.md)  
  
## <a name="see-also"></a><span data-ttu-id="7ed2f-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="7ed2f-117">See Also</span></span>  
 [<span data-ttu-id="7ed2f-118">Данные потоков данных</span><span class="sxs-lookup"><span data-stu-id="7ed2f-118">Data in Data Flows</span></span>](data-flow/data-in-data-flows.md)  
  
  
