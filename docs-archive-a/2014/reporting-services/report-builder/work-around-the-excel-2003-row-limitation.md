---
title: Обход ограничения строки Excel | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a4c8700b-bef5-4440-a99c-bba5dcc46bfd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 128f65cf09833d23234da10bf7744c6ce30065ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657026"
---
# <a name="work-around-the-excel-row-limitation"></a><span data-ttu-id="f4e12-102">Обход ограничения строк Excel</span><span class="sxs-lookup"><span data-stu-id="f4e12-102">Work Around the Excel Row Limitation</span></span>
  <span data-ttu-id="f4e12-103">В этом разделе объясняется, как обойти ограничения строк Excel 2003 при экспорте отчетов в Excel.</span><span class="sxs-lookup"><span data-stu-id="f4e12-103">This topic explains how to work around the Excel 2003 row limitation when you export reports to Excel.</span></span> <span data-ttu-id="f4e12-104">Это решение подходит для отчета, который содержит только таблицу.</span><span class="sxs-lookup"><span data-stu-id="f4e12-104">The workaround is for a report that contains only a table.</span></span>  
  
 <span data-ttu-id="f4e12-105">Excel 2003 поддерживает максимум 65 536 строк на одном листе.</span><span class="sxs-lookup"><span data-stu-id="f4e12-105">Excel 2003 supports a maximum of 65,536 rows per worksheet.</span></span> <span data-ttu-id="f4e12-106">Это ограничение можно обойти, реализовав принудительное явное разбиение на страницы после определенного числа строк.</span><span class="sxs-lookup"><span data-stu-id="f4e12-106">You can work around this limitation by forcing an explicit page break after a certain number of rows.</span></span> <span data-ttu-id="f4e12-107">Модуль подготовки отчетов Excel создаст новый лист для каждого явного разрыва страницы.</span><span class="sxs-lookup"><span data-stu-id="f4e12-107">The Excel renderer creates a new worksheet for each explicit page break.</span></span>  
  
### <a name="to-create-an-explicit-page-break"></a><span data-ttu-id="f4e12-108">Создание явного разрыва страницы</span><span class="sxs-lookup"><span data-stu-id="f4e12-108">To create an explicit page break</span></span>  
  
1.  <span data-ttu-id="f4e12-109">Откройте отчет в [!INCLUDE[ss_dtbi](../../includes/ss-dtbi-md.md)] или в диспетчере отчетов.</span><span class="sxs-lookup"><span data-stu-id="f4e12-109">Open the report in [!INCLUDE[ss_dtbi](../../includes/ss-dtbi-md.md)] or Report Manager.</span></span>  
  
2.  <span data-ttu-id="f4e12-110">Щелкните правой кнопкой мыши строку данных в таблице и выберите команду **Добавить**  >  **родительскую** группу группы, чтобы добавить внешнюю группу таблиц.</span><span class="sxs-lookup"><span data-stu-id="f4e12-110">Right click the Data row in the table, and then click **Add Group** > **Parent Group** to add an outer table group.</span></span>  
  
     <span data-ttu-id="f4e12-111">![Выбор родительской группы](../media/datarow-selectparentgroup.png "Выбор родительской группы")</span><span class="sxs-lookup"><span data-stu-id="f4e12-111">![Select the Parent Group](../media/datarow-selectparentgroup.png "Select the Parent Group")</span></span>  
  
3.  <span data-ttu-id="f4e12-112">Введите следующую формулу в поле выражения **Группировать по** и нажмите кнопку **ОК** для добавления родительской группы.</span><span class="sxs-lookup"><span data-stu-id="f4e12-112">Enter the following formula in the **Group by** expression box, and then click **OK** to add the parent group.</span></span>  
  
     <span data-ttu-id="f4e12-113">=Int((RowNumber(Nothing)-1)/65000)</span><span class="sxs-lookup"><span data-stu-id="f4e12-113">=Int((RowNumber(Nothing)-1)/65000)</span></span>  
  
     <span data-ttu-id="f4e12-114">Эта формула назначает номер каждому набору из 65 000 строк в наборе данных.</span><span class="sxs-lookup"><span data-stu-id="f4e12-114">The formula assigns a number to each set of 65000 rows in the dataset.</span></span> <span data-ttu-id="f4e12-115">Если для этой группы определен разрыв страницы, данное выражение будет выводить его через каждые 65 000 строк.</span><span class="sxs-lookup"><span data-stu-id="f4e12-115">When a page break is defined for the group, the expression results in a page break every 65000 rows.</span></span>  
  
     <span data-ttu-id="f4e12-116">При добавлении внешней группы таблицы в отчет добавляется столбец группы.</span><span class="sxs-lookup"><span data-stu-id="f4e12-116">Adding the outer table group adds a group column to the report.</span></span>  
  
4.  <span data-ttu-id="f4e12-117">Удалите столбец группы, щелкнув правой кнопкой мыши заголовок столбца, затем последовательно выбрав **Удалить столбцы**, **Удалить только столбцы**и нажав кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f4e12-117">Delete the group column by right-clicking on the column header, clicking **Delete Columns**, selecting **Delete columns only**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="f4e12-118">![Удаление столбца группы](../media/groupcolumn-delete-updated.png "Удаление столбца группы")</span><span class="sxs-lookup"><span data-stu-id="f4e12-118">![Delete a group column](../media/groupcolumn-delete-updated.png "Delete a group column")</span></span>  
  
5.  <span data-ttu-id="f4e12-119">Щелкните правой кнопкой мыши **группу 1** в разделе **Группы строк** , а затем выберите **Свойства группы**.</span><span class="sxs-lookup"><span data-stu-id="f4e12-119">Right click **Group 1** in the **Row Groups** section, and then click **Group Properties**.</span></span>  
  
     <span data-ttu-id="f4e12-120">![Просмотр свойств группы](../media/groupproperties-updated.png "Просмотр свойств группы")</span><span class="sxs-lookup"><span data-stu-id="f4e12-120">![View group properties](../media/groupproperties-updated.png "View group properties")</span></span>  
  
6.  <span data-ttu-id="f4e12-121">На странице **Сортировка** диалогового окна **Свойства группы** выберите параметр сортировки по умолчанию и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f4e12-121">On the **Sorting** page of the **Group Properties** dialog box, select the default sorting option and click **Delete**.</span></span>  
  
     <span data-ttu-id="f4e12-122">![Удаление сортировки по умолчанию](../media/groupproperties-sorting-updated.png "Удаление сортировки по умолчанию")</span><span class="sxs-lookup"><span data-stu-id="f4e12-122">![Delete default sorting](../media/groupproperties-sorting-updated.png "Delete default sorting")</span></span>  
  
7.  <span data-ttu-id="f4e12-123">На странице **Разрывы страниц** щелкните **Между всеми экземплярами группы** , затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f4e12-123">On the **Page Breaks** page, click **Between each instance of a group** and then click **OK**.</span></span>  
  
     <span data-ttu-id="f4e12-124">![Задание разрывов страниц](../media/groupproperties-pagebreaks-updated.png "Задание разрывов страниц")</span><span class="sxs-lookup"><span data-stu-id="f4e12-124">![Set page breaks](../media/groupproperties-pagebreaks-updated.png "Set page breaks")</span></span>  
  
8.  <span data-ttu-id="f4e12-125">Сохраните отчет.</span><span class="sxs-lookup"><span data-stu-id="f4e12-125">Save the report.</span></span> <span data-ttu-id="f4e12-126">При экспорте отчета в книгу Excel он размещается на нескольких листах, каждый из которых может содержать не более 65 000 строк.</span><span class="sxs-lookup"><span data-stu-id="f4e12-126">When you export it to Excel, it exports to multiple worksheets and each worksheet contains a maximum of 65000 rows.</span></span>  
  
  
