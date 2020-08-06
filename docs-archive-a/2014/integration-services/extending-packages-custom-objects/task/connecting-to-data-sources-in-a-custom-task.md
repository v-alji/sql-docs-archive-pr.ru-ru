---
title: Соединение с источниками данных в пользовательской задаче | Документы Майкрософт
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
- ConnectionManager objects
- connection managers [Integration Services], external data sources
- data sources [Integration Services], external
- custom tasks [Integration Services], external data sources
- external data sources [Integration Services]
- connections [Integration Services], external data sources
- SSIS custom tasks, external data sources
ms.assetid: 9f0b3a43-3eaa-4b3c-bb08-29b630c11306
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 71c504f4b528a0c9809d00de74de4beb9c67c4f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665444"
---
# <a name="connecting-to-data-sources-in-a-custom-task"></a><span data-ttu-id="4e684-102">Соединение с источниками данных в пользовательской задаче</span><span class="sxs-lookup"><span data-stu-id="4e684-102">Connecting to Data Sources in a Custom Task</span></span>
  <span data-ttu-id="4e684-103">Чтобы получить или сохранить данные, задачи соединяются с внешними источниками данных с помощью диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="4e684-103">Tasks connect to external data sources to retrieve or save data by using a connection manager.</span></span> <span data-ttu-id="4e684-104">Во время разработки диспетчер соединений представляет логическое соединение и описывает основные сведения, например имя сервера и любые свойства проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="4e684-104">At design time, a connection manager represents a logical connection, and describes key information such as the server name and any authentication properties.</span></span> <span data-ttu-id="4e684-105">Во время выполнения задачи вызывают метод <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> диспетчера соединений, чтобы установить физическое соединение с источником данных.</span><span class="sxs-lookup"><span data-stu-id="4e684-105">At run time, tasks call the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method of the connection manager to establish the physical connection to the data source.</span></span>  
  
 <span data-ttu-id="4e684-106">Поскольку пакет может содержать множество задач, каждая из которых может иметь соединения с различными источниками данных, пакет отслеживает все диспетчеры соединений в коллекции <xref:Microsoft.SqlServer.Dts.Runtime.Connections>.</span><span class="sxs-lookup"><span data-stu-id="4e684-106">Because a package can contain many tasks, each of which may have connections to different data sources, the package tracks all the connection managers in a collection, the <xref:Microsoft.SqlServer.Dts.Runtime.Connections> collection.</span></span> <span data-ttu-id="4e684-107">Задачи используют коллекцию в своем пакете для поиска диспетчера соединений, который они смогут использовать во время проверки и выполнения.</span><span class="sxs-lookup"><span data-stu-id="4e684-107">Tasks use the collection in their package to find the connection manager that they will use during validation and execution.</span></span> <span data-ttu-id="4e684-108">Коллекция <xref:Microsoft.SqlServer.Dts.Runtime.Connections> является первым параметром для методов <xref:Microsoft.SqlServer.Dts.Runtime.Task.Validate%2A> и <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="4e684-108">The <xref:Microsoft.SqlServer.Dts.Runtime.Connections> collection is the first parameter to the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Validate%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> methods.</span></span>  
  
 <span data-ttu-id="4e684-109">Можно предотвратить использование задачи неподходящего диспетчера соединений, отобразив для пользователя объекты <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> из коллекции с помощью диалогового окна или раскрывающегося списка в графическом пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="4e684-109">You can prevent the task from using the wrong connection manager by displaying the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects from the collection to the user, by using a dialog box or drop-down list in the graphical user interface.</span></span> <span data-ttu-id="4e684-110">При этом пользователь получит возможность выбирать только из числа тех объектов <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>, которые относятся к подходящему типу и содержатся в пакете.</span><span class="sxs-lookup"><span data-stu-id="4e684-110">This gives the user a way to select from among only those <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects of the appropriate type that are contained in the package.</span></span>  
  
 <span data-ttu-id="4e684-111">Задачи вызывают метод <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A>, чтобы установить физическое соединение с источником данных.</span><span class="sxs-lookup"><span data-stu-id="4e684-111">Tasks call the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method to establish the physical connection to the data source.</span></span> <span data-ttu-id="4e684-112">Метод возвращает объект базового соединения, который может быть использован задачей.</span><span class="sxs-lookup"><span data-stu-id="4e684-112">The method returns the underlying connection object that can then be used by the task.</span></span> <span data-ttu-id="4e684-113">Поскольку диспетчер соединений изолирует сведения об объекте базового соединения от задачи, задача должна лишь вызвать метод <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A>, чтобы установить соединение; при этом нет необходимости заботиться о других аспектах соединения.</span><span class="sxs-lookup"><span data-stu-id="4e684-113">Because the connection manager isolates the implementation details of the underlying connection object from the task, the task only has to call the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method to establish the connection, and does not have to be concerned with other aspects of the connection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e684-114">Пример</span><span class="sxs-lookup"><span data-stu-id="4e684-114">Example</span></span>  
 <span data-ttu-id="4e684-115">В следующем образце кода демонстрируется проверка имени <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> в методах Validate и Execute, а также показано, как использовать метод <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A>, чтобы установить физическое соединение в методе Execute.</span><span class="sxs-lookup"><span data-stu-id="4e684-115">The following sample code demonstrates validation of the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> name in the Validate and Execute methods, and shows how to use the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method to establish the physical connection in the Execute method.</span></span>  
  
```csharp  
private string connectionManagerName = "";  
  
public string ConnectionManagerName  
{  
  get { return this.connectionManagerName; }  
  set { this.connectionManagerName = value; }  
}  
  
public override DTSExecResult Validate(  
  Connections connections, VariableDispenser variableDispenser,  
  IDTSComponentEvents componentEvents, IDTSLogging log)  
{  
  // If the connection manager exists, validation is successful;  
  // otherwise, fail validation.  
  try  
  {  
    ConnectionManager cm = connections[this.connectionManagerName];  
    return DTSExecResult.Success;  
  }  
  catch (System.Exception e)  
  {  
    componentEvents.FireError(0, "SampleTask", "Invalid connection manager.", "", 0);  
    return DTSExecResult.Failure;  
  }  
}  
  
public override DTSExecResult Execute(Connections connections,   
  VariableDispenser variableDispenser, IDTSComponentEvents componentEvents,   
  IDTSLogging log, object transaction)  
{  
  try  
  {  
    ConnectionManager cm = connections[this.connectionManagerName];  
    object connection = cm.AcquireConnection(transaction);  
    return DTSExecResult.Success;  
  }  
  catch (System.Exception exception)  
  {  
    componentEvents.FireError(0, "SampleTask", exception.Message, "", 0);  
    return DTSExecResult.Failure;  
  }  
}  
```  
  
```vb  
Private _connectionManagerName As String = ""  
  
Public Property ConnectionManagerName() As String  
  Get  
    Return Me._connectionManagerName  
  End Get  
  Set(ByVal Value As String)  
    Me._connectionManagerName = value  
  End Set  
End Property  
  
Public Overrides Function Validate( _  
  ByVal connections As Microsoft.SqlServer.Dts.Runtime.Connections, _  
  ByVal variableDispenser As Microsoft.SqlServer.Dts.Runtime.VariableDispenser, _  
  ByVal componentEvents As Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents, _  
  ByVal log As Microsoft.SqlServer.Dts.Runtime.IDTSLogging) _  
  As Microsoft.SqlServer.Dts.Runtime.DTSExecResult  
  
  ' If the connection manager exists, validation is successful;  
  ' otherwise fail validation.  
  Try  
    Dim cm As ConnectionManager = connections(Me._connectionManagerName)  
    Return DTSExecResult.Success  
  Catch e As System.Exception  
    componentEvents.FireError(0, "SampleTask", "Invalid connection manager.", "", 0)  
    Return DTSExecResult.Failure  
  End Try  
  
End Function  
  
Public Overrides Function Execute( _  
  ByVal connections As Microsoft.SqlServer.Dts.Runtime.Connections, _  
  ByVal variableDispenser As Microsoft.SqlServer.Dts.Runtime.VariableDispenser, _  
  ByVal componentEvents As Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents, _  
  ByVal log As Microsoft.SqlServer.Dts.Runtime.IDTSLogging, ByVal transaction As Object) _  
  As Microsoft.SqlServer.Dts.Runtime.DTSExecResult  
  
  Try  
    Dim cm As ConnectionManager = connections(Me._connectionManagerName)  
    Dim connection As Object = cm.AcquireConnection(transaction)  
    Return DTSExecResult.Success  
  Catch exception As System.Exception  
    componentEvents.FireError(0, "SampleTask", exception.Message, "", 0)  
    Return DTSExecResult.Failure  
  End Try  
  
End Function  
```  
  
<span data-ttu-id="4e684-116">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="4e684-116">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="4e684-117">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="4e684-117">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="4e684-118">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="4e684-118">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="4e684-119">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="4e684-119">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e684-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="4e684-120">See Also</span></span>  
 <span data-ttu-id="4e684-121">[Integration Services &#40;соединений&#41; SSIS](../../connection-manager/integration-services-ssis-connections.md) </span><span class="sxs-lookup"><span data-stu-id="4e684-121">[Integration Services &#40;SSIS&#41; Connections](../../connection-manager/integration-services-ssis-connections.md) </span></span>  
 [<span data-ttu-id="4e684-122">Создание диспетчеров соединений</span><span class="sxs-lookup"><span data-stu-id="4e684-122">Create Connection Managers</span></span>](../../create-connection-managers.md)  
  
  
