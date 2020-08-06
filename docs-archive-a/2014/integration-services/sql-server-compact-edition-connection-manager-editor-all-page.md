---
title: Редактор диспетчера подключений SQL Server Compact Edition (страница «все») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sqlmobileconnection.all.f1
helpviewer_keywords:
- SQL Server Compact Connection Manager Editor
ms.assetid: f9fbff4b-c502-44b3-8e7b-398d66e82206
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4f881d63de5435426475c3aed4b666870d706b40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658304"
---
# <a name="sql-server-compact-edition-connection-manager-editor-all-page"></a><span data-ttu-id="c0680-102">Редактор диспетчера соединений SQL Server Compact Edition (страница «Все»)</span><span class="sxs-lookup"><span data-stu-id="c0680-102">SQL Server Compact Edition Connection Manager Editor (All Page)</span></span>
  <span data-ttu-id="c0680-103">Диалоговое окно **Диспетчер соединений SQL Server Compact Edition** позволяет задать свойства для соединения с базой данных [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="c0680-103">Use the **SQL Server Compact Edition Connection Manager** dialog box to specify properties for connecting to a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
 <span data-ttu-id="c0680-104">Дополнительные сведения о диспетчере соединений [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact Edition см. в разделе [Диспетчер соединений SQL Server Compact Edition](connection-manager/sql-server-compact-edition-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="c0680-104">To learn more about the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact Edition connection manager, see [SQL Server Compact Edition Connection Manager](connection-manager/sql-server-compact-edition-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c0680-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="c0680-105">Options</span></span>  
 <span data-ttu-id="c0680-106">**Пороговое значение для автосжатия**</span><span class="sxs-lookup"><span data-stu-id="c0680-106">**AutoShrink Threshold**</span></span>  
 <span data-ttu-id="c0680-107">Укажите в виде процентов допустимый размер свободного пространства в базе данных [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact перед запуском процесса автосжатия.</span><span class="sxs-lookup"><span data-stu-id="c0680-107">Specify the amount of free space, as a percentage, that is allowed in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database before the autoshrink process runs.</span></span>  
  
 <span data-ttu-id="c0680-108">**Укрупнение блокировок по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="c0680-108">**Default Lock Escalation**</span></span>  
 <span data-ttu-id="c0680-109">Определите число блокировок базы данных, которые установит база данных [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact, прежде чем попытается укрупнить блокировки.</span><span class="sxs-lookup"><span data-stu-id="c0680-109">Specify the number of database locks that the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database acquires before it tries to escalate locks.</span></span>  
  
 <span data-ttu-id="c0680-110">**Время ожидания блокировок по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="c0680-110">**Default Lock Timeout**</span></span>  
 <span data-ttu-id="c0680-111">Укажите время по умолчанию (в миллисекундах) ожидания транзакцией блокировок базы данных.</span><span class="sxs-lookup"><span data-stu-id="c0680-111">Specify the default interval, in milliseconds, that a transaction will wait for a lock.</span></span>  
  
 <span data-ttu-id="c0680-112">**Интервал записи**</span><span class="sxs-lookup"><span data-stu-id="c0680-112">**Flush Interval**</span></span>  
 <span data-ttu-id="c0680-113">Определите интервал (в секундах) между записями данных на диск зафиксированными транзакциями.</span><span class="sxs-lookup"><span data-stu-id="c0680-113">Specify the interval, in seconds, between committed transactions to flush data to disk.</span></span>  
  
 <span data-ttu-id="c0680-114">**Идентификатор локали**</span><span class="sxs-lookup"><span data-stu-id="c0680-114">**Locale Identifier**</span></span>  
 <span data-ttu-id="c0680-115">Задайте идентификатор локали (LCID) базы данных [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="c0680-115">Specify the Locale ID (LCID) of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
 <span data-ttu-id="c0680-116">**Максимальный размер буфера**</span><span class="sxs-lookup"><span data-stu-id="c0680-116">**Max Buffer Size**</span></span>  
 <span data-ttu-id="c0680-117">Определите максимальный объем памяти (в килобайтах), используемый базой данных [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact перед записью данных на диск.</span><span class="sxs-lookup"><span data-stu-id="c0680-117">Specify the maximum amount of memory, in kilobytes, that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact uses before flushing data to disk.</span></span>  
  
 <span data-ttu-id="c0680-118">**Максимальный размер базы данных**</span><span class="sxs-lookup"><span data-stu-id="c0680-118">**Max Database Size**</span></span>  
 <span data-ttu-id="c0680-119">Укажите максимальный размер (в мегабайтах) базы данных [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="c0680-119">Specify the maximum size, in megabytes, of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
 <span data-ttu-id="c0680-120">**Режим**</span><span class="sxs-lookup"><span data-stu-id="c0680-120">**Mode**</span></span>  
 <span data-ttu-id="c0680-121">Укажите файловый режим, в котором будет открываться база данных [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="c0680-121">Specify the file mode in which to open the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span> <span data-ttu-id="c0680-122">Значение этого свойства по умолчанию равно **Чтение и запись**.</span><span class="sxs-lookup"><span data-stu-id="c0680-122">The default value for this property is **Read Write**.</span></span>  
  
 <span data-ttu-id="c0680-123">Параметр «Режим» имеет четыре значения, описанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="c0680-123">The Mode option has four values, as described in the following table.</span></span>  
  
|<span data-ttu-id="c0680-124">Значение</span><span class="sxs-lookup"><span data-stu-id="c0680-124">Value</span></span>|<span data-ttu-id="c0680-125">Описание</span><span class="sxs-lookup"><span data-stu-id="c0680-125">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c0680-126">**Только чтение**</span><span class="sxs-lookup"><span data-stu-id="c0680-126">**Read Only**</span></span>|<span data-ttu-id="c0680-127">Определяет доступ к базе данных только для чтения.</span><span class="sxs-lookup"><span data-stu-id="c0680-127">Specifies read-only access to the database.</span></span>|  
|<span data-ttu-id="c0680-128">**Чтение и запись**</span><span class="sxs-lookup"><span data-stu-id="c0680-128">**Read Write**</span></span>|<span data-ttu-id="c0680-129">Назначает разрешения на чтение и запись базы данных.</span><span class="sxs-lookup"><span data-stu-id="c0680-129">Specifies read/write permission to the database.</span></span>|  
|<span data-ttu-id="c0680-130">**Монопольный доступ**</span><span class="sxs-lookup"><span data-stu-id="c0680-130">**Exclusive**</span></span>|<span data-ttu-id="c0680-131">Задает монопольный доступ к базе данных.</span><span class="sxs-lookup"><span data-stu-id="c0680-131">Specifies exclusive access to the database.</span></span>|  
|<span data-ttu-id="c0680-132">**Общий доступ на чтение**</span><span class="sxs-lookup"><span data-stu-id="c0680-132">**Shared Read**</span></span>|<span data-ttu-id="c0680-133">Определяет возможность одновременного чтения базы данных другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="c0680-133">Specifies that other users can read from the database at the same time.</span></span>|  
  
 <span data-ttu-id="c0680-134">**Persist Security Info**</span><span class="sxs-lookup"><span data-stu-id="c0680-134">**Persist Security Info**</span></span>  
 <span data-ttu-id="c0680-135">Определите, будет ли осуществляться возврат сведений о безопасности в виде части строки соединения.</span><span class="sxs-lookup"><span data-stu-id="c0680-135">Specify whether security information is returned as part of the connection string.</span></span> <span data-ttu-id="c0680-136">Значение по умолчанию этого параметра равно **False**.</span><span class="sxs-lookup"><span data-stu-id="c0680-136">The default value for this option is **False**.</span></span>  
  
 <span data-ttu-id="c0680-137">**Каталог временных файлов**</span><span class="sxs-lookup"><span data-stu-id="c0680-137">**Temp File Directory**</span></span>  
 <span data-ttu-id="c0680-138">Задайте расположение временных файлов базы данных [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="c0680-138">Specify the location of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact temporary database file.</span></span>  
  
 <span data-ttu-id="c0680-139">**Источник данных**</span><span class="sxs-lookup"><span data-stu-id="c0680-139">**Data Source**</span></span>  
 <span data-ttu-id="c0680-140">Укажите имя базы данных [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="c0680-140">Specify the name of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
 <span data-ttu-id="c0680-141">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="c0680-141">**Password**</span></span>  
 <span data-ttu-id="c0680-142">Введите пароль для базы данных [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="c0680-142">Enter the password for the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0680-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="c0680-143">See Also</span></span>  
 <span data-ttu-id="c0680-144">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="c0680-144">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="c0680-145">Редактор диспетчера подключений SQL Server Compact Edition (страница "Соединение")</span><span class="sxs-lookup"><span data-stu-id="c0680-145">SQL Server Compact Edition Connection Manager Editor &#40;Connection Page&#41;</span></span>](../../2014/integration-services/sql-server-compact-edition-connection-manager-editor-connection-page.md)  
  
  
