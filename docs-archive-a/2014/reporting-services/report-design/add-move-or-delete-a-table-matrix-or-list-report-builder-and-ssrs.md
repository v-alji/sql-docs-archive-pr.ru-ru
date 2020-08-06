---
title: Добавление, перемещение или удаление таблицы, матрицы или списка (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4b97c470-cde0-4bb1-a46e-5f5f5553feaa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 43941639a41c897a49cd34662b74de26a27e3f07
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739353"
---
# <a name="add-move-or-delete-a-table-matrix-or-list-report-builder-and-ssrs"></a><span data-ttu-id="a1e65-102">Добавление, перемещение или удаление таблицы, матрицы или списка (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="a1e65-102">Add, Move, or Delete a Table, Matrix, or List (Report Builder and SSRS)</span></span>
  <span data-ttu-id="a1e65-103">Область данных отображает данные из набора данных отчета.</span><span class="sxs-lookup"><span data-stu-id="a1e65-103">A data region displays data from a report dataset.</span></span> <span data-ttu-id="a1e65-104">Области данных включают таблицу, матрицу, список, диаграмму и датчик.</span><span class="sxs-lookup"><span data-stu-id="a1e65-104">Data regions include table, matrix, list, chart, and gauge.</span></span> <span data-ttu-id="a1e65-105">Чтобы вложить одну область данных в другую, добавьте каждую область данных по отдельности, а затем перетащите дочернюю область данных на родительскую.</span><span class="sxs-lookup"><span data-stu-id="a1e65-105">To nest one data region inside another, add each data region separately, and then drag the child data region onto the parent data region.</span></span>  
  
 <span data-ttu-id="a1e65-106">Самым простым способом добавления табличной или матричной области данных в отчет является запуск мастера создания таблицы или матрицы.</span><span class="sxs-lookup"><span data-stu-id="a1e65-106">The simplest way to add a table or matrix data region to your report is to run the New Table or New Matrix Wizard.</span></span> <span data-ttu-id="a1e65-107">Эти мастера помогут выполнить процесс выбора соединения с источником данных, расположения полей и выбора макета и стиля.</span><span class="sxs-lookup"><span data-stu-id="a1e65-107">These wizards will guide you through the process of choosing a connection to a data source, arranging fields, and choosing the layout and style.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a1e65-108">Мастер доступен только в построителе отчетов.</span><span class="sxs-lookup"><span data-stu-id="a1e65-108">The wizard is available only in Report Builder.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-table-or-matrix-to-a-report-by-using-the-new-table-or-new-matrix-wizard"></a><span data-ttu-id="a1e65-109">Добавление таблицы или матрицы в отчет с помощью мастера создания таблицы или матрицы</span><span class="sxs-lookup"><span data-stu-id="a1e65-109">To add a table or matrix to a report by using the New Table or New Matrix Wizard</span></span>  
  
1.  <span data-ttu-id="a1e65-110">На вкладке **Вставка** выберите пункт **Таблица** или **Матрица**, а затем выберите команду **Мастер таблиц** или **Мастер матриц**.</span><span class="sxs-lookup"><span data-stu-id="a1e65-110">On the **Insert** tab, click **Table** or **Matrix**, and then click **Table Wizard** or **Matrix Wizard**.</span></span>  
  
2.  <span data-ttu-id="a1e65-111">Выполните действия, описанные в мастере **невтабле** или **new Matrix** .</span><span class="sxs-lookup"><span data-stu-id="a1e65-111">Follow the steps in the **NewTable** or **New Matrix** wizard.</span></span>  
  
3.  <span data-ttu-id="a1e65-112">На вкладке **Корневая папка** нажмите кнопку **Выполнить** , чтобы вывести отчет, готовый для просмотра.</span><span class="sxs-lookup"><span data-stu-id="a1e65-112">On the **Home** tab, click **Run** to see the rendered report.</span></span>  
  
4.  <span data-ttu-id="a1e65-113">На вкладке **Выполнение** нажмите кнопку **Конструктор** , чтобы продолжить работу с отчетом.</span><span class="sxs-lookup"><span data-stu-id="a1e65-113">On the **Run** tab, click **Design** to continue working on the report.</span></span>  
  
### <a name="to-add-a-data-region"></a><span data-ttu-id="a1e65-114">Добавление области данных</span><span class="sxs-lookup"><span data-stu-id="a1e65-114">To add a data region</span></span>  
  
1.  <span data-ttu-id="a1e65-115">На **ленте**в группе **Области данных** щелкните область данных для добавления.</span><span class="sxs-lookup"><span data-stu-id="a1e65-115">On the **Ribbon**, in the **Data Regions** group, click the data region to add.</span></span>  
  
2.  <span data-ttu-id="a1e65-116">Щелкните область конструктора и перетащите указатель мыши, чтобы создать поле по размеру области данных.</span><span class="sxs-lookup"><span data-stu-id="a1e65-116">Click the design surface, and then drag to create a box that is the desired size of the data region.</span></span>  
  
3.  <span data-ttu-id="a1e65-117">Перетащите поле набора данных отчета из панели данных отчета в ячейку панели данных.</span><span class="sxs-lookup"><span data-stu-id="a1e65-117">Drag a report dataset field from the Report Data pane onto a data region cell.</span></span> <span data-ttu-id="a1e65-118">Теперь область данных привязана к данным из набора данных отчета.</span><span class="sxs-lookup"><span data-stu-id="a1e65-118">The data region is now bound to data from the report dataset.</span></span>  
  
### <a name="to-select-a-data-region"></a><span data-ttu-id="a1e65-119">Выбор области данных</span><span class="sxs-lookup"><span data-stu-id="a1e65-119">To select a data region</span></span>  
  
-   <span data-ttu-id="a1e65-120">При работе с областью данных табликса щелкните правой клавишей мыши угловой маркер.</span><span class="sxs-lookup"><span data-stu-id="a1e65-120">For a tablix data region, right-click the corner handle.</span></span> <span data-ttu-id="a1e65-121">В случае области данных диаграммы или датчика щелкните внутри области данных.</span><span class="sxs-lookup"><span data-stu-id="a1e65-121">For a chart or gauge data region, click in the data region.</span></span>  
  
     <span data-ttu-id="a1e65-122">Появится маркер выбора и восемь маркеров изменения размера.</span><span class="sxs-lookup"><span data-stu-id="a1e65-122">A selection handle and eight resizing handles appear.</span></span>  
  
     <span data-ttu-id="a1e65-123">В случае вложенных областей данных щелкните внутри вложенной области данных правой кнопкой мыши, щелкните команду **Выбрать**, а затем выберите требуемый элемент отчета.</span><span class="sxs-lookup"><span data-stu-id="a1e65-123">For nested data regions, right-click in the nested data region, click **Select**, and then select the report item you want.</span></span> <span data-ttu-id="a1e65-124">Чтобы проверить, какой элемент отчета выбран, используйте панель свойств.</span><span class="sxs-lookup"><span data-stu-id="a1e65-124">To verify which report item is selected, use the Properties pane.</span></span> <span data-ttu-id="a1e65-125">Имя элемента, выбранного в области конструктора, появится на панели инструментов панели свойств.</span><span class="sxs-lookup"><span data-stu-id="a1e65-125">The name of the selected item on the design surface appears in the toolbar of the Properties pane.</span></span>  
  
### <a name="to-move-a-data-region"></a><span data-ttu-id="a1e65-126">Перемещение области данных</span><span class="sxs-lookup"><span data-stu-id="a1e65-126">To move a data region</span></span>  
  
-   <span data-ttu-id="a1e65-127">Чтобы переместить область данных, щелкните маркер выбора области данных и перетащите ее.</span><span class="sxs-lookup"><span data-stu-id="a1e65-127">To move a data region, click the selection handle of the data region and drag it.</span></span> <span data-ttu-id="a1e65-128">Используйте линии привязки, чтобы выровнять ее по существующим элементам отчета.</span><span class="sxs-lookup"><span data-stu-id="a1e65-128">Use snaplines to align it to existing report items.</span></span>  
  
     <span data-ttu-id="a1e65-129">Если линейка не отображается, перейдите на вкладку «Вид» и выберите параметр **Линейка** .</span><span class="sxs-lookup"><span data-stu-id="a1e65-129">If the ruler is not visible, click the View tab and select the **Ruler** option.</span></span>  
  
     <span data-ttu-id="a1e65-130">Также для перемещения выбранной области данных по области конструктора можно использовать кнопки со стрелками.</span><span class="sxs-lookup"><span data-stu-id="a1e65-130">Alternatively, use the arrow keys to move the selected data region on the design surface.</span></span>  
  
### <a name="to-delete-a-data-region"></a><span data-ttu-id="a1e65-131">Удаление области данных</span><span class="sxs-lookup"><span data-stu-id="a1e65-131">To delete a data region</span></span>  
  
-   <span data-ttu-id="a1e65-132">Выделите области данных, щелкните внутри нее правой кнопкой мыши, а затем выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="a1e65-132">Select the data region, right-click in the data region, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1e65-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="a1e65-133">See Also</span></span>  
 <span data-ttu-id="a1e65-134">[Область данных табликса (построитель отчетов и службы SSRS)](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a1e65-134">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a1e65-135">[Таблицы &#40;построитель отчетов и службы SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a1e65-135">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a1e65-136">[Матрицы &#40;построитель отчетов и службы SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a1e65-136">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a1e65-137">[Содержит &#40;построитель отчетов и SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a1e65-137">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="a1e65-138">Таблицы, матрицы и списки (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="a1e65-138">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
