---
title: Программная работа с переменными | Документы Майкрософт
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
- System namespace
- scope [Integration Services]
- variables [Integration Services], programmatically
- configuration files [Integration Services]
- Variables collection
- User namespace
- custom variables [Integration Services]
- variables [Integration Services], customizing
ms.assetid: c4b76a3d-94ca-4a8e-bb45-cb8bd0ea3ec1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2c903ee6adb8989eaeb93efbe943eca93c73eae4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738681"
---
# <a name="working-with-variables-programmatically"></a><span data-ttu-id="9d1a9-102">Программная работа с переменными</span><span class="sxs-lookup"><span data-stu-id="9d1a9-102">Working with Variables Programmatically</span></span>
  <span data-ttu-id="9d1a9-103">С помощью переменных можно динамически задавать значения и управлять процессами в пакетах, контейнерах, задачах и обработчиках событий.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-103">Variables are a way to dynamically set values and control processes in packages, containers, tasks, and event handlers.</span></span> <span data-ttu-id="9d1a9-104">Переменные могут также использоваться элементами управления очередностью для управления направлением потока данных к различным задачам.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-104">Variables can also be used by precedence constraints to control the direction of the flow of data to different tasks.</span></span> <span data-ttu-id="9d1a9-105">С помощью переменных можно:</span><span class="sxs-lookup"><span data-stu-id="9d1a9-105">Variables have a variety of uses:</span></span>

-   <span data-ttu-id="9d1a9-106">Обновлять свойства пакета во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-106">Update properties of a package at run time.</span></span>

-   <span data-ttu-id="9d1a9-107">Заполнять значения параметров инструкций Transact-SQL во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-107">Populate parameter values for Transact-SQL statements at run time.</span></span>

-   <span data-ttu-id="9d1a9-108">Управлять потоком цикла по каждому элементу.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-108">Control the flow of a Foreach loop.</span></span> <span data-ttu-id="9d1a9-109">Дополнительные сведения см. в разделе [Добавление перечисления к потоку управления](../control-flow/control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="9d1a9-109">For more information, see [Add Enumeration to a Control Flow](../control-flow/control-flow.md).</span></span>

-   <span data-ttu-id="9d1a9-110">Управлять управлением очередностью, используя его в выражении.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-110">Control a precedence constraint by its use in an expression.</span></span> <span data-ttu-id="9d1a9-111">Управление очередностью может содержать переменные в определении ограничения.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-111">A precedence constraint can include variables in the constraint definition.</span></span> <span data-ttu-id="9d1a9-112">Дополнительные сведения см. в статье [Добавление выражений к элементам управления очередностью](../control-flow/precedence-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="9d1a9-112">For more information, see [Add Expressions to Precedence Constraints](../control-flow/precedence-constraints.md).</span></span>

-   <span data-ttu-id="9d1a9-113">Управлять условным повторением контейнера «цикл по элементам».</span><span class="sxs-lookup"><span data-stu-id="9d1a9-113">Control the conditional repeat of a For Loop container.</span></span> <span data-ttu-id="9d1a9-114">Дополнительные сведения см. в разделе [Добавление итерации к потоку управления](../add-iteration-to-a-control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="9d1a9-114">For more information, see [Add Iteration to a Control Flow](../add-iteration-to-a-control-flow.md).</span></span>

-   <span data-ttu-id="9d1a9-115">Строить выражения, содержащие значения переменных.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-115">Build expressions that include variable values.</span></span>

-   <span data-ttu-id="9d1a9-116">Пользователь может создать пользовательские переменные для всех типов контейнеров: пакетов, контейнеров **цикл по каждому элементу**, контейнеров **цикл по элементам**, контейнеров **последовательности**, серверов задач и обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-116">You can create custom variables for all container types: packages, **Foreach Loop** containers, **For Loop** containers, **Sequence** containers, TaskHosts, and event handlers.</span></span> <span data-ttu-id="9d1a9-117">Дополнительные сведения см. в разделах [Переменные в службах Integration Services (SSIS)](../integration-services-ssis-variables.md) и [Использование переменных в пакетах](../use-variables-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="9d1a9-117">For more information, see [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) and [Use Variables in Packages](../use-variables-in-packages.md).</span></span>

## <a name="scope"></a><span data-ttu-id="9d1a9-118">Область</span><span class="sxs-lookup"><span data-stu-id="9d1a9-118">Scope</span></span>
 <span data-ttu-id="9d1a9-119">Каждый контейнер имеет собственную коллекцию <xref:Microsoft.SqlServer.Dts.Runtime.Variables>.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-119">Each container has its own <xref:Microsoft.SqlServer.Dts.Runtime.Variables> collection.</span></span> <span data-ttu-id="9d1a9-120">При создании новой переменной она располагается в области своего родительского контейнера.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-120">When a new variable is created, it is within the scope of its parent container.</span></span> <span data-ttu-id="9d1a9-121">Поскольку контейнер пакета находится на верхнем уровне иерархии контейнеров, переменные в области пакета ведут себя как глобальные переменные и могут использоваться во всех контейнерах пакета.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-121">Because the package container is at the top of the container hierarchy, variables with package scope function like global variables, and are visible to all containers within the package.</span></span> <span data-ttu-id="9d1a9-122">Доступ к коллекции переменных для контейнера могут также получать дочерние элементы контейнера через коллекцию <xref:Microsoft.SqlServer.Dts.Runtime.Variables>, используя имя переменной или ее индекс в коллекции.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-122">The collection of variables for the container can also be accessed by the children of the container through the <xref:Microsoft.SqlServer.Dts.Runtime.Variables> collection, by using either the variable name or the variable's index in the collection.</span></span>

 <span data-ttu-id="9d1a9-123">Поскольку доступность переменной определяется сверху вниз, переменные, объявленные на уровне пакета, являются доступными для всех контейнеров в пакете.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-123">Because the visibility of a variable is scoped from the top down, variables declared at the package level are visible to all the containers in the package.</span></span> <span data-ttu-id="9d1a9-124">Таким образом, коллекция <xref:Microsoft.SqlServer.Dts.Runtime.Variables> в контейнере включает все переменные, принадлежащие родительской коллекции, в дополнение к своим собственным.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-124">Therefore, the <xref:Microsoft.SqlServer.Dts.Runtime.Variables> collection on a container includes all the variables that belong to its parent in addition to its own variables</span></span>

 <span data-ttu-id="9d1a9-125">С другой стороны, переменные, содержащиеся в задаче, ограничены по области применения и доступности и доступны только задаче.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-125">Conversely, the variables that are contained in a task are limited in scope and visibility, and are only visible to the task.</span></span>

 <span data-ttu-id="9d1a9-126">Если пакет выполняет другие пакеты, переменные, определенные в области вызывающего пакета, доступны для вызываемого пакета.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-126">If a package runs other packages, the variables defined in the scope of the calling package are available to the called package.</span></span> <span data-ttu-id="9d1a9-127">Единственным исключением является случай, когда в вызываемом пакете существует переменная с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-127">The only exception occurs when a same-named variable exists in the called package.</span></span> <span data-ttu-id="9d1a9-128">При возникновении такой коллизии значение переменной из вызываемого пакета переопределяет значение переменной из вызывающего пакета.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-128">When this collision occurs, the variable value in the called package overrides the value from the calling package.</span></span> <span data-ttu-id="9d1a9-129">Переменные, определенные в области вызываемого пакета, недоступны для вызывающего пакета.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-129">Variables defined in the scope of the called package are never available back to the calling package.</span></span>

 <span data-ttu-id="9d1a9-130">В следующем примере кода программным способом создается переменная `myCustomVar` в области пакета, а затем просматриваются все переменные, доступные для пакета, выводятся на печать их имена, тип данных и значения.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-130">The following code example programmatically creates a variable, `myCustomVar`, at the package scope, and then iterates through all the variables visible to the package, printing their name, data type, and value.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.SqlServer.Dts.Samples
{
  class Program
  {
    static void Main(string[] args)
    {
      Application app = new Application();
      // Load a sample package that contains a variable that sets the file name.
      Package pkg = app.LoadPackage(
        @"C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" +
        @"\Package Samples\CaptureDataLineage Sample\CaptureDataLineage\CaptureDataLineage.dtsx",
        null);
      Variables pkgVars = pkg.Variables;
      Variable myVar = pkg.Variables.Add("myCustomVar", false, "User", "3");
      foreach (Variable pkgVar in pkgVars)
      {
        Console.WriteLine("Variable: {0}, {1}, {2}", pkgVar.Name,
          pkgVar.DataType, pkgVar.Value.ToString());
      }
      Console.Read();
    }
  }
}
```

```vb
Imports Microsoft.SqlServer.Dts.Runtime

Module Module1

  Sub Main()

    Dim app As Application = New Application()
    ' Load a sample package that contains a variable that sets the file name.
    Dim pkg As Package = app.LoadPackage( _
      "C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" & _
      "\Package Samples\CaptureDataLineage Sample\CaptureDataLineage\CaptureDataLineage.dtsx", _
      Nothing)
    Dim pkgVars As Variables = pkg.Variables
    Dim myVar As Variable = pkg.Variables.Add("myCustomVar", False, "User", "3")
    Dim pkgVar As Variable
    For Each pkgVar In pkgVars
      Console.WriteLine("Variable: {0}, {1}, {2}", pkgVar.Name, _
        pkgVar.DataType, pkgVar.Value.ToString())
    Next
    Console.Read()

  End Sub

End Module
```

 <span data-ttu-id="9d1a9-131">**Образец вывода:**</span><span class="sxs-lookup"><span data-stu-id="9d1a9-131">**Sample Output:**</span></span>

 `Variable: CancelEvent, Int32, 0`

 `Variable: CreationDate, DateTime, 4/18/2003 11:57:00 AM`

 `Variable: CreatorComputerName, String,`

 `Variable: CreatorName, String,`

 `Variable: ExecutionInstanceGUID, String, {237AB5A4-7E59-4FC9-8D61-E8F20363DF25}`

 `Variable: FileName, String, Junk`

 `Variable: InteractiveMode, Boolean, False`

 `Variable: LocaleID, Int32, 1033`

 `Variable: MachineName, String, MYCOMPUTERNAME`

 `Variable: myCustomVar, String, 3`

 `Variable: OfflineMode, Boolean, False`

 `Variable: PackageID, String, {F0D2E396-A6A5-42AE-9467-04CE946A810C}`

 `Variable: PackageName, String, DTSPackage1`

 `Variable: StartTime, DateTime, 1/28/2005 7:55:39 AM`

 `Variable: UserName, String, <domain>\<userid>`

 `Variable: VersionBuild, Int32, 198`

 `Variable: VersionComments, String,`

 `Variable: VersionGUID, String, {90E105B4-B4AF-4263-9CBD-C2050C2D6148}`

 `Variable: VersionMajor, Int32, 1`

 `Variable: VersionMinor, Int32, 0`

 <span data-ttu-id="9d1a9-132">Обратите внимание, что все переменные, определенные в пространстве имен **System**, доступны для пакета.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-132">Notice that all the variables scoped in the **System** namespace are available to the package.</span></span> <span data-ttu-id="9d1a9-133">Дополнительные сведения см. в статье [System Variables](../system-variables.md).</span><span class="sxs-lookup"><span data-stu-id="9d1a9-133">For more information, see [System Variables](../system-variables.md).</span></span>

## <a name="namespaces"></a><span data-ttu-id="9d1a9-134">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="9d1a9-134">Namespaces</span></span>
 <span data-ttu-id="9d1a9-135">Службы [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) предоставляют два пространства имен по умолчанию, в которых располагаются переменные, — **User** и **System**.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-135">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) provides two default namespaces where variables reside; **User** and **System** namespaces.</span></span> <span data-ttu-id="9d1a9-136">По умолчанию любая пользовательская переменная, созданная разработчиком, добавляется в пространство имен **User**.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-136">By default, any custom variable created by the developer is added to the **User** namespace.</span></span> <span data-ttu-id="9d1a9-137">Системные переменные располагаются в пространстве имен **System**.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-137">System variables reside in the **System** namespace.</span></span> <span data-ttu-id="9d1a9-138">Можно создавать дополнительные пространства имен, отличные от **User**, для размещения пользовательских переменных. Также можно изменить имя пространства имен **User**. В то же время нельзя добавить или изменить переменные в пространстве имен **System** или назначить системные переменные другому пространству имен.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-138">You can create additional namespaces other than the **User** namespace to hold custom variables, and you can change the name of the **User** namespace, but you cannot add or modify variables in the **System** namespace, or assign system variables to a different namespace.</span></span>

 <span data-ttu-id="9d1a9-139">Доступность системных переменных определяется типом контейнера.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-139">The system variables that are available differ depending on the container type.</span></span> <span data-ttu-id="9d1a9-140">Список системных переменных, доступных для пакетов, контейнеров, задач и обработчиков событий, см. в разделе [Системные переменные](../system-variables.md).</span><span class="sxs-lookup"><span data-stu-id="9d1a9-140">For a list of the system variables available to packages, containers, tasks, and event handlers, see [System Variables](../system-variables.md).</span></span>

## <a name="value"></a><span data-ttu-id="9d1a9-141">Значение</span><span class="sxs-lookup"><span data-stu-id="9d1a9-141">Value</span></span>
 <span data-ttu-id="9d1a9-142">Значением пользовательской переменной может быть строка или выражение.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-142">The value of a custom variable can be a literal or an expression:</span></span>

-   <span data-ttu-id="9d1a9-143">Если необходимо задать для переменной литеральное значение, укажите значение ее свойства <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-143">If you want the variable to contain a literal value, set the value of its <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A> property.</span></span>

-   <span data-ttu-id="9d1a9-144">Если необходимо, чтобы переменная содержала выражение, результаты которого использовались бы в качестве ее значения, присвойте свойству <xref:Microsoft.SqlServer.Dts.Runtime.Variable.EvaluateAsExpression%2A> переменной значение `true` и предоставьте выражение в свойстве <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Expression%2A>.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-144">If you want the variable to contain an expression, so that you can use the results of the expression as its value, set the <xref:Microsoft.SqlServer.Dts.Runtime.Variable.EvaluateAsExpression%2A> property of the variable to `true`, and provide an expression in the <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Expression%2A> property.</span></span> <span data-ttu-id="9d1a9-145">Во время выполнения выражение вычисляется, и его результат используется в качестве значения переменной.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-145">At run time, the expression is evaluated, and the result of the expression is used as the value of the variable.</span></span> <span data-ttu-id="9d1a9-146">Например, если свойство выражения переменной имеет вид `"100 * 2""100 * 2"`, в результате вычисления переменная получает значение 200.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-146">For example, if the expression property of a variable is `"100 * 2""100 * 2"`, the variable evaluates to a value of 200.</span></span>

 <span data-ttu-id="9d1a9-147">Для переменной нельзя явно задать значение <xref:Microsoft.SqlServer.Dts.Runtime.Variable.DataType%2A>.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-147">For a variable, you cannot explicitly set the value of its <xref:Microsoft.SqlServer.Dts.Runtime.Variable.DataType%2A>.</span></span> <span data-ttu-id="9d1a9-148">Значение <xref:Microsoft.SqlServer.Dts.Runtime.Variable.DataType%2A> выводится из исходного значения, присвоенного переменной, и в дальнейшем не может быть изменено.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-148">The <xref:Microsoft.SqlServer.Dts.Runtime.Variable.DataType%2A> value is inferred from the initial value assigned to the variable, and cannot be changed afterward.</span></span> <span data-ttu-id="9d1a9-149">Дополнительные сведения о типах данных переменных см. в разделе [Типы данных служб Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="9d1a9-149">For more information about variable data types, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>

 <span data-ttu-id="9d1a9-150">В следующем примере кода создается новая переменная, свойству <xref:Microsoft.SqlServer.Dts.Runtime.Variable.EvaluateAsExpression%2A> присваивается значение `true`, выражение `"100 * 2"` назначается в качестве значения свойства Expression переменной, а затем выводится значение переменной.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-150">The following code example creates a new variable, sets <xref:Microsoft.SqlServer.Dts.Runtime.Variable.EvaluateAsExpression%2A> to `true`, assigns the expression `"100 * 2"` to the expression property of the variable, and then outputs the value of the variable.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.SqlServer.Dts.Samples
{
  class Program
  {
    static void Main(string[] args)
    {
      Package pkg = new Package();
      Variable v100 = pkg.Variables.Add("myVar", false, "", 1);
      v100.EvaluateAsExpression = true;
      v100.Expression = "100 * 2";
      Console.WriteLine("Expression for myVar: {0}", 
        v100.Properties["Expression"].GetValue(v100));
      Console.WriteLine("Value of myVar: {0}", v100.Value.ToString());
      Console.Read();
    }
  }
}
```

```vb
Imports Microsoft.SqlServer.Dts.Runtime

Module Module1

  Sub Main()

    Dim pkg As Package = New Package
    Dim v100 As Variable = pkg.Variables.Add("myVar", False, "", 1)
    v100.EvaluateAsExpression = True
    v100.Expression = "100 * 2"
    Console.WriteLine("Expression for myVar: {0}", _
      v100.Properties("Expression").GetValue(v100))
    Console.WriteLine("Value of myVar: {0}", v100.Value.ToString)
    Console.Read()

  End Sub

End Module
```

 <span data-ttu-id="9d1a9-151">**Образец вывода:**</span><span class="sxs-lookup"><span data-stu-id="9d1a9-151">**Sample Output:**</span></span>

 `Expression for myVar: 100 * 2`

 `Value of myVar: 200`

 <span data-ttu-id="9d1a9-152">Выражение должно быть действительным выражением, использующим синтаксис выражений служб [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9d1a9-152">The expression must be a valid expression that uses the [!INCLUDE[ssIS](../../includes/ssis-md.md)] expression syntax.</span></span> <span data-ttu-id="9d1a9-153">Литералы допускаются в выражениях переменных, в дополнение к операторам и функциям, которые предоставляются синтаксисом выражений, однако выражения не могут ссылаться на другие переменные или столбцы.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-153">Literals are permitted in variable expressions, in addition to the operators and functions that the expression syntax provides, but expressions cannot reference other variables or columns.</span></span> <span data-ttu-id="9d1a9-154">Дополнительные сведения см. в разделе [Выражения служб Integration Services (SSIS)](../expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="9d1a9-154">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../expressions/integration-services-ssis-expressions.md).</span></span>

## <a name="configuration-files"></a><span data-ttu-id="9d1a9-155">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="9d1a9-155">Configuration Files</span></span>
 <span data-ttu-id="9d1a9-156">Если в файле конфигурации содержится пользовательская переменная, эта переменная может быть обновлена во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-156">If a configuration file includes a custom variable, the variable can be updated at run time.</span></span> <span data-ttu-id="9d1a9-157">Это означает, что при выполнении пакета значение переменной, содержавшееся в пакете изначально, заменяется новым значением из файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-157">What this means is that when the package runs, the value of the variable originally in the package is replaced with a new value from the configuration file.</span></span> <span data-ttu-id="9d1a9-158">Такой способ замены оказывается полезным, когда пакет развертывается на нескольких серверах, где требуются разные значения переменной.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-158">This replacement technique is useful when a package is deployed to multiple servers that require different variable values.</span></span> <span data-ttu-id="9d1a9-159">Например, переменная может содержать число повторений рабочего процесса контейнера **цикл по каждому элементу**, список получателей, которым обработчик событий направляет сообщения электронной почты при возникновении ошибки, либо измененное максимально допустимое число ошибок перед завершением выполнения пакета со сбоем.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-159">For example, a variable can specify the number of times a **Foreach Loop** container repeats its workflow, or list the recipients that an event handler sends e-mail to when an error is raised, or change the number of errors that can occur before the package fails.</span></span> <span data-ttu-id="9d1a9-160">Эти переменные динамически передаются в файлах конфигурации для каждой среды.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-160">These variables are dynamically provided in configuration files for each environment.</span></span> <span data-ttu-id="9d1a9-161">По этой причине в файлах конфигурации допускается использование только переменных, доступных для чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-161">Therefore, only variables that are read/write are allowed in configuration files.</span></span> <span data-ttu-id="9d1a9-162">Дополнительные сведения см. в разделе [Создание конфигурации пакетов](../create-package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="9d1a9-162">For more information, see [Create Package Configurations](../create-package-configurations.md).</span></span>

<span data-ttu-id="9d1a9-163">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="9d1a9-163">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="9d1a9-164">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="9d1a9-164">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="9d1a9-165">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="9d1a9-165">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="9d1a9-166">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="9d1a9-166">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="9d1a9-167">См. также:</span><span class="sxs-lookup"><span data-stu-id="9d1a9-167">See Also</span></span>
 <span data-ttu-id="9d1a9-168">[Integration Services &#40;переменные&#41; служб SSIS](../integration-services-ssis-variables.md) [используют переменные в пакетах](../use-variables-in-packages.md)</span><span class="sxs-lookup"><span data-stu-id="9d1a9-168">[Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) [Use Variables in Packages](../use-variables-in-packages.md)</span></span>


