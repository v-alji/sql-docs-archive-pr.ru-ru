---
title: Запуск, остановка, приостановка, возобновление и перезапуск ядро СУБД, агент SQL Server или службы обозреватель SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Configuration Manager, start and stop services
- stopping SQL Server Agent
- parameters [SQL Server], startup options
- SQL Server, startup options
- Database Engine [SQL Server], starting and stopping services
- pausing SQL Server
- PowerShell [SQL Server], starting and stopping services
- single-user mode [SQL Server], starting in
- SQL Server Management Studio [SQL Server], starting or stopping services
- stopping SQL Server Browser service
- starting SQL Server Agent
- default instances [SQL Server], starting and stopping
- SQL Server Agent, starting and stopping
- command prompt [SQL Server], starting and stopping SQL Server services
- continuing SQL Server
- starting SQL Server Database Engine
- net stop commands [SQL Server]
- command prompt [SQL Server], SQL Browser service
- Configuration Manager, start and stop services
- resuming SQL Server
- startup options [SQL Server]
- named instances [SQL Server], starting and stopping
- net start commands [SQL Server]
- SQL Server, starting and stopping
- stopping SQL Server
- starting SQL Server Browser service
- SQL Server Database Engine setting startup options
- administering SQL Server, starting and stopping services
- Management Studio [SQL Server], starting or stopping services
ms.assetid: 32660a02-e5a1-411a-9e57-7066ca459df6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f4b102c8fd81923d7386c8e556896e715311a07e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738696"
---
# <a name="start-stop-pause-resume-restart-the-database-engine-sql-server-agent-or-sql-server-browser-service"></a><span data-ttu-id="cfcc2-102">Запуск, остановка, приостановка, возобновление и перезапуск компонента Database Engine, агента SQL и службы браузера SQL Server</span><span class="sxs-lookup"><span data-stu-id="cfcc2-102">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>
  <span data-ttu-id="cfcc2-103">В этом разделе описано, как запускать, останавливать, приостанавливать, возобновлять или перезапускать [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] агент или [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] службу браузера с помощью [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , команды **net** из командной строки, [!INCLUDE[tsql](../../includes/tsql-md.md)] или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-103">This topic describes how to start, stop, pause, resume, or restart the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], **net** commands from a command prompt, [!INCLUDE[tsql](../../includes/tsql-md.md)], or PowerShell.</span></span>  
  
-   <span data-ttu-id="cfcc2-104">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="cfcc2-104">**Before you begin:**</span></span>  
  
    -   [<span data-ttu-id="cfcc2-105">Что это за службы?</span><span class="sxs-lookup"><span data-stu-id="cfcc2-105">What are these services?</span></span>](#Services)  
  
    -   [<span data-ttu-id="cfcc2-106">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="cfcc2-106">Additional Information</span></span>](#MoreInformation)  
  
    -   [<span data-ttu-id="cfcc2-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="cfcc2-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="cfcc2-108">**Инструкции по использованию:**</span><span class="sxs-lookup"><span data-stu-id="cfcc2-108">**Instructions using:**</span></span>  
  
    -   [<span data-ttu-id="cfcc2-109">Диспетчер конфигурации SQL Server</span><span class="sxs-lookup"><span data-stu-id="cfcc2-109">SQL Server Configuration Manager</span></span>](#SSCMProcedure)  
  
    -   [<span data-ttu-id="cfcc2-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cfcc2-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
    -   [<span data-ttu-id="cfcc2-111">Команды NET из окна командной строки</span><span class="sxs-lookup"><span data-stu-id="cfcc2-111">net Commands from a Command Prompt window</span></span>](#CommandPrompt)  
  
    -   [<span data-ttu-id="cfcc2-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cfcc2-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
    -   [<span data-ttu-id="cfcc2-113">PowerShell</span><span class="sxs-lookup"><span data-stu-id="cfcc2-113">PowerShell</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="cfcc2-114">Перед началом</span><span class="sxs-lookup"><span data-stu-id="cfcc2-114">Before You Begin</span></span>  
  
###  <a name="what-is-the-ssdenoversion-service-the-ssnoversion-agent-service-and-the-ssnoversion-browser-service"></a><a name="Services"></a> <span data-ttu-id="cfcc2-115">Что такое служба [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , служба агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и служба браузера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ?</span><span class="sxs-lookup"><span data-stu-id="cfcc2-115">What is the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] service, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service, and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service?</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="cfcc2-116">являются исполняемыми программами, работающими в качестве служб Windows.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-116">components are executable programs that run as a Windows service.</span></span> <span data-ttu-id="cfcc2-117">Программы, запущенные в качестве служб Windows, работают, не проявляя никакой активности на экране компьютера.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-117">Programs that run as a Windows service can continue to operate without displaying any activity on the computer screen.</span></span>  
  
 <span data-ttu-id="cfcc2-118">**[!INCLUDE[ssDE](../../includes/ssde-md.md)]служеб**</span><span class="sxs-lookup"><span data-stu-id="cfcc2-118">**[!INCLUDE[ssDE](../../includes/ssde-md.md)] service**</span></span>  
 <span data-ttu-id="cfcc2-119">Исполняемый процесс, который представляет собой компонент [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cfcc2-119">The executable process that is the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="cfcc2-120">[!INCLUDE[ssDE](../../includes/ssde-md.md)] может быть экземпляром по умолчанию (может быть только один на одном компьютере) либо может быть одним из нескольких именованных экземпляров [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cfcc2-120">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] can be the default instance (limit one per computer), or can be one of many named instances of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="cfcc2-121">С помощью диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] определите, какие экземпляры [!INCLUDE[ssDE](../../includes/ssde-md.md)] установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-121">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to determine which instances of [!INCLUDE[ssDE](../../includes/ssde-md.md)] are installed on the computer.</span></span> <span data-ttu-id="cfcc2-122">Экземпляр по умолчанию (если он установлен) указан как \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (MSSQLSERVER)\*\*.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-122">The default instance (if you install it) is listed as **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (MSSQLSERVER)**.</span></span> <span data-ttu-id="cfcc2-123">Именованные экземпляры (если они установлены) перечислены как \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (<instance_name>)\*\*.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-123">Named instances (if you install them) are listed as **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (<instance_name>)**.</span></span> <span data-ttu-id="cfcc2-124">По умолчанию [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express устанавливается как \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SQLEXPRESS)\*\*.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-124">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express is installed as **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SQLEXPRESS)**.</span></span>  
  
 <span data-ttu-id="cfcc2-125">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Служба агента**</span><span class="sxs-lookup"><span data-stu-id="cfcc2-125">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service**</span></span>  
 <span data-ttu-id="cfcc2-126">Служба Microsoft Windows, выполняющая запланированные административные задачи, которые называются заданиями и предупреждениями.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-126">A Windows service that executes scheduled administrative tasks, which are called jobs and alerts.</span></span> <span data-ttu-id="cfcc2-127">Дополнительные сведения см. в статье [SQL Server Agent](../../ssms/agent/sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="cfcc2-127">For more information, see [SQL Server Agent](../../ssms/agent/sql-server-agent.md).</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="cfcc2-128">доступен не во всех выпусках [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cfcc2-128">Agent is not available in every edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cfcc2-129">Перечень функций, поддерживаемых в разных выпусках [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], см. в разделе [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="cfcc2-129">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
 <span data-ttu-id="cfcc2-130">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Служба браузера**</span><span class="sxs-lookup"><span data-stu-id="cfcc2-130">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service**</span></span>  
 <span data-ttu-id="cfcc2-131">Служба Windows, прослушивающая входящие запросы на ресурсы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и предоставляющая клиентам сведения об экземплярах [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , установленных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-131">A Windows service that listens for incoming requests for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resources and provides clients information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances installed on the computer.</span></span> <span data-ttu-id="cfcc2-132">Один экземпляр службы браузера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] используется для всех экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , установленных на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-132">A single instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service is used for all instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installed on the computer.</span></span>  
  
###  <a name="additional-information"></a><a name="MoreInformation"></a><span data-ttu-id="cfcc2-133">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="cfcc2-133">Additional Information</span></span>  
  
-   <span data-ttu-id="cfcc2-134">Приостановка службы [!INCLUDE[ssDE](../../includes/ssde-md.md)] делает невозможным подключение новых пользователей к [!INCLUDE[ssDE](../../includes/ssde-md.md)], однако уже подключенные пользователи могут работать до тех пор, пока их соединения не будут разорваны.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-134">Pausing the [!INCLUDE[ssDE](../../includes/ssde-md.md)] service prevents new users from connecting to the [!INCLUDE[ssDE](../../includes/ssde-md.md)], but users who are already connected can continue to work until their connections are broken.</span></span> <span data-ttu-id="cfcc2-135">Приостановите работу службы, если нужно дождаться окончания работы пользователей, прежде чем совсем остановить службу.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-135">Use pause when you want to wait for users to complete work before you stop the service.</span></span> <span data-ttu-id="cfcc2-136">Это позволяет им завершить транзакции, которые в данный момент выполняются.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-136">This enables them to complete transactions that are in progress.</span></span> <span data-ttu-id="cfcc2-137">Возобновление позволяет [!INCLUDE[ssDE](../../includes/ssde-md.md)] снова принимать входящие подключения.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-137">Resume allows the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to accept new connections again.</span></span> <span data-ttu-id="cfcc2-138">Службу агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] нельзя приостановить или возобновить.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-138">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service cannot be paused or resumed.</span></span>  
  
-   <span data-ttu-id="cfcc2-139">Диспетчер конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] отображают текущее состояние служб с помощью следующих значков.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-139">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager and [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] display the current status of services by using the following icons.</span></span>  
  
     <span data-ttu-id="cfcc2-140">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Configuration Manager**</span><span class="sxs-lookup"><span data-stu-id="cfcc2-140">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager**</span></span>  
  
    -   <span data-ttu-id="cfcc2-141">Зеленая стрелка на значке рядом с именем службы указывает на то, что служба запущена.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-141">A green arrow on the icon next to the service name indicates that the service is started.</span></span>  
  
    -   <span data-ttu-id="cfcc2-142">Красный квадрат на значке рядом с именем службы означает, что служба остановлена.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-142">A red square on the icon next to the service name indicates that the service is stopped.</span></span>  
  
    -   <span data-ttu-id="cfcc2-143">Пара вертикальных синих полосок на значке рядом с именем службы указывает на то, что служба приостановлена.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-143">Two vertical blue lines on the icon next to the service name indicates that the service is paused.</span></span>  
  
    -   <span data-ttu-id="cfcc2-144">При перезапуске [!INCLUDE[ssDE](../../includes/ssde-md.md)]красный квадрат обозначает, что служба остановлена, затем зеленая стрелка покажет, что служба успешно запущена.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-144">When restarting the [!INCLUDE[ssDE](../../includes/ssde-md.md)], a red square will indicate that the service stopped, and then a green arrow will indicate that he service started successfully.</span></span>  
  
     **[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**  
  
    -   <span data-ttu-id="cfcc2-145">Белая стрелка на значке с зеленым кругом рядом с именем службы указывает на то, что служба запущена.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-145">A white arrow on a green circle icon next to the service name indicates that the service is started.</span></span>  
  
    -   <span data-ttu-id="cfcc2-146">Белый квадрат на значке с красным кругом рядом с именем службы означает, что служба остановлена.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-146">A white square on a red circle icon next to the service name indicates that the service is stopped.</span></span>  
  
    -   <span data-ttu-id="cfcc2-147">Пара вертикальных белых полосок на значке с синим кругом рядом с именем службы указывает, что служба приостановлена.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-147">Two vertical white lines on a blue circle icon next to the service name indicates that the service is paused.</span></span>  
  
-   <span data-ttu-id="cfcc2-148">При использовании диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]доступны только применимые параметры.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-148">When using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager or [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], only options that are possible will be available.</span></span> <span data-ttu-id="cfcc2-149">Например, если служба уже запущена, **Пуск** будет недоступен.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-149">For example, if the service is already started, **Start** will be unavailable.</span></span>  
  
-   <span data-ttu-id="cfcc2-150">При эксплуатации на кластере службой [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] лучше всего управлять с помощью администратора кластера.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-150">When running on a cluster, the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] service is best managed by using Cluster Administrator.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="cfcc2-151">безопасность</span><span class="sxs-lookup"><span data-stu-id="cfcc2-151">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="cfcc2-152">Permissions</span><span class="sxs-lookup"><span data-stu-id="cfcc2-152">Permissions</span></span>  
 <span data-ttu-id="cfcc2-153">По умолчанию только участники локальной группы «Администраторы» могут запускать, останавливать, приостанавливать, возобновлять или перезапускать службу.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-153">By default, only members of the local administrators group can start, stop, pause, resume or restart a service.</span></span> <span data-ttu-id="cfcc2-154">При необходимости предоставить возможность управления службой для пользователей, не обладающих правами администратора, см. раздел [Как предоставить пользователям права для управления службами в Windows Server 2003](https://support.microsoft.com/kb/325349).</span><span class="sxs-lookup"><span data-stu-id="cfcc2-154">To grant non-administrators the ability to manage services, see [How to grant users rights to manage services in Windows Server 2003](https://support.microsoft.com/kb/325349).</span></span> <span data-ttu-id="cfcc2-155">(Процесс такой же, как и в других версиях Windows.)</span><span class="sxs-lookup"><span data-stu-id="cfcc2-155">(The process is similar on other versions of Windows.)</span></span>  
  
 <span data-ttu-id="cfcc2-156">Для остановки с [!INCLUDE[ssDE](../../includes/ssde-md.md)] помощью [!INCLUDE[tsql](../../includes/tsql-md.md)] `SHUTDOWN` команды требуется членство в предопределенных ролях сервера **sysadmin** или **serveradmin** , и он не может быть передан.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-156">Stopping the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by using the [!INCLUDE[tsql](../../includes/tsql-md.md)]`SHUTDOWN` command requires membership in the **sysadmin** or **serveradmin** fixed server roles, and is not transferable.</span></span>  
  
##  <a name="using-ssnoversion-configuration-manager"></a><a name="SSCMProcedure"></a> <span data-ttu-id="cfcc2-157">С помощью диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfcc2-157">Using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager</span></span>  
  
#### <a name="to-start-stop-pause-resume-or-restart-the-an-instance-of-the-ssdenoversion"></a><span data-ttu-id="cfcc2-158">Запуск, остановка, приостановка, возобновление или перезапуск экземпляра [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfcc2-158">To start, stop, pause, resume, or restart the an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]</span></span>  
  
1.  <span data-ttu-id="cfcc2-159">В меню **Пуск** последовательно выберите пункты **Все программы**, [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], **Средства настройки**и щелкните **Диспетчер конфигурации SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-159">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="cfcc2-160">В диалоговом окне **Контроль учетных записей** нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-160">If the **User Account Control** dialog box appears, click **Yes**.</span></span>  
  
3.  <span data-ttu-id="cfcc2-161">На левой панели диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] щелкните **Службы SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-161">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the left pane, click **SQL Server Services**.</span></span>  
  
4.  <span data-ttu-id="cfcc2-162">На панели результатов щелкните правой кнопкой мыши **SQL Server (MSSQLServer)** или именованный экземпляр, затем выберите **Пуск**, **Остановка**, **Пауза**, **Продолжить**или **Перезапуск**.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-162">In the results pane, right-click **SQL Server (MSSQLServer)** or a named instance, and then click **Start**, **Stop**, **Pause**, **Resume**, or **Restart**.</span></span>  
  
5.  <span data-ttu-id="cfcc2-163">Нажмите кнопку **ОК** для выхода из диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cfcc2-163">Click **OK** to close [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cfcc2-164">Инструкции по запуску экземпляра [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] с параметрами запуска см. в статье [Настройка параметров запуска сервера (диспетчер конфигурации SQL Server)](scm-services-configure-server-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="cfcc2-164">To start an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] with startup options, see [Configure Server Startup Options &#40;SQL Server Configuration Manager&#41;](scm-services-configure-server-startup-options.md).</span></span>  
  
#### <a name="to-start-stop-pause-resume-or-restart-the-ssnoversion-browser-or-an-instance-of-the-ssnoversion-agent"></a><span data-ttu-id="cfcc2-165">Запуск, остановка, приостановка, возобновление или перезапуск браузера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или экземпляра агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfcc2-165">To start, stop, pause, resume, or restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser or an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span></span>  
  
1.  <span data-ttu-id="cfcc2-166">В меню **Пуск** последовательно выберите пункты **Все программы**, [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], **Средства настройки**и щелкните **Диспетчер конфигурации SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-166">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="cfcc2-167">В диалоговом окне **Контроль учетных записей** нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-167">If the **User Account Control** dialog box appears, click **Yes**.</span></span>  
  
3.  <span data-ttu-id="cfcc2-168">На левой панели диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] щелкните **Службы SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-168">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the left pane, click **SQL Server Services**.</span></span>  
  
4.  <span data-ttu-id="cfcc2-169">В области результатов щелкните правой кнопкой мыши \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] браузер**или \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] агент (MSSQLServer)** или \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] агент (<instance_name>)\*\* для именованного экземпляра, а затем выберите пункты **Пуск**, **остановить**, **приостановить**, **продолжить**или **перезапустить**.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-169">In the results pane, right-click **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser**, or **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent (MSSQLServer)** or **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent (<instance_name>)** for a named instance, and then click **Start**, **Stop**, **Pause**, **Resume**, or **Restart**.</span></span>  
  
5.  <span data-ttu-id="cfcc2-170">Нажмите кнопку **ОК** для выхода из диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cfcc2-170">Click **OK** to close [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="cfcc2-171">Агент приостановить нельзя.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-171">Agent cannot be paused.</span></span>  
  
##  <a name="using-ssnoversion-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="cfcc2-172">С помощью служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Studio</span><span class="sxs-lookup"><span data-stu-id="cfcc2-172">Using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Studio</span></span>  
  
#### <a name="to-start-stop-pause-resume-or-restart-the-an-instance-of-the-ssdenoversion"></a><span data-ttu-id="cfcc2-173">Запуск, остановка, приостановка, возобновление или перезапуск экземпляра [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfcc2-173">To start, stop, pause, resume, or restart the an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]</span></span>  
  
1.  <span data-ttu-id="cfcc2-174">В обозревателе объектов подключитесь к экземпляру [!INCLUDE[ssDE](../../includes/ssde-md.md)], щелкните правой кнопкой мыши экземпляр [!INCLUDE[ssDE](../../includes/ssde-md.md)] , который нужно запустить, и выберите **Пуск**, **Остановка**, **Пауза**, **Продолжить**или **Перезапустить**.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-174">In Object Explorer, connect to the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], right-click the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] you want to start, and then click **Start**, **Stop**, **Pause**, **Resume**, or **Restart**.</span></span>  
  
     <span data-ttu-id="cfcc2-175">Либо в разделе "Зарегистрированные серверы" щелкните правой кнопкой мыши экземпляр [!INCLUDE[ssDE](../../includes/ssde-md.md)] , который нужно запустить, наведите указатель на **Управление службами**и выберите **Пуск**, **Остановка**, **Пауза**, **Продолжить**или **Перезапустить**.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-175">Or, in Registered Servers, right-click the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] you want to start, point to **Service Control**, and then click **Start**, **Stop**, **Pause**, **Resume**, or **Restart**.</span></span>  
  
2.  <span data-ttu-id="cfcc2-176">В диалоговом окне **Контроль учетных записей** нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-176">If the **User Account Control** dialog box appears, click **Yes**.</span></span>  
  
3.  <span data-ttu-id="cfcc2-177">При появлении запроса о необходимости выполнения действия нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-177">When prompted if you want to perform the action, click **Yes**.</span></span>  
  
#### <a name="to-start-stop-or-restart-the-an-instance-of-the-ssnoversion-agent"></a><span data-ttu-id="cfcc2-178">Запуск, остановка или перезапуск экземпляра агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfcc2-178">To start, stop, or restart the an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span></span>  
  
1.  <span data-ttu-id="cfcc2-179">В обозревателе объектов подключитесь к экземпляру, щелкните [!INCLUDE[ssDE](../../includes/ssde-md.md)] правой кнопкой мыши \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Агент\*\*, а затем выберите **запустить**, **Закрыть**или **перезапустить**.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-179">In Object Explorer, connect to the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], right-click **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent**, and then click **Start**, **Stop**, or **Restart**.</span></span>  
  
2.  <span data-ttu-id="cfcc2-180">В диалоговом окне **Контроль учетных записей** нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-180">If the **User Account Control** dialog box appears, click **Yes**.</span></span>  
  
3.  <span data-ttu-id="cfcc2-181">При появлении запроса о необходимости выполнения действия нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-181">When prompted if you want to perform the action, click **Yes**.</span></span>  
  
##  <a name="from-the-command-prompt-window-using-net-commands"></a><a name="CommandPrompt"></a><span data-ttu-id="cfcc2-182">Из окна командной строки с помощью команд net</span><span class="sxs-lookup"><span data-stu-id="cfcc2-182">From the Command Prompt Window using net Commands</span></span>  
 <span data-ttu-id="cfcc2-183">Службы [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] можно запустить, остановить или приостановить с помощью команд **net**[!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-183">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services can be started, stopped, or paused by using [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows **net** commands.</span></span>  
  
###  <a name="to-start-the-default-instance-of-the-ssde"></a><a name="dbDefault"></a><span data-ttu-id="cfcc2-184">Запуск экземпляра по умолчанию[!INCLUDE[ssDE](../../includes/ssde-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfcc2-184">To start the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span></span>  
  
-   <span data-ttu-id="cfcc2-185">В командной строке введите одну из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="cfcc2-185">From a command prompt, enter one of the following commands:</span></span>  
  
     <span data-ttu-id="cfcc2-186">**net start "SQL Server (MSSQLSERVER)"**</span><span class="sxs-lookup"><span data-stu-id="cfcc2-186">**net start "SQL Server (MSSQLSERVER)"**</span></span>  
  
     <span data-ttu-id="cfcc2-187">-или-</span><span class="sxs-lookup"><span data-stu-id="cfcc2-187">-or-</span></span>  
  
     <span data-ttu-id="cfcc2-188">**net start MSSQLSERVER**</span><span class="sxs-lookup"><span data-stu-id="cfcc2-188">**net start MSSQLSERVER**</span></span>  
  
###  <a name="to-start-a-named-instance-of-the-ssde"></a><a name="dbNamed"></a> <span data-ttu-id="cfcc2-189">Запуск именованного экземпляра [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfcc2-189">To start a named instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span></span>  
  
-   <span data-ttu-id="cfcc2-190">В командной строке введите одну из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="cfcc2-190">From a command prompt, enter one of the following commands.</span></span> <span data-ttu-id="cfcc2-191">Замените *\<instancename>* именем экземпляра, которым необходимо управлять.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-191">Replace *\<instancename>* with the name of the instance you want to manage.</span></span>  
  
     <span data-ttu-id="cfcc2-192">**net start "SQL Server (** *имя_экземпляра* **)"**</span><span class="sxs-lookup"><span data-stu-id="cfcc2-192">**net start "SQL Server (** *instancename* **)"**</span></span>  
  
     <span data-ttu-id="cfcc2-193">-или-</span><span class="sxs-lookup"><span data-stu-id="cfcc2-193">-or-</span></span>  
  
     <span data-ttu-id="cfcc2-194">**net start MSSQL$** *имя_экземпляра*</span><span class="sxs-lookup"><span data-stu-id="cfcc2-194">**net start MSSQL$** *instancename*</span></span>  
  
###  <a name="to-start-the-ssde-with-startup-options"></a><a name="dbStartup"></a> <span data-ttu-id="cfcc2-195">Запуск [!INCLUDE[ssDE](../../includes/ssde-md.md)] с параметрами запуска</span><span class="sxs-lookup"><span data-stu-id="cfcc2-195">To start the [!INCLUDE[ssDE](../../includes/ssde-md.md)] with startup options</span></span>  
  
-   <span data-ttu-id="cfcc2-196">Укажите разделенные пробелами параметры запуска в конце команды **net start "SQL Server (MSSQLSERVER)"** .</span><span class="sxs-lookup"><span data-stu-id="cfcc2-196">Add startup options to the end of the **net start "SQL Server (MSSQLSERVER)"** statement, separated by a space.</span></span> <span data-ttu-id="cfcc2-197">При запуске с помощью команды **net start**в параметрах запуска используется косая черта (/), а не дефис (-).</span><span class="sxs-lookup"><span data-stu-id="cfcc2-197">When started using **net start**, startup options use a slash (/) instead of a hyphen (-).</span></span>  
  
     <span data-ttu-id="cfcc2-198">**net start "SQL Server (MSSQLSERVER)" /f /m**</span><span class="sxs-lookup"><span data-stu-id="cfcc2-198">**net start "SQL Server (MSSQLSERVER)" /f /m**</span></span>  
  
     <span data-ttu-id="cfcc2-199">-или-</span><span class="sxs-lookup"><span data-stu-id="cfcc2-199">-or-</span></span>  
  
     <span data-ttu-id="cfcc2-200">**net start MSSQLSERVER /f /m**</span><span class="sxs-lookup"><span data-stu-id="cfcc2-200">**net start MSSQLSERVER /f /m**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cfcc2-201">Дополнительные сведения о параметрах запуска см. в разделе [Параметры запуска службы Database Engine](database-engine-service-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="cfcc2-201">For more information about startup options, see [Database Engine Service Startup Options](database-engine-service-startup-options.md).</span></span>  
  
###  <a name="to-start-the-ssnoversion-agent-on-the-default-instance-of-ssnoversion"></a><a name="agDefault"></a> <span data-ttu-id="cfcc2-202">Запуск [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfcc2-202">To start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent on the default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="cfcc2-203">В командной строке введите одну из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="cfcc2-203">From a command prompt, enter one of the following commands:</span></span>  
  
     <span data-ttu-id="cfcc2-204">**net start "SQL Server Agent (MSSQLSERVER)"**</span><span class="sxs-lookup"><span data-stu-id="cfcc2-204">**net start "SQL Server Agent (MSSQLSERVER)"**</span></span>  
  
     <span data-ttu-id="cfcc2-205">-или-</span><span class="sxs-lookup"><span data-stu-id="cfcc2-205">-or-</span></span>  
  
     <span data-ttu-id="cfcc2-206">**net start SQLSERVERAGENT**</span><span class="sxs-lookup"><span data-stu-id="cfcc2-206">**net start SQLSERVERAGENT**</span></span>  
  
###  <a name="to-start-the-ssnoversion-agent-on-a-named-instance-of-ssnoversion"></a><a name="agNamed"></a> <span data-ttu-id="cfcc2-207">Перезапуск агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на именованном экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfcc2-207">To start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent on a named instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="cfcc2-208">В командной строке введите одну из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="cfcc2-208">From a command prompt, enter one of the following commands.</span></span> <span data-ttu-id="cfcc2-209">Замените *имя_экземпляра* именем экземпляра, которым необходимо управлять.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-209">Replace *instancename* with the name of the instance you want to manage.</span></span>  
  
     <span data-ttu-id="cfcc2-210">**net start "SQL Server Agent(** *имя_экземпляра* **)"**</span><span class="sxs-lookup"><span data-stu-id="cfcc2-210">**net start "SQL Server Agent(** *instancename* **)"**</span></span>  
  
     <span data-ttu-id="cfcc2-211">-или-</span><span class="sxs-lookup"><span data-stu-id="cfcc2-211">-or-</span></span>  
  
     <span data-ttu-id="cfcc2-212">**net start SQLAgent$** *имя_экземпляра*</span><span class="sxs-lookup"><span data-stu-id="cfcc2-212">**net start SQLAgent$** *instancename*</span></span>  
  
 <span data-ttu-id="cfcc2-213">Сведения о запуске агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в подробном режиме для устранения неполадок см. в статье [sqlagent90 Application](../../tools/sqlagent90-application.md).</span><span class="sxs-lookup"><span data-stu-id="cfcc2-213">For information about how to run [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in verbose mode for troubleshooting, see [sqlagent90 Application](../../tools/sqlagent90-application.md).</span></span>  
  
###  <a name="to-start-the-ssnoversion-browser"></a><a name="Browser"></a> <span data-ttu-id="cfcc2-214">Запуск браузера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfcc2-214">To start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser</span></span>  
  
-   <span data-ttu-id="cfcc2-215">В командной строке введите одну из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="cfcc2-215">From a command prompt, enter one of the following commands:</span></span>  
  
     <span data-ttu-id="cfcc2-216">**net start "SQL Server Browser"**</span><span class="sxs-lookup"><span data-stu-id="cfcc2-216">**net start "SQL Server Browser"**</span></span>  
  
     <span data-ttu-id="cfcc2-217">-или-</span><span class="sxs-lookup"><span data-stu-id="cfcc2-217">-or-</span></span>  
  
     <span data-ttu-id="cfcc2-218">**net start SQLBrowser**</span><span class="sxs-lookup"><span data-stu-id="cfcc2-218">**net start SQLBrowser**</span></span>  
  
###  <a name="to-pause-or-stop-services-from-the-command-prompt-window"></a><a name="pauseStop"></a> <span data-ttu-id="cfcc2-219">Приостановка или остановка служб из окна командной строки</span><span class="sxs-lookup"><span data-stu-id="cfcc2-219">To pause or stop services from the Command Prompt window</span></span>  
  
-   <span data-ttu-id="cfcc2-220">Чтобы приостановить или остановить службы, измените команды следующими способами.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-220">To pause or stop services modify the commands in the following ways.</span></span>  
  
    -   <span data-ttu-id="cfcc2-221">Чтобы приостановить службу, вместо **net start** введите **net pause**.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-221">To pause a service, replace **net start** with **net pause**.</span></span>  
  
    -   <span data-ttu-id="cfcc2-222">Чтобы остановить службу, вместо **net start** введите **net stop**.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-222">To stop a service, replace **net start** with use **net stop**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="cfcc2-223">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cfcc2-223">Using Transact-SQL</span></span>  
 <span data-ttu-id="cfcc2-224">[!INCLUDE[ssDE](../../includes/ssde-md.md)] можно остановить с помощью инструкции `SHUTDOWN`.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-224">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] can be stopped by using the `SHUTDOWN` statement.</span></span>  
  
#### <a name="to-stop-the-ssde-using-tsql"></a><span data-ttu-id="cfcc2-225">Остановка [!INCLUDE[ssDE](../../includes/ssde-md.md)] с помощью [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfcc2-225">To stop the [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  
-   <span data-ttu-id="cfcc2-226">Чтобы дождаться завершения запущенных в настоящий момент инструкций и хранимых процедур [!INCLUDE[tsql](../../includes/tsql-md.md)] с последующей остановкой [!INCLUDE[ssDE](../../includes/ssde-md.md)], выполните следующую инструкцию.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-226">To wait for currently running [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and stored procedures to finish, and then stop the [!INCLUDE[ssDE](../../includes/ssde-md.md)], execute the following statement.</span></span>  
  
    ```sql  
    SHUTDOWN;   
    ```  
  
-   <span data-ttu-id="cfcc2-227">Чтобы остановить [!INCLUDE[ssDE](../../includes/ssde-md.md)] немедленно, выполните следующую инструкцию.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-227">To stop the [!INCLUDE[ssDE](../../includes/ssde-md.md)] immediately, execute the following statement.</span></span>  
  
    ```sql  
    SHUTDOWN WITH NOWAIT;   
    ```  
  
 <span data-ttu-id="cfcc2-228">Дополнительные сведения об `SHUTDOWN` инструкции см. в разделе [Shutdown &#40;TRANSACT-SQL&#41;](/sql/t-sql/language-elements/shutdown-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cfcc2-228">For more information about the `SHUTDOWN` statement, see [SHUTDOWN &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/shutdown-transact-sql).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="cfcc2-229">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="cfcc2-229">Using PowerShell</span></span>  
  
#### <a name="to-start-and-stop-ssde-services"></a><span data-ttu-id="cfcc2-230">Запуск и остановка служб [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfcc2-230">To start and stop [!INCLUDE[ssDE](../../includes/ssde-md.md)] services</span></span>  
  
1.  <span data-ttu-id="cfcc2-231">В окне командной строки запустите [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-231">In a Command Prompt window, start [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell by executing the following command.</span></span>  
  
    ```ms-dos  
    sqlps  
    ```  
  
2.  <span data-ttu-id="cfcc2-232">В окне командной строки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell путем выполнения следующей команды.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-232">At a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell command prompt, by executing the following command.</span></span> <span data-ttu-id="cfcc2-233">Замените `computername` именем нужного компьютера.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-233">Replace `computername` with the name of your computer.</span></span>  
  
    ```powershell  
    # Get a reference to the ManagedComputer class.  
    CD SQLSERVER:\SQL\computername  
    $Wmi = (Get-Item .).ManagedComputer
    ```  
  
3.  <span data-ttu-id="cfcc2-234">Определите службу, которую нужно остановить или запустить.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-234">Identify the service that you want to stop or start.</span></span> <span data-ttu-id="cfcc2-235">Выберите одну из следующих строк.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-235">Pick one of the following lines.</span></span> <span data-ttu-id="cfcc2-236">Замените `instancename` именем именованного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-236">Replace `instancename` with the name of the named instance.</span></span>  
  
    -   <span data-ttu-id="cfcc2-237">Получение ссылки на экземпляр [!INCLUDE[ssDE](../../includes/ssde-md.md)]по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-237">To get a reference to the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
        ```powershell  
        $DfltInstance = $Wmi.Services['MSSQLSERVER']  
        ```  
  
    -   <span data-ttu-id="cfcc2-238">Получение ссылки на именованный экземпляр [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cfcc2-238">To get a reference to a named instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
        ```powershell  
        $DfltInstance = $Wmi.Services['MSSQL$instancename']  
        ```  
  
    -   <span data-ttu-id="cfcc2-239">Получение ссылки на службу агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на экземпляре [!INCLUDE[ssDE](../../includes/ssde-md.md)]по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-239">To get a reference to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service on the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
        ```powershell  
        $DfltInstance = $Wmi.Services['SQLSERVERAGENT']  
        ```  
  
    -   <span data-ttu-id="cfcc2-240">Получение ссылки на службу агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на именованном экземпляре [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cfcc2-240">To get a reference to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service on a named instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
        ```powershell  
        $DfltInstance = $Wmi.Services['SQLAGENT$instancename']  
        ```  
  
    -   <span data-ttu-id="cfcc2-241">Получение ссылки на службу браузера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cfcc2-241">To get a reference to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
        ```powershell  
        $DfltInstance = $Wmi.Services['SQLBROWSER']  
        ```  
  
4.  <span data-ttu-id="cfcc2-242">Завершите пример, чтобы запустить и затем остановить выбранную службу.</span><span class="sxs-lookup"><span data-stu-id="cfcc2-242">Complete the example to start and then stop the selected service.</span></span>  
  
    ```powershell  
    # Display the state of the service.  
    $DfltInstance  
    # Start the service.  
    $DfltInstance.Start();  
    # Wait until the service has time to start.  
    # Refresh the cache.  
    $DfltInstance.Refresh();   
    # Display the state of the service.  
    $DfltInstance  
    # Stop the service.  
    $DfltInstance.Stop();  
    # Wait until the service has time to stop.  
    # Refresh the cache.  
    $DfltInstance.Refresh();   
    # Display the state of the service.  
    $DfltInstance  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="cfcc2-243">См. также:</span><span class="sxs-lookup"><span data-stu-id="cfcc2-243">See Also</span></span>  
 <span data-ttu-id="cfcc2-244">[Запуск SQL Server с минимальной конфигурацией](start-sql-server-with-minimal-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="cfcc2-244">[Start SQL Server with Minimal Configuration](start-sql-server-with-minimal-configuration.md) </span></span>  
 [<span data-ttu-id="cfcc2-245">Возможности, поддерживаемые различными выпусками SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="cfcc2-245">Features Supported by the Editions of SQL Server 2014</span></span>](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
