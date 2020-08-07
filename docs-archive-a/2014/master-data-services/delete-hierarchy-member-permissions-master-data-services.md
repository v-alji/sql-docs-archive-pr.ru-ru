---
title: Удаление разрешений для элемента иерархии (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting member permissions [Master Data Services]
- members [Master Data Services], deleting permissions
- permissions [Master Data Services], deleting member permissions
ms.assetid: 7f22d5e2-70c1-422c-99c2-e995a47d812a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8b6e7fbfc4379733d5cb809ce4d46d2c12d05a48
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731845"
---
# <a name="delete-hierarchy-member-permissions-master-data-services"></a><span data-ttu-id="5b099-102">Удаление разрешений элемента иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="5b099-102">Delete Hierarchy Member Permissions (Master Data Services)</span></span>
  <span data-ttu-id="5b099-103">В среде [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]удалите разрешения на объект модели для отмены любых существующих назначений.</span><span class="sxs-lookup"><span data-stu-id="5b099-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete model object permissions to remove any assignments that have been made.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5b099-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="5b099-104">Prerequisites</span></span>  
 <span data-ttu-id="5b099-105">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="5b099-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="5b099-106">необходимо иметь разрешение на доступ к функциональной области **Разрешения пользователей и групп** ;</span><span class="sxs-lookup"><span data-stu-id="5b099-106">You must have permission to access the **Users and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="5b099-107">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="5b099-107">You must be a model administrator.</span></span> <span data-ttu-id="5b099-108">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5b099-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-hierarchy-member-permissions"></a><span data-ttu-id="5b099-109">Удаление разрешения элемента иерархии</span><span class="sxs-lookup"><span data-stu-id="5b099-109">To delete hierarchy member permissions</span></span>  
  
1.  <span data-ttu-id="5b099-110">В среде [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните **Разрешения пользователей и групп**.</span><span class="sxs-lookup"><span data-stu-id="5b099-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="5b099-111">На странице **Пользователи** или **Группы** выберите строку пользователя или группы, которые необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="5b099-111">On the **Users** or **Groups** page, select the row for the user or group that you want to edit.</span></span>  
  
3.  <span data-ttu-id="5b099-112">Нажмите **Изменить выделенного пользователя**.</span><span class="sxs-lookup"><span data-stu-id="5b099-112">Click **Edit selected user**.</span></span>  
  
4.  <span data-ttu-id="5b099-113">Перейдите на вкладку **Элементы иерархии** .</span><span class="sxs-lookup"><span data-stu-id="5b099-113">Click the **Hierarchy Members** tab.</span></span>  
  
5.  <span data-ttu-id="5b099-114">Выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="5b099-114">From the **Model** list, select a model.</span></span>  
  
6.  <span data-ttu-id="5b099-115">Выберите версию из списка **Версия** .</span><span class="sxs-lookup"><span data-stu-id="5b099-115">From the **Version** list, select a version.</span></span>  
  
7.  <span data-ttu-id="5b099-116">В области **Сводка разрешений элемента иерархии** выберите строку для разрешения, которое требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="5b099-116">In the **Hierarchy Member Permission Summary** pane, select the row for the permission that you want to delete.</span></span>  
  
8.  <span data-ttu-id="5b099-117">Щелкните **Удалить выбранное разрешение**.</span><span class="sxs-lookup"><span data-stu-id="5b099-117">Click **Delete selected permission**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5b099-118">Нельзя удалить разрешение у пользователя, если разрешение унаследовано от группы.</span><span class="sxs-lookup"><span data-stu-id="5b099-118">You cannot remove a permission from a user if the permission is inherited from a group.</span></span> <span data-ttu-id="5b099-119">В этом случае нужно отозвать разрешение у группы.</span><span class="sxs-lookup"><span data-stu-id="5b099-119">You must remove the permission from the group instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b099-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="5b099-120">See Also</span></span>  
 <span data-ttu-id="5b099-121">[Разрешения элемента иерархии &#40;Master Data Services&#41;](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5b099-121">[Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="5b099-122">Назначение разрешений для элемента иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="5b099-122">Assign Hierarchy Member Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md)  
  
  
