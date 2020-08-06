---
title: Диспетчер подключений SQL Server Compact Edition | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Compact, connection manager
- connections [Integration Services], SQL Server Compact
- connection managers [Integration Services], SQL Server Compact
ms.assetid: ba627d4d-41f4-49fc-a921-f534cde67770
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5d4feb001cc7c0fd0bd8b6e60d5ab22b33ad2eb9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750084"
---
# <a name="sql-server-compact-edition-connection-manager"></a><span data-ttu-id="9e0d2-102">Диспетчер соединений SQL Server Compact Edition</span><span class="sxs-lookup"><span data-stu-id="9e0d2-102">SQL Server Compact Edition Connection Manager</span></span>
  <span data-ttu-id="9e0d2-103">Диспетчер соединений [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact позволяет пакету подключаться к базе данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="9e0d2-103">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact connection manager enables a package to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact database.</span></span> <span data-ttu-id="9e0d2-104">Целевое назначение [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact, содержащееся в службах [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], использует этот диспетчер соединений для загрузки данных в таблицы базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9e0d2-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses this connection manager to load data into a table in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9e0d2-105">На 64-разрядном компьютере пакеты, которые соединяются с источниками данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact, должны запускаться в 32-разрядном режиме.</span><span class="sxs-lookup"><span data-stu-id="9e0d2-105">On a 64-bit computer, you must run packages that connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact data sources in 32-bit mode.</span></span> <span data-ttu-id="9e0d2-106">Поставщик [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact, используемый службами [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] для соединения с источниками данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact, доступен только в 32-разрядной версии.</span><span class="sxs-lookup"><span data-stu-id="9e0d2-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact provider that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] uses to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact data sources is available only in a 32-bit version.</span></span>  
  
## <a name="configuration-the-sql-server-compact-edition-connection-manager"></a><span data-ttu-id="9e0d2-107">Настройка диспетчера соединений SQL Server Compact Edition</span><span class="sxs-lookup"><span data-stu-id="9e0d2-107">Configuration the SQL Server Compact Edition Connection Manager</span></span>  
 <span data-ttu-id="9e0d2-108">При добавлении [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] к пакету диспетчера соединений Compact [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] создает диспетчер соединений, который будет разрешаться в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] компактное соединение во время выполнения, устанавливает свойства диспетчера соединений и добавляет его в `Connections` коллекцию пакета.</span><span class="sxs-lookup"><span data-stu-id="9e0d2-108">When you add a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span>  
  
 <span data-ttu-id="9e0d2-109">Свойству `ConnectionManagerType` диспетчера соединений присваивается значение `SQLMOBILE`.</span><span class="sxs-lookup"><span data-stu-id="9e0d2-109">The `ConnectionManagerType` property of the connection manager is set to `SQLMOBILE`.</span></span>  
  
 <span data-ttu-id="9e0d2-110">Диспетчер соединений [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact можно настроить следующими способами:</span><span class="sxs-lookup"><span data-stu-id="9e0d2-110">You can configure the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="9e0d2-111">указать строку соединения, в которой задается расположение базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact;</span><span class="sxs-lookup"><span data-stu-id="9e0d2-111">Provide a connection string that specifies the location of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
-   <span data-ttu-id="9e0d2-112">указать пароль для защищенной паролем базы данных;</span><span class="sxs-lookup"><span data-stu-id="9e0d2-112">Provide a password for a password-protected database.</span></span>  
  
-   <span data-ttu-id="9e0d2-113">указать сервер, на котором хранится база данных;</span><span class="sxs-lookup"><span data-stu-id="9e0d2-113">Specify the server on which the database is stored.</span></span>  
  
-   <span data-ttu-id="9e0d2-114">Обозначает, будет ли соединение, созданное из диспетчера соединений, сохранено во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="9e0d2-114">Indicate whether the connection that is created from the connection manager is retained at run time.</span></span>  
  
 <span data-ttu-id="9e0d2-115">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="9e0d2-115">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="9e0d2-116">Дополнительные сведения о свойствах, которые можно задать в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] , см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="9e0d2-116">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="9e0d2-117">Редактор диспетчера подключений SQL Server Compact Edition (страница "Соединение")</span><span class="sxs-lookup"><span data-stu-id="9e0d2-117">SQL Server Compact Edition Connection Manager Editor &#40;Connection Page&#41;</span></span>](../sql-server-compact-edition-connection-manager-editor-connection-page.md)  
  
-   [<span data-ttu-id="9e0d2-118">Редактор диспетчера подключений SQL Server Compact Edition (страница "Все")</span><span class="sxs-lookup"><span data-stu-id="9e0d2-118">SQL Server Compact Edition Connection Manager Editor &#40;All Page&#41;</span></span>](../sql-server-compact-edition-connection-manager-editor-all-page.md)  
  
 <span data-ttu-id="9e0d2-119">Дополнительные сведения о программной настройке диспетчера подключений см. в разделах <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> и [Добавление соединений программным образом](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="9e0d2-119">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
  
