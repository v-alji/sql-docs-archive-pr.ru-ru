---
title: Задача "Обновление статистики" (план обслуживания) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.statistics.f1
helpviewer_keywords:
- Updates Statistics Task dialog box
ms.assetid: 22902fd0-eb39-4f18-af94-3fcb69d2a3a4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 486ef2da96785ed200900f497435117ef6437cb5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668853"
---
# <a name="update-statistics-task-maintenance-plan"></a><span data-ttu-id="1512d-102">Задача «Обновление статистики» (план обслуживания)</span><span class="sxs-lookup"><span data-stu-id="1512d-102">Update Statistics Task (Maintenance Plan)</span></span>
  <span data-ttu-id="1512d-103">Диалоговое окно **Задача "Обновление статистики"** служит для обновления сведений [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] о данных в таблицах и индексах.</span><span class="sxs-lookup"><span data-stu-id="1512d-103">Use the **Update Statistics Task** dialog to update [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] information about the data in the tables and indexes.</span></span> <span data-ttu-id="1512d-104">Эта задача осуществляет повторную выборку статистики распределения каждой пользовательской таблицы или индекса.</span><span class="sxs-lookup"><span data-stu-id="1512d-104">This task resamples the distribution statistics of each index created on user tables in the database.</span></span> <span data-ttu-id="1512d-105">При помощи статистики распределения [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] оптимизирует перемещение по таблицам во время обработки инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1512d-105">The distribution statistics are used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to optimize navigation through tables during the processing of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="1512d-106">Для автоматического сбора статистики распределения [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] периодически осуществляет выборку данных в соответствующей таблице по каждому индексу.</span><span class="sxs-lookup"><span data-stu-id="1512d-106">To build the distribution statistics automatically, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] periodically samples the data in the corresponding table for each index.</span></span> <span data-ttu-id="1512d-107">Размер выборки зависит от количества строк в таблице и частоты изменения данных.</span><span class="sxs-lookup"><span data-stu-id="1512d-107">This size of the sample is based on the number of rows in the table and the frequency of data modification.</span></span> <span data-ttu-id="1512d-108">Данный параметр используется для дополнительной выборки с использованием заданного процента данных в таблице.</span><span class="sxs-lookup"><span data-stu-id="1512d-108">Use this option to perform an additional sampling using the specified percentage of data in the tables.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1512d-109">эти сведения используются для оптимизации планов запросов.</span><span class="sxs-lookup"><span data-stu-id="1512d-109">uses this information to create better query plans.</span></span>  
  
 <span data-ttu-id="1512d-110">Данная задача использует инструкцию UPDATE STATISTICS.</span><span class="sxs-lookup"><span data-stu-id="1512d-110">This task executes the UPDATE STATISTICS statement.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1512d-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="1512d-111">Options</span></span>  
 <span data-ttu-id="1512d-112">**Соединение**</span><span class="sxs-lookup"><span data-stu-id="1512d-112">**Connection**</span></span>  
 <span data-ttu-id="1512d-113">Выберите соединение с сервером, которое будет использоваться для выполнения этой задачи.</span><span class="sxs-lookup"><span data-stu-id="1512d-113">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="1512d-114">**Создать**</span><span class="sxs-lookup"><span data-stu-id="1512d-114">**New**</span></span>  
 <span data-ttu-id="1512d-115">Создать новое соединение с сервером для его использования при выполнении этой задачи.</span><span class="sxs-lookup"><span data-stu-id="1512d-115">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="1512d-116">Диалоговое окно **Создание соединения** описано ниже.</span><span class="sxs-lookup"><span data-stu-id="1512d-116">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="1512d-117">**Базы данных**</span><span class="sxs-lookup"><span data-stu-id="1512d-117">**Databases**</span></span>  
 <span data-ttu-id="1512d-118">Укажите базы данных, для которых должна выполняться эта задача.</span><span class="sxs-lookup"><span data-stu-id="1512d-118">Specify the databases affected by this task.</span></span>  
  
-   <span data-ttu-id="1512d-119">**Все базы данных**</span><span class="sxs-lookup"><span data-stu-id="1512d-119">**All databases**</span></span>  
  
     <span data-ttu-id="1512d-120">Позволяет сформировать план обслуживания, который запускает задачи обслуживания для всех баз данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , кроме tempdb.</span><span class="sxs-lookup"><span data-stu-id="1512d-120">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases, except tempdb.</span></span>  
  
-   <span data-ttu-id="1512d-121">**Все системные базы данных**</span><span class="sxs-lookup"><span data-stu-id="1512d-121">**All system databases**</span></span>  
  
     <span data-ttu-id="1512d-122">Будет сформирован план обслуживания, запускающий задачи обслуживания для каждой системной базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , за исключением базы данных tempdb.</span><span class="sxs-lookup"><span data-stu-id="1512d-122">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases except tempdb.</span></span> <span data-ttu-id="1512d-123">Для баз данных, созданных пользователями, задачи обслуживания выполняться не будут.</span><span class="sxs-lookup"><span data-stu-id="1512d-123">No maintenance tasks are run against user-created databases.</span></span>  
  
-   <span data-ttu-id="1512d-124">**Все пользовательские базы данных**</span><span class="sxs-lookup"><span data-stu-id="1512d-124">**All user databases**</span></span>  
  
     <span data-ttu-id="1512d-125">Создается план обслуживания, по которому задачи обслуживания выполняются для всех баз данных, созданных пользователем.</span><span class="sxs-lookup"><span data-stu-id="1512d-125">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="1512d-126">Для системных баз данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] задачи обслуживания выполняться не будут.</span><span class="sxs-lookup"><span data-stu-id="1512d-126">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
-   <span data-ttu-id="1512d-127">**Определенные базы данных**</span><span class="sxs-lookup"><span data-stu-id="1512d-127">**These specific databases**</span></span>  
  
     <span data-ttu-id="1512d-128">Создается план обслуживания, по которому задачи обслуживания должны выполняться только для указанных баз данных.</span><span class="sxs-lookup"><span data-stu-id="1512d-128">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="1512d-129">Если выбран этот параметр, необходимо выбрать в списке хотя бы одну базу данных.</span><span class="sxs-lookup"><span data-stu-id="1512d-129">At least one database in the list must be selected if this option is chosen.</span></span>  
  
 <span data-ttu-id="1512d-130">**Примечание** .   Планы обслуживания выполняются только для баз данных с уровнем совместимости 80 или выше.</span><span class="sxs-lookup"><span data-stu-id="1512d-130">**Note** Maintenance plans only run against databases set to compatibility level 80 or higher.</span></span> <span data-ttu-id="1512d-131">Базы данных с уровнем совместимости 70 или ниже не отображаются.</span><span class="sxs-lookup"><span data-stu-id="1512d-131">Databases set to compatibility level 70 or lower are not displayed.</span></span>  
  
 <span data-ttu-id="1512d-132">**Объект**</span><span class="sxs-lookup"><span data-stu-id="1512d-132">**Object**</span></span>  
 <span data-ttu-id="1512d-133">Ограничьте сетку **Выбор** для отображения таблиц, представлений или обоих элементов.</span><span class="sxs-lookup"><span data-stu-id="1512d-133">Limit the **Selection** grid to display tables, views, or both.</span></span>  
  
 <span data-ttu-id="1512d-134">**Выбор**</span><span class="sxs-lookup"><span data-stu-id="1512d-134">**Selection**</span></span>  
 <span data-ttu-id="1512d-135">Укажите таблицы или индексы, которые должны обрабатываться этой задачей.</span><span class="sxs-lookup"><span data-stu-id="1512d-135">Specify the tables or indexes affected by this task.</span></span> <span data-ttu-id="1512d-136">Недоступно, если в диалоговом окне «Объект» выбран тип **Таблицы и представления** .</span><span class="sxs-lookup"><span data-stu-id="1512d-136">Not available when **Tables and Views** is selected in the Object box.</span></span>  
  
 <span data-ttu-id="1512d-137">**Вся собранная статистика**</span><span class="sxs-lookup"><span data-stu-id="1512d-137">**All existing statistics**</span></span>  
 <span data-ttu-id="1512d-138">Обновить статистику столбцов и статистику индексов.</span><span class="sxs-lookup"><span data-stu-id="1512d-138">Update statistics for both columns and indexes.</span></span>  
  
 <span data-ttu-id="1512d-139">**Только статистика по столбцам**</span><span class="sxs-lookup"><span data-stu-id="1512d-139">**Column statistics only**</span></span>  
 <span data-ttu-id="1512d-140">Обновить только статистику столбцов.</span><span class="sxs-lookup"><span data-stu-id="1512d-140">Only update column statistics.</span></span>  
  
 <span data-ttu-id="1512d-141">**Только статистика индексов**</span><span class="sxs-lookup"><span data-stu-id="1512d-141">**Index statistics only**</span></span>  
 <span data-ttu-id="1512d-142">Обновить только статистику индексов.</span><span class="sxs-lookup"><span data-stu-id="1512d-142">Only update index statistics.</span></span>  
  
 <span data-ttu-id="1512d-143">**Тип просмотра**</span><span class="sxs-lookup"><span data-stu-id="1512d-143">**Scan type**</span></span>  
 <span data-ttu-id="1512d-144">Тип просмотра, который используется для сбора обновленной статистики.</span><span class="sxs-lookup"><span data-stu-id="1512d-144">Type of scan used to gather updated statistics.</span></span>  
  
 <span data-ttu-id="1512d-145">**Полный просмотр**</span><span class="sxs-lookup"><span data-stu-id="1512d-145">**Full scan**</span></span>  
 <span data-ttu-id="1512d-146">Считывает все строки в таблице или представлении для сбора статистики.</span><span class="sxs-lookup"><span data-stu-id="1512d-146">Read all rows in the table or view to gather the statistics.</span></span>  
  
 <span data-ttu-id="1512d-147">**Пример**</span><span class="sxs-lookup"><span data-stu-id="1512d-147">**Sample by**</span></span>  
 <span data-ttu-id="1512d-148">Укажите процент таблицы или индексированного представления либо количество строк для выборки, если статистика собирается для больших таблиц или представлений.</span><span class="sxs-lookup"><span data-stu-id="1512d-148">Specify the percentage of the table or indexed view, or the number of rows to sample when collecting statistics for larger tables or views.</span></span>  
  
 <span data-ttu-id="1512d-149">**Просмотр T-SQL**</span><span class="sxs-lookup"><span data-stu-id="1512d-149">**View T-SQL**</span></span>  
 <span data-ttu-id="1512d-150">Просмотрите инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] , выполняемые для данной задачи по отношению к серверу, на основе выбранных параметров.</span><span class="sxs-lookup"><span data-stu-id="1512d-150">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1512d-151">Если количество затронутых объектов велико, построение этого отображения может занять значительное время.</span><span class="sxs-lookup"><span data-stu-id="1512d-151">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="1512d-152">Диалоговое окно «Создание соединения»</span><span class="sxs-lookup"><span data-stu-id="1512d-152">New Connection Dialog Box</span></span>  
 <span data-ttu-id="1512d-153">**Имя соединения**</span><span class="sxs-lookup"><span data-stu-id="1512d-153">**Connection name**</span></span>  
 <span data-ttu-id="1512d-154">Введите имя нового соединения.</span><span class="sxs-lookup"><span data-stu-id="1512d-154">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="1512d-155">**Выберите или введите имя сервера**</span><span class="sxs-lookup"><span data-stu-id="1512d-155">**Select or enter a server name**</span></span>  
 <span data-ttu-id="1512d-156">Выберите сервер для подключения при выполнении этой задачи.</span><span class="sxs-lookup"><span data-stu-id="1512d-156">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="1512d-157">**Обновить**</span><span class="sxs-lookup"><span data-stu-id="1512d-157">**Refresh**</span></span>  
 <span data-ttu-id="1512d-158">Обновите список доступных серверов.</span><span class="sxs-lookup"><span data-stu-id="1512d-158">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="1512d-159">**Введите данные для входа на сервер**</span><span class="sxs-lookup"><span data-stu-id="1512d-159">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="1512d-160">Укажите способ проверки подлинности на сервере.</span><span class="sxs-lookup"><span data-stu-id="1512d-160">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="1512d-161">**Использовать встроенную безопасность Windows**</span><span class="sxs-lookup"><span data-stu-id="1512d-161">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="1512d-162">Подключиться к экземпляру компонента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] c проверкой подлинности [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="1512d-162">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="1512d-163">**Использовать указанные имя пользователя и пароль**</span><span class="sxs-lookup"><span data-stu-id="1512d-163">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="1512d-164">Подключиться к экземпляру компонента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] с использованием проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1512d-164">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="1512d-165">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="1512d-165">This option is not available.</span></span>  
  
 <span data-ttu-id="1512d-166">**User name**</span><span class="sxs-lookup"><span data-stu-id="1512d-166">**User name**</span></span>  
 <span data-ttu-id="1512d-167">Укажите имя входа, используемое при проверке подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1512d-167">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="1512d-168">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="1512d-168">This option is not available.</span></span>  
  
 <span data-ttu-id="1512d-169">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="1512d-169">**Password**</span></span>  
 <span data-ttu-id="1512d-170">Укажите используемый при проверке подлинности пароль.</span><span class="sxs-lookup"><span data-stu-id="1512d-170">Provide a password to use when authenticating.</span></span> <span data-ttu-id="1512d-171">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="1512d-171">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1512d-172">См. также:</span><span class="sxs-lookup"><span data-stu-id="1512d-172">See Also</span></span>  
 [<span data-ttu-id="1512d-173">UPDATE STATISTICS (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1512d-173">UPDATE STATISTICS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/update-statistics-transact-sql)  
  
  
