---
title: Выбор атрибутов измерения (мастер измерений) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.dimensionattributes.f1
ms.assetid: f58a3e14-ab27-44d3-8c26-f5c9ee7583b0
author: minewiskan
ms.author: owend
ms.openlocfilehash: a4961092517ce1d38cfd4086ec083a939242652d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657355"
---
# <a name="select-dimension-attributes-dimension-wizard"></a><span data-ttu-id="f9641-102">Выбор атрибутов измерения (мастер измерения)</span><span class="sxs-lookup"><span data-stu-id="f9641-102">Select Dimension Attributes (Dimension Wizard)</span></span>
  <span data-ttu-id="f9641-103">Используйте страницу **Выбор атрибутов измерения** для выбора и изменения атрибутов для создаваемых измерений.</span><span class="sxs-lookup"><span data-stu-id="f9641-103">Use the **Select Dimension Attributes** page to select and modify the attributes for the dimension to be created.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f9641-104">Если невозможно прочитать значения в каком-нибудь столбце, разверните окно мастера и изменяйте ширину заголовка каждого столбца до тех пор, пока не удастся прочитать значения.</span><span class="sxs-lookup"><span data-stu-id="f9641-104">If you cannot read the values for any column, maximize the wizard window and change the width of each column heading until you can read the values.</span></span>  
  
 <span data-ttu-id="f9641-105">**Открытие мастера измерений**</span><span class="sxs-lookup"><span data-stu-id="f9641-105">**To open the Dimension Wizard**</span></span>  
  
-   <span data-ttu-id="f9641-106">В [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]обозревателе решений \*\*\*\* щелкните правой кнопкой мыши папку **Измерения** для проекта [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , а затем выберите команду **Новое измерение**.</span><span class="sxs-lookup"><span data-stu-id="f9641-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in **Solution Explorer**, right-click the **Dimensions** folder for an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, and then click **New Dimension**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f9641-107">Варианты</span><span class="sxs-lookup"><span data-stu-id="f9641-107">Options</span></span>  
 <span data-ttu-id="f9641-108">(Столбец с флажками)</span><span class="sxs-lookup"><span data-stu-id="f9641-108">(Column with check boxes)</span></span>  
 <span data-ttu-id="f9641-109">Выберите для включения атрибута в измерение.</span><span class="sxs-lookup"><span data-stu-id="f9641-109">Select to include an attribute in the dimension.</span></span>  
  
 <span data-ttu-id="f9641-110">Для включения конкретного атрибута установите флажок для этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="f9641-110">To include a specific attribute, select the check box for that attribute.</span></span>  
  
 <span data-ttu-id="f9641-111">Для включения всех атрибутов установите флажок в заголовке столбца.</span><span class="sxs-lookup"><span data-stu-id="f9641-111">To include all attributes, select the check box in the column header.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f9641-112">Нельзя снять флажок для ключевого атрибута.</span><span class="sxs-lookup"><span data-stu-id="f9641-112">The check box for the key attribute cannot be cleared.</span></span>  
  
 <span data-ttu-id="f9641-113">**Имя атрибута**</span><span class="sxs-lookup"><span data-stu-id="f9641-113">**Attribute Name**</span></span>  
 <span data-ttu-id="f9641-114">Список доступных атрибутов.</span><span class="sxs-lookup"><span data-stu-id="f9641-114">Lists the available attributes.</span></span>  
  
 <span data-ttu-id="f9641-115">Чтобы изменить имя атрибута, щелкните имя и тип атрибута, а затем введите новое имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="f9641-115">To change the name of an attribute, click the attribute name and type a new name for the attribute.</span></span>  
  
 <span data-ttu-id="f9641-116">**Разрешить обзор**</span><span class="sxs-lookup"><span data-stu-id="f9641-116">**Enable Browsing**</span></span>  
 <span data-ttu-id="f9641-117">Выберите, чтобы сделать атрибут доступным для просмотра и фильтрации конечным пользователем.</span><span class="sxs-lookup"><span data-stu-id="f9641-117">Select to make the attribute available to the end user for browsing and filtering.</span></span> <span data-ttu-id="f9641-118">Для ключевого атрибута необходимо выбрать параметр**Разрешить обзор** .</span><span class="sxs-lookup"><span data-stu-id="f9641-118">**Enable Browsing** must be selected for the key attribute.</span></span> <span data-ttu-id="f9641-119">Для неключевых атрибутов параметр **Разрешить обзор** по умолчанию не выбран, поэтому неключевые атрибуты отображаются только как свойства элементов.</span><span class="sxs-lookup"><span data-stu-id="f9641-119">For non-key attributes, the default is not to have **Enable Browsing** selected, which causes the non-key attributes to be shown only as member properties.</span></span>  
  
 <span data-ttu-id="f9641-120">В большинстве случаев просмотр атрибута разрешается или запрещается путем назначения свойству `AttributeHierarchyEnabled` значения `True` или `False` соответственно.</span><span class="sxs-lookup"><span data-stu-id="f9641-120">In most cases, the attribute is made available or not available for browsing by setting the `AttributeHierarchyEnabled` property to `True` or `False`, respectively.</span></span> <span data-ttu-id="f9641-121">Но в следующих трех случаях мастер использует другие настройки.</span><span class="sxs-lookup"><span data-stu-id="f9641-121">However, in the following three cases, the wizard uses different settings.</span></span>  
  
|<span data-ttu-id="f9641-122">Случай</span><span class="sxs-lookup"><span data-stu-id="f9641-122">Case</span></span>|<span data-ttu-id="f9641-123">Параметры</span><span class="sxs-lookup"><span data-stu-id="f9641-123">Settings</span></span>|  
|----------|--------------|  
|<span data-ttu-id="f9641-124">Измерение содержит иерархию типа "родители-потомки", а параметр **Разрешить обзор** не выбран.</span><span class="sxs-lookup"><span data-stu-id="f9641-124">A dimension contains a parent-child hierarchy and **Enable Browsing** is not selected</span></span>|<span data-ttu-id="f9641-125">Мастер оставляет свойству `AttributeHierarchyEnabled` значение `True` и назначает атрибуту `AttributeHierarchyVisible` значение `False` для ключевого атрибута.</span><span class="sxs-lookup"><span data-stu-id="f9641-125">The wizard leaves the `AttributeHierarchyEnabled` property set to `True`, and sets the `AttributeHierarchyVisible` attribute to `False` for the key attribute.</span></span>|  
|<span data-ttu-id="f9641-126">Таблица в измерении содержит внешний ключ к таблице вне этого измерения.</span><span class="sxs-lookup"><span data-stu-id="f9641-126">A table in a dimension contains a foreign key to a table that is not in the dimension</span></span>|<span data-ttu-id="f9641-127">Мастер выбирает внешний ключ, как включаемый атрибут, но не выбирает параметр **Разрешить обзор**.</span><span class="sxs-lookup"><span data-stu-id="f9641-127">The wizard selects the foreign key as an attribute to be included, but will not select **Enable Browsing**.</span></span> <span data-ttu-id="f9641-128">Если сохранить эти настройки, то свойству `AttributeHiearchyEnabled` атрибута будет присвоено значение `True`, а свойству `AttributeHierarchyVisible` — значение `False`.</span><span class="sxs-lookup"><span data-stu-id="f9641-128">If you keep these settings, the `AttributeHiearchyEnabled` property of the attribute will be set to `True`, and the `AttributeHierarchyVisible` property will be set to `False`.</span></span>|  
|<span data-ttu-id="f9641-129">Измерение содержит таблицы, связанные по схеме «снежинка», доступные через внешние ключевые столбцы, допускающих значение NULL</span><span class="sxs-lookup"><span data-stu-id="f9641-129">A dimension contains snowflake tables that are reached through nullable foreign key columns</span></span><br /><br /> <span data-ttu-id="f9641-130">- и -</span><span class="sxs-lookup"><span data-stu-id="f9641-130">-and-</span></span><br /><br /> <span data-ttu-id="f9641-131">Не выбран параметр «Разрешить обзор» для атрибута, основанного на ключе таблицы, связанной по схеме «снежинка»</span><span class="sxs-lookup"><span data-stu-id="f9641-131">Enable Browsing for the attribute that is based on the key of the snowflake table is not selected</span></span>|<span data-ttu-id="f9641-132">Мастер создаст новый атрибут со свойством `AttributeHiearchyEnabled`, установленным в значение `True`, и свойством `AttributeHierarchyVisible`, установленным в значение `False`.</span><span class="sxs-lookup"><span data-stu-id="f9641-132">The wizard will create the new attribute that has the `AttributeHiearchyEnabled` property set to `True`, and the `AttributeHierarchyVisible` property set to `False`.</span></span>|  
  
 <span data-ttu-id="f9641-133">**Тип атрибута**</span><span class="sxs-lookup"><span data-stu-id="f9641-133">**Attribute Type**</span></span>  
 <span data-ttu-id="f9641-134">Задайте тип атрибута (необязательно).</span><span class="sxs-lookup"><span data-stu-id="f9641-134">(Optional) Set the type for the attribute.</span></span> <span data-ttu-id="f9641-135">Значение по умолчанию — **Обычный**.</span><span class="sxs-lookup"><span data-stu-id="f9641-135">The default value is **Regular**.</span></span> <span data-ttu-id="f9641-136">Тип атрибута указывает клиентским приложениям, какие сведения может содержать атрибут.</span><span class="sxs-lookup"><span data-stu-id="f9641-136">The attribute type provides guidance to client applications on what information the attribute might contain.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9641-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="f9641-137">See Also</span></span>  
 <span data-ttu-id="f9641-138">[Справка F1 мастера измерений](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="f9641-138">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="f9641-139">[Измерения &#40;Analysis Services многомерных данных&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="f9641-139">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="f9641-140">Измерения в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="f9641-140">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
