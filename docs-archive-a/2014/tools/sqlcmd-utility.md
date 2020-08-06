---
title: Служебная программа sqlcmd | Документы Майкрософт
ms.custom: ''
ms.date: 11/29/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- statements [SQL Server], command prompt
- QUIT command
- Transact-SQL statements, command prompt
- EXIT command
- sqlcmd commands
- ED command
- sqlcmd utility
- command prompt utilities [SQL Server], sqlcmd
- '!! command'
- stored procedures [SQL Server], command prompt
- system stored procedures [SQL Server], command prompt
- sqlcmd utility, about sqlcmd utility
- scripts [SQL Server], command prompt
- RESET command
- GO command
ms.assetid: e1728707-5215-4c04-8320-e36f161b834a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9fbe5a3dcefb2218543e015dad71acfe79aea8e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739017"
---
# <a name="sqlcmd-utility"></a><span data-ttu-id="037a2-102">Служебная программа sqlcmd</span><span class="sxs-lookup"><span data-stu-id="037a2-102">sqlcmd Utility</span></span>
  <span data-ttu-id="037a2-103">`sqlcmd`Программа позволяет вводить [!INCLUDE[tsql](../includes/tsql-md.md)] инструкции, системные процедуры и файлы скриптов из командной строки, в **редакторе запросов** в режиме SQLCMD, в файле скрипта Windows или на шаге задания операционной системы (Cmd.exe) [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] задания агента.</span><span class="sxs-lookup"><span data-stu-id="037a2-103">The `sqlcmd` utility lets you enter [!INCLUDE[tsql](../includes/tsql-md.md)] statements, system procedures, and script files at the command prompt, in **Query Editor** in SQLCMD mode, in a Windows script file or in an operating system (Cmd.exe) job step of a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent job.</span></span> <span data-ttu-id="037a2-104">Эта программа использует технологию ODBC для выполнения пакетов [!INCLUDE[tsql](../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="037a2-104">This utility uses ODBC to execute [!INCLUDE[tsql](../includes/tsql-md.md)] batches.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]<span data-ttu-id="037a2-105">использует [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] SqlClient для выполнения в обычном и sqlcmd режиме в **редакторе запросов**.</span><span class="sxs-lookup"><span data-stu-id="037a2-105">uses the [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]SqlClient for execution in regular and SQLCMD mode in **Query Editor**.</span></span> <span data-ttu-id="037a2-106">При вызове программы `sqlcmd` из командной строки `sqlcmd` использует драйвер ODBC.</span><span class="sxs-lookup"><span data-stu-id="037a2-106">When `sqlcmd` is run from the command line, `sqlcmd` uses the ODBC driver.</span></span> <span data-ttu-id="037a2-107">Так как могут применяться различные параметры по умолчанию, выполнение одного и того же запроса в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] в режиме SQLCMD и в программе `sqlcmd` может проходить по-разному.</span><span class="sxs-lookup"><span data-stu-id="037a2-107">Because different default options may apply, you might see different behavior when you execute the same query in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] in SQLCMD Mode and in the `sqlcmd` utility.</span></span>  
  
 <span data-ttu-id="037a2-108">В настоящее время в программе `sqlcmd` не требуется указывать пробел между параметром командной строки и значением.</span><span class="sxs-lookup"><span data-stu-id="037a2-108">Currently, `sqlcmd` does not require a space between the command line option and the value.</span></span> <span data-ttu-id="037a2-109">Но в будущих выпусках пробел между параметром командной строки и значением может потребоваться.</span><span class="sxs-lookup"><span data-stu-id="037a2-109">However, in a future release, a space may be required between the command line option and the value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="037a2-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="037a2-110">Syntax</span></span>  
  
```  
  
   sqlcmd  
   -a  
   packet_size  
   -A (dedicated administrator connection)  
-b (terminate batch job if there is an error)  
-cbatch_terminator-C (trust the server certificate)  
-ddb_name-e (echo input)  
-E (use trusted connection)  
-fcodepage | i:codepage[,o:codepage] | o:codepage[,i:codepage]  
-hrows_per_header-Hworkstation_name-iinput_file-I (enable quoted identifiers)  
-k[1 | 2] (remove or replace control characters)  
-Kapplication_intent-llogin_timeout-L[c] (list servers, optional clean output)  
-merror_level-Mmultisubnet_failover-N (encrypt connection)  
-ooutput_file-p[1] (print statistics, optional colon format)  
-Ppassword-q "cmdline query"-Q "cmdline query" (and exit)  
-r[0 | 1] (msgs to stderr)  
-R (use client regional settings)  
-scol_separator-S [protocol:]server[\instance_name][,port]  
-tquery_timeout-u (unicode output file)  
-Ulogin_id-vvar = "value"-Verror_severity_level-wcolumn_width-W (remove trailing spaces)  
-x (disable variable substitution)  
-X[1] (disable commands, startup script, environment variables and optional exit)  
-yvariable_length_type_display_width-Yfixed_length_type_display_width-znew_password -Znew_password (and exit)  
  
-? (usage)  
```  
  
## <a name="command-line-options"></a><span data-ttu-id="037a2-111">Параметры командной строки</span><span class="sxs-lookup"><span data-stu-id="037a2-111">Command-line Options</span></span>  
 <span data-ttu-id="037a2-112">**Параметры, связанные с именем для входа**</span><span class="sxs-lookup"><span data-stu-id="037a2-112">**Login-Related Options**</span></span>  
  <span data-ttu-id="037a2-113">**-A**</span><span class="sxs-lookup"><span data-stu-id="037a2-113">**-A**</span></span>  
 <span data-ttu-id="037a2-114">Входит на [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] посредством выделенного административного соединения.</span><span class="sxs-lookup"><span data-stu-id="037a2-114">Logs in to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] with a Dedicated Administrator Connection (DAC).</span></span> <span data-ttu-id="037a2-115">Этот вид соединения предназначен для устранения неполадок на сервере.</span><span class="sxs-lookup"><span data-stu-id="037a2-115">This kind of connection is used to troubleshoot a server.</span></span> <span data-ttu-id="037a2-116">Параметр будет работать только с теми серверами, которые поддерживают выделенные административные соединения.</span><span class="sxs-lookup"><span data-stu-id="037a2-116">This will only work with server computers that support DAC.</span></span> <span data-ttu-id="037a2-117">Если соединение DAC недоступно, программа `sqlcmd` выдает сообщение об ошибке и завершает свою работу.</span><span class="sxs-lookup"><span data-stu-id="037a2-117">If DAC is not available, `sqlcmd` generates an error message and then exits.</span></span> <span data-ttu-id="037a2-118">Дополнительные сведения о DAC см. в статье [Диагностическое соединение для администраторов баз данных](../database-engine/configure-windows/diagnostic-connection-for-database-administrators.md).</span><span class="sxs-lookup"><span data-stu-id="037a2-118">For more information about DAC, see [Diagnostic Connection for Database Administrators](../database-engine/configure-windows/diagnostic-connection-for-database-administrators.md).</span></span>  
  
 <span data-ttu-id="037a2-119">**-C**</span><span class="sxs-lookup"><span data-stu-id="037a2-119">**-C**</span></span>  
 <span data-ttu-id="037a2-120">С помощью этого переключателя клиент настраивает неявное доверие к сертификату сервера без проверки.</span><span class="sxs-lookup"><span data-stu-id="037a2-120">This switch is used by the client to configure it to implicitly trust the server certificate without validation.</span></span> <span data-ttu-id="037a2-121">Этот параметр аналогичен параметру ADO.NET `TRUSTSERVERCERTIFICATE = true`.</span><span class="sxs-lookup"><span data-stu-id="037a2-121">This option is equivalent to the ADO.NET option `TRUSTSERVERCERTIFICATE = true`.</span></span>  
  
 <span data-ttu-id="037a2-122">**-d** _имя_базы данных_</span><span class="sxs-lookup"><span data-stu-id="037a2-122">**-d** _db_name_</span></span>  
 <span data-ttu-id="037a2-123">Выдает `USE` инструкцию *db_name* при запуске `sqlcmd` .</span><span class="sxs-lookup"><span data-stu-id="037a2-123">Issues a `USE` *db_name* statement when you start `sqlcmd`.</span></span> <span data-ttu-id="037a2-124">Этот параметр устанавливает переменную скрипта SQLCMDDBNAME программы `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="037a2-124">This option sets the `sqlcmd` scripting variable SQLCMDDBNAME.</span></span> <span data-ttu-id="037a2-125">Она задает начальную базу данных.</span><span class="sxs-lookup"><span data-stu-id="037a2-125">This specifies the initial database.</span></span> <span data-ttu-id="037a2-126">По умолчанию свойство default-database имени входа.</span><span class="sxs-lookup"><span data-stu-id="037a2-126">The default is your login's default-database property.</span></span> <span data-ttu-id="037a2-127">Если база данных не существует, выдается сообщение об ошибке и программа `sqlcmd` завершает свою работу.</span><span class="sxs-lookup"><span data-stu-id="037a2-127">If the database does not exist, an error message is generated and `sqlcmd` exits.</span></span>  
  
 <span data-ttu-id="037a2-128">**-l** _время_ожидания_входа_</span><span class="sxs-lookup"><span data-stu-id="037a2-128">**-l** _login_timeout_</span></span>  
 <span data-ttu-id="037a2-129">Задает время ожидания (в секундах) при подключении программы `sqlcmd` через драйвер ODBC при попытке соединения с сервером.</span><span class="sxs-lookup"><span data-stu-id="037a2-129">Specifies the number of seconds before a `sqlcmd` login to the ODBC driver times out when you try to connect to a server.</span></span> <span data-ttu-id="037a2-130">Этот параметр устанавливает переменную скрипта SQLCMDLOGINTIMEOUT программы `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="037a2-130">This option sets the `sqlcmd` scripting variable SQLCMDLOGINTIMEOUT.</span></span> <span data-ttu-id="037a2-131">По умолчанию время ожидания входа для программы `sqlcmd` составляет 8 секунд.</span><span class="sxs-lookup"><span data-stu-id="037a2-131">The default time-out for login to `sqlcmd` is eight seconds.</span></span> <span data-ttu-id="037a2-132">Время ожидания входа должно быть числом в диапазоне от 0 до 65 534.</span><span class="sxs-lookup"><span data-stu-id="037a2-132">The login time-out must be a number between 0 and 65534.</span></span> <span data-ttu-id="037a2-133">Если указанное значение не является числом или выходит за пределы указанного диапазона, программа `sqlcmd` выдает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="037a2-133">If the value supplied is not numeric or does not fall into that range, `sqlcmd` generates an error message.</span></span> <span data-ttu-id="037a2-134">Значение 0 задает неограниченное время ожидания.</span><span class="sxs-lookup"><span data-stu-id="037a2-134">A value of 0 specifies time-out to be infinite.</span></span>  
  
 <span data-ttu-id="037a2-135">**-E**</span><span class="sxs-lookup"><span data-stu-id="037a2-135">**-E**</span></span>  
 <span data-ttu-id="037a2-136">Использует для соединения с [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] вместо имени пользователя и пароля доверительное соединение.</span><span class="sxs-lookup"><span data-stu-id="037a2-136">Uses a trusted connection instead of using a user name and password to log on to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="037a2-137">По умолчанию, если параметр -E не указан, программа `sqlcmd` использует доверительное соединение.</span><span class="sxs-lookup"><span data-stu-id="037a2-137">By default, without -E specified, `sqlcmd` uses the trusted connection option.</span></span>  
  
 <span data-ttu-id="037a2-138">Параметр **-E** не использует имя пользователя и пароль, указанные в переменных среды, например SQLCMDPASSWORD.</span><span class="sxs-lookup"><span data-stu-id="037a2-138">The **-E** option ignores possible user name and password environment variable settings such as SQLCMDPASSWORD.</span></span> <span data-ttu-id="037a2-139">Если параметр **-E** используется в сочетании с параметром **-U** или **-P** , выдается сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="037a2-139">If the **-E** option is used together with the **-U** option or the **-P** option, an error message is generated.</span></span>  
  
 <span data-ttu-id="037a2-140">**-H** _имя_рабочей_станции_</span><span class="sxs-lookup"><span data-stu-id="037a2-140">**-H** _workstation_name_</span></span>  
 <span data-ttu-id="037a2-141">Имя рабочей станции.</span><span class="sxs-lookup"><span data-stu-id="037a2-141">A workstation name.</span></span> <span data-ttu-id="037a2-142">Этот параметр устанавливает переменную скрипта SQLCMDWORKSTATION программы `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="037a2-142">This option sets the `sqlcmd` scripting variable SQLCMDWORKSTATION.</span></span> <span data-ttu-id="037a2-143">Имя рабочей станции заносится в столбец **hostname** представления каталога **sys.processes** и может быть возвращено с помощью хранимой процедуры **sp_who**.</span><span class="sxs-lookup"><span data-stu-id="037a2-143">The workstation name is listed in the **hostname** column of the **sys.processes** catalog view and can be returned using the stored procedure **sp_who**.</span></span> <span data-ttu-id="037a2-144">Если этот параметр не указан, используется текущее имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="037a2-144">If this option is not specified, the default is the current computer name.</span></span> <span data-ttu-id="037a2-145">Это имя может использоваться для идентификации сеансов работы программы `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="037a2-145">This name can be used to identify different `sqlcmd` sessions.</span></span>  
  
 <span data-ttu-id="037a2-146">**-K** _намерение_приложения_</span><span class="sxs-lookup"><span data-stu-id="037a2-146">**-K** _application_intent_</span></span>  
 <span data-ttu-id="037a2-147">Объявляет тип рабочей нагрузки приложения при соединении с сервером.</span><span class="sxs-lookup"><span data-stu-id="037a2-147">Declares the application workload type when connecting to a server.</span></span> <span data-ttu-id="037a2-148">Единственным поддерживаемым в данное время значением является **ReadOnly**.</span><span class="sxs-lookup"><span data-stu-id="037a2-148">The only currently supported value is **ReadOnly**.</span></span> <span data-ttu-id="037a2-149">Если параметр **-K** не указан, то программа sqlcmd не будет поддерживать возможность подключения к вторичной реплике в группе доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="037a2-149">If **-K** is not specified, the sqlcmd utility will not support connectivity to a secondary replica in an AlwaysOn availability group.</span></span> <span data-ttu-id="037a2-150">Дополнительные сведения см. в разделе [Активные вторичные реплики, доступные для чтения](../database-engine/availability-groups/windows/active-secondaries-readable-secondary-replicas-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="037a2-150">For more information, see [Active Secondaries: Readable Secondary Replicas](../database-engine/availability-groups/windows/active-secondaries-readable-secondary-replicas-always-on-availability-groups.md).</span></span>  
  
 <span data-ttu-id="037a2-151">`-M`*multisubnet_failover*</span><span class="sxs-lookup"><span data-stu-id="037a2-151">`-M` *multisubnet_failover*</span></span>  
 <span data-ttu-id="037a2-152">Всегда указывайте параметр `-M` при соединении с прослушивателем группы доступности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] или экземпляром отказоустойчивого кластера [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="037a2-152">Always specify `-M` when connecting to the availability group listener of a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] availability group or a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Failover Cluster Instance.</span></span> <span data-ttu-id="037a2-153">`-M` обеспечивает более быстрое обнаружение активного (в данный момент) сервера и соединение с ним.</span><span class="sxs-lookup"><span data-stu-id="037a2-153">`-M` provides for faster detection of and connection to the (currently) active server.</span></span> <span data-ttu-id="037a2-154">Если параметр `-M` не указан, то режим `-M` отключен.</span><span class="sxs-lookup"><span data-stu-id="037a2-154">If `-M` is not specified, `-M` is off.</span></span> <span data-ttu-id="037a2-155">Дополнительные сведения о см. в статьях [!INCLUDE[ssHADR](../includes/sshadr-md.md)] [прослушиватели групп доступности, подключение клиентов и отработка отказа приложений &#40;SQL Server&#41;](../database-engine/listeners-client-connectivity-application-failover.md), [Создание и настройка групп доступности &#40;SQL Server&#41;](../database-engine/availability-groups/windows/creation-and-configuration-of-availability-groups-sql-server.md), [отказоустойчивая кластеризация и группы доступности AlwaysOn &#40;](../database-engine/availability-groups/windows/failover-clustering-and-always-on-availability-groups-sql-server.md)SQL Server&#41;и [Активные вторичные реплики](../database-engine/availability-groups/windows/active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) .</span><span class="sxs-lookup"><span data-stu-id="037a2-155">For more information about [!INCLUDE[ssHADR](../includes/sshadr-md.md)], see [Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../database-engine/listeners-client-connectivity-application-failover.md), [Creation and Configuration of Availability Groups &#40;SQL Server&#41;](../database-engine/availability-groups/windows/creation-and-configuration-of-availability-groups-sql-server.md), [Failover Clustering and AlwaysOn Availability Groups &#40;SQL Server&#41;](../database-engine/availability-groups/windows/failover-clustering-and-always-on-availability-groups-sql-server.md), and [Active Secondaries: Readable Secondary Replicas](../database-engine/availability-groups/windows/active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) .</span></span>  
  
 <span data-ttu-id="037a2-156">**-N**</span><span class="sxs-lookup"><span data-stu-id="037a2-156">**-N**</span></span>  
 <span data-ttu-id="037a2-157">С помощью этого переключателя клиент запрашивает шифрованное соединение.</span><span class="sxs-lookup"><span data-stu-id="037a2-157">This switch is used by the client to request an encrypted connection.</span></span>  
  
 <span data-ttu-id="037a2-158">**-P** _пароль_</span><span class="sxs-lookup"><span data-stu-id="037a2-158">**-P** _password_</span></span>  
 <span data-ttu-id="037a2-159">Пароль, задаваемый пользователем.</span><span class="sxs-lookup"><span data-stu-id="037a2-159">Is a user-specified password.</span></span> <span data-ttu-id="037a2-160">Пароли учитывают регистр.</span><span class="sxs-lookup"><span data-stu-id="037a2-160">Passwords are case sensitive.</span></span> <span data-ttu-id="037a2-161">Если используется параметр-U и параметр **-P** не используется и не задана ПЕРЕМЕННАЯ среды SQLCMDPASSWORD, `sqlcmd` запрашивает у пользователя пароль.</span><span class="sxs-lookup"><span data-stu-id="037a2-161">If the -U option is used and the **-P** option is not used, and the SQLCMDPASSWORD environment variable has not been set, `sqlcmd` prompts the user for a password.</span></span> <span data-ttu-id="037a2-162">Если параметр **-P** используется в конце командной строки без пароля `sqlcmd` , используется пароль по умолчанию (null).</span><span class="sxs-lookup"><span data-stu-id="037a2-162">If the **-P** option is used at the end of the command prompt without a password `sqlcmd` uses the default password (NULL).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="037a2-163">Не используйте пустые пароли.</span><span class="sxs-lookup"><span data-stu-id="037a2-163">Do not use a blank password.</span></span> <span data-ttu-id="037a2-164">Выбирайте надежные пароли.</span><span class="sxs-lookup"><span data-stu-id="037a2-164">Use a strong password.</span></span> <span data-ttu-id="037a2-165">Дополнительные сведения см. в разделе [Strong Passwords](../relational-databases/security/strong-passwords.md).</span><span class="sxs-lookup"><span data-stu-id="037a2-165">For more information, see [Strong Passwords](../relational-databases/security/strong-passwords.md).</span></span>  
  
 <span data-ttu-id="037a2-166">Запрос на ввод пароля выводится на консоль следующим образом: `Password:`.</span><span class="sxs-lookup"><span data-stu-id="037a2-166">The password prompt is displayed by printing the password prompt to the console, as follows: `Password:`</span></span>  
  
 <span data-ttu-id="037a2-167">Вводимые пользователем данные на экране не отображаются,</span><span class="sxs-lookup"><span data-stu-id="037a2-167">User input is hidden.</span></span> <span data-ttu-id="037a2-168">то есть символы не выводятся и курсор остается на месте.</span><span class="sxs-lookup"><span data-stu-id="037a2-168">This means that nothing is displayed and the cursor stays in position.</span></span>  
  
 <span data-ttu-id="037a2-169">Переменная среды SQLCMDPASSWORD позволяет задать значение пароля по умолчанию для текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="037a2-169">The SQLCMDPASSWORD environment variable lets you set a default password for the current session.</span></span> <span data-ttu-id="037a2-170">Таким образом, нет необходимости указывать пароль в пакетных файлах.</span><span class="sxs-lookup"><span data-stu-id="037a2-170">Therefore, passwords do not have to be hard-coded into batch files.</span></span>  
  
 <span data-ttu-id="037a2-171">В следующем примере сначала из командной строки устанавливается переменная SQLCMDPASSWORD, а затем производится вызов программы `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="037a2-171">The following example first sets the SQLCMDPASSWORD variable at the command prompt and then accesses the `sqlcmd` utility.</span></span> <span data-ttu-id="037a2-172">В командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="037a2-172">At the command prompt, type:</span></span>  
  
 `SET SQLCMDPASSWORD= p@a$$w0rd`  
  
> [!IMPORTANT]  
>  <span data-ttu-id="037a2-173">Пароль будет отображаться на мониторе компьютера.</span><span class="sxs-lookup"><span data-stu-id="037a2-173">The password will be visible to anyone who can see your computer monitor.</span></span>  
  
 <span data-ttu-id="037a2-174">В командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="037a2-174">At the following command prompt, type:</span></span>  
  
 `sqlcmd`  
  
 <span data-ttu-id="037a2-175">Если обнаружено неверное сочетание имени пользователя и пароля, выдается сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="037a2-175">If the user name and password combination is incorrect, an error message is generated.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="037a2-176">Переменная среды OSQLPASSWORD была сохранена в целях обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="037a2-176">The OSQLPASSWORD environment variable has been kept for backward compatibility.</span></span> <span data-ttu-id="037a2-177">Переменная среды SQLCMDPASSWORD имеет приоритет над переменной среды OSQLPASSWORD; Это означает, что `sqlcmd` и **osql** можно использовать рядом друг с другом без помех, и эти старые сценарии будут продолжать работать.</span><span class="sxs-lookup"><span data-stu-id="037a2-177">The SQLCMDPASSWORD environment variable takes precedence over the OSQLPASSWORD environment variable; this means that `sqlcmd` and **osql** can be used next to each other without interference and that old scripts will continue to work.</span></span>  
  
 <span data-ttu-id="037a2-178">Если параметр **-P** указан одновременно с параметром **-E** , выдается сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="037a2-178">If the **-P** option is used with the **-E** option, an error message is generated.</span></span>  
  
 <span data-ttu-id="037a2-179">Если после параметра **-P** указано более одного аргумента, выдается сообщение об ошибке, и программа завершает работу.</span><span class="sxs-lookup"><span data-stu-id="037a2-179">If the **-P** option is followed by more than one argument, an error message is generated and the program exits.</span></span>  
  
 <span data-ttu-id="037a2-180">**-S** [*протокол*:]*сервер*[ **\\** _instance_name_] [**,**_порт_]</span><span class="sxs-lookup"><span data-stu-id="037a2-180">**-S** [*protocol*:]*server*[**\\**_instance_name_][**,**_port_]</span></span>  
 <span data-ttu-id="037a2-181">Указывает экземпляр [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="037a2-181">Specifies the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to which to connect.</span></span> <span data-ttu-id="037a2-182">Устанавливает переменную скрипта SQLCMDSERVER программы `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="037a2-182">It sets the `sqlcmd` scripting variable SQLCMDSERVER.</span></span>  
  
 <span data-ttu-id="037a2-183">Укажите значение *имя_сервера*, чтобы подключиться к экземпляру компонента [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] по умолчанию на этом сервере.</span><span class="sxs-lookup"><span data-stu-id="037a2-183">Specify *server_name* to connect to the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on that server computer.</span></span> <span data-ttu-id="037a2-184">Укажите *server_name* [ **\\** _instance_name_ ], чтобы подключиться к именованному экземпляру [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] на этом компьютере сервера.</span><span class="sxs-lookup"><span data-stu-id="037a2-184">Specify *server_name* [ **\\**_instance_name_ ] to connect to a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on that server computer.</span></span> <span data-ttu-id="037a2-185">Если сервер не указан, программа `sqlcmd` выполняет подключение к экземпляру [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] по умолчанию на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="037a2-185">If no server computer is specified, `sqlcmd` connects to the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on the local computer.</span></span> <span data-ttu-id="037a2-186">Этот параметр обязателен при запуске программы `sqlcmd` с удаленного компьютера в сети.</span><span class="sxs-lookup"><span data-stu-id="037a2-186">This option is required when you execute `sqlcmd` from a remote computer on the network.</span></span>  
  
 <span data-ttu-id="037a2-187">*протокол* может быть `tcp` (TCP/IP), `lpc` (общая память) или `np` (именованные каналы).</span><span class="sxs-lookup"><span data-stu-id="037a2-187">*protocol* can be `tcp` (TCP/IP), `lpc` (shared memory), or `np` (named pipes).</span></span>  
  
 <span data-ttu-id="037a2-188">Если не указать *server_name* [ **\\** _instance_name_ ] при запуске `sqlcmd` , [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] проверяет и использует переменную среды SQLCMDSERVER.</span><span class="sxs-lookup"><span data-stu-id="037a2-188">If you do not specify a *server_name* [ **\\**_instance_name_ ] when you start `sqlcmd`, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] checks for and uses the SQLCMDSERVER environment variable.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="037a2-189">Переменная среды OSQLSERVER была сохранена в целях обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="037a2-189">The OSQLSERVER environment variable has been kept for backward compatibility.</span></span> <span data-ttu-id="037a2-190">Переменная среды SQLCMDSERVER имеет приоритет над переменной среды OSQLSERVER; Это означает, что `sqlcmd` и **osql** можно использовать рядом друг с другом без помех, и эти старые сценарии будут продолжать работать.</span><span class="sxs-lookup"><span data-stu-id="037a2-190">The SQLCMDSERVER environment variable takes precedence over the OSQLSERVER environment variable; this means that `sqlcmd` and **osql** can be used next to each other without interference and that old scripts will continue to work.</span></span>  
  
 <span data-ttu-id="037a2-191">**-U** _идентификатор_для_входа_</span><span class="sxs-lookup"><span data-stu-id="037a2-191">**-U** _login_id_</span></span>  
 <span data-ttu-id="037a2-192">Идентификатор входа пользователя.</span><span class="sxs-lookup"><span data-stu-id="037a2-192">Is the user login ID.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="037a2-193">В целях обратной совместимости доступна переменная среды OSQLUSER.</span><span class="sxs-lookup"><span data-stu-id="037a2-193">The OSQLUSER environment variable is available for backward compatibility.</span></span> <span data-ttu-id="037a2-194">Переменная среды SQLCMDUSER имеет больший приоритет, чем OSQLUSER.</span><span class="sxs-lookup"><span data-stu-id="037a2-194">The SQLCMDUSER environment variable takes precedence over the OSQLUSER environment variable.</span></span> <span data-ttu-id="037a2-195">Это означает, что `sqlcmd` и **osql** можно использовать рядом друг с другом без помех.</span><span class="sxs-lookup"><span data-stu-id="037a2-195">This means that `sqlcmd` and **osql** can be used next to each other without interference.</span></span> <span data-ttu-id="037a2-196">Кроме того, это означает, что существующие скрипты **osql** не перестанут работать.</span><span class="sxs-lookup"><span data-stu-id="037a2-196">It also means that existing **osql** scripts will continue to work.</span></span>  
  
 <span data-ttu-id="037a2-197">Если не указан ни параметр **-U** , ни параметр **-P** , `sqlcmd` пытается подключиться с использованием [!INCLUDE[msCoName](../includes/msconame-md.md)] режима проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="037a2-197">If neither the **-U** option nor the **-P** option is specified, `sqlcmd` tries to connect by using [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Authentication mode.</span></span> <span data-ttu-id="037a2-198">При этом используется учетная запись пользователя Windows, который запустил программу `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="037a2-198">Authentication is based on the Windows account of the user who is running `sqlcmd`.</span></span>  
  
 <span data-ttu-id="037a2-199">Если параметры **-U** и **-E** (описаны ниже в этом разделе) указаны одновременно, выдается сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="037a2-199">If the **-U** option is used with the **-E** option (described later in this topic), an error message is generated.</span></span> <span data-ttu-id="037a2-200">Если после параметра **-U** указано более одного аргумента, выдается сообщение об ошибке и программа завершает работу.</span><span class="sxs-lookup"><span data-stu-id="037a2-200">If the **-U** option is followed by more than one argument, an error message is generated and the program exits.</span></span>  
  
 <span data-ttu-id="037a2-201">**-z** _новый_пароль_</span><span class="sxs-lookup"><span data-stu-id="037a2-201">**-z** _new_password_</span></span>  
 <span data-ttu-id="037a2-202">Сменить пароль:</span><span class="sxs-lookup"><span data-stu-id="037a2-202">Change password:</span></span>  
  
 `sqlcmd -U someuser -P s0mep@ssword -z a_new_p@a$$w0rd`  
  
 <span data-ttu-id="037a2-203">**-z** _новый_пароль_</span><span class="sxs-lookup"><span data-stu-id="037a2-203">**-Z** _new_password_</span></span>  
 <span data-ttu-id="037a2-204">Измените пароль и выйти:</span><span class="sxs-lookup"><span data-stu-id="037a2-204">Change password and exit:</span></span>  
  
 `sqlcmd -U someuser -P s0mep@ssword -Z a_new_p@a$$w0rd`  
  
 <span data-ttu-id="037a2-205">**Параметры ввода-вывода**</span><span class="sxs-lookup"><span data-stu-id="037a2-205">**Input/Output Options**</span></span>  
  <span data-ttu-id="037a2-206">**-f**_кодовая_страница_ | **i:** _кодовая_страница_[ **,o:** _кодовая_страница_] | **o:** _кодовая_страница_[ **,i:** _кодовая_страница_]</span><span class="sxs-lookup"><span data-stu-id="037a2-206">**-f** _codepage_ | **i:**_codepage_[**,o:**_codepage_] | **o:**_codepage_[**,i:**_codepage_]</span></span>  
 <span data-ttu-id="037a2-207">Задает входные и выходные кодовые страницы.</span><span class="sxs-lookup"><span data-stu-id="037a2-207">Specifies the input and output code pages.</span></span> <span data-ttu-id="037a2-208">Номер кодовой страницы — это числовое значение, которое определяет установленную кодовую страницу Windows.</span><span class="sxs-lookup"><span data-stu-id="037a2-208">The codepage number is a numeric value that specifies an installed Windows code page.</span></span>  
  
 <span data-ttu-id="037a2-209">Правила преобразования кодовых страниц:</span><span class="sxs-lookup"><span data-stu-id="037a2-209">Code-page conversion rules:</span></span>  
  
-   <span data-ttu-id="037a2-210">Если кодовые страницы не заданы, программа `sqlcmd` использует текущую кодовую страницу как для входных, так и для выходных файлов. Для входного файла в Юникоде преобразование не требуется.</span><span class="sxs-lookup"><span data-stu-id="037a2-210">If no code pages are specified, `sqlcmd` will use the current code page for both input and output files, unless the input file is a Unicode file, in which case no conversion is required.</span></span>  
  
-   <span data-ttu-id="037a2-211">Программа `sqlcmd` автоматически распознает входные файлы в Юникоде как с прямым, так и с обратным порядком следования байтов.</span><span class="sxs-lookup"><span data-stu-id="037a2-211">`sqlcmd` automatically recognizes both big-endian and little-endian Unicode input files.</span></span> <span data-ttu-id="037a2-212">Если задан параметр **-u** , выходные данные всегда будут в Юникоде с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="037a2-212">If the **-u** option has been specified, the output will always be little-endian Unicode.</span></span>  
  
-   <span data-ttu-id="037a2-213">Если выходной файл не задан, то выходные данные будут иметь кодовую страницу консоли.</span><span class="sxs-lookup"><span data-stu-id="037a2-213">If no output file is specified, the output code page will be the console code page.</span></span> <span data-ttu-id="037a2-214">Это обеспечивает правильное отображение данных на консоли.</span><span class="sxs-lookup"><span data-stu-id="037a2-214">This enables the output to be displayed correctly on the console.</span></span>  
  
-   <span data-ttu-id="037a2-215">Предполагается, что все входные файлы имеют одинаковую кодовую страницу.</span><span class="sxs-lookup"><span data-stu-id="037a2-215">Multiple input files are assumed to be of the same code page.</span></span> <span data-ttu-id="037a2-216">Входные файлы в Юникоде и не в Юникоде можно обрабатывать вместе.</span><span class="sxs-lookup"><span data-stu-id="037a2-216">Unicode and non-Unicode input files can be mixed.</span></span>  
  
 <span data-ttu-id="037a2-217">Чтобы проверить кодовую страницу Cmd.exe, введите в командной строке команду `chcp`.</span><span class="sxs-lookup"><span data-stu-id="037a2-217">Enter `chcp` at the command prompt to verify the code page of Cmd.exe.</span></span>  
  
 <span data-ttu-id="037a2-218">**-i** _input_file_[**,**_input_file2_...]</span><span class="sxs-lookup"><span data-stu-id="037a2-218">**-i** _input_file_[**,**_input_file2_...]</span></span>  
 <span data-ttu-id="037a2-219">Указывает файл, содержащий пакет инструкций или хранимых процедур SQL.</span><span class="sxs-lookup"><span data-stu-id="037a2-219">Identifies the file that contains a batch of SQL statements or stored procedures.</span></span> <span data-ttu-id="037a2-220">Можно указать несколько файлов, которые будут считываться и обрабатываться в указанном порядке.</span><span class="sxs-lookup"><span data-stu-id="037a2-220">Multiple files may be specified that will be read and processed in order.</span></span> <span data-ttu-id="037a2-221">Не разделяйте имена файлов пробелами.</span><span class="sxs-lookup"><span data-stu-id="037a2-221">Do not use any spaces between file names.</span></span> <span data-ttu-id="037a2-222">Программа `sqlcmd` сначала производит проверку наличия всех указанных файлов.</span><span class="sxs-lookup"><span data-stu-id="037a2-222">`sqlcmd` will first check to see whether all the specified files exist.</span></span> <span data-ttu-id="037a2-223">Если хотя бы один из файлов не найден, программа `sqlcmd` завершит работу.</span><span class="sxs-lookup"><span data-stu-id="037a2-223">If one or more files do not exist, `sqlcmd` will exit.</span></span> <span data-ttu-id="037a2-224">Параметры -i и -Q/-q являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="037a2-224">The -i and the -Q/-q options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="037a2-225">Примеры пути:</span><span class="sxs-lookup"><span data-stu-id="037a2-225">Path examples:</span></span>  
  
 <span data-ttu-id="037a2-226">**-i** C: \\<имя файла\></span><span class="sxs-lookup"><span data-stu-id="037a2-226">**-i** C:\\<filename\></span></span>  
  
 <span data-ttu-id="037a2-227">**-i** \\ \\<Server \> \\<общий файл $>\\<имя файла\></span><span class="sxs-lookup"><span data-stu-id="037a2-227">**-i** \\\\<Server\>\\<Share$>\\<filename\></span></span>  
  
 <span data-ttu-id="037a2-228">**-i** "C: \ папка \\<имя файла \> "</span><span class="sxs-lookup"><span data-stu-id="037a2-228">**-i** "C:\Some Folder\\<file name\>"</span></span>  
  
 <span data-ttu-id="037a2-229">Пути к файлам, содержащие пробелы, необходимо заключать в кавычки.</span><span class="sxs-lookup"><span data-stu-id="037a2-229">File paths that contain spaces must be enclosed in quotation marks.</span></span>  
  
 <span data-ttu-id="037a2-230">Этот параметр можно использовать несколько раз: **-i**_input_file_ **-i**_input_file._</span><span class="sxs-lookup"><span data-stu-id="037a2-230">This option may be used more than once: **-i**_input_file_ **-I**_I input_file._</span></span>  
  
 <span data-ttu-id="037a2-231">**-o** _файл_ввода_</span><span class="sxs-lookup"><span data-stu-id="037a2-231">**-o** _output_file_</span></span>  
 <span data-ttu-id="037a2-232">Указывает файл, в который поступают выходные данные программы `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="037a2-232">Identifies the file that receives output from `sqlcmd`.</span></span>  
  
 <span data-ttu-id="037a2-233">Если указан параметр **-u** , *выходной_файл* сохраняется в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="037a2-233">If **-u** is specified, the *output_file* is stored in Unicode format.</span></span> <span data-ttu-id="037a2-234">Если указано недопустимое имя файла, программа `sqlcmd` выдает сообщение об ошибке и завершает работу.</span><span class="sxs-lookup"><span data-stu-id="037a2-234">If the file name is not valid, an error message is generated, and `sqlcmd` exits.</span></span> <span data-ttu-id="037a2-235">`sqlcmd`не поддерживает одновременную запись нескольких `sqlcmd` процессов в один и тот же файл.</span><span class="sxs-lookup"><span data-stu-id="037a2-235">`sqlcmd` does not support concurrent writing of multiple `sqlcmd` processes to the same file.</span></span> <span data-ttu-id="037a2-236">В этом случае выводимые в файл данные будут неверны или повреждены.</span><span class="sxs-lookup"><span data-stu-id="037a2-236">The file output will be corrupted or incorrect.</span></span> <span data-ttu-id="037a2-237">Дополнительные сведения о форматах файлов см. в описании параметра **-f** .</span><span class="sxs-lookup"><span data-stu-id="037a2-237">See the **-f** switch for more information about file formats.</span></span> <span data-ttu-id="037a2-238">Если этот файл не существует, он будет создан.</span><span class="sxs-lookup"><span data-stu-id="037a2-238">This file will be created if it does not exist.</span></span> <span data-ttu-id="037a2-239">Файл от предыдущего сеанса работы программы `sqlcmd` с тем же именем будет перезаписан.</span><span class="sxs-lookup"><span data-stu-id="037a2-239">A file of the same name from a prior `sqlcmd` session will be overwritten.</span></span> <span data-ttu-id="037a2-240">Указанный здесь файл не является файлом **stdout** .</span><span class="sxs-lookup"><span data-stu-id="037a2-240">The file specified here is not the **stdout** file.</span></span> <span data-ttu-id="037a2-241">Если указан файл **stdout** , этот файл не будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="037a2-241">If a **stdout** file is specified this file will not be used.</span></span>  
  
 <span data-ttu-id="037a2-242">Примеры пути:</span><span class="sxs-lookup"><span data-stu-id="037a2-242">Path examples:</span></span>  
  
 <span data-ttu-id="037a2-243">**-o** В. \\< имя файла></span><span class="sxs-lookup"><span data-stu-id="037a2-243">**-o** C:\\< filename></span></span>  
  
 <span data-ttu-id="037a2-244">**-o** \\ \\<Server \> \\<общий файл $>\\<имя файла\></span><span class="sxs-lookup"><span data-stu-id="037a2-244">**-o** \\\\<Server\>\\<Share$>\\<filename\></span></span>  
  
 <span data-ttu-id="037a2-245">**-o "** Папка C: \ \\<имя файла \> "</span><span class="sxs-lookup"><span data-stu-id="037a2-245">**-o "** C:\Some Folder\\<file name\>"</span></span>  
  
 <span data-ttu-id="037a2-246">Пути к файлам, содержащие пробелы, необходимо заключать в кавычки.</span><span class="sxs-lookup"><span data-stu-id="037a2-246">File paths that contain spaces must be enclosed in quotation marks.</span></span>  
  
 <span data-ttu-id="037a2-247">**-r**[**0** | **1**]</span><span class="sxs-lookup"><span data-stu-id="037a2-247">**-r**[**0** | **1**]</span></span>  
 <span data-ttu-id="037a2-248">Перенаправляет вывод сообщений об ошибке на экран (**stderr**).</span><span class="sxs-lookup"><span data-stu-id="037a2-248">Redirects the error message output to the screen (**stderr**).</span></span> <span data-ttu-id="037a2-249">Если параметр не указан или если указано значение **0**, происходит перенаправление только сообщений об ошибках с уровнем серьезности 11 и выше.</span><span class="sxs-lookup"><span data-stu-id="037a2-249">If you do not specify a parameter or if you specify **0**, only error messages that have a severity level of 11 or higher are redirected.</span></span> <span data-ttu-id="037a2-250">Если указать **1**, то происходит перенаправление всех сообщений об ошибках (включая команду PRINT).</span><span class="sxs-lookup"><span data-stu-id="037a2-250">If you specify **1**, all error message output including PRINT is redirected.</span></span> <span data-ttu-id="037a2-251">Не имеет эффекта, если указан параметр -o.</span><span class="sxs-lookup"><span data-stu-id="037a2-251">Has no effect if you use -o.</span></span> <span data-ttu-id="037a2-252">По умолчанию сообщения отправляются в **stdout**.</span><span class="sxs-lookup"><span data-stu-id="037a2-252">By default, messages are sent to **stdout**.</span></span>  
  
 <span data-ttu-id="037a2-253">**-R**</span><span class="sxs-lookup"><span data-stu-id="037a2-253">**-R**</span></span>  
 <span data-ttu-id="037a2-254">Вызывает `sqlcmd` локализацию числовых столбцов, валюты, даты и времени, получаемых на [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] основе языкового стандарта клиента.</span><span class="sxs-lookup"><span data-stu-id="037a2-254">Causes `sqlcmd` to localize numeric, currency, date, and time columns retrieved from [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] based on the client's locale.</span></span> <span data-ttu-id="037a2-255">По умолчанию эти столбцы отображаются с использованием региональных параметров сервера.</span><span class="sxs-lookup"><span data-stu-id="037a2-255">By default, these columns are displayed using the server's regional settings.</span></span>  
  
 <span data-ttu-id="037a2-256">**-u**</span><span class="sxs-lookup"><span data-stu-id="037a2-256">**-u**</span></span>  
 <span data-ttu-id="037a2-257">Указывает, что *выходной_файл* хранится в Юникоде независимо от формата файла *входной_файл*.</span><span class="sxs-lookup"><span data-stu-id="037a2-257">Specifies that *output_file* is stored in Unicode format, regardless of the format of *input_file*.</span></span>  
  
 <span data-ttu-id="037a2-258">**Параметры выполнения запросов**</span><span class="sxs-lookup"><span data-stu-id="037a2-258">**Query Execution Options**</span></span>  
  <span data-ttu-id="037a2-259">**-e**</span><span class="sxs-lookup"><span data-stu-id="037a2-259">**-e**</span></span>  
 <span data-ttu-id="037a2-260">Выдает входные скрипты на стандартное устройство вывода (**stdout**).</span><span class="sxs-lookup"><span data-stu-id="037a2-260">Writes input scripts to the standard output device (**stdout**).</span></span>  
  
 <span data-ttu-id="037a2-261">**-I**</span><span class="sxs-lookup"><span data-stu-id="037a2-261">**-I**</span></span>  
 <span data-ttu-id="037a2-262">Устанавливает значение ON для параметра соединения SET QUOTED_IDENTIFIER.</span><span class="sxs-lookup"><span data-stu-id="037a2-262">Sets the SET QUOTED_IDENTIFIER connection option to ON.</span></span> <span data-ttu-id="037a2-263">По умолчанию этот параметр имеет значение OFF.</span><span class="sxs-lookup"><span data-stu-id="037a2-263">By default, it is set to OFF.</span></span> <span data-ttu-id="037a2-264">Дополнительные сведения см. в статье [SET QUOTED_IDENTIFIER (Transact-SQL)](/sql/t-sql/statements/set-quoted-identifier-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="037a2-264">For more information, see [SET QUOTED_IDENTIFIER &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-quoted-identifier-transact-sql).</span></span>  
  
 <span data-ttu-id="037a2-265">**-q"** _запрос_командной_строки_ **"**</span><span class="sxs-lookup"><span data-stu-id="037a2-265">**-q"** _cmdline query_ **"**</span></span>  
 <span data-ttu-id="037a2-266">Выполняет запрос при `sqlcmd` запуске, но не завершает работу `sqlcmd` после завершения выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="037a2-266">Executes a query when `sqlcmd` starts, but does not exit `sqlcmd` when the query has finished running.</span></span> <span data-ttu-id="037a2-267">Может быть выполнено несколько запросов, разделенных точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="037a2-267">Multiple-semicolon-delimited queries can be executed.</span></span> <span data-ttu-id="037a2-268">Заключайте запрос в кавычки, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="037a2-268">Use quotation marks around the query, as shown in the following example.</span></span>  
  
 <span data-ttu-id="037a2-269">В командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="037a2-269">At the command prompt, type:</span></span>  
  
 `sqlcmd -d AdventureWorks2012 -q "SELECT FirstName, LastName FROM Person.Person WHERE LastName LIKE 'Whi%';"`  
  
 `sqlcmd -d AdventureWorks2012 -q "SELECT TOP 5 FirstName FROM Person.Person;SELECT TOP 5 LastName FROM Person.Person;"`  
  
> [!IMPORTANT]  
>  <span data-ttu-id="037a2-270">Не используйте в запросе признак конца GO.</span><span class="sxs-lookup"><span data-stu-id="037a2-270">Do not use the GO terminator in the query.</span></span>  
  
 <span data-ttu-id="037a2-271">Если вместе с этим параметром указан параметр `-b`, программа `sqlcmd` завершает работу при возникновении ошибки.</span><span class="sxs-lookup"><span data-stu-id="037a2-271">If `-b` is specified together with this option, `sqlcmd` exits on error.</span></span> <span data-ttu-id="037a2-272">Параметр `-b` описан ранее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="037a2-272">`-b` is described later in this topic.</span></span>  
  
 <span data-ttu-id="037a2-273">**-Q "** _cmdline Query_ **"**</span><span class="sxs-lookup"><span data-stu-id="037a2-273">**-Q"** _cmdline query_ **"**</span></span>  
 <span data-ttu-id="037a2-274">При запуске программы `sqlcmd` выполняет запрос и немедленно завершает работу `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="037a2-274">Executes a query when `sqlcmd` starts and then immediately exits `sqlcmd`.</span></span> <span data-ttu-id="037a2-275">Может быть выполнено несколько запросов, разделенных точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="037a2-275">Multiple-semicolon-delimited queries can be executed.</span></span>  
  
 <span data-ttu-id="037a2-276">Заключайте запрос в кавычки, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="037a2-276">Use quotation marks around the query, as shown in the following example.</span></span>  
  
 <span data-ttu-id="037a2-277">В командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="037a2-277">At the command prompt, type:</span></span>  
  
 `sqlcmd -d AdventureWorks2012 -Q "SELECT FirstName, LastName FROM Person.Person WHERE LastName LIKE 'Whi%';"`  
  
 `sqlcmd -d AdventureWorks2012 -Q "SELECT TOP 5 FirstName FROM Person.Person;SELECT TOP 5 LastName FROM Person.Person;"`  
  
> [!IMPORTANT]  
>  <span data-ttu-id="037a2-278">Не используйте в запросе признак конца GO.</span><span class="sxs-lookup"><span data-stu-id="037a2-278">Do not use the GO terminator in the query.</span></span>  
  
 <span data-ttu-id="037a2-279">Если вместе с этим параметром указан параметр `-b`, программа `sqlcmd` завершает работу при возникновении ошибки.</span><span class="sxs-lookup"><span data-stu-id="037a2-279">If `-b` is specified together with this option, `sqlcmd` exits on error.</span></span> <span data-ttu-id="037a2-280">Параметр `-b` описан ранее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="037a2-280">`-b` is described later in this topic.</span></span>  
  
 <span data-ttu-id="037a2-281">**-t** _время_ожижания_запроса_</span><span class="sxs-lookup"><span data-stu-id="037a2-281">**-t** _query_timeout_</span></span>  
 <span data-ttu-id="037a2-282">Указывает время ожидания (в секундах) перед выполнением команды (или инструкции SQL). Этот параметр задает `sqlcmd` переменную скрипта склкмдстаттимеаут.</span><span class="sxs-lookup"><span data-stu-id="037a2-282">Specifies the number of seconds before a command (or SQL statement) times out. This option sets the `sqlcmd` scripting variable SQLCMDSTATTIMEOUT.</span></span> <span data-ttu-id="037a2-283">Если значение *время_ожидания* не указывается, то команда имеет неограниченное время ожидания. Значение *время_ожидания\*\*запроса* должно быть числом в диапазоне от 1 до 65534.</span><span class="sxs-lookup"><span data-stu-id="037a2-283">If a *time_out* value is not specified, the command does not time out. The *query\*\*time_out* must be a number between 1 and 65534.</span></span> <span data-ttu-id="037a2-284">Если указанное значение не является числом или выходит за пределы указанного диапазона, программа `sqlcmd` выдает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="037a2-284">If the value supplied is not numeric or does not fall into that range, `sqlcmd` generates an error message.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="037a2-285">Фактическое время ожидания может отличаться от указанного значения *время_ожидания* на несколько секунд.</span><span class="sxs-lookup"><span data-stu-id="037a2-285">The actual time out value may vary from the specified *time_out* value by several seconds.</span></span>  
  
 <span data-ttu-id="037a2-286">**-ввар =** _значение_[ **var =** _value_...]</span><span class="sxs-lookup"><span data-stu-id="037a2-286">**-vvar =** _value_[ **var =** _value_...]</span></span>  
 <span data-ttu-id="037a2-287">Создает `sqlcmd` переменную скрипта, которую можно использовать в `sqlcmd` скрипте.</span><span class="sxs-lookup"><span data-stu-id="037a2-287">Creates a `sqlcmd`scripting variable that can be used in a `sqlcmd` script.</span></span> <span data-ttu-id="037a2-288">Если значение содержит пробелы, заключите его в кавычки.</span><span class="sxs-lookup"><span data-stu-id="037a2-288">Enclose the value in quotation marks if the value contains spaces.</span></span> <span data-ttu-id="037a2-289">Можно указать несколько значений **_var_** = **" *`values`* "** .</span><span class="sxs-lookup"><span data-stu-id="037a2-289">You can specify multiple **_var_**=**"*`values`*"** values.</span></span> <span data-ttu-id="037a2-290">Если в каком-либо из указанных значений обнаружена ошибка, программа `sqlcmd` выдает сообщение и завершает работу.</span><span class="sxs-lookup"><span data-stu-id="037a2-290">If there are errors in any of the values specified, `sqlcmd` generates an error message and then exits.</span></span>  
  
 `sqlcmd -v MyVar1=something MyVar2="some thing"`  
  
 `sqlcmd -v MyVar1=something -v MyVar2="some thing"`  
  
 <span data-ttu-id="037a2-291">**-x**</span><span class="sxs-lookup"><span data-stu-id="037a2-291">**-x**</span></span>  
 <span data-ttu-id="037a2-292">Указывает, что программа `sqlcmd` не должна обрабатывать переменные скрипта.</span><span class="sxs-lookup"><span data-stu-id="037a2-292">Causes `sqlcmd` to ignore scripting variables.</span></span> <span data-ttu-id="037a2-293">Это может отказаться полезным в случае, если в скрипте содержится много инструкций INSERT, которые могут содержать строки, имеющие тот же формат, что и обычные переменные, т. е. "$(*имя_переменной*)".</span><span class="sxs-lookup"><span data-stu-id="037a2-293">This is useful when a script contains many INSERT statements that may contain strings that have the same format as regular variables, such as $(*variable_name*).</span></span>  
  
 <span data-ttu-id="037a2-294">**Параметры форматирования**</span><span class="sxs-lookup"><span data-stu-id="037a2-294">**Formatting Options**</span></span>  
  <span data-ttu-id="037a2-295">**-h** _заголовки_</span><span class="sxs-lookup"><span data-stu-id="037a2-295">**-h** _headers_</span></span>  
 <span data-ttu-id="037a2-296">Указывает количество строк для печати между заголовками столбцов.</span><span class="sxs-lookup"><span data-stu-id="037a2-296">Specifies the number of rows to print between the column headings.</span></span> <span data-ttu-id="037a2-297">По умолчанию заголовки печатаются один раз для каждого набора результатов запроса.</span><span class="sxs-lookup"><span data-stu-id="037a2-297">The default is to print headings one time for each set of query results.</span></span> <span data-ttu-id="037a2-298">Этот параметр устанавливает переменную скрипта SQLCMDHEADERS программы `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="037a2-298">This option sets the `sqlcmd` scripting variable SQLCMDHEADERS.</span></span> <span data-ttu-id="037a2-299">Используйте значение **-1** для отмены печати заголовков.</span><span class="sxs-lookup"><span data-stu-id="037a2-299">Use **-1** to specify that headers must not be printed.</span></span> <span data-ttu-id="037a2-300">Любое недопустимое значение приводит к тому, что программа `sqlcmd` создает сообщение об ошибке и завершает свою работу.</span><span class="sxs-lookup"><span data-stu-id="037a2-300">Any value that is not valid causes `sqlcmd` to generate an error message and then exit.</span></span>  
  
 <span data-ttu-id="037a2-301">**-k** [**1** | **2**]</span><span class="sxs-lookup"><span data-stu-id="037a2-301">**-k** [**1** | **2**]</span></span>  
 <span data-ttu-id="037a2-302">Удаляет из выходных данных все управляющие символы, такие как символы табуляции и символы новой строки.</span><span class="sxs-lookup"><span data-stu-id="037a2-302">Removes all control characters, such as tabs and new line characters from the output.</span></span> <span data-ttu-id="037a2-303">Это сохраняет формат столбцов при возврате данных.</span><span class="sxs-lookup"><span data-stu-id="037a2-303">This preserves column formatting when data is returned.</span></span> <span data-ttu-id="037a2-304">При указании значения 1 управляющие символы заменяются одиночным пробелом.</span><span class="sxs-lookup"><span data-stu-id="037a2-304">If 1 is specified, the control characters are replaced by a single space.</span></span> <span data-ttu-id="037a2-305">Если указано значение 2, все последовательные управляющие символы заменяются одиночным пробелом.</span><span class="sxs-lookup"><span data-stu-id="037a2-305">If 2 is specified, consecutive control characters are replaced by a single space.</span></span> <span data-ttu-id="037a2-306">Параметр **-k** аналогичен параметру **-k1**.</span><span class="sxs-lookup"><span data-stu-id="037a2-306">**-k** is the same as **-k1**.</span></span>  
  
 <span data-ttu-id="037a2-307">**-s** _символ-разделитель_столбцов_</span><span class="sxs-lookup"><span data-stu-id="037a2-307">**-s** _col_separator_</span></span>  
 <span data-ttu-id="037a2-308">Задает символ-разделитель столбцов.</span><span class="sxs-lookup"><span data-stu-id="037a2-308">Specifies the column-separator character.</span></span> <span data-ttu-id="037a2-309">Значением по умолчанию является пробел.</span><span class="sxs-lookup"><span data-stu-id="037a2-309">The default is a blank space.</span></span> <span data-ttu-id="037a2-310">Этот параметр устанавливает переменную скрипта SQLCMDCOLSEP программы `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="037a2-310">This option sets the `sqlcmd` scripting variable SQLCMDCOLSEP.</span></span> <span data-ttu-id="037a2-311">Чтобы использовать символы, имеющие специальное значение для операционной системы, такие как амперсанд (&) или точка с запятой (;), заключайте этот символ в кавычки (").</span><span class="sxs-lookup"><span data-stu-id="037a2-311">To use characters that have special meaning to the operating system such as the ampersand (&), or semicolon (;), enclose the character in quotation marks (").</span></span> <span data-ttu-id="037a2-312">Разделитель столбцов может быть любым 8-разрядным символом.</span><span class="sxs-lookup"><span data-stu-id="037a2-312">The column separator can be any 8-bit character.</span></span>  
  
 <span data-ttu-id="037a2-313">**-w** _ширина_столбца_</span><span class="sxs-lookup"><span data-stu-id="037a2-313">**-w** _column_width_</span></span>  
 <span data-ttu-id="037a2-314">Задает ширину экрана для вывода.</span><span class="sxs-lookup"><span data-stu-id="037a2-314">Specifies the screen width for output.</span></span> <span data-ttu-id="037a2-315">Этот параметр устанавливает переменную скрипта SQLCMDCOLWIDTH программы `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="037a2-315">This option sets the `sqlcmd` scripting variable SQLCMDCOLWIDTH.</span></span> <span data-ttu-id="037a2-316">Ширина столбца должна находиться в диапазоне от 8 до 65 536.</span><span class="sxs-lookup"><span data-stu-id="037a2-316">The column width must be a number greater than 8 and less than 65536.</span></span> <span data-ttu-id="037a2-317">Если указанное значение ширины столбца выходит за пределы указанного диапазона, программа `sqlcmd` выдает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="037a2-317">If the specified column width does not fall into that range, `sqlcmd` generates and error message.</span></span> <span data-ttu-id="037a2-318">Ширина по умолчанию составляет 80 символов.</span><span class="sxs-lookup"><span data-stu-id="037a2-318">The default width is 80 characters.</span></span> <span data-ttu-id="037a2-319">Когда строка вывода превышает указанную ширину столбца, вывод переносится на следующую строку.</span><span class="sxs-lookup"><span data-stu-id="037a2-319">When an output line exceeds the specified column width, it wraps on to the next line.</span></span>  
  
 <span data-ttu-id="037a2-320">**-W**</span><span class="sxs-lookup"><span data-stu-id="037a2-320">**-W**</span></span>  
 <span data-ttu-id="037a2-321">Этот параметр удаляет конечные пробелы в столбце.</span><span class="sxs-lookup"><span data-stu-id="037a2-321">This option removes trailing spaces from a column.</span></span> <span data-ttu-id="037a2-322">При подготовке данных для экспорта в другое приложение указывайте этот параметр вместе с параметром **-s** .</span><span class="sxs-lookup"><span data-stu-id="037a2-322">Use this option together with the **-s** option when preparing data that is to be exported to another application.</span></span> <span data-ttu-id="037a2-323">Не может указываться одновременно с параметром **-y** или **-Y** .</span><span class="sxs-lookup"><span data-stu-id="037a2-323">Cannot be used with the **-y** or **-Y** options.</span></span>  
  
 <span data-ttu-id="037a2-324">**-y** _изменяемая_ширина_отображения_</span><span class="sxs-lookup"><span data-stu-id="037a2-324">**-y** _variable_length_type_display_width_</span></span>  
 <span data-ttu-id="037a2-325">Этот параметр устанавливает переменную скрипта SQLCMDMAXVARTYPEWIDTH программы `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="037a2-325">Sets the `sqlcmd` scripting variable SQLCMDMAXVARTYPEWIDTH.</span></span> <span data-ttu-id="037a2-326">Значение по умолчанию равно 256.</span><span class="sxs-lookup"><span data-stu-id="037a2-326">The default is 256.</span></span> <span data-ttu-id="037a2-327">Ограничивает число символов, возвращаемых для больших типов данных переменной длины:</span><span class="sxs-lookup"><span data-stu-id="037a2-327">It limits the number of characters that are returned for the large variable length data types:</span></span>  
  
-   `varchar(max)`  
  
-   `nvarchar(max)`  
  
-   `varbinary(max)`  
  
-   `xml`  
  
-   `UDT (user-defined data types)`  
  
-   `text`  
  
-   `ntext`  
  
-   `image`  
  
> [!NOTE]  
>  <span data-ttu-id="037a2-328">Определяемые пользователем типы могут иметь фиксированную длину в зависимости от реализации.</span><span class="sxs-lookup"><span data-stu-id="037a2-328">UDTs can be of fixed length depending on the implementation.</span></span> <span data-ttu-id="037a2-329">Если фиксированная длина определяемого пользователем типа короче, чем значение переменной *ширина_отображения*, то значение типа возвращается без изменений.</span><span class="sxs-lookup"><span data-stu-id="037a2-329">If this length of a fixed length UDT is shorter that *display_width*, the value of the UDT returned is not affected.</span></span> <span data-ttu-id="037a2-330">Однако если длина превышает значение *ширина_отображения*, то производится усечение выходных данных.</span><span class="sxs-lookup"><span data-stu-id="037a2-330">However, if the length is longer than *display_width*, the output is truncated.</span></span>  
  
 
> [!IMPORTANT]  
>  <span data-ttu-id="037a2-331">Используйте параметр **-y 0** с особой осторожностью, поскольку при большом объеме возвращаемых данных может значительно снизиться производительность сервера и сети.</span><span class="sxs-lookup"><span data-stu-id="037a2-331">Use the **-y 0** option with extreme caution because it may cause serious performance issues on both the server and the network, depending on the size of data returned.</span></span>  
  
 <span data-ttu-id="037a2-332">**-Y** _фиксированная_ширина_отображения_</span><span class="sxs-lookup"><span data-stu-id="037a2-332">**-Y** _fixed_length_type_display_width_</span></span>  
 <span data-ttu-id="037a2-333">Этот параметр устанавливает переменную скрипта SQLCMDMAXFIXEDTYPEWIDTH программы `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="037a2-333">Sets the `sqlcmd` scripting variable SQLCMDMAXFIXEDTYPEWIDTH.</span></span> <span data-ttu-id="037a2-334">Значение по умолчанию 0 (неограниченно).</span><span class="sxs-lookup"><span data-stu-id="037a2-334">The default is 0 (unlimited).</span></span> <span data-ttu-id="037a2-335">Ограничивает число символов, возвращаемых для следующих типов данных:</span><span class="sxs-lookup"><span data-stu-id="037a2-335">Limits the number of characters that are returned for the following data types:</span></span>  
  
-   <span data-ttu-id="037a2-336">`char(`*n* `)` , где 1<= n<= 8000</span><span class="sxs-lookup"><span data-stu-id="037a2-336">`char(` *n* `)`, where 1<=n<=8000</span></span>  
  
-   <span data-ttu-id="037a2-337">`nchar(n`*n* `)` , где 1<= n<= 4000</span><span class="sxs-lookup"><span data-stu-id="037a2-337">`nchar(n` *n* `)`, where 1<=n<=4000</span></span>  
  
-   <span data-ttu-id="037a2-338">`varchar(n`*n* `)` , где 1<= n<= 8000</span><span class="sxs-lookup"><span data-stu-id="037a2-338">`varchar(n` *n* `)`, where 1<=n<=8000</span></span>  
  
-   <span data-ttu-id="037a2-339">`nvarchar(n`*n* `)` , где 1<= n<= 4000</span><span class="sxs-lookup"><span data-stu-id="037a2-339">`nvarchar(n` *n* `)`, where 1<=n<=4000</span></span>  
  
-   <span data-ttu-id="037a2-340">`varbinary(n`*n* `)` , где 1<= n<= 4000</span><span class="sxs-lookup"><span data-stu-id="037a2-340">`varbinary(n` *n* `)`, where 1<=n<=4000</span></span>  
  
-   `variant`  
  
 <span data-ttu-id="037a2-341">**Параметры отчетов об ошибках**</span><span class="sxs-lookup"><span data-stu-id="037a2-341">**Error Reporting Options**</span></span>  
  `-b`  
 <span data-ttu-id="037a2-342">Указывает, что в случае ошибки программа `sqlcmd` завершает работу и возвращает значение DOS ERRORLEVEL.</span><span class="sxs-lookup"><span data-stu-id="037a2-342">Specifies that `sqlcmd` exits and returns a DOS ERRORLEVEL value when an error occurs.</span></span> <span data-ttu-id="037a2-343">Значение, возвращаемое в переменную DOS ERRORLEVEL, равно **1** , если сообщение об ошибке [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] имеет степень серьезности выше 10. В противном случае возвращаемое значение равно **0**.</span><span class="sxs-lookup"><span data-stu-id="037a2-343">The value that is returned to the DOS ERRORLEVEL variable is **1** when the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] error message has a severity level greater than 10; otherwise, the value returned is **0**.</span></span> <span data-ttu-id="037a2-344">Если параметр `-V` был указан вместе с параметром `-b`, программа `sqlcmd` не будет выдавать сообщение об ошибках, степень серьезности которых ниже значения, заданного параметром `-V`.</span><span class="sxs-lookup"><span data-stu-id="037a2-344">If the `-V` option has been set in addition to `-b`, `sqlcmd` will not report an error if the severity level is lower than the values set using `-V`.</span></span> <span data-ttu-id="037a2-345">Пакетные файлы командной строки могут быть использованы для проверки значения ERRORLEVEL и для обработки ошибки соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="037a2-345">Command prompt batch files can test the value of ERRORLEVEL and handle the error appropriately.</span></span> <span data-ttu-id="037a2-346">Программа `sqlcmd` не выдает сообщений об ошибках со степенью серьезности 10 (информационные сообщения).</span><span class="sxs-lookup"><span data-stu-id="037a2-346">`sqlcmd` does not report errors for severity level 10 (informational messages).</span></span>  
  
 <span data-ttu-id="037a2-347">Если скрипт программы `sqlcmd` содержит неверный комментарий, синтаксическую ошибку или обнаружено отсутствие переменной скрипта, то возвращается значение ERRORLEVEL, равное 1.</span><span class="sxs-lookup"><span data-stu-id="037a2-347">If the `sqlcmd` script contains an incorrect comment, syntax error, or is missing a scripting variable, ERRORLEVEL returned is 1.</span></span>  
  
 <span data-ttu-id="037a2-348">**-m** _уровень_ошибки_</span><span class="sxs-lookup"><span data-stu-id="037a2-348">**-m** _error_level_</span></span>  
 <span data-ttu-id="037a2-349">Управляет сообщениями об ошибках, отправляемыми в **stdout**.</span><span class="sxs-lookup"><span data-stu-id="037a2-349">Controls which error messages are sent to **stdout**.</span></span> <span data-ttu-id="037a2-350">Передаются сообщения со степенью серьезности, которая больше заданной или равна ей.</span><span class="sxs-lookup"><span data-stu-id="037a2-350">Messages that have a severity level greater than or equal to this level are sent.</span></span> <span data-ttu-id="037a2-351">Если это значение равно **-1**, передаются все сообщения, в том числе информационные.</span><span class="sxs-lookup"><span data-stu-id="037a2-351">When this value is set to **-1**, all messages including informational messages, are sent.</span></span> <span data-ttu-id="037a2-352">Пробелы между параметрами **-m** и **-1**не допускаются.</span><span class="sxs-lookup"><span data-stu-id="037a2-352">Spaces are not allowed between the **-m** and **-1**.</span></span> <span data-ttu-id="037a2-353">Например, **-m-1** является допустимым, а **-m-1** — нет.</span><span class="sxs-lookup"><span data-stu-id="037a2-353">For example, **-m-1** is valid, and **-m-1** is not.</span></span>  
  
 <span data-ttu-id="037a2-354">Этот параметр также задает переменную скрипта `sqlcmd` SQLCMDERRORLEVEL.</span><span class="sxs-lookup"><span data-stu-id="037a2-354">This option also sets the `sqlcmd` scripting variable SQLCMDERRORLEVEL.</span></span> <span data-ttu-id="037a2-355">По умолчанию ее значение равно 0.</span><span class="sxs-lookup"><span data-stu-id="037a2-355">This variable has a default of 0.</span></span>  
  
 <span data-ttu-id="037a2-356">`-V`*error_severity_level*</span><span class="sxs-lookup"><span data-stu-id="037a2-356">`-V` *error_severity_level*</span></span>  
 <span data-ttu-id="037a2-357">Управляет степенью серьезности, используемой для задания переменной ERRORLEVEL.</span><span class="sxs-lookup"><span data-stu-id="037a2-357">Controls the severity level that is used to set the ERRORLEVEL variable.</span></span> <span data-ttu-id="037a2-358">Сообщения об ошибках со степенями серьезности, большими этого значения или равными ему, устанавливают переменную ERRORLEVEL.</span><span class="sxs-lookup"><span data-stu-id="037a2-358">Error messages that have severity levels greater than or equal to this value set ERRORLEVEL.</span></span> <span data-ttu-id="037a2-359">Значения меньше 0 сообщаются как 0.</span><span class="sxs-lookup"><span data-stu-id="037a2-359">Values that are less than 0 are reported as 0.</span></span> <span data-ttu-id="037a2-360">Пакетные файлы и CMD-файлы могут быть использованы для проверки значения переменной ERRORLEVEL.</span><span class="sxs-lookup"><span data-stu-id="037a2-360">Batch and CMD files can be used to test the value of the ERRORLEVEL variable.</span></span>  
  
 <span data-ttu-id="037a2-361">**Прочие параметры**</span><span class="sxs-lookup"><span data-stu-id="037a2-361">**Miscellaneous Options**</span></span>  
  <span data-ttu-id="037a2-362">**-a** _размер_пакета_</span><span class="sxs-lookup"><span data-stu-id="037a2-362">**-a** _packet_size_</span></span>  
 <span data-ttu-id="037a2-363">Запрашивает пакет другого размера.</span><span class="sxs-lookup"><span data-stu-id="037a2-363">Requests a packet of a different size.</span></span> <span data-ttu-id="037a2-364">Этот параметр устанавливает переменную скрипта SQLCMDPACKETSIZE программы `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="037a2-364">This option sets the `sqlcmd` scripting variable SQLCMDPACKETSIZE.</span></span> <span data-ttu-id="037a2-365">Значение*размер_пакета* должно находиться в диапазоне от 512 до 32767.</span><span class="sxs-lookup"><span data-stu-id="037a2-365">*packet_size* must be a value between 512 and 32767.</span></span> <span data-ttu-id="037a2-366">Значение по умолчанию = 4096.</span><span class="sxs-lookup"><span data-stu-id="037a2-366">The default = 4096.</span></span> <span data-ttu-id="037a2-367">Увеличение размера пакета повышает производительность выполнения скриптов, содержащих большое количество инструкций SQL между командами GO.</span><span class="sxs-lookup"><span data-stu-id="037a2-367">A larger packet size can enhance performance for execution of scripts that have lots of SQL statements between GO commands.</span></span> <span data-ttu-id="037a2-368">Можно запросить больший размер пакета.</span><span class="sxs-lookup"><span data-stu-id="037a2-368">You can request a larger packet size.</span></span> <span data-ttu-id="037a2-369">Однако в случае, если запрос будет запрещен, программа `sqlcmd` использует размер пакета по умолчанию для сервера.</span><span class="sxs-lookup"><span data-stu-id="037a2-369">However, if the request is denied, `sqlcmd` uses the server default for packet size.</span></span>  
  
 <span data-ttu-id="037a2-370">**-c** _конец_пакета_</span><span class="sxs-lookup"><span data-stu-id="037a2-370">**-c** _batch_terminator_</span></span>  
 <span data-ttu-id="037a2-371">Задает признак конца пакета.</span><span class="sxs-lookup"><span data-stu-id="037a2-371">Specifies the batch terminator.</span></span> <span data-ttu-id="037a2-372">По умолчанию команды завершаются и отправляются на [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] при вводе слова «GO» в отдельной строке.</span><span class="sxs-lookup"><span data-stu-id="037a2-372">By default, commands are terminated and sent to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] by typing the word "GO" on a line by itself.</span></span> <span data-ttu-id="037a2-373">При сбросе признака конца пакета не используйте зарезервированные ключевые слова или символы [!INCLUDE[tsql](../includes/tsql-md.md)] , которые имеют специальное значение для операционной системы, даже если перед ними присутствует символ обратной косой черты.</span><span class="sxs-lookup"><span data-stu-id="037a2-373">When you reset the batch terminator, do not use [!INCLUDE[tsql](../includes/tsql-md.md)] reserved keywords or characters that have special meaning to the operating system, even if they are preceded by a backslash.</span></span>  
  
 <span data-ttu-id="037a2-374">**-L**[**c**]</span><span class="sxs-lookup"><span data-stu-id="037a2-374">**-L**[**c**]</span></span>  
 <span data-ttu-id="037a2-375">Выводит список локально настроенных серверов и имена серверов, осуществляющих передачу данных в сети.</span><span class="sxs-lookup"><span data-stu-id="037a2-375">Lists the locally configured server computers, and the names of the server computers that are broadcasting on the network.</span></span> <span data-ttu-id="037a2-376">Этот параметр не может использоваться в сочетании с другими параметрами.</span><span class="sxs-lookup"><span data-stu-id="037a2-376">This parameter cannot be used in combination with other parameters.</span></span> <span data-ttu-id="037a2-377">Максимальное число компьютеров серверов, которое можно указать, составляет 3 000.</span><span class="sxs-lookup"><span data-stu-id="037a2-377">The maximum number of server computers that can be listed is 3000.</span></span> <span data-ttu-id="037a2-378">При усечении списка серверов в связи с нехваткой размера буфера выдается предупреждающее сообщение.</span><span class="sxs-lookup"><span data-stu-id="037a2-378">If the server list is truncated because of the size of the buffer a warning message is displayed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="037a2-379">Из-за особенностей передачи широковещательных сообщений по сети, программа `sqlcmd` не всегда своевременно получает ответ от всех серверов.</span><span class="sxs-lookup"><span data-stu-id="037a2-379">Because of the nature of broadcasting on networks, `sqlcmd` may not receive a timely response from all servers.</span></span> <span data-ttu-id="037a2-380">Поэтому возвращаемый список серверов от вызова к вызову может различаться.</span><span class="sxs-lookup"><span data-stu-id="037a2-380">Therefore, the list of servers returned may vary for each invocation of this option.</span></span>  
  
 <span data-ttu-id="037a2-381">Если указан необязательный параметр **c** , выходные данные отображаются без заголовка Servers: Line, а каждая строка сервера отображается без начальных пробелов.</span><span class="sxs-lookup"><span data-stu-id="037a2-381">If the optional parameter **c** is specified, the output appears without the Servers: header line and each server line is listed without leading spaces.</span></span> <span data-ttu-id="037a2-382">Это называется «чистым выводом».</span><span class="sxs-lookup"><span data-stu-id="037a2-382">This is referred to as clean output.</span></span> <span data-ttu-id="037a2-383">Чистый выход улучшает производительность обработки языков скриптов.</span><span class="sxs-lookup"><span data-stu-id="037a2-383">Clean output improves the processing performance of scripting languages.</span></span>  
  
 <span data-ttu-id="037a2-384">**-p**[**1**]</span><span class="sxs-lookup"><span data-stu-id="037a2-384">**-p**[**1**]</span></span>  
 <span data-ttu-id="037a2-385">Выводит на печать статистику производительности для каждого результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="037a2-385">Prints performance statistics for every result set.</span></span> <span data-ttu-id="037a2-386">Далее представлен пример формата для статистики производительности:</span><span class="sxs-lookup"><span data-stu-id="037a2-386">The following is an example of the format for performance statistics:</span></span>  
  
 `Network packet size (bytes): n`  
  
 `x xact[s]:`  
  
 `Clock Time (ms.): total       t1  avg       t2 (t3 xacts per sec.)`  
  
 <span data-ttu-id="037a2-387">Где:</span><span class="sxs-lookup"><span data-stu-id="037a2-387">Where:</span></span>  
  
 <span data-ttu-id="037a2-388">`x` = количество транзакций, обработанных [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="037a2-388">`x` = Number of transactions that are processed by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="037a2-389">`t1` = Общее время обработки всех транзакций.</span><span class="sxs-lookup"><span data-stu-id="037a2-389">`t1` = Total time for all transactions.</span></span>  
  
 <span data-ttu-id="037a2-390">`t2` = среднее время обработки одной транзакции.</span><span class="sxs-lookup"><span data-stu-id="037a2-390">`t2` = Average time for a single transaction.</span></span>  
  
 <span data-ttu-id="037a2-391">`t3` = среднее количество транзакций, обрабатываемых в секунду.</span><span class="sxs-lookup"><span data-stu-id="037a2-391">`t3` = Average number of transactions per second.</span></span>  
  
 <span data-ttu-id="037a2-392">Все значения времени приведены в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="037a2-392">All times are in milliseconds.</span></span>  
  
 <span data-ttu-id="037a2-393">Если указывается необязательный параметр **1** , статистика выводится в формате со столбцами, разделенными двоеточиями, и может быть легко импортирована в электронную таблицу или обработана скриптом.</span><span class="sxs-lookup"><span data-stu-id="037a2-393">If the optional parameter **1** is specified, the output format of the statistics is in colon-separated format that can be imported easily into a spreadsheet or processed by a script.</span></span>  
  
 <span data-ttu-id="037a2-394">Если необязательный параметр имеет любое значение, отличное от **1**, возникает ошибка и `sqlcmd` завершается.</span><span class="sxs-lookup"><span data-stu-id="037a2-394">If the optional parameter is any value other than **1**, an error is generated and `sqlcmd` exits.</span></span>  
  
 <span data-ttu-id="037a2-395">`-X`[**1**]</span><span class="sxs-lookup"><span data-stu-id="037a2-395">`-X`[**1**]</span></span>  
 <span data-ttu-id="037a2-396">Отключает команды, которые могут поставить под угрозу безопасность системы при выполнении программы `sqlcmd` из пакетного файла.</span><span class="sxs-lookup"><span data-stu-id="037a2-396">Disables commands that might compromise system security when `sqlcmd` is executed from a batch file.</span></span> <span data-ttu-id="037a2-397">Отключенные команды по-прежнему распознаются. Программа `sqlcmd` выдает предупреждающее сообщение и продолжает работу.</span><span class="sxs-lookup"><span data-stu-id="037a2-397">The disabled commands are still recognized; `sqlcmd` issues a warning message and continues.</span></span> <span data-ttu-id="037a2-398">Если указан необязательный параметр **1** , `sqlcmd` выдает сообщение об ошибке, а затем завершает работу.</span><span class="sxs-lookup"><span data-stu-id="037a2-398">If the optional parameter **1** is specified, `sqlcmd` generates an error message and then exits.</span></span> <span data-ttu-id="037a2-399">При использовании параметра `-X` происходит отключение следующих команд:</span><span class="sxs-lookup"><span data-stu-id="037a2-399">The following commands are disabled when the `-X` option is used:</span></span>  
  
-   <span data-ttu-id="037a2-400">**ED**</span><span class="sxs-lookup"><span data-stu-id="037a2-400">**ED**</span></span>  
  
-   <span data-ttu-id="037a2-401">**!!**</span><span class="sxs-lookup"><span data-stu-id="037a2-401">**!!**</span></span> <span data-ttu-id="037a2-402">_command_</span><span class="sxs-lookup"><span data-stu-id="037a2-402">_command_</span></span>  
  
 <span data-ttu-id="037a2-403">Указание параметра `-X` блокирует передачу переменных среды программе `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="037a2-403">If the `-X` option is specified, it prevents environment variables from being passed on to `sqlcmd`.</span></span> <span data-ttu-id="037a2-404">Он также препятствует выполнению скрипта запуска, указанного с помощью переменной скрипта SQLCMDINI.</span><span class="sxs-lookup"><span data-stu-id="037a2-404">It also prevents the startup script specified by using the SQLCMDINI scripting variable from being executed.</span></span> <span data-ttu-id="037a2-405">Дополнительные сведения о `sqlcmd` переменных скрипта см. [в разделе Использование sqlcmd с переменными скрипта](../relational-databases/scripting/sqlcmd-use-with-scripting-variables.md).</span><span class="sxs-lookup"><span data-stu-id="037a2-405">For more information about `sqlcmd` scripting variables, see [Use sqlcmd with Scripting Variables](../relational-databases/scripting/sqlcmd-use-with-scripting-variables.md).</span></span>  
  
 <span data-ttu-id="037a2-406">**-?**</span><span class="sxs-lookup"><span data-stu-id="037a2-406">**-?**</span></span>  
 <span data-ttu-id="037a2-407">Отображает сводку по синтаксису параметров программы `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="037a2-407">Displays the syntax summary of `sqlcmd` options.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="037a2-408">Remarks</span><span class="sxs-lookup"><span data-stu-id="037a2-408">Remarks</span></span>  
 <span data-ttu-id="037a2-409">Параметры не обязательно должны указываться в том порядке, в котором они приведены в разделе описания синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="037a2-409">Options do not have to be used in the order shown in the syntax section.</span></span>  
  
 <span data-ttu-id="037a2-410">Если возвращается несколько результатов, программа `sqlcmd` выводит между результирующими наборами в пакете пустую строку.</span><span class="sxs-lookup"><span data-stu-id="037a2-410">When multiple results are returned, `sqlcmd` prints a blank line between each result set in a batch.</span></span> <span data-ttu-id="037a2-411">Кроме того, сообщение " \<x> затронутые строки" не отображается, если оно не применяется к выполненной инструкции.</span><span class="sxs-lookup"><span data-stu-id="037a2-411">In addition, the "\<x> rows affected" message does not appear when it does not apply to the statement executed.</span></span>  
  
 <span data-ttu-id="037a2-412">Для `sqlcmd` интерактивного использования введите `sqlcmd` в командной строке один или несколько параметров, описанных выше в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="037a2-412">To use `sqlcmd` interactively, type `sqlcmd` at the command prompt with any one or more of the options described earlier in this topic.</span></span> <span data-ttu-id="037a2-413">Дополнительные сведения см. в статье [Использование программы sqlcmd](../relational-databases/scripting/sqlcmd-use-the-utility.md)</span><span class="sxs-lookup"><span data-stu-id="037a2-413">For more information, see [Use the sqlcmd Utility](../relational-databases/scripting/sqlcmd-use-the-utility.md)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="037a2-414">Параметры **-L**, **-Q**, **-Z** или **-i** приводят `sqlcmd` к выходу после выполнения.</span><span class="sxs-lookup"><span data-stu-id="037a2-414">The options **-L**, **-Q**, **-Z** or **-i** cause `sqlcmd` to exit after execution.</span></span>  
  
 <span data-ttu-id="037a2-415">Суммарная длина командной строки программы `sqlcmd` в командной среде (Cmd.exe), включая все аргументы и расширение переменных, соответствует длине для программы Cmd.exe и определяется операционной системой.</span><span class="sxs-lookup"><span data-stu-id="037a2-415">The total length of the `sqlcmd` command line in the command environment (Cmd.exe), including all arguments and expanded variables, is that which is determined by the operating system for Cmd.exe.</span></span>  
  
## <a name="variable-precedence-low-to-high"></a><span data-ttu-id="037a2-416">Приоритет переменных (от низкого к высокому)</span><span class="sxs-lookup"><span data-stu-id="037a2-416">Variable Precedence (Low to High)</span></span>  
  
1.  <span data-ttu-id="037a2-417">Переменные среды системного уровня.</span><span class="sxs-lookup"><span data-stu-id="037a2-417">System-level environmental variables.</span></span>  
  
2.  <span data-ttu-id="037a2-418">Переменные среды пользовательского уровня.</span><span class="sxs-lookup"><span data-stu-id="037a2-418">User-level environmental variables</span></span>  
  
3.  <span data-ttu-id="037a2-419">Командная оболочка (**Set** X = Y), заданная в командной строке перед выполнением `sqlcmd` .</span><span class="sxs-lookup"><span data-stu-id="037a2-419">Command shell (**SET** X=Y) set at command prompt before running `sqlcmd`.</span></span>  
  
4.  <span data-ttu-id="037a2-420">**sqlcmd-v** X=Y</span><span class="sxs-lookup"><span data-stu-id="037a2-420">**sqlcmd-v** X=Y</span></span>  
  
5.  <span data-ttu-id="037a2-421">**:Setvar** X Y</span><span class="sxs-lookup"><span data-stu-id="037a2-421">**:Setvar** X Y</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="037a2-422">Чтобы просмотреть переменные среды, на **панели управления**откройте компонент **Система**и перейдите на вкладку **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="037a2-422">To view the environmental variables, in **Control Panel**, open **System**, and then click the **Advanced** tab.</span></span>  
  
## <a name="sqlcmd-scripting-variables"></a><span data-ttu-id="037a2-423">Переменные скрипта sqlcmd</span><span class="sxs-lookup"><span data-stu-id="037a2-423">sqlcmd Scripting Variables</span></span>  
  
|<span data-ttu-id="037a2-424">Переменная</span><span class="sxs-lookup"><span data-stu-id="037a2-424">Variable</span></span>|<span data-ttu-id="037a2-425">Связанный параметр</span><span class="sxs-lookup"><span data-stu-id="037a2-425">Related switch</span></span>|<span data-ttu-id="037a2-426">Чтение-запись</span><span class="sxs-lookup"><span data-stu-id="037a2-426">R/W</span></span>|<span data-ttu-id="037a2-427">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="037a2-427">Default</span></span>|  
|--------------|--------------------|----------|-------------|  
|<span data-ttu-id="037a2-428">SQLCMDUSER</span><span class="sxs-lookup"><span data-stu-id="037a2-428">SQLCMDUSER</span></span>|<span data-ttu-id="037a2-429">-U</span><span class="sxs-lookup"><span data-stu-id="037a2-429">-U</span></span>|<span data-ttu-id="037a2-430">R</span><span class="sxs-lookup"><span data-stu-id="037a2-430">R</span></span>|<span data-ttu-id="037a2-431">""</span><span class="sxs-lookup"><span data-stu-id="037a2-431">""</span></span>|  
|<span data-ttu-id="037a2-432">SQLCMDPASSWORD</span><span class="sxs-lookup"><span data-stu-id="037a2-432">SQLCMDPASSWORD</span></span>|<span data-ttu-id="037a2-433">-P</span><span class="sxs-lookup"><span data-stu-id="037a2-433">-P</span></span>|--|<span data-ttu-id="037a2-434">""</span><span class="sxs-lookup"><span data-stu-id="037a2-434">""</span></span>|  
|<span data-ttu-id="037a2-435">SQLCMDSERVER</span><span class="sxs-lookup"><span data-stu-id="037a2-435">SQLCMDSERVER</span></span>|<span data-ttu-id="037a2-436">-S</span><span class="sxs-lookup"><span data-stu-id="037a2-436">-S</span></span>|<span data-ttu-id="037a2-437">R</span><span class="sxs-lookup"><span data-stu-id="037a2-437">R</span></span>|<span data-ttu-id="037a2-438">"DefaultLocalInstance"</span><span class="sxs-lookup"><span data-stu-id="037a2-438">"DefaultLocalInstance"</span></span>|  
|<span data-ttu-id="037a2-439">SQLCMDWORKSTATION</span><span class="sxs-lookup"><span data-stu-id="037a2-439">SQLCMDWORKSTATION</span></span>|<span data-ttu-id="037a2-440">-H</span><span class="sxs-lookup"><span data-stu-id="037a2-440">-H</span></span>|<span data-ttu-id="037a2-441">R</span><span class="sxs-lookup"><span data-stu-id="037a2-441">R</span></span>|<span data-ttu-id="037a2-442">"ComputerName"</span><span class="sxs-lookup"><span data-stu-id="037a2-442">"ComputerName"</span></span>|  
|<span data-ttu-id="037a2-443">SQLCMDDBNAME</span><span class="sxs-lookup"><span data-stu-id="037a2-443">SQLCMDDBNAME</span></span>|<span data-ttu-id="037a2-444">-d</span><span class="sxs-lookup"><span data-stu-id="037a2-444">-d</span></span>|<span data-ttu-id="037a2-445">R</span><span class="sxs-lookup"><span data-stu-id="037a2-445">R</span></span>|<span data-ttu-id="037a2-446">""</span><span class="sxs-lookup"><span data-stu-id="037a2-446">""</span></span>|  
|<span data-ttu-id="037a2-447">SQLCMDLOGINTIMEOUT</span><span class="sxs-lookup"><span data-stu-id="037a2-447">SQLCMDLOGINTIMEOUT</span></span>|<span data-ttu-id="037a2-448">-l</span><span class="sxs-lookup"><span data-stu-id="037a2-448">-l</span></span>|<span data-ttu-id="037a2-449">Чтение-запись</span><span class="sxs-lookup"><span data-stu-id="037a2-449">R/W</span></span>|<span data-ttu-id="037a2-450">"8" (секунд)</span><span class="sxs-lookup"><span data-stu-id="037a2-450">"8" (seconds)</span></span>|  
|<span data-ttu-id="037a2-451">SQLCMDSTATTIMEOUT</span><span class="sxs-lookup"><span data-stu-id="037a2-451">SQLCMDSTATTIMEOUT</span></span>|<span data-ttu-id="037a2-452">-T</span><span class="sxs-lookup"><span data-stu-id="037a2-452">-t</span></span>|<span data-ttu-id="037a2-453">Чтение-запись</span><span class="sxs-lookup"><span data-stu-id="037a2-453">R/W</span></span>|<span data-ttu-id="037a2-454">"0" = неограниченное время ожидания</span><span class="sxs-lookup"><span data-stu-id="037a2-454">"0" = wait indefinitely</span></span>|  
|<span data-ttu-id="037a2-455">SQLCMDHEADERS</span><span class="sxs-lookup"><span data-stu-id="037a2-455">SQLCMDHEADERS</span></span>|<span data-ttu-id="037a2-456">-H</span><span class="sxs-lookup"><span data-stu-id="037a2-456">-h</span></span>|<span data-ttu-id="037a2-457">Чтение-запись</span><span class="sxs-lookup"><span data-stu-id="037a2-457">R/W</span></span>|<span data-ttu-id="037a2-458">"0"</span><span class="sxs-lookup"><span data-stu-id="037a2-458">"0"</span></span>|  
|<span data-ttu-id="037a2-459">SQLCMDCOLSEP</span><span class="sxs-lookup"><span data-stu-id="037a2-459">SQLCMDCOLSEP</span></span>|<span data-ttu-id="037a2-460">-S</span><span class="sxs-lookup"><span data-stu-id="037a2-460">-s</span></span>|<span data-ttu-id="037a2-461">Чтение-запись</span><span class="sxs-lookup"><span data-stu-id="037a2-461">R/W</span></span>|<span data-ttu-id="037a2-462">" "</span><span class="sxs-lookup"><span data-stu-id="037a2-462">" "</span></span>|  
|<span data-ttu-id="037a2-463">SQLCMDCOLWIDTH</span><span class="sxs-lookup"><span data-stu-id="037a2-463">SQLCMDCOLWIDTH</span></span>|<span data-ttu-id="037a2-464">-w</span><span class="sxs-lookup"><span data-stu-id="037a2-464">-w</span></span>|<span data-ttu-id="037a2-465">Чтение-запись</span><span class="sxs-lookup"><span data-stu-id="037a2-465">R/W</span></span>|<span data-ttu-id="037a2-466">"0"</span><span class="sxs-lookup"><span data-stu-id="037a2-466">"0"</span></span>|  
|<span data-ttu-id="037a2-467">SQLCMDPACKETSIZE</span><span class="sxs-lookup"><span data-stu-id="037a2-467">SQLCMDPACKETSIZE</span></span>|<span data-ttu-id="037a2-468">-a</span><span class="sxs-lookup"><span data-stu-id="037a2-468">-a</span></span>|<span data-ttu-id="037a2-469">R</span><span class="sxs-lookup"><span data-stu-id="037a2-469">R</span></span>|<span data-ttu-id="037a2-470">"4096"</span><span class="sxs-lookup"><span data-stu-id="037a2-470">"4096"</span></span>|  
|<span data-ttu-id="037a2-471">SQLCMDERRORLEVEL</span><span class="sxs-lookup"><span data-stu-id="037a2-471">SQLCMDERRORLEVEL</span></span>|<span data-ttu-id="037a2-472">-M</span><span class="sxs-lookup"><span data-stu-id="037a2-472">-m</span></span>|<span data-ttu-id="037a2-473">Чтение-запись</span><span class="sxs-lookup"><span data-stu-id="037a2-473">R/W</span></span>|<span data-ttu-id="037a2-474">0</span><span class="sxs-lookup"><span data-stu-id="037a2-474">0</span></span>|  
|<span data-ttu-id="037a2-475">SQLCMDMAXVARTYPEWIDTH</span><span class="sxs-lookup"><span data-stu-id="037a2-475">SQLCMDMAXVARTYPEWIDTH</span></span>|<span data-ttu-id="037a2-476">-y</span><span class="sxs-lookup"><span data-stu-id="037a2-476">-y</span></span>|<span data-ttu-id="037a2-477">Чтение-запись</span><span class="sxs-lookup"><span data-stu-id="037a2-477">R/W</span></span>|<span data-ttu-id="037a2-478">«256»</span><span class="sxs-lookup"><span data-stu-id="037a2-478">"256"</span></span>|  
|<span data-ttu-id="037a2-479">SQLCMDMAXFIXEDTYPEWIDTH</span><span class="sxs-lookup"><span data-stu-id="037a2-479">SQLCMDMAXFIXEDTYPEWIDTH</span></span>|<span data-ttu-id="037a2-480">-y</span><span class="sxs-lookup"><span data-stu-id="037a2-480">-Y</span></span>|<span data-ttu-id="037a2-481">Чтение-запись</span><span class="sxs-lookup"><span data-stu-id="037a2-481">R/W</span></span>|<span data-ttu-id="037a2-482">"0" = неограниченное время ожидания</span><span class="sxs-lookup"><span data-stu-id="037a2-482">"0" = unlimited</span></span>|  
|<span data-ttu-id="037a2-483">SQLCMDEDITOR</span><span class="sxs-lookup"><span data-stu-id="037a2-483">SQLCMDEDITOR</span></span>||<span data-ttu-id="037a2-484">Чтение-запись</span><span class="sxs-lookup"><span data-stu-id="037a2-484">R/W</span></span>|<span data-ttu-id="037a2-485">"edit.com"</span><span class="sxs-lookup"><span data-stu-id="037a2-485">"edit.com"</span></span>|  
|<span data-ttu-id="037a2-486">SQLCMDINI</span><span class="sxs-lookup"><span data-stu-id="037a2-486">SQLCMDINI</span></span>||<span data-ttu-id="037a2-487">R</span><span class="sxs-lookup"><span data-stu-id="037a2-487">R</span></span>|<span data-ttu-id="037a2-488">""</span><span class="sxs-lookup"><span data-stu-id="037a2-488">""</span></span>|  
  
 <span data-ttu-id="037a2-489">Переменные SQLCMDUSER, SQLCMDPASSWORD и SQLCMDSERVER устанавливаются при использовании команды **:Connect**</span><span class="sxs-lookup"><span data-stu-id="037a2-489">SQLCMDUSER, SQLCMDPASSWORD and SQLCMDSERVER are set when **:Connect**</span></span>  
  
 <span data-ttu-id="037a2-490">.</span><span class="sxs-lookup"><span data-stu-id="037a2-490">is used.</span></span>  
  
 <span data-ttu-id="037a2-491">Пометка «Чтение» означает, что значение может быть задано только один раз в процессе инициализации программы.</span><span class="sxs-lookup"><span data-stu-id="037a2-491">R indicates the value can only be set one time during program initialization.</span></span>  
  
 <span data-ttu-id="037a2-492">Пометка "Чтение/запись" означает, что переменная может быть изменена командой **setvar** и все последующие команды будут использовать новое значение.</span><span class="sxs-lookup"><span data-stu-id="037a2-492">R/W indicates that the value can be modified by using the **setvar** command and subsequent commands will be influenced by the new value.</span></span>  
  
## <a name="sqlcmd-commands"></a><span data-ttu-id="037a2-493">Команды sqlcmd</span><span class="sxs-lookup"><span data-stu-id="037a2-493">sqlcmd Commands</span></span>  
 <span data-ttu-id="037a2-494">В дополнение к инструкциям [!INCLUDE[tsql](../includes/tsql-md.md)] в программе `sqlcmd` доступны также следующие команды:</span><span class="sxs-lookup"><span data-stu-id="037a2-494">In addition to [!INCLUDE[tsql](../includes/tsql-md.md)] statements within `sqlcmd`, the following commands are also available:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="037a2-495">**GO** [*число*]</span><span class="sxs-lookup"><span data-stu-id="037a2-495">**GO** [*count*]</span></span>|<span data-ttu-id="037a2-496">**:List**</span><span class="sxs-lookup"><span data-stu-id="037a2-496">**:List**</span></span>|  
|<span data-ttu-id="037a2-497">[ **:** ] **RESET**</span><span class="sxs-lookup"><span data-stu-id="037a2-497">[**:**] **RESET**</span></span>|<span data-ttu-id="037a2-498">**:Error**</span><span class="sxs-lookup"><span data-stu-id="037a2-498">**:Error**</span></span>|  
|<span data-ttu-id="037a2-499">[ **:** ] **ED**</span><span class="sxs-lookup"><span data-stu-id="037a2-499">[**:**] **ED**</span></span>|<span data-ttu-id="037a2-500">**:Out**</span><span class="sxs-lookup"><span data-stu-id="037a2-500">**:Out**</span></span>|  
|<span data-ttu-id="037a2-501">[**:**] **!!**</span><span class="sxs-lookup"><span data-stu-id="037a2-501">[**:**] **!!**</span></span>|<span data-ttu-id="037a2-502">**:Perftrace**</span><span class="sxs-lookup"><span data-stu-id="037a2-502">**:Perftrace**</span></span>|  
|<span data-ttu-id="037a2-503">[ **:** ] **QUIT**</span><span class="sxs-lookup"><span data-stu-id="037a2-503">[**:**] **QUIT**</span></span>|<span data-ttu-id="037a2-504">**:Connect**</span><span class="sxs-lookup"><span data-stu-id="037a2-504">**:Connect**</span></span>|  
|<span data-ttu-id="037a2-505">[ **:** ] **EXIT**</span><span class="sxs-lookup"><span data-stu-id="037a2-505">[**:**] **EXIT**</span></span>|<span data-ttu-id="037a2-506">**:On Error**</span><span class="sxs-lookup"><span data-stu-id="037a2-506">**:On Error**</span></span>|  
|<span data-ttu-id="037a2-507">**:r**</span><span class="sxs-lookup"><span data-stu-id="037a2-507">**:r**</span></span>|<span data-ttu-id="037a2-508">**:Help**</span><span class="sxs-lookup"><span data-stu-id="037a2-508">**:Help**</span></span>|  
|<span data-ttu-id="037a2-509">**:ServerList**</span><span class="sxs-lookup"><span data-stu-id="037a2-509">**:ServerList**</span></span>|<span data-ttu-id="037a2-510">**:XML** [**ON** &#124; **OFF**]</span><span class="sxs-lookup"><span data-stu-id="037a2-510">**:XML** [**ON** &#124; **OFF**]</span></span>|  
|<span data-ttu-id="037a2-511">**:Setvar**</span><span class="sxs-lookup"><span data-stu-id="037a2-511">**:Setvar**</span></span>|<span data-ttu-id="037a2-512">**:Listvar**</span><span class="sxs-lookup"><span data-stu-id="037a2-512">**:Listvar**</span></span>|  
  
 <span data-ttu-id="037a2-513">При использовании команд программы `sqlcmd` следует учитывать следующие особенности.</span><span class="sxs-lookup"><span data-stu-id="037a2-513">Be aware of the following when you use `sqlcmd` commands:</span></span>  
  
-   <span data-ttu-id="037a2-514">Все команды `sqlcmd`, за исключением GO, должны предваряться двоеточием (:).</span><span class="sxs-lookup"><span data-stu-id="037a2-514">All `sqlcmd` commands, except GO, must be prefixed by a colon (:).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="037a2-515">Для поддержки обратной совместимости с существующими скриптами **osql** , некоторые команды будут распознаваться без двоеточия.</span><span class="sxs-lookup"><span data-stu-id="037a2-515">To maintain backward compatibility with existing **osql** scripts, some of the commands will be recognized without the colon.</span></span> <span data-ttu-id="037a2-516">На это указывают символы[**:**].</span><span class="sxs-lookup"><span data-stu-id="037a2-516">This is indicated by the [**:**].</span></span>  
  
-   <span data-ttu-id="037a2-517">Команды `sqlcmd` распознаются только в случае, если они введены в начале строки.</span><span class="sxs-lookup"><span data-stu-id="037a2-517">`sqlcmd` commands are recognized only if they appear at the start of a line.</span></span>  
  
-   <span data-ttu-id="037a2-518">Во всех командах `sqlcmd` регистр символов не учитывается.</span><span class="sxs-lookup"><span data-stu-id="037a2-518">All `sqlcmd` commands are case insensitive.</span></span>  
  
-   <span data-ttu-id="037a2-519">Каждая команда должна находиться на отдельной строке.</span><span class="sxs-lookup"><span data-stu-id="037a2-519">Each command must be on a separate line.</span></span> <span data-ttu-id="037a2-520">За командой не должна следовать инструкция [!INCLUDE[tsql](../includes/tsql-md.md)] или другая команда.</span><span class="sxs-lookup"><span data-stu-id="037a2-520">A command cannot be followed by a [!INCLUDE[tsql](../includes/tsql-md.md)] statement or another command.</span></span>  
  
-   <span data-ttu-id="037a2-521">Команды выполняются немедленно.</span><span class="sxs-lookup"><span data-stu-id="037a2-521">Commands are executed immediately.</span></span> <span data-ttu-id="037a2-522">Они не помещаются в буфер выполнения, как инструкции [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="037a2-522">They are not put in the execution buffer as [!INCLUDE[tsql](../includes/tsql-md.md)] statements are.</span></span>  
  
 <span data-ttu-id="037a2-523">**Команды изменения**</span><span class="sxs-lookup"><span data-stu-id="037a2-523">**Editing Commands**</span></span>  
  <span data-ttu-id="037a2-524">[ **:** ] **ED**</span><span class="sxs-lookup"><span data-stu-id="037a2-524">[**:**] **ED**</span></span>  
 <span data-ttu-id="037a2-525">Производит запуск текстового редактора.</span><span class="sxs-lookup"><span data-stu-id="037a2-525">Starts the text editor.</span></span> <span data-ttu-id="037a2-526">Этот редактор может использоваться для изменения текущего пакета [!INCLUDE[tsql](../includes/tsql-md.md)] или последнего выполненного пакета.</span><span class="sxs-lookup"><span data-stu-id="037a2-526">This editor can be used to edit the current [!INCLUDE[tsql](../includes/tsql-md.md)] batch, or the last executed batch.</span></span> <span data-ttu-id="037a2-527">Для изменения последнего выполненного пакета необходимо ввести команду **ED** сразу после выполнения последнего пакета.</span><span class="sxs-lookup"><span data-stu-id="037a2-527">To edit the last executed batch, the **ED** command must be typed immediately after the last batch has completed execution.</span></span>  
  
 <span data-ttu-id="037a2-528">Текстовый редактор определяется переменной среды SQLCMDEDITOR.</span><span class="sxs-lookup"><span data-stu-id="037a2-528">The text editor is defined by the SQLCMDEDITOR environment variable.</span></span> <span data-ttu-id="037a2-529">Редактором по умолчанию является «Edit».</span><span class="sxs-lookup"><span data-stu-id="037a2-529">The default editor is 'Edit'.</span></span> <span data-ttu-id="037a2-530">Чтобы изменить редактор, установите переменную среды SQLCMDEDITOR.</span><span class="sxs-lookup"><span data-stu-id="037a2-530">To change the editor, set the SQLCMDEDITOR environment variable.</span></span> <span data-ttu-id="037a2-531">Например, чтобы установить в качестве редактора Блокнот ( [!INCLUDE[msCoName](../includes/msconame-md.md)] ), в командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="037a2-531">For example, to set the editor to [!INCLUDE[msCoName](../includes/msconame-md.md)] Notepad, at the command prompt, type:</span></span>  
  
 `SET SQLCMDEDITOR=notepad`  
  
 <span data-ttu-id="037a2-532">[ **:** ] **RESET**</span><span class="sxs-lookup"><span data-stu-id="037a2-532">[**:**] **RESET**</span></span>  
 <span data-ttu-id="037a2-533">Очистка кэша инструкций.</span><span class="sxs-lookup"><span data-stu-id="037a2-533">Clears the statement cache.</span></span>  
  
 <span data-ttu-id="037a2-534">**:List**</span><span class="sxs-lookup"><span data-stu-id="037a2-534">**:List**</span></span>  
 <span data-ttu-id="037a2-535">Вывод содержимого кэша инструкций.</span><span class="sxs-lookup"><span data-stu-id="037a2-535">Prints the content of the statement cache.</span></span>  
  
 <span data-ttu-id="037a2-536">**Переменные**</span><span class="sxs-lookup"><span data-stu-id="037a2-536">**Variables**</span></span>  
  <span data-ttu-id="037a2-537">**: Setvar** \<**var**> [ **"*`value`*"** ]</span><span class="sxs-lookup"><span data-stu-id="037a2-537">**:Setvar** \<**var**> [ **"*`value`*"** ]</span></span>  
 <span data-ttu-id="037a2-538">Определяет переменные скрипта `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="037a2-538">Defines `sqlcmd` scripting variables.</span></span> <span data-ttu-id="037a2-539">Переменные скрипта имеют следующий формат: `$(VARNAME)`.</span><span class="sxs-lookup"><span data-stu-id="037a2-539">Scripting variables have the following format: `$(VARNAME)`.</span></span>  
  
 <span data-ttu-id="037a2-540">Имена переменных не зависят от регистра символов.</span><span class="sxs-lookup"><span data-stu-id="037a2-540">Variable names are case insensitive.</span></span>  
  
 <span data-ttu-id="037a2-541">Переменные скрипта могут быть установлены следующими способами.</span><span class="sxs-lookup"><span data-stu-id="037a2-541">Scripting variables can be set in the following ways:</span></span>  
  
-   <span data-ttu-id="037a2-542">Неявно, с помощью параметра командной строки.</span><span class="sxs-lookup"><span data-stu-id="037a2-542">Implicitly using a command-line option.</span></span> <span data-ttu-id="037a2-543">Например, параметр **-l** задает `sqlcmd` переменную SQLCMDLOGINTIMEOUT.</span><span class="sxs-lookup"><span data-stu-id="037a2-543">For example, the **-l** option sets the SQLCMDLOGINTIMEOUT `sqlcmd` variable.</span></span>  
  
-   <span data-ttu-id="037a2-544">Явным образом, с помощью команды **:Setvar** .</span><span class="sxs-lookup"><span data-stu-id="037a2-544">Explicitly by using the **:Setvar** command.</span></span>  
  
-   <span data-ttu-id="037a2-545">Путем установки переменной среды до запуска программы `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="037a2-545">By defining an environment variable before you run `sqlcmd`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="037a2-546">Параметр `-X` предотвращает передачу переменных среды программе `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="037a2-546">The `-X` option prevents environment variables from being passed on to `sqlcmd`.</span></span>  
  
 <span data-ttu-id="037a2-547">Если переменная, определенная с использованием **:Setvar** и переменной окружения, имеет одно и то же имя, переменная, определенная с помощью **:Setvar** имеет преимущество.</span><span class="sxs-lookup"><span data-stu-id="037a2-547">If a variable defined by using **:Setvar** and an environment variable have the same name, the variable defined by using **:Setvar** takes precedence.</span></span>  
  
 <span data-ttu-id="037a2-548">Имена переменных не должны содержать пробелы.</span><span class="sxs-lookup"><span data-stu-id="037a2-548">Variable names must not contain blank space characters.</span></span>  
  
 <span data-ttu-id="037a2-549">Имена переменных не могут иметь тот же формат, что и выражение переменной: $(переменная).</span><span class="sxs-lookup"><span data-stu-id="037a2-549">Variable names cannot have the same form as a variable expression, such as $(var).</span></span>  
  
 <span data-ttu-id="037a2-550">Если строковое значение переменной скрипта содержит пробелы, то заключите значение в кавычки.</span><span class="sxs-lookup"><span data-stu-id="037a2-550">If the string value of the scripting variable contains blank spaces, enclose the value in quotation marks.</span></span> <span data-ttu-id="037a2-551">Если значение для переменной скрипта не указано, переменная скрипта удаляется.</span><span class="sxs-lookup"><span data-stu-id="037a2-551">If a value for a scripting variable is not specified, the scripting variable is dropped.</span></span>  
  
 <span data-ttu-id="037a2-552">**:Listvar**</span><span class="sxs-lookup"><span data-stu-id="037a2-552">**:Listvar**</span></span>  
 <span data-ttu-id="037a2-553">Список переменных скрипта, заданных в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="037a2-553">Displays a list of the scripting variables that are currently set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="037a2-554">Будут отображены только переменные скрипта, заданные параметром `sqlcmd` , и те, которые задаются с помощью команды **: setvar** .</span><span class="sxs-lookup"><span data-stu-id="037a2-554">Only scripting variables that are set by `sqlcmd`, and those that are set using the **:Setvar** command will be displayed.</span></span>  
  
 <span data-ttu-id="037a2-555">**Команды вывода**</span><span class="sxs-lookup"><span data-stu-id="037a2-555">**Output Commands**</span></span>  
  <span data-ttu-id="037a2-556">**:Error** </span><span class="sxs-lookup"><span data-stu-id="037a2-556">**:Error** </span></span>  
 <span data-ttu-id="037a2-557">**_\<_** _filename_  **_>|_ STDERR | STDOUT**</span><span class="sxs-lookup"><span data-stu-id="037a2-557">**_\<_** _filename_  **_>|_ STDERR|STDOUT**</span></span>  
 <span data-ttu-id="037a2-558">Перенаправляет вывод всех сообщений об ошибках в файл, указываемый параметром *имя_файла*, в поток **stderr** или **stdout**.</span><span class="sxs-lookup"><span data-stu-id="037a2-558">Redirect all error output to the file specified by *file name*, to **stderr** or to **stdout**.</span></span> <span data-ttu-id="037a2-559">Команда **Error** может встречаться в скрипте несколько раз.</span><span class="sxs-lookup"><span data-stu-id="037a2-559">The **Error** command can appear multiple times in a script.</span></span> <span data-ttu-id="037a2-560">По умолчанию вывод об ошибках направляется в **STDERR**.</span><span class="sxs-lookup"><span data-stu-id="037a2-560">By default, error output is sent to **stderr**.</span></span>  
  
 <span data-ttu-id="037a2-561">*имя_файла*</span><span class="sxs-lookup"><span data-stu-id="037a2-561">*file name*</span></span>  
 <span data-ttu-id="037a2-562">Создает и открывает файл, который принимает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="037a2-562">Creates and opens a file that will receive the output.</span></span> <span data-ttu-id="037a2-563">Если файл уже существует, он будет усечен до 0 байт.</span><span class="sxs-lookup"><span data-stu-id="037a2-563">If the file already exists, it will be truncated to zero bytes.</span></span> <span data-ttu-id="037a2-564">Если файл недоступен по причине нехватки разрешений или по другим причинам, вывод перенаправляется не в него, а в последнее указанное назначение или в назначение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="037a2-564">If the file is not available because of permissions or other reasons, the output will not be switched and will be sent to the last specified or default destination.</span></span>  
  
 <span data-ttu-id="037a2-565">**STDERR**</span><span class="sxs-lookup"><span data-stu-id="037a2-565">**STDERR**</span></span>  
 <span data-ttu-id="037a2-566">Перенаправляет вывод сообщений об ошибках в поток **stderr** .</span><span class="sxs-lookup"><span data-stu-id="037a2-566">Switches error output to the **stderr** stream.</span></span> <span data-ttu-id="037a2-567">Если было выполнено перенаправление, то адресат, которому был перенаправлен поток, получит выход ошибок.</span><span class="sxs-lookup"><span data-stu-id="037a2-567">If this has been redirected, the target to which the stream has been redirected will receive the error output.</span></span>  
  
 <span data-ttu-id="037a2-568">**STDOUT**</span><span class="sxs-lookup"><span data-stu-id="037a2-568">**STDOUT**</span></span>  
 <span data-ttu-id="037a2-569">Перенаправляет выход ошибок в поток **stdout** .</span><span class="sxs-lookup"><span data-stu-id="037a2-569">Switches error output to the **stdout** stream.</span></span> <span data-ttu-id="037a2-570">Если было выполнено перенаправление, то адресат, которому был перенаправлен поток, получит выход ошибок.</span><span class="sxs-lookup"><span data-stu-id="037a2-570">If this has been redirected, the target to which the stream has been redirected will receive the error output.</span></span>  
  
 <span data-ttu-id="037a2-571">\*\*: Out \<** _filename_ **> \*\* |  **Stderr** |  **Stdout**</span><span class="sxs-lookup"><span data-stu-id="037a2-571">**:Out \<** _filename_ **>**| **STDERR**| **STDOUT**</span></span>  
 <span data-ttu-id="037a2-572">Создает и переадресовывает все результаты запроса в файл, указываемый параметром *имя_файла*, в **stderr** или **stdout**.</span><span class="sxs-lookup"><span data-stu-id="037a2-572">Creates and redirects all query results to the file specified by *file name*, to **stderr** or to **stdout**.</span></span> <span data-ttu-id="037a2-573">По умолчанию вывод направляется в **stdout**.</span><span class="sxs-lookup"><span data-stu-id="037a2-573">By default, output is sent to **stdout**.</span></span> <span data-ttu-id="037a2-574">Если файл уже существует, он будет усечен до 0 байт.</span><span class="sxs-lookup"><span data-stu-id="037a2-574">If the file already exists, it will be truncated to zero bytes.</span></span> <span data-ttu-id="037a2-575">Команда **Out** может встречаться в скрипте несколько раз.</span><span class="sxs-lookup"><span data-stu-id="037a2-575">The **Out** command can appear multiple times in a script.</span></span>  
  
 <span data-ttu-id="037a2-576">\*\*:P ерфтраце \<** _filename_ **> \*\* |  **Stderr** |  **Stdout**</span><span class="sxs-lookup"><span data-stu-id="037a2-576">**:Perftrace \<** _filename_ **>**| **STDERR**| **STDOUT**</span></span>  
 <span data-ttu-id="037a2-577">Создает и переадресовывает все данные трассировки производительности в файл, указываемый параметром *имя_файла*, в **stderr** или **stdout**.</span><span class="sxs-lookup"><span data-stu-id="037a2-577">Creates and redirects all performance trace information to the file specified by *file name*, to **stderr** or to **stdout**.</span></span> <span data-ttu-id="037a2-578">По умолчанию вывод о трассировки производительности направляется в **stdout**.</span><span class="sxs-lookup"><span data-stu-id="037a2-578">By default performance trace output is sent to **stdout**.</span></span> <span data-ttu-id="037a2-579">Если файл уже существует, он будет усечен до 0 байт.</span><span class="sxs-lookup"><span data-stu-id="037a2-579">If the file already exists, it will be truncated to zero bytes.</span></span> <span data-ttu-id="037a2-580">Команда **Perftrace** может встречаться в скрипте несколько раз.</span><span class="sxs-lookup"><span data-stu-id="037a2-580">The **Perftrace** command can appear multiple times in a script.</span></span>  
  
 <span data-ttu-id="037a2-581">**Команды контроля выполнения**</span><span class="sxs-lookup"><span data-stu-id="037a2-581">**Execution Control Commands**</span></span>  
  <span data-ttu-id="037a2-582">**: On Error**[ `exit`  |  `ignore` ]</span><span class="sxs-lookup"><span data-stu-id="037a2-582">**:On Error**[ `exit` | `ignore`]</span></span>  
 <span data-ttu-id="037a2-583">Установка действия, выполняемого при возникновении ошибки во время исполнения скрипта или пакета.</span><span class="sxs-lookup"><span data-stu-id="037a2-583">Sets the action to be performed when an error occurs during script or batch execution.</span></span>  
  
 <span data-ttu-id="037a2-584">Если используется параметр `exit`, программа `sqlcmd` завершает работу с возвратом значения соответствующей ошибки.</span><span class="sxs-lookup"><span data-stu-id="037a2-584">When the `exit` option is used, `sqlcmd` exits with the appropriate error value.</span></span>  
  
 <span data-ttu-id="037a2-585">Если указан параметр `ignore`, ошибка пропускается параметром `sqlcmd` и продолжается выполнение пакета или скрипта.</span><span class="sxs-lookup"><span data-stu-id="037a2-585">When the `ignore` option is used, `sqlcmd` ignores the error and continues executing the batch or script.</span></span> <span data-ttu-id="037a2-586">По умолчанию будет распечатано сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="037a2-586">By default, an error message will be printed.</span></span>  
  
 <span data-ttu-id="037a2-587">[ **:** ] **QUIT**</span><span class="sxs-lookup"><span data-stu-id="037a2-587">[**:**] **QUIT**</span></span>  
 <span data-ttu-id="037a2-588">Вызывает закрытие `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="037a2-588">Causes `sqlcmd` to exit.</span></span>  
  
 <span data-ttu-id="037a2-589">[**:**] **Exit**[ **( *`statement`* )** ]</span><span class="sxs-lookup"><span data-stu-id="037a2-589">[**:**] **EXIT**[ **(*`statement`*)** ]</span></span>  
 <span data-ttu-id="037a2-590">Позволяет использовать результат выполнения инструкции SELECT в качестве возвращаемого значения программы `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="037a2-590">Lets you use the result of a SELECT statement as the return value from `sqlcmd`.</span></span> <span data-ttu-id="037a2-591">Если числовой, первый столбец последней строки результатов преобразуется в 4-байтовое целое число (long).</span><span class="sxs-lookup"><span data-stu-id="037a2-591">If numeric, the first column of the last result row is converted to a 4-byte integer (long).</span></span> <span data-ttu-id="037a2-592">В MS-DOS младший байт передается родительскому процессу или уровню ошибки операционной системы.</span><span class="sxs-lookup"><span data-stu-id="037a2-592">MS-DOS passes the low byte to the parent process or operating system error level.</span></span> <span data-ttu-id="037a2-593">В Windows 200x передается 4-байтовое целое число.</span><span class="sxs-lookup"><span data-stu-id="037a2-593">Windows 200x passes the whole 4-byte integer.</span></span> <span data-ttu-id="037a2-594">Синтаксис:</span><span class="sxs-lookup"><span data-stu-id="037a2-594">The syntax is:</span></span>  
  
 `:EXIT(query)`  
  
 <span data-ttu-id="037a2-595">Пример:</span><span class="sxs-lookup"><span data-stu-id="037a2-595">For example:</span></span>  
  
 `:EXIT(SELECT @@ROWCOUNT)`  
  
 <span data-ttu-id="037a2-596">Также можно включить параметр **EXIT** в пакетный файл.</span><span class="sxs-lookup"><span data-stu-id="037a2-596">You can also include the **EXIT** parameter as part of a batch file.</span></span> <span data-ttu-id="037a2-597">Например, в командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="037a2-597">For example, at the command prompt, type:</span></span>  
  
 `sqlcmd -Q "EXIT(SELECT COUNT(*) FROM '%1')"`  
  
 <span data-ttu-id="037a2-598">`sqlcmd`Служебная программа отправляет на сервер все, что заключено в круглые скобки **()** .</span><span class="sxs-lookup"><span data-stu-id="037a2-598">The `sqlcmd` utility sends everything between the parentheses **()** to the server.</span></span> <span data-ttu-id="037a2-599">Если хранимая системная процедура выбирает набор и возвращает значение, то возвращается только выбранный набор.</span><span class="sxs-lookup"><span data-stu-id="037a2-599">If a system stored procedure selects a set and returns a value, only the selection is returned.</span></span> <span data-ttu-id="037a2-600">Инструкция EXIT **()** с пустыми круглыми скобками выполняет все, что предшествует ей в пакете, а затем завершается без возврата значения.</span><span class="sxs-lookup"><span data-stu-id="037a2-600">The EXIT **()** statement with nothing between the parentheses executes everything before it in the batch and then exits without a return value.</span></span>  
  
 <span data-ttu-id="037a2-601">Если указан неверный запрос, программа `sqlcmd` завершит работу, не возвращая значения.</span><span class="sxs-lookup"><span data-stu-id="037a2-601">When an incorrect query is specified, `sqlcmd` will exit without a return value.</span></span>  
  
 <span data-ttu-id="037a2-602">Список форматов инструкции EXIT:</span><span class="sxs-lookup"><span data-stu-id="037a2-602">Here is a list of EXIT formats:</span></span>  
  
-   <span data-ttu-id="037a2-603">:EXIT</span><span class="sxs-lookup"><span data-stu-id="037a2-603">:EXIT</span></span>  
  
 <span data-ttu-id="037a2-604">Не выполняет пакет, немедленно завершает работу и не возвращает значения.</span><span class="sxs-lookup"><span data-stu-id="037a2-604">Does not execute the batch, and then quits immediately and returns no value.</span></span>  
  
-   <span data-ttu-id="037a2-605">:EXIT( )</span><span class="sxs-lookup"><span data-stu-id="037a2-605">:EXIT( )</span></span>  
  
 <span data-ttu-id="037a2-606">Выполняет пакет, завершает выполнение и не возвращает значения.</span><span class="sxs-lookup"><span data-stu-id="037a2-606">Executes the batch, and then quits and returns no value.</span></span>  
  
-   <span data-ttu-id="037a2-607">:EXIT(query)</span><span class="sxs-lookup"><span data-stu-id="037a2-607">:EXIT(query)</span></span>  
  
 <span data-ttu-id="037a2-608">Выполняет пакет, включая запрос, возвращает результаты запроса и завершает работу.</span><span class="sxs-lookup"><span data-stu-id="037a2-608">Executes the batch that includes the query, and then quits after it returns the results of the query.</span></span>  
  
 <span data-ttu-id="037a2-609">Если в скрипте `sqlcmd` используется параметр RAISERROR, и при этом возникает состояние 127, программа `sqlcmd` завершает выполнение и возвращает клиенту идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="037a2-609">If RAISERROR is used within a `sqlcmd` script and a state of 127 is raised, `sqlcmd` will quit and return the message ID back to the client.</span></span> <span data-ttu-id="037a2-610">Пример:</span><span class="sxs-lookup"><span data-stu-id="037a2-610">For example:</span></span>  
  
 `RAISERROR(50001, 10, 127)`  
  
 <span data-ttu-id="037a2-611">Эта ошибка приведет к завершению скрипта `sqlcmd`, а клиенту будет возвращено сообщение с идентификатором 50001.</span><span class="sxs-lookup"><span data-stu-id="037a2-611">This error will cause the `sqlcmd` script to end and return the message ID 50001 to the client.</span></span>  
  
 <span data-ttu-id="037a2-612">Возвращаемые значения от -1 до -99 зарезервированы [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]. Программа `sqlcmd` дополнительно определяет следующие коды возврата:</span><span class="sxs-lookup"><span data-stu-id="037a2-612">The return values -1 to -99 are reserved by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]; `sqlcmd` defines the following additional return values:</span></span>  
  
|<span data-ttu-id="037a2-613">Возвращаемые значения</span><span class="sxs-lookup"><span data-stu-id="037a2-613">Return Values</span></span>|<span data-ttu-id="037a2-614">Описание</span><span class="sxs-lookup"><span data-stu-id="037a2-614">Description</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="037a2-615">–100</span><span class="sxs-lookup"><span data-stu-id="037a2-615">-100</span></span>|<span data-ttu-id="037a2-616">Перед выбором возвращаемого значения произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="037a2-616">Error encountered prior to selecting return value.</span></span>|  
|<span data-ttu-id="037a2-617">–101</span><span class="sxs-lookup"><span data-stu-id="037a2-617">-101</span></span>|<span data-ttu-id="037a2-618">При выборе возвращаемого значения не найдены строки.</span><span class="sxs-lookup"><span data-stu-id="037a2-618">No rows found when selecting return value.</span></span>|  
|<span data-ttu-id="037a2-619">–102</span><span class="sxs-lookup"><span data-stu-id="037a2-619">-102</span></span>|<span data-ttu-id="037a2-620">При выборе возвращаемого значения произошла ошибка преобразования.</span><span class="sxs-lookup"><span data-stu-id="037a2-620">Conversion error occurred when selecting return value.</span></span>|  
  
 <span data-ttu-id="037a2-621">**GO** [*число*]</span><span class="sxs-lookup"><span data-stu-id="037a2-621">**GO** [*count*]</span></span>  
 <span data-ttu-id="037a2-622">GO обозначает конец пакетного файла и исполнения любых кэшированных инструкций [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="037a2-622">GO signals both the end of a batch and the execution of any cached [!INCLUDE[tsql](../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="037a2-623">При задании значения для параметра *count*кэшируемые инструкции будут выполняться указанное *count* раз в виде единого пакета.</span><span class="sxs-lookup"><span data-stu-id="037a2-623">When specifying a value for *count*, the cached statements will be executed *count* times, as a single batch.</span></span>  
  
 <span data-ttu-id="037a2-624">**Прочие команды**</span><span class="sxs-lookup"><span data-stu-id="037a2-624">**Miscellaneous Commands**</span></span>  
  <span data-ttu-id="037a2-625">**: r\<** _filename_ **>**</span><span class="sxs-lookup"><span data-stu-id="037a2-625">**:r \<** _filename_ **>**</span></span>  
 <span data-ttu-id="037a2-626">Выполняет синтаксический анализ дополнительных [!INCLUDE[tsql](../includes/tsql-md.md)] инструкций и `sqlcmd` команд из файла, указанного **<*`filename`*>** в кэше инструкций.</span><span class="sxs-lookup"><span data-stu-id="037a2-626">Parses additional [!INCLUDE[tsql](../includes/tsql-md.md)] statements and `sqlcmd` commands from the file specified by **<*`filename`*>** into the statement cache.</span></span>  
  
 <span data-ttu-id="037a2-627">Если файл содержит инструкции [!INCLUDE[tsql](../includes/tsql-md.md)] , за которыми не следует ключевое слово **GO**, необходимо ввести **GO** в строку, следующую за **:r**.</span><span class="sxs-lookup"><span data-stu-id="037a2-627">If the file contains [!INCLUDE[tsql](../includes/tsql-md.md)] statements that are not followed by **GO**, you must enter **GO** on the line that follows **:r**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="037a2-628">**\<** _filename_ **>** считывается относительно каталога запуска, в котором выполнялся `sqlcmd` .</span><span class="sxs-lookup"><span data-stu-id="037a2-628">**\<** _filename_ **>** is read relative to the startup directory in which `sqlcmd` was run.</span></span>  
  
 <span data-ttu-id="037a2-629">Файл будет считан и выполнен после обнаружения признака конца пакета.</span><span class="sxs-lookup"><span data-stu-id="037a2-629">The file will be read and executed after a batch terminator is encountered.</span></span> <span data-ttu-id="037a2-630">Можно указывать несколько команд **:r** .</span><span class="sxs-lookup"><span data-stu-id="037a2-630">You can issue multiple **:r** commands.</span></span> <span data-ttu-id="037a2-631">В файле могут содержаться любые команды программы `sqlcmd`,</span><span class="sxs-lookup"><span data-stu-id="037a2-631">The file may include any `sqlcmd` command.</span></span> <span data-ttu-id="037a2-632">в том числе признак конца пакета **GO**.</span><span class="sxs-lookup"><span data-stu-id="037a2-632">This includes the batch terminator **GO**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="037a2-633">Число строк, отображаемых в интерактивном режиме, для каждой найденной команды **:r** будет увеличено на 1.</span><span class="sxs-lookup"><span data-stu-id="037a2-633">The line count that is displayed in interactive mode will be increased by one for every **:r** command encountered.</span></span> <span data-ttu-id="037a2-634">Команда **:r** отображается в выводе команды list.</span><span class="sxs-lookup"><span data-stu-id="037a2-634">The **:r** command will appear in the output of the list command.</span></span>  
  
 <span data-ttu-id="037a2-635">**:Serverlist**</span><span class="sxs-lookup"><span data-stu-id="037a2-635">**:Serverlist**</span></span>  
 <span data-ttu-id="037a2-636">Выводит список локально настроенных серверов и имена серверов, осуществляющих трансляцию данных в сети.</span><span class="sxs-lookup"><span data-stu-id="037a2-636">Lists the locally configured servers and the names of the servers broadcasting on the network.</span></span>  
  
 <span data-ttu-id="037a2-637">**: Connect** _server_name_[ **\\** _instance_name_] [-l *timeout*] [-U *user_name* [-P *пароль*]]</span><span class="sxs-lookup"><span data-stu-id="037a2-637">**:Connect** _server_name_[**\\**_instance_name_] [-l *timeout*] [-U *user_name* [-P *password*]]</span></span>  
 <span data-ttu-id="037a2-638">Соединяется с экземпляром [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="037a2-638">Connects to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="037a2-639">Также закрывает текущее соединение.</span><span class="sxs-lookup"><span data-stu-id="037a2-639">Also closes the current connection.</span></span>  
  
 <span data-ttu-id="037a2-640">Параметры времени ожидания:</span><span class="sxs-lookup"><span data-stu-id="037a2-640">Time-out options:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="037a2-641">0</span><span class="sxs-lookup"><span data-stu-id="037a2-641">0</span></span>|<span data-ttu-id="037a2-642">ждать бесконечно</span><span class="sxs-lookup"><span data-stu-id="037a2-642">wait forever</span></span>|  
|<span data-ttu-id="037a2-643">n>0</span><span class="sxs-lookup"><span data-stu-id="037a2-643">n>0</span></span>|<span data-ttu-id="037a2-644">ждать в течение n секунд</span><span class="sxs-lookup"><span data-stu-id="037a2-644">wait for n seconds</span></span>|  
  
 <span data-ttu-id="037a2-645">Переменная скрипта SQLCMDSERVER отображает текущее активное соединение.</span><span class="sxs-lookup"><span data-stu-id="037a2-645">The SQLCMDSERVER scripting variable will reflect the current active connection.</span></span>  
  
 <span data-ttu-id="037a2-646">Если не указан параметр *timeout* , то берется значение переменной SQLCMDLOGINTIMEOUT по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="037a2-646">If *timeout* is not specified, the value of the SQLCMDLOGINTIMEOUT variable is the default.</span></span>  
  
 <span data-ttu-id="037a2-647">Если указано только *имя_пользователя* (в виде параметра или в виде переменной среды), у пользователя будет запрошен пароль.</span><span class="sxs-lookup"><span data-stu-id="037a2-647">If only *user_name* is specified (either as an option, or as an environment variable), the user will be prompted to enter a password.</span></span> <span data-ttu-id="037a2-648">Однако этого не произойдет, если установлены переменные среды SQLCMDUSER или SQLCMDPASSWORD.</span><span class="sxs-lookup"><span data-stu-id="037a2-648">This is not true if the SQLCMDUSER or SQLCMDPASSWORD environment variables have been set.</span></span> <span data-ttu-id="037a2-649">Если ни параметры, ни переменные среды не введены, то для входа используется режим проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="037a2-649">If neither options nor environment variables are provided, Windows Authentication mode is used to login.</span></span> <span data-ttu-id="037a2-650">Например, для подключения к экземпляру `instance1`сервера [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]с именем `myserver`с использованием встроенной безопасности следует ввести следующую команду:</span><span class="sxs-lookup"><span data-stu-id="037a2-650">For example to connect to an instance, `instance1`, of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], `myserver`, by using integrated security you would use the following:</span></span>  
  
 `:connect myserver\instance1`  
  
 <span data-ttu-id="037a2-651">Для подключения к экземпляру `myserver` по умолчанию с использованием переменных скрипта следует ввести следующее выражение:</span><span class="sxs-lookup"><span data-stu-id="037a2-651">To connect to the default instance of `myserver` using scripting variables, you would use the following:</span></span>  
  
 `:setvar myusername test`  
  
 `:setvar myservername myserver`  
  
 `:connect $(myservername) $(myusername)`  
  
 <span data-ttu-id="037a2-652">[**:**] **!!**\< *command*></span><span class="sxs-lookup"><span data-stu-id="037a2-652">[**:**] **!!**\< *command*></span></span>  
 <span data-ttu-id="037a2-653">Исполнение команд операционной системы.</span><span class="sxs-lookup"><span data-stu-id="037a2-653">Executes operating system commands.</span></span> <span data-ttu-id="037a2-654">Чтобы выполнить команду операционной системы, начните строку с двух восклицательных знаков ( **!!** ) и далее укажите команду операционной системы.</span><span class="sxs-lookup"><span data-stu-id="037a2-654">To execute an operating system command, start a line with two exclamation marks (**!!**) followed by the operating system command.</span></span> <span data-ttu-id="037a2-655">Пример:</span><span class="sxs-lookup"><span data-stu-id="037a2-655">For example:</span></span>  
  
 `:!! Dir`  
  
> [!NOTE]  
>  <span data-ttu-id="037a2-656">Команда выполняется на компьютере, где работает программа `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="037a2-656">The command is executed on the computer on which `sqlcmd` is running.</span></span>  
  
 <span data-ttu-id="037a2-657">**:XML** [**ON** | **OFF**]</span><span class="sxs-lookup"><span data-stu-id="037a2-657">**:XML** [**ON** | **OFF**]</span></span>  
 <span data-ttu-id="037a2-658">Дополнительные сведения см. в подразделе «Формат выходных XML-данных» далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="037a2-658">For more information, see "XML Output Format," later in this topic</span></span>  
  
 <span data-ttu-id="037a2-659">**:Help**</span><span class="sxs-lookup"><span data-stu-id="037a2-659">**:Help**</span></span>  
 <span data-ttu-id="037a2-660">Выводит список команд программы `sqlcmd` вместе с кратким описанием каждой из них.</span><span class="sxs-lookup"><span data-stu-id="037a2-660">Lists `sqlcmd` commands together with a short description of each command.</span></span>  
  
### <a name="sqlcmd-file-names"></a><span data-ttu-id="037a2-661">Имена файлов sqlcmd</span><span class="sxs-lookup"><span data-stu-id="037a2-661">sqlcmd File Names</span></span>  
 <span data-ttu-id="037a2-662">`sqlcmd`входные файлы можно указать с помощью параметра **-i** или команды **: r** .</span><span class="sxs-lookup"><span data-stu-id="037a2-662">`sqlcmd` input files can be specified with the **-i** option or the **:r** command.</span></span> <span data-ttu-id="037a2-663">Выходные файлы можно указать параметром **-o** или командами **:Error**, **:Out** и **:Perftrace** .</span><span class="sxs-lookup"><span data-stu-id="037a2-663">Output files can be specified with the **-o** option or the **:Error**, **:Out** and **:Perftrace** commands.</span></span> <span data-ttu-id="037a2-664">При работе с этими файлами следует придерживаться следующих правил.</span><span class="sxs-lookup"><span data-stu-id="037a2-664">The following are some guidelines for working with these files:</span></span>  
  
-   <span data-ttu-id="037a2-665">**: Error**, **: out** и **:P ерфтраце** должны использовать отдельные **<*`filename`*>** .</span><span class="sxs-lookup"><span data-stu-id="037a2-665">**:Error**, **:Out** and **:Perftrace** should use separate **<*`filename`*>**.</span></span> <span data-ttu-id="037a2-666">Если используется то же значение **<*`filename`*>** , входные данные команд могут быть смешанными.</span><span class="sxs-lookup"><span data-stu-id="037a2-666">If the same **<*`filename`*>** is used, inputs from the commands may be intermixed.</span></span>  
  
-   <span data-ttu-id="037a2-667">Если входной файл, вызываемый из программы `sqlcmd` на локальном компьютере, расположен на удаленном сервере и путь к этому файлу содержит букву диска (например, «:out c:\OutputFile.txt»),</span><span class="sxs-lookup"><span data-stu-id="037a2-667">If an input file that is located on a remote server is called from `sqlcmd` on a local computer and the file contains a drive file path such as :out c:\OutputFile.txt.</span></span> <span data-ttu-id="037a2-668">то выходной файл будет создан на локальном компьютере, а не на удаленном сервере.</span><span class="sxs-lookup"><span data-stu-id="037a2-668">The output file will be created on the local computer and not on the remote server.</span></span>  
  
-   <span data-ttu-id="037a2-669">К допустимым путям файлов относятся: C: \\ **<*`filename`*>** , \\ \\<Server \> \\<Share $>\\ **<*`filename`*>** и "c: \ Folder \\ **<*`file name`*>** ".</span><span class="sxs-lookup"><span data-stu-id="037a2-669">Valid file paths include: C:\\**<*`filename`*>**, \\\\<Server\>\\<Share$>\\**<*`filename`*>** and "C:\Some Folder\\**<*`file name`*>**".</span></span> <span data-ttu-id="037a2-670">Если путь содержит пробелы, его необходимо заключить в кавычки.</span><span class="sxs-lookup"><span data-stu-id="037a2-670">If there is a space in the path, use quotation marks.</span></span>  
  
-   <span data-ttu-id="037a2-671">Каждый новый сеанс работы программы `sqlcmd` перезаписывает существующие файлы с теми же именами.</span><span class="sxs-lookup"><span data-stu-id="037a2-671">Each new `sqlcmd` session will overwrite existing files that have the same names.</span></span>  
  
### <a name="informational-messages"></a><span data-ttu-id="037a2-672">Информационные сообщения</span><span class="sxs-lookup"><span data-stu-id="037a2-672">Informational Messages</span></span>  
 <span data-ttu-id="037a2-673">Программа `sqlcmd` выводит все информационные сообщения, отправляемые сервером.</span><span class="sxs-lookup"><span data-stu-id="037a2-673">`sqlcmd` prints any informational message that are sent by the server.</span></span> <span data-ttu-id="037a2-674">В следующем примере после выполнения инструкций [!INCLUDE[tsql](../includes/tsql-md.md)] выводится информационное сообщение.</span><span class="sxs-lookup"><span data-stu-id="037a2-674">In the following example, after the [!INCLUDE[tsql](../includes/tsql-md.md)] statements are executed, an informational message is printed.</span></span>  
  
 <span data-ttu-id="037a2-675">В командной строке введите следующее.</span><span class="sxs-lookup"><span data-stu-id="037a2-675">At the command prompt, type the following:</span></span>  
  
 `sqlcmd`  
  
 `At the sqlcmd prompt type:`  
  
 `USE AdventureWorks2012;`  
  
 `GO`  
  
 <span data-ttu-id="037a2-676">При нажатии клавиши ВВОД выводится следующее информационное сообщение: Контекст базы данных изменен на AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="037a2-676">When you press ENTER, the following informational message is printed: "Changed database context to 'AdventureWorks2012'."</span></span>  
  
### <a name="output-format-from-transact-sql-queries"></a><span data-ttu-id="037a2-677">Формат вывода результатов выполнения запросов Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="037a2-677">Output Format from Transact-SQL Queries</span></span>  
 <span data-ttu-id="037a2-678">Вначале программа `sqlcmd` выводит заголовок, содержащий имена столбцов, перечисленных в списке выборки,</span><span class="sxs-lookup"><span data-stu-id="037a2-678">`sqlcmd` first prints a column header that contains the column names specified in the select list.</span></span> <span data-ttu-id="037a2-679">которые разделяются символом, определенным в переменной SQLCMDCOLSEP.</span><span class="sxs-lookup"><span data-stu-id="037a2-679">The column names are separated by using the SQLCMDCOLSEP character.</span></span> <span data-ttu-id="037a2-680">По умолчанию это пробел.</span><span class="sxs-lookup"><span data-stu-id="037a2-680">By default, this is a space.</span></span> <span data-ttu-id="037a2-681">Если имя столбца короче, чем ширина столбца, выходные данные дополняются пробелами до начала следующего столбца.</span><span class="sxs-lookup"><span data-stu-id="037a2-681">If the column name is shorter than the column width, the output is padded with spaces up to the next column.</span></span>  
  
 <span data-ttu-id="037a2-682">За этой строкой выводится строка-разделитель, которая представляет собой последовательность дефисов.</span><span class="sxs-lookup"><span data-stu-id="037a2-682">This line will be followed by a separator line that is a series of dash characters.</span></span> <span data-ttu-id="037a2-683">Далее представлен пример вывода.</span><span class="sxs-lookup"><span data-stu-id="037a2-683">The following output shows an example.</span></span>  
  
 <span data-ttu-id="037a2-684">Запустите среду `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="037a2-684">Start `sqlcmd`.</span></span> <span data-ttu-id="037a2-685">Введите в командной строке: `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="037a2-685">At the `sqlcmd` command prompt, type the following:</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `SELECT TOP (2) BusinessEntityID, FirstName, LastName`  
  
 `FROM Person.Person;`  
  
 `GO`  
  
 <span data-ttu-id="037a2-686">После нажатия клавиши ВВОД отобразится следующий результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="037a2-686">When you press ENTER, the following result set is returned.</span></span>  
  
 `BusinessEntityID FirstName    LastName`  
  
 `---------------- ------------ ----------`  
  
 `285              Syed         Abbas`  
  
 `293              Catherine    Abel`  
  
 `(2 row(s) affected)`  
  
 <span data-ttu-id="037a2-687">Хотя столбец `BusinessEntityID` имеет ширину 4 символа, она была увеличена, чтобы вместить более длинное имя столбца.</span><span class="sxs-lookup"><span data-stu-id="037a2-687">Although the `BusinessEntityID` column is only 4 characters wide, it has been expanded to accommodate the longer column name.</span></span> <span data-ttu-id="037a2-688">По умолчанию вывод заканчивается на 80 символе.</span><span class="sxs-lookup"><span data-stu-id="037a2-688">By default, output is terminated at 80 characters.</span></span> <span data-ttu-id="037a2-689">Это можно изменить с помощью параметра **-w** , либо задав переменную скрипта SQLCMDCOLWIDTH.</span><span class="sxs-lookup"><span data-stu-id="037a2-689">This can be changed by using the **-w** option, or by setting the SQLCMDCOLWIDTH scripting variable.</span></span>  
  
### <a name="xml-output-format"></a><span data-ttu-id="037a2-690">Формат вывода XML</span><span class="sxs-lookup"><span data-stu-id="037a2-690">XML Output Format</span></span>  
 <span data-ttu-id="037a2-691">Выходные XML-данные, получаемые в результате выполнения предложения FOR XML, выводятся непрерывным потоком в неформатированном виде.</span><span class="sxs-lookup"><span data-stu-id="037a2-691">XML output that is the result of a FOR XML clause is output, unformatted, in a continuous stream.</span></span>  
  
 <span data-ttu-id="037a2-692">Если вы ожидаете вывод XML-данных, воспользуйтесь следующей командой: `:XML ON`.</span><span class="sxs-lookup"><span data-stu-id="037a2-692">When you expect XML output, use the following command: `:XML ON`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="037a2-693">Программа `sqlcmd` выводит сообщения об ошибках в обычном формате.</span><span class="sxs-lookup"><span data-stu-id="037a2-693">`sqlcmd` returns error messages in the usual format.</span></span> <span data-ttu-id="037a2-694">Обратите внимание, что сообщения об ошибках также выводятся в текстовый поток в формате XML.</span><span class="sxs-lookup"><span data-stu-id="037a2-694">Notice that the error messages are also output in the XML text stream in XML format.</span></span> <span data-ttu-id="037a2-695">Если указать параметр `:XML ON`, программа `sqlcmd` не выводит информационные сообщения.</span><span class="sxs-lookup"><span data-stu-id="037a2-695">By using `:XML ON`, `sqlcmd` does not display informational messages.</span></span>  
  
 <span data-ttu-id="037a2-696">Чтобы отключить режим XML, введите следующую команду: `:XML OFF`.</span><span class="sxs-lookup"><span data-stu-id="037a2-696">To set the XML mode off, use the following command: `:XML OFF`.</span></span>  
  
 <span data-ttu-id="037a2-697">Команда GO не должна указываться раньше команды XML OFF, поскольку последняя возвращает `sqlcmd` в режим вывода с построчным форматированием.</span><span class="sxs-lookup"><span data-stu-id="037a2-697">The GO command should not appear before the XML OFF command is issued because the XML OFF command switches `sqlcmd` back to row-oriented output.</span></span>  
  
 <span data-ttu-id="037a2-698">Не допускается смешивать XML-данные (потоковые) и данные набора строк.</span><span class="sxs-lookup"><span data-stu-id="037a2-698">XML (streamed) data and rowset data cannot be mixed.</span></span> <span data-ttu-id="037a2-699">Если перед выполнением инструкции [!INCLUDE[tsql](../includes/tsql-md.md)] , которая выводит потоки XML-данных, не была введена команда XML ON, то вывод будет искажен.</span><span class="sxs-lookup"><span data-stu-id="037a2-699">If the XML ON command has not been issued before a [!INCLUDE[tsql](../includes/tsql-md.md)] statement that outputs XML streams is executed, the output will be garbled.</span></span> <span data-ttu-id="037a2-700">Если была выполнена команда XML ON, то нельзя выполнить инструкции [!INCLUDE[tsql](../includes/tsql-md.md)] , которые выводят обычные наборы строк.</span><span class="sxs-lookup"><span data-stu-id="037a2-700">If the XML ON command has been issued, you cannot execute [!INCLUDE[tsql](../includes/tsql-md.md)] statements that output regular row sets.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="037a2-701">Команда **:XML** не поддерживает инструкцию SET STATISTICS XML.</span><span class="sxs-lookup"><span data-stu-id="037a2-701">The **:XML** command does not support the SET STATISTICS XML statement.</span></span>  
  
## <a name="sqlcmd-best-practices"></a><span data-ttu-id="037a2-702">Рекомендации по использованию sqlcmd</span><span class="sxs-lookup"><span data-stu-id="037a2-702">sqlcmd Best Practices</span></span>  
 <span data-ttu-id="037a2-703">Чтобы добиться максимальной безопасности и эффективности, придерживайтесь следующих правил.</span><span class="sxs-lookup"><span data-stu-id="037a2-703">Use the following practices to help maximize security and efficiency.</span></span>  
  
-   <span data-ttu-id="037a2-704">Используйте встроенную безопасность.</span><span class="sxs-lookup"><span data-stu-id="037a2-704">Use integrated security.</span></span>  
  
-   <span data-ttu-id="037a2-705">В автоматических средах указывайте параметр `-X`.</span><span class="sxs-lookup"><span data-stu-id="037a2-705">Use `-X` in automated environments.</span></span>  
  
-   <span data-ttu-id="037a2-706">Обеспечьте защиту входных и выходных файлов при помощи соответствующих разрешений файловой системы NTFS.</span><span class="sxs-lookup"><span data-stu-id="037a2-706">Secure input and output files by using appropriate NTFS file system permissions.</span></span>  
  
-   <span data-ttu-id="037a2-707">В целях повышения производительности выполняйте как можно больше работы в одном сеансе программы `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="037a2-707">To increase performance, do as much in one `sqlcmd` session as you can, instead of in a series of sessions.</span></span>  
  
-   <span data-ttu-id="037a2-708">Задайте значение времени ожидания для выполнения пакетов или запросов выше, чем ожидаемое время их выполнения.</span><span class="sxs-lookup"><span data-stu-id="037a2-708">Set time-out values for batch or query execution higher than you expect it will take to execute the batch or query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="037a2-709">См. также:</span><span class="sxs-lookup"><span data-stu-id="037a2-709">See Also</span></span>  
 <span data-ttu-id="037a2-710">[Запуск программы sqlcmd](../relational-databases/scripting/sqlcmd-start-the-utility.md) </span><span class="sxs-lookup"><span data-stu-id="037a2-710">[Start the sqlcmd Utility](../relational-databases/scripting/sqlcmd-start-the-utility.md) </span></span>  
 <span data-ttu-id="037a2-711">[Выполнение файлов скрипта Transact-SQL с использованием программы sqlcmd](../relational-databases/scripting/sqlcmd-run-transact-sql-script-files.md) </span><span class="sxs-lookup"><span data-stu-id="037a2-711">[Run Transact-SQL Script Files Using sqlcmd](../relational-databases/scripting/sqlcmd-run-transact-sql-script-files.md) </span></span>  
 <span data-ttu-id="037a2-712">[Использование программы sqlcmd](../relational-databases/scripting/sqlcmd-use-the-utility.md) </span><span class="sxs-lookup"><span data-stu-id="037a2-712">[Use the sqlcmd Utility](../relational-databases/scripting/sqlcmd-use-the-utility.md) </span></span>  
 <span data-ttu-id="037a2-713">[Использование программы sqlcmd с переменными скрипта](../relational-databases/scripting/sqlcmd-use-with-scripting-variables.md) </span><span class="sxs-lookup"><span data-stu-id="037a2-713">[Use sqlcmd with Scripting Variables](../relational-databases/scripting/sqlcmd-use-with-scripting-variables.md) </span></span>  
 <span data-ttu-id="037a2-714">[Подключение к компоненту Database Engine при помощи программы sqlcmd](../relational-databases/scripting/sqlcmd-connect-to-the-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="037a2-714">[Connect to the Database Engine With sqlcmd](../relational-databases/scripting/sqlcmd-connect-to-the-database-engine.md) </span></span>  
 <span data-ttu-id="037a2-715">[Изменение скриптов SQLCMD при помощи редактора запросов](../relational-databases/scripting/edit-sqlcmd-scripts-with-query-editor.md) </span><span class="sxs-lookup"><span data-stu-id="037a2-715">[Edit SQLCMD Scripts with Query Editor](../relational-databases/scripting/edit-sqlcmd-scripts-with-query-editor.md) </span></span>  
 <span data-ttu-id="037a2-716">[Управление шагами задания](../ssms/agent/manage-job-steps.md) </span><span class="sxs-lookup"><span data-stu-id="037a2-716">[Manage Job Steps](../ssms/agent/manage-job-steps.md) </span></span>  
 [<span data-ttu-id="037a2-717">Create a CmdExec Job Step</span><span class="sxs-lookup"><span data-stu-id="037a2-717">Create a CmdExec Job Step</span></span>](../ssms/agent/create-a-cmdexec-job-step.md)  
  
  
