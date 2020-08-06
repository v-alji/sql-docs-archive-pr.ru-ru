---
title: Занятие 8. Определение действий | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 15459396-83c9-48a0-b10a-99ae38768c79
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4d4daaed3f1992478b309529fc15e2e903a27920
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737166"
---
# <a name="lesson-8-defining-actions"></a><span data-ttu-id="08a22-102">Урок 8. Определение действий</span><span class="sxs-lookup"><span data-stu-id="08a22-102">Lesson 8: Defining Actions</span></span>
  <span data-ttu-id="08a22-103">На этом занятии определяются действия в проекте служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="08a22-103">In this lesson, you will learn to define actions in your [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="08a22-104">Действие представляет собой инструкцию многомерных выражений, хранимую в службах [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , которая может быть включена в клиентские приложения и выполнена пользователем.</span><span class="sxs-lookup"><span data-stu-id="08a22-104">An action is just a Multidimensional Expressions (MDX) statement that is stored in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and which can be incorporated into client applications and started by a user.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="08a22-105">Завершенные проекты для всех занятий в этом учебнике доступны через Интернет.</span><span class="sxs-lookup"><span data-stu-id="08a22-105">Completed projects for all of the lessons in this tutorial are available online.</span></span> <span data-ttu-id="08a22-106">Можно перейти вперед к любому занятию, используя в качестве отправной точки завершенный проект из предыдущего урока.</span><span class="sxs-lookup"><span data-stu-id="08a22-106">You can jump ahead to any lesson by using the completed project from the previous lesson as a starting point.</span></span> <span data-ttu-id="08a22-107">[Щелкните здесь](https://go.microsoft.com/fwlink/?LinkID=221866) для загрузки образцов проектов, прилагаемых к этому учебнику.</span><span class="sxs-lookup"><span data-stu-id="08a22-107">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to download the sample projects that go with this tutorial.</span></span>  
  
 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] <span data-ttu-id="08a22-108">поддерживают типы операций, описанные в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="08a22-108">supports the types of actions that are described in the following table.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="08a22-109">Командная строка</span><span class="sxs-lookup"><span data-stu-id="08a22-109">CommandLine</span></span>|<span data-ttu-id="08a22-110">Выполняет команду в командной строке</span><span class="sxs-lookup"><span data-stu-id="08a22-110">Executes a command at the command prompt</span></span>|  
|<span data-ttu-id="08a22-111">Набор данных</span><span class="sxs-lookup"><span data-stu-id="08a22-111">Dataset</span></span>|<span data-ttu-id="08a22-112">Возвращает клиентскому приложению набор данных.</span><span class="sxs-lookup"><span data-stu-id="08a22-112">Returns a dataset to a client application.</span></span>|  
|<span data-ttu-id="08a22-113">Детализация</span><span class="sxs-lookup"><span data-stu-id="08a22-113">Drillthrough</span></span>|<span data-ttu-id="08a22-114">Возвращает инструкцию детализации в качестве выражения, которое клиент выполняет, чтобы вернуть набор строк</span><span class="sxs-lookup"><span data-stu-id="08a22-114">Returns a drillthrough statement as an expression, which the client executes to return a rowset</span></span>|  
|<span data-ttu-id="08a22-115">Html</span><span class="sxs-lookup"><span data-stu-id="08a22-115">Html</span></span>|<span data-ttu-id="08a22-116">Выполняет HTML-скрипт в браузере Интернета.</span><span class="sxs-lookup"><span data-stu-id="08a22-116">Executes an HTML script in an Internet browser</span></span>|  
|<span data-ttu-id="08a22-117">Частный</span><span class="sxs-lookup"><span data-stu-id="08a22-117">Proprietary</span></span>|<span data-ttu-id="08a22-118">Выполняет операцию с использованием интерфейса, отличного от приведенных в данной таблице.</span><span class="sxs-lookup"><span data-stu-id="08a22-118">Performs an operation by using an interface other than those listed in this table.</span></span>|  
|<span data-ttu-id="08a22-119">Отчет</span><span class="sxs-lookup"><span data-stu-id="08a22-119">Report</span></span>|<span data-ttu-id="08a22-120">Направляет серверу отчетов параметризованный запрос на основе URL-адресов и возвращает клиентскому приложению отчет.</span><span class="sxs-lookup"><span data-stu-id="08a22-120">Submits a parameterized URL-based request to a report server and returns a report to a client application.</span></span>|  
|<span data-ttu-id="08a22-121">Набор строк</span><span class="sxs-lookup"><span data-stu-id="08a22-121">Rowset</span></span>|<span data-ttu-id="08a22-122">Возвращает клиентскому приложению набор строк.</span><span class="sxs-lookup"><span data-stu-id="08a22-122">Returns a rowset to a client application.</span></span>|  
|<span data-ttu-id="08a22-123">Оператор</span><span class="sxs-lookup"><span data-stu-id="08a22-123">Statement</span></span>|<span data-ttu-id="08a22-124">Выполняет команду OLE DB.</span><span class="sxs-lookup"><span data-stu-id="08a22-124">Runs an OLE DB command.</span></span>|  
|<span data-ttu-id="08a22-125">URL-адрес</span><span class="sxs-lookup"><span data-stu-id="08a22-125">URL</span></span>|<span data-ttu-id="08a22-126">Отображает динамическую веб-страницу в браузереБраузер Интернета.</span><span class="sxs-lookup"><span data-stu-id="08a22-126">Displays a dynamic Web page in an Internet browser.</span></span>|  
  
 <span data-ttu-id="08a22-127">Действия позволяют пользователям запускать приложение или выполнять другие шаги в контексте выбранного элемента.</span><span class="sxs-lookup"><span data-stu-id="08a22-127">Actions let users start an application or perform other steps within the context of a selected item.</span></span> <span data-ttu-id="08a22-128">Дополнительные сведения см. в разделе [Действия (службы Analysis Services — многомерные данные)](multidimensional-models/actions-analysis-services-multidimensional-data.md), [Действия в многомерных моделях](multidimensional-models/actions-in-multidimensional-models.md)</span><span class="sxs-lookup"><span data-stu-id="08a22-128">For more information, see [Actions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md), [Actions in Multidimensional Models](multidimensional-models/actions-in-multidimensional-models.md)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="08a22-129">Примеры действий см. на вкладке «Шаблоны» на панели «Средства вычисления» и в примерах, содержащихся в образце хранилища данных [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW.</span><span class="sxs-lookup"><span data-stu-id="08a22-129">For examples of actions, see the action examples on the Templates tab in the Calculation Tools pane or in the examples in the [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW sample data warehouse.</span></span> <span data-ttu-id="08a22-130">Дополнительные сведения об установке этой базы данных см. в разделе [Установка образцов данных и проектов для учебника по многомерному моделированию в службах Analysis Services](install-sample-data-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="08a22-130">For more information about installing this database, see [Install Sample Data and Projects for the Analysis Services Multidimensional Modeling Tutorial](install-sample-data-and-projects.md).</span></span>  
  
 <span data-ttu-id="08a22-131">Это занятие содержит следующую задачу:</span><span class="sxs-lookup"><span data-stu-id="08a22-131">This lesson includes the following task:</span></span>  
  
 [<span data-ttu-id="08a22-132">Определение и использование действия детализации</span><span class="sxs-lookup"><span data-stu-id="08a22-132">Defining and Using a Drillthrough Action</span></span>](lesson-8-1-defining-and-using-a-drillthrough-action.md)  
 <span data-ttu-id="08a22-133">В этой задаче предстоит создать, использовать и затем изменить действие детализации связи измерений фактов, определенного ранее в этом учебнике.</span><span class="sxs-lookup"><span data-stu-id="08a22-133">In this task, you define, use, and then modify a drillthrough action through the fact dimension relationship that you defined earlier in this tutorial.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="08a22-134">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="08a22-134">Next Lesson</span></span>  
 [<span data-ttu-id="08a22-135">Урок 9. Определение перспектив и преобразований</span><span class="sxs-lookup"><span data-stu-id="08a22-135">Lesson 9: Defining Perspectives and Translations</span></span>](lesson-9-defining-perspectives-and-translations.md)  
  
## <a name="see-also"></a><span data-ttu-id="08a22-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="08a22-136">See Also</span></span>  
 <span data-ttu-id="08a22-137">[Analysis Services сценарий учебника](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="08a22-137">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 <span data-ttu-id="08a22-138">[&#40;учебника по Adventure Works в многомерном моделировании&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="08a22-138">[Multidimensional Modeling &#40;Adventure Works Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span></span>  
 <span data-ttu-id="08a22-139">[Действия &#40;Analysis Services многомерных данных&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="08a22-139">[Actions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="08a22-140">Действия в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="08a22-140">Actions in Multidimensional Models</span></span>](multidimensional-models/actions-in-multidimensional-models.md)  
  
  
