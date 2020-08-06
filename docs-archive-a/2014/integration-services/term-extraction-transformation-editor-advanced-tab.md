---
title: Редактор преобразования "Извлечение терминов" (вкладка "Дополнительно") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.termextraction.advanced.f1
helpviewer_keywords:
- Term Extraction Transformation Editor
ms.assetid: 87118281-6e3c-499e-bac4-fa4c24bb12c6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f4be56f8ac2deeab49e43071a07894a466019287
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734289"
---
# <a name="term-extraction-transformation-editor-advanced-tab"></a><span data-ttu-id="9353f-102">Редактор преобразования «Извлечение терминов» (вкладка «Дополнительно»)</span><span class="sxs-lookup"><span data-stu-id="9353f-102">Term Extraction Transformation Editor (Advanced Tab)</span></span>
  <span data-ttu-id="9353f-103">Вкладка **Дополнительно** диалогового окна **Редактор преобразования «Извлечение терминов»** используется для задания свойств извлечения, таких как частота, длина и предмет извлечения (слова или фразы).</span><span class="sxs-lookup"><span data-stu-id="9353f-103">Use the **Advanced** tab of the **Term Extraction Transformation Editor** dialog box to specify properties for the extraction such as frequency, length, and whether to extract words or phrases.</span></span>  
  
 <span data-ttu-id="9353f-104">Дополнительные сведения о преобразовании «Извлечения терминов» см. в разделе [Term Extraction Transformation](data-flow/transformations/term-extraction-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="9353f-104">To learn more about the Term Extraction transformation, see [Term Extraction Transformation](data-flow/transformations/term-extraction-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="9353f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9353f-105">Options</span></span>  
 <span data-ttu-id="9353f-106">**Имя существительное**</span><span class="sxs-lookup"><span data-stu-id="9353f-106">**Noun**</span></span>  
 <span data-ttu-id="9353f-107">Указывает, что при преобразовании будут извлекаться только отдельные существительные.</span><span class="sxs-lookup"><span data-stu-id="9353f-107">Specify that the transformation extracts individual nouns only.</span></span>  
  
 <span data-ttu-id="9353f-108">**Субстантивное словосочетание**</span><span class="sxs-lookup"><span data-stu-id="9353f-108">**Noun phrase**</span></span>  
 <span data-ttu-id="9353f-109">Указывает, что при преобразовании будут извлекаться только субстантивные словосочетания.</span><span class="sxs-lookup"><span data-stu-id="9353f-109">Specify that the transformation extracts noun phrases only.</span></span>  
  
 <span data-ttu-id="9353f-110">**Имя существительное и субстантивное словосочетание**</span><span class="sxs-lookup"><span data-stu-id="9353f-110">**Noun and noun phrase**</span></span>  
 <span data-ttu-id="9353f-111">Указывает, что при преобразовании будут извлекаться как существительные, так и субстантивные словосочетания.</span><span class="sxs-lookup"><span data-stu-id="9353f-111">Specify that the transformation extracts both nouns and noun phrases.</span></span>  
  
 <span data-ttu-id="9353f-112">**Частота**</span><span class="sxs-lookup"><span data-stu-id="9353f-112">**Frequency**</span></span>  
 <span data-ttu-id="9353f-113">Указывает, что целевой функцией является частота термина.</span><span class="sxs-lookup"><span data-stu-id="9353f-113">Specify that the score is the frequency of the term.</span></span>  
  
 <span data-ttu-id="9353f-114">**TFIDF**</span><span class="sxs-lookup"><span data-stu-id="9353f-114">**TFIDF**</span></span>  
 <span data-ttu-id="9353f-115">Указывает, что целевой функцией является значение TFIDF термина.</span><span class="sxs-lookup"><span data-stu-id="9353f-115">Specify that the score is the TFIDF value of the term.</span></span> <span data-ttu-id="9353f-116">Функция TFIDF расшифровывается как "частота термина и обратная частота документа" (Term Frequency and Inverse Document Frequency) и определяется формулой: TFIDF термина T = (частота_T) \* log (#число_строк_во_входных_данных) / (#число_строк_включающих_T)</span><span class="sxs-lookup"><span data-stu-id="9353f-116">The TFIDF score is the product of Term Frequency and Inverse Document Frequency, defined as: TFIDF of a Term T = (frequency of T) \* log( (#rows in Input) / (#rows having T) )</span></span>  
  
 <span data-ttu-id="9353f-117">**Порог частоты**</span><span class="sxs-lookup"><span data-stu-id="9353f-117">**Frequency threshold**</span></span>  
 <span data-ttu-id="9353f-118">Позволяет задать число вхождений слова или фразы, необходимое для их извлечения.</span><span class="sxs-lookup"><span data-stu-id="9353f-118">Specify the number of times a word or phrase must occur before extracting it.</span></span> <span data-ttu-id="9353f-119">Значение по умолчанию — 2.</span><span class="sxs-lookup"><span data-stu-id="9353f-119">The default value is 2.</span></span>  
  
 <span data-ttu-id="9353f-120">**Максимальная длина термина**</span><span class="sxs-lookup"><span data-stu-id="9353f-120">**Maximum length of term**</span></span>  
 <span data-ttu-id="9353f-121">Позволяет задать максимальную длину фразы или слова.</span><span class="sxs-lookup"><span data-stu-id="9353f-121">Specify the maximum length of a phrase in words.</span></span> <span data-ttu-id="9353f-122">Этот параметр затрагивает только субстантивные словосочетания.</span><span class="sxs-lookup"><span data-stu-id="9353f-122">This option affects noun phrases only.</span></span> <span data-ttu-id="9353f-123">Значение по умолчанию — 12.</span><span class="sxs-lookup"><span data-stu-id="9353f-123">The default value is 12.</span></span>  
  
 <span data-ttu-id="9353f-124">**Учитывать регистр при извлечении терминов**</span><span class="sxs-lookup"><span data-stu-id="9353f-124">**Use case-sensitive term extraction**</span></span>  
 <span data-ttu-id="9353f-125">Указывает, будет ли учитываться регистр при извлечении.</span><span class="sxs-lookup"><span data-stu-id="9353f-125">Specify whether to make the extraction case-sensitive.</span></span> <span data-ttu-id="9353f-126">Значение по умолчанию — `False`.</span><span class="sxs-lookup"><span data-stu-id="9353f-126">The default is `False`.</span></span>  
  
 <span data-ttu-id="9353f-127">**Настройка вывода ошибок**</span><span class="sxs-lookup"><span data-stu-id="9353f-127">**Configure Error Output**</span></span>  
 <span data-ttu-id="9353f-128">Используйте диалоговое окно [Настройка вывода ошибок](../../2014/integration-services/configure-error-output.md) для указания метода обработки ошибок для строк, вызвавших ошибку.</span><span class="sxs-lookup"><span data-stu-id="9353f-128">Use the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box to specify error handling for rows that cause errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9353f-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="9353f-129">See Also</span></span>  
 <span data-ttu-id="9353f-130">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="9353f-130">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="9353f-131">[Редактор преобразования "Извлечение терминов" &#40;вкладка "Извлечение терминов"&#41;](../../2014/integration-services/term-extraction-transformation-editor-term-extraction-tab.md) </span><span class="sxs-lookup"><span data-stu-id="9353f-131">[Term Extraction Transformation Editor &#40;Term Extraction Tab&#41;](../../2014/integration-services/term-extraction-transformation-editor-term-extraction-tab.md) </span></span>  
 <span data-ttu-id="9353f-132">[Редактор преобразования "Извлечение терминов" &#40;вкладка "исключения"&#41;](../../2014/integration-services/term-extraction-transformation-editor-exclusion-tab.md) </span><span class="sxs-lookup"><span data-stu-id="9353f-132">[Term Extraction Transformation Editor &#40;Exclusion Tab&#41;](../../2014/integration-services/term-extraction-transformation-editor-exclusion-tab.md) </span></span>  
 [<span data-ttu-id="9353f-133">Преобразование "Уточняющий запрос термина"</span><span class="sxs-lookup"><span data-stu-id="9353f-133">Term Lookup Transformation</span></span>](data-flow/transformations/lookup-transformation.md)  
  
  
