---
title: Редактор пути потока данных (страница "метаданные") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.patheditor.metadata.f1
helpviewer_keywords:
- Data Flow Path Editor dialog box
ms.assetid: b30bb9d7-ebc0-4b1a-8d0f-ee006b32e841
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c2c314707d8baa2fb0f853438f6486acf2a10a37
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729702"
---
# <a name="data-flow-path-editor-metadata-page"></a><span data-ttu-id="82a25-102">Редактор пути потока данных (страница «Метаданные»)</span><span class="sxs-lookup"><span data-stu-id="82a25-102">Data Flow Path Editor (Metadata Page)</span></span>
  <span data-ttu-id="82a25-103">Страница **Метаданные** диалогового окна **Редактор пути потока данных** используется для просмотра метаданных столбцов пути.</span><span class="sxs-lookup"><span data-stu-id="82a25-103">Use the **Metadata** page of the **Data Flow Path Editor** dialog box to view the metadata of the path columns.</span></span>  
  
## <a name="options"></a><span data-ttu-id="82a25-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="82a25-104">Options</span></span>  
 <span data-ttu-id="82a25-105">**Метаданные о пути**</span><span class="sxs-lookup"><span data-stu-id="82a25-105">**Path metadata**</span></span>  
 <span data-ttu-id="82a25-106">Перечисляются метаданные столбца.</span><span class="sxs-lookup"><span data-stu-id="82a25-106">Lists column metadata.</span></span> <span data-ttu-id="82a25-107">Для сортировки данных в столбце щелкните его заголовок.</span><span class="sxs-lookup"><span data-stu-id="82a25-107">Click the column headings to sort column data.</span></span>  
  
 <span data-ttu-id="82a25-108">**имя**;</span><span class="sxs-lookup"><span data-stu-id="82a25-108">**Name**</span></span>  
 <span data-ttu-id="82a25-109">Содержит имя столбца.</span><span class="sxs-lookup"><span data-stu-id="82a25-109">Lists the column name.</span></span>  
  
 <span data-ttu-id="82a25-110">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="82a25-110">**Data Type**</span></span>  
 <span data-ttu-id="82a25-111">Содержит тип данных столбца.</span><span class="sxs-lookup"><span data-stu-id="82a25-111">Lists the data type of the column.</span></span>  
  
 <span data-ttu-id="82a25-112">**Точность**</span><span class="sxs-lookup"><span data-stu-id="82a25-112">**Precision**</span></span>  
 <span data-ttu-id="82a25-113">Содержит количество десятичных знаков числового значения.</span><span class="sxs-lookup"><span data-stu-id="82a25-113">Lists the number of digits in a numeric value.</span></span>  
  
 <span data-ttu-id="82a25-114">**Масштаб**</span><span class="sxs-lookup"><span data-stu-id="82a25-114">**Scale**</span></span>  
 <span data-ttu-id="82a25-115">Содержит количество цифр справа от десятичного разделителя в числовом значении.</span><span class="sxs-lookup"><span data-stu-id="82a25-115">List the number of digits to the right of the decimal point in a numeric value.</span></span>  
  
 <span data-ttu-id="82a25-116">**Длина**</span><span class="sxs-lookup"><span data-stu-id="82a25-116">**Length**</span></span>  
 <span data-ttu-id="82a25-117">Содержит текущую ширину столбца.</span><span class="sxs-lookup"><span data-stu-id="82a25-117">Lists the current length of the column.</span></span>  
  
 <span data-ttu-id="82a25-118">**Кодовая страница**</span><span class="sxs-lookup"><span data-stu-id="82a25-118">**Code Page**</span></span>  
 <span data-ttu-id="82a25-119">Содержит кодовую страницу столбца.</span><span class="sxs-lookup"><span data-stu-id="82a25-119">Lists the code page of the column.</span></span> <span data-ttu-id="82a25-120">Значение **0** указывает на то, что столбец не использует кодовую страницу.</span><span class="sxs-lookup"><span data-stu-id="82a25-120">The value **0** indicates that the column does not use a code page.</span></span> <span data-ttu-id="82a25-121">Это бывает, если данные, представленные в Юникоде, либо имеют числовой тип данных или тип данных даты или времени.</span><span class="sxs-lookup"><span data-stu-id="82a25-121">This occurs when data is in Unicode, or has a numeric, date, or time data type.</span></span>  
  
 <span data-ttu-id="82a25-122">**Позиция ключа сортировки**</span><span class="sxs-lookup"><span data-stu-id="82a25-122">**Sort Key Position**</span></span>  
 <span data-ttu-id="82a25-123">Указывается позицию ключа сортировки столбца.</span><span class="sxs-lookup"><span data-stu-id="82a25-123">Lists the sort key position of the column.</span></span> <span data-ttu-id="82a25-124">Значение **0** указывает на то, что столбец не отсортирован.</span><span class="sxs-lookup"><span data-stu-id="82a25-124">The value **0** indicates the column is not sorted.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="82a25-125">Префикс минуса (-) указывает на то, что столбец отсортирован в порядке убывания.</span><span class="sxs-lookup"><span data-stu-id="82a25-125">A minus (-) prefix indicates the column is sorted in descending order.</span></span>  
  
 <span data-ttu-id="82a25-126">**Флаги сравнения**</span><span class="sxs-lookup"><span data-stu-id="82a25-126">**Comparison Flags**</span></span>  
 <span data-ttu-id="82a25-127">Перечисляются флаги сравнения, применимые к столбцу.</span><span class="sxs-lookup"><span data-stu-id="82a25-127">Lists the comparison flags that apply to the column.</span></span>  
  
 <span data-ttu-id="82a25-128">**Исходный компонент**</span><span class="sxs-lookup"><span data-stu-id="82a25-128">**Source Component**</span></span>  
 <span data-ttu-id="82a25-129">Указывается компонент потока данных, являющийся источником столбца.</span><span class="sxs-lookup"><span data-stu-id="82a25-129">Lists the data flow component that is the source of the column.</span></span>  
  
 <span data-ttu-id="82a25-130">**Копировать в буфер обмена**</span><span class="sxs-lookup"><span data-stu-id="82a25-130">**Copy to Clipboard**</span></span>  
 <span data-ttu-id="82a25-131">Копирование метаданных столбца в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="82a25-131">Copy the column metadata to the clipboard.</span></span> <span data-ttu-id="82a25-132">По умолчанию все строки метаданных копируются в порядке, отображенном в текущий момент.</span><span class="sxs-lookup"><span data-stu-id="82a25-132">By default, all metadata rows are copied as sorted in the order currently displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82a25-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="82a25-133">See Also</span></span>  
 <span data-ttu-id="82a25-134">[Редактор пути потока данных &#40;общие&#41;страницы](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="82a25-134">[Data Flow Path Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="82a25-135">[Редактор пути потока данных &#40;страница "средства просмотра данных"&#41;](../../2014/integration-services/data-flow-path-editor-data-viewers-page.md) </span><span class="sxs-lookup"><span data-stu-id="82a25-135">[Data Flow Path Editor &#40;Data Viewers Page&#41;](../../2014/integration-services/data-flow-path-editor-data-viewers-page.md) </span></span>  
 <span data-ttu-id="82a25-136">[Поток данных](data-flow/data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="82a25-136">[Data Flow](data-flow/data-flow.md) </span></span>  
 [<span data-ttu-id="82a25-137">Использование заметок в пакетах</span><span class="sxs-lookup"><span data-stu-id="82a25-137">Use Annotations in Packages</span></span>](use-annotations-in-packages.md)  
  
  
