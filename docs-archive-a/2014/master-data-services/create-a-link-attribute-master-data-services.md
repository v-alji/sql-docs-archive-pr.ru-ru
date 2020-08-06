---
title: Создание атрибута ссылки (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Master Data Services], creating link attributes
- creating link attributes [Master Data Services]
ms.assetid: e6658e9c-5b08-4b8d-b556-17ec2dd041d2
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 4770d7904371c10dc6720e8d3d7f28ca797d9b80
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668975"
---
# <a name="create-a-link-attribute-master-data-services"></a><span data-ttu-id="ebc54-102">Создание атрибута ссылки (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="ebc54-102">Create a Link Attribute (Master Data Services)</span></span>
  <span data-ttu-id="ebc54-103">В среде [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] атрибут ссылки создается, если нужно, чтобы пользователи вводили в качестве значения атрибута гиперссылку, такую как `http://www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="ebc54-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a link attribute when you want users to enter a hyperlink as an attribute value, such as `http://www.contoso.com`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ebc54-104">Когда пользователи вводят значение для атрибута ссылки, строка должна начинаться с **http://** . В противном случае будет выведено сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="ebc54-104">When users enter a value for a link attribute, the string must begin with **http://** or an error will be displayed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ebc54-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="ebc54-105">Prerequisites</span></span>  
 <span data-ttu-id="ebc54-106">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="ebc54-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="ebc54-107">Необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="ebc54-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="ebc54-108">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="ebc54-108">You must be a model administrator.</span></span> <span data-ttu-id="ebc54-109">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ebc54-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="ebc54-110">должна существовать сущность, для которой создается атрибут.</span><span class="sxs-lookup"><span data-stu-id="ebc54-110">An entity must exist to create the attribute for.</span></span> <span data-ttu-id="ebc54-111">Дополнительные сведения см. в разделе [Создание сущности (службы Master Data Services)](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ebc54-111">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-create-a-link-attribute"></a><span data-ttu-id="ebc54-112">Создание атрибута ссылки</span><span class="sxs-lookup"><span data-stu-id="ebc54-112">To create a link attribute</span></span>  
  
1.  <span data-ttu-id="ebc54-113">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="ebc54-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="ebc54-114">На странице **Представление модели** в строке меню наведите курсор на **Управление** и щелкните **Сущности**.</span><span class="sxs-lookup"><span data-stu-id="ebc54-114">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="ebc54-115">На странице **Обслуживание сущности** выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="ebc54-115">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="ebc54-116">Выберите строку сущности, для которой необходимо создать атрибут.</span><span class="sxs-lookup"><span data-stu-id="ebc54-116">Select the row for the entity that you want to create an attribute for.</span></span>  
  
5.  <span data-ttu-id="ebc54-117">Щелкните **Изменить выбранную сущность**.</span><span class="sxs-lookup"><span data-stu-id="ebc54-117">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="ebc54-118">На странице **Изменение сущности** :</span><span class="sxs-lookup"><span data-stu-id="ebc54-118">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="ebc54-119">если атрибут предназначен для конечных элементов, выберите команду **Добавить конечный атрибут** на панели **Атрибуты конечных элементов**;</span><span class="sxs-lookup"><span data-stu-id="ebc54-119">If the attribute is for leaf members, in the **Leaf member attributes** pane, click **Add leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="ebc54-120">если атрибут предназначен для объединенных элементов, выберите команду **Добавить объединенный атрибут** на панели **Атрибуты консолидированных элементов**;</span><span class="sxs-lookup"><span data-stu-id="ebc54-120">If the attribute is for consolidated members, in the **Consolidated member attributes** pane, click **Add consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="ebc54-121">если атрибут предназначен для коллекций, выберите команду **Добавить атрибут коллекции** на панели **Атрибуты коллекций**.</span><span class="sxs-lookup"><span data-stu-id="ebc54-121">If the attribute is for collections, in the **Collection attributes** pane, click **Add collection attribute**.</span></span>  
  
7.  <span data-ttu-id="ebc54-122">Выберите параметр **В свободной форме** на странице **Добавить атрибут** .</span><span class="sxs-lookup"><span data-stu-id="ebc54-122">On the **Add Attribute** page, select the **Free-form** option.</span></span>  
  
8.  <span data-ttu-id="ebc54-123">Введите имя атрибута в поле **Имя** .</span><span class="sxs-lookup"><span data-stu-id="ebc54-123">In the **Name** box, type a name for the attribute.</span></span> <span data-ttu-id="ebc54-124">Список слов, которые не должны использоваться в качестве имен атрибутов, см. в разделе [зарезервированные слова &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ebc54-124">For a list of words that should not be used as attribute names, see [Reserved Words &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="ebc54-125">В поле **Ширина отображаемой области (в пикселях)** введите ширину столбца атрибута для отображения в сетке **обозревателя** .</span><span class="sxs-lookup"><span data-stu-id="ebc54-125">In the **Display pixel width** box, type the width of the attribute column to be displayed in the **Explorer** grid.</span></span>  
  
10. <span data-ttu-id="ebc54-126">В списке **Тип данных** выберите **Ссылка**.</span><span class="sxs-lookup"><span data-stu-id="ebc54-126">From the **Data type** list, select **Link**.</span></span>  
  
11. <span data-ttu-id="ebc54-127">В поле **Длина** введите максимально допустимое количество символов.</span><span class="sxs-lookup"><span data-stu-id="ebc54-127">In the **Length** box, type the maximum number of characters allowed.</span></span>  
  
12. <span data-ttu-id="ebc54-128">По желанию установите флажок **Включить отслеживание изменений** , чтобы отслеживать изменения в группах атрибутов.</span><span class="sxs-lookup"><span data-stu-id="ebc54-128">Optionally, select **Enable change tracking** to track changes to groups of attributes.</span></span> <span data-ttu-id="ebc54-129">Дополнительные сведения см. в разделе [Добавление атрибутов в группу отслеживания изменений (службы Master Data Services)](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ebc54-129">For more information, see [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span></span>  
  
13. <span data-ttu-id="ebc54-130">Нажмите кнопку **Сохранить атрибут**.</span><span class="sxs-lookup"><span data-stu-id="ebc54-130">Click **Save attribute**.</span></span>  
  
14. <span data-ttu-id="ebc54-131">На странице **Обслуживание сущности** нажмите кнопку **Сохранить сущность**.</span><span class="sxs-lookup"><span data-stu-id="ebc54-131">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebc54-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="ebc54-132">See Also</span></span>  
 <span data-ttu-id="ebc54-133">[Master Data Services &#40;атрибутов&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="ebc54-133">[Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="ebc54-134">[Измените имя атрибута &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="ebc54-134">[Change an Attribute Name &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span></span>  
 <span data-ttu-id="ebc54-135">[Создание атрибута на основе домена &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="ebc54-135">[Create a Domain-Based Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="ebc54-136">Создание файлового атрибута (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="ebc54-136">Create a File Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-file-attribute-master-data-services.md)  
  
  
