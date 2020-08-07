---
title: Создание измерения типа Currency | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- dimensions [Analysis Services], currency
- currency [Analysis Services]
- converting currency
- currency dimensions [Analysis Services]
ms.assetid: b1f037d1-ce47-4e47-a1c2-5ec9e781cff6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 91123fb5fda898e90056057114295335fbd1d32c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730997"
---
# <a name="create-a-currency-type-dimension"></a><span data-ttu-id="e5f30-102">Создание измерения типа Currency</span><span class="sxs-lookup"><span data-stu-id="e5f30-102">Create a Currency type Dimension</span></span>
  <span data-ttu-id="e5f30-103">В [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] службах измерение типа Currency — это измерение, атрибуты которого представляют собой список валют для целей финансовой отчетности.</span><span class="sxs-lookup"><span data-stu-id="e5f30-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], a currency type dimension is a dimension whose attributes represent a list of currencies for financial reporting purposes.</span></span>  
  
 <span data-ttu-id="e5f30-104">Измерение валюты позволяет добавлять возможности конвертации валюты в куб в службах [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5f30-104">A currency dimension lets you add currency conversion capabilities to a cube in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="e5f30-105">Чтобы добавить в куб конвертацию валюты, воспользуйтесь мастером бизнес-аналитики для определения команды скрипта многомерного выражения, которая конвертирует меры валюты в значения, соответствующие локали клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="e5f30-105">To add currency conversion to a cube, you use the Business Intelligence Wizard define a Multidimensional Expressions (MDX) script command that converts currency measures to values that are appropriate for the locale of the client application.</span></span> <span data-ttu-id="e5f30-106">Для создания скрипта многомерных выражений мастеру бизнес-аналитики необходимы следующие данные:</span><span class="sxs-lookup"><span data-stu-id="e5f30-106">To create this MDX script, the Business Intelligence Wizard needs the following information:</span></span>  
  
-   <span data-ttu-id="e5f30-107">Измерение валюты, которое представляет собой исходные валюты.</span><span class="sxs-lookup"><span data-stu-id="e5f30-107">A currency dimension that represents source currencies.</span></span> <span data-ttu-id="e5f30-108">(Данное измерение представляет собой исходное измерение валюты.)</span><span class="sxs-lookup"><span data-stu-id="e5f30-108">(This dimension is the source currency dimension.)</span></span>  
  
-   <span data-ttu-id="e5f30-109">Группа мер, которая представляет собой используемые валютные курсы.</span><span class="sxs-lookup"><span data-stu-id="e5f30-109">A measure group that represents the exchange rates that will be used.</span></span>  
  
 <span data-ttu-id="e5f30-110">На основании этих данных мастер бизнес-аналитики разработает проект конвертации валюты, определяющий подходящее измерение целевой валюты (измерение валюты, которое представляет собой целевые валюты).</span><span class="sxs-lookup"><span data-stu-id="e5f30-110">From this information, the Business Intelligence Wizard will design a currency conversion process that identifies the appropriate destination currency dimension (the currency dimension that represents destination currencies).</span></span> <span data-ttu-id="e5f30-111">В зависимости от числа конвертаций валюты, необходимых для выбранного решения бизнес-аналитики, мастер бизнес-аналитики может задать несколько измерений целевой валюты.</span><span class="sxs-lookup"><span data-stu-id="e5f30-111">Depending on the number of currency conversions that your business intelligence solution requires, the Business Intelligence Wizard can define multiple destination currency dimensions.</span></span> <span data-ttu-id="e5f30-112">Дополнительные сведения об определении конвертаций валюты см. в разделе [Конвертация валюты (службы Analysis Services)](../currency-conversions-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="e5f30-112">For more information about defining currency conversions, see [Currency Conversions &#40;Analysis Services&#41;](../currency-conversions-analysis-services.md).</span></span>  
  
 <span data-ttu-id="e5f30-113">Чтобы определить измерение как измерение валюты, установите для свойства `Type` измерения значение `Currency`.</span><span class="sxs-lookup"><span data-stu-id="e5f30-113">To identify a dimension as a currency dimension, set the `Type` property of the dimension to `Currency`.</span></span>  
  
## <a name="dimension-structure"></a><span data-ttu-id="e5f30-114">Структура измерения</span><span class="sxs-lookup"><span data-stu-id="e5f30-114">Dimension Structure</span></span>  
 <span data-ttu-id="e5f30-115">В измерении валюты содержится, по крайней мере, ключевой атрибут, определяющий отдельные валюты в таблице измерения для измерения валюты.</span><span class="sxs-lookup"><span data-stu-id="e5f30-115">A currency dimension contains, at least, a key attribute identifying individual currencies in the dimension table for the currency dimension.</span></span> <span data-ttu-id="e5f30-116">Значение ключевого атрибута отличается как в исходных, так и в целевых измерениях валюты:</span><span class="sxs-lookup"><span data-stu-id="e5f30-116">The value of the key attribute is different in both source and destination currency dimensions:</span></span>  
  
-   <span data-ttu-id="e5f30-117">Чтобы определить атрибут как ключевой атрибут исходного измерения валюты, установите для свойства `Type` атрибута значение `CurrencySource`.</span><span class="sxs-lookup"><span data-stu-id="e5f30-117">To identify an attribute as the key attribute of a source currency dimension, set the `Type` property of the attribute to `CurrencySource`.</span></span>  
  
-   <span data-ttu-id="e5f30-118">Чтобы определить атрибут как целевое измерение валюты, установите для свойства `Type` атрибута значение `CurrencyDestination`.</span><span class="sxs-lookup"><span data-stu-id="e5f30-118">To identify an attribute as the destination currency dimension, set the `Type` property of the attribute to `CurrencyDestination`.</span></span>  
  
 <span data-ttu-id="e5f30-119">В целях отчетности как исходное, так и целевое измерение валюты может содержать следующие необязательные атрибуты:</span><span class="sxs-lookup"><span data-stu-id="e5f30-119">For reporting purposes, both source and destination currency dimensions can optionally contain the following attributes:</span></span>  
  
-   <span data-ttu-id="e5f30-120">Атрибут названия валюты.</span><span class="sxs-lookup"><span data-stu-id="e5f30-120">A currency name attribute.</span></span>  
  
     <span data-ttu-id="e5f30-121">Чтобы определить атрибут как атрибут названия валюты, установите для свойства `Type` атрибута значение `CurrencyName`.</span><span class="sxs-lookup"><span data-stu-id="e5f30-121">To identify an attribute as a currency name attribute, set the `Type` property of the attribute to `CurrencyName`.</span></span>  
  
-   <span data-ttu-id="e5f30-122">Атрибут источника валюты.</span><span class="sxs-lookup"><span data-stu-id="e5f30-122">A currency source attribute.</span></span>  
  
     <span data-ttu-id="e5f30-123">Чтобы определить атрибут как атрибут источника валюты, установите для свойства `Type` атрибута значение `CurrencySource`.</span><span class="sxs-lookup"><span data-stu-id="e5f30-123">To identify an attribute as a currency source attribute, set the `Type` property of the attribute to `CurrencySource`.</span></span>  
  
-   <span data-ttu-id="e5f30-124">Код валюты, принятый Международной организацией по стандартизации (ISO).</span><span class="sxs-lookup"><span data-stu-id="e5f30-124">A currency International Standards Organization (ISO) code.</span></span>  
  
     <span data-ttu-id="e5f30-125">Чтобы определить атрибут как атрибут кода валюты ISO, установите для свойства `Type` атрибута значение `CurrencyIsoCode`.</span><span class="sxs-lookup"><span data-stu-id="e5f30-125">To identify an attribute as a currency ISO code attribute, set the `Type` property of the attribute to `CurrencyIsoCode`.</span></span>  
  
 <span data-ttu-id="e5f30-126">Дополнительные сведения о типах атрибутов см. в разделе [Настройка типов атрибутов](attribute-properties-configure-attribute-types.md).</span><span class="sxs-lookup"><span data-stu-id="e5f30-126">For more information about attribute types, see [Configure Attribute Types](attribute-properties-configure-attribute-types.md).</span></span>  
  
## <a name="defining-account-intelligence-with-the-business-intelligence-wizard"></a><span data-ttu-id="e5f30-127">Определение логики операций со счетами с помощью мастера бизнес-аналитики</span><span class="sxs-lookup"><span data-stu-id="e5f30-127">Defining Account Intelligence with the Business Intelligence Wizard</span></span>  
 <span data-ttu-id="e5f30-128">После определения измерения счетов и его добавления в куб можно, воспользовавшись мастером бизнес-аналитики, добавить функционал логики операций со счетами, например идентифицирующие типы учетной записи и типы сопоставления, к измерению.</span><span class="sxs-lookup"><span data-stu-id="e5f30-128">After you have defined an account dimension and added that dimension to a cube, you can use the Business Intelligence Wizard to add account intelligence functionality, such as identifying and mapping account types, to the dimension.</span></span> <span data-ttu-id="e5f30-129">Дополнительные сведения см. в разделе [Добавление логики операций со счетами к измерению](bi-wizard-add-account-intelligence-to-a-dimension.md).</span><span class="sxs-lookup"><span data-stu-id="e5f30-129">For more information, see [Add Account Intelligence to a Dimension](bi-wizard-add-account-intelligence-to-a-dimension.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5f30-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="e5f30-130">See Also</span></span>  
 <span data-ttu-id="e5f30-131">[Атрибуты и иерархии атрибутов](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="e5f30-131">[Attributes and Attribute Hierarchies](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span></span>  
 <span data-ttu-id="e5f30-132">[Справка F1 мастера бизнес-аналитики](../business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="e5f30-132">[Business Intelligence Wizard F1 Help](../business-intelligence-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="e5f30-133">Типы измерений</span><span class="sxs-lookup"><span data-stu-id="e5f30-133">Dimension Types</span></span>](../multidimensional-models-olap-logical-dimension-objects/database-dimension-properties-types.md)  
  
  
