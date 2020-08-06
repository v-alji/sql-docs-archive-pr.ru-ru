---
title: Синтаксис и примеры фильтра модели (Analysis Services — интеллектуальный анализ данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- model filter [data mining]
- filter syntax [data mining]
- filters [data mining]
- filters [Analysis Services]
ms.assetid: c729d9b3-8fda-405e-9497-52b2d7493eae
author: minewiskan
ms.author: owend
ms.openlocfilehash: f7ca200d179c0fe81b948793a4b4478f71502657
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728970"
---
# <a name="model-filter-syntax-and-examples-analysis-services---data-mining"></a>Синтаксис и примеры фильтра модели (службы Analysis Services — интеллектуальный анализ данных)
  В этом разделе приводятся сведения о синтаксисе фильтров моделей, а также образцы критериев.  
  
 
  
##  <a name="filter-syntax"></a><a name="bkmk_Syntax"></a> Filter Syntax  
 Критерии фильтра обычно эквивалентны содержимому предложения WHERE. Можно соединить несколько условий с помощью логических операторов `AND`, `OR` и `NOT`.  
  
 Во вложенных таблицах также можно использовать операторы `EXISTS` и `NOT EXISTS`. Условие `EXISTS` принимает значение `true`, если вложенный запрос возвращает, по крайней мере, одну строку. Это может быть удобно в тех случаях, когда необходимо ограничить модель вариантами, содержащими определенное значение во вложенной таблице, например покупатели, купившие товар по крайней мере один раз.  
  
 Условие `NOT EXISTS` принимает значение `true`, если условие, указанное во вложенном запросе, не существует. Например, можно создать для модели ограничение, касающееся клиентов, которые не покупали определенный товар.  
  
 Общий синтаксис выглядит следующим образом:  
  
```  
<filter>::=<predicate list>  | ( <predicate list> )  
<predicate list>::= <predicate> | [<logical_operator> <predicate list>]   
<logical_operator::= AND| OR  
<predicate>::= NOT <predicate>|( <predicate> ) <avPredicate> | <nestedTablePredicate> | ( <predicate> )   
<avPredicate>::= <columnName> <operator> <scalar> | <columnName> IS [NOT] NULL  
<operator>::= = | != | <> | > | >= | < | <=  
<nestedTablePredicate>::= EXISTS (<subquery>)  
<subquery>::=SELECT * FROM <columnName>[ WHERE  <predicate list> ]  
```  
  
 *Фильтрация*  
 Содержит один или несколько предикатов, соединенных логическими операторами.  
  
 *predicate list*  
 Один или несколько критериев фильтра, разделенных логическими операторами.  
  
 *columnName*  
 Имя столбца структуры интеллектуального анализа данных.  
  
 логический оператор  
 `AND`, `OR`, `NOT`  
  
 *avPredicate*  
 Критерий фильтра, применимый только к скалярному столбцу структуры интеллектуального анализа данных. Критерий *avPredicate* может быть использован и в фильтрах моделей, и в фильтрах вложенных таблиц.  
  
 Критерий, в котором используется любой из перечисленных ниже операторов, может быть применен только к непрерывному столбцу. :  
  
-   **\<**(меньше)  
  
-   **>**(больше)  
  
-   **>=**(больше или равно)  
  
-   **\<=**(меньше или равно)  
  
> [!NOTE]  
>  Вне зависимости от типа данных эти операторы не могут быть применены к столбцам, имеющим тип `Discrete`, `Discretized` или `Key`.  
  
 Выражение, в котором используется любой из перечисленных ниже операторов, может быть применен к непрерывному, дискретному, дискретизированному или ключевому столбцу.  
  
-   **=** прошлом  
  
-   **! =** (не равно)  
  
-   **ИМЕЕТ ЗНАЧЕНИЕ NULL**  
  
 Если критерий *avPredicate*применяется к дискретизированному столбцу, то в фильтре может использоваться любое значение из конкретного сегмента.  
  
 Иными словами, условие не определяется как `AgeDisc = '25-35'`. Вместо этого вычисляется, а затем используется значение из этого интервала.  
  
 Пример:  `AgeDisc = 27`  означает любое значение в том же интервале, что и 27. В данном случае этот интервал 25–35.  
  
 *nestedTablePredicate*  
 Критерий фильтра, применяющийся к вложенной таблице. Может использоваться только в фильтрах модели.  
  
 Аргумент вложенного запроса критерия для аргумента *nestedTablePredicate*может применяться только к столбцу структуры интеллектуального анализа данных  
  
 вложенный запрос  
 Инструкция SELECT, за которой следует допустимый предикат или список предикатов.  
  
 Все предикаты должны иметь тип, описанный в *avPredicates*. Кроме того, предикаты должны ссылаться только на столбцы, включенные в текущую вложенную таблицу, определяемую аргументом *columnName*.  
  
### <a name="limitations-on-filter-syntax"></a>Ограничения синтаксиса фильтра  
 На фильтры налагаются следующие ограничения.  
  
-   Фильтр может содержать только простые предикаты. Они включают математические операторы, скалярные переменные и имена столбцов.  
  
-   В синтаксисе фильтров не допускаются определяемые пользователем функции.  
  
-   Операторы, не являющиеся логическими, например знаки плюса и минуса, не поддерживаются в синтаксисе фильтров.  
  
## <a name="examples-of-filters"></a>Примеры фильтров  
 В следующих примерах демонстрируется применение фильтров к модели интеллектуального анализа данных. Если критерий фильтра создается в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], в окне **Свойство** , на панели **Выражение** диалогового окна "Фильтр", то будет видна только строка, которая появляется за ключевыми словами WITH FILTER. Определение структуры интеллектуального анализа данных было включено, чтобы легче понять типы столбцов и методы их использования.  
  
###  <a name="example-1-typical-case-level-filtering"></a><a name="bkmk_Ex1"></a> Пример 1. Обычная фильтрация на уровне вариантов  
 В этом примере показан простой фильтр, который ограничивает варианты, используемые в модели, пользователями, имеющими профессию архитектора и возраст старше 30 лет.  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_1  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT  
)  
WITH FILTER (Age > 30 AND Occupation='Architect')  
```  
  

  
###  <a name="example-2-case-level-filtering-using-nested-table-attributes"></a><a name="bkmk_Ex2"></a> Пример 2. Фильтрация на уровне вариантов с использованием атрибутов вложенной таблицы  
 Если в структуре интеллектуального анализа данных содержатся вложенные таблицы, осуществлять фильтрацию можно по существованию значения во всей таблице либо по конкретным строкам вложенной таблицы, в которых содержится конкретное значение. В этом примере для модели ограничиваются только покупатели старше 30 лет, которые совершили по крайней мере одну покупку, включающую молоко.  
  
 В этом примере показано, что в фильтре могут использоваться столбцы, которых нет в модели. Вложенная таблица **Products** является частью структуры интеллектуального анализа данных, но не включена в модель интеллектуального анализа данных. Несмотря на это, фильтры могут применяться к значениям и атрибутам этой вложенной таблицы. Чтобы просматривать сведения о таких вариантах, необходимо включить детализацию.  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_2  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT  
)  
WITH DRILLTHROUGH,   
FILTER (Age > 30 AND EXISTS (SELECT * FROM Products WHERE ProductName='Milk')  
)  
```  
  
 
  
###  <a name="example-3-case-level-filtering-on-multiple-nested-table-attributes"></a><a name="bkmk_Ex3"></a> Пример 3. Фильтрация на уровне вариантов по нескольким атрибутам вложенной таблицы  
 В этом примере показан фильтр, состоящий из трех частей: условия, применяемого к таблице вариантов, второго условия, касающегося атрибута вложенной таблицы, и третьего условия, касающегося определенного значения в одном из столбцов вложенной таблицы.  
  
 Первое условие фильтра, `Age > 30`, применяется к столбцу в таблице вариантов. Остальные условия применяются к вложенной таблице.  
  
 Второе условие, `EXISTS (SELECT * FROM Products WHERE ProductName='Milk'`, проверяет наличие во вложенной таблице по крайней мере одной покупки, включающей молоко. Третье условие, `Quantity>=2`, обозначает, что заказчик должен был купить по крайней мере две упаковки молока за одну транзакцию.  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_3  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT,  
Products PREDICT  
(  
ProductName KEY,  
Quantity        
)  
)  
FILTER (Age > 30 AND EXISTS (SELECT * FROM Products WHERE ProductName='Milk'  AND Quantity >= 2)   
)  
```  
  

  
###  <a name="example-4-case-level-filtering-on-absence-of-nested-table-attributes"></a><a name="bkmk_Ex4"></a> Пример 4. Фильтрация на уровне вариантов по отсутствию атрибутов вложенной таблицы  
 В этом примере показано, как можно ограничить выбор вариантов покупателями, которые не приобретали определенный товар, с помощью фильтрации по атрибута во вложенной таблице. В этом примере модель обучается на данных о клиентах старше 30 лет, которые никогда не покупали молоко.  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_4  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT,  
Products PREDICT  
(  
ProductName  
)  
)  
FILTER (Age > 30 AND NOT EXISTS (SELECT * FROM Products WHERE ProductName='Milk') )  
```  
  

  
###  <a name="example-5-filtering-on-multiple-nested-table-values"></a><a name="bkmk_Ex5"></a> Пример 5. Фильтрация по нескольким значениям вложенной таблицы  
 Целью этого примера является демонстрация фильтрации во вложенной таблице. Фильтр вложенной таблицы применяется после фильтра вариантов и ограничивает только строки вложенной таблицы.  
  
 В этой модели может содержаться несколько вариантов с пустыми вложенными таблицами, поскольку инструкция EXISTS не была указана.  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_5  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT,  
Products PREDICT  
(  
ProductName KEY,  
Quantity        
) WITH FILTER(ProductName='Milk' OR ProductName='bottled water')  
)  
WITH DRILLTHROUGH  
```  
  

  
###  <a name="example-6-filtering-on-nested-table-attributes-and-exists"></a><a name="bkmk_Ex6"></a> Пример 6. Фильтрация по атрибутам вложенной таблицы с инструкцией EXISTS  
 В этом примере фильтр для вложенной таблицы ограничивает строки, в которых содержится либо молоко, либо бутилированная вода. Затем происходит фильтрация вариантов в модели с помощью инструкции `EXISTS`. Это гарантирует, что вложенная таблица не будет пустой.  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_6  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT,  
Products PREDICT  
(  
ProductName KEY,  
Quantity        
) WITH FILTER(ProductName='Milk' OR ProductName='bottled water')  
)  
FILTER (EXISTS (Products))  
```  
  

  
###  <a name="example-7-complex-filter-combinations"></a><a name="bkmk_Ex7"></a> Пример 7. Сложные сочетания фильтров  
 Сценарий для этой модели напоминает сценарий из примера 4, но здесь он более сложный. Вложенная таблица **ProductsOnSale**имеет условие фильтра `(OnSale)` , означающее, что значение **onsale** должно быть `true` для продукта, указанного в поле **ProductName**. Здесь **OnSale** — это столбец структуры.  
  
 Вторая часть фильтра для **ProductsNotOnSale**повторяет этот синтаксис, но фильтрует по продуктам, для которых значение **onsale** равно `not true``(!OnSale)` .  
  
 Затем эти условия объединяются, а на таблицу вариантов накладывается одно дополнительное ограничение. В результате прогнозируются покупки продуктов в списке **ProductsNotOnSale** на основе вариантов, включенных в список **ProductsOnSale** , для покупателей старше 25 лет.  
  
 `ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_7`  
  
 `(`  
  
 `CustomerId,`  
  
 `Age,`  
  
 `Occupation,`  
  
 `MaritalStatus,`  
  
 `ProductsOnSale`  
  
 `(`  
  
 `ProductName KEY`  
  
 `) WITH FILTER(OnSale),`  
  
 `ProductsNotOnSale PREDICT ONLY`  
  
 `(`  
  
 `ProductName KEY`  
  
 `) WITH FILTER(!OnSale)`  
  
 `)`  
  
 `WITH DRILLTHROUGH,`  
  
 `FILTER (EXISTS (ProductsOnSale) AND EXISTS(ProductsNotOnSale) AND Age > 25)`  
  
  
  
###  <a name="example-8-filtering-on-dates"></a><a name="bkmk_Ex8"></a> Пример 8. Фильтрация по датам  
 Входные столбцы можно фильтровать по датам, так же как и по любым другим данным. Даты, содержащиеся в столбце типа «дата/время», являются непрерывными значениями, поэтому можно указать диапазон дат, используя операторы, такие как «больше» (>) и «меньше» (<). Если источник данных представляет даты не как непрерывный тип данных, а как дискретные или текстовые значения, то выполнять фильтрацию по диапазону дат нельзя, необходимо указывать отдельные дискретные значения.  
  
 Однако нельзя задать фильтр по столбцу дат в модели временных рядов в том случае, если столбец дат, используемый для фильтрации, также является ключевым столбцом для модели. Это связано с тем, что в моделях временных рядов и в моделях кластеризации последовательностей столбец дат может обрабатываться как тип `KeyTime` или тип `KeySequence`.  
  
 Если необходимо выполнить фильтрацию по непрерывно расположенным датам в модели временных рядов, то можно создать копию столбца в структуре интеллектуального анализа данных и выполнить фильтрацию в модели по этому новому столбцу.  
  
 Например, следующее выражение представляет фильтр для столбца дат типа `Continuous`, добавленного в модель прогнозирования.  
  
 `=[DateCopy] > '12:31:2003:00:00:00'`  
  
> [!NOTE]  
>  Следует заметить, что любые дополнительные столбцы, добавленные в модель, могут повлиять на результат. В связи с этим, если этот столбец не должен быть использован при вычислении рядов, его следует добавить только в структуру интеллектуального анализа данных, но не в модель. Также для столбца можно установить флаг модели `PredictOnly` или `Ignore`. Дополнительные сведения см. в разделе [Флаги моделирования (интеллектуальный анализ данных)](modeling-flags-data-mining.md).  
  
 Для других типов моделей даты можно использовать в качестве входных критериев или условий критерия, как и в любых других столбцах. Однако, если необходимо использовать определенный уровень гранулярности, который не поддерживается типом данных `Continuous`, можно создать производное значение в источнике данных, использовав выражения для извлечения единицы, которая будет использоваться при фильтрации и анализе.  
  
> [!WARNING]  
>  Если в качестве условия фильтра вы указываете даты, следует использовать формат `mm/dd/yyyy`, независимо от формата даты для используемой операционной системы. Любой другой формат приведет к ошибке.  
  
 Например, если необходимо фильтровать результаты центра обработки вызовов, чтобы отображались только данные за выходные, то можно создать выражение в представлении источника данных, извлекающее название дня недели для каждой даты, а затем использовать название дня в качестве входных данных или как дискретное значение при фильтрации. Однако следует помнить, что повторяющиеся значения также могут повлиять на модель, поэтому следует использовать только один из столбцов и не использовать совместно столбец дат и производное значение.  
  
 
  
## <a name="see-also"></a>См. также:  
 [Фильтры для моделей интеллектуального анализа данных &#40;Analysis Services интеллектуального анализа&#41;](mining-models-analysis-services-data-mining.md)   
 [Тестирование и проверка (интеллектуальный анализ данных)](testing-and-validation-data-mining.md)  
  
  