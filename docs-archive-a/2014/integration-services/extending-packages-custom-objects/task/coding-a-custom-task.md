---
title: Создание кода пользовательской задачи | Документы Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Validate method
- custom tasks [Integration Services], validating
- validation [Integration Services], design-time tasks
- SSIS custom tasks, validating
ms.assetid: dc224f4f-b339-4eb6-a008-1b4fe0ea4fd2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c369f4a7e8352be7ddde9e2e3938b47b0bcc1349
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665443"
---
# <a name="coding-a-custom-task"></a><span data-ttu-id="b34bf-102">Создание кода пользовательской задачи</span><span class="sxs-lookup"><span data-stu-id="b34bf-102">Coding a Custom Task</span></span>
  <span data-ttu-id="b34bf-103">После создания класса, наследующего от базового класса [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task), и применения к нему атрибута <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> необходимо переопределить реализацию свойств и методов базового класса, чтобы обеспечить ваши пользовательские функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="b34bf-103">After you have created a class that inherits from the [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) base class, and applied the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute to the class, you must override the implementation of the properties and methods of the base class to provide your custom functionality.</span></span>

## <a name="configuring-the-task"></a><span data-ttu-id="b34bf-104">Настройка задачи</span><span class="sxs-lookup"><span data-stu-id="b34bf-104">Configuring the Task</span></span>

### <a name="validating-the-task"></a><span data-ttu-id="b34bf-105">Проверка задачи</span><span class="sxs-lookup"><span data-stu-id="b34bf-105">Validating the Task</span></span>
 <span data-ttu-id="b34bf-106">При разработке пакета служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] можно использовать проверку, чтобы убедиться в правильности настроек каждой задачи. Проверка позволит отследить неверные или неподходящие настройки сразу же после их задания, вместо того, чтобы обнаруживать их лишь во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b34bf-106">When you are designing an [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] package, you can use validation to verify settings on each task, so that you can catch incorrect or inappropriate settings as soon as they are set, instead of finding all errors at run-time only.</span></span> <span data-ttu-id="b34bf-107">Цель проверки состоит в том, чтобы определить, содержит ли задача недопустимые настройки или соединения, которые могут помешать ее успешному выполнению.</span><span class="sxs-lookup"><span data-stu-id="b34bf-107">The purpose of validation is to determine whether the task contains invalid settings or connections that will prevent it from running successfully.</span></span> <span data-ttu-id="b34bf-108">Таким образом, можно убедиться в том, что пакет содержит только те задачи, выполнение которых будет успешным с первой попытки.</span><span class="sxs-lookup"><span data-stu-id="b34bf-108">This makes sure that the package contains tasks that have a good chance of running on their first run.</span></span>

 <span data-ttu-id="b34bf-109">Можно реализовать проверку с помощью метода `Validate` в пользовательском коде.</span><span class="sxs-lookup"><span data-stu-id="b34bf-109">You can implement validation by using the `Validate` method in custom code.</span></span> <span data-ttu-id="b34bf-110">Обработчик среды выполнения осуществляет проверку задачи путем вызова метода `Validate` для этой задачи.</span><span class="sxs-lookup"><span data-stu-id="b34bf-110">The run-time engine validates a task by calling the `Validate` method on the task.</span></span> <span data-ttu-id="b34bf-111">Разработчику задачи следует определить критерии успешной или неуспешной проверки задачи, а также обеспечить уведомление обработчика времени выполнения о результатах этой оценки.</span><span class="sxs-lookup"><span data-stu-id="b34bf-111">It is the responsibility of the task developer to define the criteria that give you a successful or failed task validation, and to notify the run-time engine of the result of this evaluation.</span></span>

#### <a name="task-abstract-base-class"></a><span data-ttu-id="b34bf-112">Абстрактный базовый класс Task</span><span class="sxs-lookup"><span data-stu-id="b34bf-112">Task Abstract Base Class</span></span>
 <span data-ttu-id="b34bf-113">Абстрактный базовый класс [Microsoft. SqlServer. DTS. Runtime. Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) содержит `Validate` метод, переопределяемый каждой задачей для определения критериев проверки.</span><span class="sxs-lookup"><span data-stu-id="b34bf-113">The [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) abstract base class provides the `Validate` method that each task overrides to define its validation criteria.</span></span> <span data-ttu-id="b34bf-114">Конструктор служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] автоматически вызывает метод `Validate` неоднократно во время разработки пакета и предоставляет пользователю визуальные подсказки при появлении предупреждений или возникновении ошибок, чтобы помочь в выявлении проблем с конфигурацией задачи.</span><span class="sxs-lookup"><span data-stu-id="b34bf-114">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer automatically calls the `Validate` method multiple times during package design, and provides visual cues to the user when warnings or errors occur to help identify problems with the configuration of the task.</span></span> <span data-ttu-id="b34bf-115">Задачи предоставляют результаты проверки, возвращая значение из перечисления <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> и формируя события с предупреждениями и ошибками.</span><span class="sxs-lookup"><span data-stu-id="b34bf-115">Tasks provide validation results by returning a value from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> enumeration, and by raising warning and error events.</span></span> <span data-ttu-id="b34bf-116">Эти события содержат сведения, которые отображаются пользователю в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b34bf-116">These events contain information that is displayed to the user in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>

 <span data-ttu-id="b34bf-117">Ниже приведены примеры проверки:</span><span class="sxs-lookup"><span data-stu-id="b34bf-117">Some examples for validation follow:</span></span>

-   <span data-ttu-id="b34bf-118">Диспетчер соединений проверяет имя определенного файла.</span><span class="sxs-lookup"><span data-stu-id="b34bf-118">A connection manager validates the specific file name.</span></span>

-   <span data-ttu-id="b34bf-119">Диспетчер соединений проверяет, является ли тип входа ожидаемым типом, например, XML-файлом.</span><span class="sxs-lookup"><span data-stu-id="b34bf-119">A connection manager validates that the type of input is the expected type, such as an XML file.</span></span>

-   <span data-ttu-id="b34bf-120">Задача, которой на входе необходима база данных, убеждается в невозможности получения данных из подключения, не являющегося подключением к базе данных.</span><span class="sxs-lookup"><span data-stu-id="b34bf-120">A task that expects database input verifies that it cannot receive data from a non-database connection.</span></span>

-   <span data-ttu-id="b34bf-121">Задача убеждается в отсутствии противоречий между заданными для нее свойствами.</span><span class="sxs-lookup"><span data-stu-id="b34bf-121">A task guarantees that none of its properties contradicts other properties set on the same task.</span></span>

-   <span data-ttu-id="b34bf-122">Задача убеждается в доступности всех необходимых ресурсов, используемых ею во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b34bf-122">A task guarantees that all required resources used by the task at execution time are available.</span></span>

 <span data-ttu-id="b34bf-123">Оценивая необходимость проверки тех или иных факторов, следует учитывать производительность системы.</span><span class="sxs-lookup"><span data-stu-id="b34bf-123">Performance is something to consider in determining what is validated and what is not.</span></span> <span data-ttu-id="b34bf-124">Например, входом задачи может быть соединение по сети с низкой пропускной способностью или большим трафиком.</span><span class="sxs-lookup"><span data-stu-id="b34bf-124">For example, the input to a task might be a connection over a network that has low bandwidth or heavy traffic.</span></span> <span data-ttu-id="b34bf-125">При выполнении проверки может потребоваться несколько секунд на обработку, если необходимо проверить доступность ресурса.</span><span class="sxs-lookup"><span data-stu-id="b34bf-125">The validation may take several seconds to process if you decide to validate that the resource is available.</span></span> <span data-ttu-id="b34bf-126">Еще одна проверка может привести к полном обходу сервера с высокой загрузкой, в результате выполнение проверки замедлится.</span><span class="sxs-lookup"><span data-stu-id="b34bf-126">Another validation may cause a round-trip to a server that is in high demand, and the validation routine might be slow.</span></span> <span data-ttu-id="b34bf-127">Хотя можно проверять многие из свойств и настроек, не все они нуждаются в проверке.</span><span class="sxs-lookup"><span data-stu-id="b34bf-127">Although there are many properties and settings that can be validated, not everything should be validated.</span></span>

-   <span data-ttu-id="b34bf-128">Код в методе `Validate` также вызывается сервером задач <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> перед выполнением задачи, и <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> отменяет выполнение задачи, если проверка завершается неуспешно.</span><span class="sxs-lookup"><span data-stu-id="b34bf-128">The code in the `Validate` method is also called by the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> before the task is run, and the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> cancels execution if validation fails.</span></span>

#### <a name="user-interface-considerations-during-validation"></a><span data-ttu-id="b34bf-129">Рекомендации по пользовательскому интерфейсу во время проверки</span><span class="sxs-lookup"><span data-stu-id="b34bf-129">User Interface Considerations during Validation</span></span>
 <span data-ttu-id="b34bf-130">[Microsoft. SqlServer. DTS. Runtime. Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) включает интерфейс в <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> качестве параметра `Validate` метода.</span><span class="sxs-lookup"><span data-stu-id="b34bf-130">The [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) includes an <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> interface as a parameter to the `Validate` method.</span></span> <span data-ttu-id="b34bf-131">Интерфейс <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> содержит методы, вызываемые задачей для формирования событий в обработчике среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="b34bf-131">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> interface contains the methods that are called by the task in order to raise events to the run-time engine.</span></span> <span data-ttu-id="b34bf-132">Методы <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A> и <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A> вызываются при возникновении ошибки или выдаче предупреждения во время проверки.</span><span class="sxs-lookup"><span data-stu-id="b34bf-132">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A> methods are called when a warning or error condition occurs during validation.</span></span> <span data-ttu-id="b34bf-133">Для обоих методов требуются одни и те же параметры. В их число входит код ошибки, исходный компонент, описание, файл справки и данные контекста справки.</span><span class="sxs-lookup"><span data-stu-id="b34bf-133">Both warning methods require the same parameters, which include an error code, source component, description, Help file, and Help context information.</span></span> <span data-ttu-id="b34bf-134">Конструктор служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] использует эти сведения для отображения визуальных подсказок в области конструктора.</span><span class="sxs-lookup"><span data-stu-id="b34bf-134">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer uses this information to display visual cues on the design surface.</span></span> <span data-ttu-id="b34bf-135">К визуальным подсказкам, предоставляемым конструктором, относится значок восклицания, который отображается рядом с задачей в области конструктора.</span><span class="sxs-lookup"><span data-stu-id="b34bf-135">The visual cues that are provided by the designer include an exclamation icon that appears next to the task on the designer surface.</span></span> <span data-ttu-id="b34bf-136">Эта визуальная подсказка указывает пользователю на то, что необходима дополнительная настройка задачи прежде, чем ее выполнение может быть продолжено.</span><span class="sxs-lookup"><span data-stu-id="b34bf-136">This visual cue signals to the user that the task requires additional configuration before execution can continue.</span></span>

 <span data-ttu-id="b34bf-137">Значок восклицания также отображает подсказку, содержащую сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="b34bf-137">The exclamation icon also displays a ToolTip that contains an error message.</span></span> <span data-ttu-id="b34bf-138">Сообщение об ошибке предоставляется задачей в параметре описания события.</span><span class="sxs-lookup"><span data-stu-id="b34bf-138">The error message is provided by the task in the description parameter of the event.</span></span> <span data-ttu-id="b34bf-139">Кроме того, сообщения об ошибках отображаются на панели **Список задач** среды [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], что позволяет пользователю просматривать все ошибки проверки в одном месте.</span><span class="sxs-lookup"><span data-stu-id="b34bf-139">Error messages are also displayed in the **Task List** pane of [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], providing the user with a central location for viewing all validation errors.</span></span>

#### <a name="validation-example"></a><span data-ttu-id="b34bf-140">Пример проверки</span><span class="sxs-lookup"><span data-stu-id="b34bf-140">Validation Example</span></span>
 <span data-ttu-id="b34bf-141">В следующем примере кода показана задача со свойством `UserName`.</span><span class="sxs-lookup"><span data-stu-id="b34bf-141">The following code example shows a task with a `UserName` property.</span></span> <span data-ttu-id="b34bf-142">Это свойство было задано как обязательное для успешного завершения проверки.</span><span class="sxs-lookup"><span data-stu-id="b34bf-142">This property has been specified as required for validation to succeed.</span></span> <span data-ttu-id="b34bf-143">Если свойство не задано, задача выдает ошибку и возвращает значение <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Failure> из перечисления <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult>.</span><span class="sxs-lookup"><span data-stu-id="b34bf-143">If the property is not set, the task posts an error, and returns <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Failure> from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> enumeration.</span></span> <span data-ttu-id="b34bf-144">Метод `Validate` упакован в блок Try/Catch и приводит к неуспешному завершению проверки при возникновении исключения.</span><span class="sxs-lookup"><span data-stu-id="b34bf-144">The `Validate` method is wrapped in a try/catch block, and fails validation if an exception occurs.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Runtime;

public class SampleTask : Task
{
  private string userName = "";

  public override DTSExecResult Validate(Connections connections,
     VariableDispenser variableDispenser, IDTSComponentEvents events,
     IDTSLogging log)
  {
    try
    {
      if (this.userName == "")
      {
        //   Raise an OnError event.
        events.FireError(0, "SampleTask", "The UserName property must be configured.", "", 0);
        //   Fail validation.
        return DTSExecResult.Failure;
      }
      //   Return success.
      return DTSExecResult.Success;
    }
    catch (System.Exception exception)
    {
      //   Capture exceptions, post an error, and fail validation.
      events.FireError(0, "Sampletask", exception.Message, "", 0);
      return DTSExecResult.Failure;
    }
  }
  public string UserName
  {
    get
    {
      return this.userName;
    }
    set
    {
      this.userName = value;
    }
  }
}
```

```vb
Imports System
Imports Microsoft.SqlServer.Dts.Runtime

Public Class SampleTask
  Inherits Task

  Private _userName As String = ""

  Public Overrides Function Validate(ByVal connections As Connections, _
     ByVal variableDispenser As VariableDispenser, _
     ByVal events As IDTSComponentEvents, _
     ByVal log As IDTSLogging) As DTSExecResult

    Try
      If Me._userName = "" Then
        '   Raise an OnError event.
        events.FireError(0, "SampleTask", "The UserName property must be configured.", "", 0)
        '   Fail validation.
        Return DTSExecResult.Failure
      End If
      '   Return success.
      Return DTSExecResult.Success
    Catch exception As System.Exception
      '   Capture exceptions, post an error, and fail validation.
      events.FireError(0, "Sampletask", exception.Message, "", 0)
      Return DTSExecResult.Failure
    End Try

  End Function

  Public Property UserName() As String
    Get
      Return Me._userName
    End Get
    Set(ByVal Value As String)
      Me._userName = Value
    End Set
  End Property

End Class
```

### <a name="persisting-the-task"></a><span data-ttu-id="b34bf-145">Сохранение задачи</span><span class="sxs-lookup"><span data-stu-id="b34bf-145">Persisting the Task</span></span>
 <span data-ttu-id="b34bf-146">Как правило, нет необходимости реализовывать для задачи пользовательскую сохраняемость.</span><span class="sxs-lookup"><span data-stu-id="b34bf-146">Ordinarily you do not have to implement custom persistence for a task.</span></span> <span data-ttu-id="b34bf-147">Нестандартный механизм сохраняемости необходим только в случае, когда свойства объекта используют сложные типы данных.</span><span class="sxs-lookup"><span data-stu-id="b34bf-147">Custom persistence is required only when the properties of an object use complex data types.</span></span> <span data-ttu-id="b34bf-148">Дополнительные сведения см. в разделе [Разработка пользовательских объектов для служб Integration Services](../developing-custom-objects-for-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="b34bf-148">For more information, see [Developing Custom Objects for Integration Services](../developing-custom-objects-for-integration-services.md).</span></span>

## <a name="executing-the-task"></a><span data-ttu-id="b34bf-149">Выполнение задачи</span><span class="sxs-lookup"><span data-stu-id="b34bf-149">Executing the Task</span></span>
 <span data-ttu-id="b34bf-150">В этом разделе описывается, как использовать метод `Execute`, который наследуется и переопределяется задачами.</span><span class="sxs-lookup"><span data-stu-id="b34bf-150">This section describes how to use the `Execute` method that is inherited and overridden by tasks.</span></span> <span data-ttu-id="b34bf-151">В разделе также поясняются различные способы предоставления сведений о результатах выполнения задачи.</span><span class="sxs-lookup"><span data-stu-id="b34bf-151">This section also explains various ways of providing information about the results of task execution.</span></span>

### <a name="execute-method"></a><span data-ttu-id="b34bf-152">Метод Execute</span><span class="sxs-lookup"><span data-stu-id="b34bf-152">Execute Method</span></span>
 <span data-ttu-id="b34bf-153">Задачи, содержащиеся в пакете, выполняются, когда среда выполнения служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] вызывает их метод `Execute`.</span><span class="sxs-lookup"><span data-stu-id="b34bf-153">Tasks that are contained in a package run when the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] runtime calls their `Execute` method.</span></span> <span data-ttu-id="b34bf-154">Задачи реализуют свою основную бизнес-логику и функциональные возможности в этом методе и предоставляют результаты выполнения путем отправки сообщений, возвращения значения из <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> перечисления и переопределения свойства свойства `get` `ExecutionValue` .</span><span class="sxs-lookup"><span data-stu-id="b34bf-154">Tasks implement their core business logic and functionality in this method, and provide the results of execution by posting messages, returning a value from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> enumeration, and overriding the property `get` of the `ExecutionValue` property.</span></span>

 <span data-ttu-id="b34bf-155">Базовый класс [Microsoft.SqlServer.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) предоставляет реализацию метода <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b34bf-155">The [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) base class provides a default implementation of the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> method.</span></span> <span data-ttu-id="b34bf-156">Пользовательские задачи переопределяют этот метод, чтобы определить собственную функциональность времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="b34bf-156">The custom tasks override this method to define their run-time functionality.</span></span> <span data-ttu-id="b34bf-157">Объект <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> упаковывает задачу, изолируя ее от обработчика среды выполнения и других объектов в пакете.</span><span class="sxs-lookup"><span data-stu-id="b34bf-157">The <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> object wraps the task, isolating it from the run-time engine and the other objects in the package.</span></span> <span data-ttu-id="b34bf-158">В результате этой изоляции задача не имеет сведений о своем местоположении в пакете с учетом порядка выполнения. Она выполняется только после вызова средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="b34bf-158">Because of this isolation, the task is unaware of its location in the package with regard to its execution order, and runs only when it is called by the runtime.</span></span> <span data-ttu-id="b34bf-159">Такая архитектура предотвращает проблемы, которые могут возникнуть при изменении задачами пакета в процессе выполнения.</span><span class="sxs-lookup"><span data-stu-id="b34bf-159">This architecture prevents problems that can occur when tasks modify the package during execution.</span></span> <span data-ttu-id="b34bf-160">Задаче предоставляется доступ к другим объектам в пакете только через объекты, передаваемые ей в качестве параметров в методе <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="b34bf-160">The task is provided access to the other objects in the package only through the objects supplied to it as parameters in the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> method.</span></span> <span data-ttu-id="b34bf-161">Эти параметры позволяют задачам вызывать события, делать записи в журнале событий, обращаться к коллекции Variables и прикреплять соединения к источникам данных в транзакциях, одновременно сохраняя изоляцию, которая необходима для обеспечения стабильности и надежности пакета.</span><span class="sxs-lookup"><span data-stu-id="b34bf-161">These parameters let tasks raise events, write entries to the event log, access the variables collection, and enlist connections to data sources in transactions, while still maintaining the isolation that is necessary to guarantee the stability and reliability of the package.</span></span>

 <span data-ttu-id="b34bf-162">В следующей таблице перечислены параметры, передаваемые задаче в методе <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="b34bf-162">The following table lists the parameters provided to the task in the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> method.</span></span>

|<span data-ttu-id="b34bf-163">Параметр</span><span class="sxs-lookup"><span data-stu-id="b34bf-163">Parameter</span></span>|<span data-ttu-id="b34bf-164">Описание</span><span class="sxs-lookup"><span data-stu-id="b34bf-164">Description</span></span>|
|---------------|-----------------|
|<xref:Microsoft.SqlServer.Dts.Runtime.Connections>|<span data-ttu-id="b34bf-165">Содержит коллекцию объектов <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>, доступных для задачи.</span><span class="sxs-lookup"><span data-stu-id="b34bf-165">Contains a collection of <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects available to the task.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Runtime.VariableDispenser>|<span data-ttu-id="b34bf-166">Содержит переменные, доступные для задачи.</span><span class="sxs-lookup"><span data-stu-id="b34bf-166">Contains the variables available to the task.</span></span> <span data-ttu-id="b34bf-167">Переменные используются задачами через свойство VariableDispenser, а не напрямую.</span><span class="sxs-lookup"><span data-stu-id="b34bf-167">The tasks use variables through the VariableDispenser; the tasks do not use variables directly.</span></span> <span data-ttu-id="b34bf-168">Свойство VariableDispenser осуществляет блокировку и разблокирование переменных, а также предотвращает взаимоблокировки или перезаписи.</span><span class="sxs-lookup"><span data-stu-id="b34bf-168">The variable dispenser locks and unlocks variables, and prevents deadlocks or overwrites.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents>|<span data-ttu-id="b34bf-169">Содержит методы, вызываемые задачей для вызова событий в обработчике среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="b34bf-169">Contains the methods called by the task to raise events to the run-time engine.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSLogging>|<span data-ttu-id="b34bf-170">Содержит методы и свойства, используемые задачей для внесения записей в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="b34bf-170">Contains methods and properties used by the task to write entries to the event log.</span></span>|
|<span data-ttu-id="b34bf-171">Объект</span><span class="sxs-lookup"><span data-stu-id="b34bf-171">Object</span></span>|<span data-ttu-id="b34bf-172">Содержит объект транзакции (при наличии такового), частью которого является контейнер.</span><span class="sxs-lookup"><span data-stu-id="b34bf-172">Contains the transaction object that the container is a part of, if any.</span></span> <span data-ttu-id="b34bf-173">Это значение передается в качестве параметра методу <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> объекта <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>.</span><span class="sxs-lookup"><span data-stu-id="b34bf-173">This value is passed as a parameter to the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method of a <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> object.</span></span>|

### <a name="providing-execution-feedback"></a><span data-ttu-id="b34bf-174">Обеспечение обратной связи при выполнении</span><span class="sxs-lookup"><span data-stu-id="b34bf-174">Providing Execution Feedback</span></span>
 <span data-ttu-id="b34bf-175">Задачи упаковывают свой код в блоки `try/catch`, чтобы предотвратить возникновение исключений в обработчике среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="b34bf-175">Tasks wrap their code in `try/catch` blocks to prevent exceptions from being raised to the run-time engine.</span></span> <span data-ttu-id="b34bf-176">Таким образом, гарантируется, что выполнение пакета будет завершено, и не произойдет неожиданной остановки.</span><span class="sxs-lookup"><span data-stu-id="b34bf-176">This ensures that the package finishes execution and does not stop unexpectedly.</span></span> <span data-ttu-id="b34bf-177">Однако обработчик среды выполнения предоставляет и другие механизмы обработки ошибок, которые могут возникать во время выполнения задачи.</span><span class="sxs-lookup"><span data-stu-id="b34bf-177">However, the run-time engine provides other mechanisms for handling error conditions that can occur during the execution of a task.</span></span> <span data-ttu-id="b34bf-178">К ним относится выдача сообщений об ошибках и предупреждений, возвращение значения из структуры <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult>, выдача сообщений, возвращение значения <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> и раскрытие сведений о результатах выполнения задачи с помощью свойства <xref:Microsoft.SqlServer.Dts.Runtime.Task.ExecutionValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="b34bf-178">These include posting error and warning messages, returning a value from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> structure, posting messages, returning the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> value, and disclosing information about the results of task execution through the <xref:Microsoft.SqlServer.Dts.Runtime.Task.ExecutionValue%2A> property.</span></span>

 <span data-ttu-id="b34bf-179">Интерфейс <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> содержит методы <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A> и <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A>, которые могут быть вызваны задачей для выдачи сообщений об ошибках и предупреждений в обработчике среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="b34bf-179">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> interface contains the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A> methods, which can be called by the task to post error and warning messages to the run-time engine.</span></span> <span data-ttu-id="b34bf-180">Обоим методам требуются такие параметры, как код ошибки, исходный компонент, описание, файл справки и данные контекста справки.</span><span class="sxs-lookup"><span data-stu-id="b34bf-180">Both methods require parameters such as the error code, source component, description, Help file, and help context information.</span></span> <span data-ttu-id="b34bf-181">В зависимости от конфигурации задачи, среда выполнения отвечает на эти сообщения, вызывая события и точки останова либо записывая данные в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="b34bf-181">Depending on the configuration of the task, the runtime responds to these messages by raising events and breakpoints, or by writing information to the event log.</span></span>

 <span data-ttu-id="b34bf-182">Объект <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> также предоставляет свойство <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A>, которое можно использовать для предоставления дополнительных сведений о результатах выполнения.</span><span class="sxs-lookup"><span data-stu-id="b34bf-182">The <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> also provides the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> property that can be used to provide additional information about the results of execution.</span></span> <span data-ttu-id="b34bf-183">Например, если задача удаляет строки из таблицы в рамках своего метода `Execute`, в качестве значения свойства <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> может быть возвращено число удаленных строк.</span><span class="sxs-lookup"><span data-stu-id="b34bf-183">For example, if a task deletes rows from a table as part of its `Execute` method, it might return the number of rows deleted as the value of the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> property.</span></span> <span data-ttu-id="b34bf-184">Кроме того, объект <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> предоставляет свойство <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecValueVariable%2A>.</span><span class="sxs-lookup"><span data-stu-id="b34bf-184">In addition, the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> provides the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecValueVariable%2A> property.</span></span> <span data-ttu-id="b34bf-185">С помощью этого свойства пользователь может сопоставить значение <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A>, возвращаемое задачей, с любой другой переменной, доступной для задачи.</span><span class="sxs-lookup"><span data-stu-id="b34bf-185">This property lets the user map the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> returned from the task to any variable visible to the task.</span></span> <span data-ttu-id="b34bf-186">Затем указанную переменную можно использовать для настройки элементов управления очередностью между задачами.</span><span class="sxs-lookup"><span data-stu-id="b34bf-186">The specified variable can then be used to establish precedence constraints between tasks.</span></span>

### <a name="execution-example"></a><span data-ttu-id="b34bf-187">Пример выполнения</span><span class="sxs-lookup"><span data-stu-id="b34bf-187">Execution Example</span></span>
 <span data-ttu-id="b34bf-188">В следующем примере кода показана реализация метода `Execute` и переопределенное свойство `ExecutionValue`.</span><span class="sxs-lookup"><span data-stu-id="b34bf-188">The following code example demonstrates an implementation of the `Execute` method, and shows an overridden `ExecutionValue` property.</span></span> <span data-ttu-id="b34bf-189">Задача удаляет файл, указанный свойством `fileName` задачи.</span><span class="sxs-lookup"><span data-stu-id="b34bf-189">The task deletes the file that is specified by the `fileName` property of the task.</span></span> <span data-ttu-id="b34bf-190">Задача выдает предупреждение, если файл не существует либо если свойство `fileName` является пустой строкой.</span><span class="sxs-lookup"><span data-stu-id="b34bf-190">The task posts a warning if the file does not exist, or if the `fileName` property is an empty string.</span></span> <span data-ttu-id="b34bf-191">Задача возвращает значение типа `Boolean` для свойства <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A>, чтобы указать, был ли файл удален.</span><span class="sxs-lookup"><span data-stu-id="b34bf-191">The task returns a `Boolean` value in the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.ExecutionValue%2A> property to indicate whether the file was deleted.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Runtime;

public class SampleTask : Task
{
  private string fileName = "";
  private bool fileDeleted = false;

  public override DTSExecResult Execute(Connections cons,
     VariableDispenser vars, IDTSComponentEvents events,
     IDTSLogging log, Object txn)
  {
    try
    {
      if (this.fileName == "")
      {
        events.FireWarning(0, "SampleTask", "No file specified.", "", 0);
        this.fileDeleted = false;
      }
      else
      {
        if (System.IO.File.Exists(this.fileName))
        {
          System.IO.File.Delete(this.fileName);
          this.fileDeleted = true;
        }
        else
          this.fileDeleted = false;
      }
      return DTSExecResult.Success;
    }
    catch (System.Exception exception)
    {
      //   Capture the exception and post an error.
      events.FireError(0, "Sampletask", exception.Message, "", 0);
      return DTSExecResult.Failure;
    }
  }
  public string FileName
  {
    get { return this.fileName; }
    set { this.fileName = value; }
  }
  public override object ExecutionValue
  {
    get { return this.fileDeleted; }
  }
}
```

```vb
Imports System
Imports Microsoft.SqlServer.Dts.Runtime

Public Class SampleTask
  Inherits Task

  Private _fileName As String = ""
  Private _fileDeleted As Boolean = False

  Public Overrides Function Execute(ByVal cons As Connections, _
     ByVal vars As VariableDispenser, ByVal events As IDTSComponentEvents, _
     ByVal log As IDTSLogging, ByVal txn As Object) As DTSExecResult

    Try
      If Me._fileName = "" Then
        events.FireWarning(0, "SampleTask", "No file specified.", "", 0)
        Me._fileDeleted = False
      Else
        If System.IO.File.Exists(Me._fileName) Then
          System.IO.File.Delete(Me._fileName)
          Me._fileDeleted = True
        Else
          Me._fileDeleted = False
        End If
      End If
      Return DTSExecResult.Success
    Catch exception As System.Exception
      '   Capture the exception and post an error.
      events.FireError(0, "Sampletask", exception.Message, "", 0)
      Return DTSExecResult.Failure
    End Try

  End Function

  Public Property FileName() As String
    Get
      Return Me._fileName
    End Get
    Set(ByVal Value As String)
      Me._fileName = Value
    End Set
  End Property

  Public Overrides ReadOnly Property ExecutionValue() As Object
    Get
      Return Me._fileDeleted
    End Get
  End Property

End Class
```

<span data-ttu-id="b34bf-192">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="b34bf-192">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="b34bf-193">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="b34bf-193">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="b34bf-194">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="b34bf-194">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="b34bf-195">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="b34bf-195">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="b34bf-196">См. также:</span><span class="sxs-lookup"><span data-stu-id="b34bf-196">See Also</span></span>
 <span data-ttu-id="b34bf-197">[Создание](creating-a-custom-task.md) пользовательского [кода](coding-a-custom-task.md) настраиваемой задачи [Разработка пользовательского интерфейса для пользовательской задачи](developing-a-user-interface-for-a-custom-task.md)</span><span class="sxs-lookup"><span data-stu-id="b34bf-197">[Creating a Custom Task](creating-a-custom-task.md) [Coding a Custom Task](coding-a-custom-task.md) [Developing a User Interface for a Custom Task](developing-a-user-interface-for-a-custom-task.md)</span></span>


