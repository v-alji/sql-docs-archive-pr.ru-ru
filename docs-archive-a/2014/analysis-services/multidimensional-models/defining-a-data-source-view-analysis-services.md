---
title: Определение представления источника данных (Analysis Services) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- names [Analysis Services], data source views
- name matching criteria [Analysis Services]
- Data Source View Wizard
- data source views [Analysis Services], creating
ms.assetid: 0bae4ee4-1742-40e9-bebe-17c788854484
author: minewiskan
ms.author: owend
ms.openlocfilehash: 477504929c6e550dbdf17b6c27cd91ba030876ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668471"
---
# <a name="defining-a-data-source-view-analysis-services"></a>Определение представления источников данных (службы Analysis Services)
  Представление источника данных содержит логическую модель схемы, используемой [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] объектами многомерных баз данных, а именно Кубы, измерения и структуры интеллектуального анализа данных. Представление источника данных — это определение метаданных, хранящееся в формате XML, для элементов схемы, используемых в унифицированной многомерной модели (UDM) и структурах интеллектуального анализа данных. Представление источника данных:  
  
-   Содержит метаданные, представляющие выбранные объекты из одного или нескольких базовых источников данных, или метаданные, которые будут использоваться для формирования базового реляционного хранилища данных, если при формировании схемы используется нисходящий подход.  
  
-   Может быть построено на основе одного или нескольких источников данных, что позволяет определять многомерные объекты и объекты интеллектуального анализа данных, объединяющие данные из нескольких источников.  
  
-   может содержать связи, первичные ключи, имена объектов, вычисляемые столбцы и запросы, отсутствующие в базовом источнике данных и существующие отдельно от него;  
  
-   не видно, но доступно для запросов со стороны клиентских приложений.  
  
 Представление источника данных (DSV) является обязательным компонентом многомерной модели. Большинство разработчиков служб Analysis Services создают представление источника данных в ходе ранних этапов проектирования модели, формируя по меньшей мере одно представление источника данных на основе внешней реляционной базы данных, которая предоставляет основные данные. Однако представление источника данных можно создать на более позднем этапе, сформировав схему и базовые структуры базы данных после того, как будут созданы кубы и измерения. Такой подход иногда называют нисходящим и часто используют для создания прототипов и аналитического моделирования. В этом случае воспользуйтесь мастером создания схем для создания базового представления источников данных и объектов источника данных на основе объектов OLAP, определенных в проекте Analysis Services или базе данных. Независимо от метода создания DSV каждая модель должна содержать по крайней мере одно такое представление, иначе ее обработка будет невозможной.  
  
 Этот раздел включает следующие подразделы:  
  
 [Композиция представления источников данных](#bkmk_dsvdef)  
  
 [Создание представления источников данных с использованием мастера представлений источников данных](#bkmk_startWiz)  
  
 [Задание критериев совпадения имен для связей](#bkmk_NameMatch)  
  
 [Добавление вторичного источника данных](#bkmk_secondaryDS)  
  
##  <a name="data-source-view-composition"></a><a name="bkmk_dsvdef"></a> Создание представлений источников данных  
 Представление источника данных содержит следующие элементы.  
  
-   Имя и описание.  
  
-   Определение любого подмножества схемы, получаемого из одного или нескольких источников данных, вплоть до полной схемы и включая ее, в том числе:  
  
    -   имена таблиц;  
  
    -   имена столбцов;  
  
    -   типы данных;  
  
    -   допустимость значений NULL;  
  
    -   длины столбцов;  
  
    -   Первичные ключи.  
  
    -   связи «первичный-внешний ключ».  
  
-   Заметки к схеме из базовых источников данных, включая следующее:  
  
    -   понятные имена таблиц, представлений и столбцов;  
  
    -   именованные запросы, возвращающие столбцы из одного или нескольких источников данных (отображающихся в схеме как таблицы);  
  
    -   именованные вычисления, возвращающие столбцы из источника данных (отображающиеся как столбцы таблиц или представлений);  
  
    -   логические первичные ключи (необходимые, если первичный ключ в базовой таблице не определен или не включен в представление или именованный запрос);  
  
    -   связи «логический первичный ключ-внешний ключ» между таблицами, представлениями и именованными запросами.  
  
##  <a name="create-a-dsv-using-the-data-source-view-wizard"></a><a name="bkmk_startWiz"></a>Создание DSV с помощью мастера представлений источников данных  
 Для создания представления источника данных необходимо запустить мастер DSV в обозревателе решений [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].  
  
> [!NOTE]  
>  Также можно вначале создать измерения и кубы, а затем сформировать для модели представление источника данных c помощью мастера формирования схем. Дополнительные сведения см. в разделе [Мастер формирования схем (службы Analysis Services)](schema-generation-wizard-analysis-services.md).  
  
1.  В обозревателе решений правой кнопкой мыши щелкните папку "Представления источника данных", а затем выберите команду **Создать представление источника данных**.  
  
2.  Указывает новый или существующий объект источника данных, предоставляющий сведения о соединении с внешней реляционной базой данных (в мастере можно выбрать только один источник данных).  
  
3.  На этой же странице щелкните **Дополнительно** , чтобы выбрать конкретные схемы, применить фильтр или исключить сведения о связях между таблицами.  
  
     **Выбор схем**  
  
     Для очень больших источников данных, содержащих несколько схем, можно выбрать используемые схемы в список, разделяя схемы запятыми без пробелов.  
  
     **Получение связей**  
  
     Можно специально опустить сведения о связях между таблицами, сняв флажок **Получить связи** в диалоговом окне дополнительных параметров представления DSV, после чего можно вручную создать связи между таблицами в конструкторе представлений источников данных.  
  
4.  **Фильтрация доступных объектов**  
  
     Если список доступных объектов содержит слишком много объектов, то их число можно уменьшить путем применения простого фильтра со строкой в качестве критерия выбора. Например, если ввести **dbo** и нажать кнопку **Фильтр** , в списке **Доступные объекты** останутся только элементы, начинающиеся с «dbo». Фильтр может быть частичной строкой (например, "SAL" возвращает "продажи" и "оклад"), но не может включать несколько строк или операторов.  
  
5.  Для реляционных источников данных, которые не имеют определенных связей между таблицами, появится страница **Совпадение имен** , на которой можно выбрать подходящий метод согласования имен. Дополнительные сведения см. в подразделе [Задание критериев совпадения имен для связей](#bkmk_NameMatch) этой статьи.  
  
##  <a name="add-a-secondary-data-source"></a><a name="bkmk_secondaryDS"></a>Добавление вторичного источника данных  
 При определении представления источников данных, содержащего таблицы, представления или столбцы из нескольких источников данных, первый источник данных, из которого в представление источников данных добавляются объекты, служит в качестве первичного источника данных (нельзя изменить первичный источник данных после его создания). После определения представления источников данных, основанного на объектах из одного источника данных, можно добавлять в него объекты из других источников данных.  
  
 Если для обработки OLAP или запроса интеллектуального анализа данных в одном запросе необходимы данные из нескольких источников данных, первичный источник данных должен поддерживать удаленные запросы с помощью `OpenRowset`. Как правило, это будет источник данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Например, при конструировании измерения OLAP, содержащего атрибуты, привязанные к столбцам из нескольких источников данных, службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] создают запрос `OpenRowset` для заполнения этого измерения во время обработки. Однако, если объект OLAP может заполняться или запрос интеллектуального анализа данных разрешаться из одного источника данных, запрос `OpenRowset` не создается. В определенных ситуациях для устранения необходимости в запросе `OpenRowset` можно определять связи атрибутов. Дополнительные сведения о связях атрибутов см. в разделе [Связи атрибутов](../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md), [Добавление или удаление таблиц или представлений в представлении источника данных (службы Analysis Services)](adding-or-removing-tables-or-views-in-a-data-source-view-analysis-services.md) и [Определение связей атрибутов](attribute-relationships-define.md).  
  
 Для добавления таблиц и столбцов из второго источника данных необходимо дважды щелкнуть представление источника данных в обозревателе решений для открытия его в конструкторе представлений источников данных, а затем воспользоваться диалоговым окном «Добавление или удаление таблиц» для включения объектов из других источников данных, определенных в проекте. Дополнительные сведения см. в разделе [Добавление или удаление таблиц или представлений в представлении источника данных (службы Analysis Services)](adding-or-removing-tables-or-views-in-a-data-source-view-analysis-services.md).  
  
##  <a name="specify-name-matching-criteria-for-relationships"></a><a name="bkmk_NameMatch"></a>Укажите критерий соответствия имен для связей  
 При создании представления источников данных создаются связи между таблицами на основе ограничения внешнего ключа в источнике данных. Эти связи необходимы для механизма служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] для построения подходящих запросов оперативной аналитической обработки данных (OLAP) и запросов интеллектуального анализа данных. Однако иногда у источника данных с несколькими таблицами отсутствуют ограничения внешнего ключа. Если в источнике данных нет ограничения внешнего ключа, мастер представлений источника данных предложит указать, как следует проверять совпадение имен столбцов в различных таблицах.  
  
> [!NOTE]  
>  Появится запрос на предоставление критерия совпадения имен только если в базовом источнике данных отсутствуют связи внешнего ключа. При обнаружении связей внешних ключей они будут использоваться и необходимо вручную определить все дополнительные связи, которые необходимо включить в представление источника данных, включая логические первичные ключи. Дополнительные сведения см. в разделах [Определение логических связей в представлении источника данных (службы Analysis Services)](define-logical-relationships-in-a-data-source-view-analysis-services.md) и [Определение логических первичных ключей в представлении источника данных (службы Analysis Services)](define-logical-primary-keys-in-a-data-source-view-analysis-services.md).  
  
 Мастер представлений источника данных использует ответ пользователя, чтобы сопоставить имена столбцов и создать связи между различными таблицами в DSV. Можно задать любой критерий из перечисленных в следующей таблице.  
  
|Критерий совпадения имен|Описание|  
|----------------------------|-----------------|  
|**То же имя, что и у первичного ключа**|Имя внешнего ключевого столбца в исходной таблице совпадает с именем первичного ключевого столбца в целевой таблице. Например, внешний ключевой столбец `Order.CustomerID` тот же, что и первичный ключевой столбец `Customer.CustomerID`.|  
|**То же имя, что и у целевой таблицы**|Имя внешнего ключевого столбца в исходной таблице совпадает с именем целевой таблицы. Например, внешний ключевой столбец `Order.Customer` тот же, что и первичный ключевой столбец `Customer.CustomerID`.|  
|**Имя целевой таблицы + имя первичного ключа**|Имя внешнего ключевого столбца в исходной таблице совпадает с именем целевой таблицы, сцепленным с именем первичного ключевого столбца. В качестве разделителя допускается пробел или знак подчеркивания. Например, совпадают все следующие пары внешних и первичных ключей:<br /><br /> `Order.CustomerID` и `Customer.ID`<br /><br /> `Order.Customer ID` и `Customer.ID`<br /><br /> `Order.Customer_ID` и `Customer.ID`|  
  
 Выбранный критерий изменяет значение свойства **NameMatchingCriteria** в представлении источника данных. Этот параметр определяет, как мастер добавляет связанные таблицы. Когда представление источника данных изменяется с помощью конструктора представлений источников данных, этот параметр указывает, как конструктор проводит сопоставление столбцов, чтобы создать связи между таблицами в представлении источника данных. Можно изменять параметр свойства **NameMatchingCriteria** в конструкторе представлений источников данных. Дополнительные сведения см. в разделе [Изменение свойств в представлении источника данных (службы Analysis Services)](change-properties-in-a-data-source-view-analysis-services.md).  
  
> [!NOTE]  
>  После завершения работы мастера представлений источников данных можно добавить или удалить связи на панели схем конструктора представлений источников данных. Дополнительные сведения см. в разделе [Определение логических связей в представлении источника данных (службы Analysis Services)](define-logical-relationships-in-a-data-source-view-analysis-services.md).  
  
## <a name="see-also"></a>См. также:  
 [Добавление или удаление таблиц или представлений в представлении источника данных &#40;Analysis Services&#41;](adding-or-removing-tables-or-views-in-a-data-source-view-analysis-services.md)   
 [Определение логических первичных ключей в представлении источника данных &#40;Analysis Services&#41;](define-logical-primary-keys-in-a-data-source-view-analysis-services.md)   
 [Определение именованных вычислений в представлении источника данных &#40;Analysis Services&#41;](define-named-calculations-in-a-data-source-view-analysis-services.md)   
 [Определение именованных запросов в представлении источника данных &#40;Analysis Services&#41;](define-named-queries-in-a-data-source-view-analysis-services.md)   
 [Замените таблицу или именованный запрос в представлении источника данных &#40;Analysis Services&#41;](replace-a-table-or-a-named-query-in-a-data-source-view-analysis-services.md)   
 [Работа с диаграммами в конструкторе представлений источников данных &#40;Analysis Services&#41;](work-with-diagrams-in-data-source-view-designer-analysis-services.md)   
 [Просмотр данных в представлении источника данных &#40;Analysis Services&#41;](explore-data-in-a-data-source-view-analysis-services.md)   
 [Удаление представления источника данных &#40;Analysis Services&#41;](delete-a-data-source-view-analysis-services.md)   
 [Обновление схемы в представлении источника данных (службы Analysis Services)](refresh-the-schema-in-a-data-source-view-analysis-services.md)  
  
  