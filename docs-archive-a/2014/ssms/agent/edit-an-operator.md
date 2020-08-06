---
title: Изменение оператора | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- modifying operators
- jobs [SQL Server Agent], operators
- operators (users) [Database Engine], modifying with Management Studio
ms.assetid: b2ba2168-ca0b-4b59-9007-4e1e4c30679e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 45ffb520e240dfd97002060370ff6dcf7c60d083
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654733"
---
# <a name="edit-an-operator"></a><span data-ttu-id="0fab9-102">Изменение оператора</span><span class="sxs-lookup"><span data-stu-id="0fab9-102">Edit an Operator</span></span>
  <span data-ttu-id="0fab9-103">В этом разделе описано, как изменить доступность операторов к получению уведомлений, а также для них адрес электронной почты, номер пейджера и адрес net send в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0fab9-103">This topic describes how to edit an operators' availability for receiving notifications and their e-mail, pager, and net send addresses in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="0fab9-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="0fab9-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0fab9-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="0fab9-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0fab9-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="0fab9-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="0fab9-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="0fab9-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0fab9-108">**Изменение данных оператора с помощью:**</span><span class="sxs-lookup"><span data-stu-id="0fab9-108">**To edit an operator, using:**</span></span>  
  
     [<span data-ttu-id="0fab9-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0fab9-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="0fab9-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0fab9-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0fab9-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="0fab9-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="0fab9-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="0fab9-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="0fab9-113">Режимы отправки уведомлений с помощью пейджера и команды **net send** будут удалены из агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в следующей версии [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0fab9-113">The Pager and **net send** options will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0fab9-114">Старайтесь не использовать эти функции в новых разработках и предусмотрите соответствующие изменения в приложениях, которые используют их в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="0fab9-114">Avoid using these features in new development work, and plan to modify applications that currently use these features.</span></span>  
  
-   <span data-ttu-id="0fab9-115">Обратите внимание, что для использования компонента Database Mail для отправки операторам уведомлений по электронной почте и на пейджер агент SQL Server необходимо настроить для использования компонента Database Mail.</span><span class="sxs-lookup"><span data-stu-id="0fab9-115">Note that SQL Server Agent must be configured to use Database Mail to send e-mail and pager notifications to operators.</span></span> <span data-ttu-id="0fab9-116">Дополнительные сведения см. в разделе [Назначить предупреждения для оператора](assign-alerts-to-an-operator.md).</span><span class="sxs-lookup"><span data-stu-id="0fab9-116">For more information, see [Assign Alerts to an Operator](assign-alerts-to-an-operator.md).</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="0fab9-117">обеспечивает доступный графический способ управления заданиями и рекомендуется для создания и управления инфраструктурой заданий.</span><span class="sxs-lookup"><span data-stu-id="0fab9-117">provides an easy, graphical way to manage jobs, and is the recommended way to create and manage the job infrastructure.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0fab9-118">безопасность</span><span class="sxs-lookup"><span data-stu-id="0fab9-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0fab9-119">Permissions</span><span class="sxs-lookup"><span data-stu-id="0fab9-119">Permissions</span></span>  
 <span data-ttu-id="0fab9-120">Изменять данные операторов могут указывать только члены предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="0fab9-120">Only members of the **sysadmin** fixed server role can edit operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0fab9-121">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0fab9-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-edit-an-operator"></a><span data-ttu-id="0fab9-122">Редактирование данных оператора</span><span class="sxs-lookup"><span data-stu-id="0fab9-122">To edit an operator</span></span>  
  
1.  <span data-ttu-id="0fab9-123">В **обозревателе объектов**щелкните значок «плюс», чтобы развернуть сервер, содержащий оператора, данные которого нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="0fab9-123">In **Object Explorer**, click the plus sign to expand the server that contains the operator you want to edit.</span></span>  
  
2.  <span data-ttu-id="0fab9-124">Щелкните знак "плюс", чтобы развернуть **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="0fab9-124">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="0fab9-125">Щелкните значок «плюс», чтобы развернуть папку **Операторы** .</span><span class="sxs-lookup"><span data-stu-id="0fab9-125">Click the plus sign to expand the **Operators** folder.</span></span>  
  
4.  <span data-ttu-id="0fab9-126">Щелкните правой кнопкой оператора, данные которого нужно изменить, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="0fab9-126">Right-click the operator that you want to edit and select **Properties**.</span></span>  
  
     <span data-ttu-id="0fab9-127">Дополнительные сведения о доступных параметрах, содержащихся в диалоговом окне _Свойства_**имя_оператора** , см. в разделе:</span><span class="sxs-lookup"><span data-stu-id="0fab9-127">For more information on the available options contained in the _operator_name_**Properties** dialog box, see:</span></span>  
  
    -   [<span data-ttu-id="0fab9-128">Свойства оператора и новый оператор &#40;общие&#41;страницы</span><span class="sxs-lookup"><span data-stu-id="0fab9-128">Operator Properties and New Operator &#40;General Page&#41;</span></span>](../../integration-services/general-page-of-integration-services-designers-options.md)  
  
    -   [<span data-ttu-id="0fab9-129">Свойства оператора: Новая страница &#40;уведомлений оператора&#41;</span><span class="sxs-lookup"><span data-stu-id="0fab9-129">Operator Properties: New Operator &#40;Notifications Page&#41;</span></span>](operator-properties-new-operator-notifications-page.md)  
  
    -   [<span data-ttu-id="0fab9-130">Свойства оператора (страница "Журнал")</span><span class="sxs-lookup"><span data-stu-id="0fab9-130">Operator Properties &#40;History Page&#41;</span></span>](operator-properties-history-page.md)  
  
5.  <span data-ttu-id="0fab9-131">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0fab9-131">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0fab9-132">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0fab9-132">Using Transact-SQL</span></span>  
  
#### <a name="to-edit-an-operator"></a><span data-ttu-id="0fab9-133">Редактирование данных оператора</span><span class="sxs-lookup"><span data-stu-id="0fab9-133">To edit an operator</span></span>  
  
1.  <span data-ttu-id="0fab9-134">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0fab9-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0fab9-135">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="0fab9-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0fab9-136">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="0fab9-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- updates the operator status to enabled, and sets the days   
    -- (from Monday through Friday, from 8 A.M. through 5 P.M.) when the operator can be paged.   
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_operator   
        @name = N'Fran??ois Ajenstat',  
        @enabled = 1,  
        @email_address = N'fran??oisa',  
        @pager_address = N'5551290AW@pager.Adventure-Works.com',  
        @weekday_pager_start_time = 080000,  
        @weekday_pager_end_time = 170000,  
        @pager_days = 64 ;  
    GO  
    ```  
  
 <span data-ttu-id="0fab9-137">Дополнительные сведения см. в разделе [sp_update_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-operator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0fab9-137">For more information, see [sp_update_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-operator-transact-sql).</span></span>  
  
  
