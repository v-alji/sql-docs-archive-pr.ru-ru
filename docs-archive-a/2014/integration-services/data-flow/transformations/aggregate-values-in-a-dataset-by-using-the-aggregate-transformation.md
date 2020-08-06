---
title: Статистическая обработка значений в наборе данных с помощью преобразования "Статистическая обработка" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Aggregate transformation [Integration Services]
- aggregate values [Integration Services]
- datasets [Integration Services], aggregate values
ms.assetid: 01b81c0f-d5e0-483b-81b2-73800a6945ac
author: chugugrace
ms.author: chugu
ms.openlocfilehash: de918c6c2adf194d5808ccd1b64c77a94a52e357
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728525"
---
# <a name="aggregate-values-in-a-dataset-by-using-the-aggregate-transformation"></a><span data-ttu-id="460c0-102">Статистическая обработка значений в наборе данных с помощью преобразования «Агрегатная обработка»</span><span class="sxs-lookup"><span data-stu-id="460c0-102">Aggregate Values in a Dataset by Using the Aggregate Transformation</span></span>
  <span data-ttu-id="460c0-103">Для добавления и настройки преобразования «Агрегатная обработка» пакет должен обладать как минимум одной задачей потока данных и одним источником.</span><span class="sxs-lookup"><span data-stu-id="460c0-103">To add and configure an Aggregate transformation, the package must already include at least one Data Flow task and one source.</span></span>  
  
### <a name="to-aggregate-values-in-a-dataset"></a><span data-ttu-id="460c0-104">Выполнение статистического вычисления значений в наборе данных</span><span class="sxs-lookup"><span data-stu-id="460c0-104">To aggregate values in a dataset</span></span>  
  
1.  <span data-ttu-id="460c0-105">В среде [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="460c0-105">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="460c0-106">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="460c0-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="460c0-107">Перейдите на вкладку **Поток данных** и перетащите преобразование «Статистическая обработка» из **области элементов**в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="460c0-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the Aggregate transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="460c0-108">Подключите преобразование «Агрегатная обработка» к потоку данных, перетащив соединитель из источника или предыдущего преобразования в преобразование «Агрегатная обработка».</span><span class="sxs-lookup"><span data-stu-id="460c0-108">Connect the Aggregate transformation to the data flow by dragging a connector from the source or the previous transformation to the Aggregate transformation.</span></span>  
  
5.  <span data-ttu-id="460c0-109">Дважды щелкните преобразование.</span><span class="sxs-lookup"><span data-stu-id="460c0-109">Double-click the transformation.</span></span>  
  
6.  <span data-ttu-id="460c0-110">В диалоговом окне **Редактор преобразования «Статистическая обработка»** перейдите на вкладку **Статистические выражения** .</span><span class="sxs-lookup"><span data-stu-id="460c0-110">In the **Aggregate Transformation Editor** dialog box, click the **Aggregations** tab.</span></span>  
  
7.  <span data-ttu-id="460c0-111">В списке **Доступные входные столбцы** установите флажки рядом со столбцами, для которых нужно выполнить статистическую обработку значений.</span><span class="sxs-lookup"><span data-stu-id="460c0-111">In the **Available Input Columns** list, select the check box by the columns on which you want to aggregate values.</span></span> <span data-ttu-id="460c0-112">Отмеченные столбцы появятся в таблице.</span><span class="sxs-lookup"><span data-stu-id="460c0-112">The selected columns appear in the table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="460c0-113">Можно отметить столбец несколько раз, применяя, таким образом, к нему множественные преобразования.</span><span class="sxs-lookup"><span data-stu-id="460c0-113">You can select a column multiple times, applying multiple transformations to the column.</span></span> <span data-ttu-id="460c0-114">Для уникального определения статистических выражений к данному по умолчанию названию для псевдонима выхода столбца добавляется число.</span><span class="sxs-lookup"><span data-stu-id="460c0-114">To uniquely identify aggregations, a number is appended to the default name of the output alias of the column.</span></span>  
  
8.  <span data-ttu-id="460c0-115">При необходимости измените значение в столбцах **Псевдоним выхода** .</span><span class="sxs-lookup"><span data-stu-id="460c0-115">Optionally, modify the value in the **Output Alias** columns.</span></span>  
  
9. <span data-ttu-id="460c0-116">Для изменения установленной по умолчанию статистической операции **Group by**выберите другую операцию в списке **Операция** .</span><span class="sxs-lookup"><span data-stu-id="460c0-116">To change the default aggregation operation, **Group by**, select a different operation in the **Operation** list.</span></span>  
  
10. <span data-ttu-id="460c0-117">Для изменения сравнения по умолчанию выберите отдельные флаги сравнения, перечисленные в столбце **Флаги сравнения** .</span><span class="sxs-lookup"><span data-stu-id="460c0-117">To change the default comparison, select the individual comparison flags listed in the **Comparison Flags** column.</span></span> <span data-ttu-id="460c0-118">По умолчанию сравнение не учитывает регистр, тип японской азбуки, несамостоятельные знаки и ширину символов.</span><span class="sxs-lookup"><span data-stu-id="460c0-118">By default, a comparison ignores case, kana type, non-spacing characters, and character width.</span></span>  
  
11. <span data-ttu-id="460c0-119">При необходимости определите для статистического выражения **Подсчет различных объектов** точное число различающихся значений в столбце **Количество различных ключей** или выберите приблизительное число в столбце **Масштаб различных ключей** .</span><span class="sxs-lookup"><span data-stu-id="460c0-119">Optionally, for the **Count distinct** aggregation, specify an exact number of distinct values in the **Count Distinct Keys** column, or select an approximate count in the **Count Distinct Scale** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="460c0-120">Указание точного или приблизительного числа различных значений оптимизирует производительность, поскольку преобразование может заранее выделить память, необходимую для выполнения задачи.</span><span class="sxs-lookup"><span data-stu-id="460c0-120">Providing the number of distinct values, exact or approximate, optimizes performance, because the transformation can preallocate an appropriate amount of memory to do its work.</span></span>  
  
12. <span data-ttu-id="460c0-121">При необходимости щелкните мышью **Дополнительно** и обновите название выхода преобразования «Статистическая обработка».</span><span class="sxs-lookup"><span data-stu-id="460c0-121">Optionally, click **Advanced** and update the name of the Aggregate transformation output.</span></span> <span data-ttu-id="460c0-122">Если агрегаты включают `Group By` операцию, можно выбрать приблизительное число значений ключа группирования в столбце **Масштаб ключей** или указать точное число ключевых значений группирования в столбце **ключи** .</span><span class="sxs-lookup"><span data-stu-id="460c0-122">If the aggregations include a `Group By` operation, you can select an approximate count of grouping key values in the **Keys Scale** column or specify an exact number of grouping key values in the **Keys** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="460c0-123">Указание точного или приблизительного числа различных значений оптимизирует производительность, поскольку преобразование может заранее выделить память, необходимую для выполнения задачи.</span><span class="sxs-lookup"><span data-stu-id="460c0-123">Providing the number of distinct values, exact or approximate, optimizes performance, because the transformation can preallocate an appropriate amount of memory to do its work.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="460c0-124">Параметры **Порядок числа ключей** и **Ключи** взаимоисключающие.</span><span class="sxs-lookup"><span data-stu-id="460c0-124">The **Keys Scale** and **Keys** options are mutually exclusive.</span></span> <span data-ttu-id="460c0-125">Если значения заданы как в столбце **Порядок числа ключей** , так и в столбце **Ключи** , используется большее значение.</span><span class="sxs-lookup"><span data-stu-id="460c0-125">If you enter values in both columns, the larger value in either **Keys Scale** or **Keys** is used.</span></span>  
  
13. <span data-ttu-id="460c0-126">При необходимости щелкните мышью вкладку **Дополнительно** и установите атрибуты, которые относятся к оптимизации всех операций преобразования «Статистическая обработка».</span><span class="sxs-lookup"><span data-stu-id="460c0-126">Optionally, click the **Advanced** tab and set the attributes that apply to optimizing all the operations that the Aggregate transformation performs.</span></span>  
  
14. <span data-ttu-id="460c0-127">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="460c0-127">Click **OK**.</span></span>  
  
15. <span data-ttu-id="460c0-128">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="460c0-128">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="460c0-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="460c0-129">See Also</span></span>  
 <span data-ttu-id="460c0-130">[Преобразование «Статистическая обработка»](aggregate-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="460c0-130">[Aggregate Transformation](aggregate-transformation.md) </span></span>  
 <span data-ttu-id="460c0-131">[Преобразования служб Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="460c0-131">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="460c0-132">[Пути служб Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="460c0-132">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 [<span data-ttu-id="460c0-133">Задача потока данных</span><span class="sxs-lookup"><span data-stu-id="460c0-133">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
