---
title: Создание явной иерархии (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating explicit hierarchies [Master Data Services]
- explicit hierarchies, creating
ms.assetid: ba768393-6990-4eda-8cb0-d58cb3cfc2e2
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: aebf95e68f210fe5a573aed092231670c10fa188
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666099"
---
# <a name="create-an-explicit-hierarchy-master-data-services"></a><span data-ttu-id="9c1e5-102">Создание явной иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="9c1e5-102">Create an Explicit Hierarchy (Master Data Services)</span></span>
  <span data-ttu-id="9c1e5-103">В среде [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]явные иерархии создаются, если необходима неоднородная иерархия, элементы которой могут располагаться на любом уровне.</span><span class="sxs-lookup"><span data-stu-id="9c1e5-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create an explicit hierarchy when you need a ragged hierarchy in which members can exist at any level.</span></span> <span data-ttu-id="9c1e5-104">Явные иерархии содержат элементы из одной сущности.</span><span class="sxs-lookup"><span data-stu-id="9c1e5-104">Explicit hierarchies contain members from a single entity.</span></span>  
  
 <span data-ttu-id="9c1e5-105">После создания явной иерархии в нее можно добавлять элементы в функциональной области **Обозреватель** .</span><span class="sxs-lookup"><span data-stu-id="9c1e5-105">After you create an explicit hierarchy, you can add members to it in the **Explorer** functional area.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9c1e5-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="9c1e5-106">Prerequisites</span></span>  
 <span data-ttu-id="9c1e5-107">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="9c1e5-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="9c1e5-108">Необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="9c1e5-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="9c1e5-109">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="9c1e5-109">You must be a model administrator.</span></span> <span data-ttu-id="9c1e5-110">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9c1e5-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="9c1e5-111">Для сущности необходимо разрешить использование явных иерархий и коллекций.</span><span class="sxs-lookup"><span data-stu-id="9c1e5-111">The entity must be enabled for explicit hierarchies and collections.</span></span> <span data-ttu-id="9c1e5-112">Дополнительные сведения см. в разделе [Включение сущности для явных иерархий и коллекций &#40;Master Data Services&#41;](../../2014/master-data-services/enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9c1e5-112">For more information, see [Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;](../../2014/master-data-services/enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span></span>  
  
### <a name="to-create-an-explicit-hierarchy"></a><span data-ttu-id="9c1e5-113">Создание явной иерархии</span><span class="sxs-lookup"><span data-stu-id="9c1e5-113">To create an explicit hierarchy</span></span>  
  
1.  <span data-ttu-id="9c1e5-114">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="9c1e5-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="9c1e5-115">На странице **Представление модели** в строке меню наведите курсор на **Управление** и щелкните **Сущности**.</span><span class="sxs-lookup"><span data-stu-id="9c1e5-115">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="9c1e5-116">На странице **Обслуживание сущности** выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="9c1e5-116">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="9c1e5-117">Выберите строку сущности, для которой необходимо создать явную иерархию.</span><span class="sxs-lookup"><span data-stu-id="9c1e5-117">Select the row for the entity that you want to create an explicit hierarchy for.</span></span>  
  
5.  <span data-ttu-id="9c1e5-118">Щелкните **Изменить выбранную сущность**.</span><span class="sxs-lookup"><span data-stu-id="9c1e5-118">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="9c1e5-119">На странице **Изменение сущности** на панели **явные иерархии** нажмите кнопку **Добавить явную иерархию**.</span><span class="sxs-lookup"><span data-stu-id="9c1e5-119">On the **Edit Entity** page, in the **Explicit hierarchies** pane, click **Add explicit hierarchy**.</span></span>  
  
7.  <span data-ttu-id="9c1e5-120">На странице **Добавление явной иерархии** в поле **имя явной иерархии** введите имя иерархии.</span><span class="sxs-lookup"><span data-stu-id="9c1e5-120">On the **Add Explicit Hierarchy** page, in the **Explicit hierarchy name** box, type a name for the hierarchy.</span></span>  
  
8.  <span data-ttu-id="9c1e5-121">По желанию снимите флажок **Обязательная иерархия** для создания необязательной иерархии.</span><span class="sxs-lookup"><span data-stu-id="9c1e5-121">Optionally, clear the **Mandatory hierarchy** check box to create the hierarchy as a non-mandatory hierarchy.</span></span> <span data-ttu-id="9c1e5-122">Дополнительные сведения о типах иерархий см. в разделе [Явные иерархии (службы Master Data Services)](../../2014/master-data-services/explicit-hierarchies-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9c1e5-122">For more information about hierarchy types, see [Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="9c1e5-123">Нажмите кнопку **Сохранить иерархию**.</span><span class="sxs-lookup"><span data-stu-id="9c1e5-123">Click **Save hierarchy**.</span></span>  
  
10. <span data-ttu-id="9c1e5-124">На странице **Изменение сущности** нажмите кнопку **Сохранить сущность**.</span><span class="sxs-lookup"><span data-stu-id="9c1e5-124">On the **Edit Entity** page, click **Save entity**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9c1e5-125">Next Steps</span><span class="sxs-lookup"><span data-stu-id="9c1e5-125">Next Steps</span></span>  
  
-   [<span data-ttu-id="9c1e5-126">Создание объединенного элемента (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="9c1e5-126">Create a Consolidated Member &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-consolidated-member-master-data-services.md)  
  
-   [<span data-ttu-id="9c1e5-127">Перемещение элементов в иерархии &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9c1e5-127">Move Members within a Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/move-members-within-a-hierarchy-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="9c1e5-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="9c1e5-128">See Also</span></span>  
 <span data-ttu-id="9c1e5-129">[Явные иерархии &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9c1e5-129">[Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span></span>  
 <span data-ttu-id="9c1e5-130">[Производные иерархии с явно заданными ограничениями &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-with-explicit-caps-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9c1e5-130">[Derived Hierarchies with Explicit Caps &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-with-explicit-caps-master-data-services.md) </span></span>  
 [<span data-ttu-id="9c1e5-131">Изменение имени явной иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="9c1e5-131">Change an Explicit Hierarchy Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-an-explicit-hierarchy-name-master-data-services.md)  
  
  
