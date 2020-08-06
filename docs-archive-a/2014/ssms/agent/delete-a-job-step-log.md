---
title: Удаление журнала шага задания | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- job steps [SQL Server Agent]
- deleting job step logs
- logs [SQL Server], jobs
- removing job step logs
ms.assetid: ee20c6cd-0258-4550-bdb0-71e86a0fb330
author: stevestein
ms.author: sstein
ms.openlocfilehash: de7c64c4d7cf461eef563ae6989e043d125c6f5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665215"
---
# <a name="delete-a-job-step-log"></a><span data-ttu-id="2c1d4-102">Delete a Job Step Log</span><span class="sxs-lookup"><span data-stu-id="2c1d4-102">Delete a Job Step Log</span></span>
  <span data-ttu-id="2c1d4-103">В этом разделе описывается, как удалить журнал шага задания агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2c1d4-103">This topic describes how to delete a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step log.</span></span>  
  
-   <span data-ttu-id="2c1d4-104">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="2c1d4-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2c1d4-105">Ограничения</span><span class="sxs-lookup"><span data-stu-id="2c1d4-105">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="2c1d4-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="2c1d4-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2c1d4-107">**Для удаления журнала шага задания агента SQL Server используется:**</span><span class="sxs-lookup"><span data-stu-id="2c1d4-107">**To delete a SQL Server Agent job step log, using:**</span></span>  
  
     [<span data-ttu-id="2c1d4-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2c1d4-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="2c1d4-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2c1d4-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="2c1d4-110">Управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="2c1d4-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2c1d4-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="2c1d4-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="2c1d4-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="2c1d4-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="2c1d4-113">При удалении шагов задания автоматически удаляются их выходные журналы.</span><span class="sxs-lookup"><span data-stu-id="2c1d4-113">When job steps are deleted their output log is automatically deleted.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2c1d4-114">безопасность</span><span class="sxs-lookup"><span data-stu-id="2c1d4-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2c1d4-115">Permissions</span><span class="sxs-lookup"><span data-stu-id="2c1d4-115">Permissions</span></span>  
 <span data-ttu-id="2c1d4-116">Если пользователь не является членом предопределенной роли сервера **sysadmin** , он может изменять только свои собственные задания.</span><span class="sxs-lookup"><span data-stu-id="2c1d4-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="2c1d4-117">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2c1d4-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-sql-server-agent-job-step-log"></a><span data-ttu-id="2c1d4-118">Удаление журнала шага задания агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="2c1d4-118">To delete a SQL Server Agent job step log</span></span>  
  
1.  <span data-ttu-id="2c1d4-119">В **обозревателе объектов** подключитесь к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , а затем разверните этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="2c1d4-119">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="2c1d4-120">Разверните узел **Агент SQL Server**, выберите раздел **Задания**, щелкните правой кнопкой мыши задание, которое нужно изменить, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="2c1d4-120">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to modify, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="2c1d4-121">В диалоговом окне **Свойства задания** удалите выбранный шаг задания.</span><span class="sxs-lookup"><span data-stu-id="2c1d4-121">In the **Job Properties** dialog box, delete the selected job step.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="2c1d4-122">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2c1d4-122">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-sql-server-agent-job-step-log"></a><span data-ttu-id="2c1d4-123">Удаление журнала шага задания агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="2c1d4-123">To delete a SQL Server Agent job step log</span></span>  
  
1.  <span data-ttu-id="2c1d4-124">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c1d4-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2c1d4-125">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="2c1d4-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2c1d4-126">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="2c1d4-126">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- removes the job step log for step 2 in the job Weekly Sales Data Backup  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_delete_jobsteplog  
        @job_name = N'Weekly Sales Data Backup',  
        @step_id = 2;  
    GO  
    ```  
  
 <span data-ttu-id="2c1d4-127">Дополнительные сведения см. в разделе [sp_delete_jobsteplog &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobsteplog-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2c1d4-127">For more information, see [sp_delete_jobsteplog &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobsteplog-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="2c1d4-128">Использование управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="2c1d4-128">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="2c1d4-129">Вызовите методы `DeleteJobStepLogs` класса `Job`, используя выбранный язык программирования, например Visual Basic, Visual C# или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2c1d4-129">Use the `DeleteJobStepLogs` methods of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="2c1d4-130">Дополнительные сведения см. в разделе[Управляющие объекты SQL Server](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="2c1d4-130">For more information, see[SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
  
```powershell
# Delete all job step log files that have ID values larger than 5.  
$srv = New-Object Microsoft.SqlServer.Management.Smo.Server("(local)")  
$jb = $srv.JobServer.Jobs["Test Job"]  
$jb.DeleteJobStepLogs(5)  
```
