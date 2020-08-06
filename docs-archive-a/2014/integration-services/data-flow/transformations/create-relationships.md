---
title: Создание связей | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.createrelationships.f1
ms.assetid: 6ebd305f-ffd2-4a1d-b24c-e28c151b94f5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5a1095e193587ae7d416311031e5297a035ca37e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657174"
---
# <a name="create-relationships"></a><span data-ttu-id="698ab-102">Создание связей</span><span class="sxs-lookup"><span data-stu-id="698ab-102">Create Relationships</span></span>
  <span data-ttu-id="698ab-103">Используйте диалоговое окно **Создание связей** , чтобы изменить сопоставления между исходными столбцами и столбцами таблицы уточняющих запросов, настроенные в редакторе преобразования «Нечеткий уточняющий запрос», в редакторах преобразования «Уточняющий запрос» и «Уточняющий запрос термина».</span><span class="sxs-lookup"><span data-stu-id="698ab-103">Use the **Create Relationships** dialog box to edit mappings between the source columns and the lookup table columns that you configured in the Fuzzy Lookup Transformation Editor, the Lookup Transformation Editor, and the Term Lookup Transformation Editor.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="698ab-104">Диалоговое окно **Создание связей** отображает только списки **Входной столбец** и **Столбец подстановок** , если вызвано из редактора преобразования "Уточняющий запрос термина".</span><span class="sxs-lookup"><span data-stu-id="698ab-104">The **Create Relationships** dialog box displays only the **Input Column** and **Lookup Column** lists when invoked from the Term Lookup Transformation Editor.</span></span>  
  
 <span data-ttu-id="698ab-105">Дополнительные сведения о преобразованиях, использующих диалоговое окно **Создание связей** см. в разделах [Fuzzy Lookup Transformation](lookup-transformation.md), [Lookup Transformation](lookup-transformation.md)и [Term Lookup Transformation](term-lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="698ab-105">To learn more about the transformations that use the **Create Relationships** dialog box, see [Fuzzy Lookup Transformation](lookup-transformation.md), [Lookup Transformation](lookup-transformation.md), and [Term Lookup Transformation](term-lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="698ab-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="698ab-106">Options</span></span>  
 <span data-ttu-id="698ab-107">**Входной столбец**</span><span class="sxs-lookup"><span data-stu-id="698ab-107">**Input Column**</span></span>  
 <span data-ttu-id="698ab-108">Выберите входной столбец из списка имеющихся входных столбцов.</span><span class="sxs-lookup"><span data-stu-id="698ab-108">Select from the list of available input columns.</span></span>  
  
 <span data-ttu-id="698ab-109">**Уточняющий столбец**</span><span class="sxs-lookup"><span data-stu-id="698ab-109">**Lookup Column**</span></span>  
 <span data-ttu-id="698ab-110">Выберите из списка доступных столбцов подстановок.</span><span class="sxs-lookup"><span data-stu-id="698ab-110">Select from the list of available lookup columns.</span></span>  
  
 <span data-ttu-id="698ab-111">**Тип сопоставления**</span><span class="sxs-lookup"><span data-stu-id="698ab-111">**Mapping Type**</span></span>  
 <span data-ttu-id="698ab-112">Выберите нечеткое или четкое соответствие.</span><span class="sxs-lookup"><span data-stu-id="698ab-112">Select fuzzy or exact matching.</span></span>  
  
 <span data-ttu-id="698ab-113">При использовании нечеткого соответствия строки рассматриваются как дубликаты, если они в значительной степени совпадают по всем столбцам, имеющим нечеткий тип соответствия.</span><span class="sxs-lookup"><span data-stu-id="698ab-113">When you use fuzzy matching, rows are considered duplicates if they are sufficiently similar across all columns that have a fuzzy match type.</span></span> <span data-ttu-id="698ab-114">Для получения лучших результатов от нечеткого соответствия можно указать, чтобы некоторые столбцы использовали четкое соответствие вместо нечеткого.</span><span class="sxs-lookup"><span data-stu-id="698ab-114">To obtain better results from fuzzy matching, you can specify that some columns should use exact matching instead of fuzzy matching.</span></span> <span data-ttu-id="698ab-115">Например, если известно, что конкретный столбец не содержит ошибок или противоречий, то возможно указать для этого столбца четкое соответствие, таким образом, чтобы в качестве дубликатов рассматривались лишь те строки, которые содержат идентичные значения в этом столбце.</span><span class="sxs-lookup"><span data-stu-id="698ab-115">For example, if you know that a certain column contains no errors or inconsistencies, you can specify exact matching on that column, so that only rows which contain identical values in this column are considered as possible duplicates.</span></span> <span data-ttu-id="698ab-116">Это увеличивает степень точности нечеткого соответствия по другим столбцам.</span><span class="sxs-lookup"><span data-stu-id="698ab-116">This increases the accuracy of fuzzy matching on other columns.</span></span>  
  
 <span data-ttu-id="698ab-117">**Флаги сравнения**</span><span class="sxs-lookup"><span data-stu-id="698ab-117">**Comparison Flags**</span></span>  
 <span data-ttu-id="698ab-118">Дополнительные сведения о параметрах сравнения строк см. в разделе [Сравнение строковых данных](../comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="698ab-118">For information about the string comparison options, see [Comparing String Data](../comparing-string-data.md).</span></span>  
  
 <span data-ttu-id="698ab-119">**Минимальное подобие**</span><span class="sxs-lookup"><span data-stu-id="698ab-119">**Minimum Similarity**</span></span>  
 <span data-ttu-id="698ab-120">Установите порог подобия на уровне столбцов, используя ползунок.</span><span class="sxs-lookup"><span data-stu-id="698ab-120">Set the similarity threshold at the column level by using the slider.</span></span> <span data-ttu-id="698ab-121">Чем ближе это значение к 1, тем ближе должно быть сходство между значением уточняющего столбца и исходным значением, чтобы они считались соответствующими.</span><span class="sxs-lookup"><span data-stu-id="698ab-121">The closer the value is to 1, the more the lookup value must resemble the source value to qualify as a match.</span></span> <span data-ttu-id="698ab-122">Увеличение этого порога может повысить скорость нахождения совпадений, так как количество рассматриваемых потенциальных записей будет меньше.</span><span class="sxs-lookup"><span data-stu-id="698ab-122">Increasing the threshold can improve the speed of matching because fewer candidate records have to be considered.</span></span>  
  
 <span data-ttu-id="698ab-123">**Псевдоним выхода подобия**</span><span class="sxs-lookup"><span data-stu-id="698ab-123">**Similarity Output Alias**</span></span>  
 <span data-ttu-id="698ab-124">Укажите имя для нового выходного столбца, который является подобным выбранному столбцу.</span><span class="sxs-lookup"><span data-stu-id="698ab-124">Specify the name for a new output column that contains the similarity scores for the selected column.</span></span> <span data-ttu-id="698ab-125">Если оставить это значение пустым, то выходной столбец не будет создан.</span><span class="sxs-lookup"><span data-stu-id="698ab-125">If you leave this value empty, the output column is not created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="698ab-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="698ab-126">See Also</span></span>  
 <span data-ttu-id="698ab-127">[Справочник по сообщениям об ошибках служб Integration Services](../../integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="698ab-127">[Integration Services Error and Message Reference](../../integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="698ab-128">[Редактор преобразования "Нечеткий уточняющий запрос" (вкладка "Столбцы")](../../fuzzy-lookup-transformation-editor-columns-tab.md) </span><span class="sxs-lookup"><span data-stu-id="698ab-128">[Fuzzy Lookup Transformation Editor &#40;Columns Tab&#41;](../../fuzzy-lookup-transformation-editor-columns-tab.md) </span></span>  
 <span data-ttu-id="698ab-129">[Редактор преобразования "Уточняющий запрос" (страница "Столбцы")](../../lookup-transformation-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="698ab-129">[Lookup Transformation Editor &#40;Columns Page&#41;](../../lookup-transformation-editor-columns-page.md) </span></span>  
 [<span data-ttu-id="698ab-130">Редактор преобразований "Уточняющий запрос термина" (вкладка "Уточняющий запрос термина")</span><span class="sxs-lookup"><span data-stu-id="698ab-130">Term Lookup Transformation Editor &#40;Term Lookup Tab&#41;</span></span>](../../term-lookup-transformation-editor-term-lookup-tab.md)  
  
  
