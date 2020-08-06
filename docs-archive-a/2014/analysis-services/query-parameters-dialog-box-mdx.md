---
title: Диалоговое окно "Параметры запроса" (многомерные выражения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.sqlserverstudio.queryparameters.mdx.f1
ms.assetid: e69b9542-7b54-42bf-b2de-c091e81af7ee
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1eee07ffefc0b2d7c6115245e12d09c5ac6eb4a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738930"
---
# <a name="query-parameters-dialog-box-mdx"></a><span data-ttu-id="9a5f4-102">Диалоговое окно «Параметры запроса» (MDX)</span><span class="sxs-lookup"><span data-stu-id="9a5f4-102">Query Parameters Dialog Box (MDX)</span></span>
  <span data-ttu-id="9a5f4-103">Используйте диалоговое окно **Параметры запроса** в средах [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] и [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] для добавления параметров к запросам многомерных выражений, используемым для определения наборов, измерений и вложенных кубов.</span><span class="sxs-lookup"><span data-stu-id="9a5f4-103">Use the **Query Parameters** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to add parameters to MDX queries that are used to define sets, dimensions, and subcubes.</span></span> <span data-ttu-id="9a5f4-104">Чтобы открыть диалоговое окно **Параметры запроса** , щелкните значок **Параметры** в диалоговом окне **Построитель запросов MDX** .</span><span class="sxs-lookup"><span data-stu-id="9a5f4-104">You can display the **Query Parameters** dialog box by clicking the **Parameters** icon in the **MDX query builder** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9a5f4-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="9a5f4-105">Options</span></span>  
 <span data-ttu-id="9a5f4-106">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="9a5f4-106">**Parameter**</span></span>  
 <span data-ttu-id="9a5f4-107">Введите имя параметра, чтобы начать создание нового параметра, или измените имя существующего параметра.</span><span class="sxs-lookup"><span data-stu-id="9a5f4-107">Type a parameter name to begin creating a new parameter, or edit the name of an existing parameter.</span></span>  
  
 <span data-ttu-id="9a5f4-108">**Измерение**</span><span class="sxs-lookup"><span data-stu-id="9a5f4-108">**Dimension**</span></span>  
 <span data-ttu-id="9a5f4-109">Выберите существующее измерение из списка.</span><span class="sxs-lookup"><span data-stu-id="9a5f4-109">Choose an existing dimension from the list.</span></span>  
  
 <span data-ttu-id="9a5f4-110">**Иерархия**</span><span class="sxs-lookup"><span data-stu-id="9a5f4-110">**Hierarchy**</span></span>  
 <span data-ttu-id="9a5f4-111">Выберите из списка иерархию, если параметр применяется к конкретной иерархии.</span><span class="sxs-lookup"><span data-stu-id="9a5f4-111">Choose a hierarchy from the list, if the parameter is applied to a specific hierarchy.</span></span>  
  
 <span data-ttu-id="9a5f4-112">**Несколько значений**</span><span class="sxs-lookup"><span data-stu-id="9a5f4-112">**Multiple values**</span></span>  
 <span data-ttu-id="9a5f4-113">Описание</span><span class="sxs-lookup"><span data-stu-id="9a5f4-113">Description</span></span>  
  
 <span data-ttu-id="9a5f4-114">**Default**</span><span class="sxs-lookup"><span data-stu-id="9a5f4-114">**Default**</span></span>  
 <span data-ttu-id="9a5f4-115">Указывает значение по умолчанию для параметра, если оно имеется.</span><span class="sxs-lookup"><span data-stu-id="9a5f4-115">Indicate the default value for the parameter, if any.</span></span> <span data-ttu-id="9a5f4-116">По умолчанию значение не присваивается.</span><span class="sxs-lookup"><span data-stu-id="9a5f4-116">By default, no value is assigned.</span></span>  
  
 <span data-ttu-id="9a5f4-117">**Другое**</span><span class="sxs-lookup"><span data-stu-id="9a5f4-117">**Other**</span></span>  
 <span data-ttu-id="9a5f4-118">Используйте клавишу Delete или кнопку «X» для удаления параметров, которые уже не используются.</span><span class="sxs-lookup"><span data-stu-id="9a5f4-118">Use the Delete key or X button to remove parameters you no long use.</span></span> <span data-ttu-id="9a5f4-119">Для перемещения выделенного параметра вверх или вниз в списке используйте клавиши со стрелками.</span><span class="sxs-lookup"><span data-stu-id="9a5f4-119">Use the arrow keys to move the highlighted parameter up or down in the list.</span></span> <span data-ttu-id="9a5f4-120">К сортировке параметров применяются следующие правила:</span><span class="sxs-lookup"><span data-stu-id="9a5f4-120">The following rules apply to ordering of parameters:</span></span>  
  
-   <span data-ttu-id="9a5f4-121">Определение областей действия параметров.</span><span class="sxs-lookup"><span data-stu-id="9a5f4-121">Parameter scoping.</span></span>  
  
-   <span data-ttu-id="9a5f4-122">Порядок параметров.</span><span class="sxs-lookup"><span data-stu-id="9a5f4-122">Parameter order.</span></span>  
  
  
