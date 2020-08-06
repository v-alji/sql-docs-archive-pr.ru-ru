---
title: Уменьшение загрузки при настройке рабочего сервера | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- overhead [Database Engine Tuning Advisor]
- tuning overhead [SQL Server]
- reducing production server tuning load
- Database Engine Tuning Advisor [SQL Server], test servers
- test servers [Database Engine Tuning Advisor]
- production servers [SQL Server]
- offload tuning overhead [SQL Server]
ms.assetid: bb95ecaf-444a-4771-a625-e0a91c8f0709
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 53a61b17793a50d6b819f7c1684afdc4de4377f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666000"
---
# <a name="reduce-the-production-server-tuning-load"></a><span data-ttu-id="97671-102">Уменьшение настроечной загрузки рабочего сервера</span><span class="sxs-lookup"><span data-stu-id="97671-102">Reduce the Production Server Tuning Load</span></span>
  [!INCLUDE[ssDE](../../../includes/ssde-md.md)] <span data-ttu-id="97671-103">полагается на оптимизатор запросов, который анализирует рабочую нагрузку и создает рекомендации по настройке.</span><span class="sxs-lookup"><span data-stu-id="97671-103">Tuning Advisor relies on the query optimizer to analyze a workload and to make tuning recommendations.</span></span> <span data-ttu-id="97671-104">Выполнение этого анализа на рабочем сервере добавляет нагрузки этому серверу и может снизить его производительность на время сеанса настройки.</span><span class="sxs-lookup"><span data-stu-id="97671-104">Performing this analysis on the production server adds to the server load and can hurt server performance during the tuning session.</span></span> <span data-ttu-id="97671-105">Чтобы уменьшить дополнительную нагрузку сервера во время сеанса настройки, можно использовать тестовый сервер в дополнение к рабочему серверу.</span><span class="sxs-lookup"><span data-stu-id="97671-105">You can reduce the impact to the server load during a tuning session by using a test server in addition to the production server.</span></span>

## <a name="how-database-engine-tuning-advisor-uses-a-test-server"></a><span data-ttu-id="97671-106">Как помощник по настройке ядра СУБД работает с тестовым сервером</span><span class="sxs-lookup"><span data-stu-id="97671-106">How Database Engine Tuning Advisor Uses a Test Server</span></span>
 <span data-ttu-id="97671-107">Традиционным методом является копирование всех данных с рабочего сервера на тестовый, затем производится настройка тестового сервера и реализация рекомендаций на производственном сервере.</span><span class="sxs-lookup"><span data-stu-id="97671-107">The traditional way to use a test server is to copy all of the data from your production server to your test server, tune the test server, and then implement the recommendation on your production server.</span></span> <span data-ttu-id="97671-108">Этот процесс устраняет влияние на производительность рабочего сервера, но не является оптимальным решением.</span><span class="sxs-lookup"><span data-stu-id="97671-108">This process eliminates the performance impact on your production server, but nevertheless is not the optimal solution.</span></span> <span data-ttu-id="97671-109">Например, копирование большого количества данных с рабочего сервера на тестовый может занять много времени и ресурсов.</span><span class="sxs-lookup"><span data-stu-id="97671-109">For example, copying large amounts of data from the production to the test server can consume substantial amounts of time and resources.</span></span> <span data-ttu-id="97671-110">Кроме того, оборудование тестового сервера редко также производительно, как и использующееся на рабочих серверах.</span><span class="sxs-lookup"><span data-stu-id="97671-110">In addition, test server hardware is seldom as powerful as the hardware that is deployed for production servers.</span></span> <span data-ttu-id="97671-111">Процесс настройки полагается на оптимизатор запросов, а формируемые им рекомендации частично основываются на параметрах оборудования.</span><span class="sxs-lookup"><span data-stu-id="97671-111">The tuning process relies on the query optimizer, and the recommendations it generates are based in part on the underlying hardware.</span></span> <span data-ttu-id="97671-112">Если оборудование рабочего и тестового серверов неодинаково, качество рекомендаций помощника по настройке компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)] может снизиться.</span><span class="sxs-lookup"><span data-stu-id="97671-112">If the test and production server hardware are not identical, the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Tuning Advisor recommendation quality is diminished.</span></span>

 <span data-ttu-id="97671-113">Чтобы избежать этих проблем, помощник по настройке компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)] настраивает базу данных на рабочем сервере, перенося большую часть нагрузки, связанной с настройкой, на тестовый сервер.</span><span class="sxs-lookup"><span data-stu-id="97671-113">To avoid these problems, [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Tuning Advisor tunes a database on a production server by offloading most of the tuning load onto a test server.</span></span> <span data-ttu-id="97671-114">Это делается с использованием сведений о конфигурации оборудования рабочего сервера и без явного копирования данных с рабочего сервера на тестовый.</span><span class="sxs-lookup"><span data-stu-id="97671-114">It does this by using the production server hardware configuration information and without actually copying the data from the production server to the test server.</span></span> [!INCLUDE[ssDE](../../../includes/ssde-md.md)] <span data-ttu-id="97671-115">не копирует реальные данные с рабочего сервера на тестовый сервер.</span><span class="sxs-lookup"><span data-stu-id="97671-115">Tuning Advisor does not copy actual data from the production server to the test server.</span></span> <span data-ttu-id="97671-116">Он копирует только метаданные и необходимую статистику.</span><span class="sxs-lookup"><span data-stu-id="97671-116">It only copies the metadata and necessary statistics.</span></span>

 <span data-ttu-id="97671-117">Следующие шаги в общем виде описывают процесс настройки производственной базы данных на тестовом сервере.</span><span class="sxs-lookup"><span data-stu-id="97671-117">The following steps outline the process for tuning a production database on a test server:</span></span>

1.  <span data-ttu-id="97671-118">Убедитесь, что пользователь, который хочет работать с тестовым сервером, есть на обоих серверах.</span><span class="sxs-lookup"><span data-stu-id="97671-118">Make sure that the user who wants to use the test server exists on both servers.</span></span>

     <span data-ttu-id="97671-119">ПЕРЕД НАЧАЛОМ УБЕДИТЕСЬ, ЧТО ПОЛЬЗОВАТЕЛЬ, КОТОРЫЙ ХОЧЕТ РАБОТАТЬ С ТЕСТОВЫМ СЕРВЕРОМ ДЛЯ НАСТРОЙКИ БАЗЫ ДАННЫХ РАБОЧЕГО СЕРВЕРА, СУЩЕСТВУЕТ НА ОБОИХ СЕРВЕРАХ.Перед началом убедитесь, что пользователь, который хочет работать с тестовым сервером для настройки базы данных рабочего сервера, существует на обоих серверах.</span><span class="sxs-lookup"><span data-stu-id="97671-119">Before you start, make sure that the user who wants to use the test server to tune a database on the production server exists on both servers.</span></span> <span data-ttu-id="97671-120">Для этого нужно создать пользователя и его имя входа на тестовом сервере.</span><span class="sxs-lookup"><span data-stu-id="97671-120">This requires that you create the user and his or her login on the test server.</span></span> <span data-ttu-id="97671-121">Если вы являетесь членом предопределенной роли сервера **sysadmin** на обоих компьютерах, этот шаг можно пропустить.</span><span class="sxs-lookup"><span data-stu-id="97671-121">If you are a member of the **sysadmin** fixed server role on both computers, this step is not necessary.</span></span>

2.  <span data-ttu-id="97671-122">Настройте рабочую нагрузку на тестовом сервере.</span><span class="sxs-lookup"><span data-stu-id="97671-122">Tune the workload on the test server.</span></span>

     <span data-ttu-id="97671-123">Чтобы настроить рабочую нагрузку на тестовом сервере, используйте входной файл XML-данных и программу командной строки **dta** .</span><span class="sxs-lookup"><span data-stu-id="97671-123">To tune a workload on a test server, you must use an XML input file with the **dta** command-line utility.</span></span> <span data-ttu-id="97671-124">В этом XML-файле укажите имя тестового сервера во вложенном элементе **TestServer** вместе с другими значениями других вложенных элементов родительского элемента **TuningOptions** .</span><span class="sxs-lookup"><span data-stu-id="97671-124">In the XML input file, specify the name of your test server with the **TestServer** subelement in addition to specifying the values for the other subelements under the **TuningOptions** parent element.</span></span>

     <span data-ttu-id="97671-125">Во время процесса настройки помощник по настройке ядра СУБД создает на тестовом сервере базу данных оболочки.</span><span class="sxs-lookup"><span data-stu-id="97671-125">During the tuning process, Database Engine Tuning Advisor creates a shell database on the test server.</span></span> <span data-ttu-id="97671-126">Чтобы создать и настроить базу данных, помощник по настройке ядра СУБД отправляет рабочему серверу представленные ниже вызовы.</span><span class="sxs-lookup"><span data-stu-id="97671-126">To create this shell database and tune it, Database Engine Tuning Advisor makes calls to the production server for the following:</span></span>

    1.  [!INCLUDE[ssDE](../../../includes/ssde-md.md)] <span data-ttu-id="97671-127">импортирует метаданные производственной базы данных в базу данных оболочки тестового сервера.</span><span class="sxs-lookup"><span data-stu-id="97671-127">Tuning Advisor imports metadata from the production database to the test server shell database.</span></span> <span data-ttu-id="97671-128">В эти метаданные входят пустые таблицы, индексы, представления, хранимые процедуры, триггеры и т. д.</span><span class="sxs-lookup"><span data-stu-id="97671-128">This metadata includes empty tables, indexes, views, stored procedures, triggers, and so on.</span></span> <span data-ttu-id="97671-129">Таким образом, возможно выполнять запросы рабочей нагрузки к базе данных оболочки тестового сервера.</span><span class="sxs-lookup"><span data-stu-id="97671-129">This makes it possible for the workload queries to execute against the test server shell database.</span></span>

    2.  [!INCLUDE[ssDE](../../../includes/ssde-md.md)] <span data-ttu-id="97671-130">импортирует статистику рабочего сервера, чтобы оптимизатор запросов мог точно оптимизировать запросы на тестовом сервере.</span><span class="sxs-lookup"><span data-stu-id="97671-130">Tuning Advisor imports statistics from the production server so the query optimizer can accurately optimize queries on the test server.</span></span>

    3.  [!INCLUDE[ssDE](../../../includes/ssde-md.md)] <span data-ttu-id="97671-131">импортирует параметры оборудования, указывая число процессоров и доступную оперативную память рабочего сервера, чтобы предоставить оптимизатору запросов сведения, необходимые для формирования планов запросов.</span><span class="sxs-lookup"><span data-stu-id="97671-131">Tuning Advisor imports hardware parameters specifying the number of processors and available memory from the production server to provide the query optimizer with the information it needs to generate a query plan.</span></span>

3.  <span data-ttu-id="97671-132">После завершения настройки базы данных оболочки тестового сервера помощник по настройке компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)] сформирует рекомендации по настройке.</span><span class="sxs-lookup"><span data-stu-id="97671-132">After [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Tuning Advisor finishes tuning the test server shell database, it generates a tuning recommendation.</span></span>

4.  <span data-ttu-id="97671-133">Примените рекомендацию, полученную при настройке тестового сервера, на рабочем сервере.</span><span class="sxs-lookup"><span data-stu-id="97671-133">Apply the recommendation received from tuning the test server to the production server.</span></span>

 <span data-ttu-id="97671-134">На следующем рисунке показан сценарий с использованием тестового и рабочего серверов.</span><span class="sxs-lookup"><span data-stu-id="97671-134">The following illustration shows the test server and production server scenario:</span></span>

 <span data-ttu-id="97671-135">![Использование тестового сервера с помощником по настройке ядра СУБД](../../database-engine/media/testsvr.gif "Использование тестового сервера с помощником по настройке ядра СУБД")</span><span class="sxs-lookup"><span data-stu-id="97671-135">![Database Engine Tuning Advisor test server usage](../../database-engine/media/testsvr.gif "Database Engine Tuning Advisor test server usage")</span></span>

> [!NOTE]
>  <span data-ttu-id="97671-136">Функция настройки тестового сервера не поддерживается в графическом пользовательском интерфейсе помощника по настройке компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="97671-136">The test server tuning feature is not supported in the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Tuning Advisor graphical user interface (GUI).</span></span>

## <a name="example"></a><span data-ttu-id="97671-137">Пример</span><span class="sxs-lookup"><span data-stu-id="97671-137">Example</span></span>
 <span data-ttu-id="97671-138">Сначала убедитесь, что пользователь, который хочет работать с рабочим сервером, есть на обоих серверах.</span><span class="sxs-lookup"><span data-stu-id="97671-138">First, make sure that the user who wants to perform the tuning exists on both the test and production servers.</span></span>

 <span data-ttu-id="97671-139">После копирования сведений о пользователе на тестовый сервер можно определить сеанс его настройки во входном XML-файле помощника по настройке компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="97671-139">After the user information is copied over to your test server, you can define your test server tuning session in the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Tuning Advisor XML input file.</span></span> <span data-ttu-id="97671-140">Следующий входной XML-файл демонстрирует, как указать тестовый сервер для настройки базы данных помощником по настройке компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="97671-140">The following example XML input file illustrates how to specify a test server to tune a database with [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Tuning Advisor.</span></span>

 <span data-ttu-id="97671-141">В этом примере база данных `MyDatabaseName` настраивается на сервере `MyServerName`.</span><span class="sxs-lookup"><span data-stu-id="97671-141">In this example, the `MyDatabaseName` database is being tuned on `MyServerName`.</span></span> <span data-ttu-id="97671-142">Скрипт [!INCLUDE[tsql](../../includes/tsql-md.md)] , `MyWorkloadScript.sql`, используется в качестве рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="97671-142">The [!INCLUDE[tsql](../../includes/tsql-md.md)] script, `MyWorkloadScript.sql`, is used as the workload.</span></span> <span data-ttu-id="97671-143">Он содержит события, которые будут происходить в базе данных `MyDatabaseName`.</span><span class="sxs-lookup"><span data-stu-id="97671-143">This workload contains events that execute against `MyDatabaseName`.</span></span> <span data-ttu-id="97671-144">Большая часть вызовов оптимизатора запросов этой базы данных, которые будут производиться во время настройки, обрабатываются базой данных оболочки на сервере `MyTestServerName`.</span><span class="sxs-lookup"><span data-stu-id="97671-144">Most of the query optimizer calls to this database, which occur as part of the tuning process, are handled by the shell database that resides on `MyTestServerName`.</span></span> <span data-ttu-id="97671-145">База данных оболочки состоит из метаданных и статистики.</span><span class="sxs-lookup"><span data-stu-id="97671-145">The shell database is composed of metadata and statistics.</span></span> <span data-ttu-id="97671-146">В результате этого настроечная нагрузка переносится на тестовый сервер.</span><span class="sxs-lookup"><span data-stu-id="97671-146">This process results in the tuning overhead being offloaded to the test server.</span></span> <span data-ttu-id="97671-147">Когда помощник по настройке компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)] формирует рекомендацию по настройке с помощью этого входного XML-файла, он принимает в расчет только индексы (`<FeatureSet>IDX</FeatureSet>`), но не секционирование, и поэтому может не хранить существующие структуры физического проектирования базы данных в объекте `MyDatabaseName`.</span><span class="sxs-lookup"><span data-stu-id="97671-147">When [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Tuning Advisor generates its tuning recommendation using this XML input file, it should consider indexes only (`<FeatureSet>IDX</FeatureSet>`), no partitioning, and need not keep any of the existing physical design structures in `MyDatabaseName`.</span></span>

```
<?xml version="1.0" encoding="utf-16" ?>
<DTAXML xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="https://schemas.microsoft.com/sqlserver/2004/07/dta">
  <DTAInput>
    <Server>
      <Name>MyServerName</Name>
      <Database>
        <Name>MyDatabaseName</Name>
      </Database>
    </Server>
    <Workload>
      <File>MyWorkloadScript.sql</File>
    </Workload>
    <TuningOptions>
      <TestServer>MyTestServerName</TestServer>
      <FeatureSet>IDX</FeatureSet>
      <Partitioning>NONE</Partitioning>
      <KeepExisting>NONE</KeepExisting>
    </TuningOptions>
  </DTAInput>
</DTAXML>
```

## <a name="see-also"></a><span data-ttu-id="97671-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="97671-148">See Also</span></span>
 <span data-ttu-id="97671-149">[Рекомендации по использованию](considerations-for-using-test-servers.md) [справочника по входным XML-файлам на тестовых серверах &#40;помощник по настройке ядра СУБД&#41;](database-engine-tuning-advisor.md)</span><span class="sxs-lookup"><span data-stu-id="97671-149">[Considerations for Using Test Servers](considerations-for-using-test-servers.md) [XML Input File Reference &#40;Database Engine Tuning Advisor&#41;](database-engine-tuning-advisor.md)</span></span>


