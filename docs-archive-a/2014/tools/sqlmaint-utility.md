---
title: sqlmaint, программа | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- database maintenance plans [SQL Server]
- sqlmaint utility
- maintaining databases [SQL Server]
- backups [SQL Server], sqlmaint utility
- command prompt utilities [SQL Server], sqlmaint
- maintenance plans [SQL Server], command prompt
- backing up [SQL Server], sqlmaint utility
ms.assetid: 937a9932-4aed-464b-b97a-a5acfe6a50de
author: stevestein
ms.author: sstein
ms.openlocfilehash: 80e60b75305ee91e8b62a201d9c86af301326789
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727534"
---
# <a name="sqlmaint-utility"></a><span data-ttu-id="5bf3d-102">sqlmaint, программа</span><span class="sxs-lookup"><span data-stu-id="5bf3d-102">sqlmaint Utility</span></span>
  <span data-ttu-id="5bf3d-103">Программа**sqlmaint** выполняет заданный набор операций обслуживания с одной или несколькими базами данных.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-103">The**sqlmaint** utility performs a specified set of maintenance operations on one or more databases.</span></span> <span data-ttu-id="5bf3d-104">Программа **sqlmaint** используется для выполнения проверок DBCC, создания резервных копий базы данных и ее журнала транзакций, обновления статистики и перестроения индексов.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-104">Use **sqlmaint** to run DBCC checks, back up a database and its transaction log, update statistics, and rebuild indexes.</span></span> <span data-ttu-id="5bf3d-105">При всех действиях по обслуживанию базы данных формируется отчет, который можно записать в указанный текстовый файл, в HTML-файл или отправить по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-105">All database maintenance activities generate a report that can be sent to a designated text file, HTML file, or e-mail account.</span></span> <span data-ttu-id="5bf3d-106">Программа**sqlmaint** выполняет планы обслуживания баз данных, созданные в предыдущих версиях [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5bf3d-106">**sqlmaint** executes database maintenance plans created with previous versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5bf3d-107">Для запуска планов обслуживания [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] из командной строки используйте программу [dtexec utility](../integration-services/packages/dtexec-utility.md).</span><span class="sxs-lookup"><span data-stu-id="5bf3d-107">To run [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] maintenance plans from the command prompt, use the [dtexec Utility](../integration-services/packages/dtexec-utility.md).</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepNextAvoid](../includes/ssnotedepnextavoid-md.md)] <span data-ttu-id="5bf3d-108">Вместо этого используйте функцию плана обслуживания [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5bf3d-108">Use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] maintenance plan feature instead.</span></span> <span data-ttu-id="5bf3d-109">Дополнительные сведения о планах обслуживания см. в разделе [Планы обслуживания](../relational-databases/maintenance-plans/maintenance-plans.md).</span><span class="sxs-lookup"><span data-stu-id="5bf3d-109">For more information on maintenance plans, see [Maintenance Plans](../relational-databases/maintenance-plans/maintenance-plans.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bf3d-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5bf3d-110">Syntax</span></span>  
  
```  
  
      sqlmaint   
[-?] |  
[  
     [-Sserver_name[\instance_name]]  
     [-Ulogin_ID [-Ppassword]]  
     {  
          [-Ddatabase_name | -PlanNamename | -PlanIDguid ]  
          [-Rpttext_file]  
          [-Tooperator_name]  
          [-HtmlRpthtml_file [-DelHtmlRpt <time_period>] ]  
          [-RmUnusedSpacethreshold_percentfree_percent]  
          [-CkDB | -CkDBNoIdx]  
          [-CkAl | -CkAlNoIdx]  
          [-CkCat]  
          [-UpdOptiStatssample_percent]  
          [-RebldIdxfree_space]  
          [-SupportComputedColumn]  
          [-WriteHistory]  
          [  
               {-BkUpDB [backup_path] | -BkUpLog [backup_path] }  
               {-BkUpMedia  
                    {DISK [  
                           [-DelBkUps<time_period>]   
                           [-CrBkSubDir ]   
                           [-UseDefDir ]   
                          ]  
                     | TAPE   
                    }  
               }  
               [-BkUpOnlyIfClean]  
               [-VrfyBackup]  
          ]  
     }  
]  
<time_period> ::=  
number[minutes | hours | days | weeks | months]  
```  
  
## <a name="arguments"></a><span data-ttu-id="5bf3d-111">Аргументы</span><span class="sxs-lookup"><span data-stu-id="5bf3d-111">Arguments</span></span>  
 <span data-ttu-id="5bf3d-112">Параметры и их значения должны разделяться пробелами.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-112">The parameters and their values must be separated by a space.</span></span> <span data-ttu-id="5bf3d-113">Например, пробел должен быть между **-S** и аргументом *server_name*.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-113">For example, there must be a space between **-S** and *server_name*.</span></span>  
  
 <span data-ttu-id="5bf3d-114">**-?**</span><span class="sxs-lookup"><span data-stu-id="5bf3d-114">**-?**</span></span>  
 <span data-ttu-id="5bf3d-115">Указывает, что должна быть возвращена диаграмма синтаксиса **sqlmaint** .</span><span class="sxs-lookup"><span data-stu-id="5bf3d-115">Specifies that the syntax diagram for **sqlmaint** be returned.</span></span> <span data-ttu-id="5bf3d-116">При использовании этого параметра использование других параметров не допускается.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-116">This parameter must be used alone.</span></span>  
  
 <span data-ttu-id="5bf3d-117">**-S** _server_name_[ **\\** _instance_name_]</span><span class="sxs-lookup"><span data-stu-id="5bf3d-117">**-S** _server_name_[ **\\**_instance_name_]</span></span>  
 <span data-ttu-id="5bf3d-118">Позволяет указать целевой экземпляр [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5bf3d-118">Specifies the target instance of [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5bf3d-119">Укажите значение *имя_сервера* , чтобы подключиться к экземпляру компонента [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] по умолчанию на этом сервере.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-119">Specify *server_name* to connect to the default instance of [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] on that server.</span></span> <span data-ttu-id="5bf3d-120">Укажите *server_name **_\\_** instance_name* для подключения к именованному экземпляру [!INCLUDE[ssDE](../includes/ssde-md.md)] служб на этом сервере.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-120">Specify *server_name\*\*_\\_*\* instance_name\* to connect to a named instance of [!INCLUDE[ssDE](../includes/ssde-md.md)] on that server.</span></span> <span data-ttu-id="5bf3d-121">Если сервер не указан, **sqlmaint** подключается к экземпляру [!INCLUDE[ssDE](../includes/ssde-md.md)] по умолчанию на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-121">If no server is specified, **sqlmaint** connects to the default instance of [!INCLUDE[ssDE](../includes/ssde-md.md)] on the local computer.</span></span>  
  
 <span data-ttu-id="5bf3d-122">**-U** _имя_для_входа_</span><span class="sxs-lookup"><span data-stu-id="5bf3d-122">**-U** _login_ID_</span></span>  
 <span data-ttu-id="5bf3d-123">Указывает используемый идентификатор входа при соединении с сервером.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-123">Specifies the login ID to use when connecting to the server.</span></span> <span data-ttu-id="5bf3d-124">Если этот параметр не указан, **sqlmaint** пытается использовать проверку подлинности [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-124">If not supplied, **sqlmaint** attempts to use [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Authentication.</span></span> <span data-ttu-id="5bf3d-125">Если аргумент *login_ID* содержит специальные символы, он должен быть заключен в двойные кавычки ("). В противном случае использование двойных кавычек необязательно.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-125">If *login_ID* contains special characters, it must be enclosed in double quotation marks ("); otherwise, the double quotation marks are optional.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5bf3d-126">По возможности используйте аутентификацию Windows.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-126">When possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="5bf3d-127">**-P** _пароль_</span><span class="sxs-lookup"><span data-stu-id="5bf3d-127">**-P** _password_</span></span>  
 <span data-ttu-id="5bf3d-128">Указывает пароль для идентификатора имени входа.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-128">Specifies the password for the login ID.</span></span> <span data-ttu-id="5bf3d-129">Используется только вместе с параметром **-U** .</span><span class="sxs-lookup"><span data-stu-id="5bf3d-129">Only valid if the **-U** parameter is also supplied.</span></span> <span data-ttu-id="5bf3d-130">Если аргумент *password* содержит специальные символы, он должен быть заключен в двойные кавычки. В противном случае использование двойных кавычек необязательно.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-130">If *password* contains special characters, it must be enclosed in double quotation marks; otherwise, the double quotation marks are optional.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5bf3d-131">Маскировка пароля не производится.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-131">The password is not masked.</span></span> <span data-ttu-id="5bf3d-132">По возможности используйте аутентификацию Windows.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-132">When possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="5bf3d-133">**-D** _имя_базы_данных_</span><span class="sxs-lookup"><span data-stu-id="5bf3d-133">**-D** _database_name_</span></span>  
 <span data-ttu-id="5bf3d-134">Указывает имя базы данных, с которой будут производиться операции обслуживания.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-134">Specifies the name of the database in which to perform the maintenance operation.</span></span> <span data-ttu-id="5bf3d-135">Если аргумент *database_name* содержит специальные символы, он должен быть заключен в двойные кавычки. В противном случае использование двойных кавычек необязательно.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-135">If *database_name* contains special characters, it must be enclosed in double quotation marks; otherwise, the double quotation marks are optional.</span></span>  
  
 <span data-ttu-id="5bf3d-136">**-PlanName** _имя_</span><span class="sxs-lookup"><span data-stu-id="5bf3d-136">**-PlanName** _name_</span></span>  
 <span data-ttu-id="5bf3d-137">Указывает имя плана обслуживания базы данных, определенного с помощью мастера планов обслуживания баз данных.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-137">Specifies the name of a database maintenance plan defined using the Database Maintenance Plan Wizard.</span></span> <span data-ttu-id="5bf3d-138">Единственные сведения, которые программа **sqlmaint** использует из этого плана, — это список баз данных в плане.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-138">The only information **sqlmaint** uses from the plan is the list of the databases in the plan.</span></span> <span data-ttu-id="5bf3d-139">Любые действия по обслуживанию, которые указываются в других параметрах **sqlmaint** , применяются ко всем базам данных из этого списка.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-139">Any maintenance activities you specify in the other **sqlmaint** parameters are applied to this list of databases.</span></span>  
  
 <span data-ttu-id="5bf3d-140">**-PlanID** _GUID_</span><span class="sxs-lookup"><span data-stu-id="5bf3d-140">**-PlanID** _guid_</span></span>  
 <span data-ttu-id="5bf3d-141">Указывает идентификатор GUID плана обслуживания базы данных, определенного с помощью мастера планов обслуживания баз данных.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-141">Specifies the globally unique identifier (GUID) of a database maintenance plan defined using the Database Maintenance Plan Wizard.</span></span> <span data-ttu-id="5bf3d-142">Единственные сведения, которые программа **sqlmaint** использует из этого плана, — это список баз данных в плане.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-142">The only information **sqlmaint** uses from the plan is the list of the databases in the plan.</span></span> <span data-ttu-id="5bf3d-143">Любые действия по обслуживанию, которые указываются в других параметрах **sqlmaint** , применяются ко всем базам данных из этого списка.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-143">Any maintenance activities you specify in the other **sqlmaint** parameters are applied to this list of databases.</span></span> <span data-ttu-id="5bf3d-144">Значение должно совпадать со значением аргумента plan_id в таблице msdb.dbo.sysdbmaintplans.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-144">This must match a plan_id value in msdb.dbo.sysdbmaintplans.</span></span>  
  
 <span data-ttu-id="5bf3d-145">**-Rpt** _текстовый_файл_</span><span class="sxs-lookup"><span data-stu-id="5bf3d-145">**-Rpt** _text_file_</span></span>  
 <span data-ttu-id="5bf3d-146">Указывает полный путь и имя файла, в котором будет сформирован отчет.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-146">Specifies the full path and name of the file into which the report is to be generated.</span></span> <span data-ttu-id="5bf3d-147">Отчет также выводится на экран.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-147">The report is also generated on the screen.</span></span> <span data-ttu-id="5bf3d-148">В отчете сведения о версии отражаются при помощи добавления даты к имени файла.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-148">The report maintains version information by adding a date to the file name.</span></span> <span data-ttu-id="5bf3d-149">Дата формируется следующим образом: в конце имени файла, но перед точкой в формате _*ггггММддччмм*.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-149">The date is generated as follows: at the end of the file name but before the period, in the form _*yyyyMMddhhmm*.</span></span> <span data-ttu-id="5bf3d-150">*гггг* = год, *ММ* = месяц, *дд* = день, *hh* = часы, *мм* = минуты.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-150">*yyyy* = year, *MM* = month, *dd* = day, *hh* = hour, *mm* = minute.</span></span>  
  
 <span data-ttu-id="5bf3d-151">При запуске программы в 10:23</span><span class="sxs-lookup"><span data-stu-id="5bf3d-151">If you run the utility at 10:23 A.M.</span></span> <span data-ttu-id="5bf3d-152">1 декабря 1996 года аргумент *text_file* будет иметь следующее значение:</span><span class="sxs-lookup"><span data-stu-id="5bf3d-152">on December 1, 1996, and this is the *text_file* value:</span></span>  
  
```  
c:\Program Files\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint.rpt  
```  
  
 <span data-ttu-id="5bf3d-153">Имя создаваемого файла:</span><span class="sxs-lookup"><span data-stu-id="5bf3d-153">The generated file name is:</span></span>  
  
```  
c:\Program Files\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint_199612011023.rpt  
```  
  
 <span data-ttu-id="5bf3d-154">Когда *sqlmaint* обращается к удаленному серверу, в качестве аргумента **text_file** необходимо указывать полное UNC-имя.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-154">The full Universal Naming Convention (UNC) file name is required for *text_file* when **sqlmaint** accesses a remote server.</span></span>  
  
 <span data-ttu-id="5bf3d-155">**— Для** _operator_name_</span><span class="sxs-lookup"><span data-stu-id="5bf3d-155">**-To** _operator_name_</span></span>  
 <span data-ttu-id="5bf3d-156">Указывает оператора, которому будет отправлен сформированный отчет через службу SQL Mail.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-156">Specifies the operator to whom the generated report is sent through SQL Mail.</span></span>  
  
 <span data-ttu-id="5bf3d-157">**-HtmlRpt** _файл_HTML_</span><span class="sxs-lookup"><span data-stu-id="5bf3d-157">**-HtmlRpt** _html_file_</span></span>  
 <span data-ttu-id="5bf3d-158">Указывает полный путь и имя файла, в котором будет сформирован HTML-отчет.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-158">Specifies the full path and name of the file into which an HTML report is to be generated.</span></span> <span data-ttu-id="5bf3d-159">Программа**sqlmaint** формирует имя файла, добавляя к нему строку в формате _*ггггММддччмм* (как и в случае с параметром **-Rpt** ).</span><span class="sxs-lookup"><span data-stu-id="5bf3d-159">**sqlmaint** generates the file name by appending a string of the format _*yyyyMMddhhmm* to the file name, just as it does for the **-Rpt** parameter.</span></span>  
  
 <span data-ttu-id="5bf3d-160">Когда *sqlmaint* обращается к удаленному серверу, в качестве аргумента **html_file** необходимо указывать полное UNC-имя файла.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-160">The full UNC file name is required for *html_file* when **sqlmaint** accesses a remote server.</span></span>  
  
 <span data-ttu-id="5bf3d-161">**-DelHtmlRpt** \<*time_period*></span><span class="sxs-lookup"><span data-stu-id="5bf3d-161">**-DelHtmlRpt** \<*time_period*></span></span>  
 <span data-ttu-id="5bf3d-162">Задает удаление всех отчетов в формате HTML в каталоге отчетов, если интервал времени с момента создания отчета превышает значение \<*time_period*>.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-162">Specifies that any HTML report in the report directory be deleted if the time interval after the creation of the report file exceeds \<*time_period*>.</span></span> <span data-ttu-id="5bf3d-163">**-DelHtmlRpt** ищет файлы, имена которых соответствуют шаблону, сформированному на основе параметра *html_file*.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-163">**-DelHtmlRpt** looks for files whose name fits the pattern generated from the *html_file* parameter.</span></span> <span data-ttu-id="5bf3d-164">Если значение аргумента *html_file* равно C:\Program Files\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint.htm, параметр **-DelHtmlRpt** предпишет программе **sqlmaint** удалить все файлы, имена которых соответствуют шаблону C:\Program Files\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint\*.htm и которые являются более старыми, чем указано в значении \<*time_period*>.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-164">If *html_file* is c:\Program Files\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint.htm, then **-DelHtmlRpt** causes **sqlmaint** to delete any files whose names match the pattern C:\Program Files\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint\*.htm and that are older than the specified \<*time_period*>.</span></span>  
  
 <span data-ttu-id="5bf3d-165">**-RmUnusedSpace** _пороговое_значение_(процент) свободное_пространство_(процент)_</span><span class="sxs-lookup"><span data-stu-id="5bf3d-165">**-RmUnusedSpace** _threshold_percent free_percent_</span></span>  
 <span data-ttu-id="5bf3d-166">Указывает, что нужно удалить неиспользуемое пространство из базы данных, указанной в параметре **-D**.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-166">Specifies that unused space be removed from the database specified in **-D**.</span></span> <span data-ttu-id="5bf3d-167">Этот параметр полезен только для тех баз данных, в которых задан автоматический рост.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-167">This option is only useful for databases that are defined to grow automatically.</span></span> <span data-ttu-id="5bf3d-168">Аргумент*Threshold_percent* задает размер в мегабайтах, которого должна достичь база данных, прежде чем **sqlmaint** попытается удалить неиспользованное пространство данных.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-168">*Threshold_percent* specifies in megabytes the size that the database must reach before **sqlmaint** attempts to remove unused data space.</span></span> <span data-ttu-id="5bf3d-169">Если база данных меньше значения *threshold_percent*, никакие действия не выполняются.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-169">If the database is smaller than the *threshold_percent*, no action is taken.</span></span> <span data-ttu-id="5bf3d-170">Значение*free_percent* задает размер сохраняемого неиспользуемого пространства в базе данных, указываемого в виде процента от конечного размера базы данных.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-170">*Free_percent* specifies how much unused space must remain in the database, specified as a percentage of the final size of the database.</span></span> <span data-ttu-id="5bf3d-171">Например, если база данных размером 200 MБ содержит 100 MБ данных, то указание значения 10 в качестве аргумента *free_percent* приводит к тому, что конечный размер базы данных будет составлять 110 MБ.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-171">For example, if a 200-MB database contains 100 MB of data, specifying 10 for *free_percent* results in the final database size being 110 MB.</span></span> <span data-ttu-id="5bf3d-172">Обратите внимание, что увеличения базы данных не происходит, если ее размер меньше суммы значения *free_percent* и объема данных в базе.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-172">Note that a database is not expanded if it is smaller than *free_percent* plus the amount of data in the database.</span></span> <span data-ttu-id="5bf3d-173">Например, если база данных размером 108 MБ содержит данные размером 100 MБ, то указание 10 в качестве значения *free_percent* не приведет к увеличению базы данных до 110 MБ, ее размер останется равным 108 MБ.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-173">For example, if a 108-MB database has 100 MB of data, specifying 10 for *free_percent* does not expand the database to 110 MB; it remains at 108 MB.</span></span>  
  
 <span data-ttu-id="5bf3d-174">**-CkDB** |  **- CkDBNoIdx**</span><span class="sxs-lookup"><span data-stu-id="5bf3d-174">**-CkDB** | **-CkDBNoIdx**</span></span>  
 <span data-ttu-id="5bf3d-175">Запускает выполнение инструкции DBCC CHECKDB или DBCC CHECKDB с параметром NOINDEX в базе данных, указанной в параметре **-D**.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-175">Specifies that a DBCC CHECKDB statement or a DBCC CHECKDB statement with the NOINDEX option be run in the database specified in **-D**.</span></span> <span data-ttu-id="5bf3d-176">Дополнительные сведения см. в разделе DBCC CHECKDB.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-176">For more information, see DBCC CHECKDB.</span></span>  
  
 <span data-ttu-id="5bf3d-177">Если при запуске *sqlmaint* база данных уже используется, в **text_file** записывается предупреждение.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-177">A warning is written to *text_file* if the database is in use when **sqlmaint** runs.</span></span>  
  
 <span data-ttu-id="5bf3d-178">**-CkAl** |  **- CkAlNoIdx**</span><span class="sxs-lookup"><span data-stu-id="5bf3d-178">**-CkAl** | **-CkAlNoIdx**</span></span>  
 <span data-ttu-id="5bf3d-179">Запускает выполнение инструкции DBCC CHECKALLOC с параметром NOINDEX в базе данных, указанной в параметре **-D**.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-179">Specifies that a DBCC CHECKALLOC statement with the NOINDEX option be run in the database specified in **-D**.</span></span> <span data-ttu-id="5bf3d-180">Дополнительные сведения см. в разделе [DBCC CHECKALLOC (Transact-SQL)](/sql/t-sql/database-console-commands/dbcc-checkalloc-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5bf3d-180">For more information, see [DBCC CHECKALLOC &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkalloc-transact-sql).</span></span>  
  
 <span data-ttu-id="5bf3d-181">**-CkCat**</span><span class="sxs-lookup"><span data-stu-id="5bf3d-181">**-CkCat**</span></span>  
 <span data-ttu-id="5bf3d-182">Запускает выполнение инструкции DBCC CHECKCATALOG (Transact-SQL) в базе данных, указанной в параметре **-D**.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-182">Specifies that a DBCC CHECKCATALOG (Transact-SQL) statement be run in the database specified in **-D**.</span></span> <span data-ttu-id="5bf3d-183">Дополнительные сведения см. в разделе [DBCC CHECKCATALOG (Transact-SQL)](/sql/t-sql/database-console-commands/dbcc-checkcatalog-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5bf3d-183">For more information, see [DBCC CHECKCATALOG &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkcatalog-transact-sql).</span></span>  
  
 <span data-ttu-id="5bf3d-184">**-UpdOptiStats** _пример_значения (процент)_</span><span class="sxs-lookup"><span data-stu-id="5bf3d-184">**-UpdOptiStats** _sample_percent_</span></span>  
 <span data-ttu-id="5bf3d-185">Задает применение следующей инструкции к каждой таблице базы данных:</span><span class="sxs-lookup"><span data-stu-id="5bf3d-185">Specifies that the following statement be run on each table in the database:</span></span>  
  
```  
UPDATE STATISTICS table WITH SAMPLE sample_percent PERCENT;  
```  
  
 <span data-ttu-id="5bf3d-186">Если в таблицах есть вычисляемые столбцы, при использовании параметра **-UpdOptiStats** необходимо также задавать аргумент **-SupportedComputedColumn**.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-186">If the tables contain computed columns, you must also specify the **-SupportedComputedColumn** argument when you use **-UpdOptiStats**.</span></span>  
  
 <span data-ttu-id="5bf3d-187">Дополнительные сведения см. в статье [UPDATE STATISTICS (Transact-SQL)](/sql/t-sql/statements/update-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5bf3d-187">For more information, see [UPDATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/update-statistics-transact-sql).</span></span>  
  
 <span data-ttu-id="5bf3d-188">**-RebldIdx** _свободное_пространство_</span><span class="sxs-lookup"><span data-stu-id="5bf3d-188">**-RebldIdx** _free_space_</span></span>  
 <span data-ttu-id="5bf3d-189">Задает перестройку индексов в таблицах базы данных-получателя с использованием процентного значения *free_space* , которое составляет 100 % в сумме с коэффициентом заполнения.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-189">Specifies that indexes on tables in the target database should be rebuilt by using the *free_space* percent value as the inverse of the fill factor.</span></span> <span data-ttu-id="5bf3d-190">Например, если процент *free_space* равен 30, то используемый коэффициент заполнения равен 70.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-190">For example, if *free_space* percentage is 30, then the fill factor used is 70.</span></span> <span data-ttu-id="5bf3d-191">Если заданное значение процентов *free_space* равно 100, то повторное создание индексов происходит с использованием начального коэффициента заполнения.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-191">If a *free_space* percentage value of 100 is specified, then the indexes are rebuilt with the original fill factor value.</span></span>  
  
 <span data-ttu-id="5bf3d-192">Если индексы построены на вычисляемых столбцах, при использовании параметра **-RebldIdx** необходимо также задавать аргумент **-SupportComputedColumn**.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-192">If the indexes are on computed columns, you must also specify the **-SupportComputedColumn** argument when you use **-RebldIdx**.</span></span>  
  
 <span data-ttu-id="5bf3d-193">**-RebldIdx**</span><span class="sxs-lookup"><span data-stu-id="5bf3d-193">**-SupportComputedColumn**</span></span>  
 <span data-ttu-id="5bf3d-194">Обязательно указывается, если программа **sqlmaint** должна выполнить команды обслуживания DBCC для вычисляемых столбцов.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-194">Must be specified to run DBCC maintenance commands with **sqlmaint** on computed columns.</span></span>  
  
 <span data-ttu-id="5bf3d-195">**-WriteHistory**</span><span class="sxs-lookup"><span data-stu-id="5bf3d-195">**-WriteHistory**</span></span>  
 <span data-ttu-id="5bf3d-196">Задает создание записи журнала в msdb.dbo.sysdbmaintplan_history для каждой операции обслуживания, выполненной программой **sqlmaint**.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-196">Specifies that an entry be made in msdb.dbo.sysdbmaintplan_history for each maintenance action performed by **sqlmaint**.</span></span> <span data-ttu-id="5bf3d-197">Если указано значение **-PlanName** или **-PlanID** , то в записях журнала в sysdbmaintplan_history присутствует идентификатор указанного плана.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-197">If **-PlanName** or **-PlanID** is specified, the entries in sysdbmaintplan_history use the ID of the specified plan.</span></span> <span data-ttu-id="5bf3d-198">Если указано значение **-D** , то в записи журнала в sysdbmaintplan_history в качестве значения идентификатора плана содержатся нули.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-198">If **-D** is specified, the entries in sysdbmaintplan_history are made with zeroes for the plan ID.</span></span>  
  
 <span data-ttu-id="5bf3d-199">**-BkUpDB** [ *backup_path*] |  **-BkUpLog** [ *backup_path* ]</span><span class="sxs-lookup"><span data-stu-id="5bf3d-199">**-BkUpDB** [ *backup_path*] |  **-BkUpLog** [ *backup_path* ]</span></span>  
 <span data-ttu-id="5bf3d-200">Задает действие резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-200">Specifies a backup action.</span></span> <span data-ttu-id="5bf3d-201">**-BkUpDb** выполняет резервное копирование всей базы данных.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-201">**-BkUpDb** backs up the entire database.</span></span> <span data-ttu-id="5bf3d-202">**-BkUpLog** создает резервную копию только журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-202">**-BkUpLog** backs up only the transaction log.</span></span>  
  
 <span data-ttu-id="5bf3d-203">*backup_path* указывает каталог для резервной копии.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-203">*backup_path* specifies the directory for the backup.</span></span> <span data-ttu-id="5bf3d-204">Аргумент*backup_path* не нужно указывать, если указан параметр **-UseDefDir** . Если указать аргумент и параметр, параметр **-UseDefDir** переопределит аргумент.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-204">*backup_path* is not needed if **-UseDefDir** is also specified, and is overridden by **-UseDefDir** if both are specified.</span></span> <span data-ttu-id="5bf3d-205">Резервная копия может размещаться в каталоге или по адресу ленточного устройства (например, \\\\.\TAPE0).</span><span class="sxs-lookup"><span data-stu-id="5bf3d-205">The backup can be placed in a directory or a tape device address (for example, \\\\.\TAPE0).</span></span> <span data-ttu-id="5bf3d-206">Имя файла резервной копии базы данных создается автоматически следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5bf3d-206">The file name for a database backup is generated automatically as follows:</span></span>  
  
```  
dbname_db_yyyyMMddhhmm.BAK  
  
```  
  
 <span data-ttu-id="5bf3d-207">где</span><span class="sxs-lookup"><span data-stu-id="5bf3d-207">where</span></span>  
  
-   <span data-ttu-id="5bf3d-208">*dbname* — имя базы данных, резервная копия которой создается.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-208">*dbname* is the name of the database being backed up.</span></span>  
  
-   <span data-ttu-id="5bf3d-209">*ггггММддччмм* — время операции резервного копирования, где *гггг* = год, *ММ* = месяц, *дд* = день, *hh* = часы, а *мм* = минуты.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-209">*yyyyMMddhhmm* is the time of the backup operation with *yyyy* = year, *MM* = month, *dd* = day, *hh* = hour, and *mm* = minute.</span></span>  
  
 <span data-ttu-id="5bf3d-210">Имя файла резервной копии журнала транзакций автоматически создается в аналогичном формате:</span><span class="sxs-lookup"><span data-stu-id="5bf3d-210">The file name for a transaction backup is generated automatically with a similar format:</span></span>  
  
```  
dbname_log_yyyymmddhhmm.BAK  
  
```  
  
 <span data-ttu-id="5bf3d-211">При использовании параметра **-BkUpDB** необходимо также указать носитель данных (указывается с помощью параметра **-BkUpMedia** ).</span><span class="sxs-lookup"><span data-stu-id="5bf3d-211">If you use the **-BkUpDB** parameter, you must also specify the media by using the **-BkUpMedia** parameter.</span></span>  
  
 <span data-ttu-id="5bf3d-212">**-BkUpMedia**</span><span class="sxs-lookup"><span data-stu-id="5bf3d-212">**-BkUpMedia**</span></span>  
 <span data-ttu-id="5bf3d-213">Задает тип носителя для резервной копии, DISK (диск) или TAPE (лента).</span><span class="sxs-lookup"><span data-stu-id="5bf3d-213">Specifies the media type of the backup, either DISK or TAPE.</span></span>  
  
 <span data-ttu-id="5bf3d-214">**DISK;**</span><span class="sxs-lookup"><span data-stu-id="5bf3d-214">**DISK**</span></span>  
 <span data-ttu-id="5bf3d-215">Указывает, что носителем данных резервных копий является диск.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-215">Specifies that the backup medium is disk.</span></span>  
  
 <span data-ttu-id="5bf3d-216">**-Делбкупс**\< *time_period* ></span><span class="sxs-lookup"><span data-stu-id="5bf3d-216">**-DelBkUps**\< *time_period* ></span></span>  
 <span data-ttu-id="5bf3d-217">Задает удаление всех файлов резервных копий в каталоге резервных копий, если интервал времени с момента создания резервной копии превышает значение \<*time_period*>.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-217">For disk backups, specifies that any backup file in the backup directory be deleted if the time interval after the creation of the backup exceeds the \<*time_period*>.</span></span>  
  
 <span data-ttu-id="5bf3d-218">**-CrBkSubDir**</span><span class="sxs-lookup"><span data-stu-id="5bf3d-218">**-CrBkSubDir**</span></span>  
 <span data-ttu-id="5bf3d-219">При резервном копировании дисков, если указан параметр *-UseDefDir*, создает вложенный каталог в каталоге [ **backup_path** ] или в каталоге резервных копий по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-219">For disk backups, specifies that a subdirectory be created in the [*backup_path*] directory or in the default backup directory if **-UseDefDir** is also specified.</span></span> <span data-ttu-id="5bf3d-220">Имя вложенного каталога создается на основе имени базы данных, указанной в параметре **-D**.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-220">The name of the subdirectory is generated from the database name specified in **-D**.</span></span> <span data-ttu-id="5bf3d-221">Чтобы быстро перенести все резервные копии различных баз данных в отдельные вложенные каталоги, не изменяя параметр **-CrBkSubDir** , задайте параметр *-CrBkSubDir* .</span><span class="sxs-lookup"><span data-stu-id="5bf3d-221">**-CrBkSubDir** offers an easy way to put all the backups for different databases into separate subdirectories without having to change the *backup_path* parameter.</span></span>  
  
 <span data-ttu-id="5bf3d-222">**-UseDefDir**</span><span class="sxs-lookup"><span data-stu-id="5bf3d-222">**-UseDefDir**</span></span>  
 <span data-ttu-id="5bf3d-223">Для резервного копирования на диск задает создание файла резервной копии в каталоге резервных копий по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-223">For disk backups, specifies that the backup file be created in the default backup directory.</span></span> <span data-ttu-id="5bf3d-224">Параметр**UseDefDir** переопределяет значение *backup_path* , если они указаны одновременно.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-224">**UseDefDir** overrides *backup_path* if both are specified.</span></span> <span data-ttu-id="5bf3d-225">При установке [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] с параметрами по умолчанию каталогом резервных копий является C:\Program Files\Microsoft SQL Server\MSSQL10_50.MSSQLSERVER\MSSQL\Backup.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-225">With a default [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] setup, the default backup directory is C:\Program Files\Microsoft SQL Server\MSSQL10_50.MSSQLSERVER\MSSQL\Backup.</span></span>  
  
 <span data-ttu-id="5bf3d-226">**TAPE;**</span><span class="sxs-lookup"><span data-stu-id="5bf3d-226">**TAPE**</span></span>  
 <span data-ttu-id="5bf3d-227">Указывает, что носителем данных резервных копий является ленточный накопитель.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-227">Specifies that the backup medium is tape.</span></span>  
  
 <span data-ttu-id="5bf3d-228">**-BkUpOnlyIfClean**</span><span class="sxs-lookup"><span data-stu-id="5bf3d-228">**-BkUpOnlyIfClean**</span></span>  
 <span data-ttu-id="5bf3d-229">Указывает, что операция резервного копирования производится только в том случае, если заданные проверки **-Ck** не обнаружили ошибок в данных.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-229">Specifies that the backup occur only if any specified **-Ck** checks did not find problems with the data.</span></span> <span data-ttu-id="5bf3d-230">Действия по обслуживанию запускаются в порядке, в котором они указаны в командной строке.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-230">Maintenance actions run in the same sequence as they appear in the command prompt.</span></span> <span data-ttu-id="5bf3d-231">Если вы хотите указать параметр **-BkUpOnlyIfClean**, укажите перед параметром **-BkUpDB**-BkUpLog **параметр**-CkDB **,** -CkDBNoIdx **,** -CkAl **,** -CkAlNoIdx **,** / **-CkTxtAl** или **-CkCat**. Иначе резервное копирование будет выполняться независимо от наличия ошибок.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-231">Specify the parameters **-CkDB**, **-CkDBNoIdx**, **-CkAl**, **-CkAlNoIdx**, **-CkTxtAl**, or **-CkCat** before the **-BkUpDB**/**-BkUpLog** parameter(s) if you are also going to specify **-BkUpOnlyIfClean**, or the backup occurs whether or not the check reports problems.</span></span>  
  
 <span data-ttu-id="5bf3d-232">**-VrfyBackup**</span><span class="sxs-lookup"><span data-stu-id="5bf3d-232">**-VrfyBackup**</span></span>  
 <span data-ttu-id="5bf3d-233">Задает выполнение RESTORE VERIFYONLY на резервной копии по завершении ее создания.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-233">Specifies that RESTORE VERIFYONLY be run on the backup when it completes.</span></span>  
  
 <span data-ttu-id="5bf3d-234">*number*[**minutes**| **hours**| **day**| **weeks**| **months**]</span><span class="sxs-lookup"><span data-stu-id="5bf3d-234">*number*[**minutes**| **hours**| **day**| **weeks**| **months**]</span></span>  
 <span data-ttu-id="5bf3d-235">Задает интервал времени, используемый для определения, является ли отчет или файл резервной копии достаточно старым для его удаления.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-235">Specifies the time interval used to determine if a report or backup file is old enough to be deleted.</span></span> <span data-ttu-id="5bf3d-236">*number* — целое число, за которым (без пробела) следует единица измерения времени.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-236">*number* is an integer followed (without a space) by a unit of time.</span></span> <span data-ttu-id="5bf3d-237">Допустимые варианты:</span><span class="sxs-lookup"><span data-stu-id="5bf3d-237">Valid examples:</span></span>  
  
-   <span data-ttu-id="5bf3d-238">**12недель**</span><span class="sxs-lookup"><span data-stu-id="5bf3d-238">**12weeks**</span></span>  
  
-   <span data-ttu-id="5bf3d-239">**3месяца**</span><span class="sxs-lookup"><span data-stu-id="5bf3d-239">**3months**</span></span>  
  
-   <span data-ttu-id="5bf3d-240">**15дней**</span><span class="sxs-lookup"><span data-stu-id="5bf3d-240">**15days**</span></span>  
  
 <span data-ttu-id="5bf3d-241">Если указано только *number* , то используемой по умолчанию частью даты будут **недель**.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-241">If only *number* is specified, the default date part is **weeks**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5bf3d-242">Remarks</span><span class="sxs-lookup"><span data-stu-id="5bf3d-242">Remarks</span></span>  
 <span data-ttu-id="5bf3d-243">Программа **sqlmaint** выполняет операции обслуживания с одной или несколькими базами данных.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-243">The **sqlmaint** utility performs maintenance operations on one or more databases.</span></span> <span data-ttu-id="5bf3d-244">Если указан параметр **-D** , операции, заданные в остальных параметрах, выполняются только с указанной базой данных.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-244">If **-D** is specified, the operations specified in the remaining switches are performed only on the specified database.</span></span> <span data-ttu-id="5bf3d-245">Если указан параметр **-PlanName** или **-PlanID** , **sqlmaint** получает из указанного плана обслуживания только сведения о списке баз данных.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-245">If **-PlanName** or **-PlanID** are specified, the only information **sqlmaint** retrieves from the specified maintenance plan is the list of databases in the plan.</span></span> <span data-ttu-id="5bf3d-246">Все операции, указанные в остальных параметрах **sqlmaint** , применяются ко всем базам данных, которые указаны в полученном из плана списке.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-246">All operations specified in the remaining **sqlmaint** parameters are applied against each database in the list obtained from the plan.</span></span> <span data-ttu-id="5bf3d-247">Программа **sqlmaint** не выполняет операции обслуживания, определенные в самом плане.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-247">The **sqlmaint** utility does not apply any of the maintenance activities defined in the plan itself.</span></span>  
  
 <span data-ttu-id="5bf3d-248">В случае успешного выполнения **sqlmaint** возвращает 0, а в случае ошибки — 1.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-248">The **sqlmaint** utility returns 0 if it runs successfully or 1 if it fails.</span></span> <span data-ttu-id="5bf3d-249">Сообщение об ошибке выводится:</span><span class="sxs-lookup"><span data-stu-id="5bf3d-249">Failure is reported:</span></span>  
  
-   <span data-ttu-id="5bf3d-250">в случае неудачи любой из операций обслуживания;</span><span class="sxs-lookup"><span data-stu-id="5bf3d-250">If any of the maintenance actions fail.</span></span>  
  
-   <span data-ttu-id="5bf3d-251">если проверка **-CkDB**, **-CkDBNoIdx**, **-CkAl**, **-CkAlNoIdx**, **-CkTxtAl**или **-CkCat** обнаруживает ошибки в данных;</span><span class="sxs-lookup"><span data-stu-id="5bf3d-251">If **-CkDB**, **-CkDBNoIdx**, **-CkAl**, **-CkAlNoIdx**, **-CkTxtAl**, or **-CkCat** checks find problems with the data.</span></span>  
  
-   <span data-ttu-id="5bf3d-252">в случае общего сбоя.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-252">If a general failure is encountered.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="5bf3d-253">Разрешения</span><span class="sxs-lookup"><span data-stu-id="5bf3d-253">Permissions</span></span>  
 <span data-ttu-id="5bf3d-254">Программу **sqlmaint** может выполнить любой пользователь Windows, у которого есть разрешения на **чтение и выполнение** файла `sqlmaint.exe`(по умолчанию находится в папке `x:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER1\MSSQL\Binn` ).</span><span class="sxs-lookup"><span data-stu-id="5bf3d-254">The **sqlmaint** utility can be executed by any Windows user with **Read and Execute** permission on `sqlmaint.exe`, which by default is stored in the `x:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER1\MSSQL\Binn` folder.</span></span> <span data-ttu-id="5bf3d-255">Кроме того, учетные данные [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , указанные в параметре **-login_ID** , должны иметь разрешения [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , необходимые для выполнения указанного действия.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-255">Additionally, the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login specified with **-login_ID** must have the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] permissions required to perform the specified action.</span></span> <span data-ttu-id="5bf3d-256">Если соединение с [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] использует проверку подлинности Windows, имя входа [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , сопоставленное с прошедшим проверку пользователем Windows, должно иметь разрешения [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , достаточные для выполнения указанного действия.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-256">If the connection to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] uses Windows Authentication, the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login mapped to the authenticated Windows user must have the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] permissions required to perform the specified action.</span></span>  
  
 <span data-ttu-id="5bf3d-257">Например, для параметра **-BkUpDB** требуется разрешение на выполнение инструкции BACKUP,</span><span class="sxs-lookup"><span data-stu-id="5bf3d-257">For example, using the **-BkUpDB** requires permission to execute the BACKUP statement.</span></span> <span data-ttu-id="5bf3d-258">а использование аргумента **-UpdOptiStats** предполагает наличие разрешения на выполнение инструкции UPDATE STATISTICS.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-258">And using the **-UpdOptiStats** argument requires permission to execute the UPDATE STATISTICS statement.</span></span> <span data-ttu-id="5bf3d-259">Дополнительные сведения см. в подразделах «Разрешения» соответствующих разделов электронной документации.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-259">For more information, see the "Permissions" sections of the corresponding topics in Books Online.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="5bf3d-260">Примеры</span><span class="sxs-lookup"><span data-stu-id="5bf3d-260">Examples</span></span>  
  
### <a name="a-performing-dbcc-checks-on-a-database"></a><span data-ttu-id="5bf3d-261">A.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-261">A.</span></span> <span data-ttu-id="5bf3d-262">Выполнение проверок DBCC в базе данных</span><span class="sxs-lookup"><span data-stu-id="5bf3d-262">Performing DBCC checks on a database</span></span>  
  
```  
sqlmaint -S MyServer -D AdventureWorks2012 -CkDB -CkAl -CkCat -Rpt C:\MyReports\AdvWks_chk.rpt  
```  
  
### <a name="b-updating-statistics-using-a-15-sample-in-all-databases-in-a-plan-also-shrink-any-of-the-database-that-have-reached-110-mb-to-having-only-10-free-space"></a><span data-ttu-id="5bf3d-263">Б.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-263">B.</span></span> <span data-ttu-id="5bf3d-264">Обновление статистики, используя в качестве образца 15 % данных из всех баз данных, содержащихся в плане.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-264">Updating statistics using a 15% sample in all databases in a plan.</span></span> <span data-ttu-id="5bf3d-265">Также сжимает все базы данных, размер которых достиг 110 MБ, чтобы свободное пространство в них составляло только 10%</span><span class="sxs-lookup"><span data-stu-id="5bf3d-265">Also, shrink any of the database that have reached 110 MB to having only 10% free space</span></span>  
  
```  
sqlmaint -S MyServer -PlanName MyUserDBPlan -UpdOptiStats 15 -RmUnusedSpace 110 10  
```  
  
### <a name="c-backing-up-all-the-databases-in-a-plan-to-their-individual-subdirectories-in-the-default-xprogram-filesmicrosoft-sql-servermssql12mssqlservermssqlbackup-directory-also-delete-any-backups-older-than-2-weeks"></a><span data-ttu-id="5bf3d-266">В.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-266">C.</span></span> <span data-ttu-id="5bf3d-267">Создает резервные копии всех баз данных, содержащихся в плане, в отдельных каталогах, вложенных в каталог по умолчанию «x:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup».</span><span class="sxs-lookup"><span data-stu-id="5bf3d-267">Backing up all the databases in a plan to their individual subdirectories in the default x:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup directory.</span></span> <span data-ttu-id="5bf3d-268">Кроме того, удаляет резервные копии, созданные ранее чем две недели назад</span><span class="sxs-lookup"><span data-stu-id="5bf3d-268">Also, delete any backups older than 2 weeks</span></span>  
  
```  
sqlmaint -S MyServer -PlanName MyUserDBPlan -BkUpDB -BkUpMedia DISK -UseDefDir -CrBkSubDir -DelBkUps 2weeks  
```  
  
### <a name="d-backing-up-a-database-to-the-default-xprogram-filesmicrosoft-sql-servermssql12mssqlservermssqlbackup-directory"></a><span data-ttu-id="5bf3d-269">Г.</span><span class="sxs-lookup"><span data-stu-id="5bf3d-269">D.</span></span> <span data-ttu-id="5bf3d-270">Резервное копирование базы данных в x:\Program Files\Microsoft SQL Server\MSSQL12. по умолчанию Мссклсервер\мсскл\баккуп каталог. </span><span class="sxs-lookup"><span data-stu-id="5bf3d-270">Backing up a database to the default x:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup directory.</span></span>\  
  
```  
sqlmaint -S MyServer -BkUpDB -BkUpMedia DISK -UseDefDir  
```  
  
## <a name="see-also"></a><span data-ttu-id="5bf3d-271">См. также:</span><span class="sxs-lookup"><span data-stu-id="5bf3d-271">See Also</span></span>  
 <span data-ttu-id="5bf3d-272">[BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5bf3d-272">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 [<span data-ttu-id="5bf3d-273">UPDATE STATISTICS (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="5bf3d-273">UPDATE STATISTICS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/update-statistics-transact-sql)  
  
  
