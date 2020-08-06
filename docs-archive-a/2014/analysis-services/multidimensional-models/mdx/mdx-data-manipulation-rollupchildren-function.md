---
title: Работа с функцией RollupChildren (многомерные выражения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- queries [MDX], RollupChildren function
- RollupChildren function
- custom member properties [MDX]
- IIf function
ms.assetid: 03c624d4-f277-451d-9995-623a07ea2f86
author: minewiskan
ms.author: owend
ms.openlocfilehash: 341468d521cebe1fda33d73ea999f3b6571cb01e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737037"
---
# <a name="working-with-the-rollupchildren-function-mdx"></a>Работа с функцией RollupChildren (многомерные выражения)
  Функция МНОГОМЕРных выражений [RollupChildren](/sql/mdx/rollupchildren-mdx) [скрипт для поиска и замена] выполняет сведение дочерних элементов элемента, применяя другой унарный оператор к каждому дочернему элементу, и возвращает значение этой свертки в виде числа. Унарный оператор может браться из свойства, связанного с элементом-потомком, или же оператор может быть строковым выражением, непосредственно заданным для этой функции.  
  
## <a name="rollupchildren-function-examples"></a>Примеры функции RollupChildren  
 Применение функции `RollupChildren` в инструкциях многомерных выражений объяснить просто, однако действие этой функции на запросы многомерных выражений может быть разнообразным.  
  
 Воздействие функции `RollupChildren` осуществляется в запросах многомерных выражений, предназначенных для выполнения выборочного анализа существующих данных куба. Например, в следующей таблице перечисляются элементы-потомки для элемента-родителя «Чистая выручка от продаж», а в скобках показаны их унарные операторы (представленные свойством элементов `UNARY_OPERATOR`).  
  
|Родительский элемент|Дочерний элемент|  
|-------------------|------------------|  
|Чистая выручка от продаж|Внутренние продажи (+)<br /><br /> Внутренние возвраты (-)<br /><br /> Зарубежные продажи (+)<br /><br /> Зарубежные возвраты (-)|  
  
 Родительский элемент «Чистая выручка от продаж» в данный момент предоставляет сумму чистых продаж минус валовые внутренние и внешние продажи, причем вычитание внутренних и внешних возвратов производится как часть выполнения этой свертки.  
  
 Однако предположим, что надо быстро получить оценку прироста на 10 % внутренних и внешних валовых продаж без учета внутренних и внешних возвратов. Для вычисления этого значения можно воспользоваться функцией `RollupChildren`, одним из двух методов: с помощью пользовательского свойства элемента или функции `IIf`.  
  
### <a name="using-a-custom-member-property"></a>Применение пользовательского свойства элемента  
 Если вычисление свертки надо производить часто, то можно создать свойство элемента, хранящее оператор, который в специальной функции будет применяться к каждому дочернему элементу. В следующей таблице показаны допустимые унарные операторы и ожидаемые результаты.  
  
|Оператор|Результат|  
|--------------|------------|  
|+|сумма = сумма + текущий дочерний элемент|  
|-|сумма = сумма - текущий дочерний элемент|  
|*|сумма = сумма * текущий дочерний элемент|  
|/|сумма = сумма / текущий дочерний элемент|  
|~|Дочерний элемент не используется в свертке. Значение дочернего элемента игнорируется.|  
  
 Например, можно было бы создать свойство элемента с именем `SALES_OPERATOR`, и этому свойству элемента присваивались бы следующие унарные операторы — см. таблицу ниже.  
  
|Родительский элемент|Дочерний элемент|  
|-------------------|------------------|  
|Чистая выручка от продаж|Внутренние продажи (+)<br /><br /> Внутренние возвраты (~)<br /><br /> Зарубежные продажи (+)<br /><br /> Зарубежные возвраты (~)|  
  
 С помощью нового свойства элемента следующая инструкция многомерных выражений быстро и эффективно выполнит операцию прогнозирования валовых продаж (без учета внешних и внутренних возвратов):  
  
```  
RollupChildren([Net Sales], [Net Sales].CurrentMember.Properties("SALES_OPERATOR")) * 1.1  
```  
  
 При вызове этой функции в сумму войдет значение каждого дочернего элемента, к которому будет применен оператор, хранящийся в данном свойстве элемента. Элементы для внутренних и внешних возвратов не учитываются, а полное значение свертки вычисляется по функции `RollupChildren`, умноженной на коэффициент 1,1.  
  
### <a name="using-the-iif-function"></a>Применение функции IIf  
 Если пример операции не является распространенным или если операция применяется только к одному запросу многомерных выражений, функцию [IIf](/sql/mdx/iif-mdx) можно использовать с `RollupChildren` функцией для предоставления того же результата. Следующий запрос многомерных выражений дает тот же результат, что и описанный выше запрос многомерных выражений, но данный запрос выполняется без обращения к пользовательскому свойству элемента:  
  
```  
RollupChildren([Net Sales], IIf([Net Sales].CurrentMember.Properties("UNARY_OPERATOR") = "-", "~", [Net Sales].CurrentMember.Properties("UNARY_OPERATOR))) * 1.1  
```  
  
 Инструкция многомерных выражений анализирует унарный оператор дочернего элемента. Если унарный оператор применяется для вычитания (как в случае элементов с внутренними и внешними возвратами), то функция `IIf` заменяет унарный оператор тильду (~). В противном случае функция `IIf` использует унарный оператор дочернего элемента. Наконец вычисленное значение суммы свертки умножается на коэффициент 1,1 для получения значения прогнозируемых валовых внутренних и внешних продаж.  
  
## <a name="see-also"></a>См. также:  
 [Манипулирование данными (многомерные выражения)](mdx-data-manipulation-manipulating-data.md)  
  
  