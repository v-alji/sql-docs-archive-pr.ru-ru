---
title: Результаты параметров запроса (страница «сетка») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.query.grid.f1
ms.assetid: 764bf435-3aab-4c62-b4e0-64fe020a5a95
author: rothja
ms.author: jroth
ms.openlocfilehash: bf300dd5071128b0259230ae788a27595bd8d29e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667382"
---
# <a name="query-options-results-grid-page"></a><span data-ttu-id="5cf1b-102">Результаты параметров запроса (страница «Сетка»)</span><span class="sxs-lookup"><span data-stu-id="5cf1b-102">Query Options Results (Grid Page)</span></span>
  <span data-ttu-id="5cf1b-103">Используйте эту страницу, чтобы указать параметры отображения результирующего набора запроса в формате сетки.</span><span class="sxs-lookup"><span data-stu-id="5cf1b-103">Use this page to specify the options for displaying a query result set in grid format.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5cf1b-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="5cf1b-104">Options</span></span>  
 <span data-ttu-id="5cf1b-105">**Включение запроса в результирующий набор**</span><span class="sxs-lookup"><span data-stu-id="5cf1b-105">**Include the query in the result set**</span></span>  
 <span data-ttu-id="5cf1b-106">Возвращает текст запроса как часть результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="5cf1b-106">Returns the text of the query as part of the result set.</span></span>  
  
 <span data-ttu-id="5cf1b-107">**Включать заголовки столбцов при копировании или сохранении результатов**</span><span class="sxs-lookup"><span data-stu-id="5cf1b-107">**Include column headers when copying or saving the results**</span></span>  
 <span data-ttu-id="5cf1b-108">Включает верхние колонтитулы столбцов (заголовки) при копировании результатов в буфер обмена или при сохранении файла.</span><span class="sxs-lookup"><span data-stu-id="5cf1b-108">Include column headers (titles) when results are copied to the clipboard, or saved in a file.</span></span> <span data-ttu-id="5cf1b-109">Снимите этот флажок, если нужно, чтобы при сохранении или копировании данных результатов они содержали только данные, без заголовков столбцов.</span><span class="sxs-lookup"><span data-stu-id="5cf1b-109">Clear this check box if you do not want saved or copied result data to have only the data, and not the column headings.</span></span>  
  
 <span data-ttu-id="5cf1b-110">**Сбросить результаты после выполнения**</span><span class="sxs-lookup"><span data-stu-id="5cf1b-110">**Discard results after execution**</span></span>  
 <span data-ttu-id="5cf1b-111">Освобождает память посредством сбрасывания результатов запроса после того, как они были выведены на экран.</span><span class="sxs-lookup"><span data-stu-id="5cf1b-111">Free memory by discarding the query results after the screen display has received them.</span></span>  
  
 <span data-ttu-id="5cf1b-112">**Отобразить результаты на отдельной вкладке**</span><span class="sxs-lookup"><span data-stu-id="5cf1b-112">**Display results in a separate tab**</span></span>  
 <span data-ttu-id="5cf1b-113">Отобразить результирующий набор в новом окне документа, а не в нижней части окна документа запроса.</span><span class="sxs-lookup"><span data-stu-id="5cf1b-113">Display the result set in a new document window, instead of at the bottom of the query document window.</span></span>  
  
 <span data-ttu-id="5cf1b-114">**Открыть вкладку результатов после выполнения запроса**</span><span class="sxs-lookup"><span data-stu-id="5cf1b-114">**Switch to results tab after the query executes**</span></span>  
 <span data-ttu-id="5cf1b-115">Автоматически переводит изображение на экране к результирующему набору.</span><span class="sxs-lookup"><span data-stu-id="5cf1b-115">Automatically set the screen focus to the result set.</span></span>  
  
 <span data-ttu-id="5cf1b-116">**Максимальное число полученных символов**</span><span class="sxs-lookup"><span data-stu-id="5cf1b-116">**Maximum Characters Retrieved**</span></span>  
 <span data-ttu-id="5cf1b-117">**Данные не в формате XML**:</span><span class="sxs-lookup"><span data-stu-id="5cf1b-117">**Non XML data**:</span></span>  
  
 <span data-ttu-id="5cf1b-118">Введите число от 1 до 65 535, чтобы указать максимальное число символов, отображаемых в каждой ячейке.</span><span class="sxs-lookup"><span data-stu-id="5cf1b-118">Enter a number from 1 through 65535 to specify the maximum number of characters that will be displayed in each cell.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5cf1b-119">Указание слишком большого числа символов может привести к тому, что результирующий набор будет отображаться усеченным.</span><span class="sxs-lookup"><span data-stu-id="5cf1b-119">Specifying a large number of characters may cause data in the result set to appear truncated.</span></span> <span data-ttu-id="5cf1b-120">Максимальное число символов, отображаемых в каждой ячейке, зависит от размера шрифта.</span><span class="sxs-lookup"><span data-stu-id="5cf1b-120">The maximum number of characters displayed in each cell is dependent on the font size.</span></span> <span data-ttu-id="5cf1b-121">Высокое значение в этом окне может привести к нехватке памяти для среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] и снижению производительности системы при возвращении больших результирующих наборов.</span><span class="sxs-lookup"><span data-stu-id="5cf1b-121">When large result sets are returned, a high value in this box can cause [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to run low on memory and hinder system performance.</span></span>  
  
 <span data-ttu-id="5cf1b-122">**XML-данные**:</span><span class="sxs-lookup"><span data-stu-id="5cf1b-122">**XML data**:</span></span>  
  
 <span data-ttu-id="5cf1b-123">Выберите **1 МБ**, **2 МБ**или **5 МБ**.</span><span class="sxs-lookup"><span data-stu-id="5cf1b-123">Select **1 MB**, **2 MB**, or **5 MB**.</span></span> <span data-ttu-id="5cf1b-124">Выберите пункт **Без ограничений** , чтобы вывести все символы.</span><span class="sxs-lookup"><span data-stu-id="5cf1b-124">Select **Unlimited** to retrieve all characters.</span></span>  
  
 <span data-ttu-id="5cf1b-125">**По умолчанию**</span><span class="sxs-lookup"><span data-stu-id="5cf1b-125">**Reset to Default**</span></span>  
 <span data-ttu-id="5cf1b-126">Позволяет вернуть исходные значения по умолчанию для всех параметров на данной странице.</span><span class="sxs-lookup"><span data-stu-id="5cf1b-126">Resets all values on this page to the original default values.</span></span>  
  
  
