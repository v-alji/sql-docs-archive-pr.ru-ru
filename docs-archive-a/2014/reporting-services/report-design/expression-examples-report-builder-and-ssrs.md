---
title: Примеры выражений (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.prod: sql-server-2014
ms.technology: reporting-services
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.custom: ''
ms.date: 03/08/2017
ms.openlocfilehash: c7ef06143dafdb5034d0f6202fdc16bc51f74ca8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658121"
---
# <a name="expression-examples-report-builder-and-ssrs"></a><span data-ttu-id="34011-102">Примеры выражений (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="34011-102">Expression Examples (Report Builder and SSRS)</span></span>

<span data-ttu-id="34011-103">Выражения часто используются в отчетах для управления содержимым и внешним видом отчета.</span><span class="sxs-lookup"><span data-stu-id="34011-103">Expressions are used frequently in reports to control content and report appearance.</span></span> <span data-ttu-id="34011-104">Выражения записываются в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] и могут использовать встроенные функции пользовательский код, переменные отчета и группы, а также пользовательские переменные.</span><span class="sxs-lookup"><span data-stu-id="34011-104">Expressions are written in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)], and can use built-in functions custom code, report and group variables, and user-defined variables.</span></span> <span data-ttu-id="34011-105">Выражения начинаются со знака равенства (=).</span><span class="sxs-lookup"><span data-stu-id="34011-105">Expressions begin with an equal sign (=).</span></span> <span data-ttu-id="34011-106">Дополнительные сведения о редакторе выражений и типах ссылок, которые могут быть включены, см. в разделах [Использование выражений в отчетах (построитель отчетов и службы SSRS)](expression-uses-in-reports-report-builder-and-ssrs.md) и [Добавление выражения (построитель отчетов и службы SSRS)](add-an-expression-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="34011-106">For more information about the expression editor and the types of references that you can include, see [Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md), and [Add an Expression &#40;Report Builder and SSRS&#41;](add-an-expression-report-builder-and-ssrs.md).</span></span>  

> [!IMPORTANT]  
>  <span data-ttu-id="34011-107">При включении функции «песочницы» для языка определения отчетов только определенные типы и элементы смогут использовать в тексте выражения во время публикации отчета.</span><span class="sxs-lookup"><span data-stu-id="34011-107">When RDL Sandboxing is enabled, only certain types and members can be used in expression text at report publish time.</span></span> <span data-ttu-id="34011-108">Дополнительные сведения см. в статье [Enable and Disable RDL Sandboxing](../enable-and-disable-rdl-sandboxing.md).</span><span class="sxs-lookup"><span data-stu-id="34011-108">For more information, see [Enable and Disable RDL Sandboxing](../enable-and-disable-rdl-sandboxing.md).</span></span>  

<span data-ttu-id="34011-109">В данном разделе приведены примеры выражений, которые можно использовать для решения типичных задач в отчете.</span><span class="sxs-lookup"><span data-stu-id="34011-109">This topic provides examples of expressions that can be used for common tasks in a report.</span></span>  

-   <span data-ttu-id="34011-110">[Функции языка Visual Basic](#VisualBasicFunctions) . Примеры функций дат, строковых функций, функций преобразования и условных функций [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="34011-110">[Visual Basic Functions](#VisualBasicFunctions) Examples for date, string, conversion and conditional [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] functions.</span></span>  

-   <span data-ttu-id="34011-111">[Функции отчета](#ReportFunctions) Примеры статистических функций и других встроенных функций отчета.</span><span class="sxs-lookup"><span data-stu-id="34011-111">[Report Functions](#ReportFunctions) Examples for aggregates and other built-in report functions.</span></span>  

-   <span data-ttu-id="34011-112">[Внешний вид данных отчета](#AppearanceofReportData) Примеры изменения внешнего вида отчета.</span><span class="sxs-lookup"><span data-stu-id="34011-112">[Appearance of Report Data](#AppearanceofReportData) Examples for changing the appearance of a report.</span></span>  

-   <span data-ttu-id="34011-113">[Свойства](#Properties) Примеры задания свойств элемента отчета, отвечающих за формат и видимость.</span><span class="sxs-lookup"><span data-stu-id="34011-113">[Properties](#Properties) Examples for setting report item properties to control format or visibility.</span></span>  

-   <span data-ttu-id="34011-114">[Параметры](#Parameters) Примеры использования параметров в выражении.</span><span class="sxs-lookup"><span data-stu-id="34011-114">[Parameters](#Parameters) Examples for using parameters in an expression.</span></span>  

-   <span data-ttu-id="34011-115">[Пользовательский код](#CustomCode) Примеры внедренного пользовательского кода.</span><span class="sxs-lookup"><span data-stu-id="34011-115">[Custom Code](#CustomCode) Examples of embedded custom code.</span></span>  

<span data-ttu-id="34011-116">Примеры выражений для специальных задач см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="34011-116">For expression examples for specific uses, see the following topics:</span></span>  

-   [<span data-ttu-id="34011-117">Примеры выражений групп (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="34011-117">Group Expression Examples &#40;Report Builder and SSRS&#41;</span></span>](expression-examples-report-builder-and-ssrs.md)  

-   [<span data-ttu-id="34011-118">Примеры уравнений фильтра (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="34011-118">Filter Equation Examples &#40;Report Builder and SSRS&#41;</span></span>](filter-equation-examples-report-builder-and-ssrs.md)  

-   [<span data-ttu-id="34011-119">Часто используемые фильтры (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="34011-119">Commonly Used Filters &#40;Report Builder and SSRS&#41;</span></span>](commonly-used-filters-report-builder-and-ssrs.md)  

-   [<span data-ttu-id="34011-120">Ссылки на коллекции переменных отчета и группы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="34011-120">Report and Group Variables Collections References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-report-and-group-variables-references-report-builder.md)  

<span data-ttu-id="34011-121">Дополнительные сведения о простых и сложных выражениях, о местах, где можно использовать выражения, и о типах ссылок, которые можно включать в выражения, см. в подразделах в разделе [Выражения (построитель отчетов и службы SSRS)](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="34011-121">For more information about simple and complex expressions, where you can use expressions, and the types of references that you can include in an expression, see topics under [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span> <span data-ttu-id="34011-122">Дополнительные сведения о контексте, в котором выражения оцениваются для вычисления статистических выражений, см. в разделе [Область выражения для суммирования, агрегатных функций и встроенных коллекций (построитель отчетов и службы SSRS)](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="34011-122">For more information about the context in which expressions are evaluated for calculating aggregates, see [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  

<span data-ttu-id="34011-123">О написании выражений, в которых используются многие из функций и операторов, также используемых в примерах выражений в этом разделе, но в контексте создания отчета, см. в разделе [Tutorial: Introducing Expressions](../tutorial-introducing-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="34011-123">To learn how to write expressions that use many of the functions and operators also used by expression examples in this topic, but in the context of writing a report, see [Tutorial: Introducing Expressions](../tutorial-introducing-expressions.md).</span></span>  

<span data-ttu-id="34011-124">Редактор выражений поддерживает иерархическое представление встроенных функций.</span><span class="sxs-lookup"><span data-stu-id="34011-124">The expression editor includes a hierarchical view of built-in functions.</span></span> <span data-ttu-id="34011-125">Если выбрать функцию, на панели значений появится пример программного кода.</span><span class="sxs-lookup"><span data-stu-id="34011-125">When you select the function, a code example appears in the Values pane.</span></span> <span data-ttu-id="34011-126">Дополнительные сведения см. в разделе Диалоговое окно [выражения](../expression-dialog-box.md) или [диалоговое окно выражения &#40;построитель отчетов&#41;](../expression-dialog-box-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="34011-126">For more information, see the [Expression Dialog Box](../expression-dialog-box.md) or [Expression Dialog Box &#40;Report Builder&#41;](../expression-dialog-box-report-builder.md).</span></span>  

## <a name="functions"></a><span data-ttu-id="34011-127">Функции</span><span class="sxs-lookup"><span data-stu-id="34011-127">Functions</span></span>  

<span data-ttu-id="34011-128">Многие выражения в отчете содержат вызовы функций.</span><span class="sxs-lookup"><span data-stu-id="34011-128">Many expressions in a report contain functions.</span></span> <span data-ttu-id="34011-129">Они позволяют форматировать данные, применять логические операции и производить доступ к метаданным отчета.</span><span class="sxs-lookup"><span data-stu-id="34011-129">You can format data, apply logic, and access report metadata using these functions.</span></span> <span data-ttu-id="34011-130">Можно написать выражения, использующие функции из [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] библиотеки времени выполнения, а также из <xref:System.Convert> <xref:System.Math> пространств имен и.</span><span class="sxs-lookup"><span data-stu-id="34011-130">You can write expressions that use functions from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] run-time library, and from the <xref:System.Convert> and <xref:System.Math> namespaces.</span></span> <span data-ttu-id="34011-131">Можно добавить ссылки на функции из других сборок или пользовательский код.</span><span class="sxs-lookup"><span data-stu-id="34011-131">You can add references to functions from other assemblies or custom code.</span></span> <span data-ttu-id="34011-132">Можно также использовать классы из [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] , включая <xref:System.Text.RegularExpressions> .</span><span class="sxs-lookup"><span data-stu-id="34011-132">You can also use classes from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], including <xref:System.Text.RegularExpressions>.</span></span>  

###  <a name="visual-basic-functions"></a><a name="VisualBasicFunctions"></a> <span data-ttu-id="34011-133">Функции языка Visual Basic</span><span class="sxs-lookup"><span data-stu-id="34011-133">Visual Basic Functions</span></span>  
<span data-ttu-id="34011-134">Функции языка [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] позволяют управлять данными, отображаемыми в текстовых полях, или используются в параметрах, свойствах и других областях отчета.</span><span class="sxs-lookup"><span data-stu-id="34011-134">You can use [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] functions to manipulate the data that is displayed in text boxes or that is used for parameters, properties, or other areas of the report.</span></span> <span data-ttu-id="34011-135">В этом разделе приведены примеры, демонстрирующие применение некоторых из этих функций.</span><span class="sxs-lookup"><span data-stu-id="34011-135">This section provides examples demonstrating some of these functions.</span></span> <span data-ttu-id="34011-136">Дополнительные сведения см. в разделе [Компоненты библиотеки времени выполнения Visual Basic](https://go.microsoft.com/fwlink/?LinkId=198941) в MSDN.</span><span class="sxs-lookup"><span data-stu-id="34011-136">For more information, see [Visual Basic Runtime Library Members](https://go.microsoft.com/fwlink/?LinkId=198941) on MSDN.</span></span>  

<span data-ttu-id="34011-137">Платформа [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] предоставляет множество параметров пользовательских форматов, например для конкретных форматов даты.</span><span class="sxs-lookup"><span data-stu-id="34011-137">The [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] provides many custom format options, for example, for specific date formats.</span></span> <span data-ttu-id="34011-138">Дополнительные сведения см. в статье [Типы форматирования](https://go.microsoft.com/fwlink/?LinkId=112024) на веб-сайте MSDN.</span><span class="sxs-lookup"><span data-stu-id="34011-138">For more information, see [Formatting Types](https://go.microsoft.com/fwlink/?LinkId=112024) on MSDN.</span></span>  

#### <a name="math-functions"></a><span data-ttu-id="34011-139">Математические функции</span><span class="sxs-lookup"><span data-stu-id="34011-139">Math Functions</span></span>  

-   <span data-ttu-id="34011-140">Функция `Round` полезна при округлении чисел до ближайшего целого числа.</span><span class="sxs-lookup"><span data-stu-id="34011-140">The `Round` function is useful to round numbers to the nearest integer.</span></span> <span data-ttu-id="34011-141">В следующем выражении значение 1.3 округляется до 1:</span><span class="sxs-lookup"><span data-stu-id="34011-141">The following expression rounds a 1.3 to 1:</span></span>  

```  
= Round(1.3)  
```  

<span data-ttu-id="34011-142">Можно также написать выражение, округляющее значение до указанного кратного, подобное функции `MRound` в Excel.</span><span class="sxs-lookup"><span data-stu-id="34011-142">You can also write an expression to round a value to a multiple that you specify, similar to the `MRound` function in Excel.</span></span> <span data-ttu-id="34011-143">Умножьте значение на фактор, образующий целое число, округлите число, а затем разделите его на тот же фактор.</span><span class="sxs-lookup"><span data-stu-id="34011-143">Multiply the value by a factor that creates an integer, round the number, and then divide by the same factor.</span></span> <span data-ttu-id="34011-144">Например, для округления числа 1,3 до ближайшего числа, кратного 2(1.4), воспользуйтесь следующим выражением:</span><span class="sxs-lookup"><span data-stu-id="34011-144">For example, to round 1.3 to the nearest multiple of .2 (1.4), use the following expression:</span></span>  

```  
= Round(1.3*5)/5  
```  

####  <a name="date-functions"></a><a name="DateFunctions"></a><span data-ttu-id="34011-145">Функции даты</span><span class="sxs-lookup"><span data-stu-id="34011-145">Date Functions</span></span>  

-   <span data-ttu-id="34011-146">Функция `Today` возвращает текущую дату.</span><span class="sxs-lookup"><span data-stu-id="34011-146">The `Today` function provides the current date.</span></span> <span data-ttu-id="34011-147">Следующее выражение можно указать в текстовом поле для вывода даты формирования отчета или в качестве параметра фильтрации данных на основе текущей даты.</span><span class="sxs-lookup"><span data-stu-id="34011-147">This expression can be used in a text box to display the date on the report, or in a parameter to filter data based on the current date.</span></span>  

```  
=Today()  
```  

-   <span data-ttu-id="34011-148">Функция `DateAdd` может оказаться полезной для вычисления диапазона дат на основе одного параметра.</span><span class="sxs-lookup"><span data-stu-id="34011-148">The `DateAdd` function is useful for supplying a range of dates based on a single parameter.</span></span> <span data-ttu-id="34011-149">Следующее выражение вычисляет дату, которая отстоит на 6 месяцев позже даты, указанной в параметре *StartDate*.</span><span class="sxs-lookup"><span data-stu-id="34011-149">The following expression provides a date that is six months after the date from a parameter named *StartDate*.</span></span>  

```  
=DateAdd(DateInterval.Month, 6, Parameters!StartDate.Value)  
```  

-   <span data-ttu-id="34011-150">Функция `Year` отображает год для конкретной даты.</span><span class="sxs-lookup"><span data-stu-id="34011-150">The `Year` function displays the year for a particular date.</span></span> <span data-ttu-id="34011-151">Это можно использовать для группирования по датам или для вывода года в качестве метки для набора дат.</span><span class="sxs-lookup"><span data-stu-id="34011-151">You can use this to group dates together or to display the year as a label for a set of dates.</span></span> <span data-ttu-id="34011-152">Выражение возвращает год для заданной группы дат заказов на продажу.</span><span class="sxs-lookup"><span data-stu-id="34011-152">This expression provides the year for a given group of sales order dates.</span></span> <span data-ttu-id="34011-153">Для работы с датами можно также пользоваться функцией `Month` и другими.</span><span class="sxs-lookup"><span data-stu-id="34011-153">The `Month` function and other functions can also be used to manipulate dates.</span></span> <span data-ttu-id="34011-154">Дополнительные сведения см. в документации по [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34011-154">For more information, see the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] documentation.</span></span>  

```  
=Year(Fields!OrderDate.Value)  
```  

-   <span data-ttu-id="34011-155">Для настройки формата функции можно объединять в выражении.</span><span class="sxs-lookup"><span data-stu-id="34011-155">You can combine functions in an expression to customize the format.</span></span> <span data-ttu-id="34011-156">Следующее выражение меняет формат даты с формы «месяц-день-год» на форму «месяц-неделя-день недели».</span><span class="sxs-lookup"><span data-stu-id="34011-156">The following expression changes the format of a date in the form month-day-year to month-week-week number.</span></span> <span data-ttu-id="34011-157">Например, 12/23/2009 на декабрь неделя 3:</span><span class="sxs-lookup"><span data-stu-id="34011-157">For example, 12/23/2009 to December Week 3:</span></span>  

```  
=Format(Fields!MyDate.Value, "MMMM") & " Week " &   
(Int(DateDiff("d", DateSerial(Year(Fields!MyDate.Value),   
Month(Fields!MyDate.Value),1), Fields!FullDateAlternateKey.Value)/7)+1).ToString  
```  

<span data-ttu-id="34011-158">При использовании в качестве вычисляемого поля в наборе данных с помощью этого выражения можно выполнить агрегатную обработку значений в диаграмме по неделям каждого месяца.</span><span class="sxs-lookup"><span data-stu-id="34011-158">When used as a calculated field in a dataset, you can use this expression on a chart to aggregate values by week within each month.</span></span>  

-   <span data-ttu-id="34011-159">Следующее выражение форматирует значение SellStartDate как МММ-ГГ.</span><span class="sxs-lookup"><span data-stu-id="34011-159">The following expression formats the SellStartDate value as MMM-YY.</span></span> <span data-ttu-id="34011-160">Поле SellStartDate имеет тип datetime.</span><span class="sxs-lookup"><span data-stu-id="34011-160">SellStartDate field is a datetime data type.</span></span>  

```  
=FORMAT(Fields!SellStartDate.Value, "MMM-yy")  
```  

-   <span data-ttu-id="34011-161">Следующее выражение форматирует значение SellStartDate как дд/ММ/гггг.</span><span class="sxs-lookup"><span data-stu-id="34011-161">The following expression formats the SellStartDate value as dd/MM/yyyy.</span></span> <span data-ttu-id="34011-162">Поле SellStartDate имеет тип datetime.</span><span class="sxs-lookup"><span data-stu-id="34011-162">The SellStartDate field is a datetime data type.</span></span>  

```  
=FORMAT(Fields!SellStartDate.Value, "dd/MM/yyyy")  
```  

-   <span data-ttu-id="34011-163">Функция `CDate` преобразует это значение в дату.</span><span class="sxs-lookup"><span data-stu-id="34011-163">The `CDate` function converts the value to a date.</span></span> <span data-ttu-id="34011-164">Функция `Now` возвращает значение даты, которое содержит текущую дату и время по часам компьютера.</span><span class="sxs-lookup"><span data-stu-id="34011-164">The `Now` function returns a date value containing the current date and time according to your system.</span></span> <span data-ttu-id="34011-165">`DateDiff` возвращает значение типа Long, указывающее число интервалов времени между двумя значениями типа Date.</span><span class="sxs-lookup"><span data-stu-id="34011-165">`DateDiff` returns a Long value specifying the number of time intervals between two Date values.</span></span>  

<span data-ttu-id="34011-166">В следующем примере показана дата начала текущего года</span><span class="sxs-lookup"><span data-stu-id="34011-166">The following example displays the start date of the current year</span></span>  

```  
=DateAdd(DateInterval.Year,DateDiff(DateInterval.Year,CDate("01/01/1900"),Now()),CDate("01/01/1900"))  
```  

-   <span data-ttu-id="34011-167">В следующем примере показана дата начала прошлого месяца с учетом текущего месяца.</span><span class="sxs-lookup"><span data-stu-id="34011-167">The following example displays the start date for the previous month based on the current month.</span></span>  

```  
=DateAdd(DateInterval.Month,DateDiff(DateInterval.Month,CDate("01/01/1900"),Now())-1,CDate("01/01/1900"))  
```  

-   <span data-ttu-id="34011-168">Следующее выражение создает годы интервала между SellStartDate и LastReceiptDate.</span><span class="sxs-lookup"><span data-stu-id="34011-168">The following expression generates the interval years between SellStartDate and LastReceiptDate.</span></span> <span data-ttu-id="34011-169">Эти поля находятся в разных наборах данных — DataSet1 и DataSet2.</span><span class="sxs-lookup"><span data-stu-id="34011-169">These fields are in two different datasets, DataSet1 and DataSet2.</span></span> <span data-ttu-id="34011-170">[Функция First (построитель отчетов и службы SSRS)](report-builder-functions-first-function.md), являющаяся агрегатной функцией, возвращает первое значение SellStartDate в DataSet1 и первое значение LastReceiptDate в DataSet2.</span><span class="sxs-lookup"><span data-stu-id="34011-170">The [First Function &#40;Report Builder and SSRS&#41;](report-builder-functions-first-function.md), which is an aggregate function, returns the first value of SellStartDate in DataSet1 and the first value of LastReceiptDate in DataSet2.</span></span>  

```  
=DATEDIFF("yyyy", First(Fields!SellStartDate.Value, "DataSet1"), First(Fields!LastReceiptDate.Value, "DataSet2"))  
```  

-   <span data-ttu-id="34011-171">Функция `DatePart` возвращает значение Integer с указанным компонентом заданного значения Date. Следующее выражение возвращает год первого значения SellStartDate в DataSet1.</span><span class="sxs-lookup"><span data-stu-id="34011-171">The `DatePart` function returns an Integer value containing the specified component of a given Date value.The following expression returns the year for the first value of the SellStartDate in DataSet1.</span></span> <span data-ttu-id="34011-172">Область набора данных заданы из-за наличия нескольких наборов данных в отчете.</span><span class="sxs-lookup"><span data-stu-id="34011-172">The dataset scope is specified because there are multiple datasets in the report.</span></span>  

```  
=Datepart("yyyy", First(Fields!SellStartDate.Value, "DataSet1"))  

```  

-   <span data-ttu-id="34011-173">Функция `DateSerial` возвращает значение Date, представляющее указанные год, месяц и день, в котором время задано как полночь.</span><span class="sxs-lookup"><span data-stu-id="34011-173">The `DateSerial` function returns a Date value representing a specified year, month, and day, with the time information set to midnight.</span></span> <span data-ttu-id="34011-174">В следующем примере показана дата окончания прошлого месяца с учетом текущего месяца.</span><span class="sxs-lookup"><span data-stu-id="34011-174">The following example displays the ending date for the prior month, based on the current month.</span></span>  

```  
=DateSerial(Year(Now()), Month(Now()), "1").AddDays(-1)  
```  

-   <span data-ttu-id="34011-175">Следующее выражение отображает разные даты на основе значения параметра даты, выбранного пользователем.</span><span class="sxs-lookup"><span data-stu-id="34011-175">The following expressions display various dates based on a date parameter value selected by the user.</span></span>  

|<span data-ttu-id="34011-176">Описание примера</span><span class="sxs-lookup"><span data-stu-id="34011-176">Example Description</span></span>|<span data-ttu-id="34011-177">Пример</span><span class="sxs-lookup"><span data-stu-id="34011-177">Example</span></span>|  
|-------------------------|-------------|  
|<span data-ttu-id="34011-178">Вчера</span><span class="sxs-lookup"><span data-stu-id="34011-178">Yesterday</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value)-1)`|  
|<span data-ttu-id="34011-179">Два дня назад</span><span class="sxs-lookup"><span data-stu-id="34011-179">Two Days Ago</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value)-2)`|  
|<span data-ttu-id="34011-180">Месяц назад</span><span class="sxs-lookup"><span data-stu-id="34011-180">One Month Ago</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value)-1,Day(Parameters!TodaysDate.Value))`|  
|<span data-ttu-id="34011-181">Два месяца назад</span><span class="sxs-lookup"><span data-stu-id="34011-181">Two Months Ago</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value)-2,Day(Parameters!TodaysDate.Value))`|  
|<span data-ttu-id="34011-182">Год назад</span><span class="sxs-lookup"><span data-stu-id="34011-182">One Year Ago</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value)-1,Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value))`|  
|<span data-ttu-id="34011-183">Два года назад</span><span class="sxs-lookup"><span data-stu-id="34011-183">Two Years Ago</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value)-2,Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value))`|  

####  <a name="string-functions"></a><a name="StringFunctions"></a><span data-ttu-id="34011-184">Строковые функции</span><span class="sxs-lookup"><span data-stu-id="34011-184">String Functions</span></span>  

-   <span data-ttu-id="34011-185">Объединяют несколько полей с помощью операторов объединения и констант [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="34011-185">Combine more than one field by using concatenation operators and [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] constants.</span></span> <span data-ttu-id="34011-186">Следующее выражение возвращает два поля, каждое на отдельной строке в одном текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="34011-186">The following expression returns two fields, each on a separate line in the same text box:</span></span>  

```  
=Fields!FirstName.Value & vbCrLf & Fields!LastName.Value   
```  

-   <span data-ttu-id="34011-187">Функция `Format` позволяет отформатировать даты и числа в виде строки.</span><span class="sxs-lookup"><span data-stu-id="34011-187">Format dates and numbers in a string with the `Format` function.</span></span> <span data-ttu-id="34011-188">Следующее выражение отображает значения параметров *StartDate* и *EndDate* в длинном формате даты.</span><span class="sxs-lookup"><span data-stu-id="34011-188">The following expression displays values of the *StartDate* and *EndDate* parameters in long date format:</span></span>  

```  
=Format(Parameters!StartDate.Value, "D") & " through " &  Format(Parameters!EndDate.Value, "D")    
```  

<span data-ttu-id="34011-189">Если текстовое поле содержит только дату или число, следует использовать свойство формат текстового поля, чтобы применить форматирование вместо `Format` функции в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="34011-189">If the text box contains only a date or number, you should use the Format property of the text box to apply formatting instead of the `Format` function within the text box.</span></span>  

-   <span data-ttu-id="34011-190">`Right`Функции, `Len` и `InStr` полезны для возвращения подстроки, например, путем обрезки имени пользователя *домена* \\ *username* только именем.</span><span class="sxs-lookup"><span data-stu-id="34011-190">The `Right`, `Len`, and `InStr` functions are useful for returning a substring, for example, trimming *DOMAIN*\\*username* to just the user name.</span></span> <span data-ttu-id="34011-191">Следующее выражение возвращает часть строки параметра\\User *, расположенную справа от символа обратной косой черты (*).</span><span class="sxs-lookup"><span data-stu-id="34011-191">The following expression returns the part of the string to the right of a backslash (\\) character from a parameter named *User*:</span></span>  

```  
=Right(Parameters!User.Value, Len(Parameters!User.Value) - InStr(Parameters!User.Value, "\"))  
```  

<span data-ttu-id="34011-192">Следующее выражение приводит к тому же значению, что и предыдущее, с использованием членов [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <xref:System.String> класса вместо [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] функций:</span><span class="sxs-lookup"><span data-stu-id="34011-192">The following expression results in the same value as the previous one, using members of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <xref:System.String> class instead of [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] functions:</span></span>  

```  
=Parameters!User.Value.Substring(Parameters!User.Value.IndexOf("\")+1, Parameters!User.Value.Length-Parameters!User.Value.IndexOf("\")-1)  
```  

-   <span data-ttu-id="34011-193">Отображает выбранные значения из многозначного параметра.</span><span class="sxs-lookup"><span data-stu-id="34011-193">Display the selected values from a multivalue parameter.</span></span> <span data-ttu-id="34011-194">В следующем примере функция используется `Join` для сцепления выбранных значений параметра *MySelection* с одной строкой, которая может быть задана как выражение для значения текстового поля в элементе отчета:</span><span class="sxs-lookup"><span data-stu-id="34011-194">The following example uses the `Join` function to concatenate the selected values of the parameter *MySelection* into a single string that can be set as an expression for the value of a text box in a report item:</span></span>  

```  
= Join(Parameters!MySelection.Value)  
```  

<span data-ttu-id="34011-195">В следующем примере производится то же, что и в приведенном выше примере, а перед списком выбранных значений отображается строка текста.</span><span class="sxs-lookup"><span data-stu-id="34011-195">The following example does the same as the above example, as well as displays a text string prior to the list of selected values.</span></span>  

```  
="Report for " & JOIN(Parameters!MySelection.Value, " & ")  

```  

-   <span data-ttu-id="34011-196">`Regex`Функции из [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <xref:System.Text.RegularExpressions> используются для изменения формата существующих строк, например для форматирования телефонного номера.</span><span class="sxs-lookup"><span data-stu-id="34011-196">The `Regex` functions from the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <xref:System.Text.RegularExpressions> are useful for changing the format of existing strings, for example, formatting a telephone number.</span></span> <span data-ttu-id="34011-197">Следующее выражение использует `Replace` функцию для изменения формата 10-значного телефонного номера в поле с "*nnn* - *nnn* - *nnnn*" на "(*nnn*) *nnn* - *nnnn*":</span><span class="sxs-lookup"><span data-stu-id="34011-197">The following expression uses the `Replace` function to change the format of a ten-digit telephone number in a field from "*nnn*-*nnn*-*nnnn*" to "(*nnn*) *nnn*-*nnnn*":</span></span>  

```  
=System.Text.RegularExpressions.Regex.Replace(Fields!Phone.Value, "(\d{3})[ -.]*(\d{3})[ -.]*(\d{4})", "($1) $2-$3")  
```  

> [!NOTE]  
>  <span data-ttu-id="34011-198">Убедитесь, что значение Fields!Phone.Value не содержит лишних пробелов и имеет тип <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="34011-198">Verify that the value for Fields!Phone.Value has no extra spaces and is of type <xref:System.String>.</span></span>  

#### <a name="lookup"></a><span data-ttu-id="34011-199">Поиск</span><span class="sxs-lookup"><span data-stu-id="34011-199">Lookup</span></span>  

-   <span data-ttu-id="34011-200">При указании ключевого поля можно использовать функцию `Lookup` для извлечения значения из набора данных со связью «один к одному», например для пары «ключ-значение».</span><span class="sxs-lookup"><span data-stu-id="34011-200">By specifying a key field, you can use the `Lookup` function to retrieve a value from a dataset for a one-to-one relationship, for example, a key-value pair.</span></span> <span data-ttu-id="34011-201">Следующее выражение отображает из набора данных (Product) название продукта по его идентификатору:</span><span class="sxs-lookup"><span data-stu-id="34011-201">The following expression displays the product name from a dataset ("Product"), given the product identifier to match on:</span></span>  

```  
=Lookup(Fields!PID.Value, Fields!ProductID.Value, Fields!ProductName.Value, "Product")  
```  

#### <a name="lookupset"></a><span data-ttu-id="34011-202">LookupSet</span><span class="sxs-lookup"><span data-stu-id="34011-202">LookupSet</span></span>  

-   <span data-ttu-id="34011-203">Задавая ключевое поле, можно использовать функцию `LookupSet` для извлечения набора значений из набора данных со связью «один ко многим».</span><span class="sxs-lookup"><span data-stu-id="34011-203">By specifying a key field, you can use the `LookupSet` function to retrieve a set of values from a dataset for a one-to-many relationship.</span></span> <span data-ttu-id="34011-204">Например, у одного человека может быть несколько телефонных номеров.</span><span class="sxs-lookup"><span data-stu-id="34011-204">For example, a person can have multiple telephone numbers.</span></span> <span data-ttu-id="34011-205">В следующем примере предположим, что набор данных PhoneList содержит в каждой строке идентификатор пользователя и телефонный номер.</span><span class="sxs-lookup"><span data-stu-id="34011-205">In the following example, assume the dataset PhoneList contains a person identifier and a telephone number in each row.</span></span> <span data-ttu-id="34011-206">Функция `LookupSet` возвращает массив значений.</span><span class="sxs-lookup"><span data-stu-id="34011-206">`LookupSet` returns an array of values.</span></span> <span data-ttu-id="34011-207">В следующем выражении возвращаемые значения объединяются в одну строку. Для пользователя отображается список телефонных номеров по его ContactID:</span><span class="sxs-lookup"><span data-stu-id="34011-207">The following expression combines the return values into a single string and displays the list of telephone numbers for the person specified by ContactID:</span></span>  

```  
=Join(LookupSet(Fields!ContactID.Value, Fields!PersonID.Value, Fields!PhoneNumber.Value, "PhoneList"),",")  
```  

####  <a name="conversion-functions"></a><a name="ConversionFunctions"></a><span data-ttu-id="34011-208">Функции преобразования</span><span class="sxs-lookup"><span data-stu-id="34011-208">Conversion Functions</span></span>  
<span data-ttu-id="34011-209">Функции [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] можно использовать для преобразования поля из одного типа данных в другой тип данных.</span><span class="sxs-lookup"><span data-stu-id="34011-209">You can use [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] functions to convert a field from the one data type to a different data type.</span></span> <span data-ttu-id="34011-210">Функции преобразования могут использоваться, чтобы преобразовать тип данных по умолчанию для поля в тип данных, необходимый для вычислений или для объединения текста.</span><span class="sxs-lookup"><span data-stu-id="34011-210">Conversion functions can be used to convert the default data type for a field to the data type needed for calculations or to combine text.</span></span>  

-   <span data-ttu-id="34011-211">Следующее выражение преобразует константу 500 в тип Decimal для сравнения с денежным типом данных [!INCLUDE[tsql](../../includes/tsql-md.md)] в поле Value для выражения фильтра.</span><span class="sxs-lookup"><span data-stu-id="34011-211">The following expression converts the constant 500 to type Decimal in order to compare it to a [!INCLUDE[tsql](../../includes/tsql-md.md)] money data type in the Value field for a filter expression.</span></span>  

```  
=CDec(500)  
```  

-   <span data-ttu-id="34011-212">Следующее выражение отображает количество значений, выбранных для многозначного параметра *MySelection*.</span><span class="sxs-lookup"><span data-stu-id="34011-212">The following expression displays the number of values selected for the multivalue parameter *MySelection*.</span></span>  

```  
=CStr(Parameters!MySelection.Count)  
```  

####  <a name="decision-functions"></a><a name="DecisionFunctions"></a> <span data-ttu-id="34011-213">Функции выбора</span><span class="sxs-lookup"><span data-stu-id="34011-213">Decision Functions</span></span>  

-   <span data-ttu-id="34011-214">Функция `Iif` возвращает одно из двух значений в зависимости от того, истинно ли указанное выражение.</span><span class="sxs-lookup"><span data-stu-id="34011-214">The `Iif` function returns one of two values depending on whether the expression is true or not.</span></span> <span data-ttu-id="34011-215">В следующем выражении используется функция `Iif`, которая возвращает логическое значение `True`, если значение `LineTotal` превышает 100.</span><span class="sxs-lookup"><span data-stu-id="34011-215">The following expression uses the `Iif` function to return a Boolean value of `True` if the value of `LineTotal` exceeds 100.</span></span> <span data-ttu-id="34011-216">В противном случае возвращается значение `False`:</span><span class="sxs-lookup"><span data-stu-id="34011-216">Otherwise it returns `False`:</span></span>  

```  
=IIF(Fields!LineTotal.Value > 100, True, False)  
```  

-   <span data-ttu-id="34011-217">Следующее выражение использует несколько функций `IIF` (так называемые вложенные IIF), возвращая одно из трех значений в зависимости от значения поля `PctComplete`.</span><span class="sxs-lookup"><span data-stu-id="34011-217">Use multiple `IIF` functions (also known as "nested IIFs") to return one of three values depending on the value of `PctComplete`.</span></span> <span data-ttu-id="34011-218">Следующее выражение может быть помещено в свойство цвета заливки текстового поля, чтобы изменять цвета фона в зависимости от значения текстового поля.</span><span class="sxs-lookup"><span data-stu-id="34011-218">The following expression can be placed in the fill color of a text box to change the background color depending on the value in the text box.</span></span>  

```  
=IIF(Fields!PctComplete.Value >= 10, "Green", IIF(Fields!PctComplete.Value >= 1, "Blue", "Red"))  
```  

<span data-ttu-id="34011-219">Значения, большие или равные 10, отображаются с зеленым фоном, от 1 до 9 — с синим фоном, и меньшие 1 — с красным фоном.</span><span class="sxs-lookup"><span data-stu-id="34011-219">Values greater than or equal to 10 display with a green background, between 1 and 9 display with a blue background, and less than 1 display with a red background.</span></span>  

-   <span data-ttu-id="34011-220">Такого же эффекта можно добиться с помощью функции `Switch`.</span><span class="sxs-lookup"><span data-stu-id="34011-220">A different way to get the same functionality uses the `Switch` function.</span></span> <span data-ttu-id="34011-221">Функция `Switch` полезна при наличии трех и более проверяемых условий.</span><span class="sxs-lookup"><span data-stu-id="34011-221">The `Switch` function is useful when you have three or more conditions to test.</span></span> <span data-ttu-id="34011-222">Функция `Switch` возвращает значение, связанное с первым выражением ряда, которое оценивается как true:</span><span class="sxs-lookup"><span data-stu-id="34011-222">The `Switch` function returns the value associated with the first expression in a series that evaluates to true:</span></span>  

```  
=Switch(Fields!PctComplete.Value >= 10, "Green", Fields!PctComplete.Value >= 1, "Blue", Fields!PctComplete.Value = 1, "Yellow", Fields!PctComplete.Value <= 0, "Red",)  
```  

<span data-ttu-id="34011-223">Значения, больше или равные 10, отображаются с зеленым фоном, от 1 до 9 — с синим фоном, равные 1 — с желтым фоном и меньшие или равные 0 — с красным фоном.</span><span class="sxs-lookup"><span data-stu-id="34011-223">Values greater than or equal to 10 display with a green background, between 1 and 9 display with a blue background, equal to 1 display with a yellow background, and 0 or less display with a red background.</span></span>  

-   <span data-ttu-id="34011-224">Проверяет значение поля `ImportantDate` и возвращает строку «Red», если прошло больше недели, в ином случае — «Blue».</span><span class="sxs-lookup"><span data-stu-id="34011-224">Test the value of the `ImportantDate` field and return "Red" if it is more than a week old, and "Blue" otherwise.</span></span> <span data-ttu-id="34011-225">Это выражение позволяет управлять свойством Color текстового поля в элементе отчета.</span><span class="sxs-lookup"><span data-stu-id="34011-225">This expression can be used to control the Color property of a text box in a report item:</span></span>  

```  
=IIF(DateDiff("d",Fields!ImportantDate.Value, Now())>7,"Red","Blue")  
```  

-   <span data-ttu-id="34011-226">Проверяет значение поля `PhoneNumber` и возвращает строку «No Value», если это значение `null` (`Nothing` в [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]); в противном случае возвращает значение телефонного номера.</span><span class="sxs-lookup"><span data-stu-id="34011-226">Test the value of the `PhoneNumber` field and return "No Value" if it is `null` (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]); otherwise return the phone number value.</span></span> <span data-ttu-id="34011-227">Это выражение позволяет управлять содержимым текстового поля в элементе отчета.</span><span class="sxs-lookup"><span data-stu-id="34011-227">This expression can be used to control the value of a text box in a report item.</span></span>  

```  
=IIF(Fields!PhoneNumber.Value Is Nothing,"No Value",Fields!PhoneNumber.Value)  
```  

-   <span data-ttu-id="34011-228">Проверяет значение поля `Department` и возвращает либо имя вложенного отчета, либо значение `null` (`Nothing` в [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="34011-228">Test the value of the `Department` field and return either a subreport name or a `null` (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span></span> <span data-ttu-id="34011-229">Это выражение может использоваться для условной детализации вложенных отчетов.</span><span class="sxs-lookup"><span data-stu-id="34011-229">This expression can be used for conditional drillthrough subreports.</span></span>  

```  
=IIF(Fields!Department.Value = "Development", "EmployeeReport", Nothing)  
```  

-   <span data-ttu-id="34011-230">Проверяет, не является ли значением поля NULL.</span><span class="sxs-lookup"><span data-stu-id="34011-230">Test if a field value is null.</span></span> <span data-ttu-id="34011-231">Это выражение можно использовать для управления свойством `Hidden` элемента-изображения отчета.</span><span class="sxs-lookup"><span data-stu-id="34011-231">This expression can be used to control the `Hidden` property of an image report item.</span></span> <span data-ttu-id="34011-232">В следующем примере изображение, задаваемое полем [LargePhoto], отображается, только если значение поле не равно NULL.</span><span class="sxs-lookup"><span data-stu-id="34011-232">In the following example, the image specified by the field [LargePhoto] is displayed only if the value of the field is not null.</span></span>  

```  
=IIF(IsNothing(Fields!LargePhoto.Value),True,False)  
```  

-   <span data-ttu-id="34011-233">Функция `MonthName` возвращает значение типа String, содержащее название указанного месяца.</span><span class="sxs-lookup"><span data-stu-id="34011-233">The `MonthName` function returns a string value containing the name of the specified month.</span></span> <span data-ttu-id="34011-234">В следующем примере в поле «Месяц» указано Н/Д, если в поле содержится значение 0.</span><span class="sxs-lookup"><span data-stu-id="34011-234">The following example displays NA in the Month field when the field contains the value of 0.</span></span>  

```  
IIF(Fields!Month.Value=0,"NA",MonthName(IIF(Fields!Month.Value=0,1,Fields!Month.Value)))  

```  

###  <a name="report-functions"></a><a name="ReportFunctions"></a> <span data-ttu-id="34011-235">Функции отчета</span><span class="sxs-lookup"><span data-stu-id="34011-235">Report Functions</span></span>  
<span data-ttu-id="34011-236">В выражение можно добавить ссылку на дополнительные функции, которые позволяют управлять данными в отчете.</span><span class="sxs-lookup"><span data-stu-id="34011-236">In an expression, you can add a reference to additional report functions that manipulate data in a report.</span></span> <span data-ttu-id="34011-237">В этом разделе приведены примеры использования двух из этих функций.</span><span class="sxs-lookup"><span data-stu-id="34011-237">This section provides examples for two of these functions.</span></span> <span data-ttu-id="34011-238">Дополнительные сведения о функциях отчета и примеры см. в разделе [Справочник по агрегатным функциям (построитель отчетов и службы SSRS)](report-builder-functions-aggregate-functions-reference.md).</span><span class="sxs-lookup"><span data-stu-id="34011-238">For more information about report functions and examples, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md).</span></span>  

#####  <a name="sum"></a><a name="Sum"></a><span data-ttu-id="34011-239">Функции</span><span class="sxs-lookup"><span data-stu-id="34011-239">Sum</span></span>  

-   <span data-ttu-id="34011-240">Функция `Sum` суммирует значения в группе или области данных.</span><span class="sxs-lookup"><span data-stu-id="34011-240">The `Sum` function can total the values in a group or data region.</span></span> <span data-ttu-id="34011-241">Она может быть полезна в колонтитулах группы.</span><span class="sxs-lookup"><span data-stu-id="34011-241">This function can be useful in the header or footer of a group.</span></span> <span data-ttu-id="34011-242">Следующее выражение отображает сумму данных в группе или области данных Order.</span><span class="sxs-lookup"><span data-stu-id="34011-242">The following expression displays the sum of data in the Order group or data region:</span></span>  

```  
=Sum(Fields!LineTotal.Value, "Order")  
```  

-   <span data-ttu-id="34011-243">Функцию `Sum` можно также использоваться для вычислений условных статистических функций.</span><span class="sxs-lookup"><span data-stu-id="34011-243">You can also use the `Sum` function for conditional aggregate calculations.</span></span> <span data-ttu-id="34011-244">Например, если набор данных содержит поле State с возможными значениями «Not Started», «Started», «Finished», следующее значение, помещенное в верхний колонтитул группы, вычисляет статистическую сумму только для значения «Finished».</span><span class="sxs-lookup"><span data-stu-id="34011-244">For example, if a dataset has a field that is named State with possible values Not Started, Started, Finished, the following expression, when placed in a group header, calculates the aggregate sum for only the value Finished:</span></span>  

```  
=Sum(IIF(Fields!State.Value = "Finished", 1, 0))  
```  

#####  <a name="rownumber"></a><a name="RowNumber"></a><span data-ttu-id="34011-245">RowNumber</span><span class="sxs-lookup"><span data-stu-id="34011-245">RowNumber</span></span>  

-   <span data-ttu-id="34011-246">Если функция `RowNumber` используется в текстовом поле в области данных, то она отображает номер строки для каждого экземпляра текстового поля, в котором содержится это выражение.</span><span class="sxs-lookup"><span data-stu-id="34011-246">The `RowNumber` function, when used in a text box within a data region, displays the row number for each instance of the text box in which the expression appears.</span></span> <span data-ttu-id="34011-247">Эта функция может оказаться полезной для нумерации строк в таблице.</span><span class="sxs-lookup"><span data-stu-id="34011-247">This function can be useful to number rows in a table.</span></span> <span data-ttu-id="34011-248">Также она может быть полезна для более сложных задач, например для разбивки на страницы по определенному числу строк.</span><span class="sxs-lookup"><span data-stu-id="34011-248">It can also be useful for more complex tasks, such as providing page breaks based on number of rows.</span></span> <span data-ttu-id="34011-249">Дополнительные сведения см. в подразделе [Разрывы страниц](#PageBreaks) далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="34011-249">For more information, see [Page Breaks](#PageBreaks) in this topic.</span></span>  

<span data-ttu-id="34011-250">Область, указанная для элементов управления `RowNumber`, когда начинается перенумерация.</span><span class="sxs-lookup"><span data-stu-id="34011-250">The scope you specify for `RowNumber` controls when renumbering begins.</span></span> <span data-ttu-id="34011-251">Ключевое слово `Nothing` указывает, что функция начнет нумерацию строк с первой строки самой внешней области данных.</span><span class="sxs-lookup"><span data-stu-id="34011-251">The `Nothing` keyword indicates that the function will start counting at the first row in the outermost data region.</span></span> <span data-ttu-id="34011-252">Чтобы начать подсчет внутри вложенной области данных, используйте имя области данных.</span><span class="sxs-lookup"><span data-stu-id="34011-252">To start counting within nested data regions, use the name of the data region.</span></span> <span data-ttu-id="34011-253">Чтобы начать подсчет внутри группы, используйте имя группы.</span><span class="sxs-lookup"><span data-stu-id="34011-253">To start counting within a group, use the name of the group.</span></span>  

```  
=RowNumber(Nothing)  
```  

##  <a name="appearance-of-report-data"></a><a name="AppearanceofReportData"></a> <span data-ttu-id="34011-254">Внешний вид данных отчета</span><span class="sxs-lookup"><span data-stu-id="34011-254">Appearance of Report Data</span></span>  
<span data-ttu-id="34011-255">Выражения позволяют изменять внешний вид данных, отображаемых в отчете.</span><span class="sxs-lookup"><span data-stu-id="34011-255">You can use expressions to manipulate how data appears on a report.</span></span> <span data-ttu-id="34011-256">Например, можно отобразить значения двух полей в одном текстовом поле, вывести сведения об отчете или изменить порядок разбиения на страницы.</span><span class="sxs-lookup"><span data-stu-id="34011-256">For example, you can display the values of two fields in a single text box, display information about the report, or affect how page breaks are inserted in the report.</span></span>  

###  <a name="page-headers-and-footers"></a><a name="PageHeadersandFooters"></a><span data-ttu-id="34011-257">Верхние и нижние колонтитулы страницы</span><span class="sxs-lookup"><span data-stu-id="34011-257">Page Headers and Footers</span></span>  
<span data-ttu-id="34011-258">При конструировании отчета может понадобиться вывести в области нижнего колонтитула имя отчета и номер страницы.</span><span class="sxs-lookup"><span data-stu-id="34011-258">When designing a report, you may want to display the name of the report and page number in the report footer.</span></span> <span data-ttu-id="34011-259">Для этого воспользуйтесь следующими выражениями.</span><span class="sxs-lookup"><span data-stu-id="34011-259">To do this, you can use the following expressions:</span></span>  

-   <span data-ttu-id="34011-260">Следующее выражение выдает имя отчета и время его запуска.</span><span class="sxs-lookup"><span data-stu-id="34011-260">The following expression provides the name of the report and the time it was run.</span></span> <span data-ttu-id="34011-261">Его можно указать в текстовом поле в нижнем колонтитуле или в теле отчета.</span><span class="sxs-lookup"><span data-stu-id="34011-261">It can be placed in a text box in the report footer or in the body of the report.</span></span> <span data-ttu-id="34011-262">Время форматируется с помощью строки форматирования [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] для короткой даты:</span><span class="sxs-lookup"><span data-stu-id="34011-262">The time is formatted with the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] formatting string for short date:</span></span>  

```  
=Globals.ReportName & ", dated " & Format(Globals.ExecutionTime, "d")  
```  

-   <span data-ttu-id="34011-263">Следующее выражение, если его поместить в текстовое поле в нижнем колонтитуле отчета, выводит номер страницы и общее число страниц, содержащихся в отчете:</span><span class="sxs-lookup"><span data-stu-id="34011-263">The following expression, placed in a text box in the footer of a report, provides page number and total pages in the report:</span></span>  

```  
=Globals.PageNumber & " of " & Globals.TotalPages  
```  

<span data-ttu-id="34011-264">В следующих примерах показано, как вывести в верхнем колонтитуле страницы первое и последнее значение на странице, получив результат, похожий на список каталогов.</span><span class="sxs-lookup"><span data-stu-id="34011-264">The following examples describe how to display the first and last values from a page in the page header, similar to what you might find in a directory listing.</span></span> <span data-ttu-id="34011-265">Подразумевается, что в области данных существует текстовое поле `LastName`.</span><span class="sxs-lookup"><span data-stu-id="34011-265">The example assumes a data region that contains a text box named `LastName`.</span></span>  

-   <span data-ttu-id="34011-266">Следующее выражение, помещенное в текстовое поле в левой части верхнего колонтитула, выводит первое значение текстового поля `LastName` на этой странице.</span><span class="sxs-lookup"><span data-stu-id="34011-266">The following expression, placed in a text box on the left side of the page header, provides the first value of the `LastName` text box on the page:</span></span>  

```  
=First(ReportItems("LastName").Value)  
```  

-   <span data-ttu-id="34011-267">Следующее выражение, помещенное в текстовое поле в правой части верхнего колонтитула, выводит последнее значение текстового поля `LastName` на этой странице.</span><span class="sxs-lookup"><span data-stu-id="34011-267">The following expression, placed in a text box on the right side of the page header, provides the last value of the `LastName` text box on the page:</span></span>  

```  
=Last(ReportItems("LastName").Value)  
```  

<span data-ttu-id="34011-268">В следующем примере показано, как отобразить общее количество страниц.</span><span class="sxs-lookup"><span data-stu-id="34011-268">The following example describes how to display a page total.</span></span> <span data-ttu-id="34011-269">Подразумевается, что в области данных существует текстовое поле `Cost`.</span><span class="sxs-lookup"><span data-stu-id="34011-269">The example assumes a data region that contains a text box named `Cost`.</span></span>  

-   <span data-ttu-id="34011-270">Следующее выражение, помещенное в верхний или нижний колонтитул, выводит сумму значений в текстовом поле `Cost` для данной страницы.</span><span class="sxs-lookup"><span data-stu-id="34011-270">The following expression, placed in the page header or footer, provides the sum of the values in the `Cost` text box for the page:</span></span>  

```  
=Sum(ReportItems("Cost").Value)  
```  

> [!NOTE]  
>  <span data-ttu-id="34011-271">При ссылке из колонтитула в выражении может быть указан только один элемент отчета.</span><span class="sxs-lookup"><span data-stu-id="34011-271">You can refer to only one report item per expression in a page header or footer.</span></span> <span data-ttu-id="34011-272">Кроме того, в выражениях верхнего и нижнего колонтитулов можно ссылаться на имя текстового поля, но не использовать выражение фактических данных в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="34011-272">Also, you can refer to the text box name, but not the actual data expression within the text box, in page header and footer expressions.</span></span>  

###  <a name="page-breaks"></a><a name="PageBreaks"></a> <span data-ttu-id="34011-273">Разрывы страниц</span><span class="sxs-lookup"><span data-stu-id="34011-273">Page Breaks</span></span>  
<span data-ttu-id="34011-274">В некоторых отчетах может понадобиться возможность вставлять разрывы страниц после вывода указанного количества строк вместо или в дополнение к разрывам, вставляемым по группам или элементам отчета.</span><span class="sxs-lookup"><span data-stu-id="34011-274">In some reports, you may want to place a page break at the end of a specified number of rows instead of, or in addition to, on groups or report items.</span></span> <span data-ttu-id="34011-275">Для этого создайте группу, содержащую необходимые группы или записи сведений, добавьте к группе разрыв страницы, а затем добавьте выражение группы для группирования по указанному числу строк.</span><span class="sxs-lookup"><span data-stu-id="34011-275">To do this, create a group that contains the groups or detail records you want, add a page break to the group, and then add a group expression to group by a specified number of rows.</span></span>  

-   <span data-ttu-id="34011-276">Следующее выражение, будучи указанным в качестве выражения группы, назначает номер каждому набору из 25 строк.</span><span class="sxs-lookup"><span data-stu-id="34011-276">The following expression, when placed in the group expression, assigns a number to each set of 25 rows.</span></span> <span data-ttu-id="34011-277">Если для этой группы определен разрыв страницы, данное выражение будет выводить его через каждые 25 строк.</span><span class="sxs-lookup"><span data-stu-id="34011-277">When a page break is defined for the group, this expression results in a page break every 25 rows.</span></span>  

```  
=Ceiling(RowNumber(Nothing)/25)  
```  

<span data-ttu-id="34011-278">Чтобы позволить пользователю устанавливать значение числа строк на странице, создайте параметр с именем `RowsPerPage` и положите в основу выражения группы этот параметр, как показано в следующем выражении.</span><span class="sxs-lookup"><span data-stu-id="34011-278">To allow the user to set a value for the number of rows per page, create a parameter named `RowsPerPage` and base the group expression on the parameter, as shown in the following expression:</span></span>  

```  
=Ceiling(RowNumber(Nothing)/Parameters!RowsPerPage.Value)  
```  

<span data-ttu-id="34011-279">Дополнительные сведения об установке разрывов страниц см. в разделе [Добавление разрыва страницы (построитель отчетов и службы SSRS)](add-a-page-break-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="34011-279">For more information about setting page breaks for a group, see [Add a Page Break &#40;Report Builder and SSRS&#41;](add-a-page-break-report-builder-and-ssrs.md).</span></span>  

##  <a name="properties"></a><a name="Properties"></a> <span data-ttu-id="34011-280">Свойства</span><span class="sxs-lookup"><span data-stu-id="34011-280">Properties</span></span>  
<span data-ttu-id="34011-281">Выражения используются не только для отображения данных в текстовых полях.</span><span class="sxs-lookup"><span data-stu-id="34011-281">Expressions are not only used to display data in text boxes.</span></span> <span data-ttu-id="34011-282">С их помощью можно также менять свойства элементов отчета.</span><span class="sxs-lookup"><span data-stu-id="34011-282">They can also be used to change how properties are applied to report items.</span></span> <span data-ttu-id="34011-283">Можно изменить стиль данных или видимость элемента отчета.</span><span class="sxs-lookup"><span data-stu-id="34011-283">You can change style information for a report item, or change its visibility.</span></span>  

###  <a name="formatting"></a><a name="Formatting"></a><span data-ttu-id="34011-284">Форматирован</span><span class="sxs-lookup"><span data-stu-id="34011-284">Formatting</span></span>  

-   <span data-ttu-id="34011-285">Следующее выражение при использовании в свойстве Color текстового поля изменяет цвет текста в зависимости от значения поля `Profit` :</span><span class="sxs-lookup"><span data-stu-id="34011-285">The following expression, when used in the Color property of a text box, changes the color of the text depending on the value of the `Profit` field:</span></span>  

```  
=Iif(Fields!Profit.Value < 0, "Red", "Black")  
```  

<span data-ttu-id="34011-286">Можно также использовать объектную переменную [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] языка `Me`.</span><span class="sxs-lookup"><span data-stu-id="34011-286">You can also use the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] object variable `Me`.</span></span> <span data-ttu-id="34011-287">Эта переменная является другим способом сослаться на значение текстового поля.</span><span class="sxs-lookup"><span data-stu-id="34011-287">This variable is another way of referring to the value of a text box.</span></span>  

`=Iif(Me.Value < 0, "Red", "Black")`  

-   <span data-ttu-id="34011-288">При указании следующего выражения в свойстве BackgroundColor элемента отчета в области данных цвет фона каждой строки изменяется с бледно-зеленого до белого.</span><span class="sxs-lookup"><span data-stu-id="34011-288">The following expression, when used in the BackgroundColor property of a report item in a data region, alternates the background color of each row between pale green and white:</span></span>  

```  
=Iif(RowNumber(Nothing) Mod 2, "PaleGreen", "White")  
```  

<span data-ttu-id="34011-289">Возможно, что при использовании выражения для конкретной области понадобится указать набор данных для агрегатной функции:</span><span class="sxs-lookup"><span data-stu-id="34011-289">If you are using an expression for a specified scope, you may have to indicate the dataset for the aggregate function:</span></span>  

```  
=Iif(RowNumber("Employees") Mod 2, "PaleGreen", "White")  
```  

> [!NOTE]  
>  <span data-ttu-id="34011-290">Доступные цвета выбираются из перечисления KnownColor [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="34011-290">Available colors come from the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] KnownColor enumeration.</span></span>  

### <a name="chart-colors"></a><span data-ttu-id="34011-291">Цвета диаграммы</span><span class="sxs-lookup"><span data-stu-id="34011-291">Chart Colors</span></span>  
<span data-ttu-id="34011-292">Чтобы задать цвета в фигурной диаграмме, нужно с помощью пользовательского кода изменить порядок сопоставления цветов со значениями точек данных.</span><span class="sxs-lookup"><span data-stu-id="34011-292">To specify colors for a Shape chart, you can use custom code to control the order that colors are mapped to data point values.</span></span> <span data-ttu-id="34011-293">Это дает возможность использовать согласованные цвета в нескольких диаграммах, использующих одни и те же группы категорий.</span><span class="sxs-lookup"><span data-stu-id="34011-293">This helps you use consistent colors for multiple charts that have the same category groups.</span></span> <span data-ttu-id="34011-294">Дополнительные сведения см. в разделе [Указание согласованных цветов для нескольких фигурных диаграмм (построитель отчетов и службы SSRS)](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="34011-294">For more information, see [Specify Consistent Colors across Multiple Shape Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  

###  <a name="visibility"></a><a name="Visibility"></a><span data-ttu-id="34011-295">Доступности</span><span class="sxs-lookup"><span data-stu-id="34011-295">Visibility</span></span>  
<span data-ttu-id="34011-296">Изменяя значения свойства видимости, можно скрывать и отображать элементы отчета.</span><span class="sxs-lookup"><span data-stu-id="34011-296">You can show and hide items in a report using the visibility properties for the report item.</span></span> <span data-ttu-id="34011-297">В области данных (например, в таблице) можно в зависимости от значения выражения сделать некоторые из строк подробностей изначально невидимыми.</span><span class="sxs-lookup"><span data-stu-id="34011-297">In a data region such as a table, you can initially hide detail rows based on the value in an expression.</span></span>  

-   <span data-ttu-id="34011-298">Если указать следующее выражение для определения видимости строк сведений в группе, они отображаются только для продаж со значением более 90% в поле `PctQuota` .</span><span class="sxs-lookup"><span data-stu-id="34011-298">The following expression, when used for initial visibility of detail rows in a group, shows the detail rows for all sales exceeding 90 percent in the `PctQuota` field:</span></span>  

```  
=Iif(Fields!PctQuota.Value>.9, False, True)  
```  

-   <span data-ttu-id="34011-299">Если указать следующее выражение для свойства Hidden таблицы, то таблица будет показана, только если в ней больше 12 строк.</span><span class="sxs-lookup"><span data-stu-id="34011-299">The following expression, when set in the Hidden property of a table, shows the table only if it has more than 12 rows:</span></span>  

```  
=IIF(CountRows()>12,false,true)  
```  

-   <span data-ttu-id="34011-300">Следующее выражение, установленное в `Hidden` свойстве столбца, показывает столбец только в том случае, если поле существует в наборе данных отчета после извлечения данных из источника данных:</span><span class="sxs-lookup"><span data-stu-id="34011-300">The following expression, when set in the `Hidden` property of a column, shows the column only if the field exists in the report dataset after the data is retrieved from the data source:</span></span>  

```  
=IIF(Fields!Column_1.IsMissing, true, false)  
```  

###  <a name="urls"></a><a name="Hyperlinks"></a><span data-ttu-id="34011-301">Адрес</span><span class="sxs-lookup"><span data-stu-id="34011-301">URLs</span></span>  
<span data-ttu-id="34011-302">Можно настраивать URL-адреса с помощью данных отчета, а также управлять добавлением URL-адресов в качестве действий для текстового поля в зависимости от некоторых условий.</span><span class="sxs-lookup"><span data-stu-id="34011-302">You can customize URLs by using report data and also conditionally control whether URLs are added as an action for a text box.</span></span>  

-   <span data-ttu-id="34011-303">Следующее выражение, используемое как действие на текстовом поле, формирует настраиваемый URL-адрес, указывающий поле набора данных `EmployeeID` в качестве параметра URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="34011-303">The following expression, when used as an action on a text box, generates a customized URL that specifies the dataset field `EmployeeID` as a URL parameter.</span></span>  

```  
="http://adventure-works/MyInfo?ID=" & Fields!EmployeeID.Value  
```  

<span data-ttu-id="34011-304">Дополнительные сведения см. в разделе [Добавление гиперссылки на URL-адрес (построитель отчетов и службы SSRS)](add-a-hyperlink-to-a-url-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="34011-304">For more information, see [Add a Hyperlink to a URL &#40;Report Builder and SSRS&#41;](add-a-hyperlink-to-a-url-report-builder-and-ssrs.md).</span></span>  

-   <span data-ttu-id="34011-305">Следующее выражение в зависимости от определенных условий управляет добавлением URL-адреса в текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="34011-305">The following expression conditionally controls whether to add a URL in a text box.</span></span> <span data-ttu-id="34011-306">Это выражение зависит от параметра `IncludeURLs` , который позволяет пользователю решать, включать ли в отчет активные URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="34011-306">This expression depends on a parameter named `IncludeURLs` that allows a user to decide whether to include active URLs in a report.</span></span> <span data-ttu-id="34011-307">Это выражение установлено в качестве действия для текстового поля.</span><span class="sxs-lookup"><span data-stu-id="34011-307">This expression is set as an action on a text box.</span></span> <span data-ttu-id="34011-308">Установив параметр в значение False и просматривая затем отчет, можно экспортировать отчет Microsoft Excel без гиперссылок.</span><span class="sxs-lookup"><span data-stu-id="34011-308">By setting the parameter to False and then viewing the report, you can export the report Microsoft Excel without hyperlinks.</span></span>  

```  
=IIF(Parameters!IncludeURLs.Value,"http://adventure-works.com/productcatalog",Nothing)  
```  

##  <a name="report-data"></a><a name="ReportData"></a><span data-ttu-id="34011-309">Данные отчета</span><span class="sxs-lookup"><span data-stu-id="34011-309">Report Data</span></span>  
<span data-ttu-id="34011-310">С помощью выражений можно управлять данными отчета,</span><span class="sxs-lookup"><span data-stu-id="34011-310">Expressions can be used to manipulate the data that is used in the report.</span></span> <span data-ttu-id="34011-311">например параметрами и другими данными отчета.</span><span class="sxs-lookup"><span data-stu-id="34011-311">You can refer to parameters and other report information.</span></span> <span data-ttu-id="34011-312">Можно даже изменить запрос, используемый для получения данных при построении отчета.</span><span class="sxs-lookup"><span data-stu-id="34011-312">You can even change the query that is used to retrieve data for the report.</span></span>  

###  <a name="parameters"></a><a name="Parameters"></a> <span data-ttu-id="34011-313">Параметры</span><span class="sxs-lookup"><span data-stu-id="34011-313">Parameters</span></span>  
<span data-ttu-id="34011-314">В параметрах выражения используются для изменения их значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="34011-314">You can use expressions in a parameter to vary the default value for the parameter.</span></span> <span data-ttu-id="34011-315">Например, можно использовать параметр для фильтрации данных для конкретного пользователя на основе идентификатора пользователя, запускающего отчет.</span><span class="sxs-lookup"><span data-stu-id="34011-315">For example, you can use a parameter to filter data to a particular user based on the user ID that is used to run the report.</span></span>  

-   <span data-ttu-id="34011-316">Следующее выражение, при указании в качестве значения параметра по умолчанию, выбирает идентификатор пользователя, запустившего данный отчет:</span><span class="sxs-lookup"><span data-stu-id="34011-316">The following expression, when used as the default value for a parameter, collects the user ID of the person running the report:</span></span>  

```  
=User!UserID  
```  

-   <span data-ttu-id="34011-317">С помощью глобальной коллекции `Parameters` можно ссылаться на параметр в параметре запроса, критерий фильтра, текстовое поле или другие области отчета.</span><span class="sxs-lookup"><span data-stu-id="34011-317">To refer to a parameter in a query parameter, filter expression, text box, or other area of the report, use the `Parameters` global collection.</span></span> <span data-ttu-id="34011-318">В следующем примере подразумевается, что параметр имеет имя *Department*:</span><span class="sxs-lookup"><span data-stu-id="34011-318">This example assumes that the parameter is named *Department*:</span></span>  

```  
=Parameters!Department.Value  
```  

-   <span data-ttu-id="34011-319">Параметр может быть создан в отчете, но установлен как скрытый.</span><span class="sxs-lookup"><span data-stu-id="34011-319">Parameters can be created in a report but set to hidden.</span></span> <span data-ttu-id="34011-320">При выполнении отчета на сервере отчетов параметр не отображается на панели инструментов и читатель отчета не может изменить значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="34011-320">When the report runs on the report server, the parameter does not appear in the toolbar and the report reader cannot change the default value.</span></span> <span data-ttu-id="34011-321">Скрытый параметр можно использовать для установки значения по умолчанию в качестве пользовательской константы.</span><span class="sxs-lookup"><span data-stu-id="34011-321">You can use a hidden parameter set to a default value as custom constant.</span></span> <span data-ttu-id="34011-322">Это значение можно использовать в любом выражении, включая выражение поля.</span><span class="sxs-lookup"><span data-stu-id="34011-322">You can use this value in any expression, including a field expression.</span></span> <span data-ttu-id="34011-323">Следующее выражение идентифицирует поле, задаваемое значением параметра по умолчанию для параметра с именем *ParameterField*.</span><span class="sxs-lookup"><span data-stu-id="34011-323">The following expression identifies the field specified by the default parameter value for the parameter named *ParameterField*:</span></span>  

```  
=Fields(Parameters!ParameterField.Value).Value  
```  

## <a name="custom-code"></a><a name="CustomCode"></a><span data-ttu-id="34011-324">Пользовательский код</span><span class="sxs-lookup"><span data-stu-id="34011-324">Custom Code</span></span>

<span data-ttu-id="34011-325">В отчете можно использовать пользовательский код.</span><span class="sxs-lookup"><span data-stu-id="34011-325">You can use custom code in a report.</span></span> <span data-ttu-id="34011-326">Он либо внедряется в отчет, либо хранится в используемой отчетом пользовательской сборке.</span><span class="sxs-lookup"><span data-stu-id="34011-326">Custom code is either embedded in a report or stored in a custom assembly which is used in the report.</span></span> <span data-ttu-id="34011-327">Дополнительные сведения о пользовательском коде см. в разделе [Пользовательский код и ссылки на сборки в выражениях в конструкторе отчетов (службы SSRS)](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="34011-327">For more information about custom code, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  

### <a name="using-group-variables-for-custom-aggregation"></a><span data-ttu-id="34011-328">Использование групповых переменных для нестандартного статистического выражения</span><span class="sxs-lookup"><span data-stu-id="34011-328">Using Group Variables for Custom Aggregation</span></span>

<span data-ttu-id="34011-329">Можно инициализировать значение групповой переменной, которая является локальной в области определенной группы, а затем включать в выражения ссылку на эту переменную.</span><span class="sxs-lookup"><span data-stu-id="34011-329">You can initialize the value for a group variable that is local to a particular group scope and then include a reference to that variable in expressions.</span></span> <span data-ttu-id="34011-330">Одним из способов использования групповой переменной в пользовательском коде является реализация нестандартного статистического выражения.</span><span class="sxs-lookup"><span data-stu-id="34011-330">One of the ways that you can use a group variable with custom code is to implement a custom aggregate.</span></span> <span data-ttu-id="34011-331">Дополнительные сведения см. в разделе [Использование групповых переменных в службах Reporting Services 2008 для нестандартного статистического выражения](https://go.microsoft.com/fwlink/?LinkId=128714).</span><span class="sxs-lookup"><span data-stu-id="34011-331">For more information, see [Using Group Variables in Reporting Services 2008 for Custom Aggregation](https://go.microsoft.com/fwlink/?LinkId=128714).</span></span>  

<span data-ttu-id="34011-332">Дополнительные сведения о переменных см. в разделе [Ссылки на коллекции переменных отчета и группы (построитель отчетов и службы SSRS)](built-in-collections-report-and-group-variables-references-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="34011-332">For more information about variables, see [Report and Group Variables Collections References &#40;Report Builder and SSRS&#41;](built-in-collections-report-and-group-variables-references-report-builder.md).</span></span>  

## <a name="suppressing-null-or-zero-values-at-run-time"></a><span data-ttu-id="34011-333">Подавление значения NULL или нулевых значений во время выполнения</span><span class="sxs-lookup"><span data-stu-id="34011-333">Suppressing Null or Zero Values at Run Time</span></span>

<span data-ttu-id="34011-334">Во время обработки отчета результатом вычисления некоторых значений в выражении может быть NULL или значения могут быть неопределенными.</span><span class="sxs-lookup"><span data-stu-id="34011-334">Some values in an expression can evaluate to null or undefined at report processing time.</span></span> <span data-ttu-id="34011-335">Это может вызывать ошибки времени выполнения, которые приводят к отображению в текстовом поле значения **#Error** вместо вычисленного выражения.</span><span class="sxs-lookup"><span data-stu-id="34011-335">This can create run-time errors that result in **#Error** displaying in the text box instead of the evaluated expression.</span></span> <span data-ttu-id="34011-336">Функция `IIF` особенно чувствительна к такому поведению, так как, в отличие от инструкции If-Then-Else, каждая часть инструкции `IIF` оценивается (включая вызовы функций) перед передачей в подпрограмму, которая проверяет значения на равенство `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="34011-336">The `IIF` function is particularly sensitive to this behavior because, unlike an If-Then-Else statement, each part of the `IIF` statement is evaluated (including function calls) before being passed to the routine that tests for `true` or `false`.</span></span> <span data-ttu-id="34011-337">Инструкция `=IIF(Fields!Sales.Value is NOTHING, 0, Fields!Sales.Value)` формирует значение **#Error** в отчете, готовом для просмотра, если поле `Fields!Sales.Value` имеет значение NOTHING.</span><span class="sxs-lookup"><span data-stu-id="34011-337">The statement `=IIF(Fields!Sales.Value is NOTHING, 0, Fields!Sales.Value)` generates **#Error** in the rendered report if `Fields!Sales.Value` is NOTHING.</span></span>  

<span data-ttu-id="34011-338">Чтобы избежать этого состояния, используйте одну из следующих стратегий.</span><span class="sxs-lookup"><span data-stu-id="34011-338">To avoid this condition, use one of the following strategies:</span></span>  

-   <span data-ttu-id="34011-339">Установите числитель в 0, а знаменатель в 1, если значение поля B равно 0 или не определено; в противном случае установите в качестве числителя значение поля А, а в качестве знаменателя — значение поля B.</span><span class="sxs-lookup"><span data-stu-id="34011-339">Set the numerator to 0 and the denominator to 1 if the value for field B is 0 or undefined; otherwise, set the numerator to the value for field A and the denominator to the value for field B.</span></span>  

```  
=IIF(Field!B.Value=0, 0, Field!A.Value / IIF(Field!B.Value =0, 1, Field!B.Value))  
```  

-   <span data-ttu-id="34011-340">Используйте функцию пользовательского кода, чтобы вернуть значение выражения.</span><span class="sxs-lookup"><span data-stu-id="34011-340">Use a custom code function to return the value for the expression.</span></span> <span data-ttu-id="34011-341">В следующем примере возвращается процентная разница между текущим и предыдущим значениями.</span><span class="sxs-lookup"><span data-stu-id="34011-341">The following example returns the percentage difference between a current value and a previous value.</span></span> <span data-ttu-id="34011-342">Этот пример может использоваться для вычисления разницы между двумя последовательными значениями. В нем обрабатывается крайний случай первого сравнения (когда нет предыдущего значения) и случаи, когда либо предыдущее значение, либо текущее значение содержит `null` (`Nothing` в языке [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="34011-342">This can be used to calculate the difference between any two successive values and it handles the edge case of the first comparison (when there is no previous value) and cases whether either the previous value or the current value is `null` (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span></span>  

```  
Public Function GetDeltaPercentage(ByVal PreviousValue, ByVal CurrentValue) As Object  
     If IsNothing(PreviousValue) OR IsNothing(CurrentValue) Then  
          Return Nothing  
     Else if PreviousValue = 0 OR CurrentValue = 0 Then  
          Return Nothing  
     Else
          Return (CurrentValue - PreviousValue) / CurrentValue  
     End If  
End Function  
```  

<span data-ttu-id="34011-343">Следующее выражение показывает, как вызвать этот пользовательский код из текстового поля для контейнера ColumnGroupByYear (области данных или группы).</span><span class="sxs-lookup"><span data-stu-id="34011-343">The following expression shows how to call this custom code from a text box, for the "ColumnGroupByYear" container (group or data region).</span></span>  

```  
=Code.GetDeltaPercentage(Previous(Sum(Fields!Sales.Value),"ColumnGroupByYear"), Sum(Fields!Sales.Value))  
```  

<span data-ttu-id="34011-344">Это помогает избежать исключения во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="34011-344">This helps to avoid run-time exceptions.</span></span> <span data-ttu-id="34011-345">Для отображения в зависимости от определенных условий текста, основанного на значениях меньше или больше 0, можно использовать выражение, подобное `=IIF(Me.Value < 0, "red", "black")`, в свойстве `Color` текстового поля.</span><span class="sxs-lookup"><span data-stu-id="34011-345">You can now use an expression like `=IIF(Me.Value < 0, "red", "black")` in the `Color` property of the text box to conditionally the display text based on whether the values are greater than or less than 0.</span></span>  

## <a name="see-also"></a><span data-ttu-id="34011-346">См. также:</span><span class="sxs-lookup"><span data-stu-id="34011-346">See Also</span></span>

- [<span data-ttu-id="34011-347">Примеры уравнений фильтра (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="34011-347">Filter Equation Examples &#40;Report Builder and SSRS&#41;</span></span>](filter-equation-examples-report-builder-and-ssrs.md)
- [<span data-ttu-id="34011-348">Примеры выражений групп (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="34011-348">Group Expression Examples &#40;Report Builder and SSRS&#41;</span></span>](expression-examples-report-builder-and-ssrs.md)
- [<span data-ttu-id="34011-349">Использование выражений в отчетах (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="34011-349">Expression Uses in Reports &#40;Report Builder and SSRS&#41;</span></span>](expression-uses-in-reports-report-builder-and-ssrs.md)
- [<span data-ttu-id="34011-350">Выражения (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="34011-350">Expressions &#40;Report Builder and SSRS&#41;</span></span>](expressions-report-builder-and-ssrs.md)
- [<span data-ttu-id="34011-351">Часто используемые фильтры (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="34011-351">Commonly Used Filters &#40;Report Builder and SSRS&#41;</span></span>](commonly-used-filters-report-builder-and-ssrs.md)