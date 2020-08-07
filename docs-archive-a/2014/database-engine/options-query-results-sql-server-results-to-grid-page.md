---
title: Параметры (результаты запроса — страница «SQL Server-Results to Grid») | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.QueryResults.SqlServer.SQLResultsToGrid
ms.assetid: f88a0f5c-e800-473b-ae23-c3943de5ed63
author: rothja
ms.author: jroth
ms.openlocfilehash: 3f9cec7e544c295420a9ae2a25e96ea9aa82030b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734406"
---
# <a name="options-query-results-sql-server-results-to-grid-page"></a><span data-ttu-id="e918b-102">Параметры (результаты запроса — страница «SQL Server-Results to Grid»)</span><span class="sxs-lookup"><span data-stu-id="e918b-102">Options (Query Results-SQL Server-Results to Grid Page)</span></span>
  <span data-ttu-id="e918b-103">Используйте эту страницу, чтобы указать параметры отображения результирующего набора запроса в формате сетки.</span><span class="sxs-lookup"><span data-stu-id="e918b-103">Use this page to specify the options for displaying a query result set in grid format.</span></span> <span data-ttu-id="e918b-104">Изменения этих параметров применяются только к новым запросам [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e918b-104">Changes to these options are applied only to new [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] queries.</span></span> <span data-ttu-id="e918b-105">Чтобы изменить параметры для текущих запросов, в меню **запрос** выберите пункт **Параметры запроса** или щелкните правой кнопкой мыши в [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] окне запроса и выберите пункт **Параметры запроса**.</span><span class="sxs-lookup"><span data-stu-id="e918b-105">To change the options for the current queries, click **Query Options** on the **Query** menu, or right-click in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Query window and select **Query Options**.</span></span> <span data-ttu-id="e918b-106">На левой панели диалогового окна **Параметры запроса** в списке **Результаты**выберите пункт **Сетка**.</span><span class="sxs-lookup"><span data-stu-id="e918b-106">In the left pane of the **Query Options** dialog box, under **Results**, click **Grid**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="e918b-107">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="e918b-107">UI element list</span></span>  
 <span data-ttu-id="e918b-108">**Включение запроса в результирующий набор**</span><span class="sxs-lookup"><span data-stu-id="e918b-108">**Include the query in the result set**</span></span>  
 <span data-ttu-id="e918b-109">Возвращает текст запроса как часть вывода запроса.</span><span class="sxs-lookup"><span data-stu-id="e918b-109">Returns the text of the query as part of the query output.</span></span>  
  
 <span data-ttu-id="e918b-110">**Включать заголовки столбцов при копировании или сохранении результатов**</span><span class="sxs-lookup"><span data-stu-id="e918b-110">**Include column headers when copying or saving the results**</span></span>  
 <span data-ttu-id="e918b-111">Выберите этот флажок, чтобы включить заголовки столбца при копировании результатов в буфер обмена или сохранении в файл.</span><span class="sxs-lookup"><span data-stu-id="e918b-111">Select this check box to include column headers when results are copied to the clipboard, or saved in a file.</span></span> <span data-ttu-id="e918b-112">Снимите этот флажок, если нужно, чтобы сохраненные или скопированные данные результатов состояли только из данных без заголовков столбцов.</span><span class="sxs-lookup"><span data-stu-id="e918b-112">Clear this check box if you want saved or copied result data to have only the data and not the column headings.</span></span>  
  
 <span data-ttu-id="e918b-113">**Сбросить результаты после выполнения**</span><span class="sxs-lookup"><span data-stu-id="e918b-113">**Discard results after execution**</span></span>  
 <span data-ttu-id="e918b-114">Препятствует отображению результатов запроса на просматриваемой панели.</span><span class="sxs-lookup"><span data-stu-id="e918b-114">Prevents query results from being displayed in the reviewing pane.</span></span> <span data-ttu-id="e918b-115">Результаты отклоняются сразу после завершения.</span><span class="sxs-lookup"><span data-stu-id="e918b-115">The results are discarded immediately after execution.</span></span> <span data-ttu-id="e918b-116">Использование этого параметра позволяет сэкономить память.</span><span class="sxs-lookup"><span data-stu-id="e918b-116">Specifying this option helps save memory.</span></span>  
  
 <span data-ttu-id="e918b-117">**Отобразить результаты на отдельной вкладке**</span><span class="sxs-lookup"><span data-stu-id="e918b-117">**Display results in a separate tab**</span></span>  
 <span data-ttu-id="e918b-118">Установить этот флажок, чтобы вывести результирующий набор в новой вкладке, а не в окне документа запроса.</span><span class="sxs-lookup"><span data-stu-id="e918b-118">Select this check box to display the result set in a new tab, instead of at the bottom of the query document window.</span></span>  
  
 <span data-ttu-id="e918b-119">**Открыть вкладку результатов после выполнения запроса**</span><span class="sxs-lookup"><span data-stu-id="e918b-119">**Switch to results tab after the query executes**</span></span>  
 <span data-ttu-id="e918b-120">Нажмите для автоматической установки экранного фокуса на панели результатов после исполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="e918b-120">Click to automatically set the screen focus to the results pane upon execution of a query.</span></span>  
  
 <span data-ttu-id="e918b-121">**Максимальное число полученных символов**</span><span class="sxs-lookup"><span data-stu-id="e918b-121">**Maximum Characters Retrieved**</span></span>  
 <span data-ttu-id="e918b-122">**Данные не в формате XML**:</span><span class="sxs-lookup"><span data-stu-id="e918b-122">**Non XML data**:</span></span>  
  
 <span data-ttu-id="e918b-123">Введите число от 1 до 65 535, чтобы указать максимальное число символов, отображаемых в каждой ячейке.</span><span class="sxs-lookup"><span data-stu-id="e918b-123">Enter a number from 1 through 65535 to specify the maximum number of characters that will be displayed in each cell.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e918b-124">Указание слишком большого числа символов может привести к тому, что результирующий набор будет отображаться усеченным.</span><span class="sxs-lookup"><span data-stu-id="e918b-124">Specifying a large number of characters may cause data in the result set to appear truncated.</span></span> <span data-ttu-id="e918b-125">Максимальное число символов, отображаемых в каждой ячейке, зависит от размера шрифта.</span><span class="sxs-lookup"><span data-stu-id="e918b-125">The maximum number of characters displayed in each cell is dependent on the font size.</span></span> <span data-ttu-id="e918b-126">Высокое значение в этом окне может привести к нехватке памяти для среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] и снижению производительности системы при возвращении больших результирующих наборов.</span><span class="sxs-lookup"><span data-stu-id="e918b-126">When large result sets are returned, a high value in this box can cause [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to run low on memory and hinder system performance.</span></span>  
  
 <span data-ttu-id="e918b-127">**XML-данные**:</span><span class="sxs-lookup"><span data-stu-id="e918b-127">**XML data**:</span></span>  
  
 <span data-ttu-id="e918b-128">Выберите **1 МБ**, **2 МБ**или **5 МБ**.</span><span class="sxs-lookup"><span data-stu-id="e918b-128">Select **1 MB**, **2 MB**, or **5 MB**.</span></span> <span data-ttu-id="e918b-129">Выберите пункт **Без ограничений** , чтобы вывести все символы.</span><span class="sxs-lookup"><span data-stu-id="e918b-129">Select **Unlimited** to retrieve all characters.</span></span>  
  
 <span data-ttu-id="e918b-130">**По умолчанию**</span><span class="sxs-lookup"><span data-stu-id="e918b-130">**Reset to Default**</span></span>  
 <span data-ttu-id="e918b-131">Позволяет вернуть исходные значения по умолчанию для всех параметров на данной странице.</span><span class="sxs-lookup"><span data-stu-id="e918b-131">Resets all values on this page to the original default values.</span></span>  
  
  
