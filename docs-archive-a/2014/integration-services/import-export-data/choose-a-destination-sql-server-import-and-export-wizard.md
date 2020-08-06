---
title: Выбор назначения (мастер импорта и экспорта SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.chooseadestination.f1
ms.assetid: 1898be15-3e69-42d3-8ecb-3733c9f6c8e3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e4bf9b717ef9de20d84d32c18eb3caa4c54cad87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666164"
---
# <a name="choose-a-destination-sql-server-import-and-export-wizard"></a><span data-ttu-id="8fffd-102">Выбор назначения (мастер импорта и экспорта SQL Server)</span><span class="sxs-lookup"><span data-stu-id="8fffd-102">Choose a Destination (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="8fffd-103">Диалоговое окно **Выбор назначения** указывает место назначения для копируемых данных.</span><span class="sxs-lookup"><span data-stu-id="8fffd-103">Use the **Choose a Destination** page to specify the destination of the data that you want to copy.</span></span>  
  
 <span data-ttu-id="8fffd-104">Дополнительные сведения о работе этого мастера см. в разделе [Мастер импорта и экспорта SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="8fffd-104">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="8fffd-105">Дополнительные сведения о параметрах запуска мастера, а также о разрешениях, необходимых для успешного запуска мастера, см. в разделе [Запуск мастера импорта и экспорта SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="8fffd-105">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="8fffd-106">Мастера импорта и экспорта [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] предназначен для копирования данных из исходного расположения в целевое.</span><span class="sxs-lookup"><span data-stu-id="8fffd-106">The purpose of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="8fffd-107">Этот мастер может также создать целевую базу данных и целевые таблицы.</span><span class="sxs-lookup"><span data-stu-id="8fffd-107">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="8fffd-108">Однако если нужно скопировать несколько баз данных, таблиц или других объектов базы данных, следует использовать мастер копирования баз данных.</span><span class="sxs-lookup"><span data-stu-id="8fffd-108">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="8fffd-109">Дополнительные сведения см. в статье [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="8fffd-109">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="8fffd-110">Статические параметры</span><span class="sxs-lookup"><span data-stu-id="8fffd-110">Static Options</span></span>  
 <span data-ttu-id="8fffd-111">**Назначение**</span><span class="sxs-lookup"><span data-stu-id="8fffd-111">**Destination**</span></span>  
 <span data-ttu-id="8fffd-112">Выберите поставщика данных, соответствующего формату хранения данных места назначения.</span><span class="sxs-lookup"><span data-stu-id="8fffd-112">Choose the data provider that matches the data storage format of the destination.</span></span> <span data-ttu-id="8fffd-113">Для источника данных может существовать несколько поставщиков.</span><span class="sxs-lookup"><span data-stu-id="8fffd-113">There may be more than one provider available for your data source.</span></span> <span data-ttu-id="8fffd-114">Например, в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] может использоваться собственный клиент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , поставщик данных платформы .NET Framework для SQL Server или поставщик OLE DB для SQL Server (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="8fffd-114">For example, with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you can use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, the .NET Framework Data Provider for SQL Server, or the Microsoft OLE DB Provider for SQL Server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8fffd-115">Чтобы сохранить данные в назначение ODBC, выберите поставщик данных .NET Framework для ODBC.</span><span class="sxs-lookup"><span data-stu-id="8fffd-115">To save data to an ODBC destination, select the .NET Framework Data Provider for ODBC.</span></span>  
  
 <span data-ttu-id="8fffd-116">Свойство **Источник данных** может иметь различное число параметров, которое меняется в зависимости от поставщиков данных, установленных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="8fffd-116">The **Data Source** property has a variable number of options, which change depending on the providers installed on the computer.</span></span> <span data-ttu-id="8fffd-117">Следующие таблицы содержат список параметров для наиболее распространенных мест назначения.</span><span class="sxs-lookup"><span data-stu-id="8fffd-117">The following tables list the options for some commonly used destinations.</span></span> <span data-ttu-id="8fffd-118">В случае использования других поставщиков обращайтесь к поставляемой с ними документации.</span><span class="sxs-lookup"><span data-stu-id="8fffd-118">For other providers, see the provider-specific documentation.</span></span>  
  
## <a name="dynamic-options"></a><span data-ttu-id="8fffd-119">Динамические параметры</span><span class="sxs-lookup"><span data-stu-id="8fffd-119">Dynamic Options</span></span>  
 <span data-ttu-id="8fffd-120">В следующих разделах описаны параметры, доступные для нескольких источников данных.</span><span class="sxs-lookup"><span data-stu-id="8fffd-120">The following sections show the options available for several data sources.</span></span> <span data-ttu-id="8fffd-121">Не все места назначения доступны в раскрывающемся списке «Место назначения» и перечислены здесь.</span><span class="sxs-lookup"><span data-stu-id="8fffd-121">Not all the destinations that are available in the Destination drop-down are listed here.</span></span>  
  
### <a name="destination--sql-server-native-client-or-microsoft-ole-db-provider-for-sql-server"></a><span data-ttu-id="8fffd-122">Назначение — «Поставщик OLE DB для SQL Server (Майкрософт)» или «Собственный клиент SQL Server»</span><span class="sxs-lookup"><span data-stu-id="8fffd-122">Destination = SQL Server Native Client or Microsoft OLE DB Provider for SQL Server</span></span>  
 <span data-ttu-id="8fffd-123">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="8fffd-123">**Server name**</span></span>  
 <span data-ttu-id="8fffd-124">Введите имя сервера, принимающего данные, или выберите сервер из списка.</span><span class="sxs-lookup"><span data-stu-id="8fffd-124">Type the name of the server to receive the data, or choose a server from the list.</span></span>  
  
 <span data-ttu-id="8fffd-125">**Использовать проверку подлинности Windows**</span><span class="sxs-lookup"><span data-stu-id="8fffd-125">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="8fffd-126">Укажите, должен ли пакет использовать проверку подлинности Microsoft Windows для доступа к базе данных.</span><span class="sxs-lookup"><span data-stu-id="8fffd-126">Specify whether the package should use Microsoft Windows Authentication to log in to the database.</span></span> <span data-ttu-id="8fffd-127">Для лучшей защиты рекомендуется использовать проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="8fffd-127">Windows Authentication is recommended for better security.</span></span>  
  
 <span data-ttu-id="8fffd-128">**Использовать проверку подлинности SQL Server**</span><span class="sxs-lookup"><span data-stu-id="8fffd-128">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="8fffd-129">Укажите, должен ли пакет использовать проверку подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для доступа к базе данных.</span><span class="sxs-lookup"><span data-stu-id="8fffd-129">Specify whether the package should use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication to log in to the database.</span></span> <span data-ttu-id="8fffd-130">Если используется проверка подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , необходимо ввести имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="8fffd-130">If you use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, you must provide a user name and password.</span></span>  
  
 <span data-ttu-id="8fffd-131">**User name**</span><span class="sxs-lookup"><span data-stu-id="8fffd-131">**User name**</span></span>  
 <span data-ttu-id="8fffd-132">Укажите имя пользователя для подключения к базе данных, если используется проверка подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8fffd-132">Specify a user name for the database connection when you are using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="8fffd-133">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="8fffd-133">**Password**</span></span>  
 <span data-ttu-id="8fffd-134">Укажите пароль для подключения к базе данных, если используется проверка подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8fffd-134">Provide the password for the database connection when you are using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="8fffd-135">**База данных**</span><span class="sxs-lookup"><span data-stu-id="8fffd-135">**Database**</span></span>  
 <span data-ttu-id="8fffd-136">Выберите из списка базу данных на указанном экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]или создайте новую базу данных при помощи кнопки **Создать**.</span><span class="sxs-lookup"><span data-stu-id="8fffd-136">Select from the list of databases on the specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or create a new database by clicking **New**.</span></span>  
  
 <span data-ttu-id="8fffd-137">**Обновить**</span><span class="sxs-lookup"><span data-stu-id="8fffd-137">**Refresh**</span></span>  
 <span data-ttu-id="8fffd-138">Нажатие кнопки **Обновить** восстанавливает список доступных баз данных.</span><span class="sxs-lookup"><span data-stu-id="8fffd-138">Restore the list of available databases by clicking **Refresh**.</span></span>  
  
 <span data-ttu-id="8fffd-139">**Создать**</span><span class="sxs-lookup"><span data-stu-id="8fffd-139">**New**</span></span>  
 <span data-ttu-id="8fffd-140">Создать новую таблицу, используя диалоговое окно **Создание базы данных** .</span><span class="sxs-lookup"><span data-stu-id="8fffd-140">Create a new destination database by using the **Create Database** dialog box.</span></span>  
  
### <a name="destination--flat-file-destination"></a><span data-ttu-id="8fffd-141">Назначение — целевой объект «Неструктурированный файл»</span><span class="sxs-lookup"><span data-stu-id="8fffd-141">Destination = Flat File Destination</span></span>  
 <span data-ttu-id="8fffd-142">**Имя файла**</span><span class="sxs-lookup"><span data-stu-id="8fffd-142">**File name**</span></span>  
 <span data-ttu-id="8fffd-143">Укажите путь и имя файла для хранения данных</span><span class="sxs-lookup"><span data-stu-id="8fffd-143">Specify the path and file name for the file in which to store the data.</span></span> <span data-ttu-id="8fffd-144">Или нажмите кнопку **Обзор** , чтобы найти файл.</span><span class="sxs-lookup"><span data-stu-id="8fffd-144">Or, click **Browse** to locate a file.</span></span>  
  
 <span data-ttu-id="8fffd-145">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="8fffd-145">**Browse**</span></span>  
 <span data-ttu-id="8fffd-146">Выберите файл с помощью диалогового окна **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="8fffd-146">Locate a file by using the **Open** dialog box.</span></span>  
  
 <span data-ttu-id="8fffd-147">**Локаль**</span><span class="sxs-lookup"><span data-stu-id="8fffd-147">**Locale**</span></span>  
 <span data-ttu-id="8fffd-148">Указывает идентификатор локали (LCID), определяющий порядок сортировки по алфавиту и формат даты и времени.</span><span class="sxs-lookup"><span data-stu-id="8fffd-148">Specify the locale ID (LCID) that defines character sort orders and date and time formatting.</span></span>  
  
 <span data-ttu-id="8fffd-149">**Юникод**</span><span class="sxs-lookup"><span data-stu-id="8fffd-149">**Unicode**</span></span>  
 <span data-ttu-id="8fffd-150">Укажите, следует ли использовать Юникод.</span><span class="sxs-lookup"><span data-stu-id="8fffd-150">Indicate whether to use Unicode.</span></span> <span data-ttu-id="8fffd-151">При использовании Юникода не нужно указывать кодовую страницу.</span><span class="sxs-lookup"><span data-stu-id="8fffd-151">If you use Unicode, you do not have to specify a code page.</span></span>  
  
 <span data-ttu-id="8fffd-152">**Кодовая страница**</span><span class="sxs-lookup"><span data-stu-id="8fffd-152">**Code page**</span></span>  
 <span data-ttu-id="8fffd-153">Указывает кодовую страницу для используемого языка.</span><span class="sxs-lookup"><span data-stu-id="8fffd-153">Specify the code page for the language you want to use.</span></span>  
  
 <span data-ttu-id="8fffd-154">**Формат**</span><span class="sxs-lookup"><span data-stu-id="8fffd-154">**Format**</span></span>  
 <span data-ttu-id="8fffd-155">Укажите, будет ли использоваться форматирование с разделителями, с фиксированной шириной строк или без выравнивания по правому краю.</span><span class="sxs-lookup"><span data-stu-id="8fffd-155">Indicate whether to use delimited, fixed width, or ragged right formatting.</span></span>  
  
|<span data-ttu-id="8fffd-156">Значение</span><span class="sxs-lookup"><span data-stu-id="8fffd-156">Value</span></span>|<span data-ttu-id="8fffd-157">Описание</span><span class="sxs-lookup"><span data-stu-id="8fffd-157">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8fffd-158">С разделителями</span><span class="sxs-lookup"><span data-stu-id="8fffd-158">Delimited</span></span>|<span data-ttu-id="8fffd-159">Столбцы разделены с помощью разделителей, установленных на странице **Столбцы** .</span><span class="sxs-lookup"><span data-stu-id="8fffd-159">Columns are separated by a delimiter, specified on the **Columns** page.</span></span>|  
|<span data-ttu-id="8fffd-160">Фиксированная ширина</span><span class="sxs-lookup"><span data-stu-id="8fffd-160">Fixed width</span></span>|<span data-ttu-id="8fffd-161">Столбцы имеют фиксированную ширину.</span><span class="sxs-lookup"><span data-stu-id="8fffd-161">Columns have a fixed width.</span></span>|  
|<span data-ttu-id="8fffd-162">Переменная ширина</span><span class="sxs-lookup"><span data-stu-id="8fffd-162">Ragged right</span></span>|<span data-ttu-id="8fffd-163">В файлах с текстом без выключки вправо каждый столбец имеет фиксированную ширину, за исключением последнего столбца, разделенного разделителем строк.</span><span class="sxs-lookup"><span data-stu-id="8fffd-163">Ragged right files are files in which every column has a fixed width, except for the last column, which is delimited by the row delimiter.</span></span>|  
  
 <span data-ttu-id="8fffd-164">**Ограничитель текста**</span><span class="sxs-lookup"><span data-stu-id="8fffd-164">**Text qualifier**</span></span>  
 <span data-ttu-id="8fffd-165">Определите используемый ограничитель текста.</span><span class="sxs-lookup"><span data-stu-id="8fffd-165">Type the text qualifier to use.</span></span> <span data-ttu-id="8fffd-166">Например, можно указать, что каждый текстовый столбец будет заключен в кавычки.</span><span class="sxs-lookup"><span data-stu-id="8fffd-166">For example, you can specify that each text column be surrounded with quotation marks.</span></span>  
  
 <span data-ttu-id="8fffd-167">**Имена столбцов в первой строке данных**</span><span class="sxs-lookup"><span data-stu-id="8fffd-167">**Column names in first data row**</span></span>  
 <span data-ttu-id="8fffd-168">Укажите, нужно ли выводить имена столбцов в первой строке данных.</span><span class="sxs-lookup"><span data-stu-id="8fffd-168">Indicate whether you want to display column names in the first data row.</span></span>  
  
### <a name="destination--microsoft-excel"></a><span data-ttu-id="8fffd-169">Назначение — «Microsoft Excel»</span><span class="sxs-lookup"><span data-stu-id="8fffd-169">Destination = Microsoft Excel</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8fffd-170">Выберите **Microsoft Excel** только в случае, если необходимо соединиться с источником данных, использующим Excel 2003 или более раннюю версию.</span><span class="sxs-lookup"><span data-stu-id="8fffd-170">Select **Microsoft Excel** only if you want to connect to a data source that uses Excel 2003 or earlier.</span></span> <span data-ttu-id="8fffd-171">Чтобы подключиться к источнику данных, использующему Excel 2007, выберите **Microsoft Office 12,0 доступ ядро СУБД OLE DB поставщик**, щелкните **свойства**, а затем на вкладке **все** диалогового окна **Свойства связи данных** в поле **Расширенные свойства**введите `Excel 12.0` .</span><span class="sxs-lookup"><span data-stu-id="8fffd-171">To connect to a data source that uses Excel 2007, select **Microsoft Office 12.0 Access Database Engine OLE DB Provider**, click **Properties**, and then on the **All** tab of the **Data Link Properties** dialog box, for **Extended Properties**, enter `Excel 12.0`.</span></span>  
  
 <span data-ttu-id="8fffd-172">**Путь к файлу Excel**</span><span class="sxs-lookup"><span data-stu-id="8fffd-172">**Excel file path**</span></span>  
 <span data-ttu-id="8fffd-173">Укажите путь и имя файла для книги, в которой должны храниться данные (например, C:\MyData.xls, \\\Sales\Database\Northwind.xls).</span><span class="sxs-lookup"><span data-stu-id="8fffd-173">Specify the path and file name for the workbook in which to store the data (for example, C:\MyData.xls, \\\Sales\Database\Northwind.xls).</span></span> <span data-ttu-id="8fffd-174">Или нажмите кнопку **Обзор** , чтобы найти книгу.</span><span class="sxs-lookup"><span data-stu-id="8fffd-174">Or, click **Browse** to locate a workbook.</span></span>  
  
 <span data-ttu-id="8fffd-175">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="8fffd-175">**Browse**</span></span>  
 <span data-ttu-id="8fffd-176">Выберите книгу Excel с помощью диалогового окна **Открыть** .</span><span class="sxs-lookup"><span data-stu-id="8fffd-176">Locate an Excel workbook by using the **Open** dialog box.</span></span>  
  
 <span data-ttu-id="8fffd-177">**Версия Excel**</span><span class="sxs-lookup"><span data-stu-id="8fffd-177">**Excel version**</span></span>  
 <span data-ttu-id="8fffd-178">Выберите версию Excel для целевой рабочей книги.</span><span class="sxs-lookup"><span data-stu-id="8fffd-178">Select the version of Excel that is used by the destination workbook.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8fffd-179">При экспорте данных в назначение [!INCLUDE[ofprexcel](../../includes/ofprexcel-md.md)] мастер использует компонент назначения «Excel» служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8fffd-179">When you export data to a [!INCLUDE[ofprexcel](../../includes/ofprexcel-md.md)] destination, the wizard uses the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Excel Destination component.</span></span> <span data-ttu-id="8fffd-180">Сведения об использовании и известных проблемах см. в разделе [Excel Destination](../data-flow/excel-destination.md).</span><span class="sxs-lookup"><span data-stu-id="8fffd-180">For information on some usage considerations and known issues, see [Excel Destination](../data-flow/excel-destination.md).</span></span>  
  
### <a name="destination--microsoft-access"></a><span data-ttu-id="8fffd-181">Назначение — «Microsoft Access»</span><span class="sxs-lookup"><span data-stu-id="8fffd-181">Destination = Microsoft Access</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8fffd-182">Выберите **Microsoft Access** только в случае, если необходимо соединиться с источником данных, использующим Access 2003 или более раннюю версию.</span><span class="sxs-lookup"><span data-stu-id="8fffd-182">Select **Microsoft Access** only if you want to connect to a database that uses Access 2003 or earlier.</span></span> <span data-ttu-id="8fffd-183">Чтобы соединиться с источником данных, использующим Access 2007, выберите **Поставщик OLE DB для ядра СУБД Microsoft Office 12.0 Access**.</span><span class="sxs-lookup"><span data-stu-id="8fffd-183">To connect to a database that uses Access 2007, select **Microsoft Office 12.0 Access Database Engine OLE DB Provider**.</span></span>  
  
 <span data-ttu-id="8fffd-184">**Имя файла**</span><span class="sxs-lookup"><span data-stu-id="8fffd-184">**File name**</span></span>  
 <span data-ttu-id="8fffd-185">Укажите путь и имя файла базы данных для хранения данных (например, К:\мидата.МДБ, \\ \салес\датабасе\норсвинд.МДБ).</span><span class="sxs-lookup"><span data-stu-id="8fffd-185">Specify the path and file name for the database file in which to store the data (for example, C:\MyData.mdb, \\\Sales\Database\Northwind.mdb).</span></span> <span data-ttu-id="8fffd-186">Или нажмите кнопку **Обзор** , чтобы найти файл базы данных.</span><span class="sxs-lookup"><span data-stu-id="8fffd-186">Or, click **Browse** to locate a database file.</span></span>  
  
 <span data-ttu-id="8fffd-187">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="8fffd-187">**Browse**</span></span>  
 <span data-ttu-id="8fffd-188">Перейдите к нужной базе данных при помощи диалогового окна **Открыть** .</span><span class="sxs-lookup"><span data-stu-id="8fffd-188">Browse to the database file by using the **Open** dialog box.</span></span>  
  
 <span data-ttu-id="8fffd-189">**User name**</span><span class="sxs-lookup"><span data-stu-id="8fffd-189">**User name**</span></span>  
 <span data-ttu-id="8fffd-190">Если информационный файл рабочей группы связан с базой данных, укажите допустимое имя пользователя для подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="8fffd-190">Specify a valid user name for the database connection when a workgroup information file is associated with the database.</span></span>  
  
 <span data-ttu-id="8fffd-191">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="8fffd-191">**Password**</span></span>  
 <span data-ttu-id="8fffd-192">Если информационный файл рабочей группы связан с базой данных, укажите пароль пользователя для подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="8fffd-192">Provide the user's password for the database connection when a workgroup information file is associated with the database.</span></span> <span data-ttu-id="8fffd-193">Если база данных защищена одним для всех пользователей паролем, необходимо ввести его в диалоговом окне **Свойства связи данных** , открываемым нажатием кнопки **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="8fffd-193">However, if the database is protected with a single password for all users, you must provide this value in the **Data Link Properties** dialog box, which is accessed from the **Advanced** button.</span></span>  
  
 <span data-ttu-id="8fffd-194">**Дополнительно**</span><span class="sxs-lookup"><span data-stu-id="8fffd-194">**Advanced**</span></span>  
 <span data-ttu-id="8fffd-195">Задайте дополнительные параметры (например, пароль базы данных или нестандартный информационный файл рабочей группы) в диалоговом окне **Свойства связи данных**.</span><span class="sxs-lookup"><span data-stu-id="8fffd-195">Specify advanced options, such as the database password or a non-default workgroup information file, by using the **Data Link Properties** dialog box.</span></span> <span data-ttu-id="8fffd-196">Дополнительные сведения о свойствах поставщика OLE DB см. в разделе «Доступ к данным» (Data Access) [библиотеки MSDN по адресу](https://go.microsoft.com/fwlink/?linkid=62553).</span><span class="sxs-lookup"><span data-stu-id="8fffd-196">For more information about OLE DB provider properties, search in the Data Access section of the [MSDN Library](https://go.microsoft.com/fwlink/?linkid=62553).</span></span>  
  
  
