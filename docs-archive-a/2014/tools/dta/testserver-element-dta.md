---
title: Элемент TestServer (DTA) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- TestServer element
ms.assetid: caa3547a-2cd5-47ad-ace2-a36752835cfe
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8d1f1fadf76a43caca262652254e8a778602183c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735746"
---
# <a name="testserver-element-dta"></a><span data-ttu-id="3048b-102">Элемент TestServer (DTA)</span><span class="sxs-lookup"><span data-stu-id="3048b-102">TestServer Element (DTA)</span></span>
  <span data-ttu-id="3048b-103">Указывает, какой тестовый сервер нужно использовать при настройке рабочего сервера.</span><span class="sxs-lookup"><span data-stu-id="3048b-103">Specifies the test server to use when tuning a production server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3048b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3048b-104">Syntax</span></span>  
  
```  
  
<TuningOptions>  
  <TestServer>...</TestServer>  
   ...code removed here...  
</TuningOptions>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="3048b-105">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="3048b-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="3048b-106">Характеристика</span><span class="sxs-lookup"><span data-stu-id="3048b-106">Characteristic</span></span>|<span data-ttu-id="3048b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3048b-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="3048b-108">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="3048b-108">**Data type and length**</span></span>|<span data-ttu-id="3048b-109">**string**, неограниченная длина</span><span class="sxs-lookup"><span data-stu-id="3048b-109">**string**, unlimited length.</span></span>|  
|<span data-ttu-id="3048b-110">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="3048b-110">**Default value**</span></span>|<span data-ttu-id="3048b-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="3048b-111">None.</span></span>|  
|<span data-ttu-id="3048b-112">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="3048b-112">**Occurrence**</span></span>|<span data-ttu-id="3048b-113">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="3048b-113">Optional.</span></span> <span data-ttu-id="3048b-114">Может использоваться один раз для каждого элемента `TuningOptions`.</span><span class="sxs-lookup"><span data-stu-id="3048b-114">Can use once for each `TuningOptions` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="3048b-115">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="3048b-115">Element Relationships</span></span>  
  
|<span data-ttu-id="3048b-116">Связь</span><span class="sxs-lookup"><span data-stu-id="3048b-116">Relationship</span></span>|<span data-ttu-id="3048b-117">Элементы</span><span class="sxs-lookup"><span data-stu-id="3048b-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="3048b-118">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="3048b-118">**Parent element**</span></span>|[<span data-ttu-id="3048b-119">Элемент TuningOptions (DTA)</span><span class="sxs-lookup"><span data-stu-id="3048b-119">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="3048b-120">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="3048b-120">**Child elements**</span></span>|<span data-ttu-id="3048b-121">Нет.</span><span class="sxs-lookup"><span data-stu-id="3048b-121">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3048b-122">Пример</span><span class="sxs-lookup"><span data-stu-id="3048b-122">Example</span></span>  
 <span data-ttu-id="3048b-123">Пример использования этого элемента см. в разделе [Уменьшение настроечной загрузки рабочего сервера](../../relational-databases/performance/reduce-the-production-server-tuning-load.md).</span><span class="sxs-lookup"><span data-stu-id="3048b-123">For a usage example of this element, see [Reduce the Production Server Tuning Load](../../relational-databases/performance/reduce-the-production-server-tuning-load.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3048b-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="3048b-124">See Also</span></span>  
 [<span data-ttu-id="3048b-125">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="3048b-125">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
