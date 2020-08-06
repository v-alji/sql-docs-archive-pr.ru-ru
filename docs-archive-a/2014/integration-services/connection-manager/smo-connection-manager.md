---
title: Диспетчер подключений SMO | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], SMO
- SMO connection manager
- connection managers [Integration Services], SMO
ms.assetid: d273f1fb-a6a8-4f2f-a5ff-55c2e3de4723
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 988eef214608399bc3ec483d9976c2f5d52acb2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750088"
---
# <a name="smo-connection-manager"></a><span data-ttu-id="463cd-102">SMO, диспетчер соединений</span><span class="sxs-lookup"><span data-stu-id="463cd-102">SMO Connection Manager</span></span>
  <span data-ttu-id="463cd-103">Диспетчер соединений SMO позволяет пакету подключиться к серверу SQL Management Object (SMO).</span><span class="sxs-lookup"><span data-stu-id="463cd-103">An SMO connection manager enables a package to connect to a SQL Management Object (SMO) server.</span></span> <span data-ttu-id="463cd-104">Задачи пересылки, включенные в службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], используют диспетчер соединений SMO.</span><span class="sxs-lookup"><span data-stu-id="463cd-104">The transfer tasks that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes use an SMO connection manager.</span></span> <span data-ttu-id="463cd-105">Например, задача «Передача имен входа», пересылающая данные для входа в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , использует диспетчер соединений SMO.</span><span class="sxs-lookup"><span data-stu-id="463cd-105">For example, the Transfer Logins task that transfers [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins uses an SMO connection manager.</span></span>  
  
 <span data-ttu-id="463cd-106">При добавлении диспетчера подключений SMO в пакет службы [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] создадут диспетчер соединений, который установит соединение SMO во время выполнения, задаст параметры диспетчера и добавит диспетчер в коллекцию `Connections` пакета.</span><span class="sxs-lookup"><span data-stu-id="463cd-106">When you add an SMO connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an SMO connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span> <span data-ttu-id="463cd-107">Свойству `ConnectionManagerType` диспетчера соединений присваивается значение `SMOServer`.</span><span class="sxs-lookup"><span data-stu-id="463cd-107">The `ConnectionManagerType` property of the connection manager is set to `SMOServer`.</span></span>  
  
 <span data-ttu-id="463cd-108">Можно настроить диспетчер соединений SMO следующим образом:</span><span class="sxs-lookup"><span data-stu-id="463cd-108">You can configure an SMO connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="463cd-109">Указать имя сервера, на котором установлен [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="463cd-109">Specify the name of a server on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed.</span></span>  
  
-   <span data-ttu-id="463cd-110">Выберите режим проверки подлинности для соединения с сервером.</span><span class="sxs-lookup"><span data-stu-id="463cd-110">Select the authentication mode for connecting to the server.</span></span>  
  
## <a name="configuration-of-the-smo-connection-manager"></a><span data-ttu-id="463cd-111">Настройка диспетчера соединений SMO</span><span class="sxs-lookup"><span data-stu-id="463cd-111">Configuration of the SMO Connection Manager</span></span>  
 <span data-ttu-id="463cd-112">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="463cd-112">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="463cd-113">Дополнительные сведения о свойствах, которые можно задавать в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] , см. в статье [Редактор диспетчера соединений SMO](../smo-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="463cd-113">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [SMO Connection Manager Editor](../smo-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="463cd-114">Дополнительные сведения о программной настройке диспетчера подключений см. в разделах <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> и [Добавление соединений программным образом](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="463cd-114">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="463cd-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="463cd-115">See Also</span></span>  
 [<span data-ttu-id="463cd-116">Соединения в службах Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="463cd-116">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
