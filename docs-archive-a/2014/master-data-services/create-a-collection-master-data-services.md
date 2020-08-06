---
title: Создание коллекции (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating collections [Master Data Services]
- collections [Master Data Services], creating
ms.assetid: 3d4f152c-863c-4385-bca9-a9fcd0402e1f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f76171b4fd9b07f751d4f919011a443253fbe31b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734218"
---
# <a name="create-a-collection-master-data-services"></a><span data-ttu-id="632be-102">Создание коллекции (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="632be-102">Create a Collection (Master Data Services)</span></span>
  <span data-ttu-id="632be-103">Если нужно создать плоские списки конечных и консолидированных элементов, создайте коллекцию в среде [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="632be-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a collection when you want to create flat lists of leaf and consolidated members.</span></span> <span data-ttu-id="632be-104">Коллекции необязательно должны включать все элементы из сущности.</span><span class="sxs-lookup"><span data-stu-id="632be-104">Collections do not need to include all members from the entity.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="632be-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="632be-105">Prerequisites</span></span>  
 <span data-ttu-id="632be-106">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="632be-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="632be-107">Необходимо иметь разрешение на доступ к функциональной области **Обозреватель** .</span><span class="sxs-lookup"><span data-stu-id="632be-107">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="632be-108">как минимум необходимо разрешение **Обновление** на объект модели коллекции для сущности;</span><span class="sxs-lookup"><span data-stu-id="632be-108">You must have a minimum of **Update** permission to the collection model object for the entity.</span></span>  
  
-   <span data-ttu-id="632be-109">Для сущности необходимо разрешить использование явных иерархий и коллекций.</span><span class="sxs-lookup"><span data-stu-id="632be-109">The entity must be enabled for explicit hierarchies and collections.</span></span> <span data-ttu-id="632be-110">Дополнительные сведения см. в разделе [Включение сущности для явных иерархий и коллекций &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="632be-110">For more information, see [Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span></span>  
  
### <a name="to-create-a-collection"></a><span data-ttu-id="632be-111">Создание коллекции</span><span class="sxs-lookup"><span data-stu-id="632be-111">To create a collection</span></span>  
  
1.  <span data-ttu-id="632be-112">На домашней странице [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] выберите модель в списке **Модель** .</span><span class="sxs-lookup"><span data-stu-id="632be-112">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="632be-113">Выберите версию из списка **Версия** .</span><span class="sxs-lookup"><span data-stu-id="632be-113">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="632be-114">Нажмите кнопку **Браузер**.</span><span class="sxs-lookup"><span data-stu-id="632be-114">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="632be-115">В строке меню наведите указатель на меню **Коллекции** и выберите пункт *entity_name*.</span><span class="sxs-lookup"><span data-stu-id="632be-115">From the menu bar, point to **Collections** and click *entity_name*.</span></span>  
  
5.  <span data-ttu-id="632be-116">Нажмите кнопку **Добавить коллекцию**.</span><span class="sxs-lookup"><span data-stu-id="632be-116">Click **Add collection**.</span></span>  
  
6.  <span data-ttu-id="632be-117">На вкладке **Подробные сведения** в поле **Имя** введите имя коллекции.</span><span class="sxs-lookup"><span data-stu-id="632be-117">On the **Details** tab, in the **Name** box, type a name for the collection.</span></span>  
  
7.  <span data-ttu-id="632be-118">В поле **Код** введите уникальный код коллекции.</span><span class="sxs-lookup"><span data-stu-id="632be-118">In the **Code** box, type a unique code for the collection.</span></span>  
  
8.  <span data-ttu-id="632be-119">При необходимости в текстовом поле **Описание** введите описание коллекции.</span><span class="sxs-lookup"><span data-stu-id="632be-119">Optionally, in the **Description** box, type a description for the collection.</span></span>  
  
9. <span data-ttu-id="632be-120">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="632be-120">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="632be-121">Next Steps</span><span class="sxs-lookup"><span data-stu-id="632be-121">Next Steps</span></span>  
  
-   [<span data-ttu-id="632be-122">Добавление элементов в коллекцию (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="632be-122">Add Members to a Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/add-members-to-a-collection-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="632be-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="632be-123">See Also</span></span>  
 <span data-ttu-id="632be-124">[&#40;коллекций Master Data Services&#41;](../../2014/master-data-services/collections-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="632be-124">[Collections &#40;Master Data Services&#41;](../../2014/master-data-services/collections-master-data-services.md) </span></span>  
 <span data-ttu-id="632be-125">[Удаление элемента или коллекции &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="632be-125">[Delete a Member or Collection &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md) </span></span>  
 [<span data-ttu-id="632be-126">Создание явной иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="632be-126">Create an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md)  
  
  
