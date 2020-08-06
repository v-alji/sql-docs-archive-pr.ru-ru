---
title: Решения для интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], about data mining
- data mining [Analysis Services], development
ms.assetid: 84f6548d-ebb0-4e10-9b29-66253fa0a04a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0ab4b5ddcc9958fa36d6c8ecae0e7fd79585b4fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658557"
---
# <a name="data-mining-solutions"></a><span data-ttu-id="85205-102">Решения интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="85205-102">Data Mining Solutions</span></span>
  <span data-ttu-id="85205-103">Решение по интеллектуальному анализу данных представляет собой решение служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , которое содержит один или несколько проектов интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="85205-103">A data mining solution is an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] solution that contains one or more data mining projects.</span></span>  
  
 <span data-ttu-id="85205-104">Подразделы этого раздела содержат сведения о проектировании и реализации интегрированного решения интеллектуального анализа данных с помощью [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="85205-104">The topics in this section provide information about how to design and implement an integrated data mining solution by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="85205-105">Общие сведения о процессе разработки в области интеллектуального анализа данных и связанных с этим средствах см. в разделе [Data Mining Concepts](data-mining-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="85205-105">For an overview of the data mining design process and related tools, see [Data Mining Concepts](data-mining-concepts.md).</span></span>  
  
 <span data-ttu-id="85205-106">Дополнительные сведения о других типах проектов, полезных для интеллектуального анализа данных, см. в разделе [Связанные проекты для решений интеллектуального анализа данных](data-mining-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="85205-106">For more information about additional projects types that are useful for data mining, see [Related Projects for Data Mining Solutions](data-mining-solutions.md).</span></span>  
  
 [<span data-ttu-id="85205-107">Реляционные и многомерные решения</span><span class="sxs-lookup"><span data-stu-id="85205-107">Relational vs. Multidimensional Solutions</span></span>](#bkmk_RelMD)  
  
 [<span data-ttu-id="85205-108">Развертывание решений интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="85205-108">Deploying Data Mining Solutions</span></span>](#bkmk_Deploy)  
  
 [<span data-ttu-id="85205-109">Пошаговые руководства по решениям</span><span class="sxs-lookup"><span data-stu-id="85205-109">Solution Walkthroughs</span></span>](#bkmk_Walkthru)  
  
##  <a name="relational-vs-multidimensional-solutions"></a><a name="bkmk_RelMD"></a><span data-ttu-id="85205-110">Реляционные и многомерные решения</span><span class="sxs-lookup"><span data-stu-id="85205-110">Relational vs. Multidimensional Solutions</span></span>  
 <span data-ttu-id="85205-111">Решение интеллектуального анализа данных может основываться либо на многомерных данных, то есть в существующем Кубе, либо на чисто реляционных данных, таких как таблицы и представления в хранилище данных, а также в текстовых файлах, книгах Excel или других внешних источниках данных.</span><span class="sxs-lookup"><span data-stu-id="85205-111">A data mining solution can be based either on multidimensional data-that is, an existing cube-or on purely relational data, such as the tables and views in a data warehouse, or on text files, Excel workbooks, or other external data sources.</span></span>  
  
-   <span data-ttu-id="85205-112">Объекты интеллектуального анализа данных можно создать внутри существующего многомерного решения базы данных.</span><span class="sxs-lookup"><span data-stu-id="85205-112">You can create data mining objects within an existing multidimensional database solution.</span></span>  
  
     <span data-ttu-id="85205-113">Обычно подобное решение создается, если куб уже создан и требуется выполнить интеллектуальный анализ данных, используя этот куб в качестве источника данных.</span><span class="sxs-lookup"><span data-stu-id="85205-113">Typically you would create a solution like this if you have already created a cube and want to perform data mining by using the cube as a data source.</span></span> <span data-ttu-id="85205-114">При перемещении и резервном копировании моделей на основе куба сам куб также должен перемещаться или копироваться.</span><span class="sxs-lookup"><span data-stu-id="85205-114">When you move and backup models based on a cube, the cube must also be moved or copied.</span></span>  
  
-   <span data-ttu-id="85205-115">Можно создать решение по интеллектуальному анализу данных, которое будет содержать только объекты интеллектуального анализа данных, включая поддерживающие источники данных и представления источников данных, и будет использовать только реляционный источник данных.</span><span class="sxs-lookup"><span data-stu-id="85205-115">You can create a data mining solution that contains only data mining objects, including the supporting data sources and data source views, and that uses relational data source only.</span></span>  
  
     <span data-ttu-id="85205-116">Этот способ предпочтителен при создании моделей интеллектуального анализа данных, поскольку обработка и выполнение запросов применительно к реляционным источникам данных обычно выполняются быстрее.</span><span class="sxs-lookup"><span data-stu-id="85205-116">This is the preferred method for creating data mining models, as processing and querying is generally fastest against relational data sources.</span></span> <span data-ttu-id="85205-117">Также можно легко перемещать модели и выполнять их резервное копирование между серверами с помощью команд EXPORT и IMPORT.</span><span class="sxs-lookup"><span data-stu-id="85205-117">You can also easily move and backup models between servers by using the EXPORT and IMPORT commands.</span></span>  
  
##  <a name="deploying-data-mining-solutions"></a><a name="bkmk_Deploy"></a><span data-ttu-id="85205-118">Развертывание решений интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="85205-118">Deploying Data Mining Solutions</span></span>  
 <span data-ttu-id="85205-119">Экземпляр служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], на котором развертывается решение, должен работать в режиме, поддерживающем многомерные объекты и объекты интеллектуального анализа данных, т. е. невозможно развернуть объекты интеллектуального анализа данных на экземпляре, который содержит данные табличных моделей или данные PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="85205-119">The instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to which you deploy the solution must be running in a mode that supports multidimensional objects and data mining objects; that is, you cannot deploy data mining objects to an instance that hosts tabular models or PowerPivot data.</span></span>  
  
 <span data-ttu-id="85205-120">Поэтому, если решение интеллектуального анализа данных создается в среде Visual Studio, обязательно используйте шаблон **Проект многомерных данных и интеллектуального анализа данных служб Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="85205-120">Therefore, when you create a data mining solution in Visual Studio, be sure to use the template, **Analysis Services Multidimensional and Data Mining Project**.</span></span>  
  
 <span data-ttu-id="85205-121">Во время развертывания решения объекты, используемые для интеллектуального анализа данных, создаются на указанном экземпляре служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] — в базе данных, имя которой совпадает с именем файла решения.</span><span class="sxs-lookup"><span data-stu-id="85205-121">When you deploy the solution, the objects used for data mining are created in the specified [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance, in a database with the same name as the solution file.</span></span>  
  
 <span data-ttu-id="85205-122">Дополнительные сведения о способе развертывания как реляционных, так и многомерных решений см. в разделе [Развертывание решений интеллектуального анализа данных](deployment-of-data-mining-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="85205-122">For more information about how to deploy both relational and multidimensional solutions, see [Deployment of Data Mining Solutions](deployment-of-data-mining-solutions.md).</span></span>  
  
##  <a name="solution-walkthrough"></a><a name="bkmk_Walkthru"></a><span data-ttu-id="85205-123">Пошаговое руководство по решению</span><span class="sxs-lookup"><span data-stu-id="85205-123">Solution Walkthrough</span></span>  
 <span data-ttu-id="85205-124">Содержит обзорные сведения о том, как создавать решения по интеллектуальному анализу данных с помощью мастера интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="85205-124">Provides an overview of how to create data mining solutions by using the Data Mining Wizard.</span></span>  
  
 [<span data-ttu-id="85205-125">Создание реляционной структуры интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="85205-125">Create a Relational Mining Structure</span></span>](create-a-relational-mining-structure.md)  
 <span data-ttu-id="85205-126">Создание структуры интеллектуального анализа данных на основе реляционных данных, текстовых файлов и других источников, которые можно объединить в представлении источников данных.</span><span class="sxs-lookup"><span data-stu-id="85205-126">Create a mining structure from relational data, text files, and other sources that can be combined in a data source view.</span></span>  
  
 [<span data-ttu-id="85205-127">Создание структуры интеллектуального анализа данных OLAP</span><span class="sxs-lookup"><span data-stu-id="85205-127">Create an OLAP Mining Structure</span></span>](create-an-olap-mining-structure.md)  
 <span data-ttu-id="85205-128">Создание структуры интеллектуального анализа данных на основе данных куба OLAP.</span><span class="sxs-lookup"><span data-stu-id="85205-128">Create a mining structure based on data in an OLAP cube.</span></span> <span data-ttu-id="85205-129">Модели, создаваемые на основе данных OLAP, можно сохранять в виде измерения интеллектуального анализа данных, или же можно сохранить набор данных и модели в виде нового куба.</span><span class="sxs-lookup"><span data-stu-id="85205-129">Models that you create from OLAP data can be saved as a data mining dimension, or you can save the set of data and your models as a new cube.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="85205-130">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="85205-130">In This Section</span></span>  
 [<span data-ttu-id="85205-131">Проекты интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="85205-131">Data Mining Projects</span></span>](data-mining-projects.md)  
  
 [<span data-ttu-id="85205-132">Обработка объектов интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="85205-132">Processing Data Mining Objects</span></span>](processing-data-mining-objects.md)  
  
 [<span data-ttu-id="85205-133">Связанные проекты для решений интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="85205-133">Related Projects for Data Mining Solutions</span></span>](data-mining-solutions.md)  
  
 [<span data-ttu-id="85205-134">Развертывание решений интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="85205-134">Deployment of Data Mining Solutions</span></span>](deployment-of-data-mining-solutions.md)  
  
## <a name="related-tasks-and-topics"></a><span data-ttu-id="85205-135">Связанные задачи и разделы</span><span class="sxs-lookup"><span data-stu-id="85205-135">Related Tasks and Topics</span></span>  
 <span data-ttu-id="85205-136">После создания базового решения по интеллектуальному анализу данных, включая источники данных и структуру интеллектуального анализа данных, можно строить решение дальше, добавляя новые модели, тестируя и сравнивая модели, создавая прогнозы и экспериментируя с подмножествами данных.</span><span class="sxs-lookup"><span data-stu-id="85205-136">After you have created a basic data mining solution, including data sources and a mining structure, you can build on the solution by adding new models, testing and comparing models, creating predictions, and experimenting with subsets of data.</span></span>  
  
 <span data-ttu-id="85205-137">Дополнительные сведения см. по следующим ссылкам:</span><span class="sxs-lookup"><span data-stu-id="85205-137">For more information, see the following links:</span></span>  
  
|<span data-ttu-id="85205-138">Задания</span><span class="sxs-lookup"><span data-stu-id="85205-138">Tasks</span></span>|<span data-ttu-id="85205-139">Разделы</span><span class="sxs-lookup"><span data-stu-id="85205-139">Topics</span></span>|  
|-----------|------------|  
|<span data-ttu-id="85205-140">Тестирование создаваемых моделей, проверка качества обучающих данных и создание диаграмм, представляющих точность моделей интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="85205-140">Test the models you create, validate the quality of your training data, and create charts that represent the accuracy of data mining models.</span></span>|[<span data-ttu-id="85205-141">Тестирование и проверка (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="85205-141">Testing and Validation &#40;Data Mining&#41;</span></span>](testing-and-validation-data-mining.md)|  
|<span data-ttu-id="85205-142">Обучение модели путем заполнения структуры и связанных моделей данными.</span><span class="sxs-lookup"><span data-stu-id="85205-142">Train the model by populating the structure and related models with data.</span></span> <span data-ttu-id="85205-143">Обновление и расширение моделей новыми данными.</span><span class="sxs-lookup"><span data-stu-id="85205-143">Update and extend models with new data.</span></span>|[<span data-ttu-id="85205-144">Обработка объектов интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="85205-144">Processing Data Mining Objects</span></span>](processing-data-mining-objects.md)|  
|<span data-ttu-id="85205-145">Настройка модели интеллектуального анализа данных путем применения фильтров к обучающим данным, выбора другого алгоритма или задания расширенных параметров алгоритма.</span><span class="sxs-lookup"><span data-stu-id="85205-145">Customize a mining model by applying filters to the training data, choosing a different algorithm, or setting advanced algorithm parameters.</span></span>|[<span data-ttu-id="85205-146">Настройка структуры и моделей интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="85205-146">Customize Mining Models and Structure</span></span>](customize-mining-models-and-structure.md)|  
|<span data-ttu-id="85205-147">Настройка модели интеллектуального анализа данных путем применения фильтров к данным, используемым в обучении модели.</span><span class="sxs-lookup"><span data-stu-id="85205-147">Customize a mining model by applying filters to the data used in training the mode.</span></span>|[<span data-ttu-id="85205-148">Добавление моделей интеллектуального анализа данных в структуру (службы Analysis Services — интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="85205-148">Add Mining Models to a Structure &#40;Analysis Services - Data Mining&#41;</span></span>](add-mining-models-to-a-structure-analysis-services-data-mining.md)|  
|<span data-ttu-id="85205-149">Обновление решений по интеллектуальному анализу данных и управление ими.</span><span class="sxs-lookup"><span data-stu-id="85205-149">Update and manage data mining solutions.</span></span>|<span data-ttu-id="85205-150">Ссылка подлежит определению</span><span class="sxs-lookup"><span data-stu-id="85205-150">Link TBD</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="85205-151">См. также:</span><span class="sxs-lookup"><span data-stu-id="85205-151">See Also</span></span>  
 [<span data-ttu-id="85205-152">Учебники по интеллектуальному анализу данных (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="85205-152">Data Mining Tutorials &#40;Analysis Services&#41;</span></span>](../data-mining-tutorials-analysis-services.md)  
  
  
