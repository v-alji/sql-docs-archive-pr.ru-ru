---
title: План выполнения и выделение буферов | Документы Майкрософт
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
- custom data flow components [Integration Services], buffer allocations
- custom data flow components [Integration Services], execution plans
- buffer allocations [Integration Services]
- data flow components [Integration Services], buffer allocations
- data flow components [Integration Services], execution plans
- execution plans [Integration Services]
ms.assetid: 679d9ff0-641e-47c3-abb8-d1a7dcb279dd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 03b8bb22988ccf77f8920252ac2d600478c92f3b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729666"
---
# <a name="execution-plan-and-buffer-allocation"></a><span data-ttu-id="4eb9b-102">План выполнения и выделение буферов</span><span class="sxs-lookup"><span data-stu-id="4eb9b-102">Execution Plan and Buffer Allocation</span></span>
  <span data-ttu-id="4eb9b-103">Перед выполнением задача потока данных проверяет свои компоненты и формирует план выполнения для каждой последовательности компонентов.</span><span class="sxs-lookup"><span data-stu-id="4eb9b-103">Before execution, the data flow task examines its components and generates an execution plan for each sequence of components.</span></span> <span data-ttu-id="4eb9b-104">В этом разделе предоставляются сведения о плане выполнения, рассматривается, как просмотреть план и как на основании плана выполнения выделяются входной и выходной буферы.</span><span class="sxs-lookup"><span data-stu-id="4eb9b-104">This section provides details about the execution plan, how to view the plan, and how input and output buffers are allocated based on the execution plan.</span></span>  
  
## <a name="understanding-the-execution-plan"></a><span data-ttu-id="4eb9b-105">Основные сведения о плане выполнения</span><span class="sxs-lookup"><span data-stu-id="4eb9b-105">Understanding the Execution Plan</span></span>  
 <span data-ttu-id="4eb9b-106">План выполнения содержит потоки источника и рабочие потоки. Каждый поток содержит списки действий, которые задают списки действий над выходными данными для потоков источника или списки действий над входными и выходными данными для рабочих потоков.</span><span class="sxs-lookup"><span data-stu-id="4eb9b-106">An execution plan contains source threads and work threads, and each thread contains work lists that specify output work lists for source threads or input and output work lists for work threads.</span></span> <span data-ttu-id="4eb9b-107">Потоки источника в плане выполнения представляют компоненты источника в потоке данных и идентифицируются в плане выполнения как *SourceThread\*\*n*, где *n* — это начинающееся с нуля число потоков источника.</span><span class="sxs-lookup"><span data-stu-id="4eb9b-107">The source threads in an execution plan represent the source components in the data flow and are identified in the execution plan by *SourceThread\*\*n*, where *n* is the zero-based number of the source thread.</span></span>  
  
 <span data-ttu-id="4eb9b-108">Каждый поток источника создает буфер, устанавливает прослушивателя и вызывает метод <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> на компоненте источника.</span><span class="sxs-lookup"><span data-stu-id="4eb9b-108">Each source thread creates a buffer, sets a listener, and calls the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method on the source component.</span></span> <span data-ttu-id="4eb9b-109">Здесь начинается выполнение и отсюда берутся данные, когда компонент источника начинает добавлять строки в выходные буферы, предоставляемые ему задачей потока данных.</span><span class="sxs-lookup"><span data-stu-id="4eb9b-109">This is where execution starts and data originates, as the source component starts adding rows to the output buffers that are provided to it by the data flow task.</span></span> <span data-ttu-id="4eb9b-110">После начала работы потоков источника работа распределяется среди рабочих потоков.</span><span class="sxs-lookup"><span data-stu-id="4eb9b-110">After the source threads are running, the balance of work is distributed among work threads.</span></span>  
  
 <span data-ttu-id="4eb9b-111">Рабочий поток содержит списки действий как над входными, так и над выходными данными и идентифицируется в плане выполнения как *WorkThread\*\*n*, где *n* — это начинающееся с нуля число рабочих потоков.</span><span class="sxs-lookup"><span data-stu-id="4eb9b-111">A work thread may contain both input and output work lists and is identified in the execution plan as *WorkThread\*\*n*, where *n* is the zero-based number of the work thread.</span></span> <span data-ttu-id="4eb9b-112">Эти потоки содержат списки действий над выходными данными, если граф содержит компонент с асинхронными выходами.</span><span class="sxs-lookup"><span data-stu-id="4eb9b-112">These threads contain output work lists when the graph contains a component with asynchronous outputs.</span></span>  
  
 <span data-ttu-id="4eb9b-113">Следующий образец плана выполнения представляет поток данных, который содержит компонент источника, подключенный к преобразованию с асинхронным выходом, подключенным к компоненту назначения.</span><span class="sxs-lookup"><span data-stu-id="4eb9b-113">The following sample execution plan represents a data flow that contains a source component connected to a transformation with an asynchronous output connected to a destination component.</span></span> <span data-ttu-id="4eb9b-114">В этом примере WorkThread0 содержит список действий над выходными данными, поскольку компонент преобразования имеет асинхронный выход.</span><span class="sxs-lookup"><span data-stu-id="4eb9b-114">In this example, WorkThread0 contains an output work list because the transformation component has an asynchronous output.</span></span>  
  
```  
SourceThread0   
    Influences: 72 158   
    Output Work List   
        CreatePrimeBuffer of type 1 for output id 10   
        SetBufferListener: "WorkThread0" for input ID 73   
        CallPrimeOutput on component "OLE DB Source" (1)   
    End Output Work List   
    This thread drives 0 distributors   
End SourceThread0   
WorkThread0   
    Influences: 72 158   
    Input Work list, input ID 73   
        CallProcessInput on input ID 73 on component "Sort" (72) for view type 2   
    End Input Work list for input 73   
    Output Work List   
        CreatePrimeBuffer of type 3 for output id 74   
        SetBufferListener: "WorkThread1" for input ID 171with internal handoff   
        CallPrimeOutput on component "Sort" (72)   
    End Output Work List   
    This thread drives 0 distributors   
End WorkThread0   
WorkThread1   
    Influences: 158   
    Input Work list, input ID 171  
        CallProcessInput on input ID 171 on component "OLE DB Destination" (158) for view type 4  
    End Input Work list for input 171   
    Output Work List   
    End Output Work List   
    This thread drives 0 distributors   
End WorkThread1  
```  
  
> [!NOTE]  
>  <span data-ttu-id="4eb9b-115">План выполнения создается при каждом выполнении пакета и может отслеживаться с помощью добавления в пакет регистратора, включения ведения журнала и выбора события **PipelineExecutionPlan**.</span><span class="sxs-lookup"><span data-stu-id="4eb9b-115">The execution plan is generated every time a package is executed, and can be captured by adding a log provider to the package, enabling logging, and selecting the **PipelineExecutionPlan** event.</span></span>  
  
## <a name="understanding-buffer-allocation"></a><span data-ttu-id="4eb9b-116">Основные сведения о выделении буферов</span><span class="sxs-lookup"><span data-stu-id="4eb9b-116">Understanding Buffer Allocation</span></span>  
 <span data-ttu-id="4eb9b-117">На основании плана выполнения задача потока данных создает буферы, содержащие столбцы, определенные в выходах компонентов потока данных.</span><span class="sxs-lookup"><span data-stu-id="4eb9b-117">Based on the execution plan, the data flow task creates buffers that contain the columns defined in the outputs of the data flow components.</span></span> <span data-ttu-id="4eb9b-118">Буфер повторно используется как потоки данных через последовательность компонентов, пока не встретится компонент с асинхронными выходами.</span><span class="sxs-lookup"><span data-stu-id="4eb9b-118">The buffer is reused as the data flows through the sequence of components, until a component with asynchronous outputs is encountered.</span></span> <span data-ttu-id="4eb9b-119">После этого создается новый буфер, который содержит выходные столбцы асинхронного выхода и выходные столбцы компонентов нисходящего потока.</span><span class="sxs-lookup"><span data-stu-id="4eb9b-119">Then, a new buffer is created, which contains the output columns of the asynchronous output and the output columns of downstream components.</span></span>  
  
 <span data-ttu-id="4eb9b-120">Во время выполнения компоненты имеют доступ к буферу в текущем источнике рабочего потока.</span><span class="sxs-lookup"><span data-stu-id="4eb9b-120">During execution, components have access to the buffer in the current source or work thread.</span></span> <span data-ttu-id="4eb9b-121">Буфер является либо входным буфером, предоставляемым методом <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>, либо выходным буфером, предоставляемым методом <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="4eb9b-121">The buffer is either an input buffer, provided by the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method, or an output buffer, provided by the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method.</span></span> <span data-ttu-id="4eb9b-122">Свойство <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.Mode%2A> буфера <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> также идентифицирует каждый буфер как входной или выходной буфер.</span><span class="sxs-lookup"><span data-stu-id="4eb9b-122">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.Mode%2A> property of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> also identifies each buffer as an input or output buffer.</span></span>  
  
 <span data-ttu-id="4eb9b-123">Компоненты преобразования с асинхронными выходами получают существующий входной буфер от метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> и получают новый выходной буфер от метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="4eb9b-123">Transformation components with asynchronous outputs receive the existing input buffer from the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method, and receive the new output buffer from the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method.</span></span> <span data-ttu-id="4eb9b-124">Компонент преобразования с асинхронными выходами является единственным типом компонентов потока данных, который получает и входной, и выходной буфера.</span><span class="sxs-lookup"><span data-stu-id="4eb9b-124">A transformation component with asynchronous outputs is the only type of data flow component that receives both an input and an output buffer.</span></span>  
  
 <span data-ttu-id="4eb9b-125">Поскольку буфер, предоставленный компоненту, скорее всего, содержит больше столбцов, чем имеет компонент в его коллекциях входных и выходных столбцов, разработчики компонентов могут вызывать метод <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A>, чтобы определить положение столбца в буфере по его идентификатору `LineageID`.</span><span class="sxs-lookup"><span data-stu-id="4eb9b-125">Because the buffer provided to a component is likely to contain more columns than the component has in its input or output column collections, component developers can call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> method to locate a column in the buffer by specifying its `LineageID`.</span></span>  
  
<span data-ttu-id="4eb9b-126">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="4eb9b-126">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="4eb9b-127">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="4eb9b-127">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="4eb9b-128">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="4eb9b-128">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="4eb9b-129">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="4eb9b-129">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
