---
title: Добавление компонентов потока данных программным образом | Документы Майкрософт
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
- data flow task [Integration Services], components
- components [Integration Services], data flow
- data flow [Integration Services], components
ms.assetid: c06065cf-43e5-4b6b-9824-7309d7f5e35e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 807e758e42b738c4b0bf64b1d6f48bc29649ae6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658365"
---
# <a name="adding-data-flow-components-programmatically"></a><span data-ttu-id="a5b92-102">Добавление компонентов потока данных программным образом</span><span class="sxs-lookup"><span data-stu-id="a5b92-102">Adding Data Flow Components Programmatically</span></span>
  <span data-ttu-id="a5b92-103">Построение потока данных начинается с добавления компонентов.</span><span class="sxs-lookup"><span data-stu-id="a5b92-103">When you build a data flow, you start by adding components.</span></span> <span data-ttu-id="a5b92-104">Затем необходимо настроить эти компоненты и соединить их друг с другом, чтобы образовался поток данных времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="a5b92-104">Then you configure those components and connect them together to establish the flow of data at run time.</span></span> <span data-ttu-id="a5b92-105">В этом разделе описывается добавление компонента в задачу потока данных, создание экземпляра компонента времени разработки и последующая настройка компонента.</span><span class="sxs-lookup"><span data-stu-id="a5b92-105">This section describes adding a component to the data flow task, creating the design-time instance of the component, and then configuring the component.</span></span> <span data-ttu-id="a5b92-106">Дополнительные сведения о соединении компонентов см. в статье [Программное соединение компонентов потока данных](../building-packages-programmatically/connecting-data-flow-components-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="a5b92-106">For information about how to connect components, see [Connecting Data Flow Components Programmatically](../building-packages-programmatically/connecting-data-flow-components-programmatically.md).</span></span>  
  
## <a name="adding-a-component"></a><span data-ttu-id="a5b92-107">Добавление компонента</span><span class="sxs-lookup"><span data-stu-id="a5b92-107">Adding a Component</span></span>  
 <span data-ttu-id="a5b92-108">Вызовите метод <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaDataCollection100.New%2A> коллекции <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.MainPipeClass.ComponentMetaDataCollection%2A>, чтобы создать новый компонент и добавить его в задачу потока данных.</span><span class="sxs-lookup"><span data-stu-id="a5b92-108">Call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaDataCollection100.New%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.MainPipeClass.ComponentMetaDataCollection%2A> collection to create a new component and add it to the data flow task.</span></span> <span data-ttu-id="a5b92-109">Этот метод возвращает интерфейс <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> компонента.</span><span class="sxs-lookup"><span data-stu-id="a5b92-109">This method returns the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface of the component.</span></span> <span data-ttu-id="a5b92-110">Однако на этом этапе интерфейс <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> не содержит сведений, относящихся к какому-либо определенному компоненту.</span><span class="sxs-lookup"><span data-stu-id="a5b92-110">However, at this point, the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> does not contain information specific to any one component.</span></span> <span data-ttu-id="a5b92-111">Задайте свойство <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A>, чтобы определить тип компонента.</span><span class="sxs-lookup"><span data-stu-id="a5b92-111">Set the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> property to identify the type of component.</span></span> <span data-ttu-id="a5b92-112">Задача потока данных использует значение этого свойства для создания экземпляра компонента во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="a5b92-112">The data flow task uses the value of this property to create an instance of the component at run time.</span></span>  
  
 <span data-ttu-id="a5b92-113">Значение, указанное в свойстве <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A>, может обозначать идентификатор CLSID, PROGID или свойство <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo.CreationName%2A> компонента.</span><span class="sxs-lookup"><span data-stu-id="a5b92-113">The value specified in the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> property can be the CLSID, PROGID, or <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo.CreationName%2A> property of the component.</span></span> <span data-ttu-id="a5b92-114">Идентификатор CLSID обычно отображается в окне «Свойства» как значение свойства <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> компонента.</span><span class="sxs-lookup"><span data-stu-id="a5b92-114">The CLSID is normally displayed in the Properties window as the value of the component's <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> property.</span></span> <span data-ttu-id="a5b92-115">Сведения о получении значений этого свойства и других свойств доступных компонентов см. в разделе [Программный поиск компонентов потока данных](../building-packages-programmatically/discovering-data-flow-components-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="a5b92-115">For information about obtaining this property and other properties of available components, see [Discovering Data Flow Components Programmatically](../building-packages-programmatically/discovering-data-flow-components-programmatically.md).</span></span>  
  
## <a name="adding-a-managed-component"></a><span data-ttu-id="a5b92-116">Добавление управляемого компонента</span><span class="sxs-lookup"><span data-stu-id="a5b92-116">Adding a Managed Component</span></span>  
 <span data-ttu-id="a5b92-117">Использовать идентификаторы CLSID или PROGID для добавления управляемых компонентов потока данных в поток данных нельзя, поскольку эти значения указывают на оболочку, а не на сам компонент.</span><span class="sxs-lookup"><span data-stu-id="a5b92-117">You cannot use the CLSID or PROGID to add one the managed data flow components to the data flow, because these values point to a wrapper and not to the component itself.</span></span> <span data-ttu-id="a5b92-118">Вместо этого можно использовать свойство `CreationName` или свойство `AssemblyQualifiedName`, как показано в следующем образце.</span><span class="sxs-lookup"><span data-stu-id="a5b92-118">Instead you can use the `CreationName` property or the `AssemblyQualifiedName` property as shown in the following sample.</span></span>  
  
 <span data-ttu-id="a5b92-119">Если необходимо использовать свойство `AssemblyQualifiedName`, следует добавить в проект [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ссылку на сборку, содержащую управляемый компонент.</span><span class="sxs-lookup"><span data-stu-id="a5b92-119">If you intend to use the `AssemblyQualifiedName` property, then you must add a reference in your [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] project to the assembly that contains the managed component.</span></span> <span data-ttu-id="a5b92-120">Эти сборки отсутствуют в списке на вкладке ".NET" диалогового окна **Добавление ссылки**.</span><span class="sxs-lookup"><span data-stu-id="a5b92-120">These assemblies are not listed on the .NET tab of the **Add Reference** dialog box.</span></span> <span data-ttu-id="a5b92-121">В общем случае сборка находится в папке **C:\Program Files\Microsoft SQL Server\100\DTS\PipelineComponents**.</span><span class="sxs-lookup"><span data-stu-id="a5b92-121">Normally you must browse to locate the assembly in the **C:\Program Files\Microsoft SQL Server\100\DTS\PipelineComponents** folder.</span></span>  
  
 <span data-ttu-id="a5b92-122">В число встроенных управляемых компонентов потока данных входят:</span><span class="sxs-lookup"><span data-stu-id="a5b92-122">The built-in managed data flow components include:</span></span>  
  
-   <span data-ttu-id="a5b92-123">Источник [!INCLUDE[vstecado](../../includes/vstecado-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5b92-123">[!INCLUDE[vstecado](../../includes/vstecado-md.md)] Source</span></span>  
  
-   <span data-ttu-id="a5b92-124">XML-источник</span><span class="sxs-lookup"><span data-stu-id="a5b92-124">XML Source</span></span>  
  
-   <span data-ttu-id="a5b92-125">назначение DataReader</span><span class="sxs-lookup"><span data-stu-id="a5b92-125">DataReader Destination</span></span>  
  
-   <span data-ttu-id="a5b92-126">Назначение [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact</span><span class="sxs-lookup"><span data-stu-id="a5b92-126">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact Destination</span></span>  
  
-   <span data-ttu-id="a5b92-127">Компонент скрипта</span><span class="sxs-lookup"><span data-stu-id="a5b92-127">Script Component</span></span>  
  
 <span data-ttu-id="a5b92-128">В следующем образце кода демонстрируются оба способа добавления управляемого компонента в поток данных:</span><span class="sxs-lookup"><span data-stu-id="a5b92-128">The following code sample shows both ways of adding a managed component to the data flow:</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Microsoft.SqlServer.Dts.Runtime.Package package = new Microsoft.SqlServer.Dts.Runtime.Package();  
      Executable e = package.Executables.Add("STOCK:PipelineTask");  
      Microsoft.SqlServer.Dts.Runtime.TaskHost thMainPipe = (Microsoft.SqlServer.Dts.Runtime.TaskHost)e;  
      MainPipe dataFlowTask = (MainPipe)thMainPipe.InnerObject;  
  
      // The Application object will be used to obtain the CreationName  
      //  of a PipelineComponentInfo from its PipelineComponentInfos collection.  
      Application app = new Application();  
  
      // Add a first ADO NET source to the data flow.  
      //  The CreationName property requires an Application instance.  
      IDTSComponentMetaData100 component1 = dataFlowTask.ComponentMetaDataCollection.New();  
      component1.Name = "DataReader Source";  
      component1.ComponentClassID = app.PipelineComponentInfos["DataReader Source"].CreationName;  
  
      // Add a second ADO NET source to the data flow.  
      //  The AssemblyQualifiedName property requires a reference to the assembly.  
      IDTSComponentMetaData100 component2 = dataFlowTask.ComponentMetaDataCollection.New();  
      component2.Name = "DataReader Source";  
      component2.ComponentClassID = typeof(Microsoft.SqlServer.Dts.Pipeline.DataReaderSourceAdapter).AssemblyQualifiedName;  
    }  
  }  
}  
  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
Module Module1  
  
  Sub Main()  
  
    Dim package As Microsoft.SqlServer.Dts.Runtime.Package = _  
      New Microsoft.SqlServer.Dts.Runtime.Package()  
    Dim e As Executable = package.Executables.Add("STOCK:PipelineTask")  
    Dim thMainPipe As Microsoft.SqlServer.Dts.Runtime.TaskHost = _  
      CType(e, Microsoft.SqlServer.Dts.Runtime.TaskHost)  
    Dim dataFlowTask As MainPipe = CType(thMainPipe.InnerObject, MainPipe)  
  
    ' The Application object will be used to obtain the CreationName  
    '  of a PipelineComponentInfo from its PipelineComponentInfos collection.  
    Dim app As New Application()  
  
    ' Add a first ADO NET source to the data flow.  
    '  The CreationName property requires an Application instance.  
    Dim component1 As IDTSComponentMetaData100 = _  
      dataFlowTask.ComponentMetaDataCollection.New()  
    component1.Name = "DataReader Source"  
    component1.ComponentClassID = app.PipelineComponentInfos("DataReader Source").CreationName  
  
    ' Add a second ADO NET source to the data flow.  
    '  The AssemblyQualifiedName property requires a reference to the assembly.  
    Dim component2 As IDTSComponentMetaData100 = _  
      dataFlowTask.ComponentMetaDataCollection.New()  
    component2.Name = "DataReader Source"  
    component2.ComponentClassID = _  
      GetType(Microsoft.SqlServer.Dts.Pipeline.DataReaderSourceAdapter).AssemblyQualifiedName  
  
  End Sub  
  
End Module  
```  
  
## <a name="creating-the-design-time-instance-of-the-component"></a><span data-ttu-id="a5b92-129">Создание экземпляра компонента времени разработки</span><span class="sxs-lookup"><span data-stu-id="a5b92-129">Creating the Design-time Instance of the Component</span></span>  
 <span data-ttu-id="a5b92-130">Вызовите метод <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.Instantiate%2A>, чтобы создать экземпляр компонента времени разработки, определенный свойством <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5b92-130">Call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.Instantiate%2A> method to create the design time instance of the component identified by the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> property.</span></span> <span data-ttu-id="a5b92-131">Этот метод возвращает объект <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper>, который является управляемой оболочкой для интерфейса <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100>.</span><span class="sxs-lookup"><span data-stu-id="a5b92-131">This method returns the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper> object, which is the managed wrapper for the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> interface.</span></span>  
  
 <span data-ttu-id="a5b92-132">При возможности для изменения компонента следует использовать методы экземпляра времени разработки, а не изменять непосредственно метаданные компонента.</span><span class="sxs-lookup"><span data-stu-id="a5b92-132">Whenever possible, you should modify a component by using the methods of the design-time instance instead of by modifying the component metadata directly.</span></span> <span data-ttu-id="a5b92-133">Хотя некоторые элементы метаданных, например соединения, необходимо задавать непосредственно, обычно не рекомендуется изменять метаданные непосредственно, поскольку при этом не задействуются возможности компонента по отслеживанию и проверке изменений.</span><span class="sxs-lookup"><span data-stu-id="a5b92-133">Although there are items in the metadata that you must set directly, such as connections, generally it is inadvisable to modify the metadata directly because you bypass the ability of the component to monitor and validate changes.</span></span>  
  
## <a name="assigning-connections"></a><span data-ttu-id="a5b92-134">Назначение соединений</span><span class="sxs-lookup"><span data-stu-id="a5b92-134">Assigning Connections</span></span>  
 <span data-ttu-id="a5b92-135">Для некоторых компонентов, например, компонента «Источник OLE DB», требуется соединение с внешним источником данных. Для этой цели используется существующий в пакете объект <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>.</span><span class="sxs-lookup"><span data-stu-id="a5b92-135">Some components, such as the OLE DB Source component, require a connection to external data and use an existing <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> object in the package for this purpose.</span></span> <span data-ttu-id="a5b92-136">Значение свойства <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnectionCollection100.Count%2A> коллекции <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A> указывает на число объектов <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>, необходимых для компонента.</span><span class="sxs-lookup"><span data-stu-id="a5b92-136">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnectionCollection100.Count%2A> property of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A> collection indicates the number of run-time <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects required by the component.</span></span> <span data-ttu-id="a5b92-137">Если это число больше нуля, для компонента требуется соединение.</span><span class="sxs-lookup"><span data-stu-id="a5b92-137">If the count is greater than zero, the component requires a connection.</span></span> <span data-ttu-id="a5b92-138">Назначьте для компонента диспетчер соединений из пакета, указав свойства <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100.ConnectionManager%2A> и <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100.Name%2A> первого соединения в коллекции <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5b92-138">Assign a connection manager from the package to the component by specifying the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100.ConnectionManager%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100.Name%2A> properties of the first connection in the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>.</span></span> <span data-ttu-id="a5b92-139">Обратите внимание на то, что имя диспетчера подключений в коллекции подключений времени выполнения должно совпадать с именем диспетчера подключений, на который ссылается пакет.</span><span class="sxs-lookup"><span data-stu-id="a5b92-139">Note that the name of the connection manager in the run-time connection collection must match the name of the connection managerreferenced from the package.</span></span>  
  
## <a name="setting-the-values-of-custom-properties"></a><span data-ttu-id="a5b92-140">Задание значений пользовательских свойств</span><span class="sxs-lookup"><span data-stu-id="a5b92-140">Setting the Values of Custom Properties</span></span>  
 <span data-ttu-id="a5b92-141">После создания экземпляра компонента времени разработки, вызовите метод <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ProvideComponentProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5b92-141">After creating the design-time instance of the component, call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ProvideComponentProperties%2A> method.</span></span> <span data-ttu-id="a5b92-142">Этот метод подобен конструктору, поскольку он инициализирует только что созданный компонент, создавая его пользовательские свойства, а также объекты входа и выхода.</span><span class="sxs-lookup"><span data-stu-id="a5b92-142">This method is similar to a constructor because it initializes a newly created component by creating its custom properties and its input and output objects.</span></span> <span data-ttu-id="a5b92-143">Нельзя вызывать метод <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ProvideComponentProperties%2A> более одного раза для компонента, поскольку при этом могут быть сброшены настройки компонента и потеряны все изменения, ранее внесенные в его метаданные.</span><span class="sxs-lookup"><span data-stu-id="a5b92-143">Do not call <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ProvideComponentProperties%2A> more than one time on a component, because the component may reset itself and lose any modifications previously made to its metadata.</span></span>  
  
 <span data-ttu-id="a5b92-144">Коллекция свойств <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.CustomPropertyCollection%2A> компонента содержит коллекцию объектов <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100>, относящихся к компоненту.</span><span class="sxs-lookup"><span data-stu-id="a5b92-144">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.CustomPropertyCollection%2A> of the component contains a collection of <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100> objects specific to the component.</span></span> <span data-ttu-id="a5b92-145">В отличие от других моделей программирования, где свойства объекта всегда доступны для объекта, компоненты заполняют свои коллекции пользовательских свойств только при вызове метода <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ProvideComponentProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5b92-145">Unlike other programming models, where the properties of an object are always visible on the object, components only populate their custom property collections when you call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ProvideComponentProperties%2A> method.</span></span> <span data-ttu-id="a5b92-146">После вызова этого метода используйте метод <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.SetComponentProperty%2A> экземпляра компонента времени разработки, чтобы присвоить значения его пользовательским свойствам.</span><span class="sxs-lookup"><span data-stu-id="a5b92-146">After you call method, use the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.SetComponentProperty%2A> method of the design-time instance of the component to assign values to its custom properties.</span></span> <span data-ttu-id="a5b92-147">Этот метод принимает пару имя-значение, идентифицирующую пользовательское свойство, и возвращает ее новое значение.</span><span class="sxs-lookup"><span data-stu-id="a5b92-147">This method accepts a name/value pair that identifies the custom property and provides its new value.</span></span>  
  
## <a name="initializing-output-columns"></a><span data-ttu-id="a5b92-148">Инициализация выходных столбцов</span><span class="sxs-lookup"><span data-stu-id="a5b92-148">Initializing Output Columns</span></span>  
 <span data-ttu-id="a5b92-149">После добавления компонента в задачу и его настройки инициализируйте коллекцию столбцов в свойстве <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> объекта.</span><span class="sxs-lookup"><span data-stu-id="a5b92-149">After you add a component to the task and configure it, initialize the collection of columns in the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> of the object.</span></span> <span data-ttu-id="a5b92-150">Этот шаг имеет непосредственное отношение к компоненту-источнику, однако для компонентов преобразования и назначения может не инициализировать столбцы, поскольку они, как правило, зависят от столбцов, получаемых из вышестоящих компонентов.</span><span class="sxs-lookup"><span data-stu-id="a5b92-150">This step is especially relevant for source components, but may not initialize the columns for transformation and destination components because they generally depend on the columns that they receive from upstream components.</span></span>  
  
 <span data-ttu-id="a5b92-151">Вызовите метод <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ReinitializeMetaData%2A>, чтобы инициализировать столбцы на выходах компонента-источника.</span><span class="sxs-lookup"><span data-stu-id="a5b92-151">Call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ReinitializeMetaData%2A> method to initialize the columns in the outputs of a source component.</span></span> <span data-ttu-id="a5b92-152">Так как компоненты не соединяются автоматически с внешними источниками данных, необходимо вызвать метод <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.AcquireConnections%2A> перед вызовом метода <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ReinitializeMetaData%2A>, чтобы обеспечить компоненту доступ к его внешнему источнику данных и возможность заполнить метаданными соответствующий столбец.</span><span class="sxs-lookup"><span data-stu-id="a5b92-152">Because components do not automatically connect to external data sources, call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.AcquireConnections%2A> method before calling <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ReinitializeMetaData%2A> to provide the component access to its external data source and the ability to populate its column metadata.</span></span> <span data-ttu-id="a5b92-153">Наконец, следует вызвать метод <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ReleaseConnections%2A>, чтобы освободить соединение.</span><span class="sxs-lookup"><span data-stu-id="a5b92-153">Finally, call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ReleaseConnections%2A> method to release the connection.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="a5b92-154">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="a5b92-154">Next Step</span></span>  
 <span data-ttu-id="a5b92-155">После добавления и настройки компонента следующим шагом является создание путей между компонентами, которое рассматривается в разделе [Создание пути между двумя компонентами](../building-packages-programmatically/connecting-data-flow-components-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="a5b92-155">After adding and configuring the component, the next step is to create paths between components, which is discussed in the topic, [Creating a Path Between Two Components](../building-packages-programmatically/connecting-data-flow-components-programmatically.md).</span></span>  
  
## <a name="sample"></a><span data-ttu-id="a5b92-156">Образец</span><span class="sxs-lookup"><span data-stu-id="a5b92-156">Sample</span></span>  
 <span data-ttu-id="a5b92-157">В следующем образце кода компонент «Источник OLE DB» добавляется в задачу потока данных, создается экземпляр компонента времени разработки и выполняется настройка свойств компонента.</span><span class="sxs-lookup"><span data-stu-id="a5b92-157">The following code sample adds the OLE DB Source component to a data flow task, creates a design-time instance of the component, and configures the component's properties.</span></span> <span data-ttu-id="a5b92-158">Для этого образца необходима дополнительная ссылка на сборку Microsoft.SqlServer.DTSRuntimeWrap.</span><span class="sxs-lookup"><span data-stu-id="a5b92-158">This example requires an additional reference to the assembly Microsoft.SqlServer.DTSRuntimeWrap.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Runtime.Wrapper;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Runtime.Package package = new Runtime.Package();  
      Executable e = package.Executables.Add("STOCK:PipelineTask");  
      Runtime.TaskHost thMainPipe = e as Runtime.TaskHost;  
      MainPipe dataFlowTask = thMainPipe.InnerObject as MainPipe;  
  
      // Add an OLEDB connection manager to the package.  
      ConnectionManager cm = package.Connections.Add("OLEDB");  
      cm.Name = "OLEDB ConnectionManager";  
      cm.ConnectionString = "Data Source=(local);" +   
        "Initial Catalog=AdventureWorks;Provider=SQLOLEDB.1;" +   
        "Integrated Security=SSPI;"  
  
      // Add an OLE DB source to the data flow.  
      IDTSComponentMetaData100 component =   
        dataFlowTask.ComponentMetaDataCollection.New();  
      component.Name = "OLEDBSource";  
      component.ComponentClassID = "DTSAdapter.OleDbSource.1";  
      // You can also use the CLSID of the component instead of the PROGID.  
      //component.ComponentClassID = "{2C0A8BE5-1EDC-4353-A0EF-B778599C65A0}";  
  
      // Get the design time instance of the component.  
      CManagedComponentWrapper instance = component.Instantiate();  
  
      // Initialize the component  
      instance.ProvideComponentProperties();  
  
      // Specify the connection manager.  
      if (component.RuntimeConnectionCollection.Count > 0)  
      {  
        component.RuntimeConnectionCollection[0].ConnectionManager =   
          DtsConvert.GetExtendedInterface(package.Connections[0]);  
        component.RuntimeConnectionCollection[0].ConnectionManagerID =   
          package.Connections[0].ID;      }  
  
      // Set the custom properties.  
      instance.SetComponentProperty("AccessMode", 2);  
      instance.SetComponentProperty("SqlCommand",   
        "Select * from Production.Product");  
  
      // Reinitialize the metadata.  
      instance.AcquireConnections(null);  
      instance.ReinitializeMetaData();  
      instance.ReleaseConnections();  
  
      // Add other components to the data flow and connect them.  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
Module Module1  
  
  Sub Main()  
  
    Dim package As Microsoft.SqlServer.Dts.Runtime.Package = _  
      New Microsoft.SqlServer.Dts.Runtime.Package()  
    Dim e As Executable = package.Executables.Add("STOCK:PipelineTask")  
    Dim thMainPipe As Microsoft.SqlServer.Dts.Runtime.TaskHost = _  
      CType(e, Microsoft.SqlServer.Dts.Runtime.TaskHost)  
    Dim dataFlowTask As MainPipe = CType(thMainPipe.InnerObject, MainPipe)  
  
    ' Add an OLEDB connection manager to the package.  
    Dim cm As ConnectionManager = package.Connections.Add("OLEDB")  
    cm.Name = "OLEDB ConnectionManager"  
    cm.ConnectionString = "Data Source=(local);" & _  
      "Initial Catalog=AdventureWorks;Provider=SQLOLEDB.1;" & _  
      "Integrated Security=SSPI;"  
  
    ' Add an OLE DB source to the data flow.  
    Dim component As IDTSComponentMetaData100 = _  
      dataFlowTask.ComponentMetaDataCollection.New()  
    component.Name = "OLEDBSource"  
    component.ComponentClassID = "DTSAdapter.OleDbSource.1"  
    ' You can also use the CLSID of the component instead of the PROGID.  
    'component.ComponentClassID = "{2C0A8BE5-1EDC-4353-A0EF-B778599C65A0}";  
  
    ' Get the design time instance of the component.  
    Dim instance As CManagedComponentWrapper = component.Instantiate()  
  
    ' Initialize the component.  
    instance.ProvideComponentProperties()  
  
    ' Specify the connection manager.  
    If component.RuntimeConnectionCollection.Count > 0 Then  
      component.RuntimeConnectionCollection(0).ConnectionManager = _  
        DtsConvert.GetExtendedInterface(package.Connections(0))  
      component.RuntimeConnectionCollection(0).ConnectionManagerID = _  
        package.Connections(0).ID  
    End If  
  
    ' Set the custom properties.  
    instance.SetComponentProperty("AccessMode", 2)  
    instance.SetComponentProperty("SqlCommand", _  
      "Select * from Production.Product")  
  
    ' Reinitialize the metadata.  
    instance.AcquireConnections(vbNull)  
    instance.ReinitializeMetaData()  
    instance.ReleaseConnections()  
  
    ' Add other components to the data flow and connect them.  
  
  End Sub  
  
End Module  
```  
  
## <a name="external-resources"></a><span data-ttu-id="a5b92-159">Внешние ресурсы</span><span class="sxs-lookup"><span data-stu-id="a5b92-159">External Resources</span></span>  
 <span data-ttu-id="a5b92-160">Запись в блоге [EzAPI — обновление для SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223) на сайте blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="a5b92-160">Blog entry, [EzAPI - Updated for SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223), on blogs.msdn.com.</span></span>  
  
<span data-ttu-id="a5b92-161">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="a5b92-161">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="a5b92-162">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="a5b92-162">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="a5b92-163">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="a5b92-163">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="a5b92-164">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="a5b92-164">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5b92-165">См. также:</span><span class="sxs-lookup"><span data-stu-id="a5b92-165">See Also</span></span>  
 [<span data-ttu-id="a5b92-166">Программное соединение компонентов потока данных</span><span class="sxs-lookup"><span data-stu-id="a5b92-166">Connecting Data Flow Components Programmatically</span></span>](../building-packages-programmatically/connecting-data-flow-components-programmatically.md)  
  
  
