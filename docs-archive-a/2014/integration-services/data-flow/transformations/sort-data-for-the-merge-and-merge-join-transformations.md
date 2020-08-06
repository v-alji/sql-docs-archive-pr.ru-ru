---
title: Сортировка данных для преобразований "Слияние" и "Соединение слиянием" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- sort attributes [Integration Services]
- output columns [Integration Services]
ms.assetid: 22ce3f5d-8a88-4423-92c2-60a8f82cd4fd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7bb4e91ad84c6baa52e1d7fb4b0104d835b7e4cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728498"
---
# <a name="sort-data-for-the-merge-and-merge-join-transformations"></a><span data-ttu-id="bf1a3-102">Сортировка данных для преобразований «Слияние» и «Соединение слиянием»</span><span class="sxs-lookup"><span data-stu-id="bf1a3-102">Sort Data for the Merge and Merge Join Transformations</span></span>
  <span data-ttu-id="bf1a3-103">В службах [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]для преобразований «Слияние» и «Соединение слиянием» необходимы отсортированные входные данные.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-103">In [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], the Merge and Merge Join transformations require sorted data for their inputs.</span></span> <span data-ttu-id="bf1a3-104">Входные данные должны быть отсортированы физически, а параметры сортировки должны быть установлены на выходы и выходные столбцы источника или вышестоящего преобразования.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-104">The input data must be sorted physically, and sort options must be set on the outputs and the output columns in the source or in the upstream transformation.</span></span> <span data-ttu-id="bf1a3-105">Если параметры сортировки определяют, что данные отсортированы, но данные в действительности не отсортированы, операция слияния или соединения слиянием может дать непредвиденные результаты.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-105">If the sort options indicate that the data is sorted, but the data is not actually sorted, the results of the merge or merge join operation are unpredictable.</span></span>  
  
## <a name="sorting-the-data"></a><span data-ttu-id="bf1a3-106">Сортировка данных</span><span class="sxs-lookup"><span data-stu-id="bf1a3-106">Sorting the Data</span></span>  
 <span data-ttu-id="bf1a3-107">Сортировку данных можно выполнить одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-107">You can sort this data by using one of the following methods:</span></span>  
  
-   <span data-ttu-id="bf1a3-108">В источнике — в инструкции, с помощью которой загружаются данные, — использовать предложение ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-108">In the source, use an ORDER BY clause in the statement that is used to load the data.</span></span>  
  
-   <span data-ttu-id="bf1a3-109">В потоке данных преобразование «Сортировка» должно предшествовать преобразованию «Слияние» или «Соединение слиянием».</span><span class="sxs-lookup"><span data-stu-id="bf1a3-109">In the data flow, insert a Sort transformation before the Merge or Merge Join transformation.</span></span>  
  
 <span data-ttu-id="bf1a3-110">Если данные являются строковыми, то и преобразование «Слияние», и преобразование «Соединение слиянием» ожидают, что строковые значения отсортированы с использованием параметров сортировки Windows.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-110">If the data is string data, both the Merge and Merge Join transformations expect the string values to have been sorted by using Windows collation.</span></span> <span data-ttu-id="bf1a3-111">Чтобы строковые значения передавались преобразованиям «Слияние» и «Соединение слиянием», отсортированным с помощью параметров сортировки Windows, примените следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-111">To provide string values to the Merge and Merge Join transformations that are sorted by using Windows collation, use the following procedure.</span></span>  
  
#### <a name="to-provide-string-values-that-are-sorted-by-using-windows-collation"></a><span data-ttu-id="bf1a3-112">Чтобы передавались строковые значения, отсортированные с помощью параметров сортировки Windows</span><span class="sxs-lookup"><span data-stu-id="bf1a3-112">To provide string values that are sorted by using Windows collation</span></span>  
  
-   <span data-ttu-id="bf1a3-113">Используйте преобразование «Сортировка» для сортировки данных.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-113">Use a Sort transformation to sort the data.</span></span>  
  
     <span data-ttu-id="bf1a3-114">Преобразование «Сортировка» использует параметры сортировки Windows для упорядочения строковых значений.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-114">The Sort transformation uses Windows collation to sort string values.</span></span>  
  
     <span data-ttu-id="bf1a3-115">-или-</span><span class="sxs-lookup"><span data-stu-id="bf1a3-115">-or-</span></span>  
  
-   <span data-ttu-id="bf1a3-116">Используйте оператор языка Transact-SQL CAST для преобразования значений `varchar` в значения `nvarchar`, а затем с помощью предложения языка Transact-SQL ORDER BY отсортируйте эти данные.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-116">Use the Transact-SQL CAST operator to first cast `varchar` values to `nvarchar` values, and then use the Transact-SQL ORDER BY clause to sort the data.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="bf1a3-117">Нельзя использовать одно предложение ORDER BY, поскольку для сортировки строковых значений оно использует параметры сортировки [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bf1a3-117">You cannot use the ORDER BY clause alone because the ORDER BY clause uses a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] collation to sort string values.</span></span> <span data-ttu-id="bf1a3-118">Применение параметров сортировки [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , которые отличаются от параметров сортировки Windows порядком сортировки, может привести к тому, что преобразование «Слияние» или «Соединение слиянием» сформирует непредвиденные результаты.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-118">The use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] collation might result in a different sort order than Windows collation, which can cause the Merge or Merge Join transformation to produce unexpected results.</span></span>  
  
## <a name="setting-sort-options-on-the-data"></a><span data-ttu-id="bf1a3-119">Настройка параметров сортировки данных</span><span class="sxs-lookup"><span data-stu-id="bf1a3-119">Setting Sort Options on the Data</span></span>  
 <span data-ttu-id="bf1a3-120">Есть два важных свойства сортировки, которые необходимо задать для источника или вышестоящего преобразования, которые предоставляют данные для преобразования «Слияние» или «Соединение слиянием».</span><span class="sxs-lookup"><span data-stu-id="bf1a3-120">There are two important sort properties that must be set for the source or upstream transformation that supplies data to the Merge and Merge Join transformations:</span></span>  
  
-   <span data-ttu-id="bf1a3-121">Свойство `IsSorted` выхода показывает, были ли данные отсортированы.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-121">The `IsSorted` property of the output that indicates whether the data has been sorted.</span></span> <span data-ttu-id="bf1a3-122">Это свойство должно иметь значение `True`.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-122">This property must be set to `True`.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="bf1a3-123">Установка свойства `IsSorted` в значение `True` не приводит к сортировке данных.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-123">Setting the value of the `IsSorted` property to `True` does not sort the data.</span></span> <span data-ttu-id="bf1a3-124">Это свойство только указывает компонентам нисходящего потока, что данные раньше были отсортированы.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-124">This property only provides a hint to downstream components that the data has been previously sorted.</span></span>  
  
-   <span data-ttu-id="bf1a3-125">Свойство `SortKeyPosition` выходных столбцов показывает, отсортирован ли столбец, порядок сортировки и последовательность, в которой сортируется несколько столбцов.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-125">The `SortKeyPosition` property of output columns that indicates whether a column is sorted, the column's sort order, and the sequence in which multiple columns are sorted.</span></span> <span data-ttu-id="bf1a3-126">Это свойство должно быть задано для каждого столбца отсортированных данных.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-126">This property must be set for each column of sorted data.</span></span>  
  
 <span data-ttu-id="bf1a3-127">При сортировке данных с помощью преобразования «Сортировка» это преобразование задает оба свойства требуемым образом для преобразования «Слияние» или «Соединение слиянием».</span><span class="sxs-lookup"><span data-stu-id="bf1a3-127">If you use a Sort transformation to sort the data, the Sort transformation sets both of these properties as required by the Merge or Merge Join transformation.</span></span> <span data-ttu-id="bf1a3-128">То есть преобразование «Сортировка» задает для свойства `IsSorted` своего выхода значение `True` и задает свойство `SortKeyPosition` своих выходных столбцов.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-128">That is, the Sort transformation sets the `IsSorted` property of its output to `True`, and sets the `SortKeyPosition` properties of its output columns.</span></span>  
  
 <span data-ttu-id="bf1a3-129">Однако если не отсортировать данные с помощью преобразования «Сортировка», то придется задавать эти свойства вручную на источнике или в вышестоящем преобразовании.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-129">However, if you do not use a Sort transformation to sort the data, you must set these sort properties manually on the source or the upstream transformation.</span></span> <span data-ttu-id="bf1a3-130">С помощью следующей процедуры можно вручную настроить эти свойства на источнике или в вышестоящем преобразовании.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-130">To manually set the sort properties on the source or upstream transformation, use the following procedure.</span></span>  
  
#### <a name="to-manually-set-sort-attributes-on-a-source-or-transformation-component"></a><span data-ttu-id="bf1a3-131">Задание атрибутов сортировки вручную на источнике или в компоненте преобразования</span><span class="sxs-lookup"><span data-stu-id="bf1a3-131">To manually set sort attributes on a source or transformation component</span></span>  
  
1.  <span data-ttu-id="bf1a3-132">В среде [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-132">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="bf1a3-133">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-133">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="bf1a3-134">Найдите на вкладке **Поток данных** соответствующий источник или вышестоящее преобразование или перетащите его из **области элементов** в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-134">On the **Data Flow** tab, locate the appropriate source or upstream transformation, or drag it from the **Toolbox** to the design surface.</span></span>  
  
4.  <span data-ttu-id="bf1a3-135">Щелкните компонент правой кнопкой мыши и выберите пункт **Показать расширенный редактор**.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-135">Right-click the component and click **Show Advanced Editor**.</span></span>  
  
5.  <span data-ttu-id="bf1a3-136">Щелкните вкладку **Свойства входов и выходов** .</span><span class="sxs-lookup"><span data-stu-id="bf1a3-136">Click the **Input and Output Properties** tab.</span></span>  
  
6.  <span data-ttu-id="bf1a3-137">Щелкните \*\* \<component name> выходные данные\*\*и задайте `IsSorted` для свойства значение `True` .</span><span class="sxs-lookup"><span data-stu-id="bf1a3-137">Click **\<component name> Output**, and set the `IsSorted` property to `True`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bf1a3-138">Если пользователь вручную задаст для свойства `IsSorted` выходных данных значение `True`, а данные не сортированы, то при выполнении пакета в последующих преобразованиях «Соединение слиянием» и «Слияние» могут возникнуть отсутствующие или недопустимые сравнения данных.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-138">If you manually set the `IsSorted` property of the output to `True` and the data is not sorted, there might be missing data or bad data comparisons in the downstream Merge or Merge Join transformation when you run the package.</span></span>  
  
7.  <span data-ttu-id="bf1a3-139">Разверните элемент **Выходные столбцы**.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-139">Expand **Output Columns**.</span></span>  
  
8.  <span data-ttu-id="bf1a3-140">Щелкните столбец, который необходимо обозначить как отсортированный, и установите для его свойства `SortKeyPosition` отличное от нуля целое число, следуя следующим правилам.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-140">Click the column that you want to indicate is sorted and set its `SortKeyPosition` property to a nonzero integer value by following these guidelines:</span></span>  
  
    -   <span data-ttu-id="bf1a3-141">Целое число должно представлять числовую последовательность начиная с 1 с добавлением по единице.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-141">The integer value must represent a numeric sequence, starting with 1 and incremented by 1.</span></span>  
  
    -   <span data-ttu-id="bf1a3-142">Положительные целые значения соответствуют возрастающему порядку сортировки.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-142">A positive integer value indicates an ascending sort order.</span></span>  
  
    -   <span data-ttu-id="bf1a3-143">Отрицательные целые значения соответствуют убывающему порядку сортировки.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-143">A negative integer value indicates a descending sort order.</span></span> <span data-ttu-id="bf1a3-144">Если задано отрицательное целое число, положение столбца в последовательности сортировки будет определять абсолютное значение этого числа.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-144">(If set to a negative number, the absolute value of the number determines the column's position in the sort sequence.)</span></span>  
  
    -   <span data-ttu-id="bf1a3-145">Значение 0 указывает на то, что столбец не отсортирован.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-145">The default value of 0 indicates that the column is not sorted.</span></span> <span data-ttu-id="bf1a3-146">Чтобы выходные столбцы не участвовали в сортировке, задайте значение 0.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-146">Leave the value of 0 for output columns that do not participate in the sort.</span></span>  
  
     <span data-ttu-id="bf1a3-147">В качестве примера настройки свойства `SortKeyPosition` рассмотрите приведенную ниже инструкцию Transact-SQL, которая загружает данные в источник.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-147">As an example of how to set the `SortKeyPosition` property, consider the following Transact-SQL statement that loads data in a source:</span></span>  
  
     `SELECT * FROM MyTable ORDER BY ColumnA, ColumnB DESC, ColumnC`  
  
     <span data-ttu-id="bf1a3-148">В этой инструкции свойство `SortKeyPosition` задается для каждого столбца следующим образом.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-148">For this statement, you would set the `SortKeyPosition` property for each column as follows:</span></span>  
  
    -   <span data-ttu-id="bf1a3-149">Задайте для свойства `SortKeyPosition` столбца ColumnA значение 1.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-149">Set the `SortKeyPosition` property of ColumnA to 1.</span></span> <span data-ttu-id="bf1a3-150">Это показывает, что столбец ColumnA является первым при сортировке, а сортировка производится по возрастанию.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-150">This indicates that ColumnA is the first column to be sorted and is sorted in ascending order.</span></span>  
  
    -   <span data-ttu-id="bf1a3-151">Задайте для свойства `SortKeyPosition` столбца ColumnB значение -2.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-151">Set the `SortKeyPosition` property of ColumnB to -2.</span></span> <span data-ttu-id="bf1a3-152">Это показывает, что столбец ColumnB является вторым при сортировке, а сортировка производится по убыванию.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-152">This indicates that ColumnB is the second column to be sorted and is sorted in descending order</span></span>  
  
    -   <span data-ttu-id="bf1a3-153">Задайте для свойства `SortKeyPosition` столбца ColumnC значение 3.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-153">Set the `SortKeyPosition` property of ColumnC to 3.</span></span> <span data-ttu-id="bf1a3-154">Это показывает, что столбец ColumnC является третьим при сортировке, а сортировка производится по возрастанию.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-154">This indicates that ColumnC is the third column to be sorted and is sorted in ascending order.</span></span>  
  
9. <span data-ttu-id="bf1a3-155">Повторите шаг 8 для каждого отсортированного столбца.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-155">Repeat step 8 for each sorted column.</span></span>  
  
10. <span data-ttu-id="bf1a3-156">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bf1a3-156">Click **OK**.</span></span>  
  
11. <span data-ttu-id="bf1a3-157">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="bf1a3-157">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf1a3-158">См. также:</span><span class="sxs-lookup"><span data-stu-id="bf1a3-158">See Also</span></span>  
 <span data-ttu-id="bf1a3-159">[Преобразование «Слияние»](merge-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="bf1a3-159">[Merge Transformation](merge-transformation.md) </span></span>  
 <span data-ttu-id="bf1a3-160">[Преобразование «Соединение слиянием»](merge-join-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="bf1a3-160">[Merge Join Transformation](merge-join-transformation.md) </span></span>  
 <span data-ttu-id="bf1a3-161">[Преобразования служб Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="bf1a3-161">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="bf1a3-162">[Пути служб Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="bf1a3-162">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 [<span data-ttu-id="bf1a3-163">Задача потока данных</span><span class="sxs-lookup"><span data-stu-id="bf1a3-163">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
