---
title: Преобразование "Выборка строк" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rowsamplingtrans.f1
helpviewer_keywords:
- sampling seeds [Integration Services]
- random seeds
- random sampling
- sample data sets [Integration Services]
- Row Sampling transformation
- packages [Integration Services], samples
- datasets [Integration Services], sample
ms.assetid: b6caafd3-30b2-4368-82af-a44611d4cd39
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c56f07d9fafa03752ef8c6572a13c6ad7c02a8c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752315"
---
# <a name="row-sampling-transformation"></a><span data-ttu-id="c7e29-102">преобразование «Выборка строк»</span><span class="sxs-lookup"><span data-stu-id="c7e29-102">Row Sampling Transformation</span></span>
  <span data-ttu-id="c7e29-103">Преобразование «Выборка строк» используется для получения случайно выбранного подмножества входного набора данных.</span><span class="sxs-lookup"><span data-stu-id="c7e29-103">The Row Sampling transformation is used to obtain a randomly selected subset of an input dataset.</span></span> <span data-ttu-id="c7e29-104">Можно указать точный размер получаемого образца и задать начальное значение для генератора случайных чисел.</span><span class="sxs-lookup"><span data-stu-id="c7e29-104">You can specify the exact size of the output sample, and specify a seed for the random number generator.</span></span>  
  
 <span data-ttu-id="c7e29-105">Случайная выборка может применяться в различных ситуациях.</span><span class="sxs-lookup"><span data-stu-id="c7e29-105">There are many applications for random sampling.</span></span> <span data-ttu-id="c7e29-106">Например, если в какой-то компании требуется случайным образом выбрать 50 сотрудников для получения призов в лотерее, можно воспользоваться преобразованием «Выборка строк» в базе данных сотрудников, чтобы сформировать точное число победителей.</span><span class="sxs-lookup"><span data-stu-id="c7e29-106">For example, a company that wanted to randomly select 50 employees to receive prizes in a lottery could use the Row Sampling transformation on the employee database to generate the exact number of winners.</span></span>  
  
 <span data-ttu-id="c7e29-107">Преобразование «Выборка строк» используется также во время разработки пакета, чтобы создать небольшой, но репрезентативный набор данных.</span><span class="sxs-lookup"><span data-stu-id="c7e29-107">The Row Sampling transformation is also useful during package development for creating a small but representative dataset.</span></span> <span data-ttu-id="c7e29-108">С помощью репрезентативного набора данных выполнение пакета и преобразование данных можно протестировать гораздо быстрее за счет использования случайной выборки вместо полного набора данных.</span><span class="sxs-lookup"><span data-stu-id="c7e29-108">You can test package execution and data transformation with richly representative data, but more quickly because a random sample is used instead of the full dataset.</span></span> <span data-ttu-id="c7e29-109">Поскольку выбранный набор данных, используемый в тестовом пакете, всегда одного и того же размера, с помощью выбранного подмножества легче распознать проблемы производительности в пакете.</span><span class="sxs-lookup"><span data-stu-id="c7e29-109">Because the sample dataset used by the test package is always the same size, using the sample subset also makes it easier to identify performance problems in the package.</span></span>  
  
 <span data-ttu-id="c7e29-110">Это преобразование имеет сходство с преобразованием «Процентная выборка», которое создает набор данных с помощью выбора количества строк, заданного в процентах.</span><span class="sxs-lookup"><span data-stu-id="c7e29-110">This transformation is similar to the Percentage Sampling transformation, which creates a sample dataset by selecting a percentage of the input rows.</span></span> <span data-ttu-id="c7e29-111">См. раздел [Percentage Sampling Transformation](percentage-sampling-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="c7e29-111">See [Percentage Sampling Transformation](percentage-sampling-transformation.md).</span></span>  
  
## <a name="configuring-the-row-sampling-transformation"></a><span data-ttu-id="c7e29-112">Настройка преобразования «Выборка строк»</span><span class="sxs-lookup"><span data-stu-id="c7e29-112">Configuring the Row Sampling Transformation</span></span>  
 <span data-ttu-id="c7e29-113">Преобразование «Выборка строк» создает набор данных с помощью извлечения заданного количества строк со входа преобразования.</span><span class="sxs-lookup"><span data-stu-id="c7e29-113">The Row Sampling transformation creates a sample dataset by selecting a specified number of the transformation input rows.</span></span> <span data-ttu-id="c7e29-114">Поскольку выбор строк со входа преобразования происходит случайным образом, результирующая выборка содержит репрезентативный набор входных данных.</span><span class="sxs-lookup"><span data-stu-id="c7e29-114">Because the selection of rows from the transformation input is random, the resultant sample is representative of the input.</span></span> <span data-ttu-id="c7e29-115">Можно задать начальное значение генератора случайных чисел, чтобы изменить выбор строк преобразованием.</span><span class="sxs-lookup"><span data-stu-id="c7e29-115">You can also specify the seed that is used by the random number generator, to affect how the transformation selects rows.</span></span>  
  
 <span data-ttu-id="c7e29-116">Использование одного и того же начального значения на одном и том же входе преобразования всегда приводит к созданию одной и той же выходной выборки.</span><span class="sxs-lookup"><span data-stu-id="c7e29-116">Using the same random seed on the same transformation input always creates the same sample output.</span></span> <span data-ttu-id="c7e29-117">Если начальное значение для создания случайного номера не указано, преобразование использует счетчик тактов операционной системы.</span><span class="sxs-lookup"><span data-stu-id="c7e29-117">If no seed is specified, the transformation uses the tick count of the operating system to create the random number.</span></span> <span data-ttu-id="c7e29-118">Поэтому для проверки результатов преобразования во время разработки и тестирования пакета нужно использовать одно и то же начальное значение, которое изменяется на случайное, когда пакет выпускается в производственную среду.</span><span class="sxs-lookup"><span data-stu-id="c7e29-118">Therefore, you could use the same seed during testing, to verify the transformation results during the development and testing of the package, and then change to a random seed when the package is moved into production.</span></span>  
  
 <span data-ttu-id="c7e29-119">Преобразование «Выборка строк» включает в себя пользовательское свойство `SamplingValue`.</span><span class="sxs-lookup"><span data-stu-id="c7e29-119">The Row Sampling transformation includes the `SamplingValue` custom property.</span></span> <span data-ttu-id="c7e29-120">Это свойство может быть обновлено выражением свойства при загрузке пакета.</span><span class="sxs-lookup"><span data-stu-id="c7e29-120">This property can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="c7e29-121">Дополнительные сведения см. в разделах [Выражения служб Integration Services (SSIS)](../../expressions/integration-services-ssis-expressions.md), [Использование выражений свойств в пакетах](../../expressions/use-property-expressions-in-packages.md) и [Пользовательские свойства преобразований](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="c7e29-121">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md), [Use Property Expressions in Packages](../../expressions/use-property-expressions-in-packages.md), and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="c7e29-122">Преобразование имеет один вход и два выхода.</span><span class="sxs-lookup"><span data-stu-id="c7e29-122">This transformation has one input and two outputs.</span></span> <span data-ttu-id="c7e29-123">Оно не имеет выхода ошибок.</span><span class="sxs-lookup"><span data-stu-id="c7e29-123">It has no error output.</span></span>  
  
 <span data-ttu-id="c7e29-124">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="c7e29-124">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="c7e29-125">Дополнительные сведения о свойствах, которые можно установить в диалоговом окне **Редактор преобразования "Выборка строк"**, см. в разделе [Редактор преобразования "Выборка строк" (страница "Выборка")](../../row-sampling-transformation-editor-sampling-page.md).</span><span class="sxs-lookup"><span data-stu-id="c7e29-125">For more information about the properties that you can set in the **Row Sampling Transformation Editor** dialog box, see [Row Sampling Transformation Editor &#40;Sampling Page&#41;](../../row-sampling-transformation-editor-sampling-page.md).</span></span>  
  
 <span data-ttu-id="c7e29-126">Диалоговое окно **Расширенный редактор** содержит свойства, которые можно установить с помощью программных средств.</span><span class="sxs-lookup"><span data-stu-id="c7e29-126">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="c7e29-127">Дополнительные сведения о свойствах, которые вы можете задать в диалоговом окне **Расширенный редактор** или программными средствами, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="c7e29-127">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="c7e29-128">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="c7e29-128">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="c7e29-129">Пользовательские свойства преобразований</span><span class="sxs-lookup"><span data-stu-id="c7e29-129">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="c7e29-130">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="c7e29-130">Related Tasks</span></span>  
 [<span data-ttu-id="c7e29-131">Установление свойств компонента потока данных</span><span class="sxs-lookup"><span data-stu-id="c7e29-131">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
  
