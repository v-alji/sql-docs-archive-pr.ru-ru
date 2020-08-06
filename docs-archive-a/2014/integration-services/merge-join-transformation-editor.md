---
title: Редактор преобразования "соединение слиянием" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.mergejointransformation.f1
helpviewer_keywords:
- Merge Join Transformation Editor
ms.assetid: ac06f419-30b3-42aa-8b34-42000bec4285
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e0d15d1233c2e0ff836e9dbd17459e56c48183f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665423"
---
# <a name="merge-join-transformation-editor"></a><span data-ttu-id="39ad9-102">редактор преобразования «Cоединение слиянием»</span><span class="sxs-lookup"><span data-stu-id="39ad9-102">Merge Join Transformation Editor</span></span>
  <span data-ttu-id="39ad9-103">Диалоговое окно **Редактор преобразования «Соединение слиянием»** используется для задания типа соединения, столбцов соединения и выходных столбцов для слияния двух входных наборов с помощью соединения.</span><span class="sxs-lookup"><span data-stu-id="39ad9-103">Use the **Merge Join Transformation Editor** dialog box to specify the join type, the join columns, and the output columns for merging two inputs combined by a join.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="39ad9-104">Преобразованию «Соединение слиянием» необходимы отсортированные входные данные.</span><span class="sxs-lookup"><span data-stu-id="39ad9-104">The Merge Join Transformation requires sorted data for its inputs.</span></span> <span data-ttu-id="39ad9-105">Дополнительные сведения об этом важном требовании см. в статье [Сортировка данных для преобразований "Слияние" и "Соединение слиянием"](data-flow/transformations/sort-data-for-the-merge-and-merge-join-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="39ad9-105">For more information about this important requirement, see [Sort Data for the Merge and Merge Join Transformations](data-flow/transformations/sort-data-for-the-merge-and-merge-join-transformations.md).</span></span>  
  
 <span data-ttu-id="39ad9-106">Дополнительные сведения о преобразовании «Соединение слиянием» см. в разделе [Merge Join Transformation](data-flow/transformations/merge-join-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="39ad9-106">To learn more about the Merge Join transformation, see [Merge Join Transformation](data-flow/transformations/merge-join-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="39ad9-107">Варианты</span><span class="sxs-lookup"><span data-stu-id="39ad9-107">Options</span></span>  
 <span data-ttu-id="39ad9-108">**Тип соединения**</span><span class="sxs-lookup"><span data-stu-id="39ad9-108">**Join type**</span></span>  
 <span data-ttu-id="39ad9-109">Укажите, нужно ли использовать внутреннее, левое внешнее или полное соединение.</span><span class="sxs-lookup"><span data-stu-id="39ad9-109">Specify whether you want to use an inner join, left outer join, or full join.</span></span>  
  
 <span data-ttu-id="39ad9-110">**Обменять выходы**</span><span class="sxs-lookup"><span data-stu-id="39ad9-110">**Swap Inputs**</span></span>  
 <span data-ttu-id="39ad9-111">Переключение порядка входов выполняется с помощью кнопки **Обменять выходы** .</span><span class="sxs-lookup"><span data-stu-id="39ad9-111">Switch the order between inputs by using the **Swap Inputs** button.</span></span> <span data-ttu-id="39ad9-112">Этот выбор может быть полезен с параметром левого внешнего соединения.</span><span class="sxs-lookup"><span data-stu-id="39ad9-112">This selection may be useful with the Left outer join option.</span></span>  
  
 <span data-ttu-id="39ad9-113">**Ввод**</span><span class="sxs-lookup"><span data-stu-id="39ad9-113">**Input**</span></span>  
 <span data-ttu-id="39ad9-114">Вначале выберите из списка имеющихся входов каждый столбец, который необходимо включить в объединенный вывод.</span><span class="sxs-lookup"><span data-stu-id="39ad9-114">For each column that you want in the merged output, first select from the list of available inputs.</span></span>  
  
 <span data-ttu-id="39ad9-115">Входы отображаются в двух отдельных таблицах.</span><span class="sxs-lookup"><span data-stu-id="39ad9-115">Inputs are displayed in two separate tables.</span></span> <span data-ttu-id="39ad9-116">Выберите столбцы для включения в вывод.</span><span class="sxs-lookup"><span data-stu-id="39ad9-116">Select columns to include in the output.</span></span> <span data-ttu-id="39ad9-117">Перетащите столбцы для создания соединения между таблицами.</span><span class="sxs-lookup"><span data-stu-id="39ad9-117">Drag columns to create a join between the tables.</span></span> <span data-ttu-id="39ad9-118">Для удаления соединения выберите его и нажмите клавишу DELETE.</span><span class="sxs-lookup"><span data-stu-id="39ad9-118">To delete a join, select it and then press the DELETE key.</span></span>  
  
 <span data-ttu-id="39ad9-119">**Входной столбец**</span><span class="sxs-lookup"><span data-stu-id="39ad9-119">**Input Column**</span></span>  
 <span data-ttu-id="39ad9-120">Из списка имеющихся столбцов на выбранном входе выберите столбец для включения в объединенный вывод.</span><span class="sxs-lookup"><span data-stu-id="39ad9-120">Select a column to include in the merged output from the list of available columns on the selected input.</span></span>  
  
 <span data-ttu-id="39ad9-121">**Псевдоним вывода**</span><span class="sxs-lookup"><span data-stu-id="39ad9-121">**Output Alias**</span></span>  
 <span data-ttu-id="39ad9-122">Введите псевдоним для каждого выходного столбца.</span><span class="sxs-lookup"><span data-stu-id="39ad9-122">Type an alias for each output column.</span></span> <span data-ttu-id="39ad9-123">По умолчанию, используется имя входного столбца, однако можно выбрать любое уникальное описательное имя.</span><span class="sxs-lookup"><span data-stu-id="39ad9-123">The default is the name of the input column; however, you can choose any unique, descriptive name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39ad9-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="39ad9-124">See Also</span></span>  
 <span data-ttu-id="39ad9-125">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="39ad9-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="39ad9-126">[Сортировка данных для преобразований «Слияние» и «соединение слиянием»](data-flow/transformations/sort-data-for-the-merge-and-merge-join-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="39ad9-126">[Sort Data for the Merge and Merge Join Transformations](data-flow/transformations/sort-data-for-the-merge-and-merge-join-transformations.md) </span></span>  
 <span data-ttu-id="39ad9-127">[Расширение набора данных с помощью преобразования «Соединение слиянием»](data-flow/transformations/extend-a-dataset-by-using-the-merge-join-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="39ad9-127">[Extend a Dataset by Using the Merge Join Transformation](data-flow/transformations/extend-a-dataset-by-using-the-merge-join-transformation.md) </span></span>  
 <span data-ttu-id="39ad9-128">[Преобразование «Слияние»](data-flow/transformations/merge-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="39ad9-128">[Merge Transformation](data-flow/transformations/merge-transformation.md) </span></span>  
 [<span data-ttu-id="39ad9-129">Преобразование "Объединить все"</span><span class="sxs-lookup"><span data-stu-id="39ad9-129">Union All Transformation</span></span>](data-flow/transformations/union-all-transformation.md)  
  
  
