---
title: Определение подобных строк данных с помощью преобразования "Нечеткое группирование" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Fuzzy Grouping transformation
- match similar data [Integration Services]
- similar data rows [Integration Services]
- fuzzy matches
ms.assetid: ffcb41a6-e23d-49ea-8c32-ac980e3dc495
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4e6d49548c211b38a35d6f5f7efc3d50fec93588
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667324"
---
# <a name="identify-similar-data-rows-by-using-the-fuzzy-grouping-transformation"></a><span data-ttu-id="f8302-102">Определение подобных строк данных с помощью преобразования «Нечеткое группирование»</span><span class="sxs-lookup"><span data-stu-id="f8302-102">Identify Similar Data Rows by Using the Fuzzy Grouping Transformation</span></span>
  <span data-ttu-id="f8302-103">Перед добавлением и настройкой преобразования «Нечеткое группирование» в пакете уже должен содержаться хотя бы один источник и задача потока данных.</span><span class="sxs-lookup"><span data-stu-id="f8302-103">To add and configure a Fuzzy Grouping transformation, the package must already include at least one Data Flow task and a source.</span></span>  
  
### <a name="to-implement-fuzzy-grouping-transformation-in-a-data-flow"></a><span data-ttu-id="f8302-104">Включение преобразования «Нечеткое группирование» в поток данных</span><span class="sxs-lookup"><span data-stu-id="f8302-104">To implement Fuzzy Grouping transformation in a data flow</span></span>  
  
1.  <span data-ttu-id="f8302-105">В среде [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="f8302-105">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="f8302-106">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="f8302-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="f8302-107">Перейдите на вкладку **Поток данных** , а затем из **области элементов**перетащите преобразование «Нечеткое группирование» в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="f8302-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the Fuzzy Grouping transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="f8302-108">Подключите преобразование «Нечеткое группирование» к потоку данных, перетащив соединитель из источника данных или предыдущего преобразования в преобразование «Нечеткое группирование».</span><span class="sxs-lookup"><span data-stu-id="f8302-108">Connect the Fuzzy Grouping transformation to the data flow by dragging the connector from the data source or a previous transformation to the Fuzzy Grouping transformation.</span></span>  
  
5.  <span data-ttu-id="f8302-109">Дважды щелкните преобразование «Нечеткое группирование».</span><span class="sxs-lookup"><span data-stu-id="f8302-109">Double-click the Fuzzy Grouping transformation.</span></span>  
  
6.  <span data-ttu-id="f8302-110">В диалоговом окне **Редактор преобразования «Нечеткое группирование»** на вкладке **Диспетчер соединений** выберите диспетчер соединений OLE DB, подключающийся к базе данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f8302-110">In the **Fuzzy Grouping Transformation Editor** dialog box, on the **Connection Manager** tab, select an OLE DB connection manager that connects to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f8302-111">Соединение с базой данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] требуется преобразованию для создания временных таблиц и индексов.</span><span class="sxs-lookup"><span data-stu-id="f8302-111">The transformation requires a connection to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database to create temporary tables and indexes.</span></span>  
  
7.  <span data-ttu-id="f8302-112">Щелкните вкладку **Столбцы** и в списке **Доступные входные столбцы** установите флажок для входных столбцов, в которых будет производиться поиск похожих строк в наборе данных.</span><span class="sxs-lookup"><span data-stu-id="f8302-112">Click the **Columns** tab and, in the **Available Input Columns** list, select the check box of the input columns to use to identify similar rows in the dataset.</span></span>  
  
8.  <span data-ttu-id="f8302-113">Установите флажок в столбце **Передать** для передачи входных столбцов на выход преобразования.</span><span class="sxs-lookup"><span data-stu-id="f8302-113">Select the check box in the **Pass Through** column to identify the input columns to pass through to the transformation output.</span></span> <span data-ttu-id="f8302-114">Передаваемые столбцы не включаются в процесс выявления повторяющихся строк.</span><span class="sxs-lookup"><span data-stu-id="f8302-114">Pass-through columns are not included in the process of identification of duplicate rows.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f8302-115">Входные столбцы, используемые для группирования, автоматически помечаются как передаваемые, и эти флажки не могут быть сняты.</span><span class="sxs-lookup"><span data-stu-id="f8302-115">Input columns that are used for grouping are automatically selected as pass-through columns, and they cannot be unselected while used for grouping.</span></span>  
  
9. <span data-ttu-id="f8302-116">Существует дополнительная возможность обновления имен выходных столбцов в столбце **Псевдоним выхода** .</span><span class="sxs-lookup"><span data-stu-id="f8302-116">Optionally, update the names of output columns in the **Output Alias** column.</span></span>  
  
10. <span data-ttu-id="f8302-117">Можно также обновить имена очищенных столбцов в столбце **Псевдоним группы вывода** .</span><span class="sxs-lookup"><span data-stu-id="f8302-117">Optionally, update the names of cleaned columns in the **Group OutputAlias** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f8302-118">По умолчанию столбцам присваиваются имена входных столбцов с суффиксом «_clean».</span><span class="sxs-lookup"><span data-stu-id="f8302-118">The default names of columns are the names of the input columns with a "_clean" suffix.</span></span>  
  
11. <span data-ttu-id="f8302-119">Можно изменить используемый тип соответствия в столбце **Тип совпадения** .</span><span class="sxs-lookup"><span data-stu-id="f8302-119">Optionally, update the type of match to use in the **Match Type** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f8302-120">Хотя бы один из столбцов должен использовать нечеткое соответствие.</span><span class="sxs-lookup"><span data-stu-id="f8302-120">At least one column must use fuzzy matching.</span></span>  
  
12. <span data-ttu-id="f8302-121">Укажите в столбце **Минимальное подобие** уровень минимального подобия столбцов.</span><span class="sxs-lookup"><span data-stu-id="f8302-121">Specify the minimum similarity level columns in the **Minimum Similarity** column.</span></span> <span data-ttu-id="f8302-122">Оно должно находиться в диапазоне от 0 до 1.</span><span class="sxs-lookup"><span data-stu-id="f8302-122">The value must be between 0 and 1.</span></span> <span data-ttu-id="f8302-123">Чем больше значение, тем более похожими должны быть значения входных столбцов для объединения в группы.</span><span class="sxs-lookup"><span data-stu-id="f8302-123">The closer the value is to 1, the more similar the values in the input columns must be to form a group.</span></span> <span data-ttu-id="f8302-124">Значение минимального подобия, равное 1, указывает на четкое соответствие.</span><span class="sxs-lookup"><span data-stu-id="f8302-124">A minimum similarity of 1 indicates an exact match.</span></span>  
  
13. <span data-ttu-id="f8302-125">Можно также изменить имена столбцов подобия в столбце **Псевдоним выхода подобия** .</span><span class="sxs-lookup"><span data-stu-id="f8302-125">Optionally, update the names of similarity columns in the **Similarity Output Alias** column.</span></span>  
  
14. <span data-ttu-id="f8302-126">Для указания обработки чисел в значениях данных измените значения в столбце **Числовые значения** .</span><span class="sxs-lookup"><span data-stu-id="f8302-126">To specify the handling of numbers in data values, update the values in the **Numerals** column.</span></span>  
  
15. <span data-ttu-id="f8302-127">Чтобы указать, каким образом преобразование сравнивает символьные данные в столбце, измените установленные по умолчанию параметры сравнения в столбце **Флаги сравнения** .</span><span class="sxs-lookup"><span data-stu-id="f8302-127">To specify how the transformation compares the string data in a column, modify the default selection of comparison options in the **Comparison Flags** column.</span></span>  
  
16. <span data-ttu-id="f8302-128">Щелкните вкладку **Дополнительно** , чтобы изменить имена столбцов, которые преобразование добавляет к выходу для уникального идентификатора строки (_key_in), идентификатора повторяющейся строки (_key_out) и значения подобия (_score).</span><span class="sxs-lookup"><span data-stu-id="f8302-128">Click the **Advanced** tab to modify the names of the columns that the transformation adds to the output for the unique row identifier (_key_in), the duplicate row identifier (_key_out), and the similarity value (_score).</span></span>  
  
17. <span data-ttu-id="f8302-129">При желании можно отрегулировать порог подобия при помощи ползунка.</span><span class="sxs-lookup"><span data-stu-id="f8302-129">Optionally, adjust the similarity threshold by moving the slider bar.</span></span>  
  
18. <span data-ttu-id="f8302-130">Можно также сбросить флажки разделителей токенов, чтобы игнорировать разделители в данных.</span><span class="sxs-lookup"><span data-stu-id="f8302-130">Optionally, clear the token delimiter check boxes to ignore delimiters in the data.</span></span>  
  
19. <span data-ttu-id="f8302-131">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f8302-131">Click **OK**.</span></span>  
  
20. <span data-ttu-id="f8302-132">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="f8302-132">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8302-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="f8302-133">See Also</span></span>  
 <span data-ttu-id="f8302-134">[Преобразование «Нечеткое группирование»](fuzzy-grouping-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="f8302-134">[Fuzzy Grouping Transformation](fuzzy-grouping-transformation.md) </span></span>  
 <span data-ttu-id="f8302-135">[Преобразования служб Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="f8302-135">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="f8302-136">[Пути служб Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="f8302-136">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 [<span data-ttu-id="f8302-137">Задача потока данных</span><span class="sxs-lookup"><span data-stu-id="f8302-137">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
