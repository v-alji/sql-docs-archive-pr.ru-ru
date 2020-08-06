---
title: Редактор преобразования "Таблица символов" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.charactermaptransformation.f1
helpviewer_keywords:
- Character Map Transformation Editor
ms.assetid: 3f1dbcf9-9cca-4606-bdcc-7ea6ad48cdf3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c6cdcdba448dafc6ccf03774d4f611dee704b823
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657220"
---
# <a name="character-map-transformation-editor"></a><span data-ttu-id="64af5-102">Редактор преобразования «Таблица соответствия символов»</span><span class="sxs-lookup"><span data-stu-id="64af5-102">Character Map Transformation Editor</span></span>
  <span data-ttu-id="64af5-103">Диалоговое окно **Редактор преобразования "Таблица соответствия символов"** используется для выбора строковых функций, применяемых к данным столбцов, и для задания того, будет ли сопоставление приводить к замене на месте или к добавлению нового столбца.</span><span class="sxs-lookup"><span data-stu-id="64af5-103">Use the **Character Map Transformation Editor** dialog box to select the string functions to apply to column data and to specify whether mapping is an in-place change or added as a new column.</span></span>  
  
 <span data-ttu-id="64af5-104">Дополнительные сведения о преобразовании «Таблица символов» см. в разделе [Character Map Transformation](data-flow/transformations/character-map-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="64af5-104">To learn more about the Character Map transformation, see [Character Map Transformation](data-flow/transformations/character-map-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="64af5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="64af5-105">Options</span></span>  
 <span data-ttu-id="64af5-106">**Доступные входные столбцы**</span><span class="sxs-lookup"><span data-stu-id="64af5-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="64af5-107">Флажки используются для выбора столбцов, подлежащих преобразованию строковыми функциями.</span><span class="sxs-lookup"><span data-stu-id="64af5-107">Use the check boxes to select the columns to transform using string functions.</span></span> <span data-ttu-id="64af5-108">Результаты выбора отобразятся в таблице внизу.</span><span class="sxs-lookup"><span data-stu-id="64af5-108">Your selections appear in the table below.</span></span>  
  
 <span data-ttu-id="64af5-109">**Входной столбец**</span><span class="sxs-lookup"><span data-stu-id="64af5-109">**Input Column**</span></span>  
 <span data-ttu-id="64af5-110">Просмотрите выбранные входные столбцы из вышеприведенной таблицы.</span><span class="sxs-lookup"><span data-stu-id="64af5-110">View input columns selected from the table above.</span></span> <span data-ttu-id="64af5-111">Также можно изменить или удалить выбор, используя список доступных входных столбцов.</span><span class="sxs-lookup"><span data-stu-id="64af5-111">You can also change or remove a selection by using the list of available input columns.</span></span>  
  
 <span data-ttu-id="64af5-112">**Назначение**</span><span class="sxs-lookup"><span data-stu-id="64af5-112">**Destination**</span></span>  
 <span data-ttu-id="64af5-113">Укажите, необходимо ли сохранять результаты строковых операций в том же месте, используя существующий столбец, или сохранять измененные данные в виде нового столбца.</span><span class="sxs-lookup"><span data-stu-id="64af5-113">Specify whether to save the results of the string operations in place, using the existing column, or to save the modified data as a new column.</span></span>  
  
|<span data-ttu-id="64af5-114">Значение</span><span class="sxs-lookup"><span data-stu-id="64af5-114">Value</span></span>|<span data-ttu-id="64af5-115">Описание</span><span class="sxs-lookup"><span data-stu-id="64af5-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="64af5-116">Новый столбец</span><span class="sxs-lookup"><span data-stu-id="64af5-116">New column</span></span>|<span data-ttu-id="64af5-117">Сохранить данные в новом столбце.</span><span class="sxs-lookup"><span data-stu-id="64af5-117">Save the data in a new column.</span></span> <span data-ttu-id="64af5-118">Присвойте столбцу имя в поле **Псевдоним выхода**.</span><span class="sxs-lookup"><span data-stu-id="64af5-118">Assign the column name under **Output Alias**.</span></span>|  
|<span data-ttu-id="64af5-119">Замена на месте</span><span class="sxs-lookup"><span data-stu-id="64af5-119">In-place change</span></span>|<span data-ttu-id="64af5-120">Сохранить измененные данные в существующем столбце.</span><span class="sxs-lookup"><span data-stu-id="64af5-120">Save the modified data in the existing column.</span></span>|  
  
 <span data-ttu-id="64af5-121">**Операция**</span><span class="sxs-lookup"><span data-stu-id="64af5-121">**Operation**</span></span>  
 <span data-ttu-id="64af5-122">Выберите из списка строковые функции, которые нужно применить к данным столбца.</span><span class="sxs-lookup"><span data-stu-id="64af5-122">Select from the list the string functions to apply to column data.</span></span>  
  
|<span data-ttu-id="64af5-123">Значение</span><span class="sxs-lookup"><span data-stu-id="64af5-123">Value</span></span>|<span data-ttu-id="64af5-124">Описание</span><span class="sxs-lookup"><span data-stu-id="64af5-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="64af5-125">Нижний регистр</span><span class="sxs-lookup"><span data-stu-id="64af5-125">Lowercase</span></span>|<span data-ttu-id="64af5-126">Преобразовать в нижний регистр.</span><span class="sxs-lookup"><span data-stu-id="64af5-126">Convert to lower case.</span></span>|  
|<span data-ttu-id="64af5-127">Верхний регистр</span><span class="sxs-lookup"><span data-stu-id="64af5-127">Uppercase</span></span>|<span data-ttu-id="64af5-128">Преобразовать в верхний регистр.</span><span class="sxs-lookup"><span data-stu-id="64af5-128">Convert to upper case.</span></span>|  
|<span data-ttu-id="64af5-129">Обратный порядок байтов</span><span class="sxs-lookup"><span data-stu-id="64af5-129">Byte reversal</span></span>|<span data-ttu-id="64af5-130">Преобразовать путем обращения порядка байтов.</span><span class="sxs-lookup"><span data-stu-id="64af5-130">Convert by reversing byte order.</span></span>|  
|<span data-ttu-id="64af5-131">Хирагана</span><span class="sxs-lookup"><span data-stu-id="64af5-131">Hiragana</span></span>|<span data-ttu-id="64af5-132">Преобразовать японские символы катаканы в хирагану.</span><span class="sxs-lookup"><span data-stu-id="64af5-132">Convert Japanese katakana characters to hiragana.</span></span>|  
|<span data-ttu-id="64af5-133">Катакана</span><span class="sxs-lookup"><span data-stu-id="64af5-133">Katakana</span></span>|<span data-ttu-id="64af5-134">Преобразовать японские символы хираганы в катакану.</span><span class="sxs-lookup"><span data-stu-id="64af5-134">Convert Japanese hiragana characters to katakana.</span></span>|  
|<span data-ttu-id="64af5-135">Половинная ширина</span><span class="sxs-lookup"><span data-stu-id="64af5-135">Half width</span></span>|<span data-ttu-id="64af5-136">Преобразовать полноширинные символы в полуширинные.</span><span class="sxs-lookup"><span data-stu-id="64af5-136">Convert full-width characters to half width.</span></span>|  
|<span data-ttu-id="64af5-137">Полная ширина</span><span class="sxs-lookup"><span data-stu-id="64af5-137">Full width</span></span>|<span data-ttu-id="64af5-138">Преобразовать полуширинные символы в полноширинные.</span><span class="sxs-lookup"><span data-stu-id="64af5-138">Convert half-width characters to full width.</span></span>|  
|<span data-ttu-id="64af5-139">Регистр по правилам языка</span><span class="sxs-lookup"><span data-stu-id="64af5-139">Linguistic casing</span></span>|<span data-ttu-id="64af5-140">Применить лингвистические правила регистра (простое сопоставление регистра Юникода для локали Turkic и других) вместо системных правил.</span><span class="sxs-lookup"><span data-stu-id="64af5-140">Apply linguistic rules of casing (Unicode simple case mapping for Turkic and other locales) instead of the system rules.</span></span>|  
|<span data-ttu-id="64af5-141">Китайский (упрощенный)</span><span class="sxs-lookup"><span data-stu-id="64af5-141">Simplified Chinese</span></span>|<span data-ttu-id="64af5-142">Преобразовать символы китайского (традиционного) в китайский (упрощенный).</span><span class="sxs-lookup"><span data-stu-id="64af5-142">Convert traditional Chinese characters to simplified Chinese.</span></span>|  
|<span data-ttu-id="64af5-143">Китайский (традиционный)</span><span class="sxs-lookup"><span data-stu-id="64af5-143">Traditional Chinese</span></span>|<span data-ttu-id="64af5-144">Преобразовать символы китайского (упрощенного) в китайский (традиционный).</span><span class="sxs-lookup"><span data-stu-id="64af5-144">Convert simplified Chinese characters to traditional Chinese.</span></span>|  
  
 <span data-ttu-id="64af5-145">**Псевдоним вывода**</span><span class="sxs-lookup"><span data-stu-id="64af5-145">**Output Alias**</span></span>  
 <span data-ttu-id="64af5-146">Введите псевдоним для каждого выходного столбца.</span><span class="sxs-lookup"><span data-stu-id="64af5-146">Type an alias for each output column.</span></span> <span data-ttu-id="64af5-147">Значением по умолчанию является **Copy of** , за которым следует имя входного столбца, однако можно выбрать любое уникальное описательное имя.</span><span class="sxs-lookup"><span data-stu-id="64af5-147">The default is **Copy of** followed by the input column name; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="64af5-148">**Настройка вывода ошибок**</span><span class="sxs-lookup"><span data-stu-id="64af5-148">**Configure Error Output**</span></span>  
 <span data-ttu-id="64af5-149">Диалоговое окно [Настройка вывода ошибок](../../2014/integration-services/configure-error-output.md) для указания параметров обработки ошибок в этом преобразовании.</span><span class="sxs-lookup"><span data-stu-id="64af5-149">Use the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box to specify error handling options for this transformation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64af5-150">См. также:</span><span class="sxs-lookup"><span data-stu-id="64af5-150">See Also</span></span>  
 [<span data-ttu-id="64af5-151">Справочник по сообщениям об ошибках служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="64af5-151">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
