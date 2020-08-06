---
title: Реализация конечных точек | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- endpoints [SMO]
ms.assetid: f8674dbb-9bc0-488f-9def-e9e0ce1ddf86
author: stevestein
ms.author: sstein
ms.openlocfilehash: 293a661c6e1ad6f6139e30e0824e99686af98f90
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739620"
---
# <a name="implementing-endpoints"></a><span data-ttu-id="355f5-102">Реализация конечных точек</span><span class="sxs-lookup"><span data-stu-id="355f5-102">Implementing Endpoints</span></span>
  <span data-ttu-id="355f5-103">Конечная точка представляет собой службу, в функции которой входит прослушивание запросов.</span><span class="sxs-lookup"><span data-stu-id="355f5-103">An endpoint is a service that can listen natively for requests.</span></span> <span data-ttu-id="355f5-104">В SMO поддерживаются разные типы конечных точек с помощью объекта <xref:Microsoft.SqlServer.Management.Smo.Endpoint>.</span><span class="sxs-lookup"><span data-stu-id="355f5-104">SMO supports various types of endpoints by using the <xref:Microsoft.SqlServer.Management.Smo.Endpoint> object.</span></span> <span data-ttu-id="355f5-105">Для обработки конкретного типа полезных данных можно создать службу конечной точки, которая будет использовать указанный протокол, создав экземпляр объекта <xref:Microsoft.SqlServer.Management.Smo.Endpoint> и настроив его свойства.</span><span class="sxs-lookup"><span data-stu-id="355f5-105">You can create an endpoint service that handles a specific type of payload, which uses a specific protocol, by creating an instance of an <xref:Microsoft.SqlServer.Management.Smo.Endpoint> object and setting its properties.</span></span>  
  
 <span data-ttu-id="355f5-106">Свойство <xref:Microsoft.SqlServer.Management.Smo.Endpoint.EndpointType%2A> объекта <xref:Microsoft.SqlServer.Management.Smo.Endpoint> может использоваться для указания следующих типов полезных данных:</span><span class="sxs-lookup"><span data-stu-id="355f5-106">The <xref:Microsoft.SqlServer.Management.Smo.Endpoint.EndpointType%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Endpoint> object can be used to specify on of the following payload types:</span></span>  
  
-   <span data-ttu-id="355f5-107">Зеркальное отображение базы данных</span><span class="sxs-lookup"><span data-stu-id="355f5-107">Database mirroring</span></span>  
  
-   <span data-ttu-id="355f5-108">SOAP (поддержка для конечных точек SOAP предусмотрена в версии [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] и в предыдущих версиях [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="355f5-108">SOAP (support for SOAP endpoints is present in [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] and earlier [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] versions)</span></span>  
  
-   <span data-ttu-id="355f5-109">Компонент Service Broker</span><span class="sxs-lookup"><span data-stu-id="355f5-109">Service Broker</span></span>  
  
-   [!INCLUDE[tsql](../../../includes/tsql-md.md)]  
  
 <span data-ttu-id="355f5-110">Кроме того, свойство <xref:Microsoft.SqlServer.Management.Smo.Endpoint.ProtocolType%2A> может использоваться для указания следующих двух поддерживаемых протоколов:</span><span class="sxs-lookup"><span data-stu-id="355f5-110">Also, the <xref:Microsoft.SqlServer.Management.Smo.Endpoint.ProtocolType%2A> property can be used to specify the following two supported protocols:</span></span>  
  
-   <span data-ttu-id="355f5-111">протокол HTTP;</span><span class="sxs-lookup"><span data-stu-id="355f5-111">HTTP protocol</span></span>  
  
-   <span data-ttu-id="355f5-112">Протокол TCP.</span><span class="sxs-lookup"><span data-stu-id="355f5-112">TCP protocol</span></span>  
  
 <span data-ttu-id="355f5-113">После того как будет указан тип полезных данных, фактически применяемые полезные данные можно установить с помощью свойства <xref:Microsoft.SqlServer.Management.Smo.Endpoint.Payload%2A> объекта.</span><span class="sxs-lookup"><span data-stu-id="355f5-113">Having specified the type of payload, the actual payload can be set by using the <xref:Microsoft.SqlServer.Management.Smo.Endpoint.Payload%2A> object property.</span></span> <span data-ttu-id="355f5-114">Свойство объекта <xref:Microsoft.SqlServer.Management.Smo.Payload> обеспечивает ссылку на объект полезных данных указанного типа, свойства которого можно изменить.</span><span class="sxs-lookup"><span data-stu-id="355f5-114">The <xref:Microsoft.SqlServer.Management.Smo.Payload> object property provides a reference to a payload object of the specified type, for which the properties can be modified.</span></span>  
  
 <span data-ttu-id="355f5-115">Для объекта <xref:Microsoft.SqlServer.Management.Smo.DatabaseMirroringPayload> необходимо указать роль для зеркального отображения и отметить, включать ли шифрование.</span><span class="sxs-lookup"><span data-stu-id="355f5-115">For the <xref:Microsoft.SqlServer.Management.Smo.DatabaseMirroringPayload> object, you must specify the mirroring role and whether encryption is enabled.</span></span> <span data-ttu-id="355f5-116">Объекту <xref:Microsoft.SqlServer.Management.Smo.ServiceBrokerPayload> требуются сведения о перенаправлении сообщений, максимальном количестве разрешенных соединений и режиме проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="355f5-116">The <xref:Microsoft.SqlServer.Management.Smo.ServiceBrokerPayload> object requires information about message forwarding, maximum number of connections allowed and the authentication mode.</span></span> <span data-ttu-id="355f5-117">Для объекта <xref:Microsoft.SqlServer.Management.Smo.SoapPayloadMethod.%23ctor%2A> надо указать множество устанавливаемых свойств, включая свойство <xref:Microsoft.SqlServer.Management.Smo.SoapPayloadMethodCollection.Add%2A> объекта, которое указывает доступные клиентам методы полезных данных SOAP (хранимые процедуры и определяемые пользователем функции).</span><span class="sxs-lookup"><span data-stu-id="355f5-117">The <xref:Microsoft.SqlServer.Management.Smo.SoapPayloadMethod.%23ctor%2A> object requires various properties to be set including the <xref:Microsoft.SqlServer.Management.Smo.SoapPayloadMethodCollection.Add%2A> object property that specifies the SOAP payload methods available to clients (stored procedures and user-defined functions).</span></span>  
  
 <span data-ttu-id="355f5-118">Аналогично этому фактически применяемый протокол можно установить с помощью свойства <xref:Microsoft.SqlServer.Management.Smo.Endpoint.Protocol%2A> объекта, которое ссылается на объект протокола типа, указанного в свойстве <xref:Microsoft.SqlServer.Management.Smo.Endpoint.ProtocolType%2A>.</span><span class="sxs-lookup"><span data-stu-id="355f5-118">Similarly, the actual protocol can be set by using the <xref:Microsoft.SqlServer.Management.Smo.Endpoint.Protocol%2A> object property that references a protocol object of the type specified by <xref:Microsoft.SqlServer.Management.Smo.Endpoint.ProtocolType%2A> property.</span></span> <span data-ttu-id="355f5-119">Объекту <xref:Microsoft.SqlServer.Management.Smo.HttpProtocol> требуется список ограниченных IP-адресов, а также сведения о порте, веб-сайте и проверке подлинности.</span><span class="sxs-lookup"><span data-stu-id="355f5-119">The <xref:Microsoft.SqlServer.Management.Smo.HttpProtocol> object requires a list of restricted IP addresses, and port, website, and authentication information.</span></span> <span data-ttu-id="355f5-120">Объекту <xref:Microsoft.SqlServer.Management.Smo.TcpProtocol> также необходим список ограниченных IP-адресов и сведения о порте.</span><span class="sxs-lookup"><span data-stu-id="355f5-120">The <xref:Microsoft.SqlServer.Management.Smo.TcpProtocol> object also requires a list of restricted IP addresses and port information.</span></span>  
  
 <span data-ttu-id="355f5-121">После того как конечная точка будет создана и полностью определена, можно предоставлять, отменять и запрещать доступ к ней пользователям базы данных, группам, ролям и именам входа.</span><span class="sxs-lookup"><span data-stu-id="355f5-121">When the endpoint has been created and fully defined, access can be granted to, revoked from, and denied to database users, groups, roles, and logons.</span></span>  
  
## <a name="example"></a><span data-ttu-id="355f5-122">Пример</span><span class="sxs-lookup"><span data-stu-id="355f5-122">Example</span></span>  
 <span data-ttu-id="355f5-123">В следующем примере кода для создания приложения необходимо выбрать среду программирования, шаблон программирования и язык программирования.</span><span class="sxs-lookup"><span data-stu-id="355f5-123">For the following code example, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="355f5-124">Дополнительные сведения см. в статьях [Создание проекта Visual Basic SMO в Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) и [Создание проекта Visual C&#35; SMO в Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="355f5-124">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-a-database-mirroring-endpoint-service-in-visual-basic"></a><span data-ttu-id="355f5-125">Создание конечной точки зеркального отображения базы данных на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="355f5-125">Creating a Database Mirroring Endpoint Service in Visual Basic</span></span>  
 <span data-ttu-id="355f5-126">Этот пример кода показывает, как создать конечную точку зеркального отображения базы данных в SMO.</span><span class="sxs-lookup"><span data-stu-id="355f5-126">The code example demonstrates how to create a Database Mirroring endpoint in SMO.</span></span> <span data-ttu-id="355f5-127">Это надо сделать до того, как будет формироваться зеркальное отображение базы данных.</span><span class="sxs-lookup"><span data-stu-id="355f5-127">This is necessary before you create a database mirror.</span></span> <span data-ttu-id="355f5-128">Воспользуйтесь свойством <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> и другими свойствами объекта <xref:Microsoft.SqlServer.Management.Smo.Database> для создания зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="355f5-128">Use the <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> and other properties on the <xref:Microsoft.SqlServer.Management.Smo.Database> object to create a database mirror.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBEndpoints1](SMO How to#SMO_VBEndpoints1)]  -->  
  
## <a name="creating-a-database-mirroring-endpoint-service-in-visual-c"></a><span data-ttu-id="355f5-129">Создание конечной точки зеркального отображения базы данных на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="355f5-129">Creating a Database Mirroring Endpoint Service in Visual C#</span></span>  
 <span data-ttu-id="355f5-130">Этот пример кода показывает, как создать конечную точку зеркального отображения базы данных в SMO.</span><span class="sxs-lookup"><span data-stu-id="355f5-130">The code example demonstrates how to create a Database Mirroring endpoint in SMO.</span></span> <span data-ttu-id="355f5-131">Это надо сделать до того, как будет формироваться зеркальное отображение базы данных.</span><span class="sxs-lookup"><span data-stu-id="355f5-131">This is necessary before you create a database mirror.</span></span> <span data-ttu-id="355f5-132">Воспользуйтесь свойством <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> и другими свойствами объекта <xref:Microsoft.SqlServer.Management.Smo.Database> для создания зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="355f5-132">Use the <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> and other properties on the <xref:Microsoft.SqlServer.Management.Smo.Database> object to create a database mirror.</span></span>  
  
```csharp
{  
            //Set up a database mirroring endpoint on the server before   
        //setting up a database mirror.   
        //Connect to the local, default instance of SQL Server.   
            Server srv = new Server();  
            //Define an Endpoint object variable for database mirroring.   
            Endpoint ep = default(Endpoint);  
            ep = new Endpoint(srv, "Mirroring_Endpoint");  
            ep.ProtocolType = ProtocolType.Tcp;  
            ep.EndpointType = EndpointType.DatabaseMirroring;  
            //Specify the protocol ports.   
            ep.Protocol.Http.SslPort = 5024;  
            ep.Protocol.Tcp.ListenerPort = 6666;  
            //Specify the role of the payload.   
            ep.Payload.DatabaseMirroring.ServerMirroringRole = ServerMirroringRole.All;  
            //Create the endpoint on the instance of SQL Server.   
            ep.Create();  
            //Start the endpoint.   
            ep.Start();  
            Console.WriteLine(ep.EndpointState);  
        }  
```  
  
## <a name="creating-a-database-mirroring-endpoint-service-in-powershell"></a><span data-ttu-id="355f5-133">Создание конечной точки зеркального отображения базы данных в PowerShell</span><span class="sxs-lookup"><span data-stu-id="355f5-133">Creating a Database Mirroring Endpoint Service in PowerShell</span></span>  
 <span data-ttu-id="355f5-134">Этот пример кода показывает, как создать конечную точку зеркального отображения базы данных в SMO.</span><span class="sxs-lookup"><span data-stu-id="355f5-134">The code example demonstrates how to create a Database Mirroring endpoint in SMO.</span></span> <span data-ttu-id="355f5-135">Это надо сделать до того, как будет формироваться зеркальное отображение базы данных.</span><span class="sxs-lookup"><span data-stu-id="355f5-135">This is necessary before you create a database mirror.</span></span> <span data-ttu-id="355f5-136">Воспользуйтесь свойством <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> и другими свойствами объекта <xref:Microsoft.SqlServer.Management.Smo.Database> для создания зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="355f5-136">Use the <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> and other properties on the <xref:Microsoft.SqlServer.Management.Smo.Database> object to create a database mirror.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\  
$srv = Get-Item default  
  
#Get a new endpoint to congure and add  
$ep = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Endpoint -argumentlist $srv,"Mirroring_Endpoint"  
  
#Set some properties  
$ep.ProtocolType = [Microsoft.SqlServer.Management.SMO.ProtocolType]::Tcp  
$ep.EndpointType = [Microsoft.SqlServer.Management.SMO.EndpointType]::DatabaseMirroring  
$ep.Protocol.Http.SslPort = 5024  
$ep.Protocol.Tcp.ListenerPort = 6666 #inline comment  
$ep.Payload.DatabaseMirroring.ServerMirroringRole = [Microsoft.SqlServer.Management.SMO.ServerMirroringRole]::All  
  
# Create the endpoint on the instance  
$ep.Create()  
  
# Start the endpoint  
$ep.Start()  
  
# Report its state  
$ep.EndpointState;  
```  
  
## <a name="see-also"></a><span data-ttu-id="355f5-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="355f5-137">See Also</span></span>  
 [<span data-ttu-id="355f5-138">Конечная точка зеркального отображения базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="355f5-138">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](../../../database-engine/database-mirroring/the-database-mirroring-endpoint-sql-server.md)  
