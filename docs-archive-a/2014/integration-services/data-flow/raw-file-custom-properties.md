---
title: Пользовательские свойства необработанного файла | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 7e81f7e1-fac0-4b57-b145-8f1b9e4720bf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7614c03fbf44f37597e586549e306d01c28b523d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657182"
---
# <a name="raw-file-custom-properties"></a><span data-ttu-id="fe3cf-102">Пользовательские свойства необработанного файла</span><span class="sxs-lookup"><span data-stu-id="fe3cf-102">Raw File Custom Properties</span></span>
  <span data-ttu-id="fe3cf-103">**Пользовательские свойства источника**</span><span class="sxs-lookup"><span data-stu-id="fe3cf-103">**Source Custom Properties**</span></span>  
  
 <span data-ttu-id="fe3cf-104">Источник «Необработанный файл» обладает как пользовательскими свойствами, так и свойствами, общими для всех компонентов потока данных.</span><span class="sxs-lookup"><span data-stu-id="fe3cf-104">The Raw File source has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="fe3cf-105">В следующей таблице описаны пользовательские свойства источника «Необработанный файл».</span><span class="sxs-lookup"><span data-stu-id="fe3cf-105">The following table describes the custom properties of the Raw File source.</span></span> <span data-ttu-id="fe3cf-106">Все свойства доступны для чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="fe3cf-106">All properties are read/write.</span></span>  
  
|<span data-ttu-id="fe3cf-107">Имя свойства</span><span class="sxs-lookup"><span data-stu-id="fe3cf-107">Property name</span></span>|<span data-ttu-id="fe3cf-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="fe3cf-108">Data Type</span></span>|<span data-ttu-id="fe3cf-109">Description</span><span class="sxs-lookup"><span data-stu-id="fe3cf-109">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="fe3cf-110">AccessMode</span><span class="sxs-lookup"><span data-stu-id="fe3cf-110">AccessMode</span></span>|<span data-ttu-id="fe3cf-111">Integer (перечисление)</span><span class="sxs-lookup"><span data-stu-id="fe3cf-111">Integer (enumeration)</span></span>|<span data-ttu-id="fe3cf-112">Режим, используемый для доступа к необработанным данным.</span><span class="sxs-lookup"><span data-stu-id="fe3cf-112">The mode used to access the raw data.</span></span> <span data-ttu-id="fe3cf-113">Допустимые значения — `File name` (0) и `File name from variable` (1).</span><span class="sxs-lookup"><span data-stu-id="fe3cf-113">The possible values are `File name` (0) and `File name from variable` (1).</span></span> <span data-ttu-id="fe3cf-114">Значение по умолчанию — `File name` (0).</span><span class="sxs-lookup"><span data-stu-id="fe3cf-114">The default value is `File name` (0).</span></span>|  
|<span data-ttu-id="fe3cf-115">FileName</span><span class="sxs-lookup"><span data-stu-id="fe3cf-115">FileName</span></span>|<span data-ttu-id="fe3cf-116">String</span><span class="sxs-lookup"><span data-stu-id="fe3cf-116">String</span></span>|<span data-ttu-id="fe3cf-117">Полный путь и имя исходного файла.</span><span class="sxs-lookup"><span data-stu-id="fe3cf-117">The path and file name of the source file.</span></span>|  
  
 <span data-ttu-id="fe3cf-118">Вывод и выходные столбцы источника «Необработанный файл» не имеют пользовательских свойств.</span><span class="sxs-lookup"><span data-stu-id="fe3cf-118">The output and the output columns of the Raw File source have no custom properties.</span></span>  
  
 <span data-ttu-id="fe3cf-119">Дополнительные сведения см. в статье [Raw File Source](raw-file-source.md).</span><span class="sxs-lookup"><span data-stu-id="fe3cf-119">For more information, see [Raw File Source](raw-file-source.md).</span></span>  
  
 <span data-ttu-id="fe3cf-120">**Пользовательские свойства назначений**</span><span class="sxs-lookup"><span data-stu-id="fe3cf-120">**Destination Custom Properties**</span></span>  
  
 <span data-ttu-id="fe3cf-121">Назначение «Необработанный файл» обладает как пользовательскими свойствами, так и свойствами, общими для всех компонентов потока данных.</span><span class="sxs-lookup"><span data-stu-id="fe3cf-121">The Raw File destination has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="fe3cf-122">В следующей таблице описаны пользовательские свойства назначения «Необработанный файл».</span><span class="sxs-lookup"><span data-stu-id="fe3cf-122">The following table describes the custom properties of the Raw File destination.</span></span> <span data-ttu-id="fe3cf-123">Все свойства доступны для чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="fe3cf-123">All properties are read/write.</span></span>  
  
|<span data-ttu-id="fe3cf-124">Имя свойства</span><span class="sxs-lookup"><span data-stu-id="fe3cf-124">Property name</span></span>|<span data-ttu-id="fe3cf-125">Тип данных</span><span class="sxs-lookup"><span data-stu-id="fe3cf-125">Data Type</span></span>|<span data-ttu-id="fe3cf-126">Description</span><span class="sxs-lookup"><span data-stu-id="fe3cf-126">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="fe3cf-127">AccessMode</span><span class="sxs-lookup"><span data-stu-id="fe3cf-127">AccessMode</span></span>|<span data-ttu-id="fe3cf-128">Integer (перечисление)</span><span class="sxs-lookup"><span data-stu-id="fe3cf-128">Integer (enumeration)</span></span>|<span data-ttu-id="fe3cf-129">Значение, указывающее, содержит ли свойство FileName имя файла, или указывающее переменную, которая содержит имя файла.</span><span class="sxs-lookup"><span data-stu-id="fe3cf-129">A value that specifies whether the FileName property contains a file name, or the name of a variable that contains a file name.</span></span> <span data-ttu-id="fe3cf-130">Параметрами являются `File name` (0) и `File name from variable` (1).</span><span class="sxs-lookup"><span data-stu-id="fe3cf-130">The options are `File name` (0) and `File name from variable` (1).</span></span>|  
|<span data-ttu-id="fe3cf-131">FileName</span><span class="sxs-lookup"><span data-stu-id="fe3cf-131">FileName</span></span>|<span data-ttu-id="fe3cf-132">String</span><span class="sxs-lookup"><span data-stu-id="fe3cf-132">String</span></span>|<span data-ttu-id="fe3cf-133">Имя файла, в который назначение «Необработанный файл» осуществляет запись.</span><span class="sxs-lookup"><span data-stu-id="fe3cf-133">The name of the file to which the Raw File destination writes.</span></span>|  
|<span data-ttu-id="fe3cf-134">WriteOption</span><span class="sxs-lookup"><span data-stu-id="fe3cf-134">WriteOption</span></span>|<span data-ttu-id="fe3cf-135">Integer (перечисление)</span><span class="sxs-lookup"><span data-stu-id="fe3cf-135">Integer (enumeration)</span></span>|<span data-ttu-id="fe3cf-136">Значение, указывающее, следует ли назначению «Необработанный файл» удалять существующий файл с таким же именем.</span><span class="sxs-lookup"><span data-stu-id="fe3cf-136">A value that specifies whether the Raw File destination deletes an existing file that has the same name.</span></span> <span data-ttu-id="fe3cf-137">Допустимые параметры — `Create Always` (0), `Create Once` (1), `Truncate and Append` (3) и `Append` (2).</span><span class="sxs-lookup"><span data-stu-id="fe3cf-137">The options are `Create Always` (0), `Create Once` (1), `Truncate and Append` (3), and `Append` (2).</span></span> <span data-ttu-id="fe3cf-138">По умолчанию это свойство имеет значение `Create Always` (0).</span><span class="sxs-lookup"><span data-stu-id="fe3cf-138">The default value of this property is `Create Always` (0).</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="fe3cf-139">Операция добавления в файл требует, чтобы метаданные добавляемых данных совпадали с метаданными данных, уже содержащихся в файле.</span><span class="sxs-lookup"><span data-stu-id="fe3cf-139">An append operation requires the metadata of the appended data to match the metadata of the data already present in the file.</span></span>  
  
 <span data-ttu-id="fe3cf-140">У ввода и входных столбцов назначения «Необработанный файл» нет пользовательских свойств.</span><span class="sxs-lookup"><span data-stu-id="fe3cf-140">The input and the input columns of the Raw File destination have no custom properties.</span></span>  
  
 <span data-ttu-id="fe3cf-141">Дополнительные сведения см. в статье [Raw File Destination](raw-file-destination.md).</span><span class="sxs-lookup"><span data-stu-id="fe3cf-141">For more information, see [Raw File Destination](raw-file-destination.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe3cf-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="fe3cf-142">See Also</span></span>  
 [<span data-ttu-id="fe3cf-143">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="fe3cf-143">Common Properties</span></span>](../common-properties.md)  
  
  
