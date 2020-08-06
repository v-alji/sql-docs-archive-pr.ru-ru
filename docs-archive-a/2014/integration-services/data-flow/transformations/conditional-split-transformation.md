---
title: Преобразование "Условное разбиение" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.conditionalsplittrans.f1
helpviewer_keywords:
- Conditional Split transformation
- route rows to different outputs [Integration Services]
ms.assetid: 3f8b5825-226f-413c-ba8f-0bb931ca3770
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 96ff4b177992c329908ebc93df8f6220168e634d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665461"
---
# <a name="conditional-split-transformation"></a><span data-ttu-id="2d0ad-102">преобразование «Условное разбиение»</span><span class="sxs-lookup"><span data-stu-id="2d0ad-102">Conditional Split Transformation</span></span>
  <span data-ttu-id="2d0ad-103">Преобразование «Условное разбиение» может направлять строки данных в различные выходы в зависимости от содержимого данных.</span><span class="sxs-lookup"><span data-stu-id="2d0ad-103">The Conditional Split transformation can route data rows to different outputs depending on the content of the data.</span></span> <span data-ttu-id="2d0ad-104">Реализация преобразования "Условное разбиение" аналогична применению структур решения CASE в языке программирования.</span><span class="sxs-lookup"><span data-stu-id="2d0ad-104">The implementation of the Conditional Split transformation is similar to a CASE decision structure in a programming language.</span></span> <span data-ttu-id="2d0ad-105">Преобразование производит оценку выражений и на основе результатов направляет строку данных на указанный выход.</span><span class="sxs-lookup"><span data-stu-id="2d0ad-105">The transformation evaluates expressions, and based on the results, directs the data row to the specified output.</span></span> <span data-ttu-id="2d0ad-106">Это преобразование также обеспечивает выход по умолчанию, таким образом, если строка не совпадает с выражением, она направляется на выход по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2d0ad-106">This transformation also provides a default output, so that if a row matches no expression it is directed to the default output.</span></span>  
  
## <a name="configuration-of-the-conditional-split-transformation"></a><span data-ttu-id="2d0ad-107">Настройка преобразования «Условное разбиение»</span><span class="sxs-lookup"><span data-stu-id="2d0ad-107">Configuration of the Conditional Split Transformation</span></span>  
 <span data-ttu-id="2d0ad-108">Произвести настройку преобразования «Условное разбиение» можно следующими способами.</span><span class="sxs-lookup"><span data-stu-id="2d0ad-108">You can configure the Conditional Split transformation in the following ways:</span></span>  
  
-   <span data-ttu-id="2d0ad-109">Предоставить выражение, которое вычисляет логическое значение для каждого условия, которое должно быть проверено преобразованием.</span><span class="sxs-lookup"><span data-stu-id="2d0ad-109">Provide an expression that evaluates to a Boolean for each condition you want the transformation to test.</span></span>  
  
-   <span data-ttu-id="2d0ad-110">Указать порядок оценки условий.</span><span class="sxs-lookup"><span data-stu-id="2d0ad-110">Specify the order in which the conditions are evaluated.</span></span> <span data-ttu-id="2d0ad-111">Порядок имеет большое значение, потому что строка посылается на выход в соответствии с первым условием, имеющим значение TRUE.</span><span class="sxs-lookup"><span data-stu-id="2d0ad-111">Order is significant, because a row is sent to the output corresponding to the first condition that evaluates to true.</span></span>  
  
-   <span data-ttu-id="2d0ad-112">Задает выход по умолчанию для преобразования.</span><span class="sxs-lookup"><span data-stu-id="2d0ad-112">Specify the default output for the transformation.</span></span> <span data-ttu-id="2d0ad-113">Преобразование требует указания выхода по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2d0ad-113">The transformation requires that a default output be specified.</span></span>  
  
 <span data-ttu-id="2d0ad-114">Каждая входная строка может быть послана только на один выход, который является выходом первого условия, имеющего значение TRUE.</span><span class="sxs-lookup"><span data-stu-id="2d0ad-114">Each input row can be sent to only one output, that being the output for the first condition that evaluates to true.</span></span> <span data-ttu-id="2d0ad-115">Например, следующие условия направляют любые строки столбца **FirstName** , которые начинаются с буквы *A* на один выход, строки, начинающиеся с буквы *B* на другой выход, а все остальные строки на выход по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2d0ad-115">For example, the following conditions direct any rows in the **FirstName** column that begin with the letter *A* to one output, rows that begin with the letter *B* to a different output, and all other rows to the default output.</span></span>  
  
 <span data-ttu-id="2d0ad-116">Выход 1</span><span class="sxs-lookup"><span data-stu-id="2d0ad-116">Output 1</span></span>  
  
 `SUBSTRING(FirstName,1,1) == "A"`  
  
 <span data-ttu-id="2d0ad-117">Выход 2</span><span class="sxs-lookup"><span data-stu-id="2d0ad-117">Output 2</span></span>  
  
 `SUBSTRING(FirstName,1,1) == "B"`  
  
 [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="2d0ad-118">содержат функции и операторы, которые можно использовать для создания выражений, которые оценивают и направляют входные данные.</span><span class="sxs-lookup"><span data-stu-id="2d0ad-118">includes functions and operators that you can use to create the expressions that evaluate input data and direct output data.</span></span> <span data-ttu-id="2d0ad-119">Дополнительные сведения см. в разделе [Выражения служб Integration Services (SSIS)](../../expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="2d0ad-119">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md).</span></span>  
  
 <span data-ttu-id="2d0ad-120">Преобразование «Условное разбиение» содержит пользовательское свойство `FriendlyExpression`.</span><span class="sxs-lookup"><span data-stu-id="2d0ad-120">The Conditional Split transformation includes the `FriendlyExpression` custom property.</span></span> <span data-ttu-id="2d0ad-121">Это свойство может быть обновлено выражением свойства при загрузке пакета.</span><span class="sxs-lookup"><span data-stu-id="2d0ad-121">This property can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="2d0ad-122">Дополнительные сведения см. в разделах [Использование выражений свойств в пакетах](../../expressions/use-property-expressions-in-packages.md) и [Пользовательские свойства преобразований](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="2d0ad-122">For more information, see [Use Property Expressions in Packages](../../expressions/use-property-expressions-in-packages.md) and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="2d0ad-123">Это преобразование содержит один вход, один (или более) выход и один выход ошибки.</span><span class="sxs-lookup"><span data-stu-id="2d0ad-123">This transformation has one input, one or more outputs, and one error output.</span></span>  
  
 <span data-ttu-id="2d0ad-124">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="2d0ad-124">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="2d0ad-125">Дополнительные сведения о свойствах, которые можно установить в диалоговом окне **Редактор преобразования «Условное разбиение»** , см. в разделе [Conditional Split Transformation Editor](../../conditional-split-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="2d0ad-125">For more information about the properties that you can set in the **Conditional Split Transformation Editor** dialog box, see [Conditional Split Transformation Editor](../../conditional-split-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="2d0ad-126">Диалоговое окно **Расширенный редактор** содержит свойства, которые можно установить с помощью программных средств.</span><span class="sxs-lookup"><span data-stu-id="2d0ad-126">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="2d0ad-127">Дополнительные сведения о свойствах, которые вы можете задать в диалоговом окне **Расширенный редактор** или программными средствами, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="2d0ad-127">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="2d0ad-128">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="2d0ad-128">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="2d0ad-129">Пользовательские свойства преобразований</span><span class="sxs-lookup"><span data-stu-id="2d0ad-129">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="2d0ad-130">Дополнительные сведения о настройке свойств см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="2d0ad-130">For more information about how to set properties, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="2d0ad-131">Разбиение набора данных с помощью преобразования «Условное разбиение»</span><span class="sxs-lookup"><span data-stu-id="2d0ad-131">Split a Dataset by Using the Conditional Split Transformation</span></span>](conditional-split-transformation.md)  
  
-   [<span data-ttu-id="2d0ad-132">Установление свойств компонента потока данных</span><span class="sxs-lookup"><span data-stu-id="2d0ad-132">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="2d0ad-133">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="2d0ad-133">Related Tasks</span></span>  
 [<span data-ttu-id="2d0ad-134">Разбиение набора данных с помощью преобразования «Условное разбиение»</span><span class="sxs-lookup"><span data-stu-id="2d0ad-134">Split a Dataset by Using the Conditional Split Transformation</span></span>](conditional-split-transformation.md)  
  
## <a name="see-also"></a><span data-ttu-id="2d0ad-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="2d0ad-135">See Also</span></span>  
 <span data-ttu-id="2d0ad-136">[Поток данных](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="2d0ad-136">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="2d0ad-137">Преобразования служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="2d0ad-137">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
