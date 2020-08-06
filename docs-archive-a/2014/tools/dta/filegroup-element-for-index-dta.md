---
title: Элемент FILEGROUP для index (DTA) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Filegroup element [DTA]
ms.assetid: 7078d2fb-fa77-44fc-beb3-c095088fcb85
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5ed8ea723d6c0798b93e16411ee47d6e956c6c22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735749"
---
# <a name="filegroup-element-for-index-dta"></a><span data-ttu-id="af277-102">Элемент Filegroup описания индекса (DTA)</span><span class="sxs-lookup"><span data-stu-id="af277-102">Filegroup Element for Index (DTA)</span></span>
  <span data-ttu-id="af277-103">Определяет группу файлов, по которой будет создан индекс в пользовательской конфигурации.</span><span class="sxs-lookup"><span data-stu-id="af277-103">Specifies the filegroup on which the index is to be created for a user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af277-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="af277-104">Syntax</span></span>  
  
```  
  
<Index>  
  <Name>...</Name>  
  <Column>  
    <Name>...</Name>  
  <Filegroup>...</Filegroup>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="af277-105">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="af277-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="af277-106">Характеристика</span><span class="sxs-lookup"><span data-stu-id="af277-106">Characteristic</span></span>|<span data-ttu-id="af277-107">Описание</span><span class="sxs-lookup"><span data-stu-id="af277-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="af277-108">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="af277-108">**Data type and length**</span></span>|<span data-ttu-id="af277-109">`string`, неограниченная длина</span><span class="sxs-lookup"><span data-stu-id="af277-109">`string`, unlimited length.</span></span>|  
|<span data-ttu-id="af277-110">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="af277-110">**Default value**</span></span>|<span data-ttu-id="af277-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="af277-111">None.</span></span>|  
|<span data-ttu-id="af277-112">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="af277-112">**Occurrence**</span></span>|<span data-ttu-id="af277-113">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="af277-113">Optional.</span></span> <span data-ttu-id="af277-114">Может использоваться один раз для каждого элемента `Index`.</span><span class="sxs-lookup"><span data-stu-id="af277-114">Can use once for each `Index` element.</span></span> <span data-ttu-id="af277-115">Этот элемент нельзя использовать, если для элемента `PartitionScheme` определены элементы `PartitionColumn` и `Index`.</span><span class="sxs-lookup"><span data-stu-id="af277-115">This element cannot be used if the `PartitionScheme` and `PartitionColumn` elements are specified for the `Index` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="af277-116">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="af277-116">Element Relationships</span></span>  
  
|<span data-ttu-id="af277-117">Связь</span><span class="sxs-lookup"><span data-stu-id="af277-117">Relationship</span></span>|<span data-ttu-id="af277-118">Элементы</span><span class="sxs-lookup"><span data-stu-id="af277-118">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="af277-119">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="af277-119">**Parent element**</span></span>|[<span data-ttu-id="af277-120">Элемент Index (DTA)</span><span class="sxs-lookup"><span data-stu-id="af277-120">Index Element &#40;DTA&#41;</span></span>](index-element-dta.md)|  
|<span data-ttu-id="af277-121">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="af277-121">**Child elements**</span></span>|<span data-ttu-id="af277-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="af277-122">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="af277-123">Пример</span><span class="sxs-lookup"><span data-stu-id="af277-123">Example</span></span>  
 <span data-ttu-id="af277-124">Пример использования этого элемента см. в разделе [Образец входного XML-файла с пользовательской конфигурацией (DTA)](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="af277-124">For a usage example of this element, see [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af277-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="af277-125">See Also</span></span>  
 [<span data-ttu-id="af277-126">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="af277-126">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
