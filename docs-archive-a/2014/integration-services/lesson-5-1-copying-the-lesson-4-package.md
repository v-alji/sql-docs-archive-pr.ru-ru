---
title: Шаг 1. Копирование пакета, созданного на занятии 4 | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 8aa7d690-4649-4c0a-ac6f-9504637ee426
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1140c0e7d26f11f79e18d42143c1ed084c4ff144
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668433"
---
# <a name="step-1-copying-the-lesson-4-package"></a><span data-ttu-id="75df5-102">Шаг 1. Копирование пакета занятия 4</span><span class="sxs-lookup"><span data-stu-id="75df5-102">Step 1: Copying the Lesson 4 Package</span></span>
  <span data-ttu-id="75df5-103">В этой задаче будет создана копия пакета Lesson 4.dtsx, созданного на занятии 4.</span><span class="sxs-lookup"><span data-stu-id="75df5-103">In this task, you will create a copy of the Lesson 4.dtsx package that you created in Lesson 4.</span></span> <span data-ttu-id="75df5-104">Либо можно добавить пакет для занятия 4, прилагаемый к учебнику по проекту, и скопировать его.</span><span class="sxs-lookup"><span data-stu-id="75df5-104">Alternatively, you can add the completed lesson 4 package that is included with the tutorial to the project, and then copy it instead.</span></span> <span data-ttu-id="75df5-105">Полученная копия впоследствии будет использоваться на протяжении всего занятия 5.</span><span class="sxs-lookup"><span data-stu-id="75df5-105">You will use this new copy throughout the rest of Lesson 5.</span></span>  
  
### <a name="to-copy-the-lesson-4-package"></a><span data-ttu-id="75df5-106">Копирование пакета занятия 4</span><span class="sxs-lookup"><span data-stu-id="75df5-106">To copy the Lesson 4 package</span></span>  
  
1.  <span data-ttu-id="75df5-107">Если средства [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools еще не открыты, нажмите кнопку **Пуск**, наведите указатель на пункт **Все программы**, затем на пункт **Microsoft SQL Server 2012**и выберите пункт **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="75df5-107">If [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools is not already open, click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2012**, and then click **SQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="75df5-108">В меню **Файл** последовательно выберите пункты **Открыть**, **Проект или решение**, **Учебник по службам SSIS** и нажмите кнопку **Открыть**, а затем дважды щелкните файл **SSIS Tutorial.sln**.</span><span class="sxs-lookup"><span data-stu-id="75df5-108">On the **File** menu, click **Open**, click **Project/Solution**, select **SSIS Tutorial** and click **Open**, and then double-click **SSIS Tutorial.sln**.</span></span>  
  
3.  <span data-ttu-id="75df5-109">В обозревателе решений правой кнопкой мыши щелкните **Lesson 4.dtsx**и выберите команду **Копировать**.</span><span class="sxs-lookup"><span data-stu-id="75df5-109">In Solution Explorer, right-click **Lesson 4.dtsx**, and then click **Copy**.</span></span>  
  
4.  <span data-ttu-id="75df5-110">В обозреватель решений щелкните правой кнопкой мыши **пакеты служб SSIS**и выберите команду **Вставить**.</span><span class="sxs-lookup"><span data-stu-id="75df5-110">In Solution Explorer, right-click **SSIS Packages**, and then click **Paste**.</span></span>  
  
     <span data-ttu-id="75df5-111">По умолчанию копируемому пакету присваивается имя Lesson 5.dtsx.</span><span class="sxs-lookup"><span data-stu-id="75df5-111">By default, the copied package is named Lesson 5.dtsx.</span></span>  
  
5.  <span data-ttu-id="75df5-112">Чтобы открыть пакет, в обозревателе решений дважды щелкните **Lesson 5.dtsx** .</span><span class="sxs-lookup"><span data-stu-id="75df5-112">In the Solution Explorer, double-click **Lesson 5.dtsx** to open the package.</span></span>  
  
6.  <span data-ttu-id="75df5-113">Щелкните правой кнопкой мыши в любом месте фона вкладки **поток управления** и выберите пункт **свойства**.</span><span class="sxs-lookup"><span data-stu-id="75df5-113">Right-click anywhere in the background of the **Control Flow** tab then click **Properties**.</span></span>  
  
7.  <span data-ttu-id="75df5-114">В окно свойств измените `Name` свойство на `Lesson 5` .</span><span class="sxs-lookup"><span data-stu-id="75df5-114">In the Properties window, update the `Name` property to `Lesson 5`.</span></span>  
  
8.  <span data-ttu-id="75df5-115">Установите флажок для свойства **ID** , щелкните стрелку раскрывающегося списка, а затем в списке выберите **\<Generate New ID>**.</span><span class="sxs-lookup"><span data-stu-id="75df5-115">Click the box for the **ID** property, then click the dropdown arrow, and then click **\<Generate New ID>**.</span></span>  
  
### <a name="to-add-the-completed-lesson-4-package"></a><span data-ttu-id="75df5-116">Добавление готового пакета занятия 4</span><span class="sxs-lookup"><span data-stu-id="75df5-116">To add the completed Lesson 4 package</span></span>  
  
1.  <span data-ttu-id="75df5-117">Откройте [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools, затем откройте проект «Учебник по службам SSIS».</span><span class="sxs-lookup"><span data-stu-id="75df5-117">Open [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools and open the SSIS Tutorial project.</span></span>  
  
2.  <span data-ttu-id="75df5-118">В обозреватель решений щелкните правой кнопкой мыши **пакеты служб SSIS**и выберите команду **Добавить существующий пакет**.</span><span class="sxs-lookup"><span data-stu-id="75df5-118">In Solution Explorer, right-click **SSIS Packages**, and click **Add Existing Package**.</span></span>  
  
3.  <span data-ttu-id="75df5-119">В диалоговом окне **Добавление копии существующего пакета** в разделе **Расположение пакета**выберите пункт **Файловая система**.</span><span class="sxs-lookup"><span data-stu-id="75df5-119">In the **Add Copy of Existing Package** dialog box, in **Package location**, select **File system**.</span></span>  
  
4.  <span data-ttu-id="75df5-120">Нажмите кнопку обзора **(...)** , перейдите к **занятию 4. dtsx** на компьютере и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="75df5-120">Click the browse **(...)** button, navigate to **Lesson 4.dtsx** on your machine, and then click **Open**.</span></span>  
  
     <span data-ttu-id="75df5-121">Чтобы загрузить все пакеты занятий этого учебника, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="75df5-121">To download all of the lesson packages for this tutorial, do the following.</span></span>  
  
    1.  <span data-ttu-id="75df5-122">Перейдите к [образцам продуктов служб Integration Services](https://go.microsoft.com/fwlink/?LinkId=275027).</span><span class="sxs-lookup"><span data-stu-id="75df5-122">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=275027)</span></span>  
  
    2.  <span data-ttu-id="75df5-123">Перейдите на вкладку **Downloads (загрузки** ).</span><span class="sxs-lookup"><span data-stu-id="75df5-123">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="75df5-124">Щелкните файл SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip.</span><span class="sxs-lookup"><span data-stu-id="75df5-124">Click the SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
5.  <span data-ttu-id="75df5-125">Скопируйте и вставьте пакет занятия 4, как описано в шагах 3–8 предыдущей процедуры.</span><span class="sxs-lookup"><span data-stu-id="75df5-125">Copy and paste the Lesson 4 package as described in steps 3-8 in the previous procedure.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="75df5-126">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="75df5-126">Next Task in Lesson</span></span>  
 [<span data-ttu-id="75df5-127">Шаг 2. Активация и настройка конфигурации пакетов</span><span class="sxs-lookup"><span data-stu-id="75df5-127">Step 2: Enabling and Configuring Package Configurations</span></span>](lesson-5-2-enabling-and-configuring-package-configurations.md)  
  
  
