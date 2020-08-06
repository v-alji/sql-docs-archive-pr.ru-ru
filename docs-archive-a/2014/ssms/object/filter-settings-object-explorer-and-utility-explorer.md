---
title: Настройки фильтра (обозреватель объектов и проводник служебной программы) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.filtersettings.f1
- sql12.swb.common.filtersettings.f1
ms.assetid: 4aab04bc-e1ab-4d4b-ab74-b287fc805bc2
author: stevestein
ms.author: sstein
ms.openlocfilehash: c31fbcbef9cbab86a7bd3ab7b2fae21e626aaa59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654015"
---
# <a name="filter-settings-object-explorer-and-utility-explorer"></a><span data-ttu-id="75876-102">Настройки фильтра (обозреватель объектов и обозреватель программ)</span><span class="sxs-lookup"><span data-stu-id="75876-102">Filter Settings (Object Explorer and Utility Explorer)</span></span>
  <span data-ttu-id="75876-103">Используйте данное диалоговое окно для задания фильтра.</span><span class="sxs-lookup"><span data-stu-id="75876-103">Use this dialog box to specify a filter.</span></span> <span data-ttu-id="75876-104">Фильтр позволяет настроить обозреватель объектов и проводник служебной программы для отображения только тех элементов, которые соответствуют заданным критериям.</span><span class="sxs-lookup"><span data-stu-id="75876-104">A filter allows you to configure Object Explorer and Utility Explorer to display only items that meet specific criteria.</span></span> <span data-ttu-id="75876-105">Например, фильтр можно использовать для отображения только тех заданий, имена которых содержат слово «Maintenance».</span><span class="sxs-lookup"><span data-stu-id="75876-105">For example, you can use a filter to show only jobs with names that contain the word "Maintenance."</span></span> <span data-ttu-id="75876-106">В заголовке диалогового окна **Настройки фильтра** содержится имя сервера и может содержаться имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="75876-106">The header for the **Filter Settings** dialog box contains the name of the server, and it may contain the name of the database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="75876-107">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="75876-107">UI element list</span></span>  
 <span data-ttu-id="75876-108">**Свойство**</span><span class="sxs-lookup"><span data-stu-id="75876-108">**Property**</span></span>  
 <span data-ttu-id="75876-109">Позволяет отобразить свойство включения фильтра.</span><span class="sxs-lookup"><span data-stu-id="75876-109">Displays the property to filter on.</span></span>  
  
 <span data-ttu-id="75876-110">**Оператор**</span><span class="sxs-lookup"><span data-stu-id="75876-110">**Operator**</span></span>  
 <span data-ttu-id="75876-111">Выберите, как фильтр применяет значение к свойству.</span><span class="sxs-lookup"><span data-stu-id="75876-111">Select the way that the filter applies the value to the property.</span></span> <span data-ttu-id="75876-112">Доступны четыре варианта:</span><span class="sxs-lookup"><span data-stu-id="75876-112">There are the following options:</span></span>  
  
-   <span data-ttu-id="75876-113">**Равно**</span><span class="sxs-lookup"><span data-stu-id="75876-113">**Equals**</span></span>  
  
     <span data-ttu-id="75876-114">Отображаются элементы, если точно соответствуют их свойства и значения.</span><span class="sxs-lookup"><span data-stu-id="75876-114">The filter shows items where the property and the value are an exact match.</span></span>  
  
-   <span data-ttu-id="75876-115">**Содержит**</span><span class="sxs-lookup"><span data-stu-id="75876-115">**Contains**</span></span>  
  
     <span data-ttu-id="75876-116">Отображаются элементы, свойство которых содержит значение.</span><span class="sxs-lookup"><span data-stu-id="75876-116">The filter shows items where the property contains the value.</span></span> <span data-ttu-id="75876-117">Свойство может содержать другой текст.</span><span class="sxs-lookup"><span data-stu-id="75876-117">The property may contain other text.</span></span>  
  
-   <span data-ttu-id="75876-118">**Не содержит**</span><span class="sxs-lookup"><span data-stu-id="75876-118">**Does not contain**</span></span>  
  
     <span data-ttu-id="75876-119">Отображаются элементы, свойство которых не содержит значение.</span><span class="sxs-lookup"><span data-stu-id="75876-119">The filter shows items that where the property does not contain the value.</span></span>  
  
-   <span data-ttu-id="75876-120">**Меньше чем**</span><span class="sxs-lookup"><span data-stu-id="75876-120">**Less than**</span></span>  
  
     <span data-ttu-id="75876-121">Доступно для дат. Отображаются элементы, дата которых меньше заданного значения.</span><span class="sxs-lookup"><span data-stu-id="75876-121">Available for dates, this filter shows items whose date is before the value provided.</span></span>  
  
-   <span data-ttu-id="75876-122">**Меньше или равно**</span><span class="sxs-lookup"><span data-stu-id="75876-122">**Less than or equal**</span></span>  
  
     <span data-ttu-id="75876-123">Доступно для дат. Отображаются элементы, дата которых меньше или равна заданному значению.</span><span class="sxs-lookup"><span data-stu-id="75876-123">Available for dates, this filter shows items whose date contains or is before the value provided.</span></span>  
  
-   <span data-ttu-id="75876-124">**Больше чем**</span><span class="sxs-lookup"><span data-stu-id="75876-124">**Greater than**</span></span>  
  
     <span data-ttu-id="75876-125">Доступно для дат. Отображаются элементы, дата которых больше заданного значения.</span><span class="sxs-lookup"><span data-stu-id="75876-125">Available for dates, this filter shows items whose date is after the value provided.</span></span>  
  
-   <span data-ttu-id="75876-126">**Больше или равно**</span><span class="sxs-lookup"><span data-stu-id="75876-126">**Greater than or equal**</span></span>  
  
     <span data-ttu-id="75876-127">Доступно для дат. Отображаются элементы, дата которых больше или равна заданному значению.</span><span class="sxs-lookup"><span data-stu-id="75876-127">Available for dates, this filter shows items whose date contains or is after the value provided.</span></span>  
  
-   <span data-ttu-id="75876-128">**Между**</span><span class="sxs-lookup"><span data-stu-id="75876-128">**Between**</span></span>  
  
     <span data-ttu-id="75876-129">Доступно для дат. Отображаются элементы, дата которых находится между заданными датами.</span><span class="sxs-lookup"><span data-stu-id="75876-129">Available for dates, this filter shows items whose date is between two dates provided.</span></span> <span data-ttu-id="75876-130">Выберите **Между** и нажмите клавишу TAB, чтобы добавить строку ввода второй даты.</span><span class="sxs-lookup"><span data-stu-id="75876-130">Select **Between** and press TAB to add another row allowing entry of the second date.</span></span>  
  
-   <span data-ttu-id="75876-131">**Вне**</span><span class="sxs-lookup"><span data-stu-id="75876-131">**Not between**</span></span>  
  
     <span data-ttu-id="75876-132">Доступно для дат. Отображаются элементы, дата которых не входит в диапазон двух заданных дат.</span><span class="sxs-lookup"><span data-stu-id="75876-132">Available for dates, this filter shows items whose date is before or after two dates provided.</span></span> <span data-ttu-id="75876-133">Выберите **Вне** и в последней ячейке столбца **Оператор** нажмите клавишу TAB, чтобы добавить строку ввода второй даты.</span><span class="sxs-lookup"><span data-stu-id="75876-133">Select **Not Between** and tab out of the **Operator** column to add another row allowing entry of the second date.</span></span>  
  
 <span data-ttu-id="75876-134">**Value**</span><span class="sxs-lookup"><span data-stu-id="75876-134">**Value**</span></span>  
 <span data-ttu-id="75876-135">Введите значение, на основе которого будет сравниваться свойство.</span><span class="sxs-lookup"><span data-stu-id="75876-135">Type the value to compare to the property.</span></span> <span data-ttu-id="75876-136">Для дат нажмите кнопку со стрелкой вниз, чтобы открыть календарь, и выберите в нем дату.</span><span class="sxs-lookup"><span data-stu-id="75876-136">For dates, click the down arrow to show a calendar for selecting the date.</span></span>  
  
 <span data-ttu-id="75876-137">**Очистить фильтр**</span><span class="sxs-lookup"><span data-stu-id="75876-137">**Clear Filter**</span></span>  
 <span data-ttu-id="75876-138">Позволяет удалить все настройки текущего фильтра.</span><span class="sxs-lookup"><span data-stu-id="75876-138">Removes all current filter settings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75876-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="75876-139">See Also</span></span>  
 <span data-ttu-id="75876-140">[Использование SQL Server Management Studio](../sql-server-management-studio-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="75876-140">[Use SQL Server Management Studio](../sql-server-management-studio-ssms.md) </span></span>  
 [<span data-ttu-id="75876-141">Функции и задачи служебной программы SQL Server</span><span class="sxs-lookup"><span data-stu-id="75876-141">SQL Server Utility Features and Tasks</span></span>](../../relational-databases/manage/sql-server-utility-features-and-tasks.md)  
  
  
