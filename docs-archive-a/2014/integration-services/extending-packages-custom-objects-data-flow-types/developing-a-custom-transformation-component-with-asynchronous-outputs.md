---
title: Разработка пользовательского компонента преобразования с асинхронными выходами | Документы Майкрософт
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
- custom data flow components [Integration Services], transformation components
- asynchronous outputs [Integration Services]
- ProcessInput method
- cache [Integration Services]
- buffer allocations [Integration Services]
- transformation components [Integration Services]
- output columns [Integration Services]
- PrimeOutput method
- data flow components [Integration Services], transformation components
ms.assetid: 1c3e92c7-a4fa-4fdd-b9ca-ac3069536274
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 41e2ecdf9f90765e75ff2b8c9c0681a25366e080
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736611"
---
# <a name="developing-a-custom-transformation-component-with-asynchronous-outputs"></a><span data-ttu-id="2a38b-102">Разработка пользовательского компонента преобразования с асинхронными выходами</span><span class="sxs-lookup"><span data-stu-id="2a38b-102">Developing a Custom Transformation Component with Asynchronous Outputs</span></span>
  <span data-ttu-id="2a38b-103">Если преобразование не может вывести строки до того, как компонент получит все входные строки, или может создавать несколько выходных строк на одну входную, нужно использовать компонент с асинхронным выходом.</span><span class="sxs-lookup"><span data-stu-id="2a38b-103">You use a component with asynchronous outputs when a transform cannot output rows until the component has received all its input rows, or when the transformation does not produce exactly one output row for each row received as input.</span></span> <span data-ttu-id="2a38b-104">Например, преобразование «Статистическая обработка» не может вычислить суммарное значение для всех строк, пока не считает все строки.</span><span class="sxs-lookup"><span data-stu-id="2a38b-104">The Aggregate transformation, for example, cannot calculate a sum across rows until it has read all the rows.</span></span> <span data-ttu-id="2a38b-105">Напротив, компонент с синхронными выходами можно использовать в случае, если каждая строка преобразуется, проходя через этот компонент.</span><span class="sxs-lookup"><span data-stu-id="2a38b-105">In contrast, you can use a component with synchronous outputs any time when you modify each row of data as it passes through.</span></span> <span data-ttu-id="2a38b-106">Можно изменять данные каждой строки на месте или добавлять к строке один или несколько новых столбцов, каждый из которых содержит значение для каждого входного ряда.</span><span class="sxs-lookup"><span data-stu-id="2a38b-106">You can modify the data for each row in place, or you can create one or more new columns, each of which has a value for every one of the input rows.</span></span> <span data-ttu-id="2a38b-107">Дополнительные сведения о различиях между синхронными и асинхронными компонентами см. в разделе [Основные сведения о синхронных и асинхронных преобразованиях](../understanding-synchronous-and-asynchronous-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="2a38b-107">For more information about the difference between synchronous and asynchronous components, see [Understanding Synchronous and Asynchronous Transformations](../understanding-synchronous-and-asynchronous-transformations.md).</span></span>

 <span data-ttu-id="2a38b-108">Компоненты преобразования с асинхронными выходами уникальны, поскольку выступают одновременно в роли компонента-источника и целевого компонента.</span><span class="sxs-lookup"><span data-stu-id="2a38b-108">Transformation components with asynchronous outputs are unique because they act as both destination and source components.</span></span> <span data-ttu-id="2a38b-109">Такой компонент получает строки от вышестоящих компонентов и добавляет строки, получаемые нижестоящими компонентами.</span><span class="sxs-lookup"><span data-stu-id="2a38b-109">This kind of component receives rows from upstream components, and adds rows that are consumed by downstream components.</span></span> <span data-ttu-id="2a38b-110">Никакой другой компонент потока данных не выполняет обе операции сразу.</span><span class="sxs-lookup"><span data-stu-id="2a38b-110">No other data flow component performs both of these operations.</span></span>

 <span data-ttu-id="2a38b-111">Столбцы, полученные от вышестоящих компонентов и доступные компоненту с синхронными выходами, автоматически становятся доступны компонентам, нижестоящим по отношению к данному компоненту.</span><span class="sxs-lookup"><span data-stu-id="2a38b-111">The columns from upstream components that are available to a component with synchronous outputs are automatically available to components downstream from the component.</span></span> <span data-ttu-id="2a38b-112">Поэтому компоненту с синхронными выходами не нужно определять выходные столбцы, чтобы обеспечить следующему компоненту столбцы и строки.</span><span class="sxs-lookup"><span data-stu-id="2a38b-112">Therefore, a component with synchronous outputs does not have to define any output columns to provide columns and rows to the next component.</span></span> <span data-ttu-id="2a38b-113">С другой стороны, компоненту с асинхронными выходами нужно определять выходные столбцы и предоставлять строки нижестоящим компонентам.</span><span class="sxs-lookup"><span data-stu-id="2a38b-113">Components with asynchronous outputs, on the other hand, must define output columns and provide rows to downstream components.</span></span> <span data-ttu-id="2a38b-114">Следовательно, компоненту с асинхронными выходами приходится выполнять больше задач, как во время разработки, так и во время выполнения, а разработчику этого компонента приходится писать больше кода.</span><span class="sxs-lookup"><span data-stu-id="2a38b-114">Therefore a component with asynchronous outputs has more tasks to perform during both design and execution time, and the component developer has more code to implement.</span></span>

 <span data-ttu-id="2a38b-115">Службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] содержат несколько преобразований с асинхронными выходами.</span><span class="sxs-lookup"><span data-stu-id="2a38b-115">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] contains several transformations with asynchronous outputs.</span></span> <span data-ttu-id="2a38b-116">Например, преобразование «Сортировка» требует получения всех строк до того, как их можно будет сортировать, и использует для этого асинхронные выходы.</span><span class="sxs-lookup"><span data-stu-id="2a38b-116">For example, the Sort transformation requires all its rows before it can sort them, and achieves this by using asynchronous outputs.</span></span> <span data-ttu-id="2a38b-117">После получения всех строк преобразование сортирует их и добавляет к выходу.</span><span class="sxs-lookup"><span data-stu-id="2a38b-117">After it has received all its rows, it sorts them and adds them to its output.</span></span>

 <span data-ttu-id="2a38b-118">В данном разделе приводится подробное описание разработок преобразований с асинхронными выходами.</span><span class="sxs-lookup"><span data-stu-id="2a38b-118">This section explains in detail how to develop transformations with asynchronous outputs.</span></span> <span data-ttu-id="2a38b-119">Дополнительные сведения о разработке компонентов-источников см. в разделе [Разработка пользовательского компонента источника](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md).</span><span class="sxs-lookup"><span data-stu-id="2a38b-119">For more information about source component development, see [Developing a Custom Source Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md).</span></span>

## <a name="design-time"></a><span data-ttu-id="2a38b-120">Время разработки</span><span class="sxs-lookup"><span data-stu-id="2a38b-120">Design Time</span></span>

### <a name="creating-the-component"></a><span data-ttu-id="2a38b-121">Создание компонента</span><span class="sxs-lookup"><span data-stu-id="2a38b-121">Creating the Component</span></span>
 <span data-ttu-id="2a38b-122">Свойство <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> объекта <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> определяет, является ли его выход синхронным или асинхронным.</span><span class="sxs-lookup"><span data-stu-id="2a38b-122">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> property on the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> object identifies whether an output is synchronous or asynchronous.</span></span> <span data-ttu-id="2a38b-123">Для создания асинхронного выхода добавьте выход к компоненту и задайте для свойства <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> значение 0.</span><span class="sxs-lookup"><span data-stu-id="2a38b-123">To create an asynchronous output, add the output to the component and set the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> to zero.</span></span> <span data-ttu-id="2a38b-124">Значение этого свойства определяет также, выделяет ли задача потока данных объекты <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> для входа и выхода данного компонента или же выделяется один буфер, используемый обоими объектами сразу.</span><span class="sxs-lookup"><span data-stu-id="2a38b-124">Setting this property also determines whether the data flow task allocates <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> objects for both the input and output of the component, or whether a single buffer is allocated and shared between the two objects.</span></span>

 <span data-ttu-id="2a38b-125">Далее приводится образец кода, создающий асинхронный выход в реализации метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="2a38b-125">The following sample code shows a component that creates an asynchronous output in its <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> implementation.</span></span>

```csharp
using Microsoft.SqlServer.Dts.Pipeline;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.Samples.SqlServer.Dts
{
    [DtsPipelineComponent(DisplayName = "AsyncComponent",ComponentType = ComponentType.Transform)]
    public class AsyncComponent : PipelineComponent
    {
        public override void ProvideComponentProperties()
        {
            // Call the base class, which adds a synchronous input
            // and output.
            base.ProvideComponentProperties();

            // Make the output asynchronous.
            IDTSOutput100 output = ComponentMetaData.OutputCollection[0];
            output.SynchronousInputID = 0;
        }
    }
}
```

```vb
Imports Microsoft.SqlServer.Dts.Pipeline
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper
Imports Microsoft.SqlServer.Dts.Runtime

<DtsPipelineComponent(DisplayName:="AsyncComponent", ComponentType:=ComponentType.Transform)> _
Public Class AsyncComponent
    Inherits PipelineComponent

    Public Overrides Sub ProvideComponentProperties()

        ' Call the base class, which adds a synchronous input
        ' and output.
        Me.ProvideComponentProperties()

        ' Make the output asynchronous.
        Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)
        output.SynchronousInputID = 0

    End Sub

End Class
```

### <a name="creating-and-configuring-output-columns"></a><span data-ttu-id="2a38b-126">Создание и настройка выходных столбцов</span><span class="sxs-lookup"><span data-stu-id="2a38b-126">Creating and Configuring Output Columns</span></span>
 <span data-ttu-id="2a38b-127">Как уже упоминалось, асинхронный компонент добавляет столбцы к своей коллекции выходных столбцов, чтобы предоставить столбцы нижележащим компонентам.</span><span class="sxs-lookup"><span data-stu-id="2a38b-127">As mentioned earlier, an asynchronous component adds columns to its output column collection to provide columns to downstream components.</span></span> <span data-ttu-id="2a38b-128">Существует несколько методов времени разработки, которые можно использовать в зависимости от потребностей компонента.</span><span class="sxs-lookup"><span data-stu-id="2a38b-128">There are several design-time methods to choose from, depending on the needs of the component.</span></span> <span data-ttu-id="2a38b-129">Например, для передачи всех столбцов из вышестоящих компонентов нижестоящим нужно переопределить метод <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.OnInputPathAttached%2A> для добавления столбцов, поскольку это первый метод, в котором входные столбцы становятся доступны компоненту.</span><span class="sxs-lookup"><span data-stu-id="2a38b-129">For example, if you want to pass all the columns from the upstream components to the downstream components, you would override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.OnInputPathAttached%2A> method to add the columns, because this is the first method in which the input columns are available to the component.</span></span>

 <span data-ttu-id="2a38b-130">Если компонент создает выходные столбцы на основе столбцов, выбранных для входа, нужно переопределить метод <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.SetUsageType%2A>, чтобы он выбирал выходные столбцы и указывал, как они должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="2a38b-130">If the component creates output columns based on the columns selected for its input, override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.SetUsageType%2A> method to select the output columns and to indicate how they will be used.</span></span>

 <span data-ttu-id="2a38b-131">Если компонент с асинхронными выходами создает выходные столбцы на основе столбцов, полученных от вышестоящих компонентов, и все доступные вышестоящие столбцы изменяются, компоненту следует изменять свою собственную коллекцию выходных столбцов.</span><span class="sxs-lookup"><span data-stu-id="2a38b-131">If a component with asynchronous outputs creates output columns based on the columns from upstream components, and the available upstream columns change, the component should update its output column collection.</span></span> <span data-ttu-id="2a38b-132">Эти изменения должны обнаруживаться компонентом во время работы метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> и исправляться при вызове метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A>.</span><span class="sxs-lookup"><span data-stu-id="2a38b-132">These changes should be detected by the component during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A>, and fixed during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A>.</span></span>

> [!NOTE]
>  <span data-ttu-id="2a38b-133">Если выходной столбец удалить из коллекции выходных столбцов, это негативно повлияет на использующие его нижележащие компоненты потока данных.</span><span class="sxs-lookup"><span data-stu-id="2a38b-133">When an output column is removed from the output column collection, downstream components in the data flow that reference the column are adversely affected.</span></span> <span data-ttu-id="2a38b-134">Выходной столбец нужно исправить, а не удалять и не создавать заново, чтобы не нарушить работы нижестоящих компонентов.</span><span class="sxs-lookup"><span data-stu-id="2a38b-134">The output column must be repaired without removing and recreating the column to prevent breaking the downstream components.</span></span> <span data-ttu-id="2a38b-135">Например, если тип данных столбца изменился, нужно обновить тип данных.</span><span class="sxs-lookup"><span data-stu-id="2a38b-135">For example, if the data type of the column has changed, you must update the data type.</span></span>

 <span data-ttu-id="2a38b-136">В следующем примере кода показан компонент, добавляющий столбец в коллекцию выходных столбцов, по одному на каждый столбец, получаемый от вышестоящего компонента.</span><span class="sxs-lookup"><span data-stu-id="2a38b-136">The following code example shows a component that adds an output column to its output column collection for each column available from the upstream component.</span></span>

```csharp
public override void OnInputPathAttached(int inputID)
{
   IDTSInput100 input = ComponentMetaData.InputCollection.GetObjectByID(inputID);
   IDTSOutput100 output = ComponentMetaData.OutputCollection[0];
   IDTSVirtualInput100 vInput = input.GetVirtualInput();

   foreach (IDTSVirtualInputColumn100 vCol in vInput.VirtualInputColumnCollection)
   {
      IDTSOutputColumn100 outCol = output.OutputColumnCollection.New();
      outCol.Name = vCol.Name;
      outCol.SetDataTypeProperties(vCol.DataType, vCol.Length, vCol.Precision, vCol.Scale, vCol.CodePage);
   }
}
```

```vb
Public Overrides Sub OnInputPathAttached(ByVal inputID As Integer)

    Dim input As IDTSInput100 = ComponentMetaData.InputCollection.GetObjectByID(inputID)
    Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)
    Dim vInput As IDTSVirtualInput100 = input.GetVirtualInput()

    For Each vCol As IDTSVirtualInputColumn100 In vInput.VirtualInputColumnCollection

        Dim outCol As IDTSOutputColumn100 = output.OutputColumnCollection.New()
        outCol.Name = vCol.Name
        outCol.SetDataTypeProperties(vCol.DataType, vCol.Length, vCol.Precision, vCol.Scale, vCol.CodePage)

    Next
End Sub
```

## <a name="run-time"></a><span data-ttu-id="2a38b-137">Время выполнения</span><span class="sxs-lookup"><span data-stu-id="2a38b-137">Run Time</span></span>
 <span data-ttu-id="2a38b-138">Компоненты с асинхронным выходом также исполняют методы в последовательности, отличной от других типов компонентов, во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="2a38b-138">Components with asynchronous outputs also execute a different sequence of methods at run time than other types of components.</span></span> <span data-ttu-id="2a38b-139">Во-первых, это единственные компоненты, в которых вызываются оба метода: <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> и <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="2a38b-139">First, they are the only components that receive a call to both the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> and the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> methods.</span></span> <span data-ttu-id="2a38b-140">Компоненты с асинхронным выходом также требуют доступа ко всем входящим строкам, прежде чем смогут начать обработку; поэтому они должны сохранять входные строки в своем внутреннем кэше, пока все строки не будут прочитаны.</span><span class="sxs-lookup"><span data-stu-id="2a38b-140">Components with asynchronous outputs also require access to all the incoming rows before they can start processing; therefore, they must cache the input rows internally until all rows have been read.</span></span> <span data-ttu-id="2a38b-141">И наконец, в отличие от других компонентов, компоненты с асинхронным выходом получают и входной, и выходной буфер.</span><span class="sxs-lookup"><span data-stu-id="2a38b-141">Finally, unlike other components, components with asynchronous outputs receive both an input buffer and an output buffer.</span></span>

### <a name="understanding-the-buffers"></a><span data-ttu-id="2a38b-142">Основные сведения о буферах</span><span class="sxs-lookup"><span data-stu-id="2a38b-142">Understanding the Buffers</span></span>
 <span data-ttu-id="2a38b-143">Компонент получает входной буфер при вызове метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="2a38b-143">The input buffer is received by the component during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span> <span data-ttu-id="2a38b-144">Этот буфер содержит строки, добавленные туда вышестоящими компонентами.</span><span class="sxs-lookup"><span data-stu-id="2a38b-144">This buffer contains the rows added to the buffer by upstream components.</span></span> <span data-ttu-id="2a38b-145">Буфер также содержит столбцы входа компонента, помимо столбцов, предоставленных в качестве выхода вышестоящего компонента, но не добавленных к входной коллекции асинхронного компонента.</span><span class="sxs-lookup"><span data-stu-id="2a38b-145">The buffer also contains the columns of the component's input, in addition to the columns that were provided in the output of an upstream component but were not added to the asynchronous component's input collection.</span></span>

 <span data-ttu-id="2a38b-146">Выходной буфер, предоставленный компоненту в методе <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>, вначале не содержит строк.</span><span class="sxs-lookup"><span data-stu-id="2a38b-146">The output buffer, which is provided to the component in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>, does not initially contain rows.</span></span> <span data-ttu-id="2a38b-147">Компонент добавляет строки к этому буферу и, когда буфер заполнится, предоставляет его нижестоящим компонентам.</span><span class="sxs-lookup"><span data-stu-id="2a38b-147">The component adds rows to this buffer and provides the buffer to downstream components when it is full.</span></span> <span data-ttu-id="2a38b-148">Выходной буфер содержит столбцы, определенные в коллекции выходных столбцов компонента, помимо столбцов, добавленных к выводам других нижестоящих компонентов.</span><span class="sxs-lookup"><span data-stu-id="2a38b-148">The output buffer contains the columns defined in the component's output column collection, in addition to any columns that other downstream components have added to their outputs.</span></span>

 <span data-ttu-id="2a38b-149">Не так ведут себя компоненты с синхронными выходами — они получают единый буфер с общим доступом.</span><span class="sxs-lookup"><span data-stu-id="2a38b-149">This is different behavior from that of components with synchronous outputs, which receive a single shared buffer.</span></span> <span data-ttu-id="2a38b-150">Общий буфер компонента с синхронными выходами содержит и входные, и выходные столбцы компонента, помимо столбцов, добавленных к выходам вышестоящих и нижестоящих компонентов.</span><span class="sxs-lookup"><span data-stu-id="2a38b-150">The shared buffer of a component with synchronous outputs contains both the input and output columns of the component, in addition to columns added to the outputs of upstream and downstream components.</span></span>

### <a name="processing-rows"></a><span data-ttu-id="2a38b-151">Обработка строк</span><span class="sxs-lookup"><span data-stu-id="2a38b-151">Processing Rows</span></span>

#### <a name="caching-input-rows"></a><span data-ttu-id="2a38b-152">Кэширование входных строк</span><span class="sxs-lookup"><span data-stu-id="2a38b-152">Caching Input Rows</span></span>
 <span data-ttu-id="2a38b-153">При создании компонента с асинхронными выходами есть три способа добавления строк к выходному буферу.</span><span class="sxs-lookup"><span data-stu-id="2a38b-153">When you write a component with asynchronous outputs, you have three options for adding rows to the output buffer.</span></span> <span data-ttu-id="2a38b-154">Можно добавлять их по мере получения входных строк, кэшировать их, пока компонент не получил все строки от вышестоящего компонента, или добавлять их в какой-то другой момент, подходящий для данного конкретного компонента.</span><span class="sxs-lookup"><span data-stu-id="2a38b-154">You can add them as input rows are received, you can cache them until the component has received all the rows from the upstream component, or you can add them when it is appropriate to do so for the component.</span></span> <span data-ttu-id="2a38b-155">Выбор метода зависит от потребностей данного компонента.</span><span class="sxs-lookup"><span data-stu-id="2a38b-155">The method that you choose depends on the requirements of the component.</span></span> <span data-ttu-id="2a38b-156">Например, компонент сортировки не может провести сортировку, пока не получит все строки от вышестоящих компонентов.</span><span class="sxs-lookup"><span data-stu-id="2a38b-156">For example, the Sort component requires that all the upstream rows be received before they can be sorted.</span></span> <span data-ttu-id="2a38b-157">Поэтому он ждет, пока все строки будут прочитаны, прежде чем добавить их в выходной буфер.</span><span class="sxs-lookup"><span data-stu-id="2a38b-157">Therefore, it waits until all rows have been read before adding rows to the output buffer.</span></span>

 <span data-ttu-id="2a38b-158">Строки, полученные во входном буфере, должны сохраняться во внутреннем кэше компонента, пока тот не будет готов их обработать.</span><span class="sxs-lookup"><span data-stu-id="2a38b-158">The rows that are received in the input buffer must be cached internally by the component until it is ready to process them.</span></span> <span data-ttu-id="2a38b-159">Получаемые из буфера строки могут кэшироваться в таблице данных, многомерном массиве или иной внутренней структуре.</span><span class="sxs-lookup"><span data-stu-id="2a38b-159">The incoming buffer rows can be cached in a data table, a multidimensional array, or any other internal structure.</span></span>

#### <a name="adding-output-rows"></a><span data-ttu-id="2a38b-160">Добавление выходных строк</span><span class="sxs-lookup"><span data-stu-id="2a38b-160">Adding Output Rows</span></span>
 <span data-ttu-id="2a38b-161">Независимо от того, в какой момент строки добавляются к выходному буферу — по мере получения или после получения всех строк, — добавление производится вызовом метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.AddRow%2A> выходного буфера.</span><span class="sxs-lookup"><span data-stu-id="2a38b-161">Whether you add rows to the output buffer as they are received or after receiving all of the rows, you do so by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.AddRow%2A> method on the output buffer.</span></span> <span data-ttu-id="2a38b-162">Добавив строку, нужно задать значения всех столбцов новой строки.</span><span class="sxs-lookup"><span data-stu-id="2a38b-162">After you have added the row, you set the values of each column in the new row.</span></span>

 <span data-ttu-id="2a38b-163">Поскольку в выходном буфере иногда бывает больше столбцов, чем в коллекции выходных столбцов компонента, до присвоения значения очередному столбцу буфера нужно узнать индекс этого столбца.</span><span class="sxs-lookup"><span data-stu-id="2a38b-163">Because there are sometimes more columns in the output buffer than in the output column collection of the component, you must locate the index of the appropriate column in the buffer before you can set its value.</span></span> <span data-ttu-id="2a38b-164">Метод <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> свойства <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> возвращает индекс столбца буферной строки с соответствующим идентификатором журнала преобразований. Этот индекс затем используется для присвоения значения столбцу в буфере.</span><span class="sxs-lookup"><span data-stu-id="2a38b-164">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> property returns the index of the column in the buffer row with the specified lineage ID, which is then used to assign the value to the buffer column.</span></span>

 <span data-ttu-id="2a38b-165">Метод <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>, вызываемый до методов <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> и <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>, — первый метод, в котором доступно свойство <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>, и предоставляет первую возможность определить индексы столбцов во входном и выходном буферах.</span><span class="sxs-lookup"><span data-stu-id="2a38b-165">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> method, which is called before the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method or the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method, is the first method where the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> property is available, and the first opportunity to locate the indexes of the columns in the input and output buffers.</span></span>

## <a name="sample"></a><span data-ttu-id="2a38b-166">Образец</span><span class="sxs-lookup"><span data-stu-id="2a38b-166">Sample</span></span>
 <span data-ttu-id="2a38b-167">В следующем образце демонстрируется простой компонент преобразования с асинхронными выходами, добавляющий строки к выходному буферу по мере их получения.</span><span class="sxs-lookup"><span data-stu-id="2a38b-167">The following sample shows a simple transformation component with asynchronous outputs that adds rows to the output buffer as they are received.</span></span> <span data-ttu-id="2a38b-168">В этом образце показаны не все методы и возможности, описанные в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="2a38b-168">This sample does not demonstrate all the methods and functionality discussed in this topic.</span></span> <span data-ttu-id="2a38b-169">Он демонстрирует важные методы, с помощью которых должен переопределяться любой создаваемый пользователем компонент преобразования с асинхронными выходами, но не содержит кода для проверки во время разработки.</span><span class="sxs-lookup"><span data-stu-id="2a38b-169">It demonstrates the important methods that every custom transformation component with asynchronous outputs must override, but does not contain code for design-time validation.</span></span> <span data-ttu-id="2a38b-170">Кроме того, код метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> предполагает, что коллекция выходных столбцов содержит по одному столбцу на каждый столбец коллекции входных столбцов.</span><span class="sxs-lookup"><span data-stu-id="2a38b-170">Also, the code in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> assumes that the output column collection has one column for each column in the input column collection.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Pipeline;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime.Wrapper;

namespace Microsoft.Samples.SqlServer.Dts
{
   [DtsPipelineComponent(DisplayName = "AsynchronousOutput")]
   public class AsynchronousOutput : PipelineComponent
   {
      PipelineBuffer outputBuffer;
      int[] inputColumnBufferIndexes;
      int[] outputColumnBufferIndexes;

      public override void ProvideComponentProperties()
      {
         // Let the base class add the input and output objects.
         base.ProvideComponentProperties();

         // Name the input and output, and make the
         // output asynchronous.
         ComponentMetaData.InputCollection[0].Name = "Input";
         ComponentMetaData.OutputCollection[0].Name = "AsyncOutput";
         ComponentMetaData.OutputCollection[0].SynchronousInputID = 0;
      }
      public override void PreExecute()
      {
         IDTSInput100 input = ComponentMetaData.InputCollection[0];
         IDTSOutput100 output = ComponentMetaData.OutputCollection[0];

         inputColumnBufferIndexes = new int[input.InputColumnCollection.Count];
         outputColumnBufferIndexes = new int[output.OutputColumnCollection.Count];

         for (int col = 0; col < input.InputColumnCollection.Count; col++)
            inputColumnBufferIndexes[col] = BufferManager.FindColumnByLineageID(input.Buffer, input.InputColumnCollection[col].LineageID);

         for (int col = 0; col < output.OutputColumnCollection.Count; col++)
            outputColumnBufferIndexes[col] = BufferManager.FindColumnByLineageID(output.Buffer, output.OutputColumnCollection[col].LineageID);

      }

      public override void PrimeOutput(int outputs, int[] outputIDs, PipelineBuffer[] buffers)
      {
         if (buffers.Length != 0)
            outputBuffer = buffers[0];
      }
      public override void ProcessInput(int inputID, PipelineBuffer buffer)
      {
            // Advance the buffer to the next row.
            while (buffer.NextRow())
            {
               // Add a row to the output buffer.
               outputBuffer.AddRow();
               for (int x = 0; x < inputColumnBufferIndexes.Length; x++)
               {
                  // Copy the data from the input buffer column to the output buffer column.
                  outputBuffer[outputColumnBufferIndexes[x]] = buffer[inputColumnBufferIndexes[x]];
               }
            }
         if (buffer.EndOfRowset)
         {
            // EndOfRowset on the input buffer is true.
            // Set EndOfRowset on the output buffer.
            outputBuffer.SetEndOfRowset();
         }
      }
   }
}
```

```vb
Imports System
Imports Microsoft.SqlServer.Dts.Pipeline
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper

Namespace Microsoft.Samples.SqlServer.Dts

    <DtsPipelineComponent(DisplayName:="AsynchronousOutput")> _
    Public Class AsynchronousOutput

        Inherits PipelineComponent

        Private outputBuffer As PipelineBuffer
        Private inputColumnBufferIndexes As Integer()
        Private outputColumnBufferIndexes As Integer()

        Public Overrides Sub ProvideComponentProperties()

            ' Let the base class add the input and output objects.
            Me.ProvideComponentProperties()

            ' Name the input and output, and make the
            ' output asynchronous.
            ComponentMetaData.InputCollection(0).Name = "Input"
            ComponentMetaData.OutputCollection(0).Name = "AsyncOutput"
            ComponentMetaData.OutputCollection(0).SynchronousInputID = 0
        End Sub

        Public Overrides Sub PreExecute()

            Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)
            Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)

            ReDim inputColumnBufferIndexes(input.InputColumnCollection.Count)
            ReDim outputColumnBufferIndexes(output.OutputColumnCollection.Count)

            For col As Integer = 0 To input.InputColumnCollection.Count
                inputColumnBufferIndexes(col) = BufferManager.FindColumnByLineageID(input.Buffer, input.InputColumnCollection(col).LineageID)
            Next

            For col As Integer = 0 To output.OutputColumnCollection.Count
                outputColumnBufferIndexes(col) = BufferManager.FindColumnByLineageID(output.Buffer, output.OutputColumnCollection(col).LineageID)
            Next

        End Sub
        Public Overrides Sub PrimeOutput(ByVal outputs As Integer, ByVal outputIDs As Integer(), ByVal buffers As PipelineBuffer())

            If buffers.Length <> 0 Then
                outputBuffer = buffers(0)
            End If

        End Sub

        Public Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer)

                ' Advance the buffer to the next row.
                While (buffer.NextRow())

                    ' Add a row to the output buffer.
                    outputBuffer.AddRow()
                    For x As Integer = 0 To inputColumnBufferIndexes.Length

                        ' Copy the data from the input buffer column to the output buffer column.
                        outputBuffer(outputColumnBufferIndexes(x)) = buffer(inputColumnBufferIndexes(x))

                    Next
                End While

            If buffer.EndOfRowset = True Then
                ' EndOfRowset on the input buffer is true.
                ' Set the end of row set on the output buffer.
                outputBuffer.SetEndOfRowset()
            End If
        End Sub
    End Class
End Namespace
```

<span data-ttu-id="2a38b-171">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="2a38b-171">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="2a38b-172">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="2a38b-172">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="2a38b-173">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="2a38b-173">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="2a38b-174">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="2a38b-174">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="2a38b-175">См. также:</span><span class="sxs-lookup"><span data-stu-id="2a38b-175">See Also</span></span>
 <span data-ttu-id="2a38b-176">[Разработка пользовательского компонента преобразования с синхронными выходами](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md) [Основные сведения о синхронных и асинхронных преобразованиях](../understanding-synchronous-and-asynchronous-transformations.md) [Создание асинхронного преобразования с помощью компонента скрипта](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md)</span><span class="sxs-lookup"><span data-stu-id="2a38b-176">[Developing a Custom Transformation Component with Synchronous Outputs](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md) [Understanding Synchronous and Asynchronous Transformations](../understanding-synchronous-and-asynchronous-transformations.md) [Creating an Asynchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md)</span></span>


