---
title: Расширения в AdventureWorks для демонстрации выполняющейся в памяти OLTP | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 0186b7f2-cead-4203-8360-b6890f37cde8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 73a87751aa6cd4734f81b60cdd87a62939ba4ead
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740316"
---
# <a name="extensions-to-adventureworks-to-demonstrate-in-memory-oltp"></a><span data-ttu-id="8e62d-102">Расширения AdventureWorks для демонстрации In-Memory OLTP</span><span class="sxs-lookup"><span data-stu-id="8e62d-102">Extensions to AdventureWorks to Demonstrate In-Memory OLTP</span></span>
    
## <a name="overview"></a><span data-ttu-id="8e62d-103">Обзор</span><span class="sxs-lookup"><span data-stu-id="8e62d-103">Overview</span></span>  
 <span data-ttu-id="8e62d-104">В этом образце показана новая функция [!INCLUDE[hek_2](../includes/hek-2-md.md)] , входящая в [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e62d-104">This sample showcases the new [!INCLUDE[hek_2](../includes/hek-2-md.md)] feature, which is part of [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span> <span data-ttu-id="8e62d-105">Она показывает оптимизированные для памяти таблицы и скомпилированные в собственном коде хранимые процедуры, с ее помощью можно также продемонстрировать преимущества производительности [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e62d-105">It shows the new memory-optimized tables and natively-compiled stored procedures, and can be used to demonstrate performance benefits of [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8e62d-106">Этот раздел о SQL Server 2016 можно найти в статье [Расширения AdventureWorks для демонстрации In-Memory OLTP](https://msdn.microsoft.com/library/mt465764.aspx).</span><span class="sxs-lookup"><span data-stu-id="8e62d-106">To view this topic for SQL Server 2016, see [Extensions to AdventureWorks to Demonstrate In-Memory OLTP](https://msdn.microsoft.com/library/mt465764.aspx)</span></span>  
  
 <span data-ttu-id="8e62d-107">Пример выполняет преобразование 5 таблиц в базе данных AdventureWorks в оптимизированные для памяти таблицы. В нем также есть демонстрационная рабочая нагрузка в форме обработки заказа на продажу.</span><span class="sxs-lookup"><span data-stu-id="8e62d-107">The sample migrates 5 tables in the AdventureWorks database to memory-optimized, and it includes a demo workload for sales order processing.</span></span> <span data-ttu-id="8e62d-108">С помощью этой демонстрационной рабочей нагрузки можно оценить выигрыш по производительности, который формируется при использовании [!INCLUDE[hek_2](../includes/hek-2-md.md)] на сервере.</span><span class="sxs-lookup"><span data-stu-id="8e62d-108">You can use this demo workload to see the performance benefit of using [!INCLUDE[hek_2](../includes/hek-2-md.md)] on your server.</span></span>  
  
 <span data-ttu-id="8e62d-109">В описании примера рассматриваются компромиссные решения, которые были реализованы при переносе таблиц в [!INCLUDE[hek_2](../includes/hek-2-md.md)] с указанием тех функций, которые (пока еще) не поддерживаются для оптимизированных для памяти таблиц в [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e62d-109">In the description of the sample we discuss the tradeoffs that were made in migrating the tables to [!INCLUDE[hek_2](../includes/hek-2-md.md)] to account for the features that are not (yet) supported for memory-optimized tables in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span>  
  
 <span data-ttu-id="8e62d-110">Документация по этому примеру имеет следующую структуру.</span><span class="sxs-lookup"><span data-stu-id="8e62d-110">The documentation of this sample is structured as follows:</span></span>  
  
-   <span data-ttu-id="8e62d-111">[Предварительные требования](#Prerequisites) для установки примера и выполнения демонстрационной рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="8e62d-111">[Prerequisites](#Prerequisites) for installing the sample and running the demo workload</span></span>  
  
-   <span data-ttu-id="8e62d-112">Инструкции для [Установка образца OLTP в памяти на основе AdventureWorks](#InstallingtheIn-MemoryOLTPsamplebasedonAdventureWorks)</span><span class="sxs-lookup"><span data-stu-id="8e62d-112">Instructions for [Installing the In-Memory OLTP sample based on AdventureWorks](#InstallingtheIn-MemoryOLTPsamplebasedonAdventureWorks)</span></span>  
  
-   <span data-ttu-id="8e62d-113">[Описание образцов таблиц и процедур](#Descriptionofthesampletablesandprocedures) . сюда входят описания таблиц и процедур, добавленных в AdventureWorks [!INCLUDE[hek_2](../includes/hek-2-md.md)] образцом, а также рекомендации по переносу некоторых исходных таблиц AdventureWorks в оптимизированные для памяти</span><span class="sxs-lookup"><span data-stu-id="8e62d-113">[Description of the sample tables and procedures](#Descriptionofthesampletablesandprocedures) - this includes descriptions of the tables and procedures added to AdventureWorks by the [!INCLUDE[hek_2](../includes/hek-2-md.md)] sample, as well as considerations for migrating some of the original AdventureWorks tables to memory-optimized</span></span>  
  
-   <span data-ttu-id="8e62d-114">Инструкции по выполнению [Измерение производительности с помощью демонстрационной рабочей нагрузки](#PerformanceMeasurementsusingtheDemoWorkload) — сюда входят инструкции по установке и запуску ostress — средства, используемого для формирования рабочей нагрузки, а также по выполнению самой рабочей нагрузки</span><span class="sxs-lookup"><span data-stu-id="8e62d-114">Instructions for performing [Performance Measurements using the Demo Workload](#PerformanceMeasurementsusingtheDemoWorkload) - this includes instructions for installing and running ostress, a tool using for driving the workload, as well as running the demo workload itself</span></span>  
  
-   [<span data-ttu-id="8e62d-115">Использование памяти и места на диске образцом</span><span class="sxs-lookup"><span data-stu-id="8e62d-115">Memory and Disk Space Utilization in the Sample</span></span>](#MemoryandDiskSpaceUtilizationintheSample)  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="8e62d-116">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="8e62d-116">Prerequisites</span></span>  
  
-   [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]<span data-ttu-id="8e62d-117">RTM — ознакомительная версия, Developer или Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="8e62d-117">RTM - Evaluation, Developer, or Enterprise edition</span></span>  
  
-   <span data-ttu-id="8e62d-118">Для тестирования производительности требуется сервер, имеющий те же характеристики, что и в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="8e62d-118">For performance testing, a server with specifications similar to your production environment.</span></span> <span data-ttu-id="8e62d-119">Для этого конкретного примера должно быть доступно по меньшей мере 16 ГБ памяти в [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e62d-119">For this particular sample you should have at least 16GB of memory available to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8e62d-120">Общие рекомендации по оборудованию для [!INCLUDE[hek_2](../includes/hek-2-md.md)] см. в следующей записи блога:[https://cloudblogs.microsoft.com/sqlserver/2013/08/01/hardware-considerations-for-in-memory-oltp-in-sql-server-2014/](https://cloudblogs.microsoft.com/sqlserver/2013/08/01/hardware-considerations-for-in-memory-oltp-in-sql-server-2014/)</span><span class="sxs-lookup"><span data-stu-id="8e62d-120">For general guidelines on hardware for [!INCLUDE[hek_2](../includes/hek-2-md.md)], see the following blog post:[https://cloudblogs.microsoft.com/sqlserver/2013/08/01/hardware-considerations-for-in-memory-oltp-in-sql-server-2014/](https://cloudblogs.microsoft.com/sqlserver/2013/08/01/hardware-considerations-for-in-memory-oltp-in-sql-server-2014/)</span></span>  
  
##  <a name="installing-the-hek_2-sample-based-on-adventureworks"></a><a name="InstallingtheIn-MemoryOLTPsamplebasedonAdventureWorks"></a><span data-ttu-id="8e62d-121">Установка [!INCLUDE[hek_2](../includes/hek-2-md.md)] образца на основе AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="8e62d-121">Installing the [!INCLUDE[hek_2](../includes/hek-2-md.md)] sample based on AdventureWorks</span></span>  
 <span data-ttu-id="8e62d-122">Чтобы установить образец, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="8e62d-122">Follow these steps to install the sample:</span></span>  
  
1.  <span data-ttu-id="8e62d-123">Скачайте архив с полной резервной копией базы данных AdventureWorks2014:</span><span class="sxs-lookup"><span data-stu-id="8e62d-123">Download the archive for the full backup of the AdventureWorks2014 database:</span></span>  
  
    1.  <span data-ttu-id="8e62d-124">Откройте следующее: [https://msftdbprodsamples.codeplex.com/downloads/get/880661](https://msftdbprodsamples.codeplex.com/downloads/get/880661) .</span><span class="sxs-lookup"><span data-stu-id="8e62d-124">Open the following: [https://msftdbprodsamples.codeplex.com/downloads/get/880661](https://msftdbprodsamples.codeplex.com/downloads/get/880661).</span></span>  
  
    2.  <span data-ttu-id="8e62d-125">При запросе сохраните файл в локальную папку.</span><span class="sxs-lookup"><span data-stu-id="8e62d-125">When prompted to save the file to a local folder.</span></span>  
  
2.  <span data-ttu-id="8e62d-126">Извлеките файл **AdventureWorks2014.bak** в локальную папку, например "c:\temp".</span><span class="sxs-lookup"><span data-stu-id="8e62d-126">Extract the **AdventureWorks2014.bak** file to a local folder, for example 'c:\temp'.</span></span>  
  
3.  <span data-ttu-id="8e62d-127">Восстановите резервную копию базы данных с помощью [!INCLUDE[tsql](../includes/tsql-md.md)] или в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e62d-127">Restore the database backup using [!INCLUDE[tsql](../includes/tsql-md.md)] or [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]:</span></span>  
  
    1.  <span data-ttu-id="8e62d-128">Задайте целевую папку и имя для файла данных, например</span><span class="sxs-lookup"><span data-stu-id="8e62d-128">Identify the target folder and filename for the data file, for example</span></span>  
  
         <span data-ttu-id="8e62d-129">"h:\DATA\AdventureWorks2014_Data.mdf"</span><span class="sxs-lookup"><span data-stu-id="8e62d-129">'h:\DATA\AdventureWorks2014_Data.mdf'</span></span>  
  
    2.  <span data-ttu-id="8e62d-130">Задайте целевую папку и имя для файла журнала, например</span><span class="sxs-lookup"><span data-stu-id="8e62d-130">Identify the target folder and filename for the log file, for example</span></span>  
  
         <span data-ttu-id="8e62d-131">"i:\DATA\AdventureWorks2014_log.ldf"</span><span class="sxs-lookup"><span data-stu-id="8e62d-131">'i:\DATA\AdventureWorks2014_log.ldf'</span></span>  
  
        1.  <span data-ttu-id="8e62d-132">Файл журнала следует разместить на диске, отличном от того, на котором находится файл данных. В идеале для обеспечения максимальной производительности это должен быть высокоскоростной диск, например хранилище SSD или PCI.</span><span class="sxs-lookup"><span data-stu-id="8e62d-132">The log file should be placed on a different drive than the data file, ideally a low latency drive such as an SSD or PCIe storage, for maximum performance.</span></span>  
  
     <span data-ttu-id="8e62d-133">Пример скрипта T-SQL:</span><span class="sxs-lookup"><span data-stu-id="8e62d-133">Example T-SQL script:</span></span>  
  
    ```  
    RESTORE DATABASE [AdventureWorks2014]   
      FROM DISK = N'C:\temp\AdventureWorks2014.bak'   
        WITH FILE = 1,    
      MOVE N'AdventureWorks2014_Data' TO N'h:\DATA\AdventureWorks2014_Data.mdf',    
      MOVE N'AdventureWorks2014_Log' TO N'i:\DATA\AdventureWorks2014_log.ldf'  
     GO  
    ```  
  
4.  <span data-ttu-id="8e62d-134">Смените владельца базы данных на имя входа на сервере, выполнив следующую команду в окне запроса среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="8e62d-134">Change the database owner to a login on your server, by running the following command in the query window of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]:</span></span>  
  
    ```  
    ALTER AUTHORIZATION ON DATABASE::AdventureWorks2014 TO [<NewLogin>]  
    ```  
  
5.  <span data-ttu-id="8e62d-135">Скачайте пример скрипта [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] Sample. SQL из [примера SQL Server 2014 RTM в памяти для OLTP в](https://go.microsoft.com/fwlink/?LinkID=396372) локальную папку.</span><span class="sxs-lookup"><span data-stu-id="8e62d-135">Download the sample script '[!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] Sample.sql' from [SQL Server 2014 RTM In-Memory OLTP Sample](https://go.microsoft.com/fwlink/?LinkID=396372) to a local folder.</span></span>  
  
6.  <span data-ttu-id="8e62d-136">Обновите значение переменной "checkpoint_files_location" в скрипте " [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] Sample. SQL", чтобы указать целевое расположение для [!INCLUDE[hek_2](../includes/hek-2-md.md)] файлов контрольных точек.</span><span class="sxs-lookup"><span data-stu-id="8e62d-136">Update the value for the variable 'checkpoint_files_location' in the script '[!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] Sample.sql', to point to the target location for the [!INCLUDE[hek_2](../includes/hek-2-md.md)] checkpoint files.</span></span> <span data-ttu-id="8e62d-137">Файлы контрольных точек следует разместить на диске с высокой производительностью последовательного ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="8e62d-137">The checkpoint files should be placed on a drive with good sequential IO performance.</span></span>  
  
     <span data-ttu-id="8e62d-138">Обновите значение переменной "database_name", чтобы указать на базу данных AdventureWorks2014.</span><span class="sxs-lookup"><span data-stu-id="8e62d-138">Update the value for the variable 'database_name' to point to the AdventureWorks2014 database.</span></span>  
  
    1.  <span data-ttu-id="8e62d-139">Не забудьте добавить обратную косую черту \' как часть имени пути</span><span class="sxs-lookup"><span data-stu-id="8e62d-139">Be sure to include the backslash '\' as part of the path name</span></span>  
  
    2.  <span data-ttu-id="8e62d-140">Пример.</span><span class="sxs-lookup"><span data-stu-id="8e62d-140">Example:</span></span>  
  
        ```  
        :setvar checkpoint_files_location "d:\DBData\"  
        ...  
        :setvar database_name "AdventureWorks2014"  
        ```  
  
7.  <span data-ttu-id="8e62d-141">Запустите образец скрипта на выполнение одним из двух способов.</span><span class="sxs-lookup"><span data-stu-id="8e62d-141">Execute the sample script, in one of two ways:</span></span>  
  
    1.  <span data-ttu-id="8e62d-142">С помощью программы командной строки sqlcmd.</span><span class="sxs-lookup"><span data-stu-id="8e62d-142">Using the sqlcmd command-line utility.</span></span> <span data-ttu-id="8e62d-143">Например, выполнив следующую команду из командной строки в папке со скриптом:</span><span class="sxs-lookup"><span data-stu-id="8e62d-143">For example, for example by running the following command from the command-line prompt in the folder containing the script:</span></span>  
  
        ```  
        sqlcmd -S . -E -i "ssSQL14 RTM hek_2 Sample.sql"  
        ```  
  
    2.  <span data-ttu-id="8e62d-144">В среде Management Studio:</span><span class="sxs-lookup"><span data-stu-id="8e62d-144">Using Management Studio:</span></span>  
  
        1.  <span data-ttu-id="8e62d-145">Откройте скрипт " [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] Sample. SQL" в окне запроса</span><span class="sxs-lookup"><span data-stu-id="8e62d-145">Open the script '[!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] Sample.sql' in a query window</span></span>  
  
        2.  <span data-ttu-id="8e62d-146">Подключитесь к целевому серверу, на котором находится база данных AdventureWorks2014</span><span class="sxs-lookup"><span data-stu-id="8e62d-146">Connect to the target server that contains the database AdventureWorks2014</span></span>  
  
        3.  <span data-ttu-id="8e62d-147">Включите режим SQLCMD, щелкнув "запрос-> режим SQLCMD"</span><span class="sxs-lookup"><span data-stu-id="8e62d-147">Enable SQLCMD Mode, by clicking on 'Query -> SQLCMD Mode'</span></span>  
  
        4.  <span data-ttu-id="8e62d-148">Нажмите кнопку "выполнить", чтобы запустить скрипт.</span><span class="sxs-lookup"><span data-stu-id="8e62d-148">Click the button 'Execute' to run the script</span></span>  
  
##  <a name="description-of-the-sample-tables-and-procedures"></a><a name="Descriptionofthesampletablesandprocedures"></a> <span data-ttu-id="8e62d-149">Описание образцов таблиц и процедур</span><span class="sxs-lookup"><span data-stu-id="8e62d-149">Description of the sample tables and procedures</span></span>  
 <span data-ttu-id="8e62d-150">Образец создает новые таблицы для продуктов и заказов на продажу на основе существующих в базе данных AdventureWorks таблиц.</span><span class="sxs-lookup"><span data-stu-id="8e62d-150">The sample creates new tables for products and sales orders, based on existing tables in AdventureWorks.</span></span> <span data-ttu-id="8e62d-151">Схема новых таблиц похожа на схему существующих таблиц, а несколько различий в схемах описаны далее.</span><span class="sxs-lookup"><span data-stu-id="8e62d-151">The schema of the new tables is similar to the existing tables, with a few differences, as explained below.</span></span>  
  
 <span data-ttu-id="8e62d-152">Новые оптимизированные для памяти таблицы имеют суффикс "_inmem".</span><span class="sxs-lookup"><span data-stu-id="8e62d-152">The new memory-optimized tables carry the suffix '_inmem'.</span></span> <span data-ttu-id="8e62d-153">В образце также есть соответствующие таблицы с суффиксом "_ondisk" — эти таблицы можно использовать для сравнения "один к одному" между производительностью оптимизированных для памяти таблиц и таблиц на диске в системе.</span><span class="sxs-lookup"><span data-stu-id="8e62d-153">The sample also includes corresponding tables carrying the suffix '_ondisk' - these tables can be used to make a one-to-one comparison between the performance of memory-optimized tables and disk-based tables on your system..</span></span>  
  
 <span data-ttu-id="8e62d-154">Обратите внимание, что оптимизированные для памяти таблицы, используемые в рабочей нагрузке для сравнения производительности, являются полностью устойчивыми и работают с полным протоколированием.</span><span class="sxs-lookup"><span data-stu-id="8e62d-154">Note that the memory-optimized tables used in the workload for performance comparison are fully durable and fully logged.</span></span> <span data-ttu-id="8e62d-155">Для повышения производительности они не жертвуют устойчивостью или надежностью.</span><span class="sxs-lookup"><span data-stu-id="8e62d-155">They do not sacrifice durability or reliability to attain the performance gain.</span></span>  
  
 <span data-ttu-id="8e62d-156">Целевой рабочей нагрузкой для этого образца является обработка заказа на продажу, в рамках которой также учитывается информация о продукте и скидки.</span><span class="sxs-lookup"><span data-stu-id="8e62d-156">The target workload for this sample is sales order processing, where we consider also information about products and discounts.</span></span> <span data-ttu-id="8e62d-157">Для этого используются таблицы SalesOrderHeader, SalesOrderDetail, Product, SpecialOffer и SpecialOfferProduct.</span><span class="sxs-lookup"><span data-stu-id="8e62d-157">To this end, the table SalesOrderHeader, SalesOrderDetail, Product, SpecialOffer, and SpecialOfferProduct.</span></span>  
  
 <span data-ttu-id="8e62d-158">Две новые хранимые процедуры, Sales.usp_InsertSalesOrder_inmem и Sales.usp_UpdateSalesOrderShipInfo_inmem, используются для вставки заказов на продажу и обновления сведений о доставке по данному заказу на продажу.</span><span class="sxs-lookup"><span data-stu-id="8e62d-158">Two new stored procedures, Sales.usp_InsertSalesOrder_inmem and Sales.usp_UpdateSalesOrderShipInfo_inmem, are used to insert sales orders and to update the shipping information of a given sales order.</span></span>  
  
 <span data-ttu-id="8e62d-159">Новая схема «Demo» содержит вспомогательные таблицы и хранимые процедуры для выполнения демонстрационной рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="8e62d-159">The new schema 'Demo' contains helper tables and stored procedures to execute a demo workload.</span></span>  
  
 <span data-ttu-id="8e62d-160">В частности, образец [!INCLUDE[hek_2](../includes/hek-2-md.md)] добавляет в базу данных AdventureWorks следующие объекты:</span><span class="sxs-lookup"><span data-stu-id="8e62d-160">Concretely, the [!INCLUDE[hek_2](../includes/hek-2-md.md)] sample adds the following objects to AdventureWorks:</span></span>  
  
### <a name="tables-added-by-the-sample"></a><span data-ttu-id="8e62d-161">Таблицы, добавляемые образцом</span><span class="sxs-lookup"><span data-stu-id="8e62d-161">Tables added by the sample</span></span>  
  
#### <a name="the-new-tables"></a><span data-ttu-id="8e62d-162">Новые таблицы</span><span class="sxs-lookup"><span data-stu-id="8e62d-162">The New Tables</span></span>  
 <span data-ttu-id="8e62d-163">Sales.SalesOrderHeader_inmem</span><span class="sxs-lookup"><span data-stu-id="8e62d-163">Sales.SalesOrderHeader_inmem</span></span>  
  
-   <span data-ttu-id="8e62d-164">Данные заголовка о заказах на продажу.</span><span class="sxs-lookup"><span data-stu-id="8e62d-164">Header information about sales orders.</span></span> <span data-ttu-id="8e62d-165">Для каждого заказа на продажу в этой таблице есть отдельная строка.</span><span class="sxs-lookup"><span data-stu-id="8e62d-165">Each sales order has one row in this table.</span></span>  
  
 <span data-ttu-id="8e62d-166">Sales.SalesOrderDetail_inmem</span><span class="sxs-lookup"><span data-stu-id="8e62d-166">Sales.SalesOrderDetail_inmem</span></span>  
  
-   <span data-ttu-id="8e62d-167">Подробные сведения заказов на продажу.</span><span class="sxs-lookup"><span data-stu-id="8e62d-167">Details of sales orders.</span></span> <span data-ttu-id="8e62d-168">Для каждого элемента заказа на продажу в этой таблице есть отдельная строка.</span><span class="sxs-lookup"><span data-stu-id="8e62d-168">Each line item of a sales order has one row in this table.</span></span>  
  
 <span data-ttu-id="8e62d-169">Sales.SpecialOffer_inmem</span><span class="sxs-lookup"><span data-stu-id="8e62d-169">Sales.SpecialOffer_inmem</span></span>  
  
-   <span data-ttu-id="8e62d-170">Сведения о специальных предложениях, включая процент скидки, связанный с каждым специальным предложением.</span><span class="sxs-lookup"><span data-stu-id="8e62d-170">Information about special offers, including the discount percentage associated with each special offer.</span></span>  
  
 <span data-ttu-id="8e62d-171">Sales.SpecialOfferProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="8e62d-171">Sales.SpecialOfferProduct_inmem</span></span>  
  
-   <span data-ttu-id="8e62d-172">Ссылочная таблица между специальными предложениями и продуктами.</span><span class="sxs-lookup"><span data-stu-id="8e62d-172">Reference table between special offers and products.</span></span> <span data-ttu-id="8e62d-173">Каждое специальное предложение может включать от нуля и более продуктов, а каждый продукт может содержать нуль и более специальных предложений.</span><span class="sxs-lookup"><span data-stu-id="8e62d-173">Each special offer can feature zero or more products, and each product can be featured in zero or more special offers.</span></span>  
  
 <span data-ttu-id="8e62d-174">Production.Product_inmem</span><span class="sxs-lookup"><span data-stu-id="8e62d-174">Production.Product_inmem</span></span>  
  
-   <span data-ttu-id="8e62d-175">Сведения о продуктах, включая их цену по прейскуранту.</span><span class="sxs-lookup"><span data-stu-id="8e62d-175">Information about products, including their list price.</span></span>  
  
 <span data-ttu-id="8e62d-176">Demo.DemoSalesOrderDetailSeed</span><span class="sxs-lookup"><span data-stu-id="8e62d-176">Demo.DemoSalesOrderDetailSeed</span></span>  
  
-   <span data-ttu-id="8e62d-177">В этой демонстрационной рабочей нагрузке используется для формирования образцов заказов на продажу.</span><span class="sxs-lookup"><span data-stu-id="8e62d-177">Used in the demo workload to construct sample sales orders.</span></span>  
  
 <span data-ttu-id="8e62d-178">Те же таблицы, но находящиеся на диске:</span><span class="sxs-lookup"><span data-stu-id="8e62d-178">Disk-based variations of the tables:</span></span>  
  
-   <span data-ttu-id="8e62d-179">Sales.SalesOrderHeader_ondisk</span><span class="sxs-lookup"><span data-stu-id="8e62d-179">Sales.SalesOrderHeader_ondisk</span></span>  
  
-   <span data-ttu-id="8e62d-180">Sales.SalesOrderDetail_ondisk</span><span class="sxs-lookup"><span data-stu-id="8e62d-180">Sales.SalesOrderDetail_ondisk</span></span>  
  
-   <span data-ttu-id="8e62d-181">Sales.SpecialOffer_ondisk</span><span class="sxs-lookup"><span data-stu-id="8e62d-181">Sales.SpecialOffer_ondisk</span></span>  
  
-   <span data-ttu-id="8e62d-182">Sales.SpecialOfferProduct_ondisk</span><span class="sxs-lookup"><span data-stu-id="8e62d-182">Sales.SpecialOfferProduct_ondisk</span></span>  
  
-   <span data-ttu-id="8e62d-183">Production.Product_ondisk</span><span class="sxs-lookup"><span data-stu-id="8e62d-183">Production.Product_ondisk</span></span>  
  
#### <a name="differences-between-original-disk-based-and-the-and-new-memory-optimized-tables"></a><span data-ttu-id="8e62d-184">Различия между исходными таблицами, находящимися на диске, и новыми, оптимизированными для памяти таблицами</span><span class="sxs-lookup"><span data-stu-id="8e62d-184">Differences between original disk-based and the and new memory-optimized tables</span></span>  
 <span data-ttu-id="8e62d-185">По большей части новые таблицы, представленные в данном образце, состоят из тех же столбцов и используют те же типы данных, что и исходные таблицы.</span><span class="sxs-lookup"><span data-stu-id="8e62d-185">For the most part, the new tables introduced by this sample use the same columns and the same data types as the original tables.</span></span> <span data-ttu-id="8e62d-186">Однако между ними есть несколько различий.</span><span class="sxs-lookup"><span data-stu-id="8e62d-186">However, there are a few differences.</span></span> <span data-ttu-id="8e62d-187">Далее приведены эти различия и обоснование внесенных изменений.</span><span class="sxs-lookup"><span data-stu-id="8e62d-187">We list the differences below, along with a rationale for the changes.</span></span>  
  
 <span data-ttu-id="8e62d-188">Sales.SalesOrderHeader_inmem</span><span class="sxs-lookup"><span data-stu-id="8e62d-188">Sales.SalesOrderHeader_inmem</span></span>  
  
-   <span data-ttu-id="8e62d-189">*Ограничения по умолчанию* поддерживаются для оптимизированных для памяти таблиц, и большинство ограничений по умолчанию переносятся как есть.</span><span class="sxs-lookup"><span data-stu-id="8e62d-189">*Default constraints* are supported for memory-optimized tables, and most default constraints we migrated as is.</span></span> <span data-ttu-id="8e62d-190">Однако исходная таблица Sales.SalesOrderHeader содержит два ограничения по умолчанию, которые получают текущую дату, для столбцов OrderDate и ModifiedDate.</span><span class="sxs-lookup"><span data-stu-id="8e62d-190">However, the original table Sales.SalesOrderHeader contains two default constraints that retrieve the current date, for the columns OrderDate and ModifiedDate.</span></span> <span data-ttu-id="8e62d-191">В рабочей нагрузке по обработке заказов значительного объема, когда множество заказов обрабатываются одновременно, наличие любого глобального ресурса может вызвать конфликт.</span><span class="sxs-lookup"><span data-stu-id="8e62d-191">In a high throughput order processing workload with a lot of concurrency, any global resource can become a point of contention.</span></span> <span data-ttu-id="8e62d-192">Системное время является таким глобальным ресурсом, и мы заметили, что при выполнении рабочей нагрузки [!INCLUDE[hek_2](../includes/hek-2-md.md)] , которая вставляет заказы на продажу, это может оказаться узким местом, в частности, если требуется получить системное время для нескольких столбцов из заголовка заказа на продажу, а также для подробных сведений о заказе на продажу.</span><span class="sxs-lookup"><span data-stu-id="8e62d-192">System time is such a global resource, and we have observed that it can become a bottleneck when running an [!INCLUDE[hek_2](../includes/hek-2-md.md)] workload that inserts sales orders, in particular if the system time needs to be retrieved for multiple columns in the sales order header, as well as the sales order details.</span></span> <span data-ttu-id="8e62d-193">Для устранения этой проблемы в этом образце для каждого вставляемого заказа на продажу получение системного времени производится только один раз, после чего это значение используется для столбцов даты и времени в таблицах SalesOrderHeader_inmem и SalesOrderDetail_inmem, в хранимой процедуре Sales.usp_InsertSalesOrder_inmem.</span><span class="sxs-lookup"><span data-stu-id="8e62d-193">The problem is addressed in this sample by retrieving the system time only once for each sales order that is inserted, and use that value for the datetime columns in SalesOrderHeader_inmem and SalesOrderDetail_inmem, in the stored procedure Sales.usp_InsertSalesOrder_inmem.</span></span>  
  
-   <span data-ttu-id="8e62d-194">*Определяемые пользователем типы псевдонимов* . В исходной таблице используются два псевдонима определяемых пользователем типов данных (UDT), dbo.OrderNumber и dbo.AccountNumber, для столбцов PurchaseOrderNumber и AccountNumber соответственно.</span><span class="sxs-lookup"><span data-stu-id="8e62d-194">*Alias UDTs* - The original table uses two alias user-defined data types (UDTs) dbo.OrderNumber and dbo.AccountNumber, for the columns PurchaseOrderNumber and AccountNumber, respectively.</span></span> [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] <span data-ttu-id="8e62d-195">не поддерживает определяемые пользователем типы псевдонимов для оптимизированных для памяти таблиц, поэтому в новых таблицах используются системные типы данных nvarchar(25) и nvarchar(15) соответственно.</span><span class="sxs-lookup"><span data-stu-id="8e62d-195">does not support alias UDT for memory-optimized tables, thus the new tables use system data types nvarchar(25) and nvarchar(15), respectively.</span></span>  
  
-   <span data-ttu-id="8e62d-196">*Столбцы, допускающие значение NULL, в ключах индексов* . В столбце SalesPersonID исходной таблицы могут содержаться значения NULL, а в столбцах новых таблиц значения NULL недопустимы. Кроме того, они имеют ограничение по умолчанию со значением (-1).</span><span class="sxs-lookup"><span data-stu-id="8e62d-196">*Nullable columns in index keys* - In the original table, the column SalesPersonID is nullable, while in the new tables the column is not nullable and has a default constraint with value (-1).</span></span> <span data-ttu-id="8e62d-197">Связано это с тем, что индексы в оптимизированных для памяти таблицах не могут содержать в ключе индекса столбцы, допускающие значение NULL; в этом случае значение -1 является суррогатом значения NULL.</span><span class="sxs-lookup"><span data-stu-id="8e62d-197">This is because indexes on memory-optimized tables cannot have nullable columns in the index key; -1 is a surrogate for NULL in this case.</span></span>  
  
-   <span data-ttu-id="8e62d-198">*Вычисляемые столбцы[!INCLUDE[ssSQL14](../includes/sssql14-md.md)]. Вычисляемые столбцы SalesOrderNumber и TotalDue пропускаются, так как*  не поддерживает вычисляемые столбцы в оптимизированных для памяти таблицах.</span><span class="sxs-lookup"><span data-stu-id="8e62d-198">*Computed columns* - The computed columns SalesOrderNumber and TotalDue are omitted, as [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] does not support computed columns in memory-optimized tables.</span></span> <span data-ttu-id="8e62d-199">Новое представление Sales.vSalesOrderHeader_extended_inmem отражает столбцы SalesOrderNumber и TotalDue.</span><span class="sxs-lookup"><span data-stu-id="8e62d-199">The new view Sales.vSalesOrderHeader_extended_inmem reflects the columns SalesOrderNumber and TotalDue.</span></span> <span data-ttu-id="8e62d-200">Поэтому при необходимости в этих столбцах можно использовать это представление.</span><span class="sxs-lookup"><span data-stu-id="8e62d-200">Therefore, you can use this view if these columns are needed.</span></span>  
  
-   <span data-ttu-id="8e62d-201">*Ограничения внешнего ключа* не поддерживаются в [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]для оптимизированных для памяти таблиц.</span><span class="sxs-lookup"><span data-stu-id="8e62d-201">*Foreign key constraints* are not supported for memory-optimized tables in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span> <span data-ttu-id="8e62d-202">Кроме того, в образце рабочей нагрузки SalesOrderHeader_inmem является горячей таблицей, а ограничения внешнего ключа требуют дополнительной обработки для всех операций DML, поскольку при этом необходимо выполнять поиск и подстановку во всех остальных таблицах, на которые ссылаются эти ограничения.</span><span class="sxs-lookup"><span data-stu-id="8e62d-202">In addition, SalesOrderHeader_inmem is a hot table in the example workload, and foreign keys constraints require additional processing for all DML operations, as it requires lookups in all the other tables referenced in these constraints.</span></span> <span data-ttu-id="8e62d-203">Поэтому предполагается, что приложение обеспечивает ссылочную целостность, которая не проверяется при вставке строк.</span><span class="sxs-lookup"><span data-stu-id="8e62d-203">Therefore, the assumption is that the app ensures referential integrity, and referential integrity is not validated when rows are inserted.</span></span> <span data-ttu-id="8e62d-204">Проверку ссылочной целостности для данных из этой таблицы можно осуществить с использованием хранимой процедуры dbo.usp_ValidateIntegrity с помощью следующего скрипта:</span><span class="sxs-lookup"><span data-stu-id="8e62d-204">Referential integrity for the data in this table can be verified using the stored procedure dbo.usp_ValidateIntegrity, using the following script:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Sales.SalesOrderHeader_inmem')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
-   <span data-ttu-id="8e62d-205">*Проверочные ограничения* не поддерживаются в SQ Server 2014 для оптимизированных для памяти таблиц.</span><span class="sxs-lookup"><span data-stu-id="8e62d-205">*Check constraints* are not supported for memory-optimized tables in SQ Server 2014.</span></span> <span data-ttu-id="8e62d-206">Доменная целостность проверяется вместе со ссылочной целостностью с помощью следующего скрипта:</span><span class="sxs-lookup"><span data-stu-id="8e62d-206">Domain integrity is validated along with referential integrity using this script:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Sales.SalesOrderHeader_inmem')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
-   <span data-ttu-id="8e62d-207">*Rowguid* . Столбец rowguid опускается.</span><span class="sxs-lookup"><span data-stu-id="8e62d-207">*Rowguid* - The rowguid column is omitted.</span></span> <span data-ttu-id="8e62d-208">Притом что uniqueidentifier поддерживается для оптимизированных для памяти таблиц, параметр ROWGUIDCOL в [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]для них не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="8e62d-208">While uniqueidentifier is support for memory-optimized tables, the option ROWGUIDCOL is not supported in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span> <span data-ttu-id="8e62d-209">Столбцы этого вида обычно используются либо для репликации слиянием, либо для таблиц, в которых есть столбцы filestream.</span><span class="sxs-lookup"><span data-stu-id="8e62d-209">Columns of this kind are typically used for either merge replication or tables that have filestream columns.</span></span> <span data-ttu-id="8e62d-210">В этом образце нет ни того ни другого.</span><span class="sxs-lookup"><span data-stu-id="8e62d-210">This sample includes neither.</span></span>  
  
 <span data-ttu-id="8e62d-211">Sales.SalesOrderDetail</span><span class="sxs-lookup"><span data-stu-id="8e62d-211">Sales.SalesOrderDetail</span></span>  
  
-   <span data-ttu-id="8e62d-212">*Ограничения по умолчанию*. Как и в случае с SalesOrderHeader, ограничение по умолчанию, которому требуется системные дата и время, не переносится. Вместо этого хранимая процедура, вставляющая заказы на продажу, задает системные дату и время при первой вставке.</span><span class="sxs-lookup"><span data-stu-id="8e62d-212">*Default constraints* - similar to SalesOrderHeader, the default constraint requiring the system date/time is not migrated, instead the stored procedure inserting sales orders takes care of inserting the current system date/time on first insert.</span></span>  
  
-   <span data-ttu-id="8e62d-213">*Вычисляемые столбцы*. Вычисляемый столбец LineTotal пропускается, так как в [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] наличие вычисляемых столбцов в оптимизированных для памяти таблицах не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="8e62d-213">*Computed columns* - the computed column LineTotal was not migrated as computed columns are not supported with memory-optimized tables in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span> <span data-ttu-id="8e62d-214">Для доступа к этому столбцу используйте представление Sales.vSalesOrderDetail_extended_inmem.</span><span class="sxs-lookup"><span data-stu-id="8e62d-214">To access this column use the view Sales.vSalesOrderDetail_extended_inmem.</span></span>  
  
-   <span data-ttu-id="8e62d-215">*Rowguid* . Столбец rowguid опускается.</span><span class="sxs-lookup"><span data-stu-id="8e62d-215">*Rowguid* - The rowguid column is omitted.</span></span> <span data-ttu-id="8e62d-216">Дополнительные сведения см. в описании таблицы SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="8e62d-216">For details see the description for the table SalesOrderHeader.</span></span>  
  
-   <span data-ttu-id="8e62d-217">Сведения о *проверочных* ограничениях и ограничениях *внешнего ключа* см. в описании таблицы SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="8e62d-217">For *check* and *foreign key* constraints see the description of SalesOrderHeader.</span></span> <span data-ttu-id="8e62d-218">Для проверки целостности домена и ссылочной целостности этой таблицы можно использовать следующий скрипт:</span><span class="sxs-lookup"><span data-stu-id="8e62d-218">The following script can be used to verify domain and referential integrity for this table:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Sales.SalesOrderHeader_inmem')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
 <span data-ttu-id="8e62d-219">Production.Product</span><span class="sxs-lookup"><span data-stu-id="8e62d-219">Production.Product</span></span>  
  
-   <span data-ttu-id="8e62d-220">*Псевдонимы UDT*. В исходной таблице используется определяемый пользователем тип данных dbo.Flag, который эквивалентен системному типу данных bit.</span><span class="sxs-lookup"><span data-stu-id="8e62d-220">*Alias UDTs* - the original table uses the user-defined data type dbo.Flag, which is equivalent to the system data type bit.</span></span> <span data-ttu-id="8e62d-221">В перенесенной таблице вместо него используется тип данных bit.</span><span class="sxs-lookup"><span data-stu-id="8e62d-221">The migrated table uses the bit data type instead.</span></span>  
  
-   <span data-ttu-id="8e62d-222">*Параметры сортировки BIN2* — столбцы name и ProductNumber включены в ключи индекса и поэтому должны иметь параметры сортировки BIN2 в [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8e62d-222">*BIN2 collation* - The columns Name and ProductNumber are included in index keys, and must thus have BIN2 collations in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span> <span data-ttu-id="8e62d-223">Здесь же предполагается, что приложение не опирается на особенности параметров сортировки, например чувствительность к регистру.</span><span class="sxs-lookup"><span data-stu-id="8e62d-223">Here, the assumption is that the app does not rely on collation specifics, like case insensitivity.</span></span>  
  
-   <span data-ttu-id="8e62d-224">*Rowguid* . Столбец rowguid опускается.</span><span class="sxs-lookup"><span data-stu-id="8e62d-224">*Rowguid* - The rowguid column is omitted.</span></span> <span data-ttu-id="8e62d-225">Дополнительные сведения см. в описании таблицы SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="8e62d-225">For details see the description for the table SalesOrderHeader.</span></span>  
  
-   <span data-ttu-id="8e62d-226">*Уникальные*и *проверочные* ограничения, а также *ограничения внешнего ключа* учитываются двумя способами: хранимые процедуры Product.usp_InsertProduct_inmem и Product.usp_DeleteProduct_inmem могут использоваться для вставки и удаления продуктов. Эти процедуры проверяют доменную и ссылочную целостность и завершаются неудачей в случае ее нарушения.</span><span class="sxs-lookup"><span data-stu-id="8e62d-226">*Unique*, *Check* and *Foreign Key constraints* are accounted for in two ways: the stored procedures Product.usp_InsertProduct_inmem and Product.usp_DeleteProduct_inmem can be used to insert and delete products; these procedures validate domain and referential integrity, and will fail if integrity is violated.</span></span> <span data-ttu-id="8e62d-227">Кроме того, следующий скрипт можно использовать для проверки целостности домена и ссылочной целостности как есть:</span><span class="sxs-lookup"><span data-stu-id="8e62d-227">In addition, the follow script can be used to validate domain and referential integrity as is:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Production.Product')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
    -   <span data-ttu-id="8e62d-228">Обратите внимание, что хранимые процедуры usp_InsertProduct_inmem и usp_DeleteProduct_inmem учитывают только внешние ключи между перенесенными таблицами.</span><span class="sxs-lookup"><span data-stu-id="8e62d-228">Note that the store procedures usp_InsertProduct_inmem and usp_DeleteProduct_inmem consider only foreign keys between the migrated tables.</span></span> <span data-ttu-id="8e62d-229">Ссылки на другие таблицы ProductModel, ProductSubcategory и UnitMeasure не учитываются.</span><span class="sxs-lookup"><span data-stu-id="8e62d-229">References to other tables ProductModel, ProductSubcategory, and UnitMeasure are not considered.</span></span>  
  
 <span data-ttu-id="8e62d-230">Sales.SpecialOffer</span><span class="sxs-lookup"><span data-stu-id="8e62d-230">Sales.SpecialOffer</span></span>  
  
-   <span data-ttu-id="8e62d-231">*Проверочные* ограничения и *ограничения внешнего ключа* учитываются двумя способами: хранимые процедуры Sales.usp_InsertSpecialOffer_inmem и Sales.usp_DeleteSpecialOffer_inmem могут использоваться для вставки и удаления специальных предложений. Эти процедуры проверяют доменную и ссылочную целостность и завершаются неудачей в случае нарушения целостности.</span><span class="sxs-lookup"><span data-stu-id="8e62d-231">*Check* and *Foreign Key constraints* are accounted for in two ways: the stored procedures Sales.usp_InsertSpecialOffer_inmem and Sales.usp_DeleteSpecialOffer_inmem can be used to insert and delete special offers; these procedures validate domain and referential integrity, and will fail if integrity is violated.</span></span> <span data-ttu-id="8e62d-232">Кроме того, следующий скрипт можно использовать для проверки целостности домена и ссылочной целостности как есть:</span><span class="sxs-lookup"><span data-stu-id="8e62d-232">In addition, the follow script can be used to validate domain and referential integrity as is:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Sales.SpecialOffer_inmem')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
-   <span data-ttu-id="8e62d-233">*Rowguid* . Столбец rowguid опускается.</span><span class="sxs-lookup"><span data-stu-id="8e62d-233">*Rowguid* - The rowguid column is omitted.</span></span> <span data-ttu-id="8e62d-234">Дополнительные сведения см. в описании таблицы SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="8e62d-234">For details see the description for the table SalesOrderHeader.</span></span>  
  
 <span data-ttu-id="8e62d-235">Sales.SpecialOfferProduct</span><span class="sxs-lookup"><span data-stu-id="8e62d-235">Sales.SpecialOfferProduct</span></span>  
  
-   <span data-ttu-id="8e62d-236">*Ограничения внешнего ключа* учитываются двумя способами: хранимая процедура Sales.usp_InsertSpecialOfferProduct_inmem может использоваться для вставки связей между специальными предложениями и продуктами. Эта процедура проверяет доменную и ссылочную целостность и завершается неудачей в случае ее нарушения.</span><span class="sxs-lookup"><span data-stu-id="8e62d-236">*Foreign Key constraints* are accounted for in two ways: the stored procedure Sales.usp_InsertSpecialOfferProduct_inmem can be used to insert relationships between special offers and products; this procedures validates referential integrity, and will fail if integrity is violated.</span></span> <span data-ttu-id="8e62d-237">Кроме того, следующий скрипт можно использовать для проверки ссылочной целостности как есть:</span><span class="sxs-lookup"><span data-stu-id="8e62d-237">In addition, the follow script can be used to validate referential integrity as is:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Sales.SpecialOfferProduct_inmem')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
-   <span data-ttu-id="8e62d-238">*Rowguid* . Столбец rowguid опускается.</span><span class="sxs-lookup"><span data-stu-id="8e62d-238">*Rowguid* - The rowguid column is omitted.</span></span> <span data-ttu-id="8e62d-239">Дополнительные сведения см. в описании таблицы SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="8e62d-239">For details see the description for the table SalesOrderHeader.</span></span>  
  
#### <a name="considerations-for-indexes-on-memory-optimized-tables"></a><span data-ttu-id="8e62d-240">Соображения в отношении индексов в оптимизированных для памяти таблицах</span><span class="sxs-lookup"><span data-stu-id="8e62d-240">Considerations for indexes on memory-optimized tables</span></span>  
 <span data-ttu-id="8e62d-241">Базовым индексом для оптимизированных для памяти таблиц является индекс NONCLUSTERED, который поддерживает уточняющие запросы (поиск по индексу с использованием предиката равенства), полный просмотр индекса и упорядоченный просмотр.</span><span class="sxs-lookup"><span data-stu-id="8e62d-241">The baseline index for memory-optimized tables is the NONCLUSTERED index, which supports point lookups (index seek on equality predicate), range scans (index seek in inequality predicate), full index scans, and ordered scans.</span></span> <span data-ttu-id="8e62d-242">Кроме того, индексы NONCLUSTERED поддерживают поиск в начальных столбцах ключа индекса.</span><span class="sxs-lookup"><span data-stu-id="8e62d-242">In addition, NONCLUSTERED indexes support searching on leading columns of the index key.</span></span> <span data-ttu-id="8e62d-243">По сути дела, индексы NONCLUSTERED оптимизированных для памяти таблиц поддерживают все операции, которые поддерживаются индексами NONCLUSTERED таблиц, находящихся на диске. Единственным исключением является обратный просмотр.</span><span class="sxs-lookup"><span data-stu-id="8e62d-243">In fact memory-optimized NONCLUSTERED indexes support all the operations supported by disk-based NONCLUSTERED indexes, with the only exception being backward scans.</span></span> <span data-ttu-id="8e62d-244">Поэтому использование индексов NONCLUSTERED в нашем случае является безопасным вариантом.</span><span class="sxs-lookup"><span data-stu-id="8e62d-244">Therefore, using NONCLUSTERED indexes is a safe choice for your indexes.</span></span>  
  
 <span data-ttu-id="8e62d-245">Для дальнейшей оптимизации рабочей нагрузки можно использовать индексы HASH.</span><span class="sxs-lookup"><span data-stu-id="8e62d-245">HASH indexes are can be used to further optimize the workload.</span></span> <span data-ttu-id="8e62d-246">Они особенно хорошо подходят для уточняющих запросов и вставки строк.</span><span class="sxs-lookup"><span data-stu-id="8e62d-246">They are particularly optimized for point lookups and row inserts.</span></span> <span data-ttu-id="8e62d-247">Однако следует учитывать, что они не поддерживают просмотр диапазонов, упорядоченный просмотр или поиск в начальных столбцах ключа индекса.</span><span class="sxs-lookup"><span data-stu-id="8e62d-247">However, one must consider that they do not support range scans, ordered scans, or search on leading index key columns.</span></span> <span data-ttu-id="8e62d-248">Поэтому при использовании этих индексов требуется соблюдать осторожность.</span><span class="sxs-lookup"><span data-stu-id="8e62d-248">Therefore, care needs to be taken when using these indexes.</span></span> <span data-ttu-id="8e62d-249">Кроме того, при создании необходимо указать параметр bucket_count.</span><span class="sxs-lookup"><span data-stu-id="8e62d-249">In addition, it is necessary to specify the bucket_count at create time.</span></span> <span data-ttu-id="8e62d-250">Обычно его значение должно быть в 1–2 раза больше числа значение ключей индекса, однако переоценка редко создает проблему.</span><span class="sxs-lookup"><span data-stu-id="8e62d-250">It should usually be set at between one and two times the number of index key values, but overestimating is usually not a problem.</span></span>  
  
 <span data-ttu-id="8e62d-251">Дополнительные указания по [работе с индексами](https://technet.microsoft.com/library/dn133166\(v=sql.120\).aspx) , а также указания по [выбору правильного значения bucket_count](https://technet.microsoft.com/library/dn494956\(v=sql.120\).aspx)см. в электронной документации.</span><span class="sxs-lookup"><span data-stu-id="8e62d-251">See Books Online for more details about [index guidelines](https://technet.microsoft.com/library/dn133166\(v=sql.120\).aspx) and guidelines for [choosing the right bucket_count](https://technet.microsoft.com/library/dn494956\(v=sql.120\).aspx).</span></span>  
  
 <span data-ttu-id="8e62d-252">Индексы в перенесенных таблицах настроены для выполнения демонстрационной рабочей нагрузки по обработке заказов на продажу.</span><span class="sxs-lookup"><span data-stu-id="8e62d-252">The indexes on the migrated tables have been tuned for the demo sales order processing workload.</span></span> <span data-ttu-id="8e62d-253">Рабочая нагрузка состоит из операций вставки и уточняющих запросов, которые выполняются в таблицах Sales.SalesOrderHeader_inmem и Sales.SalesOrderDetail_inmem, а также операций уточняющих запросов, которые выполняются в столбцах первичного ключа из таблиц Production.Product_inmem и Sales.SpecialOffer_inmem.</span><span class="sxs-lookup"><span data-stu-id="8e62d-253">The workload relies on inserts and point lookups in the tables Sales.SalesOrderHeader_inmem and Sales.SalesOrderDetail_inmem, and it also relies on point lookups on the primary key columns in the tables Production.Product_inmem and Sales.SpecialOffer_inmem.</span></span>  
  
 <span data-ttu-id="8e62d-254">В таблице Sales.SalesOrderHeader_inmem есть три индекса, причем для обеспечения высокой производительности все они являются индексами HASH, а также потому, что для этой рабочей нагрузки не требуется упорядоченных просмотров или просмотров диапазона.</span><span class="sxs-lookup"><span data-stu-id="8e62d-254">Sales.SalesOrderHeader_inmem has three indexes, which are all HASH indexes for performance reasons, and because no ordered or range scans are needed for the workload.</span></span>  
  
-   <span data-ttu-id="8e62d-255">Индекс HASH в (SalesOrderID): bucket_count задан в размере 10 миллионов (с округлением до 16 миллионов), поскольку ожидаемое количество заказов на продажу составляет 10 миллионов.</span><span class="sxs-lookup"><span data-stu-id="8e62d-255">HASH index on (SalesOrderID): bucket_count is sized at 10 million (rounded up to 16 million), because the expected number of sales orders is 10 million</span></span>  
  
-   <span data-ttu-id="8e62d-256">Индекс HASH в (SalesPersonID): bucket_count равен одному миллиону.</span><span class="sxs-lookup"><span data-stu-id="8e62d-256">HASH index on (SalesPersonID): bucket_count is 1 million.</span></span> <span data-ttu-id="8e62d-257">В предоставленном наборе данных нет большого числа продавцов, однако это дает место для расширения в будущем, к тому же не придется терять производительность из-за выполнения ненужных уточняющих запросов в случае слишком большого значения bucket_count.</span><span class="sxs-lookup"><span data-stu-id="8e62d-257">The data set provided does not have a lot of sales persons, but this allows for future growth, plus you don't pay a performance penalty for point lookups if the bucket_count is oversized.</span></span>  
  
-   <span data-ttu-id="8e62d-258">Индекс HASH в (CustomerID): bucket_count равен одному миллиону.</span><span class="sxs-lookup"><span data-stu-id="8e62d-258">HASH index on (CustomerID): bucket_count is 1 million.</span></span> <span data-ttu-id="8e62d-259">В предоставленном наборе данных нет большого числа клиентов, однако это дает место для расширения в будущем.</span><span class="sxs-lookup"><span data-stu-id="8e62d-259">The data set provided does not have a lot of customers, but this allows for future growth.</span></span>  
  
 <span data-ttu-id="8e62d-260">В таблице Sales.SalesOrderDetail_inmem есть три индекса, причем для обеспечения высокой производительности все они являются индексами HASH, а также потому, что для этой рабочей нагрузки не требуется упорядоченных просмотров или просмотров диапазона.</span><span class="sxs-lookup"><span data-stu-id="8e62d-260">Sales.SalesOrderDetail_inmem has three indexes, which are all HASH indexes for performance reasons, and because no ordered or range scans are needed for the workload.</span></span>  
  
-   <span data-ttu-id="8e62d-261">Индекс HASH в (SalesOrderID, SalesOrderDetailID): это индекс первичного ключа; хотя уточняющие запросы в (SalesOrderID, SalesOrderDetailID) будут выполняться нечасто, использование индекса HASH для ключа позволяет ускорить вставку строк.</span><span class="sxs-lookup"><span data-stu-id="8e62d-261">HASH index on (SalesOrderID, SalesOrderDetailID): this is the primary key index, and even though lookups on (SalesOrderID, SalesOrderDetailID) will be infrequent, using a hash index for the key speeds up row inserts.</span></span> <span data-ttu-id="8e62d-262">Параметр bucket_count задан в размере 50 миллионов (с округлением до 67 миллионов): ожидаемое количество заказов на продажу составляет 10 миллионов, а значение параметра выбрано с тем расчетом, что каждый заказ будет содержать пять элементов.</span><span class="sxs-lookup"><span data-stu-id="8e62d-262">The bucket_count is sized at 50 million (rounded up to 67 million): the expected number of sales orders is 10 million, and this is sized to have an average of 5 items per order</span></span>  
  
-   <span data-ttu-id="8e62d-263">Индекс HASH в (SalesOrderID): уточняющие запросы заказов на продажу выполняются часто: необходимо будет находить все линейные элементы, соответствующие одному заказу.</span><span class="sxs-lookup"><span data-stu-id="8e62d-263">HASH index on (SalesOrderID): lookups by sales order are frequent: you will want to find all the line items corresponding to a single order.</span></span>  <span data-ttu-id="8e62d-264">bucket_count задан в размере 10 миллионов (с округлением до 16 миллионов), поскольку ожидаемое количество заказов на продажу составляет 10 миллионов.</span><span class="sxs-lookup"><span data-stu-id="8e62d-264">bucket_count is sized at 10 million (rounded up to 16 million), because the expected number of sales orders is 10 million</span></span>  
  
-   <span data-ttu-id="8e62d-265">Индекс HASH в (ProductID): bucket_count равен одному миллиону.</span><span class="sxs-lookup"><span data-stu-id="8e62d-265">HASH index on (ProductID): bucket_count is 1 million.</span></span> <span data-ttu-id="8e62d-266">В предоставленном наборе данных нет большого числа продуктов, однако это дает место для расширения в будущем.</span><span class="sxs-lookup"><span data-stu-id="8e62d-266">The data set provided does not have a lot of product, but this allows for future growth.</span></span>  
  
 <span data-ttu-id="8e62d-267">В таблице Production.Product_inmem есть три индекса</span><span class="sxs-lookup"><span data-stu-id="8e62d-267">Production.Product_inmem has three indexes</span></span>  
  
-   <span data-ttu-id="8e62d-268">Индекс HASH в (ProductID): запросы по ProductID выполняются по критическому пути этой демонстрационной рабочей нагрузки, поэтому здесь применяется индекс HASH</span><span class="sxs-lookup"><span data-stu-id="8e62d-268">HASH index on (ProductID): lookups on ProductID are in the critical path for the demo workload, therefore this is a hash index</span></span>  
  
-   <span data-ttu-id="8e62d-269">Индекс NONCLUSTERED в (Name): это позволит выполнять упорядоченные просмотры названий продуктов</span><span class="sxs-lookup"><span data-stu-id="8e62d-269">NONCLUSTERED index on (Name): this will allow ordered scans of product names</span></span>  
  
-   <span data-ttu-id="8e62d-270">Индекс NONCLUSTERED в (ProductNumber): это позволит выполнять упорядоченные просмотры количества продуктов</span><span class="sxs-lookup"><span data-stu-id="8e62d-270">NONCLUSTERED index on (ProductNumber): this will allow ordered scans of product numbers</span></span>  
  
 <span data-ttu-id="8e62d-271">В таблице Sales.SpecialOffer_inmem есть один индекс HASH в (SpecialOfferID): уточняющие запросы специальных предложений находятся в самом сложном месте этой демонстрационной рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="8e62d-271">Sales.SpecialOffer_inmem has one HASH index on (SpecialOfferID): point lookups of special offers are in the critical part of the demo workload.</span></span> <span data-ttu-id="8e62d-272">Параметр bucket_count задан в размере 1 миллиона для обеспечения возможности роста в будущем.</span><span class="sxs-lookup"><span data-stu-id="8e62d-272">The bucket_count is sized at 1 million to allow for future growth.</span></span>  
  
 <span data-ttu-id="8e62d-273">Ссылок на таблицу Sales.SpecialOfferProduct_inmem в демонстрационной рабочей нагрузке нет, поэтому очевидная потребность в использовании индексов HASH в этой таблице с целью оптимизации рабочей нагрузки отсутствует — в (SpecialOfferID, ProductID) и (ProductID) используются индексы NONCLUSTERED.</span><span class="sxs-lookup"><span data-stu-id="8e62d-273">Sales.SpecialOfferProduct_inmem is not referenced in the demo workload, and thus there is no apparent need to use hash indexes on this table to optimize the workload - the indexes on (SpecialOfferID, ProductID) and (ProductID) are NONCLUSTERED.</span></span>  
  
 <span data-ttu-id="8e62d-274">Обратите внимание, что некоторые из приведенных выше параметров bucket_counts имеют слишком большое значение, но не параметры bucket_count для индексов в таблицах SalesOrderHeader_inmem и SalesOrderDetail_inmem: они заданы в размере 10 миллионов заказов на продажу.</span><span class="sxs-lookup"><span data-stu-id="8e62d-274">Notice that in the above some of the bucket_counts are over-sized, but not the bucket_counts for the indexes on SalesOrderHeader_inmem and SalesOrderDetail_inmem: they are sized for just 10 million sales orders.</span></span> <span data-ttu-id="8e62d-275">Сделано это было для того, чтобы обеспечить возможность установки образца в системах с небольшим объемом памяти, хотя в этих случаях демонстрационная рабочая нагрузка будет завершаться ошибкой из-за нехватки памяти.</span><span class="sxs-lookup"><span data-stu-id="8e62d-275">This was done to allow installing the sample on systems with low memory availability, although in those cases the demo workload will fail with out-of-memory.</span></span> <span data-ttu-id="8e62d-276">Если все же требуется обрабатывать намного больше, чем 10 миллионов заказов, то можно задать соответствующие значения для числа контейнеров.</span><span class="sxs-lookup"><span data-stu-id="8e62d-276">If you do want to scale well beyond 10 million sales orders, feel free to increase the bucket counts accordingly.</span></span>  
  
#### <a name="considerations-for-memory-utilization"></a><span data-ttu-id="8e62d-277">Соображения по использованию памяти</span><span class="sxs-lookup"><span data-stu-id="8e62d-277">Considerations for memory utilization</span></span>  
 <span data-ttu-id="8e62d-278">Использование памяти в примере базы данных до и после выполнения демонстрационной рабочей нагрузки обсуждается в разделе [Использование памяти оптимизированными для памяти таблицами](#Memoryutilizationforthememory-optimizedtables).</span><span class="sxs-lookup"><span data-stu-id="8e62d-278">Memory utilization in the sample database, both before and after running the demo workload, is discussed in the Section [Memory utilization for the memory-optimized tables](#Memoryutilizationforthememory-optimizedtables).</span></span>  
  
### <a name="stored-procedures-added-by-the-sample"></a><span data-ttu-id="8e62d-279">Хранимые процедуры, добавляемые образцом</span><span class="sxs-lookup"><span data-stu-id="8e62d-279">Stored Procedures added by the sample</span></span>  
 <span data-ttu-id="8e62d-280">Две основные хранимые процедуры для вставки заказов на продажу и обновления сведений о доставке:</span><span class="sxs-lookup"><span data-stu-id="8e62d-280">The two key stored procedures for inserting sales order and updating shipping details are as follows:</span></span>  
  
-   <span data-ttu-id="8e62d-281">Sales.usp_InsertSalesOrder_inmem</span><span class="sxs-lookup"><span data-stu-id="8e62d-281">Sales.usp_InsertSalesOrder_inmem</span></span>  
  
    -   <span data-ttu-id="8e62d-282">Вставляет новые заказы на продажу в базу данных и выдает SalesOrderID для вставленных заказов на продажу.</span><span class="sxs-lookup"><span data-stu-id="8e62d-282">Inserts a new sales order in the database and outputs the SalesOrderID for that sales order.</span></span> <span data-ttu-id="8e62d-283">В качестве входных параметров эта хранимая процедура использует данные из заголовка заказа на продажу, а также указанные в заказе линейные элементы.</span><span class="sxs-lookup"><span data-stu-id="8e62d-283">As input parameters it takes details for the sales order header, as well as the line items in the order.</span></span>  
  
    -   <span data-ttu-id="8e62d-284">Выходной параметр:</span><span class="sxs-lookup"><span data-stu-id="8e62d-284">Output parameter:</span></span>  
  
        -   <span data-ttu-id="8e62d-285">@SalesOrderID int — SalesOrderID для только что вставленного заказа на продажу.</span><span class="sxs-lookup"><span data-stu-id="8e62d-285">@SalesOrderID int - the SalesOrderID for the sales order that was just inserted</span></span>  
  
    -   <span data-ttu-id="8e62d-286">Входные параметры (обязательные):</span><span class="sxs-lookup"><span data-stu-id="8e62d-286">Input parameters (required):</span></span>  
  
        -   <span data-ttu-id="8e62d-287">@DueDate datetime2</span><span class="sxs-lookup"><span data-stu-id="8e62d-287">@DueDate datetime2</span></span>  
  
        -   <span data-ttu-id="8e62d-288">@CustomerID int</span><span class="sxs-lookup"><span data-stu-id="8e62d-288">@CustomerID int</span></span>  
  
        -   <span data-ttu-id="8e62d-289">@BillToAddressID [int]</span><span class="sxs-lookup"><span data-stu-id="8e62d-289">@BillToAddressID [int]</span></span>  
  
        -   <span data-ttu-id="8e62d-290">@ShipToAddressID [int]</span><span class="sxs-lookup"><span data-stu-id="8e62d-290">@ShipToAddressID [int]</span></span>  
  
        -   <span data-ttu-id="8e62d-291">@ShipMethodID [int]</span><span class="sxs-lookup"><span data-stu-id="8e62d-291">@ShipMethodID [int]</span></span>  
  
        -   <span data-ttu-id="8e62d-292">@SalesOrderDetails Sales.SalesOrderDetailType_inmem — возвращающий табличное значение параметр, который содержит линейные элементы из заказа.</span><span class="sxs-lookup"><span data-stu-id="8e62d-292">@SalesOrderDetails Sales.SalesOrderDetailType_inmem - TVP that contains the line items of the order</span></span>  
  
    -   <span data-ttu-id="8e62d-293">Входные параметры (необязательные):</span><span class="sxs-lookup"><span data-stu-id="8e62d-293">Input parameters (optional):</span></span>  
  
        -   <span data-ttu-id="8e62d-294">@Status [tinyint]</span><span class="sxs-lookup"><span data-stu-id="8e62d-294">@Status [tinyint]</span></span>  
  
        -   <span data-ttu-id="8e62d-295">@OnlineOrderFlag [bit]</span><span class="sxs-lookup"><span data-stu-id="8e62d-295">@OnlineOrderFlag [bit]</span></span>  
  
        -   <span data-ttu-id="8e62d-296">@PurchaseOrderNumber [nvarchar](25\)</span><span class="sxs-lookup"><span data-stu-id="8e62d-296">@PurchaseOrderNumber [nvarchar](25\)</span></span>  
  
        -   <span data-ttu-id="8e62d-297">@AccountNumber [nvarchar](15\)</span><span class="sxs-lookup"><span data-stu-id="8e62d-297">@AccountNumber [nvarchar](15\)</span></span>  
  
        -   <span data-ttu-id="8e62d-298">@SalesPersonID [int]</span><span class="sxs-lookup"><span data-stu-id="8e62d-298">@SalesPersonID [int]</span></span>  
  
        -   <span data-ttu-id="8e62d-299">@TerritoryID [int]</span><span class="sxs-lookup"><span data-stu-id="8e62d-299">@TerritoryID [int]</span></span>  
  
        -   <span data-ttu-id="8e62d-300">@CreditCardID [int]</span><span class="sxs-lookup"><span data-stu-id="8e62d-300">@CreditCardID [int]</span></span>  
  
        -   <span data-ttu-id="8e62d-301">@CreditCardApprovalCode [varchar](15\)</span><span class="sxs-lookup"><span data-stu-id="8e62d-301">@CreditCardApprovalCode [varchar](15\)</span></span>  
  
        -   <span data-ttu-id="8e62d-302">@CurrencyRateID [int]</span><span class="sxs-lookup"><span data-stu-id="8e62d-302">@CurrencyRateID [int]</span></span>  
  
        -   <span data-ttu-id="8e62d-303">@Comment nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="8e62d-303">@Comment nvarchar(128)</span></span>  
  
-   <span data-ttu-id="8e62d-304">Sales.usp_UpdateSalesOrderShipInfo_inmem</span><span class="sxs-lookup"><span data-stu-id="8e62d-304">Sales.usp_UpdateSalesOrderShipInfo_inmem</span></span>  
  
    -   <span data-ttu-id="8e62d-305">Обновляет сведения о доставке для данного заказа на продажу.</span><span class="sxs-lookup"><span data-stu-id="8e62d-305">Update the shipping information for a given sales order.</span></span> <span data-ttu-id="8e62d-306">Также обновляются сведения о доставке для всех линейных элементов заказа на продажу.</span><span class="sxs-lookup"><span data-stu-id="8e62d-306">This will also update the shipping information for all line items of the sales order.</span></span>  
  
    -   <span data-ttu-id="8e62d-307">Это процедура-оболочка для скомпилированных в собственном коде хранимых процедур Sales.usp_UpdateSalesOrderShipInfo_native, содержащих логику повтора для обработки (непредвиденных) возможных конфликтов, возникающих при обновлении одного заказа выполняющимися одновременно транзакциями.</span><span class="sxs-lookup"><span data-stu-id="8e62d-307">This is a wrapper procedure for the natively compiled stored procedures Sales.usp_UpdateSalesOrderShipInfo_native with retry logic to deal with (unexpected) potential conflicts with concurrent transactions updating the same order.</span></span> <span data-ttu-id="8e62d-308">Дополнительные сведения о логике повтора см. в [этом разделе электронной документации](https://technet.microsoft.com/library/dn169141\(v=sql.120\).aspx).</span><span class="sxs-lookup"><span data-stu-id="8e62d-308">For more information about retry logic see the Books Online topic [here](https://technet.microsoft.com/library/dn169141\(v=sql.120\).aspx).</span></span>  
  
-   <span data-ttu-id="8e62d-309">Sales.usp_UpdateSalesOrderShipInfo_native</span><span class="sxs-lookup"><span data-stu-id="8e62d-309">Sales.usp_UpdateSalesOrderShipInfo_native</span></span>  
  
    -   <span data-ttu-id="8e62d-310">Это скомпилированная в собственном коде хранимая процедура, которая фактически выполняет обновление сведений о доставке.</span><span class="sxs-lookup"><span data-stu-id="8e62d-310">This is the natively compiled stored procedure that actually processes the update to the shipping information.</span></span> <span data-ttu-id="8e62d-311">Она вызывается из хранимой процедуры-оболочки Sales.usp_UpdateSalesOrderShipInfo_inmem.</span><span class="sxs-lookup"><span data-stu-id="8e62d-311">It is means to be called from the wrapper stored procedure Sales.usp_UpdateSalesOrderShipInfo_inmem.</span></span> <span data-ttu-id="8e62d-312">Если клиент может обрабатывать сбои и имеет логику повтора, то эту процедуру можно вызывать напрямую без использования хранимой процедуры-оболочки.</span><span class="sxs-lookup"><span data-stu-id="8e62d-312">If the client can deal with failures and implements retry logic, you can call this procedure directly, rather than using the wrapper stored procedure.</span></span>  
  
 <span data-ttu-id="8e62d-313">В демонстрационной рабочей нагрузке используется приведенная далее хранимая процедура.</span><span class="sxs-lookup"><span data-stu-id="8e62d-313">The following stored procedure is used for the demo workload.</span></span>  
  
-   <span data-ttu-id="8e62d-314">Demo.usp_DemoReset</span><span class="sxs-lookup"><span data-stu-id="8e62d-314">Demo.usp_DemoReset</span></span>  
  
    -   <span data-ttu-id="8e62d-315">Выполняет сброс демонстрации путем повторного заполнения таблиц SalesOrderHeader и SalesOrderDetail.</span><span class="sxs-lookup"><span data-stu-id="8e62d-315">Resets the demo by emptying and reseeding the SalesOrderHeader and SalesOrderDetail tables.</span></span>  
  
 <span data-ttu-id="8e62d-316">Следующие хранимые процедуры используются для вставки в оптимизированные для памяти таблицы и удаления из них с обеспечением доменной и ссылочной целостности.</span><span class="sxs-lookup"><span data-stu-id="8e62d-316">The following stored procedures are used for inserting in and deleting from memory-optimized tables while guaranteeing domain and referential integrity.</span></span>  
  
-   <span data-ttu-id="8e62d-317">Production.usp_InsertProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="8e62d-317">Production.usp_InsertProduct_inmem</span></span>  
  
-   <span data-ttu-id="8e62d-318">Production.usp_DeleteProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="8e62d-318">Production.usp_DeleteProduct_inmem</span></span>  
  
-   <span data-ttu-id="8e62d-319">Sales.usp_InsertSpecialOffer_inmem</span><span class="sxs-lookup"><span data-stu-id="8e62d-319">Sales.usp_InsertSpecialOffer_inmem</span></span>  
  
-   <span data-ttu-id="8e62d-320">Sales.usp_DeleteSpecialOffer_inmem</span><span class="sxs-lookup"><span data-stu-id="8e62d-320">Sales.usp_DeleteSpecialOffer_inmem</span></span>  
  
-   <span data-ttu-id="8e62d-321">Sales.usp_InsertSpecialOfferProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="8e62d-321">Sales.usp_InsertSpecialOfferProduct_inmem</span></span>  
  
 <span data-ttu-id="8e62d-322">Наконец, следующая хранимая процедура используется для проверки доменной и ссылочной целостности.</span><span class="sxs-lookup"><span data-stu-id="8e62d-322">Finally the following stored procedure is used to verify domain and referential integrity.</span></span>  
  
1.  <span data-ttu-id="8e62d-323">dbo.usp_ValidateIntegrity</span><span class="sxs-lookup"><span data-stu-id="8e62d-323">dbo.usp_ValidateIntegrity</span></span>  
  
    -   <span data-ttu-id="8e62d-324">Необязательный параметр: @object_id — идентификатор объекта для проверки целостности.</span><span class="sxs-lookup"><span data-stu-id="8e62d-324">Optional parameter: @object_id - ID of the object to validate integrity for</span></span>  
  
    -   <span data-ttu-id="8e62d-325">Эта процедура берет правила целостности, соответствие которым необходимо проверить, из таблиц dbo.DomainIntegrity, dbo.ReferentialIntegrity и dbo.UniqueIntegrity — образец заполняет эти таблицы с учетом проверочных ограничений, ограничений внешнего ключа и ограничений уникальности, которые имеются в исходных таблицах из базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="8e62d-325">This procedure relies on the tables dbo.DomainIntegrity, dbo.ReferentialIntegrity, and dbo.UniqueIntegrity for the integrity rules that need to be verified - the sample populates these tables based on the check, foreign key, and unique constraints that exist for the original tables in the AdventureWorks database.</span></span>  
  
    -   <span data-ttu-id="8e62d-326">Для формирования кода T-SQL, который нужен для выполнения проверок целостности, используются вспомогательные процедуры dbo.usp_GenerateCKCheck, dbo.usp_GenerateFKCheck и dbo.GenerateUQCheck.</span><span class="sxs-lookup"><span data-stu-id="8e62d-326">It relies on the helper procedures dbo.usp_GenerateCKCheck, dbo.usp_GenerateFKCheck, and dbo.GenerateUQCheck to generate the T-SQL needed for performing the integrity checks.</span></span>  
  
##  <a name="performance-measurements-using-the-demo-workload"></a><a name="PerformanceMeasurementsusingtheDemoWorkload"></a> <span data-ttu-id="8e62d-327">Performance Measurements using the Demo Workload</span><span class="sxs-lookup"><span data-stu-id="8e62d-327">Performance Measurements using the Demo Workload</span></span>  
 <span data-ttu-id="8e62d-328">Ostress — это средство командной строки, разработанное группой поддержки [!INCLUDE[msCoName](../includes/msconame-md.md)] CSS [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8e62d-328">Ostress is a command-line tool that was developed by the [!INCLUDE[msCoName](../includes/msconame-md.md)] CSS [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] support team.</span></span> <span data-ttu-id="8e62d-329">С его помощью можно одновременно выполнять запросы или хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="8e62d-329">This tool can be used to execute queries or run stored procedures in parallel.</span></span> <span data-ttu-id="8e62d-330">Можно задать количество потоков для параллельного выполнения данной инструкции T-SQL, а также можно указать, сколько раз следует выполнить инструкцию в этом потоке. Программа ostress запустит потоки и выполнит инструкцию во всех потоках одновременно.</span><span class="sxs-lookup"><span data-stu-id="8e62d-330">You can configure the number of threads to run a given T-SQL statement in parallel, and you can specify how many times the statement should be executed on this thread; ostress will spin up the threads and execute the statement on all threads in parallel.</span></span> <span data-ttu-id="8e62d-331">После завершения выполнения для всех потоков программа ostress сообщит время, которое потребовалось на завершение выполнения всеми потоками.</span><span class="sxs-lookup"><span data-stu-id="8e62d-331">After execution finishes for all threads, ostress will report the time taken for all threads to finish execution.</span></span>  
  
### <a name="installing-ostress"></a><span data-ttu-id="8e62d-332">Установка ostress</span><span class="sxs-lookup"><span data-stu-id="8e62d-332">Installing ostress</span></span>  
 <span data-ttu-id="8e62d-333">Программа ostress устанавливается как часть пакета RML Utilities. Ее нельзя установить отдельно.</span><span class="sxs-lookup"><span data-stu-id="8e62d-333">Ostress is installed as part of the RML Utilities; there is no standalone installation for ostress.</span></span>  
  
 <span data-ttu-id="8e62d-334">Действия по установке</span><span class="sxs-lookup"><span data-stu-id="8e62d-334">Installation steps:</span></span>  
  
1.  <span data-ttu-id="8e62d-335">Скачайте и запустите пакет установки x64 для служебных программ RML на следующей странице:[https://blogs.msdn.com/b/psssql/archive/2013/10/29/cumulative-update-2-to-the-rml-utilities-for-microsoft-sql-server-released.aspx](https://blogs.msdn.com/b/psssql/archive/2013/10/29/cumulative-update-2-to-the-rml-utilities-for-microsoft-sql-server-released.aspx)</span><span class="sxs-lookup"><span data-stu-id="8e62d-335">Download and run the x64 installation package for the RML utilities from the following page: [https://blogs.msdn.com/b/psssql/archive/2013/10/29/cumulative-update-2-to-the-rml-utilities-for-microsoft-sql-server-released.aspx](https://blogs.msdn.com/b/psssql/archive/2013/10/29/cumulative-update-2-to-the-rml-utilities-for-microsoft-sql-server-released.aspx)</span></span>  
  
2.  <span data-ttu-id="8e62d-336">Если появится диалоговое окно, в котором будет указано, что некоторые файлы используются, нажмите кнопку "Продолжить".</span><span class="sxs-lookup"><span data-stu-id="8e62d-336">If there is a dialog box saying certain files are in use, click 'Continue'</span></span>  
  
### <a name="running-ostress"></a><span data-ttu-id="8e62d-337">Запуск ostress</span><span class="sxs-lookup"><span data-stu-id="8e62d-337">Running ostress</span></span>  
 <span data-ttu-id="8e62d-338">Программа ostress запускается из командной строки.</span><span class="sxs-lookup"><span data-stu-id="8e62d-338">Ostress is run from the command-line prompt.</span></span> <span data-ttu-id="8e62d-339">Удобнее всего запускать это средство из командной строки «RML Cmd Prompt», которая устанавливается как часть пакета RML Utilities.</span><span class="sxs-lookup"><span data-stu-id="8e62d-339">It is most convenient to run the tool from the "RML Cmd Prompt", which is installed as part of the RML Utilities.</span></span>  
  
 <span data-ttu-id="8e62d-340">Чтобы открыть RML Cmd Prompt, выполните следующие инструкции:</span><span class="sxs-lookup"><span data-stu-id="8e62d-340">To open the RML Cmd Prompt follow these instructions:</span></span>  
  
 <span data-ttu-id="8e62d-341">В Windows Server 2012 [R2], а также в Windows 8 и 8.1 откройте меню "Пуск", нажав клавишу Windows, и введите "rml".</span><span class="sxs-lookup"><span data-stu-id="8e62d-341">In Windows Server 2012 [R2] and in Windows 8 and 8.1, open the start menu by clicking the Windows key, and type 'rml'.</span></span> <span data-ttu-id="8e62d-342">Щелкните RML Cmd Prompt в результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="8e62d-342">Click on "RML Cmd Prompt", which will be in the list of search results.</span></span>  
  
 <span data-ttu-id="8e62d-343">Удостоверьтесь в том, что командная строка находится в установочной папке RML Utilities.</span><span class="sxs-lookup"><span data-stu-id="8e62d-343">Ensure that the command prompt is located in the RML Utilities installation folder.</span></span> <span data-ttu-id="8e62d-344">Пример:</span><span class="sxs-lookup"><span data-stu-id="8e62d-344">For example:</span></span>  
  
 ![](../../2014/database-engine/media/SQLServer2014RTMIn-MemoryOLTP01.jpg)  
  
 <span data-ttu-id="8e62d-345">Параметры командной строки для программы ostress отображаются при запуске ostress.exe без каких-либо параметров.</span><span class="sxs-lookup"><span data-stu-id="8e62d-345">The command-line options for ostress can be seen when simply running ostress.exe without any command-line options.</span></span> <span data-ttu-id="8e62d-346">Основные параметры, которые можно использовать при запуске программы ostress для этого образца:</span><span class="sxs-lookup"><span data-stu-id="8e62d-346">The main options to consider for running ostress with this sample are:</span></span>  
  
-   <span data-ttu-id="8e62d-347">-S — имя экземпляра [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], с которым необходимо установить соединение.</span><span class="sxs-lookup"><span data-stu-id="8e62d-347">-S name of [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance to connect to</span></span>  
  
-   <span data-ttu-id="8e62d-348">-E использовать проверку подлинности Windows для подключения (по умолчанию); При использовании [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] проверки подлинности используйте параметры-u и-P, чтобы указать имя пользователя и пароль соответственно.</span><span class="sxs-lookup"><span data-stu-id="8e62d-348">-E use Windows authentication to connect (default); if you use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] authentication, use the options -U and -P to specify the username and password, respectively</span></span>  
  
-   <span data-ttu-id="8e62d-349">-d имя базы данных (в этом случае AdventureWorks2014)</span><span class="sxs-lookup"><span data-stu-id="8e62d-349">-d name of the database, for this example AdventureWorks2014</span></span>  
  
-   <span data-ttu-id="8e62d-350">-Q выполняемая инструкция T-SQL</span><span class="sxs-lookup"><span data-stu-id="8e62d-350">-Q the T-SQL statement to be executed</span></span>  
  
-   <span data-ttu-id="8e62d-351">-n количество соединений, обрабатывающих каждый входной файл/запрос</span><span class="sxs-lookup"><span data-stu-id="8e62d-351">-n number of connections processing each input file/query</span></span>  
  
-   <span data-ttu-id="8e62d-352">-r количество итераций для каждого соединения, выполняющих каждый входной файл/запрос</span><span class="sxs-lookup"><span data-stu-id="8e62d-352">-r the number of iterations for each connection to execute each input file/query</span></span>  
  
### <a name="demo-workload"></a><span data-ttu-id="8e62d-353">Демонстрационная рабочая нагрузка</span><span class="sxs-lookup"><span data-stu-id="8e62d-353">Demo Workload</span></span>  
 <span data-ttu-id="8e62d-354">Главная хранимая процедура, используемая в демонстрационной рабочей нагрузке, — Sales.usp_InsertSalesOrder_inmem/ondisk.</span><span class="sxs-lookup"><span data-stu-id="8e62d-354">The main stored procedure used in the demo workload is Sales.usp_InsertSalesOrder_inmem/ondisk.</span></span> <span data-ttu-id="8e62d-355">Приведенный далее скрипт формирует возвращающий табличное значение параметр с образцом данных и вызывает процедуру для вставки заказа на продажу с пятью линейными элементами.</span><span class="sxs-lookup"><span data-stu-id="8e62d-355">The script in the below constructs a table-valued parameter (TVP) with sample data, and calls the procedure to insert a sales order with 5 line items.</span></span>  
  
 <span data-ttu-id="8e62d-356">Средство ostress служит для параллельного выполнения вызовов хранимых процедур с целью имитации одновременной вставки заказов на продажу клиентами.</span><span class="sxs-lookup"><span data-stu-id="8e62d-356">The ostress tool is used to execute the stored procedure calls in parallel, to simulate clients inserting sales orders concurrently.</span></span>  
  
 <span data-ttu-id="8e62d-357">Сбрасывайте образец после каждого использования, выполняя Demo.usp_DemoReset.</span><span class="sxs-lookup"><span data-stu-id="8e62d-357">Reset the demo after each stress run executing Demo.usp_DemoReset.</span></span> <span data-ttu-id="8e62d-358">Эта процедура удаляет строки из оптимизированных для памяти таблиц, усекает размещенные на диске таблицы и выполняет контрольную точку базы данных.</span><span class="sxs-lookup"><span data-stu-id="8e62d-358">This procedure deletes the rows in the memory-optimized tables, truncates the disk-based tables, and executes a database checkpoint.</span></span>  
  
 <span data-ttu-id="8e62d-359">Для имитации рабочей нагрузки по обработке заказов на продажу параллельно выполняется следующий скрипт.</span><span class="sxs-lookup"><span data-stu-id="8e62d-359">The following script is executed concurrently to simulate a sales order processing workload:</span></span>  
  
```  
DECLARE   
      @i int = 0,   
      @od Sales.SalesOrderDetailType_inmem,   
      @SalesOrderID int,   
      @DueDate datetime2 = sysdatetime(),   
      @CustomerID int = rand() * 8000,   
      @BillToAddressID int = rand() * 10000,   
      @ShipToAddressID int = rand() * 10000,   
      @ShipMethodID int = (rand() * 5) + 1;   
  
INSERT INTO @od   
SELECT OrderQty, ProductID, SpecialOfferID   
FROM Demo.DemoSalesOrderDetailSeed   
WHERE OrderID= cast((rand()*106) + 1 as int);   
  
WHILE (@i < 20)   
BEGIN;   
      EXEC Sales.usp_InsertSalesOrder_inmem @SalesOrderID OUTPUT, @DueDate, @CustomerID, @BillToAddressID, @ShipToAddressID, @ShipMethodID, @od;   
      SET @i += 1   
END  
  
```  
  
 <span data-ttu-id="8e62d-360">При выполнении этого скрипта каждый образец сформированного заказа вставляется 20 раз через 20 хранимых процедур, выполняемых в цикле WHILE.</span><span class="sxs-lookup"><span data-stu-id="8e62d-360">With this script, each sample order that is constructed is inserted 20 times, through 20 stored procedures executed in a WHILE loop.</span></span> <span data-ttu-id="8e62d-361">Эти циклы используются для учета того факта, что для формирования образца заказа используется база данных.</span><span class="sxs-lookup"><span data-stu-id="8e62d-361">The loop is used to account for the fact that the database is used to construct the sample order.</span></span> <span data-ttu-id="8e62d-362">В стандартных рабочих средах вставляемый заказ на продажу формируется приложением промежуточного уровня.</span><span class="sxs-lookup"><span data-stu-id="8e62d-362">In typical production environments, the mid-tier application will construct the sales order to be inserted.</span></span>  
  
 <span data-ttu-id="8e62d-363">Приведенный выше скрипт вставляет заказы на продажу в оптимизированные для памяти таблицы.</span><span class="sxs-lookup"><span data-stu-id="8e62d-363">The above script inserts sales orders into memory-optimized tables.</span></span> <span data-ttu-id="8e62d-364">Чтобы получить скрипт для вставки заказов на продажу в таблицы, размещенные на диске, нужно заменить два вхождения _inmem на _ondisk.</span><span class="sxs-lookup"><span data-stu-id="8e62d-364">The script to insert sales orders into disk-based tables is derived by replacing the two occurrences of '_inmem' with '_ondisk'.</span></span>  
  
 <span data-ttu-id="8e62d-365">Мы воспользуемся средством ostress для выполнения скриптов с использованием нескольких параллельных соединений.</span><span class="sxs-lookup"><span data-stu-id="8e62d-365">We will use the ostress tool to execute the scripts using several concurrent connections.</span></span> <span data-ttu-id="8e62d-366">Чтобы определить количество соединений, укажем параметр -n, а параметр -r — для определения числа выполнений скрипта в каждом соединении.</span><span class="sxs-lookup"><span data-stu-id="8e62d-366">We will use the parameter '-n' to control the number of connections, and the parameter 'r' to control how many times the script is executed on each connection.</span></span>  
  
#### <a name="functional-validation-of-the-workload"></a><span data-ttu-id="8e62d-367">Функциональная проверка рабочей нагрузки</span><span class="sxs-lookup"><span data-stu-id="8e62d-367">Functional Validation of the Workload</span></span>  
 <span data-ttu-id="8e62d-368">Чтобы убедиться в том, что все работает, мы начнем с примера теста, используя 10 одновременных подключений и 5 итераций, вставляя всего 10 \* 5 \* 20 = 1000 заказа на продажу.</span><span class="sxs-lookup"><span data-stu-id="8e62d-368">To verify everything works, we will start with a sample test, using 10 concurrent connects and 5 iterations, inserting a total of 10 \* 5 \* 20 = 1000 sales order.</span></span>  
  
 <span data-ttu-id="8e62d-369">В приведенной ниже команде предполагается использование экземпляра по умолчанию на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8e62d-369">With the below command we assume using the default instance on the local machine.</span></span> <span data-ttu-id="8e62d-370">Если используется именованный экземпляр или удаленный сервер, то измените имя сервера с помощью параметра -S.</span><span class="sxs-lookup"><span data-stu-id="8e62d-370">If you are using a named instance or using a remote server, change the server name accordingly, using the parameter -S.</span></span>  
  
 <span data-ttu-id="8e62d-371">Для вставки 1000 заказов на продажу в оптимизированные для памяти таблицы используйте следующую команду в RML Cmd Prompt:</span><span class="sxs-lookup"><span data-stu-id="8e62d-371">Insert 1000 sales orders in memory-optimized tables use the following command in the RML Cmd Prompt:</span></span>  
  
 <span data-ttu-id="8e62d-372">Нажмите кнопку «Копировать», чтобы скопировать команду, и вставьте ее в командную строку RML Utilities.</span><span class="sxs-lookup"><span data-stu-id="8e62d-372">Click the Copy button to copy the command, and paste it into the RML Utilities command prompt.</span></span>  
  
```  
ostress.exe -n10 -r5 -S. -E -dAdventureWorks2014 -q -Q"DECLARE @i int = 0, @od Sales.SalesOrderDetailType_inmem, @SalesOrderID int, @DueDate datetime2 = sysdatetime(), @CustomerID int = rand() * 8000, @BillToAddressID int = rand() * 10000, @ShipToAddressID int = rand() * 10000, @ShipMethodID int = (rand() * 5) + 1; INSERT INTO @od SELECT OrderQty, ProductID, SpecialOfferID FROM Demo.DemoSalesOrderDetailSeed WHERE OrderID= cast((rand()*106) + 1 as int); while (@i < 20) begin; EXEC Sales.usp_InsertSalesOrder_inmem @SalesOrderID OUTPUT, @DueDate, @CustomerID, @BillToAddressID, @ShipToAddressID, @ShipMethodID, @od; set @i += 1 end"  
```  
  
 <span data-ttu-id="8e62d-373">Если все работает правильно, окно командной строки будет иметь примерно следующий вид.</span><span class="sxs-lookup"><span data-stu-id="8e62d-373">If everything works as expected, your command window will look similar to the following.</span></span> <span data-ttu-id="8e62d-374">Сообщений об ошибках быть не должно.</span><span class="sxs-lookup"><span data-stu-id="8e62d-374">Error messages are not expected.</span></span>  
  
 ![](../../2014/database-engine/media/SQLServer2014RTMIn-MemoryOLTP02.jpg)  
  
 <span data-ttu-id="8e62d-375">Кроме того, проверьте, что рабочая нагрузка штатно работает для таблиц, размещенных на диске, выполнив в командной строке RML Cmd Prompt следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8e62d-375">Validate that also the workload functions as expected for disk-based tables by running the following command in the RML Cmd Prompt:</span></span>  
  
 <span data-ttu-id="8e62d-376">Нажмите кнопку «Копировать», чтобы скопировать команду, и вставьте ее в командную строку RML Utilities.</span><span class="sxs-lookup"><span data-stu-id="8e62d-376">Click the Copy button to copy the command, and paste it into the RML Utilities command prompt.</span></span>  
  
```  
ostress.exe -n10 -r5 -S. -E -dAdventureWorks2014 -q -Q"DECLARE @i int = 0, @od Sales.SalesOrderDetailType_ondisk, @SalesOrderID int, @DueDate datetime2 = sysdatetime(), @CustomerID int = rand() * 8000, @BillToAddressID int = rand() * 10000, @ShipToAddressID int = rand() * 10000, @ShipMethodID int = (rand() * 5) + 1; INSERT INTO @od SELECT OrderQty, ProductID, SpecialOfferID FROM Demo.DemoSalesOrderDetailSeed WHERE OrderID= cast((rand()*106) + 1 as int); while (@i < 20) begin; EXEC Sales.usp_InsertSalesOrder_ondisk @SalesOrderID OUTPUT, @DueDate, @CustomerID, @BillToAddressID, @ShipToAddressID, @ShipMethodID, @od; set @i += 1 end"  
```  
  
#### <a name="running-the-workload"></a><span data-ttu-id="8e62d-377">Выполнение рабочей нагрузки</span><span class="sxs-lookup"><span data-stu-id="8e62d-377">Running the Workload</span></span>  
 <span data-ttu-id="8e62d-378">Чтобы выполнить масштабное тестирование, вставим 10 миллионов заказов на продажу с использованием 100 соединений.</span><span class="sxs-lookup"><span data-stu-id="8e62d-378">To test at scale we insert 10 million sales orders, using 100 connections.</span></span> <span data-ttu-id="8e62d-379">Этот тест работает относительно неплохо на не очень мощном сервере (например, с 8 физическими и 16 логическими ядрами) с базовым хранилищем SSD для журнала.</span><span class="sxs-lookup"><span data-stu-id="8e62d-379">This test performs reasonably on a modest server (e.g., 8 physical, 16 logical cores), and basic SSD storage for the log.</span></span> <span data-ttu-id="8e62d-380">Если производительность теста на вашем оборудовании неудовлетворительна, ознакомьтесь с разделом [Устранение неполадок тестов, которые выполняются медленно](#Troubleshootingslow-runningtests). Если требуется снизить нагрузку для этого теста, уменьшите количество соединений, изменив параметр -n.</span><span class="sxs-lookup"><span data-stu-id="8e62d-380">If the test does not perform well on your hardware, take look at the Section [Troubleshooting slow-running tests](#Troubleshootingslow-runningtests).If you want to reduce the level of stress for this test, lower the number of connections by changing the parameter '-n'.</span></span> <span data-ttu-id="8e62d-381">Например, чтобы снизить число соединений до 40, замените параметр -n100 на -n40.</span><span class="sxs-lookup"><span data-stu-id="8e62d-381">For example to lower the connection count to 40, change the parameter '-n100' to '-n40'.</span></span>  
  
 <span data-ttu-id="8e62d-382">В качестве меры производительности рабочей нагрузки служит затраченное время, сообщаемое программой ostress.exe после выполнения рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="8e62d-382">As a performance measure for the workload we use the elapsed time as reported by ostress.exe after running the workload.</span></span>  
  
##### <a name="memory-optimized-tables"></a><span data-ttu-id="8e62d-383">Таблицы, оптимизированные для памяти</span><span class="sxs-lookup"><span data-stu-id="8e62d-383">Memory-optimized tables</span></span>  
 <span data-ttu-id="8e62d-384">Начнем с выполнения рабочей нагрузки в оптимизированных для памяти таблицах.</span><span class="sxs-lookup"><span data-stu-id="8e62d-384">We will start by running the workload on memory-optimized tables.</span></span> <span data-ttu-id="8e62d-385">Следующая команда открывает 100 потоков, каждый из которых выполняет 5000 итераций.</span><span class="sxs-lookup"><span data-stu-id="8e62d-385">The following command opens 100 threads, each running for 5,000 iterations.</span></span>  <span data-ttu-id="8e62d-386">Каждая итерация вставляет 20 заказов на продажу в отдельных транзакциях.</span><span class="sxs-lookup"><span data-stu-id="8e62d-386">Each iteration inserts 20 sales orders in separate transactions.</span></span> <span data-ttu-id="8e62d-387">В каждой итерации есть 20 вставок для компенсации использования базы данных, для формирования вставляемых данных.</span><span class="sxs-lookup"><span data-stu-id="8e62d-387">There are 20 inserts per iteration to compensate for the fact that the database is used to generate the data to be inserted.</span></span> <span data-ttu-id="8e62d-388">Это дает всего 20 \* 5000 \* 100 = 10 000 000 вставок заказов на продажу.</span><span class="sxs-lookup"><span data-stu-id="8e62d-388">This yield a total of 20 \* 5,000 \* 100 = 10,000,000 sales order inserts.</span></span>  
  
 <span data-ttu-id="8e62d-389">Откройте командную строку RML Cmd Prompt и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8e62d-389">Open the RML Cmd Prompt, and execute the following command:</span></span>  
  
 <span data-ttu-id="8e62d-390">Нажмите кнопку «Копировать», чтобы скопировать команду, и вставьте ее в командную строку RML Utilities.</span><span class="sxs-lookup"><span data-stu-id="8e62d-390">Click the Copy button to copy the command, and paste it into the RML Utilities command prompt.</span></span>  
  
```  
ostress.exe -n100 -r5000 -S. -E -dAdventureWorks2014 -q -Q"DECLARE @i int = 0, @od Sales.SalesOrderDetailType_inmem, @SalesOrderID int, @DueDate datetime2 = sysdatetime(), @CustomerID int = rand() * 8000, @BillToAddressID int = rand() * 10000, @ShipToAddressID int = rand() * 10000, @ShipMethodID int = (rand() * 5) + 1; INSERT INTO @od SELECT OrderQty, ProductID, SpecialOfferID FROM Demo.DemoSalesOrderDetailSeed WHERE OrderID= cast((rand()*106) + 1 as int); while (@i < 20) begin; EXEC Sales.usp_InsertSalesOrder_inmem @SalesOrderID OUTPUT, @DueDate, @CustomerID, @BillToAddressID, @ShipToAddressID, @ShipMethodID, @od; set @i += 1 end"  
```  
  
 <span data-ttu-id="8e62d-391">Ее выполнение на одном тестовом сервере, общее число ядер в котором составляет 8 физических (16 логических), заняло 2 минуты 5 секунд.</span><span class="sxs-lookup"><span data-stu-id="8e62d-391">On one test server with a total number of 8 physical (16 logical) cores, this took 2 minutes and 5 seconds.</span></span> <span data-ttu-id="8e62d-392">Ее выполнение на втором тестовом сервере, общее число ядер в котором составляет 24 физических и 48 логических, заняло 1 минуту 0 секунд.</span><span class="sxs-lookup"><span data-stu-id="8e62d-392">On a second test server with 24 physical (48 logical) cores, this took 1 minute and 0 seconds.</span></span>  
  
 <span data-ttu-id="8e62d-393">Следите за использованием ЦП во время выполнения рабочей нагрузки (например, с помощью диспетчера задач).</span><span class="sxs-lookup"><span data-stu-id="8e62d-393">Observe the CPU utilization while the workload is running, for example using task manager.</span></span> <span data-ttu-id="8e62d-394">Вы увидите, что использование ЦП близко к 100 %.</span><span class="sxs-lookup"><span data-stu-id="8e62d-394">You will see that CPU utilization is close to 100%.</span></span> <span data-ttu-id="8e62d-395">Если это не так, то имеется узкое место в области ввода-вывода журнала (см. также раздел [Устранение неполадок тестов, которые выполняются медленно](#Troubleshootingslow-runningtests)).</span><span class="sxs-lookup"><span data-stu-id="8e62d-395">If this is not the case, you have a log IO bottleneck see also [Troubleshooting slow-running tests](#Troubleshootingslow-runningtests).</span></span>  
  
##### <a name="disk-based-tables"></a><span data-ttu-id="8e62d-396">Таблицы на диске</span><span class="sxs-lookup"><span data-stu-id="8e62d-396">Disk-based tables</span></span>  
 <span data-ttu-id="8e62d-397">Следующая команда будет запускать рабочую нагрузку на дисковых таблицах.</span><span class="sxs-lookup"><span data-stu-id="8e62d-397">The following command will run the workload on disk-based tables.</span></span> <span data-ttu-id="8e62d-398">Обратите внимание, что на выполнение этой рабочей нагрузки может уйти значительное время. Связано это главным образом с конфликтами кратковременных блокировок в системе.</span><span class="sxs-lookup"><span data-stu-id="8e62d-398">Note that this workload may take a while to execute, which is largely due to latch contention in the system.</span></span> <span data-ttu-id="8e62d-399">В оптимизированной для памяти таблице нет кратковременных блокировок, поэтому она не страдает от этой проблемы.</span><span class="sxs-lookup"><span data-stu-id="8e62d-399">Memory-optimized table are latch-free and thus do not suffer from this problem.</span></span>  
  
 <span data-ttu-id="8e62d-400">Откройте командную строку RML Cmd Prompt и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8e62d-400">Open the RML Cmd Prompt, and execute the following command:</span></span>  
  
 <span data-ttu-id="8e62d-401">Нажмите кнопку «Копировать», чтобы скопировать команду, и вставьте ее в командную строку RML Utilities.</span><span class="sxs-lookup"><span data-stu-id="8e62d-401">Click the Copy button to copy the command, and paste it into the RML Utilities command prompt.</span></span>  
  
```  
ostress.exe -n100 -r5000 -S. -E -dAdventureWorks2014 -q -Q"DECLARE @i int = 0, @od Sales.SalesOrderDetailType_ondisk, @SalesOrderID int, @DueDate datetime2 = sysdatetime(), @CustomerID int = rand() * 8000, @BillToAddressID int = rand() * 10000, @ShipToAddressID int = rand() * 10000, @ShipMethodID int = (rand() * 5) + 1; INSERT INTO @od SELECT OrderQty, ProductID, SpecialOfferID FROM Demo.DemoSalesOrderDetailSeed WHERE OrderID= cast((rand()*106) + 1 as int); while (@i < 20) begin; EXEC Sales.usp_InsertSalesOrder_ondisk @SalesOrderID OUTPUT, @DueDate, @CustomerID, @BillToAddressID, @ShipToAddressID, @ShipMethodID, @od; set @i += 1 end"  
```  
  
 <span data-ttu-id="8e62d-402">Ее выполнение на одном тестовом сервере, общее число ядер в котором составляет 8 физических и 16 логических, заняло 41 минуту 25 секунд.</span><span class="sxs-lookup"><span data-stu-id="8e62d-402">On one test server with a total number of 8 physical (16 logical) cores, this took 41 minutes and 25 seconds.</span></span> <span data-ttu-id="8e62d-403">Ее выполнение на втором тестовом сервере, общее число ядер в котором составляет 24 физических и 48 логических, заняло 52 минуты 16 секунд.</span><span class="sxs-lookup"><span data-stu-id="8e62d-403">On a second test server with 24 physical (48 logical) cores, this took 52 minutes and 16 seconds.</span></span>  
  
 <span data-ttu-id="8e62d-404">Основным фактором, определяющим разницу в производительности между оптимизированными для памяти таблицами и таблицами, размещенными на диске, в этом тесте является то, что при использовании таблиц, размещенных на диске, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] не может полностью использовать возможности ЦП.</span><span class="sxs-lookup"><span data-stu-id="8e62d-404">The main factor in the performance difference between memory-optimized tables and disk-based tables in this test is the fact that when using disk-based tables, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cannot not fully utilize the CPU.</span></span> <span data-ttu-id="8e62d-405">Причина состоит в конфликтах по кратковременным блокировкам: выполняющиеся одновременно транзакции пытаются производить запись на одну и ту же страницу данных. Кратковременные блокировки используются для обеспечения того, что только одна транзакция будет осуществлять запись на страницу в определенный момент времени.</span><span class="sxs-lookup"><span data-stu-id="8e62d-405">The reason is latch contention: concurrent transactions are attempting to write to the same data page; latches are used to ensure only one transaction at a time can write to a page.</span></span> <span data-ttu-id="8e62d-406">Подсистема [!INCLUDE[hek_2](../includes/hek-2-md.md)] не использует кратковременные блокировки, а строки данных не формируют страницы.</span><span class="sxs-lookup"><span data-stu-id="8e62d-406">The [!INCLUDE[hek_2](../includes/hek-2-md.md)] engine is latch-free, and data rows are not organized in pages.</span></span> <span data-ttu-id="8e62d-407">Поэтому параллельные транзакции не блокируют друг друга, что позволяет [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] полностью использовать ЦП.</span><span class="sxs-lookup"><span data-stu-id="8e62d-407">Thus, concurrent transactions do not block each other's inserts, thus enabling [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to fully utilize the CPU.</span></span>  
  
 <span data-ttu-id="8e62d-408">Отследить использование ЦП можно во время выполнения рабочей нагрузки (например, с помощью диспетчера задач).</span><span class="sxs-lookup"><span data-stu-id="8e62d-408">You can observe the CPU utilization while the workload is running, for example using task manager.</span></span> <span data-ttu-id="8e62d-409">Вы увидите, что при использовании таблиц, размещенных на диске, использование ЦП далеко от 100 %.</span><span class="sxs-lookup"><span data-stu-id="8e62d-409">You will see with disk-based tables the CPU utilization is far from 100%.</span></span> <span data-ttu-id="8e62d-410">В тестовой конфигурации с 16 логическими процессорами использование находится в районе 24 %.</span><span class="sxs-lookup"><span data-stu-id="8e62d-410">On a test configuration with 16 logical processors, the utilization would hover around 24%.</span></span>  
  
 <span data-ttu-id="8e62d-411">Кроме того, с помощью системного монитора можно просмотреть количество ожиданий, связанных с кратковременными блокировками (счетчик производительности \SQL Server:Latches\Latch Waits/sec).</span><span class="sxs-lookup"><span data-stu-id="8e62d-411">Optionally, you can view the number of latch waits per second using Performance Monitor, with the performance counter '\SQL Server:Latches\Latch Waits/sec'.</span></span>  
  
#### <a name="resetting-the-demo"></a><span data-ttu-id="8e62d-412">Сброс образца</span><span class="sxs-lookup"><span data-stu-id="8e62d-412">Resetting the demo</span></span>  
 <span data-ttu-id="8e62d-413">Чтобы сбросить образец, откройте командную строку RML Cmd Prompt и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8e62d-413">To reset the demo, open the RML Cmd Prompt, and execute the following command:</span></span>  
  
```  
ostress.exe -S. -E -dAdventureWorks2014 -Q"EXEC Demo.usp_DemoReset"  
```  
  
 <span data-ttu-id="8e62d-414">В зависимости от оборудования выполнение данного примера может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="8e62d-414">Depending on the hardware this may take a few minutes to run.</span></span>  
  
 <span data-ttu-id="8e62d-415">Рекомендуется выполнять сброс после каждого выполнения.</span><span class="sxs-lookup"><span data-stu-id="8e62d-415">We recommend a reset after every demo run.</span></span> <span data-ttu-id="8e62d-416">Поскольку рабочая нагрузка состоит только из вставки, каждое выполнение будет потреблять больше памяти, поэтому необходимо выполнять сброс, чтобы не задействовать всю память.</span><span class="sxs-lookup"><span data-stu-id="8e62d-416">Because this workload is insert-only, each run will consume more memory, and thus a reset is required to prevent running out of memory.</span></span> <span data-ttu-id="8e62d-417">Количество используемой после запуска памяти описывается в разделе [Использование памяти после выполнения рабочей нагрузки](#Memoryutilizationafterrunningtheworkload).</span><span class="sxs-lookup"><span data-stu-id="8e62d-417">The amount of memory consumed after a run is discussed in Section [Memory utilization after running the workload](#Memoryutilizationafterrunningtheworkload).</span></span>  
  
###  <a name="troubleshooting-slow-running-tests"></a><a name="Troubleshootingslow-runningtests"></a> <span data-ttu-id="8e62d-418">Устранение неполадок тестов, которые выполняются медленно</span><span class="sxs-lookup"><span data-stu-id="8e62d-418">Troubleshooting slow-running tests</span></span>  
 <span data-ttu-id="8e62d-419">Результаты теста, как правило, зависят от оборудования и уровня параллелизма во время его выполнения.</span><span class="sxs-lookup"><span data-stu-id="8e62d-419">Test results will typically vary with hardware, and also the level of concurrency used in the test run.</span></span> <span data-ttu-id="8e62d-420">Необходимо проверить несколько моментов, если результаты отличаются от ожидаемых.</span><span class="sxs-lookup"><span data-stu-id="8e62d-420">A couple of things to look for if the results are not as expected:</span></span>  
  
-   <span data-ttu-id="8e62d-421">Число одновременно выполняемых транзакций: при выполнении рабочей нагрузки в одном потоке с использованием [!INCLUDE[hek_2](../includes/hek-2-md.md)] производительность возрастет, скорее всего, менее чем в два раза.</span><span class="sxs-lookup"><span data-stu-id="8e62d-421">Number of concurrent transactions: When running the workload on a single thread, performance gain with [!INCLUDE[hek_2](../includes/hek-2-md.md)] will likely be less than 2X.</span></span> <span data-ttu-id="8e62d-422">Конфликты кратковременных блокировок становятся большой проблемой только при высоком уровне параллелизма.</span><span class="sxs-lookup"><span data-stu-id="8e62d-422">Latch contention is only a big problem if there is a high level of concurrency.</span></span>  
  
-   <span data-ttu-id="8e62d-423">Мало ядер, доступных для [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]: это означает, что в системе будет низкий уровень параллелизма, так как число параллельно исполняемых транзакций будет равно числу ядер, доступных для SQL.</span><span class="sxs-lookup"><span data-stu-id="8e62d-423">Low number of cores available to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]: This means there will be a low level of concurrency in the system, as there can only be as many concurrently executing transactions as there are cores available to SQL.</span></span>  
  
    -   <span data-ttu-id="8e62d-424">Симптом: высокий процент использования ЦП при выполнении рабочей нагрузки по таблицам, размещенным на диске, означает, что объем состязаний невелик. Это указывает на недостаток параллелизма.</span><span class="sxs-lookup"><span data-stu-id="8e62d-424">Symptom: if the CPU utilization is high when running the workload on disk-based tables, this means there is not a lot of contention, pointing to a lack of concurrency.</span></span>  
  
-   <span data-ttu-id="8e62d-425">Скорость работы диска, где расположен журнал. Если диск, на котором расположен журнал, не успевает за пропускной способностью транзакций в системе, формируется узкое место рабочей нагрузки, связанное с вводом-выводом журнала.</span><span class="sxs-lookup"><span data-stu-id="8e62d-425">Speed of the log drive: If the log drive cannot keep up with the level of transaction throughput in the system, the workload becomes bottlenecked on log IO.</span></span> <span data-ttu-id="8e62d-426">Несмотря на то что в [!INCLUDE[hek_2](../includes/hek-2-md.md)]ведение журнала стало более эффективным, если ввод-вывод журнала является узким местом, потенциальный прирост производительности будет ограничен.</span><span class="sxs-lookup"><span data-stu-id="8e62d-426">Although logging is more efficient with [!INCLUDE[hek_2](../includes/hek-2-md.md)], if log IO is a bottleneck, the potential performance gain is limited.</span></span>  
  
    -   <span data-ttu-id="8e62d-427">Симптом: если при выполнении рабочей нагрузки в оптимизированных для памяти таблицах использование ЦП не приближается к 100 % или подвержено очень высоким колебаниям, то, возможно, существует узкое место, связанное с вводом-выводом журнала.</span><span class="sxs-lookup"><span data-stu-id="8e62d-427">Symptom: if the CPU utilization is not close to 100% or is very spiky when running the workload on memory-optimized tables, it is possible there is a log IO bottleneck.</span></span> <span data-ttu-id="8e62d-428">Проверить это можно, открыв системный монитор и оценив длину очереди для диска журнала.</span><span class="sxs-lookup"><span data-stu-id="8e62d-428">This can be confirmed by opening Resource Monitor and looking at the queue length for the log drive.</span></span>  
  
##  <a name="memory-and-disk-space-utilization-in-the-sample"></a><a name="MemoryandDiskSpaceUtilizationintheSample"></a> <span data-ttu-id="8e62d-429">Использование памяти и места на диске образцом</span><span class="sxs-lookup"><span data-stu-id="8e62d-429">Memory and Disk Space Utilization in the Sample</span></span>  
 <span data-ttu-id="8e62d-430">Ниже описано, что следует ожидать в отношении использования памяти и места на диске для образца базы данных.</span><span class="sxs-lookup"><span data-stu-id="8e62d-430">In the below we describe what to expect in terms of memory and disk space utilization for the sample database.</span></span> <span data-ttu-id="8e62d-431">Также приводятся результаты, отмеченные на тестовом сервере с 16 логическими ядрами.</span><span class="sxs-lookup"><span data-stu-id="8e62d-431">We also show the results we have seen in on a test server with 16 logical cores.</span></span>  
  
###  <a name="memory-utilization-for-the-memory-optimized-tables"></a><a name="Memoryutilizationforthememory-optimizedtables"></a> <span data-ttu-id="8e62d-432">Использование памяти оптимизированными для памяти таблицами</span><span class="sxs-lookup"><span data-stu-id="8e62d-432">Memory utilization for the memory-optimized tables</span></span>  
  
#### <a name="overall-utilization-of-the-database"></a><span data-ttu-id="8e62d-433">Общее использование базы данных</span><span class="sxs-lookup"><span data-stu-id="8e62d-433">Overall utilization of the database</span></span>  
 <span data-ttu-id="8e62d-434">Следующий запрос может быть использован для получения общей загрузки памяти для системы [!INCLUDE[hek_2](../includes/hek-2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8e62d-434">The following query can be used to obtain the total memory utilization for [!INCLUDE[hek_2](../includes/hek-2-md.md)] in the system.</span></span>  
  
```  
SELECT type  
   , name  
, pages_kb/1024 AS pages_MB   
FROM sys.dm_os_memory_clerks WHERE type LIKE '%xtp%'  
```  
  
 <span data-ttu-id="8e62d-435">Моментальный снимок сразу после создания базы данных:</span><span class="sxs-lookup"><span data-stu-id="8e62d-435">Snapshot after the database has just been created:</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="8e62d-436">**type**</span><span class="sxs-lookup"><span data-stu-id="8e62d-436">**type**</span></span>|<span data-ttu-id="8e62d-437">**name**</span><span class="sxs-lookup"><span data-stu-id="8e62d-437">**name**</span></span>|<span data-ttu-id="8e62d-438">**pages_MB**</span><span class="sxs-lookup"><span data-stu-id="8e62d-438">**pages_MB**</span></span>|  
|<span data-ttu-id="8e62d-439">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="8e62d-439">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="8e62d-440">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="8e62d-440">Default</span></span>|<span data-ttu-id="8e62d-441">94</span><span class="sxs-lookup"><span data-stu-id="8e62d-441">94</span></span>|  
|<span data-ttu-id="8e62d-442">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="8e62d-442">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="8e62d-443">DB_ID_5</span><span class="sxs-lookup"><span data-stu-id="8e62d-443">DB_ID_5</span></span>|<span data-ttu-id="8e62d-444">877</span><span class="sxs-lookup"><span data-stu-id="8e62d-444">877</span></span>|  
|<span data-ttu-id="8e62d-445">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="8e62d-445">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="8e62d-446">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="8e62d-446">Default</span></span>|<span data-ttu-id="8e62d-447">0</span><span class="sxs-lookup"><span data-stu-id="8e62d-447">0</span></span>|  
|<span data-ttu-id="8e62d-448">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="8e62d-448">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="8e62d-449">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="8e62d-449">Default</span></span>|<span data-ttu-id="8e62d-450">0</span><span class="sxs-lookup"><span data-stu-id="8e62d-450">0</span></span>|  
  
 <span data-ttu-id="8e62d-451">Клерки памяти по умолчанию содержат структуры памяти во всей системе и являются относительно небольшими.</span><span class="sxs-lookup"><span data-stu-id="8e62d-451">The default memory clerks contain system-wide memory structures and are relatively small.</span></span> <span data-ttu-id="8e62d-452">Клерк памяти, предназначенный для пользовательской базы данных (в данном случае это база данных с идентификатором 5), составляет примерно 900 МБ.</span><span class="sxs-lookup"><span data-stu-id="8e62d-452">The memory clerk for the user database, in this case database with ID 5, is about 900MB.</span></span>  
  
#### <a name="memory-utilization-per-table"></a><span data-ttu-id="8e62d-453">Использование памяти на таблицу</span><span class="sxs-lookup"><span data-stu-id="8e62d-453">Memory utilization per table</span></span>  
 <span data-ttu-id="8e62d-454">С помощью следующего запроса можно получить объем использования памяти для отдельных таблиц и их индексов.</span><span class="sxs-lookup"><span data-stu-id="8e62d-454">The following query can be used to drill down into the memory utilization of the individual tables and their indexes:</span></span>  
  
```  
SELECT object_name(t.object_id) AS [Table Name]  
     , memory_allocated_for_table_kb  
 , memory_allocated_for_indexes_kb  
FROM sys.dm_db_xtp_table_memory_stats dms JOIN sys.tables t   
ON dms.object_id=t.object_id  
WHERE t.type='U'  
```  
  
 <span data-ttu-id="8e62d-455">Далее приведены результаты выполнения этого запроса для свежей установки образца.</span><span class="sxs-lookup"><span data-stu-id="8e62d-455">The following shows the results of this query for a fresh installation of the sample:</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="8e62d-456">**Имя таблицы**</span><span class="sxs-lookup"><span data-stu-id="8e62d-456">**Table Name**</span></span>|<span data-ttu-id="8e62d-457">**memory_allocated_for_table_kb**</span><span class="sxs-lookup"><span data-stu-id="8e62d-457">**memory_allocated_for_table_kb**</span></span>|<span data-ttu-id="8e62d-458">**memory_allocated_for_indexes_kb**</span><span class="sxs-lookup"><span data-stu-id="8e62d-458">**memory_allocated_for_indexes_kb**</span></span>|  
|<span data-ttu-id="8e62d-459">SpecialOfferProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="8e62d-459">SpecialOfferProduct_inmem</span></span>|<span data-ttu-id="8e62d-460">64</span><span class="sxs-lookup"><span data-stu-id="8e62d-460">64</span></span>|<span data-ttu-id="8e62d-461">3840</span><span class="sxs-lookup"><span data-stu-id="8e62d-461">3840</span></span>|  
|<span data-ttu-id="8e62d-462">DemoSalesOrderHeaderSeed</span><span class="sxs-lookup"><span data-stu-id="8e62d-462">DemoSalesOrderHeaderSeed</span></span>|<span data-ttu-id="8e62d-463">1984</span><span class="sxs-lookup"><span data-stu-id="8e62d-463">1984</span></span>|<span data-ttu-id="8e62d-464">5504</span><span class="sxs-lookup"><span data-stu-id="8e62d-464">5504</span></span>|  
|<span data-ttu-id="8e62d-465">SalesOrderDetail_inmem</span><span class="sxs-lookup"><span data-stu-id="8e62d-465">SalesOrderDetail_inmem</span></span>|<span data-ttu-id="8e62d-466">15316</span><span class="sxs-lookup"><span data-stu-id="8e62d-466">15316</span></span>|<span data-ttu-id="8e62d-467">663552</span><span class="sxs-lookup"><span data-stu-id="8e62d-467">663552</span></span>|  
|<span data-ttu-id="8e62d-468">DemoSalesOrderDetailSeed</span><span class="sxs-lookup"><span data-stu-id="8e62d-468">DemoSalesOrderDetailSeed</span></span>|<span data-ttu-id="8e62d-469">64</span><span class="sxs-lookup"><span data-stu-id="8e62d-469">64</span></span>|<span data-ttu-id="8e62d-470">10432</span><span class="sxs-lookup"><span data-stu-id="8e62d-470">10432</span></span>|  
|<span data-ttu-id="8e62d-471">SpecialOffer_inmem</span><span class="sxs-lookup"><span data-stu-id="8e62d-471">SpecialOffer_inmem</span></span>|<span data-ttu-id="8e62d-472">3</span><span class="sxs-lookup"><span data-stu-id="8e62d-472">3</span></span>|<span data-ttu-id="8e62d-473">8192</span><span class="sxs-lookup"><span data-stu-id="8e62d-473">8192</span></span>|  
|<span data-ttu-id="8e62d-474">SalesOrderHeader_inmem</span><span class="sxs-lookup"><span data-stu-id="8e62d-474">SalesOrderHeader_inmem</span></span>|<span data-ttu-id="8e62d-475">7168</span><span class="sxs-lookup"><span data-stu-id="8e62d-475">7168</span></span>|<span data-ttu-id="8e62d-476">147456</span><span class="sxs-lookup"><span data-stu-id="8e62d-476">147456</span></span>|  
|<span data-ttu-id="8e62d-477">Product_inmem</span><span class="sxs-lookup"><span data-stu-id="8e62d-477">Product_inmem</span></span>|<span data-ttu-id="8e62d-478">124</span><span class="sxs-lookup"><span data-stu-id="8e62d-478">124</span></span>|<span data-ttu-id="8e62d-479">12352</span><span class="sxs-lookup"><span data-stu-id="8e62d-479">12352</span></span>|  
  
 <span data-ttu-id="8e62d-480">Как можно увидеть, таблицы довольно небольшие: SalesOrderHeader_inmem занимает примерно 7 МБ, а SalesOrderDetail_inmem — примерно 15 МБ.</span><span class="sxs-lookup"><span data-stu-id="8e62d-480">As you can see the tables are fairly small: SalesOrderHeader_inmem is about 7MB, and SalesOrderDetail_inmem is about 15MB in size.</span></span>  
  
 <span data-ttu-id="8e62d-481">Поразительнее всего здесь размер памяти, выделенной для индексов, в сравнении с размером данных таблиц.</span><span class="sxs-lookup"><span data-stu-id="8e62d-481">What is striking here is the size of the memory allocated for indexes, compared to the size of the table data.</span></span> <span data-ttu-id="8e62d-482">Причина этого заключается в том, что размер индексов HASH в образце задан для данных большего объема.</span><span class="sxs-lookup"><span data-stu-id="8e62d-482">That is because the hash indexes in the sample are pre-sized for a larger data size.</span></span> <span data-ttu-id="8e62d-483">Обратите внимание, что индексы HASH имеют фиксированный размер, поэтому их размер не будет расти вместе с размером данных в таблице.</span><span class="sxs-lookup"><span data-stu-id="8e62d-483">Note that hash indexes have a fixed size, and thus their size will not grow with the size of data in the table.</span></span>  
  
####  <a name="memory-utilization-after-running-the-workload"></a><a name="Memoryutilizationafterrunningtheworkload"></a> <span data-ttu-id="8e62d-484">Использование памяти после выполнения рабочей нагрузки</span><span class="sxs-lookup"><span data-stu-id="8e62d-484">Memory utilization after running the workload</span></span>  
 <span data-ttu-id="8e62d-485">После вставки 10 миллионов заказов на продажу общий объем использованной памяти будет примерно таким:</span><span class="sxs-lookup"><span data-stu-id="8e62d-485">After insert 10 million sales orders, the all-up memory utilization looks similar to the following:</span></span>  
  
```  
SELECT type  
, name  
, pages_kb/1024 AS pages_MB   
FROM sys.dm_os_memory_clerks WHERE type LIKE '%xtp%'  
```  
  
||||  
|-|-|-|  
|<span data-ttu-id="8e62d-486">**type**</span><span class="sxs-lookup"><span data-stu-id="8e62d-486">**type**</span></span>|<span data-ttu-id="8e62d-487">**name**</span><span class="sxs-lookup"><span data-stu-id="8e62d-487">**name**</span></span>|<span data-ttu-id="8e62d-488">**pages_MB**</span><span class="sxs-lookup"><span data-stu-id="8e62d-488">**pages_MB**</span></span>|  
|<span data-ttu-id="8e62d-489">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="8e62d-489">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="8e62d-490">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="8e62d-490">Default</span></span>|<span data-ttu-id="8e62d-491">146</span><span class="sxs-lookup"><span data-stu-id="8e62d-491">146</span></span>|  
|<span data-ttu-id="8e62d-492">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="8e62d-492">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="8e62d-493">DB_ID_5</span><span class="sxs-lookup"><span data-stu-id="8e62d-493">DB_ID_5</span></span>|<span data-ttu-id="8e62d-494">7374</span><span class="sxs-lookup"><span data-stu-id="8e62d-494">7374</span></span>|  
|<span data-ttu-id="8e62d-495">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="8e62d-495">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="8e62d-496">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="8e62d-496">Default</span></span>|<span data-ttu-id="8e62d-497">0</span><span class="sxs-lookup"><span data-stu-id="8e62d-497">0</span></span>|  
|<span data-ttu-id="8e62d-498">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="8e62d-498">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="8e62d-499">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="8e62d-499">Default</span></span>|<span data-ttu-id="8e62d-500">0</span><span class="sxs-lookup"><span data-stu-id="8e62d-500">0</span></span>|  
  
 <span data-ttu-id="8e62d-501">Как видите, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] использует чуть меньше 8 ГБ под оптимизированные для памяти таблицы и индексы из образца базы данных.</span><span class="sxs-lookup"><span data-stu-id="8e62d-501">As you can see, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is using a bit under 8GB for the memory-optimized tables and indexes in the sample database.</span></span>  
  
 <span data-ttu-id="8e62d-502">Подробные данные об использовании памяти для каждой таблицы после одного выполнения:</span><span class="sxs-lookup"><span data-stu-id="8e62d-502">Looking at the detailed memory usage per table after one example run:</span></span>  
  
```  
SELECT object_name(t.object_id) AS [Table Name]  
     , memory_allocated_for_table_kb  
 , memory_allocated_for_indexes_kb  
FROM sys.dm_db_xtp_table_memory_stats dms JOIN sys.tables t   
ON dms.object_id=t.object_id  
WHERE t.type='U'  
```  
  
||||  
|-|-|-|  
|<span data-ttu-id="8e62d-503">**Имя таблицы**</span><span class="sxs-lookup"><span data-stu-id="8e62d-503">**Table Name**</span></span>|<span data-ttu-id="8e62d-504">**memory_allocated_for_table_kb**</span><span class="sxs-lookup"><span data-stu-id="8e62d-504">**memory_allocated_for_table_kb**</span></span>|<span data-ttu-id="8e62d-505">**memory_allocated_for_indexes_kb**</span><span class="sxs-lookup"><span data-stu-id="8e62d-505">**memory_allocated_for_indexes_kb**</span></span>|  
|<span data-ttu-id="8e62d-506">SalesOrderDetail_inmem</span><span class="sxs-lookup"><span data-stu-id="8e62d-506">SalesOrderDetail_inmem</span></span>|<span data-ttu-id="8e62d-507">5113761</span><span class="sxs-lookup"><span data-stu-id="8e62d-507">5113761</span></span>|<span data-ttu-id="8e62d-508">663552</span><span class="sxs-lookup"><span data-stu-id="8e62d-508">663552</span></span>|  
|<span data-ttu-id="8e62d-509">DemoSalesOrderDetailSeed</span><span class="sxs-lookup"><span data-stu-id="8e62d-509">DemoSalesOrderDetailSeed</span></span>|<span data-ttu-id="8e62d-510">64</span><span class="sxs-lookup"><span data-stu-id="8e62d-510">64</span></span>|<span data-ttu-id="8e62d-511">10368</span><span class="sxs-lookup"><span data-stu-id="8e62d-511">10368</span></span>|  
|<span data-ttu-id="8e62d-512">SpecialOffer_inmem</span><span class="sxs-lookup"><span data-stu-id="8e62d-512">SpecialOffer_inmem</span></span>|<span data-ttu-id="8e62d-513">2</span><span class="sxs-lookup"><span data-stu-id="8e62d-513">2</span></span>|<span data-ttu-id="8e62d-514">8192</span><span class="sxs-lookup"><span data-stu-id="8e62d-514">8192</span></span>|  
|<span data-ttu-id="8e62d-515">SalesOrderHeader_inmem</span><span class="sxs-lookup"><span data-stu-id="8e62d-515">SalesOrderHeader_inmem</span></span>|<span data-ttu-id="8e62d-516">1575679</span><span class="sxs-lookup"><span data-stu-id="8e62d-516">1575679</span></span>|<span data-ttu-id="8e62d-517">147456</span><span class="sxs-lookup"><span data-stu-id="8e62d-517">147456</span></span>|  
|<span data-ttu-id="8e62d-518">Product_inmem</span><span class="sxs-lookup"><span data-stu-id="8e62d-518">Product_inmem</span></span>|<span data-ttu-id="8e62d-519">111</span><span class="sxs-lookup"><span data-stu-id="8e62d-519">111</span></span>|<span data-ttu-id="8e62d-520">12032</span><span class="sxs-lookup"><span data-stu-id="8e62d-520">12032</span></span>|  
|<span data-ttu-id="8e62d-521">SpecialOfferProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="8e62d-521">SpecialOfferProduct_inmem</span></span>|<span data-ttu-id="8e62d-522">64</span><span class="sxs-lookup"><span data-stu-id="8e62d-522">64</span></span>|<span data-ttu-id="8e62d-523">3712</span><span class="sxs-lookup"><span data-stu-id="8e62d-523">3712</span></span>|  
|<span data-ttu-id="8e62d-524">DemoSalesOrderHeaderSeed</span><span class="sxs-lookup"><span data-stu-id="8e62d-524">DemoSalesOrderHeaderSeed</span></span>|<span data-ttu-id="8e62d-525">1984</span><span class="sxs-lookup"><span data-stu-id="8e62d-525">1984</span></span>|<span data-ttu-id="8e62d-526">5504</span><span class="sxs-lookup"><span data-stu-id="8e62d-526">5504</span></span>|  
  
 <span data-ttu-id="8e62d-527">Как видите, общий объем данных составляет примерно 6,5 ГБ.</span><span class="sxs-lookup"><span data-stu-id="8e62d-527">We can see a total of about 6.5GB of data.</span></span> <span data-ttu-id="8e62d-528">Обратите внимание, что индексы в таблицах SalesOrderHeader_inmem и SalesOrderDetail_inmem имеют тот же размер, что и индексы до вставки заказов на продажу.</span><span class="sxs-lookup"><span data-stu-id="8e62d-528">Notice that the size of the indexes on the table SalesOrderHeader_inmem and SalesOrderDetail_inmem is the same as the size of the indexes before inserting the sales orders.</span></span> <span data-ttu-id="8e62d-529">Размер индексов не изменился, потому что в обеих таблицах используются индексы HASH, а они являются статическими.</span><span class="sxs-lookup"><span data-stu-id="8e62d-529">The index size did not change because both tables are using hash indexes, and hash indexes are static.</span></span>  
  
#### <a name="after-demo-reset"></a><span data-ttu-id="8e62d-530">После сброса образца</span><span class="sxs-lookup"><span data-stu-id="8e62d-530">After demo reset</span></span>  
 <span data-ttu-id="8e62d-531">Для сброса образца используется хранимая процедура Demo.usp_DemoReset.</span><span class="sxs-lookup"><span data-stu-id="8e62d-531">The stored procedure Demo.usp_DemoReset can be used to reset the demo.</span></span> <span data-ttu-id="8e62d-532">Она удаляет данные из таблиц SalesOrderHeader_inmem и SalesOrderDetail_inmem и вносит в них данные из исходных таблиц SalesOrderHeader и SalesOrderDetail.</span><span class="sxs-lookup"><span data-stu-id="8e62d-532">It deletes the data in the tables SalesOrderHeader_inmem and SalesOrderDetail_inmem, and re-seeds the data from the original tables SalesOrderHeader and SalesOrderDetail.</span></span>  
  
 <span data-ttu-id="8e62d-533">Теперь, даже после удаления строк из таблиц, это не означает, что память сразу же будет освобождена.</span><span class="sxs-lookup"><span data-stu-id="8e62d-533">Now, even though the rows in the tables have been deleted, this does not mean that memory is reclaimed immediately.</span></span> [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="8e62d-534">возвращает память от удаленных строк из оптимизированных для памяти таблиц в фоновом режиме по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="8e62d-534">reclaims memory from deleted rows in memory-optimized tables in the background, as needed.</span></span> <span data-ttu-id="8e62d-535">Вы увидите, что сразу же после сброса образца при отсутствии в системе рабочей нагрузки по обработке транзакций память от удаленных строк остается занятой.</span><span class="sxs-lookup"><span data-stu-id="8e62d-535">You will see that immediately after demo reset, with no transactional workload on the system, memory from deleted rows is not yet reclaimed:</span></span>  
  
```  
SELECT type  
, name  
, pages_kb/1024 AS pages_MB   
FROM sys.dm_os_memory_clerks WHERE type LIKE '%xtp%'  
```  
  
||||  
|-|-|-|  
|<span data-ttu-id="8e62d-536">**type**</span><span class="sxs-lookup"><span data-stu-id="8e62d-536">**type**</span></span>|<span data-ttu-id="8e62d-537">**name**</span><span class="sxs-lookup"><span data-stu-id="8e62d-537">**name**</span></span>|<span data-ttu-id="8e62d-538">**pages_MB**</span><span class="sxs-lookup"><span data-stu-id="8e62d-538">**pages_MB**</span></span>|  
|<span data-ttu-id="8e62d-539">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="8e62d-539">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="8e62d-540">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="8e62d-540">Default</span></span>|<span data-ttu-id="8e62d-541">2261</span><span class="sxs-lookup"><span data-stu-id="8e62d-541">2261</span></span>|  
|<span data-ttu-id="8e62d-542">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="8e62d-542">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="8e62d-543">DB_ID_5</span><span class="sxs-lookup"><span data-stu-id="8e62d-543">DB_ID_5</span></span>|<span data-ttu-id="8e62d-544">7396</span><span class="sxs-lookup"><span data-stu-id="8e62d-544">7396</span></span>|  
|<span data-ttu-id="8e62d-545">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="8e62d-545">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="8e62d-546">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="8e62d-546">Default</span></span>|<span data-ttu-id="8e62d-547">0</span><span class="sxs-lookup"><span data-stu-id="8e62d-547">0</span></span>|  
|<span data-ttu-id="8e62d-548">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="8e62d-548">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="8e62d-549">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="8e62d-549">Default</span></span>|<span data-ttu-id="8e62d-550">0</span><span class="sxs-lookup"><span data-stu-id="8e62d-550">0</span></span>|  
  
 <span data-ttu-id="8e62d-551">Это ожидаемо: память будет освобождаться при выполнении транзакционной рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="8e62d-551">This is expected: memory will be reclaimed when the transactional workload is running.</span></span>  
  
 <span data-ttu-id="8e62d-552">Если снова запустить демонстрационную рабочую нагрузку, то первоначально объем использованной памяти понизится по мере очистки удаленных ранее строк.</span><span class="sxs-lookup"><span data-stu-id="8e62d-552">If you start a second run of the demo workload you will see the memory utilization decrease initially, as the previously deleted rows are cleaned up.</span></span> <span data-ttu-id="8e62d-553">В определенный момент объем использованной памяти снова начнет увеличиваться вплоть до завершения выполнения рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="8e62d-553">At some point the memory size will increase again, until the workload finishes.</span></span> <span data-ttu-id="8e62d-554">После вставки 10 миллионов строк после сброса демонстрации загрузка памяти будет очень похожа на загрузку после первоначального запуска.</span><span class="sxs-lookup"><span data-stu-id="8e62d-554">After inserting 10 million rows after demo reset, the memory utilization will be very similar to the utilization after the first run.</span></span> <span data-ttu-id="8e62d-555">Пример:</span><span class="sxs-lookup"><span data-stu-id="8e62d-555">For example:</span></span>  
  
```  
SELECT type  
, name  
, pages_kb/1024 AS pages_MB   
FROM sys.dm_os_memory_clerks WHERE type LIKE '%xtp%'  
```  
  
||||  
|-|-|-|  
|<span data-ttu-id="8e62d-556">**type**</span><span class="sxs-lookup"><span data-stu-id="8e62d-556">**type**</span></span>|<span data-ttu-id="8e62d-557">**name**</span><span class="sxs-lookup"><span data-stu-id="8e62d-557">**name**</span></span>|<span data-ttu-id="8e62d-558">**pages_MB**</span><span class="sxs-lookup"><span data-stu-id="8e62d-558">**pages_MB**</span></span>|  
|<span data-ttu-id="8e62d-559">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="8e62d-559">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="8e62d-560">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="8e62d-560">Default</span></span>|<span data-ttu-id="8e62d-561">1863</span><span class="sxs-lookup"><span data-stu-id="8e62d-561">1863</span></span>|  
|<span data-ttu-id="8e62d-562">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="8e62d-562">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="8e62d-563">DB_ID_5</span><span class="sxs-lookup"><span data-stu-id="8e62d-563">DB_ID_5</span></span>|<span data-ttu-id="8e62d-564">7390</span><span class="sxs-lookup"><span data-stu-id="8e62d-564">7390</span></span>|  
|<span data-ttu-id="8e62d-565">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="8e62d-565">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="8e62d-566">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="8e62d-566">Default</span></span>|<span data-ttu-id="8e62d-567">0</span><span class="sxs-lookup"><span data-stu-id="8e62d-567">0</span></span>|  
|<span data-ttu-id="8e62d-568">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="8e62d-568">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="8e62d-569">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="8e62d-569">Default</span></span>|<span data-ttu-id="8e62d-570">0</span><span class="sxs-lookup"><span data-stu-id="8e62d-570">0</span></span>|  
  
### <a name="disk-utilization-for-memory-optimized-tables"></a><span data-ttu-id="8e62d-571">Использование диска оптимизированными для памяти таблицами</span><span class="sxs-lookup"><span data-stu-id="8e62d-571">Disk utilization for memory-optimized tables</span></span>  
 <span data-ttu-id="8e62d-572">Общий размер на диске файлов контрольных точек базы данных в данное время можно узнать, выполнив следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="8e62d-572">The overall on-disk size for the checkpoint files of a database at a given time can be found using the query:</span></span>  
  
```  
SELECT SUM(df.size) * 8 / 1024 AS [On-disk size in MB]  
FROM sys.filegroups f JOIN sys.database_files df   
   ON f.data_space_id=df.data_space_id  
WHERE f.type=N'FX'  
  
```  
  
#### <a name="initial-state"></a><span data-ttu-id="8e62d-573">Начальное состояние</span><span class="sxs-lookup"><span data-stu-id="8e62d-573">Initial state</span></span>  
 <span data-ttu-id="8e62d-574">Когда образцы файловой группы и оптимизированных для памяти таблиц создаются первоначально, формируется несколько файлов контрольных точек и система начинает заполнять эти файлы — их число зависит от количества логических процессоров в системе.</span><span class="sxs-lookup"><span data-stu-id="8e62d-574">When the sample filegroup and sample memory-optimized tables are created initially, a number of checkpoint files are pre-created and the system starts filling the files - the number of checkpoint files pre-created depends on the number of logical processors in the system.</span></span> <span data-ttu-id="8e62d-575">Поскольку изначально образец очень мал, предварительно созданные файлы будут вначале по большей части пустыми.</span><span class="sxs-lookup"><span data-stu-id="8e62d-575">As the sample is initially very small, the pre-created files will be mostly empty after initial create.</span></span>  
  
 <span data-ttu-id="8e62d-576">Далее приведен начальный размер на диске для образца на компьютере с 16 логическими процессорами.</span><span class="sxs-lookup"><span data-stu-id="8e62d-576">The following shows the initial on-disk size for the sample on a machine with 16 logical processors:</span></span>  
  
```  
SELECT SUM(df.size) * 8 / 1024 AS [On-disk size in MB]  
FROM sys.filegroups f JOIN sys.database_files df   
   ON f.data_space_id=df.data_space_id  
WHERE f.type=N'FX'  
```  
  
||  
|-|  
|<span data-ttu-id="8e62d-577">**Размер на диске в МБ**</span><span class="sxs-lookup"><span data-stu-id="8e62d-577">**On-disk size in MB**</span></span>|  
|<span data-ttu-id="8e62d-578">2312</span><span class="sxs-lookup"><span data-stu-id="8e62d-578">2312</span></span>|  
  
 <span data-ttu-id="8e62d-579">Как видите, существует большая разница между размером файлов контрольных точек на диске, который составляет 2,3 ГБ, и фактическим размером данных, равным почти 30 МБ.</span><span class="sxs-lookup"><span data-stu-id="8e62d-579">As you can see, there is a big discrepancy between the on-disk size of the checkpoint files, which is 2.3GB, and the actual data size, which is closer to 30MB.</span></span>  
  
 <span data-ttu-id="8e62d-580">Чтобы лучше разобраться, откуда взялся такой показатель использования дискового пространства, можно выполнить следующий запрос.</span><span class="sxs-lookup"><span data-stu-id="8e62d-580">Looking closer at where the disk-space utilization comes from, you can use the following query.</span></span> <span data-ttu-id="8e62d-581">Размер на диске, возвращаемый этим запросом, является приблизительным для файлов, находящихся в состоянии 5 (REQUIRED FOR BACKUP/HA), 6 (IN TRANSITION TO TOMBSTONE) или 7 (TOMBSTONE).</span><span class="sxs-lookup"><span data-stu-id="8e62d-581">The size on disk returned by this query is approximate for files with state in 5 (REQUIRED FOR BACKUP/HA), 6 (IN TRANSITION TO TOMBSTONE), or 7 (TOMBSTONE).</span></span>  
  
```  
SELECT state_desc  
 , file_type_desc  
 , COUNT(*) AS [count]  
 , SUM(CASE  
   WHEN state = 5 AND file_type=0 THEN 128*1024*1024  
   WHEN state = 5 AND file_type=1 THEN 8*1024*1024  
   WHEN state IN (6,7) THEN 68*1024*1024  
   ELSE file_size_in_bytes  
    END) / 1024 / 1024 AS [on-disk size MB]   
FROM sys.dm_db_xtp_checkpoint_files  
GROUP BY state, state_desc, file_type, file_type_desc  
ORDER BY state, file_type  
```  
  
 <span data-ttu-id="8e62d-582">Для первоначального состояния образца результат будет выглядеть примерно как для сервера с 16 логическими процессорами:</span><span class="sxs-lookup"><span data-stu-id="8e62d-582">For the initial state of the sample, the result will look something like for a server with 16 logical processors:</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="8e62d-583">**state_desc**</span><span class="sxs-lookup"><span data-stu-id="8e62d-583">**state_desc**</span></span>|<span data-ttu-id="8e62d-584">**file_type_desc**</span><span class="sxs-lookup"><span data-stu-id="8e62d-584">**file_type_desc**</span></span>|<span data-ttu-id="8e62d-585">**count**</span><span class="sxs-lookup"><span data-stu-id="8e62d-585">**count**</span></span>|<span data-ttu-id="8e62d-586">**Размер на диске в МБ**</span><span class="sxs-lookup"><span data-stu-id="8e62d-586">**on-disk size MB**</span></span>|  
|<span data-ttu-id="8e62d-587">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="8e62d-587">PRECREATED</span></span>|<span data-ttu-id="8e62d-588">DATA</span><span class="sxs-lookup"><span data-stu-id="8e62d-588">DATA</span></span>|<span data-ttu-id="8e62d-589">16</span><span class="sxs-lookup"><span data-stu-id="8e62d-589">16</span></span>|<span data-ttu-id="8e62d-590">2048</span><span class="sxs-lookup"><span data-stu-id="8e62d-590">2048</span></span>|  
|<span data-ttu-id="8e62d-591">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="8e62d-591">PRECREATED</span></span>|<span data-ttu-id="8e62d-592">DELTA</span><span class="sxs-lookup"><span data-stu-id="8e62d-592">DELTA</span></span>|<span data-ttu-id="8e62d-593">16</span><span class="sxs-lookup"><span data-stu-id="8e62d-593">16</span></span>|<span data-ttu-id="8e62d-594">128</span><span class="sxs-lookup"><span data-stu-id="8e62d-594">128</span></span>|  
|<span data-ttu-id="8e62d-595">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="8e62d-595">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="8e62d-596">DATA</span><span class="sxs-lookup"><span data-stu-id="8e62d-596">DATA</span></span>|<span data-ttu-id="8e62d-597">1</span><span class="sxs-lookup"><span data-stu-id="8e62d-597">1</span></span>|<span data-ttu-id="8e62d-598">128</span><span class="sxs-lookup"><span data-stu-id="8e62d-598">128</span></span>|  
|<span data-ttu-id="8e62d-599">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="8e62d-599">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="8e62d-600">DELTA</span><span class="sxs-lookup"><span data-stu-id="8e62d-600">DELTA</span></span>|<span data-ttu-id="8e62d-601">1</span><span class="sxs-lookup"><span data-stu-id="8e62d-601">1</span></span>|<span data-ttu-id="8e62d-602">8</span><span class="sxs-lookup"><span data-stu-id="8e62d-602">8</span></span>|  
  
 <span data-ttu-id="8e62d-603">Как видите, большая часть объема используется воссозданными файлами данных и разностными файлами.</span><span class="sxs-lookup"><span data-stu-id="8e62d-603">As you can see, most of the space is used by precreated data and delta files.</span></span> [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="8e62d-604">предварительно создает одну пару файлов (файл данных и разностный файл) на логический процессор.</span><span class="sxs-lookup"><span data-stu-id="8e62d-604">pre-created one pair of (data, delta) files per logical processor.</span></span> <span data-ttu-id="8e62d-605">Кроме того, файлы данных имеют заранее заданный размер в 128 МБ, а разностные файлы — в 8 МБ, чтобы сделать вставку данных в эти файлы более эффективной.</span><span class="sxs-lookup"><span data-stu-id="8e62d-605">In addition, data files are pre-sized at 128MB, and delta files at 8MB, in order to make inserting data into these files more efficient.</span></span>  
  
 <span data-ttu-id="8e62d-606">Сами данные из оптимизированных для памяти таблиц находятся в одном файле данных.</span><span class="sxs-lookup"><span data-stu-id="8e62d-606">The actual data in the memory-optimized tables is in the single data file.</span></span>  
  
#### <a name="after-running-the-workload"></a><span data-ttu-id="8e62d-607">После выполнения рабочей нагрузки</span><span class="sxs-lookup"><span data-stu-id="8e62d-607">After running the workload</span></span>  
 <span data-ttu-id="8e62d-608">После единичного запуска теста, производящего вставку 10 миллионов заказов на продажу, общий размер на диске выглядит примерно так (для 16-ядерного тестового сервера):</span><span class="sxs-lookup"><span data-stu-id="8e62d-608">After a single test run that inserts 10 million sales orders, the overall on-disk size looks something like this (for a 16-core test server):</span></span>  
  
```  
SELECT SUM(df.size) * 8 / 1024 AS [On-disk size in MB]  
FROM sys.filegroups f JOIN sys.database_files df   
   ON f.data_space_id=df.data_space_id  
WHERE f.type=N'FX'  
```  
  
||  
|-|  
|<span data-ttu-id="8e62d-609">**Размер на диске в МБ**</span><span class="sxs-lookup"><span data-stu-id="8e62d-609">**On-disk size in MB**</span></span>|  
|<span data-ttu-id="8e62d-610">8828</span><span class="sxs-lookup"><span data-stu-id="8e62d-610">8828</span></span>|  
  
 <span data-ttu-id="8e62d-611">Дисковый размер приближается к 9 ГБ, что близко к размеру данных в памяти.</span><span class="sxs-lookup"><span data-stu-id="8e62d-611">The on-disk size is close to 9GB, which comes close to the in-memory size of the data.</span></span>  
  
 <span data-ttu-id="8e62d-612">Более тщательное исследование размера файлов контрольных точек в различных состояниях.</span><span class="sxs-lookup"><span data-stu-id="8e62d-612">Looking more closely at the sizes of the checkpoint files across the various states:</span></span>  
  
```  
SELECT state_desc  
 , file_type_desc  
 , COUNT(*) AS [count]  
 , SUM(CASE  
   WHEN state = 5 AND file_type=0 THEN 128*1024*1024  
   WHEN state = 5 AND file_type=1 THEN 8*1024*1024  
   WHEN state IN (6,7) THEN 68*1024*1024  
   ELSE file_size_in_bytes  
    END) / 1024 / 1024 AS [on-disk size MB]   
FROM sys.dm_db_xtp_checkpoint_files  
GROUP BY state, state_desc, file_type, file_type_desc  
ORDER BY state, file_type  
```  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="8e62d-613">**state_desc**</span><span class="sxs-lookup"><span data-stu-id="8e62d-613">**state_desc**</span></span>|<span data-ttu-id="8e62d-614">**file_type_desc**</span><span class="sxs-lookup"><span data-stu-id="8e62d-614">**file_type_desc**</span></span>|<span data-ttu-id="8e62d-615">**count**</span><span class="sxs-lookup"><span data-stu-id="8e62d-615">**count**</span></span>|<span data-ttu-id="8e62d-616">**Размер на диске в МБ**</span><span class="sxs-lookup"><span data-stu-id="8e62d-616">**on-disk size MB**</span></span>|  
|<span data-ttu-id="8e62d-617">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="8e62d-617">PRECREATED</span></span>|<span data-ttu-id="8e62d-618">DATA</span><span class="sxs-lookup"><span data-stu-id="8e62d-618">DATA</span></span>|<span data-ttu-id="8e62d-619">16</span><span class="sxs-lookup"><span data-stu-id="8e62d-619">16</span></span>|<span data-ttu-id="8e62d-620">2048</span><span class="sxs-lookup"><span data-stu-id="8e62d-620">2048</span></span>|  
|<span data-ttu-id="8e62d-621">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="8e62d-621">PRECREATED</span></span>|<span data-ttu-id="8e62d-622">DELTA</span><span class="sxs-lookup"><span data-stu-id="8e62d-622">DELTA</span></span>|<span data-ttu-id="8e62d-623">16</span><span class="sxs-lookup"><span data-stu-id="8e62d-623">16</span></span>|<span data-ttu-id="8e62d-624">128</span><span class="sxs-lookup"><span data-stu-id="8e62d-624">128</span></span>|  
|<span data-ttu-id="8e62d-625">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="8e62d-625">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="8e62d-626">DATA</span><span class="sxs-lookup"><span data-stu-id="8e62d-626">DATA</span></span>|<span data-ttu-id="8e62d-627">1</span><span class="sxs-lookup"><span data-stu-id="8e62d-627">1</span></span>|<span data-ttu-id="8e62d-628">128</span><span class="sxs-lookup"><span data-stu-id="8e62d-628">128</span></span>|  
|<span data-ttu-id="8e62d-629">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="8e62d-629">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="8e62d-630">DELTA</span><span class="sxs-lookup"><span data-stu-id="8e62d-630">DELTA</span></span>|<span data-ttu-id="8e62d-631">1</span><span class="sxs-lookup"><span data-stu-id="8e62d-631">1</span></span>|<span data-ttu-id="8e62d-632">8</span><span class="sxs-lookup"><span data-stu-id="8e62d-632">8</span></span>|  
  
 <span data-ttu-id="8e62d-633">У нас по-прежнему имеется 16 пар предварительно созданных файлов, готовых по мере закрытия контрольных точек.</span><span class="sxs-lookup"><span data-stu-id="8e62d-633">We still have 16 pairs of pre-created files, ready to go as checkpoints are closed.</span></span>  
  
 <span data-ttu-id="8e62d-634">Одна пара находится в разработке и используется до тех пор, пока не будет закрыта текущая контрольная точка.</span><span class="sxs-lookup"><span data-stu-id="8e62d-634">There is one pair under construction, which is used until the current checkpoint is closed.</span></span> <span data-ttu-id="8e62d-635">Вместе с активными файлами контрольных точек это дает примерно 6,5 ГБ занятого дискового пространства для 6,5 ГБ данных в памяти.</span><span class="sxs-lookup"><span data-stu-id="8e62d-635">Along with the active checkpoint files this gives about 6.5GB of disk utilization for 6.5GB of data in memory.</span></span> <span data-ttu-id="8e62d-636">Вспомним, что индексы не сохраняются на диск, поэтому в данном случае общий размер на диске меньше, чем размер в памяти.</span><span class="sxs-lookup"><span data-stu-id="8e62d-636">Recall that indexes are not persisted on disk, and thus the overall size on disk is smaller than the size in memory in this case.</span></span>  
  
#### <a name="after-demo-reset"></a><span data-ttu-id="8e62d-637">После сброса образца</span><span class="sxs-lookup"><span data-stu-id="8e62d-637">After demo reset</span></span>  
 <span data-ttu-id="8e62d-638">После сброса образца место на диске не возвращается немедленно, если в системе отсутствует рабочая нагрузка по обработке транзакций и нет контрольных точек базы данных.</span><span class="sxs-lookup"><span data-stu-id="8e62d-638">After demo reset, disk space is not reclaimed immediately if there is no transactional workload on the system, and there are not database checkpoints.</span></span> <span data-ttu-id="8e62d-639">Для прохождения файлами контрольных точек через различные этапы с последующим их удалением должно произойти несколько событий контрольных точек и усечения журнала, чтобы инициировать слияние файлов контрольных точек, а также сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="8e62d-639">For checkpoint files to be moved through their various stages and eventually be discarded, a number of checkpoints and log truncation events need to happen, to initiate merge of checkpoint files, as well as to initiate garbage collection.</span></span> <span data-ttu-id="8e62d-640">Это происходит автоматически при наличии в системе рабочей нагрузки по обработке транзакций [и создания обычных резервных копий журнала при использовании модели полного восстановления], но не тогда, когда система бездействует, как в нашем случае.</span><span class="sxs-lookup"><span data-stu-id="8e62d-640">These will happen automatically if you have a transactional workload in the system [and take regular log backups, in case you are using the FULL recovery model], but not when the system is idle, as in a demo scenario.</span></span>  
  
 <span data-ttu-id="8e62d-641">В этом примере после сброса образца можно наблюдать нечто похожее на</span><span class="sxs-lookup"><span data-stu-id="8e62d-641">In the example, after demo reset, you may see something like</span></span>  
  
```  
SELECT SUM(df.size) * 8 / 1024 AS [On-disk size in MB]  
FROM sys.filegroups f JOIN sys.database_files df   
   ON f.data_space_id=df.data_space_id  
WHERE f.type=N'FX'  
```  
  
||  
|-|  
|<span data-ttu-id="8e62d-642">**Размер на диске в МБ**</span><span class="sxs-lookup"><span data-stu-id="8e62d-642">**On-disk size in MB**</span></span>|  
|<span data-ttu-id="8e62d-643">11839</span><span class="sxs-lookup"><span data-stu-id="8e62d-643">11839</span></span>|  
  
 <span data-ttu-id="8e62d-644">Почти 12 ГБ, что значительно больше, чем 9 ГБ, которые мы имели до сброса образца.</span><span class="sxs-lookup"><span data-stu-id="8e62d-644">At nearly 12GB, this is significantly more than the 9GB we had before the demo reset.</span></span> <span data-ttu-id="8e62d-645">Связано это с тем, что были запущены слияния файлов контрольных точек, но некоторые цели слияния пока еще не установлены, а некоторые исходные файлы слияний пока еще не были очищены, что видно из нижеследующего.</span><span class="sxs-lookup"><span data-stu-id="8e62d-645">This is because some checkpoint file merges have been started, but some of the merge targets have not yet been installed, and some of the merge source files have not yet been cleaned up, as can be seen from the following:</span></span>  
  
```  
SELECT state_desc  
 , file_type_desc  
 , COUNT(*) AS [count]  
 , SUM(CASE  
   WHEN state = 5 AND file_type=0 THEN 128*1024*1024  
   WHEN state = 5 AND file_type=1 THEN 8*1024*1024  
   WHEN state IN (6,7) THEN 68*1024*1024  
   ELSE file_size_in_bytes  
    END) / 1024 / 1024 AS [on-disk size MB]   
FROM sys.dm_db_xtp_checkpoint_files  
GROUP BY state, state_desc, file_type, file_type_desc  
ORDER BY state, file_type  
```  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="8e62d-646">**state_desc**</span><span class="sxs-lookup"><span data-stu-id="8e62d-646">**state_desc**</span></span>|<span data-ttu-id="8e62d-647">**file_type_desc**</span><span class="sxs-lookup"><span data-stu-id="8e62d-647">**file_type_desc**</span></span>|<span data-ttu-id="8e62d-648">**count**</span><span class="sxs-lookup"><span data-stu-id="8e62d-648">**count**</span></span>|<span data-ttu-id="8e62d-649">**Размер на диске в МБ**</span><span class="sxs-lookup"><span data-stu-id="8e62d-649">**on-disk size MB**</span></span>|  
|<span data-ttu-id="8e62d-650">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="8e62d-650">PRECREATED</span></span>|<span data-ttu-id="8e62d-651">DATA</span><span class="sxs-lookup"><span data-stu-id="8e62d-651">DATA</span></span>|<span data-ttu-id="8e62d-652">16</span><span class="sxs-lookup"><span data-stu-id="8e62d-652">16</span></span>|<span data-ttu-id="8e62d-653">2048</span><span class="sxs-lookup"><span data-stu-id="8e62d-653">2048</span></span>|  
|<span data-ttu-id="8e62d-654">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="8e62d-654">PRECREATED</span></span>|<span data-ttu-id="8e62d-655">DELTA</span><span class="sxs-lookup"><span data-stu-id="8e62d-655">DELTA</span></span>|<span data-ttu-id="8e62d-656">16</span><span class="sxs-lookup"><span data-stu-id="8e62d-656">16</span></span>|<span data-ttu-id="8e62d-657">128</span><span class="sxs-lookup"><span data-stu-id="8e62d-657">128</span></span>|  
|<span data-ttu-id="8e62d-658">ACTIVE</span><span class="sxs-lookup"><span data-stu-id="8e62d-658">ACTIVE</span></span>|<span data-ttu-id="8e62d-659">DATA</span><span class="sxs-lookup"><span data-stu-id="8e62d-659">DATA</span></span>|<span data-ttu-id="8e62d-660">38</span><span class="sxs-lookup"><span data-stu-id="8e62d-660">38</span></span>|<span data-ttu-id="8e62d-661">5152</span><span class="sxs-lookup"><span data-stu-id="8e62d-661">5152</span></span>|  
|<span data-ttu-id="8e62d-662">ACTIVE</span><span class="sxs-lookup"><span data-stu-id="8e62d-662">ACTIVE</span></span>|<span data-ttu-id="8e62d-663">DELTA</span><span class="sxs-lookup"><span data-stu-id="8e62d-663">DELTA</span></span>|<span data-ttu-id="8e62d-664">38</span><span class="sxs-lookup"><span data-stu-id="8e62d-664">38</span></span>|<span data-ttu-id="8e62d-665">1331</span><span class="sxs-lookup"><span data-stu-id="8e62d-665">1331</span></span>|  
|<span data-ttu-id="8e62d-666">MERGE TARGET</span><span class="sxs-lookup"><span data-stu-id="8e62d-666">MERGE TARGET</span></span>|<span data-ttu-id="8e62d-667">DATA</span><span class="sxs-lookup"><span data-stu-id="8e62d-667">DATA</span></span>|<span data-ttu-id="8e62d-668">7</span><span class="sxs-lookup"><span data-stu-id="8e62d-668">7</span></span>|<span data-ttu-id="8e62d-669">896</span><span class="sxs-lookup"><span data-stu-id="8e62d-669">896</span></span>|  
|<span data-ttu-id="8e62d-670">MERGE TARGET</span><span class="sxs-lookup"><span data-stu-id="8e62d-670">MERGE TARGET</span></span>|<span data-ttu-id="8e62d-671">DELTA</span><span class="sxs-lookup"><span data-stu-id="8e62d-671">DELTA</span></span>|<span data-ttu-id="8e62d-672">7</span><span class="sxs-lookup"><span data-stu-id="8e62d-672">7</span></span>|<span data-ttu-id="8e62d-673">56</span><span class="sxs-lookup"><span data-stu-id="8e62d-673">56</span></span>|  
|<span data-ttu-id="8e62d-674">MERGED SOURCE</span><span class="sxs-lookup"><span data-stu-id="8e62d-674">MERGED SOURCE</span></span>|<span data-ttu-id="8e62d-675">DATA</span><span class="sxs-lookup"><span data-stu-id="8e62d-675">DATA</span></span>|<span data-ttu-id="8e62d-676">13</span><span class="sxs-lookup"><span data-stu-id="8e62d-676">13</span></span>|<span data-ttu-id="8e62d-677">1772</span><span class="sxs-lookup"><span data-stu-id="8e62d-677">1772</span></span>|  
|<span data-ttu-id="8e62d-678">MERGED SOURCE</span><span class="sxs-lookup"><span data-stu-id="8e62d-678">MERGED SOURCE</span></span>|<span data-ttu-id="8e62d-679">DELTA</span><span class="sxs-lookup"><span data-stu-id="8e62d-679">DELTA</span></span>|<span data-ttu-id="8e62d-680">13</span><span class="sxs-lookup"><span data-stu-id="8e62d-680">13</span></span>|<span data-ttu-id="8e62d-681">455</span><span class="sxs-lookup"><span data-stu-id="8e62d-681">455</span></span>|  
  
 <span data-ttu-id="8e62d-682">Цели слияния устанавливаются, а исходные файлы слияния удаляются по мере выполнения транзакций в системе.</span><span class="sxs-lookup"><span data-stu-id="8e62d-682">Merge targets are installed and merged source are cleaned up as transactional activity happens in the system.</span></span>  
  
 <span data-ttu-id="8e62d-683">После второго выполнения демонстрационной рабочей нагрузки с вставкой 10 миллионов заказов на продажу после сброса образца вы увидите, что файлы, сформированные во время первого выполнения рабочей нагрузки, были очищены.</span><span class="sxs-lookup"><span data-stu-id="8e62d-683">After a second run of the demo workload, inserting 10 million sales orders after the demo reset, you will see that the files constructed during the first run of the workload have been cleaned up.</span></span> <span data-ttu-id="8e62d-684">Приведенный выше запрос можно выполнить несколько раз во время выполнения рабочей нагрузки. Это позволит увидеть, как файлы контрольных точек проходят по различным этапам.</span><span class="sxs-lookup"><span data-stu-id="8e62d-684">If you run the above query several times while the workload is running, you can see the checkpoint files make their way through the various stages.</span></span>  
  
 <span data-ttu-id="8e62d-685">После второго выполнения рабочей нагрузки по вставке 10 миллионов заказов на продажу вы увидите, что объем использования дискового пространства будет почти такой же, хотя он и может немного отличаться, как после первого выполнения, поскольку система является по своей природе динамичной.</span><span class="sxs-lookup"><span data-stu-id="8e62d-685">After the second run of the workload insert 10 million sales orders you will see disk utilization very similar to, though not necessarily the same as after the first run, as the system is dynamic in nature.</span></span> <span data-ttu-id="8e62d-686">Пример:</span><span class="sxs-lookup"><span data-stu-id="8e62d-686">For example:</span></span>  
  
```  
SELECT state_desc  
 , file_type_desc  
 , COUNT(*) AS [count]  
 , SUM(CASE  
   WHEN state = 5 AND file_type=0 THEN 128*1024*1024  
   WHEN state = 5 AND file_type=1 THEN 8*1024*1024  
   WHEN state IN (6,7) THEN 68*1024*1024  
   ELSE file_size_in_bytes  
    END) / 1024 / 1024 AS [on-disk size MB]   
FROM sys.dm_db_xtp_checkpoint_files  
GROUP BY state, state_desc, file_type, file_type_desc  
ORDER BY state, file_type  
```  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="8e62d-687">**state_desc**</span><span class="sxs-lookup"><span data-stu-id="8e62d-687">**state_desc**</span></span>|<span data-ttu-id="8e62d-688">**file_type_desc**</span><span class="sxs-lookup"><span data-stu-id="8e62d-688">**file_type_desc**</span></span>|<span data-ttu-id="8e62d-689">**count**</span><span class="sxs-lookup"><span data-stu-id="8e62d-689">**count**</span></span>|<span data-ttu-id="8e62d-690">**Размер на диске в МБ**</span><span class="sxs-lookup"><span data-stu-id="8e62d-690">**on-disk size MB**</span></span>|  
|<span data-ttu-id="8e62d-691">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="8e62d-691">PRECREATED</span></span>|<span data-ttu-id="8e62d-692">DATA</span><span class="sxs-lookup"><span data-stu-id="8e62d-692">DATA</span></span>|<span data-ttu-id="8e62d-693">16</span><span class="sxs-lookup"><span data-stu-id="8e62d-693">16</span></span>|<span data-ttu-id="8e62d-694">2048</span><span class="sxs-lookup"><span data-stu-id="8e62d-694">2048</span></span>|  
|<span data-ttu-id="8e62d-695">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="8e62d-695">PRECREATED</span></span>|<span data-ttu-id="8e62d-696">DELTA</span><span class="sxs-lookup"><span data-stu-id="8e62d-696">DELTA</span></span>|<span data-ttu-id="8e62d-697">16</span><span class="sxs-lookup"><span data-stu-id="8e62d-697">16</span></span>|<span data-ttu-id="8e62d-698">128</span><span class="sxs-lookup"><span data-stu-id="8e62d-698">128</span></span>|  
|<span data-ttu-id="8e62d-699">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="8e62d-699">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="8e62d-700">DATA</span><span class="sxs-lookup"><span data-stu-id="8e62d-700">DATA</span></span>|<span data-ttu-id="8e62d-701">2</span><span class="sxs-lookup"><span data-stu-id="8e62d-701">2</span></span>|<span data-ttu-id="8e62d-702">268</span><span class="sxs-lookup"><span data-stu-id="8e62d-702">268</span></span>|  
|<span data-ttu-id="8e62d-703">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="8e62d-703">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="8e62d-704">DELTA</span><span class="sxs-lookup"><span data-stu-id="8e62d-704">DELTA</span></span>|<span data-ttu-id="8e62d-705">2</span><span class="sxs-lookup"><span data-stu-id="8e62d-705">2</span></span>|<span data-ttu-id="8e62d-706">16</span><span class="sxs-lookup"><span data-stu-id="8e62d-706">16</span></span>|  
|<span data-ttu-id="8e62d-707">ACTIVE</span><span class="sxs-lookup"><span data-stu-id="8e62d-707">ACTIVE</span></span>|<span data-ttu-id="8e62d-708">DATA</span><span class="sxs-lookup"><span data-stu-id="8e62d-708">DATA</span></span>|<span data-ttu-id="8e62d-709">41</span><span class="sxs-lookup"><span data-stu-id="8e62d-709">41</span></span>|<span data-ttu-id="8e62d-710">5608</span><span class="sxs-lookup"><span data-stu-id="8e62d-710">5608</span></span>|  
|<span data-ttu-id="8e62d-711">ACTIVE</span><span class="sxs-lookup"><span data-stu-id="8e62d-711">ACTIVE</span></span>|<span data-ttu-id="8e62d-712">DELTA</span><span class="sxs-lookup"><span data-stu-id="8e62d-712">DELTA</span></span>|<span data-ttu-id="8e62d-713">41</span><span class="sxs-lookup"><span data-stu-id="8e62d-713">41</span></span>|<span data-ttu-id="8e62d-714">328</span><span class="sxs-lookup"><span data-stu-id="8e62d-714">328</span></span>|  
  
 <span data-ttu-id="8e62d-715">В этом случае будет две пары файлов контрольных точек в состоянии "в разработке", а это означает, что несколько пар файлов были перемещены в состояние "в разработке", вероятнее всего, из-за высокого уровня параллелизма в рабочей нагрузке.</span><span class="sxs-lookup"><span data-stu-id="8e62d-715">In this case, there are two checkpoint file pairs in the 'under construction' state, which means multiple file pairs were moved to the 'under construction' state, likely due to the high level of concurrency in the workload.</span></span> <span data-ttu-id="8e62d-716">Нескольким параллельным потокам одновременно потребовалась новая пара файлов, из-за чего пара была переведена из состояния "создана заранее" в состояние "в разработке".</span><span class="sxs-lookup"><span data-stu-id="8e62d-716">Multiple concurrent threads required a new file pair at the same time, and thus moved a pair from 'precreated' to 'under construction'.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e62d-717">См. также:</span><span class="sxs-lookup"><span data-stu-id="8e62d-717">See Also</span></span>  
 [<span data-ttu-id="8e62d-718">Выполняющаяся в памяти OLTP (оптимизация в памяти)</span><span class="sxs-lookup"><span data-stu-id="8e62d-718">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
