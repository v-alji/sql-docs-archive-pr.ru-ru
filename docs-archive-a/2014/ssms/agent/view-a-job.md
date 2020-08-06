---
title: Просмотр задания | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], viewing
- viewing jobs
- SQL Server Agent jobs, viewing
- displaying jobs
ms.assetid: d2241a3f-dbcf-433c-b7bc-f96bdf0eac8c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 26406aaf2ba0ac4809eb7ac2c84799469d0468d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669238"
---
# <a name="view-a-job"></a><span data-ttu-id="07dcf-102">View a Job</span><span class="sxs-lookup"><span data-stu-id="07dcf-102">View a Job</span></span>
  <span data-ttu-id="07dcf-103">В этом разделе описывается просмотр [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] заданий агента в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="07dcf-103">This topic describes how to view [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="07dcf-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="07dcf-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="07dcf-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="07dcf-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="07dcf-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="07dcf-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="07dcf-107">**Для просмотра задания используется:**</span><span class="sxs-lookup"><span data-stu-id="07dcf-107">**To view a job, using:**</span></span>  
  
     [<span data-ttu-id="07dcf-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="07dcf-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="07dcf-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="07dcf-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="07dcf-110">Управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="07dcf-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="07dcf-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="07dcf-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="07dcf-112">безопасность</span><span class="sxs-lookup"><span data-stu-id="07dcf-112">Security</span></span>  
 <span data-ttu-id="07dcf-113">Если пользователь не принадлежит к предопределенной роли сервера **sysadmin** , он может просматривать лишь те задания, которыми владеет.</span><span class="sxs-lookup"><span data-stu-id="07dcf-113">You can only view jobs that you own, unless you are a member of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="07dcf-114">Члены этой роли могут просматривать все задания.</span><span class="sxs-lookup"><span data-stu-id="07dcf-114">Members of this role can view all jobs.</span></span> <span data-ttu-id="07dcf-115">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="07dcf-115">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="07dcf-116">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="07dcf-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-a-job"></a><span data-ttu-id="07dcf-117">Просмотр задания</span><span class="sxs-lookup"><span data-stu-id="07dcf-117">To view a job</span></span>  
  
1.  <span data-ttu-id="07dcf-118">В **обозревателе объектов** подключитесь к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , а затем разверните этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="07dcf-118">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="07dcf-119">Раскройте узел **Агент SQL Server**, а затем узел **Задания**.</span><span class="sxs-lookup"><span data-stu-id="07dcf-119">Expand **SQL Server Agent**, and then expand **Jobs**.</span></span>  
  
3.  <span data-ttu-id="07dcf-120">Правой кнопкой мыши щелкните задание и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="07dcf-120">Right-click a job, and then click **Properties**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="07dcf-121">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="07dcf-121">Using Transact-SQL</span></span>  
  
#### <a name="to-view-a-job"></a><span data-ttu-id="07dcf-122">Просмотр задания</span><span class="sxs-lookup"><span data-stu-id="07dcf-122">To view a job</span></span>  
  
1.  <span data-ttu-id="07dcf-123">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="07dcf-123">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="07dcf-124">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="07dcf-124">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="07dcf-125">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="07dcf-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- lists all aspects of the information for the job NightlyBackups.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_help_job  
        @job_name = N'NightlyBackups',  
        @job_aspect = N'ALL' ;  
    GO  
    ```  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="07dcf-126">Использование управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="07dcf-126">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="07dcf-127">**Просмотр задания**</span><span class="sxs-lookup"><span data-stu-id="07dcf-127">**To view a job**</span></span>  
  
 <span data-ttu-id="07dcf-128">Воспользуйтесь классом `Job` в любом языке программирования (Visual Basic, Visual C# или PowerShell).</span><span class="sxs-lookup"><span data-stu-id="07dcf-128">Use the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="07dcf-129">Дополнительные сведения см. в статье [Управляющие объекты SQL Server (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="07dcf-129">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
