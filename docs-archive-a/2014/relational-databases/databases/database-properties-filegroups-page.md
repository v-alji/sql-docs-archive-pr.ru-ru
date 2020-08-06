---
title: Свойства базы данных (страница "Файловые группы") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.databaseproperties.filegroups.f1
ms.assetid: 8d06e859-73dd-4019-b6e8-99c5c5297697
author: stevestein
ms.author: sstein
ms.openlocfilehash: d0546a17491ed5d3b36890a605c5faa922c24fe6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658814"
---
# <a name="database-properties-filegroups-page"></a><span data-ttu-id="380f5-102">Свойства базы данных (страница «Файловые группы»)</span><span class="sxs-lookup"><span data-stu-id="380f5-102">Database Properties (Filegroups Page)</span></span>
  <span data-ttu-id="380f5-103">Эта страница используется для просмотра файловых групп или добавления новой файловой группы в выбранную базу данных.</span><span class="sxs-lookup"><span data-stu-id="380f5-103">Use this page to view the filegroups or add a new filegroup to the selected database.</span></span> <span data-ttu-id="380f5-104">Типы файловых групп разделены на файловые группы *строк* , файловые группы данных FILESTREAM и файловые группы, оптимизированные для памяти.</span><span class="sxs-lookup"><span data-stu-id="380f5-104">Filegroup types are separated into *row* filegroups, FILESTREAM data, and memory-optimized filegroups.</span></span>  
  
 <span data-ttu-id="380f5-105">Файловые группы строк содержат обычные данные и файлы журналов.</span><span class="sxs-lookup"><span data-stu-id="380f5-105">Row filegroups contain regular data and log files.</span></span> <span data-ttu-id="380f5-106">Файловые группы данных FILESTREAM содержат файлы данных FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="380f5-106">FILESTREAM data filegroups contain FILESTREAM data files.</span></span> <span data-ttu-id="380f5-107">В этих файлах данных содержатся сведения о способах хранения данных больших двоичных объектов (BLOB) в файловой системе при использовании хранилища Filestream.</span><span class="sxs-lookup"><span data-stu-id="380f5-107">These data files store information about how binary large object (BLOB) data is stored on the file system when you are using FILESTREAM storage.</span></span> <span data-ttu-id="380f5-108">Параметры одинаковы для файловых групп обоих типов.</span><span class="sxs-lookup"><span data-stu-id="380f5-108">The options are the same for both types of filegroups.</span></span>  
  
 <span data-ttu-id="380f5-109">Если хранилище FILESTREAM отключено, то раздел **Filestream** недоступен.</span><span class="sxs-lookup"><span data-stu-id="380f5-109">If FILESTREAM is not enabled, the **Filestream** section will not be available.</span></span> <span data-ttu-id="380f5-110">Хранилище FILESTREAM можно включить в диалоговом окне [Свойства сервера (страница "Дополнительно")](../../database-engine/configure-windows/server-properties-advanced-page.md).</span><span class="sxs-lookup"><span data-stu-id="380f5-110">You can enable FILESTREAM storage by using [Server Properties (Advanced Page)](../../database-engine/configure-windows/server-properties-advanced-page.md).</span></span>  
  
 <span data-ttu-id="380f5-111">Дополнительные сведения об использовании файловых групп строк в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] см. в разделе [Файлы и файловые группы базы данных](database-files-and-filegroups.md).</span><span class="sxs-lookup"><span data-stu-id="380f5-111">For information about how [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses row filegroups, see [Database Files and Filegroups](database-files-and-filegroups.md).</span></span> <span data-ttu-id="380f5-112">Дополнительные сведения о данных и файловых группах FILESTREAM см. в разделе [FILESTREAM (SQL Server)](../blob/filestream-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="380f5-112">For more information about FILESTREAM data and filegroups, see [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).</span></span>  
  
 <span data-ttu-id="380f5-113">Оптимизированные для памяти файловые группы необходимы, когда база данных должна содержать одну или несколько оптимизированных для памяти таблиц.</span><span class="sxs-lookup"><span data-stu-id="380f5-113">Memory-optimized file groups are required for a database to contain one or more memory-optimized tables.</span></span>  
  
## <a name="row-and-filestream-data-filegroup-options"></a><span data-ttu-id="380f5-114">Параметры файловых групп для строк и данных FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="380f5-114">Row and FILESTREAM Data Filegroup Options</span></span>  
 <span data-ttu-id="380f5-115">**имя**;</span><span class="sxs-lookup"><span data-stu-id="380f5-115">**Name**</span></span>  
 <span data-ttu-id="380f5-116">Введите имя файловой группы.</span><span class="sxs-lookup"><span data-stu-id="380f5-116">Enter the name of the filegroup.</span></span>  
  
 <span data-ttu-id="380f5-117">**Файлы**</span><span class="sxs-lookup"><span data-stu-id="380f5-117">**Files**</span></span>  
 <span data-ttu-id="380f5-118">Отображает число файлов в файловой группе.</span><span class="sxs-lookup"><span data-stu-id="380f5-118">Displays the count of files in the filegroup.</span></span>  
  
 <span data-ttu-id="380f5-119">**Только для чтения**</span><span class="sxs-lookup"><span data-stu-id="380f5-119">**Read-only**</span></span>  
 <span data-ttu-id="380f5-120">Выберите, чтобы установить для файловой группы статус «только для чтения».</span><span class="sxs-lookup"><span data-stu-id="380f5-120">Select to set the filegroup to a read-only status.</span></span>  
  
 <span data-ttu-id="380f5-121">**Default**</span><span class="sxs-lookup"><span data-stu-id="380f5-121">**Default**</span></span>  
 <span data-ttu-id="380f5-122">Выберите, чтобы сделать эту файловую группу используемой по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="380f5-122">Select to make this filegroup the default filegroup.</span></span> <span data-ttu-id="380f5-123">Можно организовать одну файловую группу по умолчанию для строк и одну файловую группу по умолчанию для данных FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="380f5-123">You can have one default filegroup for rows and one default filegroup for FILESTREAM data.</span></span>  
  
 <span data-ttu-id="380f5-124">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="380f5-124">**Add**</span></span>  
 <span data-ttu-id="380f5-125">Позволяет добавить новую пустую строку в сетку списка файловых групп базы данных.</span><span class="sxs-lookup"><span data-stu-id="380f5-125">Adds a new blank row to the grid listing filegroups for the database.</span></span>  
  
 <span data-ttu-id="380f5-126">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="380f5-126">**Remove**</span></span>  
 <span data-ttu-id="380f5-127">Позволяет удалить выбранную строку файловой группы из сетки.</span><span class="sxs-lookup"><span data-stu-id="380f5-127">Removes the selected filegroup row from the grid.</span></span>  
  
## <a name="memory-optimized-data-filegroup-options"></a><span data-ttu-id="380f5-128">Параметры файловых групп для данных, оптимизированных для памяти.</span><span class="sxs-lookup"><span data-stu-id="380f5-128">Memory-Optimized Data Filegroup Options</span></span>  
 <span data-ttu-id="380f5-129">**имя**;</span><span class="sxs-lookup"><span data-stu-id="380f5-129">**Name**</span></span>  
 <span data-ttu-id="380f5-130">Введите имя файловой группы, оптимизированной для памяти.</span><span class="sxs-lookup"><span data-stu-id="380f5-130">Enter the name of the memory-optimized filegroup.</span></span>  
  
 <span data-ttu-id="380f5-131">**Файлы файловой группы**</span><span class="sxs-lookup"><span data-stu-id="380f5-131">**Filestream Files**</span></span>  
 <span data-ttu-id="380f5-132">Отображает число файлов (контейнеров) в оптимизированной для памяти файловой группе данных.</span><span class="sxs-lookup"><span data-stu-id="380f5-132">Displays the number of files (containers) in the memory-optimized data filegroup.</span></span> <span data-ttu-id="380f5-133">На странице **Файлы** можно добавлять контейнеры.</span><span class="sxs-lookup"><span data-stu-id="380f5-133">You can add containers in the **Files** page.</span></span>  
  
 <span data-ttu-id="380f5-134">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="380f5-134">**Add**</span></span>  
 <span data-ttu-id="380f5-135">Позволяет добавить новую пустую строку в сетку списка файловых групп базы данных.</span><span class="sxs-lookup"><span data-stu-id="380f5-135">Adds a new blank row to the grid listing filegroups for the database.</span></span>  
  
 <span data-ttu-id="380f5-136">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="380f5-136">**Remove**</span></span>  
 <span data-ttu-id="380f5-137">Позволяет удалить выбранную строку файловой группы из сетки.</span><span class="sxs-lookup"><span data-stu-id="380f5-137">Removes the selected filegroup row from the grid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="380f5-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="380f5-138">See Also</span></span>  
 <span data-ttu-id="380f5-139">[ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="380f5-139">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="380f5-140">sys.databases (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="380f5-140">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
