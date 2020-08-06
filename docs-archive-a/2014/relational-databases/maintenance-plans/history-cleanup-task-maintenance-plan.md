---
title: Задача "Очистка журнала" (план обслуживания) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.historycleanup.f1
helpviewer_keywords:
- History Cleanup Task dialog box
ms.assetid: 66bb6c39-958c-4053-a27f-b1118d2567f5
ms.reviewer: ''
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 03ff35b14fc13d2b4446b15501114489b52c421e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666572"
---
# <a name="history-cleanup-task-maintenance-plan"></a><span data-ttu-id="ba511-102">Задача «Очистка журнала» (план обслуживания)</span><span class="sxs-lookup"><span data-stu-id="ba511-102">History Cleanup Task (Maintenance Plan)</span></span>

  <span data-ttu-id="ba511-103">Используйте диалоговое окно **Задача «Очистка журнала»** , чтобы исключить устаревшие данные предыстории из таблиц в базе данных msdb.</span><span class="sxs-lookup"><span data-stu-id="ba511-103">Use the **History Cleanup Task** dialog to discard old historical information from tables in the msdb database.</span></span> <span data-ttu-id="ba511-104">Эта задача поддерживает удаление и восстановление журнала резервного копирования, журнала заданий агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , а также журнала плана обслуживания.</span><span class="sxs-lookup"><span data-stu-id="ba511-104">This task supports deleting backup and restore history, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Job history, and maintenance plan history.</span></span>  
  
 <span data-ttu-id="ba511-105">Эта инструкция применяет инструкции **sp_purge_jobhistory** и **sp_delete_backuphistory** .</span><span class="sxs-lookup"><span data-stu-id="ba511-105">This statement uses the **sp_purge_jobhistory** and **sp_delete_backuphistory** statements.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="ba511-106">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="ba511-106">UI element list</span></span>  
 <span data-ttu-id="ba511-107">**Соединение**</span><span class="sxs-lookup"><span data-stu-id="ba511-107">**Connection**</span></span>  
 <span data-ttu-id="ba511-108">Выберите соединение с сервером, которое будет использоваться для выполнения этой задачи.</span><span class="sxs-lookup"><span data-stu-id="ba511-108">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="ba511-109">**Создать**</span><span class="sxs-lookup"><span data-stu-id="ba511-109">**New**</span></span>  
 <span data-ttu-id="ba511-110">Создать новое соединение с сервером для его использования при выполнении этой задачи.</span><span class="sxs-lookup"><span data-stu-id="ba511-110">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="ba511-111">Диалоговое окно **Создать соединение** описано ниже в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="ba511-111">The **New Connection** dialog box is described later in this topic.</span></span>  
  
 <span data-ttu-id="ba511-112">**Журнал резервного копирования и восстановления**</span><span class="sxs-lookup"><span data-stu-id="ba511-112">**Backup and restore history**</span></span>  
 <span data-ttu-id="ba511-113">Хранение записей о том, когда были созданы последние резервные копии, может помочь [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в создании плана восстановления, когда потребуется восстановить базу данных.</span><span class="sxs-lookup"><span data-stu-id="ba511-113">Retaining records of when recent backups were created can help [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] create a recovery plan when you want to restore a database.</span></span> <span data-ttu-id="ba511-114">Срок хранения должен быть не меньше периода создания полных резервных копий базы данных.</span><span class="sxs-lookup"><span data-stu-id="ba511-114">The retention period should be at least the frequency of full database back ups.</span></span>  
  
 <span data-ttu-id="ba511-115">**Журнал заданий агента SQL Server**</span><span class="sxs-lookup"><span data-stu-id="ba511-115">**SQL Server Agent Job history**</span></span>  
 <span data-ttu-id="ba511-116">Этот журнал может помочь устранить ошибки, возникшие при выполнении заданий, или определить, почему были выполнены операции с базой данных.</span><span class="sxs-lookup"><span data-stu-id="ba511-116">This history can help you troubleshoot failed jobs, or determine why database actions occurred.</span></span>  
  
 <span data-ttu-id="ba511-117">**Журнал плана обслуживания**</span><span class="sxs-lookup"><span data-stu-id="ba511-117">**Maintenance plan history**</span></span>  
 <span data-ttu-id="ba511-118">Этот журнал может помочь устранить ошибки, возникшие при выполнении заданий плана обслуживания, или определить, почему были выполнены операции с базой данных.</span><span class="sxs-lookup"><span data-stu-id="ba511-118">This history can help you troubleshoot failed maintenance plan jobs, or determine why database actions occurred.</span></span>  
  
 <span data-ttu-id="ba511-119">**Удалить из журнала записи старше**</span><span class="sxs-lookup"><span data-stu-id="ba511-119">**Remove historical data older than**</span></span>  
 <span data-ttu-id="ba511-120">Укажите возраст элементов, которые следует удалить.</span><span class="sxs-lookup"><span data-stu-id="ba511-120">Specify age of items that you want to delete.</span></span>  
  
 <span data-ttu-id="ba511-121">**Просмотр T-SQL**</span><span class="sxs-lookup"><span data-stu-id="ba511-121">**View T-SQL**</span></span>  
 <span data-ttu-id="ba511-122">Просмотрите инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] , выполняемые для данной задачи по отношению к серверу, на основе выбранных параметров.</span><span class="sxs-lookup"><span data-stu-id="ba511-122">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ba511-123">Если количество затронутых объектов велико, построение этого отображения может занять значительное время.</span><span class="sxs-lookup"><span data-stu-id="ba511-123">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="ba511-124">Диалоговое окно «Создание соединения»</span><span class="sxs-lookup"><span data-stu-id="ba511-124">New Connection Dialog Box</span></span>  
 <span data-ttu-id="ba511-125">**Имя соединения**</span><span class="sxs-lookup"><span data-stu-id="ba511-125">**Connection name**</span></span>  
 <span data-ttu-id="ba511-126">Введите имя нового соединения.</span><span class="sxs-lookup"><span data-stu-id="ba511-126">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="ba511-127">**Выберите или введите имя сервера**</span><span class="sxs-lookup"><span data-stu-id="ba511-127">**Select or enter a server name**</span></span>  
 <span data-ttu-id="ba511-128">Выберите сервер для подключения при выполнении этой задачи.</span><span class="sxs-lookup"><span data-stu-id="ba511-128">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="ba511-129">**Обновить**</span><span class="sxs-lookup"><span data-stu-id="ba511-129">**Refresh**</span></span>  
 <span data-ttu-id="ba511-130">Обновите список доступных серверов.</span><span class="sxs-lookup"><span data-stu-id="ba511-130">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="ba511-131">**Введите данные для входа на сервер**</span><span class="sxs-lookup"><span data-stu-id="ba511-131">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="ba511-132">Укажите способ проверки подлинности на сервере.</span><span class="sxs-lookup"><span data-stu-id="ba511-132">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="ba511-133">**Использовать встроенную безопасность Windows**</span><span class="sxs-lookup"><span data-stu-id="ba511-133">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="ba511-134">Подключитесь к экземпляру компонента SQL Server [!INCLUDE[ssDE](../../includes/ssde-md.md)] с помощью проверки подлинности Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="ba511-134">Connect to an instance of the SQL Server [!INCLUDE[ssDE](../../includes/ssde-md.md)] with Microsoft Windows Authentication.</span></span>  
  
 <span data-ttu-id="ba511-135">**Использовать указанные имя пользователя и пароль**</span><span class="sxs-lookup"><span data-stu-id="ba511-135">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="ba511-136">Подключитесь к экземпляру компонента SQL Server [!INCLUDE[ssDE](../../includes/ssde-md.md)] с помощью проверки подлинности SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ba511-136">Connect to an instance of the SQL Server [!INCLUDE[ssDE](../../includes/ssde-md.md)] using SQL Server Authentication.</span></span> <span data-ttu-id="ba511-137">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="ba511-137">This option is not available.</span></span>  
  
 <span data-ttu-id="ba511-138">**User name**</span><span class="sxs-lookup"><span data-stu-id="ba511-138">**User name**</span></span>  
 <span data-ttu-id="ba511-139">Укажите имя входа, используемое при проверке подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ba511-139">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="ba511-140">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="ba511-140">This option is not available.</span></span>  
  
 <span data-ttu-id="ba511-141">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="ba511-141">**Password**</span></span>  
 <span data-ttu-id="ba511-142">Укажите используемый при проверке подлинности пароль.</span><span class="sxs-lookup"><span data-stu-id="ba511-142">Provide a password to use when authenticating.</span></span> <span data-ttu-id="ba511-143">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="ba511-143">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba511-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="ba511-144">See Also</span></span>  
 <span data-ttu-id="ba511-145">[sp_purge_jobhistory (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-purge-jobhistory-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ba511-145">[sp_purge_jobhistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-purge-jobhistory-transact-sql) </span></span>  
 [<span data-ttu-id="ba511-146">sp_delete_backuphistory (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="ba511-146">sp_delete_backuphistory &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql)  
  
  
