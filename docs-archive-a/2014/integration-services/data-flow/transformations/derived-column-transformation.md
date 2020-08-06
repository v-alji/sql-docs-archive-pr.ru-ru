---
title: Преобразование "Производный столбец" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.derivedcolumntrans.f1
helpviewer_keywords:
- multiple derived columns
- expressions [Integration Services], derived columns
- derived columns
- columns [Integration Services], derivations
- Derived Column transformation
ms.assetid: 8eba755e-8e48-4233-bd1e-09a46bf2692f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7bbdc46f2e67b1b859fcfa446c584373cfbeca0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655280"
---
# <a name="derived-column-transformation"></a><span data-ttu-id="7ebbc-102">Преобразование «Производный столбец»</span><span class="sxs-lookup"><span data-stu-id="7ebbc-102">Derived Column Transformation</span></span>
  <span data-ttu-id="7ebbc-103">Преобразованием «Производный столбец» создаются новые значения столбцов путем применения выражений к входным столбцам преобразования.</span><span class="sxs-lookup"><span data-stu-id="7ebbc-103">The Derived Column transformation creates new column values by applying expressions to transformation input columns.</span></span> <span data-ttu-id="7ebbc-104">Выражения могут содержать любые сочетания переменных, функций, операторов и столбцов из входа преобразования.</span><span class="sxs-lookup"><span data-stu-id="7ebbc-104">An expression can contain any combination of variables, functions, operators, and columns from the transformation input.</span></span> <span data-ttu-id="7ebbc-105">Результат добавляется в новый столбец или вставляется в существующий как замещающее значение.</span><span class="sxs-lookup"><span data-stu-id="7ebbc-105">The result can be added as a new column or inserted into an existing column as a replacement value.</span></span> <span data-ttu-id="7ebbc-106">При преобразовании «Производный столбец» может быть определено несколько производных столбцов, и любая переменная или входные столбцы могут присутствовать в нескольких выражениях.</span><span class="sxs-lookup"><span data-stu-id="7ebbc-106">The Derived Column transformation can define multiple derived columns, and any variable or input columns can appear in multiple expressions.</span></span>  
  
 <span data-ttu-id="7ebbc-107">Преобразование можно применять для выполнения следующих задач.</span><span class="sxs-lookup"><span data-stu-id="7ebbc-107">You can use this transformation to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="7ebbc-108">Объединение данных из различных столбцов в производный столбец.</span><span class="sxs-lookup"><span data-stu-id="7ebbc-108">Concatenate data from different columns into a derived column.</span></span> <span data-ttu-id="7ebbc-109">Например, можно объединять значения из столбцов **FirstName** и **LastName** в один производный столбец под названием **FullName**с помощью выражения `FirstName + " " + LastName`.</span><span class="sxs-lookup"><span data-stu-id="7ebbc-109">For example, you can combine values from the **FirstName** and **LastName** columns into a single derived column named **FullName**, by using the expression `FirstName + " " + LastName`.</span></span>  
  
-   <span data-ttu-id="7ebbc-110">Извлечение символов из строки данных с помощью таких функций, как SUBSTRING, и последующего сохранения результата в производном столбце.</span><span class="sxs-lookup"><span data-stu-id="7ebbc-110">Extract characters from string data by using functions such as SUBSTRING, and then store the result in a derived column.</span></span> <span data-ttu-id="7ebbc-111">Например, можно извлечь инициалы сотрудника из столбца **FirstName** с помощью выражения `SUBSTRING(FirstName,1,1)`.</span><span class="sxs-lookup"><span data-stu-id="7ebbc-111">For example, you can extract a person's initial from the **FirstName** column, by using the expression `SUBSTRING(FirstName,1,1)`.</span></span>  
  
-   <span data-ttu-id="7ebbc-112">Применение математических функций к числовым данным и сохранение результата в производном столбце.</span><span class="sxs-lookup"><span data-stu-id="7ebbc-112">Apply mathematical functions to numeric data and store the result in a derived column.</span></span> <span data-ttu-id="7ebbc-113">Например, можно заменить длину и точность числового столбца **SalesTax**на число с двумя десятичными знаками с помощью выражения `ROUND(SalesTax, 2)`.</span><span class="sxs-lookup"><span data-stu-id="7ebbc-113">For example, you can change the length and precision of a numeric column, **SalesTax**, to a number with two decimal places, by using the expression `ROUND(SalesTax, 2)`.</span></span>  
  
-   <span data-ttu-id="7ebbc-114">Создание выражений, сравнивающих входные столбцы и переменные.</span><span class="sxs-lookup"><span data-stu-id="7ebbc-114">Create expressions that compare input columns and variables.</span></span> <span data-ttu-id="7ebbc-115">Например, можно сравнить переменную **Version** с данными в столбце **ProductVersion**и в зависимости от результата использовать либо значение переменной **Version** , либо значение **ProductVersion**с помощью выражения `ProductVersion == @Version? ProductVersion : @Version`.</span><span class="sxs-lookup"><span data-stu-id="7ebbc-115">For example, you can compare the variable **Version** against the data in the column **ProductVersion**, and depending on the comparison result, use the value of either **Version** or **ProductVersion**, by using the expression `ProductVersion == @Version? ProductVersion : @Version`.</span></span>  
  
-   <span data-ttu-id="7ebbc-116">Извлечение частей из значений типа datetime.</span><span class="sxs-lookup"><span data-stu-id="7ebbc-116">Extract parts of a datetime value.</span></span> <span data-ttu-id="7ebbc-117">Например, с помощью функций GETDATE и DATEPART можно извлечь текущий год с помощью выражения `DATEPART("year",GETDATE())`.</span><span class="sxs-lookup"><span data-stu-id="7ebbc-117">For example, you can use the GETDATE and DATEPART functions to extract the current year, by using the expression `DATEPART("year",GETDATE())`.</span></span>  
  
-   <span data-ttu-id="7ebbc-118">Конвертируйте строки даты в определенный формат, используя выражение.</span><span class="sxs-lookup"><span data-stu-id="7ebbc-118">Convert date strings to a specific format using an expression.</span></span>  
  
## <a name="configuration-of-the-derived-column-transformation"></a><span data-ttu-id="7ebbc-119">Настройка преобразования «Производный столбец»</span><span class="sxs-lookup"><span data-stu-id="7ebbc-119">Configuration of the Derived Column Transformation</span></span>  
 <span data-ttu-id="7ebbc-120">Можно настроить преобразование «Производный столбец» следующим образом.</span><span class="sxs-lookup"><span data-stu-id="7ebbc-120">You can configure the Derived column transformation in the following ways:</span></span>  
  
-   <span data-ttu-id="7ebbc-121">Указать выражение для каждого входного столбца или нового столбца, который будет изменен.</span><span class="sxs-lookup"><span data-stu-id="7ebbc-121">Provide an expression for each input column or new column that will be changed.</span></span> <span data-ttu-id="7ebbc-122">Дополнительные сведения см. в разделе [Выражения служб Integration Services (SSIS)](../../expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="7ebbc-122">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7ebbc-123">Если выражение ссылается на входной столбец, перезаписанный преобразованием «Производный столбец», то выражение использует первоначальное, а не производное значение столбца.</span><span class="sxs-lookup"><span data-stu-id="7ebbc-123">If an expression references an input column that is overwritten by the Derived Column transformation, the expression uses the original value of the column, not the derived value.</span></span>  
  
-   <span data-ttu-id="7ebbc-124">Добавляя результаты в новые столбцы с типом данных `string`, укажите кодовую страницу.</span><span class="sxs-lookup"><span data-stu-id="7ebbc-124">If adding results to new columns and the data type is `string`, specify a code page.</span></span> <span data-ttu-id="7ebbc-125">Дополнительные сведения см. в статье [Comparing String Data](../comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="7ebbc-125">For more information, see [Comparing String Data](../comparing-string-data.md).</span></span>  
  
 <span data-ttu-id="7ebbc-126">Преобразование "Производный столбец" содержит пользовательское свойство FriendlyExpression.</span><span class="sxs-lookup"><span data-stu-id="7ebbc-126">The Derived Column transformation includes the FriendlyExpression custom property.</span></span> <span data-ttu-id="7ebbc-127">Это свойство может быть обновлено выражением свойства при загрузке пакета.</span><span class="sxs-lookup"><span data-stu-id="7ebbc-127">This property can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="7ebbc-128">Дополнительные сведения см. в разделах [Использование выражений свойств в пакетах](../../expressions/use-property-expressions-in-packages.md)и [Пользовательские свойства преобразований](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="7ebbc-128">For more information, see [Use Property Expressions in Packages](../../expressions/use-property-expressions-in-packages.md), and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="7ebbc-129">Это преобразование содержит один вход, один обычный вывод и один вывод ошибок.</span><span class="sxs-lookup"><span data-stu-id="7ebbc-129">This transformation has one input, one regular output, and one error output.</span></span>  
  
 <span data-ttu-id="7ebbc-130">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="7ebbc-130">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="7ebbc-131">Дополнительные сведения о свойствах, которые можно установить в диалоговом окне **Редактор преобразования «Производный столбец»** , см. в разделе [Derived Column Transformation Editor](../../derived-column-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="7ebbc-131">For more information about the properties that you can set in the **Derived Column Transformation Editor** dialog box, see [Derived Column Transformation Editor](../../derived-column-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="7ebbc-132">Диалоговое окно **Расширенный редактор** содержит свойства, которые можно установить с помощью программных средств.</span><span class="sxs-lookup"><span data-stu-id="7ebbc-132">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="7ebbc-133">Дополнительные сведения о свойствах, которые вы можете задать в диалоговом окне **Расширенный редактор** или программными средствами, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="7ebbc-133">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="7ebbc-134">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="7ebbc-134">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="7ebbc-135">Пользовательские свойства преобразований</span><span class="sxs-lookup"><span data-stu-id="7ebbc-135">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="7ebbc-136">Дополнительные сведения о настройке свойств см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="7ebbc-136">For more information about how to set properties, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="7ebbc-137">Установление свойств компонента потока данных</span><span class="sxs-lookup"><span data-stu-id="7ebbc-137">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="7ebbc-138">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="7ebbc-138">Related Tasks</span></span>  
  
-   [<span data-ttu-id="7ebbc-139">Получение значений столбцов с помощью преобразования «Производный столбец»</span><span class="sxs-lookup"><span data-stu-id="7ebbc-139">Derive Column Values by Using the Derived Column Transformation</span></span>](derived-column-transformation.md)  
  
## <a name="related-content"></a><span data-ttu-id="7ebbc-140">См. также</span><span class="sxs-lookup"><span data-stu-id="7ebbc-140">Related Content</span></span>  
 <span data-ttu-id="7ebbc-141">Техническая статья [Примеры выражений служб SSIS](https://go.microsoft.com/fwlink/?LinkId=220761)на сайте social.technet.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7ebbc-141">Technical article, [SSIS Expression Examples](https://go.microsoft.com/fwlink/?LinkId=220761), on social.technet.microsoft.com</span></span>  
  
 <span data-ttu-id="7ebbc-142">Блог, [разделение данных столбцов с помощью служб SSIS](https://microsoft-ssis.blogspot.com/2012/10/split-multi-value-column-into-multiple.html).</span><span class="sxs-lookup"><span data-stu-id="7ebbc-142">Blog, [How to Split Column Data using SSIS](https://microsoft-ssis.blogspot.com/2012/10/split-multi-value-column-into-multiple.html).</span></span>  
  
  
