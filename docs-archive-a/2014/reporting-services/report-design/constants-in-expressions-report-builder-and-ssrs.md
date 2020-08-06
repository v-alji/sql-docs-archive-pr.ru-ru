---
title: Константы в выражениях (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b8ae650b-0f46-4848-b62b-15f8a40751b8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d95005a04482cb03d3bb3860aea695c7e7969255
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658159"
---
# <a name="constants-in-expressions-report-builder-and-ssrs"></a><span data-ttu-id="21071-102">Константы в выражениях (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="21071-102">Constants in Expressions (Report Builder and SSRS)</span></span>
  <span data-ttu-id="21071-103">Константа состоит из литерального текста или предопределенного текста.</span><span class="sxs-lookup"><span data-stu-id="21071-103">A constant consists of literal text or predefined text.</span></span> <span data-ttu-id="21071-104">Обработчик отчетов имеет доступ к стандартным константам, поэтому при включении их в выражения значения, которые они представляют, заменяются в выражении до его оценки.</span><span class="sxs-lookup"><span data-stu-id="21071-104">The report processor has access to predefined constants so that when you include them in an expression, the values they represent are substituted in the expression before it is evaluated.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="literal-text"></a><span data-ttu-id="21071-105">Литеральный текст</span><span class="sxs-lookup"><span data-stu-id="21071-105">Literal Text</span></span>  
 <span data-ttu-id="21071-106">В выражении литеральным текстом является текст, заключенный в двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="21071-106">In an expression, literal text is text that is in double quotation marks.</span></span> <span data-ttu-id="21071-107">Можно также ввести текст непосредственно в текстовое поле без двойных кавычек, если он не является частью выражения.</span><span class="sxs-lookup"><span data-stu-id="21071-107">You can also type text directly into a text box without double quotation marks if it is not part of an expression.</span></span> <span data-ttu-id="21071-108">Если значение текстового поля не начинается со знака равенства (=), текст рассматривается как литеральный.</span><span class="sxs-lookup"><span data-stu-id="21071-108">If the text box value does not begin with an equal sign (=), the text is treated as literal text.</span></span> <span data-ttu-id="21071-109">В следующей таблице показано несколько примеров литерального текста в выражении.</span><span class="sxs-lookup"><span data-stu-id="21071-109">The following table shows several examples of literal text in an expression.</span></span>  
  
|<span data-ttu-id="21071-110">Постоянно</span><span class="sxs-lookup"><span data-stu-id="21071-110">Constant</span></span>|<span data-ttu-id="21071-111">Отображаемый текст</span><span class="sxs-lookup"><span data-stu-id="21071-111">Display text</span></span>|<span data-ttu-id="21071-112">Текст выражения</span><span class="sxs-lookup"><span data-stu-id="21071-112">Expression text</span></span>|  
|--------------|------------------|---------------------|  
|<span data-ttu-id="21071-113">Report run at:</span><span class="sxs-lookup"><span data-stu-id="21071-113">Report run at:</span></span>|<\<Expr>>|`="Report run at: " & Globals!ExecutionTime`|  
|<span data-ttu-id="21071-114">Компания Adventure Works Cycles</span><span class="sxs-lookup"><span data-stu-id="21071-114">Adventure Works Cycles</span></span>|<span data-ttu-id="21071-115">Компания Adventure Works Cycles</span><span class="sxs-lookup"><span data-stu-id="21071-115">Adventure Works Cycles</span></span>|<span data-ttu-id="21071-116">Компания Adventure Works Cycles</span><span class="sxs-lookup"><span data-stu-id="21071-116">Adventure Works Cycles</span></span>|  
|<span data-ttu-id="21071-117">[Заключенный в скобки отображаемый текст]</span><span class="sxs-lookup"><span data-stu-id="21071-117">[Bracketed display text]</span></span>|<span data-ttu-id="21071-118">\\[Заключенный в скобки отображаемый текст\\]</span><span class="sxs-lookup"><span data-stu-id="21071-118">\\[Bracketed display text\\]</span></span>|<span data-ttu-id="21071-119">[Заключенный в скобки отображаемый текст]</span><span class="sxs-lookup"><span data-stu-id="21071-119">[Bracketed display text]</span></span>|  
  
## <a name="rdl-constants"></a><span data-ttu-id="21071-120">Константы языка определения отчетов</span><span class="sxs-lookup"><span data-stu-id="21071-120">RDL Constants</span></span>  
 <span data-ttu-id="21071-121">В выражении можно использовать константы, определенные в языке определения отчетов.</span><span class="sxs-lookup"><span data-stu-id="21071-121">You can use constants defined in Report Definition Language (RDL) in an expression.</span></span> <span data-ttu-id="21071-122">В диалоговом окне **Выражение** константы появляются при создании выражения для свойства отчета, которое принимает только некоторые допустимые значения, известные также как перечислимые типы.</span><span class="sxs-lookup"><span data-stu-id="21071-122">In the **Expression** dialog box, constants appear when you create an expression for a report property that only accepts certain valid values, also known as enumerated types.</span></span> <span data-ttu-id="21071-123">В следующей таблице показаны два примера.</span><span class="sxs-lookup"><span data-stu-id="21071-123">The following table shows two examples.</span></span>  
  
|<span data-ttu-id="21071-124">Свойство</span><span class="sxs-lookup"><span data-stu-id="21071-124">Property</span></span>|<span data-ttu-id="21071-125">Описание</span><span class="sxs-lookup"><span data-stu-id="21071-125">Description</span></span>|<span data-ttu-id="21071-126">Значения</span><span class="sxs-lookup"><span data-stu-id="21071-126">Values</span></span>|  
|--------------|-----------------|------------|  
|<span data-ttu-id="21071-127">TextAlign</span><span class="sxs-lookup"><span data-stu-id="21071-127">TextAlign</span></span>|<span data-ttu-id="21071-128">Допустимые значения для выравнивания текста в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="21071-128">Valid values for aligning text in a text box.</span></span>|<span data-ttu-id="21071-129">General, Left, Center, Right</span><span class="sxs-lookup"><span data-stu-id="21071-129">General, Left, Center, Right</span></span>|  
|<span data-ttu-id="21071-130">BorderStyle</span><span class="sxs-lookup"><span data-stu-id="21071-130">BorderStyle</span></span>|<span data-ttu-id="21071-131">Допустимые значения для линии, добавляемой в отчет.</span><span class="sxs-lookup"><span data-stu-id="21071-131">Valid values for a line added to a report.</span></span>|<span data-ttu-id="21071-132">Default, None, Dotted, Dashed, Solid, Double, DashDot, DashDotdot</span><span class="sxs-lookup"><span data-stu-id="21071-132">Default, None, Dotted, Dashed, Solid, Double, DashDot, DashDotdot</span></span>|  
  
## <a name="visual-basic-constants"></a><span data-ttu-id="21071-133">Константы языка Visual Basic</span><span class="sxs-lookup"><span data-stu-id="21071-133">Visual Basic Constants</span></span>  
 <span data-ttu-id="21071-134">В выражении можно использовать константы, определенные в библиотеке времени выполнения [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="21071-134">You can use constants defined in the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] run-time library in an expression.</span></span> <span data-ttu-id="21071-135">Например, можно использовать константу `DateInterval.Day`.</span><span class="sxs-lookup"><span data-stu-id="21071-135">For example, you can use the constant `DateInterval.Day`.</span></span> <span data-ttu-id="21071-136">Следующее выражение возвращает число 10 для даты 10 января 2008 г.</span><span class="sxs-lookup"><span data-stu-id="21071-136">The following expression for the date January 10, 2008 returns the number 10:</span></span>  
  
 `=DatePart("d",Globals!ExecutionTime)`  
  
## <a name="clr-constants"></a><span data-ttu-id="21071-137">Константы среды CLR</span><span class="sxs-lookup"><span data-stu-id="21071-137">CLR Constants</span></span>  
 <span data-ttu-id="21071-138">В выражении можно использовать константы, определенные в классах среды CLR [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="21071-138">You can use constants defined in [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] common language run-time (CLR) classes in an expression.</span></span> <span data-ttu-id="21071-139">В следующей таблице показан пример определенного системой цвета.</span><span class="sxs-lookup"><span data-stu-id="21071-139">The following table shows an example of a system-defined color.</span></span>  
  
|<span data-ttu-id="21071-140">Константа</span><span class="sxs-lookup"><span data-stu-id="21071-140">Constant</span></span>|<span data-ttu-id="21071-141">Описание</span><span class="sxs-lookup"><span data-stu-id="21071-141">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="21071-142">MistyRose</span><span class="sxs-lookup"><span data-stu-id="21071-142">MistyRose</span></span>|<span data-ttu-id="21071-143">При создании выражения для свойства отчета, основанного на цвете фона, можно указать цвет по имени.</span><span class="sxs-lookup"><span data-stu-id="21071-143">When you create an expression for a report property that is based on background color, you can specify a color by name.</span></span> <span data-ttu-id="21071-144">Допустимые имена перечислены в диалоговом окне **Выражение** .</span><span class="sxs-lookup"><span data-stu-id="21071-144">Valid names are listed in the **Expression** dialog box.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="21071-145">См. также:</span><span class="sxs-lookup"><span data-stu-id="21071-145">See Also</span></span>  
 <span data-ttu-id="21071-146">[Диалоговое окно «выражение»](../expression-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="21071-146">[Expression Dialog Box](../expression-dialog-box.md) </span></span>  
 <span data-ttu-id="21071-147">[Выражения (построитель отчетов и службы SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="21071-147">[Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="21071-148">[Примеры выражений (построитель отчетов и службы SSRS)](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="21071-148">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="21071-149">[Типы данных в выражениях &#40;построитель отчетов и SSRS&#41;](data-types-in-expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="21071-149">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](data-types-in-expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="21071-150">Диалоговое окно "Выражение" (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="21071-150">Expression Dialog Box &#40;Report Builder&#41;</span></span>](../expression-dialog-box-report-builder.md)  
  
  
