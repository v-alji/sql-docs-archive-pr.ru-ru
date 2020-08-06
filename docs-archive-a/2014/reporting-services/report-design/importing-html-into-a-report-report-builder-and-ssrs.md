---
title: Импорт HTML в отчет (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: dd0410ea-8839-4e8c-9944-8cdfe5465591
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4f978e67c67556184012db6b809e4f5754f2374c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730174"
---
# <a name="importing-html-into-a-report-report-builder-and-ssrs"></a><span data-ttu-id="b0075-102">Импорт HTML в отчет (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="b0075-102">Importing HTML into a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="b0075-103">Текстовое поле можно использовать для вставки в отчет текста в формате HTML, выбранного из поля набора данных.</span><span class="sxs-lookup"><span data-stu-id="b0075-103">You can use a text box to insert HTML-formatted text that you have retrieved from a field in your dataset into a report.</span></span> <span data-ttu-id="b0075-104">Этот текст может исходить из любого простого или сложного выражения, обработка которого приводит к получению правильно отформатированного кода HTML.</span><span class="sxs-lookup"><span data-stu-id="b0075-104">The text can come from any simple or complex expression that evaluates to correctly formatted HTML.</span></span> <span data-ttu-id="b0075-105">Отформатированный текст может быть подготовлен к просмотру в любом поддерживаемом формате вывода, включая PDF.</span><span class="sxs-lookup"><span data-stu-id="b0075-105">Formatted text can be rendered to all supported output formats, including PDF.</span></span>  
  
 <span data-ttu-id="b0075-106">![rs_HTMLFormatting](../media/rs-htmlformatting.gif "rs_HTMLFormatting")</span><span class="sxs-lookup"><span data-stu-id="b0075-106">![rs_HTMLFormatting](../media/rs-htmlformatting.gif "rs_HTMLFormatting")</span></span>  
  
 <span data-ttu-id="b0075-107">На рисунке показан текст в формате HTML в режиме конструктора отчетов и этот же текст, подготовленный к просмотру во время выполнения отчета.</span><span class="sxs-lookup"><span data-stu-id="b0075-107">This illustration shows text with HTML formatting in report design view, and the same text as it is rendered when the report is run.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b0075-108">При импорте текста, содержащего разметку HTML, полученные данные всегда должны быть вначале подвергнуты синтаксическому анализу с помощью текстового поля.</span><span class="sxs-lookup"><span data-stu-id="b0075-108">When you import text that contains HTML markup, the data must always be parsed by the text box first.</span></span> <span data-ttu-id="b0075-109">Поддерживаются не все теги HTML, поэтому код HTML, отображаемый в готовом для просмотра отчете, может отличаться от исходного кода HTML.</span><span class="sxs-lookup"><span data-stu-id="b0075-109">Because only a subset of HTML tags is supported, the HTML that is shown in the rendered report may differ from your original HTML.</span></span>  
  
 <span data-ttu-id="b0075-110">Чтобы быстро приступить к работе, см. раздел [Учебник. Форматирование текста (построитель отчета)](../tutorial-format-text-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="b0075-110">To quickly get started, see [Tutorial: Format Text &#40;Report Builder&#41;](../tutorial-format-text-report-builder.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="supported-html-tags"></a><span data-ttu-id="b0075-111">Поддерживаемые теги HTML</span><span class="sxs-lookup"><span data-stu-id="b0075-111">Supported HTML Tags</span></span>  
 <span data-ttu-id="b0075-112">Ниже приведен полный список тегов, которые подготавливаются к просмотру в формате HTML, если они определены в качестве текста заполнителя.</span><span class="sxs-lookup"><span data-stu-id="b0075-112">The following is a complete list of tags that will render as HTML when defined as placeholder text:</span></span>  
  
-   <span data-ttu-id="b0075-113">Элементы заголовка, стиля и блока: \<H{n}> , \<DIV> , \<SPAN> , \<P> ,\<LI></span><span class="sxs-lookup"><span data-stu-id="b0075-113">Header, style and block elements: \<H{n}>, \<DIV>, \<SPAN>,\<P>, \<LI></span></span>  
  
 <span data-ttu-id="b0075-114">Все прочие теги разметки HTML во время обработки отчета пропускаются.</span><span class="sxs-lookup"><span data-stu-id="b0075-114">Any other HTML markup tags will be ignored during report processing.</span></span> <span data-ttu-id="b0075-115">Если код HTML, представленный с помощью выражения в тексте заполнителя, не имеет правильного формата, то заполнитель подготавливается к просмотру в виде обычного текста.</span><span class="sxs-lookup"><span data-stu-id="b0075-115">If the HTML represented by the expression in the placeholder text is not well formed, the placeholder is rendered as plain text.</span></span> <span data-ttu-id="b0075-116">Все теги HTML рассматриваются без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="b0075-116">All HTML tags are case-insensitive.</span></span>  
  
 <span data-ttu-id="b0075-117">Если текст в текстовом поле содержит только один блок текста, то любой код HTML в заполнителе, который определяет элементы блока, подготавливается к просмотру правильно.</span><span class="sxs-lookup"><span data-stu-id="b0075-117">If the text in your text box contains only one block of text, any HTML in the placeholder that defines block elements will render correctly.</span></span> <span data-ttu-id="b0075-118">Но если текстовое поле имеет несколько блоков текста, то теги HTML пропускаются и структура текста определяется блоками текста.</span><span class="sxs-lookup"><span data-stu-id="b0075-118">However, if the text box has multiple blocks of text, the HTML tags are ignored and the structure of the text is defined by the blocks of text.</span></span>  
  
 <span data-ttu-id="b0075-119">Если для текста будет определен больше чем один тег и в службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] обнаружится конфликт между кодом HTML и существующими ограничениями отчета, то в качестве кода HTML будет рассматриваться только самый внутренний тег HTML.</span><span class="sxs-lookup"><span data-stu-id="b0075-119">If more than one tag is defined for text, and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] detects a conflict between the HTML and existing report constraints, only the innermost HTML tag will be treated as HTML.</span></span>  
  
 <span data-ttu-id="b0075-120">При использовании тегов обработки списка в качестве шрифта и стиля для всех префиксов маркеров и номеров всегда будет применяться Arial black.</span><span class="sxs-lookup"><span data-stu-id="b0075-120">When using the list handling tags, the font and style of all bullets and number prefixes will be fixed to Arial black.</span></span>  
  
 <span data-ttu-id="b0075-121">Дополнительные сведения см. в разделе [Добавление HTML в отчет (построитель отчетов и службы SSRS)](add-html-into-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b0075-121">For more information, see [Add HTML into a Report &#40;Report Builder and SSRS&#41;](add-html-into-a-report-report-builder-and-ssrs.md).</span></span>  
  
## <a name="limitations-of-cascading-style-sheet-attributes"></a><span data-ttu-id="b0075-122">Ограничения атрибутов каскадной таблицы стилей</span><span class="sxs-lookup"><span data-stu-id="b0075-122">Limitations of Cascading Style Sheet Attributes</span></span>  
 <span data-ttu-id="b0075-123">При использовании атрибутов каскадной таблицы стилей (CSS) определяется только основной набор тегов.</span><span class="sxs-lookup"><span data-stu-id="b0075-123">When using cascading style sheet (CSS) attributes, only a basic set of tags are defined.</span></span> <span data-ttu-id="b0075-124">Ниже приведен список поддерживаемых атрибутов:</span><span class="sxs-lookup"><span data-stu-id="b0075-124">The following is a list of attributes that are supported:</span></span>  
  
-   <span data-ttu-id="b0075-125">text-align, text-indent;</span><span class="sxs-lookup"><span data-stu-id="b0075-125">text-align, text-indent</span></span>  
  
-   <span data-ttu-id="b0075-126">font-family</span><span class="sxs-lookup"><span data-stu-id="b0075-126">font-family</span></span>  
  
-   <span data-ttu-id="b0075-127">font-size</span><span class="sxs-lookup"><span data-stu-id="b0075-127">font-size</span></span>  
  
    -   <span data-ttu-id="b0075-128">Поддерживаются только допустимые в языке определения отчетов значения размера в абсолютных единицах длины CSS.</span><span class="sxs-lookup"><span data-stu-id="b0075-128">Only valid RDL size values, in absolute CSS length units are supported.</span></span> <span data-ttu-id="b0075-129">Поддерживаемые единицы: in, cm, mm, pt, pc.</span><span class="sxs-lookup"><span data-stu-id="b0075-129">Supported units are: in, cm, mm, pt, pc.</span></span>  
  
    -   <span data-ttu-id="b0075-130">Относительные единицы длины CSS пропускаются и не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="b0075-130">Relative CSS length units are ignored and not supported.</span></span> <span data-ttu-id="b0075-131">Неподдерживаемые единицы включают em, ex, px, %, rem.</span><span class="sxs-lookup"><span data-stu-id="b0075-131">Unsupported units include em, ex, px,%,rem.</span></span>  
  
-   <span data-ttu-id="b0075-132">color</span><span class="sxs-lookup"><span data-stu-id="b0075-132">color</span></span>  
  
-   <span data-ttu-id="b0075-133">padding, padding-bottom, padding-top, padding-right, padding-left;</span><span class="sxs-lookup"><span data-stu-id="b0075-133">padding, padding-bottom, padding-top, padding-right, padding-left</span></span>  
  
-   <span data-ttu-id="b0075-134">font-weight.</span><span class="sxs-lookup"><span data-stu-id="b0075-134">font-weight</span></span>  
  
 <span data-ttu-id="b0075-135">Ниже приведены некоторые рекомендации по использованию CSS.</span><span class="sxs-lookup"><span data-stu-id="b0075-135">Here are some considerations for using CSS:</span></span>  
  
-   <span data-ttu-id="b0075-136">Значения CSS неправильного формата пропускаются так же, как код HTML неправильного формата.</span><span class="sxs-lookup"><span data-stu-id="b0075-136">Malformed CSS values are ignored in the same way as malformed HTML.</span></span>  
  
-   <span data-ttu-id="b0075-137">Если в том же самом теге существуют и атрибут, и атрибуты стиля CSS, то свойство CSS имеет более высокий приоритет.</span><span class="sxs-lookup"><span data-stu-id="b0075-137">When both attribute and CSS style attributes exist in the same tag, the CSS property has a higher precedence.</span></span> <span data-ttu-id="b0075-138">Например, если текст имеет значение **\<p style="text-align: right" align="left">** , будет применен только атрибут «текст-выровняйте», и текст будет выставляться по правому краю.</span><span class="sxs-lookup"><span data-stu-id="b0075-138">For example, if your text is **\<p style="text-align: right" align="left">**, only the text-align attribute will be applied and the text will be right-aligned.</span></span>  
  
-   <span data-ttu-id="b0075-139">Применительно к атрибутам и стилям CSS, если свойство задано больше одного раза, применяется только последний экземпляр свойства.</span><span class="sxs-lookup"><span data-stu-id="b0075-139">For attributes and CSS styles, if a property is specified more than once, only the last instance of the property is applied.</span></span> <span data-ttu-id="b0075-140">Например, если текст имеет значение **\<p align="left" align="right">** , текст будет выставляться по правому краю.</span><span class="sxs-lookup"><span data-stu-id="b0075-140">For example, if your text is **\<p align="left" align="right">**, the text will be right-aligned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0075-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="b0075-141">See Also</span></span>  
 [<span data-ttu-id="b0075-142">Подготовка к просмотру в виде HTML (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="b0075-142">Rendering to HTML &#40;Report Builder and SSRS&#41;</span></span>](../report-builder/rendering-to-html-report-builder-and-ssrs.md)  
  
  
