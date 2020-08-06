---
title: Задача "Перестроение индекса" (план обслуживания) | Документация Майкрософт
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.reindex.f1
- reindex
helpviewer_keywords:
- Rebuild Index Task dialog box
ms.assetid: 33e2940b-139f-4563-b0cb-5683f08bd879
author: rothja
ms.author: jroth
ms.openlocfilehash: bc9d7c85a72c34cee1ef7af8cb4b4f25f918a3fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658232"
---
# <a name="rebuild-index-task-maintenance-plan"></a><span data-ttu-id="f0ca0-102">Задача «Перестроение индекса» (план обслуживания)</span><span class="sxs-lookup"><span data-stu-id="f0ca0-102">Rebuild Index Task (Maintenance Plan)</span></span>
  <span data-ttu-id="f0ca0-103">Диалоговое окно **Задача "Перестроение индекса"** используется для пересоздания индексов на таблицах в базе данных с новым коэффициентом заполнения.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-103">Use the **Rebuild Index Task** dialog to re-create the indexes on the tables in the database with a new fill factor.</span></span> <span data-ttu-id="f0ca0-104">Коэффициент заполнения определяет количество пустого пространства на каждой странице индекса для обеспечения роста в будущем.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-104">The fill factor determines the amount of empty space on each page in the index, to accommodate future expansion.</span></span> <span data-ttu-id="f0ca0-105">По мере того как к таблице добавляются данные, свободное пространство заполняется, поскольку коэффициент заполнения не сохраняется.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-105">As data is added to the table, the free space fills because the fill factor is not maintained.</span></span> <span data-ttu-id="f0ca0-106">Восстановить свободное пространство можно путем реорганизации данных и страниц индекса.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-106">Reorganizing data and index pages can re-establish the free space.</span></span>  
  
 <span data-ttu-id="f0ca0-107">**Задача "Перестроение индекса"** использует инструкцию ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-107">The **Rebuild Index Task** uses the ALTER INDEX statement.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f0ca0-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="f0ca0-108">Options</span></span>  
 <span data-ttu-id="f0ca0-109">**Соединение**</span><span class="sxs-lookup"><span data-stu-id="f0ca0-109">**Connection**</span></span>  
 <span data-ttu-id="f0ca0-110">Выберите соединение с сервером, которое будет использоваться для выполнения этой задачи.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-110">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="f0ca0-111">**Создать**</span><span class="sxs-lookup"><span data-stu-id="f0ca0-111">**New**</span></span>  
 <span data-ttu-id="f0ca0-112">Создать новое соединение с сервером для его использования при выполнении этой задачи.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-112">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="f0ca0-113">Диалоговое окно **Создание соединения** описано ниже.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-113">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="f0ca0-114">**Базы данных**</span><span class="sxs-lookup"><span data-stu-id="f0ca0-114">**Databases**</span></span>  
 <span data-ttu-id="f0ca0-115">Укажите базы данных, для которых должна выполняться эта задача.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-115">Specify the databases affected by this task.</span></span>  
  
-   <span data-ttu-id="f0ca0-116">**Все базы данных**</span><span class="sxs-lookup"><span data-stu-id="f0ca0-116">**All databases**</span></span>  
  
     <span data-ttu-id="f0ca0-117">Создается план обслуживания, по которому задачи обслуживания должны выполняться для всех баз данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , кроме базы данных tempdb.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-117">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases except tempdb.</span></span>  
  
-   <span data-ttu-id="f0ca0-118">**Все системные базы данных**</span><span class="sxs-lookup"><span data-stu-id="f0ca0-118">**All system databases**</span></span>  
  
     <span data-ttu-id="f0ca0-119">Будет сформирован план обслуживания, запускающий задачи обслуживания для каждой системной базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , за исключением базы данных tempdb.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-119">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases except tempdb.</span></span> <span data-ttu-id="f0ca0-120">Для баз данных, созданных пользователями, задачи обслуживания выполняться не будут.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-120">No maintenance tasks are run against user-created databases.</span></span>  
  
-   <span data-ttu-id="f0ca0-121">**Все пользовательские базы данных**</span><span class="sxs-lookup"><span data-stu-id="f0ca0-121">**All user databases**</span></span>  
  
     <span data-ttu-id="f0ca0-122">Создается план обслуживания, по которому задачи обслуживания выполняются для всех баз данных, созданных пользователем.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-122">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="f0ca0-123">Для системных баз данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] задачи обслуживания выполняться не будут.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-123">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
-   <span data-ttu-id="f0ca0-124">**Определенные базы данных**</span><span class="sxs-lookup"><span data-stu-id="f0ca0-124">**These specific databases**</span></span>  
  
     <span data-ttu-id="f0ca0-125">Создается план обслуживания, по которому задачи обслуживания должны выполняться только для указанных баз данных.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-125">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="f0ca0-126">Если выбран этот параметр, необходимо выбрать в списке хотя бы одну базу данных.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-126">At least one database in the list must be selected if this option is chosen.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f0ca0-127">Планы обслуживания выполняются только для баз данных, уровень совместимости которых 80 или выше.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-127">Maintenance plans only run against databases set to compatibility level 80 or higher.</span></span> <span data-ttu-id="f0ca0-128">Базы данных с уровнем совместимости 70 или ниже не отображаются.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-128">Databases set to compatibility level 70 or lower are not displayed.</span></span>  
  
 <span data-ttu-id="f0ca0-129">**Объект**</span><span class="sxs-lookup"><span data-stu-id="f0ca0-129">**Object**</span></span>  
 <span data-ttu-id="f0ca0-130">Ограничьте сетку **Выбор** для отображения таблиц, представлений или обоих элементов.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-130">Limit the **Selection** grid to display tables, views, or both.</span></span>  
  
 <span data-ttu-id="f0ca0-131">**Выбор**</span><span class="sxs-lookup"><span data-stu-id="f0ca0-131">**Selection**</span></span>  
 <span data-ttu-id="f0ca0-132">Укажите таблицы или индексы, которые должны обрабатываться этой задачей.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-132">Specify the tables or indexes affected by this task.</span></span> <span data-ttu-id="f0ca0-133">Недоступно, если в диалоговом окне «Объект» выбран тип **Таблицы и представления** .</span><span class="sxs-lookup"><span data-stu-id="f0ca0-133">Not available when **Tables and Views** is selected in the Object box.</span></span>  
  
 <span data-ttu-id="f0ca0-134">**Реорганизовать страницы с использованием объема свободного места по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="f0ca0-134">**Reorganize pages with the default amount of free space**</span></span>  
 <span data-ttu-id="f0ca0-135">Удалите индексы таблиц в базе данных и создайте их повторно с коэффициентом заполнения, указанным при создании индексов.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-135">Drop the indexes on the tables in the database and re-create them with the fill factor that was specified when the indexes were created.</span></span>  
  
 <span data-ttu-id="f0ca0-136">**Изменить процент свободного места на страницу до**</span><span class="sxs-lookup"><span data-stu-id="f0ca0-136">**Change free space per page percentage to**</span></span>  
 <span data-ttu-id="f0ca0-137">Удалите индексы таблиц в базе данных и создайте их повторно с новым, автоматически вычисляемым коэффициентом заполнения, резервирующим указанный объем свободного пространства на страницах индекса.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-137">Drop the indexes on the tables in the database and re-create them with a new, automatically calculated fill factor, thereby reserving the specified amount of free space on the index pages.</span></span> <span data-ttu-id="f0ca0-138">Чем выше процентное значение, тем больше свободного места резервируется на страницах индекса и тем больше будет размер индекса.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-138">The higher the percentage, the more free space is reserved on the index pages, and the larger the index grows.</span></span> <span data-ttu-id="f0ca0-139">Допустимые значения: от 0 до 100.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-139">Valid values are from 0 through 100.</span></span>  
  
 <span data-ttu-id="f0ca0-140">**Отсортировать результаты в базе данных tempdb**</span><span class="sxs-lookup"><span data-stu-id="f0ca0-140">**Sort results in tempdb**</span></span>  
 <span data-ttu-id="f0ca0-141">Используйте `SORT_IN_TEMPDB` параметр, определяющий, где временно сохраняются промежуточные результаты сортировки, созданные во время создания индекса.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-141">Use the `SORT_IN_TEMPDB`option, which determines where the intermediate sort results, generated during index creation, are temporarily stored.</span></span> <span data-ttu-id="f0ca0-142">Если операция сортировки не требуется или сортировка может быть выполнена в памяти, параметр `SORT_IN_TEMPDB`не учитывается.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-142">If a sort operation is not required, or if the sort can be performed in memory, the `SORT_IN_TEMPDB`option is ignored.</span></span>  
  
 <span data-ttu-id="f0ca0-143">**Сохранять индекс в рабочем состоянии в процессе переиндексирования**</span><span class="sxs-lookup"><span data-stu-id="f0ca0-143">**Keep index online while reindexing**</span></span>  
 <span data-ttu-id="f0ca0-144">Параметр `ONLINE` дает пользователям возможность получать доступ к базовой таблице или данным кластеризованного индекса, а также к любым связанным с ними некластеризованным индексам при операциях с индексами.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-144">Use the `ONLINE` option which allows users to access the underlying table or clustered index data and any associated nonclustered indexes during index operations.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f0ca0-145">Операции с индексами в сети доступны не во всех выпусках [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0ca0-145">Online index operations are not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f0ca0-146">Перечень функций, поддерживаемых в разных выпусках [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], см. в разделе [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="f0ca0-146">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
 <span data-ttu-id="f0ca0-147">**Просмотр T-SQL**</span><span class="sxs-lookup"><span data-stu-id="f0ca0-147">**View T-SQL**</span></span>  
 <span data-ttu-id="f0ca0-148">Просмотрите инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] , выполняемые для данной задачи по отношению к серверу, на основе выбранных параметров.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-148">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f0ca0-149">Если количество затронутых объектов велико, построение этого отображения может занять значительное время.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-149">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="f0ca0-150">Диалоговое окно «Создание соединения»</span><span class="sxs-lookup"><span data-stu-id="f0ca0-150">New Connection Dialog Box</span></span>  
 <span data-ttu-id="f0ca0-151">**Имя соединения**</span><span class="sxs-lookup"><span data-stu-id="f0ca0-151">**Connection name**</span></span>  
 <span data-ttu-id="f0ca0-152">Введите имя нового соединения.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-152">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="f0ca0-153">**Выберите или введите имя сервера**</span><span class="sxs-lookup"><span data-stu-id="f0ca0-153">**Select or enter a server name**</span></span>  
 <span data-ttu-id="f0ca0-154">Выберите сервер для подключения при выполнении этой задачи.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-154">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="f0ca0-155">**Обновить**</span><span class="sxs-lookup"><span data-stu-id="f0ca0-155">**Refresh**</span></span>  
 <span data-ttu-id="f0ca0-156">Обновите список доступных серверов.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-156">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="f0ca0-157">**Введите данные для входа на сервер**</span><span class="sxs-lookup"><span data-stu-id="f0ca0-157">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="f0ca0-158">Укажите способ проверки подлинности на сервере.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-158">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="f0ca0-159">**Использовать встроенную безопасность Windows**</span><span class="sxs-lookup"><span data-stu-id="f0ca0-159">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="f0ca0-160">Подключиться к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] с использованием проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-160">Connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] with Windows Authentication.</span></span>  
  
 <span data-ttu-id="f0ca0-161">**Использовать указанные имя пользователя и пароль**</span><span class="sxs-lookup"><span data-stu-id="f0ca0-161">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="f0ca0-162">Подключиться к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] с использованием проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f0ca0-162">Connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="f0ca0-163">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-163">This option is not available.</span></span>  
  
 <span data-ttu-id="f0ca0-164">**User name**</span><span class="sxs-lookup"><span data-stu-id="f0ca0-164">**User name**</span></span>  
 <span data-ttu-id="f0ca0-165">Укажите имя входа, используемое при проверке подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f0ca0-165">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="f0ca0-166">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-166">This option is not available.</span></span>  
  
 <span data-ttu-id="f0ca0-167">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="f0ca0-167">**Password**</span></span>  
 <span data-ttu-id="f0ca0-168">Укажите используемый при проверке подлинности пароль.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-168">Provide a password to use when authenticating.</span></span> <span data-ttu-id="f0ca0-169">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="f0ca0-169">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0ca0-170">См. также:</span><span class="sxs-lookup"><span data-stu-id="f0ca0-170">See Also</span></span>  
 <span data-ttu-id="f0ca0-171">[ALTER INDEX (Transact-SQL)](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f0ca0-171">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 <span data-ttu-id="f0ca0-172">[DBCC DBREINDEX (Transact-SQL)](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f0ca0-172">[DBCC DBREINDEX &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql) </span></span>  
 <span data-ttu-id="f0ca0-173">[CREATE INDEX (Transact-SQL)](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f0ca0-173">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 <span data-ttu-id="f0ca0-174">[Параметр SORT_IN_TEMPDB для индексов](../indexes/indexes.md) </span><span class="sxs-lookup"><span data-stu-id="f0ca0-174">[SORT_IN_TEMPDB Option For Indexes](../indexes/indexes.md) </span></span>  
 <span data-ttu-id="f0ca0-175">[Руководящие принципы для операций с индексами](../indexes/guidelines-for-online-index-operations.md) </span><span class="sxs-lookup"><span data-stu-id="f0ca0-175">[Guidelines for Online Index Operations](../indexes/guidelines-for-online-index-operations.md) </span></span>  
 <span data-ttu-id="f0ca0-176">[Об операциях с индексом в сети](../indexes/how-online-index-operations-work.md) </span><span class="sxs-lookup"><span data-stu-id="f0ca0-176">[How Online Index Operations Work](../indexes/how-online-index-operations-work.md) </span></span>  
 [<span data-ttu-id="f0ca0-177">Выполнение операций с индексами в оперативном режиме</span><span class="sxs-lookup"><span data-stu-id="f0ca0-177">Perform Index Operations Online</span></span>](../indexes/perform-index-operations-online.md)  
  
  
