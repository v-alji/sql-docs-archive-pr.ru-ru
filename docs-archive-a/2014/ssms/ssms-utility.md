---
title: Программа SSMS | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], opening
- command prompt utilities [SQL Server], sqlwb
- sqlwb utility
- Management Studio command line
- opening SQL Server Management Studio
ms.assetid: aafda520-9e2a-4e1e-b936-1b165f1684e8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0cfc9469e49e6ce3839d02a61477b8957fbc13e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668031"
---
# <a name="ssms-utility"></a><span data-ttu-id="67b5a-102">Программа SSMS</span><span class="sxs-lookup"><span data-stu-id="67b5a-102">Ssms Utility</span></span>
  <span data-ttu-id="67b5a-103">Служебная программа **Ssms** открывает [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67b5a-103">The **Ssms**utility opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="67b5a-104">Если указано, программа **Ssms** также устанавливает подключение к серверу и открывает запросы, скрипты, файлы, проекты и решения.</span><span class="sxs-lookup"><span data-stu-id="67b5a-104">If specified, **Ssms** also establishes a connection to a server, and opens queries, scripts, files, projects, and solutions.</span></span>  
  
 <span data-ttu-id="67b5a-105">Можно указать файлы, содержащие запросы, проекты или решения.</span><span class="sxs-lookup"><span data-stu-id="67b5a-105">You can specify files that contain queries, projects, or solutions.</span></span> <span data-ttu-id="67b5a-106">Файлы, содержащие запросы, автоматически подключаются к серверу в случае наличия сведений для соединения и в том случае, если сервер связан с этим типом файлов.</span><span class="sxs-lookup"><span data-stu-id="67b5a-106">Files that contain queries are automatically connected to a server if connection information is provided and the file type is associated with that type of server.</span></span> <span data-ttu-id="67b5a-107">Например, SQL-файлы в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]откроются в окне редактора SQL-запросов, а MDX-файлы откроются в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]в окне редактора запросов многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="67b5a-107">For instance, .sql files will open a SQL Query Editor window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], and .mdx files will open an MDX Query Editor window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="67b5a-108">**Решения и проекты SQL Server** открываются в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67b5a-108">**SQL Server Solutions and Projects** will open in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="67b5a-109">Программа **Ssms** не выполняет запросы.</span><span class="sxs-lookup"><span data-stu-id="67b5a-109">The **Ssms** utility does not run queries.</span></span> <span data-ttu-id="67b5a-110">Для запуска запросов из командной строки используйте программу **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="67b5a-110">To run queries from the command line, use the **sqlcmd** utility.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67b5a-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="67b5a-111">Syntax</span></span>  
  
```  
  
      Ssms  
    [scriptfile] [projectfile] [solutionfile]  
    [-Sservername] [-ddatabasename] [-Uusername] [-Ppassword]   
    [-E] [-nosplash] [-log[filename]?] [-?]  
```  
  
## <a name="arguments"></a><span data-ttu-id="67b5a-112">Аргументы</span><span class="sxs-lookup"><span data-stu-id="67b5a-112">Arguments</span></span>  
 <span data-ttu-id="67b5a-113">*scriptfile*</span><span class="sxs-lookup"><span data-stu-id="67b5a-113">*scriptfile*</span></span>  
 <span data-ttu-id="67b5a-114">Указывает один или более файлов скрипта для открытия.</span><span class="sxs-lookup"><span data-stu-id="67b5a-114">Specifies one or more script files to open.</span></span> <span data-ttu-id="67b5a-115">Этот параметр должен содержать полный путь к файлам.</span><span class="sxs-lookup"><span data-stu-id="67b5a-115">The parameter must contain the full path to the files.</span></span>  
  
 <span data-ttu-id="67b5a-116">*projectfile*</span><span class="sxs-lookup"><span data-stu-id="67b5a-116">*projectfile*</span></span>  
 <span data-ttu-id="67b5a-117">Задает открываемый проект скрипта.</span><span class="sxs-lookup"><span data-stu-id="67b5a-117">Specifies a script project to open.</span></span> <span data-ttu-id="67b5a-118">Этот параметр должен содержать полный путь к файлу проекта скрипта.</span><span class="sxs-lookup"><span data-stu-id="67b5a-118">The parameter must contain the full path to the script project file.</span></span>  
  
 <span data-ttu-id="67b5a-119">*solutionfile*</span><span class="sxs-lookup"><span data-stu-id="67b5a-119">*solutionfile*</span></span>  
 <span data-ttu-id="67b5a-120">Задает открываемое решение.</span><span class="sxs-lookup"><span data-stu-id="67b5a-120">Specifies a solution to open.</span></span> <span data-ttu-id="67b5a-121">Этот параметр должен содержать полный путь к файлу решения.</span><span class="sxs-lookup"><span data-stu-id="67b5a-121">The parameter must contain the full path to the solution file.</span></span>  
  
 <span data-ttu-id="67b5a-122">[**-S** _имя_сервера_]</span><span class="sxs-lookup"><span data-stu-id="67b5a-122">[**-S** _servername_]</span></span>  
 <span data-ttu-id="67b5a-123">Имя сервера</span><span class="sxs-lookup"><span data-stu-id="67b5a-123">Server name</span></span>  
  
 <span data-ttu-id="67b5a-124">[**-d** _DatabaseName_]</span><span class="sxs-lookup"><span data-stu-id="67b5a-124">[**-d** _databasename_]</span></span>  
 <span data-ttu-id="67b5a-125">Имя базы данных</span><span class="sxs-lookup"><span data-stu-id="67b5a-125">Database name</span></span>  
  
 <span data-ttu-id="67b5a-126">[**-U** _username_]</span><span class="sxs-lookup"><span data-stu-id="67b5a-126">[**-U** _username_]</span></span>  
 <span data-ttu-id="67b5a-127">Имя пользователя при соединении с использованием проверки подлинности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="67b5a-127">User name when connecting with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication</span></span>  
  
 <span data-ttu-id="67b5a-128">[**-P** _пароль_]</span><span class="sxs-lookup"><span data-stu-id="67b5a-128">[**-P** _password_]</span></span>  
 <span data-ttu-id="67b5a-129">Пароль при соединении с использованием проверки подлинности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="67b5a-129">Password when connecting with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication</span></span>  
  
 <span data-ttu-id="67b5a-130">[**-E**]</span><span class="sxs-lookup"><span data-stu-id="67b5a-130">[**-E**]</span></span>  
 <span data-ttu-id="67b5a-131">Подключение с помощью проверки подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="67b5a-131">Connect using Windows Authentication</span></span>  
  
 <span data-ttu-id="67b5a-132">[**-Заставка**]</span><span class="sxs-lookup"><span data-stu-id="67b5a-132">[**-nosplash**]</span></span>  
 <span data-ttu-id="67b5a-133">Отключает отображение экрана-заставки при открытии среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="67b5a-133">Prevents [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from displaying the splash screen graphic while opening.</span></span> <span data-ttu-id="67b5a-134">Используйте этот параметр при соединении с компьютером, где среда [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] работает с помощью служб терминалов, через соединение с ограниченной пропускной способностью.</span><span class="sxs-lookup"><span data-stu-id="67b5a-134">Use this option when connecting to the computer running [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] by means of Terminal Services over a connection with a limited bandwidth.</span></span> <span data-ttu-id="67b5a-135">При записи этого аргумента регистр символов не учитывается, он может быть указан до или после других аргументов</span><span class="sxs-lookup"><span data-stu-id="67b5a-135">This argument is not case-sensitive and may appear before or after other arguments</span></span>  
  
 <span data-ttu-id="67b5a-136">[**-log**_[имя_файла]?_]</span><span class="sxs-lookup"><span data-stu-id="67b5a-136">[**-log**_[filename]?_]</span></span>  
 <span data-ttu-id="67b5a-137">Записывает действия среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] в указанный файл для диагностики неисправностей</span><span class="sxs-lookup"><span data-stu-id="67b5a-137">Logs [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] activity to the specified file for troubleshooting</span></span>  
  
 <span data-ttu-id="67b5a-138">[**-?**]</span><span class="sxs-lookup"><span data-stu-id="67b5a-138">[**-?**]</span></span>  
 <span data-ttu-id="67b5a-139">Отображает справку командной строки.</span><span class="sxs-lookup"><span data-stu-id="67b5a-139">Displays command line help</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67b5a-140">Remarks</span><span class="sxs-lookup"><span data-stu-id="67b5a-140">Remarks</span></span>  
 <span data-ttu-id="67b5a-141">Все ключи являются необязательными и разделяются пробелами, за исключением файлов, которые разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="67b5a-141">All of the switches are optional and separated by a space except files which are separated by commas.</span></span> <span data-ttu-id="67b5a-142">Если не указан ни один ключ, программа **Ssms** откроет [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] в соответствии с настройками пункта **Параметры** в меню **Сервис** .</span><span class="sxs-lookup"><span data-stu-id="67b5a-142">If you do not specify any switches, **Ssms** opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] as specified in the **Options** settings on the **Tools** menu.</span></span> <span data-ttu-id="67b5a-143">Например, если для параметра **При запуске** на странице **Среда — Общие** задано значение **Открывать новое окно запроса**, программа **Ssms** откроется с пустым окном редактора запросов.</span><span class="sxs-lookup"><span data-stu-id="67b5a-143">For example, if the **Environment/General** page **At startup** option specifies **Open new query window**, **Ssms** will open with a blank Query Editor.</span></span>  
  
 <span data-ttu-id="67b5a-144">Параметр **-log** должен находиться в конце командной строки после всех остальных параметров.</span><span class="sxs-lookup"><span data-stu-id="67b5a-144">The **-log** switch must appear at the end of the command line, after all other switches.</span></span> <span data-ttu-id="67b5a-145">Аргумент filename является необязательным.</span><span class="sxs-lookup"><span data-stu-id="67b5a-145">The filename argument is optional.</span></span> <span data-ttu-id="67b5a-146">Если указано имя файла, а файл не существует, то он будет создан.</span><span class="sxs-lookup"><span data-stu-id="67b5a-146">If a filename is specified, and the file does not exist, the file is created.</span></span> <span data-ttu-id="67b5a-147">Если файл создать невозможно, например из-за недостаточных прав доступа, журнал будет записан в нелокализованное расположение APPDATA (см. ниже).</span><span class="sxs-lookup"><span data-stu-id="67b5a-147">If the file cannot be created - for example, due to insufficient write access, the log is written to the nonlocalized APPDATA location instead (See below).</span></span> <span data-ttu-id="67b5a-148">Если аргумент filename не задан, в папку нелокализованных данных приложения текущего пользователя записываются два файла.</span><span class="sxs-lookup"><span data-stu-id="67b5a-148">If the filename argument is not specified, two files are written to the current user's nonlocalized application data folder.</span></span> <span data-ttu-id="67b5a-149">Папку нелокализованных данных приложения для SQL Server можно найти по переменной среды APPDATA.</span><span class="sxs-lookup"><span data-stu-id="67b5a-149">The nonlocalized application data folder for SQL Server can be found from the APPDATA environment variable.</span></span> <span data-ttu-id="67b5a-150">Например, для SQL Server 2012 используется папка \<system drive> : \Users \\<username \> \AppData\Roaming\Microsoft\AppEnv\10.0 \\ .</span><span class="sxs-lookup"><span data-stu-id="67b5a-150">For example, for SQL Server 2012, the folder is \<system drive>:\Users\\<username\>\AppData\Roaming\Microsoft\AppEnv\10.0\\.</span></span> <span data-ttu-id="67b5a-151">Два файла имеют имена по умолчанию ActivityLog.xml и ActivityLog.xsl.</span><span class="sxs-lookup"><span data-stu-id="67b5a-151">The two files are, by default, named ActivityLog.xml and ActivityLog.xsl.</span></span> <span data-ttu-id="67b5a-152">Первый содержит данные журнала действий, а второй ― это таблица стилей XML, которая обеспечивает более удобный просмотр XML-файла.</span><span class="sxs-lookup"><span data-stu-id="67b5a-152">The former contains the activity log data and the latter is an XML style sheet which provides a more convenient way to view the XML file.</span></span> <span data-ttu-id="67b5a-153">Выполните следующие действия, чтобы просмотреть файл журнала в средстве просмотра XML-файлов по умолчанию, например Internet Explorer: нажмите кнопку Пуск, выберите команду выполнить... \<system drive> и введите ": \Users \\<username \>\AppData\Roaming\Microsoft\AppEnv\10.0\ActivityLog.xml" в предоставленное поле, а затем нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="67b5a-153">Use the following steps to view the log file in your default XML viewer, like Internet Explorer:  Click Start, then click Run...", then type "\<system drive>:\Users\\<username\>\AppData\Roaming\Microsoft\AppEnv\10.0\ActivityLog.xml" into the field provided, and then press Enter.</span></span>  
  
 <span data-ttu-id="67b5a-154">Файлы, содержащие запросы, выведут запрос о подключении к серверу, если имеются сведения о соединении, а тип файла связан с этим типом сервера.</span><span class="sxs-lookup"><span data-stu-id="67b5a-154">Files that contain queries will prompt to be connected to a server if connection information is provided and the file type is associated with that type of server.</span></span> <span data-ttu-id="67b5a-155">Например, SQL-файлы в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]откроются в окне редактора SQL-запросов, а MDX-файлы откроются в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]в окне редактора запросов многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="67b5a-155">For instance, .sql files will open a SQL Query Editor window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], and .mdx files will open an MDX Query Editor window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="67b5a-156">**Решения и проекты SQL Server** открываются в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67b5a-156">**SQL Server Solutions and Projects** will open in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="67b5a-157">Следующая таблица показывает сопоставление типов серверов и расширений имен файлов.</span><span class="sxs-lookup"><span data-stu-id="67b5a-157">The following table maps server types to file extensions.</span></span>  
  
|<span data-ttu-id="67b5a-158">Тип сервера</span><span class="sxs-lookup"><span data-stu-id="67b5a-158">Server type</span></span>|<span data-ttu-id="67b5a-159">Расширение</span><span class="sxs-lookup"><span data-stu-id="67b5a-159">Extension</span></span>|  
|-----------------|---------------|  
|[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]|<span data-ttu-id="67b5a-160">.sql</span><span class="sxs-lookup"><span data-stu-id="67b5a-160">.sql</span></span>|  
|<span data-ttu-id="67b5a-161">Службы SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="67b5a-161">SQL Server Analysis Services</span></span>|<span data-ttu-id="67b5a-162">MDX</span><span class="sxs-lookup"><span data-stu-id="67b5a-162">.mdx</span></span><br /><br /> <span data-ttu-id="67b5a-163">XMLA</span><span class="sxs-lookup"><span data-stu-id="67b5a-163">.xmla</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="67b5a-164">Примеры</span><span class="sxs-lookup"><span data-stu-id="67b5a-164">Examples</span></span>  
 <span data-ttu-id="67b5a-165">Следующий скрипт открывает среду [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] из командной строки с настройками по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="67b5a-165">The following script opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from a command prompt with the default settings:</span></span>  
  
```  
Ssms  
  
```  
  
 <span data-ttu-id="67b5a-166">Следующий скрипт открывает среду [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] из командной строки с применением проверки подлинности Windows и с редактором кода, настроенным для сервера `ACCTG and the database AdventureWorks2012,` без показа экрана-заставки:</span><span class="sxs-lookup"><span data-stu-id="67b5a-166">The following script opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from a command prompt, with Windows Authentication, with the Code Editor set to the server `ACCTG and the database AdventureWorks2012,` without showing the splash screen:</span></span>  
  
```  
Ssms -E -S ACCTG -d AdventureWorks2012 -nosplash  
  
```  
  
 <span data-ttu-id="67b5a-167">Следующий скрипт открывает среду [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] из командной строки и открывает скрипт MonthEndQuery:</span><span class="sxs-lookup"><span data-stu-id="67b5a-167">The following script opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from a command prompt, and opens the MonthEndQuery script.</span></span>  
  
```  
Ssms "C:\Documents and Settings\username\My Documents\SQL Server Management Studio Projects\FinanceScripts\FinanceScripts\MonthEndQuery.sql"  
  
```  
  
 <span data-ttu-id="67b5a-168">Следующий скрипт открывает среду [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] из командной строки и открывает проект NewReportsProject на компьютере с именем `developer`:</span><span class="sxs-lookup"><span data-stu-id="67b5a-168">The following script opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from a command prompt, and opens the NewReportsProject project on the computer named `developer`:</span></span>  
  
```  
Ssms "\\developer\fin\ReportProj\ReportProj\NewReportProj.ssmssqlproj"  
  
```  
  
 <span data-ttu-id="67b5a-169">Следующий скрипт открывает среду [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] из командной строки и открывает решение MonthlyReports:</span><span class="sxs-lookup"><span data-stu-id="67b5a-169">The following script opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from a command prompt, and opens the MonthlyReports solution:</span></span>  
  
```  
Ssms "C:\solutionsfolder\ReportProj\MonthlyReports.ssmssln"  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="67b5a-170">См. также:</span><span class="sxs-lookup"><span data-stu-id="67b5a-170">See Also</span></span>  
 [<span data-ttu-id="67b5a-171">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="67b5a-171">Use SQL Server Management Studio</span></span>](../database-engine/use-sql-server-management-studio.md)  
  
  
