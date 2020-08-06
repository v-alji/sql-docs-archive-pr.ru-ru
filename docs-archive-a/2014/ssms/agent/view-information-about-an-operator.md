---
title: Просмотр сведений об операторе | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- viewing operators
- operators (users) [Database Engine], viewing with Management Studio
- jobs [SQL Server Agent], operators
- notifications [SQL Server], job status
- displaying operators
ms.assetid: 92c82cdf-f704-444e-9539-82aea7fe6fb7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 680b90401f800a9c435bdae33b8e55385541cc4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658031"
---
# <a name="view-information-about-an-operator"></a><span data-ttu-id="becbb-102">Просмотр сведений об операторе</span><span class="sxs-lookup"><span data-stu-id="becbb-102">View Information About an Operator</span></span>
  <span data-ttu-id="becbb-103">В этом разделе описывается Просмотр сведений об [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] операторе агента в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="becbb-103">This topic describes how to view information about a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent operator in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="becbb-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="becbb-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="becbb-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="becbb-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="becbb-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="becbb-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="becbb-107">**Для просмотра сведений об операторе используется:**</span><span class="sxs-lookup"><span data-stu-id="becbb-107">**To view information about an operator, using:**</span></span>  
  
     [<span data-ttu-id="becbb-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="becbb-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="becbb-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="becbb-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="becbb-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="becbb-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="becbb-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="becbb-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="becbb-112">Permissions</span><span class="sxs-lookup"><span data-stu-id="becbb-112">Permissions</span></span>  
 <span data-ttu-id="becbb-113">По умолчанию эту хранимую процедуру могут выполнять только члены предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="becbb-113">By default, members of the **sysadmin** fixed server role can execute this stored procedure.</span></span> <span data-ttu-id="becbb-114">Другим пользователям должна быть предоставлена одна из следующих предопределенных ролей базы данных агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в базе данных **msdb** :</span><span class="sxs-lookup"><span data-stu-id="becbb-114">Other users must be granted one of the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles in the **msdb** database:</span></span>  
  
-   <span data-ttu-id="becbb-115">**SQLAgentUserRole**</span><span class="sxs-lookup"><span data-stu-id="becbb-115">**SQLAgentUserRole**</span></span>  
  
-   <span data-ttu-id="becbb-116">**SQLAgentReaderRole**</span><span class="sxs-lookup"><span data-stu-id="becbb-116">**SQLAgentReaderRole**</span></span>  
  
-   <span data-ttu-id="becbb-117">**SQLAgentOperatorRole**</span><span class="sxs-lookup"><span data-stu-id="becbb-117">**SQLAgentOperatorRole**</span></span>  
  
 <span data-ttu-id="becbb-118">Дополнительные сведения о разрешениях этих ролей см. в разделе [Предопределенные роли базы данных агента SQL Server](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="becbb-118">For details about the permissions of these roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="becbb-119">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="becbb-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-information-about-an-operator"></a><span data-ttu-id="becbb-120">Просмотр сведений об операторе</span><span class="sxs-lookup"><span data-stu-id="becbb-120">To view information about an operator</span></span>  
  
1.  <span data-ttu-id="becbb-121">В **обозревателе объектов**щелкните знак «плюс», чтобы развернуть сервер, содержащий оператора, которого нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="becbb-121">In **Object Explorer**, click the plus sign to expand the server that contains the operator you want to view.</span></span>  
  
2.  <span data-ttu-id="becbb-122">Щелкните знак "плюс", чтобы развернуть **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="becbb-122">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="becbb-123">Щелкните значок «плюс», чтобы развернуть папку **Операторы** .</span><span class="sxs-lookup"><span data-stu-id="becbb-123">Click the plus sign to expand the **Operators** folder.</span></span>  
  
4.  <span data-ttu-id="becbb-124">Щелкните правой кнопкой оператор, который нужно просмотреть, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="becbb-124">Right-click the operator that you want to view and select **Properties**.</span></span>  
  
     <span data-ttu-id="becbb-125">Дополнительные сведения о доступных параметрах, содержащихся в диалоговом окне _Свойства_**имя_оператора** , см. в разделе:</span><span class="sxs-lookup"><span data-stu-id="becbb-125">For more information on the available options contained in the _operator_name_**Properties** dialog box, see:</span></span>  
  
    -   [<span data-ttu-id="becbb-126">Свойства оператора и новый оператор &#40;общие&#41;страницы</span><span class="sxs-lookup"><span data-stu-id="becbb-126">Operator Properties and New Operator &#40;General Page&#41;</span></span>](../../integration-services/general-page-of-integration-services-designers-options.md)  
  
    -   [<span data-ttu-id="becbb-127">Свойства оператора: Новая страница &#40;уведомлений оператора&#41;</span><span class="sxs-lookup"><span data-stu-id="becbb-127">Operator Properties: New Operator &#40;Notifications Page&#41;</span></span>](operator-properties-new-operator-notifications-page.md)  
  
    -   [<span data-ttu-id="becbb-128">Свойства оператора (страница "Журнал")</span><span class="sxs-lookup"><span data-stu-id="becbb-128">Operator Properties &#40;History Page&#41;</span></span>](operator-properties-history-page.md)  
  
5.  <span data-ttu-id="becbb-129">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="becbb-129">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="becbb-130">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="becbb-130">Using Transact-SQL</span></span>  
  
#### <a name="to-view-information-about-an-operator"></a><span data-ttu-id="becbb-131">Просмотр сведений об операторе</span><span class="sxs-lookup"><span data-stu-id="becbb-131">To view information about an operator</span></span>  
  
1.  <span data-ttu-id="becbb-132">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="becbb-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="becbb-133">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="becbb-133">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="becbb-134">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="becbb-134">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- reports information about operator Fran??ois Ajenstat   
    -- This example assumes that the operator exists.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_help_operator  
        @operator_name = N'Fran??ois Ajenstat' ;  
    GO  
    ```  
  
 <span data-ttu-id="becbb-135">Дополнительные сведения см. в разделе [sp_help_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-operator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="becbb-135">For more information, see [sp_help_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-operator-transact-sql).</span></span>  
  
  
