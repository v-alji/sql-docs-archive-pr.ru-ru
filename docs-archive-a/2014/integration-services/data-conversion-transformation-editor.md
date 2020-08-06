---
title: Редактор преобразования "Конвертация данных" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataconversiontransformation.f1
helpviewer_keywords:
- Data Conversion Transformation Editor
ms.assetid: 7b4e4873-e8fe-4549-a965-65bebdb270bc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4b893f04dcca2dd2a1a5874b55c1c1c608aaeb12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751372"
---
# <a name="data-conversion-transformation-editor"></a><span data-ttu-id="422a0-102">редактор преобразования «Конвертация данных»</span><span class="sxs-lookup"><span data-stu-id="422a0-102">Data Conversion Transformation Editor</span></span>
  <span data-ttu-id="422a0-103">Используйте диалоговое окно **Редактор преобразования «Конвертация данных»** , чтобы выбрать столбцы, подлежащие преобразованию, выбрать тип данных, в который должен быть преобразован столбец, и установить атрибуты преобразования.</span><span class="sxs-lookup"><span data-stu-id="422a0-103">Use the **Data Conversion Transformation Editor** dialog box to select the columns to convert, select the data type to which the column is converted, and set conversion attributes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="422a0-104">`FastParse`Свойство выходных столбцов преобразования «Конвертация данных» недоступно в **редакторе преобразования «Конвертация данных**», но может быть задано с помощью **Расширенный редактор**.</span><span class="sxs-lookup"><span data-stu-id="422a0-104">The `FastParse` property of the output columns of the Data Conversion transformation is not available in the **Data Conversion Transformation Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="422a0-105">Дополнительные сведения о данном свойстве см. в подразделе «Преобразование "Конвертация данных"» раздела [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="422a0-105">For more information on this property, see the Data Conversion Transformation section of [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="422a0-106">Для более подробного знакомства с преобразованием «Конвертация данных» см. раздел [Data Conversion Transformation](data-flow/transformations/data-conversion-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="422a0-106">To learn more about the Data Conversion transformation, see [Data Conversion Transformation](data-flow/transformations/data-conversion-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="422a0-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="422a0-107">Options</span></span>  
 <span data-ttu-id="422a0-108">**Доступные входные столбцы**</span><span class="sxs-lookup"><span data-stu-id="422a0-108">**Available Input Columns**</span></span>  
 <span data-ttu-id="422a0-109">Выберите столбцы, подлежащие преобразованию, установив флажки.</span><span class="sxs-lookup"><span data-stu-id="422a0-109">Select columns to convert by using the check boxes.</span></span> <span data-ttu-id="422a0-110">Выбранные столбцы добавляются в качестве входных столбцов в таблицу, представленную ниже.</span><span class="sxs-lookup"><span data-stu-id="422a0-110">Your selections add input columns to the table below.</span></span>  
  
 <span data-ttu-id="422a0-111">**Входной столбец**</span><span class="sxs-lookup"><span data-stu-id="422a0-111">**Input Column**</span></span>  
 <span data-ttu-id="422a0-112">Выберите столбцы, подлежащие преобразованию, из списка доступных входных столбцов.</span><span class="sxs-lookup"><span data-stu-id="422a0-112">Select columns to convert from the list of available input columns.</span></span> <span data-ttu-id="422a0-113">Выбранные пункты отражены набором установленных выше флажков.</span><span class="sxs-lookup"><span data-stu-id="422a0-113">Your selections are reflected in the check box selections above.</span></span>  
  
 <span data-ttu-id="422a0-114">**Псевдоним вывода**</span><span class="sxs-lookup"><span data-stu-id="422a0-114">**Output Alias**</span></span>  
 <span data-ttu-id="422a0-115">Введите псевдоним для каждого нового столбца.</span><span class="sxs-lookup"><span data-stu-id="422a0-115">Type an alias for each new column.</span></span> <span data-ttu-id="422a0-116">Значением по умолчанию является `Copy of`, за которым следует имя входного столбца, однако можно выбрать любое уникальное описательное имя.</span><span class="sxs-lookup"><span data-stu-id="422a0-116">The default is `Copy of` followed by the input column name; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="422a0-117">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="422a0-117">**Data Type**</span></span>  
 <span data-ttu-id="422a0-118">Выберите доступный тип данных из списка.</span><span class="sxs-lookup"><span data-stu-id="422a0-118">Select an available data type from the list.</span></span> <span data-ttu-id="422a0-119">Дополнительные сведения см. в разделе [Integration Services Data Types](data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="422a0-119">For more information, see [Integration Services Data Types](data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="422a0-120">**Длина**</span><span class="sxs-lookup"><span data-stu-id="422a0-120">**Length**</span></span>  
 <span data-ttu-id="422a0-121">Установите ширину столбца для строковых данных.</span><span class="sxs-lookup"><span data-stu-id="422a0-121">Set the column length for string data.</span></span>  
  
 <span data-ttu-id="422a0-122">**Точность**</span><span class="sxs-lookup"><span data-stu-id="422a0-122">**Precision**</span></span>  
 <span data-ttu-id="422a0-123">Установите точность для числовых данных.</span><span class="sxs-lookup"><span data-stu-id="422a0-123">Set the precision for numeric data.</span></span>  
  
 <span data-ttu-id="422a0-124">**Масштаб**</span><span class="sxs-lookup"><span data-stu-id="422a0-124">**Scale**</span></span>  
 <span data-ttu-id="422a0-125">Установите масштаб для числовых данных.</span><span class="sxs-lookup"><span data-stu-id="422a0-125">Set the scale for numeric data.</span></span>  
  
 <span data-ttu-id="422a0-126">**Кодовая страница**</span><span class="sxs-lookup"><span data-stu-id="422a0-126">**Code page**</span></span>  
 <span data-ttu-id="422a0-127">Выберите подходящую кодовую страницу для столбцов типа DT_STR.</span><span class="sxs-lookup"><span data-stu-id="422a0-127">Select the appropriate code page for columns of type DT_STR.</span></span>  
  
 <span data-ttu-id="422a0-128">**Настройка вывода ошибок**</span><span class="sxs-lookup"><span data-stu-id="422a0-128">**Configure error output**</span></span>  
 <span data-ttu-id="422a0-129">Укажите способ обработки ошибок уровня строк в диалоговом окне [Настройка вывода ошибок](../../2014/integration-services/configure-error-output.md) .</span><span class="sxs-lookup"><span data-stu-id="422a0-129">Specify how to handle row-level errors by using the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="422a0-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="422a0-130">See Also</span></span>  
 <span data-ttu-id="422a0-131">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="422a0-131">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="422a0-132">Преобразование данных в другой тип данных с помощью преобразования «Конвертация данных»</span><span class="sxs-lookup"><span data-stu-id="422a0-132">Convert Data to a Different Data Type by Using the Data Conversion Transformation</span></span>](data-flow/transformations/convert-data-type-by-using-data-conversion-transformation.md)  
  
  
