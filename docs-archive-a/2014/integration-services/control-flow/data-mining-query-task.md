---
title: Задача "Запрос интеллектуального анализа данных" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataminingquerytask.f1
helpviewer_keywords:
- prediction queries [Integration Services]
- Data Mining Query task [Integration Services]
ms.assetid: f489348c-2008-4f66-8c2c-c07c3029439a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6bb3cea630401f92395e2ca4416c03bcd870c881
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665074"
---
# <a name="data-mining-query-task"></a>Задача «Запрос интеллектуального анализа данных»
  Задача «Запрос интеллектуального анализа данных» запускает прогнозирующие запросы, основанных на моделях интеллектуального анализа данных, встроенных в службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]. Прогнозирующий запрос создает прогноз для новых данных с использованием моделей интеллектуального анализа данных. Например, прогнозирующий запрос может предсказать, сколько яхт может быть продано в летние месяцы, или сформировать список предполагаемых клиентов, которые могут купить яхту.  
  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] предоставляют задачи, выполняющие другие операции бизнес-аналитики, например выполнение инструкций языка DDL и обработки аналитических объектов.  
  
 Дополнительные сведения о задачах бизнес-аналитики см. в следующих разделах:  
  
-   [Задача «Выполнение инструкции DDL служб Analysis Services»](analysis-services-execute-ddl-task.md)  
  
-   [Задача «Обработка средствами Analysis Services»](analysis-services-processing-task.md)  
  
## <a name="prediction-queries"></a>Прогнозирующие запросы  
 Такой запрос является инструкцией расширения интеллектуального анализа данных. Язык расширения интеллектуального анализа данных — это расширение языка SQL для поддержки работы с моделями интеллектуального анализа данных. Дополнительные сведения об использовании языка расширений интеллектуального анализа данных см. в разделе [Справочник по расширениям интеллектуального анализа данных](/sql/dmx/data-mining-extensions-dmx-reference).  
  
 Задача может запрашивать несколько моделей интеллектуального анализа данных, построенных в одной структуре интеллектуального анализа данных. Модель интеллектуального анализа данных строится при помощи одного из алгоритмов интеллектуального анализа данных, предоставляемых службами [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] . Структура интеллектуального анализа данных, к которой обращается задача «Запрос интеллектуального анализа данных», может включать в себя несколько моделей интеллектуального анализа данных, построенных на основе разных алгоритмов. Дополнительные сведения см. в разделах [Структуры интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)](https://docs.microsoft.com/analysis-services/data-mining/mining-structures-analysis-services-data-mining) и [Алгоритмы интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)](https://docs.microsoft.com/analysis-services/data-mining/data-mining-algorithms-analysis-services-data-mining).  
  
 Прогнозирующий запрос, запускаемый задачей «Запрос интеллектуального анализа данных», возвращает результат в виде одной строки или набора данных. Запрос, возвращающий одну строку, называется одноэлементным запросом: например, запрос, предсказывающий, сколько лодок будет продано в летние месяцы, возвращает одно число. Дополнительные сведения о прогнозирующих запросах, возвращающих одну строку, см. в разделе [интерфейсы запросов интеллектуального анализа данных](https://docs.microsoft.com/analysis-services/data-mining/data-mining-query-tools).  
  
 Результаты запроса сохраняются в таблицах. Если таблица с именем, указанным в задаче «Запрос интеллектуального анализа данных», уже существует, задача может создать новую таблицу с тем же именем, к которому прибавлен номер, или перезаписать содержимое таблицы.  
  
 Если результаты содержат вложенность, то перед сохранением результат выравнивается. Выравнивание результата преобразует вложенный результирующий набор в таблицу. Например, выравнивание вложенного результата со столбцом **Customer** и вложенным столбцом **Product** добавляет строки в столбец **Customer** , формируя таблицу, содержащую данные о продуктах для каждого клиента. Например, покупатель трех различных продуктов становится таблицей из трех строк, в которой клиент повторяется во всех трех строках, а продукты в каждой строке различаются. Если ключевое слово FLATTENED опущено, то эта таблица будет содержать только столбец **Customer** с одной строкой на каждого клиента. Дополнительные сведения см. в разделе [SELECT (расширения интеллектуального анализа данных)](/sql/dmx/select-dmx).  
  
## <a name="configuration-of-the-data-mining-query-task"></a>Настройка задачи «Запрос интеллектуального анализа данных»  
 Задача «Запрос интеллектуального анализа данных» требует два соединения. Первое соединение — это соединение диспетчера соединений служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] с экземпляром служб [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] или с проектом служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], который содержит структуру и модель интеллектуального анализа данных. Второе — это соединение диспетчера соединений OLE DB с базой данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , содержащей таблицу, в которую данная задача производит запись. Дополнительные сведения см. в разделах [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md) и [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).  
  
 Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../../includes/ssis-md.md)] или программными средствами.  
  
 Дополнительные сведения о свойствах, которые можно задать в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , см. в следующих разделах:  
  
-   [Редактор задачи "Запрос интеллектуального анализа данных" (вкладка "Модель интеллектуального анализа данных")](../data-mining-query-task-editor-mining-model-tab.md)  
  
-   [Редактор задачи "Запрос интеллектуального анализа данных" (вкладка "Запрос")](../data-mining-query-task-editor-query-tab.md)  
  
-   [Редактор задачи "Запрос интеллектуального анализа данных" (вкладка "Вывод")](../data-mining-query-task-editor-output-tab.md)  
  
> [!NOTE]  
>  В редакторе запроса интеллектуального анализа данных нет страницы «Выражения». Вместо этого нужно использовать окно **Свойства** для доступа к средствам создания и управления выражениями свойств задачи «Запрос интеллектуального анализа данных».  
  
 Дополнительные сведения об установке этих свойств в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] см. в следующем разделе:  
  
-   [Задание свойств задач или контейнеров](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="programmatic-configuration-of-data-mining-query-task"></a>Настройка задачи «Запрос интеллектуального анализа данных» программными средствами  
 Дополнительные сведения о программной настройке этих свойств см. в следующих разделах:  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.DMQueryTask.DMQueryTask>  
  
  