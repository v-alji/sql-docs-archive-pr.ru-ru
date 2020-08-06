---
title: MSSQLSERVER_8651 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8651 (Database Engine error)
ms.assetid: 4cc3498d-5449-4c4e-b1f9-3271831c725a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 43a385350a05edee3759ab83d318e365f5b4f3e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730697"
---
# <a name="mssqlserver_8651"></a><span data-ttu-id="50fce-102">MSSQLSERVER_8651</span><span class="sxs-lookup"><span data-stu-id="50fce-102">MSSQLSERVER_8651</span></span>
    
## <a name="details"></a><span data-ttu-id="50fce-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="50fce-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="50fce-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="50fce-104">Product Name</span></span>|<span data-ttu-id="50fce-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="50fce-105">SQL Server</span></span>|  
|<span data-ttu-id="50fce-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="50fce-106">Event ID</span></span>|<span data-ttu-id="50fce-107">8651</span><span class="sxs-lookup"><span data-stu-id="50fce-107">8651</span></span>|  
|<span data-ttu-id="50fce-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="50fce-108">Event Source</span></span>|<span data-ttu-id="50fce-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="50fce-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="50fce-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="50fce-110">Component</span></span>|<span data-ttu-id="50fce-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="50fce-111">SQLEngine</span></span>|  
|<span data-ttu-id="50fce-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="50fce-112">Symbolic Name</span></span>|<span data-ttu-id="50fce-113">MEMGRANT_ERR</span><span class="sxs-lookup"><span data-stu-id="50fce-113">MEMGRANT_ERR</span></span>|  
|<span data-ttu-id="50fce-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="50fce-114">Message Text</span></span>|<span data-ttu-id="50fce-115">Не удалось выполнить запрошенную операцию, потому что недоступна минимально необходимая память для запроса.</span><span class="sxs-lookup"><span data-stu-id="50fce-115">Could not perform the requested operation because the minimum query memory is not available.</span></span> <span data-ttu-id="50fce-116">Уменьшите значение параметра конфигурации сервера «min memory per query».</span><span class="sxs-lookup"><span data-stu-id="50fce-116">Decrease the configured value for the 'min memory per query' server configuration option.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="50fce-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="50fce-117">Explanation</span></span>  
 <span data-ttu-id="50fce-118">Память сервера потребляют другие процессы (усиливая нагрузку на память на сервере).</span><span class="sxs-lookup"><span data-stu-id="50fce-118">Other processes are consuming server memory (exerting memory pressure in the server).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="50fce-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="50fce-119">User Action</span></span>  
 <span data-ttu-id="50fce-120">Уменьшите значение параметра конфигурации сервера «min memory per query» или снизьте интенсивность запросов на сервере.</span><span class="sxs-lookup"><span data-stu-id="50fce-120">Either decrease the configured value for the min memory per query' server configuration option or reduce the query load to the server.</span></span>  
  
 <span data-ttu-id="50fce-121">Далее представлены общие шаги, которые помогут при устранении неполадок с памятью.</span><span class="sxs-lookup"><span data-stu-id="50fce-121">The following list outlines general steps that will help in troubleshooting memory errors:</span></span>  
  
1.  <span data-ttu-id="50fce-122">Проверьте, не используют ли память данного сервера другие приложения или службы.</span><span class="sxs-lookup"><span data-stu-id="50fce-122">Verify whether other applications or services are consuming memory on this server.</span></span> <span data-ttu-id="50fce-123">Измените настройки таким образом, чтобы менее важные приложения или службы использовали меньший объем памяти.</span><span class="sxs-lookup"><span data-stu-id="50fce-123">Reconfigure less critical applications or services to consume less memory.</span></span>  
  
2.  <span data-ttu-id="50fce-124">Начните сбор счетчиков системного монитора для **диспетчера буферов SQL Server, Buffer Manager**, **SQL Server: Memory Manager**.</span><span class="sxs-lookup"><span data-stu-id="50fce-124">Start collecting performance monitor counters for **SQL Server: Buffer Manager**, **SQL Server: Memory Manager**.</span></span>  
  
3.  <span data-ttu-id="50fce-125">Проверьте следующие параметры конфигурации памяти [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="50fce-125">Check the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory configuration parameters:</span></span>  
  
    -   <span data-ttu-id="50fce-126">**max server memory**</span><span class="sxs-lookup"><span data-stu-id="50fce-126">**max server memory**</span></span>  
  
    -   <span data-ttu-id="50fce-127">**min server memory**</span><span class="sxs-lookup"><span data-stu-id="50fce-127">**min server memory**</span></span>  
  
    -   <span data-ttu-id="50fce-128">**min memory per query**</span><span class="sxs-lookup"><span data-stu-id="50fce-128">**min memory per query**</span></span>  
  
     <span data-ttu-id="50fce-129">Обратите внимание на нестандартные параметры.</span><span class="sxs-lookup"><span data-stu-id="50fce-129">Notice unusual settings.</span></span> <span data-ttu-id="50fce-130">При необходимости измените их.</span><span class="sxs-lookup"><span data-stu-id="50fce-130">Correct them as necessary.</span></span> <span data-ttu-id="50fce-131">Параметры по умолчанию приведены в разделе «Настройка параметров конфигурации сервера» электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="50fce-131">Default settings are listed in "Setting Server Configuration Options" in SQL Server Books Online.</span></span>  
  
4.  <span data-ttu-id="50fce-132">Проверьте рабочую нагрузку (например, число параллельных сеансов, в текущий момент выполняющих запросы).</span><span class="sxs-lookup"><span data-stu-id="50fce-132">Check the workload (for example, number of concurrent sessions, currently executing queries).</span></span>  
  
 <span data-ttu-id="50fce-133">Следующие действия могут позволить использовать больший объем памяти в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="50fce-133">The following actions may make more memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="50fce-134">Если какие-либо отличные от [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] приложения используют необходимые ресурсы, попытайтесь прекратить выполнение этих приложений или перенесите их выполнение на отдельный сервер.</span><span class="sxs-lookup"><span data-stu-id="50fce-134">If applications besides [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are consuming resources, try stopping running these applications or consider running them on a separate server.</span></span> <span data-ttu-id="50fce-135">Это снизит внешнюю нагрузку на память.</span><span class="sxs-lookup"><span data-stu-id="50fce-135">This will remove external memory pressure.</span></span>  
  
-   <span data-ttu-id="50fce-136">Если установлен параметр **max server memory**, увеличьте его значение.</span><span class="sxs-lookup"><span data-stu-id="50fce-136">If you have configured **max server memory,** increase its setting.</span></span>  
  
 <span data-ttu-id="50fce-137">Выполните следующие команды DBCC для освобождения нескольких кэшей памяти [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50fce-137">Run the following DBCC commands to free several [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory caches.</span></span>  
  
-   <span data-ttu-id="50fce-138">DBCC FREESYSTEMCACHE</span><span class="sxs-lookup"><span data-stu-id="50fce-138">DBCC FREESYSTEMCACHE</span></span>  
  
-   <span data-ttu-id="50fce-139">DBCC FREESESSIONCACHE</span><span class="sxs-lookup"><span data-stu-id="50fce-139">DBCC FREESESSIONCACHE</span></span>  
  
-   <span data-ttu-id="50fce-140">DBCC FREEPROCCACHE</span><span class="sxs-lookup"><span data-stu-id="50fce-140">DBCC FREEPROCCACHE</span></span>  
  
 <span data-ttu-id="50fce-141">Если проблема не исчезла, необходимо продолжить ее исследование и, возможно, снизить рабочую нагрузку.</span><span class="sxs-lookup"><span data-stu-id="50fce-141">If the problem continues, you will need to investigate further and possibly reduce workload.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50fce-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="50fce-142">See Also</span></span>  
 <span data-ttu-id="50fce-143">[DBCC FREESYSTEMCACHE &#40;&#41;Transact-SQL](/sql/t-sql/database-console-commands/dbcc-freesystemcache-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="50fce-143">[DBCC FREESYSTEMCACHE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-freesystemcache-transact-sql) </span></span>  
 <span data-ttu-id="50fce-144">[DBCC FREESESSIONCACHE &#40;&#41;Transact-SQL](/sql/t-sql/database-console-commands/dbcc-freesessioncache-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="50fce-144">[DBCC FREESESSIONCACHE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-freesessioncache-transact-sql) </span></span>  
 <span data-ttu-id="50fce-145">[DBCC FREEPROCCACHE &#40;&#41;Transact-SQL](/sql/t-sql/database-console-commands/dbcc-freeproccache-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="50fce-145">[DBCC FREEPROCCACHE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-freeproccache-transact-sql) </span></span>  
 <span data-ttu-id="50fce-146">[Параметры конфигурации сервера (SQL Server)](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="50fce-146">[Server Configuration Options &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="50fce-147">[SQL Server, объект Buffer Manager](../performance-monitor/sql-server-buffer-manager-object.md) </span><span class="sxs-lookup"><span data-stu-id="50fce-147">[SQL Server, Buffer Manager Object](../performance-monitor/sql-server-buffer-manager-object.md) </span></span>  
 [<span data-ttu-id="50fce-148">SQL Server, объект Memory Manager</span><span class="sxs-lookup"><span data-stu-id="50fce-148">SQL Server, Memory Manager Object</span></span>](../performance-monitor/sql-server-memory-manager-object.md)  
  
  
