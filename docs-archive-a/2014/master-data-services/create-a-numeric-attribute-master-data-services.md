---
title: Создание числового атрибута (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Master Data Services], creating number attributes
- creating number attributes [Master Data Services]
ms.assetid: c0dbb6d8-ba78-485a-a40d-6d5cb7e75d0a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: bb9302c0b585c21410a6a764dc2e6dac845c6299
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654391"
---
# <a name="create-a-numeric-attribute-master-data-services"></a><span data-ttu-id="4b9d3-102">Создание числового атрибута (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="4b9d3-102">Create a Numeric Attribute (Master Data Services)</span></span>
  <span data-ttu-id="4b9d3-103">В службах [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]числовой атрибут создается, если нужно, чтобы пользователи вводили число в качестве значения атрибута.</span><span class="sxs-lookup"><span data-stu-id="4b9d3-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a numeric attribute when you want users to enter a number as an attribute value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4b9d3-104">На числовые атрибуты налагаются определенные ограничения.</span><span class="sxs-lookup"><span data-stu-id="4b9d3-104">Numeric attributes have limitations.</span></span> <span data-ttu-id="4b9d3-105">Дополнительные сведения см. в разделе [Атрибуты (службы Master Data Services)](attributes-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4b9d3-105">For more information, see [Attributes &#40;Master Data Services&#41;](attributes-master-data-services.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4b9d3-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="4b9d3-106">Prerequisites</span></span>  
 <span data-ttu-id="4b9d3-107">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="4b9d3-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="4b9d3-108">Необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="4b9d3-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="4b9d3-109">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="4b9d3-109">You must be a model administrator.</span></span> <span data-ttu-id="4b9d3-110">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4b9d3-110">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="4b9d3-111">должна существовать сущность, для которой создается атрибут.</span><span class="sxs-lookup"><span data-stu-id="4b9d3-111">An entity must exist to create the attribute for.</span></span> <span data-ttu-id="4b9d3-112">Дополнительные сведения см. в разделе [Создание сущности (службы Master Data Services)](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4b9d3-112">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-create-a-numeric-attribute"></a><span data-ttu-id="4b9d3-113">Создание числового атрибута</span><span class="sxs-lookup"><span data-stu-id="4b9d3-113">To create a numeric attribute</span></span>  
  
1.  <span data-ttu-id="4b9d3-114">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="4b9d3-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="4b9d3-115">На странице **Представление модели** в строке меню наведите курсор на **Управление** и щелкните **Сущности**.</span><span class="sxs-lookup"><span data-stu-id="4b9d3-115">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="4b9d3-116">На странице **Обслуживание сущности** выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="4b9d3-116">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="4b9d3-117">Выберите строку сущности, для которой необходимо создать атрибут.</span><span class="sxs-lookup"><span data-stu-id="4b9d3-117">Select the row for the entity that you want to create an attribute for.</span></span>  
  
5.  <span data-ttu-id="4b9d3-118">Щелкните **Изменить выбранную сущность**.</span><span class="sxs-lookup"><span data-stu-id="4b9d3-118">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="4b9d3-119">На странице **Изменение сущности** :</span><span class="sxs-lookup"><span data-stu-id="4b9d3-119">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="4b9d3-120">если атрибут предназначен для конечных элементов, выберите команду **Добавить конечный атрибут** на панели **Атрибуты конечных элементов**;</span><span class="sxs-lookup"><span data-stu-id="4b9d3-120">If the attribute is for leaf members, in the **Leaf member attributes** pane, click **Add leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="4b9d3-121">если атрибут предназначен для объединенных элементов, выберите команду **Добавить объединенный атрибут** на панели **Атрибуты консолидированных элементов**;</span><span class="sxs-lookup"><span data-stu-id="4b9d3-121">If the attribute is for consolidated members, in the **Consolidated member attributes** pane, click **Add consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="4b9d3-122">если атрибут предназначен для коллекций, выберите команду **Добавить атрибут коллекции** на панели **Атрибуты коллекций**.</span><span class="sxs-lookup"><span data-stu-id="4b9d3-122">If the attribute is for collections, in the **Collection attributes** pane, click **Add collection attribute**.</span></span>  
  
7.  <span data-ttu-id="4b9d3-123">Выберите параметр **В свободной форме** на странице **Добавить атрибут** .</span><span class="sxs-lookup"><span data-stu-id="4b9d3-123">On the **Add Attribute** page, select the **Free-form** option.</span></span>  
  
8.  <span data-ttu-id="4b9d3-124">Введите имя атрибута в поле **Имя** .</span><span class="sxs-lookup"><span data-stu-id="4b9d3-124">In the **Name** box, type a name for the attribute.</span></span> <span data-ttu-id="4b9d3-125">Список слов, которые не должны использоваться в качестве имен атрибутов, см. в разделе [зарезервированные слова &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4b9d3-125">For a list of words that should not be used as attribute names, see [Reserved Words &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="4b9d3-126">В поле **Ширина отображаемой области (в пикселях)** введите ширину столбца атрибута для отображения в сетке **обозревателя** .</span><span class="sxs-lookup"><span data-stu-id="4b9d3-126">In the **Display pixel width** box, type the width of the attribute column to be displayed in the **Explorer** grid.</span></span>  
  
10. <span data-ttu-id="4b9d3-127">В списке **Тип данных** выберите **Число**.</span><span class="sxs-lookup"><span data-stu-id="4b9d3-127">From the **Data type** list, select **Number**.</span></span>  
  
11. <span data-ttu-id="4b9d3-128">В поле **Знаки после запятой** укажите количество знаков, которые можно ввести после десятичной запятой.</span><span class="sxs-lookup"><span data-stu-id="4b9d3-128">In the **Decimals** box, type the number of numbers that can be entered after a decimal.</span></span>  
  
12. <span data-ttu-id="4b9d3-129">В списке **Маска ввода** выберите формат отрицательных чисел.</span><span class="sxs-lookup"><span data-stu-id="4b9d3-129">From the **Input mask** list, select a format for negative numbers.</span></span>  
  
13. <span data-ttu-id="4b9d3-130">По желанию установите флажок **Включить отслеживание изменений** , чтобы отслеживать изменения в группах атрибутов.</span><span class="sxs-lookup"><span data-stu-id="4b9d3-130">Optionally, select **Enable change tracking** to track changes to groups of attributes.</span></span> <span data-ttu-id="4b9d3-131">Дополнительные сведения см. в разделе [Добавление атрибутов в группу отслеживания изменений (службы Master Data Services)](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md) .</span><span class="sxs-lookup"><span data-stu-id="4b9d3-131">See [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md) for more information.</span></span>  
  
14. <span data-ttu-id="4b9d3-132">Нажмите кнопку **Сохранить атрибут**.</span><span class="sxs-lookup"><span data-stu-id="4b9d3-132">Click **Save attribute**.</span></span>  
  
15. <span data-ttu-id="4b9d3-133">На странице **Обслуживание сущности** нажмите кнопку **Сохранить сущность**.</span><span class="sxs-lookup"><span data-stu-id="4b9d3-133">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b9d3-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="4b9d3-134">See Also</span></span>  
 <span data-ttu-id="4b9d3-135">[Master Data Services &#40;атрибутов&#41;](attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="4b9d3-135">[Attributes &#40;Master Data Services&#41;](attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="4b9d3-136">[Измените имя атрибута &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="4b9d3-136">[Change an Attribute Name &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span></span>  
 <span data-ttu-id="4b9d3-137">[Создание атрибута на основе домена &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="4b9d3-137">[Create a Domain-Based Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="4b9d3-138">Создание файлового атрибута (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="4b9d3-138">Create a File Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-file-attribute-master-data-services.md)  
  
  
