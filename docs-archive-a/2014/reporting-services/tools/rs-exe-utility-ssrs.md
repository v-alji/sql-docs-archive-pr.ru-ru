---
title: Программа RS.exe (SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- automatic report server tasks
- rs utility
- command prompt utilities [Reporting Services]
- report servers [Reporting Services], automating tasks
- command prompt utilities [SQL Server], rs
- scripts [Reporting Services], command prompt
- deploying reports [Reporting Services]
ms.assetid: bd6f958f-cce6-4e79-8a0f-9475da2919ce
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bcf21a1bf2453d2bd1f0644e31ca46f3f94e6884
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735993"
---
# <a name="rsexe-utility-ssrs"></a><span data-ttu-id="d5f97-102">Служебная программа RS.exe (SSRS)</span><span class="sxs-lookup"><span data-stu-id="d5f97-102">RS.exe Utility (SSRS)</span></span>
  <span data-ttu-id="d5f97-103">Скрипт, предоставленный во входном файле, обрабатывается служебной программой rs.exe.</span><span class="sxs-lookup"><span data-stu-id="d5f97-103">The rs.exe utility processes script that you provide in an input file.</span></span> <span data-ttu-id="d5f97-104">Используйте эту программу для автоматизации развертывания сервера отчетов и административных задач.</span><span class="sxs-lookup"><span data-stu-id="d5f97-104">Use this utility to automate report server deployment and administration tasks.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d5f97-105">Начиная с [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], поддерживается применение служебной программы **rs** к серверам отчетов, которые настроены для режима интеграции с SharePoint, а также к серверам, настроенным в основном режиме.</span><span class="sxs-lookup"><span data-stu-id="d5f97-105">Beginning with [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], the **rs** utility is supported against report servers that are configured for SharePoint integrated mode as well as servers configured in native mode.</span></span> <span data-ttu-id="d5f97-106">В предыдущих версиях поддерживалась только работа в собственном режиме.</span><span class="sxs-lookup"><span data-stu-id="d5f97-106">Previous versions only supported native mode configurations.</span></span>  
  
 <span data-ttu-id="d5f97-107">**В этом разделе:**</span><span class="sxs-lookup"><span data-stu-id="d5f97-107">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="d5f97-108">Расположение файла</span><span class="sxs-lookup"><span data-stu-id="d5f97-108">File Location</span></span>](#bkmk_filelocation)  
  
-   [<span data-ttu-id="d5f97-109">Аргументы</span><span class="sxs-lookup"><span data-stu-id="d5f97-109">Arguments</span></span>](#bkmk_arguments)  
  
-   [<span data-ttu-id="d5f97-110">Разрешения</span><span class="sxs-lookup"><span data-stu-id="d5f97-110">Permissions</span></span>](#bkmk_permissions)  
  
-   [<span data-ttu-id="d5f97-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="d5f97-111">Examples</span></span>](#bkmk_examples)  
  
## <a name="syntax"></a><span data-ttu-id="d5f97-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d5f97-112">Syntax</span></span>  
  
```  
  
      rs {-?}  
{-i input_file=}  
{-s serverURL}  
{-u username}  
{-p password}  
{-e endpoint}  
{-l time_out}  
{-b batchmode}  
{-v globalvars=}  
{-t trace}  
```  
  
##  <a name="file-location"></a><a name="bkmk_filelocation"></a> <span data-ttu-id="d5f97-113">Размещение файла</span><span class="sxs-lookup"><span data-stu-id="d5f97-113">File Location</span></span>  
 <span data-ttu-id="d5f97-114">Программа**rs.exe** находится в папке **\Program Files\Microsoft SQL Server\110\Tools\Binn**.</span><span class="sxs-lookup"><span data-stu-id="d5f97-114">**RS.exe** is located at **\Program Files\Microsoft SQL Server\110\Tools\Binn**.</span></span> <span data-ttu-id="d5f97-115">Программу можно запустить из любой папки файловой системы.</span><span class="sxs-lookup"><span data-stu-id="d5f97-115">You can run the utility from any folder on your file system.</span></span>  
  
##  <a name="arguments"></a><a name="bkmk_arguments"></a> <span data-ttu-id="d5f97-116">Аргументы</span><span class="sxs-lookup"><span data-stu-id="d5f97-116">Arguments</span></span>  
 <span data-ttu-id="d5f97-117">**-?**</span><span class="sxs-lookup"><span data-stu-id="d5f97-117">**-?**</span></span>  
 <span data-ttu-id="d5f97-118">Показывает синтаксис аргументов **rs** (необязательно).</span><span class="sxs-lookup"><span data-stu-id="d5f97-118">(Optional) Displays the syntax of **rs** arguments.</span></span>  
  
 <span data-ttu-id="d5f97-119">`-i`*input_file*</span><span class="sxs-lookup"><span data-stu-id="d5f97-119">`-i` *input_file*</span></span>  
 <span data-ttu-id="d5f97-120">(обязательный) Определяет файл rss, подлежащий выполнению.</span><span class="sxs-lookup"><span data-stu-id="d5f97-120">(Required) Specifies the .rss file to execute.</span></span> <span data-ttu-id="d5f97-121">Это значение может быть как относительным, так и полным путем к файлу rss.</span><span class="sxs-lookup"><span data-stu-id="d5f97-121">This value can be a relative or fully qualified path to the .rss file.</span></span>  
  
 <span data-ttu-id="d5f97-122">`-s`*ServerUrl*</span><span class="sxs-lookup"><span data-stu-id="d5f97-122">`-s` *serverURL*</span></span>  
 <span data-ttu-id="d5f97-123">(обязательный) Определяет имя веб-сервера и имя виртуального каталога сервера отчетов, к которым будет применен выполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="d5f97-123">(Required) Specifies the Web server name and report server virtual directory name to execute the file against.</span></span> <span data-ttu-id="d5f97-124">Пример URL-адреса сервера отчетов: `http://examplewebserver/reportserver`.</span><span class="sxs-lookup"><span data-stu-id="d5f97-124">An example of a report server URL is `http://examplewebserver/reportserver`.</span></span> <span data-ttu-id="d5f97-125">Префикс http:// или https: // в начале имени сервера необязателен.</span><span class="sxs-lookup"><span data-stu-id="d5f97-125">The prefix http:// or https:// at the beginning of the server name is optional.</span></span> <span data-ttu-id="d5f97-126">Если префикс не указан, то сервер, на котором находится скрипт сервера отчетов, сначала пытается использовать протокол HTTPS, а в случае неудачи — протокол HTTP.</span><span class="sxs-lookup"><span data-stu-id="d5f97-126">If you omit the prefix, the report server script host tries to use https first, and then uses http if https does not work.</span></span>  
  
 <span data-ttu-id="d5f97-127">`-u`[*домен* \\ ] *имя пользователя*</span><span class="sxs-lookup"><span data-stu-id="d5f97-127">`-u` [*domain*\\]*username*</span></span>  
 <span data-ttu-id="d5f97-128">(Необязательный) Определяет учетную запись пользователя, используемую для подключения к серверу отчетов.</span><span class="sxs-lookup"><span data-stu-id="d5f97-128">(Optional) Specifies a user account used to connect to the report server.</span></span> <span data-ttu-id="d5f97-129">В случае отсутствия `-u` и `-p` используется текущая учетная запись пользователя Windows.</span><span class="sxs-lookup"><span data-stu-id="d5f97-129">If `-u` and `-p` are omitted, the current Windows user account is used.</span></span>  
  
 <span data-ttu-id="d5f97-130">`-p`*пароль*</span><span class="sxs-lookup"><span data-stu-id="d5f97-130">`-p` *password*</span></span>  
 <span data-ttu-id="d5f97-131">(обязательный, если задан `-u`) Определяет пароль для использования с аргументом `-u`.</span><span class="sxs-lookup"><span data-stu-id="d5f97-131">(Required if `-u` is specified) Specifies the password to use with the `-u` argument.</span></span> <span data-ttu-id="d5f97-132">Это значение учитывает регистр.</span><span class="sxs-lookup"><span data-stu-id="d5f97-132">This value is case-sensitive.</span></span>  
  
 `-e`  
 <span data-ttu-id="d5f97-133">(Необязательный) Определяет конечную точку SOAP, с которой должен выполняться скрипт.</span><span class="sxs-lookup"><span data-stu-id="d5f97-133">(Optional) Specifies the SOAP endpoint against which the script should run.</span></span> <span data-ttu-id="d5f97-134">Допустимы следующие значения.</span><span class="sxs-lookup"><span data-stu-id="d5f97-134">Valid values are the following:</span></span>  
  
-   <span data-ttu-id="d5f97-135">Mgmt2010</span><span class="sxs-lookup"><span data-stu-id="d5f97-135">Mgmt2010</span></span>  
  
-   <span data-ttu-id="d5f97-136">Mgmt2006</span><span class="sxs-lookup"><span data-stu-id="d5f97-136">Mgmt2006</span></span>  
  
-   <span data-ttu-id="d5f97-137">Mgmt2005</span><span class="sxs-lookup"><span data-stu-id="d5f97-137">Mgmt2005</span></span>  
  
-   <span data-ttu-id="d5f97-138">Exec2005</span><span class="sxs-lookup"><span data-stu-id="d5f97-138">Exec2005</span></span>  
  
 <span data-ttu-id="d5f97-139">Если значение не указано, то используется конечная точка Mgmt2005.</span><span class="sxs-lookup"><span data-stu-id="d5f97-139">If a value is not specified, the Mgmt2005 endpoint is used.</span></span> <span data-ttu-id="d5f97-140">Дополнительные сведения о конечных точках SOAP см. в разделе [Report Server Web Service Endpoints](../report-server-web-service/methods/report-server-web-service-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="d5f97-140">For more information about the SOAP endpoints, see [Report Server Web Service Endpoints](../report-server-web-service/methods/report-server-web-service-endpoints.md).</span></span>  
  
 <span data-ttu-id="d5f97-141">`-l`*time_out*</span><span class="sxs-lookup"><span data-stu-id="d5f97-141">`-l` *time_out*</span></span>  
 <span data-ttu-id="d5f97-142">Используемых Указывает количество секунд, которое должно пройти до истечения времени ожидания соединения с сервером. Значение по умолчанию — 60 секунд.</span><span class="sxs-lookup"><span data-stu-id="d5f97-142">(Optional) Specifies the number of seconds that elapse before the connection to the server times out. The default is 60 seconds.</span></span> <span data-ttu-id="d5f97-143">Если значение времени ожидания не определено, то используется значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d5f97-143">If you do not specify a time-out value, the default is used.</span></span> <span data-ttu-id="d5f97-144">Значение `0` определяет бесконечное время ожидания соединения.</span><span class="sxs-lookup"><span data-stu-id="d5f97-144">A value of `0` specifies that the connection never times out.</span></span>  
  
 <span data-ttu-id="d5f97-145">**-b**</span><span class="sxs-lookup"><span data-stu-id="d5f97-145">**-b**</span></span>  
 <span data-ttu-id="d5f97-146">(Необязательный) Задает пакетное выполнение команд файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="d5f97-146">(Optional) Specifies that the commands in the script file run in a batch.</span></span> <span data-ttu-id="d5f97-147">В случае ошибки любой из команд происходит откат всего пакета к прежнему состоянию.</span><span class="sxs-lookup"><span data-stu-id="d5f97-147">If any commands fail, the batch is rolled back.</span></span> <span data-ttu-id="d5f97-148">Некоторые команды не могут быть помещены в пакет и будут выполняться обычным способом.</span><span class="sxs-lookup"><span data-stu-id="d5f97-148">Some commands cannot be batched, and those run as usual.</span></span> <span data-ttu-id="d5f97-149">Откат вызывается только исключениями, которые возникли, но не обрабатываются скриптом.</span><span class="sxs-lookup"><span data-stu-id="d5f97-149">Only exceptions that are thrown and are not handled within the script result in a rollback.</span></span> <span data-ttu-id="d5f97-150">Если скрипт обрабатывает исключение и возвращается из функции `Main` без ошибок, пакет фиксируется.</span><span class="sxs-lookup"><span data-stu-id="d5f97-150">If the script handles an exception and returns normally from `Main`, the batch is committed.</span></span> <span data-ttu-id="d5f97-151">Если этот параметр не указан, то команды выполняются без создания пакета.</span><span class="sxs-lookup"><span data-stu-id="d5f97-151">If you omit this parameter, the commands run without creating a batch.</span></span> <span data-ttu-id="d5f97-152">Дополнительные сведения см. в статье [Batching Methods](../report-server-web-service-net-framework-soap-headers/batching-methods.md).</span><span class="sxs-lookup"><span data-stu-id="d5f97-152">For more information, see [Batching Methods](../report-server-web-service-net-framework-soap-headers/batching-methods.md).</span></span>  
  
 <span data-ttu-id="d5f97-153">`-v`*глобалвар*</span><span class="sxs-lookup"><span data-stu-id="d5f97-153">`-v` *globalvar*</span></span>  
 <span data-ttu-id="d5f97-154">(Необязательный) Определяет глобальные переменные, которые используются в скрипте.</span><span class="sxs-lookup"><span data-stu-id="d5f97-154">(Optional) Specifies global variables that are used in the script.</span></span> <span data-ttu-id="d5f97-155">Если скрипт использует глобальные переменные, то необходимо задать этот аргумент.</span><span class="sxs-lookup"><span data-stu-id="d5f97-155">If the script uses global variables, you must specify this argument.</span></span> <span data-ttu-id="d5f97-156">Задаваемое значение должно быть допустимым для глобальной переменной, определенной в файле rss.</span><span class="sxs-lookup"><span data-stu-id="d5f97-156">The value that you specify must be valid for global variable defined in the .rss file.</span></span> <span data-ttu-id="d5f97-157">Необходимо указать одну глобальную переменную для каждого аргумента **-v** .</span><span class="sxs-lookup"><span data-stu-id="d5f97-157">You must specify one global variable for each **-v** argument.</span></span>  
  
 <span data-ttu-id="d5f97-158">Аргумент `-v` задается в командной строке и используется для указания значения глобальной переменной, которая определяется в скрипте во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d5f97-158">The `-v` argument is specified on the command line and is used to set the value for a global variable that is defined in your script at run time.</span></span> <span data-ttu-id="d5f97-159">Например, если скрипт содержит переменную с именем *parentFolder*, можно указать имя для соответствующей папки в командной строке:</span><span class="sxs-lookup"><span data-stu-id="d5f97-159">For example, if your script contains a variable named *parentFolder*, you can specify a name for that folder on the command line:</span></span>  
  
 `rs.exe -i myScriptFile.rss -s http://myServer/reportserver -v parentFolder="Financial Reports"`  
  
 <span data-ttu-id="d5f97-160">Глобальные переменные создаются с указанными именами и им присваиваются заданные значения.</span><span class="sxs-lookup"><span data-stu-id="d5f97-160">Global variables are created with the names given and set to the values supplied.</span></span> <span data-ttu-id="d5f97-161">Например, **-v a =**" `1` " **-v b =**" `2` " приводит к переменной с именем `a` со значением " `1` " и переменной **b** со значением " `2` ".</span><span class="sxs-lookup"><span data-stu-id="d5f97-161">For example, **-v a=**"`1`" **-v b=**"`2`" results in a variable named `a` with a value of"`1`" and a variable **b** with a value of "`2`".</span></span>  
  
 <span data-ttu-id="d5f97-162">Глобальные переменные доступны для любой функции в скрипте.</span><span class="sxs-lookup"><span data-stu-id="d5f97-162">Global variables are available to any function in the script.</span></span> <span data-ttu-id="d5f97-163">Обратная косая черта и кавычка (\*\* \\ "\*\*) интерпретируется как двойная кавычка.</span><span class="sxs-lookup"><span data-stu-id="d5f97-163">A backslash and quotation mark (**\\"**) is interpreted as a double quotation mark.</span></span> <span data-ttu-id="d5f97-164">Кавычки требуются только в том случае, если строка содержит пробелы.</span><span class="sxs-lookup"><span data-stu-id="d5f97-164">The quotation marks are required only if the string contains a space.</span></span> <span data-ttu-id="d5f97-165">Имена переменных должны быть допустимыми для [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] ; они должны начинаться с алфавитного символа или знака подчеркивания и содержать буквы, цифры или символы подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="d5f97-165">Variable names must be valid for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]; they must start with alphabetical character or underscore and contain alphabetical characters, digits, or underscores.</span></span> <span data-ttu-id="d5f97-166">Зарезервированные слова не могут использоваться в качестве имен переменных.</span><span class="sxs-lookup"><span data-stu-id="d5f97-166">Reserved words cannot be used as variable names.</span></span> <span data-ttu-id="d5f97-167">Дополнительные сведения об использовании глобальных переменных см. в разделе [Встроенные коллекции в выражениях (построитель отчетов и службы SSRS)](../report-design/built-in-collections-in-expressions-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="d5f97-167">For more information about using global variables, see [Built-in Collections in Expressions &#40;Report Builder and SSRS&#41;](../report-design/built-in-collections-in-expressions-report-builder.md).</span></span>  
  
 <span data-ttu-id="d5f97-168">**-t**</span><span class="sxs-lookup"><span data-stu-id="d5f97-168">**-t**</span></span>  
 <span data-ttu-id="d5f97-169">(Необязательный) Записывает сообщения об ошибках в журнал трассировки.</span><span class="sxs-lookup"><span data-stu-id="d5f97-169">(Optional) Outputs error messages to the trace log.</span></span> <span data-ttu-id="d5f97-170">Этот аргумент не принимает значения.</span><span class="sxs-lookup"><span data-stu-id="d5f97-170">This argument does not take a value.</span></span> <span data-ttu-id="d5f97-171">Дополнительные сведения см. в статье [Report Server Service Trace Log](../report-server/report-server-service-trace-log.md).</span><span class="sxs-lookup"><span data-stu-id="d5f97-171">For more information, see [Report Server Service Trace Log](../report-server/report-server-service-trace-log.md).</span></span>  
  
##  <a name="permissions"></a><a name="bkmk_permissions"></a> <span data-ttu-id="d5f97-172">Permissions</span><span class="sxs-lookup"><span data-stu-id="d5f97-172">Permissions</span></span>  
 <span data-ttu-id="d5f97-173">Для запуска этого средства необходимо иметь разрешение на подключение к экземпляру сервера отчетов, с которым работает выполняемый скрипт.</span><span class="sxs-lookup"><span data-stu-id="d5f97-173">To run the tool, you must have permission to connect to the report server instance you are running the script against.</span></span> <span data-ttu-id="d5f97-174">Можно выполнять скрипты для внесения изменений на локальном или удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d5f97-174">You can run scripts to make changes to the local computer or a remote computer.</span></span> <span data-ttu-id="d5f97-175">Для внесения изменений на сервере отчетов, установленном на удаленном компьютере, укажите удаленный компьютер в аргументе `-s`.</span><span class="sxs-lookup"><span data-stu-id="d5f97-175">To make changes to a report server installed on a remote computer, specify the remote computer in the `-s` argument.</span></span>  
  
##  <a name="examples"></a><a name="bkmk_examples"></a> <span data-ttu-id="d5f97-176">Примеры</span><span class="sxs-lookup"><span data-stu-id="d5f97-176">Examples</span></span>  
 <span data-ttu-id="d5f97-177">В следующем примере показано, как задать файл скрипта, содержащего скрипт [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET, и методы веб-службы, которые требуется выполнить.</span><span class="sxs-lookup"><span data-stu-id="d5f97-177">The following example illustrates how to specify the script file that contains [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET script and Web service methods that you want to execute.</span></span>  
  
```  
rs -i c:\scriptfiles\script_copycontent.rss -s http://localhost/reportserver  
```  
  
 <span data-ttu-id="d5f97-178"> Подробный пример см. в разделе [Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span><span class="sxs-lookup"><span data-stu-id="d5f97-178">For a detailed example, see [Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span></span>  
  
 <span data-ttu-id="d5f97-179">Дополнительные примеры см. в разделе [Запуск файла скрипта для служб Reporting Services](run-a-reporting-services-script-file.md)</span><span class="sxs-lookup"><span data-stu-id="d5f97-179">For additional examples, see [Run a Reporting Services Script File](run-a-reporting-services-script-file.md)</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5f97-180">Remarks</span><span class="sxs-lookup"><span data-stu-id="d5f97-180">Remarks</span></span>  
 <span data-ttu-id="d5f97-181">Можно определять скрипты, устанавливать системные свойства, публиковать отчеты и так далее.</span><span class="sxs-lookup"><span data-stu-id="d5f97-181">You can define scripts to set system properties, publish reports, and so forth.</span></span> <span data-ttu-id="d5f97-182">Создаваемые скрипты могут включать любые методы API-интерфейса служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5f97-182">The scripts that you create can include any methods of the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] API.</span></span> <span data-ttu-id="d5f97-183">Дополнительные сведения о доступных методах и свойствах см. в разделе [Report Server Web Service](../report-server-web-service/report-server-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="d5f97-183">For more information about the methods and properties available to you, see [Report Server Web Service](../report-server-web-service/report-server-web-service.md).</span></span>  
  
 <span data-ttu-id="d5f97-184">Скрипт должен быть написан на языке [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET и храниться в текстовом файле в кодировке Юникод или UTF-8 с расширением RSS.</span><span class="sxs-lookup"><span data-stu-id="d5f97-184">The script must be written in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET code, and stored in a Unicode or UTF-8 text file with an .rss file name extension.</span></span> <span data-ttu-id="d5f97-185">Отладить скрипт с помощью программы **rs** невозможно.</span><span class="sxs-lookup"><span data-stu-id="d5f97-185">You cannot debug scripts with the **rs** utility.</span></span> <span data-ttu-id="d5f97-186">Чтобы выполнить отладку скрипта, выполните код в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5f97-186">To debug a script, run the code within [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="d5f97-187"> Подробный пример см. в разделе [Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span><span class="sxs-lookup"><span data-stu-id="d5f97-187">For a detailed example, see [Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5f97-188">См. также:</span><span class="sxs-lookup"><span data-stu-id="d5f97-188">See Also</span></span>  
 <span data-ttu-id="d5f97-189">[Запуск файла скрипта Reporting Services](run-a-reporting-services-script-file.md) </span><span class="sxs-lookup"><span data-stu-id="d5f97-189">[Run a Reporting Services Script File](run-a-reporting-services-script-file.md) </span></span>  
 <span data-ttu-id="d5f97-190">[Создание скриптов для задач развертывания и администрирования](script-deployment-and-administrative-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="d5f97-190">[Script Deployment and Administrative Tasks](script-deployment-and-administrative-tasks.md) </span></span>  
 <span data-ttu-id="d5f97-191">[Скрипт с помощью служебной программы rs.exe и веб-службы](script-with-the-rs-exe-utility-and-the-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="d5f97-191">[Script with the rs.exe Utility and the Web Service](script-with-the-rs-exe-utility-and-the-web-service.md) </span></span>  
 [<span data-ttu-id="d5f97-192">Программы командной строки сервера отчетов (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d5f97-192">Report Server Command Prompt Utilities &#40;SSRS&#41;</span></span>](report-server-command-prompt-utilities-ssrs.md)  
  
  
