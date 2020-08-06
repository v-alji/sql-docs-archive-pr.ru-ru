---
title: Создание кода пользовательского регистратора | Документы Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom log providers [Integration Services], coding
ms.assetid: 979a29ca-956e-4fdd-ab47-f06e84cead7a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5d529420207ac065ae5ecb3c1d984de3021845b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732742"
---
# <a name="coding-a-custom-log-provider"></a><span data-ttu-id="4f0ee-102">Создание кода пользовательского регистратора</span><span class="sxs-lookup"><span data-stu-id="4f0ee-102">Coding a Custom Log Provider</span></span>
  <span data-ttu-id="4f0ee-103">После создания класса, наследующего от базового класса <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase>, и применения к нему атрибута <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute>, необходимо переопределить реализацию свойств и методов базового класса, чтобы обеспечить пользовательские функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-103">After you have created a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase> base class, and applied the <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute> attribute to the class, you must override the implementation of the properties and methods of the base class to provide your custom functionality.</span></span>  
  
 <span data-ttu-id="4f0ee-104">Примеры пользовательских регистраторов см. в разделе [Разработка пользовательского интерфейса для пользовательского регистратора](developing-a-user-interface-for-a-custom-log-provider.md).</span><span class="sxs-lookup"><span data-stu-id="4f0ee-104">For working samples of custom log providers, see [Developing a User Interface for a Custom Log Provider](developing-a-user-interface-for-a-custom-log-provider.md).</span></span>  
  
## <a name="configuring-the-log-provider"></a><span data-ttu-id="4f0ee-105">Настройка регистратора</span><span class="sxs-lookup"><span data-stu-id="4f0ee-105">Configuring the Log Provider</span></span>  
  
### <a name="initializing-the-log-provider"></a><span data-ttu-id="4f0ee-106">Инициализация регистратора</span><span class="sxs-lookup"><span data-stu-id="4f0ee-106">Initializing the Log Provider</span></span>  
 <span data-ttu-id="4f0ee-107">Необходимо переопределить метод <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.InitializeLogProvider%2A> для кэширования ссылок на коллекцию соединений и интерфейс событий.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-107">You override the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.InitializeLogProvider%2A> method to cache references to the connections collection and the events interface.</span></span> <span data-ttu-id="4f0ee-108">В дальнейшем можно использовать эти кэшированные ссылки в других методах регистратора.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-108">You can use these cached references later in other methods of the log provider.</span></span>  
  
### <a name="using-the-configstring-property"></a><span data-ttu-id="4f0ee-109">Использование свойства ConfigString</span><span class="sxs-lookup"><span data-stu-id="4f0ee-109">Using the ConfigString Property</span></span>  
 <span data-ttu-id="4f0ee-110">Во время разработки регистратор получает данные конфигурации из столбца **Конфигурация**.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-110">At design time, a log provider receives configuration information from the **Configuration** column.</span></span> <span data-ttu-id="4f0ee-111">Эти данные конфигурации соответствуют свойству <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> регистратора.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-111">This configuration information corresponds to the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> property of the log provider.</span></span> <span data-ttu-id="4f0ee-112">По умолчанию этот столбец содержит текстовое поле, из которого можно получить любые строковые данные.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-112">By default, this column contains a text box from which you can retrieve any string information.</span></span> <span data-ttu-id="4f0ee-113">Большинство регистраторов, включенных в службы [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], используют это свойство для хранения имени диспетчера соединений, которое регистратор применяет для соединения с внешним источником данных.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-113">Most of the log providers included with [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] use this property to store the name of the connection manager that the provider uses to connect to an external data source.</span></span> <span data-ttu-id="4f0ee-114">Если выбранный регистратор использует свойство <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A>, используйте метод <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A>, чтобы проверить это свойство и убедиться, что оно имеет правильное значение.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-114">If your log provider uses the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> property, use the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> method to validate this property and make sure that the property is set correctly.</span></span>  
  
### <a name="validating-the-log-provider"></a><span data-ttu-id="4f0ee-115">Проверка регистратора</span><span class="sxs-lookup"><span data-stu-id="4f0ee-115">Validating the Log Provider</span></span>  
 <span data-ttu-id="4f0ee-116">Необходимо переопределить метод <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A>, чтобы убедиться в правильности настройки регистратора и его готовности к выполнению.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-116">You override the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> method to make sure that the provider has been configured correctly and is ready for execution.</span></span> <span data-ttu-id="4f0ee-117">Обычно, чтобы убедиться в правильности настройки <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A>, требуется минимальный уровень проверки.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-117">Typically, a minimum level of validation is to make sure that the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> is set correctly.</span></span> <span data-ttu-id="4f0ee-118">Выполнение не может продолжиться, пока регистратор не возвратит значение <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Success> из метода <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-118">Execution cannot continue until the log provider returns <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Success> from the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> method.</span></span>  
  
 <span data-ttu-id="4f0ee-119">В следующем примере кода демонстрируется реализация метода <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A>, которая проверяет, что имя диспетчера соединений указано, что диспетчер соединений существует в пакете и что диспетчер соединений возвращает имя файла в свойстве <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A>.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-119">The following code example shows an implementation of <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> that makes sure that the name of a connection manager name is specified, that the connection manager exists in the package, and that the connection manager returns a file name in the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> property.</span></span>  
  
```csharp  
public override DTSExecResult Validate(IDTSInfoEvents infoEvents)  
{  
    if (this.ConfigString.Length == 0 || connections.Contains(ConfigString) == false)  
    {  
        infoEvents.FireError(0, "MyTextLogProvider", "The ConnectionManager " + ConfigString + " specified in the ConfigString property cannot be found in the collection.", "", 0);  
        return DTSExecResult.Failure;  
    }  
    else  
    {  
        string fileName = connections[ConfigString].AcquireConnection(null) as string;  
  
        if (fileName == null || fileName.Length == 0)  
        {  
            infoEvents.FireError(0, "MyTextLogProvider", "The ConnectionManager " + ConfigString + " specified in the ConfigString property cannot be found in the collection.", "", 0);  
            return DTSExecResult.Failure;  
        }  
    }  
    return DTSExecResult.Success;  
}  
```  
  
```vb  
Public Overrides Function Validate(ByVal infoEvents As IDTSInfoEvents) As DTSExecResult  
    If Me.ConfigString.Length = 0 Or connections.Contains(ConfigString) = False Then  
        infoEvents.FireError(0, "MyTextLogProvider", "The ConnectionManager " + ConfigString + " specified in the ConfigString property cannot be found in the collection.", "", 0)  
        Return DTSExecResult.Failure  
    Else   
        Dim fileName As String =  connections(ConfigString).AcquireConnectionCType(as string, Nothing)  
  
        If fileName = Nothing Or fileName.Length = 0 Then  
            infoEvents.FireError(0, "MyTextLogProvider", "The ConnectionManager " + ConfigString + " specified in the ConfigString property cannot be found in the collection.", "", 0)  
            Return DTSExecResult.Failure  
        End If  
    End If  
    Return DTSExecResult.Success  
End Function  
```  
  
### <a name="persisting-the-log-provider"></a><span data-ttu-id="4f0ee-120">Сохраняемость регистратора</span><span class="sxs-lookup"><span data-stu-id="4f0ee-120">Persisting the Log Provider</span></span>  
 <span data-ttu-id="4f0ee-121">Как правило, нет необходимости реализовывать пользовательский механизм сохраняемости для диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-121">Ordinarily you do not have to implement custom persistence for a connection manager.</span></span> <span data-ttu-id="4f0ee-122">Нестандартный механизм сохраняемости необходим только в случае, когда свойства объекта используют сложные типы данных.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-122">Custom persistence is required only when the properties of an object use complex data types.</span></span> <span data-ttu-id="4f0ee-123">Дополнительные сведения см. в разделе [Разработка пользовательских объектов для служб Integration Services](../developing-custom-objects-for-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="4f0ee-123">For more information, see [Developing Custom Objects for Integration Services](../developing-custom-objects-for-integration-services.md).</span></span>  
  
## <a name="logging-with-the-log-provider"></a><span data-ttu-id="4f0ee-124">Ведение журнала с помощью регистратора</span><span class="sxs-lookup"><span data-stu-id="4f0ee-124">Logging with the Log Provider</span></span>  
 <span data-ttu-id="4f0ee-125">Существуют три метода времени выполнения, которые должны быть переопределены всеми регистраторами: <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> и <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A></span><span class="sxs-lookup"><span data-stu-id="4f0ee-125">There are three run-time methods that must be overridden by all log providers: <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A>, and <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A>.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4f0ee-126">Во время проверки и выполнения одного пакета методы <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A> и <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> вызываются более одного раза.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-126">During the validation and execution of a single package, the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> methods are called more than one time.</span></span> <span data-ttu-id="4f0ee-127">Убедитесь, что пользовательский код не приведет к перезаписи более ранних записей журнала при следующем открытии и закрытии журнала.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-127">Make sure that your custom code does not cause earlier log entries to be overwritten by the next opening and closing of the log.</span></span> <span data-ttu-id="4f0ee-128">Если была выбрана регистрация событий проверки в тестовом пакете, первым зарегистрированным событием должно быть событие OnPreValidate. Если вместо него первым событием в журнале отображается PackageStart, начальные события проверки были перезаписаны.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-128">If you have selected to log validation events in your test package, the first logged event that you should see is OnPreValidate; if instead the first logged event that you see is PackageStart, the initial validation events have been overwritten.</span></span>  
  
### <a name="opening-the-log"></a><span data-ttu-id="4f0ee-129">Открытие журнала</span><span class="sxs-lookup"><span data-stu-id="4f0ee-129">Opening the Log</span></span>  
 <span data-ttu-id="4f0ee-130">Большинство регистраторов соединяются с внешним источником данных, например с файлом или базой данных, чтобы сохранять данные событий, которые собираются в ходе выполнения пакета.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-130">Most log providers connect to an external data source, such as a file or database, to store the event information that is collected during package execution.</span></span> <span data-ttu-id="4f0ee-131">Как и в случае с любым другим объектом в среде выполнения, соединение с внешним источником данных обычно устанавливается с помощью объектов диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-131">As with any other object in the runtime, connecting to the external data source is typically accomplished by using connection manager objects.</span></span>  
  
 <span data-ttu-id="4f0ee-132">Метод <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A> вызывается в начале выполнения пакета. Переопределите этот метод, чтобы установить соединение с внешним источником данных.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-132">The <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A> method is called at the start of package execution.Override this method to establish a connection to the external data source.</span></span>  
  
 <span data-ttu-id="4f0ee-133">В следующем образце кода демонстрируется регистратор, который открывает текстовый файл для записи во время выполнения метода <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-133">The following sample code shows a log provider that opens a text file for writing during <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>.</span></span> <span data-ttu-id="4f0ee-134">Файл открывается путем вызова метода <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> диспетчера соединений, который был указан в свойстве <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A>.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-134">It opens the file by calling the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method of the connection manager that was specified in the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> property.</span></span>  
  
```csharp  
public override void OpenLog()  
{  
    if(!this.connections.Contains(this.ConfigString))  
        throw new Exception("The ConnectionManager " + this.ConfigString + " does not exist in the Connections collection.");  
  
    this.connectionManager = connections[ConfigString];  
    string filePath = this.connectionManager.AcquireConnection(null) as string;  
  
    if(filePath == null || filePath.Length == 0)  
        throw new Exception("The ConnectionManager " + this.ConfigString + " is not a valid FILE ConnectionManager");  
  
    //  Create a StreamWriter to append to.  
    sw = new StreamWriter(filePath,true);  
  
    sw.WriteLine("Open log" + System.DateTime.Now.ToShortTimeString());  
}  
```  
  
```vb  
Public Overrides  Sub OpenLog()  
    If Not Me.connections.Contains(Me.ConfigString) Then  
        Throw New Exception("The ConnectionManager " + Me.ConfigString + " does not exist in the Connections collection.")  
    End If  
  
    Me.connectionManager = connections(ConfigString)  
    Dim filePath As String =  Me.connectionManager.AcquireConnectionCType(as string, Nothing)  
  
    If filePath = Nothing Or filePath.Length = 0 Then  
        Throw New Exception("The ConnectionManager " + Me.ConfigString + " is not a valid FILE ConnectionManager")  
    End If  
  
    '  Create a StreamWriter to append to.  
    sw = New StreamWriter(filePath,True)  
  
    sw.WriteLine("Open log" + System.DateTime.Now.ToShortTimeString())  
End Sub  
```  
  
### <a name="writing-log-entries"></a><span data-ttu-id="4f0ee-135">Создание записей журнала</span><span class="sxs-lookup"><span data-stu-id="4f0ee-135">Writing Log Entries</span></span>  
 <span data-ttu-id="4f0ee-136">Метод <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> вызывается каждый раз, когда объект в пакете инициирует событие путем вызова метода Fire\<event> для одного из интерфейсов события.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-136">The <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> method is called every time that an object in the package raises an event by calling a Fire\<event> method on one of the event interfaces.</span></span> <span data-ttu-id="4f0ee-137">Каждое событие инициируется со сведениями о его контексте и обычно дополняется поясняющим сообщением.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-137">Each event is raised with information about its context and usually an explanatory message.</span></span> <span data-ttu-id="4f0ee-138">Однако не каждый вызов метода <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> включает сведения о каждом параметре метода.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-138">However, not every call to the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> method includes information for every method parameter.</span></span> <span data-ttu-id="4f0ee-139">Например, некоторые стандартные события, имена которых очевидны без пояснений, не предоставляют параметров MessageText, а параметры DataCode и DataBytes предназначены для необязательных вспомогательных сведений.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-139">For example, some standard events whose names are self-explanatory do not provide MessageText, and DataCode and DataBytes are intended for optional supplemental information.</span></span>  
  
 <span data-ttu-id="4f0ee-140">В следующем примере кода реализуется метод <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> и события записываются в поток, открытый в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-140">The following code example implements the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> method, and writes the events to the stream that was opened in the previous section.</span></span>  
  
```csharp  
public override void Log(string logEntryName, string computerName, string operatorName, string sourceName, string sourceID, string executionID, string messageText, DateTime startTime, DateTime endTime, int dataCode, byte[] dataBytes)  
{  
    sw.Write(logEntryName + ",");  
    sw.Write(computerName + ",");  
    sw.Write(operatorName + ",");  
    sw.Write(sourceName + ",");  
    sw.Write(sourceID + ",");  
    sw.Write(messageText + ",");  
    sw.Write(dataBytes + ",");  
    sw.WriteLine("");  
}  
```  
  
```vb  
Public Overrides  Sub Log(ByVal logEnTryName As String, ByVal computerName As String, ByVal operatorName As String, ByVal sourceName As String, ByVal sourceID As String, ByVal executionID As String, ByVal messageText As String, ByVal startTime As DateTime, ByVal endTime As DateTime, ByVal dataCode As Integer, ByVal dataBytes() As Byte)  
    sw.Write(logEnTryName + ",")  
    sw.Write(computerName + ",")  
    sw.Write(operatorName + ",")  
    sw.Write(sourceName + ",")  
    sw.Write(sourceID + ",")  
    sw.Write(messageText + ",")  
    sw.Write(dataBytes + ",")  
    sw.WriteLine("")  
End Sub  
```  
  
### <a name="closing-the-log"></a><span data-ttu-id="4f0ee-141">Закрытие журнала</span><span class="sxs-lookup"><span data-stu-id="4f0ee-141">Closing the Log</span></span>  
 <span data-ttu-id="4f0ee-142">Метод <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> вызывается в конце выполнения пакета, после того как все объекты в пакете завершили выполнение (либо если выполнение пакета остановлено в связи с ошибками).</span><span class="sxs-lookup"><span data-stu-id="4f0ee-142">The <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> method is called at the end of package execution, after all the objects in the package have completed execution, or, when the package stops because of errors.</span></span>  
  
 <span data-ttu-id="4f0ee-143">В следующем примере кода демонстрируется реализация метода <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A>, которая закрывает файловый поток, открытый при выполнении метода <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-143">The following code example demonstrates an implementation of the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> method that closes the file stream that was opened during the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A> method.</span></span>  
  
```csharp  
public override void CloseLog()  
{  
    if (sw != null)  
    {  
        sw.WriteLine("Close log" + System.DateTime.Now.ToShortTimeString());  
        sw.Close();  
    }  
}  
```  
  
```vb  
Public Overrides  Sub CloseLog()  
    If Not sw Is Nothing Then  
        sw.WriteLine("Close log" + System.DateTime.Now.ToShortTimeString())  
        sw.Close()  
    End If  
End Sub  
```  
  
<span data-ttu-id="4f0ee-144">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="4f0ee-144">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="4f0ee-145">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="4f0ee-145">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="4f0ee-146">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="4f0ee-146">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="4f0ee-147">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-147">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f0ee-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="4f0ee-148">See Also</span></span>  
 <span data-ttu-id="4f0ee-149">[Создание пользовательского регистратора](creating-a-custom-log-provider.md) </span><span class="sxs-lookup"><span data-stu-id="4f0ee-149">[Creating a Custom Log Provider](creating-a-custom-log-provider.md) </span></span>  
 [<span data-ttu-id="4f0ee-150">Разработка пользовательского интерфейса для пользовательского регистратора</span><span class="sxs-lookup"><span data-stu-id="4f0ee-150">Developing a User Interface for a Custom Log Provider</span></span>](developing-a-user-interface-for-a-custom-log-provider.md)  
  
  
