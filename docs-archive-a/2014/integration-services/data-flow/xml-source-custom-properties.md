---
title: Пользовательские свойства источника "XML" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: eb29b28c-3159-41ec-b3d7-fce5b2f2be55
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5e152b23b4f59ca46cb8272ca677dc1161b3efec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667290"
---
# <a name="xml-source-custom-properties"></a><span data-ttu-id="c30bc-102">Пользовательские свойства источника «XML»</span><span class="sxs-lookup"><span data-stu-id="c30bc-102">XML Source Custom Properties</span></span>
  <span data-ttu-id="c30bc-103">Источник «XML» обладает как пользовательскими свойствами, так и свойствами, общими для всех компонентов потока данных.</span><span class="sxs-lookup"><span data-stu-id="c30bc-103">The XML source has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="c30bc-104">В следующей таблице описаны пользовательские свойства источника «XML».</span><span class="sxs-lookup"><span data-stu-id="c30bc-104">The following table describes the custom properties of the XML source.</span></span> <span data-ttu-id="c30bc-105">Все свойства доступны для чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="c30bc-105">All properties are read/write.</span></span>  
  
|<span data-ttu-id="c30bc-106">Имя свойства</span><span class="sxs-lookup"><span data-stu-id="c30bc-106">Property name</span></span>|<span data-ttu-id="c30bc-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="c30bc-107">Data Type</span></span>|<span data-ttu-id="c30bc-108">Description</span><span class="sxs-lookup"><span data-stu-id="c30bc-108">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="c30bc-109">AccessMode</span><span class="sxs-lookup"><span data-stu-id="c30bc-109">AccessMode</span></span>|<span data-ttu-id="c30bc-110">Целое число</span><span class="sxs-lookup"><span data-stu-id="c30bc-110">Integer</span></span>|<span data-ttu-id="c30bc-111">Режим, используемый для доступа к XML-данным.</span><span class="sxs-lookup"><span data-stu-id="c30bc-111">The mode used to access the XML data.</span></span>|  
|<span data-ttu-id="c30bc-112">UseInlineSchema</span><span class="sxs-lookup"><span data-stu-id="c30bc-112">UseInlineSchema</span></span>|<span data-ttu-id="c30bc-113">Логическое</span><span class="sxs-lookup"><span data-stu-id="c30bc-113">Boolean</span></span>|<span data-ttu-id="c30bc-114">Указывает, следует ли использовать в источнике «XML» определение встроенной схемы.</span><span class="sxs-lookup"><span data-stu-id="c30bc-114">A value that indicates whether to use an inline schema definition within the XML source.</span></span> <span data-ttu-id="c30bc-115">Значение по умолчанию этого свойства равно `False`.</span><span class="sxs-lookup"><span data-stu-id="c30bc-115">The default value of this property is `False`.</span></span>|  
|<span data-ttu-id="c30bc-116">XMLData</span><span class="sxs-lookup"><span data-stu-id="c30bc-116">XMLData</span></span>|<span data-ttu-id="c30bc-117">String</span><span class="sxs-lookup"><span data-stu-id="c30bc-117">String</span></span>|<span data-ttu-id="c30bc-118">Файл или переменные, из которых следует получить XML-данные.</span><span class="sxs-lookup"><span data-stu-id="c30bc-118">The file or variables from which to retrieve the XML data.</span></span><br /><br /> <span data-ttu-id="c30bc-119">Значение этого свойства можно задать с помощью выражения свойства.</span><span class="sxs-lookup"><span data-stu-id="c30bc-119">The value of this property can be specified by using a property expression.</span></span>|  
|<span data-ttu-id="c30bc-120">XMLSchemaDefinition</span><span class="sxs-lookup"><span data-stu-id="c30bc-120">XMLSchemaDefinition</span></span>|<span data-ttu-id="c30bc-121">String</span><span class="sxs-lookup"><span data-stu-id="c30bc-121">String</span></span>|<span data-ttu-id="c30bc-122">Полный путь и имя файла определения схемы (XSD).</span><span class="sxs-lookup"><span data-stu-id="c30bc-122">The path and file name of the schema definition file (.xsd).</span></span><br /><br /> <span data-ttu-id="c30bc-123">Значение этого свойства можно задать с помощью выражения свойства.</span><span class="sxs-lookup"><span data-stu-id="c30bc-123">The value of this property can be specified by using a property expression.</span></span>|  
  
 <span data-ttu-id="c30bc-124">В следующей таблице описаны пользовательские свойства выхода источника «XML».</span><span class="sxs-lookup"><span data-stu-id="c30bc-124">The following table describes the custom properties of the output of the XML source.</span></span> <span data-ttu-id="c30bc-125">Все свойства доступны для чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="c30bc-125">All properties are read/write.</span></span>  
  
|<span data-ttu-id="c30bc-126">Имя свойства</span><span class="sxs-lookup"><span data-stu-id="c30bc-126">Property name</span></span>|<span data-ttu-id="c30bc-127">Тип данных</span><span class="sxs-lookup"><span data-stu-id="c30bc-127">Data Type</span></span>|<span data-ttu-id="c30bc-128">Description</span><span class="sxs-lookup"><span data-stu-id="c30bc-128">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="c30bc-129">RowsetID</span><span class="sxs-lookup"><span data-stu-id="c30bc-129">RowsetID</span></span>|<span data-ttu-id="c30bc-130">String</span><span class="sxs-lookup"><span data-stu-id="c30bc-130">String</span></span>|<span data-ttu-id="c30bc-131">Определяет набор строк, связанный с выходом.</span><span class="sxs-lookup"><span data-stu-id="c30bc-131">A value that identifies the rowset associated with the output.</span></span>|  
  
 <span data-ttu-id="c30bc-132">Выходные столбцы источника «XML» не имеют пользовательских свойств.</span><span class="sxs-lookup"><span data-stu-id="c30bc-132">The output columns of the XML source have no custom properties.</span></span>  
  
 <span data-ttu-id="c30bc-133">Дополнительные сведения см. в статье [XML Source](xml-source.md).</span><span class="sxs-lookup"><span data-stu-id="c30bc-133">For more information, see [XML Source](xml-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c30bc-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="c30bc-134">See Also</span></span>  
 [<span data-ttu-id="c30bc-135">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="c30bc-135">Common Properties</span></span>](../common-properties.md)  
  
  
