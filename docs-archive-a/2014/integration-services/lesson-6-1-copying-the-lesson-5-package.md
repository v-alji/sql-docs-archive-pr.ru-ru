---
title: Шаг 1. Копирование пакета, созданного на занятии 5 | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: a25fcc13-987e-4f3d-8f0c-76f7e6e59920
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b30ec927084548a2371f22d857d5302e5dc84c5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669001"
---
# <a name="step-1-copying-the-lesson-5-package"></a><span data-ttu-id="7c459-102">Шаг 1. Копирование пакета занятия 5</span><span class="sxs-lookup"><span data-stu-id="7c459-102">Step 1: Copying the Lesson 5 Package</span></span>
  <span data-ttu-id="7c459-103">В этой задаче будет создана копия пакета Lesson 5.dtsx, созданного на занятии 5.</span><span class="sxs-lookup"><span data-stu-id="7c459-103">In this task, you will create a copy of the Lesson 5.dtsx package that you created in Lesson 5.</span></span> <span data-ttu-id="7c459-104">Либо можно добавить пакет для занятия 5, прилагаемый к учебнику по проекту, и скопировать его.</span><span class="sxs-lookup"><span data-stu-id="7c459-104">Alternatively, you can add the completed lesson 5 package that is included with the tutorial to the project, and then copy it instead.</span></span> <span data-ttu-id="7c459-105">Полученная копия впоследствии будет использоваться на протяжении всего занятия 6.</span><span class="sxs-lookup"><span data-stu-id="7c459-105">You will use this new copy throughout the rest of Lesson 6.</span></span>  
  
### <a name="to-copy-the-lesson-5-package"></a><span data-ttu-id="7c459-106">Копирование пакета занятия 5</span><span class="sxs-lookup"><span data-stu-id="7c459-106">To copy the Lesson 5 package</span></span>  
  
1.  <span data-ttu-id="7c459-107">Если SQL Server Data Tools еще не открыты, нажмите кнопку «Пуск», укажите пункт «Все программы», пункт «Microsoft SQL Server 2012», а затем выберите пункт «SQL Server Data Tools».</span><span class="sxs-lookup"><span data-stu-id="7c459-107">If SQL Server Data Tools is not already open, click Start, point to All Programs, point to Microsoft SQL Server 2012, and then click SQL Server Data Tools.</span></span>  
  
2.  <span data-ttu-id="7c459-108">В меню Файл последовательно выберите команды Открыть, Проект или решение, Учебник по службам SSIS и нажмите кнопку Открыть, а затем дважды щелкните значок SSIS Tutorial.sln.</span><span class="sxs-lookup"><span data-stu-id="7c459-108">On the File menu, click Open, click Project/Solution, select SSIS Tutorial and click Open, and then double-click SSIS Tutorial.sln.</span></span>  
  
3.  <span data-ttu-id="7c459-109">В обозревателе решений правой кнопкой мыши щелкните Lesson 5.dtsx и выберите команду «Копировать».</span><span class="sxs-lookup"><span data-stu-id="7c459-109">In Solution Explorer, right-click Lesson 5.dtsx, and then click Copy.</span></span>  
  
4.  <span data-ttu-id="7c459-110">В обозревателе решений правой кнопкой мыши щелкните значок Пакеты служб SSIS и выберите команду Вставить.</span><span class="sxs-lookup"><span data-stu-id="7c459-110">In Solution Explorer, right-click SSIS Packages, and then click Paste.</span></span>  
  
     <span data-ttu-id="7c459-111">По умолчанию копируемому пакету присваивается имя Lesson 6.dtsx.</span><span class="sxs-lookup"><span data-stu-id="7c459-111">By default, the copied package is named Lesson 6.dtsx.</span></span>  
  
5.  <span data-ttu-id="7c459-112">Чтобы открыть пакет, в обозревателе решений дважды щелкните Lesson 6.dtsx.</span><span class="sxs-lookup"><span data-stu-id="7c459-112">In the Solution Explorer, double-click Lesson 6.dtsx to open the package.</span></span>  
  
6.  <span data-ttu-id="7c459-113">Щелкните правой кнопкой мыши фон вкладки Поток управления и выберите Свойства.</span><span class="sxs-lookup"><span data-stu-id="7c459-113">Right-click anywhere in the background of the Control Flow tab then click Properties.</span></span>  
  
7.  <span data-ttu-id="7c459-114">В окне «Свойства» измените свойство Name на «Занятие 6».</span><span class="sxs-lookup"><span data-stu-id="7c459-114">In the Properties window, update the Name property to Lesson 6.</span></span>  
  
8.  <span data-ttu-id="7c459-115">Установите флажок для свойства ID, щелкните стрелку раскрывающегося списка, а затем в списке выберите \<Generate New ID>.</span><span class="sxs-lookup"><span data-stu-id="7c459-115">Click the box for the ID property, then click the dropdown arrow, and then click \<Generate New ID>.</span></span>  
  
### <a name="to-add-the-completed-lesson-5-package"></a><span data-ttu-id="7c459-116">Добавление готового пакета занятия 5</span><span class="sxs-lookup"><span data-stu-id="7c459-116">To add the completed Lesson 5 package</span></span>  
  
1.  <span data-ttu-id="7c459-117">Откройте SQL Server Data Tools, затем откройте проект «Учебник по службам SSIS».</span><span class="sxs-lookup"><span data-stu-id="7c459-117">Open SQL Server Data Tools and open the SSIS Tutorial project.</span></span>  
  
2.  <span data-ttu-id="7c459-118">В обозревателе решений правой кнопкой мыши щелкните значок Пакеты служб SSIS и выберите команду Добавить существующий пакет.</span><span class="sxs-lookup"><span data-stu-id="7c459-118">In Solution Explorer, right-click SSIS Packages, and click Add Existing Package.</span></span>  
  
3.  <span data-ttu-id="7c459-119">В диалоговом окне «Добавление копии существующего пакета» в разделе «Размещение пакета» выберите пункт «Файловая система».</span><span class="sxs-lookup"><span data-stu-id="7c459-119">In the Add Copy of Existing Package dialog box, in Package location, select File system.</span></span>  
  
4.  <span data-ttu-id="7c459-120">Нажмите кнопку обзора (…), перейдите в папку пакета Lesson 5.dtsx и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="7c459-120">Click the browse (...) button, Lesson 5.dtsx on your machine, and then click **Open**.</span></span>  
  
     <span data-ttu-id="7c459-121">Чтобы загрузить все пакеты занятий этого учебника, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="7c459-121">To download all of the lesson packages for this tutorial, do the following.</span></span>  
  
    1.  <span data-ttu-id="7c459-122">Перейдите к [образцам продуктов служб Integration Services](https://go.microsoft.com/fwlink/?LinkId=275027).</span><span class="sxs-lookup"><span data-stu-id="7c459-122">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=275027)</span></span>  
  
    2.  <span data-ttu-id="7c459-123">Перейдите на вкладку **Downloads (загрузки** ).</span><span class="sxs-lookup"><span data-stu-id="7c459-123">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="7c459-124">Щелкните файл SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip.</span><span class="sxs-lookup"><span data-stu-id="7c459-124">Click the SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
5.  <span data-ttu-id="7c459-125">Выполните копирование и вставку пакета занятия 5, как описано в шагах 3–8 предыдущей процедуры.</span><span class="sxs-lookup"><span data-stu-id="7c459-125">Copy and paste the Lesson 5 package as described in steps 3-8 in the previous procedure.</span></span>  
  
     <span data-ttu-id="7c459-126">После копирования пакета занятия 5, если в настоящее время в решении используются пакеты из предыдущих занятий, щелкните правой кнопкой мыши каждый пакет из занятий 1–5, а затем выберите «Исключить из проекта».</span><span class="sxs-lookup"><span data-stu-id="7c459-126">After copying the Lesson 5 package, if you currently have the packages from the previous lessons in your solution, right-click each package from lessons 1-5 and click Exclude From Project.</span></span> <span data-ttu-id="7c459-127">По завершении в решении должен остаться только файл Lesson 6.dtsx.</span><span class="sxs-lookup"><span data-stu-id="7c459-127">When done you should have only Lesson 6.dtsx in your solution.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="7c459-128">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="7c459-128">Next Task in Lesson</span></span>  
 [<span data-ttu-id="7c459-129">Этап 2. Преобразование проекта в модель развертывания проекта</span><span class="sxs-lookup"><span data-stu-id="7c459-129">Step 2: Converting the Project to the Project Deployment Model</span></span>](lesson-6-2-converting-the-project-to-the-project-deployment-model.md)  
  
  
