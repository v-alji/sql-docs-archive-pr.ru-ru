---
title: Запуск мастера импорта и экспорта SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Import and Export Wizard
- starting SQL Server Import and Export Wizard
- Import and Export Wizard
- starting Import and Export Wizard
ms.assetid: 5fc4f6d1-1f6f-444e-9aeb-827f85e1c405
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 008c541b1f1a295057b0ee7cc384982627b9689a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666135"
---
# <a name="run-the-sql-server-import-and-export-wizard"></a><span data-ttu-id="e84ef-102">Запуск мастера импорта и экспорта SQL Server</span><span class="sxs-lookup"><span data-stu-id="e84ef-102">Run the SQL Server Import and Export Wizard</span></span>
  <span data-ttu-id="e84ef-103">Мастер импорта и экспорта [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] предоставляет самый простой способ копирования данных между источниками и создания основных пакетов.</span><span class="sxs-lookup"><span data-stu-id="e84ef-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard provides the simplest method of copying data between data sources and of constructing basic packages.</span></span> <span data-ttu-id="e84ef-104">Дополнительные сведения о мастере см. в разделе [SQL Server мастер импорта и экспорта](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="e84ef-104">For more information about the wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="e84ef-105">Видеоролик, демонстрирующий использование мастера импорта и экспорта SQL Server для создания пакета, который экспортирует данные из SQL Server базы данных в электронную таблицу Microsoft Excel, см. в разделе [Экспорт данных SQL Server в Excel (SQL Server видео)](https://go.microsoft.com/fwlink/?LinkId=131024).</span><span class="sxs-lookup"><span data-stu-id="e84ef-105">For a video that demonstrates how to use the SQL Server Import and Export Wizard to create a package that exports data from a SQL Server database to a Microsoft Excel spreadsheet, see [Exporting SQL Server Data to Excel (SQL Server Video)](https://go.microsoft.com/fwlink/?LinkId=131024).</span></span>  
  
### <a name="to-start-the-sql-server-import-and-export-wizard"></a><span data-ttu-id="e84ef-106">Запуск мастера импорта и экспорта SQL Server</span><span class="sxs-lookup"><span data-stu-id="e84ef-106">To start the SQL Server Import and Export Wizard</span></span>  
  
-   <span data-ttu-id="e84ef-107">В меню **Пуск** наведите указатель на пункт **все программы**, выберите**Microsoft SQL Server** , а затем щелкните **Импорт и экспорт данных**.</span><span class="sxs-lookup"><span data-stu-id="e84ef-107">On the **Start** menu, point to **All Programs**, point to**Microsoft SQL Server** , and then click **Import and Export Data**.</span></span>  
  
     <span data-ttu-id="e84ef-108">-или-</span><span class="sxs-lookup"><span data-stu-id="e84ef-108">-or-</span></span>  
  
     <span data-ttu-id="e84ef-109">В щелкните [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] правой кнопкой мыши папку **пакеты служб SSIS** и выберите пункт **Мастер ссисимпорт и экспорта**.</span><span class="sxs-lookup"><span data-stu-id="e84ef-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], right-click the **SSIS Packages** folder, and then click **SSISImport and Export Wizard**.</span></span>  
  
     <span data-ttu-id="e84ef-110">-или-</span><span class="sxs-lookup"><span data-stu-id="e84ef-110">-or-</span></span>  
  
     <span data-ttu-id="e84ef-111">В выберите в [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] меню **проект** пункт **Мастер ссисимпорт и экспорта**.</span><span class="sxs-lookup"><span data-stu-id="e84ef-111">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], on the **Project** menu, click **SSISImport and Export Wizard**.</span></span>  
  
     <span data-ttu-id="e84ef-112">-или-</span><span class="sxs-lookup"><span data-stu-id="e84ef-112">-or-</span></span>  
  
     <span data-ttu-id="e84ef-113">В [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] подключитесь к [!INCLUDE[ssDE](../../includes/ssde-md.md)] типу сервера, разверните узел базы данных, щелкните правой кнопкой мыши базу данных, укажите пункт **задачи**, а затем выберите команду **Импорт данных** или **Экспорт данных**.</span><span class="sxs-lookup"><span data-stu-id="e84ef-113">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] server type, expand Databases, right-click a database, point to **Tasks**, and then click **Import Data** or **Export data**.</span></span>  
  
     <span data-ttu-id="e84ef-114">-или-</span><span class="sxs-lookup"><span data-stu-id="e84ef-114">-or-</span></span>  
  
     <span data-ttu-id="e84ef-115">В окне командной строки запустите программу DTSWizard.exe, которая находится в папке «C:\Program Files\Microsoft SQL Server\100\DTS\Binn».</span><span class="sxs-lookup"><span data-stu-id="e84ef-115">In a command prompt window, run DTSWizard.exe, located in C:\Program Files\Microsoft SQL Server\100\DTS\Binn.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e84ef-116">На 64-разрядном компьютере службы [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] устанавливают 64-разрядную версию мастера импорта и экспорта [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (DTSWizard.exe).</span><span class="sxs-lookup"><span data-stu-id="e84ef-116">On a 64-bit computer, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installs the 64-bit version of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard (DTSWizard.exe).</span></span> <span data-ttu-id="e84ef-117">Однако некоторые источники данных, такие как Access и Excel, располагают только 32-разрядным поставщиком.</span><span class="sxs-lookup"><span data-stu-id="e84ef-117">However, some data sources, such as Access or Excel, only have a 32-bit provider available.</span></span> <span data-ttu-id="e84ef-118">Для работы с этими источниками данных необходимо установить и запустить 32-разрядную версию мастера.</span><span class="sxs-lookup"><span data-stu-id="e84ef-118">To work with these data sources, you might have to install and run the 32-bit version of the wizard.</span></span> <span data-ttu-id="e84ef-119">Чтобы установить 32-разрядную версию мастера, необходимо выбрать клиентские средства или среду [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] во время установки.</span><span class="sxs-lookup"><span data-stu-id="e84ef-119">To install the 32-bit version of the wizard, select either Client Tools or [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] during setup.</span></span>  
  
### <a name="to-import-or-export-data-by-using-the-sql-server-import-and-export-wizard"></a><span data-ttu-id="e84ef-120">Импорт и экспорт данных с помощью мастера импорта и экспорта SQL Server</span><span class="sxs-lookup"><span data-stu-id="e84ef-120">To import or export data by using the SQL Server Import and Export Wizard</span></span>  
  
1.  <span data-ttu-id="e84ef-121">Запустите мастер импорта и экспорта служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e84ef-121">Start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard.</span></span>  
  
2.  <span data-ttu-id="e84ef-122">На соответствующих страницах мастера выберите источник данных и целевое назначение данных.</span><span class="sxs-lookup"><span data-stu-id="e84ef-122">On the corresponding wizard pages, select a data source and a data destination.</span></span>  
  
     <span data-ttu-id="e84ef-123">Доступны такие источники данных, как поставщики данных [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], поставщики OLE DB, собственные клиенты-поставщики служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[vstecado](../../includes/vstecado-md.md)], Microsoft Office Excel, Microsoft Office Access, а также источник неструктурированных файлов.</span><span class="sxs-lookup"><span data-stu-id="e84ef-123">The available data sources include [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data providers, OLE DB providers, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client providers, [!INCLUDE[vstecado](../../includes/vstecado-md.md)] providers, Microsoft Office Excel, Microsoft Office Access, and the Flat File source.</span></span> <span data-ttu-id="e84ef-124">В зависимости от выбранного источника можно задать такие параметры, как режим проверки подлинности, имя сервера, имя базы данных и формат файла.</span><span class="sxs-lookup"><span data-stu-id="e84ef-124">Depending on the source, you set options such as the authentication mode, server name, database name, and file format.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e84ef-125">Поставщик OLE DB [!INCLUDE[msCoName](../../includes/msconame-md.md)] для Oracle не поддерживает следующие типы данных Oracle: Oracle BLOB, CLOB, NCLOB, BFILE и UROWID.</span><span class="sxs-lookup"><span data-stu-id="e84ef-125">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB Provider for Oracle does not support the Oracle BLOB, CLOB, NCLOB, BFILE, and UROWID data types.</span></span> <span data-ttu-id="e84ef-126">Следовательно, источник OLE DB не может извлекать данные из таблиц, содержащих столбцы с этими типами данных.</span><span class="sxs-lookup"><span data-stu-id="e84ef-126">Therefore, the OLE DB source cannot extract data from tables that contain columns with these data types.</span></span>  
  
     <span data-ttu-id="e84ef-127">Доступны такие назначения, как поставщики данных [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], поставщики OLE DB, собственный клиент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Excel, Access и назначение «Неструктурированный файл».</span><span class="sxs-lookup"><span data-stu-id="e84ef-127">The available data destinations include [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data providers, OLE DB providers, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, Excel, Access, and the Flat File destination.</span></span>  
  
3.  <span data-ttu-id="e84ef-128">Задайте параметры выбранного типа назначения.</span><span class="sxs-lookup"><span data-stu-id="e84ef-128">Set the options for the type of destination that you selected.</span></span>  
  
     <span data-ttu-id="e84ef-129">Если в качестве назначения выбрана база данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], можно задать следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="e84ef-129">If the destination is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database you can specify the following:</span></span>  
  
    -   <span data-ttu-id="e84ef-130">Укажите, нужно ли создавать новую базу данных, а также укажите свойства базы данных.</span><span class="sxs-lookup"><span data-stu-id="e84ef-130">Indicate whether to create a new database and set the database properties.</span></span> <span data-ttu-id="e84ef-131">Следующие свойства не могут быть изменены, и мастер воспользуется указанными значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e84ef-131">The following properties cannot be configured and the wizard uses the specified default values:</span></span>  
  
        |<span data-ttu-id="e84ef-132">Свойство</span><span class="sxs-lookup"><span data-stu-id="e84ef-132">Property</span></span>|<span data-ttu-id="e84ef-133">Значение</span><span class="sxs-lookup"><span data-stu-id="e84ef-133">Value</span></span>|  
        |--------------|-----------|  
        |<span data-ttu-id="e84ef-134">Параметры сортировки</span><span class="sxs-lookup"><span data-stu-id="e84ef-134">Collation</span></span>|<span data-ttu-id="e84ef-135">Latin1_General_CS_AS_KS_WS</span><span class="sxs-lookup"><span data-stu-id="e84ef-135">Latin1_General_CS_AS_KS_WS</span></span>|  
        |<span data-ttu-id="e84ef-136">Модель восстановления</span><span class="sxs-lookup"><span data-stu-id="e84ef-136">Recovery model</span></span>|<span data-ttu-id="e84ef-137">Полное</span><span class="sxs-lookup"><span data-stu-id="e84ef-137">Full</span></span>|  
        |<span data-ttu-id="e84ef-138">Использовать полнотекстовое индексирование</span><span class="sxs-lookup"><span data-stu-id="e84ef-138">Use full-text indexing</span></span>|<span data-ttu-id="e84ef-139">Верно</span><span class="sxs-lookup"><span data-stu-id="e84ef-139">True</span></span>|  
  
    -   <span data-ttu-id="e84ef-140">Выберите, копировать ли данные из таблиц или представлений или копировать результаты запроса.</span><span class="sxs-lookup"><span data-stu-id="e84ef-140">Select whether to copy data from tables or views, or to copy query results.</span></span>  
  
         <span data-ttu-id="e84ef-141">Если необходимо копировать результаты запроса данных из источника, следует создать запрос Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="e84ef-141">If you want to query the source data and copy the results, you can construct a Transact-SQL query.</span></span> <span data-ttu-id="e84ef-142">Можно ввести запрос Transact-SQL вручную либо использовать запрос, сохраненный в файле.</span><span class="sxs-lookup"><span data-stu-id="e84ef-142">You can enter the Transact-SQL query manually or use a query saved to a file.</span></span> <span data-ttu-id="e84ef-143">Мастер содержит функцию просмотра для поиска файла. После выбора файл будет автоматически открыт, а его содержимое будет вставлено на страницу мастера.</span><span class="sxs-lookup"><span data-stu-id="e84ef-143">The wizard includes a browse feature for locating the file, and the wizard automatically opens the file and pastes its content into the wizard page when you select the file.</span></span>  
  
         <span data-ttu-id="e84ef-144">Если источником является поставщик [!INCLUDE[vstecado](../../includes/vstecado-md.md)], можно также использовать этот параметр, чтобы скопировать результаты запроса, предоставляя строку DBCommand в качестве запроса.</span><span class="sxs-lookup"><span data-stu-id="e84ef-144">If the source is an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] provider you can also use the option to copy query results, providing the DBCommand string as the query.</span></span>  
  
         <span data-ttu-id="e84ef-145">Если источником данных является представление, мастер импорта и экспорта [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] автоматически преобразует это представление в таблицу в назначении.</span><span class="sxs-lookup"><span data-stu-id="e84ef-145">If the source data is a view, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard automatically converts the view to a table in the destination.</span></span>  
  
    -   <span data-ttu-id="e84ef-146">Укажите, следует ли удалить и создать повторно целевую таблицу, а также разрешить ли вставку идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="e84ef-146">Indicate whether the destination table is dropped and then re-created, and whether to enable identity inserts.</span></span>  
  
    -   <span data-ttu-id="e84ef-147">Укажите, следует ли удалять и добавлять строки в существующую целевую таблицу.</span><span class="sxs-lookup"><span data-stu-id="e84ef-147">Indicate whether to delete rows or append rows in an existing destination table.</span></span> <span data-ttu-id="e84ef-148">Если таблица не существует, мастер импорта и экспорта [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] создаст ее автоматически.</span><span class="sxs-lookup"><span data-stu-id="e84ef-148">If the table does not exist, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard automatically creates it.</span></span>  
  
     <span data-ttu-id="e84ef-149">Если в качестве назначения выбран неструктурированный файл, можно задать следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="e84ef-149">If the destination is a Flat File destination you can specify the following:</span></span>  
  
    -   <span data-ttu-id="e84ef-150">Указать разделитель строк в целевом файле.</span><span class="sxs-lookup"><span data-stu-id="e84ef-150">Specify the row delimiter in the destination file.</span></span>  
  
    -   <span data-ttu-id="e84ef-151">Указать разделитель столбцов в целевом файле.</span><span class="sxs-lookup"><span data-stu-id="e84ef-151">Specify the column delimiter in the destination file.</span></span>  
  
4.  <span data-ttu-id="e84ef-152">Дополнительно можно выбрать одну таблицу и изменить сопоставление исходных и целевых столбцов или изменить метаданные целевых столбцов.</span><span class="sxs-lookup"><span data-stu-id="e84ef-152">(Optional) Select one table and change the mappings between source and destination columns, or change the metadata of destination columns:</span></span>  
  
    -   <span data-ttu-id="e84ef-153">Сопоставьте исходные столбцы с другими целевыми столбцами.</span><span class="sxs-lookup"><span data-stu-id="e84ef-153">Map source columns to different destination columns.</span></span>  
  
    -   <span data-ttu-id="e84ef-154">Измените тип данных целевого столбца.</span><span class="sxs-lookup"><span data-stu-id="e84ef-154">Change the data type in the destination column.</span></span>  
  
    -   <span data-ttu-id="e84ef-155">Задайте длину столбцов символьных типов.</span><span class="sxs-lookup"><span data-stu-id="e84ef-155">Set the length of columns with character data types.</span></span>  
  
    -   <span data-ttu-id="e84ef-156">Задайте масштаб и точность столбцов числовых типов.</span><span class="sxs-lookup"><span data-stu-id="e84ef-156">Set the precision and scale of columns with numeric data types.</span></span>  
  
    -   <span data-ttu-id="e84ef-157">Укажите, может ли столбец содержать значения NULL.</span><span class="sxs-lookup"><span data-stu-id="e84ef-157">Specify whether the column can contain null values.</span></span>  
  
5.  <span data-ttu-id="e84ef-158">Если необходимо выбрать несколько таблиц и обновить метаданные и параметры, которые будут применены к этим таблицам, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e84ef-158">(Optional) Select multiple tables, and update the metadata and options to apply to those tables:</span></span>  
  
    -   <span data-ttu-id="e84ef-159">Выберите существующую целевую схему или предоставьте новую схему, чтобы назначить ее таблицам.</span><span class="sxs-lookup"><span data-stu-id="e84ef-159">Select an existing destination schema or provide a new schema to which to assign tables.</span></span>  
  
    -   <span data-ttu-id="e84ef-160">Укажите возможность вставки столбцов идентификаторов в целевые таблицы.</span><span class="sxs-lookup"><span data-stu-id="e84ef-160">Specify whether to enable identity inserts in destination tables.</span></span>  
  
    -   <span data-ttu-id="e84ef-161">Укажите возможность удаления и повторного создания целевых таблиц.</span><span class="sxs-lookup"><span data-stu-id="e84ef-161">Specify whether to drop and re-create destination tables.</span></span>  
  
    -   <span data-ttu-id="e84ef-162">Укажите возможность усечения целевых таблиц.</span><span class="sxs-lookup"><span data-stu-id="e84ef-162">Specify whether to truncate existing destination tables.</span></span>  
  
6.  <span data-ttu-id="e84ef-163">Сохраните и выполните пакет.</span><span class="sxs-lookup"><span data-stu-id="e84ef-163">Save and run a package.</span></span>  
  
     <span data-ttu-id="e84ef-164">Если мастер запущен из среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или из командной строки, пакет может быть выполнен немедленно.</span><span class="sxs-lookup"><span data-stu-id="e84ef-164">If the wizard is started from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or the command prompt, the package can run immediately.</span></span> <span data-ttu-id="e84ef-165">При необходимости можно сохранить пакет в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] базе данных **msdb** или в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="e84ef-165">You can optionally save the package to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **msdb** database or to the file system.</span></span> <span data-ttu-id="e84ef-166">Дополнительные сведения о базе данных **msdb** см. в разделе [Управление пакетами &#40;служб SSIS&#41;](../service/package-management-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="e84ef-166">For more information about the **msdb** database, see [Package Management &#40;SSIS Service&#41;](../service/package-management-ssis-service.md).</span></span>  
  
     <span data-ttu-id="e84ef-167">Если пакет сохранен, то можно задать уровень защиты пакета, и если уровень защиты использует пароль, то необходимо предоставить пароль.</span><span class="sxs-lookup"><span data-stu-id="e84ef-167">When you save the package you can set the package protection level, and if the protection level uses a password, provide the password.</span></span> <span data-ttu-id="e84ef-168">Дополнительные сведения об уровнях защиты пакета см. [в разделе Управление доступом для конфиденциальных данных в пакетах](../security/access-control-for-sensitive-data-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="e84ef-168">For more information about package protection levels, see [Access Control for Sensitive Data in Packages](../security/access-control-for-sensitive-data-in-packages.md).</span></span>  
  
     <span data-ttu-id="e84ef-169">Если мастер запущен из проекта служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] среды [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], пакет не может быть запущен из мастера.</span><span class="sxs-lookup"><span data-stu-id="e84ef-169">If the wizard is started from an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you cannot run the package from the wizard.</span></span> <span data-ttu-id="e84ef-170">Вместо этого пакет добавляется в проект служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], из которого был запущен мастер.</span><span class="sxs-lookup"><span data-stu-id="e84ef-170">Instead, the package is added to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project from which you started the wizard.</span></span> <span data-ttu-id="e84ef-171">Впоследствии пакет может быть запущен в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e84ef-171">You can then run the package in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e84ef-172">В выпуске [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] пакет, созданный при помощи мастера, сохранить нельзя.</span><span class="sxs-lookup"><span data-stu-id="e84ef-172">In [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], the option to save the package created by the wizard is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e84ef-173">См. также:</span><span class="sxs-lookup"><span data-stu-id="e84ef-173">See Also</span></span>  
 <span data-ttu-id="e84ef-174">[Мастер импорта и экспорта SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="e84ef-174">[SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md) </span></span>  
 [<span data-ttu-id="e84ef-175">Создание пакетов в SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="e84ef-175">Create Packages in SQL Server Data Tools</span></span>](../create-packages-in-sql-server-data-tools.md)  
  
  
