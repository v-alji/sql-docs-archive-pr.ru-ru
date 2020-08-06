---
title: Включение сущности для явных иерархий и коллекций (Master Data Services) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- entities [Master Data Services], enabling for collections
- entities [Master Data Services], enabling for explicit hierarchies
ms.assetid: 380e77e5-ad60-43d4-9605-34a84525f5dd
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: a8129b3f67f050603f85ffb782a9dd209cb303fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728397"
---
# <a name="enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services"></a><span data-ttu-id="9b4f6-102">Активация сущности для явных иерархий и коллекций (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="9b4f6-102">Enable an Entity for Explicit Hierarchies and Collections (Master Data Services)</span></span>
  <span data-ttu-id="9b4f6-103">В среде [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] активации сущностей в явные иерархии и коллекции позволяет создавать явные иерархии и коллекции для сущности.</span><span class="sxs-lookup"><span data-stu-id="9b4f6-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], enable an entity for explicit hierarchies and collections so that you can create explicit hierarchies and collections for the entity.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9b4f6-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="9b4f6-104">Prerequisites</span></span>  
 <span data-ttu-id="9b4f6-105">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="9b4f6-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="9b4f6-106">Необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="9b4f6-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="9b4f6-107">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="9b4f6-107">You must be a model administrator.</span></span> <span data-ttu-id="9b4f6-108">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9b4f6-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="9b4f6-109">Сущность должна существовать.</span><span class="sxs-lookup"><span data-stu-id="9b4f6-109">An entity must exist.</span></span> <span data-ttu-id="9b4f6-110">Дополнительные сведения см. в разделе [Создание сущности (службы Master Data Services)](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9b4f6-110">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-enable-an-entity-for-explicit-hierarchies-and-collections"></a><span data-ttu-id="9b4f6-111">Включение сущности в явные иерархии и коллекции</span><span class="sxs-lookup"><span data-stu-id="9b4f6-111">To enable an entity for explicit hierarchies and collections</span></span>  
  
1.  <span data-ttu-id="9b4f6-112">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="9b4f6-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="9b4f6-113">На странице **Представление модели** в строке меню наведите курсор на **Управление** и щелкните **Сущности**.</span><span class="sxs-lookup"><span data-stu-id="9b4f6-113">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="9b4f6-114">На странице **Обслуживание сущности** выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="9b4f6-114">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="9b4f6-115">Выберите строку для сущности, которую необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="9b4f6-115">Select the row for the entity that you want to update.</span></span>  
  
5.  <span data-ttu-id="9b4f6-116">Щелкните **Изменить выбранную сущность**.</span><span class="sxs-lookup"><span data-stu-id="9b4f6-116">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="9b4f6-117">В списке **включить явные иерархии и коллекции** выберите **Да**.</span><span class="sxs-lookup"><span data-stu-id="9b4f6-117">From the **Enable explicit hierarchies and collections** list, select **Yes**.</span></span>  
  
7.  <span data-ttu-id="9b4f6-118">В поле **имя явной иерархии** введите имя для явной иерархии.</span><span class="sxs-lookup"><span data-stu-id="9b4f6-118">In the **Explicit hierarchy name** box, type a name for an explicit hierarchy.</span></span>  
  
8.  <span data-ttu-id="9b4f6-119">По желанию снимите флажок **Обязательная иерархия** для создания необязательной иерархии.</span><span class="sxs-lookup"><span data-stu-id="9b4f6-119">Optionally, clear the **Mandatory hierarchy** check box to create the hierarchy as a non-mandatory hierarchy.</span></span>  
  
9. <span data-ttu-id="9b4f6-120">Нажмите кнопку **Сохранить сущность**.</span><span class="sxs-lookup"><span data-stu-id="9b4f6-120">Click **Save entity**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9b4f6-121">Next Steps</span><span class="sxs-lookup"><span data-stu-id="9b4f6-121">Next Steps</span></span>  
  
-   [<span data-ttu-id="9b4f6-122">Создание явной иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="9b4f6-122">Create an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md)  
  
-   [<span data-ttu-id="9b4f6-123">Создание коллекции (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="9b4f6-123">Create a Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-collection-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="9b4f6-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="9b4f6-124">See Also</span></span>  
 <span data-ttu-id="9b4f6-125">[Сущности &#40;Master Data Services&#41;](../../2014/master-data-services/entities-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9b4f6-125">[Entities &#40;Master Data Services&#41;](../../2014/master-data-services/entities-master-data-services.md) </span></span>  
 <span data-ttu-id="9b4f6-126">[Явные иерархии &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9b4f6-126">[Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span></span>  
 [<span data-ttu-id="9b4f6-127">Коллекции (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="9b4f6-127">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)  
  
  
