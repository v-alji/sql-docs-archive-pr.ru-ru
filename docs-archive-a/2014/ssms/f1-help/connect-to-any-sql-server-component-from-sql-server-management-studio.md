---
title: Подключение к любому компоненту SQL Server из SQL Server Management Studio | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- connections [SQL Server], SQL Server Management Studio
- saving connections
- components [SQL Server], connections
- SQL Server Management Studio [SQL Server], connections
ms.assetid: 5eeb41bd-b25b-4d3b-a005-a7d9e4b5978e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9cd3e185ea6f289a2a6db46cdca2cb310fefbcf9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733478"
---
# <a name="connect-to-any-sql-server-component-from-sql-server-management-studio"></a><span data-ttu-id="29686-102">Подключение к любому компоненту сервера SQL Server из среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="29686-102">Connect to Any SQL Server Component from SQL Server Management Studio</span></span>
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="29686-103">содержит функции управления всеми компонентами [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29686-103">provides functionality for managing every component of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="29686-104">Используйте среду [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] для соединения со следующими компонентами и службами:</span><span class="sxs-lookup"><span data-stu-id="29686-104">Use [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to connect to:</span></span>  
  
-   <span data-ttu-id="29686-105">Экземпляр компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29686-105">An instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
-   [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="29686-106">.</span><span class="sxs-lookup"><span data-stu-id="29686-106">.</span></span>  
  
-   [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]<span data-ttu-id="29686-107">.</span><span class="sxs-lookup"><span data-stu-id="29686-107">.</span></span>  
  
-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]<span data-ttu-id="29686-108">.</span><span class="sxs-lookup"><span data-stu-id="29686-108">.</span></span>  
  
 <span data-ttu-id="29686-109">Хотя [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] позволяет работать с запросами без предварительного установления соединения с источником данных, для большинства других задач такое соединение требуется.</span><span class="sxs-lookup"><span data-stu-id="29686-109">Although [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] allows you to work with queries without first establishing a connection to a data source, most other tasks require a connection.</span></span> [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] <span data-ttu-id="29686-110">предоставляет диалоговое окно **Соединение с сервером** , в котором можно настроить свойства компонентов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="29686-110">provides the **Connect to Server** dialog box to configure connection properties to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components.</span></span> <span data-ttu-id="29686-111">При запуске [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] открывается диалоговое окно **Соединение с сервером** с запросом на подключение к серверу.</span><span class="sxs-lookup"><span data-stu-id="29686-111">When [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] starts, it opens the **Connect to Server** dialog box and prompts you to connect to a server.</span></span> <span data-ttu-id="29686-112">В диалоговом окне **Соединение с сервером** запоминаются параметры, заданные во время предыдущего его использования.</span><span class="sxs-lookup"><span data-stu-id="29686-112">The **Connect to Server** dialog box retains the connection settings from the last time it was used.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="29686-113">Эту функцию можно отключить, чтобы отменить автоматическую установку соединения.</span><span class="sxs-lookup"><span data-stu-id="29686-113">This feature can be turned off so no connection is automatically initiated.</span></span> <span data-ttu-id="29686-114">Дополнительные сведения см. в разделе [Параметры запуска службы Database Engine](../../database-engine/configure-windows/database-engine-service-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="29686-114">For more information, see [Database Engine Service Startup Options](../../database-engine/configure-windows/database-engine-service-startup-options.md).</span></span>  
  
## <a name="saving-connections"></a><span data-ttu-id="29686-115">сохранение соединений</span><span class="sxs-lookup"><span data-stu-id="29686-115">Saving Connections</span></span>  
 <span data-ttu-id="29686-116">Соединение с конкретными серверами можно сохранять в списке «Зарегистрированные серверы», а также в проектах, создаваемых с помощью обозревателя решений.</span><span class="sxs-lookup"><span data-stu-id="29686-116">You can save connections to specific servers in Registered Servers, or you can save connections in projects with Solution Explorer.</span></span>  
  
### <a name="saving-connections-in-registered-servers"></a><span data-ttu-id="29686-117">Сохранение соединений в списке «Зарегистрированные серверы»</span><span class="sxs-lookup"><span data-stu-id="29686-117">Saving Connections in Registered Servers</span></span>  
 <span data-ttu-id="29686-118">При регистрации сервера среда [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] сохраняет данные соединения к нему в списке «Зарегистрированные серверы».</span><span class="sxs-lookup"><span data-stu-id="29686-118">When you register a server, [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] saves the connection information in Registered Servers.</span></span> <span data-ttu-id="29686-119">Для соединения с зарегистрированным сервером дважды щелкните имя сервера в списке «Зарегистрированные серверы».</span><span class="sxs-lookup"><span data-stu-id="29686-119">To connect to a registered server, double-click the server name in Registered Servers.</span></span> <span data-ttu-id="29686-120">После этого соединение с сервером откроется в обозревателе объектов.</span><span class="sxs-lookup"><span data-stu-id="29686-120">Object Explorer then opens a connection to the server.</span></span>  
  
### <a name="saving-connections-in-solution-explorer"></a><span data-ttu-id="29686-121">Сохранение соединений в обозревателе решений</span><span class="sxs-lookup"><span data-stu-id="29686-121">Saving Connections in Solution Explorer</span></span>  
 <span data-ttu-id="29686-122">Обозреватель решений позволяет хранить связанные запросы, скрипты, соединения, а также другие связанные данные в проекте.</span><span class="sxs-lookup"><span data-stu-id="29686-122">Solution Explorer allows you to store related queries, scripts, connections, and other associated information in a project.</span></span> <span data-ttu-id="29686-123">Каждый проект скриптов содержит узел **Соединения**, в котором можно сохранить одно или несколько соединений.</span><span class="sxs-lookup"><span data-stu-id="29686-123">Each script project contains a node called **Connections**, where you can save one or more connections.</span></span> <span data-ttu-id="29686-124">Для добавления соединения щелкните правой кнопкой мыши узел **Соединения**и выберите **Создать соединение**.</span><span class="sxs-lookup"><span data-stu-id="29686-124">To add a connection, right-click **Connections**, and then click **New Connection**.</span></span> <span data-ttu-id="29686-125">Для доступа к сохраненному соединению разверните пункт **Соединения** и дважды щелкните нужное соединение.</span><span class="sxs-lookup"><span data-stu-id="29686-125">To access a saved connection, expand **Connections** and double-click the connection.</span></span> [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] <span data-ttu-id="29686-126">позволяет открыть окно запроса, связанное с заданным соединением.</span><span class="sxs-lookup"><span data-stu-id="29686-126">opens a query window associated with that connection.</span></span> <span data-ttu-id="29686-127">При сохранении скриптов они остаются связанными с конкретным соединением.</span><span class="sxs-lookup"><span data-stu-id="29686-127">When saved, scripts retain their association to a specific connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29686-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="29686-128">See Also</span></span>  
 <span data-ttu-id="29686-129">[Использование SQL Server Management Studio](../sql-server-management-studio-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="29686-129">[Use SQL Server Management Studio](../sql-server-management-studio-ssms.md) </span></span>  
 [<span data-ttu-id="29686-130">Обозреватель объектов</span><span class="sxs-lookup"><span data-stu-id="29686-130">Object Explorer</span></span>](../object/object-explorer.md)  
  
  
