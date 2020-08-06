---
title: Задача "Проверка целостности базы данных" (план обслуживания) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.maintplanproperties.integrity.f1
- sql12.swb.maint.integrity.f1
helpviewer_keywords:
- Check Database Integrity Task dialog box
ms.assetid: 3534494a-5dfe-4738-b49a-e7fabd731c47
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f786755a3b7ed5d991b4cf0e32c067e355c111ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666580"
---
# <a name="check-database-integrity-task-maintenance-plan"></a><span data-ttu-id="a6f23-102">Задача «Проверка целостности базы данных» (план обслуживания)</span><span class="sxs-lookup"><span data-stu-id="a6f23-102">Check Database Integrity Task (Maintenance Plan)</span></span>
  <span data-ttu-id="a6f23-103">Диалоговое окно **Задача "Проверка целостности базы данных"** используется для проверки распределения и структурной целостности пользовательских и системных таблиц, а также индексов в базе данных путем запуска инструкции `DBCC CHECKDB`[!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6f23-103">Use the **Check Database Integrity Task** dialog to check the allocation and structural integrity of user and system tables, and indexes in the database, by running the `DBCC CHECKDB`[!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="a6f23-104">Запуск `DBCC` гарантирует, что будет сообщено обо всех проблемах с целостностью в базе данных, таким образом позволяя системному администратору или владельцу базы данных устранить их позже.</span><span class="sxs-lookup"><span data-stu-id="a6f23-104">Running `DBCC` ensures that any integrity problems with the database are reported, thereby allowing them to be addressed later by a system administrator or database owner.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a6f23-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a6f23-105">Options</span></span>  
 <span data-ttu-id="a6f23-106">**Соединение**</span><span class="sxs-lookup"><span data-stu-id="a6f23-106">**Connection**</span></span>  
 <span data-ttu-id="a6f23-107">Выберите соединение с сервером, которое будет использоваться для выполнения этой задачи.</span><span class="sxs-lookup"><span data-stu-id="a6f23-107">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="a6f23-108">**Создать**</span><span class="sxs-lookup"><span data-stu-id="a6f23-108">**New**</span></span>  
 <span data-ttu-id="a6f23-109">Создать новое соединение с сервером для его использования при выполнении этой задачи.</span><span class="sxs-lookup"><span data-stu-id="a6f23-109">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="a6f23-110">Диалоговое окно **Создание соединения** описано ниже.</span><span class="sxs-lookup"><span data-stu-id="a6f23-110">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="a6f23-111">**Базы данных**</span><span class="sxs-lookup"><span data-stu-id="a6f23-111">**Databases**</span></span>  
 <span data-ttu-id="a6f23-112">Укажите базы данных, для которых должна выполняться эта задача.</span><span class="sxs-lookup"><span data-stu-id="a6f23-112">Specify the databases affected by this task.</span></span>  
  
-   <span data-ttu-id="a6f23-113">**Все базы данных**</span><span class="sxs-lookup"><span data-stu-id="a6f23-113">**All databases**</span></span>  
  
     <span data-ttu-id="a6f23-114">Позволяет сформировать план обслуживания, который запускает задачи обслуживания для всех баз данных [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], кроме **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="a6f23-114">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases except **tempdb**.</span></span>  
  
-   <span data-ttu-id="a6f23-115">**Все системные базы данных**</span><span class="sxs-lookup"><span data-stu-id="a6f23-115">**All system databases**</span></span>  
  
     <span data-ttu-id="a6f23-116">Будет сформирован план обслуживания, запускающий задачи обслуживания для каждой системной базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , за исключением базы данных **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="a6f23-116">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases except **tempdb**.</span></span> <span data-ttu-id="a6f23-117">Для баз данных, созданных пользователями, задачи обслуживания выполняться не будут.</span><span class="sxs-lookup"><span data-stu-id="a6f23-117">No maintenance tasks are run against user-created databases.</span></span>  
  
-   <span data-ttu-id="a6f23-118">**Все пользовательские базы данных**</span><span class="sxs-lookup"><span data-stu-id="a6f23-118">**All user databases**</span></span>  
  
     <span data-ttu-id="a6f23-119">Создается план обслуживания, по которому задачи обслуживания выполняются для всех баз данных, созданных пользователем.</span><span class="sxs-lookup"><span data-stu-id="a6f23-119">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="a6f23-120">Для системных баз данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] задачи обслуживания выполняться не будут.</span><span class="sxs-lookup"><span data-stu-id="a6f23-120">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
-   <span data-ttu-id="a6f23-121">**Определенные базы данных**</span><span class="sxs-lookup"><span data-stu-id="a6f23-121">**These specific databases**</span></span>  
  
     <span data-ttu-id="a6f23-122">Создается план обслуживания, по которому задачи обслуживания должны выполняться только для указанных баз данных.</span><span class="sxs-lookup"><span data-stu-id="a6f23-122">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="a6f23-123">Если выбран этот параметр, необходимо выбрать в списке хотя бы одну базу данных.</span><span class="sxs-lookup"><span data-stu-id="a6f23-123">At least one database in the list must be selected if this option is chosen.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a6f23-124">Планы обслуживания выполняются только для баз данных, уровень совместимости которых 80 или выше.</span><span class="sxs-lookup"><span data-stu-id="a6f23-124">Maintenance plans only run against databases set to compatibility level 80 or higher.</span></span> <span data-ttu-id="a6f23-125">Базы данных с уровнем совместимости 70 или ниже не отображаются.</span><span class="sxs-lookup"><span data-stu-id="a6f23-125">Databases set to compatibility level 70 or lower are not displayed.</span></span>  
  
 <span data-ttu-id="a6f23-126">**Включить индексы**</span><span class="sxs-lookup"><span data-stu-id="a6f23-126">**Include indexes**</span></span>  
 <span data-ttu-id="a6f23-127">Проверка целостности всех страниц индекса, а также табличных страниц данных.</span><span class="sxs-lookup"><span data-stu-id="a6f23-127">Check the integrity of all the index pages as well as the table data pages.</span></span>  
  
 <span data-ttu-id="a6f23-128">**Просмотр T-SQL**</span><span class="sxs-lookup"><span data-stu-id="a6f23-128">**View T-SQL**</span></span>  
 <span data-ttu-id="a6f23-129">Просмотрите инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] , выполняемые для данной задачи по отношению к серверу, на основе выбранных параметров.</span><span class="sxs-lookup"><span data-stu-id="a6f23-129">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a6f23-130">Если количество затронутых объектов велико, построение этого отображения может занять значительное время.</span><span class="sxs-lookup"><span data-stu-id="a6f23-130">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="a6f23-131">Диалоговое окно «Создание соединения»</span><span class="sxs-lookup"><span data-stu-id="a6f23-131">New Connection Dialog Box</span></span>  
 <span data-ttu-id="a6f23-132">**Имя соединения**</span><span class="sxs-lookup"><span data-stu-id="a6f23-132">**Connection name**</span></span>  
 <span data-ttu-id="a6f23-133">Введите имя нового соединения.</span><span class="sxs-lookup"><span data-stu-id="a6f23-133">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="a6f23-134">**Выберите или введите имя сервера**</span><span class="sxs-lookup"><span data-stu-id="a6f23-134">**Select or enter a server name**</span></span>  
 <span data-ttu-id="a6f23-135">Выберите сервер для подключения при выполнении этой задачи.</span><span class="sxs-lookup"><span data-stu-id="a6f23-135">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="a6f23-136">**Обновить**</span><span class="sxs-lookup"><span data-stu-id="a6f23-136">**Refresh**</span></span>  
 <span data-ttu-id="a6f23-137">Обновите список доступных серверов.</span><span class="sxs-lookup"><span data-stu-id="a6f23-137">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="a6f23-138">**Введите данные для входа на сервер**</span><span class="sxs-lookup"><span data-stu-id="a6f23-138">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="a6f23-139">Укажите способ проверки подлинности на сервере.</span><span class="sxs-lookup"><span data-stu-id="a6f23-139">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="a6f23-140">**Использовать встроенную безопасность Windows**</span><span class="sxs-lookup"><span data-stu-id="a6f23-140">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="a6f23-141">Подключиться к экземпляру компонента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] c проверкой подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="a6f23-141">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with Windows Authentication.</span></span>  
  
 <span data-ttu-id="a6f23-142">**Использовать указанные имя пользователя и пароль**</span><span class="sxs-lookup"><span data-stu-id="a6f23-142">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="a6f23-143">Подключиться к экземпляру компонента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] с использованием проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6f23-143">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="a6f23-144">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="a6f23-144">This option is not available.</span></span>  
  
 <span data-ttu-id="a6f23-145">**User name**</span><span class="sxs-lookup"><span data-stu-id="a6f23-145">**User name**</span></span>  
 <span data-ttu-id="a6f23-146">Укажите имя входа, используемое при проверке подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6f23-146">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="a6f23-147">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="a6f23-147">This option is not available.</span></span>  
  
 <span data-ttu-id="a6f23-148">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="a6f23-148">**Password**</span></span>  
 <span data-ttu-id="a6f23-149">Укажите используемый при проверке подлинности пароль.</span><span class="sxs-lookup"><span data-stu-id="a6f23-149">Provide a password to use when authenticating.</span></span> <span data-ttu-id="a6f23-150">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="a6f23-150">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6f23-151">См. также:</span><span class="sxs-lookup"><span data-stu-id="a6f23-151">See Also</span></span>  
 [<span data-ttu-id="a6f23-152">DBCC CHECKDB (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a6f23-152">DBCC CHECKDB &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)  
  
  
