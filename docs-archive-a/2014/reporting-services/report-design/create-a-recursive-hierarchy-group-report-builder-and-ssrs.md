---
title: Создание группы рекурсивной иерархии (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8b830ba5-4d64-4348-a2b1-76b9338a1462
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bf86c3989170ed8cd452168a558ead348258331e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658145"
---
# <a name="create-a-recursive-hierarchy-group-report-builder-and-ssrs"></a><span data-ttu-id="d30cf-102">Создание группы рекурсивной иерархии (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d30cf-102">Create a Recursive Hierarchy Group (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d30cf-103">Группа рекурсивной иерархии организует данные отдельного набора данных отчета, включающего несколько уровней иерархии, например структуру подчинения для иерархии связей «начальник-подчиненный» в организации.</span><span class="sxs-lookup"><span data-stu-id="d30cf-103">A recursive hierarchy group organizes data from a single report dataset that includes multiple hierarchical levels, such as the report-to structure for manager-employee relationships in an organizational hierarchy.</span></span>  
  
 <span data-ttu-id="d30cf-104">Прежде чем организовать данные в таблице в группу рекурсивной иерархии, необходимо получить один набор данных, содержащий все иерархические данные. При этом необходимы отдельные поля для группируемого элемента и для элемента, по которому происходит группирование.</span><span class="sxs-lookup"><span data-stu-id="d30cf-104">Before you can organize data in a table as a recursive hierarchy group, you must have a single dataset that contains all the hierarchical data, You must have separate fields for the item to group and for the item to group by.</span></span> <span data-ttu-id="d30cf-105">Например, набор данных, в котором необходимо провести рекурсивное группирование подчиненных каждого руководителя, может содержать в строках такие записи: имя, имя сотрудника, идентификатор сотрудника и идентификатор руководителя.</span><span class="sxs-lookup"><span data-stu-id="d30cf-105">For example, a dataset where you want to group employees recursively under their manager might contain a name, an employee name, an employee ID, and a manager ID.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-create-a-recursive-hierarchy-group"></a><span data-ttu-id="d30cf-106">Создание группы рекурсивной иерархии</span><span class="sxs-lookup"><span data-stu-id="d30cf-106">To create a recursive hierarchy group</span></span>  
  
1.  <span data-ttu-id="d30cf-107">В представлении конструктора добавьте таблицу и перетащите туда поля набора данных, которые нужно отобразить.</span><span class="sxs-lookup"><span data-stu-id="d30cf-107">In Design view, add a table, and drag the dataset fields to display.</span></span> <span data-ttu-id="d30cf-108">Обычно поле, отображаемое в виде иерархии, находится в первом столбце.</span><span class="sxs-lookup"><span data-stu-id="d30cf-108">Typically, the field that you want to show as a hierarchy is in the first column.</span></span>  
  
2.  <span data-ttu-id="d30cf-109">Чтобы выбрать таблицу, щелкните правой кнопкой мыши в любой ее точке.</span><span class="sxs-lookup"><span data-stu-id="d30cf-109">Right-click anywhere in the table to select it.</span></span> <span data-ttu-id="d30cf-110">Панель группирования отображает группу сведений для выбранной таблицы.</span><span class="sxs-lookup"><span data-stu-id="d30cf-110">The Grouping pane displays the details group for the selected table.</span></span> <span data-ttu-id="d30cf-111">На панели "Группы строк" щелкните правой кнопкой мыши группу **Сведения**и выберите пункт **Изменить группу**.</span><span class="sxs-lookup"><span data-stu-id="d30cf-111">In the Row Groups pane, right-click **Details**, and then click **Edit Group**.</span></span> <span data-ttu-id="d30cf-112">Откроется диалоговое окно **Свойства группы** .</span><span class="sxs-lookup"><span data-stu-id="d30cf-112">The **Group Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="d30cf-113">Щелкните **Добавить**в области **Выражения группирования**.</span><span class="sxs-lookup"><span data-stu-id="d30cf-113">In **Group expressions**, click **Add**.</span></span> <span data-ttu-id="d30cf-114">В сетке появится новая строка.</span><span class="sxs-lookup"><span data-stu-id="d30cf-114">A new row appears in the grid.</span></span>  
  
4.  <span data-ttu-id="d30cf-115">В списке **Группировать по** введите или выберите поле для группирования.</span><span class="sxs-lookup"><span data-stu-id="d30cf-115">In the **Group on** list, type or select the field to group.</span></span>  
  
5.  <span data-ttu-id="d30cf-116">Щелкните **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="d30cf-116">Click **Advanced**.</span></span>  
  
6.  <span data-ttu-id="d30cf-117">В поле **Рекурсивный родитель** введите или выберите поле для группирования.</span><span class="sxs-lookup"><span data-stu-id="d30cf-117">In the **Recursive Parent** list, enter or select the field to group on.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="d30cf-118">Запустите отчет.</span><span class="sxs-lookup"><span data-stu-id="d30cf-118">Run the report.</span></span> <span data-ttu-id="d30cf-119">Отчет выведет группу рекурсивной иерархии, хотя и не выделит иерархию с помощью отступов.</span><span class="sxs-lookup"><span data-stu-id="d30cf-119">The report displays the recursive hierarchy group, although there is no indent to show the hierarchy</span></span>  
  
### <a name="to-format-a-recursive-hierarchy-group-with-indent-levels"></a><span data-ttu-id="d30cf-120">Форматирование группы рекурсивной иерархии с помощью отступов</span><span class="sxs-lookup"><span data-stu-id="d30cf-120">To format a recursive hierarchy group with indent levels</span></span>  
  
1.  <span data-ttu-id="d30cf-121">Щелкните текстовое поле, содержащее поле, к которому нужно добавить уровни отступа для вывода формата иерархии.</span><span class="sxs-lookup"><span data-stu-id="d30cf-121">Click the text box that contains the field to which you want to add indent levels to display a hierarchy format.</span></span> <span data-ttu-id="d30cf-122">Свойства этого текстового поля отобразятся на панели «Свойства».</span><span class="sxs-lookup"><span data-stu-id="d30cf-122">The properties for the text box appear in the Properties pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d30cf-123">Если панель "Свойства" не отображается, щелкните **Свойства** на вкладке **Вид** .</span><span class="sxs-lookup"><span data-stu-id="d30cf-123">If you do not see the Properties pane, click **Properties** on the **View** tab.</span></span>  
  
2.  <span data-ttu-id="d30cf-124">На панели Свойства разверните `Padding` узел, щелкните **слева**и в раскрывающемся списке выберите **\<Expression...>** .</span><span class="sxs-lookup"><span data-stu-id="d30cf-124">In the Properties pane, expand the `Padding` node, click **Left**, and from the drop-down list, select **\<Expression...>**.</span></span>  
  
3.  <span data-ttu-id="d30cf-125">На панели «Выражение» введите следующее выражение:</span><span class="sxs-lookup"><span data-stu-id="d30cf-125">In the Expression pane, type the following expression:</span></span>  
  
     `=CStr(2 + (Level()*10)) + "pt"`  
  
     <span data-ttu-id="d30cf-126">Для свойств заполнения необходимо указать строку в формате *nnyy*, где *nn* — число, а *yy* — единица измерения.</span><span class="sxs-lookup"><span data-stu-id="d30cf-126">The Padding properties all require a string in the format *nnyy*, where *nn* is a number and *yy* is the unit of measure.</span></span> <span data-ttu-id="d30cf-127">Приведенное выражение создает строку, в которой используется функция `Level` для увеличения отступа в зависимости от уровня рекурсии.</span><span class="sxs-lookup"><span data-stu-id="d30cf-127">The example expression builds a string that uses the `Level` function to increase the size of the padding based on recursion level.</span></span> <span data-ttu-id="d30cf-128">Например, строка с уровнем 1 будет иметь отступ в 12 пунктов (2 + (1\*10)), а строка с уровнем 3 — отступ в 32 пункта (2 + (3\*10)).</span><span class="sxs-lookup"><span data-stu-id="d30cf-128">For example, a row that has a level of 1 would result in a padding of (2 + (1\*10))=12pt, and a row that has a level of 3 would result in a padding of (2 + (3\*10))=32pt.</span></span> <span data-ttu-id="d30cf-129">Дополнительные сведения о `Level` функции см. в разделе [Level](report-builder-functions-level-function.md).</span><span class="sxs-lookup"><span data-stu-id="d30cf-129">For information about the `Level` function, see [Level](report-builder-functions-level-function.md).</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="d30cf-130">Запустите отчет.</span><span class="sxs-lookup"><span data-stu-id="d30cf-130">Run the report.</span></span> <span data-ttu-id="d30cf-131">Отчет выведет группированные данные в иерархическом представлении.</span><span class="sxs-lookup"><span data-stu-id="d30cf-131">The report displays a hierarchical view of the grouped data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d30cf-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="d30cf-132">See Also</span></span>  
 <span data-ttu-id="d30cf-133">[Создание групп рекурсивной иерархии (построитель отчетов и службы SSRS)](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d30cf-133">[Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d30cf-134">[Фильтрация, группирование и сортировка данных (построитель отчетов и службы SSRS)](filter-group-and-sort-data-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d30cf-134">[Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d30cf-135">[Справочник по агрегатным функциям (построитель отчетов и службы SSRS)](report-builder-functions-aggregate-functions-reference.md) </span><span class="sxs-lookup"><span data-stu-id="d30cf-135">[Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) </span></span>  
 <span data-ttu-id="d30cf-136">[Таблицы &#40;построитель отчетов и службы SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d30cf-136">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d30cf-137">[Матрицы &#40;построитель отчетов и службы SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d30cf-137">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d30cf-138">[Списки &#40;построитель отчетов и службы SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d30cf-138">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="d30cf-139">Таблицы, матрицы и списки (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d30cf-139">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
