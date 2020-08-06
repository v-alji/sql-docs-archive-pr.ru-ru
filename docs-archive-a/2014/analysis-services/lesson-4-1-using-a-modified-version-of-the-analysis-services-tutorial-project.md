---
title: Использование измененной версии проекта учебника по Analysis Services | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 685aa217-de1b-4df2-bf22-095228c40775
author: minewiskan
ms.author: owend
ms.openlocfilehash: b833a05a567f37443cf89f7356a0855e0827ea73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665643"
---
# <a name="using-a-modified-version-of-the-analysis-services-tutorial-project"></a><span data-ttu-id="fa73b-102">Использование измененной версии проекта Analysis Services Tutorial</span><span class="sxs-lookup"><span data-stu-id="fa73b-102">Using a Modified Version of the Analysis Services Tutorial Project</span></span>
  <span data-ttu-id="fa73b-103">Оставшиеся занятия этого учебника основаны на улучшенной версии проекта служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial, с которым велась работа на первых трех занятиях.</span><span class="sxs-lookup"><span data-stu-id="fa73b-103">The remaining lessons in this tutorial are based on an enhanced version of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project that you completed in the first three lessons.</span></span> <span data-ttu-id="fa73b-104">В представление источника данных **Adventure Works DW 2012** были добавлены некоторые таблицы и именованные вычисления, в проект были добавлены дополнительные измерения, которые также были добавлены в куб учебника по службам [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fa73b-104">Additional tables and named calculations have been added to the **Adventure Works DW 2012** data source view, additional dimensions have been added to the project, and these new dimensions have been added to the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span> <span data-ttu-id="fa73b-105">Кроме того, была добавлена вторая группа мер, которая содержит меры из второй таблицы фактов.</span><span class="sxs-lookup"><span data-stu-id="fa73b-105">In addition, a second measure group has been added, which contains measures from a second fact table.</span></span> <span data-ttu-id="fa73b-106">Улучшенная версия проекта позволит продолжить изучение добавления новых функций в приложение бизнес-аналитики без необходимости повторного применения полученных навыков.</span><span class="sxs-lookup"><span data-stu-id="fa73b-106">This enhanced project will enable you to continue learning how to add functionality to your business intelligence application without having to repeat the skills you have already learned.</span></span>  
  
 <span data-ttu-id="fa73b-107">Перед продолжением работы с учебником необходимо загрузить, извлечь, выполнить и обработать улучшенную версию проекта учебника по службам [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fa73b-107">Before you can continue with the tutorial, you must download, extract, load and process the enhanced version of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project.</span></span>  <span data-ttu-id="fa73b-108">Инструкции в этом разделе помогут выполнить все эти шаги.</span><span class="sxs-lookup"><span data-stu-id="fa73b-108">Use the instructions in this lesson to ensure you have performed all the steps.</span></span>  
  
## <a name="downloading-and-extracting-the-project-file"></a><span data-ttu-id="fa73b-109">Загрузка и извлечение файла проекта</span><span class="sxs-lookup"><span data-stu-id="fa73b-109">Downloading and Extracting the Project File</span></span>  
  
1.  <span data-ttu-id="fa73b-110">[Щелкните здесь](https://go.microsoft.com/fwlink/?LinkID=221866) , чтобы перейти на страницу загрузки, где представлены образцы проектов, прилагаемых к этому учебнику.</span><span class="sxs-lookup"><span data-stu-id="fa73b-110">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to go to the download page that provides the sample projects that go with this tutorial.</span></span> <span data-ttu-id="fa73b-111">Образцы проектов включены в состав пакета для скачивания **Учебник по службам SQL Server 2012 Analysis Services** .</span><span class="sxs-lookup"><span data-stu-id="fa73b-111">The tutorial projects are included in the **Analysis Services Tutorial SQL Server 2012** download.</span></span>  
  
2.  <span data-ttu-id="fa73b-112">Щелкните **Учебник по службам SQL Server 2012 Analysis Services** , чтобы скачать пакет, содержащий проекты для этого учебника.</span><span class="sxs-lookup"><span data-stu-id="fa73b-112">Click **Analysis Services Tutorial SQL Server 2012** to download the package that contains the projects for this tutorial.</span></span>  
  
     <span data-ttu-id="fa73b-113">По умолчанию этот ZIP-файл сохраняется в папке «Загрузки».</span><span class="sxs-lookup"><span data-stu-id="fa73b-113">By default, a .zip file is saved to the Downloads folder.</span></span> <span data-ttu-id="fa73b-114">Этот ZIP-файл необходимо перенести в расположение с более коротким путем (например, создайте папку C:\Tutorials для хранения таких файлов).</span><span class="sxs-lookup"><span data-stu-id="fa73b-114">You must move the .zip file to a location that has a shorter path (for example, create a C:\Tutorials folder to store the files).</span></span>  <span data-ttu-id="fa73b-115">После этого можно извлечь файлы из ZIP-файла.</span><span class="sxs-lookup"><span data-stu-id="fa73b-115">You can then extract the files contained in the .zip file.</span></span> <span data-ttu-id="fa73b-116">При попытке распаковать файлы из папки «Загрузки», путь к которой значительно больше, возникнет ошибка из занятия 1.</span><span class="sxs-lookup"><span data-stu-id="fa73b-116">If you attempt to unzip the files from the Downloads folder, which has a longer path, you will only get Lesson 1.</span></span>  
  
3.  <span data-ttu-id="fa73b-117">Создайте папку на уровне корневого диска или с неглубоким вложением, например C:\Tutorial.</span><span class="sxs-lookup"><span data-stu-id="fa73b-117">Create a subfolder at or near the root drive, for example, C:\Tutorial.</span></span>  
  
4.  <span data-ttu-id="fa73b-118">Переместите файл **Analysis Services Tutorial SQL Server 2012.zip** во вложенную папку.</span><span class="sxs-lookup"><span data-stu-id="fa73b-118">Move the **Analysis Services Tutorial SQL Server 2012.zip** file to the subfolder.</span></span>  
  
5.  <span data-ttu-id="fa73b-119">Щелкните файл правой кнопкой мыши и выберите команду **Извлечь все**.</span><span class="sxs-lookup"><span data-stu-id="fa73b-119">Right-click the file and select **Extract All**.</span></span>  
  
6.  <span data-ttu-id="fa73b-120">Перейдите в папку **Lesson 4 Start** , где находится файл **Analysis Services Tutorial.sln** .</span><span class="sxs-lookup"><span data-stu-id="fa73b-120">Browse to the **Lesson 4 Start** folder to find the **Analysis Services Tutorial.sln** file.</span></span>  
  
## <a name="loading-and-processing-the-enhanced-project"></a><span data-ttu-id="fa73b-121">Загрузка и обработка улучшенной версии проекта</span><span class="sxs-lookup"><span data-stu-id="fa73b-121">Loading and Processing the Enhanced Project</span></span>  
  
1.  <span data-ttu-id="fa73b-122">В [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] среде в меню **файл** выберите пункт **Закрыть решение** , чтобы закрыть файлы, которые вы не будете использовать.</span><span class="sxs-lookup"><span data-stu-id="fa73b-122">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **File** menu, click **Close Solution** to close files you won't be using.</span></span>  
  
2.  <span data-ttu-id="fa73b-123">В меню **Файл** выберите пункт **Открыть**, затем выберите **Проект/Решение**.</span><span class="sxs-lookup"><span data-stu-id="fa73b-123">On the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="fa73b-124">Перейдите в папку, где находятся распакованные файлы проекта из учебника.</span><span class="sxs-lookup"><span data-stu-id="fa73b-124">Browse to the location where you extracted the tutorial project files.</span></span>  
  
     <span data-ttu-id="fa73b-125">Найдите папку с именем **Lesson 4 Start**, а затем дважды щелкните файл Analysis Services Tutorial.sln.</span><span class="sxs-lookup"><span data-stu-id="fa73b-125">Find the folder named **Lesson 4 Start**, and then double-click Analysis Services Tutorial.sln.</span></span>  
  
4.  <span data-ttu-id="fa73b-126">Разверните улучшенную версию проекта [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial на локальном экземпляре служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]или другом экземпляре и убедитесь, что обработка завершена успешно.</span><span class="sxs-lookup"><span data-stu-id="fa73b-126">Deploy the enhanced version of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project to the local instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], or to another instance, and verify that processing completes successfully.</span></span>  
  
## <a name="understanding-the-enhancements-to-the-project"></a><span data-ttu-id="fa73b-127">Основные сведения об улучшениях проекта</span><span class="sxs-lookup"><span data-stu-id="fa73b-127">Understanding the Enhancements to the Project</span></span>  
 <span data-ttu-id="fa73b-128">Улучшенная версия проекта отличается от той версии проекта служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial, которая была завершена на первых трех занятиях.</span><span class="sxs-lookup"><span data-stu-id="fa73b-128">The enhanced version of the project is different from the version of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project that you completed in the first three lessons.</span></span> <span data-ttu-id="fa73b-129">Эти отличия описаны в следующих подразделах.</span><span class="sxs-lookup"><span data-stu-id="fa73b-129">The differences are described in the following sections.</span></span> <span data-ttu-id="fa73b-130">Просмотрите эти сведения перед тем, как приступить к оставшимся занятиям этого учебника.</span><span class="sxs-lookup"><span data-stu-id="fa73b-130">Review this information before continuing with the remaining lessons in the tutorial.</span></span>  
  
### <a name="data-source-view"></a><span data-ttu-id="fa73b-131">Представление источника данных</span><span class="sxs-lookup"><span data-stu-id="fa73b-131">Data Source View</span></span>  
 <span data-ttu-id="fa73b-132">Представление источника данных расширенной версии проекта содержит дополнительную таблицу фактов и четыре дополнительные таблицы измерений из базы данных [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fa73b-132">The data source view in the enhanced project contains one additional fact table and four additional dimension tables from the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] database.</span></span>  
  
 <span data-ttu-id="fa73b-133">Обратите внимание, что, поскольку представление источника данных содержит уже десять таблиц, диаграмма \<All Tables> выглядит переполненной.</span><span class="sxs-lookup"><span data-stu-id="fa73b-133">Notice that with ten tables in the data source view, the \<All Tables> diagram is becoming crowded.</span></span> <span data-ttu-id="fa73b-134">Это затрудняет нахождение нужных таблиц и понимание связей между ними.</span><span class="sxs-lookup"><span data-stu-id="fa73b-134">This makes it difficult to easily understand the relationships between the tables and to locate specific tables.</span></span> <span data-ttu-id="fa73b-135">Для разрешения этой проблемы таблицы поделены между двумя логическими диаграммами: **Продажи через Интернет** и **Товарооборот посредников** .</span><span class="sxs-lookup"><span data-stu-id="fa73b-135">To solve this problem, the tables are organized into two logical diagrams, the **Internet Sales** diagram and the **Reseller Sales** diagram.</span></span> <span data-ttu-id="fa73b-136">Каждая из диаграмм построена на основе одной таблицы фактов.</span><span class="sxs-lookup"><span data-stu-id="fa73b-136">These diagrams are each organized around a single fact table.</span></span> <span data-ttu-id="fa73b-137">Создание логических диаграмм позволяет просматривать определенные подмножества таблиц в представлении источника данных и работать с ними, вместо того чтобы всегда просматривать все таблицы и их связи в единой схеме.</span><span class="sxs-lookup"><span data-stu-id="fa73b-137">Creating logical diagrams lets you view and work with a specific subset of the tables in a data source view instead of always viewing all the tables and their relationships in a single diagram.</span></span>  
  
#### <a name="internet-sales-diagram"></a><span data-ttu-id="fa73b-138">Диаграмма Internet Sales</span><span class="sxs-lookup"><span data-stu-id="fa73b-138">Internet Sales Diagram</span></span>  
 <span data-ttu-id="fa73b-139">Диаграмма **Продажи через Интернет** содержит таблицы, которые относятся к продаже продуктов [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] напрямую покупателям через Интернет.</span><span class="sxs-lookup"><span data-stu-id="fa73b-139">The **Internet Sales** diagram contains the tables that are related to the sale of [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] products directly to customers through the Internet.</span></span> <span data-ttu-id="fa73b-140">В этой диаграмме содержатся четыре таблицы измерений и одна таблица фактов, которые были добавлены в представление источника данных **Adventure Works DW 2012** на занятии 1.</span><span class="sxs-lookup"><span data-stu-id="fa73b-140">The tables in the diagram are the four dimension tables and one fact table that you added to the **Adventure Works DW 2012** data source view in Lesson 1.</span></span> <span data-ttu-id="fa73b-141">Ниже приведены эти таблицы.</span><span class="sxs-lookup"><span data-stu-id="fa73b-141">These tables are as follows:</span></span>  
  
-   <span data-ttu-id="fa73b-142">**География**</span><span class="sxs-lookup"><span data-stu-id="fa73b-142">**Geography**</span></span>  
  
-   <span data-ttu-id="fa73b-143">**Customer**</span><span class="sxs-lookup"><span data-stu-id="fa73b-143">**Customer**</span></span>  
  
-   <span data-ttu-id="fa73b-144">**Дата**</span><span class="sxs-lookup"><span data-stu-id="fa73b-144">**Date**</span></span>  
  
-   <span data-ttu-id="fa73b-145">**Продукт**</span><span class="sxs-lookup"><span data-stu-id="fa73b-145">**Product**</span></span>  
  
-   <span data-ttu-id="fa73b-146">**InternetSales**</span><span class="sxs-lookup"><span data-stu-id="fa73b-146">**InternetSales**</span></span>  
  
#### <a name="reseller-sales-diagram"></a><span data-ttu-id="fa73b-147">Диаграмма Reseller Sales</span><span class="sxs-lookup"><span data-stu-id="fa73b-147">Reseller Sales Diagram</span></span>  
 <span data-ttu-id="fa73b-148">Диаграмма **Товарооборот посредников** содержит таблицы, относящиеся к продаже продуктов компании [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] при помощи посредников.</span><span class="sxs-lookup"><span data-stu-id="fa73b-148">The **Reseller Sales** diagram contains the tables that are related to the sale of [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] products by resellers.</span></span> <span data-ttu-id="fa73b-149">Эта диаграмма содержит следующие семь таблиц измерений и одну таблицу фактов из базы данных [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="fa73b-149">This diagram contains the following seven dimension tables and one fact table from the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] database:</span></span>  
  
-   <span data-ttu-id="fa73b-150">**Торговый посредник**</span><span class="sxs-lookup"><span data-stu-id="fa73b-150">**Reseller**</span></span>  
  
-   <span data-ttu-id="fa73b-151">**Promotion**</span><span class="sxs-lookup"><span data-stu-id="fa73b-151">**Promotion**</span></span>  
  
-   <span data-ttu-id="fa73b-152">**SalesTerritory**</span><span class="sxs-lookup"><span data-stu-id="fa73b-152">**SalesTerritory**</span></span>  
  
-   <span data-ttu-id="fa73b-153">**География**</span><span class="sxs-lookup"><span data-stu-id="fa73b-153">**Geography**</span></span>  
  
-   <span data-ttu-id="fa73b-154">**Дата**</span><span class="sxs-lookup"><span data-stu-id="fa73b-154">**Date**</span></span>  
  
-   <span data-ttu-id="fa73b-155">**Продукт**</span><span class="sxs-lookup"><span data-stu-id="fa73b-155">**Product**</span></span>  
  
-   <span data-ttu-id="fa73b-156">**Employee**</span><span class="sxs-lookup"><span data-stu-id="fa73b-156">**Employee**</span></span>  
  
-   <span data-ttu-id="fa73b-157">**ResellerSales**</span><span class="sxs-lookup"><span data-stu-id="fa73b-157">**ResellerSales**</span></span>  
  
 <span data-ttu-id="fa73b-158">Обратите внимание, что таблицы **DimGeography**, **DimDate**и **DimProduct** используются как в диаграмме **Продажи через Интернет** , так и в диаграмме **Товарооборот посредников** .</span><span class="sxs-lookup"><span data-stu-id="fa73b-158">Notice that the **DimGeography**, **DimDate**, and **DimProduct** tables are used in both the **Internet Sales** diagram and the **Reseller Sales** diagram.</span></span> <span data-ttu-id="fa73b-159">Таблицы измерений могут быть связаны с несколькими таблицами фактов.</span><span class="sxs-lookup"><span data-stu-id="fa73b-159">Dimension tables can be linked to multiple fact tables.</span></span>  
  
### <a name="database-and-cube-dimensions"></a><span data-ttu-id="fa73b-160">Измерения базы данных и кубов</span><span class="sxs-lookup"><span data-stu-id="fa73b-160">Database and Cube Dimensions</span></span>  
 <span data-ttu-id="fa73b-161">Проект служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial содержит пять новых измерений баз данных, куб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial содержит те же пять измерений в качестве измерений куба.</span><span class="sxs-lookup"><span data-stu-id="fa73b-161">The [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project contains five new database dimensions, and the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube contains these same five dimensions as cube dimensions.</span></span> <span data-ttu-id="fa73b-162">Эти измерения были определены таким образом, чтобы включать пользовательские иерархии и атрибуты, которые были изменены с использованием именованных вычислений, составных ключей элементов и папок отображения.</span><span class="sxs-lookup"><span data-stu-id="fa73b-162">These dimensions have been defined to have user hierarchies and attributes that were modified by using named calculations, composition member keys, and display folders.</span></span> <span data-ttu-id="fa73b-163">Новые измерения описаны в следующем списке.</span><span class="sxs-lookup"><span data-stu-id="fa73b-163">The new dimensions are described in the following list.</span></span>  
  
 <span data-ttu-id="fa73b-164">Измерение Reseller</span><span class="sxs-lookup"><span data-stu-id="fa73b-164">Reseller Dimension</span></span>  
 <span data-ttu-id="fa73b-165">Измерение "Торговый посредник" основано на таблице **Торговый посредник** в представлении источников данных **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="fa73b-165">The Reseller dimension is based on the **Reseller** table in the **Adventure Works DW 2012** data source view.</span></span>  
  
 <span data-ttu-id="fa73b-166">Измерение Promotion</span><span class="sxs-lookup"><span data-stu-id="fa73b-166">Promotion Dimension</span></span>  
 <span data-ttu-id="fa73b-167">Измерение "Продвижение" основано на таблице **Продвижение** в представлении источников данных **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="fa73b-167">The Promotion dimension is based on the **Promotion** table in the **Adventure Works DW 2012** data source view.</span></span>  
  
 <span data-ttu-id="fa73b-168">Измерение Sales Territory</span><span class="sxs-lookup"><span data-stu-id="fa73b-168">Sales Territory Dimension</span></span>  
 <span data-ttu-id="fa73b-169">Измерение "Территория продаж" основано на таблице **Территория продаж** в представлении источников данных **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="fa73b-169">The Sales Territory dimension is based on the **SalesTerritory** table in the **Adventure Works DW 2012** data source view.</span></span>  
  
 <span data-ttu-id="fa73b-170">Измерение Employee</span><span class="sxs-lookup"><span data-stu-id="fa73b-170">Employee Dimension</span></span>  
 <span data-ttu-id="fa73b-171">Измерение "Сотрудник" основано на таблице **Сотрудник** в представлении источников данных **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="fa73b-171">The Employee dimension is based on the **Employee** table in the **Adventure Works DW 2012** data source view.</span></span>  
  
 <span data-ttu-id="fa73b-172">Измерение Geography</span><span class="sxs-lookup"><span data-stu-id="fa73b-172">Geography Dimension</span></span>  
 <span data-ttu-id="fa73b-173">Измерение "География" основано на таблице **География** в представлении источников данных **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="fa73b-173">The Geography dimension is based on the **Geography** table in the **Adventure Works DW 2012** data source view.</span></span>  
  
#### <a name="analysis-services-cube"></a><span data-ttu-id="fa73b-174">Куб служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="fa73b-174">Analysis Services Cube</span></span>  
 <span data-ttu-id="fa73b-175">Куб **учебника по службам Analysis Services** теперь содержит две группы мер: исходную группу мер, основанную на таблице **InternetSales** , и вторую группу мер, основанную на таблице **ResellerSales** в представлении источников данных **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="fa73b-175">The **Analysis Services Tutorial** cube now contains two measure groups, the original measure group based on the **InternetSales** table and a second measure group based on the **ResellerSales** table in the **Adventure Works DW 2012** data source view.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="fa73b-176">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="fa73b-176">Next Task in Lesson</span></span>  
 [<span data-ttu-id="fa73b-177">Определение свойств родительского атрибута в иерархии «родители-потомки»</span><span class="sxs-lookup"><span data-stu-id="fa73b-177">Defining Parent Attribute Properties in a Parent-Child Hierarchy</span></span>](lesson-4-2-defining-parent-attribute-properties-in-a-parent-child-hierarchy.md) 
  
## <a name="see-also"></a><span data-ttu-id="fa73b-178">См. также:</span><span class="sxs-lookup"><span data-stu-id="fa73b-178">See Also</span></span>  
 [<span data-ttu-id="fa73b-179">Развертывание проекта служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="fa73b-179">Deploying an Analysis Services Project</span></span>](lesson-2-5-deploying-an-analysis-services-project.md)  
  
  
