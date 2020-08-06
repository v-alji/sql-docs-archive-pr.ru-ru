---
title: Редактор преобразования "Нечеткий уточняющий запрос" (вкладка "Дополнительно") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzylookuptransformation.advanced.f1
helpviewer_keywords:
- Fuzzy Lookup Transformation Editor
ms.assetid: 0a2919be-2ea7-4c06-82b8-0ffad5f0dd83
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 68f53eb2735dc07656fc8ff2b81c3259caa4847b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729630"
---
# <a name="fuzzy-lookup-transformation-editor-advanced-tab"></a><span data-ttu-id="00a46-102">Редактор преобразования «Нечеткий уточняющий запрос» (вкладка «Дополнительно»)</span><span class="sxs-lookup"><span data-stu-id="00a46-102">Fuzzy Lookup Transformation Editor (Advanced Tab)</span></span>
  <span data-ttu-id="00a46-103">Вкладка **Дополнительно** диалогового окна **Редактор преобразования «Нечеткий уточняющий запрос»** позволяет задать параметры нечеткого поиска.</span><span class="sxs-lookup"><span data-stu-id="00a46-103">Use the **Advanced** tab of the **Fuzzy Lookup Transformation Editor** dialog box to set parameters for the fuzzy lookup.</span></span>  
  
 <span data-ttu-id="00a46-104">Дополнительные сведения о преобразовании «Нечеткий уточняющий запрос» см. в разделе [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="00a46-104">To learn more about the Fuzzy Lookup transformation, see [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="00a46-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="00a46-105">Options</span></span>  
 <span data-ttu-id="00a46-106">**Максимальное количество совпадений, которое следует выводить на каждый уточняющий запрос**</span><span class="sxs-lookup"><span data-stu-id="00a46-106">**Maximum number of matches to output per lookup**</span></span>  
 <span data-ttu-id="00a46-107">Указывает максимальное число совпадений, возвращаемое преобразованием для каждой входной строки.</span><span class="sxs-lookup"><span data-stu-id="00a46-107">Specify the maximum number of matches the transformation can return for each input row.</span></span> <span data-ttu-id="00a46-108">Значение по умолчанию — **1**.</span><span class="sxs-lookup"><span data-stu-id="00a46-108">The default is **1**.</span></span>  
  
 <span data-ttu-id="00a46-109">**Порог подобия**</span><span class="sxs-lookup"><span data-stu-id="00a46-109">**Similarity threshold**</span></span>  
 <span data-ttu-id="00a46-110">Задает порог подобия на уровне компонента при помощи данного ползунка.</span><span class="sxs-lookup"><span data-stu-id="00a46-110">Set the similarity threshold at the component level by using the slider.</span></span> <span data-ttu-id="00a46-111">Чем ближе значение к 1, тем ближе к искомому должно быть значение строки уточняющего запроса.</span><span class="sxs-lookup"><span data-stu-id="00a46-111">The closer the value is to 1, the closer the resemblance of the lookup value to the source value must be to qualify as a match.</span></span> <span data-ttu-id="00a46-112">Увеличение порогового значения может увеличить скорость соответствия, так как при этом будет рассматриваться меньшее количество предполагаемых совпадений.</span><span class="sxs-lookup"><span data-stu-id="00a46-112">Increasing the threshold can improve the speed of matching since fewer candidate records need to be considered.</span></span>  
  
 <span data-ttu-id="00a46-113">**Разделители токенов**</span><span class="sxs-lookup"><span data-stu-id="00a46-113">**Token delimiters**</span></span>  
 <span data-ttu-id="00a46-114">Определяет разделители, используемые преобразованием для разделения значений столбца.</span><span class="sxs-lookup"><span data-stu-id="00a46-114">Specify the delimiters that the transformation uses to tokenize column values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00a46-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="00a46-115">See Also</span></span>  
 <span data-ttu-id="00a46-116">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="00a46-116">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="00a46-117">[Редактор преобразования "Нечеткий уточняющий запрос" &#40;вкладка "ссылочная таблица"&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-reference-table-tab.md) </span><span class="sxs-lookup"><span data-stu-id="00a46-117">[Fuzzy Lookup Transformation Editor &#40;Reference Table Tab&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-reference-table-tab.md) </span></span>  
 [<span data-ttu-id="00a46-118">Редактор преобразования "Нечеткий уточняющий запрос" (вкладка "Столбцы")</span><span class="sxs-lookup"><span data-stu-id="00a46-118">Fuzzy Lookup Transformation Editor &#40;Columns Tab&#41;</span></span>](../../2014/integration-services/fuzzy-lookup-transformation-editor-columns-tab.md)  
  
  
