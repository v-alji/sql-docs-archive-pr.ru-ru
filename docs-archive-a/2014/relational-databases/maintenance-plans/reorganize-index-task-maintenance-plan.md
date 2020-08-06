---
title: Задача "Реорганизация индекса" (план обслуживания) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.defrag.f1
helpviewer_keywords:
- Reorganize Index Task dialog box
ms.assetid: e9cbebbd-f36f-4176-9832-382a46ac946c
author: rothja
ms.author: jroth
ms.openlocfilehash: 0bbb154045b781f8a92dfce9c9d2f6ee2d819c17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658230"
---
# <a name="reorganize-index-task-maintenance-plan"></a><span data-ttu-id="27edf-102">Задача «Реорганизация индекса» (план обслуживания)</span><span class="sxs-lookup"><span data-stu-id="27edf-102">Reorganize Index Task (Maintenance Plan)</span></span>
  <span data-ttu-id="27edf-103">Используйте диалоговое окно **Задача ReorganizeIndex** для изменения порядка страниц индекса в целях повышения эффективности поиска.</span><span class="sxs-lookup"><span data-stu-id="27edf-103">Use the **ReorganizeIndex Task** dialog to move index pages into a more efficient search order.</span></span> <span data-ttu-id="27edf-104">Эта задача использует инструкцию `ALTER INDEX REORGANIZE` с базами данных [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="27edf-104">This task uses the `ALTER INDEX REORGANIZE` statement with [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] databases.</span></span>  
  
## <a name="options"></a><span data-ttu-id="27edf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="27edf-105">Options</span></span>  
 <span data-ttu-id="27edf-106">**Соединение**</span><span class="sxs-lookup"><span data-stu-id="27edf-106">**Connection**</span></span>  
 <span data-ttu-id="27edf-107">Выберите соединение с сервером, которое будет использоваться для выполнения этой задачи.</span><span class="sxs-lookup"><span data-stu-id="27edf-107">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="27edf-108">**Создать**</span><span class="sxs-lookup"><span data-stu-id="27edf-108">**New**</span></span>  
 <span data-ttu-id="27edf-109">Создать новое соединение с сервером для его использования при выполнении этой задачи.</span><span class="sxs-lookup"><span data-stu-id="27edf-109">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="27edf-110">Диалоговое окно **Создание соединения** описано ниже.</span><span class="sxs-lookup"><span data-stu-id="27edf-110">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="27edf-111">**Базы данных**</span><span class="sxs-lookup"><span data-stu-id="27edf-111">**Databases**</span></span>  
 <span data-ttu-id="27edf-112">Укажите базы данных, для которых должна выполняться эта задача.</span><span class="sxs-lookup"><span data-stu-id="27edf-112">Specify the databases affected by this task.</span></span>  
  
-   <span data-ttu-id="27edf-113">**Все базы данных**</span><span class="sxs-lookup"><span data-stu-id="27edf-113">**All databases**</span></span>  
  
     <span data-ttu-id="27edf-114">Создается план обслуживания, по которому задачи обслуживания должны выполняться для всех баз данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , кроме базы данных tempdb.</span><span class="sxs-lookup"><span data-stu-id="27edf-114">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases except tempdb.</span></span>  
  
-   <span data-ttu-id="27edf-115">**Все системные базы данных**</span><span class="sxs-lookup"><span data-stu-id="27edf-115">**All system databases**</span></span>  
  
     <span data-ttu-id="27edf-116">Будет сформирован план обслуживания, запускающий задачи обслуживания для каждой системной базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , за исключением базы данных **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="27edf-116">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases except **tempdb**.</span></span> <span data-ttu-id="27edf-117">Для баз данных, созданных пользователями, задачи обслуживания выполняться не будут.</span><span class="sxs-lookup"><span data-stu-id="27edf-117">No maintenance tasks are run against user-created databases.</span></span>  
  
-   <span data-ttu-id="27edf-118">**Все пользовательские базы данных**</span><span class="sxs-lookup"><span data-stu-id="27edf-118">**All user databases**</span></span>  
  
     <span data-ttu-id="27edf-119">Создается план обслуживания, по которому задачи обслуживания выполняются для всех баз данных, созданных пользователем.</span><span class="sxs-lookup"><span data-stu-id="27edf-119">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="27edf-120">Для системных баз данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] задачи обслуживания выполняться не будут.</span><span class="sxs-lookup"><span data-stu-id="27edf-120">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
-   <span data-ttu-id="27edf-121">**Определенные базы данных**</span><span class="sxs-lookup"><span data-stu-id="27edf-121">**These specific databases**</span></span>  
  
     <span data-ttu-id="27edf-122">Создается план обслуживания, по которому задачи обслуживания должны выполняться только для указанных баз данных.</span><span class="sxs-lookup"><span data-stu-id="27edf-122">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="27edf-123">Если выбран этот параметр, необходимо выбрать в списке хотя бы одну базу данных.</span><span class="sxs-lookup"><span data-stu-id="27edf-123">At least one database in the list must be selected if this option is chosen.</span></span>  
  
 <span data-ttu-id="27edf-124">**Объект**</span><span class="sxs-lookup"><span data-stu-id="27edf-124">**Object**</span></span>  
 <span data-ttu-id="27edf-125">Ограничьте сетку **Выбор** для отображения таблиц, представлений или обоих элементов.</span><span class="sxs-lookup"><span data-stu-id="27edf-125">Limit the **Selection** grid to display tables, views, or both.</span></span>  
  
 <span data-ttu-id="27edf-126">**Выбор**</span><span class="sxs-lookup"><span data-stu-id="27edf-126">**Selection**</span></span>  
 <span data-ttu-id="27edf-127">Укажите таблицы или индексы, которые должны обрабатываться этой задачей.</span><span class="sxs-lookup"><span data-stu-id="27edf-127">Specify the tables or indexes affected by this task.</span></span> <span data-ttu-id="27edf-128">Этот параметр недоступен, если в окне **Объекты** выбран пункт **Таблицы и представления** .</span><span class="sxs-lookup"><span data-stu-id="27edf-128">Not available when **Tables and Views** is selected in the **Object** box.</span></span>  
  
 <span data-ttu-id="27edf-129">**Сжатие больших объектов**</span><span class="sxs-lookup"><span data-stu-id="27edf-129">**Compact large objects**</span></span>  
 <span data-ttu-id="27edf-130">По возможности освобождается пространство для таблиц и представлений.</span><span class="sxs-lookup"><span data-stu-id="27edf-130">Deallocate space for tables and views when possible.</span></span> <span data-ttu-id="27edf-131">Этот параметр использует инструкцию `ALTER INDEX LOB_COMPACTION = ON`.</span><span class="sxs-lookup"><span data-stu-id="27edf-131">This option uses `ALTER INDEX LOB_COMPACTION = ON`.</span></span>  
  
 <span data-ttu-id="27edf-132">**Просмотр T-SQL**</span><span class="sxs-lookup"><span data-stu-id="27edf-132">**View T-SQL**</span></span>  
 <span data-ttu-id="27edf-133">Просмотрите инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] , выполняемые для данной задачи по отношению к серверу, на основе выбранных параметров.</span><span class="sxs-lookup"><span data-stu-id="27edf-133">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="27edf-134">Если количество затронутых объектов велико, построение этого отображения может занять значительное время.</span><span class="sxs-lookup"><span data-stu-id="27edf-134">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="27edf-135">Диалоговое окно «Создание соединения»</span><span class="sxs-lookup"><span data-stu-id="27edf-135">New Connection Dialog Box</span></span>  
 <span data-ttu-id="27edf-136">**Имя соединения**</span><span class="sxs-lookup"><span data-stu-id="27edf-136">**Connection name**</span></span>  
 <span data-ttu-id="27edf-137">Введите имя нового соединения.</span><span class="sxs-lookup"><span data-stu-id="27edf-137">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="27edf-138">**Выберите или введите имя сервера**</span><span class="sxs-lookup"><span data-stu-id="27edf-138">**Select or enter a server name**</span></span>  
 <span data-ttu-id="27edf-139">Выберите сервер для подключения при выполнении этой задачи.</span><span class="sxs-lookup"><span data-stu-id="27edf-139">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="27edf-140">**Обновить**</span><span class="sxs-lookup"><span data-stu-id="27edf-140">**Refresh**</span></span>  
 <span data-ttu-id="27edf-141">Обновите список доступных серверов.</span><span class="sxs-lookup"><span data-stu-id="27edf-141">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="27edf-142">**Введите данные для входа на сервер**</span><span class="sxs-lookup"><span data-stu-id="27edf-142">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="27edf-143">Укажите способ проверки подлинности на сервере.</span><span class="sxs-lookup"><span data-stu-id="27edf-143">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="27edf-144">**Использовать встроенную безопасность Windows**</span><span class="sxs-lookup"><span data-stu-id="27edf-144">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="27edf-145">Подключиться к экземпляру компонента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] c проверкой подлинности [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="27edf-145">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="27edf-146">**Использовать указанные имя пользователя и пароль**</span><span class="sxs-lookup"><span data-stu-id="27edf-146">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="27edf-147">Подключиться к экземпляру компонента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] с использованием проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="27edf-147">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="27edf-148">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="27edf-148">This option is not available.</span></span>  
  
 <span data-ttu-id="27edf-149">**User name**</span><span class="sxs-lookup"><span data-stu-id="27edf-149">**User name**</span></span>  
 <span data-ttu-id="27edf-150">Укажите имя входа, используемое при проверке подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="27edf-150">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="27edf-151">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="27edf-151">This option is not available.</span></span>  
  
 <span data-ttu-id="27edf-152">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="27edf-152">**Password**</span></span>  
 <span data-ttu-id="27edf-153">Укажите используемый при проверке подлинности пароль.</span><span class="sxs-lookup"><span data-stu-id="27edf-153">Provide a password to use when authenticating.</span></span> <span data-ttu-id="27edf-154">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="27edf-154">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27edf-155">См. также:</span><span class="sxs-lookup"><span data-stu-id="27edf-155">See Also</span></span>  
 <span data-ttu-id="27edf-156">[ALTER INDEX (Transact-SQL)](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="27edf-156">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 [<span data-ttu-id="27edf-157">DBCC INDEXDEFRAG (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="27edf-157">DBCC INDEXDEFRAG &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-indexdefrag-transact-sql)  
  
  
