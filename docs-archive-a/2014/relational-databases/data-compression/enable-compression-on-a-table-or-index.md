---
title: Включение сжатия таблицы или индекса | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.compwiz.selectaction.f1
- sql12.swb.compwiz.welcome.f1
- sql12.swb.compwiz.scriptfileoption.f1
- sql12.swb.compwiz.createjob.f1
- sql12.swb.compwiz.progress.f1
- sql12.swb.compwiz.outputoptions.f1
- sql12.swb.compwiz.compressiontype.f1
- sql12.swb.compwiz.summary.f1
helpviewer_keywords:
- data compression wizard
- compression [SQL Server], enable
ms.assetid: b7442cff-e616-475a-9c5a-5a765089e5f2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8a51c3b5e0c4e9b5624911310ce20db5a8e060a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667221"
---
# <a name="enable-compression-on-a-table-or-index"></a><span data-ttu-id="8b5b4-102">Включение сжатия таблицы или индекса</span><span class="sxs-lookup"><span data-stu-id="8b5b4-102">Enable Compression on a Table or Index</span></span>
  <span data-ttu-id="8b5b4-103">В этом разделе описано включение таблицы или индекса в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8b5b4-103">This topic describes how to enable compression on a table or index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="8b5b4-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="8b5b4-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8b5b4-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="8b5b4-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8b5b4-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="8b5b4-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="8b5b4-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="8b5b4-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8b5b4-108">**Чтобы включить сжатие таблицы или индекса с использованием:**</span><span class="sxs-lookup"><span data-stu-id="8b5b4-108">**To enable compression on a table or index, using:**</span></span>  
  
     [<span data-ttu-id="8b5b4-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8b5b4-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8b5b4-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8b5b4-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8b5b4-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="8b5b4-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="8b5b4-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="8b5b4-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="8b5b4-113">В системных таблицах не может быть включено сжатие.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-113">System tables cannot be enabled for compression.</span></span>  
  
-   <span data-ttu-id="8b5b4-114">Если таблица является кучей, то операция перестроения в режиме ONLINE будет однопотоковой.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-114">If the table is a heap, the rebuild operation for ONLINE mode will be single threaded.</span></span> <span data-ttu-id="8b5b4-115">Используйте режим OFFLINE для выполнения многопотоковых операций перестроения кучи.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-115">Use OFFLINE mode for a multi-threaded heap rebuild operation.</span></span> <span data-ttu-id="8b5b4-116">Дополнительную информацию о сжатии данных см. в разделе [Сжатие данных](data-compression.md).</span><span class="sxs-lookup"><span data-stu-id="8b5b4-116">For a more information about data compression, see [Data Compression](data-compression.md).</span></span>  
  
-   <span data-ttu-id="8b5b4-117">Если у таблицы есть невыровненные индексы, изменить настройку сжатия отдельной секции невозможно.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-117">You cannot change the compression setting of a single partition if the table has nonaligned indexes.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8b5b4-118">безопасность</span><span class="sxs-lookup"><span data-stu-id="8b5b4-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8b5b4-119">Permissions</span><span class="sxs-lookup"><span data-stu-id="8b5b4-119">Permissions</span></span>  
 <span data-ttu-id="8b5b4-120">Необходимо разрешение ALTER на таблицу или индекс.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-120">Requires ALTER permission on the table or index.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8b5b4-121">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8b5b4-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-enable-compression-on-a-table-or-index"></a><span data-ttu-id="8b5b4-122">Чтобы включить сжатие таблицы или индекса:</span><span class="sxs-lookup"><span data-stu-id="8b5b4-122">To enable compression on a table or index</span></span>  
  
1.  <span data-ttu-id="8b5b4-123">В обозревателе объектов разверните базу данных, в которой содержится таблица, подлежащая сжатию, а затем разверните папку **Таблицы** .</span><span class="sxs-lookup"><span data-stu-id="8b5b4-123">In Object Explorer, expand the database that contains the table that you want to compress and then expand the **Tables** folder.</span></span>  
  
2.  <span data-ttu-id="8b5b4-124">Чтобы сжать индекс, разверните таблицу, содержащую нужный индекс, затем разверните папку **Индексы** .</span><span class="sxs-lookup"><span data-stu-id="8b5b4-124">To compress an index, expand the table that contains the index that you want to compress and then expand the **Indexes** folder.</span></span>  
  
3.  <span data-ttu-id="8b5b4-125">Щелкните правой кнопкой мыши таблицу или индекс для сжатия, выберите **хранение**, а затем **Управление сжатием...**</span><span class="sxs-lookup"><span data-stu-id="8b5b4-125">Right-click the table or index to compress, point to **Storage** and select **Manage Compression...**.</span></span>  
  
4.  <span data-ttu-id="8b5b4-126">В мастере сжатия данных на странице **Добро пожаловать в мастер сжатия данных** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-126">In the Data Compression Wizard, on the **Welcome to the Data Compression Wizard** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="8b5b4-127">На странице **Выбор типа сжатия** выберите тип сжатия, который будет применен к каждой выбранной секции таблицы или индекса.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-127">On the **Select Compression Type** page, select the compression type to apply to each partition in the table or index you want to compress.</span></span> <span data-ttu-id="8b5b4-128">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-128">When finished, click **Next**.</span></span>  
  
     <span data-ttu-id="8b5b4-129">Следующие параметры доступны на странице **Выбор типа сжатия** :</span><span class="sxs-lookup"><span data-stu-id="8b5b4-129">The following options are available on the **Select Compression Type** page:</span></span>  
  
     <span data-ttu-id="8b5b4-130">флажок**Использовать один тип сжатия для всех секций**</span><span class="sxs-lookup"><span data-stu-id="8b5b4-130">**Use the same compression type for all partitions** check box</span></span>  
     <span data-ttu-id="8b5b4-131">Выберите этот вариант, чтобы задать одинаковые параметры для всех секций.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-131">Select to configure the same compression setting for all partitions.</span></span> <span data-ttu-id="8b5b4-132">Он включает флажок выбора и делает недоступным столбец **Тип сжатия** в сетке.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-132">This enables the selection box and disables the **Compression Type** column in the grid.</span></span> <span data-ttu-id="8b5b4-133">При его выборе в списке рядом появляются параметры: **Нет**, **Строка**и **Страница**.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-133">When selected, the options in the adjacent list are **None**, **Row**, and **Page**.</span></span>  
  
     <span data-ttu-id="8b5b4-134">**Номер секции**</span><span class="sxs-lookup"><span data-stu-id="8b5b4-134">**Partition Number**</span></span>  
     <span data-ttu-id="8b5b4-135">Перечисляет каждую секцию в таблице или индексе.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-135">Lists each partition in the table or index.</span></span> <span data-ttu-id="8b5b4-136">Столбец доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-136">This column is read-only.</span></span>  
  
     <span data-ttu-id="8b5b4-137">**Тип сжатия**</span><span class="sxs-lookup"><span data-stu-id="8b5b4-137">**Compression Type**</span></span>  
     <span data-ttu-id="8b5b4-138">Выберите параметры сжатия для каждой секции.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-138">Select the compression option for each partition.</span></span> <span data-ttu-id="8b5b4-139">Вариант недоступен, если выбран параметр **Использовать один и тот же тип сжатия для всех секций** .</span><span class="sxs-lookup"><span data-stu-id="8b5b4-139">Is not available when **Use the same compression type for all partitions** is selected.</span></span> <span data-ttu-id="8b5b4-140">Список параметров: **Нет**, **Строка**и **Страница**.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-140">List options are **None**, **Row**, and **Page**.</span></span>  
  
     <span data-ttu-id="8b5b4-141">**Граница**</span><span class="sxs-lookup"><span data-stu-id="8b5b4-141">**Boundary**</span></span>  
     <span data-ttu-id="8b5b4-142">Отображает границу секции.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-142">Displays the partition boundary.</span></span> <span data-ttu-id="8b5b4-143">Столбец доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-143">This column is read-only.</span></span>  
  
     <span data-ttu-id="8b5b4-144">**Количество строк**</span><span class="sxs-lookup"><span data-stu-id="8b5b4-144">**Row Count**</span></span>  
     <span data-ttu-id="8b5b4-145">Количество строк в данной секции.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-145">Displays the number of rows in this partition.</span></span> <span data-ttu-id="8b5b4-146">Столбец доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-146">This column is read-only.</span></span>  
  
     <span data-ttu-id="8b5b4-147">**Текущий размер**</span><span class="sxs-lookup"><span data-stu-id="8b5b4-147">**Current Space**</span></span>  
     <span data-ttu-id="8b5b4-148">Текущий размер, занимаемый секцией в мегабайтах (МБ).</span><span class="sxs-lookup"><span data-stu-id="8b5b4-148">Displays the current space this partition occupies in megabytes (MB).</span></span> <span data-ttu-id="8b5b4-149">Столбец доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-149">This column is read-only.</span></span>  
  
     <span data-ttu-id="8b5b4-150">**Запрошенное сжатое пространство**</span><span class="sxs-lookup"><span data-stu-id="8b5b4-150">**Requested Compressed Space**</span></span>  
     <span data-ttu-id="8b5b4-151">После нажатия кнопки **Вычислить**в этом столбце будет показан приблизительный размер каждой секции после сжатия на основе значения в столбце **Тип сжатия** .</span><span class="sxs-lookup"><span data-stu-id="8b5b4-151">After you click **Calculate**, this column displays the estimated size of each partition after compression by using the setting specified in the **Compression Type** column.</span></span> <span data-ttu-id="8b5b4-152">Столбец доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-152">This column is read-only.</span></span>  
  
     <span data-ttu-id="8b5b4-153">**Вычислить**</span><span class="sxs-lookup"><span data-stu-id="8b5b4-153">**Calculate**</span></span>  
     <span data-ttu-id="8b5b4-154">Нажмите эту кнопку, чтобы получить размер каждой секции после сжатия на основе значения в столбце **Тип сжатия** .</span><span class="sxs-lookup"><span data-stu-id="8b5b4-154">Click to estimate the size of each partition after compression by using the setting specified in the **Compression Type** column.</span></span>  
  
6.  <span data-ttu-id="8b5b4-155">На странице **Выбор выходного параметра** укажите способ завершения сжатия.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-155">In the **Select an Output Option** page, specify how you want to complete your compression.</span></span> <span data-ttu-id="8b5b4-156">Выберите **Создать скрипт** для создания скрипта SQL на основе данных на предыдущих страницах мастера.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-156">Select **Create Script** to create a SQL script based the previous pages in the wizard.</span></span> <span data-ttu-id="8b5b4-157">Выберите **Запустить немедленно** , чтобы создать новую секционированную таблицу после завершения работ со всеми оставшимися страницами мастера.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-157">Select **Run immediately** to create the new partitioned table after completing all remaining pages in the wizard.</span></span> <span data-ttu-id="8b5b4-158">Выберите **Расписание** , чтобы создать новую секционированную таблицу в заранее заданное время в будущем.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-158">Select **Schedule** to create the new partitioned table at a predetermined time in the future.</span></span>  
  
     <span data-ttu-id="8b5b4-159">При выборе **Создать скрипт**в **Параметры скрипта**будут доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="8b5b4-159">If you select **Create script**, the following options are available under **Script options**:</span></span>  
  
     <span data-ttu-id="8b5b4-160">**Вывести скрипт в файл**</span><span class="sxs-lookup"><span data-stu-id="8b5b4-160">**Script to file**</span></span>  
     <span data-ttu-id="8b5b4-161">Создание скрипта как SQL-файла.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-161">Generates the script as a .sql file.</span></span> <span data-ttu-id="8b5b4-162">Введите имя и местоположение файла в поле **Имя файла** или щелкните **Обзор** , чтобы открыть диалоговое окно **Расположение файла скрипта** .</span><span class="sxs-lookup"><span data-stu-id="8b5b4-162">Enter a file name and location in the **File name** box or click **Browse** to open the **Script File Location** dialog box.</span></span> <span data-ttu-id="8b5b4-163">В разделе **Сохранить как**выберите **Текст в Юникоде** или **Текст ANSI**.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-163">From **Save As**, select **Unicode text** or **ANSI text**.</span></span>  
  
     <span data-ttu-id="8b5b4-164">**Вывести скрипт в буфер обмена**</span><span class="sxs-lookup"><span data-stu-id="8b5b4-164">**Script to Clipboard**</span></span>  
     <span data-ttu-id="8b5b4-165">Сохранение скрипта в буфере обмена.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-165">Saves the script to the Clipboard.</span></span>  
  
     <span data-ttu-id="8b5b4-166">**Вывести скрипт в новое окно запроса**</span><span class="sxs-lookup"><span data-stu-id="8b5b4-166">**Script to New Query Window**</span></span>  
     <span data-ttu-id="8b5b4-167">Скрипт создается в новом окне редактора запросов.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-167">Generates the script to a new Query Editor window.</span></span> <span data-ttu-id="8b5b4-168">Это параметр выбирается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-168">This is the default selection.</span></span>  
  
     <span data-ttu-id="8b5b4-169">При выборе **Расписание**щелкните **Изменить расписание**.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-169">If you select **Schedule**, click **Change schedule**.</span></span>  
  
    1.  <span data-ttu-id="8b5b4-170">В диалоговом окне **Создание расписания задания** в поле **Имя** введите имя расписания задания.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-170">In the **New Job Schedule** dialog box, in the **Name** box, enter the job schedule's name.</span></span>  
  
    2.  <span data-ttu-id="8b5b4-171">В списке **Тип расписания** выберите тип расписания:</span><span class="sxs-lookup"><span data-stu-id="8b5b4-171">On the **Schedule type** list, select the type of schedule:</span></span>  
  
        -   <span data-ttu-id="8b5b4-172">**Запускать автоматически при запуске агента SQL Server**</span><span class="sxs-lookup"><span data-stu-id="8b5b4-172">**Start automatically when SQL Server Agent starts**</span></span>  
  
        -   <span data-ttu-id="8b5b4-173">**Запускать при бездействии процессоров**</span><span class="sxs-lookup"><span data-stu-id="8b5b4-173">**Start whenever the CPUs become idle**</span></span>  
  
        -   <span data-ttu-id="8b5b4-174">**Повторяющееся**.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-174">**Recurring**.</span></span> <span data-ttu-id="8b5b4-175">Выберите этот параметр, если новая секционированная таблица регулярно обновляется с учетом новых данных.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-175">Select this option if your new partitioned table updates with new information on a regular basis.</span></span>  
  
        -   <span data-ttu-id="8b5b4-176">**Однократно**.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-176">**One time**.</span></span> <span data-ttu-id="8b5b4-177">Это параметр выбирается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-177">This is the default selection.</span></span>  
  
    3.  <span data-ttu-id="8b5b4-178">Установите или снимите флажок **Включен** , чтобы включить или отключить расписание.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-178">Select or clear the **Enabled** check box to enable or disable the schedule.</span></span>  
  
    4.  <span data-ttu-id="8b5b4-179">При выборе **Повторяющееся**:</span><span class="sxs-lookup"><span data-stu-id="8b5b4-179">If you select **Recurring**:</span></span>  
  
        1.  <span data-ttu-id="8b5b4-180">В разделе **Частота**в списке **Выполняется** укажите частоту выполнения:</span><span class="sxs-lookup"><span data-stu-id="8b5b4-180">Under **Frequency**, on the **Occurs** list, specify the frequency of occurrence:</span></span>  
  
            -   <span data-ttu-id="8b5b4-181">При выборе **Ежедневно**в поле **Выполняется каждые** укажите частоту повторного выполнения расписания задания в днях.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-181">If you select **Daily**, in the **Recurs every** box, enter how often the job schedule repeats in days.</span></span>  
  
            -   <span data-ttu-id="8b5b4-182">При выборе **Еженедельно**в поле **Выполняется каждые** укажите частоту повторного выполнения расписания задания в неделях.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-182">If you select **Weekly**, in the **Recurs every** box, enter how often the job schedule repeats in weeks.</span></span> <span data-ttu-id="8b5b4-183">Выберите день или дни недели, в которые выполняется расписание задания.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-183">Select the day or days of the week on which the job schedule is run.</span></span>  
  
            -   <span data-ttu-id="8b5b4-184">При выборе **Ежемесячно**щелкните **День** или **Определенный**.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-184">If you select **Monthly**, select either **Day** or **The**.</span></span>  
  
                -   <span data-ttu-id="8b5b4-185">При выборе **День**введите дату месяца, в которую должно выполняться расписание задания, и укажите частоту повторного выполнения расписания задания в месяцах.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-185">If you select **Day**, enter both the date of the month you want the job schedule to run and how often the job schedule repeats in months.</span></span> <span data-ttu-id="8b5b4-186">Например, если требуется, чтобы расписание задания выполнялось 15 числа каждого второго месяца, выберите **День** и введите в первом поле 15 и 2 — во втором поле.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-186">For example, if you want the job schedule to run on the 15th day of the month every other month, select **Day** and enter "15" in the first box and "2" in the second box.</span></span> <span data-ttu-id="8b5b4-187">Обратите внимание, что число, введенное во втором поле, не должно превышать 99.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-187">Please note that the largest number allowed in the second box is "99".</span></span>  
  
                -   <span data-ttu-id="8b5b4-188">При выборе **Определенный**выберите определенный день недели в месяце, в котором должно выполняться расписание задания, и укажите частоту повторного выполнения расписания задания в месяцах.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-188">If you select **The**, select the specific day of the week within the month that you want the job schedule to run and how often the job schedule repeats in months.</span></span> <span data-ttu-id="8b5b4-189">Например, если требуется, чтобы расписание задания выполнялось в последний день недели каждого второго месяца, выберите **День**, затем **последний** в первом списке и **рабочий день** во втором списке, а потом введите "2" во втором поле.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-189">For example, if you want the job schedule to run on the last weekday of the month every other month, select **Day**, select **last** from the first list and **weekday** from the second list, and then enter "2" in the last box.</span></span> <span data-ttu-id="8b5b4-190">Также можно выбрать **первый**, **второй**, **третий** или **четвертый**, а также конкретные дни недели (например: воскресенье или среду) в первых двух списках.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-190">You can also select **first**, **second**, **third**, or **fourth**, as well as specific weekdays (for example: Sunday or Wednesday) from the first two lists.</span></span> <span data-ttu-id="8b5b4-191">Обратите внимание, что число, введенное в последнем поле, не должно превышать 99.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-191">Please note that the largest number allowed in the last box is "99".</span></span>  
  
        2.  <span data-ttu-id="8b5b4-192">В поле **Сколько раз в день**укажите частоту повторного выполнения расписания задания в день запуска расписания задания:</span><span class="sxs-lookup"><span data-stu-id="8b5b4-192">Under **Daily frequency**, specify how often the job schedule repeats on the day the job schedule runs:</span></span>  
  
            -   <span data-ttu-id="8b5b4-193">При выборе **Выполнять раз в**укажите определенное время дня для запуска расписания задания в поле **Выполнять раз в** .</span><span class="sxs-lookup"><span data-stu-id="8b5b4-193">If you select **Occurs once at**, enter the specific time of day when the job schedule should run in the **Occurs once at** box.</span></span> <span data-ttu-id="8b5b4-194">Укажите время дня: час, минуту и секунду.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-194">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
            -   <span data-ttu-id="8b5b4-195">При выборе **Выполняется каждые**укажите частоту выполнения задания в выбранный день в поле **Частота**.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-195">If you select **Occurs every**, specify how often the job schedule runs during the day chosen under **Frequency**.</span></span> <span data-ttu-id="8b5b4-196">Например, если требуется, чтобы расписание задания выполнялось каждые 2 часа в день запуска расписания задания, выберите **Выполняется кажд.** , введите "2" в первом поле, а затем выберите в списке **часы**.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-196">For example, if you want the job schedule to repeat every 2 hours during the day that the job schedule is run, select **Occurs every**, enter "2" in the first box, and then select **hour(s)** from the list.</span></span> <span data-ttu-id="8b5b4-197">В этом списке также можно выбрать **минуты** и **секунды**.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-197">From this list you can also select **minute(s)** and **second(s)**.</span></span> <span data-ttu-id="8b5b4-198">Обратите внимание, что число, введенное в первом поле, не должно превышать 100.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-198">Please note that the largest number allowed in the first box is "100".</span></span>  
  
                 <span data-ttu-id="8b5b4-199">В поле **Начинать в** введите время для начала запуска расписания задания.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-199">In the **Starting at** box, enter the time that the job schedule should start running.</span></span> <span data-ttu-id="8b5b4-200">В поле **Заканчивать в** введите время для завершения повторного выполнения расписания задания.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-200">In the **Ending at** box, enter the time that the job schedule should stop repeating.</span></span> <span data-ttu-id="8b5b4-201">Укажите время дня: час, минуту и секунду.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-201">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
        3.  <span data-ttu-id="8b5b4-202">В разделе **Длительность**, в области **Дата начала**введите дату начала запуска расписания задания.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-202">Under **Duration**, in **Start date**, enter the date that you want the job schedule to start running.</span></span> <span data-ttu-id="8b5b4-203">Выберите **Дата окончания** или **Без даты окончания** , чтобы указать дату завершения выполнения расписания задания.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-203">Select **End date** or **No end date** to indicate when the job schedule should stop running.</span></span> <span data-ttu-id="8b5b4-204">При выборе **Дата окончания**введите дату завершения запуска расписания задания.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-204">If you select **End date**, enter the date that you want to job schedule to stop running.</span></span>  
  
    5.  <span data-ttu-id="8b5b4-205">При выборе значения **Однократно**в **Однократное выполнение**в поле **Дата** введите дату запуска расписания задания.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-205">If you select **One Time**, under **One-time occurrence**, in the **Date** box, enter the date that the job schedule will be run.</span></span> <span data-ttu-id="8b5b4-206">В поле **Время** введите время запуска расписания задания.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-206">In the **Time** box, enter the time that the job schedule will be run.</span></span> <span data-ttu-id="8b5b4-207">Укажите время дня: час, минуту и секунду.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-207">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
    6.  <span data-ttu-id="8b5b4-208">В разделе **Сводка**в **Описание**проверьте правильность всех параметров расписания задания.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-208">Under **Summary**, in **Description**, verify that all job schedule settings are correct.</span></span>  
  
    7.  <span data-ttu-id="8b5b4-209">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-209">Click **OK**.</span></span>  
  
     <span data-ttu-id="8b5b4-210">После завершения работы с этой страницей нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-210">After completing this page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="8b5b4-211">На странице **Просмотр сводки** в разделе **Просмотр выбранных параметров**разверните все доступные параметры, чтобы проверить правильность всех настроек сжатия.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-211">On the **Review Summary** page, under **Review your selections**, expand all available options to verify that all compression settings are correct.</span></span> <span data-ttu-id="8b5b4-212">Если все настройки правильные, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-212">If everything is as expected, click **Finish**.</span></span>  
  
8.  <span data-ttu-id="8b5b4-213">Страница **Выполнение мастера сжатия** используется для мониторинга сведений о состоянии действий мастера создания секций.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-213">On the **Compression Wizard Progress** page, monitor status information about the actions of the Create Partition Wizard.</span></span> <span data-ttu-id="8b5b4-214">В зависимости от действий, выбранных в мастере, страница выполнения может содержать одно или несколько действий.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-214">Depending on the options that you selected in the wizard, the progress page might contain one or more actions.</span></span> <span data-ttu-id="8b5b4-215">В верхнем поле показано общее состояние мастера и число полученных им сообщений о состоянии, предупреждений и сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-215">The top box displays the overall status of the wizard and the number of status, error, and warning messages that the wizard has received.</span></span>  
  
     <span data-ttu-id="8b5b4-216">На странице **Выполнение мастера сжатия** доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-216">The following options are available on the **Compression Wizard Progress** page:</span></span>  
  
     <span data-ttu-id="8b5b4-217">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="8b5b4-217">**Details**</span></span>  
     <span data-ttu-id="8b5b4-218">Сведения о событии, состоянии и любых сообщениях, которые возвращены в результате действий мастера.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-218">Provides the action, status, and any messages that are returned from action taken by the wizard.</span></span>  
  
     <span data-ttu-id="8b5b4-219">**Действие**</span><span class="sxs-lookup"><span data-stu-id="8b5b4-219">**Action**</span></span>  
     <span data-ttu-id="8b5b4-220">Задает тип и имя каждого действия.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-220">Specifies the type and name of each action.</span></span>  
  
     <span data-ttu-id="8b5b4-221">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="8b5b4-221">**Status**</span></span>  
     <span data-ttu-id="8b5b4-222">Указывает, вернуло ли действие мастера в целом значение **Успешно** или **Ошибка**.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-222">Indicates whether the wizard action as a whole returned the value of **Success** or **Failure**.</span></span>  
  
     <span data-ttu-id="8b5b4-223">**Сообщение**</span><span class="sxs-lookup"><span data-stu-id="8b5b4-223">**Message**</span></span>  
     <span data-ttu-id="8b5b4-224">Любые сообщения об ошибках или предупреждения от процесса.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-224">Provides any error or warning messages that are returned from the process.</span></span>  
  
     <span data-ttu-id="8b5b4-225">**Отчет**</span><span class="sxs-lookup"><span data-stu-id="8b5b4-225">**Report**</span></span>  
     <span data-ttu-id="8b5b4-226">Создание отчета, содержащего результаты мастера создания секций.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-226">Creates a report that contains the results of the Create Partition Wizard.</span></span> <span data-ttu-id="8b5b4-227">Доступные параметры: **Просмотреть отчет**, **Сохранить отчет в файл**, **Копировать отчет в буфер обмена**и **Отправить отчет по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-227">The options are **View Report**, **Save Report to File**, **Copy Report to Clipboard**, and **Send Report as Email**.</span></span>  
  
     <span data-ttu-id="8b5b4-228">**Просмотреть отчет**</span><span class="sxs-lookup"><span data-stu-id="8b5b4-228">**View Report**</span></span>  
     <span data-ttu-id="8b5b4-229">Открытие диалогового окна **Просмотр отчета** , которое содержит текстовый отчет о работе мастера создания секций.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-229">Opens the **View Report** dialog box, which contains a text report of the progress of the Create Partition Wizard.</span></span>  
  
     <span data-ttu-id="8b5b4-230">**Сохранить отчет в файл**</span><span class="sxs-lookup"><span data-stu-id="8b5b4-230">**Save Report to File**</span></span>  
     <span data-ttu-id="8b5b4-231">Открытие диалогового окна **Сохранить отчет как** .</span><span class="sxs-lookup"><span data-stu-id="8b5b4-231">Opens the **Save Report As** dialog box.</span></span>  
  
     <span data-ttu-id="8b5b4-232">**Копировать отчет в буфер обмена**</span><span class="sxs-lookup"><span data-stu-id="8b5b4-232">**Copy Report to Clipboard**</span></span>  
     <span data-ttu-id="8b5b4-233">Копирование результатов отчета о работе мастера в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-233">Copies the results of the wizard's progress report to the Clipboard.</span></span>  
  
     <span data-ttu-id="8b5b4-234">**Отправить отчет по электронной почте**</span><span class="sxs-lookup"><span data-stu-id="8b5b4-234">**Send Report as Email**</span></span>  
     <span data-ttu-id="8b5b4-235">Копирование результатов отчета о состоянии мастера в сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-235">Copies the results of the wizard's progress report into an email message.</span></span>  
  
     <span data-ttu-id="8b5b4-236">Завершив выбор параметров, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-236">When complete, click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8b5b4-237">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8b5b4-237">Using Transact-SQL</span></span>  
  
#### <a name="to-enable-compression-on-a-table"></a><span data-ttu-id="8b5b4-238">Чтобы включить сжатие таблицы</span><span class="sxs-lookup"><span data-stu-id="8b5b4-238">To enable compression on a table</span></span>  
  
1.  <span data-ttu-id="8b5b4-239">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8b5b4-239">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8b5b4-240">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-240">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8b5b4-241">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-241">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="8b5b4-242">В примере сначала выполняется хранимая процедура `sp_estimate_data_compression_savings` для получения оценки размера объекта, если был выбран параметр сжатия ROW.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-242">The example first executes the stored procedure `sp_estimate_data_compression_savings` to return the estimated size of the object if it were to use the ROW compression setting.</span></span> <span data-ttu-id="8b5b4-243">Затем в примере включается сжатие ROW во всех секциях указанной таблицы.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-243">The example then enables ROW compression on all partitions in the specified table.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    EXEC sp_estimate_data_compression_savings 'Production', 'TransactionHistory', NULL, NULL, 'ROW' ;  
  
    ALTER TABLE Production.TransactionHistory REBUILD PARTITION = ALL  
    WITH (DATA_COMPRESSION = ROW);   
    GO  
    ```  
  
#### <a name="to-enable-compression-on-an-index"></a><span data-ttu-id="8b5b4-244">Чтобы включить сжатие индекса</span><span class="sxs-lookup"><span data-stu-id="8b5b4-244">To enable compression on an index</span></span>  
  
1.  <span data-ttu-id="8b5b4-245">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8b5b4-245">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8b5b4-246">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-246">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8b5b4-247">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-247">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="8b5b4-248">В примере сначала формируется запрос к представлению каталога `sys.indexes` для получения имени и `index_id` для каждого индекса таблицы `Production.TransactionHistory` .</span><span class="sxs-lookup"><span data-stu-id="8b5b4-248">The example first queries the `sys.indexes` catalog view to return the name and `index_id` for each index on the `Production.TransactionHistory` table.</span></span> <span data-ttu-id="8b5b4-249">Затем выполняется хранимая процедура `sp_estimate_data_compression_savings`, которая возвращает значение предполагаемого размера индекса с указанным ID, если был выбран параметр сжатия PAGE.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-249">It then executes the stored procedure `sp_estimate_data_compression_savings` to return the estimated size of the specified index ID if it were to use the PAGE compression setting.</span></span> <span data-ttu-id="8b5b4-250">В конце в примере перестраивается индекс ID 2 (`IX_TransactionHistory_ProductID`), с указанием типа сжатия PAGE.</span><span class="sxs-lookup"><span data-stu-id="8b5b4-250">Finally, the example rebuilds index ID 2 (`IX_TransactionHistory_ProductID`), specifying PAGE compression.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    SELECT name, index_id  
    FROM sys.indexes  
    WHERE OBJECT_NAME (object_id) = N'TransactionHistory';  
  
    EXEC sp_estimate_data_compression_savings   
        @schema_name = 'Production',   
        @object_name = 'TransactionHistory',  
        @index_id = 2,   
        @partition_number = NULL,   
        @data_compression = 'PAGE' ;   
  
    ALTER INDEX IX_TransactionHistory_ProductID ON Production.TransactionHistory REBUILD PARTITION = ALL WITH (DATA_COMPRESSION = PAGE);  
    GO  
    ```  
  
 <span data-ttu-id="8b5b4-251">Дополнительные сведения см. в разделах [ALTER TABLE (Transact-SQL)](/sql/t-sql/statements/alter-table-transact-sql) и [ALTER INDEX (Transact-SQL)](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8b5b4-251">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) and [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b5b4-252">См. также:</span><span class="sxs-lookup"><span data-stu-id="8b5b4-252">See Also</span></span>  
 <span data-ttu-id="8b5b4-253">[Сжатие данных](data-compression.md) </span><span class="sxs-lookup"><span data-stu-id="8b5b4-253">[Data Compression](data-compression.md) </span></span>  
 [<span data-ttu-id="8b5b4-254">sp_estimate_data_compression_savings (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8b5b4-254">sp_estimate_data_compression_savings &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-estimate-data-compression-savings-transact-sql)  
  
  
