---
title: Свойства базы данных (страница "Файлы") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.databaseproperties.files.f1
ms.assetid: 3c030e51-db82-4b43-b1e5-8547ddd3de87
author: stevestein
ms.author: sstein
ms.openlocfilehash: 955a17857ce0d847fb712473dddd581a072ab83d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728341"
---
# <a name="database-properties-files-page"></a><span data-ttu-id="d3ea7-102">Свойства базы данных (страница «Файлы»)</span><span class="sxs-lookup"><span data-stu-id="d3ea7-102">Database Properties (Files Page)</span></span>
  <span data-ttu-id="d3ea7-103">Данная страница используется для создания новой базы данных или просмотра и изменения свойств выбранной базы данных.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-103">Use this page to create a new database, or view or modify properties for the selected database.</span></span> <span data-ttu-id="d3ea7-104">Данный раздел относится к странице **Свойства базы данных (страница "Файлы")** для существующих баз данных и к странице **Создание базы данных (страница "Общие")** .</span><span class="sxs-lookup"><span data-stu-id="d3ea7-104">This topic applies to the **Database Properties (Files Page)** for existing databases, and to the **New Database (General Page)**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="d3ea7-105">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="d3ea7-105">UI element list</span></span>  
 <span data-ttu-id="d3ea7-106">**Имя базы данных**</span><span class="sxs-lookup"><span data-stu-id="d3ea7-106">**Database name**</span></span>  
 <span data-ttu-id="d3ea7-107">Добавьте или отобразите имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-107">Add or display the name of the database.</span></span>  
  
 <span data-ttu-id="d3ea7-108">**Владелец**</span><span class="sxs-lookup"><span data-stu-id="d3ea7-108">**Owner**</span></span>  
 <span data-ttu-id="d3ea7-109">Задайте владельца базы данных путем выбора из списка.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-109">Specify the owner of the database by selecting from the list.</span></span>  
  
 <span data-ttu-id="d3ea7-110">**Использовать полнотекстовое индексирование**</span><span class="sxs-lookup"><span data-stu-id="d3ea7-110">**Use full-text indexing**</span></span>  
 <span data-ttu-id="d3ea7-111">Этот флажок установлен и недоступен, так как полнотекстовое индексирование в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]включено всегда.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-111">This check box is checked and disabled because full-text indexing is always enabled in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="d3ea7-112">Дополнительные сведения см. в разделе [Полнотекстовый поиск](../search/full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="d3ea7-112">For more information, see [Full-Text Search](../search/full-text-search.md).</span></span>  
  
 <span data-ttu-id="d3ea7-113">**Файлы базы данных**</span><span class="sxs-lookup"><span data-stu-id="d3ea7-113">**Database Files**</span></span>  
 <span data-ttu-id="d3ea7-114">Добавьте, просмотрите, измените или удалите файлы базы данных для соответствующей базы.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-114">Add, view, modify, or remove database files for the associated database.</span></span> <span data-ttu-id="d3ea7-115">Файлы базы данных имеют следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-115">Database files have the following properties:</span></span>  
  
 <span data-ttu-id="d3ea7-116">**Логическое имя**</span><span class="sxs-lookup"><span data-stu-id="d3ea7-116">**Logical Name**</span></span>  
 <span data-ttu-id="d3ea7-117">Введите или измените имя файла.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-117">Enter or modify the name of the file.</span></span>  
  
 <span data-ttu-id="d3ea7-118">**Тип файла**</span><span class="sxs-lookup"><span data-stu-id="d3ea7-118">**File Type**</span></span>  
 <span data-ttu-id="d3ea7-119">Выберите тип файла из списка.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-119">Select the file type from the list.</span></span> <span data-ttu-id="d3ea7-120">Тип файла может иметь значение **Данные**, **Журнал**или **Данные FILESTREAM**.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-120">The file type can be **Data**, **Log**, or **Filestream Data**.</span></span> <span data-ttu-id="d3ea7-121">Нельзя изменить тип существующего файла.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-121">You cannot modify the file type of an existing file.</span></span>  
  
 <span data-ttu-id="d3ea7-122">Если производится добавление файлов (контейнеров) в файловую группу, оптимизированную для памяти, используйте тип **Данные Filestream** .</span><span class="sxs-lookup"><span data-stu-id="d3ea7-122">Select **Filestream Data** if you are adding files (containers) to a memory-optimized filegroup.</span></span>  
  
 <span data-ttu-id="d3ea7-123">Для добавления файлов (контейнеров) в файловую группу Filestream параметр FILESTREAM должен быть включен.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-123">To add files (containers) to a Filestream data filegroup, FILESTREAM must be enabled.</span></span> <span data-ttu-id="d3ea7-124">Хранилище FILESTREAM можно включить в диалоговом окне [Свойства сервера (страница "Дополнительно")](../../database-engine/configure-windows/server-properties-advanced-page.md) .</span><span class="sxs-lookup"><span data-stu-id="d3ea7-124">You can enable FILESTREAM by using the [Server Properties (Advanced Page)](../../database-engine/configure-windows/server-properties-advanced-page.md) dialog box.</span></span>  
  
 <span data-ttu-id="d3ea7-125">**Файловая группа**</span><span class="sxs-lookup"><span data-stu-id="d3ea7-125">**Filegroup**</span></span>  
 <span data-ttu-id="d3ea7-126">Выберите файловую группу из списка.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-126">Select the filegroup for the file from the list.</span></span> <span data-ttu-id="d3ea7-127">По умолчанию это файловая группа PRIMARY.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-127">By default, the filegroup is PRIMARY.</span></span> <span data-ttu-id="d3ea7-128">Можно создать новую файловую группу, выбрав **\<new filegroup>** и введя данные об этой группе файлов в диалоговом окне **Создание файловой группы**.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-128">You can create a new filegroup by selecting **\<new filegroup>** and entering information about the filegroup in the **New Filegroup** dialog box.</span></span> <span data-ttu-id="d3ea7-129">Новую файловую группу можно также создать на странице **Файловая группа** .</span><span class="sxs-lookup"><span data-stu-id="d3ea7-129">A new filegroup can also be created on the **Filegroup** page.</span></span> <span data-ttu-id="d3ea7-130">Нельзя изменить файловую группу для существующего файла.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-130">You cannot modify the filegroup of an existing file.</span></span>  
  
 <span data-ttu-id="d3ea7-131">При добавлении файлов (контейнеров) в оптимизированную для памяти файловую группу в поле **Файловая группа** будет вноситься имя оптимизированной для памяти файловой группы базы данных.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-131">When adding files (containers) to a memory-optimized filegroup, the **Filegroup** field will be populated with the name of the database's memory-optimized filegroup.</span></span>  
  
 <span data-ttu-id="d3ea7-132">**Начальный размер**</span><span class="sxs-lookup"><span data-stu-id="d3ea7-132">**Initial Size**</span></span>  
 <span data-ttu-id="d3ea7-133">Введите или измените начальный размер файла в мегабайтах.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-133">Enter or modify the initial size for the file in megabytes.</span></span> <span data-ttu-id="d3ea7-134">Это значение по умолчанию соответствует значению для базы данных **model** .</span><span class="sxs-lookup"><span data-stu-id="d3ea7-134">By default, this is the value of the **model** database.</span></span>  
  
 <span data-ttu-id="d3ea7-135">Данное поле неприменимо для файлов FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-135">This field is not valid for FILESTREAM files.</span></span>  
  
 <span data-ttu-id="d3ea7-136">Для файлов, состоящих в оптимизированных для памяти файловых группах, значение в этом поле не может быть изменено.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-136">For files in memory-optimized filegroups, this field cannot be modified.</span></span>  
  
 <span data-ttu-id="d3ea7-137">**Авторасширение**</span><span class="sxs-lookup"><span data-stu-id="d3ea7-137">**Autogrowth**</span></span>  
 <span data-ttu-id="d3ea7-138">Выбор или отображение свойств авторасширения для файла.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-138">Select or display the autogrowth properties for the file.</span></span> <span data-ttu-id="d3ea7-139">Эти свойства определяют способ расширения файла после достижения файлом своего максимального размера.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-139">These properties control how the file expands when its maximum file size is reached.</span></span> <span data-ttu-id="d3ea7-140">Для изменения значений авторасширения нажмите кнопку изменения рядом со свойствами автоматического расширения нужного файла и измените значения в диалоговом окне **Изменение параметров авторасширения** .</span><span class="sxs-lookup"><span data-stu-id="d3ea7-140">To edit autogrowth values, click the edit button next to the autogrowth properties for the file that you want, and change the values in the **Change Autogrowth** dialog box.</span></span> <span data-ttu-id="d3ea7-141">По умолчанию это значения базы данных **model** .</span><span class="sxs-lookup"><span data-stu-id="d3ea7-141">By default, these are the values of the **model** database.</span></span>  
  
 <span data-ttu-id="d3ea7-142">Данное поле неприменимо для файлов FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-142">This field is not valid for FILESTREAM files.</span></span>  
  
 <span data-ttu-id="d3ea7-143">Для файлов, состоящих в оптимизированных для памяти файловых группах, это поле должно иметь значение **Неограниченно**.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-143">For files in memory-optimized filegroups, this field should be **Unlimited**.</span></span>  
  
 <span data-ttu-id="d3ea7-144">**Путь**</span><span class="sxs-lookup"><span data-stu-id="d3ea7-144">**Path**</span></span>  
 <span data-ttu-id="d3ea7-145">Отображает путь к выбранному файлу.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-145">Displays the path of the selected file.</span></span> <span data-ttu-id="d3ea7-146">Для задания пути к новому файлу нажмите кнопку редактирования рядом с путем к файлу, а затем перейдите в папку назначения.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-146">To specify a path for a new file, click the edit button next to the path for the file, and navigate to the destination folder.</span></span> <span data-ttu-id="d3ea7-147">Нельзя изменить путь к существующему файлу.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-147">You cannot modify the path of an existing file.</span></span>  
  
 <span data-ttu-id="d3ea7-148">Путь для файлов FILESTREAM является папкой.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-148">For FILESTREAM files, the path is a folder.</span></span> <span data-ttu-id="d3ea7-149">Компонент [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] создаст базовые файлы в этой папке.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-149">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] will create the underlying files in this folder.</span></span>  
  
 <span data-ttu-id="d3ea7-150">**Имя файла**</span><span class="sxs-lookup"><span data-stu-id="d3ea7-150">**File Name**</span></span>  
 <span data-ttu-id="d3ea7-151">Отображает имя файла.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-151">Displays the name of the file.</span></span>  
  
 <span data-ttu-id="d3ea7-152">Данное поле неприменимо для файлов FILESTREAM, включая файлы, состоящие в оптимизированных для памяти файловых группах.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-152">This field is not valid for FILESTREAM files, including files in memory-optimized filegroups.</span></span>  
  
 <span data-ttu-id="d3ea7-153">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="d3ea7-153">**Add**</span></span>  
 <span data-ttu-id="d3ea7-154">Добавьте новый файл к базе данных.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-154">Add a new file to the database.</span></span>  
  
 <span data-ttu-id="d3ea7-155">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="d3ea7-155">**Remove**</span></span>  
 <span data-ttu-id="d3ea7-156">Удалите выбранный файл из базы данных.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-156">Delete the selected file from the database.</span></span> <span data-ttu-id="d3ea7-157">Файл можно удалить, только если он пуст.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-157">A file cannot be removed unless it is empty.</span></span> <span data-ttu-id="d3ea7-158">Первичный файл данных и файл журнала удалить нельзя.</span><span class="sxs-lookup"><span data-stu-id="d3ea7-158">The primary data file and log file cannot be removed.</span></span>  
  
 <span data-ttu-id="d3ea7-159">Дополнительные сведения о файлах см. в разделе [Database Files and Filegroups](database-files-and-filegroups.md).</span><span class="sxs-lookup"><span data-stu-id="d3ea7-159">For information about files, see [Database Files and Filegroups](database-files-and-filegroups.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3ea7-160">См. также:</span><span class="sxs-lookup"><span data-stu-id="d3ea7-160">See Also</span></span>  
 <span data-ttu-id="d3ea7-161">[ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d3ea7-161">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="d3ea7-162">sys.databases (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="d3ea7-162">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
