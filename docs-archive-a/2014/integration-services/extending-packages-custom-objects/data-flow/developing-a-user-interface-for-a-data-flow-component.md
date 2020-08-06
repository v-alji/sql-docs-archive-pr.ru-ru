---
title: Разработка пользовательского интерфейса для компонента потока данных | Документы Майкрософт
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
- data flow components [Integration Services], custom editors
- user interfaces [Integration Services]
- custom data flow components [Integration Services], custom editors
- custom component editors [Integration Services]
- IDtsComponentUI interface
- UITypeName property
- custom user interface [Integration Services], custom data flow component
- editors [Integration Services]
ms.assetid: 10b829a1-609b-42e3-9070-cfe5a2bb698c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f97f21ad14a5fa67fb49192931a0cb46d0cb41da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729665"
---
# <a name="developing-a-user-interface-for-a-data-flow-component"></a><span data-ttu-id="543bb-102">Разработка пользовательского интерфейса для компонента потока данных</span><span class="sxs-lookup"><span data-stu-id="543bb-102">Developing a User Interface for a Data Flow Component</span></span>
  <span data-ttu-id="543bb-103">Разработчики компонентов могут включить для компонента настраиваемый пользовательский интерфейс, отображающийся в среде [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] во время изменения компонента.</span><span class="sxs-lookup"><span data-stu-id="543bb-103">Component developers can provide a custom user interface for a component, which is displayed in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] when the component is edited.</span></span> <span data-ttu-id="543bb-104">Реализация пользовательского интерфейса обеспечивает возможность получать уведомления, когда компонент добавляется или удаляется из задачи потока данных или при вызове справки по компоненту.</span><span class="sxs-lookup"><span data-stu-id="543bb-104">Implementing a custom user interface provides you with notification when the component is added to or deleted from a data flow task, and when help is requested for the component.</span></span>

 <span data-ttu-id="543bb-105">Если не создать для компонента пользовательский интерфейс, пользователи смогут настраивать компонент и его свойства с помощью расширенного редактора.</span><span class="sxs-lookup"><span data-stu-id="543bb-105">If you do not provide a custom user interface for your component, users can still configure the component and its custom properties by using the Advanced Editor.</span></span> <span data-ttu-id="543bb-106">Можно при необходимости убедиться, что расширенный редактор позволяет пользователям правильно изменять значения пользовательских свойств, с помощью свойств <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.TypeConverter%2A> и <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A> интерфейса <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100>.</span><span class="sxs-lookup"><span data-stu-id="543bb-106">You can ensure that the Advanced Editor allows users to edit custom property values appropriately by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.TypeConverter%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A> properties of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100> when appropriate.</span></span> <span data-ttu-id="543bb-107">Дополнительные сведения см. в пункте "Создание пользовательских свойств" раздела [Методы времени разработки для компонента потока данных](design-time-methods-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="543bb-107">For more information, see "Creating Custom Properties" in [Design-time Methods of a Data Flow Component](design-time-methods-of-a-data-flow-component.md).</span></span>

## <a name="setting-the-uitypename-property"></a><span data-ttu-id="543bb-108">Указание свойства UITypeName</span><span class="sxs-lookup"><span data-stu-id="543bb-108">Setting the UITypeName Property</span></span>
 <span data-ttu-id="543bb-109">Чтобы обеспечить пользовательский интерфейс, разработчик должен указать в качестве свойства <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A> атрибута <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute> имя класса, реализующего интерфейс <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI>.</span><span class="sxs-lookup"><span data-stu-id="543bb-109">To provide a custom user interface, the developer must set the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A> property of the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute> to the name of a class that implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> interface.</span></span> <span data-ttu-id="543bb-110">Если это свойство задается компонентом, службы [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] загружаются и вызывают пользовательский интерфейс при изменении компонента в конструкторе [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="543bb-110">When this property is set by the component, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] loads and calls the custom user interface when the component is edited in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>

 <span data-ttu-id="543bb-111">Свойство <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A> представляет собой разделенную запятыми строку, указывающую полное имя типа.</span><span class="sxs-lookup"><span data-stu-id="543bb-111">The <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A> property is a comma-delimited string that identifies the fully qualified name of the type.</span></span> <span data-ttu-id="543bb-112">В следующем списке показаны по порядку элементы, указывающие тип.</span><span class="sxs-lookup"><span data-stu-id="543bb-112">The following list shows, in order, the elements that identify the type:</span></span>

-   <span data-ttu-id="543bb-113">Имя типа</span><span class="sxs-lookup"><span data-stu-id="543bb-113">Type name</span></span>

-   <span data-ttu-id="543bb-114">Имя сборки</span><span class="sxs-lookup"><span data-stu-id="543bb-114">Assembly name</span></span>

-   <span data-ttu-id="543bb-115">Версия файла</span><span class="sxs-lookup"><span data-stu-id="543bb-115">File version</span></span>

-   <span data-ttu-id="543bb-116">Язык и региональные параметры</span><span class="sxs-lookup"><span data-stu-id="543bb-116">Culture</span></span>

-   <span data-ttu-id="543bb-117">Токен открытого ключа</span><span class="sxs-lookup"><span data-stu-id="543bb-117">Public key token</span></span>

 <span data-ttu-id="543bb-118">В следующем примере кода показан класс, производный от базового класса <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> и задающий свойство <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A>.</span><span class="sxs-lookup"><span data-stu-id="543bb-118">The following code example shows a class that derives from the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class and specifies the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A> property.</span></span>

```csharp
[DtsPipelineComponent(
DisplayName="SampleComponent",
UITypeName="MyNamespace.MyComponentUIClassName,MyAssemblyName,Version=1.0.0.0,Culture=neutral,PublicKeyToken=abcd...",
ComponentType = ComponentType.Transform)]
public class SampleComponent : PipelineComponent
{
//TODO: Implement the component here.
}
```

```vb
<DtsPipelineComponent(DisplayName="SampleComponent", _
UITypeName="MyNamespace.MyComponentUIClassName,MyAssemblyName,Version=1.0.0.0,Culture=neutral,PublicKeyToken=abcd...", ComponentType=ComponentType.Transform)> _ 
Public Class SampleComponent 
 Inherits PipelineComponent 
End Class
```

## <a name="implementing-the-idtscomponentui-interface"></a><span data-ttu-id="543bb-119">Реализация интерфейса IDtsComponentUI</span><span class="sxs-lookup"><span data-stu-id="543bb-119">Implementing the IDtsComponentUI Interface</span></span>
 <span data-ttu-id="543bb-120">Интерфейс <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> содержит методы, которые конструктор служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] вызывает при добавлении, удалении и изменении компонента.</span><span class="sxs-lookup"><span data-stu-id="543bb-120">The <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> interface contains methods that [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer calls when a component is added, deleted, and edited.</span></span> <span data-ttu-id="543bb-121">Разработчики компонентов могут включить в свои реализации код этих методов для взаимодействия с пользователями компонента.</span><span class="sxs-lookup"><span data-stu-id="543bb-121">Component developers can provide code in their implementation of these methods to interact with users of the component.</span></span>

 <span data-ttu-id="543bb-122">Этот класс обычно реализуется в сборке, отдельной от самого компонента.</span><span class="sxs-lookup"><span data-stu-id="543bb-122">This class is typically implemented in an assembly separate from the component itself.</span></span> <span data-ttu-id="543bb-123">Хотя использование отдельной сборки необязательно, это позволяет разработчикам создавать и развертывать компонент и пользовательский интерфейс независимо, а также сохранять небольшой размер двоичного кода компонента.</span><span class="sxs-lookup"><span data-stu-id="543bb-123">Although use of a separate assembly is not required, this lets the developer build and deploy the component and the user interface independently of each other, and keeps the binary footprint of the component small.</span></span>

 <span data-ttu-id="543bb-124">Реализация пользовательского интерфейса предоставляет разработчику больше возможностей по управлению компонентом во время изменения в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="543bb-124">Implementing a custom user interface gives the component developer more control over the component as it is edited in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="543bb-125">Например, компонент может добавить код в метод <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.New%2A>, который вызывается при первом добавлении компонента в задачу потока данных, и открыть мастер, помогающий пользователю выполнить первичную настройку компонента.</span><span class="sxs-lookup"><span data-stu-id="543bb-125">For example, a component can add code to the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.New%2A> method, which is called when a component is initially added to a data flow task, and display a wizard that guides the user through the initial configuration of the component.</span></span>

 <span data-ttu-id="543bb-126">После создания класса, реализующего интерфейс <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI>, необходимо добавить код, отвечающий на взаимодействие пользователя с компонентом.</span><span class="sxs-lookup"><span data-stu-id="543bb-126">After you have created a class that implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> interface, you must add code to respond to user interaction with the component.</span></span> <span data-ttu-id="543bb-127">Метод <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A> предоставляет интерфейс <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> компонента и вызывается перед методами <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.New%2A> и <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A>.</span><span class="sxs-lookup"><span data-stu-id="543bb-127">The <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A> method provides the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface of the component, and is called before the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.New%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> methods.</span></span> <span data-ttu-id="543bb-128">Эта ссылка должна быть сохранена в переменной закрытого члена класса и использоваться для последующих изменений метаданных компонента.</span><span class="sxs-lookup"><span data-stu-id="543bb-128">This reference should be stored in a private member variable and used to modify the component's metadata thereafter.</span></span>

## <a name="modifying-a-component-and-persisting-changes"></a><span data-ttu-id="543bb-129">Изменение компонента и устойчивые изменения</span><span class="sxs-lookup"><span data-stu-id="543bb-129">Modifying a Component and Persisting Changes</span></span>
 <span data-ttu-id="543bb-130">Интерфейс <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> передается в качестве параметра методу <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A>.</span><span class="sxs-lookup"><span data-stu-id="543bb-130">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface is provided as a parameter to the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A> method.</span></span> <span data-ttu-id="543bb-131">Эта ссылка должна кэшироваться в переменной члена кодом пользовательского интерфейса, а затем использоваться для изменения компонента в ответ на взаимодействие пользователя с интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="543bb-131">This reference should be cached in a member variable by the user interface code, and then used to modify the component in response to user interaction with the user interface.</span></span>

 <span data-ttu-id="543bb-132">Хотя можно изменить компонент напрямую с помощью интерфейса <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>, лучше создать экземпляр <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper> с помощью метода <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.Instantiate%2A>.</span><span class="sxs-lookup"><span data-stu-id="543bb-132">Although you can modify the component directly through the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface, it is better to create an instance of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper> by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.Instantiate%2A> method.</span></span> <span data-ttu-id="543bb-133">При непосредственном изменении компонента с помощью интерфейса проверочная защита компонента обходится.</span><span class="sxs-lookup"><span data-stu-id="543bb-133">When you edit the component directly by using the interface, you bypass the component's validation safeguards.</span></span> <span data-ttu-id="543bb-134">Преимуществом использования экземпляра среды разработки для проектирования компонента с помощью <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper> является возможность удостовериться, что компонент может управлять внесенными в него изменениями.</span><span class="sxs-lookup"><span data-stu-id="543bb-134">The advantage of using the design-time instance of the component through the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper> is that you ensure that the component has control over the changes made to it.</span></span>

 <span data-ttu-id="543bb-135">Возвращаемое значение метода <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> определяет, сохранились ли или отменены изменения, внесенные в компонент.</span><span class="sxs-lookup"><span data-stu-id="543bb-135">The return value of the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> method determines whether changes made to a component are persisted or discarded.</span></span> <span data-ttu-id="543bb-136">Если метод возвращает значение `false`, все изменения отменяются; при значении `true` изменения в компоненте сохраняются, а пакет помечается как нуждающийся в сохранении.</span><span class="sxs-lookup"><span data-stu-id="543bb-136">When this method returns `false`, all changes are discarded; `true` persists the changes to the component and marks the package as needing to be saved.</span></span>

### <a name="using-the-services-of-the-ssis-designer"></a><span data-ttu-id="543bb-137">Использование служб конструктора служб SSIS</span><span class="sxs-lookup"><span data-stu-id="543bb-137">Using the Services of the SSIS Designer</span></span>
 <span data-ttu-id="543bb-138">Параметр `IServiceProvider` метода <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A> предоставляет доступ к следующим службам конструктора служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="543bb-138">The `IServiceProvider` parameter of the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A> method provides access to the following services of [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer:</span></span>

|<span data-ttu-id="543bb-139">Служба</span><span class="sxs-lookup"><span data-stu-id="543bb-139">Service</span></span>|<span data-ttu-id="543bb-140">Description</span><span class="sxs-lookup"><span data-stu-id="543bb-140">Description</span></span>|
|-------------|-----------------|
|<xref:Microsoft.SqlServer.Dts.Design.IDtsClipboardService>|<span data-ttu-id="543bb-141">Используется для определения, был ли компонент создан в ходе операции копирования и вставки или вырезания и вставки.</span><span class="sxs-lookup"><span data-stu-id="543bb-141">Used to determine whether the component was generated as part of a copy/paste or cut/paste operation.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionService>|<span data-ttu-id="543bb-142">Используется для доступа к существующим соединениям или для создания новых соединений в пакете.</span><span class="sxs-lookup"><span data-stu-id="543bb-142">Used to access existing connections or to create new connections in the package.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Design.IErrorCollectionService>|<span data-ttu-id="543bb-143">Используется для получения событий из компонентов потока данных, если требуется зафиксировать все возникающие ошибки и предупреждения, а не только получить последнее сообщение об ошибке или предупреждение.</span><span class="sxs-lookup"><span data-stu-id="543bb-143">Used to capture events from data flow components when you need to capture all the errors and warnings raised by the component instead of receiving only the last error or warning.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsVariableService>|<span data-ttu-id="543bb-144">Используется для доступа к существующим переменным или для создания новых переменных в пакете.</span><span class="sxs-lookup"><span data-stu-id="543bb-144">Used to access existing variables or to create new variables in the package.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Design.IDtsPipelineEnvironmentService>|<span data-ttu-id="543bb-145">Используется компонентами потока данных для доступа к родительской задаче потока данных и другим компонентам в потоке данных.</span><span class="sxs-lookup"><span data-stu-id="543bb-145">Used by data flow components to access the parent Data Flow task and other components in the data flow.</span></span> <span data-ttu-id="543bb-146">Эту функцию можно использовать для разработки такого компонента, как мастер медленно изменяющихся измерений, при необходимости создающего дополнительные компоненты потока данных.</span><span class="sxs-lookup"><span data-stu-id="543bb-146">This feature could be used to develop a component like the Slowly Changing Dimension Wizard that creates and connects additional data flow components as needed.</span></span>|

 <span data-ttu-id="543bb-147">Эти службы предоставляют разработчикам компонентов возможность доступа к объектам и создания объектов в пакете, в котором загружен компонент.</span><span class="sxs-lookup"><span data-stu-id="543bb-147">These services provide component developers the ability to access and create objects in the package in which the component is loaded.</span></span>

## <a name="sample"></a><span data-ttu-id="543bb-148">Образец</span><span class="sxs-lookup"><span data-stu-id="543bb-148">Sample</span></span>
 <span data-ttu-id="543bb-149">В следующем примере кода показана интеграция класса пользовательского интерфейса, реализующего интерфейс <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI>, и форма Windows, служащая редактором компонента.</span><span class="sxs-lookup"><span data-stu-id="543bb-149">The following code example shows the integration of a custom user interface class that implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> interface, and a Windows form that serves as the editor for a component.</span></span>

### <a name="custom-user-interface-class"></a><span data-ttu-id="543bb-150">Собственный класс пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="543bb-150">Custom User Interface Class</span></span>
 <span data-ttu-id="543bb-151">В следующем примере кода показан класс, реализующий интерфейс <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI>.</span><span class="sxs-lookup"><span data-stu-id="543bb-151">The following code shows the class that implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> interface.</span></span> <span data-ttu-id="543bb-152">Метод <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> создает редактор компонента и отображает форму.</span><span class="sxs-lookup"><span data-stu-id="543bb-152">The <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> method creates the component editor and then displays the form.</span></span> <span data-ttu-id="543bb-153">Возвращаемое формой значение определяет, сохраняются ли изменения, внесенные в компонент.</span><span class="sxs-lookup"><span data-stu-id="543bb-153">The return value of the form determines whether changes to the component are persisted.</span></span>

```csharp
using System;
using System.Windows.Forms;
using Microsoft.SqlServer.Dts.Runtime;
using Microsoft.SqlServer.Dts.Pipeline.Design;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;

namespace Microsoft.Samples.SqlServer.Dts
{
    public class SampleComponentUI : IDtsComponentUI
    {
        IDTSComponentMetaData100 md;
        IServiceProvider sp;

        public void Help(System.Windows.Forms.IWin32Window parentWindow)
        {
        }
        public void New(System.Windows.Forms.IWin32Window parentWindow)
        {
        }
        public void Delete(System.Windows.Forms.IWin32Window parentWindow)
        {
        }
        public bool Edit(System.Windows.Forms.IWin32Window parentWindow, Variables vars, Connections cons)
        {
            // Create and display the form for the user interface.
            SampleComponentUIForm componentEditor = new SampleComponentUIForm(cons, vars, md);

            DialogResult result  = componentEditor.ShowDialog(parentWindow);

            if (result == DialogResult.OK)
                return true;

            return false;
        }
        public void Initialize(IDTSComponentMetaData100 dtsComponentMetadata, IServiceProvider serviceProvider)
        {
            // Store the component metadata.
            this.md = dtsComponentMetadata;
        }
    }
}
```

```vb
Imports System 
Imports System.Windows.Forms 
Imports Microsoft.SqlServer.Dts.Runtime 
Imports Microsoft.SqlServer.Dts.Pipeline.Design 
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper 

Namespace Microsoft.Samples.SqlServer.Dts 

 Public Class SampleComponentUI 
 Implements IDtsComponentUI 
   Private md As IDTSComponentMetaData100 
   Private sp As IServiceProvider 

   Public Sub Help(ByVal parentWindow As System.Windows.Forms.IWin32Window) 
   End Sub 

   Public Sub New(ByVal parentWindow As System.Windows.Forms.IWin32Window) 
   End Sub 

   Public Sub Delete(ByVal parentWindow As System.Windows.Forms.IWin32Window) 
   End Sub 

   Public Function Edit(ByVal parentWindow As System.Windows.Forms.IWin32Window, ByVal vars As Variables, ByVal cons As Connections) As Boolean 
     ' Create and display the form for the user interface.
     Dim componentEditor As SampleComponentUIForm = New SampleComponentUIForm(cons, vars, md) 
     Dim result As DialogResult = componentEditor.ShowDialog(parentWindow) 
     If result = DialogResult.OK Then 
       Return True 
     End If 
     Return False 
   End Function 

   Public Sub Initialize(ByVal dtsComponentMetadata As IDTSComponentMetaData100, ByVal serviceProvider As IServiceProvider) 
     Me.md = dtsComponentMetadata 
   End Sub 
 End Class 

End Namespace
```

### <a name="custom-editor"></a><span data-ttu-id="543bb-154">Пользовательский редактор</span><span class="sxs-lookup"><span data-stu-id="543bb-154">Custom Editor</span></span>
 <span data-ttu-id="543bb-155">В следующем примере кода показана реализация формы Windows, отображающейся во время вызова метода <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A>.</span><span class="sxs-lookup"><span data-stu-id="543bb-155">The following code shows the implementation of the Windows form that is shown during the call to the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> method.</span></span>

```csharp
using System;
using System.Drawing;
using System.Collections;
using System.ComponentModel;
using System.Windows.Forms;
using System.Data;

using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.Samples.SqlServer.Dts
{
    public partial class SampleComponentUIForm : System.Windows.Forms.Form
    {
        private Connections connections;
        private Variables variables;
        private IDTSComponentMetaData100 metaData;
        private CManagedComponentWrapper designTimeInstance;
        private System.ComponentModel.IContainer components = null;

        public SampleComponentUIForm( Connections cons, Variables vars, IDTSComponentMetaData100 md)
        {
            variables = vars;
            connections = cons;
            metaData = md;
        }

        private void btnOk_Click(object sender, System.EventArgs e)
        {
            if (designTimeInstance == null)
                designTimeInstance = metaData.Instantiate();

            designTimeInstance.SetComponentProperty( "CustomProperty", txtCustomPropertyValue.Text);

            this.Close();
        }

        private void btnCancel_Click(object sender, System.EventArgs e)
        {
            this.Close();
        }
    }
}
```

```vb
Imports System 
Imports System.Drawing 
Imports System.Collections 
Imports System.ComponentModel 
Imports System.Windows.Forms 
Imports System.Data 
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper 
Imports Microsoft.SqlServer.Dts.Runtime 

Namespace Microsoft.Samples.SqlServer.Dts 

 Public Partial Class SampleComponentUIForm 
  Inherits System.Windows.Forms.Form 
   Private connections As Connections 
   Private variables As Variables 
   Private metaData As IDTSComponentMetaData100 
   Private designTimeInstance As CManagedComponentWrapper 
   Private components As System.ComponentModel.IContainer = Nothing 

   Public Sub New(ByVal cons As Connections, ByVal vars As Variables, ByVal md As IDTSComponentMetaData100) 
     variables = vars 
     connections = cons 
     metaData = md 
   End Sub 

   Private Sub btnOk_Click(ByVal sender As Object, ByVal e As System.EventArgs) 
     If designTimeInstance Is Nothing Then 
       designTimeInstance = metaData.Instantiate 
     End If 
     designTimeInstance.SetComponentProperty("CustomProperty", txtCustomPropertyValue.Text) 
     Me.Close 
   End Sub 

   Private Sub btnCancel_Click(ByVal sender As Object, ByVal e As System.EventArgs) 
     Me.Close 
   End Sub 
 End Class 

End Namespace
```

<span data-ttu-id="543bb-156">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="543bb-156">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="543bb-157">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="543bb-157">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="543bb-158">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="543bb-158">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="543bb-159">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="543bb-159">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="543bb-160">См. также:</span><span class="sxs-lookup"><span data-stu-id="543bb-160">See Also</span></span>
 [<span data-ttu-id="543bb-161">Создание пользовательского компонента потока данных</span><span class="sxs-lookup"><span data-stu-id="543bb-161">Creating a Custom Data Flow Component</span></span>](creating-a-custom-data-flow-component.md)


