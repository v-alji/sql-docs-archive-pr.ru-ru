---
title: Использование связанных серверов в SMO | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- linked servers [SQL Server], SMO
ms.assetid: 0ea8837b-2596-4df1-b065-3bb717c9f22c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 58804e2be1edfa685a57f56c173c77a50e0f9126
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655578"
---
# <a name="using-linked-servers-in-smo"></a><span data-ttu-id="3a87a-102">Использование связанных серверов в объектах SMO</span><span class="sxs-lookup"><span data-stu-id="3a87a-102">Using Linked Servers in SMO</span></span>
  <span data-ttu-id="3a87a-103">Связанный сервер представляет источник данных OLE DB на удаленном сервере.</span><span class="sxs-lookup"><span data-stu-id="3a87a-103">A linked server represents an OLE DB data source on a remote server.</span></span> <span data-ttu-id="3a87a-104">Удаленные источники данных OLE DB связываются с экземпляром [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] при помощи объекта <xref:Microsoft.SqlServer.Management.Smo.LinkedServer>.</span><span class="sxs-lookup"><span data-stu-id="3a87a-104">Remote OLE DB data sources are linked to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using the <xref:Microsoft.SqlServer.Management.Smo.LinkedServer> object.</span></span>  
  
 <span data-ttu-id="3a87a-105">Удаленные серверы баз данных могут быть связаны с текущим экземпляром с [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] помощью поставщика OLE DB.</span><span class="sxs-lookup"><span data-stu-id="3a87a-105">Remote database servers can be linked to the current instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using an OLE DB Provider.</span></span> <span data-ttu-id="3a87a-106">В SMO связанные серверы представлены объектом <xref:Microsoft.SqlServer.Management.Smo.LinkedServer>.</span><span class="sxs-lookup"><span data-stu-id="3a87a-106">In SMO, linked servers are represented by the <xref:Microsoft.SqlServer.Management.Smo.LinkedServer> object.</span></span> <span data-ttu-id="3a87a-107">Свойство <xref:Microsoft.SqlServer.Management.Smo.LinkedServer.LinkedServerLogins%2A> указывает на коллекцию объектов <xref:Microsoft.SqlServer.Management.Smo.LinkedServerLogin>.</span><span class="sxs-lookup"><span data-stu-id="3a87a-107">The <xref:Microsoft.SqlServer.Management.Smo.LinkedServer.LinkedServerLogins%2A> property references a collection of <xref:Microsoft.SqlServer.Management.Smo.LinkedServerLogin> objects.</span></span> <span data-ttu-id="3a87a-108">В них хранятся учетные данные входа, требуемые для установления соединения со связанным сервером.</span><span class="sxs-lookup"><span data-stu-id="3a87a-108">These store the logon credentials that are required to establish a connection with the linked server.</span></span>  
  
## <a name="ole-db-providers"></a><span data-ttu-id="3a87a-109">Поставщики OLE DB</span><span class="sxs-lookup"><span data-stu-id="3a87a-109">OLE-DB Providers</span></span>  
 <span data-ttu-id="3a87a-110">В SMO установленные поставщики OLE DB представлены коллекцией объектов <xref:Microsoft.SqlServer.Management.Smo.OleDbProviderSettings>.</span><span class="sxs-lookup"><span data-stu-id="3a87a-110">In SMO, installed OLE-DB providers are represented by a collection of <xref:Microsoft.SqlServer.Management.Smo.OleDbProviderSettings> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a87a-111">Пример</span><span class="sxs-lookup"><span data-stu-id="3a87a-111">Example</span></span>  
 <span data-ttu-id="3a87a-112">В следующем примере кода для создания приложения необходимо выбрать среду программирования, шаблон программирования и язык программирования.</span><span class="sxs-lookup"><span data-stu-id="3a87a-112">For the following code example, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="3a87a-113">Дополнительные сведения см. в статьях [Создание проекта Visual Basic SMO в Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) и [Создание проекта Visual C&#35; SMO в Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="3a87a-113">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-a-link-to-an-ole-db-provider-server-in-visual-basic"></a><span data-ttu-id="3a87a-114">Создание ссылки на сервер поставщика OLE-DB в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3a87a-114">Creating a link to an OLE-DB Provider Server in Visual Basic</span></span>  
 <span data-ttu-id="3a87a-115">Пример кода показывает, как создать ссылку на разнородный источник данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] OLE DB с помощью объекта <xref:Microsoft.SqlServer.Management.Smo.LinkedServer>.</span><span class="sxs-lookup"><span data-stu-id="3a87a-115">The code example shows how to create a link to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] OLE DB, heterogeneous data source by using the <xref:Microsoft.SqlServer.Management.Smo.LinkedServer> object.</span></span> <span data-ttu-id="3a87a-116">Указав в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] качестве имени продукта, доступ к данным на связанном сервере осуществляется с помощью [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] поставщика OLE DB клиента, который является официальным поставщиком OLE DB для [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3a87a-116">By specifying [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as the product name, data is accessed on the linked server by using the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Client OLE DB Provider, which is the official OLE DB provider for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBLinkedServers1](SMO How to#SMO_VBLinkedServers1)]  -->  
  
## <a name="creating-a-link-to-an-ole-db-provider-server-in-visual-c"></a><span data-ttu-id="3a87a-117">Создание ссылки на сервер поставщика OLE-DB в Visual C#</span><span class="sxs-lookup"><span data-stu-id="3a87a-117">Creating a link to an OLE-DB Provider Server in Visual C#</span></span>  
 <span data-ttu-id="3a87a-118">Пример кода показывает, как создать ссылку на разнородный источник данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] OLE DB с помощью объекта <xref:Microsoft.SqlServer.Management.Smo.LinkedServer>.</span><span class="sxs-lookup"><span data-stu-id="3a87a-118">The code example shows how to create a link to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] OLE DB, heterogeneous data source by using the <xref:Microsoft.SqlServer.Management.Smo.LinkedServer> object.</span></span> <span data-ttu-id="3a87a-119">Если в качестве названия продукта указан [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , то доступ к данным на связанном сервере осуществляется с помощью поставщика OLE DB для клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , являющегося официальным поставщиком OLE DB для [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a87a-119">By specifying [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as the product name, data is accessed on the linked server by using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Client OLE DB Provider, which is the official OLE DB provider for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
```csharp
//Connect to the local, default instance of SQL Server.   
{   
   Server srv = new Server();   
   //Create a linked server.   
   LinkedServer lsrv = default(LinkedServer);   
   lsrv = new LinkedServer(srv, "OLEDBSRV");   
   //When the product name is SQL Server the remaining properties are   
   //not required to be set.   
   lsrv.ProductName = "SQL Server";   
   lsrv.Create();   
}   
```  
  
## <a name="creating-a-link-to-an-ole-db-provider-server-in-powershell"></a><span data-ttu-id="3a87a-120">Создание ссылки на сервер поставщика OLE-DB в PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a87a-120">Creating a link to an OLE-DB Provider Server in PowerShell</span></span>  
 <span data-ttu-id="3a87a-121">Пример кода показывает, как создать ссылку на разнородный источник данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] OLE DB с помощью объекта <xref:Microsoft.SqlServer.Management.Smo.LinkedServer>.</span><span class="sxs-lookup"><span data-stu-id="3a87a-121">The code example shows how to create a link to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] OLE DB, heterogeneous data source by using the <xref:Microsoft.SqlServer.Management.Smo.LinkedServer> object.</span></span> <span data-ttu-id="3a87a-122">Если в качестве названия продукта указан [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , то доступ к данным на связанном сервере осуществляется с помощью поставщика OLE DB для клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , являющегося официальным поставщиком OLE DB для [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a87a-122">By specifying [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as the product name, data is accessed on the linked server by using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Client OLE DB Provider, which is the official OLE DB provider for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance  
$svr = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
  
#Create a linked server object which corresponds to an OLEDB type of SQL server product  
$lsvr = New-Object -TypeName Microsoft.SqlServer.Management.SMO.LinkedServer -ArgumentList $svr,"OLEDBSRV"  
  
#When the product name is SQL Server the remaining properties are not required to be set.
$lsvr.ProductName = "SQL Server"
  
#Create the Database Object  
$lsvr.Create()
```  
