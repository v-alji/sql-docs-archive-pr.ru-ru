---
title: Добавление атрибутов в группу отслеживания изменений (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- change tracking groups [Master Data Services]
- attributes [Master Data Services], change tracking groups
- change tracking groups [Master Data Services], adding attributes
ms.assetid: e153eb5f-70ca-4c6f-89d8-1f937ed3917d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c8a13dad3ca886668c96c1886f8cd238d9adad9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668415"
---
# <a name="add-attributes-to-a-change-tracking-group-master-data-services"></a><span data-ttu-id="b76d0-102">Добавление атрибутов в группу отслеживания изменений (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="b76d0-102">Add Attributes to a Change Tracking Group (Master Data Services)</span></span>
  <span data-ttu-id="b76d0-103">В среде [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]атрибуты можно добавить в группу отслеживания изменений, чтобы отслеживать изменение значений атрибута.</span><span class="sxs-lookup"><span data-stu-id="b76d0-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], add attributes to a change tracking group when you want to track changes to the attribute's values.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b76d0-104">Если после добавления атрибута в группу отслеживания изменений значения атрибута изменяются, атрибут помечается как измененный в базе данных [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b76d0-104">After you add an attribute to a change tracking group, when values for the attribute change, the attribute is flagged as changed in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="b76d0-105">Создайте бизнес-правило, чтобы предпринимать действия в соответствии с произведенным изменением.</span><span class="sxs-lookup"><span data-stu-id="b76d0-105">Create a business rule to take action based on the change.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b76d0-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="b76d0-106">Prerequisites</span></span>  
 <span data-ttu-id="b76d0-107">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="b76d0-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="b76d0-108">Необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="b76d0-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="b76d0-109">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="b76d0-109">You must be a model administrator.</span></span> <span data-ttu-id="b76d0-110">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b76d0-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="b76d0-111">для добавления в группу отслеживания изменений атрибуты должны уже существовать.</span><span class="sxs-lookup"><span data-stu-id="b76d0-111">Attributes must exist to add to the change tracking group.</span></span> <span data-ttu-id="b76d0-112">Дополнительные сведения см. в статье [Создание текстового атрибута (службы Master Data Services)](../../2014/master-data-services/create-a-text-attribute-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b76d0-112">For more information, see [Create a Text Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md).</span></span>  
  
### <a name="to-add-attributes-to-a-change-tracking-group"></a><span data-ttu-id="b76d0-113">Добавление атрибутов в группу отслеживания изменений</span><span class="sxs-lookup"><span data-stu-id="b76d0-113">To add attributes to a change tracking group</span></span>  
  
1.  <span data-ttu-id="b76d0-114">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="b76d0-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="b76d0-115">На странице **Обозреватель моделей** в строке меню наведите указатель мыши на пункт **Управление** и щелкните **сущности**.</span><span class="sxs-lookup"><span data-stu-id="b76d0-115">On the **Model Explorer** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="b76d0-116">На странице **Обслуживание сущности** выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="b76d0-116">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="b76d0-117">Выберите строку сущности, для которой необходимо отслеживать значения атрибутов.</span><span class="sxs-lookup"><span data-stu-id="b76d0-117">Select the row for the entity that you want to track attribute values for.</span></span>  
  
5.  <span data-ttu-id="b76d0-118">Щелкните **Изменить выбранную сущность**.</span><span class="sxs-lookup"><span data-stu-id="b76d0-118">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="b76d0-119">На странице **Изменение сущности** :</span><span class="sxs-lookup"><span data-stu-id="b76d0-119">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="b76d0-120">Если атрибут предназначен для конечных элементов, выберите атрибут в области **конечные атрибуты** и нажмите кнопку **Изменить конечный атрибут**.</span><span class="sxs-lookup"><span data-stu-id="b76d0-120">If the attribute is for leaf members, in the **Leaf attributes** pane, select the attribute and click **Edit leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="b76d0-121">Если атрибут предназначен для консолидированных элементов, в области **консолидированные атрибуты** выберите атрибут и щелкните **изменить консолидированный атрибут**.</span><span class="sxs-lookup"><span data-stu-id="b76d0-121">If the attribute is for consolidated members, in the **Consolidated attributes** pane, select the attribute and click **Edit consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="b76d0-122">Если атрибут предназначен для коллекций, на панели **атрибуты коллекции** выберите атрибут и щелкните **изменить атрибут коллекции**.</span><span class="sxs-lookup"><span data-stu-id="b76d0-122">If the attribute is for collections, in the **Collection attributes** pane, select the attribute and click **Edit collection attribute**.</span></span>  
  
7.  <span data-ttu-id="b76d0-123">Установите флажок **Включить отслеживание изменений** .</span><span class="sxs-lookup"><span data-stu-id="b76d0-123">Select the **Enable change tracking** check box.</span></span>  
  
8.  <span data-ttu-id="b76d0-124">В поле **Группа отслеживания изменений** введите номер группы.</span><span class="sxs-lookup"><span data-stu-id="b76d0-124">In the **Change tracking group** box, type a number for the group.</span></span>  
  
9. <span data-ttu-id="b76d0-125">Нажмите кнопку **Сохранить атрибут**.</span><span class="sxs-lookup"><span data-stu-id="b76d0-125">Click **Save attribute**.</span></span>  
  
10. <span data-ttu-id="b76d0-126">На странице **Обслуживание сущности** нажмите кнопку **Сохранить сущность**.</span><span class="sxs-lookup"><span data-stu-id="b76d0-126">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
11. <span data-ttu-id="b76d0-127">Повторяйте эти шаги для всех атрибутов, которые необходимо включить в группу.</span><span class="sxs-lookup"><span data-stu-id="b76d0-127">Repeat this procedure for all attributes you want to include in the group.</span></span> <span data-ttu-id="b76d0-128">Используйте для каждого атрибута в группе один и тот же номер группы отслеживания изменений.</span><span class="sxs-lookup"><span data-stu-id="b76d0-128">Use the same change tracking group number for each attribute in the group.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b76d0-129">Next Steps</span><span class="sxs-lookup"><span data-stu-id="b76d0-129">Next Steps</span></span>  
  
-   [<span data-ttu-id="b76d0-130">Инициирование действия на основе значения атрибута (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="b76d0-130">Initiate Actions Based on Attribute Value Changes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/initiate-actions-based-on-attribute-value-changes-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="b76d0-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="b76d0-131">See Also</span></span>  
 <span data-ttu-id="b76d0-132">[Создание текстового атрибута &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="b76d0-132">[Create a Text Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="b76d0-133">Создание атрибута на основе домена (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="b76d0-133">Create a Domain-Based Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md)  
  
  
