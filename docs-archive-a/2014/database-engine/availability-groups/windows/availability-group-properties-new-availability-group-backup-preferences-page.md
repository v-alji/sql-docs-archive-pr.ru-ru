---
title: 'Свойства группы доступности: создание группы доступности (страница "Параметры резервного копирования") | Документация Майкрософт'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroupproperties.backuppreferences.f1
helpviewer_keywords:
- read-only routing
ms.assetid: 65fff22d-5963-4a8c-8b31-fe9ab247a03e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7914d4b1d7af06bcaf4f3fd05a260138e3edf5fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655378"
---
# <a name="availability-group-properties-new-availability-group-backup-preferences-page"></a><span data-ttu-id="f0ee2-102">Свойства группы доступности: создание группы доступности (страница настроек резервного копирования)</span><span class="sxs-lookup"><span data-stu-id="f0ee2-102">Availability Group Properties: New Availability Group (Backup Preferences Page)</span></span>
  <span data-ttu-id="f0ee2-103">С помощью этого диалогового окна можно просмотреть и изменить параметры резервного копирования выбранной группы доступности.</span><span class="sxs-lookup"><span data-stu-id="f0ee2-103">Use this dialog box to view and change the backup preferences of the selected availability group.</span></span>  
  
 <span data-ttu-id="f0ee2-104">**Просмотр свойств группы доступности**</span><span class="sxs-lookup"><span data-stu-id="f0ee2-104">**To view availability group properties**</span></span>  
  
-   [<span data-ttu-id="f0ee2-105">Просмотр свойств группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f0ee2-105">View Availability Group Properties &#40;SQL Server&#41;</span></span>](view-availability-group-properties-sql-server.md)  
  
-   [<span data-ttu-id="f0ee2-106">Использование панели мониторинга AlwaysOn (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="f0ee2-106">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
## <a name="where-should-backups-occur"></a><span data-ttu-id="f0ee2-107">Где должно выполняться резервное копирование?</span><span class="sxs-lookup"><span data-stu-id="f0ee2-107">Where should backups occur?</span></span>  
 <span data-ttu-id="f0ee2-108">**Предпочтение вторичной**</span><span class="sxs-lookup"><span data-stu-id="f0ee2-108">**Prefer Secondary**</span></span>  
 <span data-ttu-id="f0ee2-109">Указывает, что резервное копирование должно выполняться на вторичной реплике, за исключением тех случаев, когда в режиме «в сети» находится только первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="f0ee2-109">Specifies that backups should occur on a secondary replica except when the primary replica is the only replica online.</span></span> <span data-ttu-id="f0ee2-110">В этом случае резервное копирование будет выполняться на первичной реплике.</span><span class="sxs-lookup"><span data-stu-id="f0ee2-110">In that case, the backup should occur on the primary replica.</span></span> <span data-ttu-id="f0ee2-111">Это параметр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f0ee2-111">This is the default option.</span></span>  
  
 <span data-ttu-id="f0ee2-112">**Только вторичная**</span><span class="sxs-lookup"><span data-stu-id="f0ee2-112">**Secondary only**</span></span>  
 <span data-ttu-id="f0ee2-113">Указывает, что резервное копирование никогда не выполняется на первичной реплике.</span><span class="sxs-lookup"><span data-stu-id="f0ee2-113">Specifies that backups should never be performed on the primary replica.</span></span> <span data-ttu-id="f0ee2-114">Если первичная реплика является единственной репликой, находящейся в режиме «в сети», резервное копирование не будет выполняться.</span><span class="sxs-lookup"><span data-stu-id="f0ee2-114">If the primary replica is the only replica online, the backup should not occur.</span></span>  
  
 <span data-ttu-id="f0ee2-115">**Источник**</span><span class="sxs-lookup"><span data-stu-id="f0ee2-115">**Primary**</span></span>  
 <span data-ttu-id="f0ee2-116">Указывает, что резервное копирования должно всегда выполняться на первичной реплике.</span><span class="sxs-lookup"><span data-stu-id="f0ee2-116">Specifies that the backups should always occur on the primary replica.</span></span> <span data-ttu-id="f0ee2-117">Данный параметр является полезным, если вам требуются такие функции резервного копирования, как создание разностных резервных копий, которые не поддерживаются при выполнении резервного копирования на вторичной реплике.</span><span class="sxs-lookup"><span data-stu-id="f0ee2-117">This option is useful if you need backup features, such as creating differential backups, that are not supported when backup is run on a secondary replica.</span></span>  
  
 <span data-ttu-id="f0ee2-118">**Любая реплика**</span><span class="sxs-lookup"><span data-stu-id="f0ee2-118">**Any Replica**</span></span>  
 <span data-ttu-id="f0ee2-119">Указывает, что вы предпочитаете, чтобы задания резервного копирования пропускали реплики доступности при выборе реплики для создания резервных копий.</span><span class="sxs-lookup"><span data-stu-id="f0ee2-119">Specifies that you prefer that backup jobs ignore the role of the availability replicas when choosing the replica to perform backups.</span></span> <span data-ttu-id="f0ee2-120">Примечание. Задания резервного копирования могут учитывать другие факторы, например приоритет резервного копирования каждой реплики доступности в сочетании с ее состоянием работоспособности и подключения.</span><span class="sxs-lookup"><span data-stu-id="f0ee2-120">Note backup jobs might evaluate other factors such as backup priority of each availability replica in combination with its operational state and connected state.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f0ee2-121">Принудительного применения параметра приоритета резервного копирования не существует.</span><span class="sxs-lookup"><span data-stu-id="f0ee2-121">There is no enforcement of the backup-preference setting.</span></span> <span data-ttu-id="f0ee2-122">Интерпретация данного приоритета зависит от логики (при ее наличии), которая внесена в задания резервного копирования для баз данных в указанной группе доступности.</span><span class="sxs-lookup"><span data-stu-id="f0ee2-122">The interpretation of this preference depends on the logic, if any, that you script into back jobs for the databases in a given availability group.</span></span> <span data-ttu-id="f0ee2-123">Дополнительные сведения см. [в разделе Активные вторичные реплики: резервное копирование во вторичных копиях (группы доступности AlwaysOn)](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="f0ee2-123">For more information, see [Active Secondaries: Backup on Secondary Replicas (AlwaysOn Availability Groups)](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md).</span></span>  
  
## <a name="replica-backup-priorities"></a><span data-ttu-id="f0ee2-124">Приоритеты резервного копирования реплик</span><span class="sxs-lookup"><span data-stu-id="f0ee2-124">Replica backup priorities</span></span>  
 <span data-ttu-id="f0ee2-125">В этой сетке отображается текущий приоритет резервного копирования каждого экземпляра сервера, на котором размещена реплика, входящая в данную группу доступности.</span><span class="sxs-lookup"><span data-stu-id="f0ee2-125">This grid displays the current backup priority of each server instance that hosts a replica for the availability group.</span></span> <span data-ttu-id="f0ee2-126">В этой сетке можно изменить приоритет резервного копирования одной или нескольких реплик доступности.</span><span class="sxs-lookup"><span data-stu-id="f0ee2-126">Use this grid to change the backup priority of one or more availability replicas.</span></span>  
  
 <span data-ttu-id="f0ee2-127">**Экземпляр сервера**</span><span class="sxs-lookup"><span data-stu-id="f0ee2-127">**Server Instance**</span></span>  
 <span data-ttu-id="f0ee2-128">Имя экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , в котором размещается группа доступности.</span><span class="sxs-lookup"><span data-stu-id="f0ee2-128">The name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the availability replica.</span></span>  
  
 <span data-ttu-id="f0ee2-129">**Приоритет резервного копирования (низкий = 1, высокий = 100)**</span><span class="sxs-lookup"><span data-stu-id="f0ee2-129">**Backup Priority (Lowest=1, Highest=100)**</span></span>  
 <span data-ttu-id="f0ee2-130">Указывает приоритет выполнения резервного копирования на данной реплике по отношению к другим репликам из той же группы доступности.</span><span class="sxs-lookup"><span data-stu-id="f0ee2-130">Specifies your priority for performing backups on this replica relative to the other replicas in the same availability group.</span></span> <span data-ttu-id="f0ee2-131">Значение представляет собой целое число в диапазоне от 0 до 100.</span><span class="sxs-lookup"><span data-stu-id="f0ee2-131">The value is an integer in the range of 0..100.</span></span> <span data-ttu-id="f0ee2-132">1 указывает минимальный приоритет, 100 — наивысший приоритет.</span><span class="sxs-lookup"><span data-stu-id="f0ee2-132">1 indicates the lowest priority, and 100 indicates the highest priority.</span></span> <span data-ttu-id="f0ee2-133">Если **Backup Priority** = 1, реплика доступности будет выбрана для создания резервных копий только в случае, если реплики доступности с более высоким приоритетом отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="f0ee2-133">If **Backup Priority** = 1, the availability replica would be chosen for performing backups only if no higher priority availability replicas are currently available.</span></span>  
  
 <span data-ttu-id="f0ee2-134">**Исключить реплику**</span><span class="sxs-lookup"><span data-stu-id="f0ee2-134">**Exclude Replica**</span></span>  
 <span data-ttu-id="f0ee2-135">Установите этот параметр, чтобы реплика никогда не выбиралась для выполнения резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="f0ee2-135">Select if you never want this availability replica to be chosen for performing backups.</span></span> <span data-ttu-id="f0ee2-136">Этот параметр может быть полезным, например, для исключения удаленной реплики доступности, создание резервных копий на которой нежелательно.</span><span class="sxs-lookup"><span data-stu-id="f0ee2-136">This is useful, for example, for a remote availability replica to which you never want backups to fail over.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0ee2-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="f0ee2-137">See Also</span></span>  
 <span data-ttu-id="f0ee2-138">[Активные вторичные реплики: резервное копирование во вторичных копиях (группы доступности AlwaysOn)](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="f0ee2-138">[Active Secondaries: Backup on Secondary Replicas (AlwaysOn Availability Groups)](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="f0ee2-139">ALTER AVAILABILITY GROUP (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f0ee2-139">ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-availability-group-transact-sql)  
  
  
