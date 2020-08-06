---
title: Задача "Выполнение задания агента SQL Server" (план обслуживания) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.executejob.f1
helpviewer_keywords:
- Execute SQL Server Agent Job Task dialog box
ms.assetid: 4ed75956-ebb8-4d8c-9c16-fc0eb00bd3a0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b997d5144b113102ba0ed2d9d1df59b6707acbee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666573"
---
# <a name="execute-sql-server-agent-job-task-maintenance-plan"></a><span data-ttu-id="49a08-102">Задача «Выполнение задания агента SQL Server» (план обслуживания)</span><span class="sxs-lookup"><span data-stu-id="49a08-102">Execute SQL Server Agent Job Task (Maintenance Plan)</span></span>
  <span data-ttu-id="49a08-103">Используйте диалоговое окно **Задача «Выполнение задания агента SQL Server»** для выполнения заданий агента Microsoft SQL Server в соответствии с планом обслуживания.</span><span class="sxs-lookup"><span data-stu-id="49a08-103">Use the **Execute SQL Server Agent Job Task** dialog to execute Microsoft SQL Server Agent jobs within a maintenance plan.</span></span> <span data-ttu-id="49a08-104">Данный параметр недоступен, если для выбранного соединения нет заданий агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="49a08-104">This option will not be available if you have no SQL Server Agent jobs on the selected connection.</span></span>  
  
 <span data-ttu-id="49a08-105">Эта задача использует инструкцию **.sp_start_job** .</span><span class="sxs-lookup"><span data-stu-id="49a08-105">This task uses the **.sp_start_job** statement.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="49a08-106">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="49a08-106">UI element list</span></span>  
 <span data-ttu-id="49a08-107">**Соединение**</span><span class="sxs-lookup"><span data-stu-id="49a08-107">**Connection**</span></span>  
 <span data-ttu-id="49a08-108">Выберите соединение с сервером, которое будет использоваться для выполнения этой задачи.</span><span class="sxs-lookup"><span data-stu-id="49a08-108">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="49a08-109">**Создать**</span><span class="sxs-lookup"><span data-stu-id="49a08-109">**New**</span></span>  
 <span data-ttu-id="49a08-110">Создать новое соединение с сервером для его использования при выполнении этой задачи.</span><span class="sxs-lookup"><span data-stu-id="49a08-110">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="49a08-111">Диалоговое окно **Создание соединения** описано ниже.</span><span class="sxs-lookup"><span data-stu-id="49a08-111">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="49a08-112">**Доступные задания агента SQL Server**</span><span class="sxs-lookup"><span data-stu-id="49a08-112">**Available SQL Agent jobs**</span></span>  
 <span data-ttu-id="49a08-113">Выберите задание для выполнения.</span><span class="sxs-lookup"><span data-stu-id="49a08-113">Select the job to execute.</span></span> <span data-ttu-id="49a08-114">Для идентификации заданий в сетке используются столбцы **Имя задания** и **Описание** .</span><span class="sxs-lookup"><span data-stu-id="49a08-114">The grid provides the **Job name** and **Description** to identify the jobs.</span></span>  
  
 <span data-ttu-id="49a08-115">**Просмотр T-SQL**</span><span class="sxs-lookup"><span data-stu-id="49a08-115">**View T-SQL**</span></span>  
 <span data-ttu-id="49a08-116">Просмотрите инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] , выполняемые для данной задачи по отношению к серверу, на основе выбранных параметров.</span><span class="sxs-lookup"><span data-stu-id="49a08-116">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="49a08-117">Если количество затронутых объектов велико, построение этого отображения может занять значительное время.</span><span class="sxs-lookup"><span data-stu-id="49a08-117">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="49a08-118">Диалоговое окно «Создание соединения»</span><span class="sxs-lookup"><span data-stu-id="49a08-118">New Connection Dialog Box</span></span>  
 <span data-ttu-id="49a08-119">**Имя соединения**</span><span class="sxs-lookup"><span data-stu-id="49a08-119">**Connection name**</span></span>  
 <span data-ttu-id="49a08-120">Введите имя нового соединения.</span><span class="sxs-lookup"><span data-stu-id="49a08-120">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="49a08-121">**Выберите или введите имя сервера**</span><span class="sxs-lookup"><span data-stu-id="49a08-121">**Select or enter a server name**</span></span>  
 <span data-ttu-id="49a08-122">Выберите сервер для подключения при выполнении этой задачи.</span><span class="sxs-lookup"><span data-stu-id="49a08-122">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="49a08-123">**Обновить**</span><span class="sxs-lookup"><span data-stu-id="49a08-123">**Refresh**</span></span>  
 <span data-ttu-id="49a08-124">Обновите список доступных серверов.</span><span class="sxs-lookup"><span data-stu-id="49a08-124">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="49a08-125">**Введите данные для входа на сервер**</span><span class="sxs-lookup"><span data-stu-id="49a08-125">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="49a08-126">Укажите способ проверки подлинности на сервере.</span><span class="sxs-lookup"><span data-stu-id="49a08-126">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="49a08-127">**Использовать встроенную безопасность Windows**</span><span class="sxs-lookup"><span data-stu-id="49a08-127">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="49a08-128">Подключение к экземпляру компонента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] с использованием проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="49a08-128">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with Microsoft Windows Authentication.</span></span>  
  
 <span data-ttu-id="49a08-129">**Использовать указанные имя пользователя и пароль**</span><span class="sxs-lookup"><span data-stu-id="49a08-129">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="49a08-130">Подключиться к экземпляру компонента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] с использованием проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="49a08-130">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="49a08-131">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="49a08-131">This option is not available.</span></span>  
  
 <span data-ttu-id="49a08-132">**User name**</span><span class="sxs-lookup"><span data-stu-id="49a08-132">**User name**</span></span>  
 <span data-ttu-id="49a08-133">Укажите имя входа, используемое при проверке подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="49a08-133">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="49a08-134">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="49a08-134">This option is not available.</span></span>  
  
 <span data-ttu-id="49a08-135">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="49a08-135">**Password**</span></span>  
 <span data-ttu-id="49a08-136">Укажите используемый при проверке подлинности пароль.</span><span class="sxs-lookup"><span data-stu-id="49a08-136">Provide a password to use when authenticating.</span></span> <span data-ttu-id="49a08-137">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="49a08-137">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49a08-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="49a08-138">See Also</span></span>  
 <span data-ttu-id="49a08-139">[sp_add_job (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-add-job-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="49a08-139">[sp_add_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-job-transact-sql) </span></span>  
 <span data-ttu-id="49a08-140">[Создание задания](../../ssms/agent/create-a-job.md) </span><span class="sxs-lookup"><span data-stu-id="49a08-140">[Create a Job](../../ssms/agent/create-a-job.md) </span></span>  
 [<span data-ttu-id="49a08-141">sp_start_job (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="49a08-141">sp_start_job &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-start-job-transact-sql)  
  
  
