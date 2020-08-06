---
title: Сортировка столбцов | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.sortcolumns.f1
ms.assetid: 66b44b6c-10a5-4e3f-a97b-7568609c88ac
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e5fe56688a009fd60a7731b199f32352d78bb5eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752112"
---
# <a name="sort-columns"></a><span data-ttu-id="8a165-102">Сортировка столбцов</span><span class="sxs-lookup"><span data-stu-id="8a165-102">Sort Columns</span></span>
  <span data-ttu-id="8a165-103">Диалоговое окно **Сортировка столбцов** позволяет сортировать сетки в мониторе репликации по значению одного или нескольких столбцов.</span><span class="sxs-lookup"><span data-stu-id="8a165-103">The **Sort Columns** dialog box lets you sort grids in Replication Monitor based on one or more columns.</span></span> <span data-ttu-id="8a165-104">(Отсортировать по одному столбцу можно, щелкнув его заголовок в сетке монитора репликации).</span><span class="sxs-lookup"><span data-stu-id="8a165-104">(You can also sort on a single column by clicking the column header in the Replication Monitor grid).</span></span> <span data-ttu-id="8a165-105">Например, чтобы отсортировать подписки на вкладке **Все подписки** по состоянию, а затем по типу соединения, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="8a165-105">For example, to sort subscriptions on the **All Subscriptions** tab based on status and then connection type, follow these steps:</span></span>  
  
1.  <span data-ttu-id="8a165-106">В первой строке сетки выберите **Состояние** в столбце **Имя столбца** и значение в столбце **Порядок сортировки** .</span><span class="sxs-lookup"><span data-stu-id="8a165-106">In the first row of the grid, select **Status** from the **Column Name** column and a value from the **Sort Order** column</span></span>  
  
2.  <span data-ttu-id="8a165-107">Во второй строке сетки выберите **Тип соединения** в столбце **Имя столбца** и значение в столбце **Порядок сортировки** .</span><span class="sxs-lookup"><span data-stu-id="8a165-107">In the second row of the grid, select **Connection Type** from the **Column Name** column, and a value from the **Sort Order** column.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8a165-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="8a165-108">Options</span></span>  
 <span data-ttu-id="8a165-109">**Имя столбца**</span><span class="sxs-lookup"><span data-stu-id="8a165-109">**Column Name**</span></span>  
 <span data-ttu-id="8a165-110">Имя столбца, по которому нужно выполнить сортировку.</span><span class="sxs-lookup"><span data-stu-id="8a165-110">The name of the column on which you want to sort.</span></span> <span data-ttu-id="8a165-111">Можно выполнить сортировку по одному или нескольким столбцам.</span><span class="sxs-lookup"><span data-stu-id="8a165-111">You can sort on one or more columns.</span></span> <span data-ttu-id="8a165-112">Нельзя выполнить сортировку по столбцам **Текущая средняя производительность** и **Худшая производительность в данный момент** на вкладке **Публикации** из-за способа вычисления значений в этих столбцах.</span><span class="sxs-lookup"><span data-stu-id="8a165-112">You cannot sort on the **Current Average Performance** or **Current Worst Performance** columns on the **Publications** tab, because of the way in which these column values are calculated.</span></span>  
  
 <span data-ttu-id="8a165-113">**Порядок сортировки**</span><span class="sxs-lookup"><span data-stu-id="8a165-113">**Sort Order**</span></span>  
 <span data-ttu-id="8a165-114">Укажите значение **По возрастанию** или **По убыванию**.</span><span class="sxs-lookup"><span data-stu-id="8a165-114">Specify a value of **Ascending** or **Descending**.</span></span>  
  
 <span data-ttu-id="8a165-115">**Очистить все**</span><span class="sxs-lookup"><span data-stu-id="8a165-115">**Clear All**</span></span>  
 <span data-ttu-id="8a165-116">Удалите все строки из сетки сортировки.</span><span class="sxs-lookup"><span data-stu-id="8a165-116">Remove all rows from the sorting grid.</span></span> <span data-ttu-id="8a165-117">Для удаления одной строки выделите строку и нажмите клавишу «DELETE».</span><span class="sxs-lookup"><span data-stu-id="8a165-117">To remove a single row, select the row and press the Delete key.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a165-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="8a165-118">See Also</span></span>  
 [<span data-ttu-id="8a165-119">Наблюдение за репликацией</span><span class="sxs-lookup"><span data-stu-id="8a165-119">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
