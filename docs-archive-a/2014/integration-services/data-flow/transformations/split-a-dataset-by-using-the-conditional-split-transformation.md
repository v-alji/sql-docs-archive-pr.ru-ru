---
title: Разбиение набора данных с помощью преобразования "Условное разбиение" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Conditional Split transformation
- splitting dataset
- datasets [Integration Services], splitting
ms.assetid: 23b3e84f-9296-4dc9-81c0-c7f06ae3f1ff
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2efbc3973db1ab1b6b61f6de879e451319b50e49
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667308"
---
# <a name="split-a-dataset-by-using-the-conditional-split-transformation"></a><span data-ttu-id="ce710-102">Разбиение набора данных с помощью преобразования «Условное разбиение»</span><span class="sxs-lookup"><span data-stu-id="ce710-102">Split a Dataset by Using the Conditional Split Transformation</span></span>
  <span data-ttu-id="ce710-103">Чтобы добавить и настроить преобразование «Условное разбиение», пакет должен содержать по крайней мере одну задачу потока данных и один источник.</span><span class="sxs-lookup"><span data-stu-id="ce710-103">To add and configure a Conditional Split transformation, the package must already include at least one Data Flow task and a source.</span></span>  
  
### <a name="to-conditionally-split-a-dataset"></a><span data-ttu-id="ce710-104">Чтобы условно разбить набор данных</span><span class="sxs-lookup"><span data-stu-id="ce710-104">To conditionally split a dataset</span></span>  
  
1.  <span data-ttu-id="ce710-105">В среде [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="ce710-105">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="ce710-106">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="ce710-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="ce710-107">Перейдите на вкладку **Поток данных** и перенесите преобразование «Условное разбиение» из окна **Область элементов**в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="ce710-107">Click the **Data Flow** tab, and, from the **Toolbox**, drag the Conditional Split transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="ce710-108">Подключите преобразование «Условное разбиение» к потоку данных, перетащив соединитель из источника данных или предыдущего преобразования в преобразование «Условное разбиение».</span><span class="sxs-lookup"><span data-stu-id="ce710-108">Connect the Conditional Split transformation to the data flow by dragging the connector from the data source or the previous transformation to the Conditional Split transformation.</span></span>  
  
5.  <span data-ttu-id="ce710-109">Дважды щелкните преобразование «Условное разбиение».</span><span class="sxs-lookup"><span data-stu-id="ce710-109">Double-click the Conditional Split transformation.</span></span>  
  
6.  <span data-ttu-id="ce710-110">В окне **Редактор преобразования «Условное разбиение»** постройте выражения для использования в качестве условий, перетащив необходимые переменные, столбцы, функции и операторы в столбец **Условие** сетки.</span><span class="sxs-lookup"><span data-stu-id="ce710-110">In the **Conditional Split Transformation Editor**, build the expressions to use as conditions by dragging variables, columns, functions, and operators to the **Condition** column in the grid.</span></span> <span data-ttu-id="ce710-111">Можно также ввести выражение в столбец **Условие** .</span><span class="sxs-lookup"><span data-stu-id="ce710-111">Or, you can type the expression in the **Condition** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ce710-112">Переменная или столбец могут быть использованы в нескольких выражениях.</span><span class="sxs-lookup"><span data-stu-id="ce710-112">A variable or column can be used in multiple expressions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ce710-113">Если выражение недопустимо, его текст выделяется, а в подсказке к столбцу появляется описание ошибки.</span><span class="sxs-lookup"><span data-stu-id="ce710-113">If the expression is not valid, the expression text is highlighted and a ToolTip on the column describes the errors.</span></span>  
  
7.  <span data-ttu-id="ce710-114">При необходимости измените значения в столбце **Имя выхода** .</span><span class="sxs-lookup"><span data-stu-id="ce710-114">Optionally, modify the values in the **Output Name** column.</span></span> <span data-ttu-id="ce710-115">Имена по умолчанию — «Case 1», «Case 2» и т. д.</span><span class="sxs-lookup"><span data-stu-id="ce710-115">The default names are Case 1, Case 2, and so forth.</span></span>  
  
8.  <span data-ttu-id="ce710-116">Для изменения последовательности оценки условий нажмите кнопку со стрелкой вверх или вниз.</span><span class="sxs-lookup"><span data-stu-id="ce710-116">To modify the sequence in which the conditions are evaluated, click the up arrow or down arrow.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ce710-117">Поместите условия, которые будут выполняться чаще всего, в начало списка.</span><span class="sxs-lookup"><span data-stu-id="ce710-117">Place the conditions that are most likely to be encountered at the top of the list.</span></span>  
  
9. <span data-ttu-id="ce710-118">Можно изменить имя выхода по умолчанию для строк данных, которые не подходят ни под одно из условий.</span><span class="sxs-lookup"><span data-stu-id="ce710-118">Optionally, modify the name of the default output for data rows that do not match any condition.</span></span>  
  
10. <span data-ttu-id="ce710-119">Для настройки вывода ошибок нажмите **Настроить вывод ошибок**.</span><span class="sxs-lookup"><span data-stu-id="ce710-119">To configure an error output, click **Configure Error Output**.</span></span> <span data-ttu-id="ce710-120">Дополнительные сведения см. в разделе [Настройка вывода ошибок в компоненте потока данных](../../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="ce710-120">For more information, see [Configure an Error Output in a Data Flow Component](../../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
11. <span data-ttu-id="ce710-121">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ce710-121">Click **OK**.</span></span>  
  
12. <span data-ttu-id="ce710-122">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="ce710-122">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce710-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="ce710-123">See Also</span></span>  
 <span data-ttu-id="ce710-124">[Conditional Split Transformation](conditional-split-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="ce710-124">[Conditional Split Transformation](conditional-split-transformation.md) </span></span>  
 <span data-ttu-id="ce710-125">[Преобразования служб Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="ce710-125">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="ce710-126">[Пути служб Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="ce710-126">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 <span data-ttu-id="ce710-127">[Типы данных служб Integration Services](../integration-services-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="ce710-127">[Integration Services Data Types](../integration-services-data-types.md) </span></span>  
 <span data-ttu-id="ce710-128">[Задача потока данных](../../control-flow/data-flow-task.md) </span><span class="sxs-lookup"><span data-stu-id="ce710-128">[Data Flow Task](../../control-flow/data-flow-task.md) </span></span>  
 [<span data-ttu-id="ce710-129">Выражения служб Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="ce710-129">Integration Services &#40;SSIS&#41; Expressions</span></span>](../../expressions/integration-services-ssis-expressions.md)  
  
  
