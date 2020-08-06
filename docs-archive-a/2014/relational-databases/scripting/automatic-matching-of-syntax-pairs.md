---
title: Автоматическое сопоставление синтаксических пар
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- IntelliSense [SQL Server], delimiter highlighting
- IntelliSense [SQL Server], syntax pair matching
ms.assetid: bfc54cda-bfd6-4545-a5b9-f9db2ae13769
author: rothja
ms.author: jroth
ms.openlocfilehash: d1237eeb9aaec39e3210b00c880c0005ef3d95bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658176"
---
# <a name="automatic-matching-of-syntax-pairs"></a><span data-ttu-id="1f961-102">Автоматическое сопоставление синтаксических пар</span><span class="sxs-lookup"><span data-stu-id="1f961-102">Automatic Matching of Syntax Pairs</span></span>
  <span data-ttu-id="1f961-103">Автоматическая проверка соответствия синтаксических пар позволяет немедленно убедиться в том, что парные элементы синтаксиса в коде правильно объединены в пары.</span><span class="sxs-lookup"><span data-stu-id="1f961-103">Automatic matching of syntax pairs gives you immediate feedback on whether syntax elements that must be coded in pairs are correctly paired.</span></span> <span data-ttu-id="1f961-104">В редакторе запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] такая проверка называется «соответствием разделителей», в редакторе запросов XMLA служб Analysis Services — «соответствием фигурных скобок», а в редакторах многомерных выражений и расширений интеллектуального анализа данных — «соответствием круглых скобок».</span><span class="sxs-lookup"><span data-stu-id="1f961-104">This is known as delimiter matching in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor, brace matching in the Analysis Services XMLA Query Editor, and parenthesis matching in the MDX and DMX editors.</span></span>  
  
## <a name="database-engine-query-editor-delimiter-matching"></a><span data-ttu-id="1f961-105">Проверка соответствия разделителей в редакторе запросов к компоненту Database Engine</span><span class="sxs-lookup"><span data-stu-id="1f961-105">Database Engine Query Editor Delimiter Matching</span></span>  
 <span data-ttu-id="1f961-106">Редактор запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] проверяет соответствие разделителей, обозначающих границы блоков кода.</span><span class="sxs-lookup"><span data-stu-id="1f961-106">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor matches the delimiters that identify the boundaries of code blocks.</span></span> <span data-ttu-id="1f961-107">Проверка соответствия осуществляется двумя способами.</span><span class="sxs-lookup"><span data-stu-id="1f961-107">The matching is done in two ways:</span></span>  
  
-   <span data-ttu-id="1f961-108">Редактор выделяет оба разделителя, составляющих пару, в момент ввода второго из них.</span><span class="sxs-lookup"><span data-stu-id="1f961-108">The editor highlights both delimiters in a pair when you finish typing the second delimiter in the pair.</span></span>  
  
-   <span data-ttu-id="1f961-109">Когда курсор мыши оказывается над одним из разделителей, составляющих пару, с помощью сочетания клавиш CTRL + ] можно переместиться ко второму разделителю.</span><span class="sxs-lookup"><span data-stu-id="1f961-109">Anytime the cursor is in one of the delimiters in a pair, you can use the CTRL+] keyboard shortcut to jump to the matching delimiter.</span></span>  
  
### <a name="delimiter-pairs"></a><span data-ttu-id="1f961-110">Пары разделителей</span><span class="sxs-lookup"><span data-stu-id="1f961-110">Delimiter Pairs</span></span>  
 <span data-ttu-id="1f961-111">Автоматическая проверка соответствия разделителей распознает следующие наборы разделителей.</span><span class="sxs-lookup"><span data-stu-id="1f961-111">Automatic delimiter matching recognizes the following sets of delimiters:</span></span>  
  
|<span data-ttu-id="1f961-112">Открывающий разделитель</span><span class="sxs-lookup"><span data-stu-id="1f961-112">Lead Delimiter</span></span>|<span data-ttu-id="1f961-113">Закрывающий разделитель</span><span class="sxs-lookup"><span data-stu-id="1f961-113">Closing Delimiter</span></span>|  
|--------------------|-----------------------|  
|<span data-ttu-id="1f961-114">**(**</span><span class="sxs-lookup"><span data-stu-id="1f961-114">**(**</span></span>|<span data-ttu-id="1f961-115">**)**</span><span class="sxs-lookup"><span data-stu-id="1f961-115">**)**</span></span>|  
|<span data-ttu-id="1f961-116">**BEGIN**</span><span class="sxs-lookup"><span data-stu-id="1f961-116">**BEGIN**</span></span>|<span data-ttu-id="1f961-117">**END**</span><span class="sxs-lookup"><span data-stu-id="1f961-117">**END**</span></span>|  
|<span data-ttu-id="1f961-118">**BEGIN TRY**</span><span class="sxs-lookup"><span data-stu-id="1f961-118">**BEGIN TRY**</span></span>|<span data-ttu-id="1f961-119">**END TRY**</span><span class="sxs-lookup"><span data-stu-id="1f961-119">**END TRY**</span></span>|  
|<span data-ttu-id="1f961-120">**BEGIN CATCH**</span><span class="sxs-lookup"><span data-stu-id="1f961-120">**BEGIN CATCH**</span></span>|<span data-ttu-id="1f961-121">**END CATCH**</span><span class="sxs-lookup"><span data-stu-id="1f961-121">**END CATCH**</span></span>|  
  
 <span data-ttu-id="1f961-122">Автоматическая проверка соответствия разделителей не распознает разделители идентификаторов в скобках ([ObjectName]) или в кавычках ("ObjectName").</span><span class="sxs-lookup"><span data-stu-id="1f961-122">Automatic delimiter matching does not recognize the delimiters for bracketed identifiers ([ObjectName]), or quoted identifiers ("ObjectName").</span></span> <span data-ttu-id="1f961-123">Проверка соответствия пар не сопоставляет одиночные кавычки-разделители для строковых литералов ('string'), поскольку выделение цветом само по себе обеспечивает визуальное отображение строкового значения.</span><span class="sxs-lookup"><span data-stu-id="1f961-123">Pair matching does not match the single quotation delimiters for string literals ('string') because color coding already gives a visual indication of whether the string has been delimited.</span></span>  
  
### <a name="delimiter-highlighting"></a><span data-ttu-id="1f961-124">Выделение разделителей цветом</span><span class="sxs-lookup"><span data-stu-id="1f961-124">Delimiter Highlighting</span></span>  
 <span data-ttu-id="1f961-125">При проверке соответствия выделяются одновременно открывающий и закрывающий элемент пары разделителей.</span><span class="sxs-lookup"><span data-stu-id="1f961-125">Matching highlights both the lead and closing element of a pair of delimiters.</span></span> <span data-ttu-id="1f961-126">Это позволяет визуально отделить блоки кода и проверить наличие неполных пар.</span><span class="sxs-lookup"><span data-stu-id="1f961-126">This lets you visually identify code blocks and check for mismatched pairs of delimiters.</span></span>  
  
 <span data-ttu-id="1f961-127">Разделители выделяются при вводе последнего символа, завершающего пару.</span><span class="sxs-lookup"><span data-stu-id="1f961-127">Delimiters are highlighted when you type the final letter that completes the pair.</span></span> <span data-ttu-id="1f961-128">Например, когда после разделителя BEGIN вводится разделитель END, то выделение включается после ввода последней буквы в разделителе END.</span><span class="sxs-lookup"><span data-stu-id="1f961-128">For example, for a BEGIN END pair where you type BEGIN first followed by END, highlighting turns on when you type the final letter in END.</span></span> <span data-ttu-id="1f961-129">Чтобы включить выделение, не обязательно вводить сначала открывающий разделитель, а затем закрывающий.</span><span class="sxs-lookup"><span data-stu-id="1f961-129">You do not have to type the lead delimiter followed by the closing delimiter to turn on highlighting.</span></span> <span data-ttu-id="1f961-130">Если ввести сначала закрывающий разделитель END, пролистать скрипт назад и ввести открывающий разделитель BEGIN, то выделение будет включено после ввода последней буквы в разделителе BEGIN.</span><span class="sxs-lookup"><span data-stu-id="1f961-130">If you type END first, then scroll back up the script and type BEGIN, highlighting is turned on when you type the final letter in BEGIN.</span></span> <span data-ttu-id="1f961-131">Последняя набранная буква не обязательно должна быть последней буквой разделителя.</span><span class="sxs-lookup"><span data-stu-id="1f961-131">The final letter typed does not have to be the end letter in the delimiter.</span></span> <span data-ttu-id="1f961-132">Например, если открывающий разделитель был ошибочно введен как BEIN вместо BEGIN, то пара разделителей BEGIN END будет выделена при вставке буквы G.</span><span class="sxs-lookup"><span data-stu-id="1f961-132">For example, you could misspell BEGIN as BEIN, when you insert the final G the BEGIN END pair is highlighted.</span></span>  
  
 <span data-ttu-id="1f961-133">Пара разделителей остается выделенной до тех пор, пока курсор мыши не будет перемещен в другое место.</span><span class="sxs-lookup"><span data-stu-id="1f961-133">The delimiter pair remains highlighted until you move the cursor.</span></span> <span data-ttu-id="1f961-134">Выделение отключается при перемещении курсора мыши даже в том случае, если новое положение курсора находится в пределах того же разделителя.</span><span class="sxs-lookup"><span data-stu-id="1f961-134">The highlighting is turned off when the cursor is moved, even if the new cursor position remains in the same delimiter.</span></span> <span data-ttu-id="1f961-135">Выделение можно включить повторно, удалив и заново введя любую букву в любом из разделителей, составляющих пару.</span><span class="sxs-lookup"><span data-stu-id="1f961-135">You can turn the highlighting back on by deleting and retyping any letter in either member of the pair.</span></span>  
  
## <a name="analysis-services-xmla-query-editor-brace-matching"></a><span data-ttu-id="1f961-136">Проверка соответствия фигурных скобок в редакторе запросов XMLA служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="1f961-136">Analysis Services XMLA Query Editor Brace Matching</span></span>  
 <span data-ttu-id="1f961-137">Проверка соответствия фигурных скобок в редакторе запросов XMLA позволяет убедиться в том, все ли элементы закрыты, с помощью выделения открывающих и закрывающих фигурных скобок.</span><span class="sxs-lookup"><span data-stu-id="1f961-137">The XMLA Query Editor brace matching shows if you have closed elements by highlighting opening and closing braces.</span></span> <span data-ttu-id="1f961-138">Можно также по сочетанию клавиш CTRL + ] перемещаться от одной фигурной скобки из пары ко второй.</span><span class="sxs-lookup"><span data-stu-id="1f961-138">You can also use the CTRL+] keyboard shortcut to jump from one brace to the matching brace.</span></span>  
  
 <span data-ttu-id="1f961-139">Редактор запросов XMLA осуществляет проверку соответствия фигурных скобок для следующих элементов.</span><span class="sxs-lookup"><span data-stu-id="1f961-139">The XMLA Query Editor does brace matching for the following terms:</span></span>  
  
-   <span data-ttu-id="1f961-140">Совпадающие открывающий и закрывающий теги.</span><span class="sxs-lookup"><span data-stu-id="1f961-140">Matching start and end tags.</span></span>  
  
-   <span data-ttu-id="1f961-141">Любая пара \<" and "> угловых скобок "".</span><span class="sxs-lookup"><span data-stu-id="1f961-141">Any pair of "\<" and ">" angle brackets.</span></span>  
  
-   <span data-ttu-id="1f961-142">Начало и конец комментария.</span><span class="sxs-lookup"><span data-stu-id="1f961-142">Start and end of comments.</span></span>  
  
-   <span data-ttu-id="1f961-143">Начало и конец инструкций по обработке.</span><span class="sxs-lookup"><span data-stu-id="1f961-143">Start and end of processing instructions.</span></span>  
  
-   <span data-ttu-id="1f961-144">Начало и конец блока CDATA.</span><span class="sxs-lookup"><span data-stu-id="1f961-144">Start and end of CDATA blocks.</span></span>  
  
-   <span data-ttu-id="1f961-145">Начало и конец DTD-декларации.</span><span class="sxs-lookup"><span data-stu-id="1f961-145">Start and end of DTD declarations.</span></span>  
  
-   <span data-ttu-id="1f961-146">Открывающие и закрывающие кавычки атрибутов.</span><span class="sxs-lookup"><span data-stu-id="1f961-146">Opening and closing quotes on attributes.</span></span>  
  
## <a name="mdx-and-dmx-editor-parenthesis-matching"></a><span data-ttu-id="1f961-147">Проверка соответствия круглых скобок в редакторах многомерных выражений и расширений интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="1f961-147">MDX and DMX Editor Parenthesis Matching</span></span>  
 <span data-ttu-id="1f961-148">Редакторы многомерных выражений и выражений интеллектуального анализа данных автоматически выполняют проверку соответствия пар круглых скобок в функциях.</span><span class="sxs-lookup"><span data-stu-id="1f961-148">The Multi-Dimensional Expressions (MDX) and Data Mining Expressions (DMX) Editors automatically match parenthesis pairs in functions.</span></span>  
  
  
