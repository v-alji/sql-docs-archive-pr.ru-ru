---
title: Редактор преобразования "Сортировка" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sorttransformation.f1
helpviewer_keywords:
- Sort Transformation Editor
ms.assetid: 8ae23970-49a9-4d6d-9f15-c7074783347c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9f48c366f4337af29b03877f6bb20b804457a293
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751248"
---
# <a name="sort-transformation-editor"></a><span data-ttu-id="9bbaf-102">редактор преобразования «Сортировка»</span><span class="sxs-lookup"><span data-stu-id="9bbaf-102">Sort Transformation Editor</span></span>
  <span data-ttu-id="9bbaf-103">Диалоговое окно **Редактор преобразования «Сортировка»** используется для выбора сортируемых столбцов, установки порядка сортировки, а также позволяет указать, следует ли удалять дубликаты.</span><span class="sxs-lookup"><span data-stu-id="9bbaf-103">Use the **Sort Transformation Editor** dialog box to select the columns to sort, set the sort order, and specify whether duplicates are removed.</span></span>  
  
 <span data-ttu-id="9bbaf-104">Дополнительные сведения о преобразовании «Сортировка» см. в разделе [Sort Transformation](data-flow/transformations/sort-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="9bbaf-104">To learn more about the Sort transformation, see [Sort Transformation](data-flow/transformations/sort-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="9bbaf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9bbaf-105">Options</span></span>  
 <span data-ttu-id="9bbaf-106">**Доступные входные столбцы**</span><span class="sxs-lookup"><span data-stu-id="9bbaf-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="9bbaf-107">Укажите столбцы, подлежащие сортировке, с помощью соответствующих флажков.</span><span class="sxs-lookup"><span data-stu-id="9bbaf-107">Using the check boxes, specify the columns to sort.</span></span>  
  
 <span data-ttu-id="9bbaf-108">**имя**;</span><span class="sxs-lookup"><span data-stu-id="9bbaf-108">**Name**</span></span>  
 <span data-ttu-id="9bbaf-109">Позволяет просмотреть имя каждого из доступных входных столбцов.</span><span class="sxs-lookup"><span data-stu-id="9bbaf-109">View the name of each available input column.</span></span>  
  
 <span data-ttu-id="9bbaf-110">**Сылка**</span><span class="sxs-lookup"><span data-stu-id="9bbaf-110">**Passthrough**</span></span>  
 <span data-ttu-id="9bbaf-111">Указывает, включать ли столбец в сортировку на выводе.</span><span class="sxs-lookup"><span data-stu-id="9bbaf-111">Indicate whether to include the column in the sorted output.</span></span>  
  
 <span data-ttu-id="9bbaf-112">**Входной столбец**</span><span class="sxs-lookup"><span data-stu-id="9bbaf-112">**Input Column**</span></span>  
 <span data-ttu-id="9bbaf-113">Выберите для каждой строки столбец из списка доступных входных столбцов.</span><span class="sxs-lookup"><span data-stu-id="9bbaf-113">Select from the list of available input columns for each row.</span></span> <span data-ttu-id="9bbaf-114">Выбранные столбцы обозначаются флажками в таблице **Доступные входные столбцы** .</span><span class="sxs-lookup"><span data-stu-id="9bbaf-114">Your selections are reflected in the check box selections in the **Available Input Columns** table.</span></span>  
  
 <span data-ttu-id="9bbaf-115">**Псевдоним вывода**</span><span class="sxs-lookup"><span data-stu-id="9bbaf-115">**Output Alias**</span></span>  
 <span data-ttu-id="9bbaf-116">Введите псевдоним для каждого выходного столбца.</span><span class="sxs-lookup"><span data-stu-id="9bbaf-116">Type an alias for each output column.</span></span> <span data-ttu-id="9bbaf-117">По умолчанию, используется имя входного столбца, однако можно выбрать любое уникальное описательное имя.</span><span class="sxs-lookup"><span data-stu-id="9bbaf-117">The default is the name of the input column; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="9bbaf-118">**Тип сортировки**</span><span class="sxs-lookup"><span data-stu-id="9bbaf-118">**Sort Type**</span></span>  
 <span data-ttu-id="9bbaf-119">Указывает тип сортировки — по возрастанию или по убыванию.</span><span class="sxs-lookup"><span data-stu-id="9bbaf-119">Indicate whether to sort in ascending or descending order.</span></span>  
  
 <span data-ttu-id="9bbaf-120">**Порядок сортировки**</span><span class="sxs-lookup"><span data-stu-id="9bbaf-120">**Sort Order**</span></span>  
 <span data-ttu-id="9bbaf-121">Указывает порядок сортировки столбцов.</span><span class="sxs-lookup"><span data-stu-id="9bbaf-121">Indicate the order in which to sort columns.</span></span> <span data-ttu-id="9bbaf-122">Этот параметр должен быть установлен вручную для каждого столбца.</span><span class="sxs-lookup"><span data-stu-id="9bbaf-122">This must be set manually for each column.</span></span>  
  
 <span data-ttu-id="9bbaf-123">**Флаги сравнения**</span><span class="sxs-lookup"><span data-stu-id="9bbaf-123">**Comparison Flags**</span></span>  
 <span data-ttu-id="9bbaf-124">Дополнительные сведения о параметрах сравнения строк см. в разделе [Сравнение строковых данных](data-flow/comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="9bbaf-124">For information about the string comparison options, see [Comparing String Data](data-flow/comparing-string-data.md).</span></span>  
  
 <span data-ttu-id="9bbaf-125">**Удалить строки с повторяющимися значениями сортировки**</span><span class="sxs-lookup"><span data-stu-id="9bbaf-125">**Remove rows with duplicate sort values**</span></span>  
 <span data-ttu-id="9bbaf-126">Указывает, будут ли повторяющиеся строки при преобразовании скопированы на выход или же для всех дубликатов будет создана единственная запись; дубликаты определяются на основе указанных параметров сравнения строк.</span><span class="sxs-lookup"><span data-stu-id="9bbaf-126">Indicate whether the transformation copies duplicate rows to the transformation output, or creates a single entry for all duplicates, based on the specified string comparison options.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bbaf-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="9bbaf-127">See Also</span></span>  
 [<span data-ttu-id="9bbaf-128">Справочник по сообщениям об ошибках служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="9bbaf-128">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
