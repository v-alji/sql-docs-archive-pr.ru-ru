---
title: Создание текстового атрибута (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Master Data Services], creating text attributes
- creating text attributes [Master Data Services]
ms.assetid: cd8b57de-364d-42a3-9273-c1c6b992bb40
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c0f44e0e6c6e3df49b6a3746648ee46a23a7a3ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669456"
---
# <a name="create-a-text-attribute-master-data-services"></a><span data-ttu-id="f4e4e-102">Создание текстового атрибута (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="f4e4e-102">Create a Text Attribute (Master Data Services)</span></span>
  <span data-ttu-id="f4e4e-103">В среде [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]текстовый атрибут создается, если нужно, чтобы пользователи вводили в качестве значения атрибута текстовую строку.</span><span class="sxs-lookup"><span data-stu-id="f4e4e-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a text attribute when you want users to enter a text string as an attribute value.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f4e4e-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="f4e4e-104">Prerequisites</span></span>  
 <span data-ttu-id="f4e4e-105">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="f4e4e-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="f4e4e-106">Необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="f4e4e-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="f4e4e-107">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="f4e4e-107">You must be a model administrator.</span></span> <span data-ttu-id="f4e4e-108">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f4e4e-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="f4e4e-109">должна существовать сущность, для которой создается атрибут.</span><span class="sxs-lookup"><span data-stu-id="f4e4e-109">An entity must exist to create the attribute for.</span></span> <span data-ttu-id="f4e4e-110">Дополнительные сведения см. в разделе [Создание сущности (службы Master Data Services)](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f4e4e-110">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-create-a-text-attribute"></a><span data-ttu-id="f4e4e-111">Создание текстового атрибута</span><span class="sxs-lookup"><span data-stu-id="f4e4e-111">To create a text attribute</span></span>  
  
1.  <span data-ttu-id="f4e4e-112">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="f4e4e-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="f4e4e-113">На странице **Представление модели** в строке меню наведите курсор на **Управление** и щелкните **Сущности**.</span><span class="sxs-lookup"><span data-stu-id="f4e4e-113">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="f4e4e-114">На странице **Обслуживание сущности** выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="f4e4e-114">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="f4e4e-115">Выберите строку сущности, для которой необходимо создать атрибут.</span><span class="sxs-lookup"><span data-stu-id="f4e4e-115">Select the row for the entity that you want to create an attribute for.</span></span>  
  
5.  <span data-ttu-id="f4e4e-116">Щелкните **Изменить выбранную сущность**.</span><span class="sxs-lookup"><span data-stu-id="f4e4e-116">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="f4e4e-117">На странице **Изменение сущности** :</span><span class="sxs-lookup"><span data-stu-id="f4e4e-117">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="f4e4e-118">если атрибут предназначен для конечных элементов, выберите команду **Добавить конечный атрибут** на панели **Атрибуты конечных элементов**;</span><span class="sxs-lookup"><span data-stu-id="f4e4e-118">If the attribute is for leaf members, in the **Leaf member attributes** pane, click **Add leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="f4e4e-119">если атрибут предназначен для объединенных элементов, выберите команду **Добавить объединенный атрибут** на панели **Атрибуты консолидированных элементов**;</span><span class="sxs-lookup"><span data-stu-id="f4e4e-119">If the attribute is for consolidated members, in the **Consolidated member attributes** pane, click **Add consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="f4e4e-120">если атрибут предназначен для коллекций, выберите команду **Добавить атрибут коллекции** на панели **Атрибуты коллекций**.</span><span class="sxs-lookup"><span data-stu-id="f4e4e-120">If the attribute is for collections, in the **Collection attributes** pane, click **Add collection attribute**.</span></span>  
  
7.  <span data-ttu-id="f4e4e-121">Выберите параметр **В свободной форме** на странице **Добавить атрибут** .</span><span class="sxs-lookup"><span data-stu-id="f4e4e-121">On the **Add Attribute** page, select the **Free-form** option.</span></span>  
  
8.  <span data-ttu-id="f4e4e-122">Введите имя атрибута в поле **Имя** .</span><span class="sxs-lookup"><span data-stu-id="f4e4e-122">In the **Name** box, type a name for the attribute.</span></span> <span data-ttu-id="f4e4e-123">Список слов, которые не должны использоваться в качестве имен атрибутов, см. в разделе [зарезервированные слова &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f4e4e-123">For a list of words that should not be used as attribute names, see [Reserved Words &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="f4e4e-124">В поле **Ширина отображаемой области (в пикселях)** введите ширину столбца атрибута для отображения в сетке **обозревателя** .</span><span class="sxs-lookup"><span data-stu-id="f4e4e-124">In the **Display pixel width** box, type the width of the attribute column to be displayed in the **Explorer** grid.</span></span>  
  
10. <span data-ttu-id="f4e4e-125">В списке **Тип данных** выберите **Текст**.</span><span class="sxs-lookup"><span data-stu-id="f4e4e-125">From the **Data type** list, select **Text**.</span></span>  
  
11. <span data-ttu-id="f4e4e-126">В поле **Длина** введите максимально допустимое количество символов.</span><span class="sxs-lookup"><span data-stu-id="f4e4e-126">In the **Length** box, type the maximum number of characters allowed.</span></span>  
  
12. <span data-ttu-id="f4e4e-127">По желанию установите флажок **Включить отслеживание изменений** , чтобы отслеживать изменения в группах атрибутов.</span><span class="sxs-lookup"><span data-stu-id="f4e4e-127">Optionally, select **Enable change tracking** to track changes to groups of attributes.</span></span> <span data-ttu-id="f4e4e-128">Дополнительные сведения см. в разделе [Добавление атрибутов в группу отслеживания изменений (службы Master Data Services)](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f4e4e-128">For more information, see [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span></span>  
  
13. <span data-ttu-id="f4e4e-129">Нажмите кнопку **Сохранить атрибут**.</span><span class="sxs-lookup"><span data-stu-id="f4e4e-129">Click **Save attribute**.</span></span>  
  
14. <span data-ttu-id="f4e4e-130">На странице **Обслуживание сущности** нажмите кнопку **Сохранить сущность**.</span><span class="sxs-lookup"><span data-stu-id="f4e4e-130">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4e4e-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="f4e4e-131">See Also</span></span>  
 <span data-ttu-id="f4e4e-132">[Master Data Services &#40;атрибутов&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="f4e4e-132">[Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="f4e4e-133">[Измените имя атрибута &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="f4e4e-133">[Change an Attribute Name &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span></span>  
 <span data-ttu-id="f4e4e-134">[Создание атрибута на основе домена &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="f4e4e-134">[Create a Domain-Based Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="f4e4e-135">Создание файлового атрибута (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="f4e4e-135">Create a File Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-file-attribute-master-data-services.md)  
  
  
