---
title: MSSQLSERVER_8645 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8645 (Database Engine error)
ms.assetid: 63d6d6d7-3850-4061-8e96-b1fa665e3180
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7be9774452e2008c34ecb52d228a0123992c5368
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666073"
---
# <a name="mssqlserver_8645"></a><span data-ttu-id="12eba-102">MSSQLSERVER_8645</span><span class="sxs-lookup"><span data-stu-id="12eba-102">MSSQLSERVER_8645</span></span>
    
## <a name="details"></a><span data-ttu-id="12eba-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="12eba-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="12eba-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="12eba-104">Product Name</span></span>|<span data-ttu-id="12eba-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="12eba-105">SQL Server</span></span>|  
|<span data-ttu-id="12eba-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="12eba-106">Event ID</span></span>|<span data-ttu-id="12eba-107">8645</span><span class="sxs-lookup"><span data-stu-id="12eba-107">8645</span></span>|  
|<span data-ttu-id="12eba-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="12eba-108">Event Source</span></span>|<span data-ttu-id="12eba-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="12eba-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="12eba-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="12eba-110">Component</span></span>|<span data-ttu-id="12eba-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="12eba-111">SQLEngine</span></span>|  
|<span data-ttu-id="12eba-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="12eba-112">Symbolic Name</span></span>|<span data-ttu-id="12eba-113">MEMTIMEDOUT_ERR</span><span class="sxs-lookup"><span data-stu-id="12eba-113">MEMTIMEDOUT_ERR</span></span>|  
|<span data-ttu-id="12eba-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="12eba-114">Message Text</span></span>|<span data-ttu-id="12eba-115">В процессе ожидания ресурсов памяти для исполнения запроса истекло время ожидания.</span><span class="sxs-lookup"><span data-stu-id="12eba-115">A time out occurred while waiting for memory resources to execute the query.</span></span> <span data-ttu-id="12eba-116">Повторите запрос.</span><span class="sxs-lookup"><span data-stu-id="12eba-116">Rerun the query.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="12eba-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="12eba-117">Explanation</span></span>  
 <span data-ttu-id="12eba-118">Истекло время ожидания ресурсов памяти для выполнения запроса в пуле ресурсов «default».</span><span class="sxs-lookup"><span data-stu-id="12eba-118">A timeout occurred while waiting for memory resources to execute the query in the resource pool 'default'.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="12eba-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="12eba-119">User Action</span></span>  
 <span data-ttu-id="12eba-120">Если вы не используете регулятор ресурсов, рекомендуется выполнить проверку общего состояния сервера и его загрузку, кроме того, можно проверить настройки пула ресурсов или группы рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="12eba-120">If you are not using Resource Governor, we recommend that you verify the overall server state and load, or check the resource pool or workload group settings.</span></span>  
  
 <span data-ttu-id="12eba-121">Далее представлены общие шаги, которые помогут при устранении неполадок с памятью.</span><span class="sxs-lookup"><span data-stu-id="12eba-121">The following list outlines general steps that will help in troubleshooting memory errors:</span></span>  
  
1.  <span data-ttu-id="12eba-122">Проверьте, не используют ли память данного сервера другие приложения или службы.</span><span class="sxs-lookup"><span data-stu-id="12eba-122">Verify whether other applications or services are consuming memory on this server.</span></span> <span data-ttu-id="12eba-123">Измените настройки таким образом, чтобы менее важные приложения или службы использовали меньший объем памяти.</span><span class="sxs-lookup"><span data-stu-id="12eba-123">Reconfigure less critical applications or services to consume less memory.</span></span>  
  
2.  <span data-ttu-id="12eba-124">Начните сбор счетчиков системного монитора для **диспетчера буферов SQL Server, Buffer Manager**, **SQL Server: Memory Manager**.</span><span class="sxs-lookup"><span data-stu-id="12eba-124">Start collecting performance monitor counters for **SQL Server: Buffer Manager**, **SQL Server: Memory Manager**.</span></span>  
  
3.  <span data-ttu-id="12eba-125">Проверьте следующие параметры конфигурации памяти SQL Server.</span><span class="sxs-lookup"><span data-stu-id="12eba-125">Check the following SQL Server memory configuration parameters:</span></span>  
  
    -   <span data-ttu-id="12eba-126">**max server memory**</span><span class="sxs-lookup"><span data-stu-id="12eba-126">**max server memory**</span></span>  
  
    -   <span data-ttu-id="12eba-127">**min server memory**</span><span class="sxs-lookup"><span data-stu-id="12eba-127">**min server memory**</span></span>  
  
    -   <span data-ttu-id="12eba-128">**min memory per query**</span><span class="sxs-lookup"><span data-stu-id="12eba-128">**min memory per query**</span></span>  
  
     <span data-ttu-id="12eba-129">Обратите внимание на нестандартные параметры.</span><span class="sxs-lookup"><span data-stu-id="12eba-129">Notice unusual settings.</span></span> <span data-ttu-id="12eba-130">При необходимости измените их.</span><span class="sxs-lookup"><span data-stu-id="12eba-130">Correct them as necessary.</span></span> <span data-ttu-id="12eba-131">Принимайте во внимание тот факт, что в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] предъявляются повышенные требования к доступному объему памяти.</span><span class="sxs-lookup"><span data-stu-id="12eba-131">Account for increased memory requirements for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="12eba-132">Параметры по умолчанию приведены в разделе «Настройка параметров конфигурации сервера» электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="12eba-132">Default settings are listed in "Setting Server Configuration Options" in SQL Server Books Online.</span></span>  
  
4.  <span data-ttu-id="12eba-133">Обратите внимание на сообщения инструкции DBCC MEMORYSTATUS и способ их изменения при появлении сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="12eba-133">Observe DBCC MEMORYSTATUS output and the way it changes when you see these error messages.</span></span>  
  
5.  <span data-ttu-id="12eba-134">Проверьте рабочую нагрузку (например, число параллельных сеансов, в текущий момент выполняющих запросы).</span><span class="sxs-lookup"><span data-stu-id="12eba-134">Check the workload (for example, number of concurrent sessions, currently executing queries).</span></span>  
  
 <span data-ttu-id="12eba-135">Следующие действия могут позволить использовать больший объем памяти в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="12eba-135">The following actions may make more memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="12eba-136">Если какие-либо отличные от SQL Server приложения используют необходимые ресурсы, попытайтесь прекратить выполнение этих приложений или перенесите их выполнение на отдельный сервер.</span><span class="sxs-lookup"><span data-stu-id="12eba-136">If applications besides SQL Server are consuming resources, try stopping running these applications or consider running them on a separate server.</span></span> <span data-ttu-id="12eba-137">Это снизит внешнюю нагрузку на память.</span><span class="sxs-lookup"><span data-stu-id="12eba-137">This will remove external memory pressure.</span></span>  
  
-   <span data-ttu-id="12eba-138">Если установлен параметр **max server memory**, увеличьте его значение.</span><span class="sxs-lookup"><span data-stu-id="12eba-138">If you have configured **max server memory,** increase its setting.</span></span>  
  
 <span data-ttu-id="12eba-139">Выполните следующие команды DBCC для освобождения нескольких кэшей памяти SQL Server.</span><span class="sxs-lookup"><span data-stu-id="12eba-139">Run the following DBCC commands to free several SQL Server memory caches.</span></span>  
  
-   <span data-ttu-id="12eba-140">DBCC FREESYSTEMCACHE</span><span class="sxs-lookup"><span data-stu-id="12eba-140">DBCC FREESYSTEMCACHE</span></span>  
  
-   <span data-ttu-id="12eba-141">DBCC FREESESSIONCACHE</span><span class="sxs-lookup"><span data-stu-id="12eba-141">DBCC FREESESSIONCACHE</span></span>  
  
-   <span data-ttu-id="12eba-142">DBCC FREEPROCCACHE</span><span class="sxs-lookup"><span data-stu-id="12eba-142">DBCC FREEPROCCACHE</span></span>  
  
 <span data-ttu-id="12eba-143">Если проблема не исчезла, необходимо продолжить ее исследование и, возможно, снизить рабочую нагрузку.</span><span class="sxs-lookup"><span data-stu-id="12eba-143">If the problem continues, you will need to investigate further and possibly reduce workload.</span></span>  
  
  
