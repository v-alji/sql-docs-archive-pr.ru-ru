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
# <a name="analysis-of-data-flow"></a>Анализ потока данных
  [catalog.execution_data_statistics](../relational-databases/statistics/statistics.md) `SSISDB` Для анализа потока данных пакетов можно использовать представление базы данныхcatalog.execution_data_statistics. Это представление отображает строку каждый раз, когда компонент потока данных передает данные в компонент, находящийся ниже в иерархии. Подобная информация дает полное представление о строках, отправляемых для каждого компонента.  
  
> [!NOTE]  
>  Чтобы получать необходимые сведения с помощью представления catalog.execution_data_statistics, уровнем ведения журнала должен быть **Подробно** .  
  
 В следующем примере отображается число строк, отправленных компонентами пакета.  
  
```  
use SSISDB  
select package_name, task_name, source_component_name, destination_component_name, rows_sent  
from catalog.execution_data_statistics  
where execution_id = 132  
order by source_component_name, destination_component_name  
  
```  
  
 В следующем примере подсчитывается количество строк, отправляемых в миллисекунду каждым компонентом при конкретном запуске пакета. Вычисляются следующие значения:  
  
-   **total_rows** — сумма всех строк, отправленных компонентом  
  
-   **wall_clock_time_ms** — общее время выполнения каждого компонента, в миллисекундах  
  
-   **num_rows_per_millisecond** — количество строк, отправляемых каждым компонентом в миллисекунду  
  
 `HAVING`Предложение используется для предотвращения ошибки деления на ноль в вычислениях.  
  
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
  
## <a name="related-tasks"></a>Связанные задачи  
 [Отладка потока данных](troubleshooting/debugging-data-flow.md)  
  
 [Устранение неполадок инструментов с помощью отчетов](troubleshooting/troubleshooting-tools-for-package-execution.md)  
  
## <a name="see-also"></a>См. также:  
 [Данные потоков данных](data-flow/data-in-data-flows.md)  
  
  
