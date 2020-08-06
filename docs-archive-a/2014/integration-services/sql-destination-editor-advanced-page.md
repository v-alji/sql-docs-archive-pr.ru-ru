---
title: Редактор назначения «SQL» (страница «Дополнительно») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sqlserverdestadapter.advanced.f1
helpviewer_keywords:
- SQL Server Destination Editor
ms.assetid: 9b46bcf8-ddaf-4d7d-90a6-80bc19517e9b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ccf25ad888c93f694678a152417affe5c0e16091
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656465"
---
# <a name="sql-destination-editor-advanced-page"></a><span data-ttu-id="6f70a-102">Редактор назначения SQL (страница «Дополнительно»)</span><span class="sxs-lookup"><span data-stu-id="6f70a-102">SQL Destination Editor (Advanced Page)</span></span>
  <span data-ttu-id="6f70a-103">Используйте страницу **Дополнительно** в диалоговом окне **Редактор назначения «SQL»** , чтобы указать дополнительные параметры массовой вставки.</span><span class="sxs-lookup"><span data-stu-id="6f70a-103">Use the **Advanced** page of the **SQL Destination Editor** dialog box to specify advanced bulk insert options.</span></span>  
  
 <span data-ttu-id="6f70a-104">Дополнительные сведения о назначении «SQL Server» см. в разделе [SQL Server Destination](data-flow/sql-server-destination.md).</span><span class="sxs-lookup"><span data-stu-id="6f70a-104">To learn more about the SQL Server destination, see [SQL Server Destination](data-flow/sql-server-destination.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="6f70a-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="6f70a-105">Options</span></span>  
 <span data-ttu-id="6f70a-106">**Сохранять ИД**</span><span class="sxs-lookup"><span data-stu-id="6f70a-106">**Keep identity**</span></span>  
 <span data-ttu-id="6f70a-107">Укажите, должна ли задача вставлять значения в столбцы идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="6f70a-107">Specify whether the task should insert values into identity columns.</span></span> <span data-ttu-id="6f70a-108">Значение по умолчанию этого свойства равно `False`.</span><span class="sxs-lookup"><span data-stu-id="6f70a-108">The default value of this property is `False`.</span></span>  
  
 <span data-ttu-id="6f70a-109">**Сохранять значения NULL**</span><span class="sxs-lookup"><span data-stu-id="6f70a-109">**Keep nulls**</span></span>  
 <span data-ttu-id="6f70a-110">Укажите, должна ли данная задача сохранять значения NULL.</span><span class="sxs-lookup"><span data-stu-id="6f70a-110">Specify whether the task should keep null values.</span></span> <span data-ttu-id="6f70a-111">Значение по умолчанию этого свойства равно `False`.</span><span class="sxs-lookup"><span data-stu-id="6f70a-111">The default value of this property is `False`.</span></span>  
  
 <span data-ttu-id="6f70a-112">**Блокировка таблицы**</span><span class="sxs-lookup"><span data-stu-id="6f70a-112">**Table lock**</span></span>  
 <span data-ttu-id="6f70a-113">Укажите, будет ли таблица заблокирована в ходе загрузки данных.</span><span class="sxs-lookup"><span data-stu-id="6f70a-113">Specify whether the table is locked when the data is loaded.</span></span> <span data-ttu-id="6f70a-114">Значение по умолчанию этого свойства равно `True`.</span><span class="sxs-lookup"><span data-stu-id="6f70a-114">The default value of this property is `True`.</span></span>  
  
 <span data-ttu-id="6f70a-115">**Проверочные ограничения**</span><span class="sxs-lookup"><span data-stu-id="6f70a-115">**Check constraints**</span></span>  
 <span data-ttu-id="6f70a-116">Укажите, должна ли задача проверять ограничения.</span><span class="sxs-lookup"><span data-stu-id="6f70a-116">Specify whether the task should check constraints.</span></span> <span data-ttu-id="6f70a-117">Значение по умолчанию этого свойства равно `True`.</span><span class="sxs-lookup"><span data-stu-id="6f70a-117">The default value of this property is `True`.</span></span>  
  
 <span data-ttu-id="6f70a-118">**Запускать триггеры**</span><span class="sxs-lookup"><span data-stu-id="6f70a-118">**Fire triggers**</span></span>  
 <span data-ttu-id="6f70a-119">Укажите, будет ли массовая вставка запускать триггеры таблиц.</span><span class="sxs-lookup"><span data-stu-id="6f70a-119">Specify whether the bulk insert should fire triggers on tables.</span></span> <span data-ttu-id="6f70a-120">Значение по умолчанию этого свойства равно `False`.</span><span class="sxs-lookup"><span data-stu-id="6f70a-120">The default value of this property is `False`.</span></span>  
  
 <span data-ttu-id="6f70a-121">**Первая строка**</span><span class="sxs-lookup"><span data-stu-id="6f70a-121">**First Row**</span></span>  
 <span data-ttu-id="6f70a-122">Укажите первую вставляемую строку.</span><span class="sxs-lookup"><span data-stu-id="6f70a-122">Specify the first row to insert.</span></span> <span data-ttu-id="6f70a-123">Значение по умолчанию этого свойства равно **-1**. Оно указывает, что значение не присваивалось.</span><span class="sxs-lookup"><span data-stu-id="6f70a-123">The default value of this property is **-1**, indicating that no value has been assigned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6f70a-124">Очистите текстовое поле в **Редакторе назначения «SQL»** , чтобы показать, что этому свойству не нужно присваивать значение.</span><span class="sxs-lookup"><span data-stu-id="6f70a-124">Clear the text box in the **SQL Destination Editor** to indicate that you do not want to assign a value for this property.</span></span> <span data-ttu-id="6f70a-125">Используйте значение -1 в окне **Свойства** , **Расширенном редакторе**и объектной модели.</span><span class="sxs-lookup"><span data-stu-id="6f70a-125">Use -1 in the **Properties** window, the **Advanced Editor**, and the object model.</span></span>  
  
 <span data-ttu-id="6f70a-126">**Последняя строка**</span><span class="sxs-lookup"><span data-stu-id="6f70a-126">**Last Row**</span></span>  
 <span data-ttu-id="6f70a-127">Укажите последнюю вставляемую строку.</span><span class="sxs-lookup"><span data-stu-id="6f70a-127">Specify the last row to insert.</span></span> <span data-ttu-id="6f70a-128">Значение по умолчанию этого свойства равно **-1**. Оно указывает, что значение не присваивалось.</span><span class="sxs-lookup"><span data-stu-id="6f70a-128">The default value of this property is **-1**, indicating that no value has been assigned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6f70a-129">Очистите текстовое поле в **Редакторе назначения «SQL»** , чтобы показать, что этому свойству не нужно присваивать значение.</span><span class="sxs-lookup"><span data-stu-id="6f70a-129">Clear the text box in the **SQL Destination Editor** to indicate that you do not want to assign a value for this property.</span></span> <span data-ttu-id="6f70a-130">Используйте значение -1 в окне **Свойства** , **Расширенном редакторе**и объектной модели.</span><span class="sxs-lookup"><span data-stu-id="6f70a-130">Use -1 in the **Properties** window, the **Advanced Editor**, and the object model.</span></span>  
  
 <span data-ttu-id="6f70a-131">**Максимальное количество ошибок**</span><span class="sxs-lookup"><span data-stu-id="6f70a-131">**Maximum number of errors**</span></span>  
 <span data-ttu-id="6f70a-132">Укажите допустимое максимальное число ошибок, после превышения которого происходит прекращение массовой вставки.</span><span class="sxs-lookup"><span data-stu-id="6f70a-132">Specify the number of errors that can occur before the bulk insert stops.</span></span> <span data-ttu-id="6f70a-133">Значение по умолчанию этого свойства равно **-1**. Оно указывает, что значение не присваивалось.</span><span class="sxs-lookup"><span data-stu-id="6f70a-133">The default value of this property is **-1**, indicating that no value has been assigned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6f70a-134">Очистите текстовое поле в **Редакторе назначения «SQL»** , чтобы показать, что этому свойству не нужно присваивать значение.</span><span class="sxs-lookup"><span data-stu-id="6f70a-134">Clear the text box in the **SQL Destination Editor** to indicate that you do not want to assign a value for this property.</span></span> <span data-ttu-id="6f70a-135">Используйте значение -1 в окне **Свойства** , **Расширенном редакторе**и объектной модели.</span><span class="sxs-lookup"><span data-stu-id="6f70a-135">Use -1 in the **Properties** window, the **Advanced Editor**, and the object model.</span></span>  
  
 <span data-ttu-id="6f70a-136">**Timeout**</span><span class="sxs-lookup"><span data-stu-id="6f70a-136">**Timeout**</span></span>  
 <span data-ttu-id="6f70a-137">Укажите количество секунд ожидания, по истечении которых массовая вставка будет прекращена.</span><span class="sxs-lookup"><span data-stu-id="6f70a-137">Specify the number of seconds to wait before the bulk insert stops because of a time-out.</span></span>  
  
 <span data-ttu-id="6f70a-138">**Порядок столбцов**</span><span class="sxs-lookup"><span data-stu-id="6f70a-138">**Order columns**</span></span>  
 <span data-ttu-id="6f70a-139">Введите имена столбцов сортировки.</span><span class="sxs-lookup"><span data-stu-id="6f70a-139">Type the names of the sort columns.</span></span> <span data-ttu-id="6f70a-140">Любой столбец можно сортировать в порядке возрастания или в порядке убывания.</span><span class="sxs-lookup"><span data-stu-id="6f70a-140">Each column can be sorted in ascending or descending order.</span></span> <span data-ttu-id="6f70a-141">Если нужно задать несколько столбцов сортировки, используйте в качестве разделителей запятые.</span><span class="sxs-lookup"><span data-stu-id="6f70a-141">If you use multiple sort columns, delimit the list with commas.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f70a-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="6f70a-142">See Also</span></span>  
 <span data-ttu-id="6f70a-143">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="6f70a-143">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="6f70a-144">[Редактор назначения "SQL" &#40;страница "Диспетчер соединений"&#41;](../../2014/integration-services/sql-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="6f70a-144">[SQL Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/sql-destination-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="6f70a-145">[Редактор назначения "SQL &#40;страниц сопоставления"&#41;](../../2014/integration-services/sql-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="6f70a-145">[SQL Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/sql-destination-editor-mappings-page.md) </span></span>  
 [<span data-ttu-id="6f70a-146">Выполнение массовой загрузки данных с помощью назначения «SQL Server»</span><span class="sxs-lookup"><span data-stu-id="6f70a-146">Bulk Load Data by Using the SQL Server Destination</span></span>](data-flow/bulk-load-data-by-using-the-sql-server-destination.md)  
  
  
