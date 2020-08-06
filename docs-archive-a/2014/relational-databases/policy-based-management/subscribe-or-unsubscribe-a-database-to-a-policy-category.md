---
title: Подписка базы данных на категорию политики или отмена подписки | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.groupsubscription.f1
ms.assetid: d2c31769-7098-428e-ad9c-ef56541b7c52
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2b4ca6f804352b57b30b42012da93e0d031be8d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731510"
---
# <a name="subscribe-or-unsubscribe-a-database--to-a-policy-category"></a><span data-ttu-id="3cb5e-102">Подписка базы данных на категорию политики или отмена подписки</span><span class="sxs-lookup"><span data-stu-id="3cb5e-102">Subscribe or Unsubscribe a Database  to a Policy Category</span></span>
  <span data-ttu-id="3cb5e-103">В этом разделе описывается подписка и отмена подписки базы данных на категорию политики в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cb5e-103">This topic describes how to subscribe or unsubscribe a database to a policy category.in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="3cb5e-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="3cb5e-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3cb5e-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="3cb5e-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3cb5e-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="3cb5e-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3cb5e-107">**Для подписки базы данных на категорию политики или отмены подписки используется:**</span><span class="sxs-lookup"><span data-stu-id="3cb5e-107">**To subscribe or unsubscribe a database to a policy category., using:**</span></span>  
  
     [<span data-ttu-id="3cb5e-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3cb5e-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="3cb5e-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3cb5e-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3cb5e-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="3cb5e-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3cb5e-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="3cb5e-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3cb5e-112">Permissions</span><span class="sxs-lookup"><span data-stu-id="3cb5e-112">Permissions</span></span>  
 <span data-ttu-id="3cb5e-113">Необходимо членство в предопределенной роли базы данных db_owner.</span><span class="sxs-lookup"><span data-stu-id="3cb5e-113">Requires membership in the db_owner fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3cb5e-114">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3cb5e-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-subscribe-or-unsubscribe-a-database-to-a-policy-category"></a><span data-ttu-id="3cb5e-115">Подписка базы данных на категорию политики или отмена подписки</span><span class="sxs-lookup"><span data-stu-id="3cb5e-115">To subscribe or unsubscribe a database to a policy category</span></span>  
  
1.  <span data-ttu-id="3cb5e-116">В **обозревателе объектов**щелкните знак «плюс», чтобы развернуть базу данных, в которой нужно изменить подписки на категории.</span><span class="sxs-lookup"><span data-stu-id="3cb5e-116">In **Object Explorer**, click the plus sign to expand the server that contains the database wherein you want to manage category subscriptions.</span></span>  
  
2.  <span data-ttu-id="3cb5e-117">Щелкните знак «плюс», чтобы развернуть папку **Базы данных** .</span><span class="sxs-lookup"><span data-stu-id="3cb5e-117">Click the plus sign to expand the **Databases** folder.</span></span>  
  
3.  <span data-ttu-id="3cb5e-118">Щелкните правой кнопкой мыши базу данных, в которой нужно изменить подписки на категории, укажите пункт **Политики**и выберите пункт **Категории**.</span><span class="sxs-lookup"><span data-stu-id="3cb5e-118">Right-click the database wherein you want to manage category subscriptions, point to **Policies**, and select **Categories**</span></span>  
  
     <span data-ttu-id="3cb5e-119">В диалоговом окне **Категории** доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="3cb5e-119">The following options are available in the **Categories** dialog box:</span></span>  
  
     <span data-ttu-id="3cb5e-120">Развернуть столбец</span><span class="sxs-lookup"><span data-stu-id="3cb5e-120">Expand column</span></span>  
     <span data-ttu-id="3cb5e-121">Щелкните, чтобы развернуть категорию политики.</span><span class="sxs-lookup"><span data-stu-id="3cb5e-121">Click to expand a policy category.</span></span> <span data-ttu-id="3cb5e-122">Перечисляет все политики, включенные в категорию.</span><span class="sxs-lookup"><span data-stu-id="3cb5e-122">This lists all the policies that are included in the category.</span></span>  
  
     <span data-ttu-id="3cb5e-123">**имя**;</span><span class="sxs-lookup"><span data-stu-id="3cb5e-123">**Name**</span></span>  
     <span data-ttu-id="3cb5e-124">Имя категории политики.</span><span class="sxs-lookup"><span data-stu-id="3cb5e-124">The name of the policy category.</span></span>  
  
     <span data-ttu-id="3cb5e-125">**Подписаны**</span><span class="sxs-lookup"><span data-stu-id="3cb5e-125">**Subscribed**</span></span>  
     <span data-ttu-id="3cb5e-126">Указывает, имеет ли цель подписку на категорию политики.</span><span class="sxs-lookup"><span data-stu-id="3cb5e-126">Indicates whether the target has subscribed to the policy category.</span></span> <span data-ttu-id="3cb5e-127">Если этот флажок не установлен, то категория политики задается для варианта **Обязательные подписки базы данных**.</span><span class="sxs-lookup"><span data-stu-id="3cb5e-127">If this check box is disabled, the policy category is set for **Mandate Database Subscriptions**.</span></span> <span data-ttu-id="3cb5e-128">Это означает, что категория политики может применяться ко всем базам данных на сервере.</span><span class="sxs-lookup"><span data-stu-id="3cb5e-128">This means that the policy category applies to all databases on the server.</span></span>  
  
     <span data-ttu-id="3cb5e-129">**Политика**</span><span class="sxs-lookup"><span data-stu-id="3cb5e-129">**Policy**</span></span>  
     <span data-ttu-id="3cb5e-130">Если группы политик развернуты, отображаются политики в категории политики.</span><span class="sxs-lookup"><span data-stu-id="3cb5e-130">When policy groups are expanded, displays the policies in the policy category.</span></span>  
  
     <span data-ttu-id="3cb5e-131">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="3cb5e-131">**Enabled**</span></span>  
     <span data-ttu-id="3cb5e-132">Указывает, включены или выключены политики.</span><span class="sxs-lookup"><span data-stu-id="3cb5e-132">Indicates whether the policies are enabled or disabled.</span></span>  
  
     <span data-ttu-id="3cb5e-133">**Режим выполнения**</span><span class="sxs-lookup"><span data-stu-id="3cb5e-133">**Execution Mode**</span></span>  
     <span data-ttu-id="3cb5e-134">Отображает режим выполнения политики.</span><span class="sxs-lookup"><span data-stu-id="3cb5e-134">Displays the execution mode of the policy.</span></span>  
  
     <span data-ttu-id="3cb5e-135">**Журнал**</span><span class="sxs-lookup"><span data-stu-id="3cb5e-135">**History**</span></span>  
     <span data-ttu-id="3cb5e-136">Перейдите по гиперссылке «Просмотр журнала», чтобы открыть средство просмотра файлов журнала и просмотреть журнал политики.</span><span class="sxs-lookup"><span data-stu-id="3cb5e-136">Click the View History hyperlink to open the Log File Viewer to see the policy history.</span></span>  
  
4.  <span data-ttu-id="3cb5e-137">Чтобы подписаться на категорию управления на основе политик, установите флажок категории в столбце **Подписка** .</span><span class="sxs-lookup"><span data-stu-id="3cb5e-137">To subscribe to a Policy-Based Management category, select the category's check box under the **Subscribed** column.</span></span> <span data-ttu-id="3cb5e-138">Чтобы отменить подписку на категорию, снимите флажок.</span><span class="sxs-lookup"><span data-stu-id="3cb5e-138">To unsubscribe from a category, clear the check box.</span></span>  
  
5.  <span data-ttu-id="3cb5e-139">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3cb5e-139">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3cb5e-140">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3cb5e-140">Using Transact-SQL</span></span>  
  
#### <a name="to-subscribe-a-database-to-a-policy-category"></a><span data-ttu-id="3cb5e-141">Подписка базы данных на категорию политики</span><span class="sxs-lookup"><span data-stu-id="3cb5e-141">To subscribe a database to a policy category</span></span>  
  
1.  <span data-ttu-id="3cb5e-142">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cb5e-142">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3cb5e-143">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="3cb5e-143">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3cb5e-144">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="3cb5e-144">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    -- Adds a subscription to the 'Finance' policy category for the AdventureWorks2012 database.  
    EXEC sys.sp_syspolicy_subscribe_to_policy_category @policy_category = N'Finance';  
    GO  
    ```  
  
 <span data-ttu-id="3cb5e-145">Дополнительные сведения см. в статье [sp_syspolicy_subscribe_to_policy_category (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-syspolicy-subscribe-to-policy-category-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3cb5e-145">For more information, see [sp_syspolicy_subscribe_to_policy_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-subscribe-to-policy-category-transact-sql).</span></span>  
  
#### <a name="to-unsubscribe-a-database-to-a-policy-category"></a><span data-ttu-id="3cb5e-146">Отмена подписки базы данных на категорию политики</span><span class="sxs-lookup"><span data-stu-id="3cb5e-146">To unsubscribe a database to a policy category</span></span>  
  
1.  <span data-ttu-id="3cb5e-147">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cb5e-147">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3cb5e-148">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="3cb5e-148">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3cb5e-149">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="3cb5e-149">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    -- Deletes a subscription to the 'Finance' policy category for the AdventureWorks2012 database.  
    EXEC sys.sp_syspolicy_unsubscribe_from_policy_category @policy_category = N'Finance';  
    GO  
    ```  
  
 <span data-ttu-id="3cb5e-150">Дополнительные сведения см. в статье [sp_syspolicy_unsubscribe_from_policy_category (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-syspolicy-unsubscribe-from-policy-category-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3cb5e-150">For more information, see [sp_syspolicy_unsubscribe_from_policy_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-unsubscribe-from-policy-category-transact-sql).</span></span>  
  
  
