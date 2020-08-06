---
title: Регистрация серверов
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.sqlserverregisteredserver.dhelp
helpviewer_keywords:
- connections [SQL Server], registered servers
- registering servers
- servers [SQL Server], registering
- server management [SQL Server], registering servers
- server registration [SQL Server]
ms.assetid: c2a2513e-fa09-419c-99e7-a12d57c5a0db
author: markingmyname
ms.author: maghan
ms.openlocfilehash: f4b23ba127c6b000b0abbe832c4c072ada78c5e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658026"
---
# <a name="register-servers"></a><span data-ttu-id="a90a1-102">Регистрация серверов</span><span class="sxs-lookup"><span data-stu-id="a90a1-102">Register Servers</span></span>
  <span data-ttu-id="a90a1-103">Регистрация сервера в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] позволяет сохранить информацию о подключении сервера для будущих подключений. Есть три способа зарегистрировать сервер в [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a90a1-103">Registering a server in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] allows you to store the server connection information for future connections.There are three ways to register a server in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
1.  <span data-ttu-id="a90a1-104">Локальные экземпляры [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] автоматически регистрируются во время первого запуска среды [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] после ее установки.</span><span class="sxs-lookup"><span data-stu-id="a90a1-104">Local instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are automatically registered during the first launch of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] after its installation.</span></span>  
  
2.  <span data-ttu-id="a90a1-105">Можно также запустить процесс автоматической регистрации в любое время, чтобы восстановить регистрацию локальных экземпляров сервера.</span><span class="sxs-lookup"><span data-stu-id="a90a1-105">You can also initiate the automatic registration process at any time, to restore the registration of local server instances.</span></span>  
  
3.  <span data-ttu-id="a90a1-106">Наконец, можно зарегистрировать сервер с помощью средства «Зарегистрированные серверы» в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a90a1-106">Lastly, you can register a server using the Registered Servers tool in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="benefits-of-registered-servers"></a><span data-ttu-id="a90a1-107">Преимущества зарегистрированных серверов</span><span class="sxs-lookup"><span data-stu-id="a90a1-107">Benefits of Registered Servers</span></span>  
 <span data-ttu-id="a90a1-108">С помощью списка «Зарегистрированные серверы» можно:</span><span class="sxs-lookup"><span data-stu-id="a90a1-108">With Registered Servers you can:</span></span>  
  
-   <span data-ttu-id="a90a1-109">регистрировать серверы для сохранения данных о соединениях;</span><span class="sxs-lookup"><span data-stu-id="a90a1-109">Register servers to preserve the connection information.</span></span>  
  
-   <span data-ttu-id="a90a1-110">определять, запущен ли зарегистрированный сервер;</span><span class="sxs-lookup"><span data-stu-id="a90a1-110">Determine if a registered server is running.</span></span>  
  
-   <span data-ttu-id="a90a1-111">легко подключать обозреватель объектов и редактор запросов к зарегистрированному серверу;</span><span class="sxs-lookup"><span data-stu-id="a90a1-111">Easily connect Object Explorer and Query Editor to a registered server.</span></span>  
  
-   <span data-ttu-id="a90a1-112">редактировать и удалять регистрационные данные зарегистрированного сервера;</span><span class="sxs-lookup"><span data-stu-id="a90a1-112">Edit or delete the registration information for a registered server.</span></span>  
  
-   <span data-ttu-id="a90a1-113">создавать группы серверов;</span><span class="sxs-lookup"><span data-stu-id="a90a1-113">Create groups of servers.</span></span>  
  
-   <span data-ttu-id="a90a1-114">назначать зарегистрированным серверам понятные имена путем задания в поле **Имя зарегистрированного сервера** значения, отличного от имеющегося в списке **Имя сервера** ;</span><span class="sxs-lookup"><span data-stu-id="a90a1-114">Provide user-friendly names for registered servers by providing a value in the **Registered server name** box that is different from the **Server name** list.</span></span>  
  
-   <span data-ttu-id="a90a1-115">создавать подробные описания зарегистрированных серверов;</span><span class="sxs-lookup"><span data-stu-id="a90a1-115">Provide detailed descriptions for registered servers.</span></span>  
  
-   <span data-ttu-id="a90a1-116">указывать подробные описания групп зарегистрированных серверов;</span><span class="sxs-lookup"><span data-stu-id="a90a1-116">Provide detailed descriptions of registered server groups.</span></span>  
  
-   <span data-ttu-id="a90a1-117">экспортировать группы зарегистрированных серверов;</span><span class="sxs-lookup"><span data-stu-id="a90a1-117">Export registered server groups.</span></span>  
  
-   <span data-ttu-id="a90a1-118">импортировать группы зарегистрированных серверов;</span><span class="sxs-lookup"><span data-stu-id="a90a1-118">Import registered server groups.</span></span>  
  
-   <span data-ttu-id="a90a1-119">просматривать файлы журналов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], находящихся в сети и вне сети.</span><span class="sxs-lookup"><span data-stu-id="a90a1-119">View the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files for online or offline instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="a90a1-120">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="a90a1-120">Related Tasks</span></span>  
 <span data-ttu-id="a90a1-121">Используйте следующие разделы для начала работы с зарегистрированными серверами.</span><span class="sxs-lookup"><span data-stu-id="a90a1-121">Use the following topics to get started with registered servers:</span></span>  
  
|<span data-ttu-id="a90a1-122">**Описание**</span><span class="sxs-lookup"><span data-stu-id="a90a1-122">**Description**</span></span>|<span data-ttu-id="a90a1-123">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="a90a1-123">**Topic**</span></span>|  
|---------------------|---------------|  
|<span data-ttu-id="a90a1-124">Регистрация экземпляров локального сервера</span><span class="sxs-lookup"><span data-stu-id="a90a1-124">Register local server instances</span></span>|[<span data-ttu-id="a90a1-125">Регистрация подключенного сервера (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="a90a1-125">Register a Connected Server &#40;SQL Server Management Studio&#41;</span></span>](register-a-connected-server-sql-server-management-studio.md)|  
|<span data-ttu-id="a90a1-126">Регистрация сервера</span><span class="sxs-lookup"><span data-stu-id="a90a1-126">Register a server</span></span>|[<span data-ttu-id="a90a1-127">Создание нового зарегистрированного сервера (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="a90a1-127">Create a New Registered Server &#40;SQL Server Management Studio&#41;</span></span>](create-a-new-registered-server-sql-server-management-studio.md)|  
|<span data-ttu-id="a90a1-128">Просмотр зарегистрированных серверов</span><span class="sxs-lookup"><span data-stu-id="a90a1-128">View registered servers</span></span>|[<span data-ttu-id="a90a1-129">Просмотр зарегистрированных серверов в среде SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a90a1-129">View Registered Servers in SQL Server Management Studio</span></span>](view-registered-servers-in-sql-server-management-studio.md)|  
|<span data-ttu-id="a90a1-130">Удаление зарегистрированного сервера</span><span class="sxs-lookup"><span data-stu-id="a90a1-130">Remove a registered server</span></span>|[<span data-ttu-id="a90a1-131">Удаление зарегистрированного сервера (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="a90a1-131">Remove a Registered Server &#40;SQL Server Management Studio&#41;</span></span>](remove-a-registered-server-sql-server-management-studio.md)|  
|<span data-ttu-id="a90a1-132">Изменение регистрации сервера</span><span class="sxs-lookup"><span data-stu-id="a90a1-132">Change a server's registration</span></span>|[<span data-ttu-id="a90a1-133">Изменение регистрационных данных сервера (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="a90a1-133">Change a Server's Registration &#40;SQL Server Management Studio&#41;</span></span>](change-a-server-s-registration-sql-server-management-studio.md)|  
|<span data-ttu-id="a90a1-134">Подключение к зарегистрированному серверу</span><span class="sxs-lookup"><span data-stu-id="a90a1-134">Connect to a registered server</span></span>|[<span data-ttu-id="a90a1-135">Подключение к зарегистрированному серверу (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="a90a1-135">Connect to a Registered Server &#40;SQL Server Management Studio&#41;</span></span>](connect-to-a-registered-server-sql-server-management-studio.md)|  
|<span data-ttu-id="a90a1-136">Отключение от зарегистрированного сервера</span><span class="sxs-lookup"><span data-stu-id="a90a1-136">Disconnect from a registered server</span></span>|[<span data-ttu-id="a90a1-137">Отключение от зарегистрированного сервера (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="a90a1-137">Disconnect from a Registered Server &#40;SQL Server Management Studio&#41;</span></span>](disconnect-from-a-registered-server-sql-server-management-studio.md)|  
|<span data-ttu-id="a90a1-138">Перемещение зарегистрированного сервера или группы серверов</span><span class="sxs-lookup"><span data-stu-id="a90a1-138">Move a registered server or server group</span></span>|[<span data-ttu-id="a90a1-139">Перемещение зарегистрированного сервера или зарегистрированной группы серверов (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="a90a1-139">Move a Registered Server or Registered Server Group &#40;SQL Server Management Studio&#41;</span></span>](move-a-registered-server-or-registered-server-group.md)|  
|<span data-ttu-id="a90a1-140">Изменение имени зарегистрированного сервера или группы серверов</span><span class="sxs-lookup"><span data-stu-id="a90a1-140">Change the name of a registered server or server group</span></span>|[<span data-ttu-id="a90a1-141">Изменение имени зарегистрированного сервера или зарегистрированной группы серверов (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="a90a1-141">Change the Name of a Registered Server or Registered Server Group &#40;SQL Server Management Studio&#41;</span></span>](change-the-name-of-registered-server-or-registered-server-group.md)|  
|<span data-ttu-id="a90a1-142">Создание или изменение группы серверов</span><span class="sxs-lookup"><span data-stu-id="a90a1-142">Create or edit a server group</span></span>|[<span data-ttu-id="a90a1-143">Создание или изменение группы серверов (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="a90a1-143">Create or Edit a Server Group &#40;SQL Server Management Studio&#41;</span></span>](create-or-edit-a-server-group-sql-server-management-studio.md)|  
|<span data-ttu-id="a90a1-144">Удалить группу серверов</span><span class="sxs-lookup"><span data-stu-id="a90a1-144">Remove a server group</span></span>|[<span data-ttu-id="a90a1-145">Удаление группы серверов (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="a90a1-145">Remove a Server Group &#40;SQL Server Management Studio&#41;</span></span>](remove-a-server-group-sql-server-management-studio.md)|  
|<span data-ttu-id="a90a1-146">Экспорт сведений о зарегистрированном сервере</span><span class="sxs-lookup"><span data-stu-id="a90a1-146">Export registered server information</span></span>|[<span data-ttu-id="a90a1-147">Выполнение экспорта сведений компонента "Зарегистрированные серверы" (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="a90a1-147">Export Registered Server Information &#40;SQL Server Management Studio&#41;</span></span>](export-registered-server-information-sql-server-management-studio.md)|  
|<span data-ttu-id="a90a1-148">Удаление сведений о зарегистрированном сервере</span><span class="sxs-lookup"><span data-stu-id="a90a1-148">Import registered server information</span></span>|[<span data-ttu-id="a90a1-149">Импорт сведений компонента "Зарегистрированные серверы" (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="a90a1-149">Import Registered Server Information &#40;SQL Server Management Studio&#41;</span></span>](import-registered-server-information-sql-server-management-studio.md)|  
|<span data-ttu-id="a90a1-150">Создание центрального сервера управления и группы серверов</span><span class="sxs-lookup"><span data-stu-id="a90a1-150">Create a Central Management Server and Server Group</span></span>|[<span data-ttu-id="a90a1-151">Создание центрального сервера управления и группы сервера (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="a90a1-151">Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;</span></span>](create-a-central-management-server-and-server-group.md)|  
|<span data-ttu-id="a90a1-152">Выполнение инструкций на нескольких серверах одновременно</span><span class="sxs-lookup"><span data-stu-id="a90a1-152">Execute statements against multiple servers simultaneously</span></span>|[<span data-ttu-id="a90a1-153">Выполнение инструкции на нескольких серверах одновременно (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="a90a1-153">Execute Statements Against Multiple Servers Simultaneously &#40;SQL Server Management Studio&#41;</span></span>](execute-statements-against-multiple-servers-simultaneously.md)|  
  
## <a name="see-also"></a><span data-ttu-id="a90a1-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="a90a1-154">See Also</span></span>  
 [<span data-ttu-id="a90a1-155">Удаленные серверы</span><span class="sxs-lookup"><span data-stu-id="a90a1-155">Remote Servers</span></span>](../../database-engine/configure-windows/remote-servers.md)  
  
  
