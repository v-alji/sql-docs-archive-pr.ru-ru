---
title: Написание кода и отладка задачи "Скрипт" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], debugging
- SSIS Script task, development environment
- SSIS Script task, debugging
- Script task [Integration Services], development environment
- Script task [Integration Services], coding
- debugging [Integration Services], scripts
- VSTA
- SSIS Script task, coding
ms.assetid: 687c262f-fcab-42e8-92ae-e956f3d92d69
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0f4383469368ac1fe3c70ff82f8c8bb2cf755838
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728494"
---
# <a name="coding-and-debugging-the-script-task"></a><span data-ttu-id="b41ef-102">Написание кода и отладка задачи «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="b41ef-102">Coding and Debugging the Script Task</span></span>
  <span data-ttu-id="b41ef-103">После настройки задачи "Скрипт" в окне **Редактор задачи "Скрипт"** нужно создать пользовательский код в среде разработки задачи "Скрипт".</span><span class="sxs-lookup"><span data-stu-id="b41ef-103">After configuring the Script task in the **Script Task Editor**, you write your custom code in the Script task development environment.</span></span>

## <a name="script-task-development-environment"></a><span data-ttu-id="b41ef-104">Среда разработки задачи «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="b41ef-104">Script Task Development Environment</span></span>
 <span data-ttu-id="b41ef-105">Задача "Скрипт" использует набор средств [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Tools для работы с приложениями (VSTA) в качестве среды разработки для самого скрипта.</span><span class="sxs-lookup"><span data-stu-id="b41ef-105">The Script task uses [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Tools for Applications (VSTA) as the development environment for the script itself.</span></span>

 <span data-ttu-id="b41ef-106">Код скрипта пишется на языке [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic или [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="b41ef-106">Script code is written in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic or [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span></span> <span data-ttu-id="b41ef-107">Пользователь указывает язык скрипта, задавая значение свойства **ScriptLanguage** в окне **Редактор задачи "Скрипт"** .</span><span class="sxs-lookup"><span data-stu-id="b41ef-107">You specify the script language by setting the **ScriptLanguage** property in the **Script Task Editor**.</span></span> <span data-ttu-id="b41ef-108">Если разработчик предпочитает пользоваться другим языком программирования, можно разработать пользовательскую сборку на выбранном языке и вызвать его функциональные возможности из кода в задаче «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="b41ef-108">If you prefer to use another programming language, you can develop a custom assembly in your language of choice and call its functionality from the code in the Script task.</span></span>

 <span data-ttu-id="b41ef-109">Скрипт, созданный в задаче «Скрипт», хранится в определении пакета.</span><span class="sxs-lookup"><span data-stu-id="b41ef-109">The script that you create in the Script task is stored in the package definition.</span></span> <span data-ttu-id="b41ef-110">Отдельного файла скрипта не существует.</span><span class="sxs-lookup"><span data-stu-id="b41ef-110">There is no separate script file.</span></span> <span data-ttu-id="b41ef-111">Поэтому использование задачи «Скрипт» не влияет на развертывание пакета.</span><span class="sxs-lookup"><span data-stu-id="b41ef-111">Therefore, the use of the Script task does not affect package deployment.</span></span>

> [!NOTE]
>  <span data-ttu-id="b41ef-112">При проектировании пакета и отладке скрипта код скрипта временно записывается в файл проекта.</span><span class="sxs-lookup"><span data-stu-id="b41ef-112">When you design the package and debug the script, the script code is temporarily written to a project file.</span></span> <span data-ttu-id="b41ef-113">Хранение конфиденциальных сведений в файле представляет потенциальный риск для безопасности, поэтому в код скрипта не рекомендуется включать конфиденциальные данные, например пароли.</span><span class="sxs-lookup"><span data-stu-id="b41ef-113">Because storing sensitive information in a file is a potential security risk, we recommend that you do not include sensitive information such as passwords in the script code.</span></span>

 <span data-ttu-id="b41ef-114">По умолчанию среда `Option Strict` в среде разработки отключена.</span><span class="sxs-lookup"><span data-stu-id="b41ef-114">By default, `Option Strict` is disabled in the IDE.</span></span>

## <a name="script-task-project-structure"></a><span data-ttu-id="b41ef-115">Структура проекта задачи «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="b41ef-115">Script Task Project Structure</span></span>
 <span data-ttu-id="b41ef-116">При создании или изменении скрипта, содержащегося в задаче «Скрипт» средства VSTA открывают новый пустой проект или повторно открывают существующий проект.</span><span class="sxs-lookup"><span data-stu-id="b41ef-116">When you create or modify the script that is contained in a Script task, VSTA opens an empty new project or reopens the existing project.</span></span> <span data-ttu-id="b41ef-117">Создание этого проекта VSTA не влияет на развертывание пакета, поскольку проект сохраняется внутри пакетного файла и задача «Скрипт» не создает дополнительных файлов.</span><span class="sxs-lookup"><span data-stu-id="b41ef-117">The creation of this VSTA project does not affect the deployment of the package, because the project is saved inside the package file; the Script task does not create additional files.</span></span>

### <a name="project-items-and-classes-in-the-script-task-project"></a><span data-ttu-id="b41ef-118">Элементы и классы проекта в проекте задачи «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="b41ef-118">Project Items and Classes in the Script Task Project</span></span>
 <span data-ttu-id="b41ef-119">По умолчанию проект задачи «Скрипт», отображаемый в окне обозревателя проекта VSTA, содержит один элемент `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="b41ef-119">By default, the Script task project displayed in the VSTA Project Explorer window contains a single item, `ScriptMain`.</span></span> <span data-ttu-id="b41ef-120">В свою очередь, элемент `ScriptMain` содержит один класс, именуемый `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="b41ef-120">The `ScriptMain` item, in turn, contains a single class, also named `ScriptMain`.</span></span> <span data-ttu-id="b41ef-121">Элементы кода в классе изменяются в зависимости от языка программирования, выбранного для задачи «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="b41ef-121">The code elements in the class vary depending on the programming language that you selected for the Script task:</span></span>

-   <span data-ttu-id="b41ef-122">Если задача «Скрипт» настроена для [!INCLUDE[vb_orcas_long](../../../includes/vb-orcas-long-md.md)] языка программирования, то `ScriptMain` класс имеет общедоступную подпрограмму `Main` .</span><span class="sxs-lookup"><span data-stu-id="b41ef-122">When the Script task is configured for the [!INCLUDE[vb_orcas_long](../../../includes/vb-orcas-long-md.md)] programming language, the `ScriptMain` class has a public subroutine, `Main`.</span></span> <span data-ttu-id="b41ef-123">Подпрограмма `ScriptMain.Main` является методом, который вызывается во время выполнения задачи «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="b41ef-123">The `ScriptMain.Main` subroutine is the method that the runtime calls when you run your Script task.</span></span>

     <span data-ttu-id="b41ef-124">По умолчанию единственным кодом в подпрограмме `Main` нового скрипта является строка `Dts.TaskResult = ScriptResults.Success`.</span><span class="sxs-lookup"><span data-stu-id="b41ef-124">By default, the only code in the `Main` subroutine of a new script is the line `Dts.TaskResult = ScriptResults.Success`.</span></span> <span data-ttu-id="b41ef-125">Эта строка извещает среду выполнения об успешной работе задачи.</span><span class="sxs-lookup"><span data-stu-id="b41ef-125">This line informs the runtime that the task was successful in its operation.</span></span> <span data-ttu-id="b41ef-126">`Dts.TaskResult`Свойство обсуждается в разделе [возвращение результатов из задачи «Скрипт](../../extending-packages-scripting/task/returning-results-from-the-script-task.md)».</span><span class="sxs-lookup"><span data-stu-id="b41ef-126">The `Dts.TaskResult` property is discussed in [Returning Results from the Script Task](../../extending-packages-scripting/task/returning-results-from-the-script-task.md).</span></span>

-   <span data-ttu-id="b41ef-127">Если для задачи «Скрипт» задан язык программирования Visual C#, то класс `ScriptMain` имеет публичный метод `Main`.</span><span class="sxs-lookup"><span data-stu-id="b41ef-127">When the Script task is configured for the Visual C# programming language, the `ScriptMain` class has a public method, `Main`.</span></span> <span data-ttu-id="b41ef-128">Этот метод вызывается при запуске задачи «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="b41ef-128">The method is called when the Script task runs.</span></span>

     <span data-ttu-id="b41ef-129">По умолчанию метод `Main` включает строку `Dts.TaskResult = (int)ScriptResults.Success`.</span><span class="sxs-lookup"><span data-stu-id="b41ef-129">By default, the `Main` method includes the line `Dts.TaskResult = (int)ScriptResults.Success`.</span></span> <span data-ttu-id="b41ef-130">Эта строка извещает среду выполнения об успешной работе задачи.</span><span class="sxs-lookup"><span data-stu-id="b41ef-130">This line informs the runtime that the task was successful in its operation.</span></span>

 <span data-ttu-id="b41ef-131">Элемент `ScriptMain` может содержать классы, отличные от класса `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="b41ef-131">The `ScriptMain` item can contain classes other than the `ScriptMain` class.</span></span> <span data-ttu-id="b41ef-132">Классы доступны только задаче «Скрипт», в которой они находятся.</span><span class="sxs-lookup"><span data-stu-id="b41ef-132">Classes are available only to the Script task in which they reside.</span></span>

 <span data-ttu-id="b41ef-133">По умолчанию элемент проекта `ScriptMain` содержит следующий автоматически формируемый код.</span><span class="sxs-lookup"><span data-stu-id="b41ef-133">By default, the `ScriptMain` project item contains the following autogenerated code.</span></span> <span data-ttu-id="b41ef-134">В шаблоне кода также имеются общие сведения о задаче «Скрипт» и дополнительные сведения о получении и управлении такими объектами служб SSIS, как переменные, события и подключения.</span><span class="sxs-lookup"><span data-stu-id="b41ef-134">The code template also provides an overview of the Script task, and additional information on how to retrieve and manipulate SSIS objects, such as variables, events, and connections.</span></span>

```vb
' Microsoft SQL Server Integration Services Script Task
' Write scripts using Microsoft Visual Basic 2008.
' The ScriptMain is the entry point class of the script.

Imports System
Imports System.Data
Imports System.Math
Imports Microsoft.SqlServer.Dts.Runtime.VSTAProxy

<System.AddIn.AddIn("ScriptMain", Version:="1.0", Publisher:="", Description:="")> _
Partial Class ScriptMain

Private Sub ScriptMain_Startup(ByVal sender As Object, ByVal e As System.EventArgs) Handles Me.Startup

End Sub

Private Sub ScriptMain_Shutdown(ByVal sender As Object, ByVal e As System.EventArgs) Handles Me.Shutdown
Try
' Unlock variables from the read-only and read-write variable collection properties
If (Dts.Variables.Count <> 0) Then
Dts.Variables.Unlock()
End If
Catch ex As Exception
        End Try
End Sub

Enum ScriptResults
Success = DTSExecResult.Success
Failure = DTSExecResult.Failure
End Enum

' The execution engine calls this method when the task executes.
' To access the object model, use the Dts property. Connections, variables, events,
' and logging features are available as members of the Dts property as shown in the following examples.
'
' To reference a variable, call Dts.Variables("MyCaseSensitiveVariableName").Value
' To post a log entry, call Dts.Log("This is my log text", 999, Nothing)
' To fire an event, call Dts.Events.FireInformation(99, "test", "hit the help message", "", 0, True)
'
' To use the connections collection use something like the following:
' ConnectionManager cm = Dts.Connections.Add("OLEDB")
' cm.ConnectionString = "Data Source=localhost;Initial Catalog=AdventureWorks;Provider=SQLNCLI10;Integrated Security=SSPI;Auto Translate=False;"
'
' Before returning from this method, set the value of Dts.TaskResult to indicate success or failure.
' 
' To open Help, press F1.

Public Sub Main()
'
' Add your code here
'
Dts.TaskResult = ScriptResults.Success
End Sub

End Class
```

```csharp
/*
   Microsoft SQL Server Integration Services Script Task
   Write scripts using Microsoft Visual C# 2008.
   The ScriptMain is the entry point class of the script.
*/

using System;
using System.Data;
using Microsoft.SqlServer.Dts.Runtime.VSTAProxy;
using System.Windows.Forms;

namespace ST_1bcfdbad36d94f8ba9f23a10375abe53.csproj
{
    [System.AddIn.AddIn("ScriptMain", Version = "1.0", Publisher = "", Description = "")]
    public partial class ScriptMain
    {
        private void ScriptMain_Startup(object sender, EventArgs e)
        {

        }

        private void ScriptMain_Shutdown(object sender, EventArgs e)
        {
            try
            {
                // Unlock variables from the read-only and read-write variable collection properties
                if (Dts.Variables.Count != 0)
                {
                    Dts.Variables.Unlock();
                }
            }
            catch
            {
            }
        }

        #region VSTA generated code
        private void InternalStartup()
        {
            this.Startup += new System.EventHandler(ScriptMain_Startup);
            this.Shutdown += new System.EventHandler(ScriptMain_Shutdown);
        }
        enum ScriptResults
        {
            Success = DTSExecResult.Success,
            Failure = DTSExecResult.Failure
        };

        #endregion

        /*
The execution engine calls this method when the task executes.
To access the object model, use the Dts property. Connections, variables, events,
and logging features are available as members of the Dts property as shown in the following examples.

To reference a variable, call Dts.Variables["MyCaseSensitiveVariableName"].Value;
To post a log entry, call Dts.Log("This is my log text", 999, null);
To fire an event, call Dts.Events.FireInformation(99, "test", "hit the help message", "", 0, true);

To use the connections collection use something like the following:
ConnectionManager cm = Dts.Connections.Add("OLEDB");
cm.ConnectionString = "Data Source=localhost;Initial Catalog=AdventureWorks;Provider=SQLNCLI10;Integrated Security=SSPI;Auto Translate=False;";

Before returning from this method, set the value of Dts.TaskResult to indicate success or failure.

To open Help, press F1.
*/

        public void Main()
        {
            // TODO: Add your code here
            Dts.TaskResult = (int)ScriptResults.Success;
        }
    }
```

### <a name="additional-project-items-in-the-script-task-project"></a><span data-ttu-id="b41ef-135">Дополнительные элементы проекта в проекте задачи «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="b41ef-135">Additional Project Items in the Script Task Project</span></span>
 <span data-ttu-id="b41ef-136">Проект задачи «Скрипт» может содержать элементы, отличные от элемента `ScriptMain` по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b41ef-136">The Script task project can include items other than the default `ScriptMain` item.</span></span> <span data-ttu-id="b41ef-137">К проекту можно добавлять классы, модули и файлы кодов.</span><span class="sxs-lookup"><span data-stu-id="b41ef-137">You can add classes, modules, and code files to the project.</span></span> <span data-ttu-id="b41ef-138">Можно также использовать папки для организации групп элементов.</span><span class="sxs-lookup"><span data-stu-id="b41ef-138">You can also use folders to organize groups of items.</span></span> <span data-ttu-id="b41ef-139">Все добавляемые элементы сохраняются внутри пакета.</span><span class="sxs-lookup"><span data-stu-id="b41ef-139">All the items that you add are persisted inside the package.</span></span>

### <a name="references-in-the-script-task-project"></a><span data-ttu-id="b41ef-140">Ссылки в проекте задачи «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="b41ef-140">References in the Script Task Project</span></span>
 <span data-ttu-id="b41ef-141">Чтобы добавить ссылки в управляемые сборки, щелкните правой кнопкой мыши проект задачи "Скрипт" в **Обозревателе проектов**, затем выберите **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="b41ef-141">You can add references to managed assemblies by right-clicking the Script task project in **Project Explorer**, and then clicking **Add Reference**.</span></span> <span data-ttu-id="b41ef-142">Дополнительные сведения см. в разделе [Ссылки на другие сборки в решениях со сценариями](../referencing-other-assemblies-in-scripting-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="b41ef-142">For more information, see [Referencing Other Assemblies in Scripting Solutions](../referencing-other-assemblies-in-scripting-solutions.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="b41ef-143">Ссылки проекта можно просмотреть в среде разработки VSTA в **представлении классов** или в **обозревателе проектов**.</span><span class="sxs-lookup"><span data-stu-id="b41ef-143">You can view project references in the VSTA IDE in **Class View** or in **Project Explorer**.</span></span> <span data-ttu-id="b41ef-144">Любое из этих окон можно открыть из меню **Вид**.</span><span class="sxs-lookup"><span data-stu-id="b41ef-144">You open either of these windows from the **View** menu.</span></span> <span data-ttu-id="b41ef-145">Можно добавить новую ссылку из меню **Проект**, из **обозревателя проектов** или из **представления классов**.</span><span class="sxs-lookup"><span data-stu-id="b41ef-145">You can add a new reference from the **Project** menu, from **Project Explorer**, or from **Class View**.</span></span>

## <a name="interacting-with-the-package-in-the-script-task"></a><span data-ttu-id="b41ef-146">Взаимодействие с пакетом в задаче «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="b41ef-146">Interacting with the Package in the Script Task</span></span>
 <span data-ttu-id="b41ef-147">Задача «Скрипт» использует глобальный объект `Dts`, являющийся экземпляром класса <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel>, а его элементы должны взаимодействовать с содержащим их пакетом и со средой выполнения служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b41ef-147">The Script task uses the global `Dts` object, which is an instance of the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel> class, and its members to interact with the containing package and with the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] runtime.</span></span>

 <span data-ttu-id="b41ef-148">В следующей таблице представлены основные открытые элементы класса <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel>, который представлен в коде задачи «Скрипт» через глобальный объект `Dts`.</span><span class="sxs-lookup"><span data-stu-id="b41ef-148">The following table lists the principal public members of the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel> class, which is exposed to Script task code through the global `Dts` object.</span></span> <span data-ttu-id="b41ef-149">В этом разделе более подробно рассматривается использование этих элементов.</span><span class="sxs-lookup"><span data-stu-id="b41ef-149">The topics in this section discuss the use of these members in more detail.</span></span>

|<span data-ttu-id="b41ef-150">Участник</span><span class="sxs-lookup"><span data-stu-id="b41ef-150">Member</span></span>|<span data-ttu-id="b41ef-151">Назначение</span><span class="sxs-lookup"><span data-stu-id="b41ef-151">Purpose</span></span>|
|------------|-------------|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Connections%2A>|<span data-ttu-id="b41ef-152">Предоставляет доступ к диспетчерам соединений, определенным в пакете.</span><span class="sxs-lookup"><span data-stu-id="b41ef-152">Provides access to connection managers defined in the package.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A>|<span data-ttu-id="b41ef-153">Предоставляет интерфейс событий, чтобы задача «Скрипт» могла инициировать ошибки, предупреждения и информационные сообщения.</span><span class="sxs-lookup"><span data-stu-id="b41ef-153">Provides an events interface to let the Script task raise errors, warnings, and informational messages.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A>|<span data-ttu-id="b41ef-154">Предоставляет простой способ возвращения одного объекта в среду выполнения (в дополнение к `TaskResult`), который может также использоваться для ветвления рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="b41ef-154">Provides a simple way to return a single object to the runtime (in addition to the `TaskResult`) that can also be used for workflow branching.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A>|<span data-ttu-id="b41ef-155">Записывает во включенные регистраторы данные, такие как ход выполнения задачи и результаты.</span><span class="sxs-lookup"><span data-stu-id="b41ef-155">Logs information such as task progress and results to enabled log providers.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.TaskResult%2A>|<span data-ttu-id="b41ef-156">Сообщает об успешном или неуспешном выполнении задачи.</span><span class="sxs-lookup"><span data-stu-id="b41ef-156">Reports the success or failure of the task.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Transaction%2A>|<span data-ttu-id="b41ef-157">Предоставляет транзакцию, если она имеется, в которой работает контейнер задачи.</span><span class="sxs-lookup"><span data-stu-id="b41ef-157">Provides the transaction, if any, within which the task's container is running.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A>|<span data-ttu-id="b41ef-158">Предоставляет доступ к используемым в скрипте переменным, указанным в свойствах `ReadOnlyVariables` и `ReadWriteVariables` задачи.</span><span class="sxs-lookup"><span data-stu-id="b41ef-158">Provides access to the variables listed in the `ReadOnlyVariables` and `ReadWriteVariables` task properties for use within the script.</span></span>|

 <span data-ttu-id="b41ef-159">Класс <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel> содержит также некоторые открытые элементы, которые, вероятно, не будут использованы.</span><span class="sxs-lookup"><span data-stu-id="b41ef-159">The <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel> class also contains some public members that you will probably not use.</span></span>

|<span data-ttu-id="b41ef-160">Участник</span><span class="sxs-lookup"><span data-stu-id="b41ef-160">Member</span></span>|<span data-ttu-id="b41ef-161">Description</span><span class="sxs-lookup"><span data-stu-id="b41ef-161">Description</span></span>|
|------------|-----------------|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A>|<span data-ttu-id="b41ef-162">Свойство <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> предоставляет более удобный доступ к переменным.</span><span class="sxs-lookup"><span data-stu-id="b41ef-162">The <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property provides more convenient access to variables.</span></span> <span data-ttu-id="b41ef-163">Хотя можно использовать <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A>, необходимо явно вызывать методы для блокировки и разблокировки переменных для чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="b41ef-163">Although you can use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A>, you must explicitly call methods to lock and unlock variables for reading and writing.</span></span> <span data-ttu-id="b41ef-164">Задача «Скрипт» прозрачно обрабатывает семантику блокировки при использовании свойства <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A>.</span><span class="sxs-lookup"><span data-stu-id="b41ef-164">The Script task handles locking semantics for you when you use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property.</span></span>|

## <a name="debugging-the-script-task"></a><span data-ttu-id="b41ef-165">Отладка задачи «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="b41ef-165">Debugging the Script Task</span></span>
 <span data-ttu-id="b41ef-166">Для отладки кода в задаче «Скрипт» установите в коде по крайней мере одну точку останова, а затем закройте среду разработки VSTA IDE, чтобы запустить пакет в среде [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b41ef-166">To debug the code in your Script task, set at least one breakpoint in the code, and then close the VSTA IDE to run the package in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="b41ef-167">Когда выполнение пакета входит в задачу «Скрипт», среда разработки VSTA IDE открывается повторно и отображает код в режиме только для чтения.</span><span class="sxs-lookup"><span data-stu-id="b41ef-167">When package execution enters the Script task, the VSTA IDE reopens and displays your code in read-only mode.</span></span> <span data-ttu-id="b41ef-168">После того как выполнение достигает точку останова, можно проверить значения переменных и выполнить оставшийся код в режиме пошагового выполнения.</span><span class="sxs-lookup"><span data-stu-id="b41ef-168">After execution reaches your breakpoint, you can examine variable values and step through the remaining code.</span></span>

> [!WARNING]
>  <span data-ttu-id="b41ef-169">При выполнении пакета в 64-разрядном режиме задачу «Скрипт» можно отлаживать.</span><span class="sxs-lookup"><span data-stu-id="b41ef-169">You can debug the Script task when you run the package in 64-bit mode.</span></span>

> [!NOTE]
>  <span data-ttu-id="b41ef-170">Для отладки задачи «Скрипт» необходимо выполнить пакет.</span><span class="sxs-lookup"><span data-stu-id="b41ef-170">You must execute the package to debug into your Script task.</span></span> <span data-ttu-id="b41ef-171">Если выполняется только отдельная задача, точки останова в коде задачи «Скрипт» пропускаются.</span><span class="sxs-lookup"><span data-stu-id="b41ef-171">If you execute only the individual task, breakpoints in the Script task code are ignored.</span></span>

> [!NOTE]
>  <span data-ttu-id="b41ef-172">Однако нельзя выполнять отладку задачи «Скрипт», если задача запускается как часть дочернего пакета, вызываемого задачей «Выполнение пакета».</span><span class="sxs-lookup"><span data-stu-id="b41ef-172">You cannot debug a Script task when you run the Script task as part of a child package that is run from an Execute Package task.</span></span> <span data-ttu-id="b41ef-173">В этом случае точки останова, установленные в задаче «Скрипт» в дочернем пакете, пропускаются.</span><span class="sxs-lookup"><span data-stu-id="b41ef-173">Breakpoints that you set in the Script task in the child package are disregarded in these circumstances.</span></span> <span data-ttu-id="b41ef-174">Дочерний пакет можно нормально отладить, запустив его отдельно.</span><span class="sxs-lookup"><span data-stu-id="b41ef-174">You can debug the child package normally by running it separately.</span></span>

> [!NOTE]
>  <span data-ttu-id="b41ef-175">Во время отладки пакета, содержащего несколько задач «Скрипт», отладчик выполняет отладку одной задачи «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="b41ef-175">When you debug a package that contains multiple Script tasks, the debugger debugs one Script task.</span></span> <span data-ttu-id="b41ef-176">Затем система может выполнять отладку другой задачи «Скрипт», если отладчик завершает работу, как в случае контейнера «цикл по элементам» или «цикл по каждому элементу».</span><span class="sxs-lookup"><span data-stu-id="b41ef-176">The system can debug another Script task if the debugger completes, as in the case of a Foreach Loop or For Loop container.</span></span>

## <a name="external-resources"></a><span data-ttu-id="b41ef-177">Внешние ресурсы</span><span class="sxs-lookup"><span data-stu-id="b41ef-177">External Resources</span></span>

-   <span data-ttu-id="b41ef-178">Запись в блоге [Затруднения при установке и настройке VSTA для установок SSIS 2008 и R2](https://go.microsoft.com/fwlink/?LinkId=215661) на сайте blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="b41ef-178">Blog entry, [VSTA setup and configuration troubles for SSIS 2008 and R2 installations](https://go.microsoft.com/fwlink/?LinkId=215661), on blogs.msdn.com.</span></span>

<span data-ttu-id="b41ef-179">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="b41ef-179">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="b41ef-180">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы [!INCLUDE[msCoName](../../../includes/msconame-md.md)], а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="b41ef-180">For the latest downloads, articles, samples, and videos from [!INCLUDE[msCoName](../../../includes/msconame-md.md)], as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="b41ef-181">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="b41ef-181">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="b41ef-182">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="b41ef-182">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="b41ef-183">См. также:</span><span class="sxs-lookup"><span data-stu-id="b41ef-183">See Also</span></span>
 <span data-ttu-id="b41ef-184">[Создание ссылок на другие сборки в решениях скриптов](../referencing-other-assemblies-in-scripting-solutions.md) [Настройка задачи «Скрипт» в редакторе задачи «Скрипт](configuring-the-script-task-in-the-script-task-editor.md) »</span><span class="sxs-lookup"><span data-stu-id="b41ef-184">[Referencing Other Assemblies in Scripting Solutions](../referencing-other-assemblies-in-scripting-solutions.md) [Configuring the Script Task in the Script Task Editor](configuring-the-script-task-in-the-script-task-editor.md)</span></span>


