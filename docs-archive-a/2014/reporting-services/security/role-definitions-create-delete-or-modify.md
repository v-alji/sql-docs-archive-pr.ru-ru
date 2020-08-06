---
title: Создание, удаление и изменение ролей (среда Management Studio) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- roles [Reporting Services], creating
- deleting roles
- removing roles
- roles [Reporting Services], definitions
- modifying roles
- roles [Reporting Services], deleting
- roles [Reporting Services], modifying
ms.assetid: 3d1d56e6-a283-44a7-8417-36cb4d2c74d1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 543bddda88e41af39d3200df4728716d46b3ae8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736017"
---
# <a name="create-delete-or-modify-a-role-management-studio"></a><span data-ttu-id="040ba-102">Создание, удаление и изменение ролей (среда Management Studio)</span><span class="sxs-lookup"><span data-stu-id="040ba-102">Create, Delete, or Modify a Role (Management Studio)</span></span>
  <span data-ttu-id="040ba-103">Службы Reporting Services предоставляют стандартные роли, определяющие уровень доступа к серверу отчетов.</span><span class="sxs-lookup"><span data-stu-id="040ba-103">Reporting Services provides predefined roles that define a level of access to a report server.</span></span> <span data-ttu-id="040ba-104">Каждый пользователь или группа, которым требуется доступ к серверу отчетов, получают его с помощью роли, описывающей задачи, которые может выполнять пользователь или группа.</span><span class="sxs-lookup"><span data-stu-id="040ba-104">Each user or group who requires access to report server does so through a role that describes the tasks that can be performed.</span></span> <span data-ttu-id="040ba-105">Роли определяются для сервера отчетов в целом.</span><span class="sxs-lookup"><span data-stu-id="040ba-105">Roles are defined for the report server as a whole.</span></span> <span data-ttu-id="040ba-106">Нельзя изменить определение роли для конкретной части сервера отчетов или указать, что роль будет использоваться в зависимости от обстоятельств.</span><span class="sxs-lookup"><span data-stu-id="040ba-106">You cannot vary a role definition for specific parts of the report server, or specify that a role be used differently depending on the circumstances.</span></span>  
  
 <span data-ttu-id="040ba-107">Чтобы создать, изменить или удалить роль используется среда [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="040ba-107">To create, modify, or delete roles, use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="040ba-108">Можно удалять только те роли, которые не используются.</span><span class="sxs-lookup"><span data-stu-id="040ba-108">You can only delete roles that are not used.</span></span>  
  
 <span data-ttu-id="040ba-109">Присвоить пользователю или группе созданную роль можно с помощью диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="040ba-109">To assign users and groups to the roles that you create, use Report Manager.</span></span> <span data-ttu-id="040ba-110">Дополнительные сведения см. в разделе [предоставление пользователям доступа к серверу отчетов &#40;диспетчер отчетов&#41;](grant-user-access-to-a-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="040ba-110">For more information, see [Grant User Access to a Report Server &#40;Report Manager&#41;](grant-user-access-to-a-report-server.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="040ba-111">Если сервер отчетов настроен для работы в режиме интеграции с SharePoint и установлено соединение с веб-сайтом SharePoint, с которым интегрирован диспетчер отчетов, можно просматривать и изменять уровни разрешений, управляющие доступом к содержимому и операциям сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="040ba-111">If the report server is configured for SharePoint integrated mode, and you connected to the SharePoint site that the report server is integrated with, you can view and modify the permission levels that control access to report server content and operations.</span></span>  
  
### <a name="to-create-a-role-definition"></a><span data-ttu-id="040ba-112">Создание определения роли</span><span class="sxs-lookup"><span data-stu-id="040ba-112">To create a role definition</span></span>  
  
1.  <span data-ttu-id="040ba-113">В обозревателе объектов разверните узел сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="040ba-113">In Object Explorer, expand a report server node.</span></span>  
  
2.  <span data-ttu-id="040ba-114">Разверните папку «Безопасность».</span><span class="sxs-lookup"><span data-stu-id="040ba-114">Expand the Security folder.</span></span>  
  
3.  <span data-ttu-id="040ba-115">Если создается определение роли на уровне элемента, щелкните правой кнопкой мыши элемент **Роли**, а затем выберите пункт **Создать роль**.</span><span class="sxs-lookup"><span data-stu-id="040ba-115">If you are creating an item-level role definition, right-click **Roles**, and point to **New Role**.</span></span>  
  
     <span data-ttu-id="040ba-116">Чтобы создать определение роли на уровне системы, щелкните правой кнопкой мыши элемент **Системные роли**, затем выберите пункт **Создать системную роль**.</span><span class="sxs-lookup"><span data-stu-id="040ba-116">Or, if you are creating a system-level role definition, right-click **System Roles**, and point to **New System Role**.</span></span>  
  
4.  <span data-ttu-id="040ba-117">Введите уникальное имя для роли.</span><span class="sxs-lookup"><span data-stu-id="040ba-117">Type a unique name for the role.</span></span> <span data-ttu-id="040ba-118">Имя должно содержать по крайней мере один символ.</span><span class="sxs-lookup"><span data-stu-id="040ba-118">A name must contain at least one character.</span></span> <span data-ttu-id="040ba-119">Оно также может включать в себя пробелы и другие символы, за исключением символов ; ?</span><span class="sxs-lookup"><span data-stu-id="040ba-119">It can also include spaces and certain symbols, but not the characters ; ?</span></span> <span data-ttu-id="040ba-120">: \@ & = +, $/\* \< > | "или/.</span><span class="sxs-lookup"><span data-stu-id="040ba-120">: \@ & = + , $ / \* \< > | " or /.</span></span>  
  
5.  <span data-ttu-id="040ba-121">При необходимости введите также описание.</span><span class="sxs-lookup"><span data-stu-id="040ba-121">Optionally type a description.</span></span> <span data-ttu-id="040ba-122">В среде [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] это описание видно только на данной странице.</span><span class="sxs-lookup"><span data-stu-id="040ba-122">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] this description is visible only on this page.</span></span> <span data-ttu-id="040ba-123">Пользователи, просматривающие этот элемент с помощью диспетчера отчетов, смогут увидеть это описание в нем.</span><span class="sxs-lookup"><span data-stu-id="040ba-123">Users who view this item through Report Manager can see this description in that tool.</span></span>  
  
6.  <span data-ttu-id="040ba-124">Укажите задачи, которые могут выполнять члены этой роли.</span><span class="sxs-lookup"><span data-stu-id="040ba-124">Select the tasks that members of this role can perform.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-or-modify-a-role-definition"></a><span data-ttu-id="040ba-125">Удаление или изменение определения роли</span><span class="sxs-lookup"><span data-stu-id="040ba-125">To delete or modify a role definition</span></span>  
  
1.  <span data-ttu-id="040ba-126">В обозревателе объектов разверните узел сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="040ba-126">In Object Explorer, expand a report server node.</span></span>  
  
2.  <span data-ttu-id="040ba-127">Разверните папку «Безопасность».</span><span class="sxs-lookup"><span data-stu-id="040ba-127">Expand the Security folder.</span></span>  
  
3.  <span data-ttu-id="040ba-128">Для удаления или изменения определения роли на уровне элемента разверните папку «Роли».</span><span class="sxs-lookup"><span data-stu-id="040ba-128">To delete or modify an item-level role definition, expand the Roles folder.</span></span> <span data-ttu-id="040ba-129">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="040ba-129">Perform one of the following:</span></span>  
  
    1.  <span data-ttu-id="040ba-130">Для удаления определения роли щелкните правой кнопкой мыши этот элемент и выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="040ba-130">To delete a role definition, right-click the item and click **Delete**.</span></span> <span data-ttu-id="040ba-131">Отображается диалоговое окно **Удаление объекта** .</span><span class="sxs-lookup"><span data-stu-id="040ba-131">The **Delete Object** dialog box is displayed.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    2.  <span data-ttu-id="040ba-132">Для изменения определения роли щелкните правой кнопкой мыши этот элемент и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="040ba-132">To modify a role definition, right-click the item and click **Properties**.</span></span> <span data-ttu-id="040ba-133">Отобразится страница «Общие» диалогового окна **Свойства пользовательской роли** .</span><span class="sxs-lookup"><span data-stu-id="040ba-133">The General page of the **User Role Properties** dialog box is displayed.</span></span>  
  
         <span data-ttu-id="040ba-134">Укажите задачи, которые могут выполнять члены этой роли, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="040ba-134">Select the tasks that members of this role can perform, and click **OK**.</span></span>  
  
4.  <span data-ttu-id="040ba-135">Для удаления или изменения определения роли на уровне системы разверните папку **Системные роли** .</span><span class="sxs-lookup"><span data-stu-id="040ba-135">To delete or modify a system-level role definition, expand the **System Roles** folder.</span></span> <span data-ttu-id="040ba-136">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="040ba-136">Perform one of the following:</span></span>  
  
    1.  <span data-ttu-id="040ba-137">Чтобы удалить определение системной роли, щелкните элемент правой кнопкой мыши и выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="040ba-137">To delete a system role definition, right-click the item and click **Delete**.</span></span> <span data-ttu-id="040ba-138">Отображается диалоговое окно **Удаление объекта** .</span><span class="sxs-lookup"><span data-stu-id="040ba-138">The **Delete Object** dialog box is displayed.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    2.  <span data-ttu-id="040ba-139">Чтобы изменить определение системной роли, щелкните элемент правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="040ba-139">To modify a system role definition, right-click the item and click **Properties**.</span></span> <span data-ttu-id="040ba-140">Отображается страница «Общие» диалогового окна **Свойства системной роли** .</span><span class="sxs-lookup"><span data-stu-id="040ba-140">The General page of the **System Role Properties** dialog box is displayed.</span></span>  
  
         <span data-ttu-id="040ba-141">Укажите задачи, которые могут выполнять члены этой роли, а затем нажмите кнопку **ОК** , чтобы применить изменения.</span><span class="sxs-lookup"><span data-stu-id="040ba-141">Select the tasks that members of this role can perform, and click **OK** to apply the changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="040ba-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="040ba-142">See Also</span></span>  
 <span data-ttu-id="040ba-143">[Соединение с сервером отчетов в Management Studio](../tools/connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="040ba-143">[Connect to a Report Server in Management Studio](../tools/connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="040ba-144">(create-and-manage-role-assignments.md)</span><span class="sxs-lookup"><span data-stu-id="040ba-144">(create-and-manage-role-assignments.md)</span></span>   
 [<span data-ttu-id="040ba-145">Службы Reporting Services в среде SQL Server Management Studio (SSRS)</span><span class="sxs-lookup"><span data-stu-id="040ba-145">Reporting Services in SQL Server Management Studio &#40;SSRS&#41;</span></span>](../tools/reporting-services-in-sql-server-management-studio-ssrs.md)  
  
  
