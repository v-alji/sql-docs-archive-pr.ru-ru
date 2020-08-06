---
title: Диалоговое окно "Свойства заполнителя" — "Общие" (построитель отчетов и службы SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10131"
- sql12.rtp.rptdesigner.placeholderproperties.general.f1
ms.assetid: 7a867736-a3b0-4b5a-b3e5-fe7c8d7618a8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e561f08206deae383ceb4c1b74d373aa3bcee6fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739500"
---
# <a name="placeholder-properties-dialog-box-general-report-builder-and-ssrs"></a><span data-ttu-id="8c483-102">Диалоговое окно «Свойства заполнителя» — «Общие» (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="8c483-102">Placeholder Properties Dialog Box, General (Report Builder and SSRS)</span></span>
  <span data-ttu-id="8c483-103">Диалоговое окно **Свойства заполнителя** можно использовать для изменения значения, подсказки и параметров разметки заполнителя в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="8c483-103">Use the **Placeholder Properties** dialog box to change the value, ToolTip, and markup options of a placeholder in a text box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8c483-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="8c483-104">Options</span></span>  
 <span data-ttu-id="8c483-105">**Label**</span><span class="sxs-lookup"><span data-stu-id="8c483-105">**Label**</span></span>  
 <span data-ttu-id="8c483-106">Введите метку для заполнителя.</span><span class="sxs-lookup"><span data-stu-id="8c483-106">Type a label for the placeholder.</span></span> <span data-ttu-id="8c483-107">Метка отображается только в области конструктора.</span><span class="sxs-lookup"><span data-stu-id="8c483-107">The label is displayed on the design surface only.</span></span>  
  
 <span data-ttu-id="8c483-108">**Значение**</span><span class="sxs-lookup"><span data-stu-id="8c483-108">**Value**</span></span>  
 <span data-ttu-id="8c483-109">Введите значение текстового поля.</span><span class="sxs-lookup"><span data-stu-id="8c483-109">Type the value of the text box.</span></span> <span data-ttu-id="8c483-110">Это должно быть выражение с полями, другое выражение или метка.</span><span class="sxs-lookup"><span data-stu-id="8c483-110">This should be a field expression, other expression, or a label.</span></span> <span data-ttu-id="8c483-111">Нажмите кнопку **выражение** (*FX*), чтобы изменить выражение.</span><span class="sxs-lookup"><span data-stu-id="8c483-111">Click the **Expression** (*fx*) button to edit the expression.</span></span>  
  
 <span data-ttu-id="8c483-112">**Подсказка**</span><span class="sxs-lookup"><span data-stu-id="8c483-112">**Tooltip**</span></span>  
 <span data-ttu-id="8c483-113">Введите подсказку или выражение, результатом вычисления которого является подсказка.</span><span class="sxs-lookup"><span data-stu-id="8c483-113">Type text or an expression that evaluates to a ToolTip.</span></span> <span data-ttu-id="8c483-114">Нажмите кнопку **выражение** (*FX*), чтобы изменить выражение.</span><span class="sxs-lookup"><span data-stu-id="8c483-114">Click the **Expression** (*fx*) button to edit the expression.</span></span> <span data-ttu-id="8c483-115">Подсказка появляется в случае, если задержать указатель мыши над текстовым полем в отчете, готовом для просмотра.</span><span class="sxs-lookup"><span data-stu-id="8c483-115">The ToolTip appears when the user pauses the pointer over the item in the rendered report.</span></span>  
  
 <span data-ttu-id="8c483-116">**Тип разметки**</span><span class="sxs-lookup"><span data-stu-id="8c483-116">**Markup type**</span></span>  
 <span data-ttu-id="8c483-117">Выберите параметр, указывающий метод подготовки к просмотру заполнителя.</span><span class="sxs-lookup"><span data-stu-id="8c483-117">Select an option to indicate how the placeholder is rendered.</span></span>  
  
-   <span data-ttu-id="8c483-118">**Простой текст** Отображать заполнитель как простой текст.</span><span class="sxs-lookup"><span data-stu-id="8c483-118">**Plain Text** Display the placeholder as simple text.</span></span> <span data-ttu-id="8c483-119">HTML обрабатывается как литеральный текст.</span><span class="sxs-lookup"><span data-stu-id="8c483-119">HTML is treated as literal text.</span></span>  
  
-   <span data-ttu-id="8c483-120">**HTML**  Отображать заполнитель как HTML.</span><span class="sxs-lookup"><span data-stu-id="8c483-120">**HTML**  Display the placeholder as HTML.</span></span> <span data-ttu-id="8c483-121">Если значение выражения в заполнителе содержит допустимые теги HTML, они будут подготовлены к просмотру как HTML.</span><span class="sxs-lookup"><span data-stu-id="8c483-121">If the expression value of the placeholder contains valid HTML tags, these tags are rendered as HTML.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c483-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="8c483-122">See Also</span></span>  
 <span data-ttu-id="8c483-123">[Форматирование текста в текстовом поле &#40;построитель отчетов и SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8c483-123">[Format Text in a Text Box &#40;Report Builder and SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="8c483-124">[Добавление HTML в &#40;отчетов построитель отчетов и SSRS&#41;](report-design/add-html-into-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8c483-124">[Add HTML into a Report &#40;Report Builder and SSRS&#41;](report-design/add-html-into-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="8c483-125">[Примеры выражений (построитель отчетов и службы SSRS)](report-design/expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8c483-125">[Expression Examples &#40;Report Builder and SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="8c483-126">[Текстовые поля &#40;построитель отчетов и службы SSRS&#41;](report-design/text-boxes-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8c483-126">[Text Boxes &#40;Report Builder and SSRS&#41;](report-design/text-boxes-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="8c483-127">[Форматирование элементов отчета &#40;построитель отчетов и SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8c483-127">[Formatting Report Items &#40;Report Builder and SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="8c483-128">[Форматирование текста и заполнителей &#40;построитель отчетов и SSRS&#41;](report-design/formatting-text-and-placeholders-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8c483-128">[Formatting Text and Placeholders &#40;Report Builder and SSRS&#41;](report-design/formatting-text-and-placeholders-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="8c483-129">Импорт HTML в отчет (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="8c483-129">Importing HTML into a Report &#40;Report Builder and SSRS&#41;</span></span>](report-design/importing-html-into-a-report-report-builder-and-ssrs.md)  
  
  
