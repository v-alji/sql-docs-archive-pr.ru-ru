---
title: Создание пользовательского компонента потока данных | Документы Майкрософт
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
- design-time component interface [Integration Services]
- custom data flow components [Integration Services], about data flow components
- custom data flow components [Integration Services]
- data flow components [Integration Services]
- data flow components [Integration Services], developing
ms.assetid: 9d96bcf5-eba8-44bd-b113-ed51ad0d0521
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 110d07ff88707ad1a01f299b6f532df99ce58404
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665448"
---
# <a name="creating-a-custom-data-flow-component"></a><span data-ttu-id="78217-102">Создание пользовательского компонента потока данных</span><span class="sxs-lookup"><span data-stu-id="78217-102">Creating a Custom Data Flow Component</span></span>
  <span data-ttu-id="78217-103">В службах [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] задача потока данных предоставляет доступ к объектной модели, позволяющей разработчикам создавать пользовательские компоненты потока данных (источники, преобразования и назначения) с помощью платформы [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] и управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="78217-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], the data flow task exposes an object model that lets developers create custom data flow components-sources, transformations, and destinations-by using the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] and managed code.</span></span>  
  
 <span data-ttu-id="78217-104">Задача потока данных состоит из компонентов, содержащих интерфейс <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> и коллекцию объектов <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100>, которыми определяется движение данных между компонентами.</span><span class="sxs-lookup"><span data-stu-id="78217-104">A data flow task consists of components that contain an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface and a collection of <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> objects that define the movement of data between components.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="78217-105">При создании настраиваемого поставщика в файл ProviderDescriptors.xml необходимо внести значения столбца метаданных.</span><span class="sxs-lookup"><span data-stu-id="78217-105">When you create a custom provider, you need to update the ProviderDescriptors.xml file with the metadata column values.</span></span>  
  
## <a name="design-time-and-run-time"></a><span data-ttu-id="78217-106">Время разработки и время выполнения</span><span class="sxs-lookup"><span data-stu-id="78217-106">Design Time and Run Time</span></span>  
 <span data-ttu-id="78217-107">Перед выполнением задача потока данных считается находящейся в состоянии времени разработки, поскольку она подвергается добавочным изменениям.</span><span class="sxs-lookup"><span data-stu-id="78217-107">Before execution, the data flow task is said to be in a design-time state, as it undergoes incremental changes.</span></span> <span data-ttu-id="78217-108">К таким изменениям относятся добавление или удаление компонентов, добавление или удаление объектов пути, которые соединяют компоненты, и изменения в метаданных компонентов.</span><span class="sxs-lookup"><span data-stu-id="78217-108">Changes may include the addition or removal of components, the addition or removal of the path objects that connect components, and changes to the metadata of the components.</span></span> <span data-ttu-id="78217-109">При изменении метаданных компонент может отслеживать их и выполнять ответные действия.</span><span class="sxs-lookup"><span data-stu-id="78217-109">When metadata changes occur, the component can monitor and react to the changes.</span></span> <span data-ttu-id="78217-110">Например, компонент может не допускать внесения определенных изменений или вносить дополнительные изменения в ответ на изменение.</span><span class="sxs-lookup"><span data-stu-id="78217-110">For example, a component can disallow certain changes or to make additional changes in response to a change.</span></span> <span data-ttu-id="78217-111">Во время разработки конструктор взаимодействует с компонентом через интерфейс <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> времени разработки.</span><span class="sxs-lookup"><span data-stu-id="78217-111">At design time, the designer interacts with a component through the design-time <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> interface.</span></span>  
  
 <span data-ttu-id="78217-112">Во время выполнения задача потока данных исследует последовательность компонентов, подготавливает план выполнения и управляет пулом рабочих потоков, выполняющих план работы.</span><span class="sxs-lookup"><span data-stu-id="78217-112">At execution time, the data flow task examines the sequence of components, prepares an execution plan, and manages a pool of worker threads that execute the work plan.</span></span> <span data-ttu-id="78217-113">Хотя каждый рабочий поток выполняет некоторую работу, являющуюся внутренней для задачи потока данных, основной задачей рабочего потока является вызов методов компонента через интерфейс <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100> времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="78217-113">Although each worker thread performs some work that is internal to the data flow task, the principal task of the worker thread is to call the methods of the component through the run-time <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100> interface.</span></span>  
  
## <a name="creating-a-component"></a><span data-ttu-id="78217-114">Создание компонента</span><span class="sxs-lookup"><span data-stu-id="78217-114">Creating a Component</span></span>  
 <span data-ttu-id="78217-115">Чтобы создать компонент потока данных, необходимо создать производный класс от базового класса <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent>, применить класс <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute>, а затем переопределить соответствующие методы базового класса.</span><span class="sxs-lookup"><span data-stu-id="78217-115">To create a data flow component, you derive a class from the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class, apply the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute> class, and then override the appropriate methods of the base class.</span></span> <span data-ttu-id="78217-116">Класс <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> реализует интерфейсы <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> и <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100>, а также предоставляет доступ к их методам для переопределения в пользовательском компоненте.</span><span class="sxs-lookup"><span data-stu-id="78217-116">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100> interfaces, and exposes their methods for you to override in your component.</span></span>  
  
 <span data-ttu-id="78217-117">В зависимости от объектов, используемых компонентом, для проекта могут потребоваться ссылки на некоторые (или все) из следующих сборок.</span><span class="sxs-lookup"><span data-stu-id="78217-117">Depending on the objects used by your component, your project will require references to some or all of the following assemblies:</span></span>  
  
|<span data-ttu-id="78217-118">Компонент</span><span class="sxs-lookup"><span data-stu-id="78217-118">Feature</span></span>|<span data-ttu-id="78217-119">Сборка для ссылки</span><span class="sxs-lookup"><span data-stu-id="78217-119">Assembly to reference</span></span>|<span data-ttu-id="78217-120">Пространство имен для импорта</span><span class="sxs-lookup"><span data-stu-id="78217-120">Namespace to import</span></span>|  
|-------------|---------------------------|-------------------------|  
|<span data-ttu-id="78217-121">Поток данных</span><span class="sxs-lookup"><span data-stu-id="78217-121">Data flow</span></span>|<span data-ttu-id="78217-122">Microsoft.SqlServer.PipelineHost</span><span class="sxs-lookup"><span data-stu-id="78217-122">Microsoft.SqlServer.PipelineHost</span></span>|<xref:Microsoft.SqlServer.Dts.Pipeline>|  
|<span data-ttu-id="78217-123">Оболочка потока данных</span><span class="sxs-lookup"><span data-stu-id="78217-123">Data flow wrapper</span></span>|<span data-ttu-id="78217-124">Microsoft.SqlServer.DTSPipelineWrap</span><span class="sxs-lookup"><span data-stu-id="78217-124">Microsoft.SqlServer.DTSPipelineWrap</span></span>|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper>|  
|<span data-ttu-id="78217-125">Параметры выполнения</span><span class="sxs-lookup"><span data-stu-id="78217-125">Runtime</span></span>|<span data-ttu-id="78217-126">Microsoft.SQLServer.ManagedDTS</span><span class="sxs-lookup"><span data-stu-id="78217-126">Microsoft.SQLServer.ManagedDTS</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime>|  
|<span data-ttu-id="78217-127">Оболочка среды выполнения</span><span class="sxs-lookup"><span data-stu-id="78217-127">Runtime wrapper</span></span>|<span data-ttu-id="78217-128">Microsoft.SqlServer.DTSRuntimeWrap</span><span class="sxs-lookup"><span data-stu-id="78217-128">Microsoft.SqlServer.DTSRuntimeWrap</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Wrapper>|  
  
 <span data-ttu-id="78217-129">В следующем примере кода показан простой компонент, который является производным от базового класса и применяет класс <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute>.</span><span class="sxs-lookup"><span data-stu-id="78217-129">The following code example shows a simple component that derives from the base class, and applies the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute>.</span></span> <span data-ttu-id="78217-130">Необходимо добавить ссылку на сборку DTSPipelineWrap.</span><span class="sxs-lookup"><span data-stu-id="78217-130">You need to add a reference to the DTSPipelineWrap assembly.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
  
namespace Microsoft.Samples.SqlServer.Dts  
{  
    [DtsPipelineComponent(DisplayName = "SampleComponent", ComponentType = ComponentType.Transform )]  
    public class BasicComponent: PipelineComponent  
    {  
        // TODO: Override the base class methods.  
    }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
<DtsPipelineComponent(DisplayName:="SampleComponent", ComponentType:=ComponentType.Transform)> _  
Public Class BasicComponent  
  
    Inherits PipelineComponent  
  
    ' TODO: Override the base class methods.  
  
End Class  
```  
  
<span data-ttu-id="78217-131">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="78217-131">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="78217-132">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="78217-132">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="78217-133">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="78217-133">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="78217-134">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="78217-134">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78217-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="78217-135">See Also</span></span>  
 [<span data-ttu-id="78217-136">Разработка пользовательского интерфейса для компонента потока данных</span><span class="sxs-lookup"><span data-stu-id="78217-136">Developing a User Interface for a Data Flow Component</span></span>](developing-a-user-interface-for-a-data-flow-component.md)  
  
  
