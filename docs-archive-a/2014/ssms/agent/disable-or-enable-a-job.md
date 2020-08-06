---
title: Отключение или включение задания | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- stopping jobs
- disabling jobs
- SQL Server Agent jobs, disabling
- jobs [SQL Server Agent], disabling
ms.assetid: 5041261f-0c32-4d4a-8bee-59a6c16200dd
author: stevestein
ms.author: sstein
ms.openlocfilehash: 42fe7cbeed1e2ff3f93b1afef52b165a7d660ddd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654735"
---
# <a name="disable-or-enable-a-job"></a><span data-ttu-id="5c8a3-102">Disable or Enable a Job</span><span class="sxs-lookup"><span data-stu-id="5c8a3-102">Disable or Enable a Job</span></span>
  <span data-ttu-id="5c8a3-103">В этом разделе описано, как отключить задание агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c8a3-103">This topic describes how to disable a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5c8a3-104">Отключение задания не удаляет его, поэтому при необходимости оно может быть включено заново.</span><span class="sxs-lookup"><span data-stu-id="5c8a3-104">When you disable a job, it is not deleted and can be enabled again when necessary.</span></span>  
  
 <span data-ttu-id="5c8a3-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="5c8a3-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5c8a3-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="5c8a3-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5c8a3-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="5c8a3-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5c8a3-108">**Для включения или отключения задания используется:**</span><span class="sxs-lookup"><span data-stu-id="5c8a3-108">**To disable or enable a job, using:**</span></span>  
  
     [<span data-ttu-id="5c8a3-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5c8a3-109">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="5c8a3-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5c8a3-110">Transact-SQL</span></span>](#TSQL)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5c8a3-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="5c8a3-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5c8a3-112">безопасность</span><span class="sxs-lookup"><span data-stu-id="5c8a3-112">Security</span></span>  
 <span data-ttu-id="5c8a3-113">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="5c8a3-113">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="5c8a3-114">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5c8a3-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-or-enable-a-job"></a><span data-ttu-id="5c8a3-115">Включение или отключение задания</span><span class="sxs-lookup"><span data-stu-id="5c8a3-115">To disable or enable a job</span></span>  
  
1.  <span data-ttu-id="5c8a3-116">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]и разверните его.</span><span class="sxs-lookup"><span data-stu-id="5c8a3-116">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="5c8a3-117">Разверните узел **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="5c8a3-117">Expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="5c8a3-118">Разверните папку **Задания**, а затем правой кнопкой мыши щелкните задание, которое нужно включить или отключить.</span><span class="sxs-lookup"><span data-stu-id="5c8a3-118">Expand **Jobs**, and then right-click the job that you want to disable or enable.</span></span>  
  
4.  <span data-ttu-id="5c8a3-119">Чтобы отключить задание, выберите команду **Отключить**.</span><span class="sxs-lookup"><span data-stu-id="5c8a3-119">To disable a job, click **Disable**.</span></span> <span data-ttu-id="5c8a3-120">Чтобы включить задание, выберите команду **Включить**.</span><span class="sxs-lookup"><span data-stu-id="5c8a3-120">To enable a job, click **Enable**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="5c8a3-121">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5c8a3-121">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-or-enable-a-job"></a><span data-ttu-id="5c8a3-122">Включение или отключение задания</span><span class="sxs-lookup"><span data-stu-id="5c8a3-122">To disable or enable a job</span></span>  
  
1.  <span data-ttu-id="5c8a3-123">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c8a3-123">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5c8a3-124">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="5c8a3-124">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5c8a3-125">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="5c8a3-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- changes the name, description, and enables status of the job NightlyBackups.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_job  
        @job_name = N'NightlyBackups',  
        @new_name = N'NightlyBackups -- Disabled',  
        @description = N'Nightly backups disabled during server migration.',  
        @enabled = 1 ;  
    GO  
    ```  
  
 <span data-ttu-id="5c8a3-126">Дополнительные сведения см. в разделе [sp_update_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5c8a3-126">For more information, see [sp_update_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span></span>  
  
  
