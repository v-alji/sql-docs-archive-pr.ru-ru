---
title: Таблицы FileTable (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 07/06/2016
ms.prod: sql-server-2014
ms.technology: filestream
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], overview
- FileTables [SQL Server]
- FileTable [SQL Server], see FileTables [SQL Server]
- FileTable [SQL Server]
ms.assetid: a57b629c-e9ed-48fd-9a48-ed3787d80c8f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6c0a38f0e947b0c4f68a49e13a40071f6a30cd07
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740061"
---
# <a name="filetables-sql-server"></a><span data-ttu-id="765d3-102">Таблицы FileTable (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="765d3-102">FileTables (SQL Server)</span></span>
  <span data-ttu-id="765d3-103">Функция FileTable обеспечивает поддержку пространства имен файлов Windows и совместимость с приложениями Windows для файлов данных, хранящихся в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="765d3-103">The FileTable feature brings support for the Windows file namespace and compatibility with Windows applications to the file data stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="765d3-104">Таблица FileTable позволяет приложению интегрировать свои компоненты хранения и управления данными, а также обеспечивает работу интегрированных служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , включая полнотекстовый и семантический поиск, с неструктурированными данными и метаданными.</span><span class="sxs-lookup"><span data-stu-id="765d3-104">FileTable lets an application integrate its storage and data management components, and provides integrated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services - including full-text search and semantic search - over unstructured data and metadata.</span></span>  
  
 <span data-ttu-id="765d3-105">Иными словами, появляется возможность хранить файлы и документы в специальных таблицах на [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , называемых таблицами FileTable, но при этом доступ к ним возможен из приложений Windows без внесения каких-либо изменений в эти приложения, как если бы они хранились в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="765d3-105">In other words, you can store files and documents in special tables in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] called FileTables, but access them from Windows applications as if they were stored in the file system, without making any changes to your client applications.</span></span>  
  
 <span data-ttu-id="765d3-106">Функция FileTable построена на основе технологии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="765d3-106">The FileTable feature builds on top of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] FILESTREAM technology.</span></span> <span data-ttu-id="765d3-107">Дополнительные сведения о FILESTREAM см. в разделе [FILESTREAM (SQL Server)](filestream-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="765d3-107">To learn more about FILESTREAM, see [FILESTREAM &#40;SQL Server&#41;](filestream-sql-server.md).</span></span>  
  
##  <a name="benefits-of-the-filetable-feature"></a><a name="Goals"></a> <span data-ttu-id="765d3-108">Преимущества функции FileTable</span><span class="sxs-lookup"><span data-stu-id="765d3-108">Benefits of the FileTable Feature</span></span>  
 <span data-ttu-id="765d3-109">Таблицы FileTable имеют следующее назначение.</span><span class="sxs-lookup"><span data-stu-id="765d3-109">The goals of the FileTable feature include the following:</span></span>  
  
-   <span data-ttu-id="765d3-110">Совместимость с API-интерфейсами Windows для файлов данных, хранящихся в базе данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="765d3-110">Windows API compatibility for file data stored within a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="765d3-111">Совместимость с API-интерфейсами Windows включает следующее.</span><span class="sxs-lookup"><span data-stu-id="765d3-111">Windows API compatibility includes the following:</span></span>  
  
    -   <span data-ttu-id="765d3-112">Потоковый доступ без транзакций и обновление на месте с заменой данных FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="765d3-112">Non-transactional streaming access and in-place updates to FILESTREAM data.</span></span>  
  
    -   <span data-ttu-id="765d3-113">Иерархическое пространство имен для каталогов и файлов.</span><span class="sxs-lookup"><span data-stu-id="765d3-113">A hierarchical namespace of directories and files.</span></span>  
  
    -   <span data-ttu-id="765d3-114">Хранение атрибутов файлов, таких как дата создания и дата изменения.</span><span class="sxs-lookup"><span data-stu-id="765d3-114">Storage of file attributes, such as created date and modified date.</span></span>  
  
    -   <span data-ttu-id="765d3-115">Поддержка API-интерфейсов Windows для управления файлами и каталогами.</span><span class="sxs-lookup"><span data-stu-id="765d3-115">Support for Windows file and directory management APIs.</span></span>  
  
-   <span data-ttu-id="765d3-116">Совместимость с другими функциями [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , включая средства управления, службы и возможности реляционных запросов через FILESTREAM и данные атрибутов файлов.</span><span class="sxs-lookup"><span data-stu-id="765d3-116">Compatibility with other [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] features including management tools, services, and relational query capabilities over FILESTREAM and file attribute data.</span></span>  
  
 <span data-ttu-id="765d3-117">Таким образом, таблицы FileTable позволяют перешагнуть барьер, препятствовавший использованию [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для хранения неструктурированных данных и управления данными, которые в настоящее время размещаются в виде файлов на файловом сервере.</span><span class="sxs-lookup"><span data-stu-id="765d3-117">Thus FileTables remove a significant barrier to the use of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for the storage and management of unstructured data that is currently residing as files on file servers.</span></span> <span data-ttu-id="765d3-118">Предприятия получили возможность перенести данные с файловых серверов в таблицы FileTable, чтобы пользоваться и преимуществами интегрированного администрирования, и преимуществами служб, предоставляемыми [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="765d3-118">Enterprises can move this data from file servers into FileTables to take advantage of integrated administration and services provided by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="765d3-119">В то же время сохраняется совместимость с существующими приложениями Windows, рассматривающими данные как файлы в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="765d3-119">At the same time, they can maintain Windows application compatibility for their existing Windows applications that see this data as files in the file system.</span></span>  
    
##  <a name="what-is-a-filetable"></a><a name="Description"></a> <span data-ttu-id="765d3-120">Что такое таблица FileTable?</span><span class="sxs-lookup"><span data-stu-id="765d3-120">What Is a FileTable?</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="765d3-121">предоставляет специальные **таблицы файлов**, которые также называются таблицами **FileTable**, для приложений, требующих хранения файлов и каталогов в базе данных, совместимости с API-интерфейсами Windows и нетранзакционного доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="765d3-121">provides a special **table of files**, also referred to as a **FileTable**, for applications that require file and directory storage in the database, with Windows API compatibility and non-transactional access.</span></span> <span data-ttu-id="765d3-122">Таблицы FileTable являются специализированными пользовательскими таблицами с предварительно определенной схемой для хранения данных FILESTREAM, а также сведений об иерархии файлов и каталогов и атрибутах файлов.</span><span class="sxs-lookup"><span data-stu-id="765d3-122">A FileTable is a specialized user table with a pre-defined schema that stores FILESTREAM data, as well as file and directory hierarchy information and file attributes.</span></span>  
  
 <span data-ttu-id="765d3-123">Таблицы FileTable обеспечивают следующие функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="765d3-123">A FileTable provides the following functionality:</span></span>  
  
-   <span data-ttu-id="765d3-124">Таблица FileTable представляет иерархию файлов и каталогов.</span><span class="sxs-lookup"><span data-stu-id="765d3-124">A FileTable represents a hierarchy of directories and files.</span></span> <span data-ttu-id="765d3-125">Она содержит данные, относящиеся ко всем узлам в иерархии для папок и файлов, содержащихся в них.</span><span class="sxs-lookup"><span data-stu-id="765d3-125">It stores data related to all the nodes in that hierarchy, for both directories and the files they contain.</span></span> <span data-ttu-id="765d3-126">Эта иерархия начинается с корневого каталога, указанного при создании FileTable.</span><span class="sxs-lookup"><span data-stu-id="765d3-126">This hierarchy starts from a root directory that you specify when you create the FileTable.</span></span>  
  
-   <span data-ttu-id="765d3-127">Каждая строка в таблице FileTable представляет файл или каталог.</span><span class="sxs-lookup"><span data-stu-id="765d3-127">Every row in a FileTable represents a file or a directory.</span></span>  
  
-   <span data-ttu-id="765d3-128">Каждая строка содержит следующие элементы.</span><span class="sxs-lookup"><span data-stu-id="765d3-128">Every row contains the following items.</span></span> <span data-ttu-id="765d3-129">Дополнительные сведения о схеме таблиц FileTable см. в разделе [FileTable Schema](filetable-schema.md).</span><span class="sxs-lookup"><span data-stu-id="765d3-129">For more information about the schema of a FileTable, see [FileTable Schema](filetable-schema.md).</span></span>  
  
    -   <span data-ttu-id="765d3-130">Столбец**file_stream** для потоковых данных и идентификатор **stream_id** (GUID).</span><span class="sxs-lookup"><span data-stu-id="765d3-130">A**file_stream** column for stream data and a **stream_id** (GUID) identifier.</span></span> <span data-ttu-id="765d3-131">(Для каталога значение в столбце **file_stream** равно NULL.)</span><span class="sxs-lookup"><span data-stu-id="765d3-131">(The **file_stream** column is NULL for a directory.)</span></span>  
  
    -   <span data-ttu-id="765d3-132">Столбцы **path_locator** и **parent_path_locator** для представления и обслуживания иерархии файлов и каталогов.</span><span class="sxs-lookup"><span data-stu-id="765d3-132">Both **path_locator** and **parent_path_locator** columns for representing and maintaining the file and directory hierarchy.</span></span>  
  
    -   <span data-ttu-id="765d3-133">10 атрибутов файлов, таких как дата создания и дата изменения, которые требуются для API-интерфейсов файлового ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="765d3-133">10 file attributes such as created date and modified date that are useful with file I/O APIs.</span></span>  
  
    -   <span data-ttu-id="765d3-134">Столбец типа, который поддерживает полнотекстовый поиск и семантический поиск по файлам и документам.</span><span class="sxs-lookup"><span data-stu-id="765d3-134">A type column that supports full-text search and semantic search over files and documents.</span></span>  
  
-   <span data-ttu-id="765d3-135">В таблицах FileTable применяются определенные системные ограничения и триггеры, поддерживающие семантику пространства имен файлов.</span><span class="sxs-lookup"><span data-stu-id="765d3-135">A FileTable enforces certain system-defined constraints and triggers to maintain file namespace semantics.</span></span>  
  
-   <span data-ttu-id="765d3-136">Если база данных настроена для нетранзакционного доступа, то иерархия файлов и каталогов, представленная в таблице FileTable, отображается с помощью общего ресурса FILESTREAM, настроенного для экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="765d3-136">When the database is configured for non-transactional access, the file and directory hierarchy represented in the FileTable is exposed under the FILESTREAM share configured for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="765d3-137">Это обеспечивает доступ приложениям Windows к файловой системе.</span><span class="sxs-lookup"><span data-stu-id="765d3-137">This provides file system access for Windows applications.</span></span>  
  
 <span data-ttu-id="765d3-138">Ниже перечислены некоторые дополнительные характеристики таблиц FileTable.</span><span class="sxs-lookup"><span data-stu-id="765d3-138">Some additional characteristics of FileTables include the following:</span></span>  
  
-   <span data-ttu-id="765d3-139">Данные файлов и каталогов, хранящиеся в таблице FileTable, отображаются с помощью общего ресурса Windows для нетранзакционного доступа к файлам из приложений на основе API-интерфейсов Windows.</span><span class="sxs-lookup"><span data-stu-id="765d3-139">The file and directory data stored in a FileTable is exposed through a Windows share for non-transactional file access for Windows API based applications.</span></span> <span data-ttu-id="765d3-140">Для приложения Windows это выглядит как обычная общая папка с файлами и каталогами.</span><span class="sxs-lookup"><span data-stu-id="765d3-140">For a Windows application, this looks like a normal share with its files and directories.</span></span> <span data-ttu-id="765d3-141">Приложения могут использовать богатый набор API-интерфейсов Windows для управления файлами и каталогами, находящимися в этой общей папке.</span><span class="sxs-lookup"><span data-stu-id="765d3-141">Applications can use a rich set of Windows APIs to manage the files and directories under this share.</span></span>  
  
-   <span data-ttu-id="765d3-142">Иерархия каталогов, отображаемая в общем хранилище, является просто логической структурой каталога, сохраняемой в таблице FileTable.</span><span class="sxs-lookup"><span data-stu-id="765d3-142">The directory hierarchy surfaced through the share is a purely logical directory structure that is maintained within the FileTable.</span></span>  
  
-   <span data-ttu-id="765d3-143">Вызовы для создания или изменения файла или каталога через общий ресурс Windows перехватываются компонентом [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и отражаются в соответствующих реляционных данных в таблице FileTable.</span><span class="sxs-lookup"><span data-stu-id="765d3-143">Calls to create or change a file or directory through the Windows share are intercepted by a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] component and reflected in the corresponding relational data in the FileTable.</span></span>  
  
-   <span data-ttu-id="765d3-144">Операции API-интерфейсов Windows являются по своей природе нетранзакционными и не связаны с пользовательскими транзакциями.</span><span class="sxs-lookup"><span data-stu-id="765d3-144">Windows API operations are non-transactional in nature, and are not associated with user transactions.</span></span> <span data-ttu-id="765d3-145">Тем не менее транзакционный доступ к данным FILESTREAM, хранящимся в таблице FileTable, полностью поддерживается, как это происходит для любого столбца FILESTREAM в обычной таблице.</span><span class="sxs-lookup"><span data-stu-id="765d3-145">However, transactional access to FILESTREAM data stored in a FileTable is fully supported, as is the case for any FILESTREAM column in a regular table.</span></span>  
  
-   <span data-ttu-id="765d3-146">Кроме того, таблицы FileTable можно запрашивать и обновлять с помощью обычного доступа [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="765d3-146">FileTables can also be queried and updated through normal [!INCLUDE[tsql](../../includes/tsql-md.md)] access.</span></span> <span data-ttu-id="765d3-147">Они интегрируются со средствами управления [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и такими компонентами, как средство резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="765d3-147">They are also integrated with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] management tools, and features such as backup.</span></span>  
  
  
##  <a name="additional-considerations-for-using-filetables"></a><a name="additional"></a> <span data-ttu-id="765d3-148">Дополнительные замечания об использовании таблиц FileTable</span><span class="sxs-lookup"><span data-stu-id="765d3-148">Additional Considerations for Using FileTables</span></span>  
  
###  <a name="administrative-considerations"></a><a name="DBA"></a> <span data-ttu-id="765d3-149">Вопросы управления</span><span class="sxs-lookup"><span data-stu-id="765d3-149">Administrative Considerations</span></span>  
 <span data-ttu-id="765d3-150">**О функции FILESTREAM и таблицах FileTable**</span><span class="sxs-lookup"><span data-stu-id="765d3-150">**About FILESTREAM and FileTables**</span></span>  
  
-   <span data-ttu-id="765d3-151">Можно настроить таблицы FileTable отдельно от FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="765d3-151">You configure FileTables separately from FILESTREAM.</span></span> <span data-ttu-id="765d3-152">Таким образом, можно продолжать пользоваться функцией FILESTREAM, не включая нетранзакционный доступ и не создавая таблицы FileTable.</span><span class="sxs-lookup"><span data-stu-id="765d3-152">Therefore you can continue to use the FILESTREAM feature without enabling non-transactional access or creating FileTables.</span></span>  
  
-   <span data-ttu-id="765d3-153">Нетранзакционный доступ к данным FILESTREAM возможен исключительно с помощью таблиц FileTable.</span><span class="sxs-lookup"><span data-stu-id="765d3-153">There is no non-transactional access to FILESTREAM data except through FileTables.</span></span> <span data-ttu-id="765d3-154">Таким образом, при включении нетранзакционного доступа поведение существующих столбцов FILESTREAM и приложений не изменяется.</span><span class="sxs-lookup"><span data-stu-id="765d3-154">Therefore, when you enable non-transactional access, the behavior of existing FILESTREAM columns and applications is not affected.</span></span>  
  
 <span data-ttu-id="765d3-155">**О таблицах FileTable и нетранзакционном доступе**</span><span class="sxs-lookup"><span data-stu-id="765d3-155">**About FileTables and non-transactional access**</span></span>  
  
-   <span data-ttu-id="765d3-156">Можно включить или отключить нетранзакционный доступ на уровне базы данных.</span><span class="sxs-lookup"><span data-stu-id="765d3-156">You can enable or disable non-transactional access at the database level.</span></span>  
  
-   <span data-ttu-id="765d3-157">Можно настроить или отрегулировать нетранзакционный доступ на уровне базы данных, отключив или включив доступ только для чтения или полный доступ для чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="765d3-157">You can configure or fine-tune non-transactional access at the database level by turning it off, or by enabling read only or full read/write access.</span></span>  
  
  
###  <a name="filetables-do-not-support-memory-mapped-files"></a><a name="memory"></a> <span data-ttu-id="765d3-158">Таблицы FileTable не поддерживают файлы, отображенные на память</span><span class="sxs-lookup"><span data-stu-id="765d3-158">FileTables Do Not Support Memory-Mapped Files</span></span>  
 <span data-ttu-id="765d3-159">Таблицы FileTable не поддерживают файлы, отображенные на память.</span><span class="sxs-lookup"><span data-stu-id="765d3-159">FileTables do not support memory-mapped files.</span></span> <span data-ttu-id="765d3-160">Двумя распространенными примерами приложений, в которых используются файлы, отображаемые на память, являются Notepad и Paint.</span><span class="sxs-lookup"><span data-stu-id="765d3-160">Notepad and Paint are two common examples of applications that use memory-mapped files.</span></span> <span data-ttu-id="765d3-161">Эти приложения нельзя использовать на том же компьютере, что и [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , для открытия файлов, которые хранятся в FileTable.</span><span class="sxs-lookup"><span data-stu-id="765d3-161">You cannot use these applications on the same computer as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to open files that are stored in a FileTable.</span></span> <span data-ttu-id="765d3-162">Но можно использовать эти приложения с удаленного компьютера для открытия файлов, хранящихся в FileTable, поскольку в этих обстоятельствах средство отображения на память не используется.</span><span class="sxs-lookup"><span data-stu-id="765d3-162">However you can use these applications from a remote computer to open files that are stored in a FileTable, because in these circumstances the memory-mapping feature is not used.</span></span>  
  
  
##  <a name="related-tasks"></a><a name="reltasks"></a> <span data-ttu-id="765d3-163">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="765d3-163">Related Tasks</span></span>  
 [<span data-ttu-id="765d3-164">Включение необходимых компонентов для таблицы FileTable</span><span class="sxs-lookup"><span data-stu-id="765d3-164">Enable the Prerequisites for FileTable</span></span>](enable-the-prerequisites-for-filetable.md)  
 <span data-ttu-id="765d3-165">Описывает способ включения компонентов, обязательных для создания и использования таблиц FileTable.</span><span class="sxs-lookup"><span data-stu-id="765d3-165">Describes how to enable the prerequisites for creating and using FileTables.</span></span>  
  
 [<span data-ttu-id="765d3-166">Создание, изменение и удаление таблиц FileTable</span><span class="sxs-lookup"><span data-stu-id="765d3-166">Create, Alter, and Drop FileTables</span></span>](create-alter-and-drop-filetables.md)  
 <span data-ttu-id="765d3-167">Описывает способы создания новых таблиц FileTable и изменения или удаления существующих таблиц FileTable.</span><span class="sxs-lookup"><span data-stu-id="765d3-167">Describes how to create a new FileTable, or alter or drop an existing FileTable.</span></span>  
  
 [<span data-ttu-id="765d3-168">Загрузка файлов в таблицы FileTable</span><span class="sxs-lookup"><span data-stu-id="765d3-168">Load Files into FileTables</span></span>](load-files-into-filetables.md)  
 <span data-ttu-id="765d3-169">Описывает процедуру загрузки или переноса файлов в таблицы FileTable.</span><span class="sxs-lookup"><span data-stu-id="765d3-169">Describes how to load or migrate files into FileTables.</span></span>  
  
 [<span data-ttu-id="765d3-170">Работа с каталогами и путями в таблицах FileTable</span><span class="sxs-lookup"><span data-stu-id="765d3-170">Work with Directories and Paths in FileTables</span></span>](work-with-directories-and-paths-in-filetables.md)  
 <span data-ttu-id="765d3-171">Описывает структуру каталогов, в которой файлы хранятся в таблицах FileTable.</span><span class="sxs-lookup"><span data-stu-id="765d3-171">Describes the directory structure in which the files are stored in FileTables.</span></span>  
  
 [<span data-ttu-id="765d3-172">Доступ к таблицам FileTable с помощью Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="765d3-172">Access FileTables with Transact-SQL</span></span>](access-filetables-with-transact-sql.md)  
 <span data-ttu-id="765d3-173">Описывает, как команды DML языка обработки данных Transact-SQL работают с таблицами FileTable.</span><span class="sxs-lookup"><span data-stu-id="765d3-173">Describes how Transact-SQL data manipulation language (DML) commands work with FileTables.</span></span>  
  
 [<span data-ttu-id="765d3-174">Доступ к таблицам FileTable с помощью API-интерфейсов ввода-вывода файлов</span><span class="sxs-lookup"><span data-stu-id="765d3-174">Access FileTables with File Input-Output APIs</span></span>](access-filetables-with-file-input-output-apis.md)  
 <span data-ttu-id="765d3-175">Описание работы файловой системы ввода-вывода с таблицами FileTable.</span><span class="sxs-lookup"><span data-stu-id="765d3-175">Describes how file system I/O works on a FileTable.</span></span>  
  
 [<span data-ttu-id="765d3-176">Управление таблицами FileTable</span><span class="sxs-lookup"><span data-stu-id="765d3-176">Manage FileTables</span></span>](manage-filetables.md)  
 <span data-ttu-id="765d3-177">Описывает стандартные административные задачи по управлению таблицами FileTables.</span><span class="sxs-lookup"><span data-stu-id="765d3-177">Describes common administrative tasks for managing FileTables.</span></span>  
  
  
##  <a name="related-content"></a><a name="relcontent"></a> <span data-ttu-id="765d3-178">См. также</span><span class="sxs-lookup"><span data-stu-id="765d3-178">Related Content</span></span>  
 [<span data-ttu-id="765d3-179">Схема FileTable</span><span class="sxs-lookup"><span data-stu-id="765d3-179">FileTable Schema</span></span>](filetable-schema.md)  
 <span data-ttu-id="765d3-180">Описывает стандартные и фиксированные схемы таблицы FileTable.</span><span class="sxs-lookup"><span data-stu-id="765d3-180">Describes the pre-defined and fixed schema of a FileTable.</span></span>  
  
 [<span data-ttu-id="765d3-181">Совместимость FileTable с другими компонентами SQL Server</span><span class="sxs-lookup"><span data-stu-id="765d3-181">FileTable Compatibility with Other SQL Server Features</span></span>](filetable-compatibility-with-other-sql-server-features.md)  
 <span data-ttu-id="765d3-182">Описывает работу таблиц FileTable совместно с другими компонентами SQL Server.</span><span class="sxs-lookup"><span data-stu-id="765d3-182">Describes how FileTables work with other features of SQL Server.</span></span>  
  
 [<span data-ttu-id="765d3-183">Инструкции FileTable языка DDL, функции, хранимые процедуры и представления</span><span class="sxs-lookup"><span data-stu-id="765d3-183">FileTable DDL, Functions, Stored Procedures, and Views</span></span>](../views/views.md)  
 <span data-ttu-id="765d3-184">Приведен список инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] и объектов базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , добавленных или измененных для поддержки функциональности FileTable.</span><span class="sxs-lookup"><span data-stu-id="765d3-184">Lists the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database objects that have been added or changed to support the FileTable feature.</span></span>  
  
 
  
