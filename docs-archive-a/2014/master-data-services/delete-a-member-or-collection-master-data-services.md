---
title: Удаление элемента или коллекции (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- collections [Master Data Services], deleting
- leaf members [Master Data Services], deleting
- deleting members [Master Data Services]
- members [Master Data Services], deleting
- consolidated members [Master Data Services], deleting
ms.assetid: 519130a7-4226-4d71-9124-d2ee0ce7e5bd
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9b248750c0e755c3fc9e32d45068c754e64957b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728421"
---
# <a name="delete-a-member-or-collection-master-data-services"></a><span data-ttu-id="f5479-102">Удаление элемента или коллекции (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="f5479-102">Delete a Member or Collection (Master Data Services)</span></span>
  <span data-ttu-id="f5479-103">В службах [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]элементы и коллекции следует удалять, когда в них больше нет необходимости.</span><span class="sxs-lookup"><span data-stu-id="f5479-103">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], delete a member or collection when you no longer need it.</span></span> <span data-ttu-id="f5479-104">Если необходимо удалить большое количество элементов, лучше воспользоваться промежуточным процессом.</span><span class="sxs-lookup"><span data-stu-id="f5479-104">If you want to delete members in bulk, use the staging process instead.</span></span> <span data-ttu-id="f5479-105">Дополнительные сведения см. [в разделе Отключение или удаление элементов с помощью промежуточного процесса &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f5479-105">For more information, see [Deactivate or Delete Members by Using the Staging Process &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f5479-106">Невозможно удалить элемент, если он используется в качестве значения атрибута на основе домена для другого элемента.</span><span class="sxs-lookup"><span data-stu-id="f5479-106">You cannot delete a member if it is used as a domain-based attribute value for another member.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f5479-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="f5479-107">Prerequisites</span></span>  
 <span data-ttu-id="f5479-108">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="f5479-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="f5479-109">Необходимо иметь разрешение на доступ к функциональной области **Обозреватель** .</span><span class="sxs-lookup"><span data-stu-id="f5479-109">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="f5479-110">Для членов необходимо иметь как минимум разрешение **Обновление** для объекта конечной модели, из которого удаляется элемент.</span><span class="sxs-lookup"><span data-stu-id="f5479-110">For members, you must have a minimum of **Update** permission to the leaf model object you are deleting a member from.</span></span>  
  
-   <span data-ttu-id="f5479-111">Для коллекций необходимо как минимум разрешение **Обновление** на удаляемый конечный объект коллекции.</span><span class="sxs-lookup"><span data-stu-id="f5479-111">For collections, you must have a minimum of **Update** permission to the leaf collection object you are deleting.</span></span>  
  
### <a name="to-delete-a-member-or-collection"></a><span data-ttu-id="f5479-112">Удаление элемента или коллекции</span><span class="sxs-lookup"><span data-stu-id="f5479-112">To delete a member or collection</span></span>  
  
1.  <span data-ttu-id="f5479-113">На домашней странице [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] выберите модель в списке **Модель** .</span><span class="sxs-lookup"><span data-stu-id="f5479-113">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="f5479-114">Выберите версию из списка **Версия** .</span><span class="sxs-lookup"><span data-stu-id="f5479-114">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="f5479-115">Нажмите кнопку **Браузер**.</span><span class="sxs-lookup"><span data-stu-id="f5479-115">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="f5479-116">Для удаления</span><span class="sxs-lookup"><span data-stu-id="f5479-116">To delete:</span></span>  
  
    -   <span data-ttu-id="f5479-117">конечного элемента в строке меню наведите указатель мыши на **Сущности** и щелкните имя сущности, содержащей элемент;</span><span class="sxs-lookup"><span data-stu-id="f5479-117">A leaf member, from the menu bar, point to **Entities** and click the name of the entity that contains the member.</span></span>  
  
    -   <span data-ttu-id="f5479-118">объединенного элемента в строке меню наведите указатель мыши на **Иерархии** и щелкните имя иерархии, содержащей элемент.</span><span class="sxs-lookup"><span data-stu-id="f5479-118">A consolidated member, from the menu bar, point to **Hierarchies** and click the name of the hierarchy that contains the member.</span></span> <span data-ttu-id="f5479-119">Затем щелкните узел в иерархии, содержащий элемент.</span><span class="sxs-lookup"><span data-stu-id="f5479-119">Then click the node in the hierarchy that contains the member.</span></span>  
  
    -   <span data-ttu-id="f5479-120">коллекции в строке меню наведите указатель мыши на **Коллекции** и щелкните имя сущности, содержащей коллекцию.</span><span class="sxs-lookup"><span data-stu-id="f5479-120">A collection, from the menu bar, point to **Collections** and click the name of the entity that contains the collection.</span></span>  
  
5.  <span data-ttu-id="f5479-121">Щелкните в сетке строку удаляемого элемента или коллекции.</span><span class="sxs-lookup"><span data-stu-id="f5479-121">In the grid, click the row of the member or collection you want to delete.</span></span>  
  
6.  <span data-ttu-id="f5479-122">Нажмите кнопку **Удалить элемент**, **Удалить**или **Удалить коллекцию**.</span><span class="sxs-lookup"><span data-stu-id="f5479-122">Click **Delete Member**, **Delete**, or **Delete Collection**.</span></span>  
  
7.  <span data-ttu-id="f5479-123">В диалоговом окне подтверждения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f5479-123">In the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5479-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="f5479-124">See Also</span></span>  
 <span data-ttu-id="f5479-125">[Повторная активация элемента или коллекции &#40;Master Data Services&#41;](../../2014/master-data-services/reactivate-a-member-or-collection-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="f5479-125">[Reactivate a Member or Collection &#40;Master Data Services&#41;](../../2014/master-data-services/reactivate-a-member-or-collection-master-data-services.md) </span></span>  
 <span data-ttu-id="f5479-126">[Master Data Services &#40;членов&#41;](../../2014/master-data-services/members-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="f5479-126">[Members &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span></span>  
 [<span data-ttu-id="f5479-127">Коллекции (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="f5479-127">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)  
  
  
