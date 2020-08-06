---
title: Методы времени разработки для компонента потока данных | Документы Майкрософт
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
- custom data flow components [Integration Services], method execution sequence
- ProcessInput method
- method execution sequence [Integration Services]
- PrimeOutput method
- data flow components [Integration Services], method execution sequence
ms.assetid: b5a121a1-b87c-441b-a42c-2cec628dc81c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e33fc4eb5805318dac217d2c5cbaedfd4bca70fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666181"
---
# <a name="design-time-methods-of-a-data-flow-component"></a><span data-ttu-id="cfd55-102">Методы времени разработки для компонента потока данных</span><span class="sxs-lookup"><span data-stu-id="cfd55-102">Design-time Methods of a Data Flow Component</span></span>
  <span data-ttu-id="cfd55-103">Перед выполнением задача потока данных считается находящейся в состоянии времени разработки, поскольку она подвергается добавочным изменениям.</span><span class="sxs-lookup"><span data-stu-id="cfd55-103">Before execution, the data flow task is said to be in a design-time state, as it undergoes incremental changes.</span></span> <span data-ttu-id="cfd55-104">К таким изменениям относятся добавление или удаление компонентов, добавление или удаление объектов пути, которые соединяют компоненты, и изменения в метаданных компонентов.</span><span class="sxs-lookup"><span data-stu-id="cfd55-104">Changes may include the addition or removal of components, the addition or removal of the path objects that connect components, and changes to the metadata of the components.</span></span> <span data-ttu-id="cfd55-105">При изменении метаданных компонент может отслеживать их и выполнять ответные действия.</span><span class="sxs-lookup"><span data-stu-id="cfd55-105">When metadata changes occur, the component can monitor and react to the changes.</span></span> <span data-ttu-id="cfd55-106">Например, компонент может не допускать внесения определенных изменений или вносить дополнительные изменения в ответ на изменение.</span><span class="sxs-lookup"><span data-stu-id="cfd55-106">For example, a component can disallow certain changes or make additional changes in response to a change.</span></span> <span data-ttu-id="cfd55-107">Во время разработки конструктор взаимодействует с компонентом через интерфейс <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> времени разработки.</span><span class="sxs-lookup"><span data-stu-id="cfd55-107">At design time, the designer interacts with a component through the design-time <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> interface.</span></span>

## <a name="design-time-implementation"></a><span data-ttu-id="cfd55-108">Реализация времени разработки</span><span class="sxs-lookup"><span data-stu-id="cfd55-108">Design-Time Implementation</span></span>
 <span data-ttu-id="cfd55-109">Интерфейс времени разработки компонента описывается интерфейсом <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100>.</span><span class="sxs-lookup"><span data-stu-id="cfd55-109">The design-time interface of a component is described by the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> interface.</span></span> <span data-ttu-id="cfd55-110">Хотя нельзя явным образом реализовать этот интерфейс, знакомство с методами, определенными в этом интерфейсе, поможет понять, какие методы базового класса <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> соответствуют экземпляру компонента времени разработки.</span><span class="sxs-lookup"><span data-stu-id="cfd55-110">Although you do not explicitly implement this interface, a familiarity with the methods defined in this interface will help you understand which methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class correspond to the design-time instance of a component.</span></span>

 <span data-ttu-id="cfd55-111">При загрузке компонента в среду [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] создается экземпляр компонента времени разработки, и при изменении компонента вызываются методы интерфейса <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100>.</span><span class="sxs-lookup"><span data-stu-id="cfd55-111">When a component is loaded in the [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], the design-time instance of the component is instantiated and the methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> interface are called as the component is edited.</span></span> <span data-ttu-id="cfd55-112">Реализация базового класса позволяет переопределить только те методы, которые необходимы для компонента.</span><span class="sxs-lookup"><span data-stu-id="cfd55-112">The implementation of the base class lets you override only those methods that your component requires.</span></span> <span data-ttu-id="cfd55-113">Во многих случаях можно переопределить эти методы, чтобы предотвратить внесение неправильных изменений в компонент.</span><span class="sxs-lookup"><span data-stu-id="cfd55-113">In many cases, you may override these methods to prevent inappropriate edits to a component.</span></span> <span data-ttu-id="cfd55-114">Например, чтобы не дать пользователям возможности добавлять выход в компонент, переопределите метод <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.InsertOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="cfd55-114">For example, to prevent users from adding an output to a component, override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.InsertOutput%2A> method.</span></span> <span data-ttu-id="cfd55-115">В противном случае при вызове реализации этого метода базовым классом он добавляет выход в компонент.</span><span class="sxs-lookup"><span data-stu-id="cfd55-115">Otherwise, when the implementation of this method by the base class is called, it adds an output to the component.</span></span>

 <span data-ttu-id="cfd55-116">Независимо от предназначения или функциональности компонента, следует переопределить методы <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> и <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A>.</span><span class="sxs-lookup"><span data-stu-id="cfd55-116">Regardless of the purpose or functionality of your component, you should override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A>, and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A> methods.</span></span> <span data-ttu-id="cfd55-117">Дополнительные сведения о <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> и <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A> см. в разделе [Проверка компонента потока данных](validating-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="cfd55-117">For more information about <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A>, see [Validating a Data Flow Component](validating-a-data-flow-component.md).</span></span>

## <a name="providecomponentproperties-method"></a><span data-ttu-id="cfd55-118">Метод ProvideComponentProperties</span><span class="sxs-lookup"><span data-stu-id="cfd55-118">ProvideComponentProperties Method</span></span>
 <span data-ttu-id="cfd55-119">Инициализация компонента происходит в методе <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="cfd55-119">The initialization of a component occurs in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> method.</span></span> <span data-ttu-id="cfd55-120">Этот метод вызывается конструктором служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] при добавлении компонента в задачу потока данных. Он аналогичен конструктору классов.</span><span class="sxs-lookup"><span data-stu-id="cfd55-120">This method is called by [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer when a component is added to the data flow task, and is similar to a class constructor.</span></span> <span data-ttu-id="cfd55-121">Разработчикам компонентов следует создавать и инициализировать свои входы, выходы и пользовательские свойства во время вызова этого метода.</span><span class="sxs-lookup"><span data-stu-id="cfd55-121">Component developers should create and initialize their inputs, outputs, and custom properties during this method call.</span></span> <span data-ttu-id="cfd55-122">Метод <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> отличается от конструктора тем, что не вызывается каждый раз при создании экземпляра компонента времени разработки или времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="cfd55-122">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> method differs from a constructor because it is not called every time that the design-time instance or run-time instance of the component is instantiated.</span></span>

 <span data-ttu-id="cfd55-123">Реализация этого метода базового класса добавляет вход и выход в компонент и присваивает идентификатор входа в качестве значения свойства <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A>.</span><span class="sxs-lookup"><span data-stu-id="cfd55-123">The base class implementation of the method adds an input and an output to the component and assigns the ID of the input to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> property.</span></span> <span data-ttu-id="cfd55-124">Однако в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] объекты входа и выхода, добавленные базовым классом, не именуются.</span><span class="sxs-lookup"><span data-stu-id="cfd55-124">However, in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the input and output objects added by the base class are not named.</span></span> <span data-ttu-id="cfd55-125">Успешная загрузка пакетов, содержащих компонент с объектами входа или выхода, свойство Name которых не задано, невозможна.</span><span class="sxs-lookup"><span data-stu-id="cfd55-125">Packages that contain a component with input or output objects whose Name property is not set will not successfully load.</span></span> <span data-ttu-id="cfd55-126">Поэтому при использовании базовой реализации нужно явным образом назначить значения свойству Name входа и выхода по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cfd55-126">Therefore, when you use the base implementation, you must assign values explicitly to the Name property of the default input and output.</span></span>

```csharp
public override void ProvideComponentProperties()
{
    /// TODO: Reset the component.
    /// TODO: Add custom properties.
    /// TODO: Add input objects.
    /// TODO: Add output objects.
}
```

```vb
Public Overrides Sub ProvideComponentProperties()
    ' TODO: Reset the component.
    ' TODO: Add custom properties.
    ' TODO: Add input objects.
    ' TODO: Add output objects.
End Sub
```

### <a name="creating-custom-properties"></a><span data-ttu-id="cfd55-127">Создание пользовательских свойств</span><span class="sxs-lookup"><span data-stu-id="cfd55-127">Creating Custom Properties</span></span>
 <span data-ttu-id="cfd55-128">Разработчики компонентов должны добавлять пользовательские свойства (<xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>) в компонент с помощью вызова метода <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100>.</span><span class="sxs-lookup"><span data-stu-id="cfd55-128">The call to the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> method is where component developers should add custom properties (<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100>) to the component.</span></span> <span data-ttu-id="cfd55-129">Пользовательские свойства не имеют свойства типа данных.</span><span class="sxs-lookup"><span data-stu-id="cfd55-129">Custom properties do not have a data type property.</span></span> <span data-ttu-id="cfd55-130">Тип данных пользовательского свойства определяется типом данных значения, которое присвоено его свойству <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="cfd55-130">The data type of a custom property is set by the data type of the value that you assign to its <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.Value%2A> property.</span></span> <span data-ttu-id="cfd55-131">Однако после присвоения пользовательскому свойству исходного значения присвоить ему значение с другим типом данных нельзя.</span><span class="sxs-lookup"><span data-stu-id="cfd55-131">However, after you have assigned an initial value to the custom property, you cannot assign a value with a different data type.</span></span>

> [!NOTE]
>  <span data-ttu-id="cfd55-132">Интерфейс <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100> обеспечивает ограниченную поддержку значений свойств типа `Object`.</span><span class="sxs-lookup"><span data-stu-id="cfd55-132">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100> interface has limited support for property values of type `Object`.</span></span> <span data-ttu-id="cfd55-133">Единственный объект, который можно сохранять в качестве значения пользовательского свойства, – это массив простых типов, например, строк или целых чисел.</span><span class="sxs-lookup"><span data-stu-id="cfd55-133">The only object that you can store as the value of a custom property is an array of simple types such as strings or integers.</span></span>

 <span data-ttu-id="cfd55-134">Можно указать, что пользовательское свойство поддерживает выражения свойств, присвоив его свойству <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.ExpressionType%2A> в качестве значения `CPET_NOTIFY` из перечисления <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSCustomPropertyExpressionType>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="cfd55-134">You can indicate that your custom property supports property expressions by setting the value of its <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.ExpressionType%2A> property to `CPET_NOTIFY` from the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSCustomPropertyExpressionType> enumeration, as shown in the following example.</span></span> <span data-ttu-id="cfd55-135">Нет необходимости добавлять какой-либо код для обработки или проверки выражения свойства, введенного пользователем.</span><span class="sxs-lookup"><span data-stu-id="cfd55-135">You do not have to add any code to handle or to validate the property expression entered by the user.</span></span> <span data-ttu-id="cfd55-136">Можно задать значение для свойства по умолчанию, проверить его значение, прочитать и использовать это значение обычным образом.</span><span class="sxs-lookup"><span data-stu-id="cfd55-136">You can set a default value for the property, validate its value, and read and use its value normally.</span></span>

```csharp
IDTSCustomProperty100 myCustomProperty;
...
myCustomProperty.ExpressionType = DTSCustomPropertyExpressionType.CPET_NOTIFY;
```

```vb
Dim myCustomProperty As IDTSCustomProperty100
...
myCustomProperty.ExpressionType = DTSCustomPropertyExpressionType.CPET_NOTIFY
```

 <span data-ttu-id="cfd55-137">Можно ограничить выбор пользователем значения пользовательского свойства из перечисления с помощью <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.TypeConverter%2A> свойства, как показано в следующем примере, в котором предполагается, что вы определили Открытое перечисление с именем `MyValidValues` .</span><span class="sxs-lookup"><span data-stu-id="cfd55-137">You can limit users to selecting a custom property value from an enumeration by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.TypeConverter%2A> property, as shown in the following example, which assumes that you have defined a public enumeration named `MyValidValues`.</span></span>

```csharp
IDTSCustomProperty100 customProperty = outputColumn.CustomPropertyCollection.New();
customProperty.Name = "My Custom Property";
// This line associates the type with the custom property.
customProperty.TypeConverter = typeof(MyValidValues).AssemblyQualifiedName;
// Now you can use the enumeration values directly.
customProperty.Value = MyValidValues.ValueOne;  
```

```vb
Dim customProperty As IDTSCustomProperty100 = outputColumn.CustomPropertyCollection.New 
customProperty.Name = "My Custom Property" 
' This line associates the type with the custom property.
customProperty.TypeConverter = GetType(MyValidValues).AssemblyQualifiedName 
' Now you can use the enumeration values directly.
customProperty.Value = MyValidValues.ValueOne
```

 <span data-ttu-id="cfd55-138">Дополнительные сведения см. в разделах "Преобразование обобщенного типа" и "Реализация преобразователя типов" [библиотеки MSDN](https://go.microsoft.com/fwlink/?LinkId=7022).</span><span class="sxs-lookup"><span data-stu-id="cfd55-138">For more information, see "Generalized Type Conversion" and "Implementing a Type Converter" in the [MSDN Library](https://go.microsoft.com/fwlink/?LinkId=7022).</span></span>

 <span data-ttu-id="cfd55-139">С помощью свойства <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A> в качестве значения пользовательского свойства можно указать диалоговое окно пользовательского редактора, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="cfd55-139">You can specify a custom editor dialog box for the value of your custom property by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A> property, as shown in the following example.</span></span> <span data-ttu-id="cfd55-140">Сначала необходимо создать пользовательский редактор типов, наследующий от `System.Drawing.Design.UITypeEditor`, если не удается найти существующий класс редактора типов пользовательских интерфейсов, отвечающий потребностям пользователя.</span><span class="sxs-lookup"><span data-stu-id="cfd55-140">First, you must create a custom type editor that inherits from `System.Drawing.Design.UITypeEditor`, if you cannot locate an existing UI type editor class that fits your needs.</span></span>

```csharp
public class MyCustomTypeEditor : UITypeEditor
{
...
}
```

```vb
Public Class MyCustomTypeEditor
  Inherits UITypeEditor 
  ...
End Class
```

 <span data-ttu-id="cfd55-141">Затем укажите этот класс в качестве значения для свойства <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A> пользовательского свойства.</span><span class="sxs-lookup"><span data-stu-id="cfd55-141">Next, specify this class as the value of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A> property of your custom property.</span></span>

```csharp
IDTSCustomProperty100 customProperty = outputColumn.CustomPropertyCollection.New();
customProperty.Name = "My Custom Property";
// This line associates the editor with the custom property.
customProperty.UITypeEditor = typeof(MyCustomTypeEditor).AssemblyQualifiedName;
```

```vb
Dim customProperty As IDTSCustomProperty100 = outputColumn.CustomPropertyCollection.New 
customProperty.Name = "My Custom Property" 
' This line associates the editor with the custom property.
customProperty.UITypeEditor = GetType(MyCustomTypeEditor).AssemblyQualifiedName
```

 <span data-ttu-id="cfd55-142">Дополнительные сведения см. в разделе "Реализация редактора типов пользовательских интерфейсов" [библиотеки MSDN](https://go.microsoft.com/fwlink/?LinkId=7022).</span><span class="sxs-lookup"><span data-stu-id="cfd55-142">For more information, see "Implementing a UI Type Editor" in the [MSDN Library](https://go.microsoft.com/fwlink/?LinkId=7022).</span></span>

<span data-ttu-id="cfd55-143">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="cfd55-143">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="cfd55-144">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="cfd55-144">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="cfd55-145">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="cfd55-145">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="cfd55-146">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="cfd55-146">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="cfd55-147">См. также:</span><span class="sxs-lookup"><span data-stu-id="cfd55-147">See Also</span></span>
 [<span data-ttu-id="cfd55-148">Методы времени выполнения для компонента потока данных</span><span class="sxs-lookup"><span data-stu-id="cfd55-148">Run-time Methods of a Data Flow Component</span></span>](run-time-methods-of-a-data-flow-component.md)


