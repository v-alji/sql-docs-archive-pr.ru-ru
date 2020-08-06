---
title: Элемент Name для index (DTA) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Name element
ms.assetid: 2300e9cf-f0a8-49e6-b1f5-45ffe03ccb5f
author: stevestein
ms.author: sstein
ms.openlocfilehash: a878923a3d483fae5ad6b55421a2b286f15ceb29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740610"
---
# <a name="name-element-for-index-dta"></a><span data-ttu-id="d60a0-102">Элемент Name описания индекса (DTA)</span><span class="sxs-lookup"><span data-stu-id="d60a0-102">Name Element for Index (DTA)</span></span>
  <span data-ttu-id="d60a0-103">Указывает имя индекса в определенной пользователем конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d60a0-103">Specifies a name for an index in the user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d60a0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d60a0-104">Syntax</span></span>  
  
```  
  
<Create>  
    <Index>  
        <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="d60a0-105">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="d60a0-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="d60a0-106">Характеристика</span><span class="sxs-lookup"><span data-stu-id="d60a0-106">Characteristic</span></span>|<span data-ttu-id="d60a0-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d60a0-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="d60a0-108">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="d60a0-108">**Data type and length**</span></span>|<span data-ttu-id="d60a0-109">`string`, неограниченная длина</span><span class="sxs-lookup"><span data-stu-id="d60a0-109">`string`, unlimited length.</span></span>|  
|<span data-ttu-id="d60a0-110">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="d60a0-110">**Default value**</span></span>|<span data-ttu-id="d60a0-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="d60a0-111">None.</span></span>|  
|<span data-ttu-id="d60a0-112">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="d60a0-112">**Occurrence**</span></span>|<span data-ttu-id="d60a0-113">Требуется один раз для каждого элемента `Index`.</span><span class="sxs-lookup"><span data-stu-id="d60a0-113">Required once for each `Index` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="d60a0-114">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="d60a0-114">Element Relationships</span></span>  
  
|<span data-ttu-id="d60a0-115">Связь</span><span class="sxs-lookup"><span data-stu-id="d60a0-115">Relationship</span></span>|<span data-ttu-id="d60a0-116">Элементы</span><span class="sxs-lookup"><span data-stu-id="d60a0-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="d60a0-117">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="d60a0-117">**Parent element**</span></span>|[<span data-ttu-id="d60a0-118">Элемент Index (DTA)</span><span class="sxs-lookup"><span data-stu-id="d60a0-118">Index Element &#40;DTA&#41;</span></span>](index-element-dta.md)|  
|<span data-ttu-id="d60a0-119">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="d60a0-119">**Child elements**</span></span>|<span data-ttu-id="d60a0-120">Нет.</span><span class="sxs-lookup"><span data-stu-id="d60a0-120">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d60a0-121">Пример</span><span class="sxs-lookup"><span data-stu-id="d60a0-121">Example</span></span>  
 <span data-ttu-id="d60a0-122">Пример использования этого элемента см. в разделе [Образец входного XML-файла с пользовательской конфигурацией (DTA)](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="d60a0-122">For a usage example of this element, see [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d60a0-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="d60a0-123">See Also</span></span>  
 [<span data-ttu-id="d60a0-124">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="d60a0-124">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
