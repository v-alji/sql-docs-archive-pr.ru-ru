---
title: Скрытие элемента (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.shared.visibility.f1
- "10503"
ms.assetid: 9d78f8de-959b-456f-8947-687fa6e2ba91
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 56e834204698369687528c622cf6167a492766f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657550"
---
# <a name="hide-an-item-report-builder-and-ssrs"></a><span data-ttu-id="3bb61-102">Скрытие элемента (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="3bb61-102">Hide an Item (Report Builder and SSRS)</span></span>
  <span data-ttu-id="3bb61-103">Если необходимо скрывать элемент в зависимости от параметра отчета или другого указанного выражения, то можно настроить видимость для этого элемента отчета.</span><span class="sxs-lookup"><span data-stu-id="3bb61-103">Set the visibility of a report item when you want to conditionally hide an item based on a report parameter or some other expression that you specify.</span></span>

 <span data-ttu-id="3bb61-104">Отчет можно разработать таким образом, чтобы позволить пользователям переключать видимость элементов отчета, щелкая текстовые поля, например, для вывода отчета с углубленной детализацией.</span><span class="sxs-lookup"><span data-stu-id="3bb61-104">You can also design a report to allow the user to toggle the visibility of report items based on clicking text boxes in the report, for example, for a drilldown report.</span></span> <span data-ttu-id="3bb61-105">Дополнительные сведения см. в разделе [Добавление действия "Развернуть" или "Свернуть" к элементу (построитель отчетов и службы SSRS)](../report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3bb61-105">For more information, see [Add an Expand or Collapse Action to an Item &#40;Report Builder and SSRS&#41;](../report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md).</span></span>

 <span data-ttu-id="3bb61-106">В следующих процедурах показывается, как можно скрыть или отобразить элемент отчета, готового для просмотра, на основе значения константы или выражения.</span><span class="sxs-lookup"><span data-stu-id="3bb61-106">The following procedures describe how to show or hide a report item in a rendered report based on a constant or an expression.</span></span>

> [!NOTE]
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]

### <a name="to-hide-a-report-item"></a><span data-ttu-id="3bb61-107">Скрытие элемента отчета</span><span class="sxs-lookup"><span data-stu-id="3bb61-107">To hide a report item</span></span>

1.  <span data-ttu-id="3bb61-108">В представлении конструктора отчетов щелкните правой кнопкой мыши элемент отчета и откройте страницу **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="3bb61-108">In report design view, right-click the report item and open its **Properties** page.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="3bb61-109">Для выбора целой таблицы или матричной области данных щелкните в области данных, чтобы выбрать ее, затем щелкните правой кнопкой мыши маркер строки или столбца либо угловой маркер и выберите пункт **Свойства табликса**.</span><span class="sxs-lookup"><span data-stu-id="3bb61-109">To select an entire table or matrix data region, click in the data region to select it, right-click a row, column, or corner handle, and then click **Tablix Properties**.</span></span>

2.  <span data-ttu-id="3bb61-110">Нажмите кнопку **видимость.**</span><span class="sxs-lookup"><span data-stu-id="3bb61-110">Click **Visibility.**</span></span>

3.  <span data-ttu-id="3bb61-111">В поле **При первом запуске отчета**укажите, следует ли скрыть элемент при первом просмотре отчета.</span><span class="sxs-lookup"><span data-stu-id="3bb61-111">In **When the report is initially run**, specify whether to hide the item when you first view the report:</span></span>

    -   <span data-ttu-id="3bb61-112">Чтобы отобразить элемент, щелкните **Показать**.</span><span class="sxs-lookup"><span data-stu-id="3bb61-112">To display the item, click **Show**.</span></span>

    -   <span data-ttu-id="3bb61-113">Чтобы скрыть его, щелкните **Скрыть**.</span><span class="sxs-lookup"><span data-stu-id="3bb61-113">To hide the item, click **Hide**.</span></span>

    -   <span data-ttu-id="3bb61-114">Чтобы указать выражение, которое будет вычисляться во время выполнения, щелкните **Отображать или скрывать в зависимости от выражения**.</span><span class="sxs-lookup"><span data-stu-id="3bb61-114">To specify an expression that is evaluated at run-time, click **Show or hide based on an expression**.</span></span> <span data-ttu-id="3bb61-115">Введите выражение или нажмите кнопку (**fx**), чтобы создать выражение в диалоговом окне **Выражение** .</span><span class="sxs-lookup"><span data-stu-id="3bb61-115">Type the expression or click the expression (**fx**) button to create the expression in the **Expression** dialog box.</span></span>

        > [!NOTE]
        >  <span data-ttu-id="3bb61-116">Когда вы определяете выражения для видимости, вы настраиваете свойство Hidden элемента отчета, как показано на следующем изображении.</span><span class="sxs-lookup"><span data-stu-id="3bb61-116">When you specify an expression for visibility, you are setting the Hidden property of the report item, as shown in the following image.</span></span> <span data-ttu-id="3bb61-117">Данное вычисляемое выражение отображает элемент отчета, если значение равно False и скрывает его, если значение равно True.</span><span class="sxs-lookup"><span data-stu-id="3bb61-117">The evaluated expression shows the report item when the value is False, and hides the report item when the value is True.</span></span> 
        > <span data-ttu-id="3bb61-118">![Свойства_Диалоговое окно "Видимость" и свойство Hidden](../media/hiddenproperty-propertiesvisibility.png "Свойства_Диалоговое окно "Видимость" и свойство Hidden")</span><span class="sxs-lookup"><span data-stu-id="3bb61-118">![Properties_Visibility dialog and Hidden property](../media/hiddenproperty-propertiesvisibility.png "Properties_Visibility dialog and Hidden property")</span></span>

4.  <span data-ttu-id="3bb61-119">Щелкните дважды **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3bb61-119">Click **OK** twice.</span></span>

### <a name="to-hide-static-rows-in-a-table-matrix-or-list"></a><span data-ttu-id="3bb61-120">Скрытие статических строк в таблице, матрице или списке</span><span class="sxs-lookup"><span data-stu-id="3bb61-120">To hide static rows in a table, matrix, or list</span></span>

1.  <span data-ttu-id="3bb61-121">В представлении конструктора отчетов щелкните таблицу, матрицу или список, чтобы показать маркеры строк и столбцов.</span><span class="sxs-lookup"><span data-stu-id="3bb61-121">In report design view, click the table, matrix, or list to display the row and column handles.</span></span>

2.  <span data-ttu-id="3bb61-122">Щелкните правой кнопкой мыши маркер строки и выберите пункт **Видимость строки**.</span><span class="sxs-lookup"><span data-stu-id="3bb61-122">Right-click the row handle, and then click **Row Visibility**.</span></span> <span data-ttu-id="3bb61-123">Откроется диалоговое окно **Видимость строки** .</span><span class="sxs-lookup"><span data-stu-id="3bb61-123">The **Row Visibility** dialog box opens.</span></span>

3.  <span data-ttu-id="3bb61-124">Чтобы настроить видимость, выполните шаги 3 и 4 первой процедуры.</span><span class="sxs-lookup"><span data-stu-id="3bb61-124">To set the visibility, follow steps 3 and 4 in the first procedure.</span></span>

### <a name="to-hide-static-columns-in-a-table-matrix-or-list"></a><span data-ttu-id="3bb61-125">Скрытие статических столбцов в таблице, матрице или списке</span><span class="sxs-lookup"><span data-stu-id="3bb61-125">To hide static columns in a table, matrix, or list</span></span>

1.  <span data-ttu-id="3bb61-126">В режиме конструктора выберите таблицу, матрицу или список, чтобы показать маркеры строк и столбцов.</span><span class="sxs-lookup"><span data-stu-id="3bb61-126">In Design view, select the table, matrix, or list to display the row and column handles.</span></span>

2.  <span data-ttu-id="3bb61-127">Щелкните правой кнопкой мыши маркер столбца и выберите пункт **Видимость столбца**.</span><span class="sxs-lookup"><span data-stu-id="3bb61-127">Right-click the column handle, and then click **Column Visibility**.</span></span>

3.  <span data-ttu-id="3bb61-128">В диалоговом окне **Видимость столбца** повторите шаги 3 и 4 первой процедуры.</span><span class="sxs-lookup"><span data-stu-id="3bb61-128">In the **Column Visibility** dialog box, follow steps 3 and 4 in the first procedure.</span></span>

## <a name="see-also"></a><span data-ttu-id="3bb61-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="3bb61-129">See Also</span></span>
 <span data-ttu-id="3bb61-130">[Действие углубленной детализации &#40;построитель отчетов и SSRS&#41;](../report-design/drilldown-action-report-builder-and-ssrs.md) [Добавить действие "развернуть" или "Свернуть" в элемент &#40;ПОСТРОИТЕЛЬ отчетов и службы SSRS&#41;,](../report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md) [примеры](../report-design/expression-examples-report-builder-and-ssrs.md) &#40;построитель отчетов и службы SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3bb61-130">[Drilldown Action &#40;Report Builder and SSRS&#41;](../report-design/drilldown-action-report-builder-and-ssrs.md) [Add an Expand or Collapse Action to an Item &#40;Report Builder and SSRS&#41;](../report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md) [Expression Examples &#40;Report Builder and SSRS&#41;](../report-design/expression-examples-report-builder-and-ssrs.md)</span></span>


