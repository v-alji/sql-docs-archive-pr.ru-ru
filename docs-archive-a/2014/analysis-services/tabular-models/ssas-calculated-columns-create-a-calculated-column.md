---
title: Создание вычисляемого столбца (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.as.daxref.CreataCalculatedColumn.f1
ms.assetid: 59440510-2d76-41dc-9b55-edc15259f9da
author: minewiskan
ms.author: owend
ms.openlocfilehash: cdb56ffb2b42aa8225b7eff76b11315ea511fd81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727354"
---
# <a name="create-a-calculated-column-ssas-tabular"></a><span data-ttu-id="56773-102">Создание вычисляемого столбца (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="56773-102">Create a Calculated Column (SSAS Tabular)</span></span>
  <span data-ttu-id="56773-103">Вычисляемые столбцы позволяют добавлять новые данные в модель.</span><span class="sxs-lookup"><span data-stu-id="56773-103">Calculated columns allow you to add new data to your model.</span></span> <span data-ttu-id="56773-104">Вместо того чтобы вставлять или импортировать значения в столбец, необходимо создать формулу DAX, определяющую значения на уровне строк столбца.</span><span class="sxs-lookup"><span data-stu-id="56773-104">Instead of pasting or importing values into the column, you create a DAX formula that defines the column's row level values.</span></span> <span data-ttu-id="56773-105">Значения для каждой из строк вычисляемого столбца вычисляются и распространяются после создания допустимой формулы и нажатия клавиши ВВОД.</span><span class="sxs-lookup"><span data-stu-id="56773-105">The values in each row of a calculated column are calculated and populated when you create a valid formula and then click ENTER.</span></span> <span data-ttu-id="56773-106">После этого можно добавлять вычисляемый столбец в аналитическое приложение или приложение для создания отчетов, как и любой другой столбец данных.</span><span class="sxs-lookup"><span data-stu-id="56773-106">The calculated column can then be added to a reporting or analysis application just as would any other column of data.</span></span> <span data-ttu-id="56773-107">В этом разделе показано, как создать вычисляемый столбец с помощью строки формул DAX в конструкторе моделей.</span><span class="sxs-lookup"><span data-stu-id="56773-107">This topic describes how to create a new calculated column by using the DAX formula bar in the model designer.</span></span>  
  
#### <a name="to-create-a-new-calculated-column"></a><span data-ttu-id="56773-108">Создание вычисляемого столбца</span><span class="sxs-lookup"><span data-stu-id="56773-108">To create a new calculated column</span></span>  
  
1.  <span data-ttu-id="56773-109">В представлении «Данные» конструктора моделей выберите таблицу, в которую необходимо добавить вычисляемый столбец, и в меню **Столбец** выберите пункт **Добавить столбец**.</span><span class="sxs-lookup"><span data-stu-id="56773-109">In the model designer, in Data View, select the table to which you want to add a calculated column, then click the **Column** menu, and then click **Add Column**.</span></span>  
  
     <span data-ttu-id="56773-110">Будет выделен пункт**Добавить столбец** над пустым крайним правым столбцом, и курсор переместится в строку формул.</span><span class="sxs-lookup"><span data-stu-id="56773-110">**Add Column** is highlighted over the empty rightmost column, and the cursor moves to the formula bar.</span></span>  
  
     <span data-ttu-id="56773-111">Чтобы создать новый столбец между двумя существующими, щелкните существующий столбец правой кнопкой мыши и выберите пункт **Вставить столбец**.</span><span class="sxs-lookup"><span data-stu-id="56773-111">To create a new column between two existing columns, right-click an existing column, and then click **Insert Column**.</span></span>  
  
2.  <span data-ttu-id="56773-112">В строке формул выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="56773-112">In the formula bar, do one of the following:</span></span>  
  
    -   <span data-ttu-id="56773-113">Введите знак равенства, а затем формулу.</span><span class="sxs-lookup"><span data-stu-id="56773-113">Type an equal sign followed by a formula.</span></span>  
  
    -   <span data-ttu-id="56773-114">Введите знак равенства, а затем функцию DAX, аргументы и параметры для этой функции.</span><span class="sxs-lookup"><span data-stu-id="56773-114">Type an equal sign, followed by a DAX function, followed by arguments and parameters as required by the function.</span></span>  
  
    -   <span data-ttu-id="56773-115">Нажмите кнопку функции (**fx**), а затем в диалоговом окне **Вставка функции** выберите категорию и функцию и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="56773-115">Click the function button (**fx**), then in the **Insert Function** dialog box, select a category and function, and then click **OK**.</span></span> <span data-ttu-id="56773-116">В строке формул введите остальные аргументы и параметры для функции.</span><span class="sxs-lookup"><span data-stu-id="56773-116">In the formula bar, type the remaining arguments and parameters as required by the function.</span></span>  
  
3.  <span data-ttu-id="56773-117">Нажмите клавишу ВВОД, чтобы принять формулу.</span><span class="sxs-lookup"><span data-stu-id="56773-117">Press ENTER to accept the formula.</span></span>  
  
     <span data-ttu-id="56773-118">Весь столбец будет заполнен формулой, и для каждой строки будет вычислено значение.</span><span class="sxs-lookup"><span data-stu-id="56773-118">The entire column is populated with the formula, and a value is calculated for each row.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="56773-119">Можно воспользоваться функцией автозаполнения формул DAX в середине существующей формулы с вложенными функциями.</span><span class="sxs-lookup"><span data-stu-id="56773-119">You can use DAX Formula AutoComplete in the middle of an existing formula with nested functions.</span></span> <span data-ttu-id="56773-120">Текст, расположенный непосредственно перед точкой вставки, используется для отображения значений раскрывающегося списка, а остальной текст остается без изменений.</span><span class="sxs-lookup"><span data-stu-id="56773-120">The text immediately before the insertion point is used to display values in the drop-down list, and all of the text after the insertion point remains unchanged.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56773-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="56773-121">See Also</span></span>  
 <span data-ttu-id="56773-122">[Вычисляемые столбцы &#40;табличные&#41;SSAS](ssas-calculated-columns.md) </span><span class="sxs-lookup"><span data-stu-id="56773-122">[Calculated Columns &#40;SSAS Tabular&#41;](ssas-calculated-columns.md) </span></span>  
 [<span data-ttu-id="56773-123">Меры (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="56773-123">Measures &#40;SSAS Tabular&#41;</span></span>](measures-ssas-tabular.md)  
  
  
