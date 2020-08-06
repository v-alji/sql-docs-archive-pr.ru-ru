---
title: Форматирование текста в текстовом поле (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: df0794b5-96b0-4034-bd17-1be7f31e29db
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 522bc420f77b2e5e9d2163c28d3d688b7c47883c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658099"
---
# <a name="format-text-in-a-text-box-report-builder-and-ssrs"></a><span data-ttu-id="aebaf-102">Форматирование текста в текстовом поле (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="aebaf-102">Format Text in a Text Box (Report Builder and SSRS)</span></span>
  <span data-ttu-id="aebaf-103">Любую часть текста в текстовом поле можно отформатировать отдельно, при этом в одном текстовом поле можно объединить текст заполнителя и статический текст.</span><span class="sxs-lookup"><span data-stu-id="aebaf-103">You can format any part of the text within a text box independently, and mix placeholder text and static text in one text box.</span></span> <span data-ttu-id="aebaf-104">Такая возможность смешивания форматов и добавления текста заполнителей позволяет создавать в отчете объединенные адреса электронной почты или создавать шаблоны текста.</span><span class="sxs-lookup"><span data-stu-id="aebaf-104">This ability to mix formats and add placeholder text enables you to create mail merges or templates for text in your report.</span></span> <span data-ttu-id="aebaf-105">С помощью заполнителя можно определить и по отдельности отформатировать любое выражение.</span><span class="sxs-lookup"><span data-stu-id="aebaf-105">Any expression can be defined and formatted separately using a placeholder.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-combine-multiple-formats-in-a-text-box"></a><span data-ttu-id="aebaf-106">Сочетание нескольких форматов в текстовом поле</span><span class="sxs-lookup"><span data-stu-id="aebaf-106">To combine multiple formats in a text box</span></span>  
  
1.  <span data-ttu-id="aebaf-107">На вкладке **Вставка** щелкните **Текстовое поле**.</span><span class="sxs-lookup"><span data-stu-id="aebaf-107">On the **Insert** tab, click **Text Box**.</span></span> <span data-ttu-id="aebaf-108">Щелкните в области конструктора и перетащите указатель мыши, чтобы создать поле нужного размера.</span><span class="sxs-lookup"><span data-stu-id="aebaf-108">Click the design surface, and then drag to create a box that is the size you want.</span></span>  
  
2.  <span data-ttu-id="aebaf-109">В текстовом поле выделите форматируемый текст.</span><span class="sxs-lookup"><span data-stu-id="aebaf-109">Inside the text box, select the text you want to format.</span></span>  
  
3.  <span data-ttu-id="aebaf-110">Щелкните правой кнопкой мыши выделенный текст и выберите пункт **Свойства текста**.</span><span class="sxs-lookup"><span data-stu-id="aebaf-110">Right-click the selected text, and click **Text Properties**.</span></span>  
  
4.  <span data-ttu-id="aebaf-111">Укажите параметры форматирования.</span><span class="sxs-lookup"><span data-stu-id="aebaf-111">Set formatting options.</span></span> <span data-ttu-id="aebaf-112">Для примера перейдите на вкладку **Общие** .</span><span class="sxs-lookup"><span data-stu-id="aebaf-112">For example, on the **General** tab:</span></span>  
  
    -   <span data-ttu-id="aebaf-113">**Подсказка.** Введите текст или выражение, результатом вычисления которого является подсказка.</span><span class="sxs-lookup"><span data-stu-id="aebaf-113">**Tooltip** Type text or an expression that evaluates to a ToolTip.</span></span> <span data-ttu-id="aebaf-114">Подсказка появляется при наведении указателя мыши на элемент отчета.</span><span class="sxs-lookup"><span data-stu-id="aebaf-114">The ToolTip appears when the user pauses the pointer over the item in a report</span></span>  
  
    -   <span data-ttu-id="aebaf-115">**Тип разметки.** Выберите параметр, чтобы указать способ подготовки к просмотру выбранного текста.</span><span class="sxs-lookup"><span data-stu-id="aebaf-115">**Markup type** Select an option to indicate how the selected text will be rendered:</span></span>  
  
         <span data-ttu-id="aebaf-116">**Обычный текст.** Выбранный текст выводится как обычный текст.</span><span class="sxs-lookup"><span data-stu-id="aebaf-116">**Plain Text** Display the selected text as simple text.</span></span> <span data-ttu-id="aebaf-117">HTML будет рассматриваться как простой текст.</span><span class="sxs-lookup"><span data-stu-id="aebaf-117">HTML will be treated as literal text.</span></span>  
  
         <span data-ttu-id="aebaf-118">**HTML.**  Выбранный текст выводится как HTML.</span><span class="sxs-lookup"><span data-stu-id="aebaf-118">**HTML**  Display the selected text as HTML.</span></span> <span data-ttu-id="aebaf-119">Если значение выражения в заполнителе содержит допустимые теги HTML, они будут подготовлены к просмотру как HTML.</span><span class="sxs-lookup"><span data-stu-id="aebaf-119">If the expression value of the placeholder contains valid HTML tags, these tags will be rendered as HTML.</span></span> <span data-ttu-id="aebaf-120">Дополнительные сведения см. в разделе [Импорт HTML в отчет (построитель отчетов и службы SSRS)](importing-html-into-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="aebaf-120">For more information, see [Importing HTML into a Report &#40;Report Builder and SSRS&#41;](importing-html-into-a-report-report-builder-and-ssrs.md).</span></span>  
  
5.  <span data-ttu-id="aebaf-121">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="aebaf-121">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="aebaf-122">Повторите шаги со 2 по 5 для оставшегося текста, который необходимо отформатировать.</span><span class="sxs-lookup"><span data-stu-id="aebaf-122">Repeat steps 2 through 5 for the remaining text you want to format.</span></span>  
  
### <a name="to-format-text-and-placeholders-differently-in-the-same-text-box"></a><span data-ttu-id="aebaf-123">Различное форматирование текста и заполнителей в одном текстовом поле</span><span class="sxs-lookup"><span data-stu-id="aebaf-123">To format text and placeholders differently in the same text box</span></span>  
  
1.  <span data-ttu-id="aebaf-124">На вкладке **Вставка** щелкните **Список**.</span><span class="sxs-lookup"><span data-stu-id="aebaf-124">On the **Insert** tab, click **List**.</span></span> <span data-ttu-id="aebaf-125">Щелкните в области конструктора и перетащите указатель мыши, чтобы создать поле нужного размера.</span><span class="sxs-lookup"><span data-stu-id="aebaf-125">Click the design surface, and then drag to create a box that is the size you want.</span></span> <span data-ttu-id="aebaf-126">Откроется диалоговое окно **Свойства набора данных** .</span><span class="sxs-lookup"><span data-stu-id="aebaf-126">The **Dataset Properties** dialog box opens.</span></span> <span data-ttu-id="aebaf-127">Можно использовать общий набор данных или набор данных, внедренный в отчет.</span><span class="sxs-lookup"><span data-stu-id="aebaf-127">You can use a shared dataset or a dataset embedded in your report.</span></span> <span data-ttu-id="aebaf-128">Чтобы получить дополнительные сведения, щелкните [Диалоговое окно "Свойства набора данных" — "Запрос" (построитель отчетов)](../report-data/dataset-properties-dialog-box-query-report-builder.md) или [Диалоговое окно "Свойства набора данных" — "Запрос"](../dataset-properties-dialog-box-query.md).</span><span class="sxs-lookup"><span data-stu-id="aebaf-128">For more information, click [Dataset Properties Dialog Box, Query &#40;Report Builder&#41;](../report-data/dataset-properties-dialog-box-query-report-builder.md) or [Dataset Properties Dialog Box, Query](../dataset-properties-dialog-box-query.md).</span></span>  
  
2.  <span data-ttu-id="aebaf-129">На вкладке **Вставка** щелкните **Текстовое поле**.</span><span class="sxs-lookup"><span data-stu-id="aebaf-129">On the **Insert** tab, click **Text Box**.</span></span> <span data-ttu-id="aebaf-130">Щелкните в списке и перетащите указатель мыши, чтобы создать поле нужного размера.</span><span class="sxs-lookup"><span data-stu-id="aebaf-130">Click in the list, and then drag to create a box that is the size you want.</span></span>  
  
3.  <span data-ttu-id="aebaf-131">Введите метку в текстовом поле, например **Мое поле**.</span><span class="sxs-lookup"><span data-stu-id="aebaf-131">Type a label in the text box - for example, **My Field**:.</span></span>  
  
4.  <span data-ttu-id="aebaf-132">В текстовое поле перетащите поле из набора данных.</span><span class="sxs-lookup"><span data-stu-id="aebaf-132">Drag a field from your dataset into the text box.</span></span> <span data-ttu-id="aebaf-133">Для поля создается заполнитель.</span><span class="sxs-lookup"><span data-stu-id="aebaf-133">A placeholder is created for your field.</span></span>  
  
5.  <span data-ttu-id="aebaf-134">Для базового форматирования выделите текст заполнителя и выберите один из параметров форматирования из группы **Шрифт** на вкладке **Корневая папка** . Например, нажмите кнопку **Полужирный**.</span><span class="sxs-lookup"><span data-stu-id="aebaf-134">For basic formatting, select the placeholder text and then click one of the formatting options in the **Font** group on the **Home** tab. For example, click the **Bold** button.</span></span>  
  
     <span data-ttu-id="aebaf-135">Для доступа к дополнительным параметрам форматирования щелкните правой кнопкой мыши текст заполнителя и выберите **Свойства заполнителя**.</span><span class="sxs-lookup"><span data-stu-id="aebaf-135">For more formatting options, right-click the placeholder text, and then click **Placeholder Properties**.</span></span>  
  
6.  <span data-ttu-id="aebaf-136">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="aebaf-136">Click **OK**.</span></span> <span data-ttu-id="aebaf-137">В конструкторе отчетов текстовое поле должно содержать текст "**Мое поле**: [*имя_поля*]", где *имя_поля* является именем поля.</span><span class="sxs-lookup"><span data-stu-id="aebaf-137">In report design view, the text box should contain "**My Field**: [*FieldName*]", where *FieldName* is the name of your field.</span></span>  
  
7.  <span data-ttu-id="aebaf-138">Нажмите кнопку **Запустить**.</span><span class="sxs-lookup"><span data-stu-id="aebaf-138">Click **Run**.</span></span>  
  
 <span data-ttu-id="aebaf-139">Список повторяется по одному разу для каждого значения в поле, а заполнитель *FieldName* будет каждый раз заменяться значением данного поля в наборе данных.</span><span class="sxs-lookup"><span data-stu-id="aebaf-139">The list repeats one time for every value in the field, and the *FieldName* placeholder is replaced each time by the value of that field in the dataset.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aebaf-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="aebaf-140">See Also</span></span>  
 <span data-ttu-id="aebaf-141">[Текстовые поля (построитель отчетов и службы SSRS)](text-boxes-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="aebaf-141">[Text Boxes &#40;Report Builder and SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="aebaf-142">[Форматирование текста и заполнителей (построитель отчетов и службы SSRS)](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="aebaf-142">[Formatting Text and Placeholders &#40;Report Builder and SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="aebaf-143">[Использование выражений в отчетах (построитель отчетов и службы SSRS)](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="aebaf-143">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="aebaf-144">[Примеры выражений (построитель отчетов и службы SSRS)](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="aebaf-144">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="aebaf-145">[Добавление HTML в отчет (построитель отчетов и службы SSRS)](add-html-into-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="aebaf-145">[Add HTML into a Report &#40;Report Builder and SSRS&#41;](add-html-into-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="aebaf-146">[Содержит &#40;построитель отчетов и SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="aebaf-146">[Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="aebaf-147">[Форматирование чисел и дат (построитель отчетов и службы SSRS)](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="aebaf-147">[Formatting Numbers and Dates &#40;Report Builder and SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="aebaf-148">Диалоговое окно "Свойства заполнителя" — "Общие" (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="aebaf-148">Placeholder Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../placeholder-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
