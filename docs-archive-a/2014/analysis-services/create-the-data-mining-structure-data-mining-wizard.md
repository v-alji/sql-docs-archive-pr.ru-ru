---
title: Создание структуры интеллектуального анализа данных (мастер интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.dmwizard.selectminingtechnique.f1
ms.assetid: d1ff17b2-fff3-4ed7-a5d6-42d131e59f93
author: minewiskan
ms.author: owend
ms.openlocfilehash: c9f738cff974bc0064fc9e93c86221f0b10c6e80
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658577"
---
# <a name="create-the-data-mining-structure-data-mining-wizard"></a><span data-ttu-id="cd624-102">Создание структуры интеллектуального анализа данных (мастер интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="cd624-102">Create the Data Mining Structure (Data Mining Wizard)</span></span>
  <span data-ttu-id="cd624-103">Структуру интеллектуального анализа данных и при необходимости связанную с ней модель интеллектуального анализа данных можно создать с помощью страницы **Создание структуры интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="cd624-103">Use the **Create the Data Mining Structure** page to create a data mining structure and optionally create an associated mining model.</span></span>  
  
 <span data-ttu-id="cd624-104">При создании модели интеллектуального анализа данных необходимо также указать применяемый алгоритм интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="cd624-104">If you choose to create a mining model, you must also specify the data mining algorithm that you want to use.</span></span> <span data-ttu-id="cd624-105">Если создается только структура, модель интеллектуального анализа данных можно добавить к структуре позже.</span><span class="sxs-lookup"><span data-stu-id="cd624-105">If you create only the structure now, you can add a mining model to the structure later.</span></span>  
  
 <span data-ttu-id="cd624-106">**Дополнительные сведения:** [Алгоритмы интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)](data-mining/data-mining-algorithms-analysis-services-data-mining.md), [Мастер интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)](data-mining/data-mining-wizard-analysis-services-data-mining.md) и [Создание реляционной структуры интеллектуального анализа данных](data-mining/create-a-relational-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="cd624-106">**For More Information:** [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md), [Data Mining Wizard &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Create a Relational Mining Structure](data-mining/create-a-relational-mining-structure.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="cd624-107">Варианты</span><span class="sxs-lookup"><span data-stu-id="cd624-107">Options</span></span>  
 <span data-ttu-id="cd624-108">**Создать структуру и модель интеллектуального анализа данных**</span><span class="sxs-lookup"><span data-stu-id="cd624-108">**Create mining structure with a mining model**</span></span>  
 <span data-ttu-id="cd624-109">Выберите, чтобы создать структуру интеллектуального анализа данных, а затем — связанную с ней модель.</span><span class="sxs-lookup"><span data-stu-id="cd624-109">Select to create a mining structure and then create an associated model.</span></span>  
  
 <span data-ttu-id="cd624-110">**Какой метод интеллектуального анализа данных будет использоваться?**</span><span class="sxs-lookup"><span data-stu-id="cd624-110">**Which data mining technique do you want to use?**</span></span>  
 <span data-ttu-id="cd624-111">Выберите алгоритм интеллектуального анализа данных, который будет использоваться в этой модели.</span><span class="sxs-lookup"><span data-stu-id="cd624-111">Select the data mining algorithm to use with this model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cd624-112">Список алгоритмов заполняется из экземпляра служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , в котором создается структура интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="cd624-112">The list of algorithms is populated from the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] on which you are creating the mining structure.</span></span> <span data-ttu-id="cd624-113">Если сервер недоступен, будут доступны только алгоритмы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cd624-113">If the server is not available, only the default algorithms will be available.</span></span>  
  
 <span data-ttu-id="cd624-114">**Создать структуру интеллектуального анализа данных без моделей**</span><span class="sxs-lookup"><span data-stu-id="cd624-114">**Create mining structure with no models**</span></span>  
 <span data-ttu-id="cd624-115">Выберите этот параметр, чтобы создать только структуру интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="cd624-115">Select to create only a mining structure.</span></span>  
  
 <span data-ttu-id="cd624-116">**Описание**</span><span class="sxs-lookup"><span data-stu-id="cd624-116">**Description**</span></span>  
 <span data-ttu-id="cd624-117">Отображает описание выбранного алгоритма.</span><span class="sxs-lookup"><span data-stu-id="cd624-117">Displays a description of the selected algorithm.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd624-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="cd624-118">See Also</span></span>  
 <span data-ttu-id="cd624-119">[Справка F1 мастера интеллектуального анализа данных &#40;Analysis Services — интеллектуальный анализ данных&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="cd624-119">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="cd624-120">[Выберите представление источника данных &#40;мастер интеллектуального анализа данных&#41;](select-data-source-view-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="cd624-120">[Select Data Source View &#40;Data Mining Wizard&#41;](select-data-source-view-data-mining-wizard.md) </span></span>  
 [<span data-ttu-id="cd624-121">Выберите метод определения &#40;мастер интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="cd624-121">Select the Definition Method &#40;Data Mining Wizard&#41;</span></span>](select-the-definition-method-data-mining-wizard.md)  
  
  
