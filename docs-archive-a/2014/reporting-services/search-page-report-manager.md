---
title: Страница "Поиск" (диспетчер отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 51ffdc07-e1b9-4ed7-acb3-dd98d7cce273
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2528133f5b2ecc4bed4c16fdd476591b3bab52d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664707"
---
# <a name="search-page-report-manager"></a><span data-ttu-id="5e9df-102">Страница «Поиск» (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="5e9df-102">Search Page (Report Manager)</span></span>
  <span data-ttu-id="5e9df-103">На странице «Результаты поиска» можно просмотреть результаты операции поиска, заданной в отчете, моделях отчетов, связанном отчете, общем источнике данных, папке или ресурсе.</span><span class="sxs-lookup"><span data-stu-id="5e9df-103">Use the Search Results page to view the results of a search operation specified for a report, linked report, report model, shared data source, folder, or resource.</span></span> <span data-ttu-id="5e9df-104">Результаты поиска приводятся в списке в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="5e9df-104">Search results are listed alphabetically.</span></span> <span data-ttu-id="5e9df-105">Их можно сортировать по типу, имени или описанию.</span><span class="sxs-lookup"><span data-stu-id="5e9df-105">You can sort by type, name, or description.</span></span>  
  
 <span data-ttu-id="5e9df-106">Следующие элементы исключаются из операции поиска: содержащиеся в журнале отчета моментальные снимки отчетов, подписки и общие расписания.</span><span class="sxs-lookup"><span data-stu-id="5e9df-106">The following items are excluded from a search operation: report snapshots contained in report history, subscriptions, and shared schedules.</span></span> <span data-ttu-id="5e9df-107">Аналогично, недостаточные разрешения на просмотр папки или отчета исключают этот элемент из поиска.</span><span class="sxs-lookup"><span data-stu-id="5e9df-107">Similarly, insufficient permission to view a folder or report excludes that item from a search.</span></span>  
  
 <span data-ttu-id="5e9df-108">Поиск текста в отчете или модели невозможен.</span><span class="sxs-lookup"><span data-stu-id="5e9df-108">You cannot search for text within a report or model.</span></span> <span data-ttu-id="5e9df-109">Для поиска определенного текста в отчете используется панель инструментов, расположенная в верхней части отчета.</span><span class="sxs-lookup"><span data-stu-id="5e9df-109">To search for specific text within a report, use the toolbar at the top of the report.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="5e9df-110">Навигация</span><span class="sxs-lookup"><span data-stu-id="5e9df-110">Navigation</span></span>  
 <span data-ttu-id="5e9df-111">Чтобы перейти к этому местоположению в пользовательском интерфейсе, используйте следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="5e9df-111">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-search-results-page"></a><span data-ttu-id="5e9df-112">Открытие страницы «Результаты поиска»</span><span class="sxs-lookup"><span data-stu-id="5e9df-112">To open the Search Results page</span></span>  
  
1.  <span data-ttu-id="5e9df-113">Откройте диспетчер отчетов.</span><span class="sxs-lookup"><span data-stu-id="5e9df-113">Open Report Manager.</span></span>  
  
2.  <span data-ttu-id="5e9df-114">В верхней части страницы введите критерии поиска в поле **Поиск** .</span><span class="sxs-lookup"><span data-stu-id="5e9df-114">At the top of the page, type your search criteria in the **Search** box.</span></span> <span data-ttu-id="5e9df-115">Затем нажмите клавишу ВВОД или щелкните стрелку «Поиск».</span><span class="sxs-lookup"><span data-stu-id="5e9df-115">Then press Enter or click the Search arrow.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5e9df-116">Варианты</span><span class="sxs-lookup"><span data-stu-id="5e9df-116">Options</span></span>  
 <span data-ttu-id="5e9df-117">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="5e9df-117">**Delete**</span></span>  
 <span data-ttu-id="5e9df-118">Нажмите, чтобы удалить элемент из базы данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="5e9df-118">Click to remove an item from a report server database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5e9df-119">Эта кнопка доступна только в представлении **Просмотр подробностей**.</span><span class="sxs-lookup"><span data-stu-id="5e9df-119">This button is available only in **Details View**.</span></span> <span data-ttu-id="5e9df-120">Однако можно подвести указатель к элементу и воспользоваться меню для доступа к функции удаления в **Просмотр подробностей** или в **Режим списка**.</span><span class="sxs-lookup"><span data-stu-id="5e9df-120">However, you can hover over an item and use the menu to access the delete functionality in either **Details View** or in **List View**.</span></span>  
  
 <span data-ttu-id="5e9df-121">**Перемещение**</span><span class="sxs-lookup"><span data-stu-id="5e9df-121">**Move**</span></span>  
 <span data-ttu-id="5e9df-122">Нажмите, чтобы переместить элемент.</span><span class="sxs-lookup"><span data-stu-id="5e9df-122">Click to relocate an item.</span></span> <span data-ttu-id="5e9df-123">Это приведет к открытию страницы «Перемещение элементов», на которой можно выбрать новое местоположение папки.</span><span class="sxs-lookup"><span data-stu-id="5e9df-123">This opens the Move Items page, where you can select a different folder location.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5e9df-124">Эта кнопка доступна только в представлении **Просмотр подробностей**.</span><span class="sxs-lookup"><span data-stu-id="5e9df-124">This button is available only in **Details View**.</span></span> <span data-ttu-id="5e9df-125">Однако можно подвести указатель к элементу и воспользоваться меню для доступа к функции перемещения в **Просмотр подробностей** или в **Режим списка**.</span><span class="sxs-lookup"><span data-stu-id="5e9df-125">However, you can hover over an item and use the menu to access the move functionality in either **Details View** or in **List View**.</span></span>  
  
 <span data-ttu-id="5e9df-126">Поле поиска</span><span class="sxs-lookup"><span data-stu-id="5e9df-126">Search box</span></span>  
 <span data-ttu-id="5e9df-127">Введите полное имя или его часть для элемента, который нужно найти, а затем нажмите кнопку **Начать** для начала поиска.</span><span class="sxs-lookup"><span data-stu-id="5e9df-127">Type all or part of the name of an item that you want to locate, and then click **Go** to start the search.</span></span> <span data-ttu-id="5e9df-128">Максимальная длина строки поиска составляет 128 символов.</span><span class="sxs-lookup"><span data-stu-id="5e9df-128">The longest string you can search for is 128 characters.</span></span>  
  
 <span data-ttu-id="5e9df-129">Имена или описания элементов, содержащие всю строку поиска в любом месте текстового значения, включаются в результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="5e9df-129">Item names or descriptions that contain the entire search string anywhere in the text value are included in the search results.</span></span>  
  
 <span data-ttu-id="5e9df-130">Такие логические операторы, как сложение (+), не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="5e9df-130">Boolean operators such as the plus character (+) are not supported.</span></span>  
  
 <span data-ttu-id="5e9df-131">**Подробное представление**</span><span class="sxs-lookup"><span data-stu-id="5e9df-131">**Details View**</span></span>  
 <span data-ttu-id="5e9df-132">Нажмите кнопку, чтобы открыть страницу «Результаты поиска» в списке, содержащем дополнительную информацию об элементах, такую как типы и описание элементов, папка, в которой хранятся элементы, и дата последнего запуска элементов.</span><span class="sxs-lookup"><span data-stu-id="5e9df-132">Click to display the Search Results page in a list that contains additional information about items, such as the item type, name, description, the folder in which the item is located, and when it was last run.</span></span> <span data-ttu-id="5e9df-133">В режиме **Просмотр деталей**можно использовать кнопки **Удалить** и **Переместить** , чтобы удалять и изменять местоположение элементов в папке.</span><span class="sxs-lookup"><span data-stu-id="5e9df-133">In **Details View**, you can use **Delete** and **Move** buttons to remove and relocate items in the folder.</span></span>  
  
 <span data-ttu-id="5e9df-134">Подведите курсор к элементу и щелкните стрелку раскрывающегося списка, чтобы открыть раскрывающееся меню, в котором можно получить доступ и настроить свойства выбранного элемента.</span><span class="sxs-lookup"><span data-stu-id="5e9df-134">Hover over an item and click the drop-down arrow to open the drop-down menu from which you can access and configure properties of the selected item.</span></span>  
  
 <span data-ttu-id="5e9df-135">**Представление списка**</span><span class="sxs-lookup"><span data-stu-id="5e9df-135">**List View**</span></span>  
 <span data-ttu-id="5e9df-136">Щелкните, чтобы отобразить страницу «Результаты поиска» без подробной информации, как в **Просмотр подробностей**.</span><span class="sxs-lookup"><span data-stu-id="5e9df-136">Click to display the Search Results page without details as in **Details View**.</span></span> <span data-ttu-id="5e9df-137">При открытии страницы «Результаты поиска» по умолчанию используется «Режим списка».</span><span class="sxs-lookup"><span data-stu-id="5e9df-137">List View is the default view when the Search Results page opens.</span></span>  
  
 <span data-ttu-id="5e9df-138">Подведите курсор к элементу и щелкните стрелку раскрывающегося списка, чтобы открыть раскрывающееся меню, в котором можно получить доступ и настроить свойства выбранного элемента.</span><span class="sxs-lookup"><span data-stu-id="5e9df-138">Hover over an item and click the drop-down arrow to open the drop-down menu from which you can access and configure properties of the selected item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e9df-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="5e9df-139">See Also</span></span>  
 <span data-ttu-id="5e9df-140">[Диспетчер отчетов (службы Reporting Services в основном режиме)](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="5e9df-140">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="5e9df-141">Справка F1 диспетчера отчетов</span><span class="sxs-lookup"><span data-stu-id="5e9df-141">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
