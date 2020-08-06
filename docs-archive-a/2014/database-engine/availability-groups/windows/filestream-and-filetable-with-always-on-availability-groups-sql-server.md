---
title: FILESTREAM и FileTable с группы доступности AlwaysOn (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], Availability Groups
- FILESTREAM [SQL Server], Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: fdceda9a-a9db-4d1d-8745-345992164a98
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e7de7b4d66890bb5f1fe49799844f666de81f4db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658990"
---
# <a name="filestream-and-filetable-with-alwayson-availability-groups-sql-server"></a><span data-ttu-id="7e08c-102">FILESTREAM и FileTable с группами доступности AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7e08c-102">FILESTREAM and FileTable with AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="7e08c-103">В этом разделе содержатся сведения об использовании возможностей FILESTREAM и FileTable с [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7e08c-103">This topic contains information about the using the FILESTREAM and FileTable features with [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="7e08c-104">Поддерживаются все функции FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="7e08c-104">All FILESTREAM functionality is supported.</span></span> <span data-ttu-id="7e08c-105">После отработки отказа доступ к данным FILESTREAM можно получить как на доступных для чтения вторичных репликах, так и на новой первичной реплике.</span><span class="sxs-lookup"><span data-stu-id="7e08c-105">After a failover, FILESTREAM data is accessible on both readable secondary replicas and on the new primary.</span></span>  
  
 <span data-ttu-id="7e08c-106">Функции FileTable поддерживаются частично.</span><span class="sxs-lookup"><span data-stu-id="7e08c-106">FileTable functionality is partially supported.</span></span> <span data-ttu-id="7e08c-107">После отработки отказа данные FileTable будут доступны в первичной реплике, при этом они не будут доступны на вторичных репликах, из которых можно выполнять чтение.</span><span class="sxs-lookup"><span data-stu-id="7e08c-107">After a failover, FileTable data is accessible on the primary replica, but FileTable data is not accessible on readable secondary replicas.</span></span>  
  
 <span data-ttu-id="7e08c-108">**В этом разделе.**</span><span class="sxs-lookup"><span data-stu-id="7e08c-108">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="7e08c-109">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="7e08c-109">Prerequisites</span></span>](#Prerequisites)  
  
-   [<span data-ttu-id="7e08c-110">Использование имен виртуальной сети для доступа через FILESTREAM или FileTable.</span><span class="sxs-lookup"><span data-stu-id="7e08c-110">Using Virtual Network Names (VNNs) for FILESTREAM and FileTable Access</span></span>](#vnn)  
  
-   [<span data-ttu-id="7e08c-111">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="7e08c-111">Related Tasks</span></span>](#RelatedTasks)  
  
-   [<span data-ttu-id="7e08c-112">См. также</span><span class="sxs-lookup"><span data-stu-id="7e08c-112">Related Content</span></span>](#RelatedContent)  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="7e08c-113">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="7e08c-113">Prerequisites</span></span>  
  
-   <span data-ttu-id="7e08c-114">Перед добавлением в группу доступности базы данных, в которой используется FILESTREAM (а также возможно и FileTable), следует убедиться, что FILESTREAM поддерживается на всех экземплярах серверов, на которых размещены реплики доступности для группы доступности.</span><span class="sxs-lookup"><span data-stu-id="7e08c-114">Before adding a database that uses FILESTREAM, with or without FileTable, to an availability group, ensure that FILESTREAM is enabled on every server instance that hosts an availability replica for the availability group.</span></span> <span data-ttu-id="7e08c-115">Дополнительные сведения см. в статье [Enable and Configure FILESTREAM](../../../relational-databases/blob/enable-and-configure-filestream.md).</span><span class="sxs-lookup"><span data-stu-id="7e08c-115">For more information, see [Enable and Configure FILESTREAM](../../../relational-databases/blob/enable-and-configure-filestream.md).</span></span>  
  
##  <a name="using-virtual-network-names-vnns-for-filestream-and-filetable-access"></a><a name="vnn"></a><span data-ttu-id="7e08c-116">Использование имен виртуальных сетей (через) для доступа к FILESTREAM и FileTable</span><span class="sxs-lookup"><span data-stu-id="7e08c-116">Using Virtual Network Names (VNNs) for FILESTREAM and FileTable Access</span></span>  
 <span data-ttu-id="7e08c-117">Во время включения поддержки FILESTREAM для экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]создается ресурс уровня экземпляра, обеспечивающий доступ к данным FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="7e08c-117">When you enable FILESTREAM on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], an instance-level share is created to provide access to the FILESTREAM data.</span></span> <span data-ttu-id="7e08c-118">Доступ к этому ресурсу осуществляется по имени компьютера в следующем формате.</span><span class="sxs-lookup"><span data-stu-id="7e08c-118">You access this share by using the computer name in the following format:</span></span>  
  
 `\\<computer_name>\<filestream_share_name>`  
  
 <span data-ttu-id="7e08c-119">Однако в группе доступности AlwaysOn имя компьютера виртуализируется с использованием имени виртуальной сети.</span><span class="sxs-lookup"><span data-stu-id="7e08c-119">In an AlwaysOn availability group, however, the name of the computer is virtualized by using a Virtual Network Name, or VNN.</span></span> <span data-ttu-id="7e08c-120">Если компьютер является основной репликой в группе доступности, а базы данных в группе доступности содержат данные FILESTREAM, то будет также создан ресурс в области имен виртуальной сети, обеспечивающий доступ к данным FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="7e08c-120">When the computer is the primary replica in an availability group, and databases in the availability group contain FILESTREAM data, then a VNN-scoped share is also created to provide access to the FILESTREAM data.</span></span> <span data-ttu-id="7e08c-121">Это не повлияет на доступ Transact-SQL к данным FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="7e08c-121">This does not affect Transact-SQL access to FILESTREAM data.</span></span> <span data-ttu-id="7e08c-122">Однако приложения, использующие API-интерфейсы файловой системы, должны использовать ресурс в области имен виртуальной сети, путь которого задается в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="7e08c-122">However applications that use file system APIs have to use the VNN-scoped share, which has a path in the following format:</span></span>  
  
 `\\<VNN>\<filestream_share_name>`  
  
 <span data-ttu-id="7e08c-123">Ресурс в области имен виртуальной сети создается при наступлении одного из следующих событий.</span><span class="sxs-lookup"><span data-stu-id="7e08c-123">This VNN-scoped share is created when one of the following events occurs.</span></span>  
  
-   <span data-ttu-id="7e08c-124">Необходимо добавить базу данных, содержащую данные FILESTREAM, в группу доступности AlwaysOn в первичной реплике.</span><span class="sxs-lookup"><span data-stu-id="7e08c-124">You add a database that contains FILESTREAM data to an AlwaysOn availability group on the primary replica.</span></span> <span data-ttu-id="7e08c-125">В этом случае ресурс `\\<computer_name>\<filestream_share_name>` уже существует.</span><span class="sxs-lookup"><span data-stu-id="7e08c-125">In this case, the share `\\<computer_name>\<filestream_share_name>` already exists.</span></span> <span data-ttu-id="7e08c-126">Создается ресурс `\\<VNN>\<filestream_share_name>` .</span><span class="sxs-lookup"><span data-stu-id="7e08c-126">The share `\\<VNN>\<filestream_share_name>` is created.</span></span>  
  
-   <span data-ttu-id="7e08c-127">Поддержка FILESTREAM включается для потокового доступа ввода-вывода для первичной реплики, имеющей группы доступности.</span><span class="sxs-lookup"><span data-stu-id="7e08c-127">You enable FILESTREAM for file i/o streaming access on a primary replica that has availability groups.</span></span> <span data-ttu-id="7e08c-128">Создаются следующие ресурсы.</span><span class="sxs-lookup"><span data-stu-id="7e08c-128">The following shares are created:</span></span>  
  
    1.  `\\<computer_name>\<filestream_share_name>`  
  
    2.  <span data-ttu-id="7e08c-129">`\\<VNN1>\<filestream_share_name>` для группы доступности 1.</span><span class="sxs-lookup"><span data-stu-id="7e08c-129">`\\<VNN1>\<filestream_share_name>` for availability group 1.</span></span>  
  
    3.  <span data-ttu-id="7e08c-130">`\\<VNN2>\<filestream_share_name>` для группы доступности 2.</span><span class="sxs-lookup"><span data-stu-id="7e08c-130">`\\<VNN2>\<filestream_share_name>` for availability group 2.</span></span>  
  
 <span data-ttu-id="7e08c-131">Ресурсы в области имен виртуальной сети также распространяются во все вторичные реплики.</span><span class="sxs-lookup"><span data-stu-id="7e08c-131">These VNN-scoped shares are also propagated to all secondary replicas.</span></span>  
  
 <span data-ttu-id="7e08c-132">Если база данных, содержащая данные FILESTREAM или FileTable, принадлежит группе доступности:</span><span class="sxs-lookup"><span data-stu-id="7e08c-132">When the database that contains FILESTREAM or FileTable data belongs to an AlwaysOn availability group:</span></span>  
  
-   <span data-ttu-id="7e08c-133">Функции FILESTREAM и FileTable принимают или возвращают имена виртуальной сети, а не имена компьютеров.</span><span class="sxs-lookup"><span data-stu-id="7e08c-133">The FILESTREAM and FileTable functions accept or return virtual network names (VNNs) instead of computer names.</span></span> <span data-ttu-id="7e08c-134">Дополнительные сведения об этих функциях см. в разделе [Функции Filestream и FileTable (Transact-SQL)](/sql/relational-databases/system-functions/filestream-and-filetable-functions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7e08c-134">For more information about these functions, see [Filestream and FileTable Functions &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/filestream-and-filetable-functions-transact-sql).</span></span>  
  
-   <span data-ttu-id="7e08c-135">При осуществлении любого доступа к данным FILESTREAM или FileTable посредством API-интерфейса файловой системы будут использоваться имена виртуальной сети, а не имена компьютеров.</span><span class="sxs-lookup"><span data-stu-id="7e08c-135">All access to FILESTREAM or FileTable data through the file system APIs should use VNNs instead of computer names.</span></span>  
  
 <span data-ttu-id="7e08c-136">Если база данных входит в группу доступности, а ваше приложение пытается получить доступ к ресурсу по имени компьютера в формате `\\<computer_name>\<filestream_share_name>` , то выдается ошибка.</span><span class="sxs-lookup"><span data-stu-id="7e08c-136">If your application tries to access the share by using the computer name in the format `\\<computer_name>\<filestream_share_name>` when the database is part of an availability group, then an error is raised.</span></span>  
  
 <span data-ttu-id="7e08c-137">Если приложение пытается получить доступ к ресурсу с использованием пути в области имен виртуальной сети, а база данных не входит в группу доступности, запрос может завершиться успешно.</span><span class="sxs-lookup"><span data-stu-id="7e08c-137">If your application tries to access the share by using a VNN-scoped path when the database is not part of an availability group, then the request may succeed.</span></span> <span data-ttu-id="7e08c-138">В этом случае имя виртуальной сети будет разрешено в имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="7e08c-138">In this case, the virtual network name is resolved to the computer name.</span></span> <span data-ttu-id="7e08c-139">Однако так поступать не рекомендуется, поскольку путь в области имен виртуальной сети перестанет функционировать при удалении группы доступности.</span><span class="sxs-lookup"><span data-stu-id="7e08c-139">However this usage is strongly discouraged, since the VNN-scoped path will stop working if the availability group is dropped.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="7e08c-140">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="7e08c-140">Related Tasks</span></span>  
  
-   [<span data-ttu-id="7e08c-141">Включение и настройка FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="7e08c-141">Enable and Configure FILESTREAM</span></span>](../../../relational-databases/blob/enable-and-configure-filestream.md)  
  
-   [<span data-ttu-id="7e08c-142">Включение необходимых компонентов для таблицы FileTable</span><span class="sxs-lookup"><span data-stu-id="7e08c-142">Enable the Prerequisites for FileTable</span></span>](../../../relational-databases/blob/enable-the-prerequisites-for-filetable.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="7e08c-143">См. также</span><span class="sxs-lookup"><span data-stu-id="7e08c-143">Related Content</span></span>  
 <span data-ttu-id="7e08c-144">Нет.</span><span class="sxs-lookup"><span data-stu-id="7e08c-144">None.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e08c-145">См. также:</span><span class="sxs-lookup"><span data-stu-id="7e08c-145">See Also</span></span>  
 [<span data-ttu-id="7e08c-146">Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7e08c-146">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
