---
title: Предоставление разрешения для субъекта | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Grant permission to a principal
ms.assetid: 4107389d-05b6-4aa3-9fa8-95b40cdf05dc
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 4256d62bdeac2d79c51e5f3792c991e0e3b15096
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750632"
---
# <a name="grant-a-permission-to-a-principal"></a><span data-ttu-id="5d66a-102">Предоставление разрешения для участника</span><span class="sxs-lookup"><span data-stu-id="5d66a-102">Grant a Permission to a Principal</span></span>
  <span data-ttu-id="5d66a-103">В данном разделе содержатся инструкции по предоставлению разрешения участнику [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] при помощи среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d66a-103">This topic describes how to grant permission to a principal in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="5d66a-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="5d66a-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5d66a-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="5d66a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5d66a-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="5d66a-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="5d66a-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="5d66a-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5d66a-108">**Предоставление разрешения участнику с помощью:**</span><span class="sxs-lookup"><span data-stu-id="5d66a-108">**To grant permission to a principal, using:**</span></span>  
  
     [<span data-ttu-id="5d66a-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5d66a-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5d66a-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5d66a-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5d66a-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="5d66a-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5d66a-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="5d66a-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="5d66a-113">Рассмотрим следующие рекомендации, которые упростят управление разрешениями.</span><span class="sxs-lookup"><span data-stu-id="5d66a-113">Consider the following best practices that can make managing permissions easier.</span></span>  
  
-   <span data-ttu-id="5d66a-114">Предоставляйте разрешения ролям, а не отдельным именам входа или пользователям.</span><span class="sxs-lookup"><span data-stu-id="5d66a-114">Grant permission to roles, instead of individual logins or users.</span></span> <span data-ttu-id="5d66a-115">Когда один пользователь заменяет другого, удалите уходящего пользователя из роли и добавьте в нее нового.</span><span class="sxs-lookup"><span data-stu-id="5d66a-115">When one individual is replaced by another, remove the departing individual from the role and add the new individual to the role.</span></span> <span data-ttu-id="5d66a-116">Все разрешения, связанные с ролью, автоматически становятся доступными для нового пользователя.</span><span class="sxs-lookup"><span data-stu-id="5d66a-116">The many permissions that might be associated with the role will automatically be available to the new individual.</span></span> <span data-ttu-id="5d66a-117">Если нескольким лицам в организации нужны одинаковые разрешения, то добавление их в одну роль предоставит им одинаковые разрешения.</span><span class="sxs-lookup"><span data-stu-id="5d66a-117">If several people in an organization require the same permissions, adding each of them to the role will grant them the same permissions.</span></span>  
  
-   <span data-ttu-id="5d66a-118">Поместите сходные защищаемые объекты (таблицы, представления и процедуры) в одну схему, а затем предоставьте этой схеме разрешения.</span><span class="sxs-lookup"><span data-stu-id="5d66a-118">Configure similar securables (tables, views, and procedures) to be owned by a schema, then grant permissions to the schema.</span></span> <span data-ttu-id="5d66a-119">Например, схема платежной ведомости может содержать несколько таблиц, представлений и хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="5d66a-119">For example, the payroll schema might own several tables, views, and stored procedures.</span></span> <span data-ttu-id="5d66a-120">Предоставляя доступ к схеме, можно сразу предоставить все разрешения, необходимые для осуществления расчетов.</span><span class="sxs-lookup"><span data-stu-id="5d66a-120">By granting access to the schema, all the necessary permissions to perform the payroll function can be granted at the same time.</span></span> <span data-ttu-id="5d66a-121">Дополнительные сведения о защищаемых объектах, которым можно предоставлять разрешения, см. в разделе [Securables](../securables.md).</span><span class="sxs-lookup"><span data-stu-id="5d66a-121">For more information about what securables can be granted permissions, see [Securables](../securables.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5d66a-122">безопасность</span><span class="sxs-lookup"><span data-stu-id="5d66a-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5d66a-123">Permissions</span><span class="sxs-lookup"><span data-stu-id="5d66a-123">Permissions</span></span>  
 <span data-ttu-id="5d66a-124">Лицо, предоставляющее разрешение (или участник, указанный с аргументом AS), должны иметь либо само разрешение с аргументом GRANT OPTION, либо разрешение более высокого уровня, которое включает в себя предоставленное разрешение.</span><span class="sxs-lookup"><span data-stu-id="5d66a-124">The grantor (or the principal specified with the AS option) must have either the permission itself with GRANT OPTION or a higher permission that implies the permission being granted.</span></span> <span data-ttu-id="5d66a-125">Члены предопределенной роли сервера **sysadmin** могут предоставлять любые разрешения.</span><span class="sxs-lookup"><span data-stu-id="5d66a-125">Members of the **sysadmin** fixed server role can grant any permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5d66a-126">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5d66a-126">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-grant-permission-to-a-principal"></a><span data-ttu-id="5d66a-127">Предоставление разрешения участнику</span><span class="sxs-lookup"><span data-stu-id="5d66a-127">To grant permission to a principal</span></span>  
  
1.  <span data-ttu-id="5d66a-128">В обозревателе объектов разверните базу данных, содержащую объект, которому необходимо предоставить разрешение.</span><span class="sxs-lookup"><span data-stu-id="5d66a-128">In Object Explorer, expand the database that contains the object to which you want to grant permissions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5d66a-129">Как правило, эти действия используются для предоставления разрешений хранимым процедурам, но их можно использовать и для добавления разрешений таблицам, представлениям, функциям, сборкам и другим защищаемым объектам.</span><span class="sxs-lookup"><span data-stu-id="5d66a-129">These steps deal specifically with granting permissions to a stored procedure, but you can use similar steps to add permissions to tables, views, functions, and assemblies, as well as other securables.</span></span> <span data-ttu-id="5d66a-130">Дополнительные сведения см. в разделе [GRANT (Transact-SQL)](/sql/t-sql/statements/grant-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5d66a-130">For more information, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql)</span></span>  
  
2.  <span data-ttu-id="5d66a-131">Разверните папку **Программирование** .</span><span class="sxs-lookup"><span data-stu-id="5d66a-131">Expand the **Programmability** folder.</span></span>  
  
3.  <span data-ttu-id="5d66a-132">Разверните папку **Хранимые процедуры** .</span><span class="sxs-lookup"><span data-stu-id="5d66a-132">Expand the **Stored Procedures** folder.</span></span>  
  
4.  <span data-ttu-id="5d66a-133">Щелкните правой кнопкой мыши хранимую процедуру и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="5d66a-133">Right-click a stored procedure and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="5d66a-134">В диалоговом окне **Свойства хранимой процедуры —**_stored_procedure_name_ в разделе Выбор страницы выберите **разрешения**.</span><span class="sxs-lookup"><span data-stu-id="5d66a-134">In the **Stored Procedure Properties -**_stored_procedure_name_ dialog box, under select a page, select **Permissions**.</span></span> <span data-ttu-id="5d66a-135">Данная страница используется для добавления пользователей или ролей к хранимым процедурам и для назначения разрешений этим пользователям и ролям.</span><span class="sxs-lookup"><span data-stu-id="5d66a-135">Use this page to add users or roles to the stored procedure and specify the permissions those users or roles have.</span></span>  
  
6.  <span data-ttu-id="5d66a-136">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5d66a-136">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5d66a-137">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5d66a-137">Using Transact-SQL</span></span>  
  
#### <a name="to-grant-permission-to-a-principal"></a><span data-ttu-id="5d66a-138">Предоставление разрешения участнику</span><span class="sxs-lookup"><span data-stu-id="5d66a-138">To grant permission to a principal</span></span>  
  
1.  <span data-ttu-id="5d66a-139">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d66a-139">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5d66a-140">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="5d66a-140">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5d66a-141">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="5d66a-141">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Grants EXECUTE permission on stored procedure HumanResources.uspUpdateEmployeeHireInfo to an application role called Recruiting11.   
    USE AdventureWorks2012;  
    GO  
    GRANT EXECUTE ON OBJECT::HumanResources.uspUpdateEmployeeHireInfo  
        TO Recruiting11;  
    GO  
    ```  
  
 <span data-ttu-id="5d66a-142">Дополнительные сведения см. в статьях [GRANT (Transact-SQL)](/sql/t-sql/statements/grant-transact-sql) и [Разрешения объекта GRANT (Transact-SQL)](/sql/t-sql/statements/grant-object-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5d66a-142">For more information, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) and [GRANT Object Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d66a-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="5d66a-143">See Also</span></span>  
 [<span data-ttu-id="5d66a-144">Участники (компонент Database Engine)</span><span class="sxs-lookup"><span data-stu-id="5d66a-144">Principals &#40;Database Engine&#41;</span></span>](principals-database-engine.md)  
  
  
