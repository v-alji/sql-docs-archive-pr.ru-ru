---
title: Редактор преобразования "Нечеткое группирование" (вкладка "Дополнительно") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzygroupingtransformation.advanced.f1
helpviewer_keywords:
- Fuzzy Grouping Transformation Editor
ms.assetid: dd820d75-b8a7-4515-aea4-3553ba5b442e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2f5dd05eda56b4818914f659734eb3cdfb20c4d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657154"
---
# <a name="fuzzy-grouping-transformation-editor-advanced-tab"></a><span data-ttu-id="24795-102">Редактор преобразования «Нечеткое группирование» (вкладка «Дополнительно»)</span><span class="sxs-lookup"><span data-stu-id="24795-102">Fuzzy Grouping Transformation Editor (Advanced Tab)</span></span>
  <span data-ttu-id="24795-103">На вкладке **Дополнительно** диалогового окна **Редактор преобразования «Нечеткое группирование»** можно определить входные и выходные столбцы, пороги подобия и разделители токенов.</span><span class="sxs-lookup"><span data-stu-id="24795-103">Use the **Advanced** tab of the **Fuzzy Grouping Transformation Editor** dialog box to specify input and output columns, set similarity thresholds, and define delimiters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="24795-104">`Exhaustive` `MaxMemoryUsage` Свойства и преобразования «Нечеткое группирование» недоступны в **редакторе преобразования «Нечеткое группирование**», но могут быть установлены с помощью **Расширенный редактор**.</span><span class="sxs-lookup"><span data-stu-id="24795-104">The `Exhaustive` and the `MaxMemoryUsage` properties of the Fuzzy Grouping transformation are not available in the **Fuzzy Grouping Transformation Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="24795-105">Дополнительные сведения об этих свойствах см. в подразделе «Преобразование "Нечеткое группирование"» раздела [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="24795-105">For more information on these properties, see the Fuzzy Grouping Transformation section of [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="24795-106">Дополнительные сведения о преобразовании «Нечеткое группирование» см. в разделе [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="24795-106">To learn more about the Fuzzy Grouping transformation, see [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="24795-107">Варианты</span><span class="sxs-lookup"><span data-stu-id="24795-107">Options</span></span>  
 <span data-ttu-id="24795-108">**Имя входного ключевого столбца**</span><span class="sxs-lookup"><span data-stu-id="24795-108">**Input key column name**</span></span>  
 <span data-ttu-id="24795-109">Укажите имя выходного столбца, содержащего уникальный идентификатор для каждой входной строки.</span><span class="sxs-lookup"><span data-stu-id="24795-109">Specify the name of an output column that contains the unique identifier for each input row.</span></span> <span data-ttu-id="24795-110">Столбец `_key_in` содержит значение, уникально идентифицирующее каждую строку.</span><span class="sxs-lookup"><span data-stu-id="24795-110">The `_key_in` column has a value that uniquely identifies each row.</span></span>  
  
 <span data-ttu-id="24795-111">**Имя выходного ключевого столбца**</span><span class="sxs-lookup"><span data-stu-id="24795-111">**Output key column name**</span></span>  
 <span data-ttu-id="24795-112">Укажите имя выходного столбца, содержащего уникальный идентификатор для канонической строки группы повторяющихся строк.</span><span class="sxs-lookup"><span data-stu-id="24795-112">Specify the name of an output column that contains the unique identifier for the canonical row of a group of duplicate rows.</span></span> <span data-ttu-id="24795-113">Столбец `_key_out` соответствует значению `_key_in` канонической строки данных.</span><span class="sxs-lookup"><span data-stu-id="24795-113">The `_key_out` column corresponds to the `_key_in` value of the canonical data row.</span></span>  
  
 <span data-ttu-id="24795-114">**Имя столбца порога подобия**</span><span class="sxs-lookup"><span data-stu-id="24795-114">**Similarity score column name**</span></span>  
 <span data-ttu-id="24795-115">Укажите имя столбца, содержащего показатель подобия.</span><span class="sxs-lookup"><span data-stu-id="24795-115">Specify a name for the column that contains the similarity score.</span></span> <span data-ttu-id="24795-116">Показатель подобия — значение от 0 до 1, представляющее собой степень подобия входной строки относительно канонической.</span><span class="sxs-lookup"><span data-stu-id="24795-116">The similarity score is a value between 0 and 1 that indicates the similarity of the input row to the canonical row.</span></span> <span data-ttu-id="24795-117">Чем ближе к 1 коэффициент, тем более строка соответствует канонической.</span><span class="sxs-lookup"><span data-stu-id="24795-117">The closer the score is to 1, the more closely the row matches the canonical row.</span></span>  
  
 <span data-ttu-id="24795-118">**Порог подобия**</span><span class="sxs-lookup"><span data-stu-id="24795-118">**Similarity threshold**</span></span>  
 <span data-ttu-id="24795-119">Установите порог подобия с помощью ползунка.</span><span class="sxs-lookup"><span data-stu-id="24795-119">Set the similarity threshold by using the slider.</span></span> <span data-ttu-id="24795-120">Чем ближе порог к 1, тем большее сходство между собой должны иметь строки, считающиеся повторяющимися.</span><span class="sxs-lookup"><span data-stu-id="24795-120">The closer the threshold is to 1, the more the rows must resemble each other to qualify as duplicates.</span></span> <span data-ttu-id="24795-121">Увеличение этого порога может повысить скорость нахождения совпадений, так как количество рассматриваемых потенциальных записей будет меньше.</span><span class="sxs-lookup"><span data-stu-id="24795-121">Increasing the threshold can improve the speed of matching because fewer candidate records have to be considered.</span></span>  
  
 <span data-ttu-id="24795-122">**Разделители токенов**</span><span class="sxs-lookup"><span data-stu-id="24795-122">**Token delimiters**</span></span>  
 <span data-ttu-id="24795-123">В преобразовании имеется набор разделителей по умолчанию для разделения данных на лексемы. При необходимости можно добавить или удалить разделители в списке.</span><span class="sxs-lookup"><span data-stu-id="24795-123">The transformation provides a default set of delimiters for tokenizing data, but you can add or remove delimiters as needed by editing the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24795-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="24795-124">See Also</span></span>  
 <span data-ttu-id="24795-125">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="24795-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="24795-126">Определение подобных строк данных с помощью преобразования «Нечеткое группирование»</span><span class="sxs-lookup"><span data-stu-id="24795-126">Identify Similar Data Rows by Using the Fuzzy Grouping Transformation</span></span>](data-flow/transformations/identify-similar-data-rows-by-using-the-fuzzy-grouping-transformation.md)  
  
  
