---
title: Кодирование и отладка компонента скрипта | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- SSIS Script task, development environment
- Script component [Integration Services], debugging
- Script component [Integration Services], coding
- SSIS Script component, debugging
- Script component [Integration Services], development environment
- debugging [Integration Services], scripts
- SSIS Script component, coding
- VSTA
ms.assetid: c3913c15-66aa-4b61-89b5-68488fa5f0a4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9363ad447ca3d0031289eafb1d8f616320fca5b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665437"
---
# <a name="coding-and-debugging-the-script-component"></a><span data-ttu-id="51e42-102">Кодирование и отладка компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="51e42-102">Coding and Debugging the Script Component</span></span>
  <span data-ttu-id="51e42-103">В конструкторе [!INCLUDE[ssIS](../../../includes/ssis-md.md)] у компонента Script есть два режима: режим конструирования метаданных и режим конструирования кода.</span><span class="sxs-lookup"><span data-stu-id="51e42-103">In [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, the Script component has two modes: metadata design mode and code design mode.</span></span> <span data-ttu-id="51e42-104">Когда открывается **редактор преобразования "Скрипт"** , компонент переключается в режим конструктора метаданных, в котором настраиваются метаданные и задаются свойства компонентов.</span><span class="sxs-lookup"><span data-stu-id="51e42-104">When you open the **Script Transformation Editor**, the component enters metadata design mode, in which you configure metadata and set component properties.</span></span> <span data-ttu-id="51e42-105">После того как будут заданы свойства компонента скрипта и настроены входы и выходы в режиме конструктора метаданных, можно переключиться в режим редактирования кода для составления пользовательского скрипта.</span><span class="sxs-lookup"><span data-stu-id="51e42-105">After you have set the properties of the Script component and configured the input and outputs in metadata design mode, you can switch to code design mode to write your custom script.</span></span> <span data-ttu-id="51e42-106">Дополнительные сведения о режимах конструктора метаданных и кода см. в разделе [Настройка компонента скрипта в редакторе компонента скрипта](configuring-the-script-component-in-the-script-component-editor.md).</span><span class="sxs-lookup"><span data-stu-id="51e42-106">For more information about metadata design mode and code design mode, see [Configuring the Script Component in the Script Component Editor](configuring-the-script-component-in-the-script-component-editor.md).</span></span>

## <a name="writing-the-script-in-code-design-mode"></a><span data-ttu-id="51e42-107">Разработка скрипта в режиме конструктора кода</span><span class="sxs-lookup"><span data-stu-id="51e42-107">Writing the Script in Code Design Mode</span></span>

### <a name="script-component-development-environment"></a><span data-ttu-id="51e42-108">Среда разработки компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="51e42-108">Script Component Development Environment</span></span>
 <span data-ttu-id="51e42-109">Для подготовки скрипта нажмите кнопку **Изменить скрипт** на странице **Скрипт** в окне **Редактор преобразования "Скрипт"** . Откроется среда разработки скриптов средств [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] для приложений (VSTA).</span><span class="sxs-lookup"><span data-stu-id="51e42-109">To write your script, click **Edit Script** on the **Script** page of the **Script Transformation Editor** to open the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Tools for Applications (VSTA) IDE.</span></span> <span data-ttu-id="51e42-110">В среде разработки VSTA предусмотрены все стандартные возможности среды [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] .NET, в том числе редактор [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] с цветовым выделением, технологией IntelliSense и браузером объектов.</span><span class="sxs-lookup"><span data-stu-id="51e42-110">The VSTA IDE includes all the standard features of the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] .NET environment, such as the color-coded [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] editor, IntelliSense, and Object Browser.</span></span>

 <span data-ttu-id="51e42-111">Код скрипта пишется на языке [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic или [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="51e42-111">Script code is written in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic or [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span></span> <span data-ttu-id="51e42-112">Пользователь указывает язык скриптов, задавая значение свойства **ScriptLanguage** в окне **Редактор преобразования "Скрипт"** .</span><span class="sxs-lookup"><span data-stu-id="51e42-112">You specify the script language by setting the **ScriptLanguage** property in the **Script Transformation Editor**.</span></span> <span data-ttu-id="51e42-113">Если разработчик предпочитает пользоваться другим языком программирования, то можно разработать пользовательскую сборку на выбранном языке и вызвать его функциональные возможности из кода в компоненте скрипта.</span><span class="sxs-lookup"><span data-stu-id="51e42-113">If you prefer to use another programming language, you can develop a custom assembly in your language of choice and call its functionality from the code in the Script component.</span></span>

 <span data-ttu-id="51e42-114">Скрипт, созданный в компоненте скрипта, хранится в определении пакета.</span><span class="sxs-lookup"><span data-stu-id="51e42-114">The script that you create in the Script component is stored in the package definition.</span></span> <span data-ttu-id="51e42-115">Отдельного файла скрипта не существует.</span><span class="sxs-lookup"><span data-stu-id="51e42-115">There is no separate script file.</span></span> <span data-ttu-id="51e42-116">Поэтому использование компонента скрипта не влияет на развертывание пакета.</span><span class="sxs-lookup"><span data-stu-id="51e42-116">Therefore, the use of the Script component does not affect package deployment.</span></span>

> [!NOTE]
>  <span data-ttu-id="51e42-117">При проектировании пакета код скрипта временно записывается в файл проекта.</span><span class="sxs-lookup"><span data-stu-id="51e42-117">While you design the package, the script code is temporarily written to a project file.</span></span> <span data-ttu-id="51e42-118">Хранение конфиденциальных сведений в файле представляет потенциальный риск для безопасности, поэтому в код скрипта не рекомендуется включать конфиденциальные сведения, например пароли.</span><span class="sxs-lookup"><span data-stu-id="51e42-118">Because storing sensitive information in a file is a potential security risk, we recommended that you do not include sensitive information such as passwords in the script code.</span></span>

 <span data-ttu-id="51e42-119">По умолчанию среда `Option Strict` в среде разработки отключена.</span><span class="sxs-lookup"><span data-stu-id="51e42-119">By default, `Option Strict` is disabled in the IDE.</span></span>

### <a name="script-component-project-structure"></a><span data-ttu-id="51e42-120">Структура проекта компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="51e42-120">Script Component Project Structure</span></span>
 <span data-ttu-id="51e42-121">Преимущество компонента скрипта заключается в возможности создавать код инфраструктуры, что уменьшает объем кода, который приходится писать вручную.</span><span class="sxs-lookup"><span data-stu-id="51e42-121">The power of the Script component is that it can generate infrastructure code that reduces the amount of code that you must write.</span></span> <span data-ttu-id="51e42-122">В основе этой возможности лежит тот факт, что входы и выходы, а также их столбцы и свойства являются фиксированными и известны заранее.</span><span class="sxs-lookup"><span data-stu-id="51e42-122">This feature relies on the fact that inputs and outputs and their columns and properties are fixed and known in advance.</span></span> <span data-ttu-id="51e42-123">Поэтому любые последующие изменения, внесенные в метаданные компонента, могут сделать подготовленный код неработоспособным.</span><span class="sxs-lookup"><span data-stu-id="51e42-123">Therefore, any subsequent changes that you make to the component's metadata may invalidate the code that you have written.</span></span> <span data-ttu-id="51e42-124">Это приводит к ошибке при выполнении пакета.</span><span class="sxs-lookup"><span data-stu-id="51e42-124">This causes compilation errors during execution of the package.</span></span>

#### <a name="project-items-and-classes-in-the-script-component-project"></a><span data-ttu-id="51e42-125">Элементы и классы проекта в проекте компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="51e42-125">Project Items and Classes in the Script Component Project</span></span>
 <span data-ttu-id="51e42-126">При переключении в режим конструктора кода открывается среда разработки VSTA, где отображается элемент проекта `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="51e42-126">When you switch to code design mode, the VSTA IDE opens and displays the `ScriptMain` project item.</span></span> <span data-ttu-id="51e42-127">Элемент проекта `ScriptMain` содержит редактируемый класс `ScriptMain`, который служит точкой входа в скрипт и в котором проектируется код.</span><span class="sxs-lookup"><span data-stu-id="51e42-127">The `ScriptMain` project item contains the editable `ScriptMain` class, which serves as the entry point for the script and which is where you write your code.</span></span> <span data-ttu-id="51e42-128">Элементы кода в классе изменяются в зависимости от языка программирования, выбранного для задачи «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="51e42-128">The code elements in the class vary depending on the programming language that you selected for the Script task.</span></span>

 <span data-ttu-id="51e42-129">Проект скрипта содержит два дополнительных автоматически созданных элемента проекта, доступных только для чтения.</span><span class="sxs-lookup"><span data-stu-id="51e42-129">The script project contains two additional auto-generated read-only project items:</span></span>

-   <span data-ttu-id="51e42-130">Элемент проекта `ComponentWrapper` содержит три класса.</span><span class="sxs-lookup"><span data-stu-id="51e42-130">The `ComponentWrapper` project item contains three classes:</span></span>

    -   <span data-ttu-id="51e42-131">Класс `UserComponent`, который наследуется от <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> и содержит методы и свойства для обработки данных и взаимодействия с пакетами.</span><span class="sxs-lookup"><span data-stu-id="51e42-131">The `UserComponent` class, which inherits from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> and contains the methods and properties that you will use to process data and to interact with the package.</span></span> <span data-ttu-id="51e42-132">Класс `ScriptMain` наследуется от класса `UserComponent`.</span><span class="sxs-lookup"><span data-stu-id="51e42-132">The `ScriptMain` class inherits from the `UserComponent` class.</span></span>

    -   <span data-ttu-id="51e42-133">Коллекция классов `Connections`, которая содержит ссылки на подключения, выбранные на странице «Диспетчер соединений» в редакторе преобразования «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="51e42-133">A `Connections` collection class that contains references to the connections selected on the Connection Manager page of the Script Transformation Editor.</span></span>

    -   <span data-ttu-id="51e42-134">`Variables`Класс коллекции, содержащий ссылки на переменные, указанные в `ReadOnlyVariable` `ReadWriteVariables` свойствах и на странице **Скрипт** в **редакторе преобразования "Скрипт**".</span><span class="sxs-lookup"><span data-stu-id="51e42-134">A `Variables` collection class that contains references to the variables entered in the `ReadOnlyVariable` and `ReadWriteVariables` properties on the **Script** page of the **Script Transformation Editor**.</span></span>

-   <span data-ttu-id="51e42-135">`BufferWrapper`Элемент проекта содержит класс, наследующий от <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> для каждого входных и выходных данных, настроенных на странице **входы и выходы** в **редакторе преобразования "Скрипт**".</span><span class="sxs-lookup"><span data-stu-id="51e42-135">The `BufferWrapper` project item contains a class that inherits from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> for each input and output configured on the **Inputs and Outputs** page of the **Script Transformation Editor**.</span></span> <span data-ttu-id="51e42-136">Каждый из этих классов содержит типизированные свойства метода доступа, которые соответствуют настроенным входным и выходным столбцам, а также буферы потока данных, содержащие столбцы.</span><span class="sxs-lookup"><span data-stu-id="51e42-136">Each of these classes contains typed accessor properties that correspond to the configured input and output columns, and the data flow buffers that contain the columns.</span></span>

 <span data-ttu-id="51e42-137">Дополнительные сведения об использовании этих объектов, методов и свойств см. в разделе [Основные сведения о модели объектов компонента скрипта](understanding-the-script-component-object-model.md).</span><span class="sxs-lookup"><span data-stu-id="51e42-137">For information about how to use these objects, methods, and properties, see [Understanding the Script Component Object Model](understanding-the-script-component-object-model.md).</span></span> <span data-ttu-id="51e42-138">Сведения об использовании методов и свойств этих классов в компоненте скрипта определенного типа см. в разделе [Дополнительные примеры компонента скрипта](../../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span><span class="sxs-lookup"><span data-stu-id="51e42-138">For information about how to use the methods and properties of these classes in a particular type of Script component, see the section [Additional Script Component Examples](../../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span></span> <span data-ttu-id="51e42-139">В разделах примеров также приведен полный образец кода.</span><span class="sxs-lookup"><span data-stu-id="51e42-139">The example topics also contain complete code samples.</span></span>

 <span data-ttu-id="51e42-140">Если настроить компонент «Скрипт» в качестве преобразования, элемент проекта `ScriptMain` будет содержать следующий автоматически сформированный код.</span><span class="sxs-lookup"><span data-stu-id="51e42-140">When you configure the Script component as a transformation, the `ScriptMain` project item contains the following autogenerated code.</span></span> <span data-ttu-id="51e42-141">В шаблоне кода также имеется обзор компонента «Скрипт» и дополнительные сведения о получении и управлении такими объектами служб SSIS, как переменные, события и соединения.</span><span class="sxs-lookup"><span data-stu-id="51e42-141">The code template also provides an overview of the Script component, and additional information on how to retrieve and manipulate SSIS objects, such as variables, events, and connections.</span></span>

```vb
' Microsoft SQL Server Integration Services Script Component
' Write scripts using Microsoft Visual Basic 2008.
' ScriptMain is the entry point class of the script.

Imports System
Imports System.Data
Imports System.Math
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper

<Microsoft.SqlServer.Dts.Pipeline.SSISScriptComponentEntryPointAttribute> _
<CLSCompliant(False)> _
Public Class ScriptMain
    Inherits UserComponent

    Public Overrides Sub PreExecute()
        MyBase.PreExecute()
        '
        ' Add your code here for preprocessing or remove if not needed
        '
    End Sub

    Public Overrides Sub PostExecute()
        MyBase.PostExecute()
        '
        ' Add your code here for postprocessing or remove if not needed
        ' You can set read/write variables here, for example:
        ' Me.Variables.MyIntVar = 100
        '
    End Sub

    Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)
        '
        ' Add your code here
        '
    End Sub

End Class
```

```csharp
/* Microsoft SQL Server Integration Services user script component
*  Write scripts using Microsoft Visual C# 2008.
*  ScriptMain is the entry point class of the script.*/

using System;
using System.Data;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime.Wrapper;

[Microsoft.SqlServer.Dts.Pipeline.SSISScriptComponentEntryPointAttribute]
public class ScriptMain : UserComponent
{

    public override void PreExecute()
    {
        base.PreExecute();
        /*
          Add your code here for preprocessing or remove if not needed
        */
    }

    public override void PostExecute()
    {
        base.PostExecute();
        /*
          Add your code here for postprocessing or remove if not needed
          You can set read/write variables here, for example:
          Variables.MyIntVar = 100
        */
    }

    public override void Input0_ProcessInputRow(Input0Buffer Row)
    {
        /*
          Add your code here
        */
    }

}
```

#### <a name="additional-project-items-in-the-script-component-project"></a><span data-ttu-id="51e42-142">Дополнительные элементы проекта в проекте компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="51e42-142">Additional Project Items in the Script Component Project</span></span>
 <span data-ttu-id="51e42-143">Проект компонента скрипта может содержать элементы, отличные от элемента `ScriptMain` по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="51e42-143">The Script component project can include items other than the default `ScriptMain` item.</span></span> <span data-ttu-id="51e42-144">Можно добавлять в проект классы, модули, файлы кода и папки, а также можно упорядочивать группы элементов с помощью папок.</span><span class="sxs-lookup"><span data-stu-id="51e42-144">You can add classes, modules, code files, and folders to the project, and you can use folders to organize groups of items.</span></span>

 <span data-ttu-id="51e42-145">Все добавляемые элементы сохраняются внутри пакета.</span><span class="sxs-lookup"><span data-stu-id="51e42-145">All the items that you add are persisted inside the package.</span></span>

#### <a name="references-in-the-script-component-project"></a><span data-ttu-id="51e42-146">Ссылки в проекте компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="51e42-146">References in the Script Component Project</span></span>
 <span data-ttu-id="51e42-147">Чтобы добавить ссылки в управляемые сборки, щелкните правой кнопкой мыши проект задачи "Скрипт" в **Обозревателе проектов**, затем выберите **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="51e42-147">You can add references to managed assemblies by right-clicking the Script task project in **Project Explorer**, and then clicking **Add Reference**.</span></span> <span data-ttu-id="51e42-148">Дополнительные сведения см. в разделе [Ссылки на другие сборки в решениях со сценариями](../referencing-other-assemblies-in-scripting-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="51e42-148">For more information, see [Referencing Other Assemblies in Scripting Solutions](../referencing-other-assemblies-in-scripting-solutions.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="51e42-149">Ссылки проекта можно просмотреть в среде разработки VSTA в **представлении классов** или в **обозревателе проектов**.</span><span class="sxs-lookup"><span data-stu-id="51e42-149">You can view project references in the VSTA IDE in **Class View** or in **Project Explorer**.</span></span> <span data-ttu-id="51e42-150">Любое из этих окон можно открыть из меню **Вид**.</span><span class="sxs-lookup"><span data-stu-id="51e42-150">You open either of these windows from the **View** menu.</span></span> <span data-ttu-id="51e42-151">Можно добавить новую ссылку из меню **Проект**, из **обозревателя проектов** или из **представления классов**.</span><span class="sxs-lookup"><span data-stu-id="51e42-151">You can add a new reference from the **Project** menu, from **Project Explorer**, or from **Class View**.</span></span>

## <a name="interacting-with-the-package-in-the-script-component"></a><span data-ttu-id="51e42-152">Взаимодействие с пакетом в компоненте скрипта</span><span class="sxs-lookup"><span data-stu-id="51e42-152">Interacting with the Package in the Script Component</span></span>
 <span data-ttu-id="51e42-153">Пользовательский скрипт, составленный в компоненте скрипта, может обращаться к переменным и диспетчерам соединений из объемлющего пакета и использовать их через строго типизированные методы доступа в автоматически формируемых основных классах.</span><span class="sxs-lookup"><span data-stu-id="51e42-153">The custom script that you write in the Script component can access and use variables and connection managers from the containing package through strongly-typed accessors in the auto-generated base classes.</span></span> <span data-ttu-id="51e42-154">Однако перед входом в режим конструктора кода необходимо настроить как переменные, так и диспетчеры соединений, если нужно сделать их доступными для скрипта.</span><span class="sxs-lookup"><span data-stu-id="51e42-154">However, you must configure both variables and connection managers before entering code-design mode if you want to make them available to your script.</span></span> <span data-ttu-id="51e42-155">Кроме того, из кода компонента скрипта можно создавать события и вести журналы.</span><span class="sxs-lookup"><span data-stu-id="51e42-155">You can also raise events and perform logging from your Script component code.</span></span>

 <span data-ttu-id="51e42-156">Автоматически созданные элементы проекта в проекте компонента скрипта предоставляют следующие объекты, методы и свойства для взаимодействия с пакетом.</span><span class="sxs-lookup"><span data-stu-id="51e42-156">The autogenerated project items in the Script component project provide the following objects, methods, and properties for interacting with the package.</span></span>

|<span data-ttu-id="51e42-157">Компонент пакета</span><span class="sxs-lookup"><span data-stu-id="51e42-157">Package Feature</span></span>|<span data-ttu-id="51e42-158">Метод доступа</span><span class="sxs-lookup"><span data-stu-id="51e42-158">Access Method</span></span>|
|---------------------|-------------------|
|<span data-ttu-id="51e42-159">Переменные</span><span class="sxs-lookup"><span data-stu-id="51e42-159">Variables</span></span>|<span data-ttu-id="51e42-160">Использование именованных и типизированных свойств метода доступа класса коллекции `Variables` в элементе проекта `ComponentWrapper`, отображенном в свойстве `Variables` класса `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="51e42-160">Use the named and typed accessor properties in the `Variables` collection class in the `ComponentWrapper` project item, exposed through the `Variables` property of the `ScriptMain` class.</span></span><br /><br /> <span data-ttu-id="51e42-161">Метод `PreExecute` может обращаться только к переменным, доступным только для чтения.</span><span class="sxs-lookup"><span data-stu-id="51e42-161">The `PreExecute` method can access only read-only variables.</span></span> <span data-ttu-id="51e42-162">Метод `PostExecute` может обращаться как к переменным, доступным только для чтения, так и к переменным, доступным для чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="51e42-162">The `PostExecute` method can access both read-only and read/write variables.</span></span>|
|<span data-ttu-id="51e42-163">Соединения</span><span class="sxs-lookup"><span data-stu-id="51e42-163">Connections</span></span>|<span data-ttu-id="51e42-164">Использование именованных и типизированных свойств метода доступа класса коллекции `Connections` в элементе проекта `ComponentWrapper`, отображенном в свойстве `Connections` класса `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="51e42-164">Use the named and typed accessor properties in the `Connections` collection class in the `ComponentWrapper` project item, exposed through the `Connections` property of the `ScriptMain` class.</span></span>|
|<span data-ttu-id="51e42-165">События</span><span class="sxs-lookup"><span data-stu-id="51e42-165">Events</span></span>|<span data-ttu-id="51e42-166">Инициируйте события, используя <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> свойство `ScriptMain` класса и методы \*\*Fire \<X> \*\* <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> интерфейса.</span><span class="sxs-lookup"><span data-stu-id="51e42-166">Raise events by using the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> property of the `ScriptMain` class and the **Fire\<X>** methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface.</span></span>|
|<span data-ttu-id="51e42-167">Logging</span><span class="sxs-lookup"><span data-stu-id="51e42-167">Logging</span></span>|<span data-ttu-id="51e42-168">Ведение журнала с помощью метода <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> класса `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="51e42-168">Perform logging by using the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> method of the `ScriptMain` class.</span></span>|

## <a name="debugging-the-script-component"></a><span data-ttu-id="51e42-169">Отладка компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="51e42-169">Debugging the Script Component</span></span>
 <span data-ttu-id="51e42-170">Для отладки кода в компоненте «Скрипт» установите в коде по крайней мере одну точку останова, а затем закройте среду разработки VSTA IDE, чтобы запустить пакет в среде [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="51e42-170">To debug the code in your Script component, set at least one breakpoint in the code, and then close the VSTA IDE to run the package in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="51e42-171">Когда выполнение пакета входит в компонент «Скрипт», среда разработки VSTA IDE открывается повторно и отображает код в режиме только для чтения.</span><span class="sxs-lookup"><span data-stu-id="51e42-171">When package execution enters the Script component, the VSTA IDE reopens and displays your code in read-only mode.</span></span> <span data-ttu-id="51e42-172">После того как выполнение достигает точку останова, можно проверить значения переменных и выполнить оставшийся код в режиме пошагового выполнения.</span><span class="sxs-lookup"><span data-stu-id="51e42-172">After execution reaches your breakpoint, you can examine variable values and step through the remaining code.</span></span>

> [!NOTE]
>  <span data-ttu-id="51e42-173">Однако нельзя выполнять отладку компонента «Скрипт», если этот компонент запускается как часть дочернего пакета, вызываемого задачей «Выполнение пакета».</span><span class="sxs-lookup"><span data-stu-id="51e42-173">You cannot debug a Script component when you run the Script component as part of a child package that is run from an Execute Package task.</span></span> <span data-ttu-id="51e42-174">В этом случае точки останова, установленные в компоненте «Скрипт» в дочернем пакете, пропускаются.</span><span class="sxs-lookup"><span data-stu-id="51e42-174">Breakpoints that you set in the Script component in the child package are disregarded in these circumstances.</span></span> <span data-ttu-id="51e42-175">Дочерний пакет можно нормально отладить, запустив его отдельно.</span><span class="sxs-lookup"><span data-stu-id="51e42-175">You can debug the child package normally by running it separately.</span></span>

> [!NOTE]
>  <span data-ttu-id="51e42-176">Во время отладки пакета, содержащего несколько компонентов «Скрипт», отладчик выполняет отладку одного компонента «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="51e42-176">When you debug a package that contains multiple Script components, the debugger debugs one Script component.</span></span> <span data-ttu-id="51e42-177">Затем система может выполнять отладку другого компонента «Скрипт», если отладчик завершает работу, как в случае контейнера «цикл по элементам» или «цикл по каждому элементу».</span><span class="sxs-lookup"><span data-stu-id="51e42-177">The system can debug another Script component if the debugger completes, as in the case of a Foreach Loop or For Loop container.</span></span>

 <span data-ttu-id="51e42-178">Наблюдать за выполнением компонента «Скрипт» также можно следующими способами.</span><span class="sxs-lookup"><span data-stu-id="51e42-178">You can also monitor the execution of the Script component by using the following methods:</span></span>

-   <span data-ttu-id="51e42-179">Прерывание выполнения и отображение модального сообщения с помощью `MessageBox.Show` метода в пространстве имен **System. Windows. Forms** .</span><span class="sxs-lookup"><span data-stu-id="51e42-179">Interrupt execution and display a modal message by using the `MessageBox.Show` method in the **System.Windows.Forms** namespace.</span></span> <span data-ttu-id="51e42-180">(После завершения процесса отладки этот код следует удалить.)</span><span class="sxs-lookup"><span data-stu-id="51e42-180">(Remove this code after you complete the debugging process.)</span></span>

-   <span data-ttu-id="51e42-181">Создавать события для информационных сообщений, предупреждений и ошибок.</span><span class="sxs-lookup"><span data-stu-id="51e42-181">Raise events for informational messages, warnings, and errors.</span></span> <span data-ttu-id="51e42-182">Методы FireInformation, FireWarning и FireError отображают описание события в окне **Вывод** Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="51e42-182">The FireInformation, FireWarning, and FireError methods display the event description in the Visual Studio **Output** window.</span></span> <span data-ttu-id="51e42-183">Тем не менее методы FireProgress, Console.Write и Console.WriteLine не отображают никакие сведения в окне **Вывод**.</span><span class="sxs-lookup"><span data-stu-id="51e42-183">However, the FireProgress method, the Console.Write method, and Console.WriteLine method do not display any information in the **Output** window.</span></span> <span data-ttu-id="51e42-184">Сообщения из события FireProgress отображаются на вкладке **Ход выполнения** конструктора служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="51e42-184">Messages from the FireProgress event appear on the **Progress** tab of [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="51e42-185">Дополнительные сведения см. в разделе [Вызов событий в компоненте скрипта](../../data-flow/transformations/script-component.md).</span><span class="sxs-lookup"><span data-stu-id="51e42-185">For more information, see [Raising Events in the Script Component](../../data-flow/transformations/script-component.md).</span></span>

-   <span data-ttu-id="51e42-186">Протоколировать события или пользовательские сообщения на включенных регистраторах.</span><span class="sxs-lookup"><span data-stu-id="51e42-186">Log events or user-defined messages to enabled logging providers.</span></span> <span data-ttu-id="51e42-187">Дополнительные сведения см. в разделе [Ведение журнала в задаче скрипта](logging-in-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="51e42-187">For more information, see [Logging in the Script Component](logging-in-the-script-component.md).</span></span>

 <span data-ttu-id="51e42-188">Если нужно только проанализировать выход компонента скрипта, настроенного в качестве источника или преобразования, без сохранения данных в месте назначения, то можно остановить поток данных с помощью [преобразования "Подсчет строк"](../../data-flow/transformations/row-count-transformation.md) и присоединить средство просмотра данных к выходу компонента скрипта.</span><span class="sxs-lookup"><span data-stu-id="51e42-188">If you just want to examine the output of a Script component configured as a source or as a transformation, without saving the data to a destination, you can stop the data flow with a [Row Count Transformation](../../data-flow/transformations/row-count-transformation.md) and attach a data viewer to the output of the Script component.</span></span> <span data-ttu-id="51e42-189">Дополнительные сведения о средствах просмотра данных см. в разделе [Отладка потока данных](../../troubleshooting/debugging-data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="51e42-189">For information about data viewers, see [Debugging Data Flow](../../troubleshooting/debugging-data-flow.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="51e42-190">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="51e42-190">In This Section</span></span>
 <span data-ttu-id="51e42-191">Дополнительные сведения о написании кода компонента скрипта см. в следующих подразделах в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="51e42-191">For more information about coding the Script component, see the following topics in this section.</span></span>

 <span data-ttu-id="51e42-192">[Основные сведения об объектной модели компонента скрипта](understanding-the-script-component-object-model.md) Объясняется, как использовать объекты, методы и свойства, доступные в компоненте скрипта.</span><span class="sxs-lookup"><span data-stu-id="51e42-192">[Understanding the Script Component Object Model](understanding-the-script-component-object-model.md) Explains how to use the objects, methods, and properties available in the Script component.</span></span>

 <span data-ttu-id="51e42-193">[Создание ссылок на другие сборки в решениях сценариев](../referencing-other-assemblies-in-scripting-solutions.md) Объясняется, как ссылаться на объекты из [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] библиотеки классов в компоненте скрипта.</span><span class="sxs-lookup"><span data-stu-id="51e42-193">[Referencing Other Assemblies in Scripting Solutions](../referencing-other-assemblies-in-scripting-solutions.md) Explains how to reference objects from the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] class library in the Script component.</span></span>

 <span data-ttu-id="51e42-194">[Имитация вывода ошибок для компонента скрипта](../../extending-packages-scripting-data-flow-script-component-examples/simulating-an-error-output-for-the-script-component.md) Объясняет, как имитировать вывод ошибок для строк, вызывающих ошибки при обработке компонентом скрипта.</span><span class="sxs-lookup"><span data-stu-id="51e42-194">[Simulating an Error Output for the Script Component](../../extending-packages-scripting-data-flow-script-component-examples/simulating-an-error-output-for-the-script-component.md) Explains how to simulate an error output for rows that raise errors during processing by the Script component.</span></span>

## <a name="external-resources"></a><span data-ttu-id="51e42-195">Внешние ресурсы</span><span class="sxs-lookup"><span data-stu-id="51e42-195">External Resources</span></span>

-   <span data-ttu-id="51e42-196">Запись в блоге [Затруднения при установке и настройке VSTA для установок SSIS 2008 и R2](https://go.microsoft.com/fwlink/?LinkId=215661) на сайте blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="51e42-196">Blog entry, [VSTA setup and configuration troubles for SSIS 2008 and R2 installations](https://go.microsoft.com/fwlink/?LinkId=215661), on blogs.msdn.com.</span></span>

<span data-ttu-id="51e42-197">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="51e42-197">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="51e42-198">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="51e42-198">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="51e42-199">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="51e42-199">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="51e42-200">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="51e42-200">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="51e42-201">См. также:</span><span class="sxs-lookup"><span data-stu-id="51e42-201">See Also</span></span>
 [<span data-ttu-id="51e42-202">Настройка компонента скрипта в редакторе компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="51e42-202">Configuring the Script Component in the Script Component Editor</span></span>](configuring-the-script-component-in-the-script-component-editor.md)


