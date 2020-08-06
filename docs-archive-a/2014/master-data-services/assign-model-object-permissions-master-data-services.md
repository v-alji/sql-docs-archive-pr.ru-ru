---
title: Назначение разрешения для объекта модели (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- models [Master Data Services], assigning object permissions
- permissions [Master Data Services], assigning model object permissions
ms.assetid: 4b80148d-2318-415c-9479-28c240e48bcd
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 92ac8ef3ac63b7128c4cbb7e9305ee6bd56ca010
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664982"
---
# <a name="assign-model-object-permissions-master-data-services"></a><span data-ttu-id="31e3b-102">Назначение разрешения для объекта модели (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="31e3b-102">Assign Model Object Permissions (Master Data Services)</span></span>
  <span data-ttu-id="31e3b-103">В [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]назначьте разрешения для объектов модели при необходимости разрешить пользователю или группе доступ к данным в функциональной области **Обозреватель** в [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]или при необходимости сделать пользователя или группу администратором.</span><span class="sxs-lookup"><span data-stu-id="31e3b-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], assign permissions to model objects when you need to give a user or group access to data in the **Explorer** functional area of [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], or when you need to make a user or group an administrator.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="31e3b-104">При назначении разрешения на модель доступ ко всем другим моделям неявно запрещается.</span><span class="sxs-lookup"><span data-stu-id="31e3b-104">When you assign permission to a model, permission to all other models is implicitly denied.</span></span> <span data-ttu-id="31e3b-105">Если не будут назначены никакие разрешения, то пользователи и группы не смогут обращаться к данным в **Обозревателе**.</span><span class="sxs-lookup"><span data-stu-id="31e3b-105">If you do not assign model object permissions, the user or group cannot access any data in **Explorer**.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="31e3b-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="31e3b-106">Prerequisites</span></span>  
 <span data-ttu-id="31e3b-107">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="31e3b-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="31e3b-108">необходимо иметь разрешение на доступ к функциональной области **Разрешения пользователей и групп** ;</span><span class="sxs-lookup"><span data-stu-id="31e3b-108">You must have permission to access the **Users and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="31e3b-109">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="31e3b-109">You must be a model administrator.</span></span> <span data-ttu-id="31e3b-110">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="31e3b-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-assign-model-object-permissions"></a><span data-ttu-id="31e3b-111">Назначения разрешений объекта модели</span><span class="sxs-lookup"><span data-stu-id="31e3b-111">To assign model object permissions</span></span>  
  
1.  <span data-ttu-id="31e3b-112">В среде [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните **Разрешения пользователей и групп**.</span><span class="sxs-lookup"><span data-stu-id="31e3b-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="31e3b-113">На странице **Пользователи** или **Группы** выберите строку пользователя или группы, которые необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="31e3b-113">On the **Users** or **Groups** page, select the row for the user or group that you want to edit.</span></span>  
  
3.  <span data-ttu-id="31e3b-114">Нажмите **Изменить выделенного пользователя**.</span><span class="sxs-lookup"><span data-stu-id="31e3b-114">Click **Edit selected user**.</span></span>  
  
4.  <span data-ttu-id="31e3b-115">Перейдите на вкладку **Модели** .</span><span class="sxs-lookup"><span data-stu-id="31e3b-115">Click the **Models** tab.</span></span>  
  
5.  <span data-ttu-id="31e3b-116">По желанию выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="31e3b-116">Optionally, select a model from the **Model** list.</span></span>  
  
6.  <span data-ttu-id="31e3b-117">Нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="31e3b-117">Click **Edit**.</span></span>  
  
7.  <span data-ttu-id="31e3b-118">Разверните дерево и щелкните объект модели, для которого нужно назначить разрешения.</span><span class="sxs-lookup"><span data-stu-id="31e3b-118">Expand the tree, and click the model object you want to assign permissions to.</span></span>  
  
8.  <span data-ttu-id="31e3b-119">В меню выберите **только чтение**, **Обновить**или **запретить**.</span><span class="sxs-lookup"><span data-stu-id="31e3b-119">From the menu, select **Read-only**, **Update**, or **Deny**.</span></span>  
  
9. <span data-ttu-id="31e3b-120">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="31e3b-120">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="31e3b-121">Next Steps</span><span class="sxs-lookup"><span data-stu-id="31e3b-121">Next Steps</span></span>  
  
-   <span data-ttu-id="31e3b-122">[Назначение разрешений для элемента иерархии (службы Master Data Services)](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md) (необязательно)</span><span class="sxs-lookup"><span data-stu-id="31e3b-122">(Optional) [Assign Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31e3b-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="31e3b-123">See Also</span></span>  
 <span data-ttu-id="31e3b-124">[Удаление разрешений объекта модели &#40;Master Data Services&#41;](../../2014/master-data-services/delete-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="31e3b-124">[Delete Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/delete-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="31e3b-125">[Разрешения объекта модели &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="31e3b-125">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="31e3b-126">Создание администратора модели (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="31e3b-126">Create a Model Administrator &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-model-administrator-master-data-services.md)  
  
  
