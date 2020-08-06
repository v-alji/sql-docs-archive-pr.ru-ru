---
title: Редактор преобразования "Уточняющий запрос термина" (вкладка "Поиск терминов") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.termlookup.termlookup.f1
helpviewer_keywords:
- Term Lookup Transformation Editor
ms.assetid: 245d3466-d51f-4073-978a-694a8d9dfaec
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9bb8c0bd0477d9883640cc3e4d3cb25c2a3a8b27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668427"
---
# <a name="term-lookup-transformation-editor-term-lookup-tab"></a><span data-ttu-id="1a13a-102">Редактор преобразований «Уточняющий запрос термина» (вкладка «Уточняющий запрос термина»)</span><span class="sxs-lookup"><span data-stu-id="1a13a-102">Term Lookup Transformation Editor (Term Lookup Tab)</span></span>
  <span data-ttu-id="1a13a-103">Вкладка **Уточняющий запрос термина** диалогового окна **Редактор преобразования «Уточняющий запрос термина»** позволяет сопоставить входной столбец с уточняющим столбцом в ссылочной таблице и предоставить псевдоним каждому выходному столбцу.</span><span class="sxs-lookup"><span data-stu-id="1a13a-103">Use the **Term Lookup** tab of the **Term Lookup Transformation Editor** dialog box to map an input column to a lookup column in a reference table and to provide an alias for each output column.</span></span>  
  
 <span data-ttu-id="1a13a-104">Дополнительные сведения о преобразовании «Уточняющий запрос термина» см. в разделе [Term Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="1a13a-104">To learn more about the Term Lookup transformation, see [Term Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="1a13a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1a13a-105">Options</span></span>  
 <span data-ttu-id="1a13a-106">**Доступные входные столбцы**</span><span class="sxs-lookup"><span data-stu-id="1a13a-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="1a13a-107">Используя флажки, выберите входные столбцы, которые не должны измениться на выходе.</span><span class="sxs-lookup"><span data-stu-id="1a13a-107">Using the check boxes, select input columns to pass through to the output unchanged.</span></span> <span data-ttu-id="1a13a-108">Перетащите входной столбец в список **Доступные ссылочные столбцы** , чтобы сопоставить его с уточняющим столбцом в ссылочной таблице.</span><span class="sxs-lookup"><span data-stu-id="1a13a-108">Drag an input column to the **Available Reference Columns** list to map it to a lookup column in the reference table.</span></span> <span data-ttu-id="1a13a-109">Входной столбец и уточняющий столбец должны иметь одинаковый тип данных: DT_NTEXT или DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="1a13a-109">The input and lookup columns must have matching, supported data types, either DT_NTEXT or DT_WSTR.</span></span> <span data-ttu-id="1a13a-110">Выберите строку сопоставления и щелкните ее правой кнопкой мыши, чтобы изменить ее в диалоговом окне [Создание связей](data-flow/transformations/create-relationships.md) .</span><span class="sxs-lookup"><span data-stu-id="1a13a-110">Select a mapping line and right-click to edit the mappings in the [Create Relationships](data-flow/transformations/create-relationships.md) dialog box.</span></span>  
  
 <span data-ttu-id="1a13a-111">**Доступные ссылочные столбцы**</span><span class="sxs-lookup"><span data-stu-id="1a13a-111">**Available Reference Columns**</span></span>  
 <span data-ttu-id="1a13a-112">Просмотрите список доступных столбцов в ссылочной таблице.</span><span class="sxs-lookup"><span data-stu-id="1a13a-112">View the available columns in the reference table.</span></span> <span data-ttu-id="1a13a-113">Выберите столбец, содержащий список нужных терминов.</span><span class="sxs-lookup"><span data-stu-id="1a13a-113">Choose the column that contains the list of terms to match.</span></span>  
  
 <span data-ttu-id="1a13a-114">**Передаваемый столбец**</span><span class="sxs-lookup"><span data-stu-id="1a13a-114">**Pass-Through Column**</span></span>  
 <span data-ttu-id="1a13a-115">Выберите входной столбец из списка имеющихся входных столбцов.</span><span class="sxs-lookup"><span data-stu-id="1a13a-115">Select from the list of available input columns.</span></span> <span data-ttu-id="1a13a-116">Выбранные столбцы обозначаются флажками в таблице **Доступные входные столбцы** .</span><span class="sxs-lookup"><span data-stu-id="1a13a-116">Your selections are reflected in the check box selections in the **Available Input Columns** table.</span></span>  
  
 <span data-ttu-id="1a13a-117">**Псевдоним выходного столбца**</span><span class="sxs-lookup"><span data-stu-id="1a13a-117">**Output Column Alias**</span></span>  
 <span data-ttu-id="1a13a-118">Введите псевдоним для каждого выходного столбца.</span><span class="sxs-lookup"><span data-stu-id="1a13a-118">Type an alias for each output column.</span></span> <span data-ttu-id="1a13a-119">По умолчанию, это имя столбца, но можно выбрать любое уникальное описательное имя.</span><span class="sxs-lookup"><span data-stu-id="1a13a-119">The default is the name of the column; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="1a13a-120">**Настройка вывода ошибок**</span><span class="sxs-lookup"><span data-stu-id="1a13a-120">**Configure Error Output**</span></span>  
 <span data-ttu-id="1a13a-121">Используйте диалоговое окно [Настройка вывода ошибок](../../2014/integration-services/configure-error-output.md) для указания параметров обработки ошибок для строк, вызвавших ошибку.</span><span class="sxs-lookup"><span data-stu-id="1a13a-121">Use the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box to specify error handling options for rows that cause errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a13a-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="1a13a-122">See Also</span></span>  
 <span data-ttu-id="1a13a-123">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="1a13a-123">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="1a13a-124">[Редактор преобразования "Уточняющий запрос термина" &#40;вкладка "ссылочная таблица"&#41;](../../2014/integration-services/term-lookup-transformation-editor-reference-table-tab.md) </span><span class="sxs-lookup"><span data-stu-id="1a13a-124">[Term Lookup Transformation Editor &#40;Reference Table Tab&#41;](../../2014/integration-services/term-lookup-transformation-editor-reference-table-tab.md) </span></span>  
 <span data-ttu-id="1a13a-125">[Редактор преобразования "Уточняющий запрос термина" &#40;вкладка "Дополнительно"&#41;](../../2014/integration-services/term-lookup-transformation-editor-advanced-tab.md) </span><span class="sxs-lookup"><span data-stu-id="1a13a-125">[Term Lookup Transformation Editor &#40;Advanced Tab&#41;](../../2014/integration-services/term-lookup-transformation-editor-advanced-tab.md) </span></span>  
 [<span data-ttu-id="1a13a-126">Преобразование "Извлечение терминов"</span><span class="sxs-lookup"><span data-stu-id="1a13a-126">Term Extraction Transformation</span></span>](data-flow/transformations/term-extraction-transformation.md)  
  
  
