---
title: Исключение повторяющихся строк (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], excluding rows
- row duplicates [SQL Server]
- duplicate rows
- row excluded in search [SQL Server]
- result sets [SQL Server], duplicate values
- excluding rows
ms.assetid: ab35a363-421d-4665-946b-ae3f6397af50
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3b396f2738f6895684d828884d4822ea9165e0a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668017"
---
# <a name="exclude-duplicate-rows-visual-database-tools"></a><span data-ttu-id="5c19a-102">Исключение повторяющихся строк (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="5c19a-102">Exclude Duplicate Rows (Visual Database Tools)</span></span>
  <span data-ttu-id="5c19a-103">Если необходимо, чтобы результирующий набор содержал лишь уникальные значения, можно исключить повторяющиеся значения из результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="5c19a-103">If you want to see only unique values in a result set, you can specify that you want to exclude duplicates from the result set.</span></span>  
  
### <a name="to-exclude-duplicate-rows-from-the-result-set"></a><span data-ttu-id="5c19a-104">Удаление повторяющихся строк из результирующего набора</span><span class="sxs-lookup"><span data-stu-id="5c19a-104">To exclude duplicate rows from the result set</span></span>  
  
1.  <span data-ttu-id="5c19a-105">Щелкните правой кнопкой мыши фон панели диаграмм, а затем в контекстном меню выберите пункт **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="5c19a-105">Right-click the background of the Diagram pane, then choose **Properties** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="5c19a-106">В окне свойств щелкните **Неповторяющиеся значения** и установите значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="5c19a-106">In the Property window, click **Distinct values** and set the value to **Yes**.</span></span>  
  
     <span data-ttu-id="5c19a-107">Конструктор запросов и представлений поместит ключевое слово DISTINCT перед списком отображаемых столбцов в инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="5c19a-107">The Query and View Designer inserts the keyword DISTINCT in front of the list of display columns in the SQL statement.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5c19a-108">При использовании ключевого слова DISTINCT изменение результирующего набора на панели результатов может оказаться невозможным.</span><span class="sxs-lookup"><span data-stu-id="5c19a-108">If you use the DISTINCT keyword you may not be able to modify the result set in the results pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c19a-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="5c19a-109">See Also</span></span>  
 <span data-ttu-id="5c19a-110">[Укажите условия поиска &#40;визуальные инструменты для баз данных&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="5c19a-110">[Specify Search Criteria &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="5c19a-111">Результаты запросов сортировки и группирования (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="5c19a-111">Sort and Group Query Results &#40;Visual Database Tools&#41;</span></span>](sort-and-group-query-results-visual-database-tools.md)  
  
  
