---
title: Программа Profiler | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- command prompt utilities [SQL Server], profiler90 utility
- profiler90 utility
- Profiler [SQL Server Profiler], starting
- SQL Server Profiler, starting
- starting SQL Server Profiler
ms.assetid: e91c30a9-0d29-4f84-bcb8-e8fb62afadda
author: stevestein
ms.author: sstein
ms.openlocfilehash: a8df3e8557bb52839d17291bae0c5ba507d0a671
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727610"
---
# <a name="profiler-utility"></a><span data-ttu-id="2b2f4-102">Приложение SQL Profiler</span><span class="sxs-lookup"><span data-stu-id="2b2f4-102">Profiler Utility</span></span>
  <span data-ttu-id="2b2f4-103">Служебная программа **profiler** запускает средство [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2b2f4-103">The **profiler** utility launches the [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] tool.</span></span> <span data-ttu-id="2b2f4-104">Дополнительные аргументы, перечисленные ниже в этом разделе, позволяют управлять способом запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="2b2f4-104">The optional arguments listed later in this topic allow you to control how the application starts.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2b2f4-105">Служебная программа **profiler** не предназначена для написания скриптов трассировки.</span><span class="sxs-lookup"><span data-stu-id="2b2f4-105">The **profiler** utility is not intended for scripting traces.</span></span> <span data-ttu-id="2b2f4-106">Дополнительные сведения см. в разделе [Start SQL Server Profiler](sql-server-profiler/sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="2b2f4-106">For more information, see [SQL Server Profiler](sql-server-profiler/sql-server-profiler.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b2f4-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2b2f4-107">Syntax</span></span>  
  
```  
  
      profiler  
          [ /? ] |  
[  
{  
{ /U login_id [ /P password ] }  
| /E  
}  
{[ /S sql_server_name ] | [ /A analysis_services_server_name ] }  
[ /D database ]  
[ /T "template_name" ]  
[ /B { "trace_table_name" } ]  
{ [/F "filename" ] | [ /O "filename" ] }  
[ /L locale_ID ]  
[ /M "MM-DD-YY hh:mm:ss" ]  
[ /R ]  
[ /Z file_size ]  
]  
```  
  
## <a name="arguments"></a><span data-ttu-id="2b2f4-108">Аргументы</span><span class="sxs-lookup"><span data-stu-id="2b2f4-108">Arguments</span></span>  
 <span data-ttu-id="2b2f4-109">**/?**</span><span class="sxs-lookup"><span data-stu-id="2b2f4-109">**/?**</span></span>  
 <span data-ttu-id="2b2f4-110">Показывает сводку по синтаксису аргументов **profiler** .</span><span class="sxs-lookup"><span data-stu-id="2b2f4-110">Displays the syntax summary of **profiler** arguments.</span></span>  
  
 <span data-ttu-id="2b2f4-111">**/U** *login_id*</span><span class="sxs-lookup"><span data-stu-id="2b2f4-111">**/U** *login_id*</span></span>  
 <span data-ttu-id="2b2f4-112">Идентификатор входа при проверке подлинности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2b2f4-112">Is the user login ID for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="2b2f4-113">При записи идентификаторов входа регистр символов имеет значение.</span><span class="sxs-lookup"><span data-stu-id="2b2f4-113">Login IDs are case sensitive.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoteWinAuthentication](../includes/ssnotewinauthentication-md.md)]<span data-ttu-id="2b2f4-114">.</span><span class="sxs-lookup"><span data-stu-id="2b2f4-114">.</span></span>  
  
 <span data-ttu-id="2b2f4-115">**/P** *password*</span><span class="sxs-lookup"><span data-stu-id="2b2f4-115">**/P** *password*</span></span>  
 <span data-ttu-id="2b2f4-116">Задает пользовательский пароль для проверки подлинности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2b2f4-116">Specifies a user-specified password for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="2b2f4-117">**/E**</span><span class="sxs-lookup"><span data-stu-id="2b2f4-117">**/E**</span></span>  
 <span data-ttu-id="2b2f4-118">Задает подключение с использованием проверки подлинности Windows с учетными данными текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="2b2f4-118">Specifies connecting with Windows Authentication with the current user's credentials.</span></span>  
  
 <span data-ttu-id="2b2f4-119">**/S**  *sql_server_name*</span><span class="sxs-lookup"><span data-stu-id="2b2f4-119">**/S**  *sql_server_name*</span></span>  
 <span data-ttu-id="2b2f4-120">Указывает экземпляр [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b2f4-120">Specifies an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2b2f4-121">Profiler автоматически подключится к указанному серверу с использованием данных проверки подлинности, указанных в параметрах **/U** и **/P** или **/E** .</span><span class="sxs-lookup"><span data-stu-id="2b2f4-121">Profiler will automatically connect to the specified server using the authentication information specified in the **/U** and **/P** switches or the **/E** switch.</span></span> <span data-ttu-id="2b2f4-122">Чтобы подключиться к именованному экземпляру [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], укажите **/S** *sql_server_name*\\*instance_name*.</span><span class="sxs-lookup"><span data-stu-id="2b2f4-122">To connect to a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], use **/S** *sql_server_name*\\*instance_name*.</span></span>  
  
 <span data-ttu-id="2b2f4-123">**/A**  *analysis_services_server_name*</span><span class="sxs-lookup"><span data-stu-id="2b2f4-123">**/A**  *analysis_services_server_name*</span></span>  
 <span data-ttu-id="2b2f4-124">Указывает экземпляр служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="2b2f4-124">Specifies an instance of Analysis Services.</span></span> <span data-ttu-id="2b2f4-125">Profiler автоматически подключится к указанному серверу с использованием данных проверки подлинности, указанных в параметрах **/U** и **/P** или **/E** .</span><span class="sxs-lookup"><span data-stu-id="2b2f4-125">Profiler will automatically connect to the specified server using the authentication information specified in the **/U** and **/P** switches or the **/E** switch.</span></span> <span data-ttu-id="2b2f4-126">Чтобы подключиться к именованному экземпляру [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], укажите **/A** *analysis_services_server_name\instance_name*.</span><span class="sxs-lookup"><span data-stu-id="2b2f4-126">To connect to a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] use **/A** *analysis_services_server_name\instance_name*.</span></span>  
  
 <span data-ttu-id="2b2f4-127">**/D** *database*</span><span class="sxs-lookup"><span data-stu-id="2b2f4-127">**/D** *database*</span></span>  
 <span data-ttu-id="2b2f4-128">Указывает имя базы данных, которая будет использоваться с соединением.</span><span class="sxs-lookup"><span data-stu-id="2b2f4-128">Specifies the name of the database to be used with the connection.</span></span> <span data-ttu-id="2b2f4-129">Если база данных не указывается, этот аргумент выберет базу данных по умолчанию для указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="2b2f4-129">This option will select the default database for the specified user if no database is specified.</span></span>  
  
 <span data-ttu-id="2b2f4-130">**/B "** *trace_table_name* **"**</span><span class="sxs-lookup"><span data-stu-id="2b2f4-130">**/B "** *trace_table_name* **"**</span></span>  
 <span data-ttu-id="2b2f4-131">Указывает таблицу трассировки для загрузки при запуске профайлера.</span><span class="sxs-lookup"><span data-stu-id="2b2f4-131">Specifies a trace table to load when the profiler is launched.</span></span> <span data-ttu-id="2b2f4-132">Необходимо задать базу данных, пользователя или схему, а также таблицу.</span><span class="sxs-lookup"><span data-stu-id="2b2f4-132">You must specify the database, the user or schema, and the table.</span></span>  
  
 <span data-ttu-id="2b2f4-133">**/T"** *template_name* **"**</span><span class="sxs-lookup"><span data-stu-id="2b2f4-133">**/T"** *template_name* **"**</span></span>  
 <span data-ttu-id="2b2f4-134">Указывает шаблон, загружаемый для настройки трассировки.</span><span class="sxs-lookup"><span data-stu-id="2b2f4-134">Specifies the template that will be loaded to configure the trace.</span></span> <span data-ttu-id="2b2f4-135">Имя шаблона должно быть заключено в кавычки.</span><span class="sxs-lookup"><span data-stu-id="2b2f4-135">The template name must be in quotes.</span></span> <span data-ttu-id="2b2f4-136">Имя шаблона должно находиться либо в системном каталоге шаблонов, либо в пользовательском каталоге шаблонов.</span><span class="sxs-lookup"><span data-stu-id="2b2f4-136">The template name must be in either the system template directory or the user template directory.</span></span> <span data-ttu-id="2b2f4-137">В случае существования двух шаблонов с одним именем в обоих каталогах будет загружен шаблон, находящийся в системном каталоге.</span><span class="sxs-lookup"><span data-stu-id="2b2f4-137">If two templates with the same name exist in both directories, the template from the system directory will be loaded.</span></span> <span data-ttu-id="2b2f4-138">Если шаблон с указанным именем не существует, то будет загружен стандартный шаблон.</span><span class="sxs-lookup"><span data-stu-id="2b2f4-138">If no template with the specified name exists, the standard template will be loaded.</span></span> <span data-ttu-id="2b2f4-139">Примечание. Расширение файла для шаблона (TDF) в аргументе *template_name*указывать не нужно.</span><span class="sxs-lookup"><span data-stu-id="2b2f4-139">Note that the file extension for the template (.tdf) should not be specified as part of the *template_name*.</span></span> <span data-ttu-id="2b2f4-140">Пример:</span><span class="sxs-lookup"><span data-stu-id="2b2f4-140">For example:</span></span>  
  
```  
/T "standard"  
```  
  
 <span data-ttu-id="2b2f4-141">**/F"** *filename* **"**</span><span class="sxs-lookup"><span data-stu-id="2b2f4-141">**/F"** *filename* **"**</span></span>  
 <span data-ttu-id="2b2f4-142">Указывает путь и имя файла трассировки, загружаемого при запуске профайлера.</span><span class="sxs-lookup"><span data-stu-id="2b2f4-142">Specifies the path and filename of a trace file to load when profiler is launched.</span></span> <span data-ttu-id="2b2f4-143">Полный путь и имя файла должны быть заключены в кавычки.</span><span class="sxs-lookup"><span data-stu-id="2b2f4-143">The entire path and filename must be in quotes.</span></span> <span data-ttu-id="2b2f4-144">Этот параметр нельзя использовать совместно с параметром **/O**.</span><span class="sxs-lookup"><span data-stu-id="2b2f4-144">This option cannot be used with **/O**.</span></span>  
  
 <span data-ttu-id="2b2f4-145">**/O "** *filename*  **"**</span><span class="sxs-lookup"><span data-stu-id="2b2f4-145">**/O "** *filename*  **"**</span></span>  
 <span data-ttu-id="2b2f4-146">Указывает путь и имя файла, в который должны быть записаны результаты трассировки.</span><span class="sxs-lookup"><span data-stu-id="2b2f4-146">Specifies the path and filename of a file to which trace results should be written.</span></span> <span data-ttu-id="2b2f4-147">Полный путь и имя файла должны быть заключены в кавычки.</span><span class="sxs-lookup"><span data-stu-id="2b2f4-147">The entire path and filename must be in quotes.</span></span> <span data-ttu-id="2b2f4-148">Этот параметр нельзя использовать совместно с параметром **/F**.</span><span class="sxs-lookup"><span data-stu-id="2b2f4-148">This option cannot be used with **/F.**</span></span>  
  
 <span data-ttu-id="2b2f4-149">**/L** *locale_ID*</span><span class="sxs-lookup"><span data-stu-id="2b2f4-149">**/L** *locale_ID*</span></span>  
 <span data-ttu-id="2b2f4-150">Недоступно.</span><span class="sxs-lookup"><span data-stu-id="2b2f4-150">Not available.</span></span>  
  
 <span data-ttu-id="2b2f4-151">**/M "** *MM-DD-YY hh:mm:ss* **"**</span><span class="sxs-lookup"><span data-stu-id="2b2f4-151">**/M "** *MM-DD-YY hh:mm:ss* **"**</span></span>  
 <span data-ttu-id="2b2f4-152">Задает дату и время остановки трассировки.</span><span class="sxs-lookup"><span data-stu-id="2b2f4-152">Specifies the date and time for the trace to stop.</span></span> <span data-ttu-id="2b2f4-153">Время остановки должно быть заключено в кавычки.</span><span class="sxs-lookup"><span data-stu-id="2b2f4-153">The stop time must be in quotes.</span></span> <span data-ttu-id="2b2f4-154">Задайте время остановки согласно параметрам в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="2b2f4-154">Specify the stop time according to the parameters in the table below:</span></span>  
  
|<span data-ttu-id="2b2f4-155">Параметр</span><span class="sxs-lookup"><span data-stu-id="2b2f4-155">Parameter</span></span>|<span data-ttu-id="2b2f4-156">Определение</span><span class="sxs-lookup"><span data-stu-id="2b2f4-156">Definition</span></span>|  
|---------------|----------------|  
|<span data-ttu-id="2b2f4-157">ММ</span><span class="sxs-lookup"><span data-stu-id="2b2f4-157">MM</span></span>|<span data-ttu-id="2b2f4-158">Месяц (2 разряда)</span><span class="sxs-lookup"><span data-stu-id="2b2f4-158">Two-digit month</span></span>|  
|<span data-ttu-id="2b2f4-159">DD</span><span class="sxs-lookup"><span data-stu-id="2b2f4-159">DD</span></span>|<span data-ttu-id="2b2f4-160">День (2 разряда)</span><span class="sxs-lookup"><span data-stu-id="2b2f4-160">Two-digit day</span></span>|  
|<span data-ttu-id="2b2f4-161">ГГ</span><span class="sxs-lookup"><span data-stu-id="2b2f4-161">YY</span></span>|<span data-ttu-id="2b2f4-162">Год (2 разряда)</span><span class="sxs-lookup"><span data-stu-id="2b2f4-162">Two-digit year</span></span>|  
|<span data-ttu-id="2b2f4-163">hh</span><span class="sxs-lookup"><span data-stu-id="2b2f4-163">hh</span></span>|<span data-ttu-id="2b2f4-164">Час (2 разряда), в 24-часовом формате</span><span class="sxs-lookup"><span data-stu-id="2b2f4-164">Two-digit hour on a 24-hour clock</span></span>|  
|<span data-ttu-id="2b2f4-165">ММ</span><span class="sxs-lookup"><span data-stu-id="2b2f4-165">mm</span></span>|<span data-ttu-id="2b2f4-166">Минуты (2 разряда)</span><span class="sxs-lookup"><span data-stu-id="2b2f4-166">Two-digit minute</span></span>|  
|<span data-ttu-id="2b2f4-167">сс</span><span class="sxs-lookup"><span data-stu-id="2b2f4-167">ss</span></span>|<span data-ttu-id="2b2f4-168">Секунды (2 разряда)</span><span class="sxs-lookup"><span data-stu-id="2b2f4-168">Two-digit second</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="2b2f4-169">Формат "ММ-ДД-ГГ чч:мм:сс" можно использовать только в том случае, если включен параметр **Использовать региональные настройки при показе значений даты и времени** в приложении [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b2f4-169">The "MM-DD-YY hh:mm:ss" format can only be used if the **Use regional settings to display date and time values** option is enabled in [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="2b2f4-170">Если этот параметр не включен, следует использовать формат даты и времени «ГГГГ-ММ-ДД чч:мм:сс».</span><span class="sxs-lookup"><span data-stu-id="2b2f4-170">If this option is not enabled, you must use the "YYYY-MM-DD hh:mm:ss" date and time format.</span></span>  
  
 <span data-ttu-id="2b2f4-171">**/R**</span><span class="sxs-lookup"><span data-stu-id="2b2f4-171">**/R**</span></span>  
 <span data-ttu-id="2b2f4-172">Включает операцию переключения на файл продолжения трассировки.</span><span class="sxs-lookup"><span data-stu-id="2b2f4-172">Enables trace file rollover.</span></span>  
  
 <span data-ttu-id="2b2f4-173">**/Z**  *file_size*</span><span class="sxs-lookup"><span data-stu-id="2b2f4-173">**/Z**  *file_size*</span></span>  
 <span data-ttu-id="2b2f4-174">Определяет размер файла трассировки в мегабайтах (МБ).</span><span class="sxs-lookup"><span data-stu-id="2b2f4-174">Specifies the size of the trace file in megabytes (MB).</span></span> <span data-ttu-id="2b2f4-175">Размер по умолчанию составляет 5 МБ.</span><span class="sxs-lookup"><span data-stu-id="2b2f4-175">The default size is 5 MB.</span></span> <span data-ttu-id="2b2f4-176">Если включена операция переключения, все файлы продолжения будут ограничены значением, указанным в этом аргументе.</span><span class="sxs-lookup"><span data-stu-id="2b2f4-176">If rollover is enabled, all rollover files will be limited to the value specified in this argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b2f4-177">Remarks</span><span class="sxs-lookup"><span data-stu-id="2b2f4-177">Remarks</span></span>  
 <span data-ttu-id="2b2f4-178">Для запуска трассировки с использованием определенного шаблона укажите параметры **/S** и **/T** .</span><span class="sxs-lookup"><span data-stu-id="2b2f4-178">To start a trace with a specific template, use the **/S** and **/T** options together.</span></span> <span data-ttu-id="2b2f4-179">Например, чтобы запустить трассировку с использованием шаблона Standard на экземпляре MyServer\MyInstance, введите в командной строке:</span><span class="sxs-lookup"><span data-stu-id="2b2f4-179">For example, to start a trace using the Standard template on MyServer\MyInstance, enter the following at the command prompt:</span></span>  
  
```  
profiler /S MyServer\MyInstance /T "Standard"  
```  
  
## <a name="see-also"></a><span data-ttu-id="2b2f4-180">См. также:</span><span class="sxs-lookup"><span data-stu-id="2b2f4-180">See Also</span></span>  
 [<span data-ttu-id="2b2f4-181">Справочник по программе командной строки (Database Engine)</span><span class="sxs-lookup"><span data-stu-id="2b2f4-181">Command Prompt Utility Reference &#40;Database Engine&#41;</span></span>](command-prompt-utility-reference-database-engine.md)  
  
  
