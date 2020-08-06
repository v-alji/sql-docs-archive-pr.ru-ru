---
title: Диалоговое окно "Выражение проверочного ограничения" (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.checkconstraintexpression
ms.assetid: beb6ce43-3913-4d66-8826-8e885335b790
author: stevestein
ms.author: sstein
ms.openlocfilehash: 38268d4e49a9c674c100bc22c0782e3e61477967
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654007"
---
# <a name="check-constraint-expression-dialog-box-visual-database-tools"></a><span data-ttu-id="11ccd-102">Диалоговое окно «Выражение проверочного ограничения» (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="11ccd-102">Check Constraint Expression Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="11ccd-103">При присоединении проверочных ограничений к таблице или столбцу нужно задать выражение SQL.</span><span class="sxs-lookup"><span data-stu-id="11ccd-103">When you attach a check constraint to a table or column, you must include an SQL expression.</span></span> <span data-ttu-id="11ccd-104">Введите в предоставляемое окно выражение проверочного ограничения.</span><span class="sxs-lookup"><span data-stu-id="11ccd-104">Type the check constraint expression in the box provided.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="11ccd-105">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="11ccd-105">UI element list</span></span>  
 <span data-ttu-id="11ccd-106">Выражение</span><span class="sxs-lookup"><span data-stu-id="11ccd-106">Expression</span></span>  
 <span data-ttu-id="11ccd-107">Ввод выражения</span><span class="sxs-lookup"><span data-stu-id="11ccd-107">Enter the expression</span></span>  
  
 <span data-ttu-id="11ccd-108">Для проверки данных на выполнение простого условия можно создать простое выражение ограничения; для проверки данных на выполнение нескольких условий можно создать сложное выражение с использованием логических операторов.</span><span class="sxs-lookup"><span data-stu-id="11ccd-108">You can create a simple constraint expression to check data for a simple condition; or you can create a complex expression, using Boolean operators, to check data for several conditions.</span></span> <span data-ttu-id="11ccd-109">Предположим, например, что в таблице «Авторы» есть столбец «Почтовый индекс», в котором должны находиться символьные строки из 5 цифр.</span><span class="sxs-lookup"><span data-stu-id="11ccd-109">For example, suppose the authors table has a zip column where a 5-digit character string is required.</span></span> <span data-ttu-id="11ccd-110">Данный образец выражения ограничения гарантирует, что в этом столбце разрешены только числа, состоящие из 5 цифр:</span><span class="sxs-lookup"><span data-stu-id="11ccd-110">This sample constraint expression guarantees that only 5-digit numbers are allowed:</span></span>  
  
```  
zip LIKE '[0-9][0-9][0-9][0-9][0-9]'  
```  
  
 <span data-ttu-id="11ccd-111">Или предположим, что в таблице продаж имеется столбец qty, для которого требуется значение больше 0.</span><span class="sxs-lookup"><span data-stu-id="11ccd-111">Or suppose the sales table has a column called qty which requires a value greater than 0.</span></span> <span data-ttu-id="11ccd-112">Данный образец ограничения гарантирует, что в этом столбце разрешены только положительные значения.</span><span class="sxs-lookup"><span data-stu-id="11ccd-112">This sample constraint guarantees that only positive values are allowed:</span></span>  
  
```  
qty > 0  
```  
  
 <span data-ttu-id="11ccd-113">Или предположим, что таблица «Заказы» ограничивает типы кредитных карт, принимаемых для всех заказов по кредитным картам.</span><span class="sxs-lookup"><span data-stu-id="11ccd-113">Or suppose the orders table limits the type of credit cards accepted for all credit card orders.</span></span> <span data-ttu-id="11ccd-114">Этот образец ограничения гарантирует, что если заказ размещен по кредитной карте, будут приняты только кредитные карты Visa, MasterCard или American Express:</span><span class="sxs-lookup"><span data-stu-id="11ccd-114">This sample constraint guarantees that if the order is placed on a credit card, then only Visa, MasterCard, or American Express is accepted:</span></span>  
  
```  
NOT (payment_method = 'credit card') OR  
   (card_type IN ('VISA', 'MASTERCARD', 'AMERICAN EXPRESS'))  
```  
  
## <a name="to-define-a-constraint-expression"></a><span data-ttu-id="11ccd-115">Определение выражения ограничения</span><span class="sxs-lookup"><span data-stu-id="11ccd-115">To define a constraint expression</span></span>  
 <span data-ttu-id="11ccd-116">На вкладке «Проверочные ограничения» страниц свойств в поле «Выражение ограничения» введите выражение со следующим синтаксисом:</span><span class="sxs-lookup"><span data-stu-id="11ccd-116">In the Check Constraints tab of the property pages, type an expression in the Constraint expression box using the following syntax:</span></span>  
  
 `{constant | column_name | function | (subquery)}`  
  
 `[{operator | AND | OR | NOT}`  
  
 `{constant | column_name | function | (subquery)}...]`  
  
 <span data-ttu-id="11ccd-117">Синтаксис SQL состоит из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="11ccd-117">The SQL syntax is made up of the following parameters:</span></span>  
  
|<span data-ttu-id="11ccd-118">Параметр</span><span class="sxs-lookup"><span data-stu-id="11ccd-118">Parameter</span></span>|<span data-ttu-id="11ccd-119">Description</span><span class="sxs-lookup"><span data-stu-id="11ccd-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="11ccd-120">constant</span><span class="sxs-lookup"><span data-stu-id="11ccd-120">constant</span></span>|<span data-ttu-id="11ccd-121">Символьное значение, например численные или символьные данные.</span><span class="sxs-lookup"><span data-stu-id="11ccd-121">A literal value, such as numeric or character data.</span></span> <span data-ttu-id="11ccd-122">Символьные данные должны быть заключены в одинарные кавычки (').</span><span class="sxs-lookup"><span data-stu-id="11ccd-122">Character data must be enclosed within single quotation marks (').</span></span>|  
|<span data-ttu-id="11ccd-123">column_name</span><span class="sxs-lookup"><span data-stu-id="11ccd-123">column_name</span></span>|<span data-ttu-id="11ccd-124">Указывает столбец.</span><span class="sxs-lookup"><span data-stu-id="11ccd-124">Specifies a column.</span></span>|  
|<span data-ttu-id="11ccd-125">function</span><span class="sxs-lookup"><span data-stu-id="11ccd-125">function</span></span>|<span data-ttu-id="11ccd-126">Встроенная функция.</span><span class="sxs-lookup"><span data-stu-id="11ccd-126">A built-in function.</span></span>|  
|<span data-ttu-id="11ccd-127">оператор</span><span class="sxs-lookup"><span data-stu-id="11ccd-127">operator</span></span>|<span data-ttu-id="11ccd-128">Арифметический оператор, побитовый оператор, оператор сравнения или строковый оператор.</span><span class="sxs-lookup"><span data-stu-id="11ccd-128">Arithmetic, bitwise, comparison, or string operators.</span></span>|  
|<span data-ttu-id="11ccd-129">AND</span><span class="sxs-lookup"><span data-stu-id="11ccd-129">AND</span></span>|<span data-ttu-id="11ccd-130">Используется в логических выражениях для соединения двух выражений.</span><span class="sxs-lookup"><span data-stu-id="11ccd-130">Use in Boolean expressions to connect two expressions.</span></span> <span data-ttu-id="11ccd-131">Результат возвращается, если оба выражения имеют значение TRUE.</span><span class="sxs-lookup"><span data-stu-id="11ccd-131">Results are returned when both expressions are true.</span></span><br /><br /> <span data-ttu-id="11ccd-132">Если в инструкции используются одновременно и AND, и OR, то первым обрабатывается оператор AND.</span><span class="sxs-lookup"><span data-stu-id="11ccd-132">When AND and OR are both used in a statement, AND is processed first.</span></span> <span data-ttu-id="11ccd-133">Можно изменить порядок выполнения, используя скобки.</span><span class="sxs-lookup"><span data-stu-id="11ccd-133">You can change the order of execution by using parentheses.</span></span>|  
|<span data-ttu-id="11ccd-134">OR</span><span class="sxs-lookup"><span data-stu-id="11ccd-134">OR</span></span>|<span data-ttu-id="11ccd-135">Используется в логических выражениях для соединения двух или более условий.</span><span class="sxs-lookup"><span data-stu-id="11ccd-135">Use in Boolean expressions to connect two or more conditions.</span></span> <span data-ttu-id="11ccd-136">Результат возвращается, если хотя бы одно условие имеет значение TRUE.</span><span class="sxs-lookup"><span data-stu-id="11ccd-136">Results are returned when either condition is true.</span></span><br /><br /> <span data-ttu-id="11ccd-137">Если в инструкции используются одновременно и AND, и OR, то оператор OR обрабатывается после оператора AND.</span><span class="sxs-lookup"><span data-stu-id="11ccd-137">When AND and OR are both used in a statement, OR is evaluated after AND.</span></span> <span data-ttu-id="11ccd-138">Можно изменить порядок выполнения, используя скобки.</span><span class="sxs-lookup"><span data-stu-id="11ccd-138">You can change the order of execution by using parentheses.</span></span>|  
|<span data-ttu-id="11ccd-139">NOT</span><span class="sxs-lookup"><span data-stu-id="11ccd-139">NOT</span></span>|<span data-ttu-id="11ccd-140">Инвертирует любое логическое выражение (которое может содержать ключевые слова LIKE, NULL, BETWEEN, IN и EXISTS).</span><span class="sxs-lookup"><span data-stu-id="11ccd-140">Negates any Boolean expression (which can include keywords, such as LIKE, NULL, BETWEEN, IN, and EXISTS).</span></span><br /><br /> <span data-ttu-id="11ccd-141">Если в инструкции используется несколько логических операторов, то первым обрабатывается оператор NOT.</span><span class="sxs-lookup"><span data-stu-id="11ccd-141">When more than one logical operator is used in a statement, NOT is processed first.</span></span> <span data-ttu-id="11ccd-142">Можно изменить порядок выполнения, используя скобки.</span><span class="sxs-lookup"><span data-stu-id="11ccd-142">You can change the order of execution by using parentheses.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="11ccd-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="11ccd-143">See Also</span></span>  
 <span data-ttu-id="11ccd-144">[Ограничения UNIQUE и проверочные ограничения](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="11ccd-144">[Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span></span>  
 [<span data-ttu-id="11ccd-145">Создание ограничений уникальности</span><span class="sxs-lookup"><span data-stu-id="11ccd-145">Create Unique Constraints</span></span>](../../relational-databases/tables/create-unique-constraints.md)  
  
  
