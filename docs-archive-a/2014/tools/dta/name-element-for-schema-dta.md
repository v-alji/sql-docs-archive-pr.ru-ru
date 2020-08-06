---
title: Элемент Name для Schema (DTA) | Документация Майкрософт
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
ms.assetid: 014e4854-fed2-454b-8557-5f7c5bb6b17a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 678a6d58b35b25be2aed6d91fcae7ceb2640bdcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734766"
---
# <a name="name-element-for-schema-dta"></a><span data-ttu-id="fd384-102">Элемент Name описания схемы (DTA)</span><span class="sxs-lookup"><span data-stu-id="fd384-102">Name Element for Schema (DTA)</span></span>
  <span data-ttu-id="fd384-103">Содержит имя схемы.</span><span class="sxs-lookup"><span data-stu-id="fd384-103">Contains name of the schema.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd384-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fd384-104">Syntax</span></span>  
  
```  
  
<Database>  
...code removed here  
    <Schema>  
        <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="fd384-105">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="fd384-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="fd384-106">Характеристика</span><span class="sxs-lookup"><span data-stu-id="fd384-106">Characteristic</span></span>|<span data-ttu-id="fd384-107">Описание</span><span class="sxs-lookup"><span data-stu-id="fd384-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="fd384-108">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="fd384-108">**Data type and length**</span></span>|<span data-ttu-id="fd384-109">`string` от 1 до 255 символов</span><span class="sxs-lookup"><span data-stu-id="fd384-109">`string`, between 1 and 255 characters</span></span>|  
|<span data-ttu-id="fd384-110">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="fd384-110">**Default value**</span></span>|<span data-ttu-id="fd384-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="fd384-111">None.</span></span>|  
|<span data-ttu-id="fd384-112">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="fd384-112">**Occurrence**</span></span>|<span data-ttu-id="fd384-113">Обязательно одно вхождение на каждый элемент **Schema**</span><span class="sxs-lookup"><span data-stu-id="fd384-113">Required once per **Schema** element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="fd384-114">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="fd384-114">Element Relationships</span></span>  
  
|<span data-ttu-id="fd384-115">Связь</span><span class="sxs-lookup"><span data-stu-id="fd384-115">Relationship</span></span>|<span data-ttu-id="fd384-116">Элементы</span><span class="sxs-lookup"><span data-stu-id="fd384-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="fd384-117">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="fd384-117">**Parent element**</span></span>|[<span data-ttu-id="fd384-118">Элемент Schema описания базы данных (DTA)</span><span class="sxs-lookup"><span data-stu-id="fd384-118">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)|  
|<span data-ttu-id="fd384-119">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="fd384-119">**Child elements**</span></span>|<span data-ttu-id="fd384-120">Нет.</span><span class="sxs-lookup"><span data-stu-id="fd384-120">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fd384-121">Пример</span><span class="sxs-lookup"><span data-stu-id="fd384-121">Example</span></span>  
 <span data-ttu-id="fd384-122">Пример использования этого элемента см. в разделе [Элемент Server (DTA)](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="fd384-122">For a usage example of this element, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd384-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="fd384-123">See Also</span></span>  
 [<span data-ttu-id="fd384-124">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="fd384-124">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
