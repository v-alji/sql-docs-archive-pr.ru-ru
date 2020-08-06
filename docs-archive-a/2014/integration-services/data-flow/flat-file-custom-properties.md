---
title: Пользовательские свойства неструктурированного файла | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 7f2caeab-784c-4b0c-9b3e-6a88d1ccdbf9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b906e9268bf3a74ffcf5661953397ad7a24b77a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751319"
---
# <a name="flat-file-custom-properties"></a><span data-ttu-id="2dba1-102">Пользовательские свойства неструктурированного файла</span><span class="sxs-lookup"><span data-stu-id="2dba1-102">Flat File Custom Properties</span></span>
  <span data-ttu-id="2dba1-103">**Пользовательские свойства источника**</span><span class="sxs-lookup"><span data-stu-id="2dba1-103">**Source Custom Properties**</span></span>  
  
 <span data-ttu-id="2dba1-104">Источник «Неструктурированный файл» обладает как пользовательскими свойствами, так и свойствами, общими для всех компонентов потока данных.</span><span class="sxs-lookup"><span data-stu-id="2dba1-104">The Flat File source has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="2dba1-105">В следующей таблице описаны пользовательские свойства источника «Неструктурированный файл».</span><span class="sxs-lookup"><span data-stu-id="2dba1-105">The following table describes the custom properties of the Flat File source.</span></span> <span data-ttu-id="2dba1-106">Все свойства доступны для чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="2dba1-106">All properties are read/write.</span></span>  
  
|<span data-ttu-id="2dba1-107">Имя свойства</span><span class="sxs-lookup"><span data-stu-id="2dba1-107">Property name</span></span>|<span data-ttu-id="2dba1-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="2dba1-108">Data Type</span></span>|<span data-ttu-id="2dba1-109">Description</span><span class="sxs-lookup"><span data-stu-id="2dba1-109">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="2dba1-110">FileNameColumnName</span><span class="sxs-lookup"><span data-stu-id="2dba1-110">FileNameColumnName</span></span>|<span data-ttu-id="2dba1-111">String</span><span class="sxs-lookup"><span data-stu-id="2dba1-111">String</span></span>|<span data-ttu-id="2dba1-112">Имя выходного столбца, который содержит имя файла.</span><span class="sxs-lookup"><span data-stu-id="2dba1-112">The name of an output column that contains the file name.</span></span> <span data-ttu-id="2dba1-113">Если имя не указано, выходной столбец с именем файла не будет сформирован.</span><span class="sxs-lookup"><span data-stu-id="2dba1-113">If no name is specified, no output column containing the file name will be generated.</span></span><br /><br /> <span data-ttu-id="2dba1-114">Примечание. Это свойство недоступно в диалоговом окне **Редактор источника "Неструктурированный файл"** , однако его можно установить с помощью окна **Расширенный редактор**.</span><span class="sxs-lookup"><span data-stu-id="2dba1-114">Note: This property is not available in the **Flat File Source Editor**, but can be set by using the **Advanced Editor**.</span></span>|  
|<span data-ttu-id="2dba1-115">RetainNulls</span><span class="sxs-lookup"><span data-stu-id="2dba1-115">RetainNulls</span></span>|<span data-ttu-id="2dba1-116">Логическое</span><span class="sxs-lookup"><span data-stu-id="2dba1-116">Boolean</span></span>|<span data-ttu-id="2dba1-117">Значение указывает, будут ли значения NULL из исходного файла сохранены как значения NULL при обработке данных конвейером преобразования данных.</span><span class="sxs-lookup"><span data-stu-id="2dba1-117">A value that specifies whether to retain Null values from the source file as Null values when the data is processed by the Data Transformation Pipeline engine.</span></span> <span data-ttu-id="2dba1-118">Значение по умолчанию этого свойства равно `False`.</span><span class="sxs-lookup"><span data-stu-id="2dba1-118">The default value of this property is `False`.</span></span>|  
  
 <span data-ttu-id="2dba1-119">Выход источника «Неструктурированный файл» не имеет пользовательских свойств.</span><span class="sxs-lookup"><span data-stu-id="2dba1-119">The output of the Flat File source has no custom properties.</span></span>  
  
 <span data-ttu-id="2dba1-120">В следующей таблице описаны пользовательские свойства выходных столбцов источника «Неструктурированный файл».</span><span class="sxs-lookup"><span data-stu-id="2dba1-120">The following table describes the custom properties of the output columns of the Flat File source.</span></span> <span data-ttu-id="2dba1-121">Все свойства доступны для чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="2dba1-121">All properties are read/write.</span></span>  
  
|<span data-ttu-id="2dba1-122">Имя свойства</span><span class="sxs-lookup"><span data-stu-id="2dba1-122">Property name</span></span>|<span data-ttu-id="2dba1-123">Тип данных</span><span class="sxs-lookup"><span data-stu-id="2dba1-123">Data Type</span></span>|<span data-ttu-id="2dba1-124">Description</span><span class="sxs-lookup"><span data-stu-id="2dba1-124">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="2dba1-125">FastParse</span><span class="sxs-lookup"><span data-stu-id="2dba1-125">FastParse</span></span>|<span data-ttu-id="2dba1-126">Логическое</span><span class="sxs-lookup"><span data-stu-id="2dba1-126">Boolean</span></span>|<span data-ttu-id="2dba1-127">Указывает, используются для столбца более быстрые, но независимые от локали процедуры синтаксического анализа, предоставляемые службами DTS, либо стандартные процедуры, зависимые от локали.</span><span class="sxs-lookup"><span data-stu-id="2dba1-127">A value that indicates whether the column uses the quicker, but locale-insensitive, fast parsing routines that DTS provides or the locale-sensitive standard parsing routines.</span></span> <span data-ttu-id="2dba1-128">Дополнительные сведения см. в разделах [Fast Parse](../fast-parse.md) и [Standard Parse](../standard-parse.md).</span><span class="sxs-lookup"><span data-stu-id="2dba1-128">For more information, see [Fast Parse](../fast-parse.md) and [Standard Parse](../standard-parse.md).</span></span> <span data-ttu-id="2dba1-129">Значение по умолчанию этого свойства равно `False`.</span><span class="sxs-lookup"><span data-stu-id="2dba1-129">The default value of this property is `False`.</span></span><br /><br /> <span data-ttu-id="2dba1-130">Примечание. Это свойство недоступно в диалоговом окне **Редактор источника "Неструктурированный файл"** , однако его можно установить с помощью окна **Расширенный редактор**.</span><span class="sxs-lookup"><span data-stu-id="2dba1-130">Note: This property is not available in the **Flat File Source Editor**, but can be set by using the **Advanced Editor**.</span></span>|  
  
 <span data-ttu-id="2dba1-131">Дополнительные сведения см. в статье [Flat File Source](flat-file-source.md).</span><span class="sxs-lookup"><span data-stu-id="2dba1-131">For more information, see [Flat File Source](flat-file-source.md).</span></span>  
  
 <span data-ttu-id="2dba1-132">**Пользовательские свойства назначений**</span><span class="sxs-lookup"><span data-stu-id="2dba1-132">**Destination Custom Properties**</span></span>  
  
 <span data-ttu-id="2dba1-133">Назначение «Неструктурированный файл» обладает как пользовательскими свойствами, так и свойствами, общими для всех компонентов потока данных.</span><span class="sxs-lookup"><span data-stu-id="2dba1-133">The Flat File destination has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="2dba1-134">В следующей таблице описаны пользовательские свойства назначения «Неструктурированный файл».</span><span class="sxs-lookup"><span data-stu-id="2dba1-134">The following table describes the custom properties of the Flat File destination.</span></span> <span data-ttu-id="2dba1-135">Все свойства доступны для чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="2dba1-135">All properties are read/write.</span></span>  
  
|<span data-ttu-id="2dba1-136">Имя свойства</span><span class="sxs-lookup"><span data-stu-id="2dba1-136">Property name</span></span>|<span data-ttu-id="2dba1-137">Тип данных</span><span class="sxs-lookup"><span data-stu-id="2dba1-137">Data Type</span></span>|<span data-ttu-id="2dba1-138">Description</span><span class="sxs-lookup"><span data-stu-id="2dba1-138">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="2dba1-139">Заголовок</span><span class="sxs-lookup"><span data-stu-id="2dba1-139">Header</span></span>|<span data-ttu-id="2dba1-140">String</span><span class="sxs-lookup"><span data-stu-id="2dba1-140">String</span></span>|<span data-ttu-id="2dba1-141">Блок текста, вставляемый в файл перед записью в него каких-либо данных.</span><span class="sxs-lookup"><span data-stu-id="2dba1-141">A block of text that is inserted in the file before any data is written.</span></span><br /><br /> <span data-ttu-id="2dba1-142">Значение этого свойства можно задать с помощью выражения свойства.</span><span class="sxs-lookup"><span data-stu-id="2dba1-142">The value of this property can be specified by using a property expression.</span></span>|  
|<span data-ttu-id="2dba1-143">Overwrite</span><span class="sxs-lookup"><span data-stu-id="2dba1-143">Overwrite</span></span>|<span data-ttu-id="2dba1-144">Логическое</span><span class="sxs-lookup"><span data-stu-id="2dba1-144">Boolean</span></span>|<span data-ttu-id="2dba1-145">Значение, указывающее, следует ли перезаписывать существующий целевой файл с таким же именем или добавлять данные в его конец.</span><span class="sxs-lookup"><span data-stu-id="2dba1-145">A value that specifies whether to overwrite or append to an existing destination file that has the same name.</span></span> <span data-ttu-id="2dba1-146">Значение по умолчанию этого свойства равно `True`.</span><span class="sxs-lookup"><span data-stu-id="2dba1-146">The default value of this property is `True`.</span></span>|  
  
 <span data-ttu-id="2dba1-147">У ввода и входных столбцов назначения «Неструктурированный файл» нет пользовательских свойств.</span><span class="sxs-lookup"><span data-stu-id="2dba1-147">The input and the input columns of the Flat File destination have no custom properties.</span></span>  
  
 <span data-ttu-id="2dba1-148">Дополнительные сведения см. в статье [Flat File Destination](flat-file-destination.md).</span><span class="sxs-lookup"><span data-stu-id="2dba1-148">For more information, see [Flat File Destination](flat-file-destination.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dba1-149">См. также:</span><span class="sxs-lookup"><span data-stu-id="2dba1-149">See Also</span></span>  
 [<span data-ttu-id="2dba1-150">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="2dba1-150">Common Properties</span></span>](../common-properties.md)  
  
  
