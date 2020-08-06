---
title: Связи атрибутов | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- member properties [Analysis Services], attribute relationships
- security [Analysis Services], properties
- PROPERTIES keyword
- storage [Analysis Services], attribute relationships
- natural hierarchies [Analysis Services]
- dimensions [Analysis Services], member properties
- queries [MDX], attribute relationships
- user-defined hierarchies [Analysis Services]
- attributes [Analysis Services], relationships
- member properties [Analysis Services]
- members [Analysis Services], attribute relationships
- storing data [Analysis Services], attribute relationships
- relationships [Analysis Services], attributes
ms.assetid: 2491422a-4cf5-4b23-b6ab-289222b22ce8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 122638a2728a8a85ee58661196797383da20eef8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733226"
---
# <a name="attribute-relationships"></a>можно изменить расположение фигур на вкладке
  В [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] атрибуты в пределах измерения всегда связаны напрямую или косвенно с ключевым атрибутом. Когда измерение определяется по схеме «звезда», где все атрибуты измерения наследуются из одной реляционной таблицы, то связи между ключевыми и не ключевыми атрибутами определяются автоматически. Когда измерение определяется по схеме «снежинка», где атрибуты измерения наследуются от разных реляционных таблиц, связи атрибутов автоматически определяются следующим образом:  
  
-   Между ключевым атрибутом и каждым не ключевым атрибутом, привязанным к столбцу главной таблицы измерения.  
  
-   Между ключевым атрибутом и атрибутами, привязанными к внешнему ключу вспомогательной таблицы, которая связывает таблицы базового измерения.  
  
-   Между атрибутом, привязанным к внешнему ключу вспомогательной таблицы, и каждым не ключевым атрибутом, привязанным к столбцам вспомогательной таблицы.  
  
 Однако по ряду причин может понадобиться изменить связи атрибутов, определенные по умолчанию, например чтобы определить естественную иерархию, пользовательский порядок сортировки или степень гранулярности измерения на основе неключевого атрибута. Дополнительные сведения см. в разделе [Справочник по свойствам атрибутов измерения](../multidimensional-models/dimension-attribute-properties-reference.md).  
  
> [!NOTE]  
>  Связи атрибутов называются в языке многомерных выражений свойствами элементов.  
  
## <a name="natural-hierarchy-relationships"></a>Связи естественной иерархии  
 Иерархия является естественной, когда каждый атрибут пользовательской иерархии имеет связь типа «один ко многим» с атрибутом, находящимся непосредственно под ним. Допустим, измерение Customer основано на реляционной исходной таблице, содержащей восемь столбцов:  
  
-   CustomerKey  
  
-   CustomerName  
  
-   возраст;  
  
-   пол;  
  
-   Email  
  
-   Город  
  
-   Country  
  
-   Регион  
  
 Соответствующее измерение служб Analysis Services содержит семь атрибутов:  
  
-   Customer (основанное на CustomerKey и CustomerName)  
  
-   Age, Gender, Email, City, Region, Country  
  
 Представляющие естественные иерархии связи создают, связывая атрибуты текущего и нижестоящего уровня. В службах [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] это свойство определяет естественную иерархию и возможное статистическое вычисление. В измерении Customer естественная иерархия применяется для атрибутов Country, Region, City и Customer. Естественная иерархия атрибутов `{Country, Region, City, Customer}` описывается добавлением следующих связей атрибутов:  
  
-   атрибут Country как связь атрибутов к атрибуту Region;  
  
-   атрибут Region как связь атрибутов к атрибуту City;  
  
-   атрибут City как связь атрибутов к атрибуту Customer.  
  
 Для перемещения по данным куба можно также создать пользовательскую иерархию, которая не представляет естественную иерархию в данных (которая называется *нерегламентированной* или иерархией *отчетов* ). Например, пользовательская иерархия может быть создана на основе `{Age, Gender}`. Пользователи не видят каких-либо различий в принципах работы двух иерархий, хотя естественная иерархия имеет преимущества от структуры статистической обработки и индексирования, скрытой от пользователя для естественных связей в исходных данных.  
  
 Свойство `SourceAttribute` уровня определяет, какой из атрибутов описывает уровень. Свойство `KeyColumns` атрибута определяет столбец в представлении источника данных, который является источником элементов. Свойство `NameColumn` атрибута может указывать на другой столбец имен для элементов.  
  
 Чтобы определить уровень в пользовательской иерархии с помощью [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] , **конструктор измерений** позволяет выбрать атрибут измерения, столбец в таблице измерения или столбец из связанной таблицы, входящей в представление источника данных для куба. Дополнительные сведения о создании пользовательских иерархий см. в разделе [Создание определяемых пользователем иерархий](../multidimensional-models/user-defined-hierarchies-create.md).  
  
 В службах Analysis Services о содержимом элементов измерения обычно делается предположение. Конечные элементы не имеют потомков и содержат данные, полученные непосредственно из основных источников данных. Неконечные элементы имеют потомков и содержат данные из статистических вычислений, рассчитанных по дочерним элементам. Значения на неконечных уровнях вычисляются на основе статистических вычислений над нижестоящими уровнями. Таким образом, когда свойству `IsAggregatable` исходного атрибута присваивается значение `False` для некоторого уровня, статистически вычисляемые атрибуты не должны добавляться на вышестоящие уровни.  
  
## <a name="defining-an-attribute-relationship"></a>Определения связи атрибутов  
 При создании атрибута главное проверить, чтобы атрибут, на который ссылается связь, имел не более одного значения для каждого элемента атрибута, к которому он принадлежит. Например, если определить связь между атрибутами City и State, каждый город будет принадлежать одному штату.  
  
## <a name="attribute-relationship-queries"></a>Запросы связи атрибутов  
 Чтобы получить данные о связи атрибутов в форме свойств элементов, можно использовать запросы многомерных выражений с ключевым словом `PROPERTIES` инструкции многомерных выражений `SELECT`. Дополнительные сведения об использовании многомерных выражений для получения свойств элементов см. в разделе [использование свойств элементов &#40;&#41;многомерных выражений ](../multidimensional-models/mdx/mdx-member-properties.md).  
  
## <a name="see-also"></a>См. также:  
 [Атрибуты и иерархии атрибутов](attributes-and-attribute-hierarchies.md)   
 [Справочник по свойствам атрибутов измерения](../multidimensional-models/dimension-attribute-properties-reference.md)   
 [Пользовательские иерархии](user-hierarchies.md)   
 [Свойства пользовательской иерархии](user-hierarchies-properties.md)  
  
  