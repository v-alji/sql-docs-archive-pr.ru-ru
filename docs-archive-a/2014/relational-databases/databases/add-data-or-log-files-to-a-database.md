---
title: Добавление файлов данных или журналов в базу данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], files
- adding data files
- adding files
- adding log files
- file additions [SQL Server], steps
- files [SQL Server], adding
- data additions [SQL Server]
ms.assetid: 8ead516a-1334-4f40-84b2-509d0a8ffa45
author: stevestein
ms.author: sstein
ms.openlocfilehash: f72e00f9dab422652237b4b85579c544d0cda9fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751136"
---
# <a name="add-data-or-log-files-to-a-database"></a><span data-ttu-id="817ac-102">Добавление файлов данных или журналов в базу данных</span><span class="sxs-lookup"><span data-stu-id="817ac-102">Add Data or Log Files to a Database</span></span>
  <span data-ttu-id="817ac-103">В этом подразделе содержатся инструкции по добавлению файлов данных или журналов в базу данных на сервере [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] при помощи [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="817ac-103">This topic describes how to add data or log files to a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="817ac-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="817ac-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="817ac-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="817ac-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="817ac-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="817ac-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="817ac-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="817ac-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="817ac-108">**Добавление файлов данных или журналов в базу данных при помощи следующих средств.**</span><span class="sxs-lookup"><span data-stu-id="817ac-108">**To add data or log files to a database, using:**</span></span>  
  
     [<span data-ttu-id="817ac-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="817ac-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="817ac-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="817ac-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="817ac-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="817ac-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="817ac-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="817ac-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="817ac-113">Добавить или удалить файл во время выполнения инструкции BACKUP невозможно.</span><span class="sxs-lookup"><span data-stu-id="817ac-113">You cannot add or remove a file while a BACKUP statement is running.</span></span>  
  
-   <span data-ttu-id="817ac-114">Для каждой базы данных может указываться не более 32 767 файлов и 32 767 файловых групп.</span><span class="sxs-lookup"><span data-stu-id="817ac-114">A maximum of 32,767 files and 32,767 filegroups can be specified for each database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="817ac-115">безопасность</span><span class="sxs-lookup"><span data-stu-id="817ac-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="817ac-116">Permissions</span><span class="sxs-lookup"><span data-stu-id="817ac-116">Permissions</span></span>  
 <span data-ttu-id="817ac-117">Необходимо разрешение ALTER на базу данных.</span><span class="sxs-lookup"><span data-stu-id="817ac-117">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="817ac-118">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="817ac-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-add-data-or-log-files-to-a-database"></a><span data-ttu-id="817ac-119">Добавление файлов данных или журналов в базу данных</span><span class="sxs-lookup"><span data-stu-id="817ac-119">To add data or log files to a database</span></span>  
  
1.  <span data-ttu-id="817ac-120">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] и разверните его.</span><span class="sxs-lookup"><span data-stu-id="817ac-120">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="817ac-121">Разверните узел **Базы данных**, щелкните правой кнопкой мыши базу данных, в которую необходимо добавить файлы, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="817ac-121">Expand **Databases**, right-click the database from which to add the files, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="817ac-122">В диалоговом окне **Свойства базы данных** перейдите на вкладку **Файлы** .</span><span class="sxs-lookup"><span data-stu-id="817ac-122">In the **Database Properties** dialog box, select the **Files** page.</span></span>  
  
4.  <span data-ttu-id="817ac-123">Чтобы добавить данные или файл журнала транзакций, нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="817ac-123">To add a data or transaction log file, click **Add**.</span></span>  
  
5.  <span data-ttu-id="817ac-124">В сетке **Файлы базы данных** введите логическое имя файла.</span><span class="sxs-lookup"><span data-stu-id="817ac-124">In the **Database files** grid, enter a logical name for the file.</span></span> <span data-ttu-id="817ac-125">Имя файла должно быть уникальным в пределах базы данных.</span><span class="sxs-lookup"><span data-stu-id="817ac-125">The file name must be unique within the database.</span></span>  
  
6.  <span data-ttu-id="817ac-126">Выберите тип файла, данные или журнал.</span><span class="sxs-lookup"><span data-stu-id="817ac-126">Select the file type, data or log.</span></span>  
  
7.  <span data-ttu-id="817ac-127">Выберите файловую группу, в которую следует добавить файл данных, или выберите **\<new filegroup>** , чтобы создать новую.</span><span class="sxs-lookup"><span data-stu-id="817ac-127">For a data file, select the filegroup in which the file should be included from the list, or select **\<new filegroup>** to create a new filegroup.</span></span> <span data-ttu-id="817ac-128">Журналы транзакций не могут быть помещены в файловые группы.</span><span class="sxs-lookup"><span data-stu-id="817ac-128">Transaction logs cannot be put in filegroups.</span></span>  
  
8.  <span data-ttu-id="817ac-129">Укажите исходный размер файла.</span><span class="sxs-lookup"><span data-stu-id="817ac-129">Specify the initial size of the file.</span></span> <span data-ttu-id="817ac-130">Файл данных следует делать как можно большего размера, в соответствии с максимальным предполагаемым объемом данных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="817ac-130">Make the data file as large as possible, based on the maximum amount of data you expect in the database.</span></span>  
  
9. <span data-ttu-id="817ac-131">Укажите, как должен расширяться файл, нажав кнопку ( **...** ) в столбце **Авторасширение**.</span><span class="sxs-lookup"><span data-stu-id="817ac-131">To specify how the file should grow, click (**...**) in the **Autogrowth** column.</span></span> <span data-ttu-id="817ac-132">Выберите один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="817ac-132">Select from the following options:</span></span>  
  
    1.  <span data-ttu-id="817ac-133">Чтобы разрешить выбранному файлу расти по мере необходимости, установите флажок **Разрешить авторасширение** и выберите один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="817ac-133">To allow for the currently selected file to grow as more data space is required, select the **Enable Autogrowth** check box and then select from the following options:</span></span>  
  
    2.  <span data-ttu-id="817ac-134">Чтобы файл увеличивался с фиксированным приращением, выберите параметр **В мегабайтах** и укажите значение.</span><span class="sxs-lookup"><span data-stu-id="817ac-134">To specify that the file should grow by fixed increments, select **In Megabytes** and specify a value.</span></span>  
  
    3.  <span data-ttu-id="817ac-135">Чтобы файл увеличивался на определенный процент от текущего размера, выберите параметр **В процентах** и укажите значение.</span><span class="sxs-lookup"><span data-stu-id="817ac-135">To specify that the file should grow by a percentage of the current file size, select **In Percent** and specify a value.</span></span>  
  
10. <span data-ttu-id="817ac-136">Укажите максимальный размер файла, выбрав один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="817ac-136">To specify the maximum file size limit, select from the following options:</span></span>  
  
    1.  <span data-ttu-id="817ac-137">Чтобы указать максимальный размер, до которого может увеличиваться файл, выберите параметр **Ограничение размера файла (МБ)** и укажите нужное значение.</span><span class="sxs-lookup"><span data-stu-id="817ac-137">To specify the maximum size the file should be able to grow to, select **Restricted File Growth (MB)** and specify a value.</span></span>  
  
    2.  <span data-ttu-id="817ac-138">Чтобы разрешить файлу увеличиваться по мере необходимости, выберите параметр **Неограниченный рост размера файлов**.</span><span class="sxs-lookup"><span data-stu-id="817ac-138">To allow for the file to grow as much as needed, select **Unrestricted File Growth**.</span></span>  
  
    3.  <span data-ttu-id="817ac-139">Чтобы предотвратить рост файла, снимите флажок **Разрешить авторасширение** .</span><span class="sxs-lookup"><span data-stu-id="817ac-139">To prevent the file from growing, clear the **Enable Autogrowth** check box.</span></span> <span data-ttu-id="817ac-140">При этом файл не превысит размер, указанный в столбце **Начальный размер (МБ)** .</span><span class="sxs-lookup"><span data-stu-id="817ac-140">The size of the file will not grow beyond the value specified in the **Initial Size (MB)** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="817ac-141">Максимальный размер базы данных зависит от доступного пространства на диске и от ограничений лицензии, устанавливаемых используемой версией [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="817ac-141">The maximum database size is determined by the amount of disk space available and the licensing limits determined by the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you are using.</span></span>  
  
11. <span data-ttu-id="817ac-142">Укажите путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="817ac-142">Specify the path for the file location.</span></span> <span data-ttu-id="817ac-143">Указанный путь к добавляемому файлу должен существовать.</span><span class="sxs-lookup"><span data-stu-id="817ac-143">The specified path must exist before adding the file.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="817ac-144">Данные и журналы транзакций по умолчанию помещаются на один и тот же диск и в один и тот же каталог. Это сделано в соответствии с требованиями, предъявляемыми системами с одним диском, но для рабочей среды это может оказаться неоптимальным.</span><span class="sxs-lookup"><span data-stu-id="817ac-144">By default, the data and transaction logs are put on the same drive and path to accommodate single-disk systems, but may not be optimal for production environments.</span></span> <span data-ttu-id="817ac-145">Дополнительные сведения см. в статье [Файлы и группы файлов базы данных](database-files-and-filegroups.md).</span><span class="sxs-lookup"><span data-stu-id="817ac-145">For more information, see [Database Files and Filegroups](database-files-and-filegroups.md).</span></span>  
  
12. <span data-ttu-id="817ac-146">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="817ac-146">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="817ac-147">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="817ac-147">Using Transact-SQL</span></span>  
  
#### <a name="to-add-data-or-log-files-to-a-database"></a><span data-ttu-id="817ac-148">Добавление файлов данных или журналов в базу данных</span><span class="sxs-lookup"><span data-stu-id="817ac-148">To add data or log files to a database</span></span>  
  
1.  <span data-ttu-id="817ac-149">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="817ac-149">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="817ac-150">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="817ac-150">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="817ac-151">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="817ac-151">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="817ac-152">В этом примере выполняется добавление в базу данных группы из двух файлов.</span><span class="sxs-lookup"><span data-stu-id="817ac-152">The example adds a filegroup with two files to a database.</span></span> <span data-ttu-id="817ac-153">В примере в базе данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]создается файловая группа `Test1FG1` и добавляются два файла по 5 МБ в эту файловую группу.</span><span class="sxs-lookup"><span data-stu-id="817ac-153">The example creates the filegroup `Test1FG1` in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database and adds two 5-MB files to the filegroup.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase2](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase2)]  
  
 <span data-ttu-id="817ac-154">Дополнительные сведения см. в разделе [Параметры инструкции ALTER DATABASE для файлов и файловых групп (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span><span class="sxs-lookup"><span data-stu-id="817ac-154">For more examples, see [ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="817ac-155">См. также:</span><span class="sxs-lookup"><span data-stu-id="817ac-155">See Also</span></span>  
 <span data-ttu-id="817ac-156">[Database Files and Filegroups](database-files-and-filegroups.md) </span><span class="sxs-lookup"><span data-stu-id="817ac-156">[Database Files and Filegroups](database-files-and-filegroups.md) </span></span>  
 <span data-ttu-id="817ac-157">[Удаление файлов данных или журнала из базы данных](delete-data-or-log-files-from-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="817ac-157">[Delete Data or Log Files from a Database](delete-data-or-log-files-from-a-database.md) </span></span>  
 [<span data-ttu-id="817ac-158">Увеличение размера базы данных</span><span class="sxs-lookup"><span data-stu-id="817ac-158">Increase the Size of a Database</span></span>](increase-the-size-of-a-database.md)  
  
  
