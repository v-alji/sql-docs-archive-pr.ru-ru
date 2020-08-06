---
title: Изменение целевых серверов для задания | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- modifying target servers
- SQL Server Agent jobs, target servers
- target servers [SQL Server], modifying
ms.assetid: 9dbe24f2-acec-4aa2-920c-e8e96efa18e4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 246a5bb59a681a70734cc8cabef4f724cda1b52e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658050"
---
# <a name="modify-the-target-servers-for-a-job"></a><span data-ttu-id="8ebbe-102">Modify the Target Servers for a Job</span><span class="sxs-lookup"><span data-stu-id="8ebbe-102">Modify the Target Servers for a Job</span></span>
  <span data-ttu-id="8ebbe-103">В этом разделе описывается изменение целевых серверов для [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] заданий агента в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8ebbe-103">This topic describes how to change the target servers for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="8ebbe-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="8ebbe-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8ebbe-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="8ebbe-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8ebbe-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="8ebbe-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8ebbe-107">**Для изменения целевых серверов для задания используется:**</span><span class="sxs-lookup"><span data-stu-id="8ebbe-107">**To modify the target servers for a job, using:**</span></span>  
  
     [<span data-ttu-id="8ebbe-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8ebbe-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8ebbe-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8ebbe-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8ebbe-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="8ebbe-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8ebbe-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="8ebbe-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8ebbe-112">Permissions</span><span class="sxs-lookup"><span data-stu-id="8ebbe-112">Permissions</span></span>  
 <span data-ttu-id="8ebbe-113">По умолчанию участники фиксированной роли сервера sysadmin могут выполнять эту хранимую процедуру.</span><span class="sxs-lookup"><span data-stu-id="8ebbe-113">By default, members of the sysadmin fixed server role can execute this stored procedure.</span></span> <span data-ttu-id="8ebbe-114">Другим пользователям должна быть предоставлена одна из следующих предопределенных ролей базы данных агента SQL Server в базе данных msdb.</span><span class="sxs-lookup"><span data-stu-id="8ebbe-114">Other users must be granted one of the following SQL Server Agent fixed database roles in the msdb database:</span></span>  
  
1.  `SQLAgentUserRole`  
  
2.  `SQLAgentReaderRole`  
  
3.  <span data-ttu-id="8ebbe-115">SQLAgentOperatorRole</span><span class="sxs-lookup"><span data-stu-id="8ebbe-115">SQLAgentOperatorRole</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8ebbe-116">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8ebbe-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-the-target-servers-for-a-job"></a><span data-ttu-id="8ebbe-117">Изменение целевых серверов для задания</span><span class="sxs-lookup"><span data-stu-id="8ebbe-117">To modify the target servers for a job</span></span>  
  
1.  <span data-ttu-id="8ebbe-118">В **обозревателе объектов** подключитесь к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , а затем разверните этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="8ebbe-118">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="8ebbe-119">Разверните **Агент SQL Server**, **Задания**, затем щелкните правой кнопкой мыши задание и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="8ebbe-119">Expand **SQL Server Agent**, expand **Jobs**, right-click a job, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="8ebbe-120">В диалоговом окне **Свойства задания** выберите страницу **Цели**, а затем выберите пункт **Выбрать локальный сервер в качестве целевого**или пункт **Выбрать несколько серверов в качестве целевых**.</span><span class="sxs-lookup"><span data-stu-id="8ebbe-120">In the **Job Properties** dialog, select the **Targets**page, and click **Target local server**, or **Target multiple servers**.</span></span>  
  
     <span data-ttu-id="8ebbe-121">При выборе пункта **Выбрать несколько серверов в качестве целевых**необходимо обозначить серверы, которые будут целевыми для задания, пометив флажки слева от имен соответствующих серверов.</span><span class="sxs-lookup"><span data-stu-id="8ebbe-121">If you choose **Target multiple servers**, designate the servers that will be targets for the job by checking the box to the left of the server name.</span></span> <span data-ttu-id="8ebbe-122">Убедитесь в том, что флажки серверов, которые не будут являться целевыми для задания, не помечены.</span><span class="sxs-lookup"><span data-stu-id="8ebbe-122">Verify that the check boxes for servers that will not be targets of the job are unchecked.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8ebbe-123">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8ebbe-123">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-the-target-servers-for-a-job"></a><span data-ttu-id="8ebbe-124">Изменение целевых серверов для задания</span><span class="sxs-lookup"><span data-stu-id="8ebbe-124">To modify the target servers for a job</span></span>  
  
1.  <span data-ttu-id="8ebbe-125">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ebbe-125">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8ebbe-126">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="8ebbe-126">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8ebbe-127">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="8ebbe-127">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="8ebbe-128">В этом примере многосерверное задание Weekly Sales Backups назначается серверу SEATTLE2.</span><span class="sxs-lookup"><span data-stu-id="8ebbe-128">This example assigns the multiserver job Weekly Sales Backups to the server SEATTLE2.</span></span>  
  
```  
USE msdb ;  
GO  
  
EXEC dbo.sp_add_jobserver  
    @job_name = N'Weekly Sales Backups',   
    @server_name = N'SEATTLE2' ;   
GO  
  
```  
  
 <span data-ttu-id="8ebbe-129">Дополнительные сведения см. в разделе [sp_add_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8ebbe-129">For more information, see [sp_add_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ebbe-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="8ebbe-130">See Also</span></span>  
 [<span data-ttu-id="8ebbe-131">Автоматизация администрирования в масштабах предприятия</span><span class="sxs-lookup"><span data-stu-id="8ebbe-131">Automated Administration Across an Enterprise</span></span>](automated-administration-across-an-enterprise.md)  
  
  
