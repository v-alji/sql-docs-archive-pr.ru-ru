---
title: Соединение с экземпляром SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server Management Objects, connections
- connections [SMO]
- instances of SQL Server, connections
- SMO [SQL Server], connections
ms.assetid: ad3cf354-b2e3-468b-b986-1232e375fd84
author: stevestein
ms.author: sstein
ms.openlocfilehash: efc21451f4a876c6edfe4a2389ca937d11bc5c8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668216"
---
# <a name="connecting-to-an-instance-of-sql-server"></a><span data-ttu-id="d5284-102">Соединение с экземпляром SQL Server</span><span class="sxs-lookup"><span data-stu-id="d5284-102">Connecting to an Instance of SQL Server</span></span>
  <span data-ttu-id="d5284-103">Первым шагом программирования в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] приложении управляющих объектов является создание экземпляра <xref:Microsoft.SqlServer.Management.Smo.Server> объекта и установка его соединения с экземпляром [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5284-103">The first programming step in a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) application is to create an instance of the <xref:Microsoft.SqlServer.Management.Smo.Server> object and to establish its connection to an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="d5284-104">Создать экземпляр <xref:Microsoft.SqlServer.Management.Smo.Server> и установить соединение с экземпляром [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] можно тремя способами.</span><span class="sxs-lookup"><span data-stu-id="d5284-104">You can create an instance of the <xref:Microsoft.SqlServer.Management.Smo.Server> object and establish a connection to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in three ways.</span></span> <span data-ttu-id="d5284-105">Первый способ — использовать переменную объекта <xref:Microsoft.SqlServer.Management.Common.ServerConnection> для задания информации о соединении.</span><span class="sxs-lookup"><span data-stu-id="d5284-105">The first is using a <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object variable to provide the connection information.</span></span> <span data-ttu-id="d5284-106">Второй способ — задать информацию о соединении в явном виде, присвоив соответствующие значения свойствам объекта <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="d5284-106">The second is to provide the connection information by explicitly setting the <xref:Microsoft.SqlServer.Management.Smo.Server> object properties.</span></span> <span data-ttu-id="d5284-107">Третий способ — передать имя экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в конструктор объекта <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="d5284-107">The third is to pass the name of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance in the <xref:Microsoft.SqlServer.Management.Smo.Server> object constructor.</span></span>  
  
 <span data-ttu-id="d5284-108">**Использование объекта ServerConnection**</span><span class="sxs-lookup"><span data-stu-id="d5284-108">**Using a ServerConnection object**</span></span>  
  
 <span data-ttu-id="d5284-109">Преимущество использования переменной объекта <xref:Microsoft.SqlServer.Management.Common.ServerConnection> в том, что заданную информацию о соединении можно применять многократно.</span><span class="sxs-lookup"><span data-stu-id="d5284-109">The advantage of using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object variable is that the connection information can be reused.</span></span> <span data-ttu-id="d5284-110">Объявите переменную объекта <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="d5284-110">Declare a <xref:Microsoft.SqlServer.Management.Smo.Server> object variable.</span></span> <span data-ttu-id="d5284-111">Затем объявите объект <xref:Microsoft.SqlServer.Management.Common.ServerConnection> и задайте для его свойств значения информации соединения, такие как имя экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] и режим проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="d5284-111">Then, declare a <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object and set properties with connection information such as the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], and the authentication mode.</span></span> <span data-ttu-id="d5284-112">Затем передайте переменную объекта <xref:Microsoft.SqlServer.Management.Common.ServerConnection> в качестве параметра конструктору объекта <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="d5284-112">Then, pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object variable as a parameter to the <xref:Microsoft.SqlServer.Management.Smo.Server> object constructor.</span></span> <span data-ttu-id="d5284-113">Не рекомендуется использование одного соединения несколькими серверными объектами одновременно.</span><span class="sxs-lookup"><span data-stu-id="d5284-113">It is not recommended to share connections between different server objects at the same time.</span></span> <span data-ttu-id="d5284-114">Чтобы получить копию настроек существующего соединения, вызовите метод <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A>.</span><span class="sxs-lookup"><span data-stu-id="d5284-114">Use the <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> method to get a copy of the existing connection settings.</span></span>  
  
 <span data-ttu-id="d5284-115">**Настройка свойств серверного объекта в явном виде**</span><span class="sxs-lookup"><span data-stu-id="d5284-115">**Setting Server object properties explicitly**</span></span>  
  
 <span data-ttu-id="d5284-116">Другая возможность — объявить переменную объекта <xref:Microsoft.SqlServer.Management.Smo.Server> и вызвать конструктор по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d5284-116">Alternatively, you can declare the <xref:Microsoft.SqlServer.Management.Smo.Server> object variable and call the default constructor.</span></span> <span data-ttu-id="d5284-117">Объект <xref:Microsoft.SqlServer.Management.Smo.Server> попытается соединиться с экземпляром по умолчанию [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], используя все настройки соединения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d5284-117">As is, the <xref:Microsoft.SqlServer.Management.Smo.Server> object tries to connect to the default instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with all the default connection settings.</span></span>  
  
 <span data-ttu-id="d5284-118">**Передача имени экземпляра SQL Server в конструктор объекта Server**</span><span class="sxs-lookup"><span data-stu-id="d5284-118">**Providing the SQL Server instance name in the Server object constructor**</span></span>  
  
 <span data-ttu-id="d5284-119">Объявите переменную объекта <xref:Microsoft.SqlServer.Management.Smo.Server> и передайте имя экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в качестве строкового параметра конструктору объекта.</span><span class="sxs-lookup"><span data-stu-id="d5284-119">Declare the <xref:Microsoft.SqlServer.Management.Smo.Server> object variable and pass the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance name as a string parameter in the constructor.</span></span> <span data-ttu-id="d5284-120">Объект <xref:Microsoft.SqlServer.Management.Smo.Server> установит соединение с экземпляром [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], используя значения настроек по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d5284-120">The <xref:Microsoft.SqlServer.Management.Smo.Server> object establishes a connection with the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with the default connection settings.</span></span>  
  
## <a name="connection-pooling"></a><span data-ttu-id="d5284-121">Объединение подключений в пул</span><span class="sxs-lookup"><span data-stu-id="d5284-121">Connection Pooling</span></span>  
 <span data-ttu-id="d5284-122">Вызов метода <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> объекта <xref:Microsoft.SqlServer.Management.Common.ServerConnection> обычно не требуется.</span><span class="sxs-lookup"><span data-stu-id="d5284-122">It is typically not required to call the <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> method of the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span> <span data-ttu-id="d5284-123">SMO автоматически установит соединение, когда это потребуется, и освободит его, передав в пул соединений, после завершения операций.</span><span class="sxs-lookup"><span data-stu-id="d5284-123">SMO will automatically establish a connection when required, and release the connection to the connection pool after it has finished performing operations.</span></span> <span data-ttu-id="d5284-124">При вызове метода <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> соединение не передается в пул.</span><span class="sxs-lookup"><span data-stu-id="d5284-124">When the <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> method is called, the connection is not released to the pool.</span></span> <span data-ttu-id="d5284-125">Для освобождения соединения и его передачи в пул нужен явный вызов метода <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A>.</span><span class="sxs-lookup"><span data-stu-id="d5284-125">An explicit call to the <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A> method is required to release the connection to the pool.</span></span> <span data-ttu-id="d5284-126">Кроме этого, можно запросить соединение не из пула, установив свойство <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> объекта <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="d5284-126">Additionally, you can request a non-pooled connection by setting the <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> property of the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
## <a name="multithreaded-applications"></a><span data-ttu-id="d5284-127">Многопоточные приложения</span><span class="sxs-lookup"><span data-stu-id="d5284-127">Multithreaded Applications</span></span>  
 <span data-ttu-id="d5284-128">Для многопоточных приложений в каждом потоке должен использоваться отдельный объект <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="d5284-128">For multithreaded applications, a separate <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object should be used in each thread.</span></span>  
  
## <a name="connecting-to-an-instance-of-sql-server-for-rmo"></a><span data-ttu-id="d5284-129">Соединение с экземпляром SQL Server для RMO</span><span class="sxs-lookup"><span data-stu-id="d5284-129">Connecting to an Instance of SQL Server for RMO</span></span>  
 <span data-ttu-id="d5284-130">Объекты RMO используют несколько отличный от SMO подход для соединения с сервером репликации.</span><span class="sxs-lookup"><span data-stu-id="d5284-130">Replication Management Objects (RMO) uses a slightly different method from SMO to connect to a replication server.</span></span>  
  
 <span data-ttu-id="d5284-131">Программные объекты RMO требуют, чтобы соединение с экземпляром [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] производилось с помощью объекта <xref:Microsoft.SqlServer.Management.Common.ServerConnection>, реализованного в пространстве имен `Microsoft.SqlServer.Management.Common`.</span><span class="sxs-lookup"><span data-stu-id="d5284-131">RMO programming objects require that a connection to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is made by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object implemented by the `Microsoft.SqlServer.Management.Common` namespace.</span></span> <span data-ttu-id="d5284-132">Это соединение с сервером производится независимо от программного объекта RMO.</span><span class="sxs-lookup"><span data-stu-id="d5284-132">This connection to the server is made independently of an RMO programming object.</span></span> <span data-ttu-id="d5284-133">Затем оно передается объекту RMO либо во время создания экземпляра, либо присвоением его свойству <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> объекта.</span><span class="sxs-lookup"><span data-stu-id="d5284-133">It is then it is passed to the RMO object either during instance creation or by assignment to the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property of the object.</span></span> <span data-ttu-id="d5284-134">Это позволяет создать экземпляр объекта программирования RMO независимо от объекта соединения и разделить задачи их управления. Один объект соединения можно использовать с несколькими объектами программирования RMO.</span><span class="sxs-lookup"><span data-stu-id="d5284-134">In this manner, an RMO programming object and the connection object instances can be created and managed separately, and a single connection object can be reused with multiple RMO programming objects.</span></span> <span data-ttu-id="d5284-135">Для соединений с сервером репликации действуют следующие правила.</span><span class="sxs-lookup"><span data-stu-id="d5284-135">The following rules apply for connections to a replication server:</span></span>  
  
-   <span data-ttu-id="d5284-136">Все свойства соединения определяются для конкретного объекта <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="d5284-136">All properties for the connection are defined for a specified <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
-   <span data-ttu-id="d5284-137">Каждое соединение с экземпляром [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]  должно иметь свой собственный объект <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="d5284-137">Each connection to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] must have its own <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
-   <span data-ttu-id="d5284-138">Все данные проверки подлинности, необходимые для установления соединения и входа на сервер, передаются в объекте <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="d5284-138">All authentication information to make the connection and successfully log on to the server is supplied in the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
-   <span data-ttu-id="d5284-139">По умолчанию соединения устанавливаются с использованием проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="d5284-139">By default, connections are made by using Microsoft Windows Authentication.</span></span> <span data-ttu-id="d5284-140">Для использования проверки подлинности [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] свойство <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.LoginSecure%2A> должно иметь значение False, а свойства <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.Login%2A> и <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.Password%2A> должны содержать в качестве значений действующие имя пользователя и пароль [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5284-140">To use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.LoginSecure%2A> must be set to False and <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.Login%2A> and <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.Password%2A> must be set to a valid [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logon and password.</span></span> <span data-ttu-id="d5284-141">Учетные данные безопасности нужно всегда защищать от возможного несанкционированного доступа и по возможности вводить только во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d5284-141">Security credentials must always be stored and handled securely, and supplied at run time whenever possible.</span></span>  
  
-   <span data-ttu-id="d5284-142">До передачи соединения любому объекту программирования RMO следует вызвать метод <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A>.</span><span class="sxs-lookup"><span data-stu-id="d5284-142">The <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> method must be called before passing the connection to any RMO programming object.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="d5284-143">Примеры</span><span class="sxs-lookup"><span data-stu-id="d5284-143">Examples</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="connecting-to-the-local-instance-of-sql-server-by-using-windows-authentication-in-visual-basic"></a><span data-ttu-id="d5284-144">Соединение с локальным экземпляром SQL Server с использованием проверки подлинности Windows на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d5284-144">Connecting to the Local Instance of SQL Server by Using Windows Authentication in Visual Basic</span></span>  
 <span data-ttu-id="d5284-145">Для соединения с локальным экземпляром [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] не нужно писать много программного кода.</span><span class="sxs-lookup"><span data-stu-id="d5284-145">Connecting to the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does not require much code.</span></span> <span data-ttu-id="d5284-146">Вместо этого для метода проверки подлинности и сервера используются настройки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d5284-146">Instead, it relies on default settings for authentication method and server.</span></span> <span data-ttu-id="d5284-147">Первая операция, требующая получения данных, вызовет создание соединения.</span><span class="sxs-lookup"><span data-stu-id="d5284-147">The first operation that requires data to be retrieved will cause a connection to be created.</span></span>  
  
 <span data-ttu-id="d5284-148">В этом примере используется [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] код .NET, который подключается к локальному экземпляру с [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] помощью проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="d5284-148">This example is [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET code that connects to the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VB1](SMO How to#SMO_VB1)]  -->  
  
## <a name="connecting-to-the-local-instance-of-sql-server-by-using-windows-authentication-in-visual-c"></a><span data-ttu-id="d5284-149">Соединение с локальным экземпляром SQL Server с использованием проверки подлинности Windows на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="d5284-149">Connecting to the Local Instance of SQL Server by Using Windows Authentication in Visual C#</span></span>  
 <span data-ttu-id="d5284-150">Для соединения с локальным экземпляром [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] не нужно писать много программного кода.</span><span class="sxs-lookup"><span data-stu-id="d5284-150">Connecting to the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does not require much code.</span></span> <span data-ttu-id="d5284-151">Вместо этого для метода проверки подлинности и сервера используются настройки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d5284-151">Instead, it relies on default settings for authentication method and server.</span></span> <span data-ttu-id="d5284-152">Первая операция, требующая получения данных, вызовет создание соединения.</span><span class="sxs-lookup"><span data-stu-id="d5284-152">The first operation that requires data to be retrieved will cause a connection to be created.</span></span>  
  
 <span data-ttu-id="d5284-153">Этот пример представляет собой программный код на языке Visual C# .NET, который производит подключение к локальному экземпляру [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] с использованием проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="d5284-153">This example is Visual C# .NET code that connects to the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//The connection is established when a property is requested.   
Console.WriteLine(srv.Information.Version);   
}   
//The connection is automatically disconnected when the Server variable goes out of scope.  
```  
  
## <a name="connecting-to-a-remote-instance-of-sql-server-by-using-windows-authentication-in-visual-basic"></a><span data-ttu-id="d5284-154">Соединение с удаленным экземпляром SQL Server с использованием проверки подлинности Windows на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d5284-154">Connecting to a Remote Instance of SQL Server by Using Windows Authentication in Visual Basic</span></span>  
 <span data-ttu-id="d5284-155">При подключении к экземпляру [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] с использованием проверки подлинности Windows указывать тип проверки не нужно.</span><span class="sxs-lookup"><span data-stu-id="d5284-155">When you connect to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication, you do not have to specify the authentication type.</span></span> <span data-ttu-id="d5284-156">По умолчанию используется проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="d5284-156">Windows Authentication is the default.</span></span>  
  
 <span data-ttu-id="d5284-157">В этом примере используется [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] код .NET, который подключается к удаленному экземпляру [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] с помощью проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="d5284-157">This example is [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET code that connects to the remote instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication.</span></span> <span data-ttu-id="d5284-158">Строковая переменная *стрсервер* содержит имя удаленного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="d5284-158">The string variable *strServer* contains the name of the remote instance.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VB2](SMO How to#SMO_VB2)]  -->  
  
## <a name="connecting-to-a-remote-instance-of-sql-server-by-using-windows-authentication-in-visual-c"></a><span data-ttu-id="d5284-159">Соединение с удаленным экземпляром SQL Server с использованием проверки подлинности Windows на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="d5284-159">Connecting to a Remote Instance of SQL Server by Using Windows Authentication in Visual C#</span></span>  
 <span data-ttu-id="d5284-160">При подключении к экземпляру [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] с использованием проверки подлинности Windows указывать тип проверки не нужно.</span><span class="sxs-lookup"><span data-stu-id="d5284-160">When you connect to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication, you do not have to specify the authentication type.</span></span> <span data-ttu-id="d5284-161">По умолчанию используется проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="d5284-161">Windows Authentication is the default.</span></span>  
  
 <span data-ttu-id="d5284-162">Этот пример представляет собой программный код на языке Visual C# .NET, который производит подключение к удаленному экземпляру [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] с использованием проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="d5284-162">This example is Visual C# .NET code that connects to the remote instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication.</span></span> <span data-ttu-id="d5284-163">Строковая переменная *стрсервер* содержит имя удаленного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="d5284-163">The string variable *strServer* contains the name of the remote instance.</span></span>  
  
```  
{   
//Connect to a remote instance of SQL Server.   
Server srv;   
//The strServer string variable contains the name of a remote instance of SQL Server.   
srv = new Server(strServer);   
//The actual connection is made when a property is retrieved.   
Console.WriteLine(srv.Information.Version);   
}   
//The connection is automatically disconnected when the Server variable goes out of scope.  
```  
  
## <a name="connecting-to-an-instance-of-sql-server-by-using-sql-server-authentication-in-visual-basic"></a><span data-ttu-id="d5284-164">Соединение с экземпляром SQL Server с использованием проверки подлинности SQL Server на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d5284-164">Connecting to an Instance of SQL Server by Using SQL Server Authentication in Visual Basic</span></span>  
 <span data-ttu-id="d5284-165">При подключении к экземпляру [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] с использованием проверки подлинности [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] нужно указывать тип проверки.</span><span class="sxs-lookup"><span data-stu-id="d5284-165">When you connect to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, you must specify the authentication type.</span></span> <span data-ttu-id="d5284-166">В данном примере демонстрируется альтернативный метод объявления переменной объекта <xref:Microsoft.SqlServer.Management.Common.ServerConnection>, позволяющий повторно использовать информацию соединения.</span><span class="sxs-lookup"><span data-stu-id="d5284-166">This example demonstrates the alternative method of declaring a <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object variable, which enables the connection information to be reused.</span></span>  
  
 <span data-ttu-id="d5284-167">В примере используется [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] код .NET, демонстрирующий, как соединиться с удаленным и *впассворд* содержит имя входа и пароль.</span><span class="sxs-lookup"><span data-stu-id="d5284-167">The example is [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET code that demonstrates how to connect to the remote and *vPassword* contain the logon and password.</span></span>  
  
```  
' compile with:   
' /r:Microsoft.SqlServer.Smo.dll  
' /r:Microsoft.SqlServer.ConnectionInfo.dll  
' /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll   
  
Imports Microsoft.SqlServer.Management.Smo  
Imports Microsoft.SqlServer.Management.Common  
  
Public Class A  
   Public Shared Sub Main()  
      Dim sqlServerLogin As [String] = "user_id"  
      Dim password As [String] = "pwd"  
      Dim instanceName As [String] = "instance_name"  
      Dim remoteSvrName As [String] = "remote_server_name"  
  
      ' Connecting to an instance of SQL Server using SQL Server Authentication  
      Dim srv1 As New Server()   ' connects to default instance  
      srv1.ConnectionContext.LoginSecure = False   ' set to true for Windows Authentication  
      srv1.ConnectionContext.Login = sqlServerLogin  
      srv1.ConnectionContext.Password = password  
      Console.WriteLine(srv1.Information.Version)   ' connection is established  
  
      ' Connecting to a named instance of SQL Server with SQL Server Authentication using ServerConnection  
      Dim srvConn As New ServerConnection()  
      srvConn.ServerInstance = ".\" & instanceName   ' connects to named instance  
      srvConn.LoginSecure = False   ' set to true for Windows Authentication  
      srvConn.Login = sqlServerLogin  
      srvConn.Password = password  
      Dim srv2 As New Server(srvConn)  
      Console.WriteLine(srv2.Information.Version)   ' connection is established  
  
      ' For remote connection, remote server name / ServerInstance needs to be specified  
      Dim srvConn2 As New ServerConnection(remoteSvrName)  
      srvConn2.LoginSecure = False  
      srvConn2.Login = sqlServerLogin  
      srvConn2.Password = password  
      Dim srv3 As New Server(srvConn2)  
      Console.WriteLine(srv3.Information.Version)   ' connection is established  
   End Sub  
End Class  
```  
  
## <a name="connecting-to-an-instance-of-sql-server-by-using-sql-server-authentication-in-visual-c"></a><span data-ttu-id="d5284-168">Соединение с экземпляром SQL Server с использованием проверки подлинности SQL Server на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="d5284-168">Connecting to an Instance of SQL Server by Using SQL Server Authentication in Visual C#</span></span>  
 <span data-ttu-id="d5284-169">При подключении к экземпляру [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] с использованием проверки подлинности [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] нужно указывать тип проверки.</span><span class="sxs-lookup"><span data-stu-id="d5284-169">When you connect to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, you must specify the authentication type.</span></span> <span data-ttu-id="d5284-170">В данном примере демонстрируется альтернативный метод объявления переменной объекта <xref:Microsoft.SqlServer.Management.Common.ServerConnection>, позволяющий повторно использовать информацию соединения.</span><span class="sxs-lookup"><span data-stu-id="d5284-170">This example demonstrates the alternative method of declaring a <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object variable, which enables the connection information to be reused.</span></span>  
  
 <span data-ttu-id="d5284-171">В примере используется код Visual C# .NET, демонстрирующий, как подключиться к удаленному и *впассворду* , содержащему имя входа и пароль.</span><span class="sxs-lookup"><span data-stu-id="d5284-171">The example is Visual C# .NET code that demonstrates how to connect to the remote and *vPassword* contain the logon and password.</span></span>  
  
```  
// compile with:   
// /r:Microsoft.SqlServer.Smo.dll  
// /r:Microsoft.SqlServer.ConnectionInfo.dll  
// /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll   
  
using System;  
using Microsoft.SqlServer.Management.Smo;  
using Microsoft.SqlServer.Management.Common;  
  
public class A {  
   public static void Main() {   
      String sqlServerLogin = "user_id";  
      String password = "pwd";  
      String instanceName = "instance_name";  
      String remoteSvrName = "remote_server_name";  
  
      // Connecting to an instance of SQL Server using SQL Server Authentication  
      Server srv1 = new Server();   // connects to default instance  
      srv1.ConnectionContext.LoginSecure = false;   // set to true for Windows Authentication  
      srv1.ConnectionContext.Login = sqlServerLogin;  
      srv1.ConnectionContext.Password = password;  
      Console.WriteLine(srv1.Information.Version);   // connection is established  
  
      // Connecting to a named instance of SQL Server with SQL Server Authentication using ServerConnection  
      ServerConnection srvConn = new ServerConnection();  
      srvConn.ServerInstance = @".\" + instanceName;   // connects to named instance  
      srvConn.LoginSecure = false;   // set to true for Windows Authentication  
      srvConn.Login = sqlServerLogin;  
      srvConn.Password = password;  
      Server srv2 = new Server(srvConn);  
      Console.WriteLine(srv2.Information.Version);   // connection is established  
  
      // For remote connection, remote server name / ServerInstance needs to be specified  
      ServerConnection srvConn2 = new ServerConnection(remoteSvrName);  
      srvConn2.LoginSecure = false;  
      srvConn2.Login = sqlServerLogin;  
      srvConn2.Password = password;  
      Server srv3 = new Server(srvConn2);  
      Console.WriteLine(srv3.Information.Version);   // connection is established  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="d5284-172">См. также:</span><span class="sxs-lookup"><span data-stu-id="d5284-172">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.Server>   
 <xref:Microsoft.SqlServer.Management.Common.ServerConnection>  
  
  
