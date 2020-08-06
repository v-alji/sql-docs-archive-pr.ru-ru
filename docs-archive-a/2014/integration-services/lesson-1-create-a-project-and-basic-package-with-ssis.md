---
title: Занятие 1. Создание проекта и основного пакета | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 84d0b877-603f-4f8e-bb6b-671558ade5c2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1a9ddc36ef242cc4e4b146e90dfa9de470e68d83
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664340"
---
# <a name="lesson-1-creating-the-project-and-basic-package"></a><span data-ttu-id="e8905-102">Урок 1. Создание проекта и основного пакета</span><span class="sxs-lookup"><span data-stu-id="e8905-102">Lesson 1: Creating the Project and Basic Package</span></span>
  <span data-ttu-id="e8905-103">На этом занятии будет рассмотрено создание простого ETL-пакета, который будет извлекать данные из отдельного источника неструктурированных файлов, преобразовывать полученные данные при помощи двух компонентов преобразования «Уточняющий запрос», а затем записывать эти данные в таблицу фактов **FactCurrency** , находящуюся в базе данных **AdventureWorksDW2012**.</span><span class="sxs-lookup"><span data-stu-id="e8905-103">In this lesson, you will create a simple ETL package that extracts data from a single flat file source, transforms the data using two lookup transformation components, and writes that data to the **FactCurrency** fact table in **AdventureWorksDW2012**.</span></span> <span data-ttu-id="e8905-104">На этом занятии предстоит узнать, как создавать новые пакеты, добавлять и настраивать соединения с источниками данных и назначениями, а также работать с новыми компонентами потока управления и потока данных.</span><span class="sxs-lookup"><span data-stu-id="e8905-104">As part of this lesson, you will learn how to create new packages, add and configure data source and destination connections, and work with new control flow and data flow components.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e8905-105">Для выполнения упражнений этого учебника потребуется образец базы данных **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="e8905-105">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="e8905-106">Дополнительные сведения об установке и развертывании **AdventureWorksDW2012**см. в разделе [Microsoft SQL Server Product samples: Reporting Services](https://archive.codeplex.com/?p=msftrsprodsamples).</span><span class="sxs-lookup"><span data-stu-id="e8905-106">For more information on installing and deploying **AdventureWorksDW2012**, see [Microsoft SQL Server Product Samples: Reporting Services](https://archive.codeplex.com/?p=msftrsprodsamples).</span></span>  
  
## <a name="understanding-the-package-requirements"></a><span data-ttu-id="e8905-107">Основные сведения о требованиях пакета</span><span class="sxs-lookup"><span data-stu-id="e8905-107">Understanding the Package Requirements</span></span>  
 <span data-ttu-id="e8905-108">Для выполнения упражнений этого учебника требуется Microsoft SQL Server Data Tools.</span><span class="sxs-lookup"><span data-stu-id="e8905-108">This tutorial requires Microsoft SQL Server Data Tools.</span></span>  
  
 <span data-ttu-id="e8905-109">Дополнительные сведения об установке SQL Server Data Tools см. в разделе [Загрузка SQL Server Data Tools](https://docs.microsoft.com/sql/ssdt/download-sql-server-data-tools-ssdt?view=sql-server-2017).</span><span class="sxs-lookup"><span data-stu-id="e8905-109">For more information on installing the SQL Server Data Tools see [SQL Server Data Tools Download](https://docs.microsoft.com/sql/ssdt/download-sql-server-data-tools-ssdt?view=sql-server-2017).</span></span>  
  
 <span data-ttu-id="e8905-110">Перед созданием пакета необходимо знать о форматировании в источнике данных и в назначении.</span><span class="sxs-lookup"><span data-stu-id="e8905-110">Before creating a package, you need a good understanding of the formatting used in both the source data and the destination.</span></span> <span data-ttu-id="e8905-111">Если эти форматы данных известны, можно определить преобразования, необходимые для сопоставления формата данных источника формату назначения.</span><span class="sxs-lookup"><span data-stu-id="e8905-111">Once you understand both of these data formats, you will be ready to define the transformations necessary to map the source data to the destination.</span></span>  
  
### <a name="looking-at-the-source"></a><span data-ttu-id="e8905-112">Анализ источника</span><span class="sxs-lookup"><span data-stu-id="e8905-112">Looking at the Source</span></span>  
 <span data-ttu-id="e8905-113">Для этого учебника данные источника представлены в виде набора курсов валют, содержащегося в неструктурированном файле SampleCurrencyData.txt.</span><span class="sxs-lookup"><span data-stu-id="e8905-113">For this tutorial, the source data is a set of historical currency data contained in the flat file, SampleCurrencyData.txt.</span></span> <span data-ttu-id="e8905-114">Данные источника в этом файле имеют четыре столбца: средний курс валюты, ключ валюты, ключ даты и курс на конец дня.</span><span class="sxs-lookup"><span data-stu-id="e8905-114">The source data has the following four columns: the average rate of the currency, a currency key, a date key, and the end-of-day rate.</span></span>  
  
 <span data-ttu-id="e8905-115">Здесь приведен пример данных источника, содержащихся в файле SampleCurrencyData.txt:</span><span class="sxs-lookup"><span data-stu-id="e8905-115">Here is an example of the source data contained in the SampleCurrencyData.txt file:</span></span>  
  
 `1.00070049USD9/3/05 0:001.001201442`  
  
 `1.00020004USD9/4/05 0:001`  
  
 `1.00020004USD9/5/05 0:001.001201442`  
  
 `1.00020004USD9/6/05 0:001`  
  
 `1.00020004USD9/7/05 0:001.00070049`  
  
 `1.00070049USD9/8/05 0:000.99980004`  
  
 `1.00070049USD9/9/05 0:001.001502253`  
  
 `1.00070049USD9/10/05 0:000.99990001`  
  
 `1.00020004USD9/11/05 0:001.001101211`  
  
 `1.00020004USD9/12/05 0:000.99970009`  
  
 <span data-ttu-id="e8905-116">При работе с данными источника неструктурированных файлов важно понимать, как диспетчер соединений с неструктурированными файлами интерпретирует данные неструктурированных файлов.</span><span class="sxs-lookup"><span data-stu-id="e8905-116">When working with flat file source data, it is important to understand how the Flat File connection manager interprets the flat file data.</span></span> <span data-ttu-id="e8905-117">Если неструктурированный файл является документом в Юникоде, диспетчер соединений с неструктурированными файлами определяет все столбцы как [DT_WSTR] с шириной, по умолчанию равной 50.</span><span class="sxs-lookup"><span data-stu-id="e8905-117">If the flat file source is Unicode, the Flat File connection manager defines all columns as [DT_WSTR] with a default column width of 50.</span></span> <span data-ttu-id="e8905-118">Если неструктурированный файл является документом в кодировке ANSI, все столбцы определяются как [DT_STR] с шириной, равной 50.</span><span class="sxs-lookup"><span data-stu-id="e8905-118">If the flat file source is ANSI-encoded, the columns are defined as [DT_STR] with a column width of 50.</span></span> <span data-ttu-id="e8905-119">Возможно, потребуется изменить эти настройки, чтобы оптимизировать столбцы для конкретных данных.</span><span class="sxs-lookup"><span data-stu-id="e8905-119">You will probably have to change these defaults to make the string column types more appropriate for your data.</span></span> <span data-ttu-id="e8905-120">Чтобы сделать это, необходимо узнать тип данных в назначении, куда будут заноситься эти данные, а затем выбрать правильный тип данных в диспетчере соединений с неструктурированными файлами.</span><span class="sxs-lookup"><span data-stu-id="e8905-120">To do this, you will need to look at the data type of the destination where the data will be written to and then choose the correct type within the Flat File connection manager.</span></span>  
  
### <a name="looking-at-the-destination"></a><span data-ttu-id="e8905-121">Анализ назначения</span><span class="sxs-lookup"><span data-stu-id="e8905-121">Looking at the Destination</span></span>  
 <span data-ttu-id="e8905-122">Конечным назначением источника данных является таблица фактов **FactCurrency** в базе данных **AdventureWorksDW**.</span><span class="sxs-lookup"><span data-stu-id="e8905-122">The ultimate destination for the source data is the **FactCurrency** fact table in **AdventureWorksDW**.</span></span> <span data-ttu-id="e8905-123">Таблица фактов **FactCurrency** имеет четыре столбца и связи с двумя таблицами измерений, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="e8905-123">The **FactCurrency** fact table has four columns, and has relationships to two dimension tables, as shown in the following table.</span></span>  
  
|<span data-ttu-id="e8905-124">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="e8905-124">Column Name</span></span>|<span data-ttu-id="e8905-125">Тип данных</span><span class="sxs-lookup"><span data-stu-id="e8905-125">Data Type</span></span>|<span data-ttu-id="e8905-126">Таблица уточняющих запросов</span><span class="sxs-lookup"><span data-stu-id="e8905-126">Lookup Table</span></span>|<span data-ttu-id="e8905-127">столбцом подстановки</span><span class="sxs-lookup"><span data-stu-id="e8905-127">Lookup Column</span></span>|  
|-----------------|---------------|------------------|-------------------|  
|<span data-ttu-id="e8905-128">AverageRate</span><span class="sxs-lookup"><span data-stu-id="e8905-128">AverageRate</span></span>|<span data-ttu-id="e8905-129">FLOAT</span><span class="sxs-lookup"><span data-stu-id="e8905-129">float</span></span>|<span data-ttu-id="e8905-130">None</span><span class="sxs-lookup"><span data-stu-id="e8905-130">None</span></span>|<span data-ttu-id="e8905-131">None</span><span class="sxs-lookup"><span data-stu-id="e8905-131">None</span></span>|  
|<span data-ttu-id="e8905-132">CurrencyKey</span><span class="sxs-lookup"><span data-stu-id="e8905-132">CurrencyKey</span></span>|<span data-ttu-id="e8905-133">int (FK)</span><span class="sxs-lookup"><span data-stu-id="e8905-133">int (FK)</span></span>|<span data-ttu-id="e8905-134">DimCurrency</span><span class="sxs-lookup"><span data-stu-id="e8905-134">DimCurrency</span></span>|<span data-ttu-id="e8905-135">CurrencyKey (PK)</span><span class="sxs-lookup"><span data-stu-id="e8905-135">CurrencyKey (PK)</span></span>|  
|<span data-ttu-id="e8905-136">DateKey</span><span class="sxs-lookup"><span data-stu-id="e8905-136">DateKey</span></span>|<span data-ttu-id="e8905-137">int (FK)</span><span class="sxs-lookup"><span data-stu-id="e8905-137">Int (FK)</span></span>|<span data-ttu-id="e8905-138">DimDate</span><span class="sxs-lookup"><span data-stu-id="e8905-138">DimDate</span></span>|<span data-ttu-id="e8905-139">DateKey (PK)</span><span class="sxs-lookup"><span data-stu-id="e8905-139">DateKey (PK)</span></span>|  
|<span data-ttu-id="e8905-140">EndOfDayRate</span><span class="sxs-lookup"><span data-stu-id="e8905-140">EndOfDayRate</span></span>|<span data-ttu-id="e8905-141">FLOAT</span><span class="sxs-lookup"><span data-stu-id="e8905-141">float</span></span>|<span data-ttu-id="e8905-142">None</span><span class="sxs-lookup"><span data-stu-id="e8905-142">None</span></span>|<span data-ttu-id="e8905-143">None</span><span class="sxs-lookup"><span data-stu-id="e8905-143">None</span></span>|  
  
### <a name="mapping-source-data-to-be-compatible-with-the-destination"></a><span data-ttu-id="e8905-144">Сопоставление совместимых данных источника с назначением</span><span class="sxs-lookup"><span data-stu-id="e8905-144">Mapping Source Data to be Compatible with the Destination</span></span>  
 <span data-ttu-id="e8905-145">Анализ форматов данных источника и назначения показывает, что для значений **CurrencyKey** и **DateKey** требуются уточняющие запросы.</span><span class="sxs-lookup"><span data-stu-id="e8905-145">Analysis of the source and destination data formats indicates that lookups will be necessary for the **CurrencyKey** and **DateKey** values.</span></span> <span data-ttu-id="e8905-146">Преобразования, которые выполнят эти уточняющие запросы, получат значения **CurrencyKey** и **DateKey** , с помощью альтернативных ключей из таблиц измерений **DimCurrency** и **DimDate** .</span><span class="sxs-lookup"><span data-stu-id="e8905-146">The transformations that will perform these lookups will obtain the **CurrencyKey** and **DateKey** values by using the alternate keys from **DimCurrency** and **DimDate** dimension tables.</span></span>  
  
|<span data-ttu-id="e8905-147">Столбец неструктурированных файлов</span><span class="sxs-lookup"><span data-stu-id="e8905-147">Flat File Column</span></span>|<span data-ttu-id="e8905-148">Имя таблицы</span><span class="sxs-lookup"><span data-stu-id="e8905-148">Table Name</span></span>|<span data-ttu-id="e8905-149">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="e8905-149">Column Name</span></span>|<span data-ttu-id="e8905-150">Тип данных</span><span class="sxs-lookup"><span data-stu-id="e8905-150">Data Type</span></span>|  
|----------------------|----------------|-----------------|---------------|  
|<span data-ttu-id="e8905-151">0</span><span class="sxs-lookup"><span data-stu-id="e8905-151">0</span></span>|<span data-ttu-id="e8905-152">FactCurrency</span><span class="sxs-lookup"><span data-stu-id="e8905-152">FactCurrency</span></span>|<span data-ttu-id="e8905-153">AverageRate</span><span class="sxs-lookup"><span data-stu-id="e8905-153">AverageRate</span></span>|<span data-ttu-id="e8905-154">FLOAT</span><span class="sxs-lookup"><span data-stu-id="e8905-154">float</span></span>|  
|<span data-ttu-id="e8905-155">1</span><span class="sxs-lookup"><span data-stu-id="e8905-155">1</span></span>|<span data-ttu-id="e8905-156">DimCurrency</span><span class="sxs-lookup"><span data-stu-id="e8905-156">DimCurrency</span></span>|<span data-ttu-id="e8905-157">CurrencyAlternateKey</span><span class="sxs-lookup"><span data-stu-id="e8905-157">CurrencyAlternateKey</span></span>|<span data-ttu-id="e8905-158">nchar (3)</span><span class="sxs-lookup"><span data-stu-id="e8905-158">nchar (3)</span></span>|  
|<span data-ttu-id="e8905-159">2</span><span class="sxs-lookup"><span data-stu-id="e8905-159">2</span></span>|<span data-ttu-id="e8905-160">DimDate</span><span class="sxs-lookup"><span data-stu-id="e8905-160">DimDate</span></span>|<span data-ttu-id="e8905-161">FullDateAlternateKey</span><span class="sxs-lookup"><span data-stu-id="e8905-161">FullDateAlternateKey</span></span>|<span data-ttu-id="e8905-162">Дата</span><span class="sxs-lookup"><span data-stu-id="e8905-162">date</span></span>|  
|<span data-ttu-id="e8905-163">3</span><span class="sxs-lookup"><span data-stu-id="e8905-163">3</span></span>|<span data-ttu-id="e8905-164">FactCurrency</span><span class="sxs-lookup"><span data-stu-id="e8905-164">FactCurrency</span></span>|<span data-ttu-id="e8905-165">EndOfDayRate</span><span class="sxs-lookup"><span data-stu-id="e8905-165">EndOfDayRate</span></span>|<span data-ttu-id="e8905-166">FLOAT</span><span class="sxs-lookup"><span data-stu-id="e8905-166">float</span></span>|  
  
## <a name="lesson-tasks"></a><span data-ttu-id="e8905-167">Задачи занятия</span><span class="sxs-lookup"><span data-stu-id="e8905-167">Lesson Tasks</span></span>  
 <span data-ttu-id="e8905-168">Это занятие содержит следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="e8905-168">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="e8905-169">Шаг 1. Создание нового проекта служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="e8905-169">Step 1: Creating a New Integration Services Project</span></span>](lesson-1-1-creating-a-new-integration-services-project.md)  
  
-   [<span data-ttu-id="e8905-170">Шаг 2. Добавление и настройка диспетчера соединений с неструктурированными файлами</span><span class="sxs-lookup"><span data-stu-id="e8905-170">Step 2: Adding and Configuring a Flat File Connection Manager</span></span>](lesson-1-2-adding-and-configuring-a-flat-file-connection-manager.md)  
  
-   [<span data-ttu-id="e8905-171">Шаг 3. Добавление и настройка диспетчера подключений OLE DB</span><span class="sxs-lookup"><span data-stu-id="e8905-171">Step 3: Adding and Configuring an OLE DB Connection Manager</span></span>](lesson-1-3-adding-and-configuring-an-ole-db-connection-manager.md)  
  
-   [<span data-ttu-id="e8905-172">Этап 4. Добавление задачи потока данных в пакет</span><span class="sxs-lookup"><span data-stu-id="e8905-172">Step 4: Adding a Data Flow Task to the Package</span></span>](lesson-1-4-adding-a-data-flow-task-to-the-package.md)  
  
-   [<span data-ttu-id="e8905-173">Шаг 5. Добавление и настройка источника неструктурированных файлов</span><span class="sxs-lookup"><span data-stu-id="e8905-173">Step 5: Adding and Configuring the Flat File Source</span></span>](lesson-1-5-adding-and-configuring-the-flat-file-source.md)  
  
-   [<span data-ttu-id="e8905-174">Шаг 6. Добавление и настройка преобразований «Уточняющий запрос»</span><span class="sxs-lookup"><span data-stu-id="e8905-174">Step 6: Adding and Configuring the Lookup Transformations</span></span>](lesson-1-6-adding-and-configuring-the-lookup-transformations.md)  
  
-   [<span data-ttu-id="e8905-175">Шаг 7. Добавление и настройка назначения OLE DB</span><span class="sxs-lookup"><span data-stu-id="e8905-175">Step 7: Adding and Configuring the OLE DB Destination</span></span>](lesson-1-7-adding-and-configuring-the-ole-db-destination.md)  
  
-   [<span data-ttu-id="e8905-176">Шаг 8. Облегчение чтения пакета, созданного на занятии 1</span><span class="sxs-lookup"><span data-stu-id="e8905-176">Step 8: Making the Lesson 1 Package Easier to Understand</span></span>](lesson-1-8-making-the-lesson-1-package-easier-to-understand.md)  
  
-   [<span data-ttu-id="e8905-177">Шаг 9. Проверка учебного пакета, созданного на занятии 1</span><span class="sxs-lookup"><span data-stu-id="e8905-177">Step 9: Testing the Lesson 1 Tutorial Package</span></span>](lesson-1-9-testing-the-lesson-1-tutorial-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="e8905-178">Начало занятия</span><span class="sxs-lookup"><span data-stu-id="e8905-178">Start the Lesson</span></span>  
 [<span data-ttu-id="e8905-179">Шаг 1. Создание нового проекта служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="e8905-179">Step 1: Creating a New Integration Services Project</span></span>](lesson-1-1-creating-a-new-integration-services-project.md)  
  
  
