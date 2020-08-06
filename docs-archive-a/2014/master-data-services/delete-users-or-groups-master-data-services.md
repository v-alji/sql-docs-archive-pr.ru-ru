---
title: Удаление пользователей или групп (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting groups [Master Data Services]
- groups [Master Data Services], deleting
- users [Master Data Services], deleting
- deleting users [Master Data Services]
ms.assetid: 0bbf9d2c-b826-48bb-8aa9-9905db6e717f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: be302bc974994d0f4f17a8e61244065c76fa93ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667764"
---
# <a name="delete-users-or-groups-master-data-services"></a><span data-ttu-id="ae870-102">Удаление пользователей или группы (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="ae870-102">Delete Users or Groups (Master Data Services)</span></span>
  <span data-ttu-id="ae870-103">Удалите пользователей и группы, если больше не нужно, чтобы они имели доступ к среде [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae870-103">Delete users or groups when you no longer want them to access [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
 <span data-ttu-id="ae870-104">Помните о следующих правилах при удалении пользователей и групп.</span><span class="sxs-lookup"><span data-stu-id="ae870-104">Note the following behavior when deleting users and groups:</span></span>  
  
-   <span data-ttu-id="ae870-105">При удалении пользователя, который является членом группы с доступом к [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], у него останется доступ к [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , пока его не удалить из группы Active Directory или локальной группы.</span><span class="sxs-lookup"><span data-stu-id="ae870-105">If you delete a user who is a member of a group that has access to [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], then the user can still access [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] until you remove the user from the Active Directory or local group.</span></span>  
  
-   <span data-ttu-id="ae870-106">При удалении группы все пользователи из этой группы, которые ранее обращались к [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , будут отображаться в списке **Пользователи** , пока они не будут удалены.</span><span class="sxs-lookup"><span data-stu-id="ae870-106">If you delete a group, all users from the group who have accessed [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] are displayed in the **Users** list until you delete them.</span></span>  
  
-   <span data-ttu-id="ae870-107">Изменения безопасности распространяются на MDS [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] спустя 20 минут.</span><span class="sxs-lookup"><span data-stu-id="ae870-107">Changes to security are not propagated to the MDS [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] for 20 minutes.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ae870-108">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="ae870-108">Prerequisites</span></span>  
 <span data-ttu-id="ae870-109">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="ae870-109">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="ae870-110">необходимо иметь разрешение на доступ к функциональной области **Разрешения пользователей и групп** ;</span><span class="sxs-lookup"><span data-stu-id="ae870-110">You must have permission to access the **Users and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="ae870-111">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="ae870-111">You must be a model administrator.</span></span> <span data-ttu-id="ae870-112">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ae870-112">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-users-or-groups"></a><span data-ttu-id="ae870-113">Удаление пользователей или групп</span><span class="sxs-lookup"><span data-stu-id="ae870-113">To delete users or groups</span></span>  
  
1.  <span data-ttu-id="ae870-114">В среде [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните **Разрешения пользователей и групп**.</span><span class="sxs-lookup"><span data-stu-id="ae870-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="ae870-115">Чтобы удалить пользователя, оставайтесь на странице **Пользователи** .</span><span class="sxs-lookup"><span data-stu-id="ae870-115">To delete a user, remain on the **Users** page.</span></span> <span data-ttu-id="ae870-116">Чтобы удалить группу, в строке меню щелкните **Управление группами**.</span><span class="sxs-lookup"><span data-stu-id="ae870-116">To delete a group, from the menu bar, click **ManageGroups.**</span></span>  
  
3.  <span data-ttu-id="ae870-117">Выберите в сетке строку для пользователя или группы, которых необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="ae870-117">In the grid,select the row for the user or group that you want to delete.</span></span>  
  
4.  <span data-ttu-id="ae870-118">Нажмите **Удалить выбранного пользователя** или **Удалить выбранную группу**.</span><span class="sxs-lookup"><span data-stu-id="ae870-118">Click **Delete selected user** or **Delete selected group**.</span></span>  
  
5.  <span data-ttu-id="ae870-119">В диалоговом окне подтверждения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ae870-119">On the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae870-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="ae870-120">See Also</span></span>  
 [<span data-ttu-id="ae870-121">Безопасность (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="ae870-121">Security &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/security-master-data-services.md)  
  
  
