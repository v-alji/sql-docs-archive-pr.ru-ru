---
title: Добавление соединений программным образом | Документы Майкрософт
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
- connection managers [Integration Services], packages
- Integration Services packages, connections
- connections [Integration Services], packages
- SSIS packages, connections
- packages [Integration Services], connections
- intrinsic properties [Integration Services]
- SQL Server Integration Services packages, connections
- ConnectionManager class
- SSIS connection managers
- adding package connections
ms.assetid: d90716d1-4c65-466c-b82c-4aabbee1e3e5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a5952221dbf2689d2328695baf965ce884dc07fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658366"
---
# <a name="adding-connections-programmatically"></a><span data-ttu-id="28799-102">Добавление соединений программным образом</span><span class="sxs-lookup"><span data-stu-id="28799-102">Adding Connections Programmatically</span></span>
  <span data-ttu-id="28799-103">Класс <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> представляет физические соединения с внешними источниками данных.</span><span class="sxs-lookup"><span data-stu-id="28799-103">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> class represents physical connections to external data sources.</span></span> <span data-ttu-id="28799-104">Класс <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> изолирует данные о реализации соединения от среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="28799-104">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> class isolates the implementation details of the connection from the runtime.</span></span> <span data-ttu-id="28799-105">Это обеспечивает согласованное и прогнозируемое взаимодействие среды выполнения с каждым диспетчером соединений.</span><span class="sxs-lookup"><span data-stu-id="28799-105">This enables the runtime to interact with each connection manager in a consistent and predictable manner.</span></span> <span data-ttu-id="28799-106">Диспетчеры соединений содержат набор основных свойств, общих для всех соединений, например, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ID%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Description%2A> и <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A>.</span><span class="sxs-lookup"><span data-stu-id="28799-106">Connection managers contain a set of stock properties that all connections have in common, such as the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ID%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Description%2A>, and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A>.</span></span> <span data-ttu-id="28799-107">Однако, как правило, только свойства <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A> и <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A> требуются для настройки диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="28799-107">However, the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A> properties are ordinarily the only properties required to configure a connection manager.</span></span> <span data-ttu-id="28799-108">Обычно классами соединения используются такие методы, как `Open` или `Connect`, чтобы установить физическое соединение с источником данных, однако обработчик среды выполнения управляет всеми соединениями пакета во время его выполнения.</span><span class="sxs-lookup"><span data-stu-id="28799-108">Unlike other programming paradigms, where connection classes expose methods such as `Open` or `Connect` to physically establish a connection to the data source, the run-time engine manages all the connections for the package while it runs.</span></span>  
  
 <span data-ttu-id="28799-109">Класс <xref:Microsoft.SqlServer.Dts.Runtime.Connections> представляет собой коллекцию диспетчеров соединений, добавленных в этот пакет и доступных для использования во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="28799-109">The <xref:Microsoft.SqlServer.Dts.Runtime.Connections> class is a collection of the connection managers that have been added to that package and are available for use at run time.</span></span> <span data-ttu-id="28799-110">Можно добавить в коллекцию дополнительные диспетчеры соединений, используя метод <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Add%2A> коллекции и указав строку, определяющую тип диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="28799-110">You can add more connection managers to the collection by using the <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Add%2A> method of the collection, and supplying a string that indicates the connection manager type.</span></span> <span data-ttu-id="28799-111">Метод <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Add%2A> возвращает экземпляр <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>, который был добавлен в пакет.</span><span class="sxs-lookup"><span data-stu-id="28799-111">The <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Add%2A> method returns the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> instance that was added to the package.</span></span>  
  
## <a name="intrinsic-properties"></a><span data-ttu-id="28799-112">Важные свойства</span><span class="sxs-lookup"><span data-stu-id="28799-112">Intrinsic Properties</span></span>  
 <span data-ttu-id="28799-113">Класс <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> представляет набор свойств, общих для всех соединений.</span><span class="sxs-lookup"><span data-stu-id="28799-113">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> class exposes a set of properties that are common to all connections.</span></span> <span data-ttu-id="28799-114">Однако иногда может потребоваться доступ к уникальным свойствам, характеризующим определенный тип соединений.</span><span class="sxs-lookup"><span data-stu-id="28799-114">However, sometimes you need access to properties that are unique to the specific connection type.</span></span> <span data-ttu-id="28799-115">Коллекция <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Properties%2A> класса <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> обеспечивает доступ к таким свойствам.</span><span class="sxs-lookup"><span data-stu-id="28799-115">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Properties%2A> collection of the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> class provides access to these properties.</span></span> <span data-ttu-id="28799-116">Свойства можно извлечь из коллекции с помощью индексатора или имени свойства и метода **GetValue**, а значения задаются с использованием метода **SetValue**.</span><span class="sxs-lookup"><span data-stu-id="28799-116">The properties can be retrieved from the collection using the indexer or the property name and the **GetValue** method, and the values are set using the **SetValue** method.</span></span> <span data-ttu-id="28799-117">Свойства базового объекта соединения также можно задать, получив фактический экземпляр объекта и непосредственно определив его свойства.</span><span class="sxs-lookup"><span data-stu-id="28799-117">The properties of the underlying connection object properties can also be set by acquiring an actual instance of the object and setting its properties directly.</span></span> <span data-ttu-id="28799-118">Чтобы получить базовое соединение, используйте свойство <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.InnerObject%2A> диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="28799-118">To get the underlying connection, use the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.InnerObject%2A> property of the connection manager.</span></span> <span data-ttu-id="28799-119">Ниже приведена строка кода на языке C#, создающая диспетчер соединений ADO.NET, имеющий базовый класс <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.ConnectionManagerAdoNetClass>.</span><span class="sxs-lookup"><span data-stu-id="28799-119">The following line of code shows a C# line that creates an ADO.NET connection manager that has the underlying class, <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.ConnectionManagerAdoNetClass>.</span></span>  
  
 `ConnectionManagerAdoNetClass cmado = cm.InnerObject as ConnectionManagerAdoNet;`  
  
 <span data-ttu-id="28799-120">Таким образом, выполняется приведение объекта управляемого диспетчера соединений к объекту его базового соединения.</span><span class="sxs-lookup"><span data-stu-id="28799-120">This casts the managed connection manager object to its underlying connection object.</span></span> <span data-ttu-id="28799-121">При использовании языка C++ вызывается метод `QueryInterface` объекта <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> и запрашивается интерфейс объекта базового соединения.</span><span class="sxs-lookup"><span data-stu-id="28799-121">If you are using C++, the `QueryInterface` method of the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> object is called and the interface of the underlying connection object is requested.</span></span>  
  
 <span data-ttu-id="28799-122">В следующей таблице перечислены диспетчеры соединений, входящие в состав служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28799-122">The following table lists the connection managers included with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="28799-123">и строка, которая используется в инструкции `package.Connections.Add("xxx")`.</span><span class="sxs-lookup"><span data-stu-id="28799-123">and the string that is used in the `package.Connections.Add("xxx")` statement.</span></span> <span data-ttu-id="28799-124">Список всех диспетчеров подключений см. в разделе [Соединения в службах Integration Services (SSIS)](../connection-manager/integration-services-ssis-connections.md).</span><span class="sxs-lookup"><span data-stu-id="28799-124">For a list of all connection managers, see [Integration Services &#40;SSIS&#41; Connections](../connection-manager/integration-services-ssis-connections.md).</span></span>  
  
|<span data-ttu-id="28799-125">String</span><span class="sxs-lookup"><span data-stu-id="28799-125">String</span></span>|<span data-ttu-id="28799-126">Диспетчер соединений</span><span class="sxs-lookup"><span data-stu-id="28799-126">Connection manager</span></span>|  
|------------|------------------------|  
|<span data-ttu-id="28799-127">OLEDB</span><span class="sxs-lookup"><span data-stu-id="28799-127">"OLEDB"</span></span>|<span data-ttu-id="28799-128">Диспетчер соединений для соединений OLE DB.</span><span class="sxs-lookup"><span data-stu-id="28799-128">Connection manager for OLE DB connections.</span></span>|  
|<span data-ttu-id="28799-129">ODBC</span><span class="sxs-lookup"><span data-stu-id="28799-129">"ODBC"</span></span>|<span data-ttu-id="28799-130">Диспетчер соединений для соединений ODBC.</span><span class="sxs-lookup"><span data-stu-id="28799-130">Connection manager for ODBC connections.</span></span>|  
|<span data-ttu-id="28799-131">ADO</span><span class="sxs-lookup"><span data-stu-id="28799-131">"ADO"</span></span>|<span data-ttu-id="28799-132">Диспетчер соединений для соединений ADO.</span><span class="sxs-lookup"><span data-stu-id="28799-132">Connection manager for ADO connections.</span></span>|  
|<span data-ttu-id="28799-133">ADO.NET:SQL</span><span class="sxs-lookup"><span data-stu-id="28799-133">"ADO.NET:SQL"</span></span>|<span data-ttu-id="28799-134">Диспетчер соединений для соединений ADO.NET (поставщик данных SQL).</span><span class="sxs-lookup"><span data-stu-id="28799-134">Connection manager for ADO.NET (SQL data provider) connections.</span></span>|  
|<span data-ttu-id="28799-135">ADO.NET:OLEDB</span><span class="sxs-lookup"><span data-stu-id="28799-135">"ADO.NET:OLEDB"</span></span>|<span data-ttu-id="28799-136">Диспетчер соединений для соединений ADO.NET (поставщик данных OLE DB).</span><span class="sxs-lookup"><span data-stu-id="28799-136">Connection manager for ADO.NET (OLE DB data provider) connections.</span></span>|  
|<span data-ttu-id="28799-137">FLATFILE</span><span class="sxs-lookup"><span data-stu-id="28799-137">"FLATFILE"</span></span>|<span data-ttu-id="28799-138">Диспетчер соединений для соединений неструктурированных файлов.</span><span class="sxs-lookup"><span data-stu-id="28799-138">Connection manager for flat file connections.</span></span>|  
|<span data-ttu-id="28799-139">FILE</span><span class="sxs-lookup"><span data-stu-id="28799-139">"FILE"</span></span>|<span data-ttu-id="28799-140">Диспетчер соединений для соединений файлов.</span><span class="sxs-lookup"><span data-stu-id="28799-140">Connection manager for file connections.</span></span>|  
|<span data-ttu-id="28799-141">MULTIFLATFILE</span><span class="sxs-lookup"><span data-stu-id="28799-141">"MULTIFLATFILE"</span></span>|<span data-ttu-id="28799-142">Диспетчер соединений для соединений нескольких неструктурированных файлов.</span><span class="sxs-lookup"><span data-stu-id="28799-142">Connection manager for multiple flat file connections.</span></span>|  
|<span data-ttu-id="28799-143">MULTIFILE</span><span class="sxs-lookup"><span data-stu-id="28799-143">"MULTIFILE"</span></span>|<span data-ttu-id="28799-144">Диспетчер соединений для соединений нескольких файлов.</span><span class="sxs-lookup"><span data-stu-id="28799-144">Connection manager for multiple file connections.</span></span>|  
|<span data-ttu-id="28799-145">SQLMOBILE</span><span class="sxs-lookup"><span data-stu-id="28799-145">"SQLMOBILE"</span></span>|<span data-ttu-id="28799-146">Диспетчер подключений для соединений [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="28799-146">Connection manager for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact connections.</span></span>|  
|<span data-ttu-id="28799-147">MSOLAP100</span><span class="sxs-lookup"><span data-stu-id="28799-147">"MSOLAP100"</span></span>|<span data-ttu-id="28799-148">Диспетчер соединений для соединений служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28799-148">Connection manager for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connections.</span></span>|  
|<span data-ttu-id="28799-149">FTP</span><span class="sxs-lookup"><span data-stu-id="28799-149">"FTP"</span></span>|<span data-ttu-id="28799-150">Диспетчер соединений для FTP-соединений.</span><span class="sxs-lookup"><span data-stu-id="28799-150">Connection manager for FTP connections.</span></span>|  
|<span data-ttu-id="28799-151">HTTP</span><span class="sxs-lookup"><span data-stu-id="28799-151">"HTTP"</span></span>|<span data-ttu-id="28799-152">Диспетчер соединений для HTTP-соединений.</span><span class="sxs-lookup"><span data-stu-id="28799-152">Connection manager for HTTP connections.</span></span>|  
|<span data-ttu-id="28799-153">MSMQ</span><span class="sxs-lookup"><span data-stu-id="28799-153">"MSMQ"</span></span>|<span data-ttu-id="28799-154">Диспетчер соединений для соединений службы очередей сообщений (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="28799-154">Connection manager for Message Queuing (also known as MSMQ) connections.</span></span>|  
|<span data-ttu-id="28799-155">SMTP</span><span class="sxs-lookup"><span data-stu-id="28799-155">"SMTP"</span></span>|<span data-ttu-id="28799-156">Диспетчер SMTP-соединений.</span><span class="sxs-lookup"><span data-stu-id="28799-156">Connection manager for SMTP connections.</span></span>|  
|<span data-ttu-id="28799-157">«WMI»</span><span class="sxs-lookup"><span data-stu-id="28799-157">"WMI"</span></span>|<span data-ttu-id="28799-158">Диспетчер соединений инструментария управления Windows (WMI-соединений).</span><span class="sxs-lookup"><span data-stu-id="28799-158">Connection manager for Microsoft Windows Management Instrumentation (WMI) connections.</span></span>|  
  
 <span data-ttu-id="28799-159">В следующем примере кода демонстрируется добавление соединений OLE DB и FILE в коллекцию <xref:Microsoft.SqlServer.Dts.Runtime.Package.Connections%2A> пакета <xref:Microsoft.SqlServer.Dts.Runtime.Package>.</span><span class="sxs-lookup"><span data-stu-id="28799-159">The following code example demonstrates adding an OLE DB and FILE connection to the <xref:Microsoft.SqlServer.Dts.Runtime.Package.Connections%2A> collection of a <xref:Microsoft.SqlServer.Dts.Runtime.Package>.</span></span> <span data-ttu-id="28799-160">Затем в примере задаются свойства <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A> и <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Description%2A>.</span><span class="sxs-lookup"><span data-stu-id="28799-160">The example then sets the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A>, and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Description%2A> properties.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      // Create a package, and retrieve its connections.  
      Package pkg = new Package();  
      Connections pkgConns = pkg.Connections;  
  
      // Add an OLE DB connection to the package, using the   
      // method defined in the AddConnection class.  
      CreateConnection myOLEDBConn = new CreateConnection();  
      myOLEDBConn.CreateOLEDBConnection(pkg);  
  
      // View the new connection in the package.  
      Console.WriteLine("Connection description: {0}",  
         pkg.Connections["SSIS Connection Manager for OLE DB"].Description);  
  
      // Add a second connection to the package.  
      CreateConnection myFileConn = new CreateConnection();  
      myFileConn.CreateFileConnection(pkg);  
  
      // View the second connection in the package.  
      Console.WriteLine("Connection description: {0}",  
        pkg.Connections["SSIS Connection Manager for Files"].Description);  
  
      Console.WriteLine();  
      Console.WriteLine("Number of connections in package: {0}", pkg.Connections.Count);  
  
      Console.Read();  
    }  
  }  
  // <summary>  
  // This class contains the definitions for multiple  
  // connection managers.  
  // </summary>  
  public class CreateConnection  
  {  
    // Private data.  
    private ConnectionManager ConMgr;  
  
    // Class definition for OLE DB Provider.  
    public void CreateOLEDBConnection(Package p)  
    {  
      ConMgr = p.Connections.Add("OLEDB");  
      ConMgr.ConnectionString = "Provider=SQLOLEDB.1;" +  
        "Integrated Security=SSPI;Initial Catalog=AdventureWorks;" +  
        "Data Source=(local);";  
      ConMgr.Name = "SSIS Connection Manager for OLE DB";  
      ConMgr.Description = "OLE DB connection to the AdventureWorks database.";  
    }  
    public void CreateFileConnection(Package p)  
    {  
      ConMgr = p.Connections.Add("File");  
      ConMgr.ConnectionString = @"\\<yourserver>\<yourfolder>\books.xml";  
      ConMgr.Name = "SSIS Connection Manager for Files";  
      ConMgr.Description = "Flat File connection";  
    }  
  }  
  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    ' Create a package, and retrieve its connections.  
    Dim pkg As New Package()  
    Dim pkgConns As Connections = pkg.Connections  
  
    ' Add an OLE DB connection to the package, using the   
    ' method defined in the AddConnection class.  
    Dim myOLEDBConn As New CreateConnection()  
    myOLEDBConn.CreateOLEDBConnection(pkg)  
  
    ' View the new connection in the package.  
    Console.WriteLine("Connection description: {0}", _  
      pkg.Connections("SSIS Connection Manager for OLE DB").Description)  
  
    ' Add a second connection to the package.  
    Dim myFileConn As New CreateConnection()  
    myFileConn.CreateFileConnection(pkg)  
  
    ' View the second connection in the package.  
    Console.WriteLine("Connection description: {0}", _  
      pkg.Connections("SSIS Connection Manager for Files").Description)  
  
    Console.WriteLine()  
    Console.WriteLine("Number of connections in package: {0}", pkg.Connections.Count)  
  
    Console.Read()  
  
  End Sub  
  
End Module  
  
' This class contains the definitions for multiple  
' connection managers.  
  
Public Class CreateConnection  
  ' Private data.  
  Private ConMgr As ConnectionManager  
  
  ' Class definition for OLE DB provider.  
  Public Sub CreateOLEDBConnection(ByVal p As Package)  
    ConMgr = p.Connections.Add("OLEDB")  
    ConMgr.ConnectionString = "Provider=SQLOLEDB.1;" & _  
      "Integrated Security=SSPI;Initial Catalog=AdventureWorks;" & _  
      "Data Source=(local);"  
    ConMgr.Name = "SSIS Connection Manager for OLE DB"  
    ConMgr.Description = "OLE DB connection to the AdventureWorks database."  
  End Sub  
  
  Public Sub CreateFileConnection(ByVal p As Package)  
    ConMgr = p.Connections.Add("File")  
    ConMgr.ConnectionString = "\\<yourserver>\<yourfolder>\books.xml"  
    ConMgr.Name = "SSIS Connection Manager for Files"  
    ConMgr.Description = "Flat File connection"  
  End Sub  
  
End Class  
```  
  
 <span data-ttu-id="28799-161">**Образец вывода:**</span><span class="sxs-lookup"><span data-stu-id="28799-161">**Sample Output:**</span></span>  
  
 `Connection description: OLE DB connection to the AdventureWorks database.`  
  
 `Connection description: OLE DB connection to the AdventureWorks database.`  
  
 `Number of connections in package: 2`  
  
## <a name="external-resources"></a><span data-ttu-id="28799-162">Внешние ресурсы</span><span class="sxs-lookup"><span data-stu-id="28799-162">External Resources</span></span>  
 <span data-ttu-id="28799-163">Техническая статья [Строки подключения](https://go.microsoft.com/fwlink/?LinkId=220743) на сайте carlprothman.net.</span><span class="sxs-lookup"><span data-stu-id="28799-163">Technical article, [Connection Strings](https://go.microsoft.com/fwlink/?LinkId=220743), on carlprothman.net.</span></span>  
  
<span data-ttu-id="28799-164">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="28799-164">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="28799-165">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="28799-165">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="28799-166">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="28799-166">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="28799-167">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="28799-167">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28799-168">См. также:</span><span class="sxs-lookup"><span data-stu-id="28799-168">See Also</span></span>  
 <span data-ttu-id="28799-169">[Integration Services &#40;соединений&#41; SSIS](../connection-manager/integration-services-ssis-connections.md) </span><span class="sxs-lookup"><span data-stu-id="28799-169">[Integration Services &#40;SSIS&#41; Connections](../connection-manager/integration-services-ssis-connections.md) </span></span>  
 [<span data-ttu-id="28799-170">Создание диспетчеров соединений</span><span class="sxs-lookup"><span data-stu-id="28799-170">Create Connection Managers</span></span>](../create-connection-managers.md)  
  
  
