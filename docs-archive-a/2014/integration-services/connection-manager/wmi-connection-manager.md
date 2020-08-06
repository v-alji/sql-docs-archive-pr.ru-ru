---
title: Диспетчер WMI-соединений | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], WMI
- connection managers [Integration Services], WMI
- WMI connection manager [Integration Services]
ms.assetid: fbfa4ba7-3d0d-4d6b-94ad-50741a88d03d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f15aefb0ed112f1d5b7bb05421750b6689a11339
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665081"
---
# <a name="wmi-connection-manager"></a><span data-ttu-id="3e9bf-102">Диспетчер WMI-соединений</span><span class="sxs-lookup"><span data-stu-id="3e9bf-102">WMI Connection Manager</span></span>
  <span data-ttu-id="3e9bf-103">Диспетчер WMI-соединений позволяет использовать в пакетах службу инструментария управления Windows (WMI) для управления данными в корпоративной среде.</span><span class="sxs-lookup"><span data-stu-id="3e9bf-103">A WMI connection manager enables a package to use Windows Management Instrumentation (WMI) to manage information in an enterprise environment.</span></span> <span data-ttu-id="3e9bf-104">Задача "Веб-служба", которую включают в себя службы [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], использует диспетчер WMI-соединений.</span><span class="sxs-lookup"><span data-stu-id="3e9bf-104">The Web Service task that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses a WMI connection manager.</span></span>  
  
 <span data-ttu-id="3e9bf-105">При добавлении диспетчера WMI-соединений к пакету [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] создает диспетчер соединений, который будет разрешаться в WMI-соединение во время выполнения, устанавливает свойства диспетчера соединений и добавляет его в `Connections` коллекцию пакета.</span><span class="sxs-lookup"><span data-stu-id="3e9bf-105">When you add a WMI connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to a WMI connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span> <span data-ttu-id="3e9bf-106">Свойству `ConnectionManagerType` диспетчера соединений присваивается значение `WMI`.</span><span class="sxs-lookup"><span data-stu-id="3e9bf-106">The `ConnectionManagerType` property of the connection manager is set to `WMI`.</span></span>  
  
## <a name="configuration-of-the-wmi-connection-manager"></a><span data-ttu-id="3e9bf-107">Настройка диспетчера WMI-соединений</span><span class="sxs-lookup"><span data-stu-id="3e9bf-107">Configuration of the WMI Connection Manager</span></span>  
 <span data-ttu-id="3e9bf-108">Чтобы настроить диспетчер WMI-соединений, выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="3e9bf-108">You can configure a WMI connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="3e9bf-109">Задайте имя учетной записи.</span><span class="sxs-lookup"><span data-stu-id="3e9bf-109">Specify the name of a server.</span></span>  
  
-   <span data-ttu-id="3e9bf-110">Задайте пространство имен на сервере.</span><span class="sxs-lookup"><span data-stu-id="3e9bf-110">Specify a namespace on the server.</span></span>  
  
-   <span data-ttu-id="3e9bf-111">Выберите режим проверки подлинности для соединения с сервером.</span><span class="sxs-lookup"><span data-stu-id="3e9bf-111">Select the authentication mode for connecting to the server.</span></span>  
  
 <span data-ttu-id="3e9bf-112">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="3e9bf-112">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="3e9bf-113">Дополнительные сведения о свойствах, которые можно задавать в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] , см. в статье [Редактор диспетчера WMI-сеансов](../wmi-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="3e9bf-113">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [WMI Connection Manager Editor](../wmi-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="3e9bf-114">Дополнительные сведения о программной настройке диспетчера подключений см. в разделах <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> и [Добавление соединений программным образом](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="3e9bf-114">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e9bf-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="3e9bf-115">See Also</span></span>  
 <span data-ttu-id="3e9bf-116">[Задача «веб-служба»](../control-flow/web-service-task.md) </span><span class="sxs-lookup"><span data-stu-id="3e9bf-116">[Web Service Task](../control-flow/web-service-task.md) </span></span>  
 [<span data-ttu-id="3e9bf-117">Соединения в службах Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="3e9bf-117">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
