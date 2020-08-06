---
title: Программа tablediff | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- comparing data
- tablediff utility
- tables [SQL Server replication]
- table comparisons [SQL Server]
- command prompt utilities [SQL Server], tablediff
- troubleshooting [SQL Server replication], non-convergence
- non-convergence [SQL Server]
ms.assetid: 3c3cb865-7a4d-4d66-98f2-5935e28929fc
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0a23465a7d2c7db53475a6dca81a8471a3b78b50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735709"
---
# <a name="tablediff-utility"></a><span data-ttu-id="764e1-102">tablediff, программа</span><span class="sxs-lookup"><span data-stu-id="764e1-102">tablediff Utility</span></span>
  <span data-ttu-id="764e1-103">Служебная программа **tablediff** используется для сравнения данных в двух таблицах на расхождение и особенно полезна для устранения несоответствия данных в топологии репликации.</span><span class="sxs-lookup"><span data-stu-id="764e1-103">The **tablediff** utility is used to compare the data in two tables for non-convergence, and is particularly useful for troubleshooting non-convergence in a replication topology.</span></span> <span data-ttu-id="764e1-104">Эта программа может запускаться из командной строки или из пакетного файла и служит для выполнения следующих задач:</span><span class="sxs-lookup"><span data-stu-id="764e1-104">This utility can be used from the command prompt or in a batch file to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="764e1-105">Построчное сравнение исходной таблицы в экземпляре [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], выступающем в качестве издателя репликации, и целевой таблицы в одном или нескольких экземплярах [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], выступающих в качестве подписчиков репликации.</span><span class="sxs-lookup"><span data-stu-id="764e1-105">A row by row comparison between a source table in an instance of [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] acting as a replication Publisher and the destination table at one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] acting as replication Subscribers.</span></span>  
  
-   <span data-ttu-id="764e1-106">Быстрое сравнение, сравнивающее только схемы и количество строк.</span><span class="sxs-lookup"><span data-stu-id="764e1-106">Perform a fast comparison by only comparing row counts and schema.</span></span>  
  
-   <span data-ttu-id="764e1-107">Сравнение на уровне столбцов.</span><span class="sxs-lookup"><span data-stu-id="764e1-107">Perform column-level comparisons.</span></span>  
  
-   <span data-ttu-id="764e1-108">Формирование скрипта [!INCLUDE[tsql](../includes/tsql-md.md)] для исправления несоответствий на целевом сервере и обеспечения конвергенции исходной и целевой таблиц.</span><span class="sxs-lookup"><span data-stu-id="764e1-108">Generate a [!INCLUDE[tsql](../includes/tsql-md.md)] script to fix discrepancies at the destination server to bring the source and destination tables into convergence.</span></span>  
  
-   <span data-ttu-id="764e1-109">Запись результатов операции в файл вывода или в таблицу целевой базы данных.</span><span class="sxs-lookup"><span data-stu-id="764e1-109">Log results to an output file or into a table in the destination database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="764e1-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="764e1-110">Syntax</span></span>  
  
```  
  
      tablediff   
[ -? ] |   
{  
        -sourceserversource_server_name[\instance_name]  
        -sourcedatabasesource_database-sourcetablesource_table_name   
    [ -sourceschemasource_schema_name ]  
    [ -sourcepasswordsource_password ]  
    [ -sourceusersource_login ]  
    [ -sourcelocked ]  
        -destinationserverdestination_server_name[\instance_name]  
        -destinationdatabasesubscription_database-destinationtabledestination_table   
    [ -destinationschemadestination_schema_name ]  
    [ -destinationpassworddestination_password ]  
    [ -destinationuserdestination_login ]  
    [ -destinationlocked ]  
    [ -blarge_object_bytes ]   
    [ -bfnumber_of_statements ]   
    [ -c ]   
    [ -dt ]   
    [ -ettable_name ]   
    [ -f [ file_name ] ]   
    [ -ooutput_file_name ]   
    [ -q ]   
    [ -rcnumber_of_retries ]   
    [ -riretry_interval ]   
    [ -strict ]  
    [ -tconnection_timeouts ]   
}  
```  
  
## <a name="arguments"></a><span data-ttu-id="764e1-111">Аргументы</span><span class="sxs-lookup"><span data-stu-id="764e1-111">Arguments</span></span>  
 <span data-ttu-id="764e1-112">[ **-?**</span><span class="sxs-lookup"><span data-stu-id="764e1-112">[ **-?**</span></span> <span data-ttu-id="764e1-113">]</span><span class="sxs-lookup"><span data-stu-id="764e1-113">]</span></span>  
 <span data-ttu-id="764e1-114">Возвращает список поддерживаемых параметров.</span><span class="sxs-lookup"><span data-stu-id="764e1-114">Returns the list of supported parameters.</span></span>  
  
 <span data-ttu-id="764e1-115">**-sourceServer** *source_server_name*[ **\\** _instance_name_]</span><span class="sxs-lookup"><span data-stu-id="764e1-115">**-sourceserver** *source_server_name*[**\\**_instance_name_]</span></span>  
 <span data-ttu-id="764e1-116">Имя исходного сервера.</span><span class="sxs-lookup"><span data-stu-id="764e1-116">Is the name of the source server.</span></span> <span data-ttu-id="764e1-117">Укажите _ \_ \_ имя исходного сервера_ для экземпляра по умолчанию [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="764e1-117">Specify _source\_server\_name_ for the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="764e1-118">Укажите _ \_ \_ _ **\\** _ \_ имя экземпляра_ исходного сервера для именованного экземпляра [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="764e1-118">Specify _source\_server\_name_**\\**_instance\_name_ for a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="764e1-119">**-sourcedatabase** *source_database*</span><span class="sxs-lookup"><span data-stu-id="764e1-119">**-sourcedatabase** *source_database*</span></span>  
 <span data-ttu-id="764e1-120">Имя базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="764e1-120">Is the name of the source database.</span></span>  
  
 <span data-ttu-id="764e1-121">**-sourcetable** *source_table_name*</span><span class="sxs-lookup"><span data-stu-id="764e1-121">**-sourcetable** *source_table_name*</span></span>  
 <span data-ttu-id="764e1-122">Имя проверяемой исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="764e1-122">Is the name of the source table being checked.</span></span>  
  
 <span data-ttu-id="764e1-123">**-sourceschema** *source_schema_name*</span><span class="sxs-lookup"><span data-stu-id="764e1-123">**-sourceschema** *source_schema_name*</span></span>  
 <span data-ttu-id="764e1-124">Владелец схемы исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="764e1-124">The schema owner of the source table.</span></span> <span data-ttu-id="764e1-125">Владельцем таблицы по умолчанию считается dbo.</span><span class="sxs-lookup"><span data-stu-id="764e1-125">By default, the table owner is assumed to be dbo.</span></span>  
  
 <span data-ttu-id="764e1-126">**-sourcepassword** *source_password*</span><span class="sxs-lookup"><span data-stu-id="764e1-126">**-sourcepassword** *source_password*</span></span>  
 <span data-ttu-id="764e1-127">Пароль для имени входа, используемого для подключения к исходному серверу с помощью проверки подлинности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="764e1-127">Is the password for the login used to connect to the source server using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="764e1-128">По возможности указывайте учетные данные во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="764e1-128">When possible, supply security credentials at runtime.</span></span> <span data-ttu-id="764e1-129">Если необходимо хранить учетные данные в файле скрипта, необходимо обеспечить его безопасность, чтобы предотвратить несанкционированный доступ.</span><span class="sxs-lookup"><span data-stu-id="764e1-129">If you must store credentials in a script file, you should secure the file to prevent unauthorized access.</span></span>  
  
 <span data-ttu-id="764e1-130">**-sourceuser** *source_login*</span><span class="sxs-lookup"><span data-stu-id="764e1-130">**-sourceuser** *source_login*</span></span>  
 <span data-ttu-id="764e1-131">Имя входа, используемое для подключения к исходному серверу с помощью проверки подлинности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="764e1-131">Is the login used to connect to the source server using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="764e1-132">Если *исходное_имя_входа* не указано, для соединения с исходным сервером используется проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="764e1-132">If *source_login* is not supplied, then Windows Authentication is used when connecting to the source server.</span></span> [!INCLUDE[ssNoteWinAuthentication](../includes/ssnotewinauthentication-md.md)]  
  
 <span data-ttu-id="764e1-133">**-sourcelocked**</span><span class="sxs-lookup"><span data-stu-id="764e1-133">**-sourcelocked**</span></span>  
 <span data-ttu-id="764e1-134">Исходная таблица блокируется в ходе сравнения при помощи табличных подсказок TABLOCK и HOLDLOCK.</span><span class="sxs-lookup"><span data-stu-id="764e1-134">The source table is locked during the comparison using the TABLOCK and HOLDLOCK table hints.</span></span>  
  
 <span data-ttu-id="764e1-135">**-DestinationServer** *destination_server_name*[ **\\** _ \_ имя экземпляра_]</span><span class="sxs-lookup"><span data-stu-id="764e1-135">**-destinationserver** *destination_server_name*[**\\**_instance\_name_]</span></span>  
 <span data-ttu-id="764e1-136">Имя целевого сервера.</span><span class="sxs-lookup"><span data-stu-id="764e1-136">Is the name of the destination server.</span></span> <span data-ttu-id="764e1-137">Укажите *имя_целевого_сервера* для экземпляра [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="764e1-137">Specify *destination_server_name* for the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="764e1-138">Укажите _ \_ \_ _ **\\** _ \_ имя экземпляра_ сервера назначения для именованного экземпляра [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="764e1-138">Specify _destination\_server\_name_**\\**_instance\_name_ for a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="764e1-139">**-destinationdatabase** *subscription_database*</span><span class="sxs-lookup"><span data-stu-id="764e1-139">**-destinationdatabase** *subscription_database*</span></span>  
 <span data-ttu-id="764e1-140">Имя целевой базы данных.</span><span class="sxs-lookup"><span data-stu-id="764e1-140">Is the name of the destination database.</span></span>  
  
 <span data-ttu-id="764e1-141">**-destinationtable** *destination_table*</span><span class="sxs-lookup"><span data-stu-id="764e1-141">**-destinationtable** *destination_table*</span></span>  
 <span data-ttu-id="764e1-142">Имя целевой таблицы.</span><span class="sxs-lookup"><span data-stu-id="764e1-142">Is the name of the destination table.</span></span>  
  
 <span data-ttu-id="764e1-143">**-destinationschema** *destination_schema_name*</span><span class="sxs-lookup"><span data-stu-id="764e1-143">**-destinationschema** *destination_schema_name*</span></span>  
 <span data-ttu-id="764e1-144">Владелец схемы целевой таблицы.</span><span class="sxs-lookup"><span data-stu-id="764e1-144">The schema owner of the destination table.</span></span> <span data-ttu-id="764e1-145">Владельцем таблицы по умолчанию считается dbo.</span><span class="sxs-lookup"><span data-stu-id="764e1-145">By default, the table owner is assumed to be dbo.</span></span>  
  
 <span data-ttu-id="764e1-146">**-destinationpassword** *destination_password*</span><span class="sxs-lookup"><span data-stu-id="764e1-146">**-destinationpassword** *destination_password*</span></span>  
 <span data-ttu-id="764e1-147">Пароль для имени входа, используемого для подключения к целевому серверу с помощью проверки подлинности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="764e1-147">Is the password for the login used to connect to the destination server using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="764e1-148">По возможности указывайте учетные данные во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="764e1-148">When possible, supply security credentials at runtime.</span></span> <span data-ttu-id="764e1-149">Если необходимо хранить учетные данные в файле скрипта, необходимо обеспечить его безопасность, чтобы предотвратить несанкционированный доступ.</span><span class="sxs-lookup"><span data-stu-id="764e1-149">If you must store credentials in a script file, you should secure the file to prevent unauthorized access.</span></span>  
  
 <span data-ttu-id="764e1-150">**-destinationuser** *destination_login*</span><span class="sxs-lookup"><span data-stu-id="764e1-150">**-destinationuser** *destination_login*</span></span>  
 <span data-ttu-id="764e1-151">Имя входа, используемое для подключения к целевому серверу с помощью проверки подлинности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="764e1-151">Is the login used to connect to the destination server using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="764e1-152">Если *целевое_имя_входа* не указано, для соединения с исходным сервером используется проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="764e1-152">If *destination_login* is not supplied, then Windows Authentication is used when connecting to the server.</span></span> [!INCLUDE[ssNoteWinAuthentication](../includes/ssnotewinauthentication-md.md)]  
  
 <span data-ttu-id="764e1-153">**-destinationlocked**</span><span class="sxs-lookup"><span data-stu-id="764e1-153">**-destinationlocked**</span></span>  
 <span data-ttu-id="764e1-154">Целевая таблица блокируется в ходе сравнения при помощи табличных указаний TABLOCK и HOLDLOCK.</span><span class="sxs-lookup"><span data-stu-id="764e1-154">The destination table is locked during the comparison using the TABLOCK and HOLDLOCK table hints.</span></span>  
  
 <span data-ttu-id="764e1-155">**-b** *large_object_bytes*</span><span class="sxs-lookup"><span data-stu-id="764e1-155">**-b** *large_object_bytes*</span></span>  
 <span data-ttu-id="764e1-156">Число байтов для сравнения столбцов, содержащих данные типа больших объектов, к которым относятся: `text`, `ntext`, `image`, `varchar(max)`, `nvarchar(max)` и `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="764e1-156">Is the number of bytes to compare for large object data type columns, which includes: `text`, `ntext`, `image`, `varchar(max)`, `nvarchar(max)` and `varbinary(max)`.</span></span> <span data-ttu-id="764e1-157">*число_байтов_больших_объектов* по умолчанию имеет размер столбца.</span><span class="sxs-lookup"><span data-stu-id="764e1-157">*large_object_bytes* defaults to the size of the column.</span></span> <span data-ttu-id="764e1-158">Любые данные, размер которых превышает значение *число_байтов_больших_объектов* , не учитываются при сравнении.</span><span class="sxs-lookup"><span data-stu-id="764e1-158">Any data above *large_object_bytes* will not be compared.</span></span>  
  
 <span data-ttu-id="764e1-159">**-bf**  *number_of_statements*</span><span class="sxs-lookup"><span data-stu-id="764e1-159">**-bf**  *number_of_statements*</span></span>  
 <span data-ttu-id="764e1-160">Число инструкций [!INCLUDE[tsql](../includes/tsql-md.md)] для записи в текущий файл скрипта [!INCLUDE[tsql](../includes/tsql-md.md)] при использовании параметра **-f** .</span><span class="sxs-lookup"><span data-stu-id="764e1-160">Is the number of [!INCLUDE[tsql](../includes/tsql-md.md)] statements to write to the current [!INCLUDE[tsql](../includes/tsql-md.md)] script file when the **-f** option is used.</span></span> <span data-ttu-id="764e1-161">Когда число инструкций [!INCLUDE[tsql](../includes/tsql-md.md)] превышает значение *число_инструкций*, создается новый файл скрипта [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="764e1-161">When the number of [!INCLUDE[tsql](../includes/tsql-md.md)] statements exceeds *number_of_statements*, a new [!INCLUDE[tsql](../includes/tsql-md.md)] script file is created.</span></span>  
  
 <span data-ttu-id="764e1-162">**-c**</span><span class="sxs-lookup"><span data-stu-id="764e1-162">**-c**</span></span>  
 <span data-ttu-id="764e1-163">Сравнение на уровне столбцов.</span><span class="sxs-lookup"><span data-stu-id="764e1-163">Compare column-level differences.</span></span>  
  
 <span data-ttu-id="764e1-164">**-dt**</span><span class="sxs-lookup"><span data-stu-id="764e1-164">**-dt**</span></span>  
 <span data-ttu-id="764e1-165">Удаление таблицы результатов, указанной в аргументе *имя_таблицы*, если она уже существует.</span><span class="sxs-lookup"><span data-stu-id="764e1-165">Drop the result table specified by *table_name*, if the table already exists.</span></span>  
  
 <span data-ttu-id="764e1-166">**-et** *table_name*</span><span class="sxs-lookup"><span data-stu-id="764e1-166">**-et** *table_name*</span></span>  
 <span data-ttu-id="764e1-167">Имя создаваемой таблицы результатов.</span><span class="sxs-lookup"><span data-stu-id="764e1-167">Specifies the name of the result table to create.</span></span> <span data-ttu-id="764e1-168">Если таблица уже существует, необходимо использовать аргумент **-DT** , иначе операция завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="764e1-168">If this table already exists, **-DT** must be used or the operation will fail.</span></span>  
  
 <span data-ttu-id="764e1-169">**-f** [ *имя_файла* ]</span><span class="sxs-lookup"><span data-stu-id="764e1-169">**-f** [ *file_name* ]</span></span>  
 <span data-ttu-id="764e1-170">Формирует скрипт [!INCLUDE[tsql](../includes/tsql-md.md)] , по которому обеспечивается конвергенция таблицы на целевом сервере и таблицы на исходном сервере.</span><span class="sxs-lookup"><span data-stu-id="764e1-170">Generates a [!INCLUDE[tsql](../includes/tsql-md.md)] script to bring the table at the destination server into convergence with the table at the source server.</span></span> <span data-ttu-id="764e1-171">Можно дополнительно указать имя и путь для создаваемого файла скрипта [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="764e1-171">You can optionally specify a name and path for the generated [!INCLUDE[tsql](../includes/tsql-md.md)] script file.</span></span> <span data-ttu-id="764e1-172">Если параметр *имя_файла* не указан, файл скрипта [!INCLUDE[tsql](../includes/tsql-md.md)] создается в каталоге, в котором запущена данная программа.</span><span class="sxs-lookup"><span data-stu-id="764e1-172">If *file_name* is not specified, the [!INCLUDE[tsql](../includes/tsql-md.md)] script file is generated in the directory where the utility runs.</span></span>  
  
 <span data-ttu-id="764e1-173">**-o** *output_file_name*</span><span class="sxs-lookup"><span data-stu-id="764e1-173">**-o** *output_file_name*</span></span>  
 <span data-ttu-id="764e1-174">Полное имя и путь файла вывода.</span><span class="sxs-lookup"><span data-stu-id="764e1-174">Is the full name and path of the output file.</span></span>  
  
 <span data-ttu-id="764e1-175">**-q**</span><span class="sxs-lookup"><span data-stu-id="764e1-175">**-q**</span></span>  
 <span data-ttu-id="764e1-176">Быстрое сравнение, сравнивающее только схемы и количество строк.</span><span class="sxs-lookup"><span data-stu-id="764e1-176">Perform a fast comparison by only comparing row counts and schema.</span></span>  
  
 <span data-ttu-id="764e1-177">**-rc** *number_of_retries*</span><span class="sxs-lookup"><span data-stu-id="764e1-177">**-rc** *number_of_retries*</span></span>  
 <span data-ttu-id="764e1-178">Количество попыток повтора программой неудачно завершившейся операции.</span><span class="sxs-lookup"><span data-stu-id="764e1-178">Number of times that the utility retries a failed operation.</span></span>  
  
 <span data-ttu-id="764e1-179">**-ri**  *retry_interval*</span><span class="sxs-lookup"><span data-stu-id="764e1-179">**-ri**  *retry_interval*</span></span>  
 <span data-ttu-id="764e1-180">Интервал в секундах между повторными попытками.</span><span class="sxs-lookup"><span data-stu-id="764e1-180">Interval, in seconds, to wait between retries.</span></span>  
  
 <span data-ttu-id="764e1-181">**-strict**</span><span class="sxs-lookup"><span data-stu-id="764e1-181">**-strict**</span></span>  
 <span data-ttu-id="764e1-182">Строгая проверка исходной и целевой схем.</span><span class="sxs-lookup"><span data-stu-id="764e1-182">Source and destination schema are strictly compared.</span></span>  
  
 <span data-ttu-id="764e1-183">**-t** *connection_timeouts*</span><span class="sxs-lookup"><span data-stu-id="764e1-183">**-t** *connection_timeouts*</span></span>  
 <span data-ttu-id="764e1-184">Устанавливает время ожидания в секундах для соединений с исходным сервером и целевым сервером.</span><span class="sxs-lookup"><span data-stu-id="764e1-184">Sets the connection timeout period, in seconds, for connections to the source server and destination server.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="764e1-185">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="764e1-185">Return Value</span></span>  
  
|<span data-ttu-id="764e1-186">Значение</span><span class="sxs-lookup"><span data-stu-id="764e1-186">Value</span></span>|<span data-ttu-id="764e1-187">Описание</span><span class="sxs-lookup"><span data-stu-id="764e1-187">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="764e1-188">**0**</span><span class="sxs-lookup"><span data-stu-id="764e1-188">**0**</span></span>|<span data-ttu-id="764e1-189">Успешно</span><span class="sxs-lookup"><span data-stu-id="764e1-189">Success</span></span>|  
|<span data-ttu-id="764e1-190">**1**</span><span class="sxs-lookup"><span data-stu-id="764e1-190">**1**</span></span>|<span data-ttu-id="764e1-191">Критическая ошибка</span><span class="sxs-lookup"><span data-stu-id="764e1-191">Critical error</span></span>|  
|<span data-ttu-id="764e1-192">**2**</span><span class="sxs-lookup"><span data-stu-id="764e1-192">**2**</span></span>|<span data-ttu-id="764e1-193">Различия таблиц</span><span class="sxs-lookup"><span data-stu-id="764e1-193">Table differences</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="764e1-194">Remarks</span><span class="sxs-lookup"><span data-stu-id="764e1-194">Remarks</span></span>  
 <span data-ttu-id="764e1-195">Служебную программу **tablediff** нельзя использовать с серверами, отличными от [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="764e1-195">The **tablediff** utility cannot be used with non-[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] servers.</span></span>  
  
 <span data-ttu-id="764e1-196">Таблицы со столбцами с данными типа `sql_variant` не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="764e1-196">Tables with `sql_variant` data type columns are not supported.</span></span>  
  
 <span data-ttu-id="764e1-197">По умолчанию служебная программа **tablediff** поддерживает перечисленные ниже сопоставления типов данных между исходными и целевыми столбцами.</span><span class="sxs-lookup"><span data-stu-id="764e1-197">By default, the **tablediff** utility supports the following data type mappings between source and destination columns.</span></span>  
  
|<span data-ttu-id="764e1-198">Тип данных источника</span><span class="sxs-lookup"><span data-stu-id="764e1-198">Source data type</span></span>|<span data-ttu-id="764e1-199">Тип данных назначения</span><span class="sxs-lookup"><span data-stu-id="764e1-199">Destination data type</span></span>|  
|----------------------|---------------------------|  
|`tinyint`|<span data-ttu-id="764e1-200">`smallint`, `int` или `bigint`</span><span class="sxs-lookup"><span data-stu-id="764e1-200">`smallint`, `int`, or `bigint`</span></span>|  
|`smallint`|<span data-ttu-id="764e1-201">`int` или `bigint`</span><span class="sxs-lookup"><span data-stu-id="764e1-201">`int` or `bigint`</span></span>|  
|`int`|`bigint`|  
|`timestamp`|`varbinary`|  
|`varchar(max)`|`text`|  
|`nvarchar(max)`|`ntext`|  
|`varbinary(max)`|`image`|  
|`text`|`varchar(max)`|  
|`ntext`|`nvarchar(max)`|  
|`image`|`varbinary(max)`|  
  
 <span data-ttu-id="764e1-202">Параметр **-strict** запрещает такое сопоставление и выполняет строгую проверку.</span><span class="sxs-lookup"><span data-stu-id="764e1-202">Use the **-strict** option to disallow these mappings and perform a strict validation.</span></span>  
  
 <span data-ttu-id="764e1-203">Исходная таблица при данном сравнении должна содержать хотя бы один столбец первичного ключа, столбец идентификаторов или столбец ROWGUID.</span><span class="sxs-lookup"><span data-stu-id="764e1-203">The source table in the comparison must contain at least one primary key, identity, or ROWGUID column.</span></span> <span data-ttu-id="764e1-204">При использовании параметра **-strict** целевая таблица также должна содержать столбец первичного ключа, столбец идентификаторов или столбец ROWGUID.</span><span class="sxs-lookup"><span data-stu-id="764e1-204">When you use the **-strict** option, the destination table must also have a primary key, identity, or ROWGUID column.</span></span>  
  
 <span data-ttu-id="764e1-205">Скрипт [!INCLUDE[tsql](../includes/tsql-md.md)] , создаваемый для приведения целевой таблицы в состояние конвергенции, не включает следующие типы данных:</span><span class="sxs-lookup"><span data-stu-id="764e1-205">The [!INCLUDE[tsql](../includes/tsql-md.md)] script generated to bring the destination table into convergence does not include the following data types:</span></span>  
  
-   `varchar(max)`  
  
-   `nvarchar(max)`  
  
-   `varbinary(max)`  
  
-   `timestamp`  
  
-   <span data-ttu-id="764e1-206">**xml**</span><span class="sxs-lookup"><span data-stu-id="764e1-206">**xml**</span></span>  
  
-   `text`  
  
-   `ntext`  
  
-   `image`  
  
## <a name="permissions"></a><span data-ttu-id="764e1-207">Разрешения</span><span class="sxs-lookup"><span data-stu-id="764e1-207">Permissions</span></span>  
 <span data-ttu-id="764e1-208">Для сравнения таблиц на сравниваемые объекты таблиц необходимо иметь разрешения SELECT ALL.</span><span class="sxs-lookup"><span data-stu-id="764e1-208">To compare tables, you need SELECT ALL permissions on the table objects being compared.</span></span>  
  
 <span data-ttu-id="764e1-209">Для использования параметра **-et** необходимо быть членом предопределенной роли базы данных db_owner или как минимум иметь разрешение CREATE TABLE в базе данных подписки и разрешение ALTER на схему конечного владельца на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="764e1-209">To use the **-et** option, you must be a member of the db_owner fixed database role, or at least have CREATE TABLE permission in the subscription database and ALTER permission on the destination owner schema at the destination server.</span></span>  
  
 <span data-ttu-id="764e1-210">Для использования параметра **-dt** необходимо быть членом предопределенной роли базы данных db_owner или как минимум иметь разрешение ALTER на схему конечного владельца на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="764e1-210">To use the **-dt** option, you must be a member of the db_owner fixed database role, or at least have ALTER permission on the destination owner schema at the destination server.</span></span>  
  
 <span data-ttu-id="764e1-211">Чтобы использовать параметр **-o** или **-f** , необходимо иметь разрешения на запись в указанный каталог файлов.</span><span class="sxs-lookup"><span data-stu-id="764e1-211">To use the **-o** or **-f** options, you must have write permissions to the specified file directory location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="764e1-212">См. также:</span><span class="sxs-lookup"><span data-stu-id="764e1-212">See Also</span></span>  
 [<span data-ttu-id="764e1-213">Сравнение реплицируемых таблиц на предмет различий (программирование репликации)</span><span class="sxs-lookup"><span data-stu-id="764e1-213">Compare Replicated Tables for Differences &#40;Replication Programming&#41;</span></span>](../relational-databases/replication/administration/compare-replicated-tables-for-differences-replication-programming.md)  
  
  
