---
title: Установка и настройка семантического поиска | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- semantic search [SQL Server], installing
- semantic search [SQL Server], configuring
ms.assetid: 2cdd0568-7799-474b-82fb-65d79df3057c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8d95e0bb2adf3bacf7057b881ab2e85afd50feef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733793"
---
# <a name="install-and-configure-semantic-search"></a><span data-ttu-id="081ff-102">Установка и настройка семантического поиска</span><span class="sxs-lookup"><span data-stu-id="081ff-102">Install and Configure Semantic Search</span></span>
  <span data-ttu-id="081ff-103">Описывает компоненты, необходимые для статистического семантического поиска, и способы их установки и проверки.</span><span class="sxs-lookup"><span data-stu-id="081ff-103">Describes the prerequisites for statistical semantic search and how to install or check them.</span></span>  
  
## <a name="installing-semantic-search"></a><span data-ttu-id="081ff-104">Установка семантического поиска</span><span class="sxs-lookup"><span data-stu-id="081ff-104">Installing Semantic Search</span></span>  
  
###  <a name="how-to-check-whether-semantic-search-is-installed"></a><a name="HowToCheckInstalled"></a><span data-ttu-id="081ff-105">Как проверить, установлен ли семантический поиск</span><span class="sxs-lookup"><span data-stu-id="081ff-105">How To: Check Whether Semantic Search Is Installed</span></span>  
 <span data-ttu-id="081ff-106">Отправьте запрос к свойству **IsFullTextInstalled** функции метаданных [SERVERPROPERTY (Transact-SQL)](/sql/t-sql/functions/serverproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="081ff-106">Query the **IsFullTextInstalled** property of the [SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) metadata function.</span></span>  
  
 <span data-ttu-id="081ff-107">Возвращаемое значение 1 указывает, что установлен компонент Full-Text Search и семантический поиск. Возвращаемое значение 0 указывает, что они не установлены.</span><span class="sxs-lookup"><span data-stu-id="081ff-107">A return value of 1 indicates that Full-Text Search and Semantic Search are installed; a return value of 0 indicates that they are not installed.</span></span>  
  
```sql  
SELECT SERVERPROPERTY('IsFullTextInstalled');  
GO  
```  
  
###  <a name="how-to-install-semantic-search"></a><a name="BasicsSemanticSearch"></a><span data-ttu-id="081ff-108">Руководство. Установка семантического поиска</span><span class="sxs-lookup"><span data-stu-id="081ff-108">How To: Install Semantic Search</span></span>  
 <span data-ttu-id="081ff-109">Чтобы установить семантический поиск, выберите пункт **Полнотекстовые и семантические извлечения для поиска** на странице **Устанавливаемые средства** во время установки.</span><span class="sxs-lookup"><span data-stu-id="081ff-109">To install Semantic Search, select **Full-Text and Semantic Extractions for Search** on the **Features to Install** page during setup.</span></span>  
  
 <span data-ttu-id="081ff-110">Статистический семантический поиск зависит от полнотекстового поиска.</span><span class="sxs-lookup"><span data-stu-id="081ff-110">Statistical Semantic Search depends on Full-Text Search.</span></span> <span data-ttu-id="081ff-111">Эти два дополнительных компонента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] устанавливаются совместно.</span><span class="sxs-lookup"><span data-stu-id="081ff-111">These two optional features of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] are installed together.</span></span>  
  
## <a name="installing-or-removing-the-semantic-language-statistics-database"></a><span data-ttu-id="081ff-112">Установка или удаление базы данных семантической статистики языка</span><span class="sxs-lookup"><span data-stu-id="081ff-112">Installing or Removing the Semantic Language Statistics Database</span></span>  
 <span data-ttu-id="081ff-113">Средства семантического поиска имеют дополнительную внешнюю зависимость; речь идет о базе данных семантической статистики языка.</span><span class="sxs-lookup"><span data-stu-id="081ff-113">Semantic Search has an additional external dependency that is called the semantic language statistics database.</span></span> <span data-ttu-id="081ff-114">Эта база данных содержит статистические языковые модели, необходимые для семантического поиска.</span><span class="sxs-lookup"><span data-stu-id="081ff-114">This database contains the statistical language models required by semantic search.</span></span> <span data-ttu-id="081ff-115">Каждая база данных статистики семантики языка содержит языковые модели для всех языков, поддерживаемых семантическим индексированием.</span><span class="sxs-lookup"><span data-stu-id="081ff-115">A single semantic language statistics database contains the language models for all the languages that are supported for semantic indexing.</span></span>  
  
###  <a name="how-to-check-whether-the-semantic-language-statistics-database-is-installed"></a><a name="HowToCheckDatabase"></a><span data-ttu-id="081ff-116">Как проверить, установлена ли база данных Семантическая статистика языка</span><span class="sxs-lookup"><span data-stu-id="081ff-116">How To: Check Whether the Semantic Language Statistics Database Is Installed</span></span>  
 <span data-ttu-id="081ff-117">Отправьте запрос в представление каталога [sys.fulltext_semantic_language_statistics_database (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-fulltext-semantic-language-statistics-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="081ff-117">Query the catalog view [sys.fulltext_semantic_language_statistics_database &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-semantic-language-statistics-database-transact-sql).</span></span>  
  
 <span data-ttu-id="081ff-118">Если для экземпляра установлена и зарегистрирована база данных семантической статистики языка, то результаты запроса содержат единственную строку сведений о базе данных.</span><span class="sxs-lookup"><span data-stu-id="081ff-118">If the semantic language statistics database is installed and registered for the instance, then the query results contain a single row of information about the database.</span></span>  
  
```vb  
SELECT * FROM sys.fulltext_semantic_language_statistics_database;  
GO  
```  
  
###  <a name="how-to-install-attach-and-register-the-semantic-language-statistics-database"></a><a name="HowToInstallModel"></a><span data-ttu-id="081ff-119">Как установить, присоединить и зарегистрировать базу данных Семантическая статистика языка</span><span class="sxs-lookup"><span data-stu-id="081ff-119">How To: Install, Attach, and Register the Semantic Language Statistics Database</span></span>  
 <span data-ttu-id="081ff-120">База данных семантической статистики языка не устанавливается программой установки [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="081ff-120">The semantic language statistics database is not installed by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] setup program.</span></span> <span data-ttu-id="081ff-121">Чтобы установить базу данных семантической статистики языка как необходимый компонент для семантического индексирования, выполните следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="081ff-121">To set up the Semantic Language Statistics database as a prerequisite for semantic indexing, do the following tasks:</span></span>  
  
 <span data-ttu-id="081ff-122">**1. Установите базу данных семантической статистики языка.**</span><span class="sxs-lookup"><span data-stu-id="081ff-122">**1. Install the semantic language statistics database.**</span></span>  
 1.  <span data-ttu-id="081ff-123">Найдите базу данных семантической статистики языка на установочном носителе [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] или загрузите её из Интернета.</span><span class="sxs-lookup"><span data-stu-id="081ff-123">Locate the semantic language statistics database on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installation media or download it from the Web.</span></span>  
  
    -   <span data-ttu-id="081ff-124">Найдите пакет установщика Windows с именем файла **SemanticLanguageDatabase.msi** на установочном носителе [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="081ff-124">Locate the Windows installer package named **SemanticLanguageDatabase.msi** on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installation media.</span></span> <span data-ttu-id="081ff-125">Выберите 32-разрядную или 64-разрядную версию пакета установщика с учетом целевой системы.</span><span class="sxs-lookup"><span data-stu-id="081ff-125">Locate the 32-bit or 64-bit version of the installer package depending on the target system.</span></span> <span data-ttu-id="081ff-126">Имя папки, содержащей файл, обозначает 32-разрядную или 64-разрядную версию файла; само имя файла остается одинаковым для обеих версий.</span><span class="sxs-lookup"><span data-stu-id="081ff-126">The name of the containing folder identifies the 32-bit or 64-bit version of the file; the file name itself is the same for both versions.</span></span>  
  
    -   <span data-ttu-id="081ff-127">Загрузить пакет установщика из [Microsoft?? SQL Server?? 2014 Семантическая статистика языка](https://go.microsoft.com/fwlink/?LinkID=296743) страница в [!INCLUDE[msCoName](../../../includes/msconame-md.md)] центре загрузки.</span><span class="sxs-lookup"><span data-stu-id="081ff-127">Download the installer package from the [Microsoft?? SQL Server?? 2014 Semantic Language Statistics](https://go.microsoft.com/fwlink/?LinkID=296743) page on the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Download Center.</span></span>  
  
2.  <span data-ttu-id="081ff-128">Запустите пакет установщика Windows **SemanticLanguageDatabase.msi** , чтобы извлечь базу данных и файл журнала.</span><span class="sxs-lookup"><span data-stu-id="081ff-128">Run the **SemanticLanguageDatabase.msi** Windows installer package to extract the database and log file.</span></span>  
  
     <span data-ttu-id="081ff-129">Предусмотрена возможность изменить каталог назначения (не обязательно).</span><span class="sxs-lookup"><span data-stu-id="081ff-129">You can optionally change the destination directory.</span></span> <span data-ttu-id="081ff-130">По умолчанию установщик извлекает файлы в папку с именем **базы данных семантического языка Майкрософт** в папке 32-bit или 64-bit Program Files.</span><span class="sxs-lookup"><span data-stu-id="081ff-130">By default, the installer extracts the files to a folder named **Microsoft Semantic Language Database** in the 32-bit or 64-bit Program Files folder.</span></span> <span data-ttu-id="081ff-131">Файл MSI содержит файл базы данных и файл журнала в сжатом виде.</span><span class="sxs-lookup"><span data-stu-id="081ff-131">The MSI file contains a compressed database file and log file.</span></span>  
  
3.  <span data-ttu-id="081ff-132">Переместите извлеченный файл базы данных и файл журнала в подходящее расположение в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="081ff-132">Move the extracted database file and log file to a suitable location in the file system.</span></span>  
  
     <span data-ttu-id="081ff-133">Если оставить эти файлы на месте, невозможно будет извлечь еще одну копию базы данных для другого экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="081ff-133">If you leave the files in their default location, it will not be possible to extract another copy of the database for another instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="081ff-134">Файлу базы данных и файлу журнала при извлечении базы данных семантической статистики языка назначаются ограниченные разрешения в расположении по умолчанию в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="081ff-134">When the semantic language statistics database is extracted, restricted permissions are assigned to the database file and log file in the default location in the file system.</span></span> <span data-ttu-id="081ff-135">В результате, если вы перейдете из расположения по умолчанию, у вас может не оказаться разрешения на присоединение базы данных.</span><span class="sxs-lookup"><span data-stu-id="081ff-135">As a result, you may not have permission to attach the database if you leave it in the default location.</span></span> <span data-ttu-id="081ff-136">Если при попытке присоединить базу данных возникает ошибка, переместите файлы или проверьте и исправьте разрешения файловой системы соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="081ff-136">If an error is raised when you try to attach the database, move the files, or check and fix file system permissions as appropriate.</span></span>  
  
 <span data-ttu-id="081ff-137">**2. Присоедините базу данных семантической статистики языка.**</span><span class="sxs-lookup"><span data-stu-id="081ff-137">**2. Attach the semantic language statistics database.**</span></span>  
 <span data-ttu-id="081ff-138">Присоедините базу данных к экземпляру [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] с помощью инструкции [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] или вызвав инструкцию [CREATE DATABASE (SQL Server Transact-SQL)](/sql/t-sql/statements/create-database-sql-server-transact-sql) с синтаксисом **FOR ATTACH**.</span><span class="sxs-lookup"><span data-stu-id="081ff-138">Attach the database to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] or by calling [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) with the **FOR ATTACH** syntax.</span></span> <span data-ttu-id="081ff-139">Дополнительные сведения см. в разделе [Присоединение и отсоединение базы данных (SQL Server)](../databases/database-detach-and-attach-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="081ff-139">For more information, see [Database Detach and Attach &#40;SQL Server&#41;](../databases/database-detach-and-attach-sql-server.md).</span></span>  
  
 <span data-ttu-id="081ff-140">По умолчанию база данных имеет имя **semanticsdb**.</span><span class="sxs-lookup"><span data-stu-id="081ff-140">By default, the name of the database is **semanticsdb**.</span></span> <span data-ttu-id="081ff-141">При присоединении можно присвоить базе данных другое имя (необязательно).</span><span class="sxs-lookup"><span data-stu-id="081ff-141">You can optionally give the database a different name when you attach it.</span></span> <span data-ttu-id="081ff-142">Это имя необходимо предоставить при регистрации базы данных в следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="081ff-142">You have to provide this name when you register the database in the subsequent step.</span></span>  
  
```sql  
CREATE DATABASE semanticsdb  
            ON ( FILENAME = 'C:\Microsoft Semantic Language Database\semanticsdb.mdf' )  
            LOG ON ( FILENAME = 'C:\Microsoft Semantic Language Database\semanticsdb_log.ldf' )  
            FOR ATTACH;  
GO  
```  
  
 <span data-ttu-id="081ff-143">В этих образцах кода предполагается, что вы переместили базу данных из расположения по умолчанию в новое место хранения.</span><span class="sxs-lookup"><span data-stu-id="081ff-143">This code sample assumes that you have moved the database from its default location to a new location.</span></span>  
  
 <span data-ttu-id="081ff-144">**3. Зарегистрируйте базу данных статистики семантики языка.**</span><span class="sxs-lookup"><span data-stu-id="081ff-144">**3. Register the semantic language statistics database.**</span></span>  
 <span data-ttu-id="081ff-145">Вызовите хранимую процедуру [sp_fulltext_semantic_register_language_statistics_db (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-fulltext-semantic-register-language-statistics-db-transact-sql) и укажите имя, присвоенное базе данных при присоединении.</span><span class="sxs-lookup"><span data-stu-id="081ff-145">Call the stored procedure [sp_fulltext_semantic_register_language_statistics_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-fulltext-semantic-register-language-statistics-db-transact-sql) and provide the name that you gave to the database when you attached it.</span></span>  
  
```sql  
EXEC sp_fulltext_semantic_register_language_statistics_db @dbname = N'semanticsdb';  
GO  
```  
  
###  <a name="how-to-unregister-detach-and-remove-the-semantic-language-statistics-database"></a><a name="HowToUnregister"></a><span data-ttu-id="081ff-146">Как отменить регистрацию, отсоединить и удалить базу данных Семантическая статистика языка</span><span class="sxs-lookup"><span data-stu-id="081ff-146">How To: Unregister, Detach, and Remove the Semantic Language Statistics Database</span></span>  
 <span data-ttu-id="081ff-147">**Отмените регистрацию базы данных семантической статистики языка.**</span><span class="sxs-lookup"><span data-stu-id="081ff-147">**Unregister the semantic language statistics database.**</span></span>  
 <span data-ttu-id="081ff-148">Вызовите хранимую процедуру [sp_fulltext_semantic_unregister_language_statistics_db (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-fulltext-semantic-unregister-language-statistics-db-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="081ff-148">Call the stored procedure [sp_fulltext_semantic_unregister_language_statistics_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-fulltext-semantic-unregister-language-statistics-db-transact-sql).</span></span> <span data-ttu-id="081ff-149">Необходимость предоставлять имя базы данных отсутствует, поскольку экземпляр может иметь только одну базу данных семантической статистики языка.</span><span class="sxs-lookup"><span data-stu-id="081ff-149">You do not have to provide the name of the database since an instance can have only one semantic language statistics database.</span></span>  
  
```sql  
EXEC sp_fulltext_semantic_unregister_language_statistics_db;  
GO  
```  
  
 <span data-ttu-id="081ff-150">**Отсоедините базу данных семантической статистики языка.**</span><span class="sxs-lookup"><span data-stu-id="081ff-150">**Detach the semantic language statistics database.**</span></span>  
 <span data-ttu-id="081ff-151">Вызовите хранимую процедуру [sp_detach_db (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-detach-db-transact-sql) и укажите имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="081ff-151">Call the stored procedure [sp_detach_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-detach-db-transact-sql) and provide the name of the database.</span></span>  
  
```sql  
USE master;  
GO  
  
EXEC sp_detach_db @dbname = N'semanticsdb';  
GO  
```  
  
 <span data-ttu-id="081ff-152">**Удалите базу данных семантической статистики языка.**</span><span class="sxs-lookup"><span data-stu-id="081ff-152">**Remove the semantic language statistics database.**</span></span>  
 <span data-ttu-id="081ff-153">После отмены регистрации и отсоединения базы данных можно просто удалить файл базы данных.</span><span class="sxs-lookup"><span data-stu-id="081ff-153">After unregistering and detaching the database, you can simply delete the database file.</span></span> <span data-ttu-id="081ff-154">Программы удаления не существует, отсутствует пункт в списке **Программы и компоненты** на панели управления.</span><span class="sxs-lookup"><span data-stu-id="081ff-154">There is no uninstall program and there is no entry in **Programs and Features** in the Control Panel.</span></span>  
  
###  <a name="requirements-and-restrictions-for-installing-and-removing-the-semantic-language-statistics-database"></a><a name="reqinstall"></a><span data-ttu-id="081ff-155">Требования и ограничения для установки и удаления базы данных Семантическая статистика языка</span><span class="sxs-lookup"><span data-stu-id="081ff-155">Requirements and Restrictions for Installing and Removing the Semantic Language Statistics Database</span></span>  
  
-   <span data-ttu-id="081ff-156">Вы можете присоединить и зарегистрировать только одну базу данных статистики семантики языка для экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="081ff-156">You can only attach and register one semantic language statistics database on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="081ff-157">Для каждого экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] на одном компьютере требуется отдельная физическая копия базы данных семантической статистики языка.</span><span class="sxs-lookup"><span data-stu-id="081ff-157">Each instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on a single computer requires a separate physical copy of the semantic language statistics database.</span></span> <span data-ttu-id="081ff-158">Присоедините по одной копии к каждому экземпляру.</span><span class="sxs-lookup"><span data-stu-id="081ff-158">Attach one copy to each instance.</span></span>  
  
-   <span data-ttu-id="081ff-159">Нельзя отсоединить действительную базу данных статистики семантики языка и заменить ее произвольной базой данных с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="081ff-159">You cannot detach a valid and registered semantic language statistics database and replace it with an arbitrary database that has the same name.</span></span> <span data-ttu-id="081ff-160">Это приведет к сбоям активного или последующего заполнения индекса.</span><span class="sxs-lookup"><span data-stu-id="081ff-160">Doing so will cause active or future index populations to fail.</span></span>  
  
-   <span data-ttu-id="081ff-161">База данных статистики семантики языка доступна только для чтения.</span><span class="sxs-lookup"><span data-stu-id="081ff-161">The semantic language statistics database is read-only.</span></span> <span data-ttu-id="081ff-162">Вы не можете настраивать эту базу данных.</span><span class="sxs-lookup"><span data-stu-id="081ff-162">You cannot customize this database.</span></span> <span data-ttu-id="081ff-163">Если содержимое этой базы данных будет изменено каким-то образом, то результаты будущего семантического индексирования станут недетерминированными.</span><span class="sxs-lookup"><span data-stu-id="081ff-163">If you alter the content of the database in any way, the results for future semantic indexing are indeterministic.</span></span> <span data-ttu-id="081ff-164">Чтобы восстановить исходное состояние данных, можно удалить измененную базу данных, загрузить и прикрепить новую неизмененную копию базы данных.</span><span class="sxs-lookup"><span data-stu-id="081ff-164">To restore the original state of this data, you can drop the altered database, and download and attach a new and unaltered copy of the database.</span></span>  
  
-   <span data-ttu-id="081ff-165">Имеется возможность отключить или удалить базу данных статистики семантики языка.</span><span class="sxs-lookup"><span data-stu-id="081ff-165">It is possible to detach or drop the semantic language statistics database.</span></span> <span data-ttu-id="081ff-166">При наличии активных операций индексирования, имеющих блокировки чтения в базе данных, операция отсоединения или удаления завершится ошибкой или истечет время ожидания. Это согласуется с существующим поведением.</span><span class="sxs-lookup"><span data-stu-id="081ff-166">If there are any active indexing operations that have read locks on the database, then the detach or drop operation will fail or time out. This is consistent with existing behavior.</span></span> <span data-ttu-id="081ff-167">Операции семантического индексирования после удаления базы данных будут оканчиваться неудачей.</span><span class="sxs-lookup"><span data-stu-id="081ff-167">After the database is removed, semantic indexing operations will fail.</span></span>  
  
## <a name="installing-optional-support-for-newer-document-types"></a><span data-ttu-id="081ff-168">Установка дополнительной поддержки для новых типов документов</span><span class="sxs-lookup"><span data-stu-id="081ff-168">Installing Optional Support for Newer Document Types</span></span>  
  
###  <a name="how-to-install-the-latest-filters-for-microsoft-office-and-other-microsoft-document-types"></a><a name="office"></a><span data-ttu-id="081ff-169">Как установить последние фильтры для Microsoft Office и других типов документов Майкрософт</span><span class="sxs-lookup"><span data-stu-id="081ff-169">How to: Install the Latest Filters for Microsoft Office and other Microsoft Document Types</span></span>  
 <span data-ttu-id="081ff-170">Этот выпуск [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] устанавливает самые последние средства разбиения по словам и парадигматические модули [!INCLUDE[msCoName](../../../includes/msconame-md.md)] , но не устанавливает последние фильтры для документов [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Office и других типов документов [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="081ff-170">This release of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installs the latest [!INCLUDE[msCoName](../../../includes/msconame-md.md)] word breakers and stemmers, but does not install the latest filters for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Office documents and other [!INCLUDE[msCoName](../../../includes/msconame-md.md)] document types.</span></span> <span data-ttu-id="081ff-171">Эти фильтры необходимы для индексирования документов, созданных в последних версиях программ [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Office и других приложениях [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="081ff-171">These filters are required for indexing documents created with recent versions of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Office and other [!INCLUDE[msCoName](../../../includes/msconame-md.md)] applications.</span></span> <span data-ttu-id="081ff-172">Чтобы загрузить последние фильтры, см. раздел [Пакеты фильтров Microsoft Office 2010](https://www.microsoft.com/download/details.aspx?id=17062).</span><span class="sxs-lookup"><span data-stu-id="081ff-172">To download the latest filters, see [Microsoft Office 2010 Filter Packs](https://www.microsoft.com/download/details.aspx?id=17062).</span></span>  
  
  
