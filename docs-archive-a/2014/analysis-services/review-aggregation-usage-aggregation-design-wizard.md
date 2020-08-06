---
title: Обзор использования статистической обработки (мастер статистических схем) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.aggregationdesignwizard.reviewusage.f1
ms.assetid: 107ee872-3df2-4931-b56c-af11e38f6745
author: minewiskan
ms.author: owend
ms.openlocfilehash: afbb02dae64f3f7ebd57065c3ff8a7d1e202dcf2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656644"
---
# <a name="review-aggregation-usage-aggregation-design-wizard"></a><span data-ttu-id="e00d2-102">Просмотр использования статистической обработки (мастер статистических схем)</span><span class="sxs-lookup"><span data-stu-id="e00d2-102">Review Aggregation Usage (Aggregation Design Wizard)</span></span>
  <span data-ttu-id="e00d2-103">Используйте страницу **Просмотр использования статистической обработки** для настройки параметров статистической обработки.</span><span class="sxs-lookup"><span data-stu-id="e00d2-103">Use the **Review Aggregation Usage** page to configure aggregation usage settings.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e00d2-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="e00d2-104">Options</span></span>  
 <span data-ttu-id="e00d2-105">**Default**</span><span class="sxs-lookup"><span data-stu-id="e00d2-105">**Default**</span></span>  
 <span data-ttu-id="e00d2-106">Выберите, чтобы присвоить параметру статистической обработки атрибута значение «По умолчанию».</span><span class="sxs-lookup"><span data-stu-id="e00d2-106">Select to set the aggregation usage setting for the attribute to Default.</span></span> <span data-ttu-id="e00d2-107">Используя данный параметр, конструктор применяет правило по умолчанию, основанное на типе атрибута и измерения.</span><span class="sxs-lookup"><span data-stu-id="e00d2-107">By using this setting, the designer applies a default rule based on the type of attribute and dimension.</span></span>  
  
 `Full`  
 <span data-ttu-id="e00d2-108">Выберите, чтобы присвоить параметру статистической обработки атрибута значение `Full`.</span><span class="sxs-lookup"><span data-stu-id="e00d2-108">Select to set the aggregation usage setting for the attribute to `Full`.</span></span> <span data-ttu-id="e00d2-109">При использовании данного параметра, каждый агрегат для куба должен включать данный атрибут или связанный атрибут, находящийся ниже в цепочке атрибутов.</span><span class="sxs-lookup"><span data-stu-id="e00d2-109">By using this setting, every aggregation for the cube must include this attribute or a related attribute that is lower in the attribute chain.</span></span> <span data-ttu-id="e00d2-110">Если атрибут содержит большое количество элементов, следует избегать использования параметра статистической обработки `Full`.</span><span class="sxs-lookup"><span data-stu-id="e00d2-110">The `Full` aggregation usage setting should be avoided when an attribute contains many members.</span></span> <span data-ttu-id="e00d2-111">При назначении нескольким атрибутам или атрибутам, включающим множество элементов, данный параметр может привести к тому, что агрегат не будет создан из-за избыточного размера.</span><span class="sxs-lookup"><span data-stu-id="e00d2-111">If specified for multiple attributes or attributes that have many members, this setting might prevent aggregations from being designed because of excessive size.</span></span>  
  
 <span data-ttu-id="e00d2-112">**None**</span><span class="sxs-lookup"><span data-stu-id="e00d2-112">**None**</span></span>  
 <span data-ttu-id="e00d2-113">Выберите, чтобы присвоить параметру статистической обработки атрибута значение «Нет».</span><span class="sxs-lookup"><span data-stu-id="e00d2-113">Select to set the aggregation usage setting for the attribute to None.</span></span> <span data-ttu-id="e00d2-114">При использовании этого параметра, ни одна статистическая обработка для куба не может включать данный атрибут.</span><span class="sxs-lookup"><span data-stu-id="e00d2-114">By using this setting, no aggregation for the cube can include this attribute.</span></span>  
  
 `Unrestricted`  
 <span data-ttu-id="e00d2-115">Выберите, чтобы присвоить параметру статистической обработки атрибута значение `Unrestricted`.</span><span class="sxs-lookup"><span data-stu-id="e00d2-115">Select to set the aggregation usage setting for the attribute to `Unrestricted`.</span></span> <span data-ttu-id="e00d2-116">При использовании этого параметра к конструктору агрегатов не применяются никакие ограничения; тем не менее необходимо провести оценку, может ли этот атрибут использоваться в качестве агрегата.</span><span class="sxs-lookup"><span data-stu-id="e00d2-116">By using this setting, no restrictions are put on the aggregation designer; however, the attribute must still be evaluated to determine whether it is a valuable aggregation candidate.</span></span>  
  
 <span data-ttu-id="e00d2-117">**Установить все значения по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="e00d2-117">**Set All to Default**</span></span>  
 <span data-ttu-id="e00d2-118">Выберите, чтобы присвоить для всех атрибутов настройки статистической обработки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e00d2-118">Select to set the aggregation usage settings for all attributes to Default.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e00d2-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="e00d2-119">See Also</span></span>  
 <span data-ttu-id="e00d2-120">[Справка F1 мастера статистических схем](aggregation-design-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="e00d2-120">[Aggregation Design Wizard F1 Help](aggregation-design-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="e00d2-121">Analysis Services мастера &#40;многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="e00d2-121">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
