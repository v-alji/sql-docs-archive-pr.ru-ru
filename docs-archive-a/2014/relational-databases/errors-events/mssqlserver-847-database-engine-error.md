---
title: MSSQLSERVER_847 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 847 (Database Engine error)
ms.assetid: 67208b7c-bd8d-48a1-9f70-a6488e0f5f9b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6b2d5c0a35533700606a44867d2a51cf9087e399
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666081"
---
# <a name="mssqlserver_847"></a><span data-ttu-id="b4158-102">MSSQLSERVER_847</span><span class="sxs-lookup"><span data-stu-id="b4158-102">MSSQLSERVER_847</span></span>
    
## <a name="details"></a><span data-ttu-id="b4158-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="b4158-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b4158-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="b4158-104">Product Name</span></span>|<span data-ttu-id="b4158-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b4158-105">SQL Server</span></span>|  
|<span data-ttu-id="b4158-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="b4158-106">Event ID</span></span>|<span data-ttu-id="b4158-107">847</span><span class="sxs-lookup"><span data-stu-id="b4158-107">847</span></span>|  
|<span data-ttu-id="b4158-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="b4158-108">Event Source</span></span>|<span data-ttu-id="b4158-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b4158-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b4158-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="b4158-110">Component</span></span>|<span data-ttu-id="b4158-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b4158-111">SQLEngine</span></span>|  
|<span data-ttu-id="b4158-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="b4158-112">Symbolic Name</span></span>|<span data-ttu-id="b4158-113">Недоступно</span><span class="sxs-lookup"><span data-stu-id="b4158-113">N/A</span></span>|  
|<span data-ttu-id="b4158-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="b4158-114">Message Text</span></span>|<span data-ttu-id="b4158-115">Истекло время ожидания кратковременной блокировки: класс '%ls', идентификатор %p, тип %d, задача 0x%p: %d, время ожидания %d, флаги 0x%I64x, задача-владелец 0x%p.</span><span class="sxs-lookup"><span data-stu-id="b4158-115">Time-out occurred while waiting for latch: class '%ls', id %p, type %d, Task 0x%p : %d, waittime %d, flags 0x%I64x, owning task 0x%p.</span></span> <span data-ttu-id="b4158-116">Продолжение ожидания.</span><span class="sxs-lookup"><span data-stu-id="b4158-116">Continuing to wait.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b4158-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="b4158-117">Explanation</span></span>  
 <span data-ttu-id="b4158-118">Возможно, компьютер не отвечает на запросы, истекло время ожидания либо происходит какой-то сбой в тот момент, когда [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] записывает ошибки кратковременной блокировки буфера в журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4158-118">A computer might stop responding, or a time-out or some other disruption of regular operations might occur at the same time that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] writes buffer latch errors to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log.</span></span>  
  
 <span data-ttu-id="b4158-119">Если в сообщении в поле состояния указано значение 0x04, то [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ожидает операцию ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="b4158-119">If the stat field in the message has the value of 0x04 on, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is waiting for an I/O operation.</span></span> <span data-ttu-id="b4158-120">Кроме того, может быть получено сообщение [MSSQLSERVER_833](mssqlserver-833-database-engine-error.md) в журнале ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4158-120">You may also receive message [MSSQLSERVER_833](mssqlserver-833-database-engine-error.md) in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log.</span></span>  
  
 <span data-ttu-id="b4158-121">Если в сообщении в поле состояния указано значение stat 0x04 off, это означает серьезное состязание на странице.</span><span class="sxs-lookup"><span data-stu-id="b4158-121">If the stat field in the message has the value 0x04 off, there is heavy contention for a page.</span></span> <span data-ttu-id="b4158-122">Если объектом является страница данных, это может быть связано с неэффективной разработкой кода.</span><span class="sxs-lookup"><span data-stu-id="b4158-122">If the object is a data page, this can be caused by inefficient code design.</span></span> <span data-ttu-id="b4158-123">Если страница не является страницей данных, то причиной ошибки могут быть узкие места серверов, например недостаток ресурсов оборудования.</span><span class="sxs-lookup"><span data-stu-id="b4158-123">If the page is nondata, the error might be caused by server bottlenecks, such as insufficient hardware resources.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b4158-124">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="b4158-124">User Action</span></span>  
 <span data-ttu-id="b4158-125">Для решения проблемы в зависимости от среды выполнение одного или нескольких следующих шагов может сократить количество сообщений об ошибках или исключить их.</span><span class="sxs-lookup"><span data-stu-id="b4158-125">To work around this problem, depending on your environment, one or more of the following steps might reduce or eliminate the error messages:</span></span>  
  
-   <span data-ttu-id="b4158-126">Определите наличие узких мест оборудования.</span><span class="sxs-lookup"><span data-stu-id="b4158-126">Determine whether you have any hardware bottlenecks.</span></span> <span data-ttu-id="b4158-127">При необходимости обновите оборудование, чтобы оно поддерживало требования среды к конфигурации, запросам и нагрузке.</span><span class="sxs-lookup"><span data-stu-id="b4158-127">If it is necessary, upgrade your hardware so that it can support the configuration, query, and load requirements of your environment.</span></span> <span data-ttu-id="b4158-128">Дополнительные сведения об узких местах см. в статье [Выявление узких мест](../performance/identify-bottlenecks.md).</span><span class="sxs-lookup"><span data-stu-id="b4158-128">For more information about bottlenecks, see [Identify Bottlenecks](../performance/identify-bottlenecks.md).</span></span>  
  
-   <span data-ttu-id="b4158-129">Проверьте все зарегистрированные в журнале ошибки и запустите программу диагностики, предоставляемую поставщиком оборудования.</span><span class="sxs-lookup"><span data-stu-id="b4158-129">Check for any logged errors and run any diagnostics provided by your hardware vendor.</span></span>  
  
-   <span data-ttu-id="b4158-130">Убедитесь, что жесткие диски не сжаты.</span><span class="sxs-lookup"><span data-stu-id="b4158-130">Make sure that your disk drives are not compressed.</span></span> <span data-ttu-id="b4158-131">Хранение данных или файлов журнала на сжатых дисках не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="b4158-131">Storing data or log files on compressed drives is not supported.</span></span> <span data-ttu-id="b4158-132">Дополнительные сведения о физических файлах см. в статье [Файлы и файловые группы базы данных](../databases/database-files-and-filegroups.md).</span><span class="sxs-lookup"><span data-stu-id="b4158-132">For more information about physical files, see [Database Files and Filegroups](../databases/database-files-and-filegroups.md).</span></span>  
  
-   <span data-ttu-id="b4158-133">Проверьте, перестанут ли возникать сообщения об ошибках после отключения следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="b4158-133">See whether the error messages disappear when you set the following options to off:</span></span>  
  
    -   <span data-ttu-id="b4158-134">Параметр конфигурации SQL Server «повышение приоритета».</span><span class="sxs-lookup"><span data-stu-id="b4158-134">SQL Server priority boost configuration option</span></span>  
  
    -   <span data-ttu-id="b4158-135">Параметр «использование упрощенных пулов» (в режиме волокон).</span><span class="sxs-lookup"><span data-stu-id="b4158-135">Lightweight pooling (fiber mode) option</span></span>  
  
    -   <span data-ttu-id="b4158-136">Параметр «set working set size».</span><span class="sxs-lookup"><span data-stu-id="b4158-136">Set working set size option</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b4158-137">Приведенные выше параметры зачастую ухудшают производительность, если их значения по умолчанию отличаются от OFF.</span><span class="sxs-lookup"><span data-stu-id="b4158-137">The previous settings can frequently be counter-productive if you change them from their default setting of OFF.</span></span> <span data-ttu-id="b4158-138">Дополнительные сведения см. в статье [Параметры конфигурации сервера (SQL Server)](../../database-engine/configure-windows/server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b4158-138">For more information about the settings, see [Server Configuration Options &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md).</span></span>  
  
-   <span data-ttu-id="b4158-139">Настройте запросы таким образом, чтобы система потребляла меньший объем ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b4158-139">Tune queries to reduce resources used on the system.</span></span> <span data-ttu-id="b4158-140">Настройка производительности поможет снизить нагрузку на систему и сократить время отклика отдельных запросов.</span><span class="sxs-lookup"><span data-stu-id="b4158-140">Performance tuning will help reduce the stress on a system and improve response time for individual queries.</span></span>  
  
-   <span data-ttu-id="b4158-141">Присвойте параметру AUTO_SHRINK значение OFF для снижения затрат на изменение размера базы данных.</span><span class="sxs-lookup"><span data-stu-id="b4158-141">Set the AUTO_SHRINK option to OFF to reduce the overhead of changes to the database size.</span></span>  
  
-   <span data-ttu-id="b4158-142">Убедитесь, что приращения, заданные с помощью параметра FILEGROWTH, велики настолько, чтобы выполняться достаточно редко.</span><span class="sxs-lookup"><span data-stu-id="b4158-142">Make sure that you set the FILEGROWTH option to increments that are large enough to be infrequent.</span></span> <span data-ttu-id="b4158-143">Запланируйте задание проверки доступного места на диске в базах данных, затем задайте увеличение размера базы данных в периоды наименьшей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="b4158-143">Schedule a job to check the available space in the databases, and then increase the database size during nonpeak hours.</span></span>  
  
  
