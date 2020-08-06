---
title: Защита папки "Мои отчеты" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- denying My Reports folder access
- private folders [Reporting Services]
- user workspace [Reporting Services]
- security [Reporting Services], My Reports folder
- My Reports folder [Reporting Services]
ms.assetid: 3b23a382-13b8-4196-9a93-7fe62d03a63c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b0a832133852e05c54a80b73fad8a91426840467
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730082"
---
# <a name="secure-my-reports"></a><span data-ttu-id="1f110-102">Обеспечение безопасности «Моих отчетов»</span><span class="sxs-lookup"><span data-stu-id="1f110-102">Secure My Reports</span></span>
  <span data-ttu-id="1f110-103">В компоненте «Мои отчеты» представлено управляемое пользователем рабочее пространство для работы с отчетами.</span><span class="sxs-lookup"><span data-stu-id="1f110-103">The My Reports feature provides a user-managed workspace for working with reports.</span></span> <span data-ttu-id="1f110-104">Чтобы обеспечить соответствие своему назначению, для папки «Мои отчеты» требуются более широкие права доступа, чем для других папок, доступных для общего пользования.</span><span class="sxs-lookup"><span data-stu-id="1f110-104">In order to serve its intended purpose, the My Reports folder requires less restrictive permissions than other folders that are available for general use.</span></span> <span data-ttu-id="1f110-105">Пользователям, имеющим разрешения в других папках только на просмотр и запуск отчетов, могут потребоваться дополнительные разрешения для управления их папками My Reports и содержимым, которое им принадлежит.</span><span class="sxs-lookup"><span data-stu-id="1f110-105">Users who have permissions to only view and run reports in other folders might require an expanded set of permissions to manage their My Reports folders and content that they own.</span></span> [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="1f110-106">предоставляет для этого специальный механизм назначения и определения ролей.</span><span class="sxs-lookup"><span data-stu-id="1f110-106">provides a specialized role assignment and role definition for this purpose.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1f110-107">Доступ к папке «Мои отчеты» возможен только в диспетчере отчетов.</span><span class="sxs-lookup"><span data-stu-id="1f110-107">My Reports is available only in Report Manager.</span></span> <span data-ttu-id="1f110-108">Она недоступна в среде [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f110-108">It is not available in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
## <a name="role-assignment-for-my-reports"></a><span data-ttu-id="1f110-109">Назначение роли для папки «Мои отчеты»</span><span class="sxs-lookup"><span data-stu-id="1f110-109">Role Assignment for My Reports</span></span>  
 <span data-ttu-id="1f110-110">Назначение роли для папки «Мои отчеты» имеет стандартные элементы и создается автоматически для каждого пользователя, активирующего папку «Мои отчеты».</span><span class="sxs-lookup"><span data-stu-id="1f110-110">The role assignment for My Reports has preset elements and is automatically created for each user who activates a My Reports folder.</span></span> <span data-ttu-id="1f110-111">Для организаций, широко использующих папку «Мои отчеты», особенно удобно иметь автоматически назначаемую защиту сервера отчетов, так как администраторы не обязаны разрешать доступ каждому пользователю папкой «Мои отчеты».</span><span class="sxs-lookup"><span data-stu-id="1f110-111">Having the report server automatically assign security is especially useful for organizations that use My Reports widely because administrators do not have to enable access for each My Reports user.</span></span>  
  
 <span data-ttu-id="1f110-112">Назначение роли папки **Мои отчеты** включает следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="1f110-112">A **My Reports** role assignment consists of the following elements:</span></span>  
  
-   <span data-ttu-id="1f110-113">Папка Мои отчеты пользователя, расположенная в папке "папки пользователей \ \\ *\<username>* Мои отчеты".</span><span class="sxs-lookup"><span data-stu-id="1f110-113">The user's My Reports folder, which is located in Users Folders\\*\<username>* \My Reports folder.</span></span>  
  
-   <span data-ttu-id="1f110-114">учетная запись пользователя, определяемая при активации папки «Мои отчеты».</span><span class="sxs-lookup"><span data-stu-id="1f110-114">The user account, which is determined when the My Reports folder is activated.</span></span> <span data-ttu-id="1f110-115">Папка активируется при щелчке пользователем папки «Мои отчеты» в диспетчере отчетов или при публикации отчета в папке «Мои отчеты» из конструктора отчетов.</span><span class="sxs-lookup"><span data-stu-id="1f110-115">A folder is activated when a user clicks a My Reports folder in Report Manager or when publishing a report to a My Reports folder from Report Designer.</span></span> <span data-ttu-id="1f110-116">Эта папка также активируется при запросе пользователем свойств по ссылке «Мои отчеты»;</span><span class="sxs-lookup"><span data-stu-id="1f110-116">This folder is also activated when a user requests properties on the My Reports link.</span></span>  
  
-   <span data-ttu-id="1f110-117">заранее заданное определение роли для папки «Мои отчеты».</span><span class="sxs-lookup"><span data-stu-id="1f110-117">The predefined role definition for My Reports.</span></span>  
  
## <a name="role-definition-for-my-reports"></a><span data-ttu-id="1f110-118">Определение роли для папки «Мои отчеты»</span><span class="sxs-lookup"><span data-stu-id="1f110-118">Role Definition for My Reports</span></span>  
 <span data-ttu-id="1f110-119">Определение роли папки **Мои отчеты** включает задачи, обеспечивающие управление содержимым папки «Мои отчеты».</span><span class="sxs-lookup"><span data-stu-id="1f110-119">The **My Reports** role definition includes tasks that support content management of a My Reports folder.</span></span> <span data-ttu-id="1f110-120">Роль папки **Мои отчеты** является узкоспециализированной ролью.</span><span class="sxs-lookup"><span data-stu-id="1f110-120">The **My Reports** role is intended to be a single-purpose role.</span></span> <span data-ttu-id="1f110-121">Несмотря на то, что эту роль можно выбрать для политики безопасности на уровне любого элемента, следует этого избегать, чтобы свести к минимуму возможность ее изменения в целях соответствия требованиям других папок.</span><span class="sxs-lookup"><span data-stu-id="1f110-121">Although you can choose it for any item-level security policy, you should avoid doing so to minimize the chance that you will modify it to accommodate other folder requirements.</span></span> <span data-ttu-id="1f110-122">Резервирование роли папки **Мои отчеты** для компонента позволяет пользователям получить необходимый опыт.</span><span class="sxs-lookup"><span data-stu-id="1f110-122">Reserving the **My Reports** role for the My Reports feature can help you maintain a consistent experience for users.</span></span>  
  
 <span data-ttu-id="1f110-123">По умолчанию роль папки **Мои отчеты** изменяют только администраторы сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="1f110-123">By default, only report server administrators modify the **My Reports** role.</span></span> <span data-ttu-id="1f110-124">Настроить роль папки **Мои отчеты** можно путем изменения содержащихся в ней задач.</span><span class="sxs-lookup"><span data-stu-id="1f110-124">You can customize the **My Reports** role by changing the tasks it contains.</span></span> <span data-ttu-id="1f110-125">Также можно назначить другую роль.</span><span class="sxs-lookup"><span data-stu-id="1f110-125">You can also substitute a different role.</span></span>  
  
## <a name="denying-access-to-my-reports"></a><span data-ttu-id="1f110-126">Запрет на доступ к папке «Мои отчеты»</span><span class="sxs-lookup"><span data-stu-id="1f110-126">Denying Access to My Reports</span></span>  
 <span data-ttu-id="1f110-127">Препятствовать доступу пользователей к папке «Мои отчеты» можно при помощи:</span><span class="sxs-lookup"><span data-stu-id="1f110-127">You can prevent users from accessing My Reports by:</span></span>  
  
-   <span data-ttu-id="1f110-128">отключения папки «Мои отчеты» на странице «Параметры сайта».</span><span class="sxs-lookup"><span data-stu-id="1f110-128">Disabling My Reports on the Site Settings page.</span></span> <span data-ttu-id="1f110-129">Дополнительные сведения см. в статье [Включение и отключение папки "Мои отчеты"](../report-server/enable-and-disable-my-reports.md).</span><span class="sxs-lookup"><span data-stu-id="1f110-129">For more information, see [Enable and Disable My Reports](../report-server/enable-and-disable-my-reports.md).</span></span>  
  
-   <span data-ttu-id="1f110-130">удаления всех задач из роли папки **Мои отчеты** .</span><span class="sxs-lookup"><span data-stu-id="1f110-130">Removing all tasks from the **My Reports** role.</span></span>  
  
 <span data-ttu-id="1f110-131">При отключении папки «Мои отчеты» ссылка на папку «Мои отчеты» удаляется из диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="1f110-131">When you disable My Reports, the link to a My Reports folder is removed from Report Manager.</span></span> <span data-ttu-id="1f110-132">Доступ к соответствующей структуре папки, поддерживающей папку «Мои отчеты» (т.е. папка «Users Folders» и ее вложенные папки), все еще возможен и может быть осуществлен, если пользователь знает путь к папке.</span><span class="sxs-lookup"><span data-stu-id="1f110-132">The underlying folder structure that supports My Reports (that is, the Users Folders folder and subfolders) is still available and can be accessed if a user knows the folder path.</span></span> <span data-ttu-id="1f110-133">Удаление задач из роли папки **Мои отчеты** предотвращает доступ к ней.</span><span class="sxs-lookup"><span data-stu-id="1f110-133">Removing tasks from **My Reports** role ensures that access is prevented.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f110-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="1f110-134">See Also</span></span>  
 <span data-ttu-id="1f110-135">[Защищенные отчеты и ресурсы](secure-reports-and-resources.md) </span><span class="sxs-lookup"><span data-stu-id="1f110-135">[Secure Reports and Resources](secure-reports-and-resources.md) </span></span>  
 <span data-ttu-id="1f110-136">[Защита папок](secure-folders.md) </span><span class="sxs-lookup"><span data-stu-id="1f110-136">[Secure Folders](secure-folders.md) </span></span>  
 [<span data-ttu-id="1f110-137">Предоставление разрешений на сервер отчетов в собственном режиме</span><span class="sxs-lookup"><span data-stu-id="1f110-137">Granting Permissions on a Native Mode Report Server</span></span>](granting-permissions-on-a-native-mode-report-server.md)  
  
  
