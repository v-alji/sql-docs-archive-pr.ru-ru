---
title: Присоединение базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.attachdatabase.f1
helpviewer_keywords:
- database attaching [SQL Server]
- attaching databases [SQL Server]
ms.assetid: b4efb0ae-cfe6-4d81-a4b4-6e4916885caa
author: stevestein
ms.author: sstein
ms.openlocfilehash: cb11b5c257007872e92d3f0a7eadb3e46b4969cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751131"
---
# <a name="attach-a-database"></a><span data-ttu-id="78a93-102">Присоединение базы данных</span><span class="sxs-lookup"><span data-stu-id="78a93-102">Attach a Database</span></span>
  <span data-ttu-id="78a93-103">В этом разделе описывается присоединение базы данных в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78a93-103">This topic describes how to attach a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="78a93-104">Эту функцию можно использовать для копирования, перемещения или обновления базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78a93-104">You can use this feature to copy, move, or upgrade a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="78a93-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="78a93-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="78a93-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="78a93-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="78a93-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="78a93-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="78a93-108">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="78a93-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="78a93-109">Безопасность</span><span class="sxs-lookup"><span data-stu-id="78a93-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="78a93-110">**Присоединение базы данных с помощью различных средств.**</span><span class="sxs-lookup"><span data-stu-id="78a93-110">**To Attach a Database by using:**</span></span>  
  
     [<span data-ttu-id="78a93-111">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="78a93-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="78a93-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="78a93-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="78a93-113">**Дальнейшие действия.**  [После обновления базы данных](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="78a93-113">**Follow Up:**  [After Upgrading a Database](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="78a93-114">Перед началом</span><span class="sxs-lookup"><span data-stu-id="78a93-114">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="78a93-115">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="78a93-115">Prerequisites</span></span>  
  
-   <span data-ttu-id="78a93-116">Базу данных сначала необходимо отсоединить.</span><span class="sxs-lookup"><span data-stu-id="78a93-116">The database must first be detached.</span></span> <span data-ttu-id="78a93-117">Попытка присоединить базу данных, которая не была отсоединена, приведет к возникновению ошибки.</span><span class="sxs-lookup"><span data-stu-id="78a93-117">Attempting to attach a database that has not been detached will return an error.</span></span> <span data-ttu-id="78a93-118">Дополнительные сведения см. в разделе [Отсоединение базы данных](detach-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="78a93-118">For more information, see [Detach a Database](detach-a-database.md).</span></span>  
  
-   <span data-ttu-id="78a93-119">При присоединении базы данных должны быть доступны все файлы данных (файлы MDF и LDF).</span><span class="sxs-lookup"><span data-stu-id="78a93-119">When you attach a database, all data files (MDF and LDF files) must be available.</span></span> <span data-ttu-id="78a93-120">Если у какого-либо файла данных путь отличается от того, каким он был при первом создании или последнем присоединении, необходимо указать текущий путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="78a93-120">If any data file has a different path from when the database was first created or last attached, you must specify the current path of the file.</span></span>  
  
-   <span data-ttu-id="78a93-121">Если при присоединении базы данных файлы MDF и LDF находятся в разных каталогах, а один из путей содержит \\\\?\GlobalRoot, операция завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="78a93-121">When you attach a database, if MDF and LDF files are located in different directories and one of the paths includes \\\\?\GlobalRoot, the operation will fail.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="78a93-122">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="78a93-122">Recommendations</span></span>  
<span data-ttu-id="78a93-123">Рекомендуется перемещать базы данных с помощью `ALTER DATABASE` процедуры запланированного перемещения вместо того, чтобы использовать отсоединение и присоединение.</span><span class="sxs-lookup"><span data-stu-id="78a93-123">We recommend that you move databases by using the `ALTER DATABASE` planned relocation procedure, instead of using detach and attach.</span></span> <span data-ttu-id="78a93-124">Дополнительные сведения см. в статье [Move User Databases](move-user-databases.md).</span><span class="sxs-lookup"><span data-stu-id="78a93-124">For more information, see [Move User Databases](move-user-databases.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="78a93-125">безопасность</span><span class="sxs-lookup"><span data-stu-id="78a93-125">Security</span></span>  
<span data-ttu-id="78a93-126">Разрешения на доступ к файлам устанавливаются во время выполнения определенных операций с базами данных, включая отсоединение и присоединение баз данных.</span><span class="sxs-lookup"><span data-stu-id="78a93-126">File access permissions are set during a number of database operations, including detaching or attaching a database.</span></span> <span data-ttu-id="78a93-127">Дополнительные сведения о разрешениях доступа к файлам, задаваемые во время отсоединения и присоединения базы данных, см. в разделе [Защита данных и файлов журналов](https://technet.microsoft.com/library/ms189128.aspx) электронной документации по [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="78a93-127">For information about file permissions that are set whenever a database is detached and attached, see [Securing Data and Log Files](https://technet.microsoft.com/library/ms189128.aspx) in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] Books Online.</span></span>  
  
<span data-ttu-id="78a93-128">Не рекомендуется подключать или восстанавливать базы данных, полученные из неизвестных или ненадежных источников.</span><span class="sxs-lookup"><span data-stu-id="78a93-128">We recommend that you do not attach or restore databases from unknown or untrusted sources.</span></span> <span data-ttu-id="78a93-129">В этих базах данных может содержаться вредоносный код, вызывающий выполнение непредусмотренных инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] или появление ошибок из-за изменения схемы или физической структуры базы данных.</span><span class="sxs-lookup"><span data-stu-id="78a93-129">Such databases could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema or the physical database structure.</span></span> <span data-ttu-id="78a93-130">Перед тем как использовать базу данных, полученную из неизвестного или ненадежного источника, выполните на тестовом сервере инструкцию [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) для этой базы данных, а также изучите исходный код в базе данных, например хранимые процедуры и другой пользовательский код.</span><span class="sxs-lookup"><span data-stu-id="78a93-130">Before you use a database from an unknown or untrusted source, run [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database on a nonproduction server and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span> <span data-ttu-id="78a93-131">Дополнительные сведения о присоединении баз данных и сведения об изменениях, вносимых при присоединении баз данных в метаданные, см. в статье [Присоединение и отсоединение базы данных (SQL Server)](database-detach-and-attach-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="78a93-131">For more information about attaching databases and information about changes that are made to metadata when you attach a database, see [Database Detach and Attach &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="78a93-132">Permissions</span><span class="sxs-lookup"><span data-stu-id="78a93-132">Permissions</span></span>  
<span data-ttu-id="78a93-133">Требуется разрешение `CREATE DATABASE`, `CREATE ANY DATABASE` или `ALTER ANY DATABASE`.</span><span class="sxs-lookup"><span data-stu-id="78a93-133">Requires `CREATE DATABASE`, `CREATE ANY DATABASE`, or `ALTER ANY DATABASE` permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="78a93-134">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="78a93-134">Using SQL Server Management Studio</span></span>  
  
### <a name="to-attach-a-database"></a><span data-ttu-id="78a93-135">Присоединение базы данных</span><span class="sxs-lookup"><span data-stu-id="78a93-135">To Attach a Database</span></span>  
  
1.  <span data-ttu-id="78a93-136">В обозревателе объектов среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] подключитесь к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]и разверните его.</span><span class="sxs-lookup"><span data-stu-id="78a93-136">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="78a93-137">Щелкните правой кнопкой мыши узел **Базы данных** и выберите команду **Присоединить**.</span><span class="sxs-lookup"><span data-stu-id="78a93-137">Right-click **Databases** and click **Attach**.</span></span>  
  
3.  <span data-ttu-id="78a93-138">Чтобы указать присоединяемую базу данных, в диалоговом окне **Присоединение баз данных** нажмите кнопку **Добавить**, в диалоговом окне **Расположение файлов базы данных** выберите диск, на котором находится база данных, и разверните дерево каталогов, чтобы найти и выбрать MDF-файл, например:</span><span class="sxs-lookup"><span data-stu-id="78a93-138">In the **Attach Databases** dialog box, to specify the database to be attached, click **Add**; and in the **Locate Database Files** dialog box, select the disk drive where the database resides and expand the directory tree to find and select the .mdf file of the database; for example:</span></span>  
  
     `C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\AdventureWorks2012_Data.mdf`  
  
    > [!IMPORTANT]  
    > <span data-ttu-id="78a93-139">При попытке выбора базы данных, которая уже присоединена, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="78a93-139">Trying to select a database that is already attached generates an error.</span></span>  
  
     <span data-ttu-id="78a93-140">**Базы данных для присоединения**</span><span class="sxs-lookup"><span data-stu-id="78a93-140">**Databases to attach**</span></span>  
     <span data-ttu-id="78a93-141">Отобразятся сведения о выбранных базах данных.</span><span class="sxs-lookup"><span data-stu-id="78a93-141">Displays information about the selected databases.</span></span>  
  
     \<no column header>  
     <span data-ttu-id="78a93-142">Отображается значок, указывающий на состояние операции присоединения.</span><span class="sxs-lookup"><span data-stu-id="78a93-142">Displays an icon indicating the status of the attach operation.</span></span> <span data-ttu-id="78a93-143">Возможные значки описываются в приводимом ниже описании **Состояние** .</span><span class="sxs-lookup"><span data-stu-id="78a93-143">The possible icons are described in the **Status** description, below).</span></span>  
  
     <span data-ttu-id="78a93-144">**Расположение файла MDF**</span><span class="sxs-lookup"><span data-stu-id="78a93-144">**MDF File Location**</span></span>  
     <span data-ttu-id="78a93-145">Отображается путь и имя выбранного MDF-файла.</span><span class="sxs-lookup"><span data-stu-id="78a93-145">Displays the path and file name of the selected MDF file.</span></span>  
  
     <span data-ttu-id="78a93-146">**Имя базы данных**</span><span class="sxs-lookup"><span data-stu-id="78a93-146">**Database Name**</span></span>  
     <span data-ttu-id="78a93-147">Отображается имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="78a93-147">Displays the name of the database.</span></span>  
  
     <span data-ttu-id="78a93-148">**Присоединить как**</span><span class="sxs-lookup"><span data-stu-id="78a93-148">**Attach As**</span></span>  
     <span data-ttu-id="78a93-149">Необязательный параметр, указывает другое имя, под которым присоединяется база данных.</span><span class="sxs-lookup"><span data-stu-id="78a93-149">Optionally, specifies a different name for the database to attach as.</span></span>  
  
     <span data-ttu-id="78a93-150">**Владелец**</span><span class="sxs-lookup"><span data-stu-id="78a93-150">**Owner**</span></span>  
     <span data-ttu-id="78a93-151">Содержит раскрывающийся список возможных владельцев базы данных, из которого при необходимости можно выбрать другого владельца.</span><span class="sxs-lookup"><span data-stu-id="78a93-151">Provides a drop-down list of possible database owners from which you can optionally select a different owner.</span></span>  
  
     <span data-ttu-id="78a93-152">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="78a93-152">**Status**</span></span>  
     <span data-ttu-id="78a93-153">Отображается состояние базы данных в соответствии со следующей таблицей.</span><span class="sxs-lookup"><span data-stu-id="78a93-153">Displays the status of the database according to the following table.</span></span>  
  
    |<span data-ttu-id="78a93-154">Значок</span><span class="sxs-lookup"><span data-stu-id="78a93-154">Icon</span></span>|<span data-ttu-id="78a93-155">Текст состояния</span><span class="sxs-lookup"><span data-stu-id="78a93-155">Status text</span></span>|<span data-ttu-id="78a93-156">Описание</span><span class="sxs-lookup"><span data-stu-id="78a93-156">Description</span></span>|  
    |----------|-----------------|-----------------|  
    |<span data-ttu-id="78a93-157">(Нет значка)</span><span class="sxs-lookup"><span data-stu-id="78a93-157">(No icon)</span></span>|<span data-ttu-id="78a93-158">(Нет текста)</span><span class="sxs-lookup"><span data-stu-id="78a93-158">(No text)</span></span>|<span data-ttu-id="78a93-159">Операция присоединения не была запущена или находится в режиме ожидания для этого объекта.</span><span class="sxs-lookup"><span data-stu-id="78a93-159">Attach operation has not been started or may be pending for this object.</span></span> <span data-ttu-id="78a93-160">Это состояние по умолчанию при открытии диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="78a93-160">This is the default when the dialog is opened.</span></span>|  
    |<span data-ttu-id="78a93-161">Зеленый, указывающий направо треугольник</span><span class="sxs-lookup"><span data-stu-id="78a93-161">Green, right-pointing triangle</span></span>|<span data-ttu-id="78a93-162">Выполняется</span><span class="sxs-lookup"><span data-stu-id="78a93-162">In progress</span></span>|<span data-ttu-id="78a93-163">Операция присоединения была запущена, но не завершена.</span><span class="sxs-lookup"><span data-stu-id="78a93-163">Attach operation has been started but it is not complete.</span></span>|  
    |<span data-ttu-id="78a93-164">Зеленый флажок</span><span class="sxs-lookup"><span data-stu-id="78a93-164">Green check mark</span></span>|<span data-ttu-id="78a93-165">Успешно</span><span class="sxs-lookup"><span data-stu-id="78a93-165">Success</span></span>|<span data-ttu-id="78a93-166">Объект успешно присоединен.</span><span class="sxs-lookup"><span data-stu-id="78a93-166">The object has been attached successfully.</span></span>|  
    |<span data-ttu-id="78a93-167">Красный кружок с белым крестом внутри</span><span class="sxs-lookup"><span data-stu-id="78a93-167">Red circle containing a white cross</span></span>|<span data-ttu-id="78a93-168">Error</span><span class="sxs-lookup"><span data-stu-id="78a93-168">Error</span></span>|<span data-ttu-id="78a93-169">При выполнении операции присоединения возникла ошибка, и операция не была успешно завершена.</span><span class="sxs-lookup"><span data-stu-id="78a93-169">Attach operation encountered an error and did not complete successfully.</span></span>|  
    |<span data-ttu-id="78a93-170">Кружок с двумя черными квадратами (слева и справа) и двумя белыми квадратами (сверху и снизу)</span><span class="sxs-lookup"><span data-stu-id="78a93-170">Circle containing two black quadrants (on left and right) and two white quadrants (on top and bottom)</span></span>|<span data-ttu-id="78a93-171">Остановлена</span><span class="sxs-lookup"><span data-stu-id="78a93-171">Stopped</span></span>|<span data-ttu-id="78a93-172">Операция присоединения не была успешно завершена, т.к. пользователь остановил операцию.</span><span class="sxs-lookup"><span data-stu-id="78a93-172">Attach operation was not completed successfully because the user stopped the operation.</span></span>|  
    |<span data-ttu-id="78a93-173">Кружок, содержащий изогнутую стрелку, указывающую в направлении против часовой стрелки</span><span class="sxs-lookup"><span data-stu-id="78a93-173">Circle containing a curved arrow pointing counter-clockwise</span></span>|<span data-ttu-id="78a93-174">Выполнен откат</span><span class="sxs-lookup"><span data-stu-id="78a93-174">Rolled Back</span></span>|<span data-ttu-id="78a93-175">Операция присоединения была успешной, но был выполнен ее откат из-за ошибки, возникшей при вложении другого объекта.</span><span class="sxs-lookup"><span data-stu-id="78a93-175">Attach operation was successful but it has been rolled back due to an error during attachment of another object.</span></span>|  
  
     <span data-ttu-id="78a93-176">**Сообщение**</span><span class="sxs-lookup"><span data-stu-id="78a93-176">**Message**</span></span>  
     <span data-ttu-id="78a93-177">Отображается пустое сообщение или гиперссылка «Файл не найден».</span><span class="sxs-lookup"><span data-stu-id="78a93-177">Displays either a blank message or a "File not found" hyperlink.</span></span>  
  
     <span data-ttu-id="78a93-178">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="78a93-178">**Add**</span></span>  
     <span data-ttu-id="78a93-179">Найдите необходимые основные файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="78a93-179">Find the necessary main database files.</span></span> <span data-ttu-id="78a93-180">Если пользователь выбирает mdf-файл, необходимые сведения автоматически вводятся в соответствующие поля сетки **Базы данных для присоединения** .</span><span class="sxs-lookup"><span data-stu-id="78a93-180">When the user selects an .mdf file, applicable information is automatically filled in the respective fields of the **Databases to attach** grid.</span></span>  
  
     <span data-ttu-id="78a93-181">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="78a93-181">**Remove**</span></span>  
     <span data-ttu-id="78a93-182">Удаляет выбранный файл из сетки **Базы данных для присоединения** .</span><span class="sxs-lookup"><span data-stu-id="78a93-182">Removes the selected file from the **Databases to attach** grid.</span></span>  
  
     <span data-ttu-id="78a93-183">**Сведения о базе данных "** *<имя_базы_данных>* **"**</span><span class="sxs-lookup"><span data-stu-id="78a93-183">**"** *<database_name>* **" database details**</span></span>  
     <span data-ttu-id="78a93-184">Отображаются имена файлов, которые необходимо присоединить.</span><span class="sxs-lookup"><span data-stu-id="78a93-184">Displays the names of the files to be attached.</span></span> <span data-ttu-id="78a93-185">Чтобы проверить или изменить путь к файлу, нажмите кнопку **Обзор** ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="78a93-185">To verify or change the pathname of a file, click the **Browse** button (**...**).</span></span>  
  
    > [!NOTE]  
    > <span data-ttu-id="78a93-186">Если файл не существует, в столбце **Сообщение** отображается сообщение «Не найден».</span><span class="sxs-lookup"><span data-stu-id="78a93-186">If a file does not exist, the **Message** column displays "Not found."</span></span> <span data-ttu-id="78a93-187">Если файл журнала не найден, то он существует в другом каталоге или был удален.</span><span class="sxs-lookup"><span data-stu-id="78a93-187">If a log file is not found, it exists in another directory or has been deleted.</span></span> <span data-ttu-id="78a93-188">Необходимо или обновить путь файла в сетке **Сведения о базе данных** таким образом, чтобы этот путь указывал на правильное расположение, или удалить файл журнала из сетки.</span><span class="sxs-lookup"><span data-stu-id="78a93-188">You need to either update the file path in the **database details** grid to point to the correct location or remove the log file from the grid.</span></span> <span data-ttu-id="78a93-189">Если MDF-файл не найден, необходимо обновить путь этого файла в сетке таким образом, чтобы этот путь указывал на правильное расположение.</span><span class="sxs-lookup"><span data-stu-id="78a93-189">If an .ndf data file is not found, you need to update its path in the grid to point to the correct location.</span></span>  
  
     <span data-ttu-id="78a93-190">**Имя исходного файла**</span><span class="sxs-lookup"><span data-stu-id="78a93-190">**Original File Name**</span></span>  
     <span data-ttu-id="78a93-191">Отображается имя присоединенного файла, принадлежащего базе данных.</span><span class="sxs-lookup"><span data-stu-id="78a93-191">Displays the name of the attached file belonging to the database.</span></span>  
  
     <span data-ttu-id="78a93-192">**Тип файла**</span><span class="sxs-lookup"><span data-stu-id="78a93-192">**File Type**</span></span>  
     <span data-ttu-id="78a93-193">Указывается тип файла: **Данные** или **Журнал**.</span><span class="sxs-lookup"><span data-stu-id="78a93-193">Indicates the type of file, **Data** or **Log**.</span></span>  
  
     <span data-ttu-id="78a93-194">**Текущий путь к файлу**</span><span class="sxs-lookup"><span data-stu-id="78a93-194">**Current File Path**</span></span>  
     <span data-ttu-id="78a93-195">Отображается путь к выбранному файлу базы данных.</span><span class="sxs-lookup"><span data-stu-id="78a93-195">Displays the path to the selected database file.</span></span> <span data-ttu-id="78a93-196">Путь может быть изменен вручную.</span><span class="sxs-lookup"><span data-stu-id="78a93-196">The path can be edited manually.</span></span>  
  
     <span data-ttu-id="78a93-197">**Сообщение**</span><span class="sxs-lookup"><span data-stu-id="78a93-197">**Message**</span></span>  
     <span data-ttu-id="78a93-198">Отображается пустое сообщение или гиперссылка "**Файл не найден**".</span><span class="sxs-lookup"><span data-stu-id="78a93-198">Displays either a blank message or a "**File not found**" hyperlink.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="78a93-199">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="78a93-199">Using Transact-SQL</span></span>  
  
### <a name="to-attach-a-database"></a><span data-ttu-id="78a93-200">Присоединение базы данных</span><span class="sxs-lookup"><span data-stu-id="78a93-200">To attach a database</span></span>  
  
1.  <span data-ttu-id="78a93-201">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78a93-201">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="78a93-202">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="78a93-202">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="78a93-203">Используйте инструкцию [Create Database](/sql/t-sql/statements/create-database-sql-server-transact-sql) с предложением `FOR ATTACH` Close.</span><span class="sxs-lookup"><span data-stu-id="78a93-203">Use the [CREATE DATABASE](/sql/t-sql/statements/create-database-sql-server-transact-sql) statement with the `FOR ATTACH` close.</span></span>  
  
     <span data-ttu-id="78a93-204">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="78a93-204">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="78a93-205">В этом примере производится присоединение файлов базы данных [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] с ее последующим переименованием в `MyAdventureWorks`.</span><span class="sxs-lookup"><span data-stu-id="78a93-205">This example attaches the files of the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database and renames the database to `MyAdventureWorks`.</span></span>  
  
    ```sql  
    CREATE DATABASE MyAdventureWorks   
        ON (FILENAME = 'C:\MySQLServer\AdventureWorks_Data.mdf'),   
        (FILENAME = 'C:\MySQLServer\AdventureWorks_Log.ldf')   
        FOR ATTACH;  
    ```  
  
    > [!NOTE]  
    > <span data-ttu-id="78a93-206">Кроме того, можно вызвать хранимую процедуру [sp_attach_db](/sql/relational-databases/system-stored-procedures/sp-attach-db-transact-sql) или [sp_attach_single_file_db](/sql/relational-databases/system-stored-procedures/sp-attach-single-file-db-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="78a93-206">Alternatively, you can use the [sp_attach_db](/sql/relational-databases/system-stored-procedures/sp-attach-db-transact-sql) or [sp_attach_single_file_db](/sql/relational-databases/system-stored-procedures/sp-attach-single-file-db-transact-sql) stored procedure.</span></span> <span data-ttu-id="78a93-207">Но эти расширенные хранимые процедуры в будущих версиях [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]будут удалены.</span><span class="sxs-lookup"><span data-stu-id="78a93-207">However, these procedures will be removed in a future version of Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="78a93-208">Избегайте использования этого компонента в новых разработках и запланируйте изменение существующих приложений, в которых он применяется.</span><span class="sxs-lookup"><span data-stu-id="78a93-208">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span> <span data-ttu-id="78a93-209">Рекомендуется использовать CREATE DATABASE... Вместо этого для присоединения.</span><span class="sxs-lookup"><span data-stu-id="78a93-209">We recommend that you use CREATE DATABASE ... FOR ATTACH instead.</span></span>  
  
##  <a name="follow-up-after-upgrading-a-sql-server-database"></a><a name="FollowUp"></a> <span data-ttu-id="78a93-210">Дальнейшие действия. После обновления базы данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="78a93-210">Follow Up: After Upgrading a SQL Server Database</span></span>  
 <span data-ttu-id="78a93-211">вставить обновление базы данных с помощью метода Attach, база данных немедленно становится доступной и автоматически обновляется.</span><span class="sxs-lookup"><span data-stu-id="78a93-211">fter you upgrade a database by using the attach method, the database becomes available immediately and is automatically upgraded.</span></span> <span data-ttu-id="78a93-212">Если база данных содержит полнотекстовые индексы, то в процессе обновления будет произведен их импорт, сброс или перестроение в зависимости от установленного значения свойства сервера **Режим обновления полнотекстового каталога** .</span><span class="sxs-lookup"><span data-stu-id="78a93-212">If the database has full-text indexes, the upgrade process either imports, resets, or rebuilds them, depending on the setting of the **Full-Text Upgrade Option** server property.</span></span> <span data-ttu-id="78a93-213">Если при обновлении выбран режим **Импортировать** или **Перестроить**, то полнотекстовые индексы во время обновления будут недоступны.</span><span class="sxs-lookup"><span data-stu-id="78a93-213">If the upgrade option is set to **Import** or **Rebuild**, the full-text indexes will be unavailable during the upgrade.</span></span> <span data-ttu-id="78a93-214">В зависимости от объема индексируемых данных процесс импорта может занять несколько часов, а перестроение — в несколько (до десяти) раз больше.</span><span class="sxs-lookup"><span data-stu-id="78a93-214">Depending the amount of data being indexed, importing can take several hours, and rebuilding can take up to ten times longer.</span></span> <span data-ttu-id="78a93-215">Обратите внимание, что если при обновлении выбран режим **Импортировать**, а полнотекстовый каталог недоступен, то связанные с ним полнотекстовые индексы будут перестроены.</span><span class="sxs-lookup"><span data-stu-id="78a93-215">Note also that when the upgrade option is set to **Import**, if a full-text catalog is not available, the associated full-text indexes are rebuilt.</span></span>  
  
<span data-ttu-id="78a93-216">Если уровень совместимости пользовательской базы данных до обновления был 100 или выше, после обновления он останется таким же.</span><span class="sxs-lookup"><span data-stu-id="78a93-216">If the compatibility level of a user database is 100 or higher before upgrade, it remains the same after upgrade.</span></span> <span data-ttu-id="78a93-217">Если уровень совместимости до обновления был 90, в обновленной базе данных он устанавливается в 100, что является минимально поддерживаемым уровнем совместимости в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78a93-217">If the compatibility level is 90 before upgrade, in the upgraded database, the compatibility level is set to 100, which is the lowest supported compatibility level in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="78a93-218">Дополнительные сведения см. в разделе [Уровень совместимости инструкции ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span><span class="sxs-lookup"><span data-stu-id="78a93-218">For more information, see [ALTER DATABASE Compatibility Level &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78a93-219">См. также:</span><span class="sxs-lookup"><span data-stu-id="78a93-219">See Also</span></span>  
 <span data-ttu-id="78a93-220">[CREATE DATABASE (SQL Server Transact-SQL)](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="78a93-220">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="78a93-221">Отсоединение базы данных</span><span class="sxs-lookup"><span data-stu-id="78a93-221">Detach a Database</span></span>](detach-a-database.md)  
  
  
