---
title: Использование поставщика PowerShell для расширенных событий | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- PowerShell [SQL Server], xevent
- extended events [SQL Server], PowerShell
- PowerShell [SQL Server], extended events
ms.assetid: 0b10016f-a479-4444-a484-46cb4677cf64
author: rothja
ms.author: jroth
ms.openlocfilehash: a9efbd389545dcde8285a38b06f41580fb65de6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665339"
---
# <a name="use-the-powershell-provider-for-extended-events"></a><span data-ttu-id="7f20e-102">Использование поставщика PowerShell для расширенных событий</span><span class="sxs-lookup"><span data-stu-id="7f20e-102">Use the PowerShell Provider for Extended Events</span></span>
  <span data-ttu-id="7f20e-103">Управлять расширенными событиями [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] можно с помощью поставщика [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7f20e-103">You can manage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Extended Events by using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell provider.</span></span> <span data-ttu-id="7f20e-104">Вложенная папка XEvent находится на диске SQLSERVER.</span><span class="sxs-lookup"><span data-stu-id="7f20e-104">The XEvent subfolder is available under the SQLSERVER drive.</span></span> <span data-ttu-id="7f20e-105">Получить доступ к папке можно одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="7f20e-105">You can access the folder by using either of the following methods:</span></span>  
  
-   <span data-ttu-id="7f20e-106">В командной строке введите команду `sqlps` и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="7f20e-106">At a command prompt, type `sqlps`, and then press ENTER.</span></span> <span data-ttu-id="7f20e-107">Введите `cd xevent` и нажмите ВВОД.</span><span class="sxs-lookup"><span data-stu-id="7f20e-107">Type `cd xevent`, and then press ENTER.</span></span> <span data-ttu-id="7f20e-108">В нем можно использовать **компакт-диск** и `dir` команды (или командлеты **Set-Location** и **Get-ChildItem** ) для перехода по имени сервера и имени экземпляра.</span><span class="sxs-lookup"><span data-stu-id="7f20e-108">From there, you can use the **cd** and `dir` commands (or **Set-Location** and **Get-Childitem** cmdlets) to navigate to the server name and instance name.</span></span>  
  
-   <span data-ttu-id="7f20e-109">В обозревателе объектов разверните узел имени экземпляра, разверните узел **Управление**, щелкните правой кнопкой мыши **Расширенные события**и выберите команду **Запустить PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="7f20e-109">In Object Explorer, expand the instance name, expand **Management**, right-click **Extended Events**, and then click **Start PowerShell**.</span></span> <span data-ttu-id="7f20e-110">Оболочка PowerShell будет запущена в следующем пути:</span><span class="sxs-lookup"><span data-stu-id="7f20e-110">This starts PowerShell in the following path:</span></span>  
  
     <span data-ttu-id="7f20e-111">PS SQLServer: \ XEvent \\ *ServerName* \\ *имя_экземпляра*></span><span class="sxs-lookup"><span data-stu-id="7f20e-111">PS SQLSERVER:\XEvent\\*ServerName*\\*InstanceName*></span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7f20e-112">Запустить PowerShell можно из любого узла в категории **Расширенные события**.</span><span class="sxs-lookup"><span data-stu-id="7f20e-112">You can start PowerShell from any node under **Extended Events**.</span></span> <span data-ttu-id="7f20e-113">Например, можно щелкнуть правой кнопкой мыши **Сеансы**, а затем выбрать команду **Запустить PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="7f20e-113">For example, you can right-click **Sessions**, and then click **Start PowerShell**.</span></span> <span data-ttu-id="7f20e-114">При этом оболочка PowerShell будет запущена на один уровень ниже, в папке «Сеансы».</span><span class="sxs-lookup"><span data-stu-id="7f20e-114">This starts PowerShell one level deeper, at the Sessions folder.</span></span>  
  
 <span data-ttu-id="7f20e-115">В дереве папки XEvent можно просматривать существующие сеансы расширенных событий и связанные с ними события, цели и предикаты.</span><span class="sxs-lookup"><span data-stu-id="7f20e-115">You can browse the XEvent folder tree to view existing Extended Events sessions and their associated events, targets and predicates.</span></span> <span data-ttu-id="7f20e-116">Например, если в строке PS SQLServer: \ XEvent \\ *имя_сервера* \\ *имя_экземпляра*> путь, введите `cd sessions` , нажмите клавишу ВВОД, введите `dir` , а затем нажмите клавишу ВВОД, вы увидите список сеансов, хранящихся в этом экземпляре.</span><span class="sxs-lookup"><span data-stu-id="7f20e-116">For example, from the PS SQLSERVER:\XEvent\\*ServerName*\\*InstanceName*> path, if you type `cd sessions`, press ENTER, type `dir`, and then press ENTER, you can see the list of sessions that are stored on that instance.</span></span> <span data-ttu-id="7f20e-117">Также можно проверить, выполняется ли сеанс в данный момент (и если выполняется, то в течение какого периода), а также задан ли запуск сеанса вместе с запуском экземпляра.</span><span class="sxs-lookup"><span data-stu-id="7f20e-117">You can also view whether the session is running (and if this is the case, for how long), and whether the session is configured to start when the instance starts.</span></span>  
  
 <span data-ttu-id="7f20e-118">Для просмотра событий, их предикатов и целей, связанных с сеансом, можно изменить имена каталогов на имя сеанса и затем просматривать либо папку событий, либо папку целей.</span><span class="sxs-lookup"><span data-stu-id="7f20e-118">To view the events, their predictates, and the targets that are associated with a session, you can change directories to the session name, and then view either the events or targets folder.</span></span> <span data-ttu-id="7f20e-119">Например, чтобы просмотреть события и их предикаты, связанные с сеансом исправности системы по умолчанию, введите в поле PS SQLServer: \ XEvent \\ *имя_сервера* \\ *имя_экземпляра*\сессионс> путь, `cd system_health\events,` нажмите клавишу ВВОД, введите `dir` , а затем нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="7f20e-119">For example, to view the events and their predicates that are associated with the default system health session, from the PS SQLSERVER:\XEvent\\*ServerName*\\*InstanceName*\Sessions> path, type `cd system_health\events,` press ENTER, type `dir`, and then press ENTER.</span></span>  
  
 <span data-ttu-id="7f20e-120">Поставщик [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell предоставляет широкий набор функций для создания, изменения сеансов расширенных событий и управления ими.</span><span class="sxs-lookup"><span data-stu-id="7f20e-120">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell provider is a powerful tool that you can use to create, alter, and manage Extended Events sessions.</span></span> <span data-ttu-id="7f20e-121">В следующем разделе приведены некоторые простые примеры использования скриптов PowerShell с расширенными событиями.</span><span class="sxs-lookup"><span data-stu-id="7f20e-121">The following section provides some basic examples of using PowerShell scripts with Extended Events.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="7f20e-122">Примеры</span><span class="sxs-lookup"><span data-stu-id="7f20e-122">Examples</span></span>  
 <span data-ttu-id="7f20e-123">В приведенных далее примерах обратите внимание на следующие моменты.</span><span class="sxs-lookup"><span data-stu-id="7f20e-123">In the following examples, note the following:</span></span>  
  
-   <span data-ttu-id="7f20e-124">Скрипты должны запускаться из командной строки PS SQLSERVER: \\> (доступного при вводе `sqlps` в командной строке).</span><span class="sxs-lookup"><span data-stu-id="7f20e-124">The scripts must be run from the PS SQLSERVER:\\> prompt (available by typing `sqlps` at a command prompt).</span></span>  
  
-   <span data-ttu-id="7f20e-125">Скрипты используют экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7f20e-125">The scripts use the default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="7f20e-126">Скрипты должны сохраняться с расширением PS1.</span><span class="sxs-lookup"><span data-stu-id="7f20e-126">The scripts must be saved with a .ps1 extension.</span></span>  
  
-   <span data-ttu-id="7f20e-127">Политика выполнения PowerShell должна разрешать выполнения скриптов.</span><span class="sxs-lookup"><span data-stu-id="7f20e-127">The PowerShell execution policy must allow the script to run.</span></span> <span data-ttu-id="7f20e-128">Чтобы задать политику выполнения, воспользуйтесь командлетом **Set-Executionpolicy** .</span><span class="sxs-lookup"><span data-stu-id="7f20e-128">To set the execution policy, use the **Set-Executionpolicy** cmdlet.</span></span> <span data-ttu-id="7f20e-129">(Для получения дополнительных сведений введите `get-help set-executionpolicy -detailed` и нажмите клавишу ВВОД.)</span><span class="sxs-lookup"><span data-stu-id="7f20e-129">(For more information, type `get-help set-executionpolicy -detailed`, and then press ENTER.)</span></span>  
  
 <span data-ttu-id="7f20e-130">Следующий скрипт создает новый сеанс с именем «TestSession».</span><span class="sxs-lookup"><span data-stu-id="7f20e-130">The following script creates a new session that is named 'TestSession'.</span></span>  
  
```powershell
#Script for creating a session.  
cd XEvent  
$h = hostname  
cd $h  
  
#Use the default instance.  
$store = dir | where {$_.DisplayName -ieq 'default'}  
$session = New-Object Microsoft.SqlServer.Management.XEvent.Session -ArgumentList $store, "TestSession"  
$event = $session.AddEvent("sqlserver.file_written")  
$event.AddAction("package0.callstack")  
$session.Create()  
```  
  
 <span data-ttu-id="7f20e-131">Следующий скрипт добавляет цель «Кольцевой буфер» в сеанс, созданный в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="7f20e-131">The following script adds the ring buffer target to the session that was created in the previous example.</span></span> <span data-ttu-id="7f20e-132">(В этом примере демонстрируется использование метода `Alter`.</span><span class="sxs-lookup"><span data-stu-id="7f20e-132">(This example shows the use of the `Alter` method.</span></span> <span data-ttu-id="7f20e-133">Помните, что добавлять цель можно только после создания сеанса.)</span><span class="sxs-lookup"><span data-stu-id="7f20e-133">Be aware that you can add the target when you first create the session.)</span></span>  
  
```powershell
#Script to alter a session.  
cd XEvent  
$h = hostname  
cd $h  
cd DEFAULT\Sessions  
  
#Used to find the specified session.  
$session = dir | where {$_.Name -eq 'TestSession'}  
  
#Add the ring buffer target and call the Alter method.  
$session.AddTarget("package0.ring_buffer")  
$session.Alter()  
```  
  
 <span data-ttu-id="7f20e-134">Следующий скрипт создает новый сеанс, в котором используется выражение предиката.</span><span class="sxs-lookup"><span data-stu-id="7f20e-134">The following script creates a new session that uses a predicate expression.</span></span> <span data-ttu-id="7f20e-135">В данном случае сеанс собирает сведения о времени записи в файл c:\temp.log (с помощью события sqlserver.file_written).</span><span class="sxs-lookup"><span data-stu-id="7f20e-135">In this case, the session collects information for when the c:\temp.log file is written to (through the sqlserver.file_written event).</span></span>  
  
```powershell
#Script for creating a session.  
cd XEvent  
$h = hostname  
cd $h  
  
#Use the default instance.  
$store = dir | where {$_.DisplayName -ieq 'default'}  
$session = New-Object Microsoft.SqlServer.Management.XEvent.Session -ArgumentList $store, "TestSession2"  
$event = $session.AddEvent("sqlserver.file_written")  
  
#Construct a predicate "equal_i_unicode_string(path, N'c:\temp.log')".  
$column = $store.SqlServerPackage.EventInfoSet["file_written"].DataEventColumnInfoSet["path"]  
$operand = new-object Microsoft.SqlServer.Management.XEvent.PredOperand -argumentlist $column  
$value = new-object Microsoft.SqlServer.Management.XEvent.PredValue -argumentlist "c:\temp.log"  
$compare = $store.Package0Package.PredCompareInfoSet["equal_i_unicode_string"]  
$predicate = new-object Microsoft.SqlServer.Management.XEvent.PredFunctionExpr -ArgumentList $compare, $operand, $value  
$event.SetPredicate($predicate)  
$session.Create()  
```  
  
## <a name="security"></a><span data-ttu-id="7f20e-136">Безопасность</span><span class="sxs-lookup"><span data-stu-id="7f20e-136">Security</span></span>  
 <span data-ttu-id="7f20e-137">Чтобы создать, изменить или удалить сеанс расширенных событий, требуется разрешение ALTER ANY EVENT SESSION.</span><span class="sxs-lookup"><span data-stu-id="7f20e-137">To create, alter, or drop an Extended Events session, you must have the ALTER ANY EVENT SESSION permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f20e-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="7f20e-138">See Also</span></span>  
 <span data-ttu-id="7f20e-139">[SQL Server PowerShell](../../powershell/sql-server-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="7f20e-139">[SQL Server PowerShell](../../powershell/sql-server-powershell.md) </span></span>  
 <span data-ttu-id="7f20e-140">[Использование сеанса system_health](use-the-ssms-xe-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="7f20e-140">[Use the system_health Session](use-the-ssms-xe-profiler.md) </span></span>  
 [<span data-ttu-id="7f20e-141">Средства расширенных событий</span><span class="sxs-lookup"><span data-stu-id="7f20e-141">Extended Events Tools</span></span>](extended-events-tools.md)  
