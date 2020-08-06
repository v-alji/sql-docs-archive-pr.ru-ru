---
title: Добавление группы (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- groups [Master Data Services], adding
- adding groups [Master Data Services]
ms.assetid: c7a88381-3b2c-4af7-9cf7-3a930c1abdee
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8f9da1d558ccb648af8fbc0dd3b802751bd5ae44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736485"
---
# <a name="add-a-group-master-data-services"></a><span data-ttu-id="2ae5c-102">Добавление группы (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="2ae5c-102">Add a Group (Master Data Services)</span></span>
  <span data-ttu-id="2ae5c-103">Чтобы начать процесс назначения разрешений для веб-приложения, нужно добавить группу в список **Группы** служб [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2ae5c-103">Add a group to the **Groups** list in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] to begin the process of assigning permission to the Web application.</span></span> <span data-ttu-id="2ae5c-104">Прежде чем пользователь группы сможет получить доступ к [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], группе необходимо предоставить разрешения для одной или нескольких функциональных областей и объектов модели.</span><span class="sxs-lookup"><span data-stu-id="2ae5c-104">Before a user in the group can access [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], you must give the group permission to one or more functional areas and model objects.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2ae5c-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="2ae5c-105">Prerequisites</span></span>  
 <span data-ttu-id="2ae5c-106">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="2ae5c-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="2ae5c-107">необходимо иметь разрешение на доступ к функциональной области **Разрешения пользователей и групп** ;</span><span class="sxs-lookup"><span data-stu-id="2ae5c-107">You must have permission to access the **Users and Group Permissions** functional area.</span></span>  
  
### <a name="to-add-a-group"></a><span data-ttu-id="2ae5c-108">Добавление группы</span><span class="sxs-lookup"><span data-stu-id="2ae5c-108">To add a group</span></span>  
  
1.  <span data-ttu-id="2ae5c-109">В среде [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните **Разрешения пользователей и групп**.</span><span class="sxs-lookup"><span data-stu-id="2ae5c-109">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **User and Group Permissions**.</span></span>  
  
2.  <span data-ttu-id="2ae5c-110">На панели меню страницы **Пользователи** нажмите кнопку **Управление группами**.</span><span class="sxs-lookup"><span data-stu-id="2ae5c-110">On the **Users** page, from the menu bar, click **Manage Groups**.</span></span>  
  
3.  <span data-ttu-id="2ae5c-111">Нажмите кнопку **Добавить группы**.</span><span class="sxs-lookup"><span data-stu-id="2ae5c-111">Click **Add groups**.</span></span>  
  
4.  <span data-ttu-id="2ae5c-112">Введите имя группы, предваряемое именем домена Active Directory либо именем сервера в виде *домен\имя_группы* или *компьютер\имя_группы*.</span><span class="sxs-lookup"><span data-stu-id="2ae5c-112">Type the group's name preceded by the Active Directory domain name or by the server computer's name, as in *domain\group_name* or *computer\group_name*.</span></span>  
  
5.  <span data-ttu-id="2ae5c-113">По желанию нажмите кнопку **Проверить имена**.</span><span class="sxs-lookup"><span data-stu-id="2ae5c-113">Optionally, click **Check names**.</span></span>  
  
6.  <span data-ttu-id="2ae5c-114">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2ae5c-114">Click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2ae5c-115">После первого обращения пользователя к [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]имя пользователя добавляется в список пользователей [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2ae5c-115">When the user first accesses [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], the user's name is added to the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] list of users.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="2ae5c-116">Next Steps</span><span class="sxs-lookup"><span data-stu-id="2ae5c-116">Next Steps</span></span>  
  
-   [<span data-ttu-id="2ae5c-117">Назначение разрешений для функциональной области (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="2ae5c-117">Assign Functional Area Permissions &#40;Master Data Services&#41;</span></span>](assign-functional-area-permissions-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="2ae5c-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="2ae5c-118">See Also</span></span>  
 [<span data-ttu-id="2ae5c-119">Безопасность (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="2ae5c-119">Security &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/security-master-data-services.md)  
  
  
