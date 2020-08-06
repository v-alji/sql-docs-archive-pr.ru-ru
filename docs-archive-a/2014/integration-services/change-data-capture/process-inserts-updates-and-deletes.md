---
title: Обработка операций вставки, обновления и удаления | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],processing data
ms.assetid: 13a84d21-2623-4efe-b442-4125a7a2d690
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 67f016aaf4f7f83c0fa506966c4e78f5b8fadef6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655295"
---
# <a name="process-inserts-updates-and-deletes"></a><span data-ttu-id="fc371-102">Обработка операций вставки, обновления и удаления</span><span class="sxs-lookup"><span data-stu-id="fc371-102">Process Inserts, Updates, and Deletes</span></span>
  <span data-ttu-id="fc371-103">В потоке данных пакета служб Integration Services, выполняющего добавочную загрузку информации об измененных данных, второй задачей является разделение вставок, обновлений и удалений.</span><span class="sxs-lookup"><span data-stu-id="fc371-103">In the data flow of an Integration Services package that performs an incremental load of change data, the second task is to separate inserts, updates, and deletes.</span></span> <span data-ttu-id="fc371-104">Затем можно использовать соответствующие команды, чтобы применить их к назначению.</span><span class="sxs-lookup"><span data-stu-id="fc371-104">Then, you can use appropriate commands to apply them to the destination.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fc371-105">Первой задачей в проектировании потока данных пакета, выполняющего добавочную загрузку измененных данных, является настройка исходного компонента, который запрашивает измененные данные.</span><span class="sxs-lookup"><span data-stu-id="fc371-105">The first task in designing the data flow of a package that performs an incremental load of change data is to configure the source component that runs the query that retrieves the change data.</span></span> <span data-ttu-id="fc371-106">Дополнительные сведения об этом компоненте см. в разделе [Получение и интерпретация измененных данных](retrieve-and-understand-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="fc371-106">For more information about this component, see [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md).</span></span> <span data-ttu-id="fc371-107">Описание общего процесса создания пакета, выполняющего добавочную загрузку информации об изменениях, см. в разделе [Система отслеживания измененных данных (SSIS)](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="fc371-107">For a description of the overall process for creating a package that performs an incremental load of change data, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="associating-friendly-values-to-separate-inserts-updates-and-deletes"></a><span data-ttu-id="fc371-108">Связывание понятных значений для разделения операций вставки, обновления и удаления</span><span class="sxs-lookup"><span data-stu-id="fc371-108">Associating Friendly Values to Separate Inserts, Updates, and Deletes</span></span>  
 <span data-ttu-id="fc371-109">В приведенном примере извлечения измененных данных функция **cdc.fn_cdc_get_net_changes_<экземпляр_отслеживания>** возвращает только столбец метаданных с именем **__$operation**.</span><span class="sxs-lookup"><span data-stu-id="fc371-109">In the example query that retrieves change data, the **cdc.fn_cdc_get_net_changes_<capture_instance>** function returns only the column of metadata named **__$operation**.</span></span> <span data-ttu-id="fc371-110">Этот столбец метаданных содержит порядковое значение, которое указывает операцию, вызвавшую изменение.</span><span class="sxs-lookup"><span data-stu-id="fc371-110">This metadata column contains an ordinal value that indicates which operation caused the change.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fc371-111">Дополнительные сведения о запросе, использующем вызовы функции **cdc.fn_cdc_get_net_changes_<экземпляр_отслеживания>** , см. в статье [Создание функции для получения информации об изменениях](create-the-function-to-retrieve-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="fc371-111">For more information about the query that uses calls the **cdc.fn_cdc_get_net_changes_<capture_instance>** function, see [Create the Function to Retrieve the Change Data](create-the-function-to-retrieve-the-change-data.md).</span></span>  
  
 <span data-ttu-id="fc371-112">Связать порядковое значение с соответствующей операцией сложнее, чем использовать мнемонический код операции.</span><span class="sxs-lookup"><span data-stu-id="fc371-112">Matching an ordinal value to its corresponding operation is not as easy as using a mnemonic of the operation.</span></span> <span data-ttu-id="fc371-113">Например, «D» может представлять операцию удаления, а «I» — операцию вставки.</span><span class="sxs-lookup"><span data-stu-id="fc371-113">For example, 'D' can easily represent a delete operation and 'I' represent an insert operation.</span></span> <span data-ttu-id="fc371-114">В примере запроса, созданном в разделе [Создание функции для получения измененных данных](create-the-function-to-retrieve-the-change-data.md), порядковое значение преобразуется в понятное строковое значение, которое возвращается в новом столбце.</span><span class="sxs-lookup"><span data-stu-id="fc371-114">The example query that was created in the topic, [Creating the Function to Retrieve the Change Data](create-the-function-to-retrieve-the-change-data.md), makes this conversion from an ordinal value to a friendly string value that is returned in a new column.</span></span> <span data-ttu-id="fc371-115">Это преобразование показано в следующем сегменте кода:</span><span class="sxs-lookup"><span data-stu-id="fc371-115">The following segment of code shows this conversion:</span></span>  
  
```  
select   
    ...  
    case __$operation  
        when 1 then 'D'  
        when 2 then 'I'  
        when 4 then 'U'  
        else null  
     end as CDC_OPERATION  
```  
  
## <a name="configuring-a-conditional-split-transformation-to-direct-inserts-updates-and-deletes"></a><span data-ttu-id="fc371-116">Настройка преобразования «Условное разбиение» для направления операций вставки, обновления и удаления в разные выходы</span><span class="sxs-lookup"><span data-stu-id="fc371-116">Configuring a Conditional Split Transformation to Direct Inserts, Updates, and Deletes</span></span>  
 <span data-ttu-id="fc371-117">Если требуется направить строки измененных данных на один из трех выходов, преобразование «Условное разбиение» подходит идеально.</span><span class="sxs-lookup"><span data-stu-id="fc371-117">To direct rows of change data to one of three outputs, the Conditional Split transformation is ideal.</span></span> <span data-ttu-id="fc371-118">Это преобразование проверяет значение столбца **CDC_OPERATION** в каждой строке и определяет, было изменение вставкой, обновлением или удалением.</span><span class="sxs-lookup"><span data-stu-id="fc371-118">The transformation just checks the value of the **CDC_OPERATION** column in each row and determines whether that change was an insert, update, or delete.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fc371-119">Столбец CDC_OPERATION содержит понятное строковое значение, полученное из числового значения в столбце **__$operation** .</span><span class="sxs-lookup"><span data-stu-id="fc371-119">The CDC_OPERATION column contains a friendly string value derived from the numeric value in the **__$operation** column.</span></span>  
  
#### <a name="to-split-inserts-updates-and-deletes-for-processing-by-using-a-conditional-split-transformation"></a><span data-ttu-id="fc371-120">Разбиение операций вставки, обновления и удаления для обработки с помощью преобразования «Условное разбиение»</span><span class="sxs-lookup"><span data-stu-id="fc371-120">To split inserts, updates, and deletes for processing by using a Conditional Split transformation</span></span>  
  
1.  <span data-ttu-id="fc371-121">На вкладке **Поток данных** добавьте преобразование «Условное разбиение».</span><span class="sxs-lookup"><span data-stu-id="fc371-121">On the **Data Flow** tab, add a Conditional Split transformation.</span></span>  
  
2.  <span data-ttu-id="fc371-122">Соедините выход источника OLE DB с преобразованием «Условное разбиение».</span><span class="sxs-lookup"><span data-stu-id="fc371-122">Connect the output of the OLE DB source to the Conditional Split transformation.</span></span>  
  
3.  <span data-ttu-id="fc371-123">На нижней панели **Редактора преобразования «Условное разбиение»** введите три следующие строки, чтобы обозначить три выхода.</span><span class="sxs-lookup"><span data-stu-id="fc371-123">In the **Conditional Split Transformation Editor**, in the lower pane of the editor, enter the following three lines to designate the three outputs</span></span>  
  
    1.  <span data-ttu-id="fc371-124">Введите строку с условием `CDC_OPERATION == "I"` , чтобы направить вставленные строки на выход для вставок.</span><span class="sxs-lookup"><span data-stu-id="fc371-124">Enter a line with the condition `CDC_OPERATION == "I"` to direct inserted rows to the output for inserts.</span></span>  
  
    2.  <span data-ttu-id="fc371-125">Введите строку с условием `CDC_OPERATION == "U"` , чтобы направить обновленные строки на выход для обновлений.</span><span class="sxs-lookup"><span data-stu-id="fc371-125">Enter a line with the condition `CDC_OPERATION == "U"` to direct updated rows to the output for updates.</span></span>  
  
    3.  <span data-ttu-id="fc371-126">Введите строку с условием `CDC_OPERATION == "D"` , чтобы направить удаленные строки на выход для удалений.</span><span class="sxs-lookup"><span data-stu-id="fc371-126">Enter a line with the condition `CDC_OPERATION == "D"` to direct deleted rows to the output for deletes.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="fc371-127">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="fc371-127">Next Step</span></span>  
 <span data-ttu-id="fc371-128">Когда строки разбиты для обработки, следующим шагом является применение изменений к назначению.</span><span class="sxs-lookup"><span data-stu-id="fc371-128">After you split the rows for processing, the next step is to apply the changes to the destination.</span></span>  
  
 <span data-ttu-id="fc371-129">**Следующая статья:** [Применение изменений в назначении](apply-the-changes-to-the-destination.md)</span><span class="sxs-lookup"><span data-stu-id="fc371-129">**Next topic:** [Apply the Changes to the Destination](apply-the-changes-to-the-destination.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc371-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="fc371-130">See Also</span></span>  
 <span data-ttu-id="fc371-131">[Conditional Split Transformation](../data-flow/transformations/conditional-split-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="fc371-131">[Conditional Split Transformation](../data-flow/transformations/conditional-split-transformation.md) </span></span>  
 [<span data-ttu-id="fc371-132">Разбиение набора данных с помощью преобразования "Условное разбиение"</span><span class="sxs-lookup"><span data-stu-id="fc371-132">Split a Dataset by Using the Conditional Split Transformation</span></span>](../data-flow/transformations/split-a-dataset-by-using-the-conditional-split-transformation.md)  
  
  
