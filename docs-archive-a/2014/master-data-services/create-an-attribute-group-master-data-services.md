---
title: Создание группы атрибутов (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attribute groups [Master Data Services], creating
- creating attribute groups [Master Data Services]
ms.assetid: 798c325e-e8d8-412a-b02e-118f2741d1c7
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fbd95869082ea0a73f3abea092163c4705e4da5c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736470"
---
# <a name="create-an-attribute-group-master-data-services"></a><span data-ttu-id="aa62f-102">Создание группы атрибутов (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="aa62f-102">Create an Attribute Group (Master Data Services)</span></span>
  <span data-ttu-id="aa62f-103">В среде [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]группы атрибутов создаются, когда нужно отобразить атрибуты на отдельных вкладках сетки **обозревателя** .</span><span class="sxs-lookup"><span data-stu-id="aa62f-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create attribute groups when you want to display attributes on individual tabs in the **Explorer** grid.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aa62f-104">При создании группы атрибутов она автоматически скрыта от всех пользователей, кроме того, кто ее создал.</span><span class="sxs-lookup"><span data-stu-id="aa62f-104">When you create an attribute group, it is automatically hidden from all users except the one who created it.</span></span> <span data-ttu-id="aa62f-105">Дополнительные сведения о назначении видимости группе см. в разделе [Превращение группы атрибутов в видимую для пользователей (службы Master Data Services)](make-an-attribute-group-visible-to-users-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="aa62f-105">For more information about making the group visible, see [Make an Attribute Group Visible to Users &#40;Master Data Services&#41;](make-an-attribute-group-visible-to-users-master-data-services.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="aa62f-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="aa62f-106">Prerequisites</span></span>  
 <span data-ttu-id="aa62f-107">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="aa62f-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="aa62f-108">Необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="aa62f-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="aa62f-109">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="aa62f-109">You must be a model administrator.</span></span> <span data-ttu-id="aa62f-110">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="aa62f-110">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="aa62f-111">Требуется хотя бы один атрибут.</span><span class="sxs-lookup"><span data-stu-id="aa62f-111">At least one attribute must exist.</span></span> <span data-ttu-id="aa62f-112">Дополнительные сведения см. в статье [Создание текстового атрибута (службы Master Data Services)](../../2014/master-data-services/create-a-text-attribute-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="aa62f-112">For more information, see [Create a Text Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md).</span></span>  
  
### <a name="to-create-an-attribute-group"></a><span data-ttu-id="aa62f-113">Создание группы атрибутов</span><span class="sxs-lookup"><span data-stu-id="aa62f-113">To create an attribute group</span></span>  
  
1.  <span data-ttu-id="aa62f-114">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="aa62f-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="aa62f-115">На странице **представление модели** в строке меню наведите указатель мыши на пункт **Управление** и щелкните **группы атрибутов**.</span><span class="sxs-lookup"><span data-stu-id="aa62f-115">On the **Model View** page, from the menu bar, point to **Manage** and click **Attribute Groups**.</span></span>  
  
3.  <span data-ttu-id="aa62f-116">Выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="aa62f-116">From the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="aa62f-117">Выберите сущность из списка **Сущность** .</span><span class="sxs-lookup"><span data-stu-id="aa62f-117">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="aa62f-118">Выберите **Конечные группы**, **Консолидированные группы**или **Группы коллекций** , чтобы создать группу атрибутов для конечных элементов, объединенных элементов или коллекций соответственно.</span><span class="sxs-lookup"><span data-stu-id="aa62f-118">Click **Leaf Groups**, **Consolidated Groups**, or **Collection Groups** to create an attribute group of leaf members, consolidated members, or collections respectively.</span></span>  
  
6.  <span data-ttu-id="aa62f-119">Нажмите кнопку **Добавить группу атрибутов**.</span><span class="sxs-lookup"><span data-stu-id="aa62f-119">Click **Add attribute group**.</span></span>  
  
7.  <span data-ttu-id="aa62f-120">В поле **имя конечной группы** введите имя группы.</span><span class="sxs-lookup"><span data-stu-id="aa62f-120">In the **Leaf group name** box, type a name for the group.</span></span> <span data-ttu-id="aa62f-121">Это имя отображается на вкладке в **обозревателе**.</span><span class="sxs-lookup"><span data-stu-id="aa62f-121">This is the name displayed on the tab in **Explorer**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="aa62f-122">Если в шаге 5 были выбраны **консолидированные группы** или **группы коллекций** , это поле будет **объединено в группу** или имя **группы коллекций**соответственно.</span><span class="sxs-lookup"><span data-stu-id="aa62f-122">If you selected **Consolidated Groups** or **Collection Groups** in step 5, this box is **Consolidated group name** or **Collection group name**, respectively.</span></span>  
  
8.  <span data-ttu-id="aa62f-123">Нажмите кнопку **Сохранить группу**.</span><span class="sxs-lookup"><span data-stu-id="aa62f-123">Click **Save group**.</span></span>  
  
9. <span data-ttu-id="aa62f-124">Разверните папку группы.</span><span class="sxs-lookup"><span data-stu-id="aa62f-124">Expand the folder for the group.</span></span>  
  
10. <span data-ttu-id="aa62f-125">Нажмите **Атрибуты**.</span><span class="sxs-lookup"><span data-stu-id="aa62f-125">Click **Attributes**.</span></span>  
  
11. <span data-ttu-id="aa62f-126">Нажмите кнопку **изменить выбранный элемент**.</span><span class="sxs-lookup"><span data-stu-id="aa62f-126">Click **Edit selected item**.</span></span>  
  
12. <span data-ttu-id="aa62f-127">Щелкните атрибуты в поле **доступно** и щелкните стрелку **Добавить** .</span><span class="sxs-lookup"><span data-stu-id="aa62f-127">Click attributes in the **Available** box and click the **Add** arrow.</span></span> <span data-ttu-id="aa62f-128">Чтобы добавить все, щелкните стрелку **Добавить все** .</span><span class="sxs-lookup"><span data-stu-id="aa62f-128">To add all, click the **Add All** arrow.</span></span>  
  
13. <span data-ttu-id="aa62f-129">При необходимости можно нажать кнопки со стрелками **вверх** и **вниз** , чтобы изменить порядок атрибутов слева направо.</span><span class="sxs-lookup"><span data-stu-id="aa62f-129">Optionally, click the **Up** and **Down** arrows to change the left-to-right order of the attributes.</span></span>  
  
14. <span data-ttu-id="aa62f-130">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="aa62f-130">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="aa62f-131">Next Steps</span><span class="sxs-lookup"><span data-stu-id="aa62f-131">Next Steps</span></span>  
  
-   [<span data-ttu-id="aa62f-132">Превращение группы атрибутов в видимую для пользователей (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="aa62f-132">Make an Attribute Group Visible to Users &#40;Master Data Services&#41;</span></span>](make-an-attribute-group-visible-to-users-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="aa62f-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="aa62f-133">See Also</span></span>  
 <span data-ttu-id="aa62f-134">[Группы атрибутов &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="aa62f-134">[Attribute Groups &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span></span>  
 <span data-ttu-id="aa62f-135">[Master Data Services &#40;атрибутов&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="aa62f-135">[Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="aa62f-136">[Изменение имени группы атрибутов &#40;Master Data Services&#41;](../../2014/master-data-services/change-an-attribute-group-name-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="aa62f-136">[Change an Attribute Group Name &#40;Master Data Services&#41;](../../2014/master-data-services/change-an-attribute-group-name-master-data-services.md) </span></span>  
 <span data-ttu-id="aa62f-137">[Удаление группы атрибутов &#40;Master Data Services&#41;](../../2014/master-data-services/delete-an-attribute-group-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="aa62f-137">[Delete an Attribute Group &#40;Master Data Services&#41;](../../2014/master-data-services/delete-an-attribute-group-master-data-services.md) </span></span>  
 <span data-ttu-id="aa62f-138">[Конечные разрешения &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="aa62f-138">[Leaf Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="aa62f-139">Объединенные разрешения &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="aa62f-139">Consolidated Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/consolidated-permissions-master-data-services.md)  
  
  
