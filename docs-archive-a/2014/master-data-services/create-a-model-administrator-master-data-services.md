---
title: Создание администратора модели (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- administrators [Master Data Services], creating
ms.assetid: dae17afc-3b39-490e-b51f-2d8da26d429e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 24efc3961e6ed5b9f41b2321dfcc4fbf16632270
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668973"
---
# <a name="create-a-model-administrator-master-data-services"></a><span data-ttu-id="9f265-102">Создание администратора модели (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="9f265-102">Create a Model Administrator (Master Data Services)</span></span>
  <span data-ttu-id="9f265-103">В [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] Создайте администратора модели, если требуется, чтобы группа или пользователь имели разрешение **Обновление** для всех объектов в одной или нескольких моделях.</span><span class="sxs-lookup"><span data-stu-id="9f265-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a model administrator when you want a group or user to have **Update** permission to all objects in one or more models.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="9f265-104">Чтобы упростить администрирование, создайте локальную группу Windows или локальной группы и настройте ее в качестве администратора модели.</span><span class="sxs-lookup"><span data-stu-id="9f265-104">To simplify administration, create a Windows or local group and configure it as a model administrator.</span></span> <span data-ttu-id="9f265-105">Впоследствии добавлять пользователей в группу и удалять их из нее можно без обращения к [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f265-105">You can then add and remove users from the group without accessing [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9f265-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="9f265-106">Prerequisites</span></span>  
 <span data-ttu-id="9f265-107">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="9f265-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="9f265-108">необходимо разрешение на доступ к функциональной области **Разрешения пользователей и групп** ;</span><span class="sxs-lookup"><span data-stu-id="9f265-108">You must have permission to access the **User and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="9f265-109">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="9f265-109">You must be a model administrator.</span></span> <span data-ttu-id="9f265-110">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9f265-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-a-model-administrator"></a><span data-ttu-id="9f265-111">Создание администратора модели</span><span class="sxs-lookup"><span data-stu-id="9f265-111">To create a model administrator</span></span>  
  
1.  <span data-ttu-id="9f265-112">В среде [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните **Разрешения пользователей и групп**.</span><span class="sxs-lookup"><span data-stu-id="9f265-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="9f265-113">На странице **Пользователи** или **Группы** выберите строку пользователя или группы, которые необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="9f265-113">On the **Users** or **Groups** page, select the row for the user or group that you want to edit.</span></span>  
  
3.  <span data-ttu-id="9f265-114">Нажмите **Изменить выделенного пользователя**.</span><span class="sxs-lookup"><span data-stu-id="9f265-114">Click **Edit selected user**.</span></span>  
  
4.  <span data-ttu-id="9f265-115">Перейдите на вкладку **Модели** .</span><span class="sxs-lookup"><span data-stu-id="9f265-115">Click the **Models** tab.</span></span>  
  
5.  <span data-ttu-id="9f265-116">По желанию выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="9f265-116">Optionally, select a model from the **Model** list.</span></span>  
  
6.  <span data-ttu-id="9f265-117">Нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="9f265-117">Click **Edit**.</span></span>  
  
7.  <span data-ttu-id="9f265-118">Щелкните модель, разрешение на которую необходимо предоставить.</span><span class="sxs-lookup"><span data-stu-id="9f265-118">Click the model you want to grant permission to.</span></span>  
  
8.  <span data-ttu-id="9f265-119">В меню выберите **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="9f265-119">From the menu, select **Update**.</span></span>  
  
9. <span data-ttu-id="9f265-120">Выполните шаги 7 и 8 для каждой модели, для которой необходимо назначить администратором пользователя или группу.</span><span class="sxs-lookup"><span data-stu-id="9f265-120">Complete steps 7 and 8 for each model you want the group or user to be an administrator for.</span></span>  
  
10. <span data-ttu-id="9f265-121">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9f265-121">Click **Save**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f265-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="9f265-122">Remarks</span></span>  
 <span data-ttu-id="9f265-123">Не назначайте какие-либо другие разрешения объектам модели или элементам иерархий.</span><span class="sxs-lookup"><span data-stu-id="9f265-123">Do not assign any other permissions to model objects or hierarchy members.</span></span> <span data-ttu-id="9f265-124">В этом случае пользователь больше не является администратором и не может просматривать модель в любой функциональной области, отличной от **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="9f265-124">If you do, the user is no longer an administrator and cannot view the model in any functional area other than **Explorer**.</span></span>  
  
 <span data-ttu-id="9f265-125">Существует одно исключение: Если пользователь имеет разрешение на **Обновление** , назначенное **корню** иерархии на вкладке **элементы иерархии** , пользователь по-прежнему считается администратором модели.</span><span class="sxs-lookup"><span data-stu-id="9f265-125">There is one exception: if the user has **Update** permission assigned to a hierarchy **Root** on the **Hierarchy Members** tab, the user is still considered a model administrator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f265-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="9f265-126">See Also</span></span>  
 <span data-ttu-id="9f265-127">[Администраторы &#40;Master Data Services&#41;](administrators-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9f265-127">[Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md) </span></span>  
 <span data-ttu-id="9f265-128">[Назначение разрешений объекта модели &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9f265-128">[Assign Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="9f265-129">[Назначение разрешений элемента иерархии &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9f265-129">[Assign Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="9f265-130">[Разрешения объекта модели &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9f265-130">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="9f265-131">Разрешения на элементы иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="9f265-131">Hierarchy Member Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md)  
  
  
