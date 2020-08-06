---
title: Задача "Сжатие базы данных" (план обслуживания) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.shrink.f1
- Shrink Database Task
- Shrink Database(s) Task
helpviewer_keywords:
- Shrink Database Task dialog box
ms.assetid: a9874cac-cded-4145-9c38-8aafd267dbee
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b8ee6060a4ee6ca3272434cf3d9115638a675e62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731565"
---
# <a name="shrink-database-task-maintenance-plan"></a><span data-ttu-id="0d1dd-102">Задача «Сжатие базы данных» (план обслуживания)</span><span class="sxs-lookup"><span data-stu-id="0d1dd-102">Shrink Database Task (Maintenance Plan)</span></span>
  <span data-ttu-id="0d1dd-103">Диалоговое окно **Задача «Сжатие базы данных»** используется для создания задачи, которая пытается уменьшить размер выбранных баз данных.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-103">Use the **Shrink Database Task** dialog to create a task that attempts to reduce the size of the selected databases.</span></span> <span data-ttu-id="0d1dd-104">Перечисленные ниже параметры используются для определения количества неиспользуемого пространства, которое должно остаться в базе данных после сжатия (чем больше процент, тем меньше сжимается база данных).</span><span class="sxs-lookup"><span data-stu-id="0d1dd-104">Use the options below to determine the amount of unused space to remain in the database after the database is shrunk (the larger the percentage, the less the database can shrink).</span></span> <span data-ttu-id="0d1dd-105">Это значение определяется долей фактических данных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-105">The value is based on the percentage of the actual data in the database.</span></span> <span data-ttu-id="0d1dd-106">Например: 100-мегабайтная база данных, содержащая 60 МБ данных и 40 МБ свободного пространства с заданным значением свободного пространства, равным 50 процентам, будет содержать 60 МБ данных и 30 МБ свободного пространства (поскольку 50 процентов от 60 МБ равно 30 МБ).</span><span class="sxs-lookup"><span data-stu-id="0d1dd-106">For example, a 100-MB database containing 60 MB of data and 40 MB of free space, with a free space percentage of 50 percent, would result in 60 MB of data and 30 MB of free space (because 50 percent of 60 MB is 30 MB).</span></span> <span data-ttu-id="0d1dd-107">Удаляется только лишнее пространство в базе данных.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-107">Only excess space in the database is eliminated.</span></span> <span data-ttu-id="0d1dd-108">Допустимые значения: от 0 до 100.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-108">Valid values are from 0 through 100.</span></span>  
  
 <span data-ttu-id="0d1dd-109">Сжатие файлов данных позволяет освободить неиспользуемое пространство путем перемещения страниц данных с конца файла в незанятое пространство ближе к началу файла.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-109">Shrinking data files recovers space by moving pages of data from the end of the file to unoccupied space closer to the front of the file.</span></span> <span data-ttu-id="0d1dd-110">Когда в конце файла образуется достаточно свободного места, страницы данных в конце файла могут быть освобождены и возвращены в файловую систему.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-110">When enough free space is created at the end of the file, data pages at end of the file can deallocated and returned to the file system.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="0d1dd-111">Данные, перемещаемые в процессе сжатия файла, могут быть разбросаны по любым доступным местам в файле.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-111">Data that is moved to shrink a file can be scattered to any available location in the file.</span></span> <span data-ttu-id="0d1dd-112">Это вызывает фрагментацию индекса и может увеличить время выполнения запросов, выполняющих поиск в диапазоне индекса.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-112">This causes index fragmentation and can slow the performance of queries that search a range of the index.</span></span> <span data-ttu-id="0d1dd-113">Чтобы устранить фрагментацию, предусмотрите возможность перестроения индексов файла после сжатия.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-113">To eliminate the fragmentation, consider rebuilding the indexes on the file after shrinking.</span></span>  
  
 <span data-ttu-id="0d1dd-114">Эта задача выполняет инструкцию DBCC SHRINKDATABASE.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-114">This task executes the DBCC SHRINKDATABASE statement.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0d1dd-115">Параметры</span><span class="sxs-lookup"><span data-stu-id="0d1dd-115">Options</span></span>  
 <span data-ttu-id="0d1dd-116">**Соединение**</span><span class="sxs-lookup"><span data-stu-id="0d1dd-116">**Connection**</span></span>  
 <span data-ttu-id="0d1dd-117">Выберите соединение с сервером, которое будет использоваться для выполнения этой задачи.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-117">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="0d1dd-118">**Создать**</span><span class="sxs-lookup"><span data-stu-id="0d1dd-118">**New**</span></span>  
 <span data-ttu-id="0d1dd-119">Создать новое соединение с сервером для его использования при выполнении этой задачи.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-119">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="0d1dd-120">Диалоговое окно **Создание соединения** описано ниже.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-120">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="0d1dd-121">**Базы данных**</span><span class="sxs-lookup"><span data-stu-id="0d1dd-121">**Databases**</span></span>  
 <span data-ttu-id="0d1dd-122">Укажите базы данных, для которых должна выполняться эта задача.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-122">Specify the databases affected by this task.</span></span>  
  
-   <span data-ttu-id="0d1dd-123">**Все базы данных**</span><span class="sxs-lookup"><span data-stu-id="0d1dd-123">**All databases**</span></span>  
  
     <span data-ttu-id="0d1dd-124">Позволяет сформировать план обслуживания, который запускает задачи обслуживания для всех баз данных [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], кроме tempdb.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-124">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases except tempdb.</span></span>  
  
-   <span data-ttu-id="0d1dd-125">**Все системные базы данных**</span><span class="sxs-lookup"><span data-stu-id="0d1dd-125">**All system databases**</span></span>  
  
     <span data-ttu-id="0d1dd-126">Будет сформирован план обслуживания, запускающий задачи обслуживания для каждой системной базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , за исключением базы данных tempdb.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-126">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases except tempdb.</span></span> <span data-ttu-id="0d1dd-127">Для баз данных, созданных пользователями, задачи обслуживания выполняться не будут.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-127">No maintenance tasks are run against user-created databases.</span></span>  
  
-   <span data-ttu-id="0d1dd-128">**Все пользовательские базы данных**</span><span class="sxs-lookup"><span data-stu-id="0d1dd-128">**All user databases**</span></span>  
  
     <span data-ttu-id="0d1dd-129">Создается план обслуживания, по которому задачи обслуживания выполняются для всех баз данных, созданных пользователем.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-129">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="0d1dd-130">Для системных баз данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] задачи обслуживания выполняться не будут.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-130">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
-   <span data-ttu-id="0d1dd-131">**Следующие базы данных**</span><span class="sxs-lookup"><span data-stu-id="0d1dd-131">**These databases**</span></span>  
  
     <span data-ttu-id="0d1dd-132">Создается план обслуживания, по которому задачи обслуживания должны выполняться только для указанных баз данных.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-132">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="0d1dd-133">Если выбран этот параметр, необходимо выбрать в списке хотя бы одну базу данных.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-133">At least one database in the list must be selected if this option is chosen.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0d1dd-134">Планы обслуживания выполняются только для баз данных, уровень совместимости которых 80 или выше.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-134">Maintenance plans only run against databases set to compatibility level 80 or higher.</span></span> <span data-ttu-id="0d1dd-135">Базы данных с уровнем совместимости 70 или ниже не отображаются.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-135">Databases set to compatibility level 70 or lower are not displayed.</span></span>  
  
 <span data-ttu-id="0d1dd-136">**Сжимать базу данных при превышении ею размера**</span><span class="sxs-lookup"><span data-stu-id="0d1dd-136">**Shrink database when it grows beyond**</span></span>  
 <span data-ttu-id="0d1dd-137">Укажите размер в мегабайтах, по достижении которого будет выполняться задача.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-137">Specify the size in megabytes that causes the task to execute.</span></span>  
  
 <span data-ttu-id="0d1dd-138">**Объем свободного места после сжатия**</span><span class="sxs-lookup"><span data-stu-id="0d1dd-138">**Amount of free space to remain after shrink**</span></span>  
 <span data-ttu-id="0d1dd-139">Прекратить сжатие по достижении заданного размера свободного пространства в базе данных.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-139">Stop shrinking when free space in database files reaches this size.</span></span>  
  
 <span data-ttu-id="0d1dd-140">**Просмотр T-SQL**</span><span class="sxs-lookup"><span data-stu-id="0d1dd-140">**View T-SQL**</span></span>  
 <span data-ttu-id="0d1dd-141">Просмотрите инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] , выполняемые для данной задачи по отношению к серверу, на основе выбранных параметров.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-141">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0d1dd-142">Если количество затронутых объектов велико, построение этого отображения может занять значительное время.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-142">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="0d1dd-143">Диалоговое окно «Создание соединения»</span><span class="sxs-lookup"><span data-stu-id="0d1dd-143">New Connection Dialog Box</span></span>  
 <span data-ttu-id="0d1dd-144">**Имя соединения**</span><span class="sxs-lookup"><span data-stu-id="0d1dd-144">**Connection name**</span></span>  
 <span data-ttu-id="0d1dd-145">Введите имя нового соединения.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-145">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="0d1dd-146">**Выберите или введите имя сервера**</span><span class="sxs-lookup"><span data-stu-id="0d1dd-146">**Select or enter a server name**</span></span>  
 <span data-ttu-id="0d1dd-147">Выберите сервер для подключения при выполнении этой задачи.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-147">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="0d1dd-148">**Обновить**</span><span class="sxs-lookup"><span data-stu-id="0d1dd-148">**Refresh**</span></span>  
 <span data-ttu-id="0d1dd-149">Обновите список доступных серверов.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-149">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="0d1dd-150">**Введите данные для входа на сервер**</span><span class="sxs-lookup"><span data-stu-id="0d1dd-150">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="0d1dd-151">Укажите способ проверки подлинности на сервере.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-151">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="0d1dd-152">**Использовать встроенную систему безопасности Windows NT**</span><span class="sxs-lookup"><span data-stu-id="0d1dd-152">**Use Windows NT Integrated security**</span></span>  
 <span data-ttu-id="0d1dd-153">Подключиться к экземпляру компонента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] c проверкой подлинности [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-153">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="0d1dd-154">**Использовать указанные имя пользователя и пароль**</span><span class="sxs-lookup"><span data-stu-id="0d1dd-154">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="0d1dd-155">Подключиться к экземпляру компонента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] с использованием проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d1dd-155">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="0d1dd-156">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-156">This option is not available.</span></span>  
  
 <span data-ttu-id="0d1dd-157">**User name**</span><span class="sxs-lookup"><span data-stu-id="0d1dd-157">**User name**</span></span>  
 <span data-ttu-id="0d1dd-158">Укажите имя входа, используемое при проверке подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0d1dd-158">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="0d1dd-159">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-159">This option is not available.</span></span>  
  
 <span data-ttu-id="0d1dd-160">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="0d1dd-160">**Password**</span></span>  
 <span data-ttu-id="0d1dd-161">Укажите используемый при проверке подлинности пароль.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-161">Provide a password to use when authenticating.</span></span> <span data-ttu-id="0d1dd-162">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="0d1dd-162">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d1dd-163">См. также:</span><span class="sxs-lookup"><span data-stu-id="0d1dd-163">See Also</span></span>  
 [<span data-ttu-id="0d1dd-164">DBCC SHRINKDATABASE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0d1dd-164">DBCC SHRINKDATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql)  
  
  
