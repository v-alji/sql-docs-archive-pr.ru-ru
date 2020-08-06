---
title: Редактор преобразования "Условное разбиение" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.conditionalsplittransformation.f1
helpviewer_keywords:
- Conditional Split Transformation Editor
ms.assetid: c30e1633-537a-4837-9991-6203c6f2a21e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 386a93eb7c3058c7c3e98f2b652199d115d841f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655885"
---
# <a name="conditional-split-transformation-editor"></a><span data-ttu-id="3f595-102">редактор преобразования «Условное разбиение»</span><span class="sxs-lookup"><span data-stu-id="3f595-102">Conditional Split Transformation Editor</span></span>
  <span data-ttu-id="3f595-103">Диалоговое окно **Редактор преобразования «Условное разбиение»** используется для создания выражений, определения порядка, в котором производится вычисление выражений, а также для именования выходных данных условных разбиений.</span><span class="sxs-lookup"><span data-stu-id="3f595-103">Use the **Conditional Split Transformation Editor** dialog box to create expressions, set the order in which expressions are evaluated, and name the outputs of a conditional split.</span></span> <span data-ttu-id="3f595-104">В этом диалоговом окне вызываются математические, строковые функции, функции даты и времени, а также операторы, которые можно использовать при построении выражений.</span><span class="sxs-lookup"><span data-stu-id="3f595-104">This dialog box includes mathematical, string, and date/time functions and operators that you can use to build expressions.</span></span> <span data-ttu-id="3f595-105">Первое условие, значение которого вычисляется как TRUE, определяет вывод, на который направляется строка.</span><span class="sxs-lookup"><span data-stu-id="3f595-105">The first condition that evaluates as true determines the output to which a row is directed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3f595-106">Преобразование «Условное разбиение» направляет каждую входную строку только на один вывод.</span><span class="sxs-lookup"><span data-stu-id="3f595-106">The Conditional Split transformation directs each input row to one output only.</span></span> <span data-ttu-id="3f595-107">При введении нескольких условий преобразование направляет каждую строку на первый вывод, для которого условие имеет значение TRUE, и не учитывает последующие условия для данной строки.</span><span class="sxs-lookup"><span data-stu-id="3f595-107">If you enter multiple conditions, the transformation sends each row to the first output for which the condition is true and disregards subsequent conditions for that row.</span></span> <span data-ttu-id="3f595-108">При необходимости последовательной проверки выполнения нескольких условий может потребоваться объединить в потоке данных несколько преобразований «Условное разбиение».</span><span class="sxs-lookup"><span data-stu-id="3f595-108">If you need to evaluate several conditions successively, you may need to concatenate multiple Conditional Split transformations in the data flow.</span></span>  
  
 <span data-ttu-id="3f595-109">Дополнительные сведения о редакторе преобразований "Условное разбиение" см. в разделе [Преобразование "Условное разбиение"](data-flow/transformations/conditional-split-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="3f595-109">To learn more about the Conditional Split transformation, see [Conditional Split Transformation](data-flow/transformations/conditional-split-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="3f595-110">Варианты</span><span class="sxs-lookup"><span data-stu-id="3f595-110">Options</span></span>  
 <span data-ttu-id="3f595-111">**Заказ**</span><span class="sxs-lookup"><span data-stu-id="3f595-111">**Order**</span></span>  
 <span data-ttu-id="3f595-112">Выберите строку и с помощью расположенных справа клавиш-стрелок измените порядок, в соответствии с которым будут оцениваться выражения.</span><span class="sxs-lookup"><span data-stu-id="3f595-112">Select a row and use the arrow keys at right to change the order in which to evaluate expressions.</span></span>  
  
 <span data-ttu-id="3f595-113">**Имя выходных данных**</span><span class="sxs-lookup"><span data-stu-id="3f595-113">**Output Name**</span></span>  
 <span data-ttu-id="3f595-114">Укажите имя вывода.</span><span class="sxs-lookup"><span data-stu-id="3f595-114">Provide an output name.</span></span> <span data-ttu-id="3f595-115">По умолчанию, используется нумерованный список вариантов, однако можно выбрать любое уникальное имя для описания.</span><span class="sxs-lookup"><span data-stu-id="3f595-115">The default is a numbered list of cases; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="3f595-116">**Условие**</span><span class="sxs-lookup"><span data-stu-id="3f595-116">**Condition**</span></span>  
 <span data-ttu-id="3f595-117">Введите выражение или постройте его, перетаскивая элементы из списка доступных столбцов, переменных, функций и операторов.</span><span class="sxs-lookup"><span data-stu-id="3f595-117">Type an expression or build one by dragging from the list of available columns, variables, functions, and operators.</span></span>  
  
 <span data-ttu-id="3f595-118">Значение этого свойства можно задать с помощью выражения свойства.</span><span class="sxs-lookup"><span data-stu-id="3f595-118">The value of this property can be specified by using a property expression.</span></span>  
  
 <span data-ttu-id="3f595-119">\*\*См. также: \*\*  [Выражения служб Integration Services (SSIS)](expressions/integration-services-ssis-expressions.md), [Операторы (выражение служб SSIS)](expressions/operators-ssis-expression.md) и [Функции (выражение служб SSIS)](expressions/functions-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="3f595-119">**Related topics:**  [Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md), [Operators &#40;SSIS Expression&#41;](expressions/operators-ssis-expression.md), and [Functions &#40;SSIS Expression&#41;](expressions/functions-ssis-expression.md)</span></span>  
  
 <span data-ttu-id="3f595-120">**Имя выхода по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="3f595-120">**Default output name**</span></span>  
 <span data-ttu-id="3f595-121">Введите имя вывода по умолчанию или используйте имя, установленное по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3f595-121">Type a name for the default output, or use the default.</span></span>  
  
 <span data-ttu-id="3f595-122">**Настройка вывода ошибок**</span><span class="sxs-lookup"><span data-stu-id="3f595-122">**Configure error output**</span></span>  
 <span data-ttu-id="3f595-123">Укажите способ обработки ошибок в диалоговом окне [Настройка вывода ошибок](../../2014/integration-services/configure-error-output.md) .</span><span class="sxs-lookup"><span data-stu-id="3f595-123">Specify how to handle errors by using the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f595-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="3f595-124">See Also</span></span>  
 <span data-ttu-id="3f595-125">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="3f595-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="3f595-126">Разбиение набора данных с помощью преобразования «Условное разбиение»</span><span class="sxs-lookup"><span data-stu-id="3f595-126">Split a Dataset by Using the Conditional Split Transformation</span></span>](data-flow/transformations/split-a-dataset-by-using-the-conditional-split-transformation.md)  
  
  
