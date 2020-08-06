---
title: Создание базы данных (мастер импорта и экспорта SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.createdatabase.f1
ms.assetid: 56a8a79f-086c-4bdc-8888-0045bb4b0cbf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 617b3fe10a17ae2d8659b51e85cdb3fed4470506
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666155"
---
# <a name="create-database-sql-server-import-and-export-wizard"></a><span data-ttu-id="95e8a-102">Создание базы данных (мастер импорта и экспорта SQL Server)</span><span class="sxs-lookup"><span data-stu-id="95e8a-102">Create Database (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="95e8a-103">Используйте страницу **Создание базы данных** , чтобы определить новую базу данных для целевого файла.</span><span class="sxs-lookup"><span data-stu-id="95e8a-103">Use the **Create Database** page to define a new database for a destination file.</span></span>  
  
 <span data-ttu-id="95e8a-104">Эта страница предоставляет подмножество параметров, доступных при создании базы данных.</span><span class="sxs-lookup"><span data-stu-id="95e8a-104">This page offers a subset of the available options for creating a new database.</span></span> <span data-ttu-id="95e8a-105">Чтобы просмотреть все параметры, используйте [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="95e8a-105">To view all the options, use [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="95e8a-106">Дополнительные сведения о работе этого мастера см. в разделе [Мастер импорта и экспорта SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="95e8a-106">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="95e8a-107">Дополнительные сведения о параметрах запуска мастера и о разрешениях, необходимых для успешного запуска мастера, см. [в разделе Запуск мастера импорта и экспорта SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="95e8a-107">To learn about the options for starting the wizard, and about the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="95e8a-108">Назначение мастера импорта и экспорта SQL Server заключается в копировании данных из исходного расположения в целевое.</span><span class="sxs-lookup"><span data-stu-id="95e8a-108">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="95e8a-109">Этот мастер может также создать целевую базу данных и целевые таблицы.</span><span class="sxs-lookup"><span data-stu-id="95e8a-109">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="95e8a-110">Однако если нужно скопировать несколько баз данных, таблиц или других объектов базы данных, следует использовать мастер копирования баз данных.</span><span class="sxs-lookup"><span data-stu-id="95e8a-110">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="95e8a-111">Дополнительные сведения см. в статье [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="95e8a-111">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="95e8a-112">Параметры</span><span class="sxs-lookup"><span data-stu-id="95e8a-112">Options</span></span>  
 <span data-ttu-id="95e8a-113">**Название**</span><span class="sxs-lookup"><span data-stu-id="95e8a-113">**Name**</span></span>  
 <span data-ttu-id="95e8a-114">Введите уникальное имя для базы данных назначения SQL Server.</span><span class="sxs-lookup"><span data-stu-id="95e8a-114">Provide a unique name for the destination SQL Server database.</span></span> <span data-ttu-id="95e8a-115">При вводе имени обязательно следуйте соглашению об именах SQL Server.</span><span class="sxs-lookup"><span data-stu-id="95e8a-115">Make sure that you follow SQL Server conventions when you name this database.</span></span>  
  
 <span data-ttu-id="95e8a-116">**Имя файла данных**</span><span class="sxs-lookup"><span data-stu-id="95e8a-116">**Data file name**</span></span>  
 <span data-ttu-id="95e8a-117">Просмотрите имя файла данных.</span><span class="sxs-lookup"><span data-stu-id="95e8a-117">View the name of the data file.</span></span> <span data-ttu-id="95e8a-118">Это имя создается на основе ранее указанного имени базы данных.</span><span class="sxs-lookup"><span data-stu-id="95e8a-118">This is derived from the database name you provided earlier.</span></span>  
  
 <span data-ttu-id="95e8a-119">**Имя файла журнала**</span><span class="sxs-lookup"><span data-stu-id="95e8a-119">**Log file name**</span></span>  
 <span data-ttu-id="95e8a-120">Просмотрите имя файла журнала.</span><span class="sxs-lookup"><span data-stu-id="95e8a-120">View the name of the log file.</span></span> <span data-ttu-id="95e8a-121">Это имя создается на основе ранее указанного имени базы данных.</span><span class="sxs-lookup"><span data-stu-id="95e8a-121">This is derived from the database name you provided earlier.</span></span>  
  
 <span data-ttu-id="95e8a-122">**Начальный размер (файл данных)**</span><span class="sxs-lookup"><span data-stu-id="95e8a-122">**Initial size (data file)**</span></span>  
 <span data-ttu-id="95e8a-123">Задайте количество мегабайтов для начального размера файла данных.</span><span class="sxs-lookup"><span data-stu-id="95e8a-123">Specify the number of megabytes for the initial size of the data file.</span></span>  
  
 <span data-ttu-id="95e8a-124">**Рост не разрешен (файл данных)**</span><span class="sxs-lookup"><span data-stu-id="95e8a-124">**No growth allowed (data file)**</span></span>  
 <span data-ttu-id="95e8a-125">Укажите, может ли файл данных выйти за пределы заданного начального размера.</span><span class="sxs-lookup"><span data-stu-id="95e8a-125">Indicate whether the data file can grow beyond the specified initial size.</span></span>  
  
 <span data-ttu-id="95e8a-126">**Процент роста (файл данных)**</span><span class="sxs-lookup"><span data-stu-id="95e8a-126">**Grow by percentage (data file)**</span></span>  
 <span data-ttu-id="95e8a-127">Задайте процентный показатель, на который может возрастать файл данных.</span><span class="sxs-lookup"><span data-stu-id="95e8a-127">Specify a percentage by which the data file can grow.</span></span>  
  
 <span data-ttu-id="95e8a-128">**Размер роста (файл данных)**</span><span class="sxs-lookup"><span data-stu-id="95e8a-128">**Grow by size (data file)**</span></span>  
 <span data-ttu-id="95e8a-129">Задайте количество мегабайтов, на которое может возрастать файл данных.</span><span class="sxs-lookup"><span data-stu-id="95e8a-129">Specify a number of megabytes by which the data file can grow.</span></span>  
  
 <span data-ttu-id="95e8a-130">**Начальный размер (файл журнала)**</span><span class="sxs-lookup"><span data-stu-id="95e8a-130">**Initial size (log file)**</span></span>  
 <span data-ttu-id="95e8a-131">Задайте количество мегабайтов для начального размера файла журнала.</span><span class="sxs-lookup"><span data-stu-id="95e8a-131">Specify the number of megabytes for the initial size of the log file.</span></span>  
  
 <span data-ttu-id="95e8a-132">**Рост недопустим (файл журнала)**</span><span class="sxs-lookup"><span data-stu-id="95e8a-132">**No growth allowed (log file)**</span></span>  
 <span data-ttu-id="95e8a-133">Укажите, может ли файл журнала выйти за пределы заданного начального размера.</span><span class="sxs-lookup"><span data-stu-id="95e8a-133">Indicate whether the log file can grow beyond the specified initial size.</span></span>  
  
 <span data-ttu-id="95e8a-134">**Процент роста (файл журнала)**</span><span class="sxs-lookup"><span data-stu-id="95e8a-134">**Grow by percentage (log file)**</span></span>  
 <span data-ttu-id="95e8a-135">Задайте процентный показатель, на который может возрастать файл журнала.</span><span class="sxs-lookup"><span data-stu-id="95e8a-135">Specify a percentage by which the log file can grow.</span></span>  
  
 <span data-ttu-id="95e8a-136">**Размер роста (файл журнала)**</span><span class="sxs-lookup"><span data-stu-id="95e8a-136">**Grow by size (log file)**</span></span>  
 <span data-ttu-id="95e8a-137">Задайте количество мегабайтов, на которое может возрастать файл журнала.</span><span class="sxs-lookup"><span data-stu-id="95e8a-137">Specify a number of megabytes by which the log file can grow.</span></span>  
  
  
