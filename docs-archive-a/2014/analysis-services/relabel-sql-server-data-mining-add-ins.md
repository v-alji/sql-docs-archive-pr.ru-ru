---
title: Переразметка (SQL Server надстроек интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data preparation
- relabel
- data cleaning
ms.assetid: af041b39-fdd1-4cb5-a5ef-2f3ddab84614
author: minewiskan
ms.author: owend
ms.openlocfilehash: a625676f60e2da32e19b85a94002b51eeb9ac816
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664509"
---
# <a name="relabel-sql-server-data-mining-add-ins"></a><span data-ttu-id="d04b1-102">Переразметка (надстройки интеллектуального анализа данных SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d04b1-102">Relabel (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="d04b1-103">![Значок Office 13 для средства «Переразметка»](media/dm13-relabel.gif "Значок Office 13 для средства «Переразметка»")</span><span class="sxs-lookup"><span data-stu-id="d04b1-103">![Office 13 icon for Relabel tool](media/dm13-relabel.gif "Office 13 icon for Relabel tool")</span></span>

 <span data-ttu-id="d04b1-104">С помощью клиента интеллектуального анализа данных для Excel можно создать для данных новые метки, чтобы облегчить понимание результатов анализа.</span><span class="sxs-lookup"><span data-stu-id="d04b1-104">The Data Mining Client for Excel helps you create new labels for data to make it easier to understand the results of analysis.</span></span>

 <span data-ttu-id="d04b1-105">Причины для переразметки:</span><span class="sxs-lookup"><span data-stu-id="d04b1-105">Reasons for relabeling include:</span></span>

-   <span data-ttu-id="d04b1-106">Данные содержат закодированные результаты, например 1 — мужчины, 2 — женщины.</span><span class="sxs-lookup"><span data-stu-id="d04b1-106">The data includes results that were coded, such as 1 for Male and 2 for Female.</span></span>

-   <span data-ttu-id="d04b1-107">Вы группируете числовые значения и хотите указать описательные имена для диапазонов.</span><span class="sxs-lookup"><span data-stu-id="d04b1-107">You are bucketing numeric values and want to give the ranges a descriptive name.</span></span>

-   <span data-ttu-id="d04b1-108">Вы хотите упростить длинные имена.</span><span class="sxs-lookup"><span data-stu-id="d04b1-108">You want to simplify long names.</span></span>

## <a name="using-the-relabel-wizard"></a><span data-ttu-id="d04b1-109">Использование мастера переразметки</span><span class="sxs-lookup"><span data-stu-id="d04b1-109">Using the Relabel Wizard</span></span>

1.  <span data-ttu-id="d04b1-110">На ленте **интеллектуальный анализ данных** нажмите кнопку **очистить** , а затем выберите пункт **изменить метку**.</span><span class="sxs-lookup"><span data-stu-id="d04b1-110">In the **Data Mining** ribbon, click **Clean** and then select **Re-Label**.</span></span>

2.  <span data-ttu-id="d04b1-111">Выберите таблицу или диапазон данных, содержащий данные, которые необходимо исправить.</span><span class="sxs-lookup"><span data-stu-id="d04b1-111">Select the table or data range that has the data you want to fix.</span></span>

3.  <span data-ttu-id="d04b1-112">На странице мастера **переразметки** выберите один столбец, либо выбрав столбец из раскрывающегося списка, либо щелкнув столбец на панели **образцы данных** .</span><span class="sxs-lookup"><span data-stu-id="d04b1-112">In the **Re-label** page of the wizard, select a single column, either by choosing the column from the dropdown list, or by clicking the column in the **Data samples** pane.</span></span>

     <span data-ttu-id="d04b1-113">На панели " **образцы данных** " отображается только около 50 строк данных, но они вычисляются, чтобы убедиться, что вы видите хороший разворот значений.</span><span class="sxs-lookup"><span data-stu-id="d04b1-113">The **Data samples** pane only shows about 50 rows of data, but they are sampled to ensure that you see a good spread of values.</span></span>

     <span data-ttu-id="d04b1-114">Щелкните заголовок столбца **Count** , чтобы выполнить сортировку по количеству значений.</span><span class="sxs-lookup"><span data-stu-id="d04b1-114">Click the column header for **Count** to sort by the count of each value.</span></span>

     <span data-ttu-id="d04b1-115">Кроме того, можно выполнять сортировку по **исходным меткам**, что удобно, если необходимо сначала повторно пометить все наиболее или наименьшие значения.</span><span class="sxs-lookup"><span data-stu-id="d04b1-115">You can also sort by **Original Labels**, which is handy if you want to re-label all the highest or lowest values first.</span></span>

4.  <span data-ttu-id="d04b1-116">На странице " **переметка** данных" мастера проверьте значения в столбце **исходные метки** и выберите способ группировки или редактирования.</span><span class="sxs-lookup"><span data-stu-id="d04b1-116">In the **Re-label** data page of the wizard, review the values in the **Original Labels** column, and decide how you want to group or edit them.</span></span>

5.  <span data-ttu-id="d04b1-117">Введите новое значение в строку под заголовком **новые метки**.</span><span class="sxs-lookup"><span data-stu-id="d04b1-117">Type a new value into the row under **New Labels**.</span></span> <span data-ttu-id="d04b1-118">Также можно выбрать значение из списка существующих значений.</span><span class="sxs-lookup"><span data-stu-id="d04b1-118">You can also choose a value from the list of existing values.</span></span> <span data-ttu-id="d04b1-119">При вводе новых значений они сразу же становятся доступными для повторного использования.</span><span class="sxs-lookup"><span data-stu-id="d04b1-119">As you type new values, they become available for re-use right away.</span></span>

6.  <span data-ttu-id="d04b1-120">Если введено достаточное количество строк, нажмите кнопку **Далее**, а затем на странице **Выбор назначения** выберите место сохранения перепомеченных данных.</span><span class="sxs-lookup"><span data-stu-id="d04b1-120">When you have entered enough rows, click **Next**, and on the **Select Destination** page, choose where you'll save the relabeled data.</span></span>

    -   <span data-ttu-id="d04b1-121">**Добавление нового столбца на текущий лист**</span><span class="sxs-lookup"><span data-stu-id="d04b1-121">**Add as a new column to the current worksheet**</span></span>

         <span data-ttu-id="d04b1-122">Щелкните, чтобы добавить новый столбец в таблицу, содержащую новые значения.</span><span class="sxs-lookup"><span data-stu-id="d04b1-122">Click to add a new column to the table that contains the new values.</span></span>

    -   <span data-ttu-id="d04b1-123">**Копирование данных листа с изменениями на новый лист**</span><span class="sxs-lookup"><span data-stu-id="d04b1-123">**Copy sheet data with changes to a new worksheet**</span></span>

         <span data-ttu-id="d04b1-124">Щелкните, чтобы создать новый лист, содержащий обновленные данные.</span><span class="sxs-lookup"><span data-stu-id="d04b1-124">Click to create a new worksheet that contains the updated data.</span></span>

    -   <span data-ttu-id="d04b1-125">**Изменение данных на месте**</span><span class="sxs-lookup"><span data-stu-id="d04b1-125">**Change data in place**</span></span>

         <span data-ttu-id="d04b1-126">Щелкните, чтобы заменить исходные данные новыми значениями.</span><span class="sxs-lookup"><span data-stu-id="d04b1-126">Click to replace the original data with the new values.</span></span>

## <a name="see-also"></a><span data-ttu-id="d04b1-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="d04b1-127">See Also</span></span>
 [<span data-ttu-id="d04b1-128">Исследование и очистка данных</span><span class="sxs-lookup"><span data-stu-id="d04b1-128">Exploring and Cleaning Data</span></span>](exploring-and-cleaning-data.md)


