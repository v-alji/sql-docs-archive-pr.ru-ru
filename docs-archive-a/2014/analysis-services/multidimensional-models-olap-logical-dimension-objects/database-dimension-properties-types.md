---
title: Типы измерений | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- time dimensions [Analysis Services]
- quantitative dimensions [Analysis Services]
- BillOfMaterials dimension [Analysis Services]
- geography dimensions
- utility dimensions [Analysis Services]
- channel dimensions
- dimensions [Analysis Services], types
- products dimensions [Analysis Services]
- account dimensions [Analysis Services]
- organization dimensions
- currency dimensions [Analysis Services]
- rates dimensions
- promotion dimensions
- scenario dimensions [Analysis Services]
- customers dimensions [Analysis Services]
- Type property
ms.assetid: bd3195da-e762-4c98-b643-34c76e842343
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5e0c16a57081aa1d9ed3cc6964d1f17fa7135986
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669134"
---
# <a name="dimension-types"></a><span data-ttu-id="d114d-102">Типы измерений</span><span class="sxs-lookup"><span data-stu-id="d114d-102">Dimension Types</span></span>
  <span data-ttu-id="d114d-103">Настройка свойства `Type` предоставляет данные о содержимом измерения серверу и клиентским приложениям.</span><span class="sxs-lookup"><span data-stu-id="d114d-103">The `Type` property setting provides information about the contents of a dimension to server and client applications.</span></span> <span data-ttu-id="d114d-104">В некоторых случаях настройка `Type` предоставляет клиентским приложениям только справочные сведения и является необязательной.</span><span class="sxs-lookup"><span data-stu-id="d114d-104">In some cases, the `Type` setting only provides guidance for client applications and is optional.</span></span> <span data-ttu-id="d114d-105">В других случаях, например для измерений `Accounts` или `Time`, настройка свойства `Type` для измерения и его атрибутов определяет конкретные режимы, относящиеся к серверу, и может быть необходимой для реализации определенных режимов куба.</span><span class="sxs-lookup"><span data-stu-id="d114d-105">In other cases, such as `Accounts` or `Time` dimensions, the `Type` property settings for the dimension and its attributes determine specific server-based behaviors and may be required to implement certain behaviors in the cube.</span></span> <span data-ttu-id="d114d-106">Например, для свойства `Type` измерения можно установить значение `Accounts`, тем самым указывая клиентским приложениям, что в стандартном измерении содержатся атрибуты счетов. </span><span class="sxs-lookup"><span data-stu-id="d114d-106">For example, the `Type` property of a dimension can be set to `Accounts` to indicate to client applications that the standard dimension contains account attributes.</span></span> <span data-ttu-id="d114d-107">Дополнительные сведения об измерениях времени, счетов и валют см. в разделе [Создание измерения типа Date](../multidimensional-models/database-dimensions-create-a-date-type-dimension.md), [Создание учетной записи типа "финансовый" измерения "родители-потомки](../multidimensional-models/database-dimensions-finance-account-of-parent-child-type.md)" и [Создание измерения типа "Валюта](../multidimensional-models/database-dimensions-create-a-currency-type-dimension.md)".</span><span class="sxs-lookup"><span data-stu-id="d114d-107">For more information about time, account, and currency dimensions, see [Create a Date type Dimension](../multidimensional-models/database-dimensions-create-a-date-type-dimension.md), [Create a Finance Account of parent-child type Dimension](../multidimensional-models/database-dimensions-finance-account-of-parent-child-type.md), and [Create a Currency type Dimension](../multidimensional-models/database-dimensions-create-a-currency-type-dimension.md).</span></span>  
  
 <span data-ttu-id="d114d-108">Настройка по умолчанию для типа измерения равна `Regular`, при этом не делаются никакие предположения в отношении содержимого измерения.</span><span class="sxs-lookup"><span data-stu-id="d114d-108">The default setting for the dimension type is `Regular`, which makes no assumptions about the contents of the dimension.</span></span> <span data-ttu-id="d114d-109">Эта настройка применяется по умолчанию для всех измерений при первоначальном определении измерения, если только при определении измерения с помощью мастера измерений не указывается измерение `Time`.</span><span class="sxs-lookup"><span data-stu-id="d114d-109">This is the default setting for all dimensions when you initially define a dimension unless you specify `Time` when defining the dimension using the Dimension Wizard.</span></span> <span data-ttu-id="d114d-110">Необходимо также оставить `Regular` как тип измерения, если мастер измерений не предоставляет список соответствующих типов для типов измерения.</span><span class="sxs-lookup"><span data-stu-id="d114d-110">You should also leave `Regular` as the dimension type if the Dimension Wizard does not list an appropriate type for Dimension type.</span></span>  
  
## <a name="available-dimension-types"></a><span data-ttu-id="d114d-111">Доступные типы измерений</span><span class="sxs-lookup"><span data-stu-id="d114d-111">Available Dimension Types</span></span>  
 <span data-ttu-id="d114d-112">В следующей таблице описаны типы измерений, доступные в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d114d-112">The following table describes the dimension types available in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
|<span data-ttu-id="d114d-113">Тип измерения</span><span class="sxs-lookup"><span data-stu-id="d114d-113">Dimension type</span></span>|<span data-ttu-id="d114d-114">Описание</span><span class="sxs-lookup"><span data-stu-id="d114d-114">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="d114d-115">Регулярно</span><span class="sxs-lookup"><span data-stu-id="d114d-115">Regular</span></span>|<span data-ttu-id="d114d-116">Измерение, тип которого не был изменен на специальный тип измерения. </span><span class="sxs-lookup"><span data-stu-id="d114d-116">A dimension whose type has not been set to a special dimension type.</span></span>|  
|<span data-ttu-id="d114d-117">Time</span><span class="sxs-lookup"><span data-stu-id="d114d-117">Time</span></span>|<span data-ttu-id="d114d-118">Измерение, атрибуты которого представляют периоды времени, например годы, семестры, кварталы, месяцы и дни.</span><span class="sxs-lookup"><span data-stu-id="d114d-118">A dimension whose attributes represent time periods, such as years, semesters, quarters, months, and days.</span></span>|  
|<span data-ttu-id="d114d-119">План</span><span class="sxs-lookup"><span data-stu-id="d114d-119">Organization</span></span>|<span data-ttu-id="d114d-120">Измерение, атрибуты которого представляют сведения об организации, например сотрудниках или филиалах.</span><span class="sxs-lookup"><span data-stu-id="d114d-120">A dimension whose attributes represent organizational information, such as employees or subsidiaries.</span></span>|  
|<span data-ttu-id="d114d-121">Geography</span><span class="sxs-lookup"><span data-stu-id="d114d-121">Geography</span></span>|<span data-ttu-id="d114d-122">Измерение, атрибуты которого представляют географические сведения, например города или почтовые индексы.</span><span class="sxs-lookup"><span data-stu-id="d114d-122">A dimension whose attributes represent geographic information, such as cities or postal codes.</span></span>|  
|<span data-ttu-id="d114d-123">Измерение ведомости материалов</span><span class="sxs-lookup"><span data-stu-id="d114d-123">BillOfMaterials</span></span>|<span data-ttu-id="d114d-124">Измерение, атрибуты которого представляют сведения по описи или производственные данные, например списки деталей для изделий.</span><span class="sxs-lookup"><span data-stu-id="d114d-124">A dimension whose attributes represent inventory or manufacturing information, such as parts lists for products.</span></span>|  
|<span data-ttu-id="d114d-125">Учетные записи</span><span class="sxs-lookup"><span data-stu-id="d114d-125">Accounts</span></span>|<span data-ttu-id="d114d-126">Измерение, атрибуты которого представляют диаграмму счетов для финансовой отчетности.</span><span class="sxs-lookup"><span data-stu-id="d114d-126">A dimension whose attributes represent a chart of accounts for financial reporting purposes.</span></span>|  
|<span data-ttu-id="d114d-127">Клиенты</span><span class="sxs-lookup"><span data-stu-id="d114d-127">Customers</span></span>|<span data-ttu-id="d114d-128">Измерение, атрибуты которого представляют сведения о заказчиках или контактные данные.</span><span class="sxs-lookup"><span data-stu-id="d114d-128">A dimension whose attributes represent customer or contact information.</span></span>|  
|<span data-ttu-id="d114d-129">Продукты</span><span class="sxs-lookup"><span data-stu-id="d114d-129">Products</span></span>|<span data-ttu-id="d114d-130">Измерение, атрибуты которого представляют сведения о продуктах.</span><span class="sxs-lookup"><span data-stu-id="d114d-130">A dimension whose attributes represent product information.</span></span>|  
|<span data-ttu-id="d114d-131">Сценарий</span><span class="sxs-lookup"><span data-stu-id="d114d-131">Scenario</span></span>|<span data-ttu-id="d114d-132">Измерение, атрибуты которого представляют сведения о планах или данные о стратегическом анализе.</span><span class="sxs-lookup"><span data-stu-id="d114d-132">A dimension whose attributes represent planning or strategic analysis information.</span></span>|  
|<span data-ttu-id="d114d-133">Количественное измерение</span><span class="sxs-lookup"><span data-stu-id="d114d-133">Quantitative</span></span>|<span data-ttu-id="d114d-134">Измерение, атрибуты которого представляют количественные данные.</span><span class="sxs-lookup"><span data-stu-id="d114d-134">A dimension whose attributes represent quantitative information.</span></span>|  
|<span data-ttu-id="d114d-135">Служебная программа</span><span class="sxs-lookup"><span data-stu-id="d114d-135">Utility</span></span>|<span data-ttu-id="d114d-136">Измерение, атрибуты которого представляют прочие сведения.</span><span class="sxs-lookup"><span data-stu-id="d114d-136">A dimension whose attributes represent miscellaneous information.</span></span>|  
|<span data-ttu-id="d114d-137">Валюта</span><span class="sxs-lookup"><span data-stu-id="d114d-137">Currency</span></span>|<span data-ttu-id="d114d-138">Измерение, атрибуты которого содержат данные валюты и метаданные.</span><span class="sxs-lookup"><span data-stu-id="d114d-138">This type of dimension contains currency data and metadata.</span></span>|  
|<span data-ttu-id="d114d-139">Изменения курсов</span><span class="sxs-lookup"><span data-stu-id="d114d-139">Rates</span></span>|<span data-ttu-id="d114d-140">Измерение, атрибуты которого представляют данные о курсе обмена валюты.</span><span class="sxs-lookup"><span data-stu-id="d114d-140">A dimension whose attributes represent currency rate information.</span></span>|  
|<span data-ttu-id="d114d-141">Channel</span><span class="sxs-lookup"><span data-stu-id="d114d-141">Channel</span></span>|<span data-ttu-id="d114d-142">Измерение, атрибуты которого представляют данные о каналах.</span><span class="sxs-lookup"><span data-stu-id="d114d-142">A dimension whose attributes represent channel information.</span></span>|  
|<span data-ttu-id="d114d-143">Promotion</span><span class="sxs-lookup"><span data-stu-id="d114d-143">Promotion</span></span>|<span data-ttu-id="d114d-144">Измерение, атрибуты которого представляют сведения об акциях по продвижению.</span><span class="sxs-lookup"><span data-stu-id="d114d-144">A dimension whose attributes represent marketing promotion information.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d114d-145">См. также:</span><span class="sxs-lookup"><span data-stu-id="d114d-145">See Also</span></span>  
 <span data-ttu-id="d114d-146">[Создание измерения с помощью существующей таблицы](../multidimensional-models/create-a-dimension-by-using-an-existing-table.md) </span><span class="sxs-lookup"><span data-stu-id="d114d-146">[Create a Dimension by Using an Existing Table](../multidimensional-models/create-a-dimension-by-using-an-existing-table.md) </span></span>  
 [<span data-ttu-id="d114d-147">Измерения (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="d114d-147">Dimensions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimensions-analysis-services-multidimensional-data.md)  
  
  
