---
title: Преобразование "Объединить все" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.unionalltrans.f1
helpviewer_keywords:
- merging datasets [Integration Services]
- combining datasets
- Union All transformation
- datasets [Integration Services], merging
ms.assetid: 942e4b90-9c41-4e9c-a6f3-80b3afe57f2f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: eaaab1abf2587979e947cc1be24cbedf8f61b6e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667304"
---
# <a name="union-all-transformation"></a><span data-ttu-id="3bd5a-102">преобразование «Объединить все»</span><span class="sxs-lookup"><span data-stu-id="3bd5a-102">Union All Transformation</span></span>
  <span data-ttu-id="3bd5a-103">Преобразование «Объединить все» объединяет несколько входов в один выход.</span><span class="sxs-lookup"><span data-stu-id="3bd5a-103">The Union All transformation combines multiple inputs into one output.</span></span> <span data-ttu-id="3bd5a-104">Например, выходы из пяти различных источников неструктурированных файлов можно сделать входами для преобразования «Объединить все» и объединить в один выход.</span><span class="sxs-lookup"><span data-stu-id="3bd5a-104">For example, the outputs from five different Flat File sources can be inputs to the Union All transformation and combined into one output.</span></span>  
  
## <a name="inputs-and-outputs"></a><span data-ttu-id="3bd5a-105">Входы и выходы</span><span class="sxs-lookup"><span data-stu-id="3bd5a-105">Inputs and Outputs</span></span>  
 <span data-ttu-id="3bd5a-106">Входы преобразования добавляются к выходу преобразования один за другим без переупорядочения строк.</span><span class="sxs-lookup"><span data-stu-id="3bd5a-106">The transformation inputs are added to the transformation output one after the other; no reordering of rows occurs.</span></span> <span data-ttu-id="3bd5a-107">Если пакет требует сортировки выхода, то вместо преобразования «Объединить все» следует применять преобразование «Слияние».</span><span class="sxs-lookup"><span data-stu-id="3bd5a-107">If the package requires a sorted output, you should use the Merge transformation instead of the Union All transformation.</span></span>  
  
 <span data-ttu-id="3bd5a-108">Первый вход, подключенный к преобразованию «Объединить все» — это вход, из которого преобразование создает собственный выход.</span><span class="sxs-lookup"><span data-stu-id="3bd5a-108">The first input that you connect to the Union All transformation is the input from which the transformation creates the transformation output.</span></span> <span data-ttu-id="3bd5a-109">Входные столбцы, которые впоследствии будут подключены к преобразованию, сопоставляются со столбцами в выходе преобразования.</span><span class="sxs-lookup"><span data-stu-id="3bd5a-109">The columns in the inputs you subsequently connect to the transformation are mapped to the columns in the transformation output.</span></span>  
  
 <span data-ttu-id="3bd5a-110">Для слияния входов нужно сопоставить входные и выходные столбцы.</span><span class="sxs-lookup"><span data-stu-id="3bd5a-110">To merge inputs, you map columns in the inputs to columns in the output.</span></span> <span data-ttu-id="3bd5a-111">Необходимо, чтобы хотя бы один вход был сопоставлен каждому выходному столбцу.</span><span class="sxs-lookup"><span data-stu-id="3bd5a-111">A column from at least one input must be mapped to each output column.</span></span> <span data-ttu-id="3bd5a-112">Сопоставление двух столбцов требует, чтобы метаданные этих столбцов совпадали.</span><span class="sxs-lookup"><span data-stu-id="3bd5a-112">The mapping between two columns requires that the metadata of the columns match.</span></span> <span data-ttu-id="3bd5a-113">Например, сопоставленные столбцы должны относиться к одному и тому же типу данных.</span><span class="sxs-lookup"><span data-stu-id="3bd5a-113">For example, the mapped columns must have the same data type.</span></span>  
  
 <span data-ttu-id="3bd5a-114">Если сопоставленные столбцы содержат строковые данные, а длина выходного столбца меньше, чем длина входного, то выходной столбец автоматически увеличивается до нужной длины.</span><span class="sxs-lookup"><span data-stu-id="3bd5a-114">If the mapped columns contain string data and the output column is shorter in length than the input column, the output column is automatically increased in length to contain the input column.</span></span> <span data-ttu-id="3bd5a-115">Входные столбцы, не сопоставленные выходным столбцам, получают на выходных столбцах значения NULL.</span><span class="sxs-lookup"><span data-stu-id="3bd5a-115">Input columns that are not mapped to output columns are set to null values in the output columns.</span></span>  
  
 <span data-ttu-id="3bd5a-116">Это преобразование имеет несколько входов и один выход.</span><span class="sxs-lookup"><span data-stu-id="3bd5a-116">This transformation has multiple inputs and one output.</span></span> <span data-ttu-id="3bd5a-117">Вывод ошибок не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="3bd5a-117">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-union-all-transformation"></a><span data-ttu-id="3bd5a-118">Настройка преобразования «Объединить все»</span><span class="sxs-lookup"><span data-stu-id="3bd5a-118">Configuration of the Union All Transformation</span></span>  
 <span data-ttu-id="3bd5a-119">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="3bd5a-119">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="3bd5a-120">Дополнительные сведения о свойствах, которые можно установить в диалоговом окне **Редактор преобразования «Объединить все»** , см. в разделе [Union All Transformation Editor](../../union-all-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="3bd5a-120">For more information about the properties that you can set in the **Union All Transformation Editor** dialog box, see [Union All Transformation Editor](../../union-all-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="3bd5a-121">Дополнительные сведения о свойствах, которые можно задать программно, см. в разделе [Common Properties](../../common-properties.md).</span><span class="sxs-lookup"><span data-stu-id="3bd5a-121">For more information about the properties that you can set programmatically, see [Common Properties](../../common-properties.md).</span></span>  
  
 <span data-ttu-id="3bd5a-122">Дополнительные сведения о настройке свойств см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="3bd5a-122">For more information about how to set properties, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="3bd5a-123">Установление свойств компонента потока данных</span><span class="sxs-lookup"><span data-stu-id="3bd5a-123">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="3bd5a-124">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="3bd5a-124">Related Tasks</span></span>  
 [<span data-ttu-id="3bd5a-125">Выполнение слияния данных с помощью преобразования «Объединить все»</span><span class="sxs-lookup"><span data-stu-id="3bd5a-125">Merge Data by Using the Union All Transformation</span></span>](union-all-transformation.md)  
  
  
