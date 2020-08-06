---
title: Удаление файлов данных или журналов из базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], files
- deleting files
- removing files
- removing data
- data deletions [SQL Server]
- file deletion [SQL Server]
- deleting data
ms.assetid: 0db4018c-ce2c-4ba1-bb29-1e4f3791c925
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6f7bd170e085e9bc94b00446545850e905efaa34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751095"
---
# <a name="delete-data-or-log-files-from-a-database"></a><span data-ttu-id="4a715-102">Удаление файлов данных или журнала из базы данных</span><span class="sxs-lookup"><span data-stu-id="4a715-102">Delete Data or Log Files from a Database</span></span>
  <span data-ttu-id="4a715-103">В данном разделе содержатся инструкции по удалению файлов данных или журналов в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] при помощи [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a715-103">This topic describes how to delete data or log files in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4a715-104">Перед началом</span><span class="sxs-lookup"><span data-stu-id="4a715-104">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="4a715-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="4a715-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="4a715-106">Чтобы можно было удалить файл, он должен быть пустым.</span><span class="sxs-lookup"><span data-stu-id="4a715-106">A file must be empty before it can be deleted.</span></span> <span data-ttu-id="4a715-107">Дополнительные сведения см. в разделе [Сжатие файла](shrink-a-file.md).</span><span class="sxs-lookup"><span data-stu-id="4a715-107">For more information, see [Shrink a File](shrink-a-file.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4a715-108">безопасность</span><span class="sxs-lookup"><span data-stu-id="4a715-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4a715-109">Permissions</span><span class="sxs-lookup"><span data-stu-id="4a715-109">Permissions</span></span>  
 <span data-ttu-id="4a715-110">Необходимо разрешение ALTER на базу данных.</span><span class="sxs-lookup"><span data-stu-id="4a715-110">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4a715-111">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4a715-111">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-data-or-log-files-from-a-database"></a><span data-ttu-id="4a715-112">Удаление файлов данных или журнала из базы данных</span><span class="sxs-lookup"><span data-stu-id="4a715-112">To delete data or log files from a database</span></span>  
  
1.  <span data-ttu-id="4a715-113">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] и разверните его.</span><span class="sxs-lookup"><span data-stu-id="4a715-113">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="4a715-114">Раскройте список **Базы данных**, щелкните правой кнопкой мыши базу данных, из которой удаляется файл, а затем выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="4a715-114">Expand **Databases**, right-click the database from which to delete the file, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="4a715-115">Выберите страницу **Файлы** .</span><span class="sxs-lookup"><span data-stu-id="4a715-115">Select the **Files** page.</span></span>  
  
4.  <span data-ttu-id="4a715-116">В списке **Файлы базы данных** выберите файл для удаления и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="4a715-116">In the **Database files** grid, select the file to delete and then click **Remove**.</span></span>  
  
5.  <span data-ttu-id="4a715-117">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4a715-117">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4a715-118">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4a715-118">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-data-or-log-files-from-a-database"></a><span data-ttu-id="4a715-119">Удаление файлов данных или журнала из базы данных</span><span class="sxs-lookup"><span data-stu-id="4a715-119">To delete data or log files from a database</span></span>  
  
1.  <span data-ttu-id="4a715-120">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a715-120">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4a715-121">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="4a715-121">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4a715-122">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="4a715-122">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="4a715-123">В этом примере удаляется файл `test1dat4`.</span><span class="sxs-lookup"><span data-stu-id="4a715-123">This example removes the file `test1dat4`.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase4](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase4)]  
  
 <span data-ttu-id="4a715-124">Дополнительные сведения см. в разделе [Параметры инструкции ALTER DATABASE для файлов и файловых групп (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span><span class="sxs-lookup"><span data-stu-id="4a715-124">For more examples, see [ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a715-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="4a715-125">See Also</span></span>  
 <span data-ttu-id="4a715-126">[Сжатие базы данных](shrink-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="4a715-126">[Shrink a Database](shrink-a-database.md) </span></span>  
 [<span data-ttu-id="4a715-127">Добавление файлов данных или журналов в базу данных</span><span class="sxs-lookup"><span data-stu-id="4a715-127">Add Data or Log Files to a Database</span></span>](add-data-or-log-files-to-a-database.md)  
  
  
