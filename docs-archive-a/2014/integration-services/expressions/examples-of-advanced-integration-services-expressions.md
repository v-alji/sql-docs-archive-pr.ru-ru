---
title: Примеры расширенных выражений служб Integration Services | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- functions [Integration Services]
- operators [Integration Services]
- expressions [Integration Services], examples
- examples [Integration Services]
ms.assetid: c7794ba3-0de5-466b-ae8a-9ddd27360049
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fb1e8dc6f9bffd22c917414f80f6ba9f257b25b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658930"
---
# <a name="examples-of-advanced-integration-services-expressions"></a><span data-ttu-id="e9e90-102">Примеры расширенных выражений служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="e9e90-102">Examples of Advanced Integration Services Expressions</span></span>
  <span data-ttu-id="e9e90-103">В этом разделе даются примеры расширенных выражений, объединяющих несколько операторов и функций.</span><span class="sxs-lookup"><span data-stu-id="e9e90-103">This section provides examples of advanced expressions that combine multiple operators and functions.</span></span> <span data-ttu-id="e9e90-104">Если выражение использует управление очередностью или преобразование «Условное разбиение», результат его оценки должен быть логическим.</span><span class="sxs-lookup"><span data-stu-id="e9e90-104">If an expression is used in a precedence constraint or the Conditional Split transformation, it must evaluate to a Boolean.</span></span> <span data-ttu-id="e9e90-105">Это ограничение, однако, не применяется к выражениям, используемым в выражениях свойств, переменных, преобразовании «Производный столбец» или в контейнере «цикл по элементам».</span><span class="sxs-lookup"><span data-stu-id="e9e90-105">That restriction, however, does not apply to expressions used in property expressions, variables, the Derived Column transformation, or the For Loop container.</span></span>  
  
 <span data-ttu-id="e9e90-106">В следующих примерах используются базы данных **AdventureWorks** и [!INCLUDE[ssSampleDBDWobject](../../includes/sssampledbdwobject-md.md)][!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9e90-106">The following examples use the **AdventureWorks** and the [!INCLUDE[ssSampleDBDWobject](../../includes/sssampledbdwobject-md.md)][!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases.</span></span> <span data-ttu-id="e9e90-107">В каждом примере указываются используемые в нем таблицы.</span><span class="sxs-lookup"><span data-stu-id="e9e90-107">Each example identifies the tables it uses.</span></span>  
  
## <a name="boolean-expressions"></a><span data-ttu-id="e9e90-108">Логические выражения</span><span class="sxs-lookup"><span data-stu-id="e9e90-108">Boolean Expressions</span></span>  
  
-   <span data-ttu-id="e9e90-109">В этом примере используется таблица **Product** .</span><span class="sxs-lookup"><span data-stu-id="e9e90-109">This example uses the **Product** table.</span></span> <span data-ttu-id="e9e90-110">Выражение оценивает значение месяца в столбце **SellStartDate** и возвращает TRUE, если месяцем является любой месяц года, начиная с июня.</span><span class="sxs-lookup"><span data-stu-id="e9e90-110">The expression evaluates the month entry in the **SellStartDate** column and returns TRUE if the month is June or later.</span></span>  
  
    ```  
    DATEPART("mm",SellStartDate) > 6  
    ```  
  
-   <span data-ttu-id="e9e90-111">В этом примере используется таблица **Product** .</span><span class="sxs-lookup"><span data-stu-id="e9e90-111">This example uses the **Product** table.</span></span> <span data-ttu-id="e9e90-112">Выражение оценивает округленный результат деления столбца **ListPrice** на столбец **StandardCost** и возвращает TRUE, если результат больше 1.5.</span><span class="sxs-lookup"><span data-stu-id="e9e90-112">The expression evaluates the rounded result of dividing the **ListPrice** column by the **StandardCost** column, and returns TRUE if the result is greater than 1.5.</span></span>  
  
    ```  
    ROUND(ListPrice / StandardCost,2) > 1.50  
    ```  
  
-   <span data-ttu-id="e9e90-113">В этом примере используется таблица **Product** .</span><span class="sxs-lookup"><span data-stu-id="e9e90-113">This example uses the **Product** table.</span></span> <span data-ttu-id="e9e90-114">Выражение возвращает TRUE, если результатом всех трех операций является TRUE.</span><span class="sxs-lookup"><span data-stu-id="e9e90-114">The expression returns TRUE if all three operations evaluate to TRUE.</span></span> <span data-ttu-id="e9e90-115">Столбец **Size** и переменная **BikeSize** имеют несовместимые типы данных, выражение требует явного приведения, как показано во втором примере.</span><span class="sxs-lookup"><span data-stu-id="e9e90-115">If the **Size** column and the **BikeSize** variable have incompatible data types, the expression requires an explicit cast as shown the second example.</span></span> <span data-ttu-id="e9e90-116">Приведение к типу данных DT_WSTR включает в себя длину строки.</span><span class="sxs-lookup"><span data-stu-id="e9e90-116">The cast to DT_WSTR includes the length of the string.</span></span>  
  
    ```  
    MakeFlag ==  TRUE && FinishedGoodsFlag == TRUE && Size != @BikeSize  
    MakeFlag ==  TRUE && FinishedGoodsFlag == TRUE  && Size != (DT_WSTR,10)@BikeSize  
    ```  
  
-   <span data-ttu-id="e9e90-117">Этот пример использует таблицу **CurrencyRate** .</span><span class="sxs-lookup"><span data-stu-id="e9e90-117">This example uses the **CurrencyRate** table.</span></span> <span data-ttu-id="e9e90-118">Выражение сравнивает значения в таблице и значения переменных.</span><span class="sxs-lookup"><span data-stu-id="e9e90-118">The expression compares values in tables and variables.</span></span> <span data-ttu-id="e9e90-119">Оно возвращает TRUE, если значения столбцов **FromCurrencyCode** или **ToCurrencyCode** равны значениям переменной и если значение **AverageRate** больше значения **EndOfDayRate**.</span><span class="sxs-lookup"><span data-stu-id="e9e90-119">It returns TRUE if entries in the **FromCurrencyCode** or **ToCurrencyCode** columns are equal to variable values and if the value in **AverageRate** is greater that the value in **EndOfDayRate**.</span></span>  
  
    ```  
    (FromCurrencyCode == @FromCur || ToCurrencyCode == @ToCur) && AverageRate > EndOfDayRate  
    ```  
  
-   <span data-ttu-id="e9e90-120">Этот пример использует таблицу **Currency** .</span><span class="sxs-lookup"><span data-stu-id="e9e90-120">This example uses the **Currency** table.</span></span> <span data-ttu-id="e9e90-121">Выражение возвращает TRUE, если первый символ в столбце **Name** — не «a» и не «A».</span><span class="sxs-lookup"><span data-stu-id="e9e90-121">The expression returns TRUE if the first character in the **Name** column is not a or A.</span></span>  
  
    ```  
    SUBSTRING(UPPER(Name),1,1) != "A"  
    ```  
  
     <span data-ttu-id="e9e90-122">Следующее выражение дает тот же результат, но оно более эффективно, т.к. в верхний регистр переводится только одна буква.</span><span class="sxs-lookup"><span data-stu-id="e9e90-122">The following expression provides the same results, but it is more efficient because only one character is converted to uppercase.</span></span>  
  
    ```  
    UPPER(SUBSTRING(Name,1,1)) != "A"  
    ```  
  
## <a name="non-boolean-expressions"></a><span data-ttu-id="e9e90-123">Нелогические выражения</span><span class="sxs-lookup"><span data-stu-id="e9e90-123">Non-Boolean Expressions</span></span>  
 <span data-ttu-id="e9e90-124">Нелогические выражения используются в преобразовании «Производный столбец», в выражениях свойств и в контейнере «цикл по элементам».</span><span class="sxs-lookup"><span data-stu-id="e9e90-124">Non-Boolean expressions are used in the Derived Column transformation, property expressions, and the For Loop container.</span></span>  
  
-   <span data-ttu-id="e9e90-125">Этот пример использует таблицу **Contact** .</span><span class="sxs-lookup"><span data-stu-id="e9e90-125">This example uses the **Contact** table.</span></span> <span data-ttu-id="e9e90-126">Выражение удаляет начальные и конечные пробелы из столбцов **FirstName**, **MiddleName**и **LastName** .</span><span class="sxs-lookup"><span data-stu-id="e9e90-126">The expression removes leading and trailing spaces from the **FirstName**, **MiddleName**, and **LastName** columns.</span></span> <span data-ttu-id="e9e90-127">Оно выделяет первую букву столбца **MiddleName** , если она не NULL, сцепляет инициал второго имени и значения столбцов **FirstName** и **LastName**, а затем вставляет необходимые пробелы между значениями.</span><span class="sxs-lookup"><span data-stu-id="e9e90-127">It extracts the first letter of the **MiddleName** column if it is not null, concatenates the middle initial and the values in **FirstName** and **LastName**, and inserts appropriate spaces between values.</span></span>  
  
    ```  
    TRIM(FirstName) + " " + (!ISNULL(MiddleName) ? SUBSTRING(MiddleName,1,1) + " " : "") + TRIM(LastName)  
    ```  
  
-   <span data-ttu-id="e9e90-128">Этот пример использует таблицу **Contact** .</span><span class="sxs-lookup"><span data-stu-id="e9e90-128">This example uses the **Contact** table.</span></span> <span data-ttu-id="e9e90-129">Выражение проверяет значения столбца **Salutation** .</span><span class="sxs-lookup"><span data-stu-id="e9e90-129">The expression validates entries in the **Salutation** column.</span></span> <span data-ttu-id="e9e90-130">Оно возвращает значение столбца **Salutation** или пустую строку.</span><span class="sxs-lookup"><span data-stu-id="e9e90-130">It returns a **Salutation** entry or an empty string.</span></span>  
  
    ```  
    (Salutation == "Sr." || Salutation == "Ms." || Salutation == "Sra." || Salutation == "Mr.") ? Salutation : ""  
    ```  
  
-   <span data-ttu-id="e9e90-131">В этом примере используется таблица **Product** .</span><span class="sxs-lookup"><span data-stu-id="e9e90-131">This example uses the **Product** table.</span></span> <span data-ttu-id="e9e90-132">Выражение преобразует первую букву в столбце **Color** в верхний регистр и преобразует остальные символы в нижний регистр.</span><span class="sxs-lookup"><span data-stu-id="e9e90-132">The expression converts the first character in the **Color** column to uppercase and converts remaining characters to lowercase.</span></span>  
  
    ```  
    UPPER(SUBSTRING(Color,1,1)) + LOWER(SUBSTRING(Color,2,15))  
    ```  
  
-   <span data-ttu-id="e9e90-133">В этом примере используется таблица **Product** .</span><span class="sxs-lookup"><span data-stu-id="e9e90-133">This example uses the **Product** table.</span></span> <span data-ttu-id="e9e90-134">Выражение вычисляет номер месяца, в котором был продан продукт и возвращает строку «Unknown», если столбец **SellStartDate** или столбец **SellEndDate** содержат NULL.</span><span class="sxs-lookup"><span data-stu-id="e9e90-134">The expression calculates the number of months a product has been sold and returns the string "Unknown" if either the **SellStartDate** or the **SellEndDate** column contains NULL.</span></span>  
  
    ```  
    !(ISNULL(SellStartDate)) && !(ISNULL(SellEndDate)) ? (DT_WSTR,2)DATEDIFF("mm",SellStartDate,SellEndDate) : "Unknown"  
    ```  
  
-   <span data-ttu-id="e9e90-135">В этом примере используется таблица **Product** .</span><span class="sxs-lookup"><span data-stu-id="e9e90-135">This example uses the **Product** table.</span></span> <span data-ttu-id="e9e90-136">Выражение вычисляет наценку на значение столбца **StandardCost** и округляет результат с точностью до двух знаков.</span><span class="sxs-lookup"><span data-stu-id="e9e90-136">The expression calculates the markup on the **StandardCost** column and rounds the result to a precision of two.</span></span> <span data-ttu-id="e9e90-137">Результат представляется в виде процентного значения.</span><span class="sxs-lookup"><span data-stu-id="e9e90-137">The result is presented as a percentage.</span></span>  
  
    ```  
    ROUND(ListPrice / StandardCost,2) * 100  
    ```  
  
## <a name="related-tasks"></a><span data-ttu-id="e9e90-138">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="e9e90-138">Related Tasks</span></span>  
 [<span data-ttu-id="e9e90-139">Использование выражения в компоненте потока данных</span><span class="sxs-lookup"><span data-stu-id="e9e90-139">Use an Expression in a Data Flow Component</span></span>](../use-an-expression-in-a-data-flow-component.md)  
  
## <a name="related-content"></a><span data-ttu-id="e9e90-140">См. также</span><span class="sxs-lookup"><span data-stu-id="e9e90-140">Related Content</span></span>  
 <span data-ttu-id="e9e90-141">Техническая статья [Памятка выражений служб SSIS](https://pragmaticworks.com/Resources/Cheat-Sheets/SSIS-Expression-Cheat-Sheet)на сайте pragmaticworks.com</span><span class="sxs-lookup"><span data-stu-id="e9e90-141">Technical article, [SSIS Expression Cheat Sheet](https://pragmaticworks.com/Resources/Cheat-Sheets/SSIS-Expression-Cheat-Sheet), on pragmaticworks.com</span></span>  
  
  
