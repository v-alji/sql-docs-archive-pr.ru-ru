---
title: MSSQLSERVER_4846 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 4846 (Database Engine error)
ms.assetid: a455e809-1883-4c7d-b3e3-835ee5bfe258
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 923137645aae72476fb4b2ae33f0cbbf3e81c2a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730702"
---
# <a name="mssqlserver_4846"></a><span data-ttu-id="36e27-102">MSSQLSERVER_4846</span><span class="sxs-lookup"><span data-stu-id="36e27-102">MSSQLSERVER_4846</span></span>
    
## <a name="details"></a><span data-ttu-id="36e27-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="36e27-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="36e27-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="36e27-104">Product Name</span></span>|<span data-ttu-id="36e27-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="36e27-105">SQL Server</span></span>|  
|<span data-ttu-id="36e27-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="36e27-106">Event ID</span></span>|<span data-ttu-id="36e27-107">4846</span><span class="sxs-lookup"><span data-stu-id="36e27-107">4846</span></span>|  
|<span data-ttu-id="36e27-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="36e27-108">Event Source</span></span>|<span data-ttu-id="36e27-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="36e27-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="36e27-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="36e27-110">Component</span></span>|<span data-ttu-id="36e27-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="36e27-111">SQLEngine</span></span>|  
|<span data-ttu-id="36e27-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="36e27-112">Symbolic Name</span></span>|<span data-ttu-id="36e27-113">BULKPROV_MEMORY</span><span class="sxs-lookup"><span data-stu-id="36e27-113">BULKPROV_MEMORY</span></span>|  
|<span data-ttu-id="36e27-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="36e27-114">Message Text</span></span>|<span data-ttu-id="36e27-115">Поставщику массовых данных не удалось выделить память.</span><span class="sxs-lookup"><span data-stu-id="36e27-115">The bulk data provider failed to allocate memory.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="36e27-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="36e27-116">Explanation</span></span>  
 <span data-ttu-id="36e27-117">Ошибка выделения памяти.</span><span class="sxs-lookup"><span data-stu-id="36e27-117">Memory allocation failed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="36e27-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="36e27-118">User Action</span></span>  
 <span data-ttu-id="36e27-119">Для диагностики ошибок памяти выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="36e27-119">Follow these general steps to troubleshoot memory errors:</span></span>  
  
1.  <span data-ttu-id="36e27-120">Проверьте, не используют ли память данного сервера другие приложения или службы.</span><span class="sxs-lookup"><span data-stu-id="36e27-120">Verify whether other applications or services are consuming memory on this server.</span></span> <span data-ttu-id="36e27-121">Измените настройки таким образом, чтобы менее важные приложения или службы использовали меньший объем памяти.</span><span class="sxs-lookup"><span data-stu-id="36e27-121">Reconfigure less critical applications or services to consume less memory.</span></span>  
  
2.  <span data-ttu-id="36e27-122">Начните сбор счетчиков системного монитора для **диспетчера буферов SQL Server, Buffer Manager**, **SQL Server: Memory Manager**.</span><span class="sxs-lookup"><span data-stu-id="36e27-122">Start collecting performance monitor counters for **SQL Server: Buffer Manager**, **SQL Server: Memory Manager**.</span></span>  
  
3.  <span data-ttu-id="36e27-123">Проверьте следующие параметры конфигурации памяти SQL Server.</span><span class="sxs-lookup"><span data-stu-id="36e27-123">Check the following SQL Server memory configuration parameters:</span></span>  
  
    -   <span data-ttu-id="36e27-124">**max server memory**</span><span class="sxs-lookup"><span data-stu-id="36e27-124">**max server memory**</span></span>  
  
    -   <span data-ttu-id="36e27-125">**min server memory**</span><span class="sxs-lookup"><span data-stu-id="36e27-125">**min server memory**</span></span>  
  
    -   <span data-ttu-id="36e27-126">**min memory per query**</span><span class="sxs-lookup"><span data-stu-id="36e27-126">**min memory per query**</span></span>  
  
     <span data-ttu-id="36e27-127">Обращайте внимание на любые необычные настройки.</span><span class="sxs-lookup"><span data-stu-id="36e27-127">Notice any unusual settings.</span></span> <span data-ttu-id="36e27-128">При необходимости измените их.</span><span class="sxs-lookup"><span data-stu-id="36e27-128">Correct them as necessary.</span></span> <span data-ttu-id="36e27-129">Учтите требования [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] к объему памяти.</span><span class="sxs-lookup"><span data-stu-id="36e27-129">Account for memory requirements for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="36e27-130">Параметры по умолчанию приведены в разделе «Настройка параметров конфигурации сервера» электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="36e27-130">Default settings are listed in "Setting Server Configuration Options" in SQL Server Books Online.</span></span>  
  
4.  <span data-ttu-id="36e27-131">Обратите внимание на сообщения инструкции DBCC MEMORYSTATUS и способ их изменения при появлении сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="36e27-131">Observe DBCC MEMORYSTATUS output and the way it changes when you see these error messages.</span></span>  
  
5.  <span data-ttu-id="36e27-132">Проверьте рабочую нагрузку (например, число параллельных сеансов, в текущий момент выполняющих запросы).</span><span class="sxs-lookup"><span data-stu-id="36e27-132">Check the workload (for example, number of concurrent sessions, currently executing queries).</span></span>  
  
 <span data-ttu-id="36e27-133">Следующие действия могут позволить использовать больший объем памяти в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="36e27-133">The following actions may make more memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="36e27-134">Если какие-либо отличные от SQL Server приложения используют необходимые ресурсы, попытайтесь прекратить выполнение этих приложений или перенесите их выполнение на отдельный сервер.</span><span class="sxs-lookup"><span data-stu-id="36e27-134">If applications besides SQL Server are consuming resources, try stopping running these applications or consider running them on a separate server.</span></span> <span data-ttu-id="36e27-135">Это снизит внешнюю нагрузку на память.</span><span class="sxs-lookup"><span data-stu-id="36e27-135">This will remove external memory pressure.</span></span>  
  
-   <span data-ttu-id="36e27-136">Если установлен параметр **max server memory**, увеличьте его значение.</span><span class="sxs-lookup"><span data-stu-id="36e27-136">If you have configured **max server memory,** increase its setting.</span></span>  
  
 <span data-ttu-id="36e27-137">Выполните следующие команды DBCC для освобождения нескольких кэшей памяти [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36e27-137">Run the following DBCC commands to free several [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory caches.</span></span>  
  
-   <span data-ttu-id="36e27-138">DBCC FREESYSTEMCACHE</span><span class="sxs-lookup"><span data-stu-id="36e27-138">DBCC FREESYSTEMCACHE</span></span>  
  
-   <span data-ttu-id="36e27-139">DBCC FREESESSIONCACHE</span><span class="sxs-lookup"><span data-stu-id="36e27-139">DBCC FREESESSIONCACHE</span></span>  
  
-   <span data-ttu-id="36e27-140">DBCC FREEPROCCACHE</span><span class="sxs-lookup"><span data-stu-id="36e27-140">DBCC FREEPROCCACHE</span></span>  
  
 <span data-ttu-id="36e27-141">Если проблема не исчезла, необходимо продолжить ее исследование и, возможно, снизить рабочую нагрузку.</span><span class="sxs-lookup"><span data-stu-id="36e27-141">If the problem continues, you will need to investigate further and possibly reduce workload.</span></span>  
  
  
