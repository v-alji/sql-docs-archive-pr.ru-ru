---
title: MSSQLSERVER_701 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 701 (Database Engine error)
ms.assetid: 3b975000-63a1-43c2-a40f-89d0a8a36bef
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 542535223d3e394c72079092411add143de61545
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657796"
---
# <a name="mssqlserver_701"></a><span data-ttu-id="cc869-102">MSSQLSERVER_701</span><span class="sxs-lookup"><span data-stu-id="cc869-102">MSSQLSERVER_701</span></span>
    
## <a name="details"></a><span data-ttu-id="cc869-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="cc869-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cc869-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="cc869-104">Product Name</span></span>|<span data-ttu-id="cc869-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="cc869-105">SQL Server</span></span>|  
|<span data-ttu-id="cc869-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="cc869-106">Event ID</span></span>|<span data-ttu-id="cc869-107">701</span><span class="sxs-lookup"><span data-stu-id="cc869-107">701</span></span>|  
|<span data-ttu-id="cc869-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="cc869-108">Event Source</span></span>|<span data-ttu-id="cc869-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="cc869-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="cc869-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="cc869-110">Component</span></span>|<span data-ttu-id="cc869-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="cc869-111">SQLEngine</span></span>|  
|<span data-ttu-id="cc869-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="cc869-112">Symbolic Name</span></span>|<span data-ttu-id="cc869-113">NOSYSMEM</span><span class="sxs-lookup"><span data-stu-id="cc869-113">NOSYSMEM</span></span>|  
|<span data-ttu-id="cc869-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="cc869-114">Message Text</span></span>|<span data-ttu-id="cc869-115">Недостаточно системной памяти для выполнения данного запроса.</span><span class="sxs-lookup"><span data-stu-id="cc869-115">There is insufficient system memory to run this query.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cc869-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="cc869-116">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="cc869-117">не смог выделить достаточно памяти для выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="cc869-117">has failed to allocate sufficient memory to run the query.</span></span> <span data-ttu-id="cc869-118">Ошибка может быть вызвана различными причинами, включая параметры операционной системы, доступность физической памяти или ограничениями памяти для текущей рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="cc869-118">This can be caused by a variety of reasons including operating system settings, physical memory availability, or memory limits on the current workload.</span></span> <span data-ttu-id="cc869-119">В большинстве случаев эта ошибка не возникает из-за сбоя транзакции.</span><span class="sxs-lookup"><span data-stu-id="cc869-119">In most cases, the transaction that failed is not the cause of this error.</span></span>  
  
 <span data-ttu-id="cc869-120">Диагностические запросы, например инструкции DBCC, могут выдавать ошибку, потому что у сервера недостаточный объем памяти.</span><span class="sxs-lookup"><span data-stu-id="cc869-120">Diagnostic queries, such as DBCC statements, may fail because server the does not have sufficient memory.</span></span>  
  
 <span data-ttu-id="cc869-121">Истекло время ожидания ресурсов памяти для выполнения запроса в пуле ресурсов «default».</span><span class="sxs-lookup"><span data-stu-id="cc869-121">A timeout occurred while waiting for memory resources to execute the query in the resource pool 'default'.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cc869-122">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="cc869-122">User Action</span></span>  
 <span data-ttu-id="cc869-123">Если вы не используете регулятор ресурсов, рекомендуется выполнить проверку общего состояния сервера и его загрузку, кроме того, можно проверить настройки пула ресурсов или группы рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="cc869-123">If you are not using Resource Governor, we recommend that you verify the overall server state and load, or check the resource pool or workload group settings.</span></span>  
  
 <span data-ttu-id="cc869-124">Далее представлены общие шаги, которые помогут при устранении неполадок с памятью.</span><span class="sxs-lookup"><span data-stu-id="cc869-124">The following list outlines general steps that will help in troubleshooting memory errors:</span></span>  
  
1.  <span data-ttu-id="cc869-125">Проверьте, не используют ли память данного сервера другие приложения или службы.</span><span class="sxs-lookup"><span data-stu-id="cc869-125">Verify whether other applications or services are consuming memory on this server.</span></span> <span data-ttu-id="cc869-126">Измените настройки таким образом, чтобы менее важные приложения или службы использовали меньший объем памяти.</span><span class="sxs-lookup"><span data-stu-id="cc869-126">Reconfigure less critical applications or services to consume less memory.</span></span>  
  
2.  <span data-ttu-id="cc869-127">Начните сбор счетчиков системного монитора для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **: Buffer Manager**, **SQL Server: Memory Manager**.</span><span class="sxs-lookup"><span data-stu-id="cc869-127">Start collecting performance monitor counters for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**: Buffer Manager**, **SQL Server: Memory Manager**.</span></span>  
  
3.  <span data-ttu-id="cc869-128">Проверьте следующие параметры конфигурации памяти SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cc869-128">Check the following SQL Server memory configuration parameters:</span></span>  
  
    -   <span data-ttu-id="cc869-129">**max server memory**</span><span class="sxs-lookup"><span data-stu-id="cc869-129">**max server memory**</span></span>  
  
    -   <span data-ttu-id="cc869-130">**min server memory**</span><span class="sxs-lookup"><span data-stu-id="cc869-130">**min server memory**</span></span>  
  
    -   <span data-ttu-id="cc869-131">**min memory per query**</span><span class="sxs-lookup"><span data-stu-id="cc869-131">**min memory per query**</span></span>  
  
     <span data-ttu-id="cc869-132">Обратите внимание на нестандартные параметры.</span><span class="sxs-lookup"><span data-stu-id="cc869-132">Notice unusual settings.</span></span> <span data-ttu-id="cc869-133">При необходимости измените их.</span><span class="sxs-lookup"><span data-stu-id="cc869-133">Correct them as necessary.</span></span> <span data-ttu-id="cc869-134">Учтите, что требования к объему памяти возросли.</span><span class="sxs-lookup"><span data-stu-id="cc869-134">Account for increased memory requirements.</span></span> <span data-ttu-id="cc869-135">Параметры по умолчанию приведены в разделе «Настройка параметров конфигурации сервера» электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cc869-135">Default settings are listed in "Setting Server Configuration Options" in SQL Server Books Online.</span></span>  
  
4.  <span data-ttu-id="cc869-136">Обратите внимание на сообщения инструкции DBCC MEMORYSTATUS и способ их изменения при появлении сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="cc869-136">Observe DBCC MEMORYSTATUS output and the way it changes when you see these error messages.</span></span>  
  
5.  <span data-ttu-id="cc869-137">Проверьте рабочую нагрузку (например, число параллельных сеансов, в текущий момент выполняющих запросы).</span><span class="sxs-lookup"><span data-stu-id="cc869-137">Check the workload (for example, number of concurrent sessions, currently executing queries).</span></span>  
  
 <span data-ttu-id="cc869-138">Следующие действия могут позволить использовать больший объем памяти в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="cc869-138">The following actions may make more memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="cc869-139">Если какие-либо отличные от [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] приложения используют необходимые ресурсы, попытайтесь прекратить выполнение этих приложений или перенесите их выполнение на отдельный сервер.</span><span class="sxs-lookup"><span data-stu-id="cc869-139">If applications besides [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are consuming resources, try stopping running these applications or consider running them on a separate server.</span></span> <span data-ttu-id="cc869-140">Это снизит внешнюю нагрузку на память.</span><span class="sxs-lookup"><span data-stu-id="cc869-140">This will remove external memory pressure.</span></span>  
  
-   <span data-ttu-id="cc869-141">Если установлен параметр **max server memory**, увеличьте его значение.</span><span class="sxs-lookup"><span data-stu-id="cc869-141">If you have configured **max server memory,** increase its setting.</span></span>  
  
 <span data-ttu-id="cc869-142">Выполните следующие команды DBCC для освобождения нескольких кэшей памяти [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc869-142">Run the following DBCC commands to free several [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory caches.</span></span>  
  
-   <span data-ttu-id="cc869-143">DBCC FREESYSTEMCACHE</span><span class="sxs-lookup"><span data-stu-id="cc869-143">DBCC FREESYSTEMCACHE</span></span>  
  
-   <span data-ttu-id="cc869-144">DBCC FREESESSIONCACHE</span><span class="sxs-lookup"><span data-stu-id="cc869-144">DBCC FREESESSIONCACHE</span></span>  
  
-   <span data-ttu-id="cc869-145">DBCC FREEPROCCACHE</span><span class="sxs-lookup"><span data-stu-id="cc869-145">DBCC FREEPROCCACHE</span></span>  
  
 <span data-ttu-id="cc869-146">Если проблема не исчезла, необходимо продолжить ее исследование и, возможно, снизить рабочую нагрузку.</span><span class="sxs-lookup"><span data-stu-id="cc869-146">If the problem continues, you will need to investigate further and possibly reduce workload.</span></span>  
  
  
