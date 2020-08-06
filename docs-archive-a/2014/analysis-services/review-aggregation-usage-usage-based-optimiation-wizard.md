---
title: Обзор использования статистической обработки (мастер оптимизации с на основе использования) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.storagedesignwizard.reviewaggregationusage.f1
ms.assetid: 49ce2094-c4dc-4e46-8cef-c17c5db084ca
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5ef9f900e64858515db226d1f9b864874a4ba827
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656643"
---
# <a name="review-aggregation-usage-usage-based-optimiation-wizard"></a><span data-ttu-id="6c857-102">Просмотр использования статистической обработки (мастер оптимизации с учетом использования)</span><span class="sxs-lookup"><span data-stu-id="6c857-102">Review Aggregation Usage (Usage-Based Optimiation Wizard)</span></span>
  <span data-ttu-id="6c857-103">Используйте страницу **Просмотр использования статистической обработки** для настройки параметров статистической обработки.</span><span class="sxs-lookup"><span data-stu-id="6c857-103">Use the **Review Aggregation Usage** page to configure aggregation usage settings.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6c857-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="6c857-104">Options</span></span>  
 <span data-ttu-id="6c857-105">**Default**</span><span class="sxs-lookup"><span data-stu-id="6c857-105">**Default**</span></span>  
 <span data-ttu-id="6c857-106">Выберите, чтобы присвоить параметру статистической обработки атрибута значение «По умолчанию».</span><span class="sxs-lookup"><span data-stu-id="6c857-106">Select to set the aggregation usage setting for the attribute to Default.</span></span> <span data-ttu-id="6c857-107">Используя данный параметр, конструктор применяет правило по умолчанию, основанное на типе атрибута и измерения.</span><span class="sxs-lookup"><span data-stu-id="6c857-107">By using this setting, the designer applies a default rule based on the type of attribute and dimension.</span></span>  
  
 <span data-ttu-id="6c857-108">**Полное**</span><span class="sxs-lookup"><span data-stu-id="6c857-108">**Full**</span></span>  
 <span data-ttu-id="6c857-109">Выберите этот вариант, чтобы присвоить параметру использования статистической обработки атрибута значение «Полная».</span><span class="sxs-lookup"><span data-stu-id="6c857-109">Select to set the aggregation usage setting for the attribute to Full.</span></span> <span data-ttu-id="6c857-110">При использовании данного параметра, каждый агрегат для куба должен включать данный атрибут или связанный атрибут, находящийся ниже в цепочке атрибутов.</span><span class="sxs-lookup"><span data-stu-id="6c857-110">By using this setting, every aggregation for the cube must include this attribute or a related attribute that is lower in the attribute chain.</span></span> <span data-ttu-id="6c857-111">Если атрибут содержит большое количество элементов, то для использования статистической обработки следует избегать значения «Полная».</span><span class="sxs-lookup"><span data-stu-id="6c857-111">The Full aggregation usage setting should be avoided when an attribute contains many members.</span></span> <span data-ttu-id="6c857-112">При назначении нескольким атрибутам или атрибутам, включающим множество элементов, данный параметр может привести к тому, что агрегат не будет создан из-за избыточного размера.</span><span class="sxs-lookup"><span data-stu-id="6c857-112">If specified for multiple attributes or attributes that have many members, this setting might prevent aggregations from being designed because of excessive size.</span></span>  
  
 <span data-ttu-id="6c857-113">**None**</span><span class="sxs-lookup"><span data-stu-id="6c857-113">**None**</span></span>  
 <span data-ttu-id="6c857-114">Выберите, чтобы присвоить параметру статистической обработки атрибута значение «Нет».</span><span class="sxs-lookup"><span data-stu-id="6c857-114">Select to set the aggregation usage setting for the attribute to None.</span></span> <span data-ttu-id="6c857-115">При использовании этого параметра, ни одна статистическая обработка для куба не может включать данный атрибут.</span><span class="sxs-lookup"><span data-stu-id="6c857-115">By using this setting, no aggregation for the cube can include this attribute.</span></span>  
  
 <span data-ttu-id="6c857-116">**Неограниченный**</span><span class="sxs-lookup"><span data-stu-id="6c857-116">**Unrestricted**</span></span>  
 <span data-ttu-id="6c857-117">Выберите этот параметр, чтобы присвоить параметру использования статистической обработки атрибута значение «Unrestricted».</span><span class="sxs-lookup"><span data-stu-id="6c857-117">Select to set the aggregation usage setting for the attribute to Unrestricted.</span></span> <span data-ttu-id="6c857-118">При использовании этого параметра к конструктору агрегатов не применяются никакие ограничения.</span><span class="sxs-lookup"><span data-stu-id="6c857-118">By using this setting, no restrictions are put on the aggregation designer.</span></span> <span data-ttu-id="6c857-119">Тем не менее необходимо провести оценку, может ли этот атрибут использоваться в качестве агрегата.</span><span class="sxs-lookup"><span data-stu-id="6c857-119">However, the attribute must still be evaluated to determine whether it is a valuable aggregation candidate.</span></span>  
  
 <span data-ttu-id="6c857-120">**Установить все значения по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="6c857-120">**Set All to Default**</span></span>  
 <span data-ttu-id="6c857-121">Выберите, чтобы присвоить для всех атрибутов настройки статистической обработки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6c857-121">Select to set the aggregation usage settings for all attributes to Default.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c857-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="6c857-122">See Also</span></span>  
 <span data-ttu-id="6c857-123">[Справка F1 мастера статистических схем](aggregation-design-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="6c857-123">[Aggregation Design Wizard F1 Help](aggregation-design-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="6c857-124">Analysis Services мастера &#40;многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="6c857-124">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
