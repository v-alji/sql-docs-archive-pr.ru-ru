---
title: Шаг 1. Копирование пакета, созданного на занятии 1 | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 7f1616c2-2b4e-4010-be50-27d7b897403a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 43e117d82983bdaca8959fe7af8940d248ded97b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664328"
---
# <a name="step-1-copying-the-lesson-1-package"></a><span data-ttu-id="0fb02-102">Шаг 1. Копирование пакета занятия 1</span><span class="sxs-lookup"><span data-stu-id="0fb02-102">Step 1: Copying the Lesson 1 Package</span></span>
  <span data-ttu-id="0fb02-103">В этой задаче будет создана копия пакета Lesson 1.dtsx, созданного на занятии 1.</span><span class="sxs-lookup"><span data-stu-id="0fb02-103">In this task, you will create a copy of the Lesson 1.dtsx package that you created in Lesson 1.</span></span> <span data-ttu-id="0fb02-104">Если вы не прошли занятие 1, можно добавить пакет задания 1, прилагаемый к учебнику по проекту, и скопировать его.</span><span class="sxs-lookup"><span data-stu-id="0fb02-104">If you did not complete Lesson 1, you can add the completed lesson 1 package that is included with the tutorial to the project, and then copy it instead.</span></span> <span data-ttu-id="0fb02-105">Полученная копия впоследствии будет использоваться на протяжении всего занятия 2.</span><span class="sxs-lookup"><span data-stu-id="0fb02-105">You will use this new copy throughout the rest of Lesson 2.</span></span>  
  
### <a name="to-create-the-lesson-2-package"></a><span data-ttu-id="0fb02-106">Создание пакета занятия 2</span><span class="sxs-lookup"><span data-stu-id="0fb02-106">To create the Lesson 2 package</span></span>  
  
1.  <span data-ttu-id="0fb02-107">Если средства [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools еще не открыты, нажмите кнопку **Пуск**, наведите указатель на пункт **Все программы**, затем на пункт **Microsoft SQL Server 2012**и выберите пункт **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="0fb02-107">If [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools is not already open, click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2012**, and then click **SQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="0fb02-108">В меню **Файл** выберите команду **Открыть**, выберите пункт **Проект или решение**, щелкните папку **Учебник по службам SSIS** и выберите **Открыть**, а затем дважды щелкните файл **SSIS Tutorial.sln**.</span><span class="sxs-lookup"><span data-stu-id="0fb02-108">On the **File** menu, click **Open**, click **Project/Solution**, click the **SSIS Tutorial** folder and click **Open**, and then double-click **SSIS Tutorial.sln**.</span></span>  
  
3.  <span data-ttu-id="0fb02-109">В обозревателе решений правой кнопкой мыши щелкните **Lesson 1.dtsx**и выберите команду **Копировать**.</span><span class="sxs-lookup"><span data-stu-id="0fb02-109">In Solution Explorer, right-click **Lesson 1.dtsx**, and then click **Copy**.</span></span>  
  
4.  <span data-ttu-id="0fb02-110">В обозреватель решений щелкните правой кнопкой мыши **пакеты служб SSIS**и выберите команду **Вставить**.</span><span class="sxs-lookup"><span data-stu-id="0fb02-110">In Solution Explorer, right-click **SSIS Packages**, and then click **Paste**.</span></span>  
  
     <span data-ttu-id="0fb02-111">По умолчанию копируемому пакету будет присвоено имя Lesson 2.dtsx.</span><span class="sxs-lookup"><span data-stu-id="0fb02-111">By default, the copied package will be named Lesson 2.dtsx.</span></span>  
  
5.  <span data-ttu-id="0fb02-112">В обозреватель решений дважды щелкните **занятие 2. dtsx** , чтобы открыть пакет.</span><span class="sxs-lookup"><span data-stu-id="0fb02-112">In Solution Explorer, double-click **Lesson 2.dtsx** to open the package</span></span>  
  
6.  <span data-ttu-id="0fb02-113">Щелкните правой кнопкой мыши в области конструктора **Поток управления** и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="0fb02-113">Right-click anywhere in the background of the **Control Flow** design surface and click **Properties**.</span></span>  
  
7.  <span data-ttu-id="0fb02-114">В окно свойств измените `Name` свойство на `Lesson 2` .</span><span class="sxs-lookup"><span data-stu-id="0fb02-114">In the Properties window, update the `Name` property to `Lesson 2`.</span></span>  
  
8.  <span data-ttu-id="0fb02-115">Установите флажок для свойства **ID** , щелкните стрелку раскрывающегося списка, а затем в списке выберите **\<Generate New ID>**.</span><span class="sxs-lookup"><span data-stu-id="0fb02-115">Click the box for the **ID** property, click the dropdown arrow and then click **\<Generate New ID>**.</span></span>  
  
### <a name="to-add-the-completed-lesson-1-package"></a><span data-ttu-id="0fb02-116">Добавление готового пакета занятия 1</span><span class="sxs-lookup"><span data-stu-id="0fb02-116">To add the completed Lesson 1 package</span></span>  
  
1.  <span data-ttu-id="0fb02-117">Откройте [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools, затем откройте проект «Учебник по службам SSIS».</span><span class="sxs-lookup"><span data-stu-id="0fb02-117">Open [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools and open the SSIS Tutorial project.</span></span>  
  
2.  <span data-ttu-id="0fb02-118">В обозреватель решений щелкните правой кнопкой мыши **пакеты служб SSIS**и выберите команду **Добавить существующий пакет**.</span><span class="sxs-lookup"><span data-stu-id="0fb02-118">In Solution Explorer, right-click **SSIS Packages**, and click **Add Existing Package**.</span></span>  
  
3.  <span data-ttu-id="0fb02-119">В диалоговом окне **Добавление копии существующего пакета** в разделе **Расположение пакета**выберите пункт **Файловая система**.</span><span class="sxs-lookup"><span data-stu-id="0fb02-119">In the **Add Copy of Existing Package** dialog box, in **Package location**, select **File system**.</span></span>  
  
4.  <span data-ttu-id="0fb02-120">Нажмите кнопку обзора **(…)**, перейдите в папку с пакетом **Lesson 1.dtsx** на компьютере и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="0fb02-120">Click the browse **(...)** button, navigate to **Lesson 1.dtsx** on your machine, and then click **Open**.</span></span>  
  
     <span data-ttu-id="0fb02-121">Чтобы загрузить все пакеты занятий этого учебника, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="0fb02-121">To download all of the lesson packages for this tutorial, do the following.</span></span>  
  
    1.  <span data-ttu-id="0fb02-122">Перейдите к [образцам продуктов служб Integration Services](https://go.microsoft.com/fwlink/?LinkId=275027).</span><span class="sxs-lookup"><span data-stu-id="0fb02-122">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=275027)</span></span>  
  
    2.  <span data-ttu-id="0fb02-123">Перейдите на вкладку **Downloads (загрузки** ).</span><span class="sxs-lookup"><span data-stu-id="0fb02-123">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="0fb02-124">Щелкните файл SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip.</span><span class="sxs-lookup"><span data-stu-id="0fb02-124">Click the SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
5.  <span data-ttu-id="0fb02-125">Выполните копирование и вставку пакета занятия 1, как описано в шагах 3–8 предыдущей процедуры.</span><span class="sxs-lookup"><span data-stu-id="0fb02-125">Copy and paste the Lesson 1 package as described in steps 3-8 in the previous procedure.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="0fb02-126">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="0fb02-126">Next Task in Lesson</span></span>  
 [<span data-ttu-id="0fb02-127">Шаг 2. Добавление и настройка контейнера "цикл по каждому элементу"</span><span class="sxs-lookup"><span data-stu-id="0fb02-127">Step 2: Adding and Configuring the Foreach Loop Container</span></span>](lesson-2-2-adding-and-configuring-the-foreach-loop-container.md)  
  
  
