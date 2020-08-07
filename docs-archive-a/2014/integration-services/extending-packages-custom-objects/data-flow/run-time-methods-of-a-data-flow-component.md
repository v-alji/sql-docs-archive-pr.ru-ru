---
title: Методы времени выполнения для компонента потока данных | Документы Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- run-time [Integration Services]
- data flow components [Integration Services], run-time methods
ms.assetid: fd9e4317-18dd-43af-bbdc-79db32183ac4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: df0afe4c29044541c5a57aa3a466283ab4fe4fef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734370"
---
# <a name="run-time-methods-of-a-data-flow-component"></a><span data-ttu-id="83bc7-102">Методы времени выполнения для компонента потока данных</span><span class="sxs-lookup"><span data-stu-id="83bc7-102">Run-time Methods of a Data Flow Component</span></span>
  <span data-ttu-id="83bc7-103">Во время выполнения задача потока данных проверяет последовательность компонентов, подготавливает план выполнения и управляет пулом рабочих потоков, выполняющих план работы.</span><span class="sxs-lookup"><span data-stu-id="83bc7-103">At run time, the data flow task examines the sequence of components, prepares an execution plan, and manages a pool of worker threads that execute the work plan.</span></span> <span data-ttu-id="83bc7-104">Задача загружает строки данных из источников, обрабатывает их с помощью преобразований, а затем сохраняет в соответствующие назначения.</span><span class="sxs-lookup"><span data-stu-id="83bc7-104">The task loads rows of data from sources, processes them through transformations, then saves them to destinations.</span></span>  
  
## <a name="sequence-of-method-execution"></a><span data-ttu-id="83bc7-105">Последовательность выполнения методов</span><span class="sxs-lookup"><span data-stu-id="83bc7-105">Sequence of Method Execution</span></span>  
 <span data-ttu-id="83bc7-106">Во время выполнения компонента потока данных вызывается поднабор методов в базовом классе <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent>.</span><span class="sxs-lookup"><span data-stu-id="83bc7-106">During the execution of a data flow component, a subset of the methods in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class is called.</span></span> <span data-ttu-id="83bc7-107">Всегда вызываются одни и те же методы в одной и той же последовательности, за исключением методов <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> и <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="83bc7-107">The methods, and the sequence in which they are called, are always the same, with the exception of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> methods.</span></span> <span data-ttu-id="83bc7-108">Эти два метода вызываются в зависимости от существования и конфигурации объектов <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100> и <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> компонента.</span><span class="sxs-lookup"><span data-stu-id="83bc7-108">These two methods are called based on the existence and configuration of a component's <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> objects.</span></span>  
  
 <span data-ttu-id="83bc7-109">Следующий список содержит методы в том порядке, в котором они вызываются во время выполнения компонента.</span><span class="sxs-lookup"><span data-stu-id="83bc7-109">The following list shows the methods in the order in which they are called during component execution.</span></span> <span data-ttu-id="83bc7-110">Обратите внимание на то, что если метод <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> вызывается, это всегда происходит перед вызовом метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="83bc7-110">Note that <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>, when called, is always called before <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrepareForExecute%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PostExecute%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Cleanup%2A>  
  
### <a name="primeoutput-method"></a><span data-ttu-id="83bc7-111">Метод PrimeOutput</span><span class="sxs-lookup"><span data-stu-id="83bc7-111">PrimeOutput Method</span></span>  
 <span data-ttu-id="83bc7-112">Метод <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.PrimeOutput%2A> вызывается, когда в компоненте имеется, по меньшей мере, один выход, присоединенный к нижестоящему компоненту через объект <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100>, а свойство <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> этого выхода имеет нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="83bc7-112">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.PrimeOutput%2A> method is called when a component has at least one output, attached to a downstream component through an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> object, and the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> property of the output is zero.</span></span> <span data-ttu-id="83bc7-113">Метод <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.PrimeOutput%2A> вызывается для исходных компонентов и для преобразований с асинхронными выходами.</span><span class="sxs-lookup"><span data-stu-id="83bc7-113">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.PrimeOutput%2A> method is called for source components and for transformations with asynchronous outputs.</span></span> <span data-ttu-id="83bc7-114">В отличие от метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>, описываемого ниже, метод <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> вызывается только один раз для каждого компонента, где он требуется.</span><span class="sxs-lookup"><span data-stu-id="83bc7-114">Unlike the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method described below, the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method is only called once for each component that requires it.</span></span>  
  
### <a name="processinput-method"></a><span data-ttu-id="83bc7-115">Метод ProcessInput</span><span class="sxs-lookup"><span data-stu-id="83bc7-115">ProcessInput Method</span></span>  
 <span data-ttu-id="83bc7-116">Метод <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.ProcessInput%2A> вызывается для компонентов, имеющих, по меньшей мере, один вход, присоединенный к вышестоящему компоненту посредством объекта <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100>.</span><span class="sxs-lookup"><span data-stu-id="83bc7-116">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.ProcessInput%2A> method is called for components that have at least one input attached to an upstream component by an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> object.</span></span> <span data-ttu-id="83bc7-117">Метод <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.ProcessInput%2A> вызывается для целевых компонентов и для преобразований с синхронными выходами.</span><span class="sxs-lookup"><span data-stu-id="83bc7-117">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.ProcessInput%2A> method is called for destination components and for transformations with synchronous outputs.</span></span> <span data-ttu-id="83bc7-118">Метод <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> вызывается повторно до тех пор, пока не будут обработаны все строки из вышестоящих компонентов.</span><span class="sxs-lookup"><span data-stu-id="83bc7-118"><xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> is called repeatedly until there are no more rows to process from upstream components.</span></span>  
  
## <a name="working-with-inputs-and-outputs"></a><span data-ttu-id="83bc7-119">Работа с входами и выходами</span><span class="sxs-lookup"><span data-stu-id="83bc7-119">Working with Inputs and Outputs</span></span>  
 <span data-ttu-id="83bc7-120">Во время выполнения компонентами потока данных выполняются следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="83bc7-120">At run time, data flow components perform the following tasks:</span></span>  
  
-   <span data-ttu-id="83bc7-121">Исходные компоненты добавляют строки.</span><span class="sxs-lookup"><span data-stu-id="83bc7-121">Source components add rows.</span></span>  
  
-   <span data-ttu-id="83bc7-122">Компоненты преобразования с синхронными выходами получают строки, передаваемые исходными компонентами.</span><span class="sxs-lookup"><span data-stu-id="83bc7-122">Transformation components with synchronous outputs receive rows provided by source components.</span></span>  
  
-   <span data-ttu-id="83bc7-123">Компоненты преобразования с асинхронными выходами получают строки и добавляют строки.</span><span class="sxs-lookup"><span data-stu-id="83bc7-123">Transformation components with asynchronous outputs receive rows and add rows.</span></span>  
  
-   <span data-ttu-id="83bc7-124">Целевые компоненты получают строки и затем передают их в назначение.</span><span class="sxs-lookup"><span data-stu-id="83bc7-124">Destination components receive rows and then load them into a destination.</span></span>  
  
 <span data-ttu-id="83bc7-125">Во время выполнения задача потока данных выделяет объекты <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>, которые содержат все столбцы, определенные в коллекциях выходных столбцов последовательности компонентов.</span><span class="sxs-lookup"><span data-stu-id="83bc7-125">During execution, the data flow task allocates <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> objects that contain all the columns defined in the output column collections of a sequence of components.</span></span> <span data-ttu-id="83bc7-126">Например, если каждый из четырех компонентов в последовательности потока данных добавляет один выходной столбец в его коллекцию выходных столбцов, буфер, предоставляемый каждому компоненту, содержит четыре столбца, по одному для каждого выходного столбца на компонент.</span><span class="sxs-lookup"><span data-stu-id="83bc7-126">For example, if each of four components in a data flow sequence adds one output column to its output column collection,the buffer that is provided to each component contains four columns, one for each output column per component.</span></span> <span data-ttu-id="83bc7-127">В силу этого компонент иногда получает буферы, содержащие столбцы, которые им не используются.</span><span class="sxs-lookup"><span data-stu-id="83bc7-127">Because of this behavior, a component sometimes receives buffers that contain columns it does not use.</span></span>  
  
 <span data-ttu-id="83bc7-128">Поскольку буферы, которые получает компонент, могут содержать не используемые им столбцы, необходимо найти столбцы, которые должны быть использованы в коллекциях входных и выходных столбцов компонента, в буфере, предоставляемом компоненту задачей потока данных.</span><span class="sxs-lookup"><span data-stu-id="83bc7-128">Since the buffers received by your component may contain columns that the component will not use, you must locate the columns that you want to use in your component's input and output column collections in the buffer provided to the component by the data flow task.</span></span> <span data-ttu-id="83bc7-129">Для этого используется метод <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> свойства <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span><span class="sxs-lookup"><span data-stu-id="83bc7-129">You do this by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> property.</span></span> <span data-ttu-id="83bc7-130">Для улучшения производительности эта задача обычно выполняется во время выполнения метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>, а не методов <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> или <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="83bc7-130">For performance reasons, this task is ordinarily performed during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> method, rather than in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> or <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span>  
  
 <span data-ttu-id="83bc7-131">Метод <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> вызывается перед методами <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> и <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> и является для компонента первой возможностью выполнить эту работу после получения компонентом доступа к <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span><span class="sxs-lookup"><span data-stu-id="83bc7-131"><xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> is called before the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> methods, and is the first opportunity for a component to perform this work after the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> becomes available to the component.</span></span> <span data-ttu-id="83bc7-132">Во время выполнения этого метода компоненту необходимо найти его столбцы в буферах и сохранить эти данные внутренне, чтобы столбцы можно было использовать в методах <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> или <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="83bc7-132">During this method, the component should locate its columns in the buffers and store this information internally so the columns can be used in either the  <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> or <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> methods.</span></span>  
  
 <span data-ttu-id="83bc7-133">В следующем примере кода показано, как компонент преобразования с синхронным выходом осуществляет поиск своих входных столбцов в буфере во время выполнения <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>.</span><span class="sxs-lookup"><span data-stu-id="83bc7-133">The following code example demonstrates how a transformation component with a synchronous output locates its input columns in the buffer during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>.</span></span>  
  
```csharp  
private int []bufferColumnIndex;  
public override void PreExecute()  
{  
    IDTSInput100 input = ComponentMetaData.InputCollection[0];  
    bufferColumnIndex = new int[input.InputColumnCollection.Count];  
  
    for( int x=0; x < input.InputColumnCollection.Count; x++)  
    {  
        IDTSInputColumn100 column = input.InputColumnCollection[x];  
        bufferColumnIndex[x] = BufferManager.FindColumnByLineageID( input.Buffer, column.LineageID);  
    }  
}  
```  
  
```vb  
Dim bufferColumnIndex As Integer()  
  
    Public Overrides Sub PreExecute()  
  
        Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)  
  
        ReDim bufferColumnIndex(input.InputColumnCollection.Count)  
  
        For x As Integer = 0 To input.InputColumnCollection.Count  
  
            Dim column As IDTSInputColumn100 = input.InputColumnCollection(x)  
            bufferColumnIndex(x) = BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID)  
  
        Next  
  
    End Sub  
```  
  
### <a name="adding-rows"></a><span data-ttu-id="83bc7-134">Добавление строк</span><span class="sxs-lookup"><span data-stu-id="83bc7-134">Adding Rows</span></span>  
 <span data-ttu-id="83bc7-135">Компоненты предоставляют строки нижестоящим компонентам путем добавления строк в объекты <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>.</span><span class="sxs-lookup"><span data-stu-id="83bc7-135">Components supply rows to downstream components by adding rows to <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> objects.</span></span> <span data-ttu-id="83bc7-136">Задача потока данных предоставляет массив выходных буферов, по одному для каждого объекта <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100>, соединенного с нижестоящим компонентом, в качестве параметра метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="83bc7-136">The data flow task provides an array of output buffers - one for each <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> object that is connected to a downstream component - as a parameter to the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method.</span></span> <span data-ttu-id="83bc7-137">Исходные компоненты и компоненты преобразования с асинхронными выходами добавляют строки в буферы и вызывают метод <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A> по окончании добавления строк.</span><span class="sxs-lookup"><span data-stu-id="83bc7-137">Source components and transformation components with asynchronous outputs add rows to the buffers and call the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A> method when they are finished adding rows.</span></span> <span data-ttu-id="83bc7-138">Задача потока данных управляет выходными буферами, предоставляемыми ею компонентам, и, по мере заполнения буфера, автоматически перемещает строки в буфере в следующий компонент.</span><span class="sxs-lookup"><span data-stu-id="83bc7-138">The data flow task manages the output buffers that it supplies to components and, as a buffer becomes full, automatically moves the rows in the buffer to the next component.</span></span> <span data-ttu-id="83bc7-139">Метод <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> вызывается один раз для каждого компонента, в отличие от метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>, вызываемого неоднократно.</span><span class="sxs-lookup"><span data-stu-id="83bc7-139">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method is called one time per component, unlike  the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method, which is called repeatedly.</span></span>  
  
 <span data-ttu-id="83bc7-140">В следующем примере кода показано, как компонент добавляет строки в свои выходные буферы во время выполнения метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>, а затем вызывает метод <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A>.</span><span class="sxs-lookup"><span data-stu-id="83bc7-140">The following code example demonstrates how a component adds rows to its output buffers during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method, then calls the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A> method.</span></span>  
  
```csharp  
public override void PrimeOutput( int outputs, int []outputIDs,PipelineBuffer []buffers)  
{  
    for( int x=0; x < outputs; x++ )  
    {  
        IDTSOutput100 output = ComponentMetaData.OutputCollection.GetObjectByID( outputIDs[x]);  
        PipelineBuffer buffer = buffers[x];  
  
        // TODO: Add rows to the output buffer.  
    }  
    foreach( PipelineBuffer buffer in buffers )  
    {  
        /// Notify the data flow task that no more rows are coming.  
        buffer.SetEndOfRowset();  
    }  
}  
```  
  
```vb  
public overrides sub PrimeOutput( outputs as Integer , outputIDs() as Integer ,buffers() as PipelineBuffer buffers)  
  
    For x As Integer = 0 To outputs.MaxValue  
  
        Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection.GetObjectByID(outputIDs(x))  
        Dim buffer As PipelineBuffer = buffers(x)  
  
        ' TODO: Add rows to the output buffer.  
  
    Next  
  
    For Each buffer As PipelineBuffer In buffers  
  
        ' Notify the data flow task that no more rows are coming.  
        buffer.SetEndOfRowset()  
  
    Next  
  
End Sub  
```  
  
 <span data-ttu-id="83bc7-141">Дополнительные сведения о разработке компонентов, добавляющих строки в выходные буферы, см. в разделах [Разработка пользовательского компонента источника](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md) и [Разработка пользовательского компонента преобразования с асинхронными выходами](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md).</span><span class="sxs-lookup"><span data-stu-id="83bc7-141">For more information about developing components that add rows to output buffers, see [Developing a Custom Source Component](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md) and [Developing a Custom Transformation Component with Asynchronous Outputs](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md).</span></span>  
  
### <a name="receiving-rows"></a><span data-ttu-id="83bc7-142">Получение строк</span><span class="sxs-lookup"><span data-stu-id="83bc7-142">Receiving Rows</span></span>  
 <span data-ttu-id="83bc7-143">Компоненты получают строки из вышестоящих компонентов в объектах <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>.</span><span class="sxs-lookup"><span data-stu-id="83bc7-143">Components receive rows from upstream components in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> objects.</span></span> <span data-ttu-id="83bc7-144">Задача потока данных передает объект <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>, который содержит строки, добавленные в поток данных вышестоящими компонентами, в качестве параметра метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="83bc7-144">The data flow task provides a <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> object that contains the rows added to the data flow by upstream components as a parameter to the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method.</span></span> <span data-ttu-id="83bc7-145">Этот входной буфер можно использовать для проверки и изменения строк и столбцов в буфере, но непригоден для добавления или удаления строк.</span><span class="sxs-lookup"><span data-stu-id="83bc7-145">This input buffer can be used to examine and modify the rows and columns in the buffer, but cannot be used to add or remove rows.</span></span> <span data-ttu-id="83bc7-146">Метод <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> вызывается повторно до тех пор, пока не останется ни одного доступного буфера.</span><span class="sxs-lookup"><span data-stu-id="83bc7-146">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method is called repeatedly until there are no more available buffers.</span></span> <span data-ttu-id="83bc7-147">При последнем вызове свойство <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="83bc7-147">The last time it is called, the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> property is `true`.</span></span> <span data-ttu-id="83bc7-148">Можно просматривать коллекцию строк в буфере с помощью метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.NextRow%2A>, при этом буфер перемещается в следующую строку.</span><span class="sxs-lookup"><span data-stu-id="83bc7-148">You can iterate over the collection of rows in the buffer by using the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.NextRow%2A> method, which advances the buffer to the next row.</span></span> <span data-ttu-id="83bc7-149">Этот метод возвращает значение `false`, когда буфер располагается в последней строке коллекции.</span><span class="sxs-lookup"><span data-stu-id="83bc7-149">This method returns `false` when the buffer is on the last row in the collection.</span></span> <span data-ttu-id="83bc7-150">Нет необходимости проверять значение свойства <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A>, если не требуется выполнить дополнительное действие после обработки последних строк данных.</span><span class="sxs-lookup"><span data-stu-id="83bc7-150">You do not have to check the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> property unless you have to perform an additional action after the last rows of data have been processed.</span></span>  
  
 <span data-ttu-id="83bc7-151">Ниже показан правильный шаблон использования метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.NextRow%2A> и свойства <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A>.</span><span class="sxs-lookup"><span data-stu-id="83bc7-151">The following text shows the correct pattern for using the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.NextRow%2A> method and the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> property:</span></span>  
  
 `while (buffer.NextRow())`  
  
 `{`  
  
 `// Do something with each row.`  
  
 `}`  
  
 `if (buffer.EndOfRowset)`  
  
 `{`  
  
 `// Optionally, do something after all rows have been processed.`  
  
 `}`  
  
 <span data-ttu-id="83bc7-152">В следующем примере кода демонстрируется, как компонент обрабатывает строки во входных буферах во время выполнения метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="83bc7-152">The following code example demonstrates how a component processes the rows in input buffers during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method.</span></span>  
  
```csharp  
public override void ProcessInput( int inputID, PipelineBuffer buffer )  
{  
    {  
        IDTSInput100 input = ComponentMetaData.InputCollection.GetObjectByID(inputID);  
        while( buffer.NextRow())  
        {  
            // TODO: Examine the columns in the current row.  
        }  
}  
```  
  
```vb  
Public Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer)  
  
        Dim input As IDTSInput100 = ComponentMetaData.InputCollection.GetObjectByID(inputID)  
        While buffer.NextRow() = True  
  
            ' TODO: Examine the columns in the current row.  
        End While  
  
End Sub  
```  
  
 <span data-ttu-id="83bc7-153">Дополнительные сведения о разработке компонентов, получающих строки из входных буферов, см. в разделах [Разработка пользовательского компонента назначения](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md) и [Разработка пользовательского компонента преобразования с синхронными выходами](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md).</span><span class="sxs-lookup"><span data-stu-id="83bc7-153">For more information about developing components that receive rows in input buffers, see [Developing a Custom Destination Component](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md) and [Developing a Custom Transformation Component with Synchronous Outputs](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md).</span></span>  
  
<span data-ttu-id="83bc7-154">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="83bc7-154">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="83bc7-155">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="83bc7-155">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="83bc7-156">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="83bc7-156">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="83bc7-157">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="83bc7-157">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83bc7-158">См. также:</span><span class="sxs-lookup"><span data-stu-id="83bc7-158">See Also</span></span>  
 [<span data-ttu-id="83bc7-159">Методы времени разработки для компонента потока данных</span><span class="sxs-lookup"><span data-stu-id="83bc7-159">Design-time Methods of a Data Flow Component</span></span>](design-time-methods-of-a-data-flow-component.md)  
  
  
