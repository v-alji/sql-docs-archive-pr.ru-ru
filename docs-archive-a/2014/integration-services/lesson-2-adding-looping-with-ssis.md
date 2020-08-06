---
title: Занятие 2. Добавление циклов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 01f2ed61-1e5a-4ec6-b6a6-2bd070c64077
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 65efb84b4e50b470470e396bbe5681ce4b5dfac3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657151"
---
# <a name="lesson-2-adding-looping"></a><span data-ttu-id="2ec9e-102">Занятие 2. Добавление циклов</span><span class="sxs-lookup"><span data-stu-id="2ec9e-102">Lesson 2: Adding Looping</span></span>
  <span data-ttu-id="2ec9e-103">В [уроке 1. Создание проекта и основного пакета](lesson-1-create-a-project-and-basic-package-with-ssis.md)был создан пакет, который извлекает данные из одного источника неструктурированного файла, преобразует данные с помощью преобразований «Уточняющий запрос» и, наконец, загружает данные в таблицу фактов **FactCurrency** образца базы данных **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="2ec9e-103">In [Lesson 1: Creating the Project and Basic Package](lesson-1-create-a-project-and-basic-package-with-ssis.md), you created a package that extracted data from a single flat file source, transformed the data using Lookup transformations, and finally loaded the data into the **FactCurrency** fact table of the **AdventureWorksDW2012** sample database.</span></span>  
  
 <span data-ttu-id="2ec9e-104">Однако в процессе извлечения, преобразования и загрузки (ETL) редко используется отдельный неструктурированный файл.</span><span class="sxs-lookup"><span data-stu-id="2ec9e-104">However, it is rare for an extract, transform, and load (ETL) process to use a single flat file.</span></span> <span data-ttu-id="2ec9e-105">Как правило, в процессе ETL данные извлекаются из нескольких источников неструктурированного файла.</span><span class="sxs-lookup"><span data-stu-id="2ec9e-105">A typical ETL process would extract data from multiple flat file sources.</span></span> <span data-ttu-id="2ec9e-106">Извлечение данных из нескольких источников требует итеративного потока управления.</span><span class="sxs-lookup"><span data-stu-id="2ec9e-106">Extracting data from multiple sources requires an iterative control flow.</span></span> <span data-ttu-id="2ec9e-107">Одной из наиболее ожидаемых функций [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] является возможность легко добавлять в пакеты итерации или циклы.</span><span class="sxs-lookup"><span data-stu-id="2ec9e-107">One of the most anticipated features of [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] is the ability to easily add iteration or looping to packages.</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="2ec9e-108">предоставляют два типа контейнеров для циклов по пакетам: контейнер «цикл по каждому элементу» и контейнер «цикл по элементам».</span><span class="sxs-lookup"><span data-stu-id="2ec9e-108">provides two types of containers for looping through packages: the Foreach Loop container and the For Loop container.</span></span> <span data-ttu-id="2ec9e-109">В контейнере «цикл по каждому элементу» для выполнения циклической обработки используется перечислитель, а в контейнере «цикл по элементам» чаще используется переменное выражение.</span><span class="sxs-lookup"><span data-stu-id="2ec9e-109">The Foreach Loop container uses an enumerator to perform the looping, whereas the For Loop container typically uses a variable expression.</span></span> <span data-ttu-id="2ec9e-110">На этом занятии рассматривается контейнер «цикл по каждому элементу».</span><span class="sxs-lookup"><span data-stu-id="2ec9e-110">This lesson uses the Foreach Loop container.</span></span>  
  
 <span data-ttu-id="2ec9e-111">При помощи этого контейнера поток управления в пакете может повторяться для каждого элемента указанного перечислителя.</span><span class="sxs-lookup"><span data-stu-id="2ec9e-111">The Foreach Loop container enables a package to repeat the control flow for each member of a specified enumerator.</span></span> <span data-ttu-id="2ec9e-112">Используя контейнер «цикл по каждому элементу», можно перечислять:</span><span class="sxs-lookup"><span data-stu-id="2ec9e-112">With the Foreach Loop container, you can enumerate:</span></span>  
  
-   <span data-ttu-id="2ec9e-113">Строки наборов записей ADO</span><span class="sxs-lookup"><span data-stu-id="2ec9e-113">ADO recordset rows</span></span>  
  
-   <span data-ttu-id="2ec9e-114">Данные схемы ADO.NET:</span><span class="sxs-lookup"><span data-stu-id="2ec9e-114">ADO .Net schema information</span></span>  
  
-   <span data-ttu-id="2ec9e-115">структуры файлов и каталогов;</span><span class="sxs-lookup"><span data-stu-id="2ec9e-115">File and directory structures</span></span>  
  
-   <span data-ttu-id="2ec9e-116">системные, пакетные и пользовательские переменные;</span><span class="sxs-lookup"><span data-stu-id="2ec9e-116">System, package and user variables</span></span>  
  
-   <span data-ttu-id="2ec9e-117">перечисляемые объекты, содержащиеся в переменной;</span><span class="sxs-lookup"><span data-stu-id="2ec9e-117">Enumerable objects contained in a variable</span></span>  
  
-   <span data-ttu-id="2ec9e-118">элементы коллекции;</span><span class="sxs-lookup"><span data-stu-id="2ec9e-118">Items in a collection</span></span>  
  
-   <span data-ttu-id="2ec9e-119">узлы в выражении языка пути XML (XPath);</span><span class="sxs-lookup"><span data-stu-id="2ec9e-119">Nodes in an XML Path Language (XPath) expression</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="2ec9e-120">Управляющие объекты (SMO)</span><span class="sxs-lookup"><span data-stu-id="2ec9e-120">Management Objects (SMO)</span></span>  
  
 <span data-ttu-id="2ec9e-121">На этом занятии предстоит изменить простой пакет ETL, созданный на занятии 1, с целью использования возможностей контейнера «цикл по каждому элементу».</span><span class="sxs-lookup"><span data-stu-id="2ec9e-121">In this lesson, you will modify the simple ETL package created in Lesson 1 to take advantage of the Foreach Loop container.</span></span> <span data-ttu-id="2ec9e-122">Кроме того, предстоит задать пользовательские пакетные переменные, чтобы в пакете учебника могли последовательно обрабатываться все неструктурированные файлы в папке.</span><span class="sxs-lookup"><span data-stu-id="2ec9e-122">You will also set user-defined package variables to enable the tutorial package to iterate through all the flat files in the folder.</span></span> <span data-ttu-id="2ec9e-123">Если предыдущее занятие не выполнялось, можно скопировать завершенный пакет занятия 1, который включен в учебник.</span><span class="sxs-lookup"><span data-stu-id="2ec9e-123">If you have not completed the previous lesson, you can also copy the completed Lesson 1 package that is included with the tutorial.</span></span>  
  
 <span data-ttu-id="2ec9e-124">На этом занятии будет изменяться только поток управления, поток данных не рассматривается.</span><span class="sxs-lookup"><span data-stu-id="2ec9e-124">In this lesson, you will not modify the data flow, only the control flow.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2ec9e-125">Для выполнения упражнений этого учебника потребуется образец базы данных **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="2ec9e-125">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="2ec9e-126">Дополнительные сведения об установке и развертывании **AdventureWorksDW2012**см. в разделе [Проект образцов продуктов службы Reporting Services на сайте CodePlex](https://go.microsoft.com/fwlink/p/?LinkID=526910).</span><span class="sxs-lookup"><span data-stu-id="2ec9e-126">For more information about how to install and deploy **AdventureWorksDW2012**, see [Reporting Services Product Samples on CodePlex](https://go.microsoft.com/fwlink/p/?LinkID=526910).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="2ec9e-127">Задачи занятия</span><span class="sxs-lookup"><span data-stu-id="2ec9e-127">Lesson Tasks</span></span>  
 <span data-ttu-id="2ec9e-128">Это занятие содержит следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="2ec9e-128">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="2ec9e-129">Шаг 1. Копирование пакета занятия 1</span><span class="sxs-lookup"><span data-stu-id="2ec9e-129">Step 1: Copying the Lesson 1 Package</span></span>](lesson-2-1-copying-the-lesson-1-package.md)  
  
-   [<span data-ttu-id="2ec9e-130">Шаг 2. Добавление и настройка контейнера "цикл по каждому элементу"</span><span class="sxs-lookup"><span data-stu-id="2ec9e-130">Step 2: Adding and Configuring the Foreach Loop Container</span></span>](lesson-2-2-adding-and-configuring-the-foreach-loop-container.md)  
  
-   [<span data-ttu-id="2ec9e-131">Шаг 3. Изменение диспетчера соединений с неструктурированными файлами</span><span class="sxs-lookup"><span data-stu-id="2ec9e-131">Step 3: Modifying the Flat File Connection Manager</span></span>](lesson-2-3-modifying-the-flat-file-connection-manager.md)  
  
-   [<span data-ttu-id="2ec9e-132">Шаг 4. Проверка учебного пакета, созданного на занятии 2</span><span class="sxs-lookup"><span data-stu-id="2ec9e-132">Step 4: Testing the Lesson 2 Tutorial Package</span></span>](lesson-2-4-testing-the-lesson-2-tutorial-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="2ec9e-133">Начало занятия</span><span class="sxs-lookup"><span data-stu-id="2ec9e-133">Start the Lesson</span></span>  
 [<span data-ttu-id="2ec9e-134">Шаг 1. Копирование пакета занятия 1</span><span class="sxs-lookup"><span data-stu-id="2ec9e-134">Step 1: Copying the Lesson 1 Package</span></span>](lesson-2-1-copying-the-lesson-1-package.md)  
  
## <a name="see-also"></a><span data-ttu-id="2ec9e-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="2ec9e-135">See Also</span></span>  
 [<span data-ttu-id="2ec9e-136">Контейнер «цикл по элементам»</span><span class="sxs-lookup"><span data-stu-id="2ec9e-136">For Loop Container</span></span>](control-flow/for-loop-container.md)  
  
  
