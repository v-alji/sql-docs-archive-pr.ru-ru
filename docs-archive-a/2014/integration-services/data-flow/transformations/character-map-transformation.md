---
title: Преобразование "Таблица символов" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.charactertrans.f1
helpviewer_keywords:
- mutually exclusive mapping [Integration Services]
- mapping data [Integration Services]
- string functions
- Character Map transformation [Integration Services]
ms.assetid: e0f50eb6-b893-400f-bb8c-fb3072cc2620
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b5fc31e1a3500a7a7b023e43a968e70e5b438dec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665463"
---
# <a name="character-map-transformation"></a><span data-ttu-id="90727-102">Преобразование «Таблица символов»</span><span class="sxs-lookup"><span data-stu-id="90727-102">Character Map Transformation</span></span>
  <span data-ttu-id="90727-103">Преобразование «Таблица символов» применяет строковые функции, такие как преобразование из нижнего регистра в верхний, к символьным данным.</span><span class="sxs-lookup"><span data-stu-id="90727-103">The Character Map transformation applies string functions, such as conversion from lowercase to uppercase, to character data.</span></span> <span data-ttu-id="90727-104">Это преобразование работает только со столбцами данных строкового типа данных.</span><span class="sxs-lookup"><span data-stu-id="90727-104">This transformation operates only on column data with a string data type.</span></span>  
  
 <span data-ttu-id="90727-105">Преобразование «Таблица символов» может обновить данные столбца преобразованными значениями или поместить преобразованные данные в новый столбец выхода преобразования.</span><span class="sxs-lookup"><span data-stu-id="90727-105">The Character Map transformation can convert column data in place or add a column to the transformation output and put the converted data in the new column.</span></span> <span data-ttu-id="90727-106">Можно применять различные наборы операторов сопоставления к одному входному столбцу и помещать результаты в разные столбцы.</span><span class="sxs-lookup"><span data-stu-id="90727-106">You can apply different sets of mapping operations to the same input column and put the results in different columns.</span></span> <span data-ttu-id="90727-107">Например, можно преобразовать данные одного и того же столбца в верхний и нижний регистр и поместить результаты в два различных столбца.</span><span class="sxs-lookup"><span data-stu-id="90727-107">For example, you can convert the same column to uppercase and lowercase and put the results in two different columns.</span></span>  
  
 <span data-ttu-id="90727-108">Сопоставление может при некоторых обстоятельствах быть причиной усечения данных.</span><span class="sxs-lookup"><span data-stu-id="90727-108">Mapping can, under some circumstances, cause data to be truncated.</span></span> <span data-ttu-id="90727-109">Например, усечение может произойти, когда однобайтный символ сопоставляется с символом в многобайтном представлении.</span><span class="sxs-lookup"><span data-stu-id="90727-109">For example, truncation can occur when single-byte characters are mapped to characters with a multibyte representation.</span></span> <span data-ttu-id="90727-110">Преобразование «Таблица символов» имеет выход ошибок, который может быть использован для направления усеченных данных в отдельный выход.</span><span class="sxs-lookup"><span data-stu-id="90727-110">The Character Map transformation includes an error output, which can be used to direct truncated data to separate output.</span></span> <span data-ttu-id="90727-111">Дополнительные сведения см. в разделе [Обработка ошибок в данных](../error-handling-in-data.md).</span><span class="sxs-lookup"><span data-stu-id="90727-111">For more information, see [Error Handling in Data](../error-handling-in-data.md).</span></span>  
  
 <span data-ttu-id="90727-112">Это преобразование имеет один вход, один выход и один выход ошибок.</span><span class="sxs-lookup"><span data-stu-id="90727-112">This transformation has one input, one output, and one error output.</span></span>  
  
## <a name="mapping-operations"></a><span data-ttu-id="90727-113">Операции сопоставления</span><span class="sxs-lookup"><span data-stu-id="90727-113">Mapping Operations</span></span>  
 <span data-ttu-id="90727-114">Следующая таблица описывает операции сопоставления, которые поддерживаются преобразованием «Таблица символов».</span><span class="sxs-lookup"><span data-stu-id="90727-114">The following table describes the mapping operations that the Character Map transformation supports.</span></span>  
  
|<span data-ttu-id="90727-115">Операция</span><span class="sxs-lookup"><span data-stu-id="90727-115">Operation</span></span>|<span data-ttu-id="90727-116">Description</span><span class="sxs-lookup"><span data-stu-id="90727-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="90727-117">Обратный порядок байтов</span><span class="sxs-lookup"><span data-stu-id="90727-117">Byte reversal</span></span>|<span data-ttu-id="90727-118">Меняет порядок байтов.</span><span class="sxs-lookup"><span data-stu-id="90727-118">Reverses byte order.</span></span>|  
|<span data-ttu-id="90727-119">Полная ширина</span><span class="sxs-lookup"><span data-stu-id="90727-119">Full width</span></span>|<span data-ttu-id="90727-120">Сопоставляет полуширинные символы полноширинным символам.</span><span class="sxs-lookup"><span data-stu-id="90727-120">Maps half-width characters to full-width characters.</span></span>|  
|<span data-ttu-id="90727-121">Половинная ширина</span><span class="sxs-lookup"><span data-stu-id="90727-121">Half width</span></span>|<span data-ttu-id="90727-122">Сопоставляет полноширинные символы полуширинным символам.</span><span class="sxs-lookup"><span data-stu-id="90727-122">Maps full-width characters to half-width characters.</span></span>|  
|<span data-ttu-id="90727-123">Хирагана</span><span class="sxs-lookup"><span data-stu-id="90727-123">Hiragana</span></span>|<span data-ttu-id="90727-124">Сопоставляет символы катакана символам хирагана.</span><span class="sxs-lookup"><span data-stu-id="90727-124">Maps katakana characters to hiragana characters.</span></span>|  
|<span data-ttu-id="90727-125">Катакана</span><span class="sxs-lookup"><span data-stu-id="90727-125">Katakana</span></span>|<span data-ttu-id="90727-126">Сопоставляет символы хирагана символам катакана.</span><span class="sxs-lookup"><span data-stu-id="90727-126">Maps hiragana characters to katakana characters.</span></span>|  
|<span data-ttu-id="90727-127">Регистр по правилам языка</span><span class="sxs-lookup"><span data-stu-id="90727-127">Linguistic casing</span></span>|<span data-ttu-id="90727-128">Применяет регистр по правилам языка вместо системных правил.</span><span class="sxs-lookup"><span data-stu-id="90727-128">Applies linguistic casing instead of the system rules.</span></span> <span data-ttu-id="90727-129">Регистр по правилам языка относится к функциональным возможностям, предоставляемым API-интерфейсами Win32 для простого сопоставления в Юникод турецкого и других локалях.</span><span class="sxs-lookup"><span data-stu-id="90727-129">Linguistic casing refers to functionality provided by the Win32 API for Unicode simple case mapping of Turkic and other locales.</span></span>|  
|<span data-ttu-id="90727-130">Нижний регистр</span><span class="sxs-lookup"><span data-stu-id="90727-130">Lowercase</span></span>|<span data-ttu-id="90727-131">Преобразует символы в нижний регистр.</span><span class="sxs-lookup"><span data-stu-id="90727-131">Converts characters to lowercase.</span></span>|  
|<span data-ttu-id="90727-132">Китайский (упрощенный)</span><span class="sxs-lookup"><span data-stu-id="90727-132">Simplified Chinese</span></span>|<span data-ttu-id="90727-133">Сопоставляет символы традиционного китайского символам упрощенного китайского алфавита.</span><span class="sxs-lookup"><span data-stu-id="90727-133">Maps traditional Chinese characters to simplified Chinese characters.</span></span>|  
|<span data-ttu-id="90727-134">Китайский (традиционный)</span><span class="sxs-lookup"><span data-stu-id="90727-134">Traditional Chinese</span></span>|<span data-ttu-id="90727-135">Сопоставляет символы упрощенного китайского символам традиционного китайского алфавита.</span><span class="sxs-lookup"><span data-stu-id="90727-135">Maps simplified Chinese characters to traditional Chinese characters.</span></span>|  
|<span data-ttu-id="90727-136">Верхний регистр</span><span class="sxs-lookup"><span data-stu-id="90727-136">Uppercase</span></span>|<span data-ttu-id="90727-137">Преобразует символы в верхний регистр.</span><span class="sxs-lookup"><span data-stu-id="90727-137">Converts characters to uppercase.</span></span>|  
  
## <a name="mutually-exclusive-mapping-operations"></a><span data-ttu-id="90727-138">Взаимоисключающие операции сопоставления</span><span class="sxs-lookup"><span data-stu-id="90727-138">Mutually Exclusive Mapping Operations</span></span>  
 <span data-ttu-id="90727-139">В преобразовании может быть выполнено несколько операций.</span><span class="sxs-lookup"><span data-stu-id="90727-139">More than one operation can be performed in a transformation.</span></span> <span data-ttu-id="90727-140">Однако некоторые операции сопоставления являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="90727-140">However, some mapping operations are mutually exclusive.</span></span> <span data-ttu-id="90727-141">Следующая таблица перечисляет ограничения, которые применяются, когда применяется множество операций над одним столбцом.</span><span class="sxs-lookup"><span data-stu-id="90727-141">The following table lists restrictions that apply when you use multiple operations on the same column.</span></span> <span data-ttu-id="90727-142">Операции в столбцах Операция A и Операция B являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="90727-142">Operations in the columns Operation A and Operation B are mutually exclusive.</span></span>  
  
|<span data-ttu-id="90727-143">Операция A</span><span class="sxs-lookup"><span data-stu-id="90727-143">Operation A</span></span>|<span data-ttu-id="90727-144">Операция B</span><span class="sxs-lookup"><span data-stu-id="90727-144">Operation B</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="90727-145">Нижний регистр</span><span class="sxs-lookup"><span data-stu-id="90727-145">Lowercase</span></span>|<span data-ttu-id="90727-146">Верхний регистр</span><span class="sxs-lookup"><span data-stu-id="90727-146">Uppercase</span></span>|  
|<span data-ttu-id="90727-147">Хирагана</span><span class="sxs-lookup"><span data-stu-id="90727-147">Hiragana</span></span>|<span data-ttu-id="90727-148">Катакана</span><span class="sxs-lookup"><span data-stu-id="90727-148">Katakana</span></span>|  
|<span data-ttu-id="90727-149">Половинная ширина</span><span class="sxs-lookup"><span data-stu-id="90727-149">Half width</span></span>|<span data-ttu-id="90727-150">Полная ширина</span><span class="sxs-lookup"><span data-stu-id="90727-150">Full width</span></span>|  
|<span data-ttu-id="90727-151">Китайский (традиционный)</span><span class="sxs-lookup"><span data-stu-id="90727-151">Traditional Chinese</span></span>|<span data-ttu-id="90727-152">Китайский (упрощенный)</span><span class="sxs-lookup"><span data-stu-id="90727-152">Simplified Chinese</span></span>|  
|<span data-ttu-id="90727-153">Нижний регистр</span><span class="sxs-lookup"><span data-stu-id="90727-153">Lowercase</span></span>|<span data-ttu-id="90727-154">Хирагана, катакана, половинная ширина, полная ширина</span><span class="sxs-lookup"><span data-stu-id="90727-154">Hiragana, katakana, half width, full width</span></span>|  
|<span data-ttu-id="90727-155">Верхний регистр</span><span class="sxs-lookup"><span data-stu-id="90727-155">Uppercase</span></span>|<span data-ttu-id="90727-156">Хирагана, катакана, половинная ширина, полная ширина</span><span class="sxs-lookup"><span data-stu-id="90727-156">Hiragana, katakana, half width, full width</span></span>|  
  
## <a name="configuration-of-the-character-map-transformation"></a><span data-ttu-id="90727-157">Настройка преобразования «Таблица символов»</span><span class="sxs-lookup"><span data-stu-id="90727-157">Configuration of the Character Map Transformation</span></span>  
 <span data-ttu-id="90727-158">Чтобы настроить преобразование «Таблица символов» необходимо:</span><span class="sxs-lookup"><span data-stu-id="90727-158">You configure the Character Map transformation in the following ways:</span></span>  
  
-   <span data-ttu-id="90727-159">указать столбцы для преобразования;</span><span class="sxs-lookup"><span data-stu-id="90727-159">Specify the columns to convert.</span></span>  
  
-   <span data-ttu-id="90727-160">указать операции, которые будут применяться к каждому столбцу.</span><span class="sxs-lookup"><span data-stu-id="90727-160">Specify the operations to apply to each column.</span></span>  
  
 <span data-ttu-id="90727-161">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="90727-161">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="90727-162">Дополнительные сведения о свойствах, которые можно установить в диалоговом окне **Редактор преобразования «Таблица соответствия символов»** см. в разделе [Character Map Transformation Editor](../../character-map-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="90727-162">For more information about the properties that you can set in the **Character Map Transformation Editor** dialog box, see [Character Map Transformation Editor](../../character-map-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="90727-163">Диалоговое окно **Расширенный редактор** содержит свойства, которые можно установить с помощью программных средств.</span><span class="sxs-lookup"><span data-stu-id="90727-163">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="90727-164">Дополнительные сведения о свойствах, которые вы можете задать в диалоговом окне **Расширенный редактор** или программными средствами, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="90727-164">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="90727-165">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="90727-165">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="90727-166">Пользовательские свойства преобразований</span><span class="sxs-lookup"><span data-stu-id="90727-166">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="90727-167">Дополнительные сведения о настройке свойств см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="90727-167">For more information about how to set properties, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="90727-168">Установление свойств компонента потока данных</span><span class="sxs-lookup"><span data-stu-id="90727-168">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
-   [<span data-ttu-id="90727-169">Сортировка данных для преобразований "Слияние" и "Соединение слиянием"</span><span class="sxs-lookup"><span data-stu-id="90727-169">Sort Data for the Merge and Merge Join Transformations</span></span>](sort-data-for-the-merge-and-merge-join-transformations.md)  
  
  
