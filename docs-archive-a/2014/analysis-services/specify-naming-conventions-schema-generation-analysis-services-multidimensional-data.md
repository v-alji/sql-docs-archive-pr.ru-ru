---
title: Определение соглашений об именовании (мастер формирования схем) (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.schemagenwizard.namingconventions.f1
ms.assetid: 02d830ea-5b1f-4485-9f94-d64b8bea592b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2e9588b49331934041cad888142d29d189fc1a7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666775"
---
# <a name="specify-naming-conventions-schema-generation-wizard-analysis-services---multidimensional-data"></a><span data-ttu-id="df919-102">Соглашения об именах (мастер формирования схем) (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="df919-102">Specify Naming Conventions (Schema Generation Wizard) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="df919-103">Страница **Соглашения о наименовании** для определения соглашений об именовании, которые мастер формирования схем будет использовать при создании объектов схемы.</span><span class="sxs-lookup"><span data-stu-id="df919-103">Use the **Specify Naming Conventions** page to define the naming conventions that the Schema Generation Wizard uses when creating schema objects.</span></span>  
  
## <a name="options"></a><span data-ttu-id="df919-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="df919-104">Options</span></span>  
 <span data-ttu-id="df919-105">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="df919-105">**Option**</span></span>  
 <span data-ttu-id="df919-106">Укажите соглашения об именовании для использования мастером.</span><span class="sxs-lookup"><span data-stu-id="df919-106">Specify the naming conventions for the wizard to use.</span></span> <span data-ttu-id="df919-107">В следующей таблице приводятся описания параметров.</span><span class="sxs-lookup"><span data-stu-id="df919-107">The following table describes the options you can specify.</span></span>  
  
|<span data-ttu-id="df919-108">Параметр</span><span class="sxs-lookup"><span data-stu-id="df919-108">Option</span></span>|<span data-ttu-id="df919-109">Описание</span><span class="sxs-lookup"><span data-stu-id="df919-109">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="df919-110">**Separator**</span><span class="sxs-lookup"><span data-stu-id="df919-110">**Separator**</span></span>|<span data-ttu-id="df919-111">Символ, разделяющий слова в имени объекта.</span><span class="sxs-lookup"><span data-stu-id="df919-111">Specifies the character that separates words in an object name.</span></span> <span data-ttu-id="df919-112">В столбце **Значение** выберите **Подчеркивание**, **Пробел**или **Нет**.</span><span class="sxs-lookup"><span data-stu-id="df919-112">In the **Value** column, select **Underscore**, **Space**, or **None**.</span></span> <span data-ttu-id="df919-113">Значение по умолчанию — **Подчеркивание**.</span><span class="sxs-lookup"><span data-stu-id="df919-113">The default is **Underscore**.</span></span>|  
|<span data-ttu-id="df919-114">**Префикс первичного ключевого столбца**</span><span class="sxs-lookup"><span data-stu-id="df919-114">**Primary key column prefix**</span></span>|<span data-ttu-id="df919-115">Определяет строку, которая предшествует имени каждого первичного ключевого столбца.</span><span class="sxs-lookup"><span data-stu-id="df919-115">Specifies the string to prefix the name of each primary key column.</span></span> <span data-ttu-id="df919-116">Значение по умолчанию — **PK**.</span><span class="sxs-lookup"><span data-stu-id="df919-116">The default is **PK**.</span></span>|  
|<span data-ttu-id="df919-117">**Префикс внешнего ключевого столбца**</span><span class="sxs-lookup"><span data-stu-id="df919-117">**Foreign key column prefix**</span></span>|<span data-ttu-id="df919-118">Определяет строку, которая предшествует имени каждого внешнего ключевого столбца.</span><span class="sxs-lookup"><span data-stu-id="df919-118">Specifies the string to prefix the name of each foreign key column.</span></span> <span data-ttu-id="df919-119">Значение по умолчанию — **FK**.</span><span class="sxs-lookup"><span data-stu-id="df919-119">The default is **FK**.</span></span>|  
|<span data-ttu-id="df919-120">**Суффикс имени атрибута**</span><span class="sxs-lookup"><span data-stu-id="df919-120">**Attribute name suffix**</span></span>|<span data-ttu-id="df919-121">Строка, добавляемая к имени каждого столбца атрибутов.</span><span class="sxs-lookup"><span data-stu-id="df919-121">Specifies the string to be appended to the name of each attribute column.</span></span> <span data-ttu-id="df919-122">Значение по умолчанию — **Name**.</span><span class="sxs-lookup"><span data-stu-id="df919-122">The default is **Name**.</span></span>|  
|<span data-ttu-id="df919-123">**Суффикс пользовательской свертки**</span><span class="sxs-lookup"><span data-stu-id="df919-123">**Custom rollup suffix**</span></span>|<span data-ttu-id="df919-124">Строка, добавляемая к имени каждого столбца специальной свертки.</span><span class="sxs-lookup"><span data-stu-id="df919-124">Specifies the string to be appended to the name of each rollup column.</span></span> <span data-ttu-id="df919-125">Значение по умолчанию — **CustomRollup**.</span><span class="sxs-lookup"><span data-stu-id="df919-125">The default is **CustomRollup**.</span></span>|  
|<span data-ttu-id="df919-126">**Суффикс свойств пользовательской свертки**</span><span class="sxs-lookup"><span data-stu-id="df919-126">**Custom rollup Properties suffix**</span></span>|<span data-ttu-id="df919-127">Строка, добавляемая к имени каждого столбца свойств специальной свертки.</span><span class="sxs-lookup"><span data-stu-id="df919-127">Specifies the string to be appended to the name of each rollup property column.</span></span> <span data-ttu-id="df919-128">Значение по умолчанию — **CustomRollupProperties**.</span><span class="sxs-lookup"><span data-stu-id="df919-128">The default is **CustomRollupProperties**.</span></span>|  
|<span data-ttu-id="df919-129">**Суффикс унарного оператора**</span><span class="sxs-lookup"><span data-stu-id="df919-129">**Unary operator suffix**</span></span>|<span data-ttu-id="df919-130">Строка, добавляемая к имени каждого столбца унарного оператора.</span><span class="sxs-lookup"><span data-stu-id="df919-130">Specifies the string to be appended to the name of each unary operator column.</span></span> <span data-ttu-id="df919-131">Значение по умолчанию — **UnaryOperator**.</span><span class="sxs-lookup"><span data-stu-id="df919-131">The default is **UnaryOperator**.</span></span>|  
  
 <span data-ttu-id="df919-132">**Значение**</span><span class="sxs-lookup"><span data-stu-id="df919-132">**Value**</span></span>  
 <span data-ttu-id="df919-133">Укажите значение параметра, указанного в поле **Параметр** для использования при создании схемы.</span><span class="sxs-lookup"><span data-stu-id="df919-133">Specify a value for the option specified in **Option** that you want to use when the schema is generated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df919-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="df919-134">See Also</span></span>  
 <span data-ttu-id="df919-135">[Справка F1 мастера формирования схем &#40;Analysis Services многомерных данных&#41;](schema-generation-wizard-f1-help-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="df919-135">[Schema Generation Wizard F1 Help &#40;Analysis Services - Multidimensional Data&#41;](schema-generation-wizard-f1-help-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="df919-136">Analysis Services мастера &#40;многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="df919-136">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
