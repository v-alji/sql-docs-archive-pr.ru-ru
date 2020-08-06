---
title: Определение табличных типов (мастер интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.dmwizard.specifytabletypes.f1
ms.assetid: 8209a707-faef-4ffc-8991-6c13bb350753
author: minewiskan
ms.author: owend
ms.openlocfilehash: 88c09f26958c37ed0a99efb54a5eb5c08505d16b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666764"
---
# <a name="specify-table-types-data-mining-wizard"></a><span data-ttu-id="88994-102">Определение типов таблиц (мастер интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="88994-102">Specify Table Types (Data Mining Wizard)</span></span>
  <span data-ttu-id="88994-103">Страница **Определение типов таблиц** используется для идентификации таблиц, используемых для определения структуры интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="88994-103">Use the **Specify Table Types** page to identify the tables to use to define the mining structure.</span></span> <span data-ttu-id="88994-104">Если таблица не выбрана, она не будет использоваться для определения структуры интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="88994-104">If a table is not selected, it will not be used to define the mining structure.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="88994-105">Таблицы можно добавлять позже на вкладке **Структура интеллектуального анализа данных** в окне **Конструктор интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="88994-105">You can add tables later from the **Mining Structure** tab in **Data Mining Designer**.</span></span>  
  
 <span data-ttu-id="88994-106">**Дополнительные сведения:** [Вложенные таблицы (службы Analysis Services — интеллектуальный анализ данных)](data-mining/nested-tables-analysis-services-data-mining.md), [Мастер интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)](data-mining/data-mining-wizard-analysis-services-data-mining.md) и [Создание реляционной структуры интеллектуального анализа данных](data-mining/create-a-relational-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="88994-106">**For More Information:** [Nested Tables &#40;Analysis Services - Data Mining&#41;](data-mining/nested-tables-analysis-services-data-mining.md), [Data Mining Wizard &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Create a Relational Mining Structure](data-mining/create-a-relational-mining-structure.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="88994-107">Варианты</span><span class="sxs-lookup"><span data-stu-id="88994-107">Options</span></span>  
 <span data-ttu-id="88994-108">**Таблицы**</span><span class="sxs-lookup"><span data-stu-id="88994-108">**Tables**</span></span>  
 <span data-ttu-id="88994-109">Отображает таблицы в представлении источника данных, выбранном на странице **Выбор представления источников данных** данного мастера.</span><span class="sxs-lookup"><span data-stu-id="88994-109">Displays the tables in the data source view that you selected on the **Select Data Source View** page of the wizard.</span></span>  
  
 <span data-ttu-id="88994-110">**Ситуации**</span><span class="sxs-lookup"><span data-stu-id="88994-110">**Case**</span></span>  
 <span data-ttu-id="88994-111">Выберите таблицу для использования ее в качестве таблицы вариантов.</span><span class="sxs-lookup"><span data-stu-id="88994-111">Select one table to use as the case table.</span></span>  
  
 <span data-ttu-id="88994-112">**Вложенный**</span><span class="sxs-lookup"><span data-stu-id="88994-112">**Nested**</span></span>  
 <span data-ttu-id="88994-113">Выберите таблицы для использования в качестве вложенных таблиц.</span><span class="sxs-lookup"><span data-stu-id="88994-113">Select the tables to use as nested tables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="88994-114">У этих таблиц должна быть связь «многие к одному» с таблицей вариантов, а не «один-ко-многим».</span><span class="sxs-lookup"><span data-stu-id="88994-114">These tables must have a many-to-one relationship with the case table, not a one-to-many relationship.</span></span> <span data-ttu-id="88994-115">Необходимо определить эту связь в представлении источника данных, прежде чем можно будет выбрать таблицу в качестве вложенной.</span><span class="sxs-lookup"><span data-stu-id="88994-115">You must specify this relationship in the data source view before you can select the table as nested.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88994-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="88994-116">See Also</span></span>  
 <span data-ttu-id="88994-117">[Справка F1 мастера интеллектуального анализа данных &#40;Analysis Services — интеллектуальный анализ данных&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="88994-117">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="88994-118">[Выберите представление источника данных &#40;мастер интеллектуального анализа данных&#41;](select-data-source-view-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="88994-118">[Select Data Source View &#40;Data Mining Wizard&#41;](select-data-source-view-data-mining-wizard.md) </span></span>  
 [<span data-ttu-id="88994-119">Укажите обучающие данные &#40;мастер интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="88994-119">Specify the Training Data &#40;Data Mining Wizard&#41;</span></span>](specify-the-training-data-data-mining-wizard.md)  
  
  
