---
title: Объединение данных с помощью преобразования "Объединить все" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- merging datasets [Integration Services]
- merging inputs [Integration Services]
- combining datasets
- Union All transformation
- datasets [Integration Services], merging
ms.assetid: 78304403-a81c-4101-b87e-ec80ddfdac98
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e782a5770ab9936e4c5cc84da706a5472ecd4d36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667311"
---
# <a name="merge-data-by-using-the-union-all-transformation"></a><span data-ttu-id="3b16f-102">Выполнение слияния данных с помощью преобразования «Объединить все»</span><span class="sxs-lookup"><span data-stu-id="3b16f-102">Merge Data by Using the Union All Transformation</span></span>
  <span data-ttu-id="3b16f-103">Чтобы добавить и настроить преобразование «Объединить все», в пакет уже должны быть включены хотя бы одна задача потока данных и два источника данных.</span><span class="sxs-lookup"><span data-stu-id="3b16f-103">To add and configure a Union All transformation, the package must already include at least one Data Flow task and two data sources.</span></span>  
  
 <span data-ttu-id="3b16f-104">Преобразование «Объединить все» объединяет несколько входов.</span><span class="sxs-lookup"><span data-stu-id="3b16f-104">The Union All transformation combines multiple inputs.</span></span> <span data-ttu-id="3b16f-105">Первый вход, связываемый с преобразованием, будет ссылочным, а все последующие — дополнительными.</span><span class="sxs-lookup"><span data-stu-id="3b16f-105">The first input that is connected to the transformation is the reference input, and the inputs connected subsequently are the secondary inputs.</span></span> <span data-ttu-id="3b16f-106">Выход содержит столбцы ссылочного входа.</span><span class="sxs-lookup"><span data-stu-id="3b16f-106">The output includes the columns in the reference input.</span></span>  
  
### <a name="to-combine-inputs-in-a-data-flow"></a><span data-ttu-id="3b16f-107">Комбинирование входов в потоке данных</span><span class="sxs-lookup"><span data-stu-id="3b16f-107">To combine inputs in a data flow</span></span>  
  
1.  <span data-ttu-id="3b16f-108">В среде [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]дважды щелкните пакет в обозревателе решений, чтобы открыть его в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , а затем выберите вкладку **Поток данных** .</span><span class="sxs-lookup"><span data-stu-id="3b16f-108">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], double-click the package in Solution Explorer to open the package in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, and then click the **Data Flow** tab.</span></span>  
  
2.  <span data-ttu-id="3b16f-109">Из **области элементов**перетащите преобразование «Объединить все» в область конструктора на вкладке **Поток данных** .</span><span class="sxs-lookup"><span data-stu-id="3b16f-109">From the **Toolbox**, drag the Union All transformation to the design surface of the **Data Flow** tab.</span></span>  
  
3.  <span data-ttu-id="3b16f-110">Подключите преобразование «Объединить все» к потоку данных, перетащив соединитель из источника данных или предыдущего преобразования в преобразование «Объединить все».</span><span class="sxs-lookup"><span data-stu-id="3b16f-110">Connect the Union All transformation to the data flow by dragging a connector from the data source or a previous transformation to the Union All transformation.</span></span>  
  
4.  <span data-ttu-id="3b16f-111">Дважды щелкните преобразование «Объединить все».</span><span class="sxs-lookup"><span data-stu-id="3b16f-111">Double-click the Union All transformation.</span></span>  
  
5.  <span data-ttu-id="3b16f-112">В **Редакторе преобразования «Объединить все»** сопоставьте столбец входа со столбцом в списке **Имя выходного столбца** , щелкнув строку и выбрав столбец в списке входов.</span><span class="sxs-lookup"><span data-stu-id="3b16f-112">In the **Union All Transformation Editor**, map a column from an input to a column in the **Output Column Name** list by clicking a row and then selecting a column in the input list.</span></span> <span data-ttu-id="3b16f-113">Выберите **\<ignore>** в списке входов, чтобы не сопоставлять столбец.</span><span class="sxs-lookup"><span data-stu-id="3b16f-113">Select **\<ignore>** in the input list to skip mapping the column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3b16f-114">Сопоставление двух столбцов требует, чтобы метаданные этих столбцов совпадали.</span><span class="sxs-lookup"><span data-stu-id="3b16f-114">The mapping between two columns requires that the metadata of the columns match.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3b16f-115">Столбцы дополнительного входа, не сопоставленные со ссылочными столбцами, получают на выходе значения NULL.</span><span class="sxs-lookup"><span data-stu-id="3b16f-115">Columns in a secondary input that are not mapped to reference columns are set to null values in the output.</span></span>  
  
6.  <span data-ttu-id="3b16f-116">При необходимости можно изменить имена столбцов в списке **Имя выходного столбца** .</span><span class="sxs-lookup"><span data-stu-id="3b16f-116">Optionally, modify the names of columns in the **Output Column Name** column.</span></span>  
  
7.  <span data-ttu-id="3b16f-117">Повторите шаги 5 и 6 для каждого столбца каждого входа.</span><span class="sxs-lookup"><span data-stu-id="3b16f-117">Repeat steps 5 and 6 for each column in each input.</span></span>  
  
8.  <span data-ttu-id="3b16f-118">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3b16f-118">Click **OK**.</span></span>  
  
9. <span data-ttu-id="3b16f-119">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="3b16f-119">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b16f-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="3b16f-120">See Also</span></span>  
 <span data-ttu-id="3b16f-121">[Преобразование «Объединить все»](union-all-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="3b16f-121">[Union All Transformation](union-all-transformation.md) </span></span>  
 <span data-ttu-id="3b16f-122">[Преобразования служб Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="3b16f-122">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="3b16f-123">[Пути служб Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="3b16f-123">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 [<span data-ttu-id="3b16f-124">Задача потока данных</span><span class="sxs-lookup"><span data-stu-id="3b16f-124">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
