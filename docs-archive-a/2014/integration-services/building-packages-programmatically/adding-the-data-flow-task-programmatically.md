---
title: Добавление задачи потока данных программным образом | Документы Майкрософт
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
- adding Data Flow task
- SSIS data flow
- data flow task [Integration Services], adding
- MainPipe object
ms.assetid: 0ca03712-a82e-4aa7-949b-f869a8936ddf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4f7e699cc8e88bafb2a4508fdac8560fa73befe1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658362"
---
# <a name="adding-the-data-flow-task-programmatically"></a><span data-ttu-id="f3545-102">Добавление задачи потока данных программным образом</span><span class="sxs-lookup"><span data-stu-id="f3545-102">Adding the Data Flow Task Programmatically</span></span>
  <span data-ttu-id="f3545-103">Среда [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] включает задачу потока данных, представленную пространством имен <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper> в объектной модели.</span><span class="sxs-lookup"><span data-stu-id="f3545-103">[!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] includes a task called the Data Flow task, which is represented by the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper> namespace in the object model.</span></span> <span data-ttu-id="f3545-104">Задача потока данных — это специализированная высокопроизводительная задача, предназначенная для преобразования и перемещения данных во время выполнения пакета.</span><span class="sxs-lookup"><span data-stu-id="f3545-104">The Data Flow task is a specialized, high-performance task, dedicated to transforming and moving data during package execution.</span></span> <span data-ttu-id="f3545-105">Как и другие задачи, задача потока данных упакована в объект <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, и с точки зрения подсистемы выполнения эта задача является просто одной из задач в пакете.</span><span class="sxs-lookup"><span data-stu-id="f3545-105">Like other tasks, the Data Flow task is wrapped by the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> object, and from the perspective of the run-time engine, this task is just another task in the package.</span></span> <span data-ttu-id="f3545-106">Однако поток данных содержит дополнительные объекты, называемые компонентами потока данных.</span><span class="sxs-lookup"><span data-stu-id="f3545-106">However, the data flow contains additional objects called data flow components.</span></span> <span data-ttu-id="f3545-107">Эти компоненты выполняют перемещение данных из источника в место назначения, иногда посредством преобразования.</span><span class="sxs-lookup"><span data-stu-id="f3545-107">These components are the components that make data move from a source to a destination, sometimes through a transformation.</span></span> <span data-ttu-id="f3545-108">Эти компоненты определяют направление перемещения и способ преобразования данных.</span><span class="sxs-lookup"><span data-stu-id="f3545-108">The components define both the direction of movement and how data is transformed.</span></span> <span data-ttu-id="f3545-109">Настройка задачи потока данных включает добавление компонентов в задачу, а затем их соединение для установления потока данных и выполнения требуемого преобразования.</span><span class="sxs-lookup"><span data-stu-id="f3545-109">Configuring the Data Flow task involves adding components to the task, and then connecting them to establish the flow of data and achieve the intended transformation.</span></span>  
  
 <span data-ttu-id="f3545-110">В задаче потока данных имеются компоненты трех типов: **Источники потока данных**, **Преобразования потока данных** и **Назначения потока данных**, которые отображаются в этом порядке на панели элементов конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3545-110">There are three types of components within a Data Flow task: **Data Flow Sources**, **Data Flow Transformations**, and **Data Flow Destinations**, shown in that order within the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer toolbox.</span></span> <span data-ttu-id="f3545-111">Эти типы также называются просто источниками, преобразованиями и назначениями.</span><span class="sxs-lookup"><span data-stu-id="f3545-111">These types are also referred to more simply as sources, transformations, or destinations.</span></span> <span data-ttu-id="f3545-112">Как видно из имен, поток данных направляется из источника в компонент преобразования, а затем назначению.</span><span class="sxs-lookup"><span data-stu-id="f3545-112">As implied by the names, data flows from a source to a transformation, and then to a destination.</span></span> <span data-ttu-id="f3545-113">Это простое описание потока данных, иллюстрирующее понятие, но задача потока данных является достаточно гибкой и мощной для обработки нескольких источников и объединения нескольких преобразований, отправляющих выходные данные нескольким назначениям.</span><span class="sxs-lookup"><span data-stu-id="f3545-113">This is a simplistic description of the data flow to illustrate the concept, but the Data Flow task is flexible and powerful enough to handle multiple sources, and to connect together many transformations that send output to multiple destinations.</span></span>  
  
 <span data-ttu-id="f3545-114">Задача потока данных добавляется в пакет так же, как и другие задачи.</span><span class="sxs-lookup"><span data-stu-id="f3545-114">The Data Flow task is added to a package the same way other tasks are added.</span></span> <span data-ttu-id="f3545-115">После добавления задачи она настраивается путем добавления компонентов в задачу потока данных, настройки и соединения компонентов в задаче.</span><span class="sxs-lookup"><span data-stu-id="f3545-115">After the task has been added, it is configured by adding components to the data flow task, and configuring and connecting components in the task.</span></span>  
  
## <a name="sample"></a><span data-ttu-id="f3545-116">Образец</span><span class="sxs-lookup"><span data-stu-id="f3545-116">Sample</span></span>  
 <span data-ttu-id="f3545-117">В следующем образце кода показан способ добавления задачи потока данных в пакет.</span><span class="sxs-lookup"><span data-stu-id="f3545-117">The following code sample shows how to add a Data Flow task to a package.</span></span> <span data-ttu-id="f3545-118">Этот пример требует наличия ссылок на сборки Microsoft.SqlServer.PipelineHost, Microsoft.SqlServer.DTSPipelineWrap и Microsoft.SqlServer.ManagedDTS.</span><span class="sxs-lookup"><span data-stu-id="f3545-118">This example requires a reference to the assemblies Microsoft.SqlServer.PipelineHost, Microsoft.SqlServer.DTSPipelineWrap, and Microsoft.SqlServer.ManagedDTS.</span></span>  
  
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
      Package p = new Package();  
      Executable e = p.Executables.Add("STOCK:PipelineTask");  
      TaskHost thMainPipe = e as TaskHost;  
      MainPipe dataFlowTask = thMainPipe.InnerObject as MainPipe;   
    }  
  }  
}  
```  
  
```vb  
Imports System.IO  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
Module Module1  
  
  Sub Main()  
  
    Dim p As Package = New Package()  
    Dim e As Executable = p.Executables.Add("STOCK:PipelineTask")  
    Dim thMainPipe As TaskHost = CType(e, TaskHost)  
    Dim dataFlowTask As MainPipe = CType(thMainPipe.InnerObject, MainPipe)  
  
  End Sub  
  
End Module  
```  
  
## <a name="external-resources"></a><span data-ttu-id="f3545-119">Внешние ресурсы</span><span class="sxs-lookup"><span data-stu-id="f3545-119">External Resources</span></span>  
 <span data-ttu-id="f3545-120">Запись в блоге [EzAPI — обновление для SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223) на сайте blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="f3545-120">Blog entry, [EzAPI - Updated for SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223), on blogs.msdn.com.</span></span>  
  
<span data-ttu-id="f3545-121">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="f3545-121">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="f3545-122">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="f3545-122">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="f3545-123">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="f3545-123">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="f3545-124">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="f3545-124">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3545-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="f3545-125">See Also</span></span>  
 [<span data-ttu-id="f3545-126">Программный поиск компонентов потока данных</span><span class="sxs-lookup"><span data-stu-id="f3545-126">Discovering Data Flow Components Programmatically</span></span>](../building-packages-programmatically/discovering-data-flow-components-programmatically.md)  
  
  
