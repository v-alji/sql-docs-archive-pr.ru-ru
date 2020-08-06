---
title: Редактор преобразования "производный столбец" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.derivedcolumntransformation.f1
helpviewer_keywords:
- Derived Column Transformation Editor
ms.assetid: ff73923e-d245-43d8-bf24-af3bdc942e51
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 41a0f0dcd253473f78f2f38426b5fbd3d2ac2812
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667827"
---
# <a name="derived-column-transformation-editor"></a><span data-ttu-id="ed389-102">редактор преобразования «Производный столбец»</span><span class="sxs-lookup"><span data-stu-id="ed389-102">Derived Column Transformation Editor</span></span>
  <span data-ttu-id="ed389-103">Используйте диалоговое окно **Редактор преобразования «Производный столбец»** для создания выражений, которые заполняют новые или замещающие столбцы.</span><span class="sxs-lookup"><span data-stu-id="ed389-103">Use the **Derived Column Transformation Editor** dialog box to create expressions that populate new or replacement columns.</span></span>  
  
 <span data-ttu-id="ed389-104">Дополнительные сведения о преобразовании «Производный столбец» см. в разделе [Derived Column Transformation](data-flow/transformations/derived-column-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="ed389-104">To learn more about the Derived Column transformation, see [Derived Column Transformation](data-flow/transformations/derived-column-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ed389-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="ed389-105">Options</span></span>  
 <span data-ttu-id="ed389-106">**Переменные и столбцы**</span><span class="sxs-lookup"><span data-stu-id="ed389-106">**Variables and Columns**</span></span>  
 <span data-ttu-id="ed389-107">Создайте выражение, которое использует переменную или входной столбец, путем перетаскивания переменной или столбца из списка в существующую строку таблицы на панели внизу или в новую строку внизу списка.</span><span class="sxs-lookup"><span data-stu-id="ed389-107">Build an expression that uses a variable or an input column by dragging the variable or column from the list of available variables and columns to an existing table row in the pane below, or to a new row at the bottom of the list.</span></span>  
  
 <span data-ttu-id="ed389-108">**Функции и операторы**</span><span class="sxs-lookup"><span data-stu-id="ed389-108">**Functions and Operators**</span></span>  
 <span data-ttu-id="ed389-109">Создайте выражение, которое использует функцию или оператор, для расчета входных данных и прямых выходных данных, путем перетаскивания функций и операторов из списка на панель внизу.</span><span class="sxs-lookup"><span data-stu-id="ed389-109">Build an expression that uses a function or an operator to evaluate input data and direct output data by dragging functions and operators from the list to the pane below.</span></span>  
  
 <span data-ttu-id="ed389-110">**Имя производного столбца**</span><span class="sxs-lookup"><span data-stu-id="ed389-110">**Derived Column Name**</span></span>  
 <span data-ttu-id="ed389-111">Введите имя производного столбца.</span><span class="sxs-lookup"><span data-stu-id="ed389-111">Provide a derived column name.</span></span> <span data-ttu-id="ed389-112">По умолчанию используется нумерованный список производных столбцов, однако можно выбрать любое уникальное описательное имя.</span><span class="sxs-lookup"><span data-stu-id="ed389-112">The default is a numbered list of derived columns; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="ed389-113">**Производный столбец**</span><span class="sxs-lookup"><span data-stu-id="ed389-113">**Derived Column**</span></span>  
 <span data-ttu-id="ed389-114">Выберите из списка производный столбец.</span><span class="sxs-lookup"><span data-stu-id="ed389-114">Select a derived column from the list.</span></span> <span data-ttu-id="ed389-115">Выберите, добавлять ли производный столбец как новый выходной столбец или заменять данные существующего столбца.</span><span class="sxs-lookup"><span data-stu-id="ed389-115">Choose whether to add the derived column as a new output column, or to replace the data in an existing column.</span></span>  
  
 <span data-ttu-id="ed389-116">**Выражение**</span><span class="sxs-lookup"><span data-stu-id="ed389-116">**Expression**</span></span>  
 <span data-ttu-id="ed389-117">Введите выражение или создайте его с помощью перетаскивания из предыдущего списка доступных столбцов, переменных, функций и операторов.</span><span class="sxs-lookup"><span data-stu-id="ed389-117">Type an expression or build one by dragging from the previous list of available columns, variables, functions, and operators.</span></span>  
  
 <span data-ttu-id="ed389-118">Значение этого свойства можно задать с помощью выражения свойства.</span><span class="sxs-lookup"><span data-stu-id="ed389-118">The value of this property can be specified by using a property expression.</span></span>  
  
 <span data-ttu-id="ed389-119">**См. также**: [Выражения служб Integration Services (SSIS)](expressions/integration-services-ssis-expressions.md), [Операторы (выражение служб SSIS)](expressions/operators-ssis-expression.md) и [Функции (выражение служб SSIS)](expressions/functions-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="ed389-119">**Related topics**: [Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md), [Operators &#40;SSIS Expression&#41;](expressions/operators-ssis-expression.md), and [Functions &#40;SSIS Expression&#41;](expressions/functions-ssis-expression.md)</span></span>  
  
 <span data-ttu-id="ed389-120">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ed389-120">**Data Type**</span></span>  
 <span data-ttu-id="ed389-121">При добавлении данных в новый столбец диалоговое окно **Редактор преобразования "Производный столбец"** автоматически оценивает выражение и задает соответствующий тип данных.</span><span class="sxs-lookup"><span data-stu-id="ed389-121">If adding data to a new column, the **Derived Column TransformationEditor** dialog box automatically evaluates the expression and sets the data type appropriately.</span></span> <span data-ttu-id="ed389-122">Значение этого столбца доступно только для чтения.</span><span class="sxs-lookup"><span data-stu-id="ed389-122">The value of this column is read-only.</span></span> <span data-ttu-id="ed389-123">Дополнительные сведения см. в разделе [Integration Services Data Types](data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="ed389-123">For more information, see [Integration Services Data Types](data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="ed389-124">**Длина**</span><span class="sxs-lookup"><span data-stu-id="ed389-124">**Length**</span></span>  
 <span data-ttu-id="ed389-125">При добавлении данных в новый столбец диалоговое окно **Редактор преобразования "Производный столбец"** автоматически оценивает выражение и задает длину столбца для строковых данных.</span><span class="sxs-lookup"><span data-stu-id="ed389-125">If adding data to a new column, the **Derived Column TransformationEditor** dialog box automatically evaluates the expression and sets the column length for string data.</span></span> <span data-ttu-id="ed389-126">Значение этого столбца доступно только для чтения.</span><span class="sxs-lookup"><span data-stu-id="ed389-126">The value of this column is read-only.</span></span>  
  
 <span data-ttu-id="ed389-127">**Точность**</span><span class="sxs-lookup"><span data-stu-id="ed389-127">**Precision**</span></span>  
 <span data-ttu-id="ed389-128">При добавлении данных в новый столбец диалоговое окно **Редактор преобразования "Производный столбец"** автоматически задает точность для числовых данных, основываясь на типе данных.</span><span class="sxs-lookup"><span data-stu-id="ed389-128">If adding data to a new column, the **Derived Column TransformationEditor** dialog box automatically sets the precision for numeric data based on the data type.</span></span> <span data-ttu-id="ed389-129">Значение этого столбца доступно только для чтения.</span><span class="sxs-lookup"><span data-stu-id="ed389-129">The value of this column is read-only.</span></span>  
  
 <span data-ttu-id="ed389-130">**Масштаб**</span><span class="sxs-lookup"><span data-stu-id="ed389-130">**Scale**</span></span>  
 <span data-ttu-id="ed389-131">При добавлении данных в новый столбец диалоговое окно **Редактор преобразования "Производный столбец"** автоматически задает масштаб для числовых данных, основываясь на типе данных.</span><span class="sxs-lookup"><span data-stu-id="ed389-131">If adding data to a new column, the **Derived Column TransformationEditor** dialog box automatically sets the scale for numeric data based on the data type.</span></span> <span data-ttu-id="ed389-132">Значение этого столбца доступно только для чтения.</span><span class="sxs-lookup"><span data-stu-id="ed389-132">The value of this column is read-only.</span></span>  
  
 <span data-ttu-id="ed389-133">**Кодовая страница**</span><span class="sxs-lookup"><span data-stu-id="ed389-133">**Code Page**</span></span>  
 <span data-ttu-id="ed389-134">При добавлении данных в новый столбец диалоговое окно **Редактор преобразования "Производный столбец"** автоматически задает кодовую страницу для типа данных DT_STR.</span><span class="sxs-lookup"><span data-stu-id="ed389-134">If adding data to a new column, the **Derived Column TransformationEditor** dialog box automatically sets code page for the DT_STR data type.</span></span> <span data-ttu-id="ed389-135">Параметр **Кодовая страница**можно изменить.</span><span class="sxs-lookup"><span data-stu-id="ed389-135">You can update **Code Page**.</span></span>  
  
 <span data-ttu-id="ed389-136">**Настройка вывода ошибок**</span><span class="sxs-lookup"><span data-stu-id="ed389-136">**Configure error output**</span></span>  
 <span data-ttu-id="ed389-137">Укажите способ обработки ошибок в диалоговом окне [Настройка вывода ошибок](../../2014/integration-services/configure-error-output.md) .</span><span class="sxs-lookup"><span data-stu-id="ed389-137">Specify how to handle errors by using the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed389-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="ed389-138">See Also</span></span>  
 <span data-ttu-id="ed389-139">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="ed389-139">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="ed389-140">Получение значений столбцов с помощью преобразования «Производный столбец»</span><span class="sxs-lookup"><span data-stu-id="ed389-140">Derive Column Values by Using the Derived Column Transformation</span></span>](data-flow/transformations/derive-column-values-by-using-the-derived-column-transformation.md)  
  
  
