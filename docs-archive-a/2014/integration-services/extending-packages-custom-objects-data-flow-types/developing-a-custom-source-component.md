---
title: Разработка пользовательского компонента источника | Документы Майкрософт
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
- validation [Integration Services], components
- external data sources [Integration Services]
- data flow components [Integration Services], source components
- output columns [Integration Services]
- custom data flow components [Integration Services], source components
- custom sources [Integration Services]
- source components [Integration Services]
ms.assetid: 4dc0f631-8fd6-4007-b573-ca67f58ca068
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6679b28463a09efe069235a5aef9dca54a381d62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736620"
---
# <a name="developing-a-custom-source-component"></a><span data-ttu-id="ca4ab-102">Разработка пользовательского компонента источника</span><span class="sxs-lookup"><span data-stu-id="ca4ab-102">Developing a Custom Source Component</span></span>
  <span data-ttu-id="ca4ab-103">Службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] предоставляют разработчикам возможность создавать компоненты источника, которые могут подключаться к пользовательским источникам данных и предоставлять данные из этих источников другим компонентам в задаче потока данных.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] gives developers the ability to write source components that can connect to custom data sources and supply data from those sources to other components in a data flow task.</span></span> <span data-ttu-id="ca4ab-104">Возможность создавать пользовательские источники становится полезной, если возникает необходимость подключаться к источникам данных, доступ к которым нельзя получить с помощью одного из существующих источников служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca4ab-104">The ability to create custom sources is valuable when you must connect to data sources that cannot be accessed by using one of the existing [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sources.</span></span>

 <span data-ttu-id="ca4ab-105">Компоненты источника имеют один или несколько выходов и не имеют входов.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-105">Source components have one or more outputs and zero inputs.</span></span> <span data-ttu-id="ca4ab-106">Во время разработки компоненты источника используются для создания и настройки соединений, чтения метаданных столбца из внешнего источника данных и настройки выходных столбцов источника, исходя из внешнего источника данных.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-106">At design time, source components are used to create and configure connections, read column metadata from the external data source, and configure the source's output columns based on the external data source.</span></span> <span data-ttu-id="ca4ab-107">Во время выполнения они подключаются к внешнему источнику данных и добавляют строки в выходной буфер.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-107">During execution they connect to the external data source and add rows to an output buffer.</span></span> <span data-ttu-id="ca4ab-108">Затем задача потока данных предоставляет этот буфер со строками данных для нижестоящих компонентов.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-108">The data flow task then provides this buffer of data rows to downstream components.</span></span>

 <span data-ttu-id="ca4ab-109">Общие сведения о разработке компонентов потока данных см. в разделе [Разработка пользовательского компонента потока данных](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="ca4ab-109">For a general overview of data flow component development, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>

## <a name="design-time"></a><span data-ttu-id="ca4ab-110">Время разработки</span><span class="sxs-lookup"><span data-stu-id="ca4ab-110">Design Time</span></span>
 <span data-ttu-id="ca4ab-111">Реализация функциональных возможностей времени разработки для компонента источника включает указание соединения с внешним источником данных, добавление и настройку выходных столбцов, которые отражают источник данных, а также проверку готовности компонента к выполнению.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-111">Implementing the design-time functionality of a source component involves specifying a connection to an external data source, adding and configuring output columns that reflect the data source, and validating that the component is ready to execute.</span></span> <span data-ttu-id="ca4ab-112">По определению, компонент источника не имеет входов и один или несколько асинхронных выходов.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-112">By definition, a source component has zero inputs and one or more asynchronous outputs.</span></span>

### <a name="creating-the-component"></a><span data-ttu-id="ca4ab-113">Создание компонента</span><span class="sxs-lookup"><span data-stu-id="ca4ab-113">Creating the Component</span></span>
 <span data-ttu-id="ca4ab-114">Компоненты источника подключаются к внешним источникам данных с помощью объектов <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>, определенных в пакете.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-114">Source components connect to external data sources by using <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects defined in a package.</span></span> <span data-ttu-id="ca4ab-115">Они указывают свои требования для диспетчера соединений, добавляя элемент к коллекции <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A> свойства <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A>.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-115">They indicate their requirement for a connection manager by adding an element to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A> collection of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A> property.</span></span> <span data-ttu-id="ca4ab-116">Эта коллекция предназначена для двух целей: хранение ссылок на диспетчеры подключений в пакете, используемом компонентом, и объявление необходимости диспетчера подключений для конструктора.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-116">This collection serves two purposes-to hold references to connection managers in the package used by the component, and to advertise the need for a connection manager to the designer.</span></span> <span data-ttu-id="ca4ab-117">При добавлении объекта <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> к коллекции в окне **Расширенный редактор** отображается вкладка **Свойства соединения**, которая позволяет пользователям выбрать или создать соединение в пакете.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-117">When an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> has been added to the collection, the **Advanced Editor** displays the **Connection Properties** tab, which lets users select or create a connection in the package.</span></span>

 <span data-ttu-id="ca4ab-118">В следующем примере кода показана реализация метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>, который добавляет выход, а также добавляет объект <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> к коллекции <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-118">The following code example shows an implementation of <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> that adds an output, and adds a <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> object to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>.</span></span>

```csharp
using System;
using System.Collections;
using System.Data;
using System.Data.SqlClient;
using System.Data.OleDb;
using Microsoft.SqlServer.Dts.Runtime;
using Microsoft.SqlServer.Dts.Runtime.Wrapper;
using Microsoft.SqlServer.Dts.Pipeline;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;

namespace Microsoft.Samples.SqlServer.Dts
{
    [DtsPipelineComponent(DisplayName = "MySourceComponent",ComponentType = ComponentType.SourceAdapter)]
    public class MyComponent : PipelineComponent
    {
        public override void ProvideComponentProperties()
        {
            // Reset the component.
            base.RemoveAllInputsOutputsAndCustomProperties();
            ComponentMetaData.RuntimeConnectionCollection.RemoveAll();

            IDTSOutput100 output = ComponentMetaData.OutputCollection.New();
            output.Name = "Output";

            IDTSRuntimeConnection100 connection = ComponentMetaData.RuntimeConnectionCollection.New();
            connection.Name = "ADO.NET";
        }
```

```vb
Imports System.Data
Imports System.Data.SqlClient
Imports Microsoft.SqlServer.Dts.Runtime
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper
Imports Microsoft.SqlServer.Dts.Pipeline
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper

<DtsPipelineComponent(DisplayName:="MySourceComponent", ComponentType:=ComponentType.SourceAdapter)> _
Public Class MySourceComponent
    Inherits PipelineComponent

    Public Overrides Sub ProvideComponentProperties()

        ' Allow for resetting the component.
        RemoveAllInputsOutputsAndCustomProperties()
        ComponentMetaData.RuntimeConnectionCollection.RemoveAll()

        Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection.New()
        output.Name = "Output"

        Dim connection As IDTSRuntimeConnection100 = ComponentMetaData.RuntimeConnectionCollection.New()
        connection.Name = "ADO.NET"

    End Sub
End Class
```

### <a name="connecting-to-an-external-data-source"></a><span data-ttu-id="ca4ab-119">Соединение с внешним источником данных</span><span class="sxs-lookup"><span data-stu-id="ca4ab-119">Connecting to an External Data Source</span></span>
 <span data-ttu-id="ca4ab-120">После добавления соединения к коллекции <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A> необходимо переопределить метод <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>, чтобы установить соединение с внешним источником данных.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-120">After a connection has been added to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>, you override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> method to establish a connection to the external data source.</span></span> <span data-ttu-id="ca4ab-121">Этот метод вызывается и во время проектирования, и во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-121">This method is called during both design and execution time.</span></span> <span data-ttu-id="ca4ab-122">Компонент должен установить соединение с диспетчером соединений, указанным с помощью соединения времени выполнения, а впоследствии — с внешним источником данных.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-122">The component should establish a connection to the connection manager specified by the run-time connection, and subsequently, to the external data source.</span></span>

 <span data-ttu-id="ca4ab-123">Установленное соединение необходимо кэшировать в компоненте и затем освободить после вызова метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-123">After the connection is established, it should be cached internally by the component and released when the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> method is called.</span></span> <span data-ttu-id="ca4ab-124">Метод <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> вызывается и во время проектирования, и во время выполнения, как и метод <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-124">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> method is called at design and execution time, like the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> method.</span></span> <span data-ttu-id="ca4ab-125">Разработчики переопределяют этот метод и освобождают соединение, установленное компонентом во время вызова метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-125">Developers override this method, and release the connection established by the component during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>.</span></span>

 <span data-ttu-id="ca4ab-126">В следующем примере кода показан компонент, который подключается к соединению ADO.NET в методе <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> и закрывает соединение в методе <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-126">The following code example shows a component that connects to an ADO.NET connection in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> method and closes the connection in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> method.</span></span>

```csharp
private SqlConnection sqlConnection;

public override void AcquireConnections(object transaction)
{
    if (ComponentMetaData.RuntimeConnectionCollection[0].ConnectionManager != null)
    {
        ConnectionManager cm = Microsoft.SqlServer.Dts.Runtime.DtsConvert.GetWrapper(ComponentMetaData.RuntimeConnectionCollection[0].ConnectionManager);
        ConnectionManagerAdoNet cmado = cm.InnerObject as ConnectionManagerAdoNet;

        if (cmado == null)
            throw new Exception("The ConnectionManager " + cm.Name + " is not an ADO.NET connection.");

        sqlConnection = cmado.AcquireConnection(transaction) as SqlConnection;
        sqlConnection.Open();
    }
}

public override void ReleaseConnections()
{
    if (sqlConnection != null && sqlConnection.State != ConnectionState.Closed)
        sqlConnection.Close();
}
```

```vb
Private sqlConnection As SqlConnection

Public Overrides Sub AcquireConnections(ByVal transaction As Object)

    If Not IsNothing(ComponentMetaData.RuntimeConnectionCollection(0).ConnectionManager) Then

        Dim cm As ConnectionManager = Microsoft.SqlServer.Dts.Runtime.DtsConvert.GetWrapper(ComponentMetaData.RuntimeConnectionCollection(0).ConnectionManager)
        Dim cmado As ConnectionManagerAdoNet = CType(cm.InnerObject, ConnectionManagerAdoNet)

        If IsNothing(cmado) Then
            Throw New Exception("The ConnectionManager " + cm.Name + " is not an ADO.NET connection.")
        End If

        sqlConnection = CType(cmado.AcquireConnection(transaction), SqlConnection)
        sqlConnection.Open()

    End If
End Sub

Public Overrides Sub ReleaseConnections()

    If Not IsNothing(sqlConnection) And sqlConnection.State <> ConnectionState.Closed Then
        sqlConnection.Close()
    End If

End Sub
```

### <a name="creating-and-configuring-output-columns"></a><span data-ttu-id="ca4ab-127">Создание и настройка выходных столбцов</span><span class="sxs-lookup"><span data-stu-id="ca4ab-127">Creating and Configuring Output Columns</span></span>
 <span data-ttu-id="ca4ab-128">Выходные столбцы компонента источника отражают столбцы из внешнего источника данных, который добавляется компонентом к потоку данных во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-128">The output columns of a source component reflect the columns from the external data source that the component adds to the data flow during execution.</span></span> <span data-ttu-id="ca4ab-129">Во время разработки выходные столбцы добавляются после настройки компонента для подключения к внешнему источнику данных.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-129">At design time, you add output columns after the component has been configured to connect to an external data source.</span></span> <span data-ttu-id="ca4ab-130">Метод времени разработки, используемый компонентом для добавления столбцов к своей выходной коллекции, может изменяться в зависимости от потребностей компонента, хотя эти столбцы не должны добавляться во время выполнения методов <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> или <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-130">The design-time method that a component uses to add the columns to its output collection can vary based on the needs of the component, although they should not be added during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> or <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>.</span></span> <span data-ttu-id="ca4ab-131">Например, компонент, содержащий инструкцию SQL в пользовательском свойстве, которое управляет набором данных для компонента, может добавлять свои выходные столбцы во время выполнения метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.SetComponentProperty%2A>.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-131">For example, a component that contains a SQL statement in a custom property that controls the data set for the component may add its output columns during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.SetComponentProperty%2A> method.</span></span> <span data-ttu-id="ca4ab-132">Компонент проверяет, хранится ли в нем кэшированное соединение, и если оно имеется, подключается к источнику данных и создает выходные столбцы.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-132">The component checks to see whether it has a cached connection, and, if it does, connects to the data source and generates its output columns.</span></span>

 <span data-ttu-id="ca4ab-133">После создания выходного столбца компонент задает для него свойства типа данных, вызывая метод <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.SetDataTypeProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-133">After an output column has been created, set its data type properties by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.SetDataTypeProperties%2A> method.</span></span> <span data-ttu-id="ca4ab-134">Этот метод необходим, поскольку свойства <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Length%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Precision%2A> и <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.CodePage%2A> допускают только чтение, причем параметры каждого свойства зависят от параметров другого.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-134">This method is necessary because the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Length%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Precision%2A>, and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.CodePage%2A> properties are read-only and each property is dependent on the settings of the other.</span></span> <span data-ttu-id="ca4ab-135">Применение данного метода подчеркивает необходимость задавать эти значения единообразно, а задача потока данных проверяет, заданы ли значения правильно.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-135">This method enforces the need for these values to be set consistently, and the data flow task validates that they are set correctly.</span></span>

 <span data-ttu-id="ca4ab-136">Свойство <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A> столбца определяет значения, задаваемые для других свойств.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-136">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A> of the column determines the values that are set for the other properties.</span></span> <span data-ttu-id="ca4ab-137">В следующей таблице показаны требования к зависимым свойствам для каждого значения <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-137">The following table shows the requirements on the dependent properties for each <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>.</span></span> <span data-ttu-id="ca4ab-138">Для не указанных здесь типов данных зависимые свойства имеют нулевые значения.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-138">The data types not listed have their dependent properties set to zero.</span></span>

|<span data-ttu-id="ca4ab-139">DataType</span><span class="sxs-lookup"><span data-stu-id="ca4ab-139">DataType</span></span>|<span data-ttu-id="ca4ab-140">Длина</span><span class="sxs-lookup"><span data-stu-id="ca4ab-140">Length</span></span>|<span data-ttu-id="ca4ab-141">Масштабирование</span><span class="sxs-lookup"><span data-stu-id="ca4ab-141">Scale</span></span>|<span data-ttu-id="ca4ab-142">Точность</span><span class="sxs-lookup"><span data-stu-id="ca4ab-142">Precision</span></span>|<span data-ttu-id="ca4ab-143">CodePage</span><span class="sxs-lookup"><span data-stu-id="ca4ab-143">CodePage</span></span>|
|--------------|------------|-----------|---------------|--------------|
|<span data-ttu-id="ca4ab-144">DT_DECIMAL</span><span class="sxs-lookup"><span data-stu-id="ca4ab-144">DT_DECIMAL</span></span>|<span data-ttu-id="ca4ab-145">0</span><span class="sxs-lookup"><span data-stu-id="ca4ab-145">0</span></span>|<span data-ttu-id="ca4ab-146">Больше 0 и меньше или равно 28.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-146">Greater than 0 and less than or equal to 28.</span></span>|<span data-ttu-id="ca4ab-147">0</span><span class="sxs-lookup"><span data-stu-id="ca4ab-147">0</span></span>|<span data-ttu-id="ca4ab-148">0</span><span class="sxs-lookup"><span data-stu-id="ca4ab-148">0</span></span>|
|<span data-ttu-id="ca4ab-149">DT_CY</span><span class="sxs-lookup"><span data-stu-id="ca4ab-149">DT_CY</span></span>|<span data-ttu-id="ca4ab-150">0</span><span class="sxs-lookup"><span data-stu-id="ca4ab-150">0</span></span>|<span data-ttu-id="ca4ab-151">0</span><span class="sxs-lookup"><span data-stu-id="ca4ab-151">0</span></span>|<span data-ttu-id="ca4ab-152">0</span><span class="sxs-lookup"><span data-stu-id="ca4ab-152">0</span></span>|<span data-ttu-id="ca4ab-153">0</span><span class="sxs-lookup"><span data-stu-id="ca4ab-153">0</span></span>|
|<span data-ttu-id="ca4ab-154">DT_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="ca4ab-154">DT_NUMERIC</span></span>|<span data-ttu-id="ca4ab-155">0</span><span class="sxs-lookup"><span data-stu-id="ca4ab-155">0</span></span>|<span data-ttu-id="ca4ab-156">Больше 0, меньше или равно 28 и меньше, чем точность.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-156">Greater than 0 and less than or equal to 28, and less than Precision.</span></span>|<span data-ttu-id="ca4ab-157">Больше или равно 1 и меньше или равно 38.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-157">Greater than or equal to 1 and less than or equal to 38.</span></span>|<span data-ttu-id="ca4ab-158">0</span><span class="sxs-lookup"><span data-stu-id="ca4ab-158">0</span></span>|
|<span data-ttu-id="ca4ab-159">DT_BYTES</span><span class="sxs-lookup"><span data-stu-id="ca4ab-159">DT_BYTES</span></span>|<span data-ttu-id="ca4ab-160">Больше 0.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-160">Greater than 0.</span></span>|<span data-ttu-id="ca4ab-161">0</span><span class="sxs-lookup"><span data-stu-id="ca4ab-161">0</span></span>|<span data-ttu-id="ca4ab-162">0</span><span class="sxs-lookup"><span data-stu-id="ca4ab-162">0</span></span>|<span data-ttu-id="ca4ab-163">0</span><span class="sxs-lookup"><span data-stu-id="ca4ab-163">0</span></span>|
|<span data-ttu-id="ca4ab-164">DT_STR</span><span class="sxs-lookup"><span data-stu-id="ca4ab-164">DT_STR</span></span>|<span data-ttu-id="ca4ab-165">Больше 0 и меньше 8000.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-165">Greater than 0 and less than 8000.</span></span>|<span data-ttu-id="ca4ab-166">0</span><span class="sxs-lookup"><span data-stu-id="ca4ab-166">0</span></span>|<span data-ttu-id="ca4ab-167">0</span><span class="sxs-lookup"><span data-stu-id="ca4ab-167">0</span></span>|<span data-ttu-id="ca4ab-168">Не равно 0 и представляет допустимую кодовую страницу.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-168">Not 0, and a valid code page.</span></span>|
|<span data-ttu-id="ca4ab-169">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="ca4ab-169">DT_WSTR</span></span>|<span data-ttu-id="ca4ab-170">Больше 0 и меньше 4 000.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-170">Greater than 0 and less than 4000.</span></span>|<span data-ttu-id="ca4ab-171">0</span><span class="sxs-lookup"><span data-stu-id="ca4ab-171">0</span></span>|<span data-ttu-id="ca4ab-172">0</span><span class="sxs-lookup"><span data-stu-id="ca4ab-172">0</span></span>|<span data-ttu-id="ca4ab-173">0</span><span class="sxs-lookup"><span data-stu-id="ca4ab-173">0</span></span>|

 <span data-ttu-id="ca4ab-174">Поскольку ограничения свойств типа данных основаны на типе данных выходного столбца, во время работы с управляемыми типами необходимо выбрать правильный тип данных служб [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca4ab-174">Because the restrictions on the data type properties are based on the data type of the output column, you must choose the correct [!INCLUDE[ssIS](../../includes/ssis-md.md)] data type when you work with managed types.</span></span> <span data-ttu-id="ca4ab-175">В базовом классе предусмотрены три вспомогательных метода: <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ConvertBufferDataTypeToFitManaged%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferTypeToDataRecordType%2A> и <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.DataRecordTypeToBufferType%2A>, позволяющие разработчикам управляемых компонентов выбрать тип данных служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] с учетом управляемого типа.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-175">The base class provides three helper methods, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ConvertBufferDataTypeToFitManaged%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferTypeToDataRecordType%2A>, and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.DataRecordTypeToBufferType%2A>, to assist managed component developers in selecting an [!INCLUDE[ssIS](../../includes/ssis-md.md)] data type given a managed type.</span></span> <span data-ttu-id="ca4ab-176">Эти методы преобразуют управляемые типы данных в типы данных служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] и обратно.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-176">These methods convert managed data types to [!INCLUDE[ssIS](../../includes/ssis-md.md)] data types, and vice versa.</span></span>

 <span data-ttu-id="ca4ab-177">В следующем примере кода показано, как происходит заполнение коллекции выходных столбцов компонента на основе схемы таблицы.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-177">The following code example shows how the output column collection of a component is populated based on the schema of a table.</span></span> <span data-ttu-id="ca4ab-178">Вспомогательные методы базового класса используются для задания типа данных столбца, а зависимые свойства задаются с учетом типа данных.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-178">The helper methods of the base class are used to set the data type of the column, and the dependent properties are set based on the data type.</span></span>

```csharp
SqlCommand sqlCommand;

private void CreateColumnsFromDataTable()
{
    // Get the output.
    IDTSOutput100 output = ComponentMetaData.OutputCollection[0];

    // Start clean, and remove the columns from both collections.
    output.OutputColumnCollection.RemoveAll();
    output.ExternalMetadataColumnCollection.RemoveAll();

    this.sqlCommand = sqlConnection.CreateCommand();
    this.sqlCommand.CommandType = CommandType.Text;
    this.sqlCommand.CommandText = (string)ComponentMetaData.CustomPropertyCollection["SqlStatement"].Value;
    SqlDataReader schemaReader = this.sqlCommand.ExecuteReader(CommandBehavior.SchemaOnly);
    DataTable dataTable = schemaReader.GetSchemaTable();

    // Walk the columns in the schema, 
    // and for each data column create an output column and an external metadata column.
    foreach (DataRow row in dataTable.Rows)
    {
        IDTSOutputColumn100 outColumn = output.OutputColumnCollection.New();
        IDTSExternalMetadataColumn100 exColumn = output.ExternalMetadataColumnCollection.New();

        // Set column data type properties.
        bool isLong = false;
        DataType dt = DataRecordTypeToBufferType((Type)row["DataType"]);
        dt = ConvertBufferDataTypeToFitManaged(dt, ref isLong);
        int length = 0;
        int precision = (short)row["NumericPrecision"];
        int scale = (short)row["NumericScale"];
        int codepage = dataTable.Locale.TextInfo.ANSICodePage;

        switch (dt)
        {
            // The length cannot be zero, and the code page property must contain a valid code page.
            case DataType.DT_STR:
            case DataType.DT_TEXT:
                length = precision;
                precision = 0;
                scale = 0;
                break;

            case DataType.DT_WSTR:
                length = precision;
                codepage = 0;
                scale = 0;
                precision = 0;
                break;

            case DataType.DT_BYTES:
                precision = 0;
                scale = 0;
                codepage = 0;
                break;

            case DataType.DT_NUMERIC:
                length = 0;
                codepage = 0;

                if (precision > 38)
                    precision = 38;

                if (scale > 6)
                    scale = 6;
                break;

            case DataType.DT_DECIMAL:
                length = 0;
                precision = 0;
                codepage = 0;
                break;

            default:
                length = 0;
                precision = 0;
                codepage = 0;
                scale = 0;
                break;

        }

        // Set the properties of the output column.
        outColumn.Name = (string)row["ColumnName"];
        outColumn.SetDataTypeProperties(dt, length, precision, scale, codepage);
    }
}
```

```vb
Private sqlCommand As SqlCommand

Private Sub CreateColumnsFromDataTable()

    ' Get the output.
    Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)

    ' Start clean, and remove the columns from both collections.
    output.OutputColumnCollection.RemoveAll()
    output.ExternalMetadataColumnCollection.RemoveAll()

    Me.sqlCommand = sqlConnection.CreateCommand()
    Me.sqlCommand.CommandType = CommandType.Text
    Me.sqlCommand.CommandText = CStr(ComponentMetaData.CustomPropertyCollection("SqlStatement").Value)

    Dim schemaReader As SqlDataReader = Me.sqlCommand.ExecuteReader(CommandBehavior.SchemaOnly)
    Dim dataTable As DataTable = schemaReader.GetSchemaTable()

    ' Walk the columns in the schema, 
    ' and for each data column create an output column and an external metadata column.
    For Each row As DataRow In dataTable.Rows

        Dim outColumn As IDTSOutputColumn100 = output.OutputColumnCollection.New()
        Dim exColumn As IDTSExternalMetadataColumn100 = output.ExternalMetadataColumnCollection.New()

        ' Set column data type properties.
        Dim isLong As Boolean = False
        Dim dt As DataType = DataRecordTypeToBufferType(CType(row("DataType"), Type))
        dt = ConvertBufferDataTypeToFitManaged(dt, isLong)
        Dim length As Integer = 0
        Dim precision As Integer = CType(row("NumericPrecision"), Short)
        Dim scale As Integer = CType(row("NumericScale"), Short)
        Dim codepage As Integer = dataTable.Locale.TextInfo.ANSICodePage

        Select Case dt

            ' The length cannot be zero, and the code page property must contain a valid code page.
            Case DataType.DT_STR
            Case DataType.DT_TEXT
                length = precision
                precision = 0
                scale = 0

            Case DataType.DT_WSTR
                length = precision
                codepage = 0
                scale = 0
                precision = 0

            Case DataType.DT_BYTES
                precision = 0
                scale = 0
                codepage = 0

            Case DataType.DT_NUMERIC
                length = 0
                codepage = 0

                If precision > 38 Then
                    precision = 38
                End If

                If scale > 6 Then
                    scale = 6
                End If

            Case DataType.DT_DECIMAL
                length = 0
                precision = 0
                codepage = 0

            Case Else
                length = 0
                precision = 0
                codepage = 0
                scale = 0
        End Select

        ' Set the properties of the output column.
        outColumn.Name = CStr(row("ColumnName"))
        outColumn.SetDataTypeProperties(dt, length, precision, scale, codepage)
    Next
End Sub
```

### <a name="validating-the-component"></a><span data-ttu-id="ca4ab-179">Проверка компонента</span><span class="sxs-lookup"><span data-stu-id="ca4ab-179">Validating the Component</span></span>
 <span data-ttu-id="ca4ab-180">Необходимо проверить компонент источника и убедиться, что столбцы, определенные в его коллекциях выходных столбцов, совпадают со столбцами во внешнем источнике данных.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-180">You should validate a source component and verify that the columns defined in its output column collections match the columns at the external data source.</span></span> <span data-ttu-id="ca4ab-181">Иногда сверка выходных столбцов с внешним источником данных может оказаться невозможной, например, если имеет место отсоединенное состояние или желательно обойтись без применения продолжительных операций обмена данными с сервером.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-181">Sometimes, verifying the output columns against the external data source can be impossible, such as in a disconnected state, or when it is preferable to avoid lengthy round trips to the server.</span></span> <span data-ttu-id="ca4ab-182">В этих ситуациях все равно может быть выполнена проверка столбцов в выходе с помощью коллекции <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.ExternalMetadataColumnCollection%2A> выходного объекта.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-182">In these situations, the columns in the output can still be validated by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.ExternalMetadataColumnCollection%2A> of the output object.</span></span> <span data-ttu-id="ca4ab-183">Дополнительные сведения см. в разделе [Проверка компонента потока данных](../extending-packages-custom-objects/data-flow/validating-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="ca4ab-183">For more information, see [Validating a Data Flow Component](../extending-packages-custom-objects/data-flow/validating-a-data-flow-component.md).</span></span>

 <span data-ttu-id="ca4ab-184">Эта коллекция существует и во входных, и в выходных объектах, и ее можно заполнить столбцами из внешнего источника данных.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-184">This collection exists on both input and output objects and you can populate it with the columns from the external data source.</span></span> <span data-ttu-id="ca4ab-185">Эту коллекцию можно использовать для проверки выходных столбцов, если конструктор служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] находится в режиме вне сети, компонент отсоединен или свойство <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ValidateExternalMetadata%2A> имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-185">You can use this collection to validate the output columns when [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer is offline, when the component is disconnected, or when the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ValidateExternalMetadata%2A> property is `false`.</span></span> <span data-ttu-id="ca4ab-186">Эту коллекцию необходимо вначале заполнить одновременно с созданием выходных столбцов.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-186">The collection should be first populated at the same time that the output columns are created.</span></span> <span data-ttu-id="ca4ab-187">Добавление столбцов внешних метаданных к коллекции происходит относительно просто, поскольку столбец внешних метаданных должен с самого начала совпадать с выходным столбцом.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-187">Adding external metadata columns to the collection is relatively easy because the external metadata column should initially match the output column.</span></span> <span data-ttu-id="ca4ab-188">Свойства типа данных столбца уже должны быть заданы правильно, поэтому эти свойства можно скопировать непосредственно в объект <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumn100>.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-188">The data type properties of the column should have already been set correctly, and the properties can be copied directly to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumn100> object.</span></span>

 <span data-ttu-id="ca4ab-189">В следующем образце кода добавляется столбец внешних метаданных, который основан на вновь созданном выходном столбце.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-189">The following sample code adds an external metadata column that is based on a newly created output column.</span></span> <span data-ttu-id="ca4ab-190">При этом подразумевается, что выходной столбец уже был создан.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-190">It assumes that the output column has already been created.</span></span>

```csharp
private void CreateExternalMetaDataColumn(IDTSOutput100 output, IDTSOutputColumn100 outputColumn)
{

    // Set the properties of the external metadata column.
    IDTSExternalMetadataColumn100 externalColumn = output.ExternalMetadataColumnCollection.New();
    externalColumn.Name = outputColumn.Name;
    externalColumn.Precision = outputColumn.Precision;
    externalColumn.Length = outputColumn.Length;
    externalColumn.DataType = outputColumn.DataType;
    externalColumn.Scale = outputColumn.Scale;

    // Map the external column to the output column.
    outputColumn.ExternalMetadataColumnID = externalColumn.ID;

}
```

```vb
Private Sub CreateExternalMetaDataColumn(ByVal output As IDTSOutput100, ByVal outputColumn As IDTSOutputColumn100)

        ' Set the properties of the external metadata column.
        Dim externalColumn As IDTSExternalMetadataColumn100 = output.ExternalMetadataColumnCollection.New()
        externalColumn.Name = outputColumn.Name
        externalColumn.Precision = outputColumn.Precision
        externalColumn.Length = outputColumn.Length
        externalColumn.DataType = outputColumn.DataType
        externalColumn.Scale = outputColumn.Scale

        ' Map the external column to the output column.
        outputColumn.ExternalMetadataColumnID = externalColumn.ID

    End Sub
```

## <a name="run-time"></a><span data-ttu-id="ca4ab-191">Время выполнения</span><span class="sxs-lookup"><span data-stu-id="ca4ab-191">Run Time</span></span>
 <span data-ttu-id="ca4ab-192">Во время выполнения компоненты добавляют строки в выходные буферы, созданные задачей потока данных и предоставленные компоненту в методе <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-192">During execution, components add rows to output buffers that are created by the data flow task and provided to the component in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span></span> <span data-ttu-id="ca4ab-193">Этот метод, вызываемый однократно для компонентов источника, получает выходной буфер для каждого объекта <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> компонента, который подключен к нижестоящему компоненту.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-193">Called once for source components, the method receives an output buffer for each <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> of the component that is connected to a downstream component.</span></span>

### <a name="locating-columns-in-the-buffer"></a><span data-ttu-id="ca4ab-194">Поиск столбцов в буфере</span><span class="sxs-lookup"><span data-stu-id="ca4ab-194">Locating Columns in the Buffer</span></span>
 <span data-ttu-id="ca4ab-195">Выходной буфер для компонента содержит столбцы, определенные компонентом, и все столбцы, добавленные к выходу нижестоящего компонента.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-195">The output buffer for a component contains the columns defined by the component and any columns added to the output of a downstream component.</span></span> <span data-ttu-id="ca4ab-196">Например, если компонент источника предоставляет три столбца на выходе, а в следующем компоненте добавляется четвертый выходной столбец, то выходной буфер, предназначенный для использования компонентом источника, содержит эти четыре столбца.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-196">For example, if a source component provides three columns in its output, and the next component adds a fourth output column, the output buffer provided for use by the source component contains these four columns.</span></span>

 <span data-ttu-id="ca4ab-197">Порядок столбцов в строке буфера не определяется индексом выходного столбца в коллекции выходных столбцов.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-197">The order of the columns in a buffer row is not defined by the index of the output column in the output column collection.</span></span> <span data-ttu-id="ca4ab-198">Выходной столбец можно точно найти в строке буфера только с помощью метода <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSBufferManagerClass.FindColumnByLineageID%2A> объекта <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-198">An output column can only be accurately located in a buffer row by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSBufferManagerClass.FindColumnByLineageID%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span></span> <span data-ttu-id="ca4ab-199">Этот метод находит столбец с указанным идентификатором журнала обращений и преобразований в указанном буфере, после чего возвращает его расположение в строке.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-199">This method locates the column with the specified lineage ID in the specified buffer, and returns its location in the row.</span></span> <span data-ttu-id="ca4ab-200">Индексы выходных столбцов обычно определяются в методе <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> и сохраняются для использования во время выполнения метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-200">The indexes of the output columns are typically located in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> method, and stored for use during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span></span>

 <span data-ttu-id="ca4ab-201">В следующем примере кода находится расположение выходных столбцов в выходном буфере во время вызова метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> и полученные данные сохраняются во внутренней структуре.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-201">The following code example finds the location of the output columns in the output buffer during a call to <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>, and stores them in an internal structure.</span></span> <span data-ttu-id="ca4ab-202">В структуре сохраняется также имя столбца, которое затем используется в примере кода, относящемся к методу <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>, в следующем подразделе этого раздела.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-202">The name of the column is also stored in the structure and is used in the code example for the  <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method in the next section of this topic.</span></span>

```csharp
ArrayList columnInformation;

private struct ColumnInfo
{
    public int BufferColumnIndex;
    public string ColumnName;
}

public override void PreExecute()
{
    this.columnInformation = new ArrayList();
    IDTSOutput100 output = ComponentMetaData.OutputCollection[0];

    foreach (IDTSOutputColumn100 col in output.OutputColumnCollection)
    {
        ColumnInfo ci = new ColumnInfo();
        ci.BufferColumnIndex = BufferManager.FindColumnByLineageID(output.Buffer, col.LineageID);
        ci.ColumnName = col.Name;
        columnInformation.Add(ci);
    }
}
```

```vb
Public Overrides Sub PreExecute()

    Me.columnInformation = New ArrayList()
    Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)

    For Each col As IDTSOutputColumn100 In output.OutputColumnCollection

        Dim ci As ColumnInfo = New ColumnInfo()
        ci.BufferColumnIndex = BufferManager.FindColumnByLineageID(output.Buffer, col.LineageID)
        ci.ColumnName = col.Name
        columnInformation.Add(ci)
    Next
End Sub
```

### <a name="processing-rows"></a><span data-ttu-id="ca4ab-203">Обработка строк</span><span class="sxs-lookup"><span data-stu-id="ca4ab-203">Processing Rows</span></span>
 <span data-ttu-id="ca4ab-204">Строки добавляются к выходному буферу путем вызова метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.AddRow%2A>, который создает новую строку буфера с пустыми значениями в ее столбцах.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-204">Rows are added to the output buffer by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.AddRow%2A> method, which creates a new buffer row with empty values in its columns.</span></span> <span data-ttu-id="ca4ab-205">Затем компонент присваивает значения отдельным столбцам.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-205">The component then assigns values to the individual columns.</span></span> <span data-ttu-id="ca4ab-206">Выходные буферы, предоставленные компоненту, создаются и наблюдаются задачей потока данных.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-206">The output buffers provided to a component are created and monitored by the data flow task.</span></span> <span data-ttu-id="ca4ab-207">По мере их заполнения строки буферы перемещаются в следующий компонент.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-207">As they become full, the rows in the buffer are moved to the next component.</span></span> <span data-ttu-id="ca4ab-208">Невозможно определить время отправки пакета строк в следующий компонент, поскольку перемещение строк задачей потока данных прозрачно для разработчика компонента, а свойство <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.RowCount%2A> для выходных буферов всегда равно нулю.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-208">There is no way to determine when a batch of rows has been sent to the next component because the movement of rows by the data flow task is transparent to the component developer, and the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.RowCount%2A> property is always zero on output buffers.</span></span> <span data-ttu-id="ca4ab-209">Компонент источника после завершения добавления строк в выходной буфер уведомляет задачу потока данных путем вызова метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A> буфера <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>, а оставшиеся в буфере строки передаются следующему компоненту.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-209">When a source component is finished adding rows to its output buffer, it notifies the data flow task by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>, and the remaining rows in the buffer are passed to the next component.</span></span>

 <span data-ttu-id="ca4ab-210">При считывании строк компонентом источника из внешнего источника данных может потребоваться обновить счетчики производительности «Rows read» (Количество считанных строк) или «BLOB bytes read» (Количество считанных байтов больших двоичных объектов) путем вызова метода <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.IncrementPipelinePerfCounter%2A>.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-210">While the source component reads rows from the external data source, you may want to update the "Rows read" or "BLOB bytes read" performance counters by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.IncrementPipelinePerfCounter%2A> method.</span></span> <span data-ttu-id="ca4ab-211">Дополнительные сведения см. в статье [Performance Counters](../performance/performance-counters.md).</span><span class="sxs-lookup"><span data-stu-id="ca4ab-211">For more information, see [Performance Counters](../performance/performance-counters.md).</span></span>

 <span data-ttu-id="ca4ab-212">В следующем примере кода показан компонент, который добавляет строки в выходной буфер в методе <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-212">The following code example shows a component that adds rows to an output buffer in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span></span> <span data-ttu-id="ca4ab-213">Индексы выходных столбцов в буфере были найдены с помощью метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> в предыдущем примере кода.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-213">The indexes of the output columns in the buffer were located using <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> in the previous code example.</span></span>

```csharp
public override void PrimeOutput(int outputs, int[] outputIDs, PipelineBuffer[] buffers)
{
    IDTSOutput100 output = ComponentMetaData.OutputCollection[0];
    PipelineBuffer buffer = buffers[0];

    SqlDataReader dataReader = sqlCommand.ExecuteReader();

    // Loop over the rows in the DataReader, 
    // and add them to the output buffer.
    while (dataReader.Read())
    {
        // Add a row to the output buffer.
        buffer.AddRow();

        for (int x = 0; x < columnInformation.Count; x++)
        {
            ColumnInfo ci = (ColumnInfo)columnInformation[x];
            int ordinal = dataReader.GetOrdinal(ci.ColumnName);

            if (dataReader.IsDBNull(ordinal))
                buffer.SetNull(ci.BufferColumnIndex);
            else
            {
                buffer[ci.BufferColumnIndex] = dataReader[ci.ColumnName];
            }
        }
    }
    buffer.SetEndOfRowset();
}
```

```vb
Public Overrides Sub PrimeOutput(ByVal outputs As Integer, ByVal outputIDs As Integer(), ByVal buffers As PipelineBuffer())

    Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)
    Dim buffer As PipelineBuffer = buffers(0)

    Dim dataReader As SqlDataReader = sqlCommand.ExecuteReader()

    ' Loop over the rows in the DataReader, 
    ' and add them to the output buffer.
    While (dataReader.Read())

        ' Add a row to the output buffer.
        buffer.AddRow()

        For x As Integer = 0 To columnInformation.Count

            Dim ci As ColumnInfo = CType(columnInformation(x), ColumnInfo)

            Dim ordinal As Integer = dataReader.GetOrdinal(ci.ColumnName)

            If (dataReader.IsDBNull(ordinal)) Then
                buffer.SetNull(ci.BufferColumnIndex)
            Else
                buffer(ci.BufferColumnIndex) = dataReader(ci.ColumnName)

            End If
        Next

    End While

    buffer.SetEndOfRowset()
End Sub
```

## <a name="sample"></a><span data-ttu-id="ca4ab-214">Образец</span><span class="sxs-lookup"><span data-stu-id="ca4ab-214">Sample</span></span>
 <span data-ttu-id="ca4ab-215">В следующем образце показан простой компонент источника, в котором используется диспетчер соединения файлов для загрузки двоичного содержимого из файлов в поток данных.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-215">The following sample shows a simple source component that uses a File connection manager to load the binary contents of files into the data flow.</span></span> <span data-ttu-id="ca4ab-216">В этом образце показаны не все методы и возможности, описанные в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-216">This sample does not demonstrate all the methods and functionality discussed in this topic.</span></span> <span data-ttu-id="ca4ab-217">Он демонстрирует важные методы, которые должны быть переопределены в каждом пользовательском компоненте источника, но не содержат код для проверки во время разработки.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-217">It demonstrates the important methods that every custom source component must override, but does not contain code for design-time validation.</span></span>

```csharp
using System;
using System.IO;
using Microsoft.SqlServer.Dts.Pipeline;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime.Wrapper;

namespace BlobSrc
{
  [DtsPipelineComponent(DisplayName = "BLOB Inserter Source", Description = "Inserts files into the data flow as BLOBs")]
  public class BlobSrc : PipelineComponent
  {
    IDTSConnectionManager100 m_ConnMgr;
    int m_FileNameColumnIndex = -1;
    int m_FileBlobColumnIndex = -1;

    public override void ProvideComponentProperties()
    {
      IDTSOutput100 output = ComponentMetaData.OutputCollection.New();
      output.Name = "BLOB File Inserter Output";

      IDTSOutputColumn100 column = output.OutputColumnCollection.New();
      column.Name = "FileName";
      column.SetDataTypeProperties(DataType.DT_WSTR, 256, 0, 0, 0);

      column = output.OutputColumnCollection.New();
      column.Name = "FileBLOB";
      column.SetDataTypeProperties(DataType.DT_IMAGE, 0, 0, 0, 0);

      IDTSRuntimeConnection100 conn = ComponentMetaData.RuntimeConnectionCollection.New();
      conn.Name = "FileConnection";
    }

    public override void AcquireConnections(object transaction)
    {
      IDTSRuntimeConnection100 conn = ComponentMetaData.RuntimeConnectionCollection[0];
      m_ConnMgr = conn.ConnectionManager;
    }

    public override void ReleaseConnections()
    {
      m_ConnMgr = null;
    }

    public override void PreExecute()
    {
      IDTSOutput100 output = ComponentMetaData.OutputCollection[0];

      m_FileNameColumnIndex = (int)BufferManager.FindColumnByLineageID(output.Buffer, output.OutputColumnCollection[0].LineageID);
      m_FileBlobColumnIndex = (int)BufferManager.FindColumnByLineageID(output.Buffer, output.OutputColumnCollection[1].LineageID);
    }

    public override void PrimeOutput(int outputs, int[] outputIDs, PipelineBuffer[] buffers)
    {
      string strFileName = (string)m_ConnMgr.AcquireConnection(null);

      while (strFileName != null)
      {
        buffers[0].AddRow();

        buffers[0].SetString(m_FileNameColumnIndex, strFileName);

        FileInfo fileInfo = new FileInfo(strFileName);
        byte[] fileData = new byte[fileInfo.Length];
        FileStream fs = new FileStream(strFileName, FileMode.Open, FileAccess.Read, FileShare.Read);
        fs.Read(fileData, 0, fileData.Length);

        buffers[0].AddBlobData(m_FileBlobColumnIndex, fileData);

        strFileName = (string)m_ConnMgr.AcquireConnection(null);
      }

      buffers[0].SetEndOfRowset();
    }
  }
}
```

```vb
Imports System 
Imports System.IO 
Imports Microsoft.SqlServer.Dts.Pipeline 
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper 
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper 
Namespace BlobSrc 

 <DtsPipelineComponent(DisplayName="BLOB Inserter Source", Description="Inserts files into the data flow as BLOBs")> _ 
 Public Class BlobSrc 
 Inherits PipelineComponent 
   Private m_ConnMgr As IDTSConnectionManager100 
   Private m_FileNameColumnIndex As Integer = -1 
   Private m_FileBlobColumnIndex As Integer = -1 

   Public  Overrides Sub ProvideComponentProperties() 
     Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection.New 
     output.Name = "BLOB File Inserter Output" 
     Dim column As IDTSOutputColumn100 = output.OutputColumnCollection.New 
     column.Name = "FileName" 
     column.SetDataTypeProperties(DataType.DT_WSTR, 256, 0, 0, 0) 
     column = output.OutputColumnCollection.New 
     column.Name = "FileBLOB" 
     column.SetDataTypeProperties(DataType.DT_IMAGE, 0, 0, 0, 0) 
     Dim conn As IDTSRuntimeConnection90 = ComponentMetaData.RuntimeConnectionCollection.New 
     conn.Name = "FileConnection" 
   End Sub 

   Public  Overrides Sub AcquireConnections(ByVal transaction As Object) 
     Dim conn As IDTSRuntimeConnection100 = ComponentMetaData.RuntimeConnectionCollection(0) 
     m_ConnMgr = conn.ConnectionManager 
   End Sub 

   Public  Overrides Sub ReleaseConnections() 
     m_ConnMgr = Nothing 
   End Sub 

   Public  Overrides Sub PreExecute() 
     Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0) 
     m_FileNameColumnIndex = CType(BufferManager.FindColumnByLineageID(output.Buffer, output.OutputColumnCollection(0).LineageID), Integer) 
     m_FileBlobColumnIndex = CType(BufferManager.FindColumnByLineageID(output.Buffer, output.OutputColumnCollection(1).LineageID), Integer) 
   End Sub 

   Public  Overrides Sub PrimeOutput(ByVal outputs As Integer, ByVal outputIDs As Integer(), ByVal buffers As PipelineBuffer()) 
     Dim strFileName As String = CType(m_ConnMgr.AcquireConnection(Nothing), String) 
     While Not (strFileName Is Nothing) 
       buffers(0).AddRow 
       buffers(0).SetString(m_FileNameColumnIndex, strFileName) 
       Dim fileInfo As FileInfo = New FileInfo(strFileName) 
       Dim fileData(fileInfo.Length) As Byte 
       Dim fs As FileStream = New FileStream(strFileName, FileMode.Open, FileAccess.Read, FileShare.Read) 
       fs.Read(fileData, 0, fileData.Length) 
       buffers(0).AddBlobData(m_FileBlobColumnIndex, fileData) 
       strFileName = CType(m_ConnMgr.AcquireConnection(Nothing), String) 
     End While 
     buffers(0).SetEndOfRowset 
   End Sub 
 End Class 
End Namespace
```

<span data-ttu-id="ca4ab-218">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="ca4ab-218">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="ca4ab-219">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="ca4ab-219">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="ca4ab-220">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="ca4ab-220">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="ca4ab-221">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="ca4ab-221">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="ca4ab-222">См. также:</span><span class="sxs-lookup"><span data-stu-id="ca4ab-222">See Also</span></span>
 <span data-ttu-id="ca4ab-223">[Разработка пользовательского компонента назначения](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md) [Создание источника с помощью компонента скрипта](../extending-packages-scripting-data-flow-script-component-types/creating-a-source-with-the-script-component.md)</span><span class="sxs-lookup"><span data-stu-id="ca4ab-223">[Developing a Custom Destination Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md) [Creating a Source with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-source-with-the-script-component.md)</span></span>


