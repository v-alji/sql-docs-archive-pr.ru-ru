---
title: Увеличение размера базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- databases [SQL Server], size
- increasing database size
- database size [SQL Server], increasing
- size [SQL Server], databases
ms.assetid: 14f4206d-3afa-4ba9-9849-23e81d63306d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 71dcb00b3f5525f7059fc54911baed929f763008
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751087"
---
# <a name="increase-the-size-of-a-database"></a><span data-ttu-id="27655-102">Увеличение размера базы данных</span><span class="sxs-lookup"><span data-stu-id="27655-102">Increase the Size of a Database</span></span>
  <span data-ttu-id="27655-103">Этот подраздел описывает, как увеличить размер базы данных [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="27655-103">This topic describes how to increase the size of a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="27655-104">База данных расширяется или путем увеличения размера существующих данных либо файла журнала, или путем добавления нового файла к базе данных.</span><span class="sxs-lookup"><span data-stu-id="27655-104">The database is expanded by either increasing the size of an existing data or log file or by adding a new file to the database.</span></span>  
  
 <span data-ttu-id="27655-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="27655-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="27655-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="27655-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="27655-107">Ограничения</span><span class="sxs-lookup"><span data-stu-id="27655-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="27655-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="27655-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="27655-109">**Увеличение размера базы данных с помощью следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="27655-109">**To increase the size of a database, using:**</span></span>  
  
     [<span data-ttu-id="27655-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="27655-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="27655-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="27655-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="27655-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="27655-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="27655-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="27655-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="27655-114">Добавить или удалить файл во время выполнения инструкции BACKUP невозможно.</span><span class="sxs-lookup"><span data-stu-id="27655-114">You cannot add or remove a file while a BACKUP statement is running.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="27655-115">безопасность</span><span class="sxs-lookup"><span data-stu-id="27655-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="27655-116">Permissions</span><span class="sxs-lookup"><span data-stu-id="27655-116">Permissions</span></span>  
 <span data-ttu-id="27655-117">Необходимо разрешение ALTER на базу данных.</span><span class="sxs-lookup"><span data-stu-id="27655-117">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="27655-118">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="27655-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-increase-the-size-of-a-database"></a><span data-ttu-id="27655-119">Увеличение размера базы данных</span><span class="sxs-lookup"><span data-stu-id="27655-119">To increase the size of a database</span></span>  
  
1.  <span data-ttu-id="27655-120">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]и разверните его.</span><span class="sxs-lookup"><span data-stu-id="27655-120">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="27655-121">Разверните узел **Базы данных**, щелкните правой кнопкой мыши базу данных, размер которой необходимо увеличить, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="27655-121">Expand **Databases**, right-click the database to increase, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="27655-122">В окне **Свойства базы данных**выберите страницу **Файлы** .</span><span class="sxs-lookup"><span data-stu-id="27655-122">In **Database Properties**, select the **Files** page.</span></span>  
  
4.  <span data-ttu-id="27655-123">Чтобы увеличить размер существующего файла, увеличьте значение в столбце **Исходный размер (МБ)** для файла.</span><span class="sxs-lookup"><span data-stu-id="27655-123">To increase the size of an existing file, increase the value in the **Initial Size (MB)** column for the file.</span></span> <span data-ttu-id="27655-124">Необходимо увеличить размер базы данных, по крайней мере, на 1 мегабайт.</span><span class="sxs-lookup"><span data-stu-id="27655-124">You must increase the size of the database by at least 1 megabyte.</span></span>  
  
5.  <span data-ttu-id="27655-125">Чтобы увеличить размер базы данных путем добавления нового файла, нажмите кнопку **Добавить** и введите значения для нового файла.</span><span class="sxs-lookup"><span data-stu-id="27655-125">To increase the size of the database by adding a new file, click **Add** and then enter the values for the new file.</span></span> <span data-ttu-id="27655-126">Дополнительные сведения см. в статье [AДобавление файлов данных или журналов в базу данных](add-data-or-log-files-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="27655-126">For more information, see [Add Data or Log Files to a Database](add-data-or-log-files-to-a-database.md).</span></span>  
  
6.  <span data-ttu-id="27655-127">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="27655-127">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="27655-128">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="27655-128">Using Transact-SQL</span></span>  
  
#### <a name="to-increase-the-size-of-a-database"></a><span data-ttu-id="27655-129">Увеличение размера базы данных</span><span class="sxs-lookup"><span data-stu-id="27655-129">To increase the size of a database</span></span>  
  
1.  <span data-ttu-id="27655-130">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="27655-130">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="27655-131">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="27655-131">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="27655-132">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="27655-132">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="27655-133">В этом примере увеличивается размер файла `test1dat3`.</span><span class="sxs-lookup"><span data-stu-id="27655-133">This example increases the size of the file `test1dat3`.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase5](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase5)]  
  
 <span data-ttu-id="27655-134">Дополнительные сведения см. в разделе [Параметры инструкции ALTER DATABASE для файлов и файловых групп (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span><span class="sxs-lookup"><span data-stu-id="27655-134">For more examples, see [ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27655-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="27655-135">See Also</span></span>  
 <span data-ttu-id="27655-136">[Добавление файлов данных или журналов в базу данных](add-data-or-log-files-to-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="27655-136">[Add Data or Log Files to a Database](add-data-or-log-files-to-a-database.md) </span></span>  
 [<span data-ttu-id="27655-137">Сжатие базы данных</span><span class="sxs-lookup"><span data-stu-id="27655-137">Shrink a Database</span></span>](shrink-a-database.md)  
  
  
