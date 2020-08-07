---
title: Параметры (результаты запроса — SQL Server-результаты на текстовую страницу) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.QueryResults.SqlServer.SQLResultsToText
ms.assetid: 2ccbdf17-e14f-42f1-a836-ca999a3432c9
author: rothja
ms.author: jroth
ms.openlocfilehash: 4ece458e4bab9a57cb6692d4ac6dfdf2e8f4bd22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734402"
---
# <a name="options-query-results-sql-server-results-to-text-page"></a><span data-ttu-id="3f36b-102">Параметры (результаты запроса — SQL Server — результаты на текстовую страницу)</span><span class="sxs-lookup"><span data-stu-id="3f36b-102">Options (Query Results-SQL Server-Results to Text Page)</span></span>
  <span data-ttu-id="3f36b-103">Используйте эту страницу, чтобы задать параметры для представления результирующего набора запроса в текстовом формате.</span><span class="sxs-lookup"><span data-stu-id="3f36b-103">Use this page to specify the options for displaying a query result set in text format.</span></span> <span data-ttu-id="3f36b-104">Изменения этих параметров применяются только к новым запросам [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3f36b-104">Changes to these options are applied only to new [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] queries.</span></span> <span data-ttu-id="3f36b-105">Чтобы изменить параметры для текущих запросов, в меню **запрос** выберите пункт **Параметры запроса** или щелкните правой кнопкой мыши в [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] окне запроса и выберите пункт **Параметры запроса**.</span><span class="sxs-lookup"><span data-stu-id="3f36b-105">To change the options for the current queries, click **Query Options** on the **Query** menu, or right-click in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Query window, and select **Query Options**.</span></span> <span data-ttu-id="3f36b-106">В области **Результаты** диалогового окна **Параметры запроса**нажмите **Текст**.</span><span class="sxs-lookup"><span data-stu-id="3f36b-106">In the **Query Options** dialog box, under **Results**, click **Text**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="3f36b-107">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="3f36b-107">UI element list</span></span>  
 <span data-ttu-id="3f36b-108">**Формат вывода**</span><span class="sxs-lookup"><span data-stu-id="3f36b-108">**Output format**</span></span>  
 <span data-ttu-id="3f36b-109">По умолчанию выходные данные отображаются в столбцах, полученных дополнением результатов пробелами.</span><span class="sxs-lookup"><span data-stu-id="3f36b-109">By default the output is displayed in columns created by padding the results with spaces.</span></span> <span data-ttu-id="3f36b-110">Также для разделения столбцов можно использовать запятые, табуляцию или пробелы.</span><span class="sxs-lookup"><span data-stu-id="3f36b-110">Other options are to use commas, tabs, or spaces to separate columns.</span></span> <span data-ttu-id="3f36b-111">Выберите **Другой** из раскрывающегося списка, чтобы задать другой символ разделителя в текстовом поле **Выберите разделитель**.</span><span class="sxs-lookup"><span data-stu-id="3f36b-111">Select **Custom delimiter** from this drop-down list to specify a different delimiting character in the **Custom delimiter** text box.</span></span>  
  
 <span data-ttu-id="3f36b-112">**Другой**</span><span class="sxs-lookup"><span data-stu-id="3f36b-112">**Custom delimiter**</span></span>  
 <span data-ttu-id="3f36b-113">Задайте символ, которым будут разделяться столбцы.</span><span class="sxs-lookup"><span data-stu-id="3f36b-113">Specify the character of your choice to separate columns.</span></span> <span data-ttu-id="3f36b-114">Это текстовое поле доступно, только если выбран пункт "Пользовательский разделитель" в поле с раскрывающимся списком **Формат вывода**.</span><span class="sxs-lookup"><span data-stu-id="3f36b-114">This text box is available only if you clicked Custom delimiter in the **Output format** drop-down list box.</span></span>  
  
 <span data-ttu-id="3f36b-115">**Включить заголовки столбцов в результирующий набор**</span><span class="sxs-lookup"><span data-stu-id="3f36b-115">**Include column headers in the result set**</span></span>  
 <span data-ttu-id="3f36b-116">Снимите этот флажок, если заголовки столбцов не нужны.</span><span class="sxs-lookup"><span data-stu-id="3f36b-116">Clear this check box if you do not want each column labeled with a column title.</span></span>  
  
 <span data-ttu-id="3f36b-117">**Включение запроса в результирующий набор**</span><span class="sxs-lookup"><span data-stu-id="3f36b-117">**Include the query in the result set**</span></span>  
 <span data-ttu-id="3f36b-118">Установите этот флажок, чтобы вывести текст выполняющегося запроса на панели результатов перед результатами запроса.</span><span class="sxs-lookup"><span data-stu-id="3f36b-118">Select this check box to include the text of the query that is running in the results pane before the results of the query.</span></span>  
  
 <span data-ttu-id="3f36b-119">**Прокрутка по мере получения результатов**</span><span class="sxs-lookup"><span data-stu-id="3f36b-119">**Scroll as results are received**</span></span>  
 <span data-ttu-id="3f36b-120">Установите этот флажок, чтобы сохранить фокус на самых последних возвращаемых записях в конце результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="3f36b-120">Select this check box to keep the display focus on the most recently returned records at the end of the results set.</span></span> <span data-ttu-id="3f36b-121">Снимите этот флажок, чтобы на экране отображалась первая возвращенная строка.</span><span class="sxs-lookup"><span data-stu-id="3f36b-121">Clear this check box to keep the display focus on the first rows received.</span></span>  
  
 <span data-ttu-id="3f36b-122">**Выравнивание результатов по правому краю**</span><span class="sxs-lookup"><span data-stu-id="3f36b-122">**Right align numeric values**</span></span>  
 <span data-ttu-id="3f36b-123">Установите этот флажок, чтобы выровнять числовые значения по правому краю столбца.</span><span class="sxs-lookup"><span data-stu-id="3f36b-123">Select this check box to align numeric values to the right of the column.</span></span> <span data-ttu-id="3f36b-124">Это облегчит просмотр целочисленных значений и цифр с десятичными разрядами.</span><span class="sxs-lookup"><span data-stu-id="3f36b-124">This can make it easier to review numbers with a fixed number of decimal places.</span></span>  
  
 <span data-ttu-id="3f36b-125">**Сбросить результат после выполнения запроса**</span><span class="sxs-lookup"><span data-stu-id="3f36b-125">**Discard result after query executes**</span></span>  
 <span data-ttu-id="3f36b-126">Установите этот флажок, чтобы отбрасывать результаты запроса после их вывода на панели результатов окна запроса.</span><span class="sxs-lookup"><span data-stu-id="3f36b-126">Select this check box to discard the query results after they are displayed in the results pane of the query window.</span></span>  
  
 <span data-ttu-id="3f36b-127">**Отобразить результаты на отдельной вкладке**</span><span class="sxs-lookup"><span data-stu-id="3f36b-127">**Display results in a separate tab**</span></span>  
 <span data-ttu-id="3f36b-128">Установите этот флажок, чтобы вывести результирующий набор в окне нового документа, а не в окне документа запроса.</span><span class="sxs-lookup"><span data-stu-id="3f36b-128">Select this check box to display the result set in a new document window, instead of at the bottom of the query document window.</span></span>  
  
 <span data-ttu-id="3f36b-129">**Открыть вкладку результатов после выполнения запроса**</span><span class="sxs-lookup"><span data-stu-id="3f36b-129">**Switch to results tab after the query executes**</span></span>  
 <span data-ttu-id="3f36b-130">Установите этот флажок, чтобы автоматически задавать фокус на результирующем наборе.</span><span class="sxs-lookup"><span data-stu-id="3f36b-130">Select this check box to automatically set the screen focus to the result set.</span></span>  
  
 <span data-ttu-id="3f36b-131">**Максимальное число символов в каждом столбце**</span><span class="sxs-lookup"><span data-stu-id="3f36b-131">**Maximum number of characters displayed in each column**</span></span>  
 <span data-ttu-id="3f36b-132">По умолчанию это значение равно 256.</span><span class="sxs-lookup"><span data-stu-id="3f36b-132">This value defaults to 256.</span></span> <span data-ttu-id="3f36b-133">Увеличьте это значение для вывода результирующих наборов большего размера без усечения.</span><span class="sxs-lookup"><span data-stu-id="3f36b-133">Increase this value to display larger result sets without truncation.</span></span> <span data-ttu-id="3f36b-134">Максимальное значение равно 8192.</span><span class="sxs-lookup"><span data-stu-id="3f36b-134">The maximum value is 8,192.</span></span>  
  
 <span data-ttu-id="3f36b-135">**По умолчанию**</span><span class="sxs-lookup"><span data-stu-id="3f36b-135">**Reset to Default**</span></span>  
 <span data-ttu-id="3f36b-136">Позволяет вернуть исходные значения по умолчанию для всех параметров на данной странице.</span><span class="sxs-lookup"><span data-stu-id="3f36b-136">Resets all values on this page to the original default values.</span></span>  
  
  
