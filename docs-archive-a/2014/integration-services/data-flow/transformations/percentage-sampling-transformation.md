---
title: Преобразование "Процентная выборка" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.percentagesamplingtrans.f1
helpviewer_keywords:
- testing mining models
- sampling seeds [Integration Services]
- data mining [Analysis Services], sample data sets
- Percentage Sampling transformation
- sample data sets [Integration Services]
- datasets [Integration Services], sample
- training mining models
ms.assetid: 59767e52-f732-4b3f-8602-be50d0a64ef2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e5fe41ecf4a2ca0f9d20eec2c8e10af8ed4cd47b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752320"
---
# <a name="percentage-sampling-transformation"></a><span data-ttu-id="036e3-102">преобразование «Процентная выборка»</span><span class="sxs-lookup"><span data-stu-id="036e3-102">Percentage Sampling Transformation</span></span>
  <span data-ttu-id="036e3-103">Преобразование «Процентная выборка» создает образец набора данных извлечением некоторого процента входных строк преобразования.</span><span class="sxs-lookup"><span data-stu-id="036e3-103">The Percentage Sampling transformation creates a sample data set by selecting a percentage of the transformation input rows.</span></span> <span data-ttu-id="036e3-104">Данные выборки извлекаются случайным образом из входа преобразования. За счет этого достигается репрезентативность выборки.</span><span class="sxs-lookup"><span data-stu-id="036e3-104">The sample data set is a random selection of rows from the transformation input, to make the resultant sample representative of the input.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="036e3-105">Помимо заданного количества процентов преобразование «Процентная выборка» использует алгоритм, определяющий возможность включения строки в результирующую выборку.</span><span class="sxs-lookup"><span data-stu-id="036e3-105">In addition to the specified percentage, the Percentage Sampling transformation uses an algorithm to determine whether a row should be included in the sample output.</span></span> <span data-ttu-id="036e3-106">Это означает, что количество строк в выборке может не соответствовать точно заданному количеству процентов.</span><span class="sxs-lookup"><span data-stu-id="036e3-106">This means that the number of rows in the sample output may not exactly reflect the specified percentage.</span></span> <span data-ttu-id="036e3-107">Например, определив 10 процентов от входного набора данных, содержащего 25000 строк, можно получить выборку, содержащую немного больше или немного меньше, чем 2500 строк.</span><span class="sxs-lookup"><span data-stu-id="036e3-107">For example, specifying 10 percent for an input data set that has 25,000 rows may not generate a sample with 2,500 rows; the sample may have a few more or a few less rows.</span></span>  
  
 <span data-ttu-id="036e3-108">Преобразование «Процентная выборка» особенно полезно для интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="036e3-108">The Percentage Sampling transformation is especially useful for data mining.</span></span> <span data-ttu-id="036e3-109">С помощью этого преобразования можно случайным образом разделить набор данных на два набора: один — для изучения модели интеллектуального анализа данных, другой — для тестирования этой модели.</span><span class="sxs-lookup"><span data-stu-id="036e3-109">By using this transformation, you can randomly divide a data set into two data sets: one for training the data mining model, and one for testing the model.</span></span>  
  
 <span data-ttu-id="036e3-110">Преобразование «Процентная выборка» также полезно для создания образца набора данных, используемого при разработке пакета.</span><span class="sxs-lookup"><span data-stu-id="036e3-110">The Percentage Sampling transformation is also useful for creating sample data sets for package development.</span></span> <span data-ttu-id="036e3-111">Применяя преобразование «Процентная выборка» к потоку данных, можно уменьшить размер набора данных, сохраняя его статистические характеристики.</span><span class="sxs-lookup"><span data-stu-id="036e3-111">By applying the Percentage Sampling transformation to a data flow, you can uniformly reduce the size of the data set while preserving its data characteristics.</span></span> <span data-ttu-id="036e3-112">Тестовый пакет можно выполнить быстрее, потому что он содержит меньший, но репрезентативный набор данных.</span><span class="sxs-lookup"><span data-stu-id="036e3-112">The test package can then run more quickly because it uses a small, but representative, data set.</span></span>  
  
## <a name="configuration-the-percentage-sampling-transformation"></a><span data-ttu-id="036e3-113">Настройка преобразования «Процентная выборка»</span><span class="sxs-lookup"><span data-stu-id="036e3-113">Configuration the Percentage Sampling Transformation</span></span>  
 <span data-ttu-id="036e3-114">Можно изменить начальное значение генератора случайных чисел, используемого для выборки строк.</span><span class="sxs-lookup"><span data-stu-id="036e3-114">You can specify a sampling seed to modify the behavior of the random number generator that the transformation uses to select rows.</span></span> <span data-ttu-id="036e3-115">Если всегда использовать одинаковое начальное значение для генератора, то результирующая выборка, при прочих равных условиях, будет тоже всегда одинаковая.</span><span class="sxs-lookup"><span data-stu-id="036e3-115">If the same sampling seed is used, the transformation always creates the same sample output.</span></span> <span data-ttu-id="036e3-116">Если начальное значение для создания случайного номера не указано, преобразование использует счетчик тактов операционной системы.</span><span class="sxs-lookup"><span data-stu-id="036e3-116">If no seed is specified, the transformation uses the tick count of the operating system to create the random number.</span></span> <span data-ttu-id="036e3-117">Поэтому можно выбрать постоянное начальное значение для генератора во время отладки и случайное значение при передаче пакета в производственную эксплуатацию.</span><span class="sxs-lookup"><span data-stu-id="036e3-117">Therefore, you might choose to use a standard seed when you want to verify the transformation results during the development and testing of a package, and then change to use a random seed when the package is moved into production.</span></span>  
  
 <span data-ttu-id="036e3-118">Это преобразование немного схоже с преобразованием «Выборка строк», которое создает выборку с заданным количеством строк.</span><span class="sxs-lookup"><span data-stu-id="036e3-118">This transformation is similar to the Row Sampling transformation, which creates a sample data set by selecting a specified number of the input rows.</span></span> <span data-ttu-id="036e3-119">Дополнительные сведения см. в разделе [Row Sampling Transformation](row-sampling-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="036e3-119">For more information, see [Row Sampling Transformation](row-sampling-transformation.md).</span></span>  
  
 <span data-ttu-id="036e3-120">Преобразование «Процентная выборка» содержит пользовательское свойство `SamplingValue`.</span><span class="sxs-lookup"><span data-stu-id="036e3-120">The Percentage Sampling transformation includes the `SamplingValue` custom property.</span></span> <span data-ttu-id="036e3-121">Это свойство может быть обновлено выражением свойства при загрузке пакета.</span><span class="sxs-lookup"><span data-stu-id="036e3-121">This property can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="036e3-122">Дополнительные сведения см. в разделах [Выражения служб Integration Services (SSIS)](../../expressions/integration-services-ssis-expressions.md), [Использование выражений свойств в пакетах](../../expressions/use-property-expressions-in-packages.md) и [Пользовательские свойства преобразований](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="036e3-122">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md), [Use Property Expressions in Packages](../../expressions/use-property-expressions-in-packages.md), and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="036e3-123">Преобразование имеет один вход и два выхода.</span><span class="sxs-lookup"><span data-stu-id="036e3-123">The transformation has one input and two outputs.</span></span> <span data-ttu-id="036e3-124">Вывод ошибок не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="036e3-124">It does not support an error output.</span></span>  
  
 <span data-ttu-id="036e3-125">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="036e3-125">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="036e3-126">Дополнительные сведения о свойствах, которые можно установить в диалоговом окне **Редактор преобразования «Процентная выборка»** , см. в разделе [Percentage Sampling Transformation Editor](../../percentage-sampling-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="036e3-126">For more information about the properties that you can set in the **Percentage Sampling Transformation Editor** dialog box, see [Percentage Sampling Transformation Editor](../../percentage-sampling-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="036e3-127">Диалоговое окно **Расширенный редактор** содержит свойства, которые можно установить с помощью программных средств.</span><span class="sxs-lookup"><span data-stu-id="036e3-127">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="036e3-128">Дополнительные сведения о свойствах, которые вы можете задать в диалоговом окне **Расширенный редактор** или программными средствами, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="036e3-128">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="036e3-129">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="036e3-129">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="036e3-130">Пользовательские свойства преобразований</span><span class="sxs-lookup"><span data-stu-id="036e3-130">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="036e3-131">Дополнительные сведения о настройке свойств см. в разделе [Установление свойств компонента потока данных](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="036e3-131">For more information about how to set properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
