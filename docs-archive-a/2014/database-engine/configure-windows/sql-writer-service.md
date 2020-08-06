---
title: Служба "Модуль записи SQL" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- VDI [SQL Server]
- restoring [SQL Server], SQL Writer Service
- backups [SQL Server], while SQL Server running
- Volume Shadow Copy Service
- volume backups while running [SQL Server]
- Virtual Backup Device Interface [SQL Server]
- SQL Writer Service
- services [SQL Server], SQL Writer
- MSDE Writer
- VSS
ms.assetid: 0f299867-f499-4c2a-ad6f-b2ef1869381d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 310722c6617c7a2c9e0f384ec23ae371ab230536
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655348"
---
# <a name="sql-writer-service"></a><span data-ttu-id="4965d-102">cлужба «Модуль записи SQL»</span><span class="sxs-lookup"><span data-stu-id="4965d-102">SQL Writer Service</span></span>
  <span data-ttu-id="4965d-103">Служба «Модуль записи SQL» предоставляет дополнительные возможности резервного копирования и восстановления [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с помощью механизма службы теневого копирования тома.</span><span class="sxs-lookup"><span data-stu-id="4965d-103">The SQL Writer Service provides added functionality for backup and restore of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] through the Volume Shadow Copy Service framework.</span></span>  
  
 <span data-ttu-id="4965d-104">Служба «Модуль записи SQL» устанавливается автоматически.</span><span class="sxs-lookup"><span data-stu-id="4965d-104">The SQL Writer Service is installed automatically.</span></span> <span data-ttu-id="4965d-105">Она должна запускаться при запросе службы теневого копирования томов (VSS) резервного копирования или восстановления.</span><span class="sxs-lookup"><span data-stu-id="4965d-105">It must be running when the Volume Shadow Copy Service (VSS) application requests a backup or restore.</span></span> <span data-ttu-id="4965d-106">Служба настраивается с помощью оснастки «Службы» [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="4965d-106">To configure the service, use the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Services applet.</span></span> <span data-ttu-id="4965d-107">Служба модуля записи SQL устанавливается на всех операционных системах.</span><span class="sxs-lookup"><span data-stu-id="4965d-107">The SQL Writer Service installs on all operating systems.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="4965d-108">Назначение</span><span class="sxs-lookup"><span data-stu-id="4965d-108">Purpose</span></span>  
 <span data-ttu-id="4965d-109">Во время работы компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] блокирует файлы данных и обладает монопольными правами доступа к ним.</span><span class="sxs-lookup"><span data-stu-id="4965d-109">When running, [!INCLUDE[ssDE](../../includes/ssde-md.md)] locks and has exclusive access to the data files.</span></span> <span data-ttu-id="4965d-110">Если служба «Модуль записи SQL» не запущена, то у программ резервного копирования, работающих в Windows, нет доступа к файлам данных, а резервное копирование должно выполняться с помощью функции резервного копирования [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4965d-110">When the SQL Writer Service is not running, backup programs running in Windows do not have access to the data files, and backups must be performed using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup.</span></span>  
  
 <span data-ttu-id="4965d-111">Служба «Модуль записи SQL» позволяет во время работы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] разрешить программам резервного копирования Windows копирование файлов данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4965d-111">Use the SQL Writer Service to permit Windows backup programs to copy [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data files while [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span>  
  
## <a name="volume-shadow-copy-service"></a><span data-ttu-id="4965d-112">служба «Теневое копирование томов»</span><span class="sxs-lookup"><span data-stu-id="4965d-112">Volume Shadow Copy Service</span></span>  
 <span data-ttu-id="4965d-113">Служба теневого копирования томов — это набор API-интерфейсов COM, которые обеспечивают платформу для реализации резервного копирования томов во время записи приложениями данных в эти тома.</span><span class="sxs-lookup"><span data-stu-id="4965d-113">The VSS is a set of COM APIs that implements a framework to allow volume backups to be performed while applications on a system continue to write to the volumes.</span></span> <span data-ttu-id="4965d-114">В службе теневого копирования томов предусмотрен согласованный интерфейс, обеспечивающий координацию пользовательских приложений, обновляющих данные на диске (модулей записи) и программ, выполняющих резервное копирование приложений (генераторов запросов).</span><span class="sxs-lookup"><span data-stu-id="4965d-114">The VSS provides a consistent interface that allows coordination between user applications that update data on disk (writers) and those that back up applications (requestors).</span></span>  
  
 <span data-ttu-id="4965d-115">Служба теневого копирования томов захватывает и копирует стабильные образы для резервного копирования в работающих системах, особенно на серверах. При этом не происходит чрезмерного понижения производительности и стабильности работы служб.</span><span class="sxs-lookup"><span data-stu-id="4965d-115">The VSS captures and copies stable images for backup on running systems, particularly servers, without unduly degrading the performance and stability of the services they provide.</span></span> <span data-ttu-id="4965d-116">Дополнительные сведения о службе теневого копирования томов см. в документации по Windows.</span><span class="sxs-lookup"><span data-stu-id="4965d-116">For more information on the VSS, see your Windows documentation.</span></span>  
  
## <a name="virtual-backup-device-interface-vdi"></a><span data-ttu-id="4965d-117">Интерфейс виртуальных устройств резервного копирования (VDI)</span><span class="sxs-lookup"><span data-stu-id="4965d-117">Virtual Backup Device Interface (VDI)</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="4965d-118">включает API с названием "Интерфейс виртуальных устройств резервного копирования" (VDI), который позволяет независимым поставщикам программного обеспечения встраивать [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в их продукты для поддержки операций резервного копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="4965d-118">provides an API called Virtual Backup Device Interface (VDI) that enables independent software vendors to integrate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] into their products for providing support for backup and restore operations.</span></span> <span data-ttu-id="4965d-119">Эти функции API обеспечивают максимальную надежность и производительность, а также поддерживают все функции резервного копирования и восстановления [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , включая полный набор возможностей оперативного и моментального резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="4965d-119">These APIs are engineered to provide maximum reliability and performance, and support the full range of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup and restore functionality, including the full range of hot and snapshot backup capabilities.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="4965d-120">Разрешения</span><span class="sxs-lookup"><span data-stu-id="4965d-120">Permissions</span></span>  
 <span data-ttu-id="4965d-121">Служба «Модуль записи SQL» должна запускаться под учетной записью **Local System** .</span><span class="sxs-lookup"><span data-stu-id="4965d-121">The SQL Writer service must run under the **Local System** account.</span></span> <span data-ttu-id="4965d-122">Модуль записи SQL использует имя входа **NT Service\SQLWriter** при подключении к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4965d-122">The SQL Writer service uses the **NT Service\SQLWriter** login to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4965d-123">С помощью имени входа **NT Service\SQLWriter** процесс записи SQL может запускаться на более низком уровне прав доступа в учетной записи, помеченной как **без имени входа**, что снижает потенциальную уязвимость.</span><span class="sxs-lookup"><span data-stu-id="4965d-123">Using the **NT Service\SQLWriter** login allows the SQL Writer process to run at a lower privilege level in an account designated as **no login**, which limits vulnerability.</span></span> <span data-ttu-id="4965d-124">Если модуль записи SQL отключен, то каждая служебная программа, которая полагается на моментальные снимки VSS, например System Center Data Protection Manager, а также некоторые другие продукты сторонних поставщиков, перестанет работать и будет сбоить с риском принятия нецелостных резервных копий баз данных.</span><span class="sxs-lookup"><span data-stu-id="4965d-124">If the SQL Writer service is disabled, then any utility which in relies on VSS snapshots, such as System Center Data Protection Manager, as well as some other 3rd-party products, would be broken, or worse, at risk of taking backups of databases which were not consistent.</span></span> <span data-ttu-id="4965d-125">Если ни службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ни система, где они выполняются, ни система их размещения (в случае виртуальной машины) не нуждаются в чем-либо помимо резервного копирования [!INCLUDE[tsql](../../includes/tsql-md.md)] , то модуль записи SQL можно спокойно отключить и удалить имя входа.</span><span class="sxs-lookup"><span data-stu-id="4965d-125">If neither [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the system it runs on, nor the host system (in the event of a virtual machine), need to use anything besides [!INCLUDE[tsql](../../includes/tsql-md.md)] backup, then the SQL Writer service can be safely disabled and the login removed.</span></span>  <span data-ttu-id="4965d-126">Обратите внимание, что модуль записи SQL может вызываться системой или резервной копией тома независимо от того, использует ли копия моментальные снимки напрямую или нет.</span><span class="sxs-lookup"><span data-stu-id="4965d-126">Note that the SQL Writer service may be invoked by a system or volume level backup, whether the backup is directly snapshot-based or not.</span></span> <span data-ttu-id="4965d-127">Некоторые продукты для резервного копирования системы используют службу VSS во избежание блокировки по открытым или заблокированным файлам.</span><span class="sxs-lookup"><span data-stu-id="4965d-127">Some system backup products use VSS to avoid being blocked by open or locked files.</span></span> <span data-ttu-id="4965d-128">Модулю записи SQL требуются повышенные разрешения в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , поскольку во время его работы на короткий момент времени замораживаются все операции ввода и вывода для экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4965d-128">The SQL Writer service needs elevated permissions in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] because in the course of its activities it briefly freezes all I/O for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="features"></a><span data-ttu-id="4965d-129">Компоненты</span><span class="sxs-lookup"><span data-stu-id="4965d-129">Features</span></span>  
 <span data-ttu-id="4965d-130">Служба «Модуль записи SQL» поддерживает:</span><span class="sxs-lookup"><span data-stu-id="4965d-130">SQL Writer supports:</span></span>  
  
-   <span data-ttu-id="4965d-131">полное резервное копирование и восстановление баз данных, включая полнотекстовые каталоги;</span><span class="sxs-lookup"><span data-stu-id="4965d-131">Full database backup and restore including full-text catalogs</span></span>  
  
-   <span data-ttu-id="4965d-132">разностное резервное копирование и восстановление;</span><span class="sxs-lookup"><span data-stu-id="4965d-132">Differential backup and restore</span></span>  
  
-   <span data-ttu-id="4965d-133">восстановление с перемещением;</span><span class="sxs-lookup"><span data-stu-id="4965d-133">Restore with move</span></span>  
  
-   <span data-ttu-id="4965d-134">переименование базы данных;</span><span class="sxs-lookup"><span data-stu-id="4965d-134">Database rename</span></span>  
  
-   <span data-ttu-id="4965d-135">резервная копия, предназначенная только для копирования;</span><span class="sxs-lookup"><span data-stu-id="4965d-135">Copy-only backup</span></span>  
  
-   <span data-ttu-id="4965d-136">автоматическое восстановление моментального снимка базы данных.</span><span class="sxs-lookup"><span data-stu-id="4965d-136">Auto-recovery of database snapshot</span></span>  
  
 <span data-ttu-id="4965d-137">Служба «Модуль записи SQL» не поддерживает:</span><span class="sxs-lookup"><span data-stu-id="4965d-137">SQL Writer does not support:</span></span>  
  
-   <span data-ttu-id="4965d-138">Резервные копии журналов;</span><span class="sxs-lookup"><span data-stu-id="4965d-138">Log backups</span></span>  
  
-   <span data-ttu-id="4965d-139">Резервное копирование файлов и файловых групп;</span><span class="sxs-lookup"><span data-stu-id="4965d-139">File and filegroup backup</span></span>  
  
-   <span data-ttu-id="4965d-140">Восстановление страницы</span><span class="sxs-lookup"><span data-stu-id="4965d-140">Page restore</span></span>  
  
  
