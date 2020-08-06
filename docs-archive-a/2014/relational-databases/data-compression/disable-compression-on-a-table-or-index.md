---
title: Отключение сжатия таблицы или индекса | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- data compression [SQL Server], disabling
ms.assetid: bda1e452-397b-4757-82a4-181217361589
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 80b5775d3b6f7a3f47ab75c5348b556c17b6e676
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667224"
---
# <a name="disable-compression-on-a-table-or-index"></a><span data-ttu-id="7e0f3-102">Отключение сжатия таблицы или индекса</span><span class="sxs-lookup"><span data-stu-id="7e0f3-102">Disable Compression on a Table or Index</span></span>
  <span data-ttu-id="7e0f3-103">В этом разделе описывается, как отключить сжатие для таблицы или индекса в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7e0f3-103">This topic describes how to disable compression on a table or index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="7e0f3-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="7e0f3-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7e0f3-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="7e0f3-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7e0f3-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="7e0f3-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="7e0f3-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="7e0f3-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7e0f3-108">**Отключение сжатия для таблицы или индекса при помощи:**</span><span class="sxs-lookup"><span data-stu-id="7e0f3-108">**To disable compression on a table or index, using:**</span></span>  
  
     [<span data-ttu-id="7e0f3-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7e0f3-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7e0f3-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7e0f3-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7e0f3-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="7e0f3-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="7e0f3-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="7e0f3-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="7e0f3-113">Если таблица является кучей, то операция перестроения в режиме ONLINE будет однопотоковой.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-113">If the table is a heap, the rebuild operation for ONLINE mode will be single threaded.</span></span> <span data-ttu-id="7e0f3-114">Используйте режим OFFLINE для выполнения многопотоковых операций перестроения кучи.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-114">Use OFFLINE mode for a multi-threaded heap rebuild operation.</span></span> <span data-ttu-id="7e0f3-115">Дополнительную информацию о сжатии данных см. в разделе [Сжатие данных](data-compression.md).</span><span class="sxs-lookup"><span data-stu-id="7e0f3-115">For a more information about data compression, see [Data Compression](data-compression.md).</span></span>  
  
-   <span data-ttu-id="7e0f3-116">Оценить состояние сжатия таблицы, индекса или секции можно с помощью хранимой процедуры [sp_estimate_data_compression_savings](/sql/relational-databases/system-stored-procedures/sp-estimate-data-compression-savings-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7e0f3-116">To evaluate how changing the compression state will affect a table, an index, or a partition, use the [sp_estimate_data_compression_savings](/sql/relational-databases/system-stored-procedures/sp-estimate-data-compression-savings-transact-sql) stored procedure.</span></span>  
  
-   <span data-ttu-id="7e0f3-117">Если у таблицы есть невыровненные индексы, изменить настройку сжатия отдельной секции невозможно.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-117">You cannot change the compression setting of a single partition if the table has nonaligned indexes.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7e0f3-118">безопасность</span><span class="sxs-lookup"><span data-stu-id="7e0f3-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7e0f3-119">Permissions</span><span class="sxs-lookup"><span data-stu-id="7e0f3-119">Permissions</span></span>  
 <span data-ttu-id="7e0f3-120">Необходимо разрешение ALTER на таблицу или индекс.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-120">Requires ALTER permission on the table or index.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7e0f3-121">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7e0f3-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-compression-on-a-table"></a><span data-ttu-id="7e0f3-122">Отключение сжатия в таблице</span><span class="sxs-lookup"><span data-stu-id="7e0f3-122">To disable compression on a table</span></span>  
  
1.  <span data-ttu-id="7e0f3-123">В обозревателе объектов разверните базу данных, содержащую таблицу, для которой необходимо отключить сжатие, а затем разверните папку **Таблицы** .</span><span class="sxs-lookup"><span data-stu-id="7e0f3-123">In Object Explorer, expand the database that contains the table on which you want to disable compression and then expand the **Tables** folder.</span></span>  
  
2.  <span data-ttu-id="7e0f3-124">Щелкните правой кнопкой мыши эту таблицу или индекс, для которых требуется отключить сжатие, наведите курсор мыши на раздел **Хранилище** и выберите **Управление сжатием...** .</span><span class="sxs-lookup"><span data-stu-id="7e0f3-124">Right-click the table or index on which you want to disable compression, point to **Storage** and select **Manage Compression...**.</span></span>  
  
3.  <span data-ttu-id="7e0f3-125">Чтобы отключить сжатие для индекса, разверните таблицу, содержащую индекс, а затем разверните папку **Индексы** .</span><span class="sxs-lookup"><span data-stu-id="7e0f3-125">To disable compression on an index, expand the table that contains the index and then expand the **Indexes** folder.</span></span>  
  
4.  <span data-ttu-id="7e0f3-126">В мастере сжатия данных на странице **Добро пожаловать в мастер сжатия данных** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-126">In the Data Compression Wizard, on the **Welcome to the Data Compression Wizard** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="7e0f3-127">На странице **Выбор типа сжатия** выберите **Отсутствует** в качестве типа сжатия, который будет применен к каждой секции индекса, для которого требуется отключить сжатие данных.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-127">On the **Select Compression Type** page, select **None** as the compression type to apply to each partition in the index on which you want to disable compression.</span></span> <span data-ttu-id="7e0f3-128">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-128">When finished, click **Next**.</span></span>  
  
     <span data-ttu-id="7e0f3-129">Следующие параметры доступны на странице **Выбор типа сжатия** :</span><span class="sxs-lookup"><span data-stu-id="7e0f3-129">The following options are available on the **Select Compression Type** page:</span></span>  
  
     <span data-ttu-id="7e0f3-130">флажок**Использовать один тип сжатия для всех секций**</span><span class="sxs-lookup"><span data-stu-id="7e0f3-130">**Use the same compression type for all partitions** check box</span></span>  
     <span data-ttu-id="7e0f3-131">Выберите этот вариант, чтобы задать одинаковые параметры для всех секций.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-131">Select to configure the same compression setting for all partitions.</span></span> <span data-ttu-id="7e0f3-132">Он включает флажок выбора и делает недоступным столбец **Тип сжатия** в сетке.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-132">This enables the selection box and disables the **Compression Type** column in the grid.</span></span> <span data-ttu-id="7e0f3-133">При его выборе в списке рядом появляются параметры: **Нет**, **Строка**и **Страница**.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-133">When selected, the options in the adjacent list are **None**, **Row**, and **Page**.</span></span>  
  
     <span data-ttu-id="7e0f3-134">**Номер секции**</span><span class="sxs-lookup"><span data-stu-id="7e0f3-134">**Partition Number**</span></span>  
     <span data-ttu-id="7e0f3-135">Перечисляет каждую секцию в таблице или индексе.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-135">Lists each partition in the table or index.</span></span> <span data-ttu-id="7e0f3-136">Столбец доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-136">This column is read-only.</span></span>  
  
     <span data-ttu-id="7e0f3-137">**Тип сжатия**</span><span class="sxs-lookup"><span data-stu-id="7e0f3-137">**Compression Type**</span></span>  
     <span data-ttu-id="7e0f3-138">Выберите параметры сжатия для каждой секции.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-138">Select the compression option for each partition.</span></span> <span data-ttu-id="7e0f3-139">Вариант недоступен, если выбран параметр **Использовать один и тот же тип сжатия для всех секций** .</span><span class="sxs-lookup"><span data-stu-id="7e0f3-139">Is not available when **Use the same compression type for all partitions** is selected.</span></span> <span data-ttu-id="7e0f3-140">Список параметров: **Нет**, **Строка**и **Страница**.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-140">List options are **None**, **Row**, and **Page**.</span></span>  
  
     <span data-ttu-id="7e0f3-141">**Граница**</span><span class="sxs-lookup"><span data-stu-id="7e0f3-141">**Boundary**</span></span>  
     <span data-ttu-id="7e0f3-142">Отображает границу секции.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-142">Displays the partition boundary.</span></span> <span data-ttu-id="7e0f3-143">Столбец доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-143">This column is read-only.</span></span>  
  
     <span data-ttu-id="7e0f3-144">**Количество строк**</span><span class="sxs-lookup"><span data-stu-id="7e0f3-144">**Row Count**</span></span>  
     <span data-ttu-id="7e0f3-145">Количество строк в данной секции.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-145">Displays the number of rows in this partition.</span></span> <span data-ttu-id="7e0f3-146">Столбец доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-146">This column is read-only.</span></span>  
  
     <span data-ttu-id="7e0f3-147">**Текущий размер**</span><span class="sxs-lookup"><span data-stu-id="7e0f3-147">**Current Space**</span></span>  
     <span data-ttu-id="7e0f3-148">Текущий размер, занимаемый секцией в мегабайтах (МБ).</span><span class="sxs-lookup"><span data-stu-id="7e0f3-148">Displays the current space this partition occupies in megabytes (MB).</span></span> <span data-ttu-id="7e0f3-149">Столбец доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-149">This column is read-only.</span></span>  
  
     <span data-ttu-id="7e0f3-150">**Запрошенное сжатое пространство**</span><span class="sxs-lookup"><span data-stu-id="7e0f3-150">**Requested Compressed Space**</span></span>  
     <span data-ttu-id="7e0f3-151">После нажатия кнопки **Вычислить**в этом столбце будет показан приблизительный размер каждой секции после сжатия на основе значения в столбце **Тип сжатия** .</span><span class="sxs-lookup"><span data-stu-id="7e0f3-151">After you click **Calculate**, this column displays the estimated size of each partition after compression by using the setting specified in the **Compression Type** column.</span></span> <span data-ttu-id="7e0f3-152">Столбец доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-152">This column is read-only.</span></span>  
  
     <span data-ttu-id="7e0f3-153">**Вычислить**</span><span class="sxs-lookup"><span data-stu-id="7e0f3-153">**Calculate**</span></span>  
     <span data-ttu-id="7e0f3-154">Нажмите эту кнопку, чтобы получить размер каждой секции после сжатия на основе значения в столбце **Тип сжатия** .</span><span class="sxs-lookup"><span data-stu-id="7e0f3-154">Click to estimate the size of each partition after compression by using the setting specified in the **Compression Type** column.</span></span>  
  
6.  <span data-ttu-id="7e0f3-155">На странице **Выбор выходного параметра** укажите способ завершения этого задания.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-155">In the **Select an Output Option** page, specify how you want to complete this task.</span></span> <span data-ttu-id="7e0f3-156">Выберите **Создать скрипт** для создания скрипта SQL на основе данных на предыдущих страницах мастера.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-156">Select **Create Script** to create a SQL script based the previous pages in the wizard.</span></span> <span data-ttu-id="7e0f3-157">Выберите **Запустить немедленно** , чтобы создать новую секционированную таблицу после завершения работ со всеми оставшимися страницами мастера.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-157">Select **Run immediately** to create the new partitioned table after completing all remaining pages in the wizard.</span></span> <span data-ttu-id="7e0f3-158">Выберите **Расписание** , чтобы создать новую секционированную таблицу в заранее заданное время в будущем.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-158">Select **Schedule** to create the new partitioned table at a predetermined time in the future.</span></span>  
  
     <span data-ttu-id="7e0f3-159">При выборе **Создать скрипт**в **Параметры скрипта**будут доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="7e0f3-159">If you select **Create script**, the following options are available under **Script options**:</span></span>  
  
     <span data-ttu-id="7e0f3-160">**Вывести скрипт в файл**</span><span class="sxs-lookup"><span data-stu-id="7e0f3-160">**Script to file**</span></span>  
     <span data-ttu-id="7e0f3-161">Создание скрипта как SQL-файла.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-161">Generates the script as a .sql file.</span></span> <span data-ttu-id="7e0f3-162">Введите имя и местоположение файла в поле **Имя файла** или щелкните **Обзор** , чтобы открыть диалоговое окно **Расположение файла скрипта** .</span><span class="sxs-lookup"><span data-stu-id="7e0f3-162">Enter a file name and location in the **File name** box or click **Browse** to open the **Script File Location** dialog box.</span></span> <span data-ttu-id="7e0f3-163">В разделе **Сохранить как**выберите **Текст в Юникоде** или **Текст ANSI**.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-163">From **Save As**, select **Unicode text** or **ANSI text**.</span></span>  
  
     <span data-ttu-id="7e0f3-164">**Вывести скрипт в буфер обмена**</span><span class="sxs-lookup"><span data-stu-id="7e0f3-164">**Script to Clipboard**</span></span>  
     <span data-ttu-id="7e0f3-165">Сохранение скрипта в буфере обмена.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-165">Saves the script to the Clipboard.</span></span>  
  
     <span data-ttu-id="7e0f3-166">**Вывести скрипт в новое окно запроса**</span><span class="sxs-lookup"><span data-stu-id="7e0f3-166">**Script to New Query Window**</span></span>  
     <span data-ttu-id="7e0f3-167">Скрипт создается в новом окне редактора запросов.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-167">Generates the script to a new Query Editor window.</span></span> <span data-ttu-id="7e0f3-168">Это параметр выбирается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-168">This is the default selection.</span></span>  
  
     <span data-ttu-id="7e0f3-169">При выборе **Расписание**щелкните **Изменить расписание**.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-169">If you select **Schedule**, click **Change schedule**.</span></span>  
  
    1.  <span data-ttu-id="7e0f3-170">В диалоговом окне **Создание расписания задания** в поле **Имя** введите имя расписания задания.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-170">In the **New Job Schedule** dialog box, in the **Name** box, enter the job schedule's name.</span></span>  
  
    2.  <span data-ttu-id="7e0f3-171">В списке **Тип расписания** выберите тип расписания:</span><span class="sxs-lookup"><span data-stu-id="7e0f3-171">On the **Schedule type** list, select the type of schedule:</span></span>  
  
        -   <span data-ttu-id="7e0f3-172">**Запускать автоматически при запуске агента SQL Server**</span><span class="sxs-lookup"><span data-stu-id="7e0f3-172">**Start automatically when SQL Server Agent starts**</span></span>  
  
        -   <span data-ttu-id="7e0f3-173">**Запускать при бездействии процессоров**</span><span class="sxs-lookup"><span data-stu-id="7e0f3-173">**Start whenever the CPUs become idle**</span></span>  
  
        -   <span data-ttu-id="7e0f3-174">**Повторяющееся**.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-174">**Recurring**.</span></span> <span data-ttu-id="7e0f3-175">Выберите этот параметр, если новая секционированная таблица регулярно обновляется с учетом новых данных.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-175">Select this option if your new partitioned table updates with new information on a regular basis.</span></span>  
  
        -   <span data-ttu-id="7e0f3-176">**Однократно**.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-176">**One time**.</span></span> <span data-ttu-id="7e0f3-177">Это параметр выбирается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-177">This is the default selection.</span></span>  
  
    3.  <span data-ttu-id="7e0f3-178">Установите или снимите флажок **Включен** , чтобы включить или отключить расписание.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-178">Select or clear the **Enabled** check box to enable or disable the schedule.</span></span>  
  
    4.  <span data-ttu-id="7e0f3-179">При выборе **Повторяющееся**:</span><span class="sxs-lookup"><span data-stu-id="7e0f3-179">If you select **Recurring**:</span></span>  
  
        1.  <span data-ttu-id="7e0f3-180">В разделе **Частота**в списке **Выполняется** укажите частоту выполнения:</span><span class="sxs-lookup"><span data-stu-id="7e0f3-180">Under **Frequency**, on the **Occurs** list, specify the frequency of occurrence:</span></span>  
  
            -   <span data-ttu-id="7e0f3-181">При выборе **Ежедневно**в поле **Выполняется каждые** укажите частоту повторного выполнения расписания задания в днях.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-181">If you select **Daily**, in the **Recurs every** box, enter how often the job schedule repeats in days.</span></span>  
  
            -   <span data-ttu-id="7e0f3-182">При выборе **Еженедельно**в поле **Выполняется каждые** укажите частоту повторного выполнения расписания задания в неделях.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-182">If you select **Weekly**, in the **Recurs every** box, enter how often the job schedule repeats in weeks.</span></span> <span data-ttu-id="7e0f3-183">Выберите день или дни недели, в которые выполняется расписание задания.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-183">Select the day or days of the week on which the job schedule is run.</span></span>  
  
            -   <span data-ttu-id="7e0f3-184">При выборе **Ежемесячно**щелкните **День** или **Определенный**.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-184">If you select **Monthly**, select either **Day** or **The**.</span></span>  
  
                -   <span data-ttu-id="7e0f3-185">При выборе **День**введите дату месяца, в которую должно выполняться расписание задания, и укажите частоту повторного выполнения расписания задания в месяцах.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-185">If you select **Day**, enter both the date of the month you want the job schedule to run and how often the job schedule repeats in months.</span></span> <span data-ttu-id="7e0f3-186">Например, если требуется, чтобы расписание задания выполнялось 15 числа каждого второго месяца, выберите **День** и введите в первом поле 15 и 2 — во втором поле.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-186">For example, if you want the job schedule to run on the 15th day of the month every other month, select **Day** and enter "15" in the first box and "2" in the second box.</span></span> <span data-ttu-id="7e0f3-187">Обратите внимание, что число, введенное во втором поле, не должно превышать 99.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-187">Please note that the largest number allowed in the second box is "99".</span></span>  
  
                -   <span data-ttu-id="7e0f3-188">При выборе **Определенный**выберите определенный день недели в месяце, в котором должно выполняться расписание задания, и укажите частоту повторного выполнения расписания задания в месяцах.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-188">If you select **The**, select the specific day of the week within the month that you want the job schedule to run and how often the job schedule repeats in months.</span></span> <span data-ttu-id="7e0f3-189">Например, если требуется, чтобы расписание задания выполнялось в последний день недели каждого второго месяца, выберите **День**, затем **последний** в первом списке и **рабочий день** во втором списке, а потом введите "2" во втором поле.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-189">For example, if you want the job schedule to run on the last weekday of the month every other month, select **Day**, select **last** from the first list and **weekday** from the second list, and then enter "2" in the last box.</span></span> <span data-ttu-id="7e0f3-190">Также можно выбрать **первый**, **второй**, **третий** или **четвертый**, а также конкретные дни недели (например: воскресенье или среду) в первых двух списках.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-190">You can also select **first**, **second**, **third**, or **fourth**, as well as specific weekdays (for example: Sunday or Wednesday) from the first two lists.</span></span> <span data-ttu-id="7e0f3-191">Обратите внимание, что число, введенное в последнем поле, не должно превышать 99.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-191">Please note that the largest number allowed in the last box is "99".</span></span>  
  
        2.  <span data-ttu-id="7e0f3-192">В поле **Сколько раз в день**укажите частоту повторного выполнения расписания задания в день запуска расписания задания:</span><span class="sxs-lookup"><span data-stu-id="7e0f3-192">Under **Daily frequency**, specify how often the job schedule repeats on the day the job schedule runs:</span></span>  
  
            -   <span data-ttu-id="7e0f3-193">При выборе **Выполнять раз в**укажите определенное время дня для запуска расписания задания в поле **Выполнять раз в** .</span><span class="sxs-lookup"><span data-stu-id="7e0f3-193">If you select **Occurs once at**, enter the specific time of day when the job schedule should run in the **Occurs once at** box.</span></span> <span data-ttu-id="7e0f3-194">Укажите время дня: час, минуту и секунду.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-194">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
            -   <span data-ttu-id="7e0f3-195">При выборе **Выполняется каждые**укажите частоту выполнения задания в выбранный день в поле **Частота**.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-195">If you select **Occurs every**, specify how often the job schedule runs during the day chosen under **Frequency**.</span></span> <span data-ttu-id="7e0f3-196">Например, если требуется, чтобы расписание задания выполнялось каждые 2 часа в день запуска расписания задания, выберите **Выполняется кажд.** , введите "2" в первом поле, а затем выберите в списке **часы**.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-196">For example, if you want the job schedule to repeat every 2 hours during the day that the job schedule is run, select **Occurs every**, enter "2" in the first box, and then select **hour(s)** from the list.</span></span> <span data-ttu-id="7e0f3-197">В этом списке также можно выбрать **минуты** и **секунды**.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-197">From this list you can also select **minute(s)** and **second(s)**.</span></span> <span data-ttu-id="7e0f3-198">Обратите внимание, что число, введенное в первом поле, не должно превышать 100.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-198">Please note that the largest number allowed in the first box is "100".</span></span>  
  
                 <span data-ttu-id="7e0f3-199">В поле **Начинать в** введите время для начала запуска расписания задания.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-199">In the **Starting at** box, enter the time that the job schedule should start running.</span></span> <span data-ttu-id="7e0f3-200">В поле **Заканчивать в** введите время для завершения повторного выполнения расписания задания.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-200">In the **Ending at** box, enter the time that the job schedule should stop repeating.</span></span> <span data-ttu-id="7e0f3-201">Укажите время дня: час, минуту и секунду.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-201">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
        3.  <span data-ttu-id="7e0f3-202">В разделе **Длительность**, в области **Дата начала**введите дату начала запуска расписания задания.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-202">Under **Duration**, in **Start date**, enter the date that you want the job schedule to start running.</span></span> <span data-ttu-id="7e0f3-203">Выберите **Дата окончания** или **Без даты окончания** , чтобы указать дату завершения выполнения расписания задания.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-203">Select **End date** or **No end date** to indicate when the job schedule should stop running.</span></span> <span data-ttu-id="7e0f3-204">При выборе **Дата окончания**введите дату завершения запуска расписания задания.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-204">If you select **End date**, enter the date that you want to job schedule to stop running.</span></span>  
  
    5.  <span data-ttu-id="7e0f3-205">При выборе значения **Однократно**в **Однократное выполнение**в поле **Дата** введите дату запуска расписания задания.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-205">If you select **One Time**, under **One-time occurrence**, in the **Date** box, enter the date that the job schedule will be run.</span></span> <span data-ttu-id="7e0f3-206">В поле **Время** введите время запуска расписания задания.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-206">In the **Time** box, enter the time that the job schedule will be run.</span></span> <span data-ttu-id="7e0f3-207">Укажите время дня: час, минуту и секунду.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-207">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
    6.  <span data-ttu-id="7e0f3-208">В разделе **Сводка**в **Описание**проверьте правильность всех параметров расписания задания.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-208">Under **Summary**, in **Description**, verify that all job schedule settings are correct.</span></span>  
  
    7.  <span data-ttu-id="7e0f3-209">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-209">Click **OK**.</span></span>  
  
     <span data-ttu-id="7e0f3-210">После завершения работы с этой страницей нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-210">After completing this page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="7e0f3-211">На странице **Просмотр сводки** в разделе **Просмотр выбранных параметров**разверните все доступные параметры, чтобы убедиться в правильности всех настроек.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-211">On the **Review Summary** page, under **Review your selections**, expand all available options to verify that all settings are correct.</span></span> <span data-ttu-id="7e0f3-212">Если все настройки правильные, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-212">If everything is as expected, click **Finish**.</span></span>  
  
8.  <span data-ttu-id="7e0f3-213">Страница **Выполнение мастера сжатия** используется для мониторинга сведений о состоянии действий мастера создания секций.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-213">On the **Compression Wizard Progress** page, monitor status information about the actions of the Create Partition Wizard.</span></span> <span data-ttu-id="7e0f3-214">В зависимости от действий, выбранных в мастере, страница выполнения может содержать одно или несколько действий.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-214">Depending on the options that you selected in the wizard, the progress page might contain one or more actions.</span></span> <span data-ttu-id="7e0f3-215">В верхнем поле показано общее состояние мастера и число полученных им сообщений о состоянии, предупреждений и сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-215">The top box displays the overall status of the wizard and the number of status, error, and warning messages that the wizard has received.</span></span>  
  
     <span data-ttu-id="7e0f3-216">На странице **Выполнение мастера сжатия** доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-216">The following options are available on the **Compression Wizard Progress** page:</span></span>  
  
     <span data-ttu-id="7e0f3-217">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="7e0f3-217">**Details**</span></span>  
     <span data-ttu-id="7e0f3-218">Сведения о событии, состоянии и любых сообщениях, которые возвращены в результате действий мастера.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-218">Provides the action, status, and any messages that are returned from action taken by the wizard.</span></span>  
  
     <span data-ttu-id="7e0f3-219">**Действие**</span><span class="sxs-lookup"><span data-stu-id="7e0f3-219">**Action**</span></span>  
     <span data-ttu-id="7e0f3-220">Задает тип и имя каждого действия.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-220">Specifies the type and name of each action.</span></span>  
  
     <span data-ttu-id="7e0f3-221">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="7e0f3-221">**Status**</span></span>  
     <span data-ttu-id="7e0f3-222">Указывает, вернуло ли действие мастера в целом значение **Успешно** или **Ошибка**.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-222">Indicates whether the wizard action as a whole returned the value of **Success** or **Failure**.</span></span>  
  
     <span data-ttu-id="7e0f3-223">**Сообщение**</span><span class="sxs-lookup"><span data-stu-id="7e0f3-223">**Message**</span></span>  
     <span data-ttu-id="7e0f3-224">Любые сообщения об ошибках или предупреждения от процесса.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-224">Provides any error or warning messages that are returned from the process.</span></span>  
  
     <span data-ttu-id="7e0f3-225">**Отчет**</span><span class="sxs-lookup"><span data-stu-id="7e0f3-225">**Report**</span></span>  
     <span data-ttu-id="7e0f3-226">Создание отчета, содержащего результаты мастера создания секций.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-226">Creates a report that contains the results of the Create Partition Wizard.</span></span> <span data-ttu-id="7e0f3-227">Доступные параметры: **Просмотреть отчет**, **Сохранить отчет в файл**, **Копировать отчет в буфер обмена**и **Отправить отчет по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-227">The options are **View Report**, **Save Report to File**, **Copy Report to Clipboard**, and **Send Report as Email**.</span></span>  
  
     <span data-ttu-id="7e0f3-228">**Просмотреть отчет**</span><span class="sxs-lookup"><span data-stu-id="7e0f3-228">**View Report**</span></span>  
     <span data-ttu-id="7e0f3-229">Открытие диалогового окна **Просмотр отчета** , которое содержит текстовый отчет о работе мастера создания секций.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-229">Opens the **View Report** dialog box, which contains a text report of the progress of the Create Partition Wizard.</span></span>  
  
     <span data-ttu-id="7e0f3-230">**Сохранить отчет в файл**</span><span class="sxs-lookup"><span data-stu-id="7e0f3-230">**Save Report to File**</span></span>  
     <span data-ttu-id="7e0f3-231">Открытие диалогового окна **Сохранить отчет как** .</span><span class="sxs-lookup"><span data-stu-id="7e0f3-231">Opens the **Save Report As** dialog box.</span></span>  
  
     <span data-ttu-id="7e0f3-232">**Копировать отчет в буфер обмена**</span><span class="sxs-lookup"><span data-stu-id="7e0f3-232">**Copy Report to Clipboard**</span></span>  
     <span data-ttu-id="7e0f3-233">Копирование результатов отчета о работе мастера в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-233">Copies the results of the wizard's progress report to the Clipboard.</span></span>  
  
     <span data-ttu-id="7e0f3-234">**Отправить отчет по электронной почте**</span><span class="sxs-lookup"><span data-stu-id="7e0f3-234">**Send Report as Email**</span></span>  
     <span data-ttu-id="7e0f3-235">Копирование результатов отчета о состоянии мастера в сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-235">Copies the results of the wizard's progress report into an email message.</span></span>  
  
     <span data-ttu-id="7e0f3-236">Завершив выбор параметров, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-236">When complete, click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7e0f3-237">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7e0f3-237">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-compression-on-a-table"></a><span data-ttu-id="7e0f3-238">Отключение сжатия в таблице</span><span class="sxs-lookup"><span data-stu-id="7e0f3-238">To disable compression on a table</span></span>  
  
1.  <span data-ttu-id="7e0f3-239">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7e0f3-239">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7e0f3-240">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-240">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7e0f3-241">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-241">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE Person.Person REBUILD PARTITION = ALL  
    WITH (DATA_COMPRESSION = NONE);  
    GO  
    ```  
  
#### <a name="to-disable-compression-on-an-index"></a><span data-ttu-id="7e0f3-242">Отключение сжатия для индекса</span><span class="sxs-lookup"><span data-stu-id="7e0f3-242">To disable compression on an index</span></span>  
  
1.  <span data-ttu-id="7e0f3-243">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7e0f3-243">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7e0f3-244">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-244">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7e0f3-245">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="7e0f3-245">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER INDEX AK_Person_rowguid ON Person.Person REBUILD PARTITION = ALL WITH (DATA_COMPRESSION = NONE);  
    GO  
    ```  
  
 <span data-ttu-id="7e0f3-246">Дополнительные сведения см. в разделах [ALTER TABLE (Transact-SQL)](/sql/t-sql/statements/alter-table-transact-sql) и [ALTER INDEX (Transact-SQL)](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7e0f3-246">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) and [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
  
