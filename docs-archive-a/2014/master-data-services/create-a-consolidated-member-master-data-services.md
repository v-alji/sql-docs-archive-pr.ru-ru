---
title: Создание объединенного элемента (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating consolidated members [Master Data Services]
- members [Master Data Services], creating consolidated members
- consolidated members [Master Data Services], creating
ms.assetid: 431ab2d2-5517-4372-9980-142b05427c08
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c41673f6f3bf1f4de2a831ecd659321b273b6af9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734209"
---
# <a name="create-a-consolidated-member-master-data-services"></a><span data-ttu-id="0b4ee-102">Create a Consolidated Member (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="0b4ee-102">Create a Consolidated Member (Master Data Services)</span></span>
  <span data-ttu-id="0b4ee-103">В среде [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]объединенный элемент создается, когда нужен родительский узел для явной иерархии.</span><span class="sxs-lookup"><span data-stu-id="0b4ee-103">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], create a consolidated member when you want a parent node for an explicit hierarchy.</span></span> <span data-ttu-id="0b4ee-104">Консолидированные элементы могут содержать собственные атрибуты.</span><span class="sxs-lookup"><span data-stu-id="0b4ee-104">Consolidated members can have their own attributes.</span></span> <span data-ttu-id="0b4ee-105">Они используются для группировки.</span><span class="sxs-lookup"><span data-stu-id="0b4ee-105">They are used for grouping.</span></span> <span data-ttu-id="0b4ee-106">Как показано в следующем примере, консолидированные элементы можно использовать для групп учетных записей, содержащих учетные записи.</span><span class="sxs-lookup"><span data-stu-id="0b4ee-106">As shown in the following example, consolidated members can be used for account groups that have accounts under them.</span></span>

 <span data-ttu-id="0b4ee-107">![Консолидированные члены MDS](../../2014/master-data-services/media/mds-consolidated-members.png "Консолидированные члены MDS")</span><span class="sxs-lookup"><span data-stu-id="0b4ee-107">![MDS Consolidated Members](../../2014/master-data-services/media/mds-consolidated-members.png "MDS Consolidated Members")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0b4ee-108">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="0b4ee-108">Prerequisites</span></span>
 <span data-ttu-id="0b4ee-109">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="0b4ee-109">To perform this procedure:</span></span>

-   <span data-ttu-id="0b4ee-110">Необходимо иметь разрешение на доступ к функциональной области **Обозреватель** .</span><span class="sxs-lookup"><span data-stu-id="0b4ee-110">You must have permission to access the **Explorer** functional area.</span></span>

-   <span data-ttu-id="0b4ee-111">как минимум, необходимо разрешение **Обновление** на объединенный объект модели для сущности, в которую нужно добавить элемент.</span><span class="sxs-lookup"><span data-stu-id="0b4ee-111">You must have a minimum of **Update** permission to the consolidated model object for the entity you are adding a member to.</span></span>

### <a name="to-create-a-consolidated-member"></a><span data-ttu-id="0b4ee-112">Создание объединенного элемента</span><span class="sxs-lookup"><span data-stu-id="0b4ee-112">To create a consolidated member</span></span>

1.  <span data-ttu-id="0b4ee-113">На домашней странице [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] выберите модель в списке **Модель** .</span><span class="sxs-lookup"><span data-stu-id="0b4ee-113">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>

2.  <span data-ttu-id="0b4ee-114">Выберите версию из списка **Версия** .</span><span class="sxs-lookup"><span data-stu-id="0b4ee-114">From the **Version** list, select a version.</span></span>

3.  <span data-ttu-id="0b4ee-115">Нажмите кнопку **Браузер**.</span><span class="sxs-lookup"><span data-stu-id="0b4ee-115">Click **Explorer**.</span></span>

4.  <span data-ttu-id="0b4ee-116">В строке меню наведите указатель мыши на **Иерархии** и щелкните имя иерархии, к которой нужно добавить объединенный элемент.</span><span class="sxs-lookup"><span data-stu-id="0b4ee-116">From the menu bar, point to **Hierarchies** and click the name of the hierarchy you want to add a consolidated member to.</span></span>

5.  <span data-ttu-id="0b4ee-117">Над сеткой выберите вариант **Консолидированные элементы** или **Все Консолидированные элементы в иерархии** .</span><span class="sxs-lookup"><span data-stu-id="0b4ee-117">Above the grid, select either the **Consolidated members** or the **All consolidated members in hierarchy** option.</span></span>

6.  <span data-ttu-id="0b4ee-118">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="0b4ee-118">Click **Add**.</span></span>

7.  <span data-ttu-id="0b4ee-119">Заполните поля на панели справа.</span><span class="sxs-lookup"><span data-stu-id="0b4ee-119">In the pane on the right, complete the fields.</span></span>

8.  <span data-ttu-id="0b4ee-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="0b4ee-120">Optional.</span></span> <span data-ttu-id="0b4ee-121">В поле **Заметки** введите комментарий о том, для чего добавлен элемент.</span><span class="sxs-lookup"><span data-stu-id="0b4ee-121">In the **Annotations** box, type a comment about why the member was added.</span></span> <span data-ttu-id="0b4ee-122">Заметку могут просматривать все пользователи, которые имеют доступ к элементу.</span><span class="sxs-lookup"><span data-stu-id="0b4ee-122">All users who have access to the member can view the annotation.</span></span>

9. <span data-ttu-id="0b4ee-123">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0b4ee-123">Click **OK**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0b4ee-124">Next Steps</span><span class="sxs-lookup"><span data-stu-id="0b4ee-124">Next Steps</span></span>

-   [<span data-ttu-id="0b4ee-125">Перемещение элементов в иерархии &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0b4ee-125">Move Members within a Hierarchy &#40;Master Data Services&#41;</span></span>](move-members-within-a-hierarchy-master-data-services.md)

## <a name="see-also"></a><span data-ttu-id="0b4ee-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="0b4ee-126">See Also</span></span>
 <span data-ttu-id="0b4ee-127">[Создание явной иерархии &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md) [создания конечного элемента &#40;Master Data Services](../../2014/master-data-services/create-a-leaf-member-master-data-services.md)&#41;[загрузки или обновления элементов в Master Data Services с помощью элементов промежуточного процесса](add-update-and-delete-data-master-data-services.md) [&#40;Master Data Services](../../2014/master-data-services/members-master-data-services.md)&#41;[явных иерархий &#40;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0b4ee-127">[Create an Explicit Hierarchy &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md) [Create a Leaf Member &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-leaf-member-master-data-services.md) [Load or Update Members in Master Data Services by Using the Staging Process](add-update-and-delete-data-master-data-services.md) [Members &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) [Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)</span></span>


