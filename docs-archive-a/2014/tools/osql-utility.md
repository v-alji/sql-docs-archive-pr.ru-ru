---
title: Программа osql | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- statements [SQL Server], command prompt
- QUIT command
- Transact-SQL statements, command prompt
- EXIT command
- operating systems [SQL Server], commands
- osql utility [SQL Server]
- stored procedures [SQL Server], command prompt
- scripts [SQL Server], command prompt
- RESET command
- GO command
- command prompt utilities [SQL Server], osql
- CTRL+C command
ms.assetid: cf530d9e-0609-4528-8975-ab8e08e40b9a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 95782afe0de8567781316e3478d04a090f968ed5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727617"
---
# <a name="osql-utility"></a><span data-ttu-id="8e205-102">Программа osql</span><span class="sxs-lookup"><span data-stu-id="8e205-102">osql Utility</span></span>
  <span data-ttu-id="8e205-103">Программа **osql** позволяет вводить инструкции [!INCLUDE[tsql](../includes/tsql-md.md)] , системные процедуры и файлы скриптов.</span><span class="sxs-lookup"><span data-stu-id="8e205-103">The **osql** utility allows you to enter [!INCLUDE[tsql](../includes/tsql-md.md)] statements, system procedures, and script files.</span></span> <span data-ttu-id="8e205-104">Для связи с сервером эта программа использует ODBC.</span><span class="sxs-lookup"><span data-stu-id="8e205-104">This utility uses ODBC to communicate with the server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8e205-105">Эта функция будет исключена из будущей версии [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e205-105">This feature will be removed in a future version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8e205-106">Не используйте эту функцию в новых разработках и планируйте изменение приложений, которые используют ее в данный момент.</span><span class="sxs-lookup"><span data-stu-id="8e205-106">Avoid using this feature in new development work, and plan to modify applications that currently use the feature.</span></span> <span data-ttu-id="8e205-107">Вместо этого используйте **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="8e205-107">Use **sqlcmd** instead.</span></span> <span data-ttu-id="8e205-108">Дополнительные сведения см. в статье [sqlcmd Utility](sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="8e205-108">For more information, see [sqlcmd Utility](sqlcmd-utility.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e205-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8e205-109">Syntax</span></span>  
  
```  
  
      osql  
[-?] |  
[-L] |  
[  
  {  
     {-Ulogin_id [-Ppassword]} | -E }  
     [-Sserver_name[\instance_name]] [-Hwksta_name] [-ddb_name]  
     [-ltime_out] [-ttime_out] [-hheaders]  
     [-scol_separator] [-wcolumn_width] [-apacket_size]  
     [-e] [-I] [-D data_source_name]  
     [-ccmd_end] [-q "query"] [-Q"query"]  
     [-n] [-merror_level] [-r {0 | 1}]  
     [-iinput_file] [-ooutput_file] [-p]  
     [-b] [-u] [-R] [-O]  
]  
```  
  
## <a name="arguments"></a><span data-ttu-id="8e205-110">Аргументы</span><span class="sxs-lookup"><span data-stu-id="8e205-110">Arguments</span></span>  
 <span data-ttu-id="8e205-111">**-?**</span><span class="sxs-lookup"><span data-stu-id="8e205-111">**-?**</span></span>  
 <span data-ttu-id="8e205-112">Отображает сводку по синтаксису параметров программы **osql** .</span><span class="sxs-lookup"><span data-stu-id="8e205-112">Displays the syntax summary of **osql** switches.</span></span>  
  
 <span data-ttu-id="8e205-113">**-L**</span><span class="sxs-lookup"><span data-stu-id="8e205-113">**-L**</span></span>  
 <span data-ttu-id="8e205-114">Выводит список локально настроенных серверов и имена серверов, осуществляющих трансляцию данных в сети.</span><span class="sxs-lookup"><span data-stu-id="8e205-114">Lists the locally configured servers and the names of the servers broadcasting on the network.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8e205-115">Из-за особенностей широковещательной передачи в сетях программа **osql** может не получить своевременный ответ от всех серверов.</span><span class="sxs-lookup"><span data-stu-id="8e205-115">Due to the nature of broadcasting on networks, **osql** may not receive a timely response from all servers.</span></span> <span data-ttu-id="8e205-116">Поэтому возвращаемый список серверов может меняться при каждом вызове этого параметра.</span><span class="sxs-lookup"><span data-stu-id="8e205-116">Therefore the list of servers returned may vary for each invocation of this option.</span></span>  
  
 <span data-ttu-id="8e205-117">**-U** _идентификатор_для_входа_</span><span class="sxs-lookup"><span data-stu-id="8e205-117">**-U** _login_id_</span></span>  
 <span data-ttu-id="8e205-118">Идентификатор входа пользователя.</span><span class="sxs-lookup"><span data-stu-id="8e205-118">Is the user login ID.</span></span> <span data-ttu-id="8e205-119">Идентификаторы входа зависят от регистра.</span><span class="sxs-lookup"><span data-stu-id="8e205-119">Login IDs are case-sensitive.</span></span>  
  
 <span data-ttu-id="8e205-120">**-P** _пароль_</span><span class="sxs-lookup"><span data-stu-id="8e205-120">**-P** _password_</span></span>  
 <span data-ttu-id="8e205-121">Пароль, задаваемый пользователем.</span><span class="sxs-lookup"><span data-stu-id="8e205-121">Is a user-specified password.</span></span> <span data-ttu-id="8e205-122">Если параметр **-P** не указан, программа **osql** запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="8e205-122">If the **-P** option is not used, **osql** prompts for a password.</span></span> <span data-ttu-id="8e205-123">Если параметр **-P** указывается в конце командной строки без указания пароля, то программа **osql** использует пароль по умолчанию (NULL).</span><span class="sxs-lookup"><span data-stu-id="8e205-123">If the **-P** option is used at the end of the command prompt without any password, **osql** uses the default password (NULL).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8e205-124">Не используйте пустые пароли.</span><span class="sxs-lookup"><span data-stu-id="8e205-124">Do not use a blank password.</span></span> <span data-ttu-id="8e205-125">Выбирайте надежные пароли.</span><span class="sxs-lookup"><span data-stu-id="8e205-125">Use a strong password.</span></span> <span data-ttu-id="8e205-126">Дополнительные сведения см. в разделе [Strong Passwords](../relational-databases/security/strong-passwords.md).</span><span class="sxs-lookup"><span data-stu-id="8e205-126">For more information, see [Strong Passwords](../relational-databases/security/strong-passwords.md).</span></span>  
  
 <span data-ttu-id="8e205-127">В паролях учитывается регистр символов.</span><span class="sxs-lookup"><span data-stu-id="8e205-127">Passwords are case-sensitive.</span></span>  
  
 <span data-ttu-id="8e205-128">Переменная среды OSQLPASSWORD позволяет установить значение пароля по умолчанию для текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="8e205-128">The OSQLPASSWORD environment variable allows you to set a default password for the current session.</span></span> <span data-ttu-id="8e205-129">Поэтому нет необходимости вписывать пароль в пакетные файлы.</span><span class="sxs-lookup"><span data-stu-id="8e205-129">Therefore, you do not have to hard code a password into batch files.</span></span>  
  
 <span data-ttu-id="8e205-130">Если пароль не указан с помощью параметра **-P** , программа **osql** сначала проверяет переменную OSQLPASSWORD.</span><span class="sxs-lookup"><span data-stu-id="8e205-130">If you do not specify a password with the **-P** option, **osql** first checks for the OSQLPASSWORD variable.</span></span> <span data-ttu-id="8e205-131">Если значение переменной не задано, программа **osql** использует пароль по умолчанию (NULL).</span><span class="sxs-lookup"><span data-stu-id="8e205-131">If no value is set, **osql** uses the default password, NULL.</span></span> <span data-ttu-id="8e205-132">В следующем примере задается значение переменной OSQLPASSWORD в командной строке, а затем запускается программа **osql** :</span><span class="sxs-lookup"><span data-stu-id="8e205-132">The following example sets the OSQLPASSWORD variable at a command prompt and then accesses the **osql** utility:</span></span>  
  
```  
C:\>SET OSQLPASSWORD=abracadabra  
C:\>osql   
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8e205-133">Чтобы скрыть пароль, не указывайте параметр **-P** вместе с параметром **-U** .</span><span class="sxs-lookup"><span data-stu-id="8e205-133">To mask your password, do not specify the **-P** option along with the **-U** option.</span></span> <span data-ttu-id="8e205-134">Вместо этого после ввода команды **osql** с параметром **-U** и другими параметрами (не задавайте **-P**) нажмите клавишу ВВОД, и программа **osql** предложит ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="8e205-134">Instead, after specifying **osql** along with the **-U** option and other switches (do not specify **-P**), press ENTER, and **osql** will prompt you for a password.</span></span> <span data-ttu-id="8e205-135">Этот метод обеспечивает скрытие пароля при вводе.</span><span class="sxs-lookup"><span data-stu-id="8e205-135">This method ensures that your password will be masked when it is entered.</span></span>  
  
 <span data-ttu-id="8e205-136">**-E**</span><span class="sxs-lookup"><span data-stu-id="8e205-136">**-E**</span></span>  
 <span data-ttu-id="8e205-137">Использует доверительное соединение вместо запроса пароля.</span><span class="sxs-lookup"><span data-stu-id="8e205-137">Uses a trusted connection instead of requesting a password.</span></span>  
  
 <span data-ttu-id="8e205-138">**-S** _server_name_[ **\\** _instance_name_]</span><span class="sxs-lookup"><span data-stu-id="8e205-138">**-S** _server_name_[ **\\**_instance_name_]</span></span>  
 <span data-ttu-id="8e205-139">Указывает экземпляр [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] для подключения.</span><span class="sxs-lookup"><span data-stu-id="8e205-139">Specifies the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to connect to.</span></span> <span data-ttu-id="8e205-140">Укажите значение *имя_сервера* , чтобы подключиться к экземпляру компонента [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] по умолчанию на этом сервере.</span><span class="sxs-lookup"><span data-stu-id="8e205-140">Specify *server_name* to connect to the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on that server.</span></span> <span data-ttu-id="8e205-141">Укажите _server_name_ **\\** _instance_name_ для подключения к именованному экземпляру [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] служб на этом сервере.</span><span class="sxs-lookup"><span data-stu-id="8e205-141">Specify _server_name_**\\**_instance_name_ to connect to a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on that server.</span></span> <span data-ttu-id="8e205-142">Если сервер не указан, программа **osql** устанавливает подключение к используемому по умолчанию экземпляру [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8e205-142">If no server is specified, **osql** connects to the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on the local computer.</span></span> <span data-ttu-id="8e205-143">Этот параметр необходим при выполнении программы **osql** с удаленного компьютера в сети.</span><span class="sxs-lookup"><span data-stu-id="8e205-143">This option is required when executing **osql** from a remote computer on the network.</span></span>  
  
 <span data-ttu-id="8e205-144">**-H** _имя_wksta_</span><span class="sxs-lookup"><span data-stu-id="8e205-144">**-H** _wksta_name_</span></span>  
 <span data-ttu-id="8e205-145">Имя рабочей станции.</span><span class="sxs-lookup"><span data-stu-id="8e205-145">Is a workstation name.</span></span> <span data-ttu-id="8e205-146">Имя рабочей станции хранится в **sysprocesses.hostname** и выводится процедурой **sp_who**.</span><span class="sxs-lookup"><span data-stu-id="8e205-146">The workstation name is stored in **sysprocesses.hostname** and is displayed by **sp_who**.</span></span> <span data-ttu-id="8e205-147">Если этот параметр не указан, используется текущее имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="8e205-147">If this option is not specified, the current computer name is assumed.</span></span>  
  
 <span data-ttu-id="8e205-148">**-d** _имя_базы данных_</span><span class="sxs-lookup"><span data-stu-id="8e205-148">**-d** _db_name_</span></span>  
 <span data-ttu-id="8e205-149">Выдает инструкцию USE *db_name* при запуске программы **osql**.</span><span class="sxs-lookup"><span data-stu-id="8e205-149">Issues a USE *db_name* statement when **osql**is started.</span></span>  
  
 <span data-ttu-id="8e205-150">**-l** _время_ожидания_</span><span class="sxs-lookup"><span data-stu-id="8e205-150">**-l** _time_out_</span></span>  
 <span data-ttu-id="8e205-151">Указывает время ожидания входа для программы **osql** (в секундах). По умолчанию время ожидания входа для программы **osql** составляет 8 секунд.</span><span class="sxs-lookup"><span data-stu-id="8e205-151">Specifies the number of seconds before an **osql** login times out. The default time-out for login to **osql** is eight seconds.</span></span>  
  
 <span data-ttu-id="8e205-152">**-t** _время_ожидания_</span><span class="sxs-lookup"><span data-stu-id="8e205-152">**-t** _time_out_</span></span>  
 <span data-ttu-id="8e205-153">Указывает время ожидания для выполнения команды (в секундах). Если значение *время_ожидания* не указано, команды имеют неограниченное время ожидания.</span><span class="sxs-lookup"><span data-stu-id="8e205-153">Specifies the number of seconds before a command times out. If a *time_out* value is not specified, commands do not time out.</span></span>  
  
 <span data-ttu-id="8e205-154">**-h** _заголовки_</span><span class="sxs-lookup"><span data-stu-id="8e205-154">**-h** _headers_</span></span>  
 <span data-ttu-id="8e205-155">Указывает количество строк для печати между заголовками столбцов.</span><span class="sxs-lookup"><span data-stu-id="8e205-155">Specifies the number of rows to print between column headings.</span></span> <span data-ttu-id="8e205-156">По умолчанию заголовки печатаются один раз для каждого набора результатов запроса.</span><span class="sxs-lookup"><span data-stu-id="8e205-156">The default is to print headings one time for each set of query results.</span></span> <span data-ttu-id="8e205-157">Чтобы не печатать заголовки, укажите значение -1.</span><span class="sxs-lookup"><span data-stu-id="8e205-157">Use -1 to specify that no headers will be printed.</span></span> <span data-ttu-id="8e205-158">При использовании значения -1 между параметром и значением не должно быть пробела ( **-h-1**, а не **-h -1**).</span><span class="sxs-lookup"><span data-stu-id="8e205-158">If -1 is used, there must be no space between the parameter and the setting (**-h-1**, not **-h -1**).</span></span>  
  
 <span data-ttu-id="8e205-159">**-s** _разделитель_столбцов_</span><span class="sxs-lookup"><span data-stu-id="8e205-159">**-s** _col_separator_</span></span>  
 <span data-ttu-id="8e205-160">Указывает символ-разделитель столбцов, по умолчанию — пробел.</span><span class="sxs-lookup"><span data-stu-id="8e205-160">Specifies the column-separator character, which is a blank space by default.</span></span> <span data-ttu-id="8e205-161">Чтобы использовать символы, имеющие специальное значение для операционной системы (например, |; & \< > ), заключите этот символ в двойные кавычки (").</span><span class="sxs-lookup"><span data-stu-id="8e205-161">To use characters that have special meaning to the operating system (for example, | ; & \< >), enclose the character in double quotation marks (").</span></span>  
  
 <span data-ttu-id="8e205-162">**-w** _ширина_столбца_</span><span class="sxs-lookup"><span data-stu-id="8e205-162">**-w** _column_width_</span></span>  
 <span data-ttu-id="8e205-163">Позволяет пользователю устанавливать ширину экрана для выводимых данных.</span><span class="sxs-lookup"><span data-stu-id="8e205-163">Allows the user to set the screen width for output.</span></span> <span data-ttu-id="8e205-164">Значение по умолчанию составляет 80 символов.</span><span class="sxs-lookup"><span data-stu-id="8e205-164">The default is 80 characters.</span></span> <span data-ttu-id="8e205-165">Когда строка вывода достигает максимальной ширины экрана, она разбивается на несколько строк.</span><span class="sxs-lookup"><span data-stu-id="8e205-165">When an output line has reached its maximum screen width, it is broken into multiple lines.</span></span>  
  
 <span data-ttu-id="8e205-166">**-a** _размер_пакета_</span><span class="sxs-lookup"><span data-stu-id="8e205-166">**-a** _packet_size_</span></span>  
 <span data-ttu-id="8e205-167">Позволяет запросить пакет нестандартного размера.</span><span class="sxs-lookup"><span data-stu-id="8e205-167">Allows you to request a different-sized packet.</span></span> <span data-ttu-id="8e205-168">Допустимые значения для *размер_пакета* лежат в диапазоне от 512 до 65 535.</span><span class="sxs-lookup"><span data-stu-id="8e205-168">The valid values for *packet_size* are 512 through 65535.</span></span> <span data-ttu-id="8e205-169">Значение по умолчанию **osql** — это параметр сервера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8e205-169">The default value **osql** is the server default.</span></span> <span data-ttu-id="8e205-170">Увеличенный размер пакета может увеличить производительность при выполнении большого скрипта со значительным количеством инструкций SQL между командами GO.</span><span class="sxs-lookup"><span data-stu-id="8e205-170">Increased packet size can enhance performance on larger script execution where the amount of SQL statements between GO commands is substantial.</span></span> [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="8e205-171">показывает, что при установке значения 8192 массовое копирование обычно происходит с максимальной скоростью.</span><span class="sxs-lookup"><span data-stu-id="8e205-171">testing indicates that 8192 is typically the fastest setting for bulk copy operations.</span></span> <span data-ttu-id="8e205-172">Можно запросить больший размер пакета, но программа **osql** использует значение сервера по умолчанию, если выполнить запрос невозможно.</span><span class="sxs-lookup"><span data-stu-id="8e205-172">A larger packet size can be requested, but **osql** defaults to the server default if the request cannot be granted.</span></span>  
  
 <span data-ttu-id="8e205-173">**-e**</span><span class="sxs-lookup"><span data-stu-id="8e205-173">**-e**</span></span>  
 <span data-ttu-id="8e205-174">Отображает вводимые данные на экране.</span><span class="sxs-lookup"><span data-stu-id="8e205-174">Echoes input.</span></span>  
  
 <span data-ttu-id="8e205-175">**-I**</span><span class="sxs-lookup"><span data-stu-id="8e205-175">**-I**</span></span>  
 <span data-ttu-id="8e205-176">Включает параметр соединения QUOTED_IDENTIFIER.</span><span class="sxs-lookup"><span data-stu-id="8e205-176">Sets the QUOTED_IDENTIFIER connection option on.</span></span>  
  
 <span data-ttu-id="8e205-177">**-D** _имя_источника_данных_</span><span class="sxs-lookup"><span data-stu-id="8e205-177">**-D** _data_source_name_</span></span>  
 <span data-ttu-id="8e205-178">Выполняет подключение к источнику данных ODBC, который определен с помощью драйвера ODBC для [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e205-178">Connects to an ODBC data source that is defined using the ODBC driver for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8e205-179">Подключение **osql** использует параметры, указанные в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="8e205-179">The **osql** connection uses the options specified in the data source.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8e205-180">Этот параметр не работает с источниками данных, определенными для других драйверов.</span><span class="sxs-lookup"><span data-stu-id="8e205-180">This option does not work with data sources defined for other drivers.</span></span>  
  
 <span data-ttu-id="8e205-181">**-c** _завершение_cmd_</span><span class="sxs-lookup"><span data-stu-id="8e205-181">**-c** _cmd_end_</span></span>  
 <span data-ttu-id="8e205-182">Указывает признак конца команды.</span><span class="sxs-lookup"><span data-stu-id="8e205-182">Specifies the command terminator.</span></span> <span data-ttu-id="8e205-183">По умолчанию команды заканчиваются и отправляются в [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] с помощью ввода GO в отдельной строке.</span><span class="sxs-lookup"><span data-stu-id="8e205-183">By default, commands are terminated and sent to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] by entering GO on a line by itself.</span></span> <span data-ttu-id="8e205-184">При сбросе признака конца команды не используйте зарезервированные слова [!INCLUDE[tsql](../includes/tsql-md.md)] или символы, которые имеют специальное значение для операционной системы независимо от того, указана ли перед ними обратная косая черта.</span><span class="sxs-lookup"><span data-stu-id="8e205-184">When you reset the command terminator, do not use [!INCLUDE[tsql](../includes/tsql-md.md)] reserved words or characters that have special meaning to the operating system, whether preceded by a backslash or not.</span></span>  
  
 <span data-ttu-id="8e205-185">**-q "** _запрос_ **"**</span><span class="sxs-lookup"><span data-stu-id="8e205-185">**-q "** _query_ **"**</span></span>  
 <span data-ttu-id="8e205-186">Выполняет запрос при запуске программы **osql** , но не закрывает программу **osql** по завершении запроса.</span><span class="sxs-lookup"><span data-stu-id="8e205-186">Executes a query when **osql** starts, but does not exit **osql** when the query completes.</span></span> <span data-ttu-id="8e205-187">(Обратите внимание, что инструкция запроса не должна содержать GO.)</span><span class="sxs-lookup"><span data-stu-id="8e205-187">(Note that the query statement should not include GO).</span></span> <span data-ttu-id="8e205-188">При выполнении запроса из пакетного файла используйте синтаксис %переменные или %переменные среды%.</span><span class="sxs-lookup"><span data-stu-id="8e205-188">If you issue a query from a batch file, use %variables, or environment %variables%.</span></span> <span data-ttu-id="8e205-189">Пример:</span><span class="sxs-lookup"><span data-stu-id="8e205-189">For example:</span></span>  
  
```  
SET table=sys.objects  
osql -E -q "select name, object_id from %table%"  
```  
  
 <span data-ttu-id="8e205-190">Используйте двойные кавычки для запроса и одинарные кавычки для выражений, внедренных в запрос.</span><span class="sxs-lookup"><span data-stu-id="8e205-190">Use double quotation marks around the query and single quotation marks around anything embedded in the query.</span></span>  
  
 <span data-ttu-id="8e205-191">**-Q"** _запрос_ **"**</span><span class="sxs-lookup"><span data-stu-id="8e205-191">**-Q"** _query_ **"**</span></span>  
 <span data-ttu-id="8e205-192">Выполняет запрос и сразу же закрывает программу **osql**.</span><span class="sxs-lookup"><span data-stu-id="8e205-192">Executes a query and immediately exits **osql**.</span></span> <span data-ttu-id="8e205-193">Используйте двойные кавычки для запроса и одинарные кавычки для выражений, внедренных в запрос.</span><span class="sxs-lookup"><span data-stu-id="8e205-193">Use double quotation marks around the query and single quotation marks around anything embedded in the query.</span></span>  
  
 <span data-ttu-id="8e205-194">**-n**</span><span class="sxs-lookup"><span data-stu-id="8e205-194">**-n**</span></span>  
 <span data-ttu-id="8e205-195">Удаляет нумерацию и символ приглашения (>) из строк ввода.</span><span class="sxs-lookup"><span data-stu-id="8e205-195">Removes numbering and the prompt symbol (>) from input lines.</span></span>  
  
 <span data-ttu-id="8e205-196">**-m** _уровень_ошибки_</span><span class="sxs-lookup"><span data-stu-id="8e205-196">**-m** _error_level_</span></span>  
 <span data-ttu-id="8e205-197">Настраивает отображение сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="8e205-197">Customizes the display of error messages.</span></span> <span data-ttu-id="8e205-198">Номер сообщения, состояние и уровень ошибки отображаются для ошибок указанного или более высокого уровня серьезности.</span><span class="sxs-lookup"><span data-stu-id="8e205-198">The message number, state, and error level are displayed for errors of the specified severity level or higher.</span></span> <span data-ttu-id="8e205-199">Сообщения для ошибок, у которых уровень серьезности меньше заданного, не отображаются.</span><span class="sxs-lookup"><span data-stu-id="8e205-199">Nothing is displayed for errors of levels lower than the specified level.</span></span> <span data-ttu-id="8e205-200">Используйте значение **-1** , чтобы указать, что все заголовки должны возвращаться с сообщениями, даже с информационными.</span><span class="sxs-lookup"><span data-stu-id="8e205-200">Use **-1** to specify that all headers are returned with messages, even informational messages.</span></span> <span data-ttu-id="8e205-201">При использовании значения **-1**между параметром и значением не должно быть пробела ( **-m-1**, а не **-m -1**).</span><span class="sxs-lookup"><span data-stu-id="8e205-201">If using **-1**, there must be no space between the parameter and the setting (**-m-1**, not **-m -1**).</span></span>  
  
 <span data-ttu-id="8e205-202">**-r** { **0**| **1**}</span><span class="sxs-lookup"><span data-stu-id="8e205-202">**-r** { **0**| **1**}</span></span>  
 <span data-ttu-id="8e205-203">Перенаправляет вывод сообщений на экран (**stderr**).</span><span class="sxs-lookup"><span data-stu-id="8e205-203">Redirects message output to the screen (**stderr**).</span></span> <span data-ttu-id="8e205-204">Если параметр не указан, или если указано значение **0**, происходит перенаправление только сообщений об ошибках с уровнем серьезности 11 и выше.</span><span class="sxs-lookup"><span data-stu-id="8e205-204">If you do not specify a parameter, or if you specify **0**, only error messages with a severity level 11 or higher are redirected.</span></span> <span data-ttu-id="8e205-205">Если указать значение **1**, то происходит перенаправление всех выводимых сообщений (включая сообщения для вывода на печать).</span><span class="sxs-lookup"><span data-stu-id="8e205-205">If you specify **1**, all message output (including "print") is redirected.</span></span>  
  
 <span data-ttu-id="8e205-206">**-i** _входной_файл_</span><span class="sxs-lookup"><span data-stu-id="8e205-206">**-i** _input_file_</span></span>  
 <span data-ttu-id="8e205-207">Указывает файл, содержащий пакет инструкций или хранимых процедур SQL.</span><span class="sxs-lookup"><span data-stu-id="8e205-207">Identifies the file that contains a batch of SQL statements or stored procedures.</span></span> <span data-ttu-id="8e205-208">Оператор сравнения "меньше" ( **\<** ) можно использовать вместо параметра **-i**.</span><span class="sxs-lookup"><span data-stu-id="8e205-208">The less than (**\<**) comparison operator can be used in place of **-i**.</span></span>  
  
 <span data-ttu-id="8e205-209">**-o** _выходной_файл_</span><span class="sxs-lookup"><span data-stu-id="8e205-209">**-o** _output_file_</span></span>  
 <span data-ttu-id="8e205-210">Указывает файл, в который поступают выходные данные программы **osql**.</span><span class="sxs-lookup"><span data-stu-id="8e205-210">Identifies the file that receives output from **osql**.</span></span> <span data-ttu-id="8e205-211">Оператор сравнения "больше" ( **>** ) можно использовать вместо параметра **-o**.</span><span class="sxs-lookup"><span data-stu-id="8e205-211">The greater than (**>**) comparison operator can be used in place of **-o**.</span></span>  
  
 <span data-ttu-id="8e205-212">Если *входной_файл* имеет формат, отличный от Юникода, а параметр **-u** не указан, то файл *выходной_файл* сохраняется в формате OEM.</span><span class="sxs-lookup"><span data-stu-id="8e205-212">If *input_file* is not Unicode and **-u** is not specified, *output_file* is stored in OEM format.</span></span> <span data-ttu-id="8e205-213">Если файл *входной_файл* имеет формат Юникода или параметр **-u** указан, то файл *выходной_файл* сохраняется в формате Юникод.</span><span class="sxs-lookup"><span data-stu-id="8e205-213">If *input_file* is Unicode or **-u** is specified, *output_file* is stored in Unicode format.</span></span>  
  
 <span data-ttu-id="8e205-214">**-p**</span><span class="sxs-lookup"><span data-stu-id="8e205-214">**-p**</span></span>  
 <span data-ttu-id="8e205-215">Выводит статистику производительности.</span><span class="sxs-lookup"><span data-stu-id="8e205-215">Prints performance statistics.</span></span>  
  
 <span data-ttu-id="8e205-216">**-b**</span><span class="sxs-lookup"><span data-stu-id="8e205-216">**-b**</span></span>  
 <span data-ttu-id="8e205-217">Указывает, что в случае ошибки программа **osql** завершает работу и возвращает значение DOS ERRORLEVEL.</span><span class="sxs-lookup"><span data-stu-id="8e205-217">Specifies that **osql** exits and returns a DOS ERRORLEVEL value when an error occurs.</span></span> <span data-ttu-id="8e205-218">Значение, возвращаемое в переменную DOS ERRORLEVEL, равно 1, если сообщение об ошибке [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] имеет степень серьезности выше 11. В противном случае возвращаемое значение равно 0.</span><span class="sxs-lookup"><span data-stu-id="8e205-218">The value returned to the DOS ERRORLEVEL variable is 1 when the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] error message has a severity of 11 or greater; otherwise, the value returned is 0.</span></span> [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="8e205-219">Пакетные файлы MS-DOS можно использовать для проверки значения DOS ERRORLEVEL и для обработки ошибки соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="8e205-219">MS-DOS batch files can test the value of DOS ERRORLEVEL and handle the error appropriately.</span></span>  
  
 <span data-ttu-id="8e205-220">**-u**</span><span class="sxs-lookup"><span data-stu-id="8e205-220">**-u**</span></span>  
 <span data-ttu-id="8e205-221">Указывает, что *выходной_файл* хранится в Юникоде независимо от формата файла *входной_файл*.</span><span class="sxs-lookup"><span data-stu-id="8e205-221">Specifies that *output_file* is stored in Unicode format, regardless of the format of the *input_file*.</span></span>  
  
 <span data-ttu-id="8e205-222">**-R**</span><span class="sxs-lookup"><span data-stu-id="8e205-222">**-R**</span></span>  
 <span data-ttu-id="8e205-223">Указывает, что драйвер ODBC [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] использует настройки клиента при преобразовании данных в денежном формате, формате даты и времени в символьные данные.</span><span class="sxs-lookup"><span data-stu-id="8e205-223">Specifies that the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ODBC driver use client settings when converting currency, date, and time data to character data.</span></span>  
  
 <span data-ttu-id="8e205-224">**-O**</span><span class="sxs-lookup"><span data-stu-id="8e205-224">**-O**</span></span>  
 <span data-ttu-id="8e205-225">Указывает, что определенные возможности программы **osql** будут отключены для совместимости с более ранними версиями программы **isql**.</span><span class="sxs-lookup"><span data-stu-id="8e205-225">Specifies that certain **osql** features be deactivated to match the behavior of earlier versions of **isql**.</span></span> <span data-ttu-id="8e205-226">Будут отключены следующие функции.</span><span class="sxs-lookup"><span data-stu-id="8e205-226">These features are deactivated:</span></span>  
  
-   <span data-ttu-id="8e205-227">Пакетная обработка окончания файла</span><span class="sxs-lookup"><span data-stu-id="8e205-227">EOF batch processing</span></span>  
  
-   <span data-ttu-id="8e205-228">Автоматическое масштабирование ширины консоли</span><span class="sxs-lookup"><span data-stu-id="8e205-228">Automatic console width scaling</span></span>  
  
-   <span data-ttu-id="8e205-229">Длинные сообщения</span><span class="sxs-lookup"><span data-stu-id="8e205-229">Wide messages</span></span>  
  
 <span data-ttu-id="8e205-230">Этот параметр также устанавливает значения ERRORLEVEL DOS по умолчанию, равное -1.</span><span class="sxs-lookup"><span data-stu-id="8e205-230">It also sets the default DOS ERRORLEVEL value to -1.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8e205-231">Программа **osql**больше не поддерживает параметры **-n** , **-O** и **-D**.</span><span class="sxs-lookup"><span data-stu-id="8e205-231">The **-n**, **-O** and **-D** options are no longer supported by **osql**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e205-232">Remarks</span><span class="sxs-lookup"><span data-stu-id="8e205-232">Remarks</span></span>  
 <span data-ttu-id="8e205-233">Программа **osql** запускается непосредственно из операционной системы с перечисленными ниже параметрами, в которых учитывается регистр символов.</span><span class="sxs-lookup"><span data-stu-id="8e205-233">The **osql** utility is started directly from the operating system with the case-sensitive options listed here.</span></span> <span data-ttu-id="8e205-234">После запуска программа **osql**принимает инструкции SQL и интерактивно передает их [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8e205-234">After **osql**starts, it accepts SQL statements and sends them to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] interactively.</span></span> <span data-ttu-id="8e205-235">Результаты форматируются и выводятся на экране (**stdout**).</span><span class="sxs-lookup"><span data-stu-id="8e205-235">The results are formatted and displayed on the screen (**stdout**).</span></span> <span data-ttu-id="8e205-236">Для выхода из программы **osql**используются команды QUIT или EXIT.</span><span class="sxs-lookup"><span data-stu-id="8e205-236">Use QUIT or EXIT to exit from **osql**.</span></span>  
  
 <span data-ttu-id="8e205-237">Если не указать имя пользователя при запуске программы **osql**, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] проверяет переменные среды и использует их, например **osqluser = ( *`user`* )** или **osqlserver = ( *`server`* )**.</span><span class="sxs-lookup"><span data-stu-id="8e205-237">If you do not specify a user name when you start **osql**, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] checks for the environment variables and uses those, for example, **osqluser=(*`user`*)** or **osqlserver=(*`server`*)**.</span></span> <span data-ttu-id="8e205-238">Если переменные среды не установлены, используется имя пользователя рабочей станции.</span><span class="sxs-lookup"><span data-stu-id="8e205-238">If no environment variables are set, the workstation user name is used.</span></span> <span data-ttu-id="8e205-239">Если не указан сервер, используется имя рабочей станции.</span><span class="sxs-lookup"><span data-stu-id="8e205-239">If you do not specify a server, the name of the workstation is used.</span></span>  
  
 <span data-ttu-id="8e205-240">Если параметры **-U** и **-P** не используются, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] пытается установить подключение с помощью режима проверки подлинности [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="8e205-240">If neither the **-U** or **-P** options are used, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] attempts to connect using [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Authentication Mode.</span></span> <span data-ttu-id="8e205-241">Проверка подлинности основана на учетной записи пользователя [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows, запустившего программу **osql**.</span><span class="sxs-lookup"><span data-stu-id="8e205-241">Authentication is based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows account of the user running **osql**.</span></span>  
  
 <span data-ttu-id="8e205-242">Программа **osql** использует API ODBC.</span><span class="sxs-lookup"><span data-stu-id="8e205-242">The **osql** utility uses the ODBC API.</span></span> <span data-ttu-id="8e205-243">Эта программа использует настройки драйвера ODBC [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] по умолчанию для параметров соединения ISO в [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8e205-243">The utility uses the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ODBC driver default settings for the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ISO connection options.</span></span> <span data-ttu-id="8e205-244">Дополнительные сведения см. в разделе «Влияние параметров ANSI».</span><span class="sxs-lookup"><span data-stu-id="8e205-244">For more information, see Effects of ANSI Options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8e205-245">Программа **osql** не поддерживает определяемые пользователем типы данных среды CLR.</span><span class="sxs-lookup"><span data-stu-id="8e205-245">The **osql** utility does not support CLR user-defined data types.</span></span> <span data-ttu-id="8e205-246">Для обработки этих типов данных следует использовать программу **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="8e205-246">To process these data types, you must use the **sqlcmd** utility.</span></span> <span data-ttu-id="8e205-247">Дополнительные сведения см. в статье [sqlcmd Utility](sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="8e205-247">For more information, see [sqlcmd Utility](sqlcmd-utility.md).</span></span>  
  
## <a name="osql-commands"></a><span data-ttu-id="8e205-248">Команды OSQL</span><span class="sxs-lookup"><span data-stu-id="8e205-248">OSQL Commands</span></span>  
 <span data-ttu-id="8e205-249">Помимо инструкций [!INCLUDE[tsql](../includes/tsql-md.md)] в программе **osql**также доступны следующие команды.</span><span class="sxs-lookup"><span data-stu-id="8e205-249">In addition to [!INCLUDE[tsql](../includes/tsql-md.md)] statements within **osql**, these commands are also available.</span></span>  
  
|<span data-ttu-id="8e205-250">Get-Help</span><span class="sxs-lookup"><span data-stu-id="8e205-250">Command</span></span>|<span data-ttu-id="8e205-251">Описание</span><span class="sxs-lookup"><span data-stu-id="8e205-251">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8e205-252">GO</span><span class="sxs-lookup"><span data-stu-id="8e205-252">GO</span></span>|<span data-ttu-id="8e205-253">Выполняет все инструкции, введенные после последней команды GO.</span><span class="sxs-lookup"><span data-stu-id="8e205-253">Executes all statements entered after the last GO.</span></span>|  
|<span data-ttu-id="8e205-254">RESET</span><span class="sxs-lookup"><span data-stu-id="8e205-254">RESET</span></span>|<span data-ttu-id="8e205-255">Очищает все введенные инструкции.</span><span class="sxs-lookup"><span data-stu-id="8e205-255">Clears any statements you have entered.</span></span>|  
|<span data-ttu-id="8e205-256">QUIT или EXIT( )</span><span class="sxs-lookup"><span data-stu-id="8e205-256">QUIT or EXIT( )</span></span>|<span data-ttu-id="8e205-257">Завершение работы программы **osql**.</span><span class="sxs-lookup"><span data-stu-id="8e205-257">Exits from **osql**.</span></span>|  
|<span data-ttu-id="8e205-258">CTRL+C</span><span class="sxs-lookup"><span data-stu-id="8e205-258">CTRL+C</span></span>|<span data-ttu-id="8e205-259">Завершает запрос без выхода из программы **osql**.</span><span class="sxs-lookup"><span data-stu-id="8e205-259">Ends a query without exiting from **osql**.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="8e205-260">Команды !!</span><span class="sxs-lookup"><span data-stu-id="8e205-260">The !!</span></span> <span data-ttu-id="8e205-261">и ED больше не поддерживаются программой **osql**.</span><span class="sxs-lookup"><span data-stu-id="8e205-261">and ED commands are no longer supported by **osql**.</span></span>  
  
 <span data-ttu-id="8e205-262">Признаки конца команды GO (по умолчанию), RESET, EXIT, QUIT и CTRL+C распознаются только в начале строки, сразу после запроса программы **osql** .</span><span class="sxs-lookup"><span data-stu-id="8e205-262">The command terminators GO (by default), RESET EXIT, QUIT, and CTRL+C, are recognized only if they appear at the beginning of a line, immediately following the **osql** prompt.</span></span>  
  
 <span data-ttu-id="8e205-263">GO обозначает конец пакетного файла и исполнения любых кэшированных инструкций [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8e205-263">GO signals both the end of a batch and the execution of any cached [!INCLUDE[tsql](../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="8e205-264">При нажатии клавиши ВВОД в конце каждой строки ввода программа **osql** выполняет кэширование инструкций из этой строки.</span><span class="sxs-lookup"><span data-stu-id="8e205-264">When you press ENTER at the end of each input line, **osql** caches the statements on that line.</span></span> <span data-ttu-id="8e205-265">При нажатии клавиши ВВОД после ввода команды GO все текущие инструкции в кэше отправляются в виде пакета в [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e205-265">When you press ENTER after typing GO, all of the currently cached statements are sent as a batch to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="8e205-266">Последняя версия программы **osql** работает таким образом, как будто в конце любого выполняемого скрипта имеется подразумеваемая инструкция GO, поэтому выполняются все инструкции скрипта.</span><span class="sxs-lookup"><span data-stu-id="8e205-266">The current **osql** utility works as if there is an implied GO at the end of any script executed, therefore all statements in the script execute.</span></span>  
  
 <span data-ttu-id="8e205-267">Закончите команду с помощью ввода строки, которая начинается с признака конца команды.</span><span class="sxs-lookup"><span data-stu-id="8e205-267">End a command by typing a line beginning with a command terminator.</span></span> <span data-ttu-id="8e205-268">Следом за признаком конца команды можно ввести целое число, чтобы указать, сколько раз выполнить команду.</span><span class="sxs-lookup"><span data-stu-id="8e205-268">You can follow the command terminator with an integer to specify how many times the command should be run.</span></span> <span data-ttu-id="8e205-269">Например, чтобы выполнить эту команду 100 раз, введите:</span><span class="sxs-lookup"><span data-stu-id="8e205-269">For example, to execute this command 100 times, type:</span></span>  
  
```  
SELECT x = 1  
GO 100  
```  
  
 <span data-ttu-id="8e205-270">Результаты выводятся на печать один раз после завершения.</span><span class="sxs-lookup"><span data-stu-id="8e205-270">The results are printed once at the end of execution.</span></span> <span data-ttu-id="8e205-271">Программа**osql** не принимает более 1000 символов в одной строке.</span><span class="sxs-lookup"><span data-stu-id="8e205-271">**osql** does not accept more than 1,000 characters per line.</span></span> <span data-ttu-id="8e205-272">Большие инструкции должны вводиться в несколько строк.</span><span class="sxs-lookup"><span data-stu-id="8e205-272">Large statements should be spread across multiple lines.</span></span>  
  
 <span data-ttu-id="8e205-273">Для повторного вызова и изменения инструкций **osql** могут использоваться средства повторного вызова команд Windows.</span><span class="sxs-lookup"><span data-stu-id="8e205-273">The command recall facilities of Windows can be used to recall and modify **osql** statements.</span></span> <span data-ttu-id="8e205-274">Существующий буфер запросов можно очистить с помощью команды RESET.</span><span class="sxs-lookup"><span data-stu-id="8e205-274">The existing query buffer can be cleared by typing RESET.</span></span>  
  
 <span data-ttu-id="8e205-275">При запуске хранимых процедур программа **osql** выводит пустую строку между результирующими наборами в пакете.</span><span class="sxs-lookup"><span data-stu-id="8e205-275">When running stored procedures, **osql** prints a blank line between each set of results in a batch.</span></span> <span data-ttu-id="8e205-276">Кроме того, сообщение «обработано строк: 0» не выводится, если оно не применимо к выполненной инструкции.</span><span class="sxs-lookup"><span data-stu-id="8e205-276">In addition, the "0 rows affected" message does not appear when it does not apply to the statement executed.</span></span>  
  
## <a name="using-osql-interactively"></a><span data-ttu-id="8e205-277">Применение программы osql в интерактивном режиме</span><span class="sxs-lookup"><span data-stu-id="8e205-277">Using osql Interactively</span></span>  
 <span data-ttu-id="8e205-278">Чтобы использовать программу **osql** в интерактивном режиме, введите команду **osql** (и любые параметры) в командной строке.</span><span class="sxs-lookup"><span data-stu-id="8e205-278">To use **osql** interactively, type the **osql** command (and any of the options) at a command prompt.</span></span>  
  
 <span data-ttu-id="8e205-279">Файл, содержащий запрос (например, Stores.qry), можно загрузить в программу **osql** и выполнить, введя команду следующего вида:</span><span class="sxs-lookup"><span data-stu-id="8e205-279">You can read in a file containing a query (such as Stores.qry) for execution by **osql** by typing a command similar to this:</span></span>  
  
```  
osql -E -i stores.qry  
```  
  
 <span data-ttu-id="8e205-280">Можно считать запрос из файла (например, Titles.qry) и направить результаты в другой файл, введя команду, подобную следующей:</span><span class="sxs-lookup"><span data-stu-id="8e205-280">You can read in a file containing a query (such as Titles.qry) and direct the results to another file by typing a command similar to this:</span></span>  
  
```  
osql -E -i titles.qry -o titles.res  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8e205-281">По возможности используйте параметр **-E**(доверительное соединение).</span><span class="sxs-lookup"><span data-stu-id="8e205-281">When possible, use the **-E**option (trusted connection).</span></span>  
  
 <span data-ttu-id="8e205-282">При использовании программы **osql** в интерактивном режиме можно прочитать файл операционной системы в буфер команд с помощью команды **: r**_file_name_.</span><span class="sxs-lookup"><span data-stu-id="8e205-282">When using **osql** interactively, you can read an operating-system file into the command buffer with **:r**_file_name_.</span></span> <span data-ttu-id="8e205-283">Это приведет к отправке скрипта SQL в файле с именем *имя_файла* непосредственно на сервер в виде единого пакета.</span><span class="sxs-lookup"><span data-stu-id="8e205-283">This sends the SQL script in *file_name* directly to the server as a single batch.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8e205-284">Если при использовании программы **osql**в файле скрипта SQL содержится разделитель пакетов GO, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] воспринимает его как синтаксическую ошибку.</span><span class="sxs-lookup"><span data-stu-id="8e205-284">When using **osql**, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] treats the batch separator GO, if it appears in a SQL script file, as a syntax error.</span></span>  
  
## <a name="inserting-comments"></a><span data-ttu-id="8e205-285">Вставка примечаний</span><span class="sxs-lookup"><span data-stu-id="8e205-285">Inserting Comments</span></span>  
 <span data-ttu-id="8e205-286">В инструкцию Transact-SQL, отправляемую программой [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] osql **в**, можно включать комментарии.</span><span class="sxs-lookup"><span data-stu-id="8e205-286">You can include comments in a Transact-SQL statement submitted to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] by **osql**.</span></span> <span data-ttu-id="8e205-287">Допускаются два типа стиля комментариев: -- и /\*…\*/.</span><span class="sxs-lookup"><span data-stu-id="8e205-287">Two types of commenting styles are allowed: -- and /\*...\*/.</span></span>  
  
## <a name="using-exit-to-return-results-in-osql"></a><span data-ttu-id="8e205-288">Использование инструкции EXIT для возвращения результатов программы osql</span><span class="sxs-lookup"><span data-stu-id="8e205-288">Using EXIT to Return Results in osql</span></span>  
 <span data-ttu-id="8e205-289">Результат выполнения инструкции SELECT можно использовать в качестве возвращаемого программой **osql**значения.</span><span class="sxs-lookup"><span data-stu-id="8e205-289">You can use the result of a SELECT statement as the return value from **osql**.</span></span> <span data-ttu-id="8e205-290">Если тип числовой, то последний столбец последней строки результатов преобразуется в 4-байтовое целое число (long).</span><span class="sxs-lookup"><span data-stu-id="8e205-290">If it is numeric, the last column of the last result row is converted to a 4-byte integer (long).</span></span> <span data-ttu-id="8e205-291">В MS-DOS младший байт передается родительскому процессу или уровню ошибки операционной системы.</span><span class="sxs-lookup"><span data-stu-id="8e205-291">MS-DOS passes the low byte to the parent process or operating system error level.</span></span> <span data-ttu-id="8e205-292">Windows передает все 4-байтовое целое число.</span><span class="sxs-lookup"><span data-stu-id="8e205-292">Windows passes the entire 4-byte integer.</span></span> <span data-ttu-id="8e205-293">Синтаксис:</span><span class="sxs-lookup"><span data-stu-id="8e205-293">The syntax is:</span></span>  
  
```  
EXIT ( < query > )  
```  
  
 <span data-ttu-id="8e205-294">Пример:</span><span class="sxs-lookup"><span data-stu-id="8e205-294">For example:</span></span>  
  
```  
EXIT(SELECT @@ROWCOUNT)  
```  
  
 <span data-ttu-id="8e205-295">В пакетный файл также можно включить параметр EXIT.</span><span class="sxs-lookup"><span data-stu-id="8e205-295">You can also include the EXIT parameter as part of a batch file.</span></span> <span data-ttu-id="8e205-296">Пример:</span><span class="sxs-lookup"><span data-stu-id="8e205-296">For example:</span></span>  
  
```  
osql -E -Q "EXIT(SELECT COUNT(*) FROM '%1')"  
```  
  
 <span data-ttu-id="8e205-297">Программа **osql** передает на сервер все содержимое, которое заключено в круглые скобки **()** , точно в таком виде, в котором оно введено.</span><span class="sxs-lookup"><span data-stu-id="8e205-297">The **osql** utility passes everything between the parentheses **()** to the server exactly as entered.</span></span> <span data-ttu-id="8e205-298">Если хранимая системная процедура выбирает набор и возвращает значение, то возвращается только выбранный набор.</span><span class="sxs-lookup"><span data-stu-id="8e205-298">If a stored system procedure selects a set and returns a value, only the selection is returned.</span></span> <span data-ttu-id="8e205-299">Инструкция EXIT **()** без выражения в круглых скобках выполняет все, что предшествует ей в пакете, и затем завершается, не возвращая значения.</span><span class="sxs-lookup"><span data-stu-id="8e205-299">The EXIT **()** statement with nothing between the parentheses executes everything preceding it in the batch and then exits with no return value.</span></span>  
  
 <span data-ttu-id="8e205-300">Существуют четыре формата инструкции EXIT:</span><span class="sxs-lookup"><span data-stu-id="8e205-300">There are four EXIT formats:</span></span>  
  
-   <span data-ttu-id="8e205-301">EXIT</span><span class="sxs-lookup"><span data-stu-id="8e205-301">EXIT</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8e205-302">Не выполняет пакет, немедленно завершает работу и не возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="8e205-302">Does not execute the batch; quits immediately and returns no value.</span></span>  
  
-   <span data-ttu-id="8e205-303">EXIT **()**</span><span class="sxs-lookup"><span data-stu-id="8e205-303">EXIT **()**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8e205-304">Выполняет пакет, завершает выполнение и не возвращает значения.</span><span class="sxs-lookup"><span data-stu-id="8e205-304">Executes the batch, and then quits and returns no value.</span></span>  
  
-   <span data-ttu-id="8e205-305">EXIT **( *`query`* )**</span><span class="sxs-lookup"><span data-stu-id="8e205-305">EXIT **(*`query`*)**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8e205-306">Выполняет пакет, включая запрос, затем возвращает результаты запроса и завершает работу.</span><span class="sxs-lookup"><span data-stu-id="8e205-306">Executes the batch, including the query, and then quits after returning the results of the query.</span></span>  
  
-   <span data-ttu-id="8e205-307">RAISERROR с состоянием 127</span><span class="sxs-lookup"><span data-stu-id="8e205-307">RAISERROR with a state of 127</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8e205-308">Если в скрипте **osql** используется RAISERROR и при этом возникает состояние 127, программа **osql** завершает выполнение и возвращает клиенту идентификатор сообщения.</span><span class="sxs-lookup"><span data-stu-id="8e205-308">If RAISERROR is used within an **osql** script and a state of 127 is raised, **osql** will quit and return the message ID back to the client.</span></span> <span data-ttu-id="8e205-309">Пример:</span><span class="sxs-lookup"><span data-stu-id="8e205-309">For example:</span></span>  
  
```  
RAISERROR(50001, 10, 127)  
```  
  
 <span data-ttu-id="8e205-310">Эта ошибка приведет к завершению скрипта **osql** , при этом клиенту будет возвращен идентификатор сообщения 50001.</span><span class="sxs-lookup"><span data-stu-id="8e205-310">This error will cause the **osql** script to end and the message ID 50001 will be returned to the client.</span></span>  
  
 <span data-ttu-id="8e205-311">Возвращаемые значения от -1 до -99 зарезервированы для [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]. Программа **osql** определяет следующие значения:</span><span class="sxs-lookup"><span data-stu-id="8e205-311">The return values -1 to -99 are reserved by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]; **osql** defines these values:</span></span>  
  
-   <span data-ttu-id="8e205-312">–100</span><span class="sxs-lookup"><span data-stu-id="8e205-312">-100</span></span>  
  
     <span data-ttu-id="8e205-313">Перед выбором возвращаемого значения произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="8e205-313">Error encountered prior to selecting return value.</span></span>  
  
-   <span data-ttu-id="8e205-314">–101</span><span class="sxs-lookup"><span data-stu-id="8e205-314">-101</span></span>  
  
     <span data-ttu-id="8e205-315">При выборе возвращаемого значения не найдены строки.</span><span class="sxs-lookup"><span data-stu-id="8e205-315">No rows found when selecting return value.</span></span>  
  
-   <span data-ttu-id="8e205-316">–102</span><span class="sxs-lookup"><span data-stu-id="8e205-316">-102</span></span>  
  
     <span data-ttu-id="8e205-317">При выборе возвращаемого значения произошла ошибка преобразования.</span><span class="sxs-lookup"><span data-stu-id="8e205-317">Conversion error occurred when selecting return value.</span></span>  
  
## <a name="displaying-money-and-smallmoney-data-types"></a><span data-ttu-id="8e205-318">Отображение типов данных money и smallmoney</span><span class="sxs-lookup"><span data-stu-id="8e205-318">Displaying money and smallmoney Data Types</span></span>  
 <span data-ttu-id="8e205-319">**osql** отображает `money` `smallmoney` типы данных и с двумя десятичными разрядами, хотя [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] сохраняет значение внутренне с четырьмя десятичными разрядами.</span><span class="sxs-lookup"><span data-stu-id="8e205-319">**osql** displays the `money` and `smallmoney` data types with two decimal places although [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] stores the value internally with four decimal places.</span></span> <span data-ttu-id="8e205-320">Рассмотрим пример:</span><span class="sxs-lookup"><span data-stu-id="8e205-320">Consider the example:</span></span>  
  
```  
SELECT CAST(CAST(10.3496 AS money) AS decimal(6, 4))  
GO  
```  
  
 <span data-ttu-id="8e205-321">Эта инструкция вернет `10.3496`— это означает, что значение хранится без сокращения количества десятичных разрядов.</span><span class="sxs-lookup"><span data-stu-id="8e205-321">This statement produces a result of `10.3496`, which indicates that the value is stored with all decimal places intact.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e205-322">См. также:</span><span class="sxs-lookup"><span data-stu-id="8e205-322">See Also</span></span>  
 <span data-ttu-id="8e205-323">[Комментарий (MDX)](/sql/mdx/comment-mdx) </span><span class="sxs-lookup"><span data-stu-id="8e205-323">[Comment &#40;MDX&#41;](/sql/mdx/comment-mdx) </span></span>  
 <span data-ttu-id="8e205-324">[-- (Комментарий) (MDX)](/sql/mdx/comment-mdx) </span><span class="sxs-lookup"><span data-stu-id="8e205-324">[-- &#40;Comment&#41; &#40;MDX&#41;](/sql/mdx/comment-mdx) </span></span>  
 <span data-ttu-id="8e205-325">[Функции CAST и CONVERT (Transact-SQL)](/sql/t-sql/functions/cast-and-convert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8e205-325">[CAST and CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql) </span></span>  
 [<span data-ttu-id="8e205-326">RAISERROR (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8e205-326">RAISERROR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/raiserror-transact-sql)  
  
  
