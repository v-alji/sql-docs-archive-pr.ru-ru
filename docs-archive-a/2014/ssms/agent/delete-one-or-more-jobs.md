---
title: Удаление одного или нескольких заданий | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, deleting
- dropping jobs
- jobs [SQL Server Agent], deleting
- deleting jobs
- removing jobs
ms.assetid: 67dcdad0-57b2-431c-b77f-4ffc926af93d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 436625f9ad629a6b0e574aa046059f4e7e9c2bf2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655526"
---
# <a name="delete-one-or-more-jobs"></a><span data-ttu-id="d1fde-102">Удаление одного или нескольких заданий</span><span class="sxs-lookup"><span data-stu-id="d1fde-102">Delete One or More Jobs</span></span>
  <span data-ttu-id="d1fde-103">В этом разделе описывается удаление [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] заданий агента в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] или управляющие объекты SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d1fde-103">This topic describes how to delete [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d1fde-104">Перед началом</span><span class="sxs-lookup"><span data-stu-id="d1fde-104">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d1fde-105">безопасность</span><span class="sxs-lookup"><span data-stu-id="d1fde-105">Security</span></span>  
 <span data-ttu-id="d1fde-106">Пользователь, не являющийся членом предопределенной роли сервера **sysadmin** , может удалять только те задания, которыми владеет.</span><span class="sxs-lookup"><span data-stu-id="d1fde-106">Unless you are a member of the **sysadmin** fixed server role, you can only delete jobs that you own.</span></span>  
  
 
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="d1fde-107">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d1fde-107">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-job"></a><span data-ttu-id="d1fde-108">Удаление задания</span><span class="sxs-lookup"><span data-stu-id="d1fde-108">To delete a job</span></span>  
  
1.  <span data-ttu-id="d1fde-109">В **обозревателе объектов** подключитесь к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , а затем разверните этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="d1fde-109">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="d1fde-110">Разверните узел **Агент SQL Server**, выберите раздел **Задания**, щелкните правой кнопкой мыши задание, которое необходимо удалить, и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="d1fde-110">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to delete, and then click **Delete**.</span></span>  
  
3.  <span data-ttu-id="d1fde-111">В диалоговом окне **Удаление объекта** убедитесь, что выбрано задание, которое следует удалить.</span><span class="sxs-lookup"><span data-stu-id="d1fde-111">In the **Delete Object** dialog box, confirm that the job you intend to delete is selected.</span></span>  
  
4.  <span data-ttu-id="d1fde-112">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d1fde-112">Click **OK**.</span></span>  
  
#### <a name="to-delete-multiple-jobs"></a><span data-ttu-id="d1fde-113">Удаление нескольких заданий</span><span class="sxs-lookup"><span data-stu-id="d1fde-113">To delete multiple jobs</span></span>  
  
1.  <span data-ttu-id="d1fde-114">В **обозревателе объектов** подключитесь к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , а затем разверните этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="d1fde-114">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="d1fde-115">Разверните узел **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="d1fde-115">Expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="d1fde-116">Щелкните правой кнопкой мыши **Монитор активности заданий**и выберите пункт **Просмотр активности заданий**.</span><span class="sxs-lookup"><span data-stu-id="d1fde-116">Right-click **Job Activity Monitor**, and click **View Job Activity**.</span></span>  
  
4.  <span data-ttu-id="d1fde-117">В мониторе активности заданий выберите задания для удаления, щелкните правой кнопкой мыши выделенные задания и выберите команду **Удалить задания**.</span><span class="sxs-lookup"><span data-stu-id="d1fde-117">In the Job Activity Monitor, select the jobs you want to delete, right-click your selection, and choose **Delete jobs**.</span></span>  
  

  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="d1fde-118">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d1fde-118">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-job"></a><span data-ttu-id="d1fde-119">Удаление задания</span><span class="sxs-lookup"><span data-stu-id="d1fde-119">To delete a job</span></span>  
  
1.  <span data-ttu-id="d1fde-120">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1fde-120">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d1fde-121">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="d1fde-121">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d1fde-122">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="d1fde-122">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    USE msdb ;  
    GO  
  
    EXEC sp_delete_job  
        @job_name = N'NightlyBackups' ;  
    GO  
    ```  
  
 <span data-ttu-id="d1fde-123">Дополнительные сведения см. в разделе [sp_delete_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d1fde-123">For more information, see [sp_delete_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-job-transact-sql).</span></span>  

##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="d1fde-124">Использование управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="d1fde-124">Using SQL Server Management Objects</span></span>  

### <a name="to-delete-multiple-jobs"></a><span data-ttu-id="d1fde-125">Удаление нескольких заданий</span><span class="sxs-lookup"><span data-stu-id="d1fde-125">To delete multiple jobs</span></span>
  
 <span data-ttu-id="d1fde-126">Воспользуйтесь классом `JobCollection` в любом языке программирования (Visual Basic, Visual C# или PowerShell).</span><span class="sxs-lookup"><span data-stu-id="d1fde-126">Use the `JobCollection` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="d1fde-127">Дополнительные сведения см. в статье [Управляющие объекты SQL Server (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="d1fde-127">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
