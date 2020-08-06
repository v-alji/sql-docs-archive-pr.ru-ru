---
title: Отключение от экземпляра SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server Management Objects, disconnecting
- SMO [SQL Server], disconnecting
- instances of SQL Server, disconnecting
- disconnecting [SMO]
ms.assetid: 4ca7f7eb-6b3f-4c73-ac63-88afa8570b61
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3514fce8fb8f1ccc8bd1b54acfa27825eaebbd34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668214"
---
# <a name="disconnecting-from-an-instance-of-sql-server"></a><span data-ttu-id="18632-102">Отсоединение от экземпляра SQL Server</span><span class="sxs-lookup"><span data-stu-id="18632-102">Disconnecting from an Instance of SQL Server</span></span>
  <span data-ttu-id="18632-103">Закрытие и отсоединение объектов SMO [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] вручную не требуется.</span><span class="sxs-lookup"><span data-stu-id="18632-103">Manually closing and disconnecting [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) objects is not required.</span></span> <span data-ttu-id="18632-104">Соединения открываются и закрываются по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="18632-104">Connections are opened and closed as required.</span></span>  
  
## <a name="connection-pooling"></a><span data-ttu-id="18632-105">Объединение подключений в пул</span><span class="sxs-lookup"><span data-stu-id="18632-105">Connection Pooling</span></span>  
 <span data-ttu-id="18632-106">Соединение не освобождается автоматически при вызове метода <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A>.</span><span class="sxs-lookup"><span data-stu-id="18632-106">When the <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> method is called, the connection is not automatically released.</span></span> <span data-ttu-id="18632-107">Чтобы освободить соединение обратно в пул, необходимо явно вызвать метод <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A>.</span><span class="sxs-lookup"><span data-stu-id="18632-107">The <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A> method must be called explicitly to release the connection to the connection pool.</span></span> <span data-ttu-id="18632-108">Можно также запросить соединение вне пула.</span><span class="sxs-lookup"><span data-stu-id="18632-108">Also, you can request a non-pooled connection.</span></span> <span data-ttu-id="18632-109">Это делается путем установки свойства <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> свойства <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A>, которое ссылается на объект <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="18632-109">You do this by setting the <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> property that references the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
## <a name="disconnecting-from-an-instance-of-sql-server-for-rmo"></a><span data-ttu-id="18632-110">Отсоединение от экземпляра SQL Server для объектов RMO</span><span class="sxs-lookup"><span data-stu-id="18632-110">Disconnecting from an Instance of SQL Server for RMO</span></span>  
 <span data-ttu-id="18632-111">При программировании с использованием объектов RMO закрытие серверных соединений немного отличается от закрытия при использовании объектов SMO.</span><span class="sxs-lookup"><span data-stu-id="18632-111">Closing server connections when you are programming with RMO works slightly different from SMO.</span></span>  
  
 <span data-ttu-id="18632-112">Поскольку соединение с сервером для объекта RMO поддерживается <xref:Microsoft.SqlServer.Management.Common.ServerConnection> объектом, этот объект также используется при отключении от экземпляра [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] при программировании с помощью RMO.</span><span class="sxs-lookup"><span data-stu-id="18632-112">Because the server connection for an RMO object is maintained by the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object, this object is also used when disconnecting from an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when you program by using RMO.</span></span> <span data-ttu-id="18632-113">Чтобы закрыть соединение с помощью объекта <xref:Microsoft.SqlServer.Management.Common.ServerConnection>, вызовите метод <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A> объекта RMO.</span><span class="sxs-lookup"><span data-stu-id="18632-113">To close a connection by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object, call the <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A> method of the RMO object.</span></span> <span data-ttu-id="18632-114">После закрытия соединения объекты RMO использовать нельзя.</span><span class="sxs-lookup"><span data-stu-id="18632-114">After the connection has been closed, RMO objects cannot be used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18632-115">Пример</span><span class="sxs-lookup"><span data-stu-id="18632-115">Example</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="closing-and-disconnecting-an-smo-object-in-visual-basic"></a><span data-ttu-id="18632-116">Закрытие и отсоединение объекта SMO на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="18632-116">Closing and Disconnecting an SMO Object in Visual Basic</span></span>  
 <span data-ttu-id="18632-117">Этот пример кода показывает, как запросить соединение вне пула, задав свойство <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> свойства объекта <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="18632-117">This code example shows how to request a non-pooled connection by setting the <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> object property.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VB4](SMO How to#SMO_VB4)]  -->  
  
## <a name="closing-and-disconnecting-an-smo-object-in-visual-c"></a><span data-ttu-id="18632-118">Закрытие и отсоединение объекта SMO на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="18632-118">Closing and Disconnecting an SMO Object in Visual C#</span></span>  
 <span data-ttu-id="18632-119">Этот пример кода показывает, как запросить соединение вне пула, задав свойство <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> свойства объекта <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="18632-119">This code example shows how to request a non-pooled connection by setting the <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> object property.</span></span>  
  
```  
{   
Server srv;   
srv = new Server();   
//Disable automatic disconnection.   
srv.ConnectionContext.AutoDisconnectMode = AutoDisconnectMode.NoAutoDisconnect;   
//Connect to the local, default instance of SQL Server.   
srv.ConnectionContext.Connect();   
//The actual connection is made when a property is retrieved.   
Console.WriteLine(srv.Information.Version);   
//Disconnect explicitly.   
srv.ConnectionContext.Disconnect();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="18632-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="18632-120">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.Server>   
 <xref:Microsoft.SqlServer.Management.Common.ServerConnection>  
  
  
