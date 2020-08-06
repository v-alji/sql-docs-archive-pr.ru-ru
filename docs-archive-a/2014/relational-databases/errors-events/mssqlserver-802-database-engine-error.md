---
title: MSSQLSERVER_802 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 802 (Database Engine error)
ms.assetid: 5892ed24-4dcb-4bf9-a8a4-a7ca898832d5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9edcdda1410d7651f7c7531ef98c64c85741f15a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669431"
---
# <a name="mssqlserver_802"></a><span data-ttu-id="0f0d4-102">MSSQLSERVER_802</span><span class="sxs-lookup"><span data-stu-id="0f0d4-102">MSSQLSERVER_802</span></span>
    
## <a name="details"></a><span data-ttu-id="0f0d4-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="0f0d4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0f0d4-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="0f0d4-104">Product Name</span></span>|<span data-ttu-id="0f0d4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0f0d4-105">SQL Server</span></span>|  
|<span data-ttu-id="0f0d4-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="0f0d4-106">Event ID</span></span>|<span data-ttu-id="0f0d4-107">802</span><span class="sxs-lookup"><span data-stu-id="0f0d4-107">802</span></span>|  
|<span data-ttu-id="0f0d4-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="0f0d4-108">Event Source</span></span>|<span data-ttu-id="0f0d4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0f0d4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0f0d4-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="0f0d4-110">Component</span></span>|<span data-ttu-id="0f0d4-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0f0d4-111">SQLEngine</span></span>|  
|<span data-ttu-id="0f0d4-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="0f0d4-112">Symbolic Name</span></span>|<span data-ttu-id="0f0d4-113">NO_BUFS</span><span class="sxs-lookup"><span data-stu-id="0f0d4-113">NO_BUFS</span></span>|  
|<span data-ttu-id="0f0d4-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="0f0d4-114">Message Text</span></span>|<span data-ttu-id="0f0d4-115">Недостаточно свободной памяти в буферном пуле.</span><span class="sxs-lookup"><span data-stu-id="0f0d4-115">There is insufficient memory available in the buffer pool.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0f0d4-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="0f0d4-116">Explanation</span></span>  
 <span data-ttu-id="0f0d4-117">Это происходит, если буферный пул заполнен и не может больше увеличиваться.</span><span class="sxs-lookup"><span data-stu-id="0f0d4-117">This is caused when the buffer pool is full and the buffer pool can not grow any larger.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0f0d4-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="0f0d4-118">User Action</span></span>  
 <span data-ttu-id="0f0d4-119">Далее представлены общие шаги, которые помогут при устранении неполадок с памятью.</span><span class="sxs-lookup"><span data-stu-id="0f0d4-119">The following list outlines general steps that will help in troubleshooting memory errors:</span></span>  
  
1.  <span data-ttu-id="0f0d4-120">Проверьте, не используют ли память данного сервера другие приложения или службы.</span><span class="sxs-lookup"><span data-stu-id="0f0d4-120">Verify whether other applications or services are consuming memory on this server.</span></span> <span data-ttu-id="0f0d4-121">Измените настройки таким образом, чтобы менее важные приложения или службы использовали меньший объем памяти.</span><span class="sxs-lookup"><span data-stu-id="0f0d4-121">Reconfigure less critical applications or services to consume less memory.</span></span>  
  
2.  <span data-ttu-id="0f0d4-122">Начните сбор счетчиков системного монитора для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **: Buffer Manager**, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **: Memory Manager**.</span><span class="sxs-lookup"><span data-stu-id="0f0d4-122">Start collecting performance monitor counters for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**: Buffer Manager**, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**: Memory Manager**.</span></span>  
  
3.  <span data-ttu-id="0f0d4-123">Проверьте следующие параметры конфигурации памяти [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="0f0d4-123">Check the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory configuration parameters:</span></span>  
  
    -   <span data-ttu-id="0f0d4-124">**max server memory**</span><span class="sxs-lookup"><span data-stu-id="0f0d4-124">**max server memory**</span></span>  
  
    -   <span data-ttu-id="0f0d4-125">**min server memory**</span><span class="sxs-lookup"><span data-stu-id="0f0d4-125">**min server memory**</span></span>  
  
    -   <span data-ttu-id="0f0d4-126">**min memory per query**</span><span class="sxs-lookup"><span data-stu-id="0f0d4-126">**min memory per query**</span></span>  
  
     <span data-ttu-id="0f0d4-127">Обратите внимание на любые необычные параметры и исправьте их при необходимости.</span><span class="sxs-lookup"><span data-stu-id="0f0d4-127">Notice any unusual settings and correct them as necessary.</span></span> <span data-ttu-id="0f0d4-128">Принимайте во внимание тот факт, что в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] предъявляются повышенные требования к доступному объему памяти.</span><span class="sxs-lookup"><span data-stu-id="0f0d4-128">Account for increased memory requirements for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0f0d4-129">Настройки по умолчанию приведены в электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в разделе «Настройка параметров конфигурации сервера».</span><span class="sxs-lookup"><span data-stu-id="0f0d4-129">Default settings are listed in "Setting Server Configuration Options" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
4.  <span data-ttu-id="0f0d4-130">Обратите внимание на сообщения инструкции DBCC MEMORYSTATUS и способ их изменения при появлении сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="0f0d4-130">Observe DBCC MEMORYSTATUS output and the way it changes when you see these error messages.</span></span>  
  
5.  <span data-ttu-id="0f0d4-131">Проверьте рабочую нагрузку (число параллельных сеансов, выполняющихся запросов).</span><span class="sxs-lookup"><span data-stu-id="0f0d4-131">Check the workload (number of concurrent sessions, currently executing queries).</span></span>  
  
 <span data-ttu-id="0f0d4-132">Следующие действия могут позволить использовать больший объем памяти в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="0f0d4-132">The following actions may make more memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="0f0d4-133">Если ресурсы потребляют приложения, выполняющиеся вместе с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], попробуйте остановить эти приложения или выполнить их на отдельном сервере.</span><span class="sxs-lookup"><span data-stu-id="0f0d4-133">If applications besides [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are consuming resources, try stopping these applications or running them on a separate server.</span></span>  
  
-   <span data-ttu-id="0f0d4-134">Если установлен параметр **max server memory**, увеличьте его значение.</span><span class="sxs-lookup"><span data-stu-id="0f0d4-134">If you have configured **max server memory,** increase the setting.</span></span>  
  
 <span data-ttu-id="0f0d4-135">Выполните следующие команды DBCC для освобождения нескольких кэшей памяти [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f0d4-135">Run the following DBCC commands to free several [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory caches.</span></span>  
  
-   <span data-ttu-id="0f0d4-136">DBCC FREESYSTEMCACHE</span><span class="sxs-lookup"><span data-stu-id="0f0d4-136">DBCC FREESYSTEMCACHE</span></span>  
  
-   <span data-ttu-id="0f0d4-137">DBCC FREESESSIONCACHE</span><span class="sxs-lookup"><span data-stu-id="0f0d4-137">DBCC FREESESSIONCACHE</span></span>  
  
-   <span data-ttu-id="0f0d4-138">DBCC FREEPROCCACHE</span><span class="sxs-lookup"><span data-stu-id="0f0d4-138">DBCC FREEPROCCACHE</span></span>  
  
 <span data-ttu-id="0f0d4-139">Если проблема не исчезла, необходимо продолжить ее исследование и, возможно, снизить рабочую нагрузку.</span><span class="sxs-lookup"><span data-stu-id="0f0d4-139">If the problem continues, you will need to investigate further and possibly reduce workload.</span></span>  
  
  
