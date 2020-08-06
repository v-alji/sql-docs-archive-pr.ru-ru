---
title: Создание измерения путем создания таблицы, не являющейся таблицей времени, в источнике данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data sources [Analysis Services], dimensions without data source
- dimensions [Analysis Services], standard
- dimensions [Analysis Services], creating without data source
- standard dimensions [Analysis Services]
ms.assetid: a37f7a46-7451-4582-ba19-2595196d97bc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 49dbfb0c1fc15c1cbf703514e0fc693dfabf1e9d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737061"
---
# <a name="create-a-dimension-by-generating-a-non-time-table-in-the-data-source"></a><span data-ttu-id="0f218-102">Создание измерения путем формирования в источнике данных таблицы, отличной от таблицы времени</span><span class="sxs-lookup"><span data-stu-id="0f218-102">Create a Dimension by Generating a Non-Time Table in the Data Source</span></span>
  <span data-ttu-id="0f218-103">В [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] среде можно использовать мастер измерений в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] для создания измерения без использования существующего источника данных.</span><span class="sxs-lookup"><span data-stu-id="0f218-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you can use the Dimension Wizard in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] to create a dimension without using an existing data source.</span></span> <span data-ttu-id="0f218-104">Для этого на странице мастера **Выберите метод создания** следует выбрать параметр **Создать в источнике данных таблицу, отличную от таблицы времени** .</span><span class="sxs-lookup"><span data-stu-id="0f218-104">You do this by selecting the **Generate a non-time table in the data source** option of the **Select Creation Method** page of the wizard.</span></span> <span data-ttu-id="0f218-105">Для создания новой таблицы измерения в базовом источнике данных нужно иметь разрешение на создание объектов в базовом источнике данных.</span><span class="sxs-lookup"><span data-stu-id="0f218-105">To create a new dimension table in the underlying data source, you must have permission to create objects in the underlying data source.</span></span> <span data-ttu-id="0f218-106">Определение измерения без стандартного представления источников данных можно выполнить с нуля или с помощью шаблона измерения.</span><span class="sxs-lookup"><span data-stu-id="0f218-106">When defining a dimension without a predefined data source view, you can either define the dimension from scratch or use a dimension template.</span></span>  
  
 <span data-ttu-id="0f218-107">Мастер измерений предоставляет шаблоны измерений, из которых можно создать распространенный тип измерения.</span><span class="sxs-lookup"><span data-stu-id="0f218-107">The Dimension Wizard provides sample dimension templates from which you can build a common dimension type.</span></span> <span data-ttu-id="0f218-108">Можно выбрать из следующих типов измерений:</span><span class="sxs-lookup"><span data-stu-id="0f218-108">You can select from the following types of dimensions:</span></span>  
  
-   <span data-ttu-id="0f218-109">Учетная запись</span><span class="sxs-lookup"><span data-stu-id="0f218-109">Account</span></span>  
  
-   <span data-ttu-id="0f218-110">Customer</span><span class="sxs-lookup"><span data-stu-id="0f218-110">Customer</span></span>  
  
-   <span data-ttu-id="0f218-111">Дата</span><span class="sxs-lookup"><span data-stu-id="0f218-111">Date</span></span>  
  
-   <span data-ttu-id="0f218-112">отдел;</span><span class="sxs-lookup"><span data-stu-id="0f218-112">Department</span></span>  
  
-   <span data-ttu-id="0f218-113">Целевая валюта</span><span class="sxs-lookup"><span data-stu-id="0f218-113">Destination Currency</span></span>  
  
-   <span data-ttu-id="0f218-114">Сотрудник</span><span class="sxs-lookup"><span data-stu-id="0f218-114">Employee</span></span>  
  
-   <span data-ttu-id="0f218-115">Geography</span><span class="sxs-lookup"><span data-stu-id="0f218-115">Geography</span></span>  
  
-   <span data-ttu-id="0f218-116">Подробности заказа через Интернет</span><span class="sxs-lookup"><span data-stu-id="0f218-116">Internet Sales Order Details</span></span>  
  
-   <span data-ttu-id="0f218-117">План</span><span class="sxs-lookup"><span data-stu-id="0f218-117">Organization</span></span>  
  
-   <span data-ttu-id="0f218-118">Продукт</span><span class="sxs-lookup"><span data-stu-id="0f218-118">Product</span></span>  
  
-   <span data-ttu-id="0f218-119">Promotion</span><span class="sxs-lookup"><span data-stu-id="0f218-119">Promotion</span></span>  
  
-   <span data-ttu-id="0f218-120">Подробности заказа через посредников</span><span class="sxs-lookup"><span data-stu-id="0f218-120">Reseller Sales Order Details</span></span>  
  
-   <span data-ttu-id="0f218-121">Reseller</span><span class="sxs-lookup"><span data-stu-id="0f218-121">Reseller</span></span>  
  
-   <span data-ttu-id="0f218-122">Канал продаж</span><span class="sxs-lookup"><span data-stu-id="0f218-122">Sales Channel</span></span>  
  
-   <span data-ttu-id="0f218-123">Причина покупки</span><span class="sxs-lookup"><span data-stu-id="0f218-123">Sales Reason</span></span>  
  
-   <span data-ttu-id="0f218-124">Подробности заказа в сводке по продажам</span><span class="sxs-lookup"><span data-stu-id="0f218-124">Sales Summary Order Details</span></span>  
  
-   <span data-ttu-id="0f218-125">Территория продаж</span><span class="sxs-lookup"><span data-stu-id="0f218-125">Sales Territory</span></span>  
  
-   <span data-ttu-id="0f218-126">Сценарий</span><span class="sxs-lookup"><span data-stu-id="0f218-126">Scenario</span></span>  
  
-   <span data-ttu-id="0f218-127">Исходная валюта</span><span class="sxs-lookup"><span data-stu-id="0f218-127">Source Currency</span></span>  
  
 <span data-ttu-id="0f218-128">Каждый из этих стандартных шаблонов поддерживает атрибуты, которые можно выбрать для включения в измерение.</span><span class="sxs-lookup"><span data-stu-id="0f218-128">Each of the standard templates supports attributes that you can choose to include in the dimension.</span></span> <span data-ttu-id="0f218-129">Можно также добавлять собственные файлы шаблонов для измерений, часто используемых с данными.</span><span class="sxs-lookup"><span data-stu-id="0f218-129">You can also add your own template files for dimensions that are commonly used with your data.</span></span> <span data-ttu-id="0f218-130">Шаблоны измерений расположены в следующей папке:</span><span class="sxs-lookup"><span data-stu-id="0f218-130">The dimension templates are located in the following folder:</span></span>  
  
 `C:\Program Files\Microsoft SQL Server\100\Tools\Templates\olap\1033\Dimension Templates`  
  
 <span data-ttu-id="0f218-131">После добавления, удаления и настройки атрибутов и иерархий в измерении с помощью мастера измерений можно использовать конструктор измерений.</span><span class="sxs-lookup"><span data-stu-id="0f218-131">You can use Dimension Designer after you complete the Dimension Wizard to add, remove, and configure attributes and hierarchies in the dimension.</span></span>  
  
 <span data-ttu-id="0f218-132">Если создается измерение, отличное от измерения времени, без использования источника данных, мастер измерений проводит пользователя через этапы задания типа измерения, ключевого атрибута и медленно меняющихся измерений.</span><span class="sxs-lookup"><span data-stu-id="0f218-132">When you are creating a non-time dimension without using a data source, the Dimension Wizard guides you through the steps of specifying the dimension type, and identifying the key attribute and slowly changing dimensions.</span></span>  
  
## <a name="specify-dimension-type"></a><span data-ttu-id="0f218-133">Указание типа измерения</span><span class="sxs-lookup"><span data-stu-id="0f218-133">Specify Dimension Type</span></span>  
 <span data-ttu-id="0f218-134">На странице **Определение типа измерения** мастера измерений можно задать тип измерения.</span><span class="sxs-lookup"><span data-stu-id="0f218-134">On the **Specify Dimension Type** page of the Dimension Wizard, you can specify the dimension type.</span></span> <span data-ttu-id="0f218-135">Если измерение создается на основе шаблона, тип измерения задается автоматически.</span><span class="sxs-lookup"><span data-stu-id="0f218-135">If you are building the dimension based on a template, the dimension type is defined for you.</span></span> <span data-ttu-id="0f218-136">На этой странице можно также выбрать стандартные атрибуты для указанного типа измерения, если они есть.</span><span class="sxs-lookup"><span data-stu-id="0f218-136">On this page, you can also select standard attributes for the specified dimension type if any are available.</span></span>  
  
 <span data-ttu-id="0f218-137">Если выбран шаблон, соответствующий типу измерения, то эта страница заполняется параметрами для этого типа измерения.</span><span class="sxs-lookup"><span data-stu-id="0f218-137">If you selected a template that corresponds to a dimension type, this page is populated with the options for that dimension type.</span></span> <span data-ttu-id="0f218-138">Если шаблон не выбран или не существует соответствующего типа измерения, то типом измерения по умолчанию является **Обычный**.</span><span class="sxs-lookup"><span data-stu-id="0f218-138">If you did not select a template, or if there is no corresponding dimension type, the default dimension type is **Regular**.</span></span> <span data-ttu-id="0f218-139">Если тип измерения еще не выбран, выберите наиболее подходящий тип для создаваемого измерения.</span><span class="sxs-lookup"><span data-stu-id="0f218-139">If a dimension type is not already selected, select the most appropriate type for the dimension that you are creating.</span></span> <span data-ttu-id="0f218-140">Если в списке **Тип измерения**отсутствует соответствующий тип, то используйте тип **Обычный**.</span><span class="sxs-lookup"><span data-stu-id="0f218-140">If no appropriate type is listed for **Dimension type**, use **Regular**.</span></span>  
  
 <span data-ttu-id="0f218-141">Когда выбирается тип измерения, мастер выводит список типов атрибутов для этого измерения в разделе **Атрибуты измерения**.</span><span class="sxs-lookup"><span data-stu-id="0f218-141">When you select a dimension type, the wizard lists the attribute types that apply to this dimension under **Dimension attributes**.</span></span> <span data-ttu-id="0f218-142">Чтобы выбрать тип атрибута, установите флажок **Включить** рядом с типом атрибута и введите имя для атрибута в разделе **Атрибут измерения**.</span><span class="sxs-lookup"><span data-stu-id="0f218-142">To select an attribute type, select the **Include** check box next to the attribute type, and type the name for the attribute under **Dimension Attribute**.</span></span> <span data-ttu-id="0f218-143">Имя по умолчанию такое же, как **Тип атрибута**.</span><span class="sxs-lookup"><span data-stu-id="0f218-143">The default name is the same as **Attribute Type**.</span></span>  
  
## <a name="identify-key-attribute-and-changing-dimensions"></a><span data-ttu-id="0f218-144">Идентификация ключевого атрибута и изменяющихся измерений</span><span class="sxs-lookup"><span data-stu-id="0f218-144">Identify Key Attribute and Changing Dimensions</span></span>  
 <span data-ttu-id="0f218-145">На странице **Определение ключа и типа измерения** выберите атрибут, который должен быть ключевым для измерения.</span><span class="sxs-lookup"><span data-stu-id="0f218-145">On the **Specify Dimension Key and Type** page, select the attribute that you want to be the key attribute for the dimension.</span></span> <span data-ttu-id="0f218-146">Ключевой атрибут обычно соответствует первичному ключевому столбцу в главной таблице измерения, и он обычно индексирует конечные элементы этого измерения.</span><span class="sxs-lookup"><span data-stu-id="0f218-146">The key attribute typically corresponds to the primary key column in the main dimension table, and it typically indexes the leaf members of the dimension.</span></span>  
  
 <span data-ttu-id="0f218-147">Если выбран шаблон и в нем определен ключевой атрибут, то этот атрибут является ключевым атрибутом по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0f218-147">If you selected a template, and a key attribute is defined in the template, that attribute is the default key attribute.</span></span> <span data-ttu-id="0f218-148">Если был выбран шаблон, но в шаблоне не задан ключевой атрибут, по умолчанию им становится первый атрибут в списке.</span><span class="sxs-lookup"><span data-stu-id="0f218-148">If you selected a template but no key attribute is defined in the template, the default is the first attribute in the list.</span></span> <span data-ttu-id="0f218-149">Список содержит все атрибуты, выбранные на странице **Определение типа измерения** .</span><span class="sxs-lookup"><span data-stu-id="0f218-149">The list contains all the attributes that you selected on the **Specify Dimension Type** page.</span></span> <span data-ttu-id="0f218-150">В качестве ключевого можно выбрать любой из атрибутов, выбранных на странице **Определение типа измерения** .</span><span class="sxs-lookup"><span data-stu-id="0f218-150">You can select any one of the attributes that you selected on the **Specify Dimension Type** page to be the key attribute.</span></span> <span data-ttu-id="0f218-151">Если не выбраны никакие атрибуты, то мастер автоматически создает ключевой атрибут и присваивает ему имя, объединяя имя измерения и «ID».</span><span class="sxs-lookup"><span data-stu-id="0f218-151">If you did not select any attributes, the wizard automatically creates a key attribute and names it by concatenating the dimension name and "ID".</span></span>  
  
 <span data-ttu-id="0f218-152">В конце необходимо указать, является ли измерение изменяющимся измерением.</span><span class="sxs-lookup"><span data-stu-id="0f218-152">Finally, specify whether this dimension is a changing dimension.</span></span> <span data-ttu-id="0f218-153">Элементы изменяющегося измерения со временем перемещаются в разные места местоположения в пределах иерархии.</span><span class="sxs-lookup"><span data-stu-id="0f218-153">Members in a changing dimension move over time to different locations in the hierarchy.</span></span> <span data-ttu-id="0f218-154">Мастер формирует дополнительные столбцы и создает соответствующие им атрибуты.</span><span class="sxs-lookup"><span data-stu-id="0f218-154">The wizard generates additional columns and creates attributes that correspond to those columns.</span></span> <span data-ttu-id="0f218-155">Эти столбцы дадут возможность создавать запросы к измерению с учетом изменений.</span><span class="sxs-lookup"><span data-stu-id="0f218-155">These columns will let users query the dimension in such a way as to factor in the change.</span></span> <span data-ttu-id="0f218-156">Любые пакеты, создаваемые в последующем с использованием мастера формирования схем, управляют суррогатными ключами на основе характеристик медленно изменяющегося измерения.</span><span class="sxs-lookup"><span data-stu-id="0f218-156">Any packages that you subsequently create with the Schema Generation Wizard manage surrogate keys based on slowly changing dimension characteristics of the dimension.</span></span>  
  
 <span data-ttu-id="0f218-157">Если установлен флажок **Это изменяющееся измерение** , мастер измерений определяет атрибуты, указанные в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="0f218-157">When you select the **This is a changing dimension** check box, the Dimension Wizard defines the attributes indicated in the following table:</span></span>  
  
|<span data-ttu-id="0f218-158">attribute</span><span class="sxs-lookup"><span data-stu-id="0f218-158">Attribute</span></span>|<span data-ttu-id="0f218-159">Тип</span><span class="sxs-lookup"><span data-stu-id="0f218-159">Type</span></span>|  
|---------------|----------|  
|<span data-ttu-id="0f218-160">Первоначальный идентификатор медленно изменяющегося измерения</span><span class="sxs-lookup"><span data-stu-id="0f218-160">SCD OriginalID</span></span>|<span data-ttu-id="0f218-161">SCDOriginalID</span><span class="sxs-lookup"><span data-stu-id="0f218-161">SCDOriginalID</span></span>|  
|<span data-ttu-id="0f218-162">Дата окончания медленно изменяющегося измерения</span><span class="sxs-lookup"><span data-stu-id="0f218-162">SCD End Date</span></span>|<span data-ttu-id="0f218-163">SCDEndDate</span><span class="sxs-lookup"><span data-stu-id="0f218-163">SCDEndDate</span></span>|  
|<span data-ttu-id="0f218-164">Дата начала медленно изменяющегося измерения</span><span class="sxs-lookup"><span data-stu-id="0f218-164">SCD Start Date</span></span>|<span data-ttu-id="0f218-165">SCDStartDate</span><span class="sxs-lookup"><span data-stu-id="0f218-165">SCDStartDate</span></span>|  
|<span data-ttu-id="0f218-166">Состояние медленно изменяющегося измерения</span><span class="sxs-lookup"><span data-stu-id="0f218-166">SCD Status</span></span>|<span data-ttu-id="0f218-167">SCDStatus</span><span class="sxs-lookup"><span data-stu-id="0f218-167">SCDStatus</span></span>|  
  
 <span data-ttu-id="0f218-168">Флажок **Это изменяющееся измерение** устанавливается по умолчанию, если используется шаблон, в котором определены эти атрибуты медленно изменяющегося измерения.</span><span class="sxs-lookup"><span data-stu-id="0f218-168">By default, the **This is a changing dimension** check box is selected if you use a template that has these slowly changing dimension attributes defined.</span></span> <span data-ttu-id="0f218-169">Если флажок снят, то атрибуты медленно изменяющегося измерения удаляются из измерения.</span><span class="sxs-lookup"><span data-stu-id="0f218-169">If you clear the check box, the slowly changing dimension attributes are removed from the dimension.</span></span>  
  
 <span data-ttu-id="0f218-170">Можно использовать конструктор измерений для настройки свойств для медленно изменяющегося измерения.</span><span class="sxs-lookup"><span data-stu-id="0f218-170">You can use Dimension Designer to configure properties for a slowly changing dimension.</span></span>  
  
## <a name="completing-the-dimension-wizard"></a><span data-ttu-id="0f218-171">Завершение работы мастера измерений</span><span class="sxs-lookup"><span data-stu-id="0f218-171">Completing the Dimension Wizard</span></span>  
 <span data-ttu-id="0f218-172">На странице **Завершение работы мастера** введите имя для нового измерения и просмотрите структуру измерения.</span><span class="sxs-lookup"><span data-stu-id="0f218-172">On the **Completing the Wizard** page, type a name for the new dimension and view the dimension structure.</span></span> <span data-ttu-id="0f218-173">Установите флажок **Сформировать схему** , чтобы запустить мастер формирования схем после нажатия кнопки **Готово**.</span><span class="sxs-lookup"><span data-stu-id="0f218-173">Select the **Generate schema now** check box to start the Schema Generation Wizard after you click **Finish**.</span></span> <span data-ttu-id="0f218-174">В большинстве случаев не следует устанавливать этот флажок, если запланировано создание дополнительных объектов.</span><span class="sxs-lookup"><span data-stu-id="0f218-174">In most cases, you should not select this check box if you plan to create additional objects.</span></span> <span data-ttu-id="0f218-175">Если этот флажок не установлен, то можно использовать конструктор измерений для формирования схемы позже.</span><span class="sxs-lookup"><span data-stu-id="0f218-175">If you do not select this check box, you can use Dimension Designer to generate the schema later.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f218-176">См. также:</span><span class="sxs-lookup"><span data-stu-id="0f218-176">See Also</span></span>  
 <span data-ttu-id="0f218-177">[Создание измерения времени путем создания таблицы времени](create-a-time-dimension-by-generating-a-time-table.md) </span><span class="sxs-lookup"><span data-stu-id="0f218-177">[Create a Time Dimension by Generating a Time Table](create-a-time-dimension-by-generating-a-time-table.md) </span></span>  
 [<span data-ttu-id="0f218-178">Создание измерения времени посредством формирования таблицы времени</span><span class="sxs-lookup"><span data-stu-id="0f218-178">Create a Time Dimension by Generating a Time Table</span></span>](create-a-time-dimension-by-generating-a-time-table.md)  
  
  
