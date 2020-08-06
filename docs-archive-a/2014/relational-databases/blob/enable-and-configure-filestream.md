---
title: Включение и настройка FILESTREAM | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.technology: filestream
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], enabling
ms.assetid: 78737e19-c65b-48d9-8fa9-aa6f1e1bce73
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f6c0e505bd32636d045519b36e439bc21c7079d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654361"
---
# <a name="enable-and-configure-filestream"></a><span data-ttu-id="bd9b1-102">Включение и настройка FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="bd9b1-102">Enable and Configure FILESTREAM</span></span>
  <span data-ttu-id="bd9b1-103">Перед началом использования хранилища FILESTREAM его необходимо включить в экземпляре компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd9b1-103">Before you can start to use FILESTREAM, you must enable FILESTREAM on the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="bd9b1-104">В этом разделе описано, как включить FILESTREAM с помощью диспетчера конфигурации SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bd9b1-104">This topic describes how to enable FILESTREAM by using SQL Server Configuration Manager.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bd9b1-105">Нельзя включить функцию FILESTREAM в 32-разрядной версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], запущенной в 64-разрядной операционной системе.</span><span class="sxs-lookup"><span data-stu-id="bd9b1-105">You cannot enable FILESTREAM on a 32-bit version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on a 64-bit operating system.</span></span>  
  
##  <a name="enabling-filestream"></a><a name="enabling"></a> <span data-ttu-id="bd9b1-106">Включение FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="bd9b1-106">Enabling FILESTREAM</span></span>  
  
#### <a name="to-enable-and-change-filestream-settings"></a><span data-ttu-id="bd9b1-107">Включение и изменение параметров FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="bd9b1-107">To enable and change FILESTREAM settings</span></span>  
  
1.  <span data-ttu-id="bd9b1-108">В меню **Пуск** последовательно выберите пункты **Все программы**, [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], **Средства настройки**и щелкните **Диспетчер конфигурации SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="bd9b1-108">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="bd9b1-109">В списке служб щелкните правой кнопкой мыши **Службы SQL Server**и выберите команду **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="bd9b1-109">In the list of services, right-click **SQL Server Services**, and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="bd9b1-110">В оснастке **Диспетчер конфигурации SQL Server** найдите экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , в котором нужно включить FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="bd9b1-110">In the **SQL Server Configuration Manager** snap-in, locate the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on which you want to enable FILESTREAM.</span></span>  
  
4.  <span data-ttu-id="bd9b1-111">Щелкните правой кнопкой мыши экземпляр и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="bd9b1-111">Right-click the instance, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="bd9b1-112">В диалоговом окне **Свойства SQL Server** перейдите на вкладку **FILESTREAM** .</span><span class="sxs-lookup"><span data-stu-id="bd9b1-112">In the **SQL Server Properties** dialog box, click the **FILESTREAM** tab.</span></span>  
  
6.  <span data-ttu-id="bd9b1-113">Установите флажок **Разрешить FILESTREAM при доступе через Transact-SQL** .</span><span class="sxs-lookup"><span data-stu-id="bd9b1-113">Select the **Enable FILESTREAM for Transact-SQL access** check box.</span></span>  
  
7.  <span data-ttu-id="bd9b1-114">Если нужно считывать и записывать данные FILESTREAM из Windows, установите флажок **Разрешить FILESTREAM при потоковом доступе файлового ввода-вывода**.</span><span class="sxs-lookup"><span data-stu-id="bd9b1-114">If you want to read and write FILESTREAM data from Windows, click **Enable FILESTREAM for file I/O streaming access**.</span></span> <span data-ttu-id="bd9b1-115">Введите имя общего ресурса Windows в поле **Имя общего ресурса Windows** .</span><span class="sxs-lookup"><span data-stu-id="bd9b1-115">Enter the name of the Windows share in the **Windows Share Name** box.</span></span>  
  
8.  <span data-ttu-id="bd9b1-116">Если удаленные клиенты должны иметь доступ к данным FILESTREAM, хранящимся в этом общем ресурсе, установите флажок **Разрешить удаленным клиентам потоковый доступ к данным FILESTREAM**.</span><span class="sxs-lookup"><span data-stu-id="bd9b1-116">If remote clients must access the FILESTREAM data that is stored on this share, select **Allow remote clients to have streaming access to FILESTREAM data**.</span></span>  
  
9. <span data-ttu-id="bd9b1-117">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="bd9b1-117">Click **Apply**.</span></span>  
  
10. <span data-ttu-id="bd9b1-118">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]нажмите кнопку **Создать запрос** , чтобы открыть редактор запросов.</span><span class="sxs-lookup"><span data-stu-id="bd9b1-118">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], click **New Query** to display the Query Editor.</span></span>  
  
11. <span data-ttu-id="bd9b1-119">В редакторе запросов введите следующий код [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="bd9b1-119">In Query Editor, enter the following [!INCLUDE[tsql](../../includes/tsql-md.md)] code:</span></span>  
  
    ```sql  
    EXEC sp_configure filestream_access_level, 2  
    RECONFIGURE  
    ```  
  
12. <span data-ttu-id="bd9b1-120">Нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="bd9b1-120">Click **Execute**.</span></span>  
  
13. <span data-ttu-id="bd9b1-121">Перезапустите службу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bd9b1-121">Restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  

  
##  <a name="best-practices"></a><a name="best"></a> <span data-ttu-id="bd9b1-122">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="bd9b1-122">Best Practices</span></span>  
  
###  <a name="physical-configuration-and-maintenance"></a><a name="config"></a><span data-ttu-id="bd9b1-123">Физическая конфигурация и обслуживание</span><span class="sxs-lookup"><span data-stu-id="bd9b1-123">Physical Configuration and Maintenance</span></span>  
 <span data-ttu-id="bd9b1-124">При использовании томов хранилища FILESTREAM обратите внимание на следующие рекомендации.</span><span class="sxs-lookup"><span data-stu-id="bd9b1-124">When you set up FILESTREAM storage volumes, consider the following guidelines:</span></span>  
  
-   <span data-ttu-id="bd9b1-125">Отключите короткие имена файлов на компьютерах с FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="bd9b1-125">Turn off short file names on FILESTREAM computer systems.</span></span> <span data-ttu-id="bd9b1-126">Короткие имена файлов создаются гораздо дольше.</span><span class="sxs-lookup"><span data-stu-id="bd9b1-126">Short file names take significantly longer to create.</span></span> <span data-ttu-id="bd9b1-127">Отключить короткие имена файлов можно с помощью программы Windows **fsutil** .</span><span class="sxs-lookup"><span data-stu-id="bd9b1-127">To disable short file names, use the Windows **fsutil** utility.</span></span>  
  
-   <span data-ttu-id="bd9b1-128">Регулярно выполняйте дефрагментацию на компьютерах с FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="bd9b1-128">Regularly defragment FILESTREAM computer systems.</span></span>  
  
-   <span data-ttu-id="bd9b1-129">Используйте файловую систему NTFS с кластерами по 64 килобайт.</span><span class="sxs-lookup"><span data-stu-id="bd9b1-129">Use 64-KB NTFS clusters.</span></span> <span data-ttu-id="bd9b1-130">На сжатых томах должна быть файловая система NTFS с кластерами по 4 килобайта.</span><span class="sxs-lookup"><span data-stu-id="bd9b1-130">Compressed volumes must be set to 4-KB NTFS clusters.</span></span>  
  
-   <span data-ttu-id="bd9b1-131">Отключите индексирование на томах FILESTREAM и установите параметр **disablelastaccess** . **Для этого**воспользуйтесь программой **fsutil** Windows.</span><span class="sxs-lookup"><span data-stu-id="bd9b1-131">Disable indexing on FILESTREAM volumes and set **disablelastaccess** To set **disablelastaccess**, use the Windows **fsutil** utility.</span></span>  
  
-   <span data-ttu-id="bd9b1-132">Отключите антивирусное сканирование на томах FILESTREAM, если оно не является необходимым.</span><span class="sxs-lookup"><span data-stu-id="bd9b1-132">Disable antivirus scanning of FILESTREAM volumes when it is not unnecessary.</span></span> <span data-ttu-id="bd9b1-133">Если антивирусное сканирование необходимо, не настраивайте политики автоматического удаления зараженных файлов.</span><span class="sxs-lookup"><span data-stu-id="bd9b1-133">If antivirus scanning is necessary, avoid setting policies that will automatically delete offending files.</span></span>  
  
-   <span data-ttu-id="bd9b1-134">Настройте уровень отказоустойчивости и производительности RAID в соответствии с требованиями приложения.</span><span class="sxs-lookup"><span data-stu-id="bd9b1-134">Set up and tune the RAID level for fault tolerance and the performance that is required by an application.</span></span>  
  
||||||  
|-|-|-|-|-|  
|<span data-ttu-id="bd9b1-135">Уровень RAID</span><span class="sxs-lookup"><span data-stu-id="bd9b1-135">RAID level</span></span>|<span data-ttu-id="bd9b1-136">Производительность записи</span><span class="sxs-lookup"><span data-stu-id="bd9b1-136">Write performance</span></span>|<span data-ttu-id="bd9b1-137">Производительность чтения</span><span class="sxs-lookup"><span data-stu-id="bd9b1-137">Read performance</span></span>|<span data-ttu-id="bd9b1-138">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="bd9b1-138">Fault tolerance</span></span>|<span data-ttu-id="bd9b1-139">Remarks</span><span class="sxs-lookup"><span data-stu-id="bd9b1-139">Remarks</span></span>|  
|<span data-ttu-id="bd9b1-140">RAID 5</span><span class="sxs-lookup"><span data-stu-id="bd9b1-140">RAID 5</span></span>|<span data-ttu-id="bd9b1-141">Нормальный</span><span class="sxs-lookup"><span data-stu-id="bd9b1-141">Normal</span></span>|<span data-ttu-id="bd9b1-142">Нормальный</span><span class="sxs-lookup"><span data-stu-id="bd9b1-142">Normal</span></span>|<span data-ttu-id="bd9b1-143">Высокая</span><span class="sxs-lookup"><span data-stu-id="bd9b1-143">Excellent</span></span>|<span data-ttu-id="bd9b1-144">Производительность лучше, чем у диска или JBOD, но хуже, чем у RAID 0 или RAID 5 с чередованием.</span><span class="sxs-lookup"><span data-stu-id="bd9b1-144">Performance is better than one disk or JBOD; and less than RAID 0 or RAID 5 with striping.</span></span>|  
|<span data-ttu-id="bd9b1-145">RAID 0</span><span class="sxs-lookup"><span data-stu-id="bd9b1-145">RAID 0</span></span>|<span data-ttu-id="bd9b1-146">Высокая</span><span class="sxs-lookup"><span data-stu-id="bd9b1-146">Excellent</span></span>|<span data-ttu-id="bd9b1-147">Высокая</span><span class="sxs-lookup"><span data-stu-id="bd9b1-147">Excellent</span></span>|<span data-ttu-id="bd9b1-148">None</span><span class="sxs-lookup"><span data-stu-id="bd9b1-148">None</span></span>||  
|<span data-ttu-id="bd9b1-149">RAID 5 + чередование</span><span class="sxs-lookup"><span data-stu-id="bd9b1-149">RAID 5 + stripping</span></span>|<span data-ttu-id="bd9b1-150">Высокая</span><span class="sxs-lookup"><span data-stu-id="bd9b1-150">Excellent</span></span>|<span data-ttu-id="bd9b1-151">Высокая</span><span class="sxs-lookup"><span data-stu-id="bd9b1-151">Excellent</span></span>|<span data-ttu-id="bd9b1-152">Высокая</span><span class="sxs-lookup"><span data-stu-id="bd9b1-152">Excellent</span></span>|<span data-ttu-id="bd9b1-153">Самый дорогостоящий вариант.</span><span class="sxs-lookup"><span data-stu-id="bd9b1-153">Most expensive option.</span></span>|  
  

  
###  <a name="physical-database-design"></a><a name="database"></a><span data-ttu-id="bd9b1-154">Структура физической базы данных</span><span class="sxs-lookup"><span data-stu-id="bd9b1-154">Physical Database Design</span></span>  
 <span data-ttu-id="bd9b1-155">При проектировании базы данных FILESTREAM следует учитывать следующие рекомендации.</span><span class="sxs-lookup"><span data-stu-id="bd9b1-155">When you design a FILESTREAM database, consider the following guidelines:</span></span>  
  
-   <span data-ttu-id="bd9b1-156">Столбцы FILESTREAM должны сопровождаться соответствующим `uniqueidentifier` столбцом ROWGUID.</span><span class="sxs-lookup"><span data-stu-id="bd9b1-156">FILESTREAM columns must be accompanied by a corresponding `uniqueidentifier`ROWGUID column.</span></span> <span data-ttu-id="bd9b1-157">Кроме того, типам таблиц также должен соответствовать уникальный индекс.</span><span class="sxs-lookup"><span data-stu-id="bd9b1-157">These kinds of tables must also be accompanied by a unique index.</span></span> <span data-ttu-id="bd9b1-158">Как правило, этот индекс не является кластеризованным.</span><span class="sxs-lookup"><span data-stu-id="bd9b1-158">Typically this index is not a clustered index.</span></span> <span data-ttu-id="bd9b1-159">Если бизнес-логика базы данных требует использовать кластеризованный индекс, следует убедиться, что значения, которые хранятся в индексе, не являются случайными.</span><span class="sxs-lookup"><span data-stu-id="bd9b1-159">If the databases business logic requires a clustered index, you have to make sure that the values stored in the index are not random.</span></span> <span data-ttu-id="bd9b1-160">Случайные значения приведут к переупорядочению индекса при каждом добавлении или удалении строки в таблице.</span><span class="sxs-lookup"><span data-stu-id="bd9b1-160">Random values will cause the index to be reordered every time that a row is added or removed from the table.</span></span>  
  
-   <span data-ttu-id="bd9b1-161">По соображениям производительности файловые группы и контейнеры FILESTREAM находятся на томах, отличных от тех, где находится операционная система, база данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , журнал [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , база данных tempdb или файл подкачки.</span><span class="sxs-lookup"><span data-stu-id="bd9b1-161">For performance reasons, FILESTREAM filegroups and containers should reside on volumes other than the operating system, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log, tempdb, or paging file.</span></span>  
  
-   <span data-ttu-id="bd9b1-162">Управление местом на диске и соответствующие политики не поддерживаются FILESTREAM напрямую.</span><span class="sxs-lookup"><span data-stu-id="bd9b1-162">Space management and policies are not directly supported by FILESTREAM.</span></span> <span data-ttu-id="bd9b1-163">Однако можно управлять местом и применять политики косвенно путем присвоения каждой файловой группы FILESTREAM отдельному тому с последующим применением функций управления данного тома.</span><span class="sxs-lookup"><span data-stu-id="bd9b1-163">However, you can manage space and apply policies indirectly by assigning each FILESTREAM filegroup to a separate volume and using the volume's management features.</span></span>  
  
  
