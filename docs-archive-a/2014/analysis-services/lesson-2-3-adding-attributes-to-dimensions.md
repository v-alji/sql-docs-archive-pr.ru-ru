---
title: Добавление атрибутов в измерения | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 80551dad-97ac-40d0-90af-b810780321ce
author: minewiskan
ms.author: owend
ms.openlocfilehash: 76a04c42cc501fdca3e5ceb6481452052966796b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654542"
---
# <a name="adding-attributes-to-dimensions"></a><span data-ttu-id="6fcf9-102">Добавление атрибутов к измерениям</span><span class="sxs-lookup"><span data-stu-id="6fcf9-102">Adding Attributes to Dimensions</span></span>
  <span data-ttu-id="6fcf9-103">Теперь после определения измерений можно наполнить их атрибутами, которые представляют все элементы данных в измерении.</span><span class="sxs-lookup"><span data-stu-id="6fcf9-103">Now that you have defined dimensions, you can populate them with attributes that represent each data element in the dimension.</span></span> <span data-ttu-id="6fcf9-104">Атрибуты обычно основаны на полях из представления источников данных.</span><span class="sxs-lookup"><span data-stu-id="6fcf9-104">Attributes are commonly based on fields from a data source view.</span></span> <span data-ttu-id="6fcf9-105">При добавлении атрибутов в измерение можно включить поля из любой таблицы в представлении источника данных.</span><span class="sxs-lookup"><span data-stu-id="6fcf9-105">When adding attributes to a dimension, you can include fields from any table in the data source view.</span></span>  
  
 <span data-ttu-id="6fcf9-106">В этой задаче с помощью конструктора измерений в измерения «Заказчик» и «Продукт» будут добавлены атрибуты.</span><span class="sxs-lookup"><span data-stu-id="6fcf9-106">In this task, you will use Dimension Designer to add attributes to the Customer and Product dimensions.</span></span> <span data-ttu-id="6fcf9-107">Измерение «Заказчик» будет включать атрибуты, основанные на полях из таблиц как «Заказчик», так и «География».</span><span class="sxs-lookup"><span data-stu-id="6fcf9-107">The Customer dimension will include attributes based on fields from both the Customer and Geography tables.</span></span>  
  
## <a name="adding-attributes-to-the-customer-dimension"></a><span data-ttu-id="6fcf9-108">Добавление атрибутов в измерение «Заказчик»</span><span class="sxs-lookup"><span data-stu-id="6fcf9-108">Adding Attributes to the Customer Dimension</span></span>  
  
#### <a name="to-add-attributes"></a><span data-ttu-id="6fcf9-109">Добавление атрибутов</span><span class="sxs-lookup"><span data-stu-id="6fcf9-109">To add attributes</span></span>  
  
1.  <span data-ttu-id="6fcf9-110">Откройте в конструкторе измерений измерение «Заказчик».</span><span class="sxs-lookup"><span data-stu-id="6fcf9-110">Open Dimension Designer for the Customer dimension.</span></span> <span data-ttu-id="6fcf9-111">Для этого дважды щелкните измерение **Заказчик** в узле **Измерения** обозревателя решений.</span><span class="sxs-lookup"><span data-stu-id="6fcf9-111">To do this, double-click the **Customer** dimension in the **Dimensions** node of Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="6fcf9-112">На панели **Атрибуты** обратите внимание на атрибуты «Customer Key» и «Geography Key», созданные мастером кубов.</span><span class="sxs-lookup"><span data-stu-id="6fcf9-112">In the **Attributes** pane, notice the Customer Key and Geography Key attributes that were created by the Cube Wizard.</span></span>  
  
3.  <span data-ttu-id="6fcf9-113">На панели инструментов вкладки **Структура измерения** щелкните значок «Масштаб», чтобы просмотреть таблицы области **Представление источника данных** в масштабе 100 %.</span><span class="sxs-lookup"><span data-stu-id="6fcf9-113">On the toolbar of the **Dimension Structure** tab, make sure the Zoom icon to view the tables in the **Data Source View** pane is set at 100 percent.</span></span>  
  
4.  <span data-ttu-id="6fcf9-114">Перетащите следующие столбцы из таблицы **Customer** в области **Представление источника данных** в область **Атрибуты** .</span><span class="sxs-lookup"><span data-stu-id="6fcf9-114">Drag the following columns from the **Customer** table in the **Data Source View** pane to the **Attributes** pane:</span></span>  
  
    -   <span data-ttu-id="6fcf9-115">**BirthDate**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-115">**BirthDate**</span></span>  
  
    -   <span data-ttu-id="6fcf9-116">**MaritalStatus**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-116">**MaritalStatus**</span></span>  
  
    -   <span data-ttu-id="6fcf9-117">**Gender**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-117">**Gender**</span></span>  
  
    -   <span data-ttu-id="6fcf9-118">**EmailAddress**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-118">**EmailAddress**</span></span>  
  
    -   <span data-ttu-id="6fcf9-119">**YearlyIncome**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-119">**YearlyIncome**</span></span>  
  
    -   <span data-ttu-id="6fcf9-120">**TotalChildren**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-120">**TotalChildren**</span></span>  
  
    -   <span data-ttu-id="6fcf9-121">**NumberChildrenAtHome**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-121">**NumberChildrenAtHome**</span></span>  
  
    -   <span data-ttu-id="6fcf9-122">**EnglishEducation**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-122">**EnglishEducation**</span></span>  
  
    -   <span data-ttu-id="6fcf9-123">**EnglishOccupation**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-123">**EnglishOccupation**</span></span>  
  
    -   <span data-ttu-id="6fcf9-124">**HouseOwnerFlag**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-124">**HouseOwnerFlag**</span></span>  
  
    -   <span data-ttu-id="6fcf9-125">**NumberCarsOwned**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-125">**NumberCarsOwned**</span></span>  
  
    -   <span data-ttu-id="6fcf9-126">**Факс**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-126">**Phone**</span></span>  
  
    -   <span data-ttu-id="6fcf9-127">**DateFirstPurchase**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-127">**DateFirstPurchase**</span></span>  
  
    -   <span data-ttu-id="6fcf9-128">**CommuteDistance**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-128">**CommuteDistance**</span></span>  
  
5.  <span data-ttu-id="6fcf9-129">Перетащите следующие столбцы из таблицы **Geography** в области **Представление источника данных** в область **Атрибуты** .</span><span class="sxs-lookup"><span data-stu-id="6fcf9-129">Drag the following columns from the **Geography** table in the **Data Source View** pane to the **Attributes** pane:</span></span>  
  
    -   <span data-ttu-id="6fcf9-130">**Город**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-130">**City**</span></span>  
  
    -   <span data-ttu-id="6fcf9-131">**StateProvinceName**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-131">**StateProvinceName**</span></span>  
  
    -   <span data-ttu-id="6fcf9-132">**EnglishCountryRegionName**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-132">**EnglishCountryRegionName**</span></span>  
  
    -   <span data-ttu-id="6fcf9-133">**PostalCode**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-133">**PostalCode**</span></span>  
  
6.  <span data-ttu-id="6fcf9-134">В меню File (Файл) выберите команду **Save All** (Сохранить все).</span><span class="sxs-lookup"><span data-stu-id="6fcf9-134">On the File menu, click **Save All**.</span></span>  
  
## <a name="adding-attributes-to-the-product-dimension"></a><span data-ttu-id="6fcf9-135">Добавление атрибутов в измерение «Продукт»</span><span class="sxs-lookup"><span data-stu-id="6fcf9-135">Adding Attributes to the Product Dimension</span></span>  
  
#### <a name="to-add-attributes"></a><span data-ttu-id="6fcf9-136">Добавление атрибутов</span><span class="sxs-lookup"><span data-stu-id="6fcf9-136">To add attributes</span></span>  
  
1.  <span data-ttu-id="6fcf9-137">Откройте в конструкторе измерений измерение «Продукт».</span><span class="sxs-lookup"><span data-stu-id="6fcf9-137">Open Dimension Designer for the Product dimension.</span></span> <span data-ttu-id="6fcf9-138">Дважды щелкните измерение **Продукт** в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="6fcf9-138">Double-click the **Product** dimension in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="6fcf9-139">На панели **Атрибуты** обратите внимание на атрибут «Ключ продукта», созданный мастером кубов.</span><span class="sxs-lookup"><span data-stu-id="6fcf9-139">In the **Attributes** pane, notice the Product Key attribute that was created by the Cube Wizard.</span></span>  
  
3.  <span data-ttu-id="6fcf9-140">На панели инструментов вкладки **Структура измерения** щелкните значок «Масштаб», чтобы просмотреть таблицы области **Представление источника данных** в масштабе 100 %.</span><span class="sxs-lookup"><span data-stu-id="6fcf9-140">On the toolbar of the **Dimension Structure** tab, make sure the Zoom icon to view the tables in the **Data Source View** pane is set at 100 percent.</span></span>  
  
4.  <span data-ttu-id="6fcf9-141">Перетащите следующие столбцы из таблицы **Продукт** в области **Представление источника данных** в область **Атрибуты** .</span><span class="sxs-lookup"><span data-stu-id="6fcf9-141">Drag the following columns from the **Product** table in the **Data Source View** pane to the **Attributes** pane:</span></span>  
  
    -   <span data-ttu-id="6fcf9-142">**StandardCost**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-142">**StandardCost**</span></span>  
  
    -   <span data-ttu-id="6fcf9-143">**Цвет**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-143">**Color**</span></span>  
  
    -   <span data-ttu-id="6fcf9-144">**SafetyStockLevel**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-144">**SafetyStockLevel**</span></span>  
  
    -   <span data-ttu-id="6fcf9-145">**ReorderPoint**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-145">**ReorderPoint**</span></span>  
  
    -   <span data-ttu-id="6fcf9-146">**ListPrice**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-146">**ListPrice**</span></span>  
  
    -   <span data-ttu-id="6fcf9-147">**Размер**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-147">**Size**</span></span>  
  
    -   <span data-ttu-id="6fcf9-148">**SizeRange**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-148">**SizeRange**</span></span>  
  
    -   <span data-ttu-id="6fcf9-149">**Weight**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-149">**Weight**</span></span>  
  
    -   <span data-ttu-id="6fcf9-150">**DaysToManufacture**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-150">**DaysToManufacture**</span></span>  
  
    -   <span data-ttu-id="6fcf9-151">**ProductLine**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-151">**ProductLine**</span></span>  
  
    -   <span data-ttu-id="6fcf9-152">**DealerPrice**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-152">**DealerPrice**</span></span>  
  
    -   <span data-ttu-id="6fcf9-153">**Класс**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-153">**Class**</span></span>  
  
    -   <span data-ttu-id="6fcf9-154">**Style**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-154">**Style**</span></span>  
  
    -   <span data-ttu-id="6fcf9-155">**ModelName**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-155">**ModelName**</span></span>  
  
    -   <span data-ttu-id="6fcf9-156">**/SD**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-156">**StartDate**</span></span>  
  
    -   <span data-ttu-id="6fcf9-157">**Предшеству**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-157">**EndDate**</span></span>  
  
    -   <span data-ttu-id="6fcf9-158">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="6fcf9-158">**Status**</span></span>  
  
5.  <span data-ttu-id="6fcf9-159">В меню File (Файл) выберите команду **Save All** (Сохранить все).</span><span class="sxs-lookup"><span data-stu-id="6fcf9-159">On the File menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="6fcf9-160">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="6fcf9-160">Next Task in Lesson</span></span>  
 [<span data-ttu-id="6fcf9-161">Просмотр свойств куба и измерения</span><span class="sxs-lookup"><span data-stu-id="6fcf9-161">Reviewing Cube and Dimension Properties</span></span>](lesson-2-4-reviewing-cube-and-dimension-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="6fcf9-162">См. также:</span><span class="sxs-lookup"><span data-stu-id="6fcf9-162">See Also</span></span>  
 [<span data-ttu-id="6fcf9-163">Справочник по свойствам атрибута измерения</span><span class="sxs-lookup"><span data-stu-id="6fcf9-163">Dimension Attribute Properties Reference</span></span>](multidimensional-models/dimension-attribute-properties-reference.md)  
  
  
