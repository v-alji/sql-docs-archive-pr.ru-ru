---
title: Разработка пользовательского компонента преобразования с синхронными выходами | Документы Майкрософт
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
- ProcessInput method
- buffer allocations [Integration Services]
- synchronous outputs [Integration Services]
- transformation components [Integration Services]
- output columns [Integration Services]
- data flow components [Integration Services], transformation components
ms.assetid: b694d21f-9919-402d-9192-666c6449b0b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 94d78872570103d3df7e1cb96aecb144fafe4257
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736614"
---
# <a name="developing-a-custom-transformation-component-with-synchronous-outputs"></a><span data-ttu-id="050e1-102">Разработка пользовательского компонента преобразования с синхронными выходами</span><span class="sxs-lookup"><span data-stu-id="050e1-102">Developing a Custom Transformation Component with Synchronous Outputs</span></span>
  <span data-ttu-id="050e1-103">Компоненты преобразования с синхронными выходами получают строки из вышестоящих компонентов и считывают либо изменяют значения в столбцах этих строк по мере передачи строк нижестоящим компонентам.</span><span class="sxs-lookup"><span data-stu-id="050e1-103">Transformation components with synchronous outputs receive rows from upstream components, and read or modify the values in the columns of these rows as they pass the rows to downstream components.</span></span> <span data-ttu-id="050e1-104">В них также можно определить дополнительные выходные столбцы, производные от столбцов, которые передаются вышестоящими компонентами, однако эти столбцы не добавляют строки в поток данных.</span><span class="sxs-lookup"><span data-stu-id="050e1-104">They may also define additional output columns that are derived from the columns provided by upstream components, but they do not add rows to the data flow.</span></span> <span data-ttu-id="050e1-105">Дополнительные сведения о различиях между синхронными и асинхронными компонентами см. в разделе [Основные сведения о синхронных и асинхронных преобразованиях](../understanding-synchronous-and-asynchronous-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="050e1-105">For more information about the difference between synchronous and asynchronous components, see [Understanding Synchronous and Asynchronous Transformations](../understanding-synchronous-and-asynchronous-transformations.md).</span></span>  
  
 <span data-ttu-id="050e1-106">Компоненты такого типа подходят для задач, в которых данные изменяются встроенными средствами при передаче компоненту, а компоненту необязательно просматривать все строки, прежде чем приступать к их обработке.</span><span class="sxs-lookup"><span data-stu-id="050e1-106">This kind of component is suited for tasks where the data is modified inline as it is provided to the component and where the component does not have to see all the rows before processing them.</span></span> <span data-ttu-id="050e1-107">Это наиболее простой для разработки вид компонента, поскольку преобразования с синхронными выходами обычно не соединяются с внешними источниками данных, не управляют столбцами внешних метаданных и не добавляют строки в выходные буферы.</span><span class="sxs-lookup"><span data-stu-id="050e1-107">It is the easiest component to develop because transformations with synchronous outputs typically do not connect to external data sources, manage external metadata columns, or add rows to output buffers.</span></span>  
  
 <span data-ttu-id="050e1-108">Создание компонента преобразования с синхронными выходами предполагает добавление объекта <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100>, который содержит вышестоящие столбцы, выбранные для компонента, и объекта <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100>, который может содержать производные столбцы, созданные компонентом.</span><span class="sxs-lookup"><span data-stu-id="050e1-108">Creating a transformation component with synchronous outputs involves adding an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100> that will contain the upstream columns selected for the component, and a <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> object that may contain derived columns created by the component.</span></span> <span data-ttu-id="050e1-109">Необходимо также реализовать методы времени разработки и предоставить код, осуществляющий считывание или изменение столбцов во входящих строках буфера в процессе выполнения.</span><span class="sxs-lookup"><span data-stu-id="050e1-109">It also includes implementing the design-time methods, and providing code that reads or modifies the columns in the incoming buffer rows during execution.</span></span>  
  
 <span data-ttu-id="050e1-110">В этом разделе содержатся сведения о том, что требуется для реализации пользовательского компонента преобразования, а также приведены примеры кода, которые помогут лучше понять основные понятия.</span><span class="sxs-lookup"><span data-stu-id="050e1-110">This section provides the information that is required to implement a custom transformation component, and provides code examples to help you better understand the concepts.</span></span>  
  
## <a name="design-time"></a><span data-ttu-id="050e1-111">Время разработки</span><span class="sxs-lookup"><span data-stu-id="050e1-111">Design Time</span></span>  
 <span data-ttu-id="050e1-112">Код времени разработки для этого компонента включает создание входов и выходов, добавление дополнительных выходных столбцов, формируемых компонентом, и проверку конфигурации компонента.</span><span class="sxs-lookup"><span data-stu-id="050e1-112">The design-time code for this component involves creating the inputs and outputs, adding any additional output columns that the component generates, and validating the configuration of the component.</span></span>  
  
### <a name="creating-the-component"></a><span data-ttu-id="050e1-113">Создание компонента</span><span class="sxs-lookup"><span data-stu-id="050e1-113">Creating the Component</span></span>  
 <span data-ttu-id="050e1-114">Создание входов, выходов и пользовательских свойств компонента обычно осуществляется при выполнении метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="050e1-114">The inputs, outputs, and custom properties of the component are typically created during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> method.</span></span> <span data-ttu-id="050e1-115">Существует два способа добавления входа и выхода в компонент преобразования с синхронными выходами.</span><span class="sxs-lookup"><span data-stu-id="050e1-115">There are two ways that you can add the input and the output of a transformation component with synchronous outputs.</span></span> <span data-ttu-id="050e1-116">Можно использовать реализацию базового класса метода и затем изменить созданные им вход и выход по умолчанию, либо можно явным образом самостоятельно добавить вход и выход.</span><span class="sxs-lookup"><span data-stu-id="050e1-116">You can use the base class implementation of the method and then modify the default input and output that it creates, or you can explicitly add the input and output yourself.</span></span>  
  
 <span data-ttu-id="050e1-117">В следующем примере кода демонстрируется реализация метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>, явно добавляющего объекты входа и выхода.</span><span class="sxs-lookup"><span data-stu-id="050e1-117">The following code example shows an implementation of <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> that explicitly adds the input and output objects.</span></span> <span data-ttu-id="050e1-118">Вызов базового класса, с помощью которого можно достичь того же результата, заключен в комментарий.</span><span class="sxs-lookup"><span data-stu-id="050e1-118">The call to the base class that would accomplish the same thing is included in a comment.</span></span>  
  
```csharp  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.Samples.SqlServer.Dts  
{  
    [DtsPipelineComponent(DisplayName = "SynchronousComponent", ComponentType = ComponentType.Transform)]  
    public class SyncComponent : PipelineComponent  
    {  
  
        public override void ProvideComponentProperties()  
        {  
            // Add the input.  
            IDTSInput100 input = ComponentMetaData.InputCollection.New();  
            input.Name = "Input";  
  
            // Add the output.  
            IDTSOutput100 output = ComponentMetaData.OutputCollection.New();  
            output.Name = "Output";  
            output.SynchronousInputID = input.ID;  
  
            // Alternatively, you can let the base class add the input and output  
            // and set the SynchronousInputID of the output to the ID of the input.  
            // base.ProvideComponentProperties();  
        }  
    }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
Imports Microsoft.SqlServer.Dts.Runtime  
  
<DtsPipelineComponent(DisplayName:="SynchronousComponent", ComponentType:=ComponentType.Transform)> _  
Public Class SyncComponent  
    Inherits PipelineComponent  
  
    Public Overrides Sub ProvideComponentProperties()  
  
        ' Add the input.  
        Dim input As IDTSInput100 = ComponentMetaData.InputCollection.New()  
        input.Name = "Input"  
  
        ' Add the output.  
        Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection.New()  
        output.Name = "Output"  
        output.SynchronousInputID = Input.ID  
  
        ' Alternatively, you can let the base class add the input and output  
        ' and set the SynchronousInputID of the output to the ID of the input.  
        ' base.ProvideComponentProperties();  
  
    End Sub  
  
End Class  
```  
  
### <a name="creating-and-configuring-output-columns"></a><span data-ttu-id="050e1-119">Создание и настройка выходных столбцов</span><span class="sxs-lookup"><span data-stu-id="050e1-119">Creating and Configuring Output Columns</span></span>  
 <span data-ttu-id="050e1-120">Хотя компоненты преобразования с синхронными выходами не добавляют строки в буферы, они могут добавлять дополнительные выходные столбцы в собственный выход.</span><span class="sxs-lookup"><span data-stu-id="050e1-120">Although transformation components with synchronous outputs do not add rows to buffers, they may add extra output columns to their output.</span></span> <span data-ttu-id="050e1-121">Как правило, при добавлении компонентом выходного столбца значения нового выходного столбца производятся во время выполнения от данных, содержащихся в одном или нескольких столбцах, переданных компоненту вышестоящим компонентом.</span><span class="sxs-lookup"><span data-stu-id="050e1-121">Typically, when a component adds an output column, the values for the new output column are derived at run time from the data that is contained in one or more of the columns provided to the component by an upstream component.</span></span>  
  
 <span data-ttu-id="050e1-122">После создания выходного столбца необходимо задать для него свойства типа данных.</span><span class="sxs-lookup"><span data-stu-id="050e1-122">After an output column has been created, its data type properties must be set.</span></span> <span data-ttu-id="050e1-123">Задание свойств типа данных выходного столбца требует специальной обработки и осуществляется путем вызова метода <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.SetDataTypeProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="050e1-123">Setting the data type properties of an output column requires special handling and is performed by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.SetDataTypeProperties%2A> method.</span></span> <span data-ttu-id="050e1-124">Использование этого метода необходимо, поскольку свойства <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Length%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Precision%2A> и <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.CodePage%2A> по отдельности доступны только для чтения по причине зависимости каждого из них от настроек других.</span><span class="sxs-lookup"><span data-stu-id="050e1-124">This method is required because the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Length%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Precision%2A>, and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.CodePage%2A> properties are individually read-only, because each depends on the settings of the other.</span></span> <span data-ttu-id="050e1-125">Этот метод гарантирует согласованность задания значений свойств, а задача потока данных осуществляет проверку правильности задания значений.</span><span class="sxs-lookup"><span data-stu-id="050e1-125">This method guarantees that the values of the properties are set consistently, and the data flow task validates that they are set correctly.</span></span>  
  
 <span data-ttu-id="050e1-126">Свойство <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A> столбца определяет значения, задаваемые для других свойств.</span><span class="sxs-lookup"><span data-stu-id="050e1-126">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A> of the column determines the values that are set for the other properties.</span></span> <span data-ttu-id="050e1-127">В следующей таблице показаны требования к зависимым свойствам для каждого значения <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>.</span><span class="sxs-lookup"><span data-stu-id="050e1-127">The following table shows the requirements on the dependent properties for each <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>.</span></span> <span data-ttu-id="050e1-128">Для не указанных здесь типов данных зависимые свойства имеют нулевые значения.</span><span class="sxs-lookup"><span data-stu-id="050e1-128">The data types not listed have their dependent properties set to zero.</span></span>  
  
|<span data-ttu-id="050e1-129">DataType</span><span class="sxs-lookup"><span data-stu-id="050e1-129">DataType</span></span>|<span data-ttu-id="050e1-130">Длина</span><span class="sxs-lookup"><span data-stu-id="050e1-130">Length</span></span>|<span data-ttu-id="050e1-131">Масштабирование</span><span class="sxs-lookup"><span data-stu-id="050e1-131">Scale</span></span>|<span data-ttu-id="050e1-132">Точность</span><span class="sxs-lookup"><span data-stu-id="050e1-132">Precision</span></span>|<span data-ttu-id="050e1-133">CodePage</span><span class="sxs-lookup"><span data-stu-id="050e1-133">CodePage</span></span>|  
|--------------|------------|-----------|---------------|--------------|  
|<span data-ttu-id="050e1-134">DT_DECIMAL</span><span class="sxs-lookup"><span data-stu-id="050e1-134">DT_DECIMAL</span></span>|<span data-ttu-id="050e1-135">0</span><span class="sxs-lookup"><span data-stu-id="050e1-135">0</span></span>|<span data-ttu-id="050e1-136">Больше 0 и меньше или равно 28.</span><span class="sxs-lookup"><span data-stu-id="050e1-136">Greater than 0 and less than or equal to 28.</span></span>|<span data-ttu-id="050e1-137">0</span><span class="sxs-lookup"><span data-stu-id="050e1-137">0</span></span>|<span data-ttu-id="050e1-138">0</span><span class="sxs-lookup"><span data-stu-id="050e1-138">0</span></span>|  
|<span data-ttu-id="050e1-139">DT_CY</span><span class="sxs-lookup"><span data-stu-id="050e1-139">DT_CY</span></span>|<span data-ttu-id="050e1-140">0</span><span class="sxs-lookup"><span data-stu-id="050e1-140">0</span></span>|<span data-ttu-id="050e1-141">0</span><span class="sxs-lookup"><span data-stu-id="050e1-141">0</span></span>|<span data-ttu-id="050e1-142">0</span><span class="sxs-lookup"><span data-stu-id="050e1-142">0</span></span>|<span data-ttu-id="050e1-143">0</span><span class="sxs-lookup"><span data-stu-id="050e1-143">0</span></span>|  
|<span data-ttu-id="050e1-144">DT_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="050e1-144">DT_NUMERIC</span></span>|<span data-ttu-id="050e1-145">0</span><span class="sxs-lookup"><span data-stu-id="050e1-145">0</span></span>|<span data-ttu-id="050e1-146">Больше 0, меньше или равно 28 и меньше, чем точность.</span><span class="sxs-lookup"><span data-stu-id="050e1-146">Greater than 0 and less than or equal to 28, and less than Precision.</span></span>|<span data-ttu-id="050e1-147">Больше или равно 1 и меньше или равно 38.</span><span class="sxs-lookup"><span data-stu-id="050e1-147">Greater than or equal to 1 and less than or equal to 38.</span></span>|<span data-ttu-id="050e1-148">0</span><span class="sxs-lookup"><span data-stu-id="050e1-148">0</span></span>|  
|<span data-ttu-id="050e1-149">DT_BYTES</span><span class="sxs-lookup"><span data-stu-id="050e1-149">DT_BYTES</span></span>|<span data-ttu-id="050e1-150">Больше 0.</span><span class="sxs-lookup"><span data-stu-id="050e1-150">Greater than 0.</span></span>|<span data-ttu-id="050e1-151">0</span><span class="sxs-lookup"><span data-stu-id="050e1-151">0</span></span>|<span data-ttu-id="050e1-152">0</span><span class="sxs-lookup"><span data-stu-id="050e1-152">0</span></span>|<span data-ttu-id="050e1-153">0</span><span class="sxs-lookup"><span data-stu-id="050e1-153">0</span></span>|  
|<span data-ttu-id="050e1-154">DT_STR</span><span class="sxs-lookup"><span data-stu-id="050e1-154">DT_STR</span></span>|<span data-ttu-id="050e1-155">Больше 0 и меньше 8000.</span><span class="sxs-lookup"><span data-stu-id="050e1-155">Greater than 0 and less than 8000.</span></span>|<span data-ttu-id="050e1-156">0</span><span class="sxs-lookup"><span data-stu-id="050e1-156">0</span></span>|<span data-ttu-id="050e1-157">0</span><span class="sxs-lookup"><span data-stu-id="050e1-157">0</span></span>|<span data-ttu-id="050e1-158">Не равно 0 и представляет допустимую кодовую страницу.</span><span class="sxs-lookup"><span data-stu-id="050e1-158">Not 0, and a valid code page.</span></span>|  
|<span data-ttu-id="050e1-159">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="050e1-159">DT_WSTR</span></span>|<span data-ttu-id="050e1-160">Больше 0 и меньше 4 000.</span><span class="sxs-lookup"><span data-stu-id="050e1-160">Greater than 0 and less than 4000.</span></span>|<span data-ttu-id="050e1-161">0</span><span class="sxs-lookup"><span data-stu-id="050e1-161">0</span></span>|<span data-ttu-id="050e1-162">0</span><span class="sxs-lookup"><span data-stu-id="050e1-162">0</span></span>|<span data-ttu-id="050e1-163">0</span><span class="sxs-lookup"><span data-stu-id="050e1-163">0</span></span>|  
  
 <span data-ttu-id="050e1-164">Поскольку ограничения свойств типа данных основаны на типе данных выходного столбца, во время работы с управляемыми типами необходимо выбрать правильный тип данных служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="050e1-164">Because the restrictions on the data type properties are based on the data type of the output column, you must choose the correct [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] data type when you work with managed types.</span></span> <span data-ttu-id="050e1-165">Базовый класс предоставляет три вспомогательных метода, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ConvertBufferDataTypeToFitManaged%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferTypeToDataRecordType%2A> и <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.DataRecordTypeToBufferType%2A>, которые упрощают для разработчиков управляемых компонентов выбор типа данных служб [!INCLUDE[ssIS](../../includes/ssis-md.md)], если необходим управляемый тип.</span><span class="sxs-lookup"><span data-stu-id="050e1-165">The base class provides three helper methods, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ConvertBufferDataTypeToFitManaged%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferTypeToDataRecordType%2A>, and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.DataRecordTypeToBufferType%2A> that assist managed component developers in selecting an [!INCLUDE[ssIS](../../includes/ssis-md.md)] data type given a managed type.</span></span> <span data-ttu-id="050e1-166">Эти методы преобразуют управляемые типы данных в типы данных служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] и обратно.</span><span class="sxs-lookup"><span data-stu-id="050e1-166">These methods convert managed data types to [!INCLUDE[ssIS](../../includes/ssis-md.md)] data types, and vice versa.</span></span>  
  
## <a name="run-time"></a><span data-ttu-id="050e1-167">Время выполнения</span><span class="sxs-lookup"><span data-stu-id="050e1-167">Run Time</span></span>  
 <span data-ttu-id="050e1-168">Обычно реализация части компонента, которая относится ко времени выполнения, заключается в решении двух задач — поиска входных и выходных столбцов компонента в буфере и считывания либо записи значений этих столбцов во входящие строки буфера.</span><span class="sxs-lookup"><span data-stu-id="050e1-168">Generally, the implementation of the run-time part of the component is categorized into two tasks-locating the input and output columns of the component in the buffer, and reading or writing the values of these columns in the incoming buffer rows.</span></span>  
  
### <a name="locating-columns-in-the-buffer"></a><span data-ttu-id="050e1-169">Поиск столбцов в буфере</span><span class="sxs-lookup"><span data-stu-id="050e1-169">Locating Columns in the Buffer</span></span>  
 <span data-ttu-id="050e1-170">Количество столбцов в буферах, передаваемых компоненту во время выполнения, скорее всего, окажется больше числа столбцов во входных и выходных коллекциях компонента.</span><span class="sxs-lookup"><span data-stu-id="050e1-170">The number of columns in the buffers that are provided to a component during execution will likely exceed the number of columns in the input or output collections of the component.</span></span> <span data-ttu-id="050e1-171">Так происходит потому, что каждый буфер содержит все выходные столбцы, определенные в компонентах потока данных.</span><span class="sxs-lookup"><span data-stu-id="050e1-171">This is because each buffer contains all the output columns defined in the components in a data flow.</span></span> <span data-ttu-id="050e1-172">Чтобы обеспечить правильное сопоставление столбцов буфера со столбцами входа и выхода, разработчикам компонентов следует использовать метод <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> диспетчера буферов <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span><span class="sxs-lookup"><span data-stu-id="050e1-172">To ensure that the buffer columns are correctly matched to the columns of the input or output, component developers must use the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span></span> <span data-ttu-id="050e1-173">Этот метод осуществляет поиск столбца в указанном буфере по его идентификатору журнала преобразований.</span><span class="sxs-lookup"><span data-stu-id="050e1-173">This method locates a column in the specified buffer by its lineage ID.</span></span> <span data-ttu-id="050e1-174">Обычно поиск столбцов производится в процессе выполнения метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>, поскольку это первый метод времени выполнения, в котором становится доступным свойство <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span><span class="sxs-lookup"><span data-stu-id="050e1-174">Typically columns are located during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> because this is the first run-time method where the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> property becomes available.</span></span>  
  
 <span data-ttu-id="050e1-175">В следующем примере кода демонстрируется компонент, осуществляющий поиск индексов столбцов в своей коллекции входных и выходных столбцов в процессе выполнения метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>.</span><span class="sxs-lookup"><span data-stu-id="050e1-175">The following code example shows a component that locates indexes of the columns in its input and output column collection during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>.</span></span> <span data-ttu-id="050e1-176">Индексы столбцов хранятся в целочисленном массиве, и доступ к ним компонент может получить в процессе выполнения метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="050e1-176">The column indexes are stored in an integer array, and can be accessed by the component during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span>  
  
```csharp  
int []inputColumns;  
int []outputColumns;  
  
public override void PreExecute()  
{  
    IDTSInput100 input = ComponentMetaData.InputCollection[0];  
    IDTSOutput100 output = ComponentMetaData.OutputCollection[0];  
  
    inputColumns = new int[input.InputColumnCollection.Count];  
    outputColumns = new int[output.OutputColumnCollection.Count];  
  
    for(int col=0; col < input.InputColumnCollection.Count; col++)  
    {  
        IDTSInputColumn100 inputColumn = input.InputColumnCollection[col];  
        inputColumns[col] = BufferManager.FindColumnByLineageID(input.Buffer, inputColumn.LineageID);  
    }  
  
    for(int col=0; col < output.OutputColumnCollection.Count; col++)  
    {  
        IDTSOutputColumn100 outputColumn = output.OutputColumnCollection[col];  
        outputColumns[col] = BufferManager.FindColumnByLineageID(input.Buffer, outputColumn.LineageID);  
    }  
  
}  
```  
  
```vb  
Public Overrides Sub PreExecute()  
  
    Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)  
    Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)  
  
    ReDim inputColumns(input.InputColumnCollection.Count)  
    ReDim outputColumns(output.OutputColumnCollection.Count)  
  
    For col As Integer = 0 To input.InputColumnCollection.Count  
  
        Dim inputColumn As IDTSInputColumn100 = input.InputColumnCollection(col)  
        inputColumns(col) = BufferManager.FindColumnByLineageID(input.Buffer, inputColumn.LineageID)  
    Next  
  
    For col As Integer = 0 To output.OutputColumnCollection.Count  
  
        Dim outputColumn As IDTSOutputColumn100 = output.OutputColumnCollection(col)  
        outputColumns(col) = BufferManager.FindColumnByLineageID(input.Buffer, outputColumn.LineageID)  
    Next  
  
End Sub  
```  
  
### <a name="processing-rows"></a><span data-ttu-id="050e1-177">Обработка строк</span><span class="sxs-lookup"><span data-stu-id="050e1-177">Processing Rows</span></span>  
 <span data-ttu-id="050e1-178">Компоненты получают объекты <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>, содержащие строки и столбцы, в методе <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="050e1-178">Components receive <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> objects that contain rows and columns in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method.</span></span> <span data-ttu-id="050e1-179">При выполнении этого метода осуществляется итерация по строкам в буфере, а столбцы, идентифицированные во время выполнения метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>, считываются и изменяются.</span><span class="sxs-lookup"><span data-stu-id="050e1-179">During this method the rows in the buffer are iterated, and the columns identified during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> are read and modified.</span></span> <span data-ttu-id="050e1-180">Метод вызывается задачей потока данных повторно до тех пор, пока не останется строк, переданных из вышестоящего компонента.</span><span class="sxs-lookup"><span data-stu-id="050e1-180">The method is called repeatedly by the data flow task until no more rows are provided from the upstream component.</span></span>  
  
 <span data-ttu-id="050e1-181">Считывание или запись отдельного столбца в буфере осуществляется с использованием индексатора массива в качестве метода доступа либо с помощью одного из методов `Get` или `Set`.</span><span class="sxs-lookup"><span data-stu-id="050e1-181">An individual column in the buffer is read or written by using the array indexer access method, or by using one of the `Get` or `Set` methods.</span></span> <span data-ttu-id="050e1-182">Методы `Get` и `Set` более эффективны, их следует использовать в случаях, когда тип данных столбца в буфере известен.</span><span class="sxs-lookup"><span data-stu-id="050e1-182">The `Get` and `Set` methods are more efficient and should be used when the data type of the column in the buffer is known.</span></span>  
  
 <span data-ttu-id="050e1-183">В следующем примере кода демонстрируется реализация метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>, обрабатывающего входящие строки.</span><span class="sxs-lookup"><span data-stu-id="050e1-183">The following code example shows an implementation of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method that processes incoming rows.</span></span>  
  
```csharp  
public override void ProcessInput( int InputID, PipelineBuffer buffer)  
{  
       while( buffer.NextRow())  
       {  
            for(int x=0; x < inputColumns.Length;x++)  
            {  
                if(!buffer.IsNull(inputColumns[x]))  
                {  
                    object columnData = buffer[inputColumns[x]];  
                    // TODO: Modify the column data.  
                    buffer[inputColumns[x]] = columnData;  
                }  
            }  
  
      }  
}  
```  
  
```vb  
Public Overrides Sub ProcessInput(ByVal InputID As Integer, ByVal buffer As PipelineBuffer)  
  
        While (buffer.NextRow())  
  
            For x As Integer = 0 To inputColumns.Length  
  
                if buffer.IsNull(inputColumns(x)) = false then  
  
                    Dim columnData As Object = buffer(inputColumns(x))  
                    ' TODO: Modify the column data.  
                    buffer(inputColumns(x)) = columnData  
  
                End If  
            Next  
  
        End While  
End Sub  
```  
  
## <a name="sample"></a><span data-ttu-id="050e1-184">Образец</span><span class="sxs-lookup"><span data-stu-id="050e1-184">Sample</span></span>  
 <span data-ttu-id="050e1-185">В следующем образце демонстрируется простой компонент преобразования с синхронными выходами, изменяющий регистр значений всех символьных столбцов на верхний.</span><span class="sxs-lookup"><span data-stu-id="050e1-185">The following sample shows a simple transformation component with synchronous outputs that converts the values of all string columns to uppercase.</span></span> <span data-ttu-id="050e1-186">В этом образце показаны не все методы и возможности, описанные в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="050e1-186">This sample does not demonstrate all the methods and functionality discussed in this topic.</span></span> <span data-ttu-id="050e1-187">В этом образце демонстрируются важные методы, которые должны быть переопределены каждым пользовательским компонентом преобразования с синхронными выходами, но отсутствует код для проверки во время разработки.</span><span class="sxs-lookup"><span data-stu-id="050e1-187">It demonstrates the important methods that every custom transformation component with synchronous outputs must override, but does not contain code for design-time validation.</span></span>  
  
```csharp  
using System;  
using System.Collections;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
using Microsoft.SqlServer.Dts.Runtime.Wrapper;  
  
namespace Uppercase  
{  
  [DtsPipelineComponent(DisplayName = "Uppercase")]  
  public class Uppercase : PipelineComponent  
  {  
    ArrayList m_ColumnIndexList = new ArrayList();  
  
    public override void ProvideComponentProperties()  
    {  
      base.ProvideComponentProperties();  
      ComponentMetaData.InputCollection[0].Name = "Uppercase Input";  
      ComponentMetaData.OutputCollection[0].Name = "Uppercase Output";  
    }  
  
    public override void PreExecute()  
    {  
      IDTSInput100 input = ComponentMetaData.InputCollection[0];  
      IDTSInputColumnCollection100 inputColumns = input.InputColumnCollection;  
  
      foreach (IDTSInputColumn100 column in inputColumns)  
      {  
        if (column.DataType == DataType.DT_STR || column.DataType == DataType.DT_WSTR)  
        {  
          m_ColumnIndexList.Add((int)BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID));  
        }  
      }  
    }  
  
    public override void ProcessInput(int inputID, PipelineBuffer buffer)  
    {  
      while (buffer.NextRow())  
      {  
        foreach (int columnIndex in m_ColumnIndexList)  
        {  
          string str = buffer.GetString(columnIndex);  
          buffer.SetString(columnIndex, str.ToUpper());  
        }  
      }  
    }  
  }  
}  
```  
  
```vb  
Imports System   
Imports System.Collections   
Imports Microsoft.SqlServer.Dts.Pipeline   
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper   
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper   
Namespace Uppercase   
  
 <DtsPipelineComponent(DisplayName="Uppercase")> _   
 Public Class Uppercase   
 Inherits PipelineComponent   
   Private m_ColumnIndexList As ArrayList = New ArrayList   
  
   Public  Overrides Sub ProvideComponentProperties()   
     MyBase.ProvideComponentProperties   
     ComponentMetaData.InputCollection(0).Name = "Uppercase Input"   
     ComponentMetaData.OutputCollection(0).Name = "Uppercase Output"   
   End Sub   
  
   Public  Overrides Sub PreExecute()   
     Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)   
     Dim inputColumns As IDTSInputColumnCollection100 = input.InputColumnCollection   
     For Each column As IDTSInputColumn100 In inputColumns   
       If column.DataType = DataType.DT_STR OrElse column.DataType = DataType.DT_WSTR Then   
         m_ColumnIndexList.Add(CType(BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID), Integer))   
       End If   
     Next   
   End Sub   
  
   Public  Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer)   
     While buffer.NextRow   
       For Each columnIndex As Integer In m_ColumnIndexList   
         Dim str As String = buffer.GetString(columnIndex)   
         buffer.SetString(columnIndex, str.ToUpper)   
       Next   
     End While   
   End Sub   
 End Class   
End Namespace  
```  
  
<span data-ttu-id="050e1-188">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="050e1-188">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="050e1-189">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="050e1-189">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="050e1-190">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="050e1-190">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="050e1-191">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="050e1-191">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="050e1-192">См. также:</span><span class="sxs-lookup"><span data-stu-id="050e1-192">See Also</span></span>  
 <span data-ttu-id="050e1-193">[Разработка пользовательского компонента преобразования с асинхронными выходами](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md) </span><span class="sxs-lookup"><span data-stu-id="050e1-193">[Developing a Custom Transformation Component with Asynchronous Outputs](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md) </span></span>  
 <span data-ttu-id="050e1-194">[Основные сведения о синхронных и асинхронных преобразованиях](../understanding-synchronous-and-asynchronous-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="050e1-194">[Understanding Synchronous and Asynchronous Transformations](../understanding-synchronous-and-asynchronous-transformations.md) </span></span>  
 [<span data-ttu-id="050e1-195">Создание синхронного преобразования с помощью компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="050e1-195">Creating a Synchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md) 
  
  
