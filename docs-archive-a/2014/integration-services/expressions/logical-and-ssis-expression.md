---
title: '&amp;&amp; (логическое И) (выражение служб SSIS) | Документы Майкрософт'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- '&& (logical AND)'
- AND, logical AND
- logical AND (&&)
ms.assetid: a8cb3517-d5d1-4861-9f04-905c719185ff
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8d973d7d4e86f88f7ae88c820ed4e4a5c1ce526f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729669"
---
# <a name="ampamp-logical-and-ssis-expression"></a>&amp;&amp; (логическое И) (выражение служб SSIS)
  Выполняет логическую операцию И. Выражение принимает значение TRUE, если все условия имеют значение TRUE.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
boolean_expression1 && boolean_expression2  
```  
  
## <a name="arguments"></a>Аргументы  
 *boolean_expression1, boolean_expression2*  
 Любое допустимое выражение, результатом которого являются TRUE, FALSE или NULL  
  
## <a name="result-types"></a>Типы результата  
 DT_BOOL  
  
## <a name="remarks"></a>Remarks  
 Следующая таблица демонстрирует результаты выполнения оператора &&.  
  
|Результат|Выражение|Выражение|  
|------------|----------------|----------------|  
|TRUE|TRUE|TRUE|  
|FALSE|TRUE|FALSE|  
|FALSE|FALSE|FALSE|  
|NULL|NULL|NULL|  
|NULL|NULL|TRUE|  
|FALSE|NULL|FALSE|  
  
## <a name="expression-examples"></a>Примеры выражений  
 В этом примере используются столбцы **StandardCost** и **ListPrice** . Пример возвращает значение TRUE, если значение столбца **StandardCost** меньше 300 или значение столбца **ListPrice** больше 500.  
  
```  
StandardCost < 300 && ListPrice > 500  
```  
  
 Этот пример использует переменные **SPrice** и **LPrice** вместо числовых литералов.  
  
```  
StandardCost < @SPrice && ListPrice > @LPrice  
```  
  
## <a name="see-also"></a>См. также:  
 [& (битовое И) (выражение служб SSIS)](bitwise-and-ssis-expression.md)   
 [Очередность и ассоциативность операторов](operator-precedence-and-associativity.md)   
 [Операторы (выражение служб SSIS)](operators-ssis-expression.md)  
  
  
