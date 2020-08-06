---
title: Добавление или изменение выражения свойства | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- expressions [Integration Services], creating
- expressions [Integration Services], property expressions
ms.assetid: cb5da499-065f-4fa6-9f6d-5bc5f385241e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0d6d12fbe46930818af2b47b59620963d39616e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666196"
---
# <a name="add-or-change-a-property-expression"></a><span data-ttu-id="3567e-102">Добавление или изменение выражение свойства</span><span class="sxs-lookup"><span data-stu-id="3567e-102">Add or Change a Property Expression</span></span>
  <span data-ttu-id="3567e-103">Пользователь может создать выражения свойств для пакетов, задач, контейнеров «цикл по каждому элементу», контейнеров «цикл по элементам», контейнеров последовательности, обработчиков событий, диспетчеров соединений на уровне пакетов и проектов и регистраторов.</span><span class="sxs-lookup"><span data-stu-id="3567e-103">You can create property expressions for packages, tasks, Foreach Loop containers, For Loop containers, Sequence containers, event handlers, package and project level connection managers, and log providers.</span></span>  
  
 <span data-ttu-id="3567e-104">Для создания или изменения выражений свойств вы можете использовать **Редактор выражений свойств** или **Построитель выражений**.</span><span class="sxs-lookup"><span data-stu-id="3567e-104">To create or change property expressions, you can use either the **Property Expressions Editor** or **Expression Builder**.</span></span> <span data-ttu-id="3567e-105">К **редактору выражений свойств** можно получить доступ из пользовательских редакторов задач и контейнеров или в окне **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="3567e-105">The **Property Expressions Editor** can be accessed from either the custom editors that are available for tasks and containers, or from the **Properties** window.</span></span> <span data-ttu-id="3567e-106">К**построителю выражений** можно обращаться из **редактора выражений свойств**.</span><span class="sxs-lookup"><span data-stu-id="3567e-106">**Expression Builder** can be accessed from inside the **Property Expressions Editor**.</span></span> <span data-ttu-id="3567e-107">Хотя выражения можно писать и в **редакторе выражений свойств** , и в **построителе выражений**, **построитель выражений** предоставляет набор графических средств, облегчающий создание сложных выражений.</span><span class="sxs-lookup"><span data-stu-id="3567e-107">While you can write expressions in either the **Property Expressions Editor** or **Expression Builder**, **Expression Builder** provides a graphical set of tools that makes it simple to build complex expressions.</span></span>  
  
 <span data-ttu-id="3567e-108">Чтобы лучше изучить синтаксис, операторы и функции, которые предоставляют службы [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], см. статьи [Операторы (выражение служб SSIS)](operators-ssis-expression.md) и [Функции (выражение служб SSIS)](functions-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="3567e-108">To learn more about the syntax, operators, and functions that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] provides, see [Operators &#40;SSIS Expression&#41;](operators-ssis-expression.md) and [Functions &#40;SSIS Expression&#41;](functions-ssis-expression.md).</span></span> <span data-ttu-id="3567e-109">Разделы по каждому оператору и каждой функции включают в себя примеры использования оператора или функции в выражении.</span><span class="sxs-lookup"><span data-stu-id="3567e-109">The topic for each operator or function includes examples of using that operator or function in an expression.</span></span> <span data-ttu-id="3567e-110">Примеры более сложных выражений см. в разделе [Использование выражений свойств в пакетах](use-property-expressions-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="3567e-110">For examples of more complex expressions, see [Use Property Expressions in Packages](use-property-expressions-in-packages.md).</span></span>  
  
### <a name="to-create-or-change-a-property-expression"></a><span data-ttu-id="3567e-111">Создание или изменение выражения свойства</span><span class="sxs-lookup"><span data-stu-id="3567e-111">To create or change a property expression</span></span>  
  
1.  <span data-ttu-id="3567e-112">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте проект, содержащий необходимый пакет служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3567e-112">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project that contains the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package you want.</span></span>  
  
2.  <span data-ttu-id="3567e-113">В обозревателе решений дважды щелкните пакет, чтобы открыть его, затем выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="3567e-113">In Solution Explorer, double-click the package to open it, and then do one of the following:</span></span>  
  
    -   <span data-ttu-id="3567e-114">Если элемент является задачей или контейнером, выделите его двойным щелчком и выберите **Выражения** в редакторе.</span><span class="sxs-lookup"><span data-stu-id="3567e-114">If the item is a task or a container, double-click the item, and then click **Expressions** in the editor.</span></span>  
  
    -   <span data-ttu-id="3567e-115">Правой кнопкой мыши щелкните элемент и выберите команду **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="3567e-115">Right-click the item and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="3567e-116">Щелкните окно **Выражения** и нажмите кнопку с многоточием (...).</span><span class="sxs-lookup"><span data-stu-id="3567e-116">Click in the **Expressions** box and then click the ellipsis (...).</span></span>  
  
4.  <span data-ttu-id="3567e-117">В **редакторе выражений свойств**выберите свойство в списке **Свойства** , затем выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="3567e-117">In the **Property Expressions Editor**, select a property in the **Property** list, and then do one of the following:</span></span>  
  
    -   <span data-ttu-id="3567e-118">Введите или измените выражение свойства непосредственно в столбце **Выражение** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3567e-118">Type or change the property expression directly in the **Expression** column, and then click **OK**.</span></span>  
  
         <span data-ttu-id="3567e-119">-или-</span><span class="sxs-lookup"><span data-stu-id="3567e-119">-or-</span></span>  
  
    -   <span data-ttu-id="3567e-120">Нажмите кнопку с многоточием (...) в строке выражения свойства, чтобы открыть **построитель выражений**.</span><span class="sxs-lookup"><span data-stu-id="3567e-120">Click the ellipsis (...) in the expression row of the property to open the **Expression Builder**.</span></span>  
  
5.  <span data-ttu-id="3567e-121">В **построителе выражений**выполните одну из следующих задач (необязательно):</span><span class="sxs-lookup"><span data-stu-id="3567e-121">(Optional) In the **Expression Builder**, do any of the following tasks:</span></span>  
  
    -   <span data-ttu-id="3567e-122">Для доступа к системным и пользовательским переменным разверните узел **Переменные**.</span><span class="sxs-lookup"><span data-stu-id="3567e-122">To access system and user-defined variables, expand **Variables**.</span></span>  
  
    -   <span data-ttu-id="3567e-123">Чтобы получить доступ к функциям, приведениям и операторам языка выражений служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] , разверните узел **Математические функции**, **Строковые функции**, **Функции даты-времени**, **Функции работы со значением NULL**, **Приведения типов**и **Операторы**.</span><span class="sxs-lookup"><span data-stu-id="3567e-123">To access the functions, the casts, and the operators that the [!INCLUDE[ssIS](../../includes/ssis-md.md)] expression language provides, expand **Mathematical Functions**, **String Functions**, **Date/Time Functions**, **NULL Functions**, **Type Casts**, and **Operators**.</span></span>  
  
    -   <span data-ttu-id="3567e-124">Чтобы создать или изменить выражение в **построителе выражений**, перетащите переменные, столбцы, функции, операторы и приведения в поле **Выражение** или введите выражение в это поле.</span><span class="sxs-lookup"><span data-stu-id="3567e-124">To build or change an expression in the **Expression Builder**, drag variables, columns, functions, operators, and casts to the **Expression** box, or type the expression in the box.</span></span>  
  
    -   <span data-ttu-id="3567e-125">Чтобы просмотреть результат вычисления выражения, щелкните **Вычислить значение выражения** в **построителе выражений**.</span><span class="sxs-lookup"><span data-stu-id="3567e-125">To view the evaluation result of the expression, click **Evaluate Expression** in the **Expression Builder**.</span></span>  
  
         <span data-ttu-id="3567e-126">Если выражение является недопустимым, появится предупреждение с описанием синтаксических ошибок данного выражения.</span><span class="sxs-lookup"><span data-stu-id="3567e-126">If the expression is not valid, an alert appears that describes the syntax errors in the expression.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="3567e-127">Вычисление выражения не присваивает результат вычисления свойству.</span><span class="sxs-lookup"><span data-stu-id="3567e-127">Evaluating an expression does not assign the evaluation result to the property.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3567e-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="3567e-128">See Also</span></span>  
 <span data-ttu-id="3567e-129">[Выражения служб Integration Services (SSIS)](integration-services-ssis-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="3567e-129">[Integration Services &#40;SSIS&#41; Expressions](integration-services-ssis-expressions.md) </span></span>  
 <span data-ttu-id="3567e-130">[Использование выражений свойств в пакетах](use-property-expressions-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="3567e-130">[Use Property Expressions in Packages](use-property-expressions-in-packages.md) </span></span>  
 <span data-ttu-id="3567e-131">[Пакеты служб Integration Services (SSIS)](../integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="3567e-131">[Integration Services &#40;SSIS&#41; Packages](../integration-services-ssis-packages.md) </span></span>  
 <span data-ttu-id="3567e-132">[Контейнеры служб Integration Services](../control-flow/integration-services-containers.md) </span><span class="sxs-lookup"><span data-stu-id="3567e-132">[Integration Services Containers](../control-flow/integration-services-containers.md) </span></span>  
 <span data-ttu-id="3567e-133">[Задачи служб Integration Services](../control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="3567e-133">[Integration Services Tasks](../control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="3567e-134">[Обработчики событий в службах Integration Services (SSIS)](../integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="3567e-134">[Integration Services &#40;SSIS&#41; Event Handlers](../integration-services-ssis-event-handlers.md) </span></span>  
 <span data-ttu-id="3567e-135">[Соединения в службах Integration Services (SSIS)](../connection-manager/integration-services-ssis-connections.md) </span><span class="sxs-lookup"><span data-stu-id="3567e-135">[Integration Services &#40;SSIS&#41; Connections](../connection-manager/integration-services-ssis-connections.md) </span></span>  
 [<span data-ttu-id="3567e-136">Ведение журналов в службах Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="3567e-136">Integration Services &#40;SSIS&#41; Logging</span></span>](../performance/integration-services-ssis-logging.md)  
  
  
