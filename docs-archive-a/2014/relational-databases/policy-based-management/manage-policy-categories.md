---
title: Управление категориями политик | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.policycategories.f1
ms.assetid: d188a819-731f-4029-98aa-780d3299a0ce
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 168d05dd88286263da1dca5456a2c6072e946786
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657717"
---
# <a name="manage-policy-categories"></a><span data-ttu-id="f3225-102">Управление категориями политики</span><span class="sxs-lookup"><span data-stu-id="f3225-102">Manage Policy Categories</span></span>
  <span data-ttu-id="f3225-103">В этом разделе описывается применение любой политики или всех доступных политик в категории ко всему экземпляру [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3225-103">This topic describes how to apply any or all available policies in a category to the whole instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="f3225-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="f3225-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f3225-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="f3225-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f3225-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="f3225-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f3225-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="f3225-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f3225-108">**Для применения политик категории к экземпляру SQL Server используется:**</span><span class="sxs-lookup"><span data-stu-id="f3225-108">**To apply category policies to a SQL Server instance, using:**</span></span>  
  
     [<span data-ttu-id="f3225-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f3225-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f3225-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f3225-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f3225-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="f3225-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f3225-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="f3225-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="f3225-113">Если при использовании [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]флажок **Обязательные подписки базы данных** не установлен, каждую категорию политики будет необходимо индивидуально применить к каждому участку сервера, например базам данных или таблицам.</span><span class="sxs-lookup"><span data-stu-id="f3225-113">When using [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], if the **Mandate Database Subscriptions** check box is not selected, the policy category must be individually applied to each relevant portion of the server, such as one or more databases or tables.</span></span>  
  
-   <span data-ttu-id="f3225-114">Если указать несуществующую категорию политики, то во время выполнения хранимой процедуры будет создана новая категория политики и подписка будет обязательной для всех баз данных.</span><span class="sxs-lookup"><span data-stu-id="f3225-114">If you specify a policy category that does not exist, a new policy category is created and the subscription is mandated for all databases when you execute the stored procedure.</span></span> <span data-ttu-id="f3225-115">Если затем очистить обязательную подписку для новой категории, то подписка будет применяться только к базе данных, указанной в аргументе *target_object*.</span><span class="sxs-lookup"><span data-stu-id="f3225-115">If you then clear the mandated subscription for the new category, the subscription will only apply for the database that you specified as the *target_object*.</span></span> <span data-ttu-id="f3225-116">Дополнительные сведения об изменении параметра обязательной подписки см. в разделе [sp_syspolicy_update_policy_category (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-syspolicy-update-policy-category-subscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f3225-116">For more information about how to change a mandated subscription setting, see [sp_syspolicy_update_policy_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-update-policy-category-subscription-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f3225-117">безопасность</span><span class="sxs-lookup"><span data-stu-id="f3225-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f3225-118">Permissions</span><span class="sxs-lookup"><span data-stu-id="f3225-118">Permissions</span></span>  
 <span data-ttu-id="f3225-119">Эта хранимая процедура выполняется в контексте текущего владельца хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="f3225-119">This stored procedure runs in the context of the current owner of the stored procedure.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f3225-120">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f3225-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-apply-category-policies-to-a-sql-server-instance"></a><span data-ttu-id="f3225-121">Применение политик категории к экземпляру SQL Server</span><span class="sxs-lookup"><span data-stu-id="f3225-121">To apply category policies to a SQL Server instance</span></span>  
  
1.  <span data-ttu-id="f3225-122">В **обозревателе объектов**щелкните знак «плюс», чтобы развернуть сервер, к которому нужно применить политики категории.</span><span class="sxs-lookup"><span data-stu-id="f3225-122">In **Object Explorer**, click the plus sign to expand the server where you will apply category policies.</span></span>  
  
2.  <span data-ttu-id="f3225-123">Щелкните знак «плюс», чтобы развернуть папку **Управление** .</span><span class="sxs-lookup"><span data-stu-id="f3225-123">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="f3225-124">Щелкните правой кнопкой мыши элемент **Управление политиками** и выберите пункт **Управление категориями**.</span><span class="sxs-lookup"><span data-stu-id="f3225-124">Right-click **Policy Management** and select **Manage Categories**.</span></span>  
  
     <span data-ttu-id="f3225-125">В диалоговом окне **Управление категориями политики** доступны следующие данные.</span><span class="sxs-lookup"><span data-stu-id="f3225-125">The following information is available in the **Manage Policy Categories** dialog box:</span></span>  
  
     <span data-ttu-id="f3225-126">**Название**</span><span class="sxs-lookup"><span data-stu-id="f3225-126">**Name**</span></span>  
     <span data-ttu-id="f3225-127">Имя категории политики.</span><span class="sxs-lookup"><span data-stu-id="f3225-127">The name of the policy category.</span></span>  
  
     <span data-ttu-id="f3225-128">**Обязательные подписки базы данных**</span><span class="sxs-lookup"><span data-stu-id="f3225-128">**Mandate Database Subscriptions**</span></span>  
     <span data-ttu-id="f3225-129">Заставляет все базы данных в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] применять политики из категории политики.</span><span class="sxs-lookup"><span data-stu-id="f3225-129">Forces all databases on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to enforce policies in the policy category.</span></span>  
  
4.  <span data-ttu-id="f3225-130">Установите или снимите флажки в разделе **Обязательные подписки базы данных** , чтобы применить ту или иную категорию политики к экземпляру SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f3225-130">Select or clear any or all check boxes under **Mandate Database Subscriptions** to apply that policy category to the SQL Server instance.</span></span>  
  
5.  <span data-ttu-id="f3225-131">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f3225-131">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f3225-132">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f3225-132">Using Transact-SQL</span></span>  
  
#### <a name="to-apply-category-policies-to-a-sql-server-instance"></a><span data-ttu-id="f3225-133">Применение политик категории к экземпляру SQL Server</span><span class="sxs-lookup"><span data-stu-id="f3225-133">To apply category policies to a SQL Server instance</span></span>  
  
1.  <span data-ttu-id="f3225-134">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3225-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f3225-135">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="f3225-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f3225-136">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="f3225-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb;  
    GO  
    -- configures the specified database to subscribe to a policy category that is named 'Table Naming Policies'.  
    EXEC dbo.sp_syspolicy_add_policy_category_subscription @target_type = N'DATABASE'  
    , @target_object = N'AdventureWorks2012'  
    , @policy_category = N'Table Naming Policies';  
    GO  
    ```  
  
 <span data-ttu-id="f3225-137">Дополнительные сведения см. в разделе [sp_syspolicy_add_policy_category_subscription (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-syspolicy-add-policy-category-subscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f3225-137">For more information, see [sp_syspolicy_add_policy_category_subscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-add-policy-category-subscription-transact-sql).</span></span>  
  
  
