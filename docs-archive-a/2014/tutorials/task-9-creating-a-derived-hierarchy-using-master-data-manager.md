---
title: Задача 9. создание производной иерархии с помощью диспетчер основных данных | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 3bd2ec05-933f-4947-b1fe-c9226961eb7d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 5c85750e4556722c6e6a5edbccb4a3c82c119a74
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751576"
---
# <a name="task-9-creating-a-derived-hierarchy-using-master-data-manager"></a><span data-ttu-id="66632-102">Задача 9. Создание производной иерархии с помощью диспетчера основных данных</span><span class="sxs-lookup"><span data-stu-id="66632-102">Task 9: Creating a Derived Hierarchy using Master Data Manager</span></span>
  <span data-ttu-id="66632-103">В этой задаче вы создадите производную иерархию с помощью диспетчера основных данных.</span><span class="sxs-lookup"><span data-stu-id="66632-103">In this task, you create a derived hierarchy by using Master Data Manager.</span></span> <span data-ttu-id="66632-104">Эта производная иерархия является производной от отношений атрибутов на основе домена между сущностями **поставщика** и **состояния** .</span><span class="sxs-lookup"><span data-stu-id="66632-104">This derived hierarchy is derived from the domain-based attribute relationships between the **Supplier** and **State** entities.</span></span>  
  
1.  <span data-ttu-id="66632-105">Перейдите на главную страницу **Диспетчер основных данных** , щелкнув **SQL Server 2012 Master Data Services** в верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="66632-105">Switch to the main page of **Master Data Manager** by clicking **SQL Server 2012 Master Data Services** at the top of the page.</span></span>  
  
2.  <span data-ttu-id="66632-106">В разделе **задачи администрирования** щелкните **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="66632-106">Click **System Administration** in the **Administrative Tasks** section.</span></span>  
  
3.  <span data-ttu-id="66632-107">Наведите указатель мыши на **Управление** в строке меню и выберите пункт **производные иерархии**.</span><span class="sxs-lookup"><span data-stu-id="66632-107">Hover the mouse over **Manage** on the menu bar, and click **Derived Hierarchies**.</span></span>  
  
     <span data-ttu-id="66632-108">![Меню управления — выбрана производная иерархия](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-01.jpg "Меню управления — выбрана производная иерархия")</span><span class="sxs-lookup"><span data-stu-id="66632-108">![Manage Menu - Derived Hierarchies Selected](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-01.jpg "Manage Menu - Derived Hierarchies Selected")</span></span>  
  
4.  <span data-ttu-id="66632-109">Нажмите кнопку **Добавить производную иерархию (+)** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="66632-109">Click **Add Derived Hierarchy (+)** button on the toolbar.</span></span>  
  
     <span data-ttu-id="66632-110">![Кнопка «Добавить производную иерархию»](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-02.jpg "Кнопка «Добавить производную иерархию»")</span><span class="sxs-lookup"><span data-stu-id="66632-110">![Add Derived Hierarchy Button](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-02.jpg "Add Derived Hierarchy Button")</span></span>  
  
5.  <span data-ttu-id="66632-111">Введите **SuppliersInState** в качестве **имени производной иерархии**.</span><span class="sxs-lookup"><span data-stu-id="66632-111">Type **SuppliersInState** for the **Derived hierarchy name**.</span></span>  
  
6.  <span data-ttu-id="66632-112">Нажмите кнопку **сохранить** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="66632-112">Click **Save** button on the toolbar.</span></span>  
  
     <span data-ttu-id="66632-113">![Кнопка «Сохранить производную иерархию»](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-03.jpg "Кнопка «Сохранить производную иерархию»")</span><span class="sxs-lookup"><span data-stu-id="66632-113">![Save Derived Hierarchy Button](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-03.jpg "Save Derived Hierarchy Button")</span></span>  
  
7.  <span data-ttu-id="66632-114">Перетащите **поставщик** из **доступных уровней: SuppliersInState** на **текущие уровни: SuppliersInState**.</span><span class="sxs-lookup"><span data-stu-id="66632-114">Drag **Supplier** from **Available Levels: SuppliersInState** to **Current Levels: SuppliersInState**.</span></span>  
  
     <span data-ttu-id="66632-115">![Доступные сущности и иерархии для текущего уровня](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-04.jpg "Доступные сущности и иерархии для текущего уровня")</span><span class="sxs-lookup"><span data-stu-id="66632-115">![Avialble Entities and Hierarchies to Current Level](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-04.jpg "Avialble Entities and Hierarchies to Current Level")</span></span>  
  
8.  <span data-ttu-id="66632-116">Перетащите **состояние** из **доступных уровней: SuppliersInState** на **текущие уровни: SuppliersInState**.</span><span class="sxs-lookup"><span data-stu-id="66632-116">Drag **State** from **Available Levels: SuppliersInState** to **Current Levels: SuppliersInState**.</span></span> <span data-ttu-id="66632-117">На экране должны быть **текущие уровни** , как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="66632-117">The screen should have **Current Levels** as shown in the following picture.</span></span>  
  
     <span data-ttu-id="66632-118">![Текущие уровни и предварительный просмотр производной иерархии](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-05.jpg "Текущие уровни и предварительный просмотр производной иерархии")</span><span class="sxs-lookup"><span data-stu-id="66632-118">![Current Levels and Preview of Derived Hierarchy](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-05.jpg "Current Levels and Preview of Derived Hierarchy")</span></span>  
  
9. <span data-ttu-id="66632-119">В окне **предварительного просмотра** разверните узел **Нью {Нью Йорк}** , и в этом состоянии вы должны увидеть одного поставщика, как показано на предыдущем рисунке.</span><span class="sxs-lookup"><span data-stu-id="66632-119">In the **Preview** window, expand **NY { New York}** and you should see one supplier in that state as shown in the preceding image.</span></span>  
  
10. <span data-ttu-id="66632-120">Перейдите на главную страницу **Диспетчер основных данных** , щелкнув **SQL Server 2012 Master Data Services** в верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="66632-120">Switch to the main page of **Master Data Manager** by clicking **SQL Server 2012 Master Data Services** at the top of the page.</span></span>  
  
11. <span data-ttu-id="66632-121">Нажмите кнопку **Браузер**.</span><span class="sxs-lookup"><span data-stu-id="66632-121">Click **Explorer**.</span></span>  
  
12. <span data-ttu-id="66632-122">Наведите указатель мыши на **иерархии** и выберите **производный: SuppliersInState**.</span><span class="sxs-lookup"><span data-stu-id="66632-122">Hover the mouse over **Hierarchies** and click **Derived:SuppliersInState**.</span></span>  
  
     <span data-ttu-id="66632-123">![Иерархии — меню Derived:SuppliersInState](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-06.jpg "Иерархии — меню Derived:SuppliersInState")</span><span class="sxs-lookup"><span data-stu-id="66632-123">![Hierarchies - Derived:SuppliersInState Menu](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-06.jpg "Hierarchies - Derived:SuppliersInState Menu")</span></span>  
  
13. <span data-ttu-id="66632-124">Щелкните любой узел **состояния** в представлении в **виде дерева** , и вы увидите поставщиков в этом состоянии на правой панели.</span><span class="sxs-lookup"><span data-stu-id="66632-124">Click on any **state** node in the **tree view** and you should see the suppliers in that state in the right pane.</span></span>  
  
     <span data-ttu-id="66632-125">![Производная иерархия в обозревателе](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-07.jpg "Производная иерархия в обозревателе")</span><span class="sxs-lookup"><span data-stu-id="66632-125">![Derived Hierarchy in Explorer](../../2014/tutorials/media/et-creatingaderivedhierarchyusingmdm-07.jpg "Derived Hierarchy in Explorer")</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="66632-126">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="66632-126">Next Step</span></span>  
 [<span data-ttu-id="66632-127">Занятие 5.: Автоматизация очистки и сопоставления с помощью SSIS</span><span class="sxs-lookup"><span data-stu-id="66632-127">Lesson 5: Automating the Cleansing and Matching using SSIS</span></span>](../../2014/tutorials/lesson-5-automating-the-cleansing-and-matching-using-ssis.md)  
  
  
