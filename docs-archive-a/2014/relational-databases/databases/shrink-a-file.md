---
title: Сжатие файла | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.shrinkfile.f1
helpviewer_keywords:
- shrinking files
- decreasing file size
- databases [SQL Server], shrinking
- reducing file size
- size [SQL Server], files
- file size [SQL Server]
ms.assetid: ce5c8798-c039-4ab2-81e7-90a8d688b893
author: stevestein
ms.author: sstein
ms.openlocfilehash: ac69e4bd2db3ef7fe0815d235dd1de7d3396b302
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728329"
---
# <a name="shrink-a-file"></a><span data-ttu-id="5e6e4-102">Сжатие файла</span><span class="sxs-lookup"><span data-stu-id="5e6e4-102">Shrink a File</span></span>
  <span data-ttu-id="5e6e4-103">В этом подразделе описывается сжатие данных или файла журнала в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] при помощи среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e6e4-103">This topic describes how to shrink a data or log file in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="5e6e4-104">Сжатие файлов данных позволяет освободить неиспользуемое пространство путем перемещения страниц данных с конца файла в незанятое пространство ближе к началу файла.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-104">Shrinking data files recovers space by moving pages of data from the end of the file to unoccupied space closer to the front of the file.</span></span> <span data-ttu-id="5e6e4-105">Когда в конце файла образуется достаточно свободного места, страницы данных в конце файла могут быть освобождены и возвращены в файловую систему.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-105">When enough free space is created at the end of the file, data pages at end of the file can deallocated and returned to the file system.</span></span>  
  
 <span data-ttu-id="5e6e4-106">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="5e6e4-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5e6e4-107">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="5e6e4-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5e6e4-108">Ограничения</span><span class="sxs-lookup"><span data-stu-id="5e6e4-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="5e6e4-109">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="5e6e4-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="5e6e4-110">Безопасность</span><span class="sxs-lookup"><span data-stu-id="5e6e4-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5e6e4-111">**Сжатие файла данных или журнала с помощью различных средств.**</span><span class="sxs-lookup"><span data-stu-id="5e6e4-111">**To shrink a data or log file, using:**</span></span>  
  
     [<span data-ttu-id="5e6e4-112">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5e6e4-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5e6e4-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5e6e4-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5e6e4-114">Перед началом</span><span class="sxs-lookup"><span data-stu-id="5e6e4-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5e6e4-115">Ограничения</span><span class="sxs-lookup"><span data-stu-id="5e6e4-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="5e6e4-116">Первичный файл данных не может быть сделан меньше, чем размер первичного файла в базе данных model.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-116">The primary data file cannot be made smaller than the size of the primary file in the model database.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="5e6e4-117">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="5e6e4-117">Recommendations</span></span>  
  
-   <span data-ttu-id="5e6e4-118">Данные, перемещаемые в процессе сжатия файла, могут быть разбросаны по любым доступным местам в файле.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-118">Data that is moved to shrink a file can be scattered to any available location in the file.</span></span> <span data-ttu-id="5e6e4-119">Это вызывает фрагментацию индекса и может увеличить время выполнения запросов, выполняющих поиск в диапазоне индекса.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-119">This causes index fragmentation and can slow the performance of queries that search a range of the index.</span></span> <span data-ttu-id="5e6e4-120">Чтобы устранить фрагментацию, предусмотрите возможность перестроения индексов файла после сжатия.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-120">To eliminate the fragmentation, consider rebuilding the indexes on the file after shrinking.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5e6e4-121">безопасность</span><span class="sxs-lookup"><span data-stu-id="5e6e4-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5e6e4-122">Permissions</span><span class="sxs-lookup"><span data-stu-id="5e6e4-122">Permissions</span></span>  
 <span data-ttu-id="5e6e4-123">Необходимо быть членом предопределенной роли сервера **sysadmin** или предопределенной роли базы данных **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="5e6e4-123">Requires membership in the **sysadmin** fixed server role or the **db_owner** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5e6e4-124">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5e6e4-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-shrink-a-data-or-log-file"></a><span data-ttu-id="5e6e4-125">Сжатие файла данных или журнала</span><span class="sxs-lookup"><span data-stu-id="5e6e4-125">To shrink a data or log file</span></span>  
  
1.  <span data-ttu-id="5e6e4-126">В обозревателе объектов подключитесь к экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] и разверните его.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-126">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="5e6e4-127">Разверните узел **Базы данных** и щелкните правой кнопкой мыши базу данных, которую нужно сжать.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-127">Expand **Databases** and then right-click the database that you want to shrink.</span></span>  
  
3.  <span data-ttu-id="5e6e4-128">Укажите пункты **Задачи**и **Сжать**, затем выберите пункт **Файлы**.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-128">Point to **Tasks**, point to **Shrink**, and then click **Files**.</span></span>  
  
     <span data-ttu-id="5e6e4-129">**База данных**</span><span class="sxs-lookup"><span data-stu-id="5e6e4-129">**Database**</span></span>  
     <span data-ttu-id="5e6e4-130">Отображает имя выбранной базы данных.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-130">Displays the name of the selected database.</span></span>  
  
     <span data-ttu-id="5e6e4-131">**Тип файла**</span><span class="sxs-lookup"><span data-stu-id="5e6e4-131">**File type**</span></span>  
     <span data-ttu-id="5e6e4-132">Выберите тип файла.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-132">Select the file type for the file.</span></span> <span data-ttu-id="5e6e4-133">Доступны следующие возможности: **Данные** и **Журнал** .</span><span class="sxs-lookup"><span data-stu-id="5e6e4-133">The available choices are **Data** and **Log** files.</span></span> <span data-ttu-id="5e6e4-134">Значение по умолчанию: **Данные**.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-134">The default selection is **Data**.</span></span> <span data-ttu-id="5e6e4-135">Выбор другого типа файловой группы соответственным образом изменяет выбор в других полях.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-135">Selecting a different filegroup type changes the selections in the other fields accordingly.</span></span>  
  
     <span data-ttu-id="5e6e4-136">**Файловая группа**</span><span class="sxs-lookup"><span data-stu-id="5e6e4-136">**Filegroup**</span></span>  
     <span data-ttu-id="5e6e4-137">Выберите файловую группу из списка файловых групп, связанных с выбранным ранее **типом файлов** .</span><span class="sxs-lookup"><span data-stu-id="5e6e4-137">Select a filegroup from the list of Filegroups associated with the selected **File type** above.</span></span> <span data-ttu-id="5e6e4-138">Выбор другой файловой группы соответственным образом изменяет выбор в других полях.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-138">Selecting a different filegroup changes the selections in the other fields accordingly.</span></span>  
  
     <span data-ttu-id="5e6e4-139">**Имя файла**</span><span class="sxs-lookup"><span data-stu-id="5e6e4-139">**File name**</span></span>  
     <span data-ttu-id="5e6e4-140">Выберите файл из списка имеющихся файлов выбранной файловой группы и типа.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-140">Select a file from the list of available files of the selected filegroup and file type.</span></span>  
  
     <span data-ttu-id="5e6e4-141">**Расположение**</span><span class="sxs-lookup"><span data-stu-id="5e6e4-141">**Location**</span></span>  
     <span data-ttu-id="5e6e4-142">Отображает полный путь к текущему выбранному файлу.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-142">Displays the full path to the currently selected file.</span></span> <span data-ttu-id="5e6e4-143">Путь нельзя редактировать, но можно скопировать в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-143">The path is not editable, but it can be copied to the clipboard.</span></span>  
  
     <span data-ttu-id="5e6e4-144">**Выделенное в данный момент место**</span><span class="sxs-lookup"><span data-stu-id="5e6e4-144">**Currently allocated space**</span></span>  
     <span data-ttu-id="5e6e4-145">Для файлов данных отображает выделенное в данный момент место.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-145">For data files, displays the current allocated space.</span></span> <span data-ttu-id="5e6e4-146">Для файлов журнала отображается выделенное в данный момент пространство, вычисленное на основании результата процедуры SQLPERF(LOGSPACE) модуля DBCC.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-146">For log files, displays the current allocated space computed from the output of DBCC SQLPERF(LOGSPACE).</span></span>  
  
     <span data-ttu-id="5e6e4-147">**Доступное свободное место**</span><span class="sxs-lookup"><span data-stu-id="5e6e4-147">**Available free space**</span></span>  
     <span data-ttu-id="5e6e4-148">Для файлов данных отображается имеющееся в данный момент доступное свободное место, вычисленное на основании результата процедуры SHOWFILESTATS(идентификатор_файла) модуля DBCC.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-148">For data files, displays the current available free space computed from the output of DBCC SHOWFILESTATS(fileid).</span></span> <span data-ttu-id="5e6e4-149">Для файлов журнала отображается имеющиеся в данный момент доступное свободное место, вычисленное на основании результата процедуры SQLPERF(LOGSPACE) модуля DBCC.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-149">For log files, displays the current available free space computed from the output of DBCC SQLPERF(LOGSPACE).</span></span>  
  
     <span data-ttu-id="5e6e4-150">**Освободить неиспользуемое место**</span><span class="sxs-lookup"><span data-stu-id="5e6e4-150">**Release unused space**</span></span>  
     <span data-ttu-id="5e6e4-151">Все неиспользуемое пространство, выделенное для файлов, освобождается для нужд операционной системы, а файл сжимается в последний выделенный экстент, тем самым размер файла уменьшается без перемещения данных.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-151">Cause any unused space in the files to be released to the operating system and shrink the file to the last allocated extent, reducing the file size without moving any data.</span></span> <span data-ttu-id="5e6e4-152">Не производится попыток перемещения строк на нераспределенные страницы.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-152">No attempt is made to relocate rows to unallocated pages.</span></span>  
  
     <span data-ttu-id="5e6e4-153">**Реорганизовать страницы, перед тем как освободить неиспользуемое место**</span><span class="sxs-lookup"><span data-stu-id="5e6e4-153">**Reorganize pages before releasing unused space**</span></span>  
     <span data-ttu-id="5e6e4-154">Эквивалентно выполнению процедуры SHRINKFILE модуля DBCC, определяющей размер целевого файла.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-154">Equivalent to executing DBCC SHRINKFILE specifying the target file size.</span></span> <span data-ttu-id="5e6e4-155">При выборе этого параметра необходимо указать размер целевого файла в поле **Сжать файл до** .</span><span class="sxs-lookup"><span data-stu-id="5e6e4-155">When this option is selected, the user must specify a target file size in the **Shrink file to** box.</span></span>  
  
     <span data-ttu-id="5e6e4-156">**Сжать файл до**</span><span class="sxs-lookup"><span data-stu-id="5e6e4-156">**Shrink file to**</span></span>  
     <span data-ttu-id="5e6e4-157">Определяет размер целевого файла для операции сжатия.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-157">Specifies the target file size for the shrink operation.</span></span> <span data-ttu-id="5e6e4-158">Размер не должен быть меньше текущего выделенного пространства или больше общего количества экстентов, выделенных файлу.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-158">The size cannot be less than the current allocated space or more than the total extents allocated to the file.</span></span> <span data-ttu-id="5e6e4-159">Если вводимое значение выходит за допустимые границы, оно будет преобразовано к минимальному или максимальному значению при изменении фокуса ввода или при нажатии на любую кнопку панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-159">Entering a value beyond the minimum or the maximum will revert to the min or the max once the focus is changed or when any of the buttons on the toolbar are clicked.</span></span>  
  
     <span data-ttu-id="5e6e4-160">**Очистить файл путем переноса данных в другие файлы той же файловой группы**</span><span class="sxs-lookup"><span data-stu-id="5e6e4-160">**Empty file by migrating the data to other files in the same filegroup**</span></span>  
     <span data-ttu-id="5e6e4-161">Выполняется перенос всех данных из указанного файла.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-161">Migrate all data from the specified file.</span></span> <span data-ttu-id="5e6e4-162">Этот параметр позволяет удалить файл при помощи инструкции ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-162">This option allows the file to be dropped using the ALTER DATABASE statement.</span></span> <span data-ttu-id="5e6e4-163">Эта возможность эквивалентна выполнению процедуры SHRINKFILE модуля DBCC с параметром EMPTYFILE.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-163">This option is equivalent to executing DBCC SHRINKFILE with the EMPTYFILE option.</span></span>  
  
4.  <span data-ttu-id="5e6e4-164">Выберите тип файла и имя файла.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-164">Select the file type and file name.</span></span>  
  
5.  <span data-ttu-id="5e6e4-165">Дополнительно можно установить флажок **Освободить неиспользуемое место** .</span><span class="sxs-lookup"><span data-stu-id="5e6e4-165">Optionally, select the **Release unused space** check box.</span></span>  
  
     <span data-ttu-id="5e6e4-166">Выбор этого параметра приводит к освобождению всего неиспользуемого пространства файла для ОС и уменьшению размера файла до последнего размещенного экстента.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-166">Selecting this option causes any unused space in the file to be released to the operating system and shrinks the file to the last allocated extent.</span></span> <span data-ttu-id="5e6e4-167">Это уменьшает размер файла без перемещения каких-либо данных.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-167">This reduces the file size without moving any data.</span></span>  
  
6.  <span data-ttu-id="5e6e4-168">Дополнительно можно установить флажок **Реорганизовать файлы перед освобождением неиспользуемого места** .</span><span class="sxs-lookup"><span data-stu-id="5e6e4-168">Optionally, select the **Reorganize files before releasing unused space** check box.</span></span> <span data-ttu-id="5e6e4-169">При выборе этого режима необходимо указать значение **Сжать файл до** .</span><span class="sxs-lookup"><span data-stu-id="5e6e4-169">If this is selected, the **Shrink file to** value must be specified.</span></span> <span data-ttu-id="5e6e4-170">По умолчанию этот флажок снят.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-170">By default, the option is cleared.</span></span>  
  
     <span data-ttu-id="5e6e4-171">Выбор этого параметра приводит к освобождению всего неиспользуемого пространства файла для ОС и попытке перемещения строк в неразмещенные страницы.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-171">Selecting this option causes any unused space in the file to be released to the operating system and tries to relocate rows to unallocated pages.</span></span>  
  
7.  <span data-ttu-id="5e6e4-172">При необходимости введите максимальный процент свободного пространства, которое должно остаться в базе данных после ее сжатия.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-172">Optionally, enter the maximum percentage of free space to be left in the database file after the database has been shrunk.</span></span> <span data-ttu-id="5e6e4-173">Допустимы значения от 0 до 99.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-173">Permissible values are between 0 and 99.</span></span> <span data-ttu-id="5e6e4-174">Этот параметр доступен только в том случае, если установлен флажок **Реорганизовать файлы перед освобождением неиспользуемого места** .</span><span class="sxs-lookup"><span data-stu-id="5e6e4-174">This option is only available when **Reorganize files before releasing unused space** is enabled.</span></span>  
  
8.  <span data-ttu-id="5e6e4-175">При необходимости установите флажок **Очистить файл путем переноса данных в другие файлы той же файловой группы** .</span><span class="sxs-lookup"><span data-stu-id="5e6e4-175">Optionally, select the **Empty file by migrating the data to other files in the same filegroup** check box.</span></span>  
  
     <span data-ttu-id="5e6e4-176">Выбор этого режима перемещает все данные из указанного файла в другие файлы данной файловой группы.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-176">Selecting this option moves all data from the specified file to other files in the filegroup.</span></span> <span data-ttu-id="5e6e4-177">Пустой файл удалить нельзя.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-177">The empty file can then be deleted.</span></span> <span data-ttu-id="5e6e4-178">Этот режим эквивалентен выполнению процедуры DBCC SHRINKFILE с параметром EMPTYFILE.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-178">This option is the same as executing DBCC SHRINKFILE with the EMPTYFILE option.</span></span>  
  
9. <span data-ttu-id="5e6e4-179">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-179">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5e6e4-180">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5e6e4-180">Using Transact-SQL</span></span>  
  
#### <a name="to-shrink-a-data-or-log-file"></a><span data-ttu-id="5e6e4-181">Сжатие файла данных или журнала</span><span class="sxs-lookup"><span data-stu-id="5e6e4-181">To shrink a data or log file</span></span>  
  
1.  <span data-ttu-id="5e6e4-182">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e6e4-182">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5e6e4-183">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-183">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5e6e4-184">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="5e6e4-184">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="5e6e4-185">В следующем примере для сжатия файла [в базе данных](/sql/t-sql/database-console-commands/dbcc-shrinkfile-transact-sql) до 7 МБ используется функция `DataFile1` DBCC SHRINKFILE `UserDB` .</span><span class="sxs-lookup"><span data-stu-id="5e6e4-185">This example uses [DBCC SHRINKFILE](/sql/t-sql/database-console-commands/dbcc-shrinkfile-transact-sql) to shrink the size of a data file named `DataFile1` in the `UserDB` database to 7 MB.</span></span>  
  
 [!code-sql[DBCC#DBCC_SHRINKFILE1](../../snippets/tsql/SQL14/tsql/dbcc/transact-sql/dbcc_other.sql#dbcc_shrinkfile1)]  
  
## <a name="see-also"></a><span data-ttu-id="5e6e4-186">См. также:</span><span class="sxs-lookup"><span data-stu-id="5e6e4-186">See Also</span></span>  
 <span data-ttu-id="5e6e4-187">[DBCC SHRINKDATABASE (Transact-SQL)](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5e6e4-187">[DBCC SHRINKDATABASE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql) </span></span>  
 <span data-ttu-id="5e6e4-188">[Сжатие базы данных](shrink-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="5e6e4-188">[Shrink a Database](shrink-a-database.md) </span></span>  
 <span data-ttu-id="5e6e4-189">[Удаление файлов данных или журнала из базы данных](delete-data-or-log-files-from-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="5e6e4-189">[Delete Data or Log Files from a Database](delete-data-or-log-files-from-a-database.md) </span></span>  
 <span data-ttu-id="5e6e4-190">[sys.databases (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5e6e4-190">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 [<span data-ttu-id="5e6e4-191">sys.database_files (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="5e6e4-191">sys.database_files &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql)  
  
  
