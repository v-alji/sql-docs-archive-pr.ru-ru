---
title: Использование выражения в компоненте потока данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- components [Integration Services], data flow
- expressions [Integration Services], data flow components
ms.assetid: 9181b998-d24a-41fb-bb3c-14eee34f910d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 653bf468d0af6d44c5abe7344fcc13f93f86b430
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734261"
---
# <a name="use-an-expression-in-a-data-flow-component"></a><span data-ttu-id="f492f-102">Использование выражения в компоненте потока данных</span><span class="sxs-lookup"><span data-stu-id="f492f-102">Use an Expression in a Data Flow Component</span></span>
  <span data-ttu-id="f492f-103">Ниже описана процедура добавления выражения в преобразование «Условное разбиение» или «Производный столбец».</span><span class="sxs-lookup"><span data-stu-id="f492f-103">This procedure describes how to add an expression to the Conditional Split transformation or to the Derived Column transformation.</span></span> <span data-ttu-id="f492f-104">Преобразование «Условное разбиение» с помощью выражений определяет условия, которые направляют строки данных в выход преобразования, а преобразование «Производный столбец» с помощью выражений определяет значения, присваиваемые столбцам.</span><span class="sxs-lookup"><span data-stu-id="f492f-104">The Conditional Split transformation uses expressions to define the conditions that direct data rows to a transformation output, and the Derived Column transformation uses expressions to define values assigned to columns.</span></span>  
  
 <span data-ttu-id="f492f-105">Чтобы реализовать выражение в преобразовании, необходимо, чтобы в пакете уже была хотя бы одна задача потока данных и один источник.</span><span class="sxs-lookup"><span data-stu-id="f492f-105">To implement an expression in a transformation, the package must already include at least one Data Flow task and a source.</span></span> <span data-ttu-id="f492f-106">Сведения о добавлении элементов к пакетам см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="f492f-106">For information about adding items to packages, see the following topics:</span></span>  
  
-   [<span data-ttu-id="f492f-107">Добавление задачи или контейнера в поток управления или удалить их из него</span><span class="sxs-lookup"><span data-stu-id="f492f-107">Add or Delete a Task or a Container in a Control Flow</span></span>](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)  
    
  
-   [<span data-ttu-id="f492f-108">Добавление или удаление компонента в потоке данных</span><span class="sxs-lookup"><span data-stu-id="f492f-108">Add or Delete a Component in a Data Flow</span></span>](data-flow/add-or-delete-a-component-in-a-data-flow.md)  
  
-   [<span data-ttu-id="f492f-109">Соединение компонентов в потоке данных</span><span class="sxs-lookup"><span data-stu-id="f492f-109">Connect Components in a Data Flow</span></span>](data-flow/connect-components-in-a-data-flow.md)  
  
### <a name="to-create-an-expression"></a><span data-ttu-id="f492f-110">Создание выражения</span><span class="sxs-lookup"><span data-stu-id="f492f-110">To create an expression</span></span>  
  
1.  <span data-ttu-id="f492f-111">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="f492f-111">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="f492f-112">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="f492f-112">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="f492f-113">В конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] перейдите на вкладку **Поток управления** , затем щелкните задачу потока данных, содержащую поток данных, в котором нужно реализовать выражение.</span><span class="sxs-lookup"><span data-stu-id="f492f-113">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Control Flow** tab, and then click the Data Flow task that contains the data flow in which you want to implement an expression.</span></span>  
  
4.  <span data-ttu-id="f492f-114">Перейдите на вкладку **Поток данных** и перетащите преобразование «Условное разбиение» или «Производный столбец» из окна **Область элементов** в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="f492f-114">Click the **Data Flow** tab, and drag either a Conditional Split or Derived Column transformation from the **Toolbox** to the design surface.</span></span>  
  
5.  <span data-ttu-id="f492f-115">Перетащите зеленый соединитель из источника или преобразования в преобразование «Условное разбиение» или «Производный столбец».</span><span class="sxs-lookup"><span data-stu-id="f492f-115">Drag the green connector from the source or a transformation to the Conditional Split or Derived Column transformation.</span></span>  
  
6.  <span data-ttu-id="f492f-116">Дважды щелкните преобразование, чтобы открыть его диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="f492f-116">Double-click the transformation to open its dialog box.</span></span>  
  
7.  <span data-ttu-id="f492f-117">В левой панели разверните узел **Переменные** для отображения системных и пользовательских переменных, затем разверните узел **Столбцы** . Отобразятся входные столбцы преобразования.</span><span class="sxs-lookup"><span data-stu-id="f492f-117">In the left pane, expand **Variables** to display system and user-defined variables, and expand **Columns** to display the transformation input columns.</span></span>  
  
8.  <span data-ttu-id="f492f-118">В правой панели разверните узлы **Математические функции**, **Строковые функции**, **Функции даты-времени**, **Функции NULL**, **Приведения типов**и **Операторы** для доступа к функциям, операторам приведения и операторам, предоставляемым грамматикой выражения.</span><span class="sxs-lookup"><span data-stu-id="f492f-118">In the right pane, expand **Mathematical Functions**, **String Functions**, **Date/Time Functions**, **NULL Functions**, **Type Casts**, and **Operators** to access the functions, the casts, and the operators that the expression grammar provides.</span></span>  
  
9. <span data-ttu-id="f492f-119">В зависимости от вида преобразования выполните одно из следующих действий для создания выражения.</span><span class="sxs-lookup"><span data-stu-id="f492f-119">Depending on the transformation, do one of the following to build an expression:</span></span>  
  
    -   <span data-ttu-id="f492f-120">В диалоговом окне **Редактор преобразования «Условное разбиение»** перетащите переменные, столбцы, функции, операторы и приведения в столбец **Условие** .</span><span class="sxs-lookup"><span data-stu-id="f492f-120">In the **Conditional Split Transformation Editor** dialog box, drag variables, columns, functions, operators, and casts to the **Condition** column.</span></span> <span data-ttu-id="f492f-121">Также можно ввести выражение непосредственно в столбец **Условие** .</span><span class="sxs-lookup"><span data-stu-id="f492f-121">Alternatively, you can type an expression directly in the **Condition** column.</span></span>  
  
    -   <span data-ttu-id="f492f-122">В диалоговом окне **Редактор преобразования «Производный столбец»** перетащите переменные, столбцы, функции, операторы и приведения в столбец **Выражение** .</span><span class="sxs-lookup"><span data-stu-id="f492f-122">In the **Derived Column Transformation Editor** dialog box, drag variables, columns, functions, operators, and casts to the **Expression** column.</span></span> <span data-ttu-id="f492f-123">Также можно ввести выражение непосредственно в столбец **Выражение** .</span><span class="sxs-lookup"><span data-stu-id="f492f-123">Alternatively, you can type an expression directly in the **Expression** column.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="f492f-124">При переключении фокуса со столбца **Условие** или **Выражение** текст выражения может быть выделен, что указывает на ошибку в синтаксисе выражения.</span><span class="sxs-lookup"><span data-stu-id="f492f-124">When you remove the focus from the **Condition** column or the **Expression** column, the expression text might be highlighted to indicate that the expression syntax is incorrect.</span></span>  
  
10. <span data-ttu-id="f492f-125">Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="f492f-125">Click **OK** to exit the dialog box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f492f-126">Если выражение является недопустимым, появится предупреждение с описанием синтаксических ошибок данного выражения.</span><span class="sxs-lookup"><span data-stu-id="f492f-126">If the expression is not valid, an alert appears describing the syntax errors in the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f492f-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="f492f-127">See Also</span></span>  
 <span data-ttu-id="f492f-128">[Выражения&#41; Integration Services &#40;SSIS](expressions/integration-services-ssis-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="f492f-128">[Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md) </span></span>  
 <span data-ttu-id="f492f-129">[Преобразование «Условное разбиение»](data-flow/transformations/conditional-split-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="f492f-129">[Conditional Split Transformation](data-flow/transformations/conditional-split-transformation.md) </span></span>  
 <span data-ttu-id="f492f-130">[Derived Column Transformation](data-flow/transformations/derived-column-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="f492f-130">[Derived Column Transformation](data-flow/transformations/derived-column-transformation.md) </span></span>  
 <span data-ttu-id="f492f-131">[Задача потока данных](control-flow/data-flow-task.md) </span><span class="sxs-lookup"><span data-stu-id="f492f-131">[Data Flow Task](control-flow/data-flow-task.md) </span></span>  
 [<span data-ttu-id="f492f-132">Поток данных</span><span class="sxs-lookup"><span data-stu-id="f492f-132">Data Flow</span></span>](data-flow/data-flow.md)  
  
  
