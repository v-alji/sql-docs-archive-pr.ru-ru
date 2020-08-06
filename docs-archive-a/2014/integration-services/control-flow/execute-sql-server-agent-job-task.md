---
title: Задача "Выполнение задания агента SQL Server" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executesqlserveragentjobtask.f1
helpviewer_keywords:
- Execute SQL Server Agent Job task [Integration Services]
- jobs [Integration Services]
- SQL Server Agent [Integration Services]
ms.assetid: 3aa3bc0e-1a1c-452e-81b8-b4e3422ea053
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d0c66eb7022312fa3ec3d161f63a9aee92b840f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665059"
---
# <a name="execute-sql-server-agent-job-task"></a><span data-ttu-id="512a5-102">Задача «Выполнение задания агента SQL Server»</span><span class="sxs-lookup"><span data-stu-id="512a5-102">Execute SQL Server Agent Job Task</span></span>
  <span data-ttu-id="512a5-103">Задача «Выполнение задания агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] » запускает задания агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="512a5-103">The Execute [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Job task runs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="512a5-104">является службой [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, которая запускает задания, определенные для экземпляра SQL Server.</span><span class="sxs-lookup"><span data-stu-id="512a5-104">Agent is a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows service that runs jobs that have been defined in an instance of SQL Server.</span></span> <span data-ttu-id="512a5-105">Можно создавать задания, которые выполняют инструкции Transact-SQL и скрипты ActiveX, задачи служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] и задачи обслуживания репликаций либо производят запуск пакетов.</span><span class="sxs-lookup"><span data-stu-id="512a5-105">You can create jobs that execute Transact-SQL statements and ActiveX scripts, perform [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] and Replication maintenance tasks, or run packages.</span></span> <span data-ttu-id="512a5-106">Можно также настроить задание, чтобы контролировать [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и вызывать предупреждения.</span><span class="sxs-lookup"><span data-stu-id="512a5-106">You can also configure a job to monitor [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and fire alerts.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="512a5-107">обычно используются, чтобы автоматически выполнять повторяющиеся задачи.</span><span class="sxs-lookup"><span data-stu-id="512a5-107">Agent jobs are typically used to automate tasks that you perform repeatedly.</span></span> <span data-ttu-id="512a5-108">Дополнительные сведения см. в разделе [Реализация заданий](../../ssms/agent/implement-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="512a5-108">For more information, see [Implement Jobs](../../ssms/agent/implement-jobs.md).</span></span>  
  
 <span data-ttu-id="512a5-109">Используя задачу «Выполнение задания агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] », пакет может выполнять административные задачи, связанные с компонентами [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="512a5-109">By using the Execute [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Job task, a package can perform administrative tasks related to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components.</span></span> <span data-ttu-id="512a5-110">Например, задача агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] может запускать системную хранимую процедуру — к примеру, **sp_dts_listpackages** — для получения списка пакетов в папке.</span><span class="sxs-lookup"><span data-stu-id="512a5-110">For example, a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job can run a system stored procedure such as **sp_enum_dtspackages** to obtain a list of packages in a folder.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="512a5-111">Агент должен быть запущен для автоматического запуска локальных или многосерверных административных заданий.</span><span class="sxs-lookup"><span data-stu-id="512a5-111">Agent must be running before local or multiserver administrative jobs can run automatically.</span></span>  
  
 <span data-ttu-id="512a5-112">Эта задача содержит системную процедуру **sp_start_job** и передает имя задания агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в виде аргумента.</span><span class="sxs-lookup"><span data-stu-id="512a5-112">This task encapsulates the **sp_start_job** system procedure and passes the name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job to the procedure as an argument.</span></span> <span data-ttu-id="512a5-113">Дополнительные сведения см. в разделе [sp_start_job (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-start-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="512a5-113">For more information, see [sp_start_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-start-job-transact-sql).</span></span>  
  
## <a name="configuring-the-execute-sql-server-agent-job-task"></a><span data-ttu-id="512a5-114">Настройка задачи «Выполнение задания агента SQL Server»</span><span class="sxs-lookup"><span data-stu-id="512a5-114">Configuring the Execute SQL Server Agent Job Task</span></span>  
 <span data-ttu-id="512a5-115">Свойства задаются с помощью конструктора служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="512a5-115">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="512a5-116">Эта задача находится в разделе **Задачи плана обслуживания** **области элементов** в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="512a5-116">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="512a5-117">Дополнительные сведения о свойствах, которые можно задать в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="512a5-117">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="512a5-118">Задача "Выполнение задания агента SQL Server" (план обслуживания)</span><span class="sxs-lookup"><span data-stu-id="512a5-118">Execute SQL Server Agent Job Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/execute-sql-server-agent-job-task-maintenance-plan.md)  
  
 <span data-ttu-id="512a5-119">Дополнительные сведения об установке этих свойств в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="512a5-119">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="512a5-120">Задание свойств задач или контейнеров</span><span class="sxs-lookup"><span data-stu-id="512a5-120">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
  
