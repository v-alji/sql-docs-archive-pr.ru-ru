---
title: Удаление разрешений для объекта модели (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting model object permissions [Master Data Services]
- permissions [Master Data Services], deleting model object permissions
- models [Master Data Services], deleting object permissions
ms.assetid: 859c5952-f600-4940-8064-1afd13f7f6dc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 98da869476e597d76a83b0b86cc9e6e4274a25e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731842"
---
# <a name="delete-model-object-permissions-master-data-services"></a><span data-ttu-id="bfca8-102">Удаление разрешений для объекта модели (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="bfca8-102">Delete Model Object Permissions (Master Data Services)</span></span>
  <span data-ttu-id="bfca8-103">В среде [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]удалите разрешения на объект модели для отмены любых существующих назначений.</span><span class="sxs-lookup"><span data-stu-id="bfca8-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete model object permissions to remove any assignments that have been made.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bfca8-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="bfca8-104">Prerequisites</span></span>  
 <span data-ttu-id="bfca8-105">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="bfca8-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="bfca8-106">необходимо иметь разрешение на доступ к функциональной области **Разрешения пользователей и групп** ;</span><span class="sxs-lookup"><span data-stu-id="bfca8-106">You must have permission to access the **Users and Group Permissions** functional area.</span></span>  
  
-   <span data-ttu-id="bfca8-107">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="bfca8-107">You must be a model administrator.</span></span> <span data-ttu-id="bfca8-108">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="bfca8-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-model-object-permissions"></a><span data-ttu-id="bfca8-109">Удаление разрешений объекта модели</span><span class="sxs-lookup"><span data-stu-id="bfca8-109">To delete model object permissions</span></span>  
  
1.  <span data-ttu-id="bfca8-110">В среде [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните **Разрешения пользователей и групп**.</span><span class="sxs-lookup"><span data-stu-id="bfca8-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="bfca8-111">На странице **Пользователи** или **Группы** выберите строку пользователя или группы, которые необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="bfca8-111">On the **Users** or **Groups** page, select the row for the user or group that you want to edit.</span></span>  
  
3.  <span data-ttu-id="bfca8-112">Нажмите **Изменить выделенного пользователя**.</span><span class="sxs-lookup"><span data-stu-id="bfca8-112">Click **Edit selected user**.</span></span>  
  
4.  <span data-ttu-id="bfca8-113">Перейдите на вкладку **Модели** .</span><span class="sxs-lookup"><span data-stu-id="bfca8-113">Click the **Models** tab.</span></span>  
  
5.  <span data-ttu-id="bfca8-114">По желанию выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="bfca8-114">Optionally, select a model from the **Model** list.</span></span>  
  
6.  <span data-ttu-id="bfca8-115">В области **Сводка разрешения модели** выберите строку для разрешения, которое требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="bfca8-115">In the **Model Permission Summary** pane, select the row for the permission that you want to delete.</span></span>  
  
7.  <span data-ttu-id="bfca8-116">Щелкните **Удалить выбранное разрешение**.</span><span class="sxs-lookup"><span data-stu-id="bfca8-116">Click **Delete selected permission**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bfca8-117">Нельзя удалить разрешение у пользователя, если разрешение унаследовано от группы.</span><span class="sxs-lookup"><span data-stu-id="bfca8-117">You cannot remove a permission from a user if the permission is inherited from a group.</span></span> <span data-ttu-id="bfca8-118">В этом случае нужно отозвать разрешение у группы.</span><span class="sxs-lookup"><span data-stu-id="bfca8-118">You must remove the permission from the group instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfca8-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="bfca8-119">See Also</span></span>  
 <span data-ttu-id="bfca8-120">[Разрешения объекта модели &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="bfca8-120">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="bfca8-121">Назначение разрешения для объекта модели (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="bfca8-121">Assign Model Object Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md)  
  
  
