---
title: Назначение разрешений для элемента иерархии (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- permissions [Master Data Services], assigning member permissions
- members [Master Data Services], assigning permissions
ms.assetid: e1b8b46a-7cd1-4a7d-9345-dd7df081e145
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 4a1602f9fe351f826b63d4447f90dcf02a10f49e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664998"
---
# <a name="assign-hierarchy-member-permissions-master-data-services"></a><span data-ttu-id="be97d-102">Назначение разрешений для элемента иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="be97d-102">Assign Hierarchy Member Permissions (Master Data Services)</span></span>
  <span data-ttu-id="be97d-103">Разрешения для элементов иерархии назначаются, чтобы дать пользователям или группам возможность просматривать данные в функциональной области **Обозреватель**[!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="be97d-103">Assign permissions to hierarchy members to give users or groups access to view data in the **Explorer** functional area of [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
 <span data-ttu-id="be97d-104">Разрешения для элементов иерархии необязательны.</span><span class="sxs-lookup"><span data-stu-id="be97d-104">Hierarchy member permissions are optional.</span></span> <span data-ttu-id="be97d-105">Они позволяют детализировать разрешения для объектов модели в случаях, когда это необходимо.</span><span class="sxs-lookup"><span data-stu-id="be97d-105">They provide added granularity to model object permissions, which are required.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="be97d-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="be97d-106">Prerequisites</span></span>  
 <span data-ttu-id="be97d-107">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="be97d-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="be97d-108">необходимо иметь разрешение на доступ к функциональной области **Разрешения пользователей и групп** ;</span><span class="sxs-lookup"><span data-stu-id="be97d-108">You must have permission to access the **Users and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="be97d-109">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="be97d-109">You must be a model administrator.</span></span> <span data-ttu-id="be97d-110">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="be97d-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-assign-hierarchy-member-permissions"></a><span data-ttu-id="be97d-111">Назначение разрешений для элементов иерархии</span><span class="sxs-lookup"><span data-stu-id="be97d-111">To assign hierarchy member permissions</span></span>  
  
1.  <span data-ttu-id="be97d-112">В среде [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните **Разрешения пользователей и групп**.</span><span class="sxs-lookup"><span data-stu-id="be97d-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="be97d-113">На странице **Пользователи** или **Группы** выберите строку пользователя или группы, которые необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="be97d-113">On the **Users** or **Groups** page, select the row for the user or group that you want to edit.</span></span>  
  
3.  <span data-ttu-id="be97d-114">Нажмите **Изменить выделенного пользователя**.</span><span class="sxs-lookup"><span data-stu-id="be97d-114">Click **Edit selected user**.</span></span>  
  
4.  <span data-ttu-id="be97d-115">Перейдите на вкладку **Элементы иерархии** .</span><span class="sxs-lookup"><span data-stu-id="be97d-115">Click the **Hierarchy Members** tab.</span></span>  
  
5.  <span data-ttu-id="be97d-116">Выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="be97d-116">From the **Model** list, select a model.</span></span>  
  
6.  <span data-ttu-id="be97d-117">Выберите версию из списка **Версия** .</span><span class="sxs-lookup"><span data-stu-id="be97d-117">From the **Version** list, select a version.</span></span>  
  
7.  <span data-ttu-id="be97d-118">Выберите иерархию из списка **Иерархия** .</span><span class="sxs-lookup"><span data-stu-id="be97d-118">From the **Hierarchy** list, select a hierarchy.</span></span>  
  
8.  <span data-ttu-id="be97d-119">Нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="be97d-119">Click **Edit**.</span></span>  
  
9. <span data-ttu-id="be97d-120">Разверните дерево и щелкните узел иерархии, для которого нужно назначить разрешения.</span><span class="sxs-lookup"><span data-stu-id="be97d-120">Expand the tree, and click the hierarchy node you want to assign permissions to.</span></span>  
  
10. <span data-ttu-id="be97d-121">В меню выберите **только чтение**, **Обновить**или **запретить**.</span><span class="sxs-lookup"><span data-stu-id="be97d-121">From the menu, select **Read-only**, **Update**, or **Deny**.</span></span>  
  
11. <span data-ttu-id="be97d-122">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="be97d-122">Click **Save**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="be97d-123">Разрешения для элемента иерархии вступают в силу не сразу.</span><span class="sxs-lookup"><span data-stu-id="be97d-123">Hierarchy member permissions do not take effect immediately.</span></span> <span data-ttu-id="be97d-124">См. раздел [Срочное применение разрешения для элемента (службы Master Data Services)](../../2014/master-data-services/immediately-apply-member-permissions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="be97d-124">See [Immediately Apply Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/immediately-apply-member-permissions-master-data-services.md) for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be97d-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="be97d-125">See Also</span></span>  
 <span data-ttu-id="be97d-126">[Удаление разрешений элемента иерархии &#40;Master Data Services&#41;](../../2014/master-data-services/delete-hierarchy-member-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="be97d-126">[Delete Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/delete-hierarchy-member-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="be97d-127">[Назначение разрешений объекта модели &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="be97d-127">[Assign Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="be97d-128">Разрешения на элементы иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="be97d-128">Hierarchy Member Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md)  
  
  
