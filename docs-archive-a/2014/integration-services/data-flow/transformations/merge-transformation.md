---
title: Преобразование "Слияние" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.mergetrans.f1
helpviewer_keywords:
- merging datasets [Integration Services]
- merging data [Integration Services]
- Merge transformation
- combining datasets
- datasets [Integration Services], merging
ms.assetid: cff8690c-07ac-46a0-aab5-20bd4848c677
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7d1d35e92b5978016b6a53956e5b6f1f6642f5ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740178"
---
# <a name="merge-transformation"></a><span data-ttu-id="b7995-102">преобразование «Слияние»</span><span class="sxs-lookup"><span data-stu-id="b7995-102">Merge Transformation</span></span>
  <span data-ttu-id="b7995-103">Преобразование «Слияние» объединяет два упорядоченных набора данных в один.</span><span class="sxs-lookup"><span data-stu-id="b7995-103">The Merge transformation combines two sorted datasets into a single dataset.</span></span> <span data-ttu-id="b7995-104">Строки из каждого набора данных вставляются в выходной набор на основе значений их ключевых столбцов.</span><span class="sxs-lookup"><span data-stu-id="b7995-104">The rows from each dataset are inserted into the output based on values in their key columns.</span></span>  
  
 <span data-ttu-id="b7995-105">Включая преобразование «Слияние» в поток данных, можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="b7995-105">By including the Merge transformation in a data flow, you can perform the following tasks:</span></span>  
  
-   <span data-ttu-id="b7995-106">Произвести слияние данных из двух источников данных, таких как таблицы и файлы.</span><span class="sxs-lookup"><span data-stu-id="b7995-106">Merge data from two data sources, such as tables and files.</span></span>  
  
-   <span data-ttu-id="b7995-107">Создать сложные наборы данных при помощи вложенных преобразований «Слияние».</span><span class="sxs-lookup"><span data-stu-id="b7995-107">Create complex datasets by nesting Merge transformations.</span></span>  
  
-   <span data-ttu-id="b7995-108">Произвести повторное слияние строк после исправления ошибок в данных.</span><span class="sxs-lookup"><span data-stu-id="b7995-108">Remerge rows after correcting errors in the data.</span></span>  
  
 <span data-ttu-id="b7995-109">Преобразование «Слияние» похоже на преобразование «Объединить все».</span><span class="sxs-lookup"><span data-stu-id="b7995-109">The Merge transformation is similar to the Union All transformations.</span></span> <span data-ttu-id="b7995-110">Используйте преобразование «Объединить все» вместо преобразования «Слияние» в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="b7995-110">Use the Union All transformation instead of the Merge transformation in the following situations:</span></span>  
  
-   <span data-ttu-id="b7995-111">Входы преобразования не упорядочены.</span><span class="sxs-lookup"><span data-stu-id="b7995-111">The transformation inputs are not sorted.</span></span>  
  
-   <span data-ttu-id="b7995-112">Объединенный выход не требует упорядочения.</span><span class="sxs-lookup"><span data-stu-id="b7995-112">The combined output does not need to be sorted.</span></span>  
  
-   <span data-ttu-id="b7995-113">Преобразование имеет более двух входов.</span><span class="sxs-lookup"><span data-stu-id="b7995-113">The transformation has more than two inputs.</span></span>  
  
## <a name="input-requirements"></a><span data-ttu-id="b7995-114">Требования к входным данным</span><span class="sxs-lookup"><span data-stu-id="b7995-114">Input Requirements</span></span>  
 <span data-ttu-id="b7995-115">Преобразованию «Слияние» необходимы отсортированные входные данные.</span><span class="sxs-lookup"><span data-stu-id="b7995-115">The Merge Transformation requires sorted data for its inputs.</span></span> <span data-ttu-id="b7995-116">Дополнительные сведения об этом важном требовании см. в статье [Сортировка данных для преобразований "Слияние" и "Соединение слиянием"](sort-data-for-the-merge-and-merge-join-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="b7995-116">For more information about this important requirement, see [Sort Data for the Merge and Merge Join Transformations](sort-data-for-the-merge-and-merge-join-transformations.md).</span></span>  
  
 <span data-ttu-id="b7995-117">Кроме того, преобразование «Слияние» требует, чтобы у объединенных столбцов входных данных совпадали метаданные.</span><span class="sxs-lookup"><span data-stu-id="b7995-117">The Merge transformation also requires that the merged columns in its inputs have matching metadata.</span></span> <span data-ttu-id="b7995-118">Например, нельзя произвести слияние столбца числового типа данных со столбцом символьного типа.</span><span class="sxs-lookup"><span data-stu-id="b7995-118">For example, you cannot merge a column that has a numeric data type with a column that has a character data type.</span></span> <span data-ttu-id="b7995-119">Если данные представляют собой тип строковых данных, длина столбца при вторичном входе должна быть меньше или равна длине столбца при первичном входе, с которым происходит слияние.</span><span class="sxs-lookup"><span data-stu-id="b7995-119">If the data has a string data type, the length of the column in the second input must be less than or equal to the length of the column in the first input with which it is merged.</span></span>  
  
 <span data-ttu-id="b7995-120">Пользовательский интерфейс для преобразования «Слияние» в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] автоматически сопоставляет столбцы с одинаковыми метаданными.</span><span class="sxs-lookup"><span data-stu-id="b7995-120">In the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, the user interface for the Merge transformation automatically maps columns that have the same metadata.</span></span> <span data-ttu-id="b7995-121">Затем можно вручную сопоставить столбцы с совместимыми типами данных.</span><span class="sxs-lookup"><span data-stu-id="b7995-121">You can then manually map other columns that have compatible data types.</span></span>  
  
 <span data-ttu-id="b7995-122">Это преобразование имеет два входа и один выход.</span><span class="sxs-lookup"><span data-stu-id="b7995-122">This transformation has two inputs and one output.</span></span> <span data-ttu-id="b7995-123">Вывод ошибок не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="b7995-123">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-merge-transformation"></a><span data-ttu-id="b7995-124">Настройка преобразования «Слияние»</span><span class="sxs-lookup"><span data-stu-id="b7995-124">Configuration of the Merge Transformation</span></span>  
 <span data-ttu-id="b7995-125">Свойства могут устанавливаться через конструктор служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] или с помощью программных средств.</span><span class="sxs-lookup"><span data-stu-id="b7995-125">You can set properties through the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="b7995-126">Дополнительные сведения о параметрах, задаваемых в диалоговом окне **Редактор преобразования «Слияние»** , см. в разделе [Merge Transformation Editor](../../merge-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="b7995-126">For more information about the properties that you can set in the **Merge Transformation Editor** dialog box, see [Merge Transformation Editor](../../merge-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="b7995-127">Дополнительные сведения о параметрах, задаваемых программно, см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="b7995-127">For more information about the properties that you can programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="b7995-128">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="b7995-128">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="b7995-129">Пользовательские свойства преобразований</span><span class="sxs-lookup"><span data-stu-id="b7995-129">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="b7995-130">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="b7995-130">Related Tasks</span></span>  
 <span data-ttu-id="b7995-131">Дополнительные сведения о способах задания свойств см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="b7995-131">For details about how to set properties, see the following topics:</span></span>  
  
-   [<span data-ttu-id="b7995-132">Установление свойств компонента потока данных</span><span class="sxs-lookup"><span data-stu-id="b7995-132">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
-   [<span data-ttu-id="b7995-133">Сортировка данных для преобразований "Слияние" и "Соединение слиянием"</span><span class="sxs-lookup"><span data-stu-id="b7995-133">Sort Data for the Merge and Merge Join Transformations</span></span>](sort-data-for-the-merge-and-merge-join-transformations.md)  
  
## <a name="see-also"></a><span data-ttu-id="b7995-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="b7995-134">See Also</span></span>  
 <span data-ttu-id="b7995-135">[Преобразование «Соединение слиянием»](merge-join-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="b7995-135">[Merge Join Transformation](merge-join-transformation.md) </span></span>  
 <span data-ttu-id="b7995-136">[Преобразование «Объединить все»](union-all-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="b7995-136">[Union All Transformation](union-all-transformation.md) </span></span>  
 <span data-ttu-id="b7995-137">[Поток данных](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="b7995-137">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="b7995-138">Преобразования служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="b7995-138">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
