---
title: Преобразование "Конвертация данных" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataconversiontrans.f1
helpviewer_keywords:
- converting data types [Integration Services]
- Data Conversion transformation
- data types [Integration Services], converting
ms.assetid: fd515bbc-6f49-4d0c-ae7f-6ea3c3f24a1c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 57b1f70c070cdf81dc0bc899ed365d048db26cc9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655285"
---
# <a name="data-conversion-transformation"></a><span data-ttu-id="21bff-102">преобразование «Конвертация данных»</span><span class="sxs-lookup"><span data-stu-id="21bff-102">Data Conversion Transformation</span></span>
  <span data-ttu-id="21bff-103">При преобразовании «Конвертация данных» данные во входном столбце преобразуются в другой тип, а затем копируются в новый выходной столбец.</span><span class="sxs-lookup"><span data-stu-id="21bff-103">The Data Conversion transformation converts the data in an input column to a different data type and then copies it to a new output column.</span></span> <span data-ttu-id="21bff-104">Например, пакет может извлечь данные из нескольких источников, а затем с помощью этого преобразования привести столбцы к типу данных, требуемому целевым хранилищем данных.</span><span class="sxs-lookup"><span data-stu-id="21bff-104">For example, a package can extract data from multiple sources, and then use this transformation to convert columns to the data type required by the destination data store.</span></span> <span data-ttu-id="21bff-105">К одному входному столбцу можно применять несколько преобразований.</span><span class="sxs-lookup"><span data-stu-id="21bff-105">You can apply multiple conversions to a single input column.</span></span>  
  
 <span data-ttu-id="21bff-106">С помощью этой функции пакет может выполнять следующие типы преобразований данных:</span><span class="sxs-lookup"><span data-stu-id="21bff-106">Using this transformation, a package can perform the following types of data conversions:</span></span>  
  
-   <span data-ttu-id="21bff-107">Изменить тип данных.</span><span class="sxs-lookup"><span data-stu-id="21bff-107">Change the data type.</span></span> <span data-ttu-id="21bff-108">Дополнительные сведения см. в разделе [Integration Services Data Types](../integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="21bff-108">For more information, see [Integration Services Data Types](../integration-services-data-types.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="21bff-109">Если данные преобразуются в тип данных даты или даты и времени, дата в выходном столбце имеет формат ISO, хотя специфические локали могут задавать другой формат.</span><span class="sxs-lookup"><span data-stu-id="21bff-109">If you are converting data to a date or a datetime data type, the date in the output column is in the ISO format, although the locale preference may specify a different format.</span></span>  
  
-   <span data-ttu-id="21bff-110">Задавать длину столбца строковых данных, а также точность и масштаб числовых данных.</span><span class="sxs-lookup"><span data-stu-id="21bff-110">Set the column length of string data and the precision and scale on numeric data.</span></span> <span data-ttu-id="21bff-111">Дополнительные сведения см. в разделе [Точность, масштаб и длина (Transact-SQL)](/sql/t-sql/data-types/precision-scale-and-length-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="21bff-111">For more information, see [Precision, Scale, and Length &#40;Transact-SQL&#41;](/sql/t-sql/data-types/precision-scale-and-length-transact-sql).</span></span>  
  
-   <span data-ttu-id="21bff-112">Указать кодовую страницу.</span><span class="sxs-lookup"><span data-stu-id="21bff-112">Specify a code page.</span></span> <span data-ttu-id="21bff-113">Дополнительные сведения см. в статье [Comparing String Data](../comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="21bff-113">For more information, see [Comparing String Data](../comparing-string-data.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="21bff-114">При выполнении копирования столбцов строкового типа данных оба столбца должны использовать одну и ту же кодовую страницу.</span><span class="sxs-lookup"><span data-stu-id="21bff-114">When copying between columns with a string data type, the two columns must use the same code page.</span></span>  
  
 <span data-ttu-id="21bff-115">Если длина выходного столбца строковых данных меньше, чем длина соответствующего ему входного столбца, выходные данные усекаются.</span><span class="sxs-lookup"><span data-stu-id="21bff-115">If the length of an output column of string data is shorter than the length of its corresponding input column, the output data is truncated.</span></span> <span data-ttu-id="21bff-116">Дополнительные сведения см. в разделе [Обработка ошибок в данных](../error-handling-in-data.md).</span><span class="sxs-lookup"><span data-stu-id="21bff-116">For more information, see [Error Handling in Data](../error-handling-in-data.md).</span></span>  
  
 <span data-ttu-id="21bff-117">Это преобразование имеет один вход, один выход и один выход ошибок.</span><span class="sxs-lookup"><span data-stu-id="21bff-117">This transformation has one input, one output, and one error output.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="21bff-118">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="21bff-118">Related Tasks</span></span>  
 <span data-ttu-id="21bff-119">Свойства могут устанавливаться через конструктор служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] или с помощью программных средств.</span><span class="sxs-lookup"><span data-stu-id="21bff-119">You can set properties through the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span> <span data-ttu-id="21bff-120">Сведения об использовании преобразования "Конвертация данных" в конструкторе SSIS см. в разделах [Преобразование данных в другой тип данных с помощью преобразования "Конвертация данных"](data-conversion-transformation.md) и [Редактор преобразования "Конвертация данных"](../../data-conversion-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="21bff-120">For information about using the Data Conversion Transformation in the SSIS Designer, see [Convert Data to a Different Data Type by Using the Data Conversion Transformation](data-conversion-transformation.md) and [Data Conversion Transformation Editor](../../data-conversion-transformation-editor.md).</span></span> <span data-ttu-id="21bff-121">Сведения о настройке свойств этого преобразования программными средствами см. в разделах [Общие свойства](../../common-properties.md) и [Пользовательские свойства преобразований](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="21bff-121">For information about setting properties of this transformation programmatically, see [Common Properties](../../common-properties.md) and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="21bff-122">См. также</span><span class="sxs-lookup"><span data-stu-id="21bff-122">Related Content</span></span>  
 <span data-ttu-id="21bff-123">Запись в блоге [Сравнение производительности между способами преобразования типов данных в службах SSIS 2008](https://techcommunity.microsoft.com/t5/datacat/performance-comparison-between-data-type-conversion-techniques/ba-p/305035)на сайте blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="21bff-123">Blog entry, [Performance Comparison between Data Type Conversion Techniques in SSIS 2008](https://techcommunity.microsoft.com/t5/datacat/performance-comparison-between-data-type-conversion-techniques/ba-p/305035), on blogs.msdn.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21bff-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="21bff-124">See Also</span></span>  
 <span data-ttu-id="21bff-125">[Быстрый синтаксический анализ](../../fast-parse.md) </span><span class="sxs-lookup"><span data-stu-id="21bff-125">[Fast Parse](../../fast-parse.md) </span></span>  
 <span data-ttu-id="21bff-126">[Поток данных](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="21bff-126">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="21bff-127">Преобразования служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="21bff-127">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
