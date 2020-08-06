---
title: Написание кода пользовательского диспетчера соединений | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom connection managers [Integration Services], coding
ms.assetid: b12b6778-1f01-4a7d-984d-73f2f7630aa5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 793d70ba0a9ae6176ab35c82e16b9aba8c9ba2cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736587"
---
# <a name="coding-a-custom-connection-manager"></a><span data-ttu-id="9022d-102">Написание кода пользовательского диспетчера соединений</span><span class="sxs-lookup"><span data-stu-id="9022d-102">Coding a Custom Connection Manager</span></span>
  <span data-ttu-id="9022d-103">После создания класса, наследующего от базового класса <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase>, и применения к нему атрибута <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute>, необходимо переопределить реализацию свойств и методов базового класса, чтобы обеспечить пользовательские функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="9022d-103">After you have created a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase> base class, and applied the <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute> attribute to the class, you must override the implementation of the properties and methods of the base class to provide your custom functionality.</span></span>  
  
 <span data-ttu-id="9022d-104">Примеры пользовательских диспетчеров соединений см. в разделе [Разработка пользовательского интерфейса для пользовательского диспетчера соединений](developing-a-user-interface-for-a-custom-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="9022d-104">For samples of custom connection managers, see [Developing a User Interface for a Custom Connection Manager](developing-a-user-interface-for-a-custom-connection-manager.md).</span></span> <span data-ttu-id="9022d-105">Примеры кода, приведенные в этом разделе, взяты из образца пользовательского диспетчера соединений SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9022d-105">The code examples shown in this topic are drawn from the SQL Server Custom Connection Manager sample.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9022d-106">Большая часть задач, источников и назначений в службах [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] работает только с определенными типами встроенных диспетчеров соединений.</span><span class="sxs-lookup"><span data-stu-id="9022d-106">Most of the tasks, sources, and destinations that have been built into [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] work only with specific types of built-in connection managers.</span></span> <span data-ttu-id="9022d-107">Поэтому данные образцы нельзя протестировать с помощью встроенных задач и компонентов.</span><span class="sxs-lookup"><span data-stu-id="9022d-107">Therefore, these samples cannot be tested with the built-in tasks and components.</span></span>  
  
## <a name="configuring-the-connection-manager"></a><span data-ttu-id="9022d-108">Настройка диспетчера соединений</span><span class="sxs-lookup"><span data-stu-id="9022d-108">Configuring the Connection Manager</span></span>  
  
### <a name="setting-the-connectionstring-property"></a><span data-ttu-id="9022d-109">Задание свойства ConnectionString</span><span class="sxs-lookup"><span data-stu-id="9022d-109">Setting the ConnectionString Property</span></span>  
 <span data-ttu-id="9022d-110">Свойство <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> – важное свойство, которое является единственным уникальным свойством для пользовательского диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="9022d-110">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> property is an important property and the only property unique to a custom connection manager.</span></span> <span data-ttu-id="9022d-111">Диспетчер соединений использует значение этого свойства для соединения с внешним источником данных.</span><span class="sxs-lookup"><span data-stu-id="9022d-111">The connection manager uses the value of this property to connect to the external data source.</span></span> <span data-ttu-id="9022d-112">Если необходимо скомбинировать несколько других свойств, например, имя сервера и имя базы данных, чтобы создать строку соединения, можно использовать вспомогательную функцию для сборки строки путем замены определенных значений в шаблоне строки соединения новыми значениями, предоставленными пользователем.</span><span class="sxs-lookup"><span data-stu-id="9022d-112">If you are combining several other properties, such as server name and database name, to create the connection string, you can use a helper function to assemble the string by replacing certain values in a connection string template with the new value supplied by the user.</span></span> <span data-ttu-id="9022d-113">В следующем примере кода демонстрируется реализация свойства <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A>, которое использует вспомогательную функцию для сборки строки.</span><span class="sxs-lookup"><span data-stu-id="9022d-113">The following code example shows an implementation of the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> property that relies on a helper function to assemble the string.</span></span>  
  
```vb  
' Default values.  
Private _serverName As String = "(local)"  
Private _databaseName As String = "AdventureWorks"  
Private _connectionString As String = String.Empty  
  
Private Const CONNECTIONSTRING_TEMPLATE As String = _  
  "Data Source=<servername>;Initial Catalog=<databasename>;Integrated Security=SSPI"  
  
Public Property ServerName() As String  
  Get  
    Return _serverName  
  End Get  
  Set(ByVal value As String)  
    _serverName = value  
  End Set  
End Property  
  
Public Property DatabaseName() As String  
  Get  
    Return _databaseName  
  End Get  
  Set(ByVal value As String)  
    _databaseName = value  
  End Set  
End Property  
  
Public Overrides Property ConnectionString() As String  
  Get  
    UpdateConnectionString()  
    Return _connectionString  
  End Get  
  Set(ByVal value As String)  
    _connectionString = value  
  End Set  
End Property  
  
Private Sub UpdateConnectionString()  
  
  Dim temporaryString As String = CONNECTIONSTRING_TEMPLATE  
  
  If Not String.IsNullOrEmpty(_serverName) Then  
    temporaryString = temporaryString.Replace("<servername>", _serverName)  
  End If  
  If Not String.IsNullOrEmpty(_databaseName) Then  
    temporaryString = temporaryString.Replace("<databasename>", _databaseName)  
  End If  
  
  _connectionString = temporaryString  
  
End Sub  
```  
  
```csharp  
// Default values.  
private string _serverName = "(local)";  
private string _databaseName = "AdventureWorks";  
private string _connectionString = String.Empty;  
  
private const string CONNECTIONSTRING_TEMPLATE = "Data Source=<servername>;Initial Catalog=<databasename>;Integrated Security=SSPI";  
  
public string ServerName  
{  
  get  
  {  
    return _serverName;  
  }  
  set  
  {  
    _serverName = value;  
  }  
}  
  
public string DatabaseName  
{  
  get  
  {  
    return _databaseName;  
  }  
  set  
  {  
    _databaseName = value;  
  }  
}  
  
public override string ConnectionString  
{  
  get  
  {  
    UpdateConnectionString();  
    return _connectionString;  
  }  
  set  
  {  
    _connectionString = value;  
  }  
}  
  
private void UpdateConnectionString()  
{  
  
  string temporaryString = CONNECTIONSTRING_TEMPLATE;  
  
  if (!String.IsNullOrEmpty(_serverName))  
  {  
    temporaryString = temporaryString.Replace("<servername>", _serverName);  
  }  
  
  if (!String.IsNullOrEmpty(_databaseName))  
  {  
    temporaryString = temporaryString.Replace("<databasename>", _databaseName);  
  }  
  
  _connectionString = temporaryString;  
  
}  
```  
  
### <a name="validating-the-connection-manager"></a><span data-ttu-id="9022d-114">Проверка диспетчера соединений</span><span class="sxs-lookup"><span data-stu-id="9022d-114">Validating the Connection Manager</span></span>  
 <span data-ttu-id="9022d-115">Необходимо переопределить метод <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.Validate%2A>, чтобы убедиться в правильности настройки диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="9022d-115">You override the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.Validate%2A> method to make sure that the connection manager has been configured correctly.</span></span> <span data-ttu-id="9022d-116">Как минимум, следует проверить формат строки соединения и убедиться в том, что предоставлены значения для всех аргументов.</span><span class="sxs-lookup"><span data-stu-id="9022d-116">At a minimum, you should validate the format of the connection string and make sure that values have been provided for all arguments.</span></span> <span data-ttu-id="9022d-117">Выполнение не может продолжиться, пока диспетчер соединений не возвратит значение <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Success> из метода <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="9022d-117">Execution cannot continue until the connection manager returns <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Success> from the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.Validate%2A> method.</span></span>  
  
 <span data-ttu-id="9022d-118">В следующем примере кода демонстрируется реализация метода <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.Validate%2A>, который проверяет, указано ли пользователем имя сервера для соединения.</span><span class="sxs-lookup"><span data-stu-id="9022d-118">The following code example shows an implementation of <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.Validate%2A> that makes sure that the user has specified a server name for the connection.</span></span>  
  
```vb  
Public Overrides Function Validate(ByVal infoEvents As Microsoft.SqlServer.Dts.Runtime.IDTSInfoEvents) As Microsoft.SqlServer.Dts.Runtime.DTSExecResult  
  
  If String.IsNullOrEmpty(_serverName) Then  
    infoEvents.FireError(0, "SqlConnectionManager", "No server name specified", String.Empty, 0)  
    Return DTSExecResult.Failure  
  Else  
    Return DTSExecResult.Success  
  End If  
  
End Function  
```  
  
```csharp  
public override Microsoft.SqlServer.Dts.Runtime.DTSExecResult Validate(Microsoft.SqlServer.Dts.Runtime.IDTSInfoEvents infoEvents)  
{  
  
  if (String.IsNullOrEmpty(_serverName))  
  {  
    infoEvents.FireError(0, "SqlConnectionManager", "No server name specified", String.Empty, 0);  
    return DTSExecResult.Failure;  
  }  
  else  
  {  
    return DTSExecResult.Success;  
  }  
  
}  
```  
  
### <a name="persisting-the-connection-manager"></a><span data-ttu-id="9022d-119">Сохраняемость диспетчера соединений</span><span class="sxs-lookup"><span data-stu-id="9022d-119">Persisting the Connection Manager</span></span>  
 <span data-ttu-id="9022d-120">Как правило, реализовывать пользовательскую сохраняемость для диспетчера соединений нет необходимости.</span><span class="sxs-lookup"><span data-stu-id="9022d-120">Usually, you do not have to implement custom persistence for a connection manager.</span></span> <span data-ttu-id="9022d-121">Нестандартный механизм сохраняемости необходим только в случае, когда свойства объекта используют сложные типы данных.</span><span class="sxs-lookup"><span data-stu-id="9022d-121">Custom persistence is required only when the properties of an object use complex data types.</span></span> <span data-ttu-id="9022d-122">Дополнительные сведения см. в разделе [Разработка пользовательских объектов для служб Integration Services](../developing-custom-objects-for-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="9022d-122">For more information, see [Developing Custom Objects for Integration Services](../developing-custom-objects-for-integration-services.md).</span></span>  
  
## <a name="working-with-the-external-data-source"></a><span data-ttu-id="9022d-123">Работа с внешним источником данных</span><span class="sxs-lookup"><span data-stu-id="9022d-123">Working with the External Data Source</span></span>  
 <span data-ttu-id="9022d-124">Методы, поддерживающие соединение с внешним источником данных, являются наиболее важными методами для пользовательского диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="9022d-124">The methods that support connecting to an external data source are the most important methods of a custom connection manager.</span></span> <span data-ttu-id="9022d-125">Методы <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> и <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ReleaseConnection%2A> вызываются в различные моменты, как во время разработки, так и во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="9022d-125">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ReleaseConnection%2A> methods are called at various times during both design time and run time.</span></span>  
  
### <a name="acquiring-the-connection"></a><span data-ttu-id="9022d-126">Получение соединения</span><span class="sxs-lookup"><span data-stu-id="9022d-126">Acquiring the Connection</span></span>  
 <span data-ttu-id="9022d-127">Необходимо решить, какого типа объект должен возвращаться методом <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> из пользовательского диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="9022d-127">You need to decide what type of object it is appropriate for the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> method to return from your custom connection manager.</span></span> <span data-ttu-id="9022d-128">Например, диспетчер соединения файлов возвращает только строку, содержащую путь и имя файла, в то время как диспетчер соединений ADO.NET возвращает управляемый объект соединения, который уже открыт.</span><span class="sxs-lookup"><span data-stu-id="9022d-128">For example, a File connection manager returns only a string that contains a path and filename, whereas an ADO.NET connection manager returns a managed connection object that is already open.</span></span> <span data-ttu-id="9022d-129">Диспетчер соединений OLE DB возвращает собственный объект соединения OLE DB, который не может использоваться из управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="9022d-129">An OLE DB connection manager returns a native OLE DB connection object that cannot be used from managed code.</span></span> <span data-ttu-id="9022d-130">Пользовательский диспетчер соединений SQL Server, из которого взяты фрагменты кода в этом разделе, возвращает открытый объект `SqlConnection`.</span><span class="sxs-lookup"><span data-stu-id="9022d-130">The custom SQL Server connection manager, from which the code snippets in this topic are taken, returns an open `SqlConnection` object.</span></span>  
  
 <span data-ttu-id="9022d-131">Пользователям диспетчера соединений необходимо знать заранее, какого типа объект следует ожидать, чтобы они могли привести возвращенный объект к соответствующему типу и получить доступ к его методам и свойствам.</span><span class="sxs-lookup"><span data-stu-id="9022d-131">Users of your connection manager need to know in advance what type of object to expect, so that they can cast the returned object to the appropriate type and access its methods and properties.</span></span>  
  
```vb  
Public Overrides Function AcquireConnection(ByVal txn As Object) As Object  
  
  Dim sqlConnection As New SqlConnection  
  
  UpdateConnectionString()  
  
  With sqlConnection  
    .ConnectionString = _connectionString  
    .Open()  
  End With  
  
  Return sqlConnection  
  
End Function  
```  
  
```csharp  
public override object AcquireConnection(object txn)  
{  
  
  SqlConnection sqlConnection = new SqlConnection();  
  
  UpdateConnectionString();  
  
  {  
    sqlConnection.ConnectionString = _connectionString;  
    sqlConnection.Open();  
  }  
  
  return sqlConnection;  
  
}  
```  
  
### <a name="releasing-the-connection"></a><span data-ttu-id="9022d-132">Освобождение соединения</span><span class="sxs-lookup"><span data-stu-id="9022d-132">Releasing the Connection</span></span>  
 <span data-ttu-id="9022d-133">Действие, которое необходимо предпринять в методе <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ReleaseConnection%2A>, зависит от типа объекта, возвращаемого из метода <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A>.</span><span class="sxs-lookup"><span data-stu-id="9022d-133">The action that you take in the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ReleaseConnection%2A> method depends on the type of object that you returned from the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> method.</span></span> <span data-ttu-id="9022d-134">Если имеется открытый объект соединения, следует закрыть его и освободить используемые им ресурсы.</span><span class="sxs-lookup"><span data-stu-id="9022d-134">If there is an open connection object, you should close it and to release any resources that it is using.</span></span> <span data-ttu-id="9022d-135">Если методом <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> возвращено только строковое значение, не нужно предпринимать никаких действий.</span><span class="sxs-lookup"><span data-stu-id="9022d-135">If <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> returned only a string value, no action needs to be taken.</span></span>  
  
```vb  
Public Overrides Sub ReleaseConnection(ByVal connection As Object)  
  
  Dim sqlConnection As SqlConnection  
  
  sqlConnection = DirectCast(connection, SqlConnection)  
  
  If sqlConnection.State <> ConnectionState.Closed Then  
    sqlConnection.Close()  
  End If  
  
End Sub  
```  
  
```csharp  
public override void ReleaseConnection(object connection)  
{  
  SqlConnection sqlConnection;  
  sqlConnection = (SqlConnection)connection;  
  if (sqlConnection.State != ConnectionState.Closed)  
    sqlConnection.Close();  
}  
```  
  
<span data-ttu-id="9022d-136">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="9022d-136">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="9022d-137">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="9022d-137">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="9022d-138">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="9022d-138">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="9022d-139">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="9022d-139">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9022d-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="9022d-140">See Also</span></span>  
 <span data-ttu-id="9022d-141">[Создание пользовательского диспетчера соединений](creating-a-custom-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="9022d-141">[Creating a Custom Connection Manager](creating-a-custom-connection-manager.md) </span></span>  
 [<span data-ttu-id="9022d-142">Разработка пользовательского интерфейса для пользовательского диспетчера соединений</span><span class="sxs-lookup"><span data-stu-id="9022d-142">Developing a User Interface for a Custom Connection Manager</span></span>](developing-a-user-interface-for-a-custom-connection-manager.md)  
  
  
