---
title: Связи (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 21e0144a-3cfd-4bc7-87ff-bb7d1800ed2f
author: minewiskan
ms.author: owend
ms.openlocfilehash: eac90102e4595bf19cbeb7eefc22e975ecf53610
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738822"
---
# <a name="relationships-ssas-tabular"></a>Связи (табличные службы SSAS)
  В табличных моделях связь — это соединение между двумя таблицами данных. Связь определяет, как должны соотноситься данные в двух таблицах. Например, таблица «Customers» и таблица «Orders» могут быть связаны, чтобы отображалось имя клиента, соответствующее каждому заказу.  
  
 При использовании мастера импорта таблиц для импорта из одного и того же источника данных связи, существующие в таблицах (в источнике данных), которые выбраны для импорта, будут повторно созданы в модели. Можно просмотреть связи, которые были автоматически обнаружены и созданы повторно, с помощью конструктора моделей в представлении диаграммы либо с помощью диалогового окна «Управление связями». Можно также вручную создавать новые связи между таблицами при помощи конструктора моделей в представлении диаграмм или при помощи диалоговых окон «Создание связи» или «Управление связями».  
  
 После определения связи между заданными таблицами (автоматически, во время импорта или вручную) можно будет выполнять фильтрацию данных с помощью связанных столбцов и выполнять поиск значений в связанных таблицах.  
  
> [!TIP]  
>  Если модель содержит много связей, представление диаграммы лучше поможет визуально представить и создавать связи между таблицами.  
  
 Разделы данной темы:  
  
-   [Преимущества](#what)  
  
-   [Требования к связям](#requirements)  
  
-   [Вывод связей](#detection)  
  
-   [Обнаружение связей при импорте данных](#bkmk_detection)  
  
-   [Создание связей вручную](#bkmk_manually_create)  
  
-   [Дублирующиеся значения и другие ошибки](#bkmk_dupl_errors)  
  
-   [Связанные задачи](#bkmk_related_tasks)  
  
##  <a name="benefits"></a><a name="what"></a> Преимущества  
 Связь представляет собой соединение двух таблиц данных на основании одного или нескольких столбцов в каждой таблице. Чтобы понять, чем полезны связи, представим, что отслеживаются данные для заказов клиентов в бизнесе. Можно отслеживать все данные в одной таблице, имеющей структуру, подобную следующей.  
  
|CustomerID|Имя|EMail|DiscountRate|OrderID|OrderDate|Продукт|Количество|  
|----------------|----------|-----------|------------------|-------------|---------------|-------------|--------------|  
|1|Эштон|chris.ashton@contoso.com|0,05|256|2010-01-07|Компактный цифровой|11|  
|1|Эштон|chris.ashton@contoso.com|0,05|255|2010-01-03|Однообъективный зеркальный фотоаппарат|15|  
|2|Яворски|michal.jaworski@contoso.com|0,10|254|2010-01-03|Недорогая видеокамера|27|  
  
 Этот подход может быть эффективным, но он подразумевает хранение множества избыточных данных, таких как адрес электронной почты клиента для каждого заказа. Хранение не требует больших затрат, но нужно быть уверенным в том, что при изменении адреса электронной почты будет обновлена каждая строка для этого клиента. Одним из решений этой проблемы является разбиение данных на множество таблиц и определение связей между этими таблицами. Именно этот подход используется в *реляционных базах данных* наподобие [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Например, база данных, которая импортируется в модель, может представлять данные заказов, используя три связанные таблицы.  
  
### <a name="customers"></a>Клиенты  
  
|[CustomerID]|Имя|Email|  
|--------------------|----------|-----------|  
|1|Эштон|chris.ashton@contoso.com|  
|2|Яворски|michal.jaworski@contoso.com|  
  
### <a name="customerdiscounts"></a>CustomerDiscounts  
  
|[CustomerID]|DiscountRate|  
|--------------------|------------------|  
|1|0,05|  
|2|0,10|  
  
### <a name="orders"></a>Orders  
  
|[CustomerID]|OrderID|OrderDate|Продукт|Количество|  
|--------------------|-------------|---------------|-------------|--------------|  
|1|256|2010-01-07|Компактный цифровой|11|  
|1|255|2010-01-03|Однообъективный зеркальный фотоаппарат|15|  
|2|254|2010-01-03|Недорогая видеокамера|27|  
  
 При импорте этих таблиц из одной и той же базы данных мастер импорта таблиц может обнаружить связи между таблицами, основанные на столбцах, заключенных в [квадратные скобки], и воспроизвести эти связи в конструкторе моделей. Дополнительные сведения см. в подразделе [Автоматическое обнаружение и вывод связей](#detection) этого раздела. Если таблицы импортируются из нескольких источников, то связи можно создавать вручную, как описано в разделе [Создание связи между двумя таблицами (табличные службы SSAS)](create-a-relationship-between-two-tables-ssas-tabular.md).  
  
### <a name="columns-and-keys"></a>Столбцы и ключи  
 Связи основаны на столбцах в каждой таблице, содержащих одинаковые данные. Например, таблицы Customers и Orders могут быть связаны друг с другом, поскольку обе содержат столбец, в котором хранится идентификатор клиента. В данном примере имена столбцов одинаковы, но это не является обязательным условием. Один столбец может называться CustomerID, а другой — CustomerNumber, при условии, что все строки в таблице Orders содержат идентификатор, который также хранится в таблице Customers.  
  
 В реляционной базе данных имеется несколько типов *ключей*, которые обычно представлены столбцами со специальными свойствами. Следующие четыре типа ключей могут использоваться в реляционных базах данных:  
  
-   *Первичный ключ*: однозначно определяет строку в таблице, например CustomerID в таблице Customers.  
  
-   *Альтернативный ключ* (или *потенциальный ключ*): уникальный столбец, который не является первичным ключом. Например, таблица Employees может хранить идентификатор работника и номер карточки социального страхования, при том что оба они являются уникальными.  
  
-   *Внешний ключ*: столбец, который ссылается на уникальный столбец в другой таблице, например CustomerID в таблице Orders, который ссылается на CustomerID в таблице Customers.  
  
-   *Составной ключ*— это ключ, состоящий из нескольких столбцов. Составные ключи в табличных моделях не поддерживаются. Дополнительные сведения см. в подразделе «Составные ключи и столбцы подстановки» в этом разделе.  
  
 В табличных моделях первичный ключ или резервный ключ называется *связанным столбцом подстановки*или просто *столбцом подстановки*. Если таблица имеет и первичный и резервный ключ, в качестве столбца подстановки можно использовать любой из них. Внешний ключ называется *исходным столбцом* или просто *столбцом*. В нашем примере связь была бы определена между CustomerID в таблице Orders (столбец) и CustomerID (столбец подстановки) в таблице Customers. Если данные импортируются из реляционной базы данных, по умолчанию конструктор моделей выбирает внешний ключ из одной таблицы и соответствующий первичный ключ из другой таблицы. Однако в качестве столбца подстановки можно использовать любой столбец, имеющий уникальные значения.  
  
### <a name="types-of-relationships"></a>Типы связей  
 Связь между таблицами Customers и Orders является связью *один ко многим*. Каждый клиент может иметь несколько заказов, но заказ не может иметь несколько клиентов. Другими типами связей являются связи *один к одному* и *многие ко многим*. Таблица CustomerDiscounts, которая определяет по одному льготному тарифу для каждого клиента, находится в связи «один к одному» с таблицей Customers. Примером связи "многие ко многим" является прямая связь между таблицами Products и Customers, когда один клиент может купить много продуктов и один продукт может быть куплен несколькими клиентами. Конструктор моделей не поддерживает связи "многие ко многим" в пользовательском интерфейсе. Дополнительные сведения можно узнать в разделе "[Связи «многие ко многим»](#bkmk_many_to_many)" этой темы.  
  
 В следующей таблице представлены связи между тремя таблицами.  
  
|Связь|Type|столбцом подстановки|Столбец|  
|------------------|----------|-------------------|------------|  
|Customers — CustomerDiscounts|один к одному|Customers.CustomerID|CustomerDiscounts.CustomerID|  
|Customers — Orders|один ко многим|Customers.CustomerID|Orders.CustomerID|  
  
### <a name="relationships-and-performance"></a>Связи и производительность  
 После создания любой связи конструктор моделей, как правило, должен повторно вычислить формулы, использующие столбцы из таблиц, участвующих в созданной связи. Обработка может занять некоторое время, в зависимости от объема данных и сложности связей.  
  
##  <a name="requirements-for-relationships"></a><a name="requirements"></a>Требования к связям  
 Конструктор моделей предъявляет несколько требований, которые должны учитываться при создании связей.  
  
### <a name="single-active-relationship-between-tables"></a>Одиночная активная связь между таблицами  
 Наличие нескольких связей может привести к неоднозначной зависимости между таблицами. Для создания точных вычислений необходимо, чтобы от одной таблицы к другой вел единственный путь. Поэтому между каждой парой таблиц может существовать только одна активная связь. Например, в базе данных AdventureWorks DW 2012 содержится таблица DimDate со столбцом DateKey, который связан с тремя различными столбцами из таблицы FactInternetSales: OrderDate, DueDate и ShipDate. Если импортировать эти таблицы без изменений, то первая связь будет создана успешно, однако для последующих связей с участием того же столбца будет получено следующее сообщение об ошибке.  
  
 \*Связь: таблица [столбец 1]-> таблица [столбец 2]-состояние: Ошибка-Причина: невозможно создать связь между таблицами \<table 1> и \<table 2> . Между двумя таблицами может существовать только одна прямая или косвенная связь.  
  
 Если имеются две таблицы, между которыми существует несколько связей, то необходимо импортировать несколько копий таблицы, содержащей столбец подстановки, и создать между каждой парой таблиц одну связь.  
  
 Между таблицами может быть много неактивных связей. Путь для использования между таблицами указывается клиентским средством создания отчетов во время запроса.  
  
### <a name="one-relationship-for-each-source-column"></a>Наличие одной связи для каждого исходного столбца  
 Исходный столбец не может участвовать в нескольких связях. Если вы уже использовали столбец в качестве исходного столбца в одной связи, но его необходимо связать с другим столбцом подстановки в другой таблице, можно создать копию столбца и использовать ее в новой связи.  
  
 Создание копии столбца, имеющего те же значения, упрощается посредством применения формулы DAX в вычисляемом столбце. Дополнительные сведения см. в разделе [Вычисляемые столбцы (табличные службы SSAS)](ssas-calculated-columns-create-a-calculated-column.md).  
  
### <a name="unique-identifier-for-each-table"></a>Применение уникального идентификатора для каждой таблицы  
 Каждая таблица должна иметь один столбец, который однозначно идентифицирует каждую строку в этой таблице. Такой столбец часто именуется первичным ключом.  
  
### <a name="unique-lookup-columns"></a>Уникальные столбцы подстановки  
 Значения данных в столбце подстановки должны быть уникальными. Иными словами, столбец не может содержать повторяющиеся значения. В табличных моделях значения NULL и пустые строки считаются эквивалентными пустому значению, которое является отдельным значением данных. Это значит, что столбец подстановки не может содержать несколько значений NULL.  
  
### <a name="compatible-data-types"></a>Совместимые типы данных  
 Типы данных в исходном столбце и в столбце подстановки должны быть совместимыми. Дополнительные сведения о типах данных см. в разделе [Поддерживаемые типы данных (табличные службы SSAS)](data-types-supported-ssas-tabular.md).  
  
### <a name="composite-keys-and-lookup-columns"></a>Составные ключи и столбцы подстановки  
 Составные ключи нельзя использовать в табличной модели. Необходимо иметь только один столбец, однозначно определяющий каждую строку в таблице. Если импортировать таблицы, для которых существует связь по составному ключу, мастер импорта таблиц будет игнорировать такую связь, поскольку ее нельзя создать в табличной модели.  
  
 Если нужно создать связь между двумя таблицами в конструкторе моделей, а первичный и внешний ключи определяются несколькими столбцами, то перед созданием связи необходимо объединить значения, чтобы создать один ключевой столбец. Это можно сделать перед импортом данных или осуществить в конструкторе моделей, создав вычисляемый столбец.  
  
###  <a name="many-to-many-relationships"></a><a name="bkmk_many_to_many"></a>Связи «многие ко многим»  
 Табличные модели не поддерживают связи "многие ко многим", что не позволяет добавлять *соединяющие таблицы* в конструктор моделей. Тем не менее можно использовать функции DAX для моделирования связи «многие ко многим».  
  
### <a name="self-joins-and-loops"></a>Самосоединения и циклы  
 В таблицах табличной модели не допускаются самосоединения. Самосоединение — это рекурсивная связь таблицы с самой собой. Самосоединения часто используются для определения иерархий типа «родители-потомки». Например, можно соединить таблицу Employees с самой собой, чтобы сформировать иерархию, которая показывает цепочку подчиненности на предприятии.  
  
 Конструктор моделей не позволяет создавать циклы между связями в модели. Иными словами, следующий набор связей запрещается.  
  
 От таблицы 1, столбец a   к   таблице 2, столбец f  
  
 От таблицы 2, столбец f   к   таблице 3, столбец n  
  
 От таблицы 3, столбец n   к   таблице 1, столбец a  
  
 При попытке создания такой связи, которая приведет к образованию цикла, выдается ошибка.  
  
##  <a name="inference-of-relationships"></a><a name="detection"></a>Вывод связей  
 В некоторых случаях связи между таблицами автоматически объединяются в цепочки. Например, если создать связь между первыми двумя наборами таблиц, указанных ниже, то определяется наличие связи между другими двумя таблицами и эта связь устанавливается автоматически.  
  
 Products и Category — связь создается вручную  
  
 Category и SubCategory — связь создается вручную  
  
 Products и SubCategory — связь определяется автоматически  
  
 Для автоматического объединения связей в цепочки эти связи должны идти в одном направлении, как показано выше. Если исходные связи были установлены, например между таблицами Sales и Products, а также между Sales и Customers, то связь не выводится. Это вызвано тем, что связь между таблицами Products и Customer является связью «многие ко многим».  
  
##  <a name="detection-of-relationships-when-importing-data"></a><a name="bkmk_detection"></a>Обнаружение связей при импорте данных  
 При импорте из таблицы реляционного источника данных, мастер импорта таблиц обнаруживает существующие связи в этих исходных таблицах на основе данных схемы источника. При импорте связанных таблиц их связи будут продублированы в модели.  
  
##  <a name="manually-create-relationships"></a><a name="bkmk_manually_create"></a>Создание связей вручную  
 Хотя большинство связей между таблицами в едином реляционном источнике данных обнаруживаются автоматически и создаются в табличной модели, во многих случаях необходимо создать связи между таблицами модели вручную.  
  
 Если модель содержит данные из нескольких источников, то, вероятно, придется создавать связи вручную. Например, можно импортировать таблицы Customers, CustomerDiscounts и Orders из реляционного источника данных. Связи, существующие между этими таблицами в источнике, будут автоматически созданы в модели. Затем можно добавить другую таблицу из другого источника, например региональные данные из таблицы Geography в книге Microsoft Excel. Затем можно вручную создать связь между столбцом таблицы Customers и столбцом таблицы Geography.  
  
 Чтобы вручную создавать новые связи в табличной модели, можно воспользоваться конструктором моделей в представлении диаграмм либо диалоговым окном «Управление связями». В представлении диаграммы графически отображаются таблицы и связи между ними. Связь можно легко создать, щелкнув столбец в одной таблице и перетащив курсор в другую таблицу. Между таблицами будет создана связь в правильном порядке. Связи между таблицами отображаются в диалоговом окне «Управление связями» в простом табличном формате. Дополнительные сведения о том, как создавать связи вручную, см. в разделе [Создание связи между двумя таблицами (табличные службы SSAS)](create-a-relationship-between-two-tables-ssas-tabular.md).  
  
##  <a name="duplicate-values-and-other-errors"></a><a name="bkmk_dupl_errors"></a>Дублирующиеся значения и другие ошибки  
 Если выбрать столбец, который нельзя использовать в связи, рядом с ним появится красный значок X. Если навести курсор мыши на значок ошибки, можно просмотреть сообщение с подробными сведениями о проблеме. Следующие проблемы могут сделать невозможным создание связи между выбранными столбцами.  
  
|Проблема или сообщение|Решение|  
|------------------------|----------------|  
|Связь не удается создать, поскольку оба выбранных столбца содержат повторяющиеся значения.|Для создания допустимой связи необходимо, чтобы хотя бы один столбец в паре содержал только уникальные значения.<br /><br /> Можно изменить столбцы, чтобы удалить повторяющиеся значения, или изменить порядок столбцов на обратный, чтобы столбец, содержащий уникальные значения, использовался как **Связанный столбец уточняющих запросов**.|  
|Столбец содержит пустое значение или значение NULL.|Столбцы данных не могут соединяться по значению NULL. Для каждой строки должно быть значение в обоих столбцах, используемых в связи.|  
  
##  <a name="related-tasks"></a><a name="bkmk_related_tasks"></a> Связанные задачи  
  
|Раздел|Описание|  
|-----------|-----------------|  
|[Создание связи между двумя таблицами (табличные службы SSAS)](create-a-relationship-between-two-tables-ssas-tabular.md)|Содержит описание того, как вручную создать связь между двумя таблицами.|  
|[Удаление связей (табличные службы SSAS)](relationships-ssas-tabular.md)|Содержит описание того, как удалить связь, а также последствий удаления отношений.|  
  
## <a name="see-also"></a>См. также:  
 [Таблицы и столбцы &#40;табличные&#41;SSAS](tables-and-columns-ssas-tabular.md)   
 [Импорт данных (табличные службы SSAS)](../import-data-ssas-tabular.md)  
  
  