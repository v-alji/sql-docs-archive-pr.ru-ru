---
title: Программное обнаружение компонентов потока данных | Документы Майкрософт
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
- PipelineComponentInfos collection
- data flow task [Integration Services], components
- discovering data flow components
- components [Integration Services], data flow
- data flow [Integration Services], components
ms.assetid: ff92a96a-8af6-4532-82cc-c0bbff92401b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a18102f38f1ad06e918efe2ca529185d40deef9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731973"
---
# <a name="discovering-data-flow-components-programmatically"></a><span data-ttu-id="4ad2d-102">Программный поиск компонентов потока данных</span><span class="sxs-lookup"><span data-stu-id="4ad2d-102">Discovering Data Flow Components Programmatically</span></span>
  <span data-ttu-id="4ad2d-103">После добавления задачи потока данных в пакет может возникнуть необходимость определить, какие компоненты потока данных доступны для использования.</span><span class="sxs-lookup"><span data-stu-id="4ad2d-103">After you have added a data flow task to a package, your next step may be to determine what data flow components are available for your use.</span></span> <span data-ttu-id="4ad2d-104">Можно программным способом выявить источники, преобразования и назначения потока данных, установленные и доступные на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="4ad2d-104">You can programmatically discover the data flow sources, transformations, and destinations that are installed and available on the local computer.</span></span> <span data-ttu-id="4ad2d-105">Сведения о добавлении задачи потока данных в пакет см. в разделе [Добавление задачи потока данных программным образом](../building-packages-programmatically/adding-the-data-flow-task-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="4ad2d-105">For information about adding a data flow task to the package, see [Adding the Data Flow Task Programmatically](../building-packages-programmatically/adding-the-data-flow-task-programmatically.md).</span></span>  
  
## <a name="discovering-components"></a><span data-ttu-id="4ad2d-106">Поиск компонентов</span><span class="sxs-lookup"><span data-stu-id="4ad2d-106">Discovering Components</span></span>  
 <span data-ttu-id="4ad2d-107">Класс <xref:Microsoft.SqlServer.Dts.Runtime.Application> предоставляет коллекцию <xref:Microsoft.SqlServer.Dts.Runtime.Application.PipelineComponentInfos%2A>, содержащую объект <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo> для каждого компонента, правильно установленного на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="4ad2d-107">The <xref:Microsoft.SqlServer.Dts.Runtime.Application> class provides the <xref:Microsoft.SqlServer.Dts.Runtime.Application.PipelineComponentInfos%2A> collection, which contains a <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo> object for each component correctly installed on the local computer.</span></span> <span data-ttu-id="4ad2d-108">Каждый объект <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo> содержит сведения о компоненте, в частности, его имя, описание и время создания.</span><span class="sxs-lookup"><span data-stu-id="4ad2d-108">Each <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo> contains information about a component such as its name, description, and creation name.</span></span> <span data-ttu-id="4ad2d-109">Можно использовать значение, возвращаемое в свойстве <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo.CreationName%2A>, чтобы задать свойство <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A><xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> при добавлении компонента в пакет.</span><span class="sxs-lookup"><span data-stu-id="4ad2d-109">You can use the value returned in the <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo.CreationName%2A> property to set the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> property of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> when you add a component to a package.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="4ad2d-110">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="4ad2d-110">Next Step</span></span>  
 <span data-ttu-id="4ad2d-111">Следующим шагом после выявления доступных компонентов является добавление и настройка компонентов, которые рассматриваются в следующем разделе [Добавление компонентов потока данных программным образом](../building-packages-programmatically/adding-data-flow-components-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="4ad2d-111">After discovering available components, the next step is to add and configure the components, which is discussed in the next topic, [Adding Data Flow Components Programmatically](../building-packages-programmatically/adding-data-flow-components-programmatically.md).</span></span>  
  
## <a name="sample"></a><span data-ttu-id="4ad2d-112">Образец</span><span class="sxs-lookup"><span data-stu-id="4ad2d-112">Sample</span></span>  
 <span data-ttu-id="4ad2d-113">В следующем образце кода показано, как перечислить коллекцию <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfos> объекта <xref:Microsoft.SqlServer.Dts.Runtime.Application>, чтобы программным способом определить компоненты потока данных, доступные на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="4ad2d-113">The following code sample shows how to enumerate the <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfos> collection of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> object to programmatically discover the data flow components available on the local computer.</span></span> <span data-ttu-id="4ad2d-114">В этом примере необходима ссылка на сборку Microsoft.SqlServer.ManagedDTS.</span><span class="sxs-lookup"><span data-stu-id="4ad2d-114">This sample requires a reference to the Microsoft.SqlServer.ManagedDTS assembly.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Application application = new Application();  
      PipelineComponentInfos componentInfos = application.PipelineComponentInfos;  
  
      foreach (PipelineComponentInfo componentInfo in componentInfos)  
      {  
        Console.WriteLine("Name: " + componentInfo.Name + "\n" +  
          " CreationName: " + componentInfo.CreationName + "\n");  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim application As Application = New Application()  
  
    Dim componentInfos As PipelineComponentInfos = application.PipelineComponentInfos  
  
    For Each componentInfo As PipelineComponentInfo In componentInfos  
      Console.WriteLine("Name: " & componentInfo.Name & vbCrLf & _  
        " CreationName: " & componentInfo.CreationName & vbCrLf)  
    Next  
  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
<span data-ttu-id="4ad2d-115">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="4ad2d-115">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="4ad2d-116">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="4ad2d-116">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="4ad2d-117">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="4ad2d-117">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="4ad2d-118">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="4ad2d-118">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ad2d-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="4ad2d-119">See Also</span></span>  
 [<span data-ttu-id="4ad2d-120">Добавление компонентов потока данных программным образом</span><span class="sxs-lookup"><span data-stu-id="4ad2d-120">Adding Data Flow Components Programmatically</span></span>](../building-packages-programmatically/adding-data-flow-components-programmatically.md)  
  
  
