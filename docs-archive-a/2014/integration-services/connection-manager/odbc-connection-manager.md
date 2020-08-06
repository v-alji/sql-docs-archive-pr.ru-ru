---
title: Диспетчер соединений ODBC | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], ODBC
- ODBC connection manager
- data sources [Integration Services], connections
- connection managers [Integration Services], ODBC
ms.assetid: e8c77aa7-6772-485e-918e-cef9eeb18c58
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e1069e31f3f8ffaf14dde091d913ff6d9f8fa7cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658345"
---
# <a name="odbc-connection-manager"></a><span data-ttu-id="caa82-102">диспетчер соединений ODBC</span><span class="sxs-lookup"><span data-stu-id="caa82-102">ODBC Connection Manager</span></span>
  <span data-ttu-id="caa82-103">Диспетчер соединений ODBC позволяет пакету подключаться к разнообразным системам управления базами данных, используя открытый интерфейс взаимодействия с базами данных (ODBC).</span><span class="sxs-lookup"><span data-stu-id="caa82-103">An ODBC connection manager enables a package to connect to a variety of database management systems using the Open Database Connectivity specification (ODBC).</span></span>  
  
 <span data-ttu-id="caa82-104">При добавлении подключения ODBC к пакету и задании свойств диспетчера соединений [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] создает диспетчер соединений и добавляет его в `Connections` коллекцию пакета.</span><span class="sxs-lookup"><span data-stu-id="caa82-104">When you add an ODBC connection to a package and set the connection manager properties, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager and adds the connection manager to the `Connections` collection of the package.</span></span> <span data-ttu-id="caa82-105">Во время выполнения диспетчер соединений рассматривается как физическое соединение с ODBC.</span><span class="sxs-lookup"><span data-stu-id="caa82-105">At run time the connection manager is resolved as a physical ODBC connection.</span></span>  
  
 <span data-ttu-id="caa82-106">Свойству `ConnectionManagerType` диспетчера соединений присваивается значение `ODBC`.</span><span class="sxs-lookup"><span data-stu-id="caa82-106">The `ConnectionManagerType` property of the connection manager is set to `ODBC`.</span></span>  
  
 <span data-ttu-id="caa82-107">Настроить диспетчер соединений ODBC можно следующими способами:</span><span class="sxs-lookup"><span data-stu-id="caa82-107">You can configure the ODBC connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="caa82-108">Предоставить строку соединения, которая ссылается на пользовательское или системное имя источника данных.</span><span class="sxs-lookup"><span data-stu-id="caa82-108">Provide a connection string that references a user or system data source name.</span></span>  
  
-   <span data-ttu-id="caa82-109">Указать сервер, к которому нужно подключиться.</span><span class="sxs-lookup"><span data-stu-id="caa82-109">Specify the server to connect to.</span></span>  
  
-   <span data-ttu-id="caa82-110">Указать, сохранять ли соединение во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="caa82-110">Indicate whether the connection is retained at run time.</span></span>  
  
## <a name="configuration-of-the-odbc-connection-manager"></a><span data-ttu-id="caa82-111">Настройка диспетчера соединений ODBC</span><span class="sxs-lookup"><span data-stu-id="caa82-111">Configuration of the ODBC Connection Manager</span></span>  
 <span data-ttu-id="caa82-112">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="caa82-112">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="caa82-113">Дополнительные сведения о свойствах, которые можно задать в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] , см. в одном из последующих разделов.</span><span class="sxs-lookup"><span data-stu-id="caa82-113">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topic:</span></span>  
  
-   [<span data-ttu-id="caa82-114">Справочник по пользовательскому интерфейсу диспетчера подключений ODBC</span><span class="sxs-lookup"><span data-stu-id="caa82-114">ODBC Connection Manager UI Reference</span></span>](../odbc-connection-manager-ui-reference.md)  
  
 <span data-ttu-id="caa82-115">Дополнительные сведения о программной настройке диспетчера подключений см. в разделах <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> и [Добавление соединений программным образом](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="caa82-115">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caa82-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="caa82-116">See Also</span></span>  
 [<span data-ttu-id="caa82-117">Соединения в службах Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="caa82-117">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
