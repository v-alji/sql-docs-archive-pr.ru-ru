---
title: Добавление выражения (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a60ee091-b4ed-41e1-9b6a-032c316cd03f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 16f414bfad47ae92681de50eb576a6ac2cb3f5fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729054"
---
# <a name="add-an-expression-report-builder-and-ssrs"></a><span data-ttu-id="5fe79-102">Добавление выражения (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="5fe79-102">Add an Expression (Report Builder and SSRS)</span></span>
  <span data-ttu-id="5fe79-103">Выражения используются в отчете для определения свойств элементов отчета, фильтров, групп, порядка сортировки, строк подключения и значений параметров.</span><span class="sxs-lookup"><span data-stu-id="5fe79-103">Expressions are used throughout a report for defining report item properties, filters, groups, sort order, connection strings, and parameter values.</span></span> <span data-ttu-id="5fe79-104">Выражения начинаются со знака равенства (=) и создаются в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5fe79-104">Expressions begin with an equal sign (=) and are written in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span></span> <span data-ttu-id="5fe79-105">Во время выполнения отчета обработчик отчета вычисляет их и применяет результат вычисления к элементам макета отчета.</span><span class="sxs-lookup"><span data-stu-id="5fe79-105">They are evaluated at run time by the report processor, which combines the evaluation result with report layout elements.</span></span>  
  
 <span data-ttu-id="5fe79-106">Выражения бывают простыми и сложными.</span><span class="sxs-lookup"><span data-stu-id="5fe79-106">Expressions can be simple or complex.</span></span> <span data-ttu-id="5fe79-107">Простое выражение ссылается на один элемент встроенной коллекции.</span><span class="sxs-lookup"><span data-stu-id="5fe79-107">Simple expression refer to a single item in a built-in collection.</span></span> <span data-ttu-id="5fe79-108">Сложные выражения могут содержать константы, операторы, глобальные элементы сбора и вызовы функций.</span><span class="sxs-lookup"><span data-stu-id="5fe79-108">Complex expressions can contain constants, operators, global collection items, and function calls.</span></span> <span data-ttu-id="5fe79-109">Дополнительные сведения см. в разделе [Выражения (построитель отчетов и службы SSRS)](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="5fe79-109">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-an-expression-to-a-text-box"></a><span data-ttu-id="5fe79-110">Добавление выражения в текстовое поле</span><span class="sxs-lookup"><span data-stu-id="5fe79-110">To add an expression to a text box</span></span>  
  
-   <span data-ttu-id="5fe79-111">В режиме **Конструктор** щелкните текстовое поле в области конструктора, в которое нужно добавить выражение.</span><span class="sxs-lookup"><span data-stu-id="5fe79-111">In **Design** view, click the text box on the design surface to which you want to add an expression.</span></span>  
  
    -   <span data-ttu-id="5fe79-112">В случае простого выражения введите текст выражения в текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="5fe79-112">For a simple expression, type the display text for the expression in the text box.</span></span> <span data-ttu-id="5fe79-113">Например, для поля набора данных «Sales» введите `[Sales]`.</span><span class="sxs-lookup"><span data-stu-id="5fe79-113">For example, for the dataset field Sales, type `[Sales]`.</span></span>  
  
    -   <span data-ttu-id="5fe79-114">В случае сложного выражения щелкните правой кнопкой мыши текстовое поле и выберите **Выражение**.</span><span class="sxs-lookup"><span data-stu-id="5fe79-114">For a complex expression, right-click the text box, and select **Expression**.</span></span> <span data-ttu-id="5fe79-115">Откроется диалоговое окно **Выражение** .</span><span class="sxs-lookup"><span data-stu-id="5fe79-115">The **Expression** dialog box opens.</span></span> <span data-ttu-id="5fe79-116">Введите или интерактивно создайте нужное выражение после знака равенства «=» в панели выражений, а затем нажмите кнопку «ОК».</span><span class="sxs-lookup"><span data-stu-id="5fe79-116">Type or interactively create your expression after the '=' in the expression pane, and then click OK.</span></span>  
  
         <span data-ttu-id="5fe79-117">Выражение появится в области конструктора в следующем виде: `<<Expr>>`.</span><span class="sxs-lookup"><span data-stu-id="5fe79-117">The expression appears on the design surface as `<<Expr>>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fe79-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="5fe79-118">See Also</span></span>  
 <span data-ttu-id="5fe79-119">[Форматирование текста и заполнителей (построитель отчетов и службы SSRS)](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5fe79-119">[Formatting Text and Placeholders &#40;Report Builder and SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5fe79-120">[Текстовые поля (построитель отчетов и службы SSRS)](text-boxes-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5fe79-120">[Text Boxes &#40;Report Builder and SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5fe79-121">[Использование выражений в отчетах (построитель отчетов и службы SSRS)](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5fe79-121">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5fe79-122">[Примеры уравнений фильтра (построитель отчетов и службы SSRS)](filter-equation-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5fe79-122">[Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5fe79-123">[Примеры выражений групп &#40;построитель отчетов и службы SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5fe79-123">[Group Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5fe79-124">[Диалоговое окно "Выражение" (построитель отчетов)](../expression-dialog-box-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="5fe79-124">[Expression Dialog Box &#40;Report Builder&#41;](../expression-dialog-box-report-builder.md) </span></span>  
 <span data-ttu-id="5fe79-125">[Примеры выражений (построитель отчетов и службы SSRS)](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5fe79-125">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="5fe79-126">Добавление кода в отчет (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="5fe79-126">Add Code to a Report &#40;SSRS&#41;</span></span>](add-code-to-a-report-ssrs.md)  
  
  
