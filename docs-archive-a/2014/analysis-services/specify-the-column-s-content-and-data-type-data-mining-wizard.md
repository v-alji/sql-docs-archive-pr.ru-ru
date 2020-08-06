---
title: Указание содержимого столбца&#39;s и типа данных (мастер интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.dmwizard.specifycontentdatatype.f1
ms.assetid: 7061f674-e806-46f2-8c15-e260a3c69a17
author: minewiskan
ms.author: owend
ms.openlocfilehash: 66af7280e444036468b9cc33a131993524d3586d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666763"
---
# <a name="specify-the-column39s-content-and-data-type-data-mining-wizard"></a><span data-ttu-id="e0e57-102">Указание содержимого столбца&#39;s и типа данных (мастер интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="e0e57-102">Specify the Column&#39;s Content and Data Type (Data Mining Wizard)</span></span>
  <span data-ttu-id="e0e57-103">Используйте страницу **Определение содержимого и типа данных столбцов** , чтобы изменить типы данных и типы содержимого столбцов, уже установленные мастером.</span><span class="sxs-lookup"><span data-stu-id="e0e57-103">Use the **Specify the Column's Content and Data Type** page to modify the column and content types that have already been set by the wizard.</span></span> <span data-ttu-id="e0e57-104">Мастер использует типы данных исходных столбцов и возможности выбранного алгоритма, чтобы определить данные по умолчанию и типы содержимого для каждого столбца.</span><span class="sxs-lookup"><span data-stu-id="e0e57-104">The wizard uses the data types of the source columns and the capabilities of the selected algorithm to determine the default data and content types for each column.</span></span>  
  
 <span data-ttu-id="e0e57-105">**Дополнительные сведения:** [Мастер интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Создание реляционной структуры интеллектуального анализа данных](data-mining/create-a-relational-mining-structure.md)</span><span class="sxs-lookup"><span data-stu-id="e0e57-105">**For More Information:** [Data Mining Wizard &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Create a Relational Mining Structure](data-mining/create-a-relational-mining-structure.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="e0e57-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="e0e57-106">Options</span></span>  
 <span data-ttu-id="e0e57-107">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="e0e57-107">**Columns**</span></span>  
 <span data-ttu-id="e0e57-108">Список столбцов, определенных на странице мастера **Определение обучающих данных** .</span><span class="sxs-lookup"><span data-stu-id="e0e57-108">A list of the columns that are defined in the **Specify the Training Data** page of the wizard.</span></span>  
  
 <span data-ttu-id="e0e57-109">**Тип содержимого**</span><span class="sxs-lookup"><span data-stu-id="e0e57-109">**Content Type**</span></span>  
 <span data-ttu-id="e0e57-110">Тип содержимого, назначенный для каждого столбца.</span><span class="sxs-lookup"><span data-stu-id="e0e57-110">The content type that is assigned to each column.</span></span> <span data-ttu-id="e0e57-111">Щелкните внутри ячейки, чтобы изменить тип содержимого.</span><span class="sxs-lookup"><span data-stu-id="e0e57-111">Click inside a cell to change the content type.</span></span> <span data-ttu-id="e0e57-112">Дополнительные сведения о типах содержимого и типах данных см. в разделе [Типы содержимого (интеллектуальный анализ данных)](data-mining/content-types-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="e0e57-112">For more information about content types, see [Content Types &#40;Data Mining&#41;](data-mining/content-types-data-mining.md).</span></span>  
  
 <span data-ttu-id="e0e57-113">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="e0e57-113">**Data Type**</span></span>  
 <span data-ttu-id="e0e57-114">Типы данных, назначенные для каждого столбца.</span><span class="sxs-lookup"><span data-stu-id="e0e57-114">The data types that are assigned to each column.</span></span> <span data-ttu-id="e0e57-115">Щелкните внутри ячейки, чтобы изменить тип данных.</span><span class="sxs-lookup"><span data-stu-id="e0e57-115">Click inside a cell to change the data type.</span></span> <span data-ttu-id="e0e57-116">Дополнительные сведения о типах данных см. в разделе [Типы данных (интеллектуальный анализ данных)](data-mining/data-types-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="e0e57-116">For more information about data types, see [Data Types &#40;Data Mining&#41;](data-mining/data-types-data-mining.md).</span></span>  
  
 <span data-ttu-id="e0e57-117">**Detect**</span><span class="sxs-lookup"><span data-stu-id="e0e57-117">**Detect**</span></span>  
 <span data-ttu-id="e0e57-118">Нажмите, чтобы автоматически определить непрерывные и дискретные типы содержимого для числового столбца.</span><span class="sxs-lookup"><span data-stu-id="e0e57-118">Click to automatically detect the continuous and discrete content types for numeric column.</span></span> <span data-ttu-id="e0e57-119">Эта возможность не применяется к структурам интеллектуального анализа данных, основанным на источниках данных OLAP.</span><span class="sxs-lookup"><span data-stu-id="e0e57-119">This does not apply to mining structures that are based on OLAP data sources.</span></span> <span data-ttu-id="e0e57-120">Для структур интеллектуального анализа данных OLAP мастер автоматически выявляет типы содержимого и выбирает тип, совместимый с выбранным алгоритмом.</span><span class="sxs-lookup"><span data-stu-id="e0e57-120">For OLAP mining structures, the wizard automatically detects content types and chooses a type that is compatible with the selected algorithm.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0e57-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="e0e57-121">See Also</span></span>  
 <span data-ttu-id="e0e57-122">[Завершение работы мастера &#40;мастера интеллектуального анализа данных&#41;](completing-the-wizard-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="e0e57-122">[Completing the Wizard &#40;Data Mining Wizard&#41;](completing-the-wizard-data-mining-wizard.md) </span></span>  
 <span data-ttu-id="e0e57-123">[Справка F1 мастера интеллектуального анализа данных &#40;Analysis Services — интеллектуальный анализ данных&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="e0e57-123">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="e0e57-124">Укажите обучающие данные &#40;мастер интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="e0e57-124">Specify the Training Data &#40;Data Mining Wizard&#41;</span></span>](specify-the-training-data-data-mining-wizard.md)  
  
  
