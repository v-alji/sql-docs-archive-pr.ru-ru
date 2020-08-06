---
title: Редактор преобразования "Уточняющий запрос" (страница "столбцы") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.lookuptransformation.columns.f1
helpviewer_keywords:
- Lookup Transformation Editor
ms.assetid: 690ffef5-fd59-4e95-a27d-4fcf0d6b1c0b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b768076d8acbcaef8cbff21783a7697020e027eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664323"
---
# <a name="lookup-transformation-editor-columns-page"></a><span data-ttu-id="daaa2-102">Редактор преобразования «Уточняющий запрос» (страница «Столбцы»)</span><span class="sxs-lookup"><span data-stu-id="daaa2-102">Lookup Transformation Editor (Columns Page)</span></span>
  <span data-ttu-id="daaa2-103">Используйте страницу **Столбцы** диалогового окна **Редактор преобразования «Уточняющий запрос»** , чтобы указать соединение между исходной и ссылочной таблицами и выбрать уточняющие столбцы из ссылочной таблицы.</span><span class="sxs-lookup"><span data-stu-id="daaa2-103">Use the **Columns** page of the **Lookup Transformation Editor** dialog box to specify the join between the source table and the reference table, and to select lookup columns from the reference table.</span></span>  
  
 <span data-ttu-id="daaa2-104">Дополнительные сведения о преобразовании «Уточняющий запрос» см. в разделе [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="daaa2-104">To learn more about the Lookup transformation, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="daaa2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="daaa2-105">Options</span></span>  
 <span data-ttu-id="daaa2-106">**Доступные входные столбцы**</span><span class="sxs-lookup"><span data-stu-id="daaa2-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="daaa2-107">Просмотрите список доступных входных столбцов.</span><span class="sxs-lookup"><span data-stu-id="daaa2-107">View the list of available input columns.</span></span> <span data-ttu-id="daaa2-108">Входные столбцы — это столбцы в потоке данных из подключенного источника.</span><span class="sxs-lookup"><span data-stu-id="daaa2-108">The input columns are the columns in the data flow from a connected source.</span></span> <span data-ttu-id="daaa2-109">Входной и уточняющий столбец должны иметь одинаковый тип данных.</span><span class="sxs-lookup"><span data-stu-id="daaa2-109">The input columns and lookup column must have matching data types.</span></span>  
  
 <span data-ttu-id="daaa2-110">Чтобы сопоставить доступные входные столбцы с уточняющими столбцами, воспользуйтесь операцией перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="daaa2-110">Use a drag-and-drop operation to map available input columns to lookup columns.</span></span>  
  
 <span data-ttu-id="daaa2-111">Также можно сопоставить входные и уточняющие столбцы с помощью клавиатуры, выделив цветом столбец в таблице **Доступные входные столбцы** , нажав клавишу «Приложение» и выбрав пункт **Изменить сопоставления**.</span><span class="sxs-lookup"><span data-stu-id="daaa2-111">You can also map input columns to lookup columns using the keyboard, by highlighting a column in the **Available Input Columns** table, pressing the Application key, and then clicking **Edit Mappings**.</span></span>  
  
 <span data-ttu-id="daaa2-112">**Доступные уточняющие столбцы**</span><span class="sxs-lookup"><span data-stu-id="daaa2-112">**Available Lookup Columns**</span></span>  
 <span data-ttu-id="daaa2-113">Просмотр списка уточняющих столбцов.</span><span class="sxs-lookup"><span data-stu-id="daaa2-113">View the list of lookup columns.</span></span> <span data-ttu-id="daaa2-114">Уточняющие столбцы представляют собой столбцы в ссылочной таблице, в которых должен производиться поиск значений, совпадающих с входными столбцами.</span><span class="sxs-lookup"><span data-stu-id="daaa2-114">The lookup columns are columns in the reference table in which you want to look up values that match the input columns.</span></span>  
  
 <span data-ttu-id="daaa2-115">Чтобы сопоставить доступные уточняющие столбцы с входными столбцами, воспользуйтесь операцией перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="daaa2-115">Use a drag-and-drop operation to map available lookup columns to input columns.</span></span>  
  
 <span data-ttu-id="daaa2-116">С помощью флажков выберите уточняющие столбцы в ссылочной таблице, по которым будет выполняться уточняющий запрос.</span><span class="sxs-lookup"><span data-stu-id="daaa2-116">Use the check boxes to select lookup columns in the reference table on which to perform lookup operations.</span></span>  
  
 <span data-ttu-id="daaa2-117">Также можно сопоставить входные и уточняющие столбцы с помощью клавиатуры, выделив цветом столбец в таблице **Доступные уточняющие столбцы** , нажав клавишу «Приложение» и выбрав пункт **Изменить сопоставления**.</span><span class="sxs-lookup"><span data-stu-id="daaa2-117">You can also map lookup columns to input columns using the keyboard, by highlighting a column in the **Available Lookup Columns** table, pressing the Application key, and then clicking **Edit Mappings**.</span></span>  
  
 <span data-ttu-id="daaa2-118">**Уточняющий столбец**</span><span class="sxs-lookup"><span data-stu-id="daaa2-118">**Lookup Column**</span></span>  
 <span data-ttu-id="daaa2-119">Просмотр выбранных уточняющих столбцов.</span><span class="sxs-lookup"><span data-stu-id="daaa2-119">View the selected lookup columns.</span></span> <span data-ttu-id="daaa2-120">Выбор отражается установкой флажков в таблице **Доступные уточняющие столбцы** .</span><span class="sxs-lookup"><span data-stu-id="daaa2-120">The selections are reflected in the check box selections in the **Available Lookup Columns** table.</span></span>  
  
 <span data-ttu-id="daaa2-121">**Операция уточняющего запроса**</span><span class="sxs-lookup"><span data-stu-id="daaa2-121">**Lookup Operation**</span></span>  
 <span data-ttu-id="daaa2-122">Выберите из списка операцию уточняющего запроса, которую нужно выполнить для уточняющего столбца.</span><span class="sxs-lookup"><span data-stu-id="daaa2-122">Select a lookup operation from the list to perform on the lookup column.</span></span>  
  
 <span data-ttu-id="daaa2-123">**Псевдоним вывода**</span><span class="sxs-lookup"><span data-stu-id="daaa2-123">**Output Alias**</span></span>  
 <span data-ttu-id="daaa2-124">Введите псевдоним выхода для каждого уточняющего столбца.</span><span class="sxs-lookup"><span data-stu-id="daaa2-124">Type an alias for the output for each lookup column.</span></span> <span data-ttu-id="daaa2-125">По умолчанию используется имя уточняющего столбца, однако можно выбрать любое уникальное описательное имя.</span><span class="sxs-lookup"><span data-stu-id="daaa2-125">The default is the name of the lookup column; however, you can select any unique, descriptive name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daaa2-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="daaa2-126">See Also</span></span>  
 <span data-ttu-id="daaa2-127">[Редактор преобразования "Уточняющий запрос" &#40;общие&#41;страницы](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="daaa2-127">[Lookup Transformation Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="daaa2-128">[Редактор преобразования "Уточняющий запрос" &#40;страница подключения&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span><span class="sxs-lookup"><span data-stu-id="daaa2-128">[Lookup Transformation Editor &#40;Connection Page&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span></span>  
 <span data-ttu-id="daaa2-129">[Редактор преобразования "Уточняющий запрос" &#40;страница "Дополнительно"&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="daaa2-129">[Lookup Transformation Editor &#40;Advanced Page&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span></span>  
 <span data-ttu-id="daaa2-130">[Редактор преобразования "Уточняющий запрос" &#40;страница "вывод ошибок"&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="daaa2-130">[Lookup Transformation Editor &#40;Error Output Page&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="daaa2-131">преобразование «Нечеткий уточняющий запрос»</span><span class="sxs-lookup"><span data-stu-id="daaa2-131">Fuzzy Lookup Transformation</span></span>](data-flow/transformations/fuzzy-lookup-transformation.md)  
  
  
