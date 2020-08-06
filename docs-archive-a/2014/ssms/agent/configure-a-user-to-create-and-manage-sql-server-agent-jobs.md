---
title: Настройка пользователя для создания заданий агента SQL Server и управления ими | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, user configuration
- jobs [SQL Server Agent], user configuration
- SQLAgentUserRole database role
- proxy accounts [SQL Server Agent]
ms.assetid: 67897e3e-b7d0-43dd-a2e2-2840ec4dd1ef
author: stevestein
ms.author: sstein
ms.openlocfilehash: 83313389b3b872004fb23b0babdad19cfb5b8e7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668592"
---
# <a name="configure-a-user-to-create-and-manage-sql-server-agent-jobs"></a><span data-ttu-id="2f336-102">Configure a User to Create and Manage SQL Server Agent Jobs</span><span class="sxs-lookup"><span data-stu-id="2f336-102">Configure a User to Create and Manage SQL Server Agent Jobs</span></span>
  <span data-ttu-id="2f336-103">В этом разделе описывается настройка пользователя для создания или выполнения [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] заданий агента.</span><span class="sxs-lookup"><span data-stu-id="2f336-103">This topic describes how to configure a user to create or execute [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span>  
  
-   <span data-ttu-id="2f336-104">**Перед началом работы**  [Безопасность](#Security)</span><span class="sxs-lookup"><span data-stu-id="2f336-104">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="2f336-105">**Настройка пользователя для создания заданий агента SQL Server и управления ими с помощью следующих средств:**  [SQL Server Management Studio](#SSMS)</span><span class="sxs-lookup"><span data-stu-id="2f336-105">**To configure a user to create and manage SQL Server Agent jobs, using:**  [SQL Server Management Studio](#SSMS)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2f336-106">Перед началом</span><span class="sxs-lookup"><span data-stu-id="2f336-106">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2f336-107">безопасность</span><span class="sxs-lookup"><span data-stu-id="2f336-107">Security</span></span>  
 <span data-ttu-id="2f336-108">Чтобы настроить пользователя для создания или выполнения [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] заданий агента, необходимо сначала добавить существующее SQL Server имя входа или роль msdb в одну из следующих [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] предопределенных ролей базы данных агента в базе данных msdb: SQLAgentUserRole, SQLAgentReaderRole или SQLAgentOperatorRole.</span><span class="sxs-lookup"><span data-stu-id="2f336-108">To configure a user to create or execute [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs, you must first add an existing SQL Server login or msdb role to one of the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles in the msdb database: SQLAgentUserRole, SQLAgentReaderRole, or SQLAgentOperatorRole.</span></span>  
  
 <span data-ttu-id="2f336-109">По умолчанию члены этих ролей базы данных могут создавать свои собственные шаги заданий, которые запускаются сами по себе.</span><span class="sxs-lookup"><span data-stu-id="2f336-109">By default, members of these database roles can create their own job steps that run as themselves.</span></span> <span data-ttu-id="2f336-110">Если пользователи, не являющиеся администраторами, желают выполнить задания, которые выполняют другие типы шагов заданий, например пакеты [!INCLUDE[ssIS](../../includes/ssis-md.md)] , им необходимо будет получить доступ к учетной записи-посреднику.</span><span class="sxs-lookup"><span data-stu-id="2f336-110">If these non-administrative users want to run jobs that execute other job step types (for example, [!INCLUDE[ssIS](../../includes/ssis-md.md)] packages), they will need to have access to a proxy account.</span></span> <span data-ttu-id="2f336-111">Все члены предопределенной роли сервера sysadmin имеют разрешения на создание, изменение и удаление учетных записей-посредников.</span><span class="sxs-lookup"><span data-stu-id="2f336-111">All members of the sysadmin fixed server role have permission to create, modify, and delete proxy accounts.</span></span> <span data-ttu-id="2f336-112">Дополнительные сведения о разрешениях, связанных с этими предопределенными ролями баз данных агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , см. в разделе [Предопределенные роли базы данных агента SQL Server](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="2f336-112">For more information about the permissions that are associated with these [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2f336-113">Permissions</span><span class="sxs-lookup"><span data-stu-id="2f336-113">Permissions</span></span>  
 <span data-ttu-id="2f336-114">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="2f336-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="2f336-115">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2f336-115">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="2f336-116">**Добавление имени входа SQL или роли базы данных msdb к предопределенной роли базы данных агента SQL Server**</span><span class="sxs-lookup"><span data-stu-id="2f336-116">**To add a SQL login or msdb role to a SQL Server Agent fixed database role**</span></span>  
  
1.  <span data-ttu-id="2f336-117">В **Обозревателе объектов**разверните сервер.</span><span class="sxs-lookup"><span data-stu-id="2f336-117">In **Object Explorer**, expand a server.</span></span>  
  
2.  <span data-ttu-id="2f336-118">Разверните элемент **Безопасность**, а затем элемент **Имена входа**.</span><span class="sxs-lookup"><span data-stu-id="2f336-118">Expand **Security**, and then expand **Logins**.</span></span>  
  
3.  <span data-ttu-id="2f336-119">Щелкните правой кнопкой мыши имя входа, которое необходимо добавить к предопределенной роли базы данных агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="2f336-119">Right-click the login you wish to add to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database role, and select **Properties**.</span></span>  
  
4.  <span data-ttu-id="2f336-120">На странице **Сопоставление пользователей** диалогового окна **Свойства имени входа** выберите строку, содержащую `msdb` .</span><span class="sxs-lookup"><span data-stu-id="2f336-120">On the **User Mapping** page of the **Login Properties** dialog box, select the row containing `msdb`.</span></span>  
  
5.  <span data-ttu-id="2f336-121">На вкладке **Членство в роли базы данных для: msdb**выберите соответствующую предопределенную роль базы данных агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2f336-121">Under **Database role membership for: msdb**, check the appropriate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database role.</span></span>  
  
 <span data-ttu-id="2f336-122">**Настройка учетной записи-посредника для создания и управления шагами заданий агента SQL Server**</span><span class="sxs-lookup"><span data-stu-id="2f336-122">**To configure a proxy account to create and manage SQL Server Agent job steps**</span></span>  
  
1.  <span data-ttu-id="2f336-123">В **Обозревателе объектов**разверните сервер.</span><span class="sxs-lookup"><span data-stu-id="2f336-123">In **Object Explorer**, expand a server.</span></span>  
  
2.  <span data-ttu-id="2f336-124">Разверните узел **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="2f336-124">Expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="2f336-125">Щелкните правой кнопкой мыши элемент **Учетные записи-посредники** и выберите пункт **Создать учетную запись-посредник**.</span><span class="sxs-lookup"><span data-stu-id="2f336-125">Right-click **Proxies** and select **New Proxy**.</span></span>  
  
4.  <span data-ttu-id="2f336-126">На вкладке **Общие** диалогового окна **Создание учетной записи-посредника** укажите имя учетной записи-посредника, имя входа и описание.</span><span class="sxs-lookup"><span data-stu-id="2f336-126">On the **General** page of the **New Proxy Account** dialog, specify the proxy name, credential name, and description for the new proxy.</span></span> <span data-ttu-id="2f336-127">Обратите внимание, на то, что прежде чем создавать учетную запись-посредник агента SQL Server, необходимо создать учетные данные.</span><span class="sxs-lookup"><span data-stu-id="2f336-127">Note that you must create a credential first before creating a SQL Server Agent proxy.</span></span> <span data-ttu-id="2f336-128">Дополнительные сведения о создании учетных данных см. в статьях [Создание учетных данных](../../relational-databases/security/authentication-access/create-a-credential.md) и [Создание учетных данных &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2f336-128">For more information about creating a credential, see [Create a Credential](../../relational-databases/security/authentication-access/create-a-credential.md) and [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span></span>  
  
5.  <span data-ttu-id="2f336-129">Проверьте соответствующие подсистемы для этой учетной записи-посредника.</span><span class="sxs-lookup"><span data-stu-id="2f336-129">Check the appropriate subsystems for this proxy.</span></span>  
  
6.  <span data-ttu-id="2f336-130">На вкладке **Участники** добавьте или удалите имена входа или роли, чтобы предоставить или отменить доступ к учетной записи-посреднику.</span><span class="sxs-lookup"><span data-stu-id="2f336-130">On the **Principals** page, add or remove logins or roles to grant or remove access to the proxy account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f336-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="2f336-131">See Also</span></span>  
 [<span data-ttu-id="2f336-132">Обеспечение безопасности агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="2f336-132">Implement SQL Server Agent Security</span></span>](implement-sql-server-agent-security.md)  
  
  
