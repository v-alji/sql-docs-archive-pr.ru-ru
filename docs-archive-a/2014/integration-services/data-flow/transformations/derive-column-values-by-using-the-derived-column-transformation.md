---
title: Получение значений столбцов с помощью преобразования "Производный столбец" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- columns [Integration Services]
- derived columns
- columns [Integration Services], values
- Derived Column transformation
ms.assetid: 28b07746-fc6f-42b2-b741-9de6fac3f29c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 837ec552144697b40cf649bc0403edfe4dc57a57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655281"
---
# <a name="derive-column-values-by-using-the-derived-column-transformation"></a><span data-ttu-id="abf59-102">Получение значений столбцов с помощью преобразования «Производный столбец»</span><span class="sxs-lookup"><span data-stu-id="abf59-102">Derive Column Values by Using the Derived Column Transformation</span></span>
  <span data-ttu-id="abf59-103">Чтобы добавить и настроить преобразование «Производный столбец», пакет уже должен содержать по крайней мере одну задачу потока данных и один источник.</span><span class="sxs-lookup"><span data-stu-id="abf59-103">To add and configure a Derived Column transformation, the package must already include at least one Data Flow task and one source.</span></span>  
  
 <span data-ttu-id="abf59-104">Преобразование «Производный столбец» использует выражения, чтобы обновить существующие значения или добавить значения в новые столбцы.</span><span class="sxs-lookup"><span data-stu-id="abf59-104">The Derived Column transformation uses expressions to update the values of existing or to add values to new columns.</span></span> <span data-ttu-id="abf59-105">Если выбрано заполнение новых столбцов, диалоговое окно **Редактор преобразования «Производный столбец»** вычисляет выражение и определяет метаданные для столбцов соответственно.</span><span class="sxs-lookup"><span data-stu-id="abf59-105">When you choose to add values to new columns, the **Derived Column Transformation Editor** dialog box evaluates the expression and defines the metadata of the columns accordingly.</span></span> <span data-ttu-id="abf59-106">Например, если выражение объединяет два столбца, каждый с типом данных DT_WSTR и длиной 50, и между двумя значениями столбцов задается пробел, новый столбец имеет тип DT_WSTR и длину 101.</span><span class="sxs-lookup"><span data-stu-id="abf59-106">For example, if an expression concatenates two columns-each with the DT_WSTR data type and a length of 50-with a space between the two column values, the new column has the DT_WSTR data type and a length of 101.</span></span> <span data-ttu-id="abf59-107">Можно обновить тип данных новых столбцов.</span><span class="sxs-lookup"><span data-stu-id="abf59-107">You can update the data type of new columns.</span></span> <span data-ttu-id="abf59-108">Единственное условие состоит в том, что тип данных должен соответствовать добавляемым данным.</span><span class="sxs-lookup"><span data-stu-id="abf59-108">The only requirement is that data type be compatible with the inserted data.</span></span> <span data-ttu-id="abf59-109">Например, диалоговое окно **Редактор преобразования «Производный столбец»** формирует ошибку проверки правильности при попытке присвоить значение типа date столбцу типа integer.</span><span class="sxs-lookup"><span data-stu-id="abf59-109">For example, the **Derived Column Transformation Editor** dialog box generates a validation error when you assign a date value to a column with an integer data type.</span></span> <span data-ttu-id="abf59-110">В зависимости от выбранного типа данных можно указать длину, точность, масштаб и кодовую страницу для столбца.</span><span class="sxs-lookup"><span data-stu-id="abf59-110">Depending on the data type that you selected, you can specify the length, precision, scale, and code page of the column.</span></span>  
  
### <a name="to-derive-column-values"></a><span data-ttu-id="abf59-111">Получение производных значений столбца</span><span class="sxs-lookup"><span data-stu-id="abf59-111">To derive column values</span></span>  
  
1.  <span data-ttu-id="abf59-112">В среде [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="abf59-112">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="abf59-113">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="abf59-113">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="abf59-114">Перейдите на вкладку **Поток данных** и из окна **Область элементов**перенесите преобразование «Производный столбец» в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="abf59-114">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the Derived Column transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="abf59-115">Соедините преобразование «Производный столбец» с потоком данных, перетащив соединитель от источника данных или предыдущего преобразования к текущему преобразованию «Производный столбец».</span><span class="sxs-lookup"><span data-stu-id="abf59-115">Connect the Derived Column transformation to the data flow by dragging the connector from the source or the previous transformation to the Derived Column transformation.</span></span>  
  
5.  <span data-ttu-id="abf59-116">Дважды щелкните преобразование «Производный столбец».</span><span class="sxs-lookup"><span data-stu-id="abf59-116">Double-click the Derived Column transformation.</span></span>  
  
6.  <span data-ttu-id="abf59-117">В окне **Редактор преобразования «Производный столбец»** постройте выражения для использования в качестве условий, перетащив необходимые переменные, столбцы, функции и операторы в столбец **Условие** сетки.</span><span class="sxs-lookup"><span data-stu-id="abf59-117">In the **Derived Column Transformation Editor** dialog box, build the expressions to use as conditions by dragging variables, columns, functions, and operators to the **Expression** column in the grid.</span></span> <span data-ttu-id="abf59-118">Вы можете также ввести выражение в столбец **Выражение** .</span><span class="sxs-lookup"><span data-stu-id="abf59-118">Alternatively, you can type the expression in the **Expression** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="abf59-119">Если выражение недопустимо, его текст выделяется, а в подсказке к столбцу появляется описание ошибки.</span><span class="sxs-lookup"><span data-stu-id="abf59-119">If the expression is not valid, the expression text is highlighted and a ToolTip on the column describes the errors.</span></span>  
  
7.  <span data-ttu-id="abf59-120">В списке **Производный столбец** выберите **\<add as new column>** для записи результата вычисления выражения в новый столбец или выберите существующий столбец для обновления его с использованием результата вычисления.</span><span class="sxs-lookup"><span data-stu-id="abf59-120">In the **Derived Column** list, select **\<add as new column>** to write the evaluation result of the expression to a new column, or select an existing column to update with the evaluation result.</span></span>  
  
     <span data-ttu-id="abf59-121">Если выбрано использование нового столбца, диалоговое окно **Редактор преобразования «Производный столбец»** вычисляет выражение и присваивает тип данных столбцу в зависимости от типа данных, длины, точности, масштаба и кодовой страницы.</span><span class="sxs-lookup"><span data-stu-id="abf59-121">If you chose to use a new column, the **Derived Column Transformation Editor** dialog box evaluates the expression and assigns a data type to the column, depending on the data type, length, precisions, scale, and code page.</span></span>  
  
8.  <span data-ttu-id="abf59-122">При использовании нового столбца выберите тип данных из списка **Тип данных** .</span><span class="sxs-lookup"><span data-stu-id="abf59-122">If using a new column, select a data type in the **Data Type** list.</span></span> <span data-ttu-id="abf59-123">Если требуется, в зависимости от выбранного типа данных обновите значения в столбцах **Длина**, **Точность**, **Масштаб**и **Кодовая страница** .</span><span class="sxs-lookup"><span data-stu-id="abf59-123">Depending on the selected data type, optionally update the values in the **Length**, **Precision**, **Scale**, and **Code Page** columns.</span></span> <span data-ttu-id="abf59-124">Изменить метаданные существующих столбцов невозможно.</span><span class="sxs-lookup"><span data-stu-id="abf59-124">Metadata of existing columns cannot be changed.</span></span>  
  
9. <span data-ttu-id="abf59-125">При необходимости измените значения в столбце **Имя производного столбца** .</span><span class="sxs-lookup"><span data-stu-id="abf59-125">Optionally, modify the values in the **Derived Column Name** column.</span></span>  
  
10. <span data-ttu-id="abf59-126">Для настройки вывода ошибок нажмите **Настройка вывода ошибок**.</span><span class="sxs-lookup"><span data-stu-id="abf59-126">To configure the error output, click **Configure Error Output**.</span></span> <span data-ttu-id="abf59-127">Дополнительные сведения см. в разделе [Настройка вывода ошибок в компоненте потока данных](../../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="abf59-127">For more information, see [Configure an Error Output in a Data Flow Component](../../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
11. <span data-ttu-id="abf59-128">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="abf59-128">Click **OK**.</span></span>  
  
12. <span data-ttu-id="abf59-129">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="abf59-129">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abf59-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="abf59-130">See Also</span></span>  
 <span data-ttu-id="abf59-131">[Derived Column Transformation](derived-column-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="abf59-131">[Derived Column Transformation](derived-column-transformation.md) </span></span>  
 <span data-ttu-id="abf59-132">[Типы данных служб Integration Services](../integration-services-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="abf59-132">[Integration Services Data Types](../integration-services-data-types.md) </span></span>  
 <span data-ttu-id="abf59-133">[Преобразования служб Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="abf59-133">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="abf59-134">[Пути служб Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="abf59-134">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 <span data-ttu-id="abf59-135">[Задача потока данных](../../control-flow/data-flow-task.md) </span><span class="sxs-lookup"><span data-stu-id="abf59-135">[Data Flow Task](../../control-flow/data-flow-task.md) </span></span>  
 [<span data-ttu-id="abf59-136">Выражения служб Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="abf59-136">Integration Services &#40;SSIS&#41; Expressions</span></span>](../../expressions/integration-services-ssis-expressions.md)  
  
  
