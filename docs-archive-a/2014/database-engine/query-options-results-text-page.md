---
title: Результаты параметров запроса (страница "текст") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.query.text.f1
ms.assetid: fd2fb409-58f9-4ede-8349-ce007126b68d
author: rothja
ms.author: jroth
ms.openlocfilehash: 45019450c8fc959b440aac5bf1e9098e59cecefc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667381"
---
# <a name="query-options-results-text-page"></a><span data-ttu-id="8c45f-102">Результирующие параметры запроса (страница «Текст»)</span><span class="sxs-lookup"><span data-stu-id="8c45f-102">Query Options Results (Text Page)</span></span>
  <span data-ttu-id="8c45f-103">Используйте эту страницу, чтобы задать параметры для представления результирующего набора запроса в текстовом формате.</span><span class="sxs-lookup"><span data-stu-id="8c45f-103">Use this page to specify the options for displaying a query result set in text format.</span></span> <span data-ttu-id="8c45f-104">Параметры на этой странице применяются также при выборе параметра **Сохранить результаты в файл** .</span><span class="sxs-lookup"><span data-stu-id="8c45f-104">The settings on this page also apply when **Results to File** is selected.</span></span>  
  
 <span data-ttu-id="8c45f-105">**Формат вывода**</span><span class="sxs-lookup"><span data-stu-id="8c45f-105">**Output format**</span></span>  
 <span data-ttu-id="8c45f-106">По умолчанию выходные данные отображаются в столбцах, полученных дополнением результатов пробелами.</span><span class="sxs-lookup"><span data-stu-id="8c45f-106">By default the output is displayed in columns created by padding the results with spaces.</span></span> <span data-ttu-id="8c45f-107">Другие параметры используют для разделения столбцов запятые, символы табуляции и пробелы.</span><span class="sxs-lookup"><span data-stu-id="8c45f-107">Other options are using commas, tabs, or spaces to separate columns.</span></span> <span data-ttu-id="8c45f-108">Установите флажок **Другой** , чтобы задать иной разделяющий символ в поле **Произвольный разделитель** .</span><span class="sxs-lookup"><span data-stu-id="8c45f-108">Select the **Custom delimiter** check box to specify a different delimiting character in the **Custom delimiter** box.</span></span>  
  
 <span data-ttu-id="8c45f-109">**Другой**</span><span class="sxs-lookup"><span data-stu-id="8c45f-109">**Custom delimiter**</span></span>  
 <span data-ttu-id="8c45f-110">Задайте символ, которым будут разделяться столбцы.</span><span class="sxs-lookup"><span data-stu-id="8c45f-110">Specify the character of your choice to separate columns.</span></span> <span data-ttu-id="8c45f-111">Этот параметр доступен, только если флажок **Другой** был выбран в поле **Выходной формат** .</span><span class="sxs-lookup"><span data-stu-id="8c45f-111">This option is only available if the **Custom delimiter** check box is selected in the **Output format** box.</span></span>  
  
 <span data-ttu-id="8c45f-112">**Включить заголовки столбцов в результирующий набор**</span><span class="sxs-lookup"><span data-stu-id="8c45f-112">**Include column headers in the result set**</span></span>  
 <span data-ttu-id="8c45f-113">Снимите этот флажок, если заголовки столбцов не нужны.</span><span class="sxs-lookup"><span data-stu-id="8c45f-113">Clear this check box if you do not want each column labeled with a column title.</span></span>  
  
 <span data-ttu-id="8c45f-114">**Прокрутка по мере получения результатов**</span><span class="sxs-lookup"><span data-stu-id="8c45f-114">**Scroll as results are received**</span></span>  
 <span data-ttu-id="8c45f-115">Установите этот флажок, чтобы в нижней части экрана отображались последние возвращаемые строки.</span><span class="sxs-lookup"><span data-stu-id="8c45f-115">Select this check box to keep the display focus on the most recently returned records at the bottom.</span></span> <span data-ttu-id="8c45f-116">Снимите этот флажок, чтобы на экране отображалась первая возвращенная строка.</span><span class="sxs-lookup"><span data-stu-id="8c45f-116">Clear this check box to keep the display focus on the first rows received.</span></span>  
  
 <span data-ttu-id="8c45f-117">**Выравнивание результатов по правому краю**</span><span class="sxs-lookup"><span data-stu-id="8c45f-117">**Right align numeric values**</span></span>  
 <span data-ttu-id="8c45f-118">Установите этот флажок, чтобы выровнять числовые значения по правому краю столбца.</span><span class="sxs-lookup"><span data-stu-id="8c45f-118">Select this check box to align numeric values to the right of the column.</span></span> <span data-ttu-id="8c45f-119">Это облегчит просмотр целочисленных значений и цифр с десятичными разрядами.</span><span class="sxs-lookup"><span data-stu-id="8c45f-119">This can make it easier to review numbers with a fixed number of decimal places.</span></span>  
  
 <span data-ttu-id="8c45f-120">**Сбросить результат после выполнения запроса**</span><span class="sxs-lookup"><span data-stu-id="8c45f-120">**Discard result after query executes**</span></span>  
 <span data-ttu-id="8c45f-121">Освобождает память, сбрасывая результаты выполнения запроса после того, как их получит экранное устройство отображения.</span><span class="sxs-lookup"><span data-stu-id="8c45f-121">Frees memory by discarding the query results after the screen display has received them.</span></span>  
  
 <span data-ttu-id="8c45f-122">**Отобразить результаты на отдельной вкладке**</span><span class="sxs-lookup"><span data-stu-id="8c45f-122">**Display results in a separate tab**</span></span>  
 <span data-ttu-id="8c45f-123">Установите этот флажок, чтобы вывести результирующий набор в окне нового документа, а не в окне документа запроса.</span><span class="sxs-lookup"><span data-stu-id="8c45f-123">Select this check box to display the result set in a new document window, instead of at the bottom of the query document window.</span></span>  
  
 <span data-ttu-id="8c45f-124">**Открыть вкладку результатов после выполнения запроса**</span><span class="sxs-lookup"><span data-stu-id="8c45f-124">**Switch to results tab after the query executes**</span></span>  
 <span data-ttu-id="8c45f-125">Нажмите, чтобы автоматически сфокусировать экран на результирующем наборе.</span><span class="sxs-lookup"><span data-stu-id="8c45f-125">Click to automatically set the screen focus to the result set.</span></span>  
  
 <span data-ttu-id="8c45f-126">**Максимальное число символов в каждом столбце**</span><span class="sxs-lookup"><span data-stu-id="8c45f-126">**Maximum number of characters displayed in each column**</span></span>  
 <span data-ttu-id="8c45f-127">По умолчанию это значение равно 256.</span><span class="sxs-lookup"><span data-stu-id="8c45f-127">This value defaults to 256.</span></span> <span data-ttu-id="8c45f-128">Увеличьте это значение для вывода результирующих наборов большего размера без усечения.</span><span class="sxs-lookup"><span data-stu-id="8c45f-128">Increase this value to display larger result sets without truncation.</span></span>  
  
 <span data-ttu-id="8c45f-129">**По умолчанию**</span><span class="sxs-lookup"><span data-stu-id="8c45f-129">**Reset to Default**</span></span>  
 <span data-ttu-id="8c45f-130">Позволяет вернуть исходные значения по умолчанию для всех параметров на данной странице.</span><span class="sxs-lookup"><span data-stu-id="8c45f-130">Resets all values on this page to the original default values.</span></span>  
  
## <a name="saving-a-text-result-set-with-headers"></a><span data-ttu-id="8c45f-131">Сохранить текстовый результирующий набор с заголовками</span><span class="sxs-lookup"><span data-stu-id="8c45f-131">Saving a text result set with headers</span></span>  
 <span data-ttu-id="8c45f-132">Чтобы сохранить результаты запроса в виде текстового файла с заголовками, установите флажок **Включить заголовки столбцов в результирующий набор** и выберите выходной формат с разделителями.</span><span class="sxs-lookup"><span data-stu-id="8c45f-132">To save query results as a text file with headers, select the **Include column headers in the result set** check box and a delimited output format.</span></span> <span data-ttu-id="8c45f-133">Теперь файл отчета будет содержать заголовки, если нажать кнопку **Сохранить результаты в файл** на панели инструментов или щелкнуть правой кнопкой любые результаты запроса, а затем выбрать команду **Сохранить результаты как**, ввести имя файла и далее нажать кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8c45f-133">Now the report file will contain headers when you click **Results to File** on the toolbar, or when you right-click any query results, click **Save Results As**, type a file name, and then click **Save**.</span></span>  
  
  
