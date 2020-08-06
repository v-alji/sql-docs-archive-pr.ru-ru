---
title: Создание атрибута на основе домена (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- domain-based attributes [Master Data Services], creating
- creating domain-based attributes [Master Data Services]
- attributes [Master Data Services], creating domain-based attributes
ms.assetid: 11c31c9f-e6cc-47b7-b76a-d691f84c93c6
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 51c0f44bb76ae2ad4c25987ed5e5ee144a18c739
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656447"
---
# <a name="create-a-domain-based-attribute-master-data-services"></a><span data-ttu-id="4bb5e-102">Создание атрибута на основе домена (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="4bb5e-102">Create a Domain-Based Attribute (Master Data Services)</span></span>
  <span data-ttu-id="4bb5e-103">В службах [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]атрибут на основе домена создается, чтобы заполнить значения атрибута элементами сущности.</span><span class="sxs-lookup"><span data-stu-id="4bb5e-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a domain-based attribute to populate an attribute's values with members from an entity.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4bb5e-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="4bb5e-104">Prerequisites</span></span>  
 <span data-ttu-id="4bb5e-105">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="4bb5e-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="4bb5e-106">Необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="4bb5e-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="4bb5e-107">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="4bb5e-107">You must be a model administrator.</span></span> <span data-ttu-id="4bb5e-108">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4bb5e-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="4bb5e-109">Должна существовать сущность, являющаяся источником значений атрибута.</span><span class="sxs-lookup"><span data-stu-id="4bb5e-109">An entity must exist to use as the source of the attribute values.</span></span> <span data-ttu-id="4bb5e-110">Например, чтобы создать доменный атрибут на основе сущности Color, нужно сначала создать сущность Color.</span><span class="sxs-lookup"><span data-stu-id="4bb5e-110">For example, to create a domain-based attribute based on the Color entity, you must first create the Color entity.</span></span> <span data-ttu-id="4bb5e-111">Дополнительные сведения см. в разделе [Создание сущности (службы Master Data Services)](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4bb5e-111">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="4bb5e-112">должна существовать сущность, для которой создается атрибут.</span><span class="sxs-lookup"><span data-stu-id="4bb5e-112">An entity must exist to create the attribute for.</span></span> <span data-ttu-id="4bb5e-113">Дополнительные сведения см. в разделе [Создание сущности (службы Master Data Services)](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4bb5e-113">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-create-a-domain-based-attribute"></a><span data-ttu-id="4bb5e-114">Создание атрибута на основе домена</span><span class="sxs-lookup"><span data-stu-id="4bb5e-114">To create a domain-based attribute</span></span>  
  
1.  <span data-ttu-id="4bb5e-115">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="4bb5e-115">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="4bb5e-116">На странице **Представление модели** в строке меню наведите курсор на **Управление** и щелкните **Сущности**.</span><span class="sxs-lookup"><span data-stu-id="4bb5e-116">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="4bb5e-117">На странице **Обслуживание сущности** выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="4bb5e-117">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="4bb5e-118">Выберите строку сущности, для которой необходимо создать атрибут.</span><span class="sxs-lookup"><span data-stu-id="4bb5e-118">Select the row for the entity that you want to create an attribute for.</span></span>  
  
5.  <span data-ttu-id="4bb5e-119">Щелкните **Изменить выбранную сущность**.</span><span class="sxs-lookup"><span data-stu-id="4bb5e-119">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="4bb5e-120">На странице **Изменение сущности** :</span><span class="sxs-lookup"><span data-stu-id="4bb5e-120">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="4bb5e-121">если атрибут предназначен для конечных элементов, выберите команду **Добавить конечный атрибут** на панели **Атрибуты конечных элементов**;</span><span class="sxs-lookup"><span data-stu-id="4bb5e-121">If the attribute is for leaf members, in the **Leaf member attributes** pane, click **Add leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="4bb5e-122">если атрибут предназначен для объединенных элементов, выберите команду **Добавить объединенный атрибут** на панели **Атрибуты консолидированных элементов**;</span><span class="sxs-lookup"><span data-stu-id="4bb5e-122">If the attribute is for consolidated members, in the **Consolidated member attributes** pane, click **Add consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="4bb5e-123">если атрибут предназначен для коллекций, выберите команду **Добавить атрибут коллекции** на панели **Атрибуты коллекций**.</span><span class="sxs-lookup"><span data-stu-id="4bb5e-123">If the attribute is for collections, in the **Collection attributes** pane, click **Add collection attribute**.</span></span>  
  
7.  <span data-ttu-id="4bb5e-124">На странице **Добавление атрибута** выберите параметр **на основе домена** .</span><span class="sxs-lookup"><span data-stu-id="4bb5e-124">On the **Add Attribute** page, select the **Domain-based** option.</span></span>  
  
8.  <span data-ttu-id="4bb5e-125">Введите имя атрибута в поле **Имя** .</span><span class="sxs-lookup"><span data-stu-id="4bb5e-125">In the **Name** box, type a name for the attribute.</span></span> <span data-ttu-id="4bb5e-126">Оно не обязательно должно совпадать с именем сущности, являющейся источником значений атрибута.</span><span class="sxs-lookup"><span data-stu-id="4bb5e-126">It does not have to be the same name as the entity that you use for the source of the attribute values.</span></span>  
  
9. <span data-ttu-id="4bb5e-127">В поле **Ширина отображаемой области (в пикселях)** введите ширину столбца атрибута для отображения в сетке **обозревателя** .</span><span class="sxs-lookup"><span data-stu-id="4bb5e-127">In the **Display pixel width** box, type the width of the attribute column to be displayed in the **Explorer** grid.</span></span>  
  
10. <span data-ttu-id="4bb5e-128">В списке **сущность** выберите сущность, которая будет использоваться для заполнения значений атрибутов.</span><span class="sxs-lookup"><span data-stu-id="4bb5e-128">From the **Entity** list, choose the entity to be used to populate the attribute values.</span></span>  
  
11. <span data-ttu-id="4bb5e-129">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4bb5e-129">Optional.</span></span> <span data-ttu-id="4bb5e-130">Чтобы отслеживать изменения в группах атрибутов, выберите **Enable change tracking** .</span><span class="sxs-lookup"><span data-stu-id="4bb5e-130">Select **Enable change tracking** to track changes to groups of attributes.</span></span> <span data-ttu-id="4bb5e-131">Дополнительные сведения см. в разделе [Добавление атрибутов в группу отслеживания изменений (службы Master Data Services)](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4bb5e-131">For more information, see [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span></span>  
  
12. <span data-ttu-id="4bb5e-132">Нажмите кнопку **Сохранить атрибут**.</span><span class="sxs-lookup"><span data-stu-id="4bb5e-132">Click **Save attribute**.</span></span>  
  
13. <span data-ttu-id="4bb5e-133">На странице **Обслуживание сущности** нажмите кнопку **Сохранить сущность**.</span><span class="sxs-lookup"><span data-stu-id="4bb5e-133">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bb5e-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="4bb5e-134">See Also</span></span>  
 <span data-ttu-id="4bb5e-135">[Атрибуты на основе домена &#40;Master Data Services&#41;](../../2014/master-data-services/domain-based-attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="4bb5e-135">[Domain-Based Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/domain-based-attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="4bb5e-136">[Создание производной иерархии &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-derived-hierarchy-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="4bb5e-136">[Create a Derived Hierarchy &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-derived-hierarchy-master-data-services.md) </span></span>  
 <span data-ttu-id="4bb5e-137">[Измените имя атрибута &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="4bb5e-137">[Change an Attribute Name &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span></span>  
 [<span data-ttu-id="4bb5e-138">Удаление атрибута (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="4bb5e-138">Delete an Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-an-attribute-master-data-services.md)  
  
  
