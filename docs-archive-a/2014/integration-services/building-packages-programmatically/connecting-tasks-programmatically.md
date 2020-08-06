---
title: Соединение задач программным образом | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- tasks [Integration Services], precedence constraints
- precedence constraints [Integration Services], connecting tasks
- constraints [Integration Services]
ms.assetid: 23668e88-cef4-4009-a9cf-38e607eab7a2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5aeeb70ed5741cc7372fdfc63e637fd53d932f91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658357"
---
# <a name="connecting-tasks-programmatically"></a><span data-ttu-id="7510a-102">Соединение задач программным образом</span><span class="sxs-lookup"><span data-stu-id="7510a-102">Connecting Tasks Programmatically</span></span>
  <span data-ttu-id="7510a-103">Управление очередностью, представленное в объектной модели классом <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>, устанавливает порядок запуска объектов <xref:Microsoft.SqlServer.Dts.Runtime.Executable> в пакете.</span><span class="sxs-lookup"><span data-stu-id="7510a-103">A precedence constraint, represented in the object model by the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> class, establishes the order in which <xref:Microsoft.SqlServer.Dts.Runtime.Executable> objects run in a package.</span></span> <span data-ttu-id="7510a-104">Управление очередностью позволяет установить зависимость выполнения контейнеров и задач в пакете от результата выполнения предыдущего контейнера или задачи.</span><span class="sxs-lookup"><span data-stu-id="7510a-104">The precedence constraint allows the execution of the containers and tasks in a package to be dependent on the result of the execution of a previous task or container.</span></span> <span data-ttu-id="7510a-105">Элементы управления очередностью устанавливаются между парами объектов <xref:Microsoft.SqlServer.Dts.Runtime.Executable> путем вызова метода <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraints.Add%2A> коллекции <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraints> объекта-контейнера.</span><span class="sxs-lookup"><span data-stu-id="7510a-105">Precedence constraints are established between pairs of <xref:Microsoft.SqlServer.Dts.Runtime.Executable> objects by calling the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraints.Add%2A> method of the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraints> collection on the container object.</span></span> <span data-ttu-id="7510a-106">После создания ограничения между двумя исполняемыми объектами необходимо задать значение свойства <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A>, устанавливающего критерии выполнения второго исполняемого объекта, определенного в ограничении.</span><span class="sxs-lookup"><span data-stu-id="7510a-106">After you create a constraint between two executable objects, you set the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> property to establish the criteria for executing the second executable defined in the constraint.</span></span>  
  
 <span data-ttu-id="7510a-107">В зависимости от значения, заданного свойству <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.EvalOp%2A>, можно использовать одновременно и ограничение, и выражение в одном и том же управлении очередностью, как описано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="7510a-107">You can use both a constraint and an expression in a single precedence constraint, depending on the value that you specify for the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.EvalOp%2A> property, as described in the following table:</span></span>  
  
|<span data-ttu-id="7510a-108">Значение свойства EvalOp</span><span class="sxs-lookup"><span data-stu-id="7510a-108">Value of the EvalOp property</span></span>|<span data-ttu-id="7510a-109">Description</span><span class="sxs-lookup"><span data-stu-id="7510a-109">Description</span></span>|  
|----------------------------------|-----------------|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DTSPrecedenceEvalOp.Constraint>|<span data-ttu-id="7510a-110">Указывает, что результат выполнения определяет, будет ли запущен связанный ограничением контейнер или задача.</span><span class="sxs-lookup"><span data-stu-id="7510a-110">Specifies that the execution outcome determines whether the constrained container or task runs.</span></span> <span data-ttu-id="7510a-111">Задайте свойству <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> объекта <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> необходимое значение из перечисления <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult>.</span><span class="sxs-lookup"><span data-stu-id="7510a-111">Set the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> property of the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> to the desired value from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> enumeration.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DTSPrecedenceEvalOp.Expression>|<span data-ttu-id="7510a-112">Указывает, что значение выражения определяет, будет ли запущен связанный ограничением контейнер или задача.</span><span class="sxs-lookup"><span data-stu-id="7510a-112">Specifies that the value of an expression determines whether the constrained container or task runs.</span></span> <span data-ttu-id="7510a-113">Задайте значение свойства <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A> объекта <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>.</span><span class="sxs-lookup"><span data-stu-id="7510a-113">Set the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A> property of the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DTSPrecedenceEvalOp.ExpressionAndConstraint>|<span data-ttu-id="7510a-114">Указывает, что связанный ограничением контейнер или задача будут выполнены, если выполнится ограничение и выражение вернет положительный результат.</span><span class="sxs-lookup"><span data-stu-id="7510a-114">Specifies that the constraint outcome must occur and the expression must evaluate for the constrained container or task to run.</span></span> <span data-ttu-id="7510a-115">Установите свойства <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> и <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A> объекта <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>, а свойство <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.LogicalAnd%2A> установите в значение `true`.</span><span class="sxs-lookup"><span data-stu-id="7510a-115">Set both the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> and the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A> properties of the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>, and set its <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.LogicalAnd%2A> property to `true`.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DTSPrecedenceEvalOp.ExpressionOrConstraint>|<span data-ttu-id="7510a-116">Указывает, что связанный ограничением контейнер или задача будут выполнены, если выполнится ограничение либо выражение вернет положительный результат.</span><span class="sxs-lookup"><span data-stu-id="7510a-116">Specifies that either the constraint outcome must occur, or the expression must evaluate, for the constrained container or task to run.</span></span> <span data-ttu-id="7510a-117">Установите свойства <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> и <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A> объекта <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>, а свойство <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.LogicalAnd%2A> установите в значение `false`.</span><span class="sxs-lookup"><span data-stu-id="7510a-117">Set both the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> and the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A> properties of the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>, and set its <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.LogicalAnd%2A> property to `false`.</span></span>|  
  
 <span data-ttu-id="7510a-118">Следующий образец кода демонстрирует добавление двух задач в пакет.</span><span class="sxs-lookup"><span data-stu-id="7510a-118">The following code sample demonstrates adding two tasks to a package.</span></span> <span data-ttu-id="7510a-119">Между ними создается управление очередностью <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>, препятствующее выполнению второй задачи до завершения первой.</span><span class="sxs-lookup"><span data-stu-id="7510a-119">A <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> is created between them that prevents the second task from running until the first task finishes.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package p = new Package();  
  
      // Add a File System task.  
      Executable eFileTask1 = p.Executables.Add("STOCK:FileSystemTask");  
      TaskHost thFileHost1 = eFileTask1 as TaskHost;  
  
      // Add a second File System task.  
      Executable eFileTask2 = p.Executables.Add("STOCK:FileSystemTask");  
      TaskHost thFileHost2 = eFileTask2 as TaskHost;  
  
      // Put a precedence constraint between the tasks.  
      // Set the constraint to specify that the second File System task cannot run  
      // until the first File System task finishes.  
      PrecedenceConstraint pcFileTasks =   
        p.PrecedenceConstraints.Add((Executable)thFileHost1, (Executable)thFileHost2);  
      pcFileTasks.Value = DTSExecResult.Completion;  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim p As Package = New Package()  
    ' Add a File System task.  
    Dim eFileTask1 As Executable = p.Executables.Add("STOCK:FileSystemTask")  
    Dim thFileHost1 As TaskHost = CType(eFileTask1, TaskHost)  
  
    ' Add a second File System task.  
    Dim eFileTask2 As Executable = p.Executables.Add("STOCK:FileSystemTask")  
    Dim thFileHost2 As TaskHost = CType(eFileTask2, TaskHost)  
  
    ' Put a precedence constraint between the tasks.  
    ' Set the constraint to specify that the second File System task cannot run  
    ' until the first File System task finishes.  
    Dim pcFileTasks As PrecedenceConstraint = _  
      p.PrecedenceConstraints.Add(CType(thFileHost1, Executable), CType(thFileHost2, Executable))  
    pcFileTasks.Value = DTSExecResult.Completion  
  
  End Sub  
  
End Module  
```  
  
<span data-ttu-id="7510a-120">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="7510a-120">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="7510a-121">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="7510a-121">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="7510a-122">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="7510a-122">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="7510a-123">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="7510a-123">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7510a-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="7510a-124">See Also</span></span>  
 [<span data-ttu-id="7510a-125">Добавление задачи потока данных программным образом</span><span class="sxs-lookup"><span data-stu-id="7510a-125">Adding the Data Flow Task Programmatically</span></span>](../building-packages-programmatically/adding-the-data-flow-task-programmatically.md)  
  
  
