---
title: Добавление поддержки отладки в пользовательскую задачу | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- BreakpointManager class
- breakpoints [Integration Services]
- custom tasks [Integration Services], debugging
- IDTSSuspend interface
- IDTSBreakpointSite interface
- SSIS custom tasks, debugging
- debugging [Integration Services], custom tasks
ms.assetid: 7f06e49b-0b60-4e81-97da-d32dc248264a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fcc1d0c18cd559b547eadb9c1fa77e8f143389d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665446"
---
# <a name="adding-support-for-debugging-in-a-custom-task"></a><span data-ttu-id="7a687-102">Добавление поддержки отладки в пользовательскую задачу</span><span class="sxs-lookup"><span data-stu-id="7a687-102">Adding Support for Debugging in a Custom Task</span></span>
  <span data-ttu-id="7a687-103">Обработчик среды выполнения служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] дает возможность приостанавливать пакеты, задачи и другие типы контейнеров во время выполнения при помощи точек останова.</span><span class="sxs-lookup"><span data-stu-id="7a687-103">The [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] run-time engine enables packages, tasks, and other types of containers to be suspended during execution by using breakpoints.</span></span> <span data-ttu-id="7a687-104">Использование точек останова позволяет просматривать и исправлять ошибки, мешающие правильной работе приложения или задач.</span><span class="sxs-lookup"><span data-stu-id="7a687-104">The use of breakpoints lets you review and correct errors that prevent your application or tasks from running correctly.</span></span> <span data-ttu-id="7a687-105">Архитектура точек останова позволяет оценивать во время выполнения значения объектов в пакете в определенных точках выполнения при приостановке обработки задачи.</span><span class="sxs-lookup"><span data-stu-id="7a687-105">The breakpoint architecture enables the client to evaluate the run-time value of objects in the package at defined points of execution while task processing is suspended.</span></span>  
  
 <span data-ttu-id="7a687-106">Разработчики пользовательских задач могут использовать эту архитектуру для создания целевых объектов пользовательских точек останова с помощью интерфейса <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> и его родительского интерфейса <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend>.</span><span class="sxs-lookup"><span data-stu-id="7a687-106">Custom task developers can use this architecture to create custom breakpoint targets by using the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> interface, and its parent interface, <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend>.</span></span> <span data-ttu-id="7a687-107">Интерфейс <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> определяет взаимодействие между обработчиком среды выполнения и задачей для создания сайтов или целевых объектов пользовательских точек останова и управления этими сайтами и объектами.</span><span class="sxs-lookup"><span data-stu-id="7a687-107">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> interface defines the interaction between the run-time engine and the task for creating and managing custom breakpoint sites or targets.</span></span> <span data-ttu-id="7a687-108">Интерфейс <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> предоставляет методы и свойства, вызываемые обработчиком среды выполнения для уведомления задачи о приостановке или возобновлении ее обработки.</span><span class="sxs-lookup"><span data-stu-id="7a687-108">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> interface provides methods and properties that are called by the run-time engine to notify the task to suspend or resume its execution.</span></span>  
  
 <span data-ttu-id="7a687-109">Сайтом или целевым объектом точки останова является точка в выполнении задачи, где обработка может быть приостановлена.</span><span class="sxs-lookup"><span data-stu-id="7a687-109">A breakpoint site or target is a point in the execution of the task where processing can be suspended.</span></span> <span data-ttu-id="7a687-110">Пользователи выбирают из доступных сайтов точек останова с помощью диалогового окна **Задание точек останова**.</span><span class="sxs-lookup"><span data-stu-id="7a687-110">Users select from available breakpoint sites in the **Set Breakpoints** dialog box.</span></span> <span data-ttu-id="7a687-111">Например, дополнительно к параметрам точек останова по умолчанию контейнер «цикл по каждому элементу» предлагает параметр «Прервать в начале каждого повторения цикла».</span><span class="sxs-lookup"><span data-stu-id="7a687-111">For example, in addition to the default breakpoint options, the Foreach Loop Container offers the "Break at the beginning of every iteration of the loop" option.</span></span>  
  
 <span data-ttu-id="7a687-112">Когда во время выполнения задача достигает целевого объекта точки останова, она оценивает целевой объект точки останова для определения, включена ли точка останова.</span><span class="sxs-lookup"><span data-stu-id="7a687-112">When a task reaches a breakpoint target during execution, it evaluates the breakpoint target to determine whether a breakpoint is enabled.</span></span> <span data-ttu-id="7a687-113">Включение указывает на то, что пользователь хочет остановить выполнение в этой точке останова.</span><span class="sxs-lookup"><span data-stu-id="7a687-113">This indicates that the user wants execution to stop at that breakpoint.</span></span> <span data-ttu-id="7a687-114">Если точка останова включена, задача инициирует событие <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A> для обработчика среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="7a687-114">If the breakpoint is enabled, the task raises the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A> event to the run-time engine.</span></span> <span data-ttu-id="7a687-115">Обработчик среды выполнения реагирует на событие вызовом метода `Suspend` каждой задачи, которая выполняется в настоящее время в пакете.</span><span class="sxs-lookup"><span data-stu-id="7a687-115">The run-time engine responds to the event by calling the `Suspend` method of each task that is currently running in the package.</span></span> <span data-ttu-id="7a687-116">Выполнение задачи возобновляется, когда среда выполнения вызывает метод `ResumeExecution` приостановленной задачи.</span><span class="sxs-lookup"><span data-stu-id="7a687-116">Execution of the task resumes when the runtime calls the `ResumeExecution` method of the suspended task.</span></span>  
  
 <span data-ttu-id="7a687-117">Задачи, не использующие точек останова, должны тем не менее реализовывать интерфейсы <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> и <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend>.</span><span class="sxs-lookup"><span data-stu-id="7a687-117">Tasks that do not use breakpoints should still implement the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> and <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> interfaces.</span></span> <span data-ttu-id="7a687-118">Это гарантирует, что задача правильно приостановится, если другие объекты в пакете инициируют события <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A>.</span><span class="sxs-lookup"><span data-stu-id="7a687-118">This ensures that the task is suspended correctly when other objects in the package raise <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A> events.</span></span>  
  
## <a name="idtsbreakpointsite-interface-and-breakpointmanager"></a><span data-ttu-id="7a687-119">Интерфейс IDTSBreakpointSite и класс BreakpointManager</span><span class="sxs-lookup"><span data-stu-id="7a687-119">IDTSBreakpointSite Interface and BreakpointManager</span></span>  
 <span data-ttu-id="7a687-120">Задачи создают целевые объекты точек останова, вызывая метод <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager.CreateBreakpointTarget%2A> класса <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager>, предоставляя целочисленный идентификатор и строковое описание как параметры.</span><span class="sxs-lookup"><span data-stu-id="7a687-120">Tasks create breakpoint targets by calling the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager.CreateBreakpointTarget%2A> method of the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager>, providing an integer ID and string description as parameters.</span></span> <span data-ttu-id="7a687-121">Когда задача достигает точки в коде, которая содержит целевой объект точки останова, она оценивает целевой объект при помощи метода <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager.IsBreakpointTargetEnabled%2A>, чтобы определить, включена ли точка останова.</span><span class="sxs-lookup"><span data-stu-id="7a687-121">When the task reaches the point in its code that contains a breakpoint target, it evaluates the breakpoint target by using the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager.IsBreakpointTargetEnabled%2A> method to determine whether that breakpoint is enabled.</span></span> <span data-ttu-id="7a687-122">Если возвращается значение `true`, задача уведомляет обработчик среды выполнения, инициируя событие <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A>.</span><span class="sxs-lookup"><span data-stu-id="7a687-122">If `true`, the task notifies the run-time engine by raising the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A> event.</span></span>  
  
 <span data-ttu-id="7a687-123">Интерфейс <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> определяет единственный метод <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite.AcceptBreakpointManager%2A>, который вызывается обработчиком среды выполнения во время создания задачи.</span><span class="sxs-lookup"><span data-stu-id="7a687-123">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> interface defines a single method, <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite.AcceptBreakpointManager%2A>, which is called by the run-time engine during task creation.</span></span> <span data-ttu-id="7a687-124">Этот метод предоставляет в качестве параметра объект <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager>, который далее используется задачей для создания точек останова и управления ими.</span><span class="sxs-lookup"><span data-stu-id="7a687-124">This method provides as a parameter the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager> object, which is then used by the task to create and manage its breakpoints.</span></span> <span data-ttu-id="7a687-125">Задачи должны хранить объект <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager> локально для использования во время выполнения методов `Validate` и `Execute`.</span><span class="sxs-lookup"><span data-stu-id="7a687-125">Tasks should store the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager> locally for use during the `Validate` and `Execute` methods.</span></span>  
  
 <span data-ttu-id="7a687-126">В следующем образце кода демонстрируется создание целевого объекта точки останова <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager>.</span><span class="sxs-lookup"><span data-stu-id="7a687-126">The following sample code demonstrates how to create a breakpoint target by using the <xref:Microsoft.SqlServer.Dts.Runtime.BreakpointManager>.</span></span> <span data-ttu-id="7a687-127">В образце для инициирования события вызывается метод <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A>.</span><span class="sxs-lookup"><span data-stu-id="7a687-127">The sample calls the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnBreakpointHit%2A> method to raise the event.</span></span>  
  
```csharp  
public void AcceptBreakpointManager( BreakpointManager breakPointManager )  
{  
   //   Store the breakpoint manager locally.  
   this.bpm  = breakPointManager;  
}  
public override DTSExecResult Execute( Connections connections,  
  Variables variables, IDTSComponentEvents events,  
  IDTSLogging log, DtsTransaction txn)  
{  
   //   Create a breakpoint.  
   this.bpm.CreateBreakPointTarget( 1 , "A sample breakpoint target." );  
...  
   if( this.bpm.IsBreakpointTargetEnabled( 1 ) == true )  
      events.OnBreakpointHit( this.bpm.GetBreakpointTarget( 1 ) );  
}  
```  
  
```vb  
Public Sub AcceptBreakpointManager(ByVal breakPointManager As BreakpointManager)  
  
   ' Store the breakpoint manager locally.  
   Me.bpm  = breakPointManager  
  
End Sub  
  
Public Overrides Function Execute(ByVal connections As Connections, _  
  ByVal variables As Variables, ByVal events As IDTSComponentEvents, _  
  ByVal log As IDTSLogging, ByVal txn As DtsTransaction) As DTSExecResult  
  
   ' Create a breakpoint.  
   Me.bpm.CreateBreakPointTarget(1 , "A sample breakpoint target.")  
  
   If Me.bpm.IsBreakpointTargetEnabled(1) = True Then  
      events.OnBreakpointHit(Me.bpm.GetBreakpointTarget(1))  
   End If  
  
End Function  
```  
  
## <a name="idtssuspend-interface"></a><span data-ttu-id="7a687-128">Интерфейс IDTSSuspend</span><span class="sxs-lookup"><span data-stu-id="7a687-128">IDTSSuspend Interface</span></span>  
 <span data-ttu-id="7a687-129">Интерфейс <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> определяет методы, вызываемые обработчиком среды выполнения, когда он приостанавливает или возобновляет выполнение задачи.</span><span class="sxs-lookup"><span data-stu-id="7a687-129">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> interface defines the methods that are called by the run-time engine when it pauses or resumes execution of a task.</span></span> <span data-ttu-id="7a687-130">Интерфейс <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> реализован интерфейсом <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> и его методы `Suspend` и `ResumeExecution` обычно переопределяются пользовательской задачей.</span><span class="sxs-lookup"><span data-stu-id="7a687-130">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSuspend> interface is implemented by the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSBreakpointSite> interface, and its `Suspend` and `ResumeExecution` methods are usually overridden by the custom task.</span></span> <span data-ttu-id="7a687-131">Если обработчик среды выполнения получает от задачи событие `OnBreakpointHit`, он вызывает метод `Suspend` каждой выполняемой задачи, уведомляя задачи о приостановке.</span><span class="sxs-lookup"><span data-stu-id="7a687-131">When the run-time engine receives an `OnBreakpointHit` event from a task, it calls the `Suspend` method of each running task, notifying the tasks to pause.</span></span> <span data-ttu-id="7a687-132">Когда клиент возобновляет выполнение, обработчик среды выполнения вызывает метод `ResumeExecution` приостановленных задач.</span><span class="sxs-lookup"><span data-stu-id="7a687-132">When the client resumes execution, the run-time engine calls the `ResumeExecution` method of the tasks that are suspended.</span></span>  
  
 <span data-ttu-id="7a687-133">Приостановка и возобновление выполнения задачи подразумевают приостановку и возобновление потока выполнения задачи.</span><span class="sxs-lookup"><span data-stu-id="7a687-133">Suspending and resuming task execution involves pausing and resuming the task's execution thread.</span></span> <span data-ttu-id="7a687-134">В управляемом коде это выполняется с помощью класса `ManualResetEvent` в пространстве имен `System.Threading` платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7a687-134">In managed code, you do this using the `ManualResetEvent` class in `System.Threading` namespace of the .NET Framework.</span></span>  
  
 <span data-ttu-id="7a687-135">В следующем образце кода демонстрируется приостановка и возобновление выполнения задачи.</span><span class="sxs-lookup"><span data-stu-id="7a687-135">The following code sample demonstrates suspension and resumption of task execution.</span></span> <span data-ttu-id="7a687-136">Обратите внимание, что метод `Execute` изменен по сравнению с предыдущим примером образца кода и поток выполнения приостанавливается при срабатывании точки останова.</span><span class="sxs-lookup"><span data-stu-id="7a687-136">Notice that the `Execute` method has changed from the previous code sample, and the execution thread is paused when firing the breakpoint.</span></span>  
  
```csharp  
private ManualResetEvent m_suspended = new ManualResetEvent( true );  
private ManualResetEvent m_canExecute = new ManualResetEvent( true );  
private int   m_suspendRequired = 0;  
private int   m_debugMode = 0;  
  
public override DTSExecResult Execute( Connections connections, Variables variables, IDTSComponentEvents events, IDTSLogging log, DtsTransaction txn)  
{  
   // While a task is not executing, it is suspended.    
   // Now that we are executing,  
   // change to not suspended.  
   ChangeEvent(m_suspended, false);  
  
   // Check for a suspend before doing any work,   
   // in case the suspend and execute calls  
   // were initiated at virtually the same time.  
   CheckAndSuspend();  
   CheckAndFireBreakpoint( componentEvents, 1);  
}  
private void CheckAndSuspend()  
{  
   // Loop until we can execute.    
   // The loop is required rather than a simple If  
   // because there is a time between the return from WaitOne and the  
   // reset that we might receive another Suspend call.    
   // Suspend() will see that we are suspended  
   // and return.  So we need to rewait.  
   while (!m_canExecute.WaitOne(0, false))  
   {  
      ChangeEvent(m_suspended, true);  
      m_canExecute.WaitOne();  
      ChangeEvent(m_suspended, false);  
   }  
}  
private void CheckAndFireBreakpoint(IDTSComponentEvents events, int breakpointID)  
{  
   // If the breakpoint is enabled, fire it.  
   if (m_debugMode != 0 &&    this.bpm.IsBreakpointTargetEnabled(breakpointID))  
   {  
      //   Enter a suspend mode before firing the breakpoint.    
      //   Firing the breakpoint will cause the runtime   
      //   to call Suspend on this task.    
      //   Because we are blocked on the breakpoint,   
      //   we are suspended.  
      ChangeEvent(m_suspended, true);  
      events.OnBreakpointHit(this.bpm.GetBreakpointTarget(breakpointID));  
      ChangeEvent(m_suspended, false);  
   }  
   // Check for a suspension for two reasons:   
   //   1. If we are at a point where we could fire a breakpoint,   
   //      we are at a valid suspend point.  Even if we didn't hit a  
   //      breakpoint, the runtime may have called suspend,   
   //      so check for it.       
   //   2. Between the return from OnBreakpointHit   
   //      and the reset of the event, it is possible to have  
   //      received a suspend call from which we returned because   
   //      we were already suspended.  We need to be sure it is okay  
   //      to continue executing now.  
   CheckAndSuspend();  
}  
static void ChangeEvent(ManualResetEvent e, bool shouldSet)  
{  
   bool succeeded;  
   if (shouldSet)  
      succeeded = e.Set();  
   else  
      succeeded = e.Reset();  
  
   if (!succeeded)  
      throw new Exception("Synchronization object failed.");  
  
}  
public bool SuspendRequired  
{  
   get   {return m_suspendRequired != 0;}  
   set  
   {  
      // This lock is also taken by Suspend().    
      // Because it is possible for the package to be  
      // suspended and resumed in quick succession,   
      // this property might be set before  
      // the actual Suspend() call.    
      // Without the lock, the Suspend() might reset the canExecute  
      // event after we set it to abort the suspension.  
      lock (this)  
      {  
         Interlocked.Exchange(ref m_suspendRequired, value ? 1 : 0);  
         if (!value)  
            ResumeExecution();  
      }  
   }  
}  
public void ResumeExecution()  
{  
   ChangeEvent( m_canExecute,true );  
}  
public void Suspend()  
{  
   // This lock is also taken by the set SuspendRequired method.    
   // It prevents this call from overriding an   
   // aborted suspension.  See comments in set SuspendRequired.  
   lock (this)  
   {  
      // If a Suspend is required, do it.  
      if (m_suspendRequired != 0)  
         ChangeEvent(m_canExecute, false);  
   }  
   // We can't return from Suspend until the task is "suspended".  
   // This can happen one of two ways:   
   // the m_suspended event occurs, indicating that the execute thread  
   // has suspended, or the canExecute flag is set,   
   // indicating that a suspend is no longer required.  
   WaitHandle [] suspendOperationComplete = {m_suspended, m_canExecute};  
   WaitHandle.WaitAny(suspendOperationComplete);  
}  
```  
  
```vb  
Private m_suspended As ManualResetEvent = New ManualResetEvent(True)  
Private m_canExecute As ManualResetEvent = New ManualResetEvent(True)  
Private m_suspendRequired As Integer = 0  
Private m_debugMode As Integer = 0  
  
Public Overrides Function Execute(ByVal connections As Connections, _  
ByVal variables As Variables, ByVal events As IDTSComponentEvents, _  
ByVal log As IDTSLogging, ByVal txn As DtsTransaction) As DTSExecResult  
  
   ' While a task is not executing it is suspended.    
   ' Now that we are executing,  
   ' change to not suspended.  
   ChangeEvent(m_suspended, False)  
  
   ' Check for a suspend before doing any work,   
   ' in case the suspend and execute calls  
   ' were initiated at virtually the same time.  
   CheckAndSuspend()  
   CheckAndFireBreakpoint(componentEvents, 1)  
  
End Function  
  
Private Sub CheckAndSuspend()  
  
   ' Loop until we can execute.    
   ' The loop is required rather than a simple if  
   ' because there is a time between the return from WaitOne and the  
   ' reset that we might receive another Suspend call.    
   ' Suspend() will see that we are suspended  
   ' and return.  So we need to rewait.  
   Do While Not m_canExecute.WaitOne(0, False)  
              ChangeEvent(m_suspended, True)  
              m_canExecute.WaitOne()  
              ChangeEvent(m_suspended, False)  
   Loop  
  
End Sub  
  
Private Sub CheckAndFireBreakpoint(ByVal events As IDTSComponentEvents, _  
ByVal breakpointID As Integer)  
  
   ' If the breakpoint is enabled, fire it.  
   If m_debugMode <> 0 AndAlso Me.bpm.IsBreakpointTargetEnabled(breakpointID) Then  
              '   Enter a suspend mode before firing the breakpoint.    
              '   Firing the breakpoint will cause the runtime   
              '   to call Suspend on this task.    
              '   Because we are blocked on the breakpoint,   
              '   we are suspended.  
              ChangeEvent(m_suspended, True)  
              events.OnBreakpointHit(Me.bpm.GetBreakpointTarget(breakpointID))  
              ChangeEvent(m_suspended, False)  
   End If  
  
   ' Check for a suspension for two reasons:   
   '   1. If we are at a point where we could fire a breakpoint,   
   '         we are at a valid suspend point.  Even if we didn't hit a  
   '         breakpoint, the runtime may have called suspend,   
   '         so check for it.     
   '   2. Between the return from OnBreakpointHit   
   '         and the reset of the event, it is possible to have  
   '         received a suspend call from which we returned because   
   '         we were already suspended.  We need to be sure it is okay  
   '         to continue executing now.  
   CheckAndSuspend()  
  
End Sub  
  
Shared Sub ChangeEvent(ByVal e As ManualResetEvent, ByVal shouldSet As Boolean)  
  
   Dim succeeded As Boolean  
   If shouldSet Then  
              succeeded = e.Set()  
   Else  
              succeeded = e.Reset()  
   End If  
  
   If (Not succeeded) Then  
              Throw New Exception("Synchronization object failed.")  
   End If  
  
End Sub  
  
Public Property SuspendRequired() As Boolean  
   Get  
               Return m_suspendRequired <> 0  
  End Get  
  Set  
    ' This lock is also taken by Suspend().    
     '   Because it is possible for the package to be  
     '   suspended and resumed in quick succession,   
     '   this property might be set before  
     '   the actual Suspend() call.    
     '   Without the lock, the Suspend() might reset the canExecute  
     '   event after we set it to abort the suspension.  
              SyncLock Me  
                         Interlocked.Exchange(m_suspendRequired,IIf(Value, 1, 0))  
                         If (Not Value) Then  
                                    ResumeExecution()  
                         End If  
              End SyncLock  
   End Set  
End Property  
  
Public Sub ResumeExecution()  
   ChangeEvent(m_canExecute,True)  
End Sub  
  
Public Sub Suspend()  
  
   ' This lock is also taken by the set SuspendRequired method.    
   ' It prevents this call from overriding an   
   ' aborted suspension.  See comments in set SuspendRequired.  
   SyncLock Me  
   ' If a Suspend is required, do it.  
              If m_suspendRequired <> 0 Then  
                         ChangeEvent(m_canExecute, False)  
              End If  
   End SyncLock  
   ' We can't return from Suspend until the task is "suspended".  
   ' This can happen one of two ways:   
   ' the m_suspended event occurs, indicating that the execute thread  
   ' has suspended, or the canExecute flag is set,   
   ' indicating that a suspend is no longer required.  
   Dim suspendOperationComplete As WaitHandle() = {m_suspended, m_canExecute}  
   WaitHandle.WaitAny(suspendOperationComplete)  
  
End Sub  
```  
  
<span data-ttu-id="7a687-137">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="7a687-137">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="7a687-138">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="7a687-138">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="7a687-139">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="7a687-139">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="7a687-140">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="7a687-140">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a687-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="7a687-141">See Also</span></span>  
 [<span data-ttu-id="7a687-142">Отладка потока управления</span><span class="sxs-lookup"><span data-stu-id="7a687-142">Debugging Control Flow</span></span>](../../troubleshooting/debugging-control-flow.md)  
  
  
