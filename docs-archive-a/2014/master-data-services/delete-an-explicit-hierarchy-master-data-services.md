---
title: Удаление явной иерархии (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- explicit hierarchies, deleting
- deleting explicit hierarchies [Master Data Services]
ms.assetid: 4ce177b0-9884-47a2-9cea-212e845dd762
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 744f96a2705a3abbc2318ecd3c9b0c7fffb7605e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669452"
---
# <a name="delete-an-explicit-hierarchy-master-data-services"></a><span data-ttu-id="3e89a-102">Удаление явной иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="3e89a-102">Delete an Explicit Hierarchy (Master Data Services)</span></span>
  <span data-ttu-id="3e89a-103">В службах [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]явные иерархии удаляются тогда, когда в них отпадает необходимость.</span><span class="sxs-lookup"><span data-stu-id="3e89a-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete an explicit hierarchy when you no longer need it.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="3e89a-104">При удалении явной иерархии все консолидированные элементы в этой иерархии также удаляются.</span><span class="sxs-lookup"><span data-stu-id="3e89a-104">When you delete an explicit hierarchy, all consolidated members in the hierarchy are deleted also.</span></span> <span data-ttu-id="3e89a-105">Если удаляются все явные иерархии для сущности, то все коллекции для этой сущности также удаляются и сущность перестает поддерживать явные иерархии и коллекции.</span><span class="sxs-lookup"><span data-stu-id="3e89a-105">If you delete all explicit hierarchies for an entity, all collections for the entity are also deleted and the entity is no longer enabled for explicit hierarchies and collections.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3e89a-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="3e89a-106">Prerequisites</span></span>  
 <span data-ttu-id="3e89a-107">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="3e89a-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="3e89a-108">Необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="3e89a-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="3e89a-109">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="3e89a-109">You must be a model administrator.</span></span> <span data-ttu-id="3e89a-110">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3e89a-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-an-explicit-hierarchy"></a><span data-ttu-id="3e89a-111">Удаление явной иерархии</span><span class="sxs-lookup"><span data-stu-id="3e89a-111">To delete an explicit hierarchy</span></span>  
  
1.  <span data-ttu-id="3e89a-112">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="3e89a-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="3e89a-113">На странице **Представление модели** в строке меню наведите курсор на **Управление** и щелкните **Сущности**.</span><span class="sxs-lookup"><span data-stu-id="3e89a-113">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="3e89a-114">На странице **Обслуживание сущности** выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="3e89a-114">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="3e89a-115">Выберите строку сущности, содержащую явную иерархию, которую необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="3e89a-115">Select the row for the entity that contains the explicit hierarchy you want to delete.</span></span>  
  
5.  <span data-ttu-id="3e89a-116">Щелкните **Изменить выбранную сущность**.</span><span class="sxs-lookup"><span data-stu-id="3e89a-116">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="3e89a-117">На странице **Изменение сущности** на панели **явные иерархии** щелкните явную иерархию, которую нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="3e89a-117">On the **Edit Entity** page, in the **Explicit Hierarchies** pane, click the explicit hierarchy you want to delete.</span></span>  
  
7.  <span data-ttu-id="3e89a-118">Нажмите кнопку **Удалить выбранную иерархию**.</span><span class="sxs-lookup"><span data-stu-id="3e89a-118">Click **Delete selected hierarchy**.</span></span>  
  
8.  <span data-ttu-id="3e89a-119">В диалоговом окне подтверждения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3e89a-119">In the confirmation dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="3e89a-120">В дополнительном диалоговом окне подтверждения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3e89a-120">In the additional confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e89a-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="3e89a-121">See Also</span></span>  
 <span data-ttu-id="3e89a-122">[Создание явной иерархии &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="3e89a-122">[Create an Explicit Hierarchy &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md) </span></span>  
 [<span data-ttu-id="3e89a-123">Явные иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="3e89a-123">Explicit Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)  
  
  
