---
title: Расширение набора данных с помощью преобразования "Соединение слиянием" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Merge Join transformation
- datasets [Integration Services], joining
- datasets [Integration Services], extending
- joining datasets [Integration Services]
ms.assetid: 9e512c3c-f89b-45f3-8281-cdb8f35a2b1f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a387c4ad840eb739d36023be9323c063dcb9a68e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656493"
---
# <a name="extend-a-dataset-by-using-the-merge-join-transformation"></a><span data-ttu-id="37030-102">Расширение набора данных при помощи преобразования «Соединение слиянием»</span><span class="sxs-lookup"><span data-stu-id="37030-102">Extend a Dataset by Using the Merge Join Transformation</span></span>
  <span data-ttu-id="37030-103">Чтобы добавить и настроить преобразование «Соединение слиянием», пакет должен содержать по крайней мере одну задачу потока данных и два компонента потока данных, которые используются в качестве входных для преобразования «Соединение слиянием».</span><span class="sxs-lookup"><span data-stu-id="37030-103">To add and configure a Merge Join transformation, the package must already include at least one Data Flow task and two data flow components that provide inputs to the Merge Join transformation.</span></span>  
  
 <span data-ttu-id="37030-104">Преобразование «Соединение слиянием» требует наличия двух отсортированных входов.</span><span class="sxs-lookup"><span data-stu-id="37030-104">The Merge Join transformation requires two sorted inputs.</span></span> <span data-ttu-id="37030-105">Дополнительные сведения см. в разделе [Сортировка данных для преобразований "Слияние" и "Соединение слиянием"](sort-data-for-the-merge-and-merge-join-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="37030-105">For more information, see [Sort Data for the Merge and Merge Join Transformations](sort-data-for-the-merge-and-merge-join-transformations.md).</span></span>  
  
### <a name="to-extend-a-dataset"></a><span data-ttu-id="37030-106">Расширение набора данных</span><span class="sxs-lookup"><span data-stu-id="37030-106">To extend a dataset</span></span>  
  
1.  <span data-ttu-id="37030-107">В среде [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="37030-107">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="37030-108">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="37030-108">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="37030-109">Перейдите на вкладку **Поток данных** и из окна **Область элементов**перенесите преобразование «Соединение слиянием» в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="37030-109">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the Merge Join transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="37030-110">Подключите преобразование «Соединение слиянием» к потоку данных, перетащив соединитель из источника данных или предыдущего преобразования в текущее преобразование «Соединение слиянием».</span><span class="sxs-lookup"><span data-stu-id="37030-110">Connect the Merge Join transformation to the data flow by dragging the connector from a data source or a previous transformation to the Merge Join transformation.</span></span>  
  
5.  <span data-ttu-id="37030-111">Дважды щелкните преобразование «Соединение слиянием».</span><span class="sxs-lookup"><span data-stu-id="37030-111">Double-click the Merge Join transformation.</span></span>  
  
6.  <span data-ttu-id="37030-112">В диалоговом окне **Редактор преобразования «Соединение слиянием»** выберите тип объединения из списка **Тип объединения** .</span><span class="sxs-lookup"><span data-stu-id="37030-112">In the **Merge Join Transformation Editor** dialog box, select the type of join to use in the **Join type** list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="37030-113">При выборе типа **Левое внешнее соединение** можно щелкнуть **Обменять выходы** для переключения входов и преобразования левого внешнего соединения в правое.</span><span class="sxs-lookup"><span data-stu-id="37030-113">If you select the **Left outer join** type, you can click **Swap Inputs** to switch the inputs and convert the left outer join to a right outer join.</span></span>  
  
7.  <span data-ttu-id="37030-114">Задайте соединяемые колонки, перетащив столбцы левого входа к колонкам правого входа.</span><span class="sxs-lookup"><span data-stu-id="37030-114">Drag columns in the left input to columns in the right input to specify the join columns.</span></span> <span data-ttu-id="37030-115">Если у столбцов одинаковые имена, то при установке флажка **Ключ соединения** преобразование «Соединение слиянием» автоматически создаст объединение.</span><span class="sxs-lookup"><span data-stu-id="37030-115">If the columns have the same name, you can select the **Join Key** check box and the Merge Join transformation automatically creates the join.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="37030-116">Можно создавать объединения только между теми столбцами, которые имеют одинаковую позицию сортировки. Объединение должно быть создано согласно указанной позиции сортировки.</span><span class="sxs-lookup"><span data-stu-id="37030-116">You can create joins only between columns that have the same sort position, and the joins must be created in the order specified by the sort position.</span></span> <span data-ttu-id="37030-117">Если попытаться создать соединения не по порядку, то **Редактор преобразования «Соединение слиянием»** предложит создать дополнительное объединение для пропущенных позиций порядка сортировки.</span><span class="sxs-lookup"><span data-stu-id="37030-117">If you attempt to create the joins out of order, the **Merge Join Transformation Editor** prompts you to create additional joins for the skipped sort order positions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="37030-118">По умолчанию выход отсортирован по столбцам соединения.</span><span class="sxs-lookup"><span data-stu-id="37030-118">By default, the output is sorted on the join columns.</span></span>  
  
8.  <span data-ttu-id="37030-119">В левом и правом входах установите флажки для дополнительных столбцов, которые необходимо включить в выход.</span><span class="sxs-lookup"><span data-stu-id="37030-119">In the left and right inputs, select the check boxes of additional columns to include in the output.</span></span> <span data-ttu-id="37030-120">Столбцы соединения включаются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="37030-120">Join columns are included by default.</span></span>  
  
9. <span data-ttu-id="37030-121">Существует дополнительная возможность обновления имен выходных столбцов в столбце **Псевдоним выхода** .</span><span class="sxs-lookup"><span data-stu-id="37030-121">Optionally, update the names of output columns in the **Output Alias** column.</span></span>  
  
10. <span data-ttu-id="37030-122">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="37030-122">Click **OK**.</span></span>  
  
11. <span data-ttu-id="37030-123">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="37030-123">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37030-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="37030-124">See Also</span></span>  
 <span data-ttu-id="37030-125">[Преобразование «Соединение слиянием»](merge-join-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="37030-125">[Merge Join Transformation](merge-join-transformation.md) </span></span>  
 <span data-ttu-id="37030-126">[Преобразования служб Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="37030-126">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="37030-127">[Пути служб Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="37030-127">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 [<span data-ttu-id="37030-128">Задача потока данных</span><span class="sxs-lookup"><span data-stu-id="37030-128">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
