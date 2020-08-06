---
title: Элемент Name для Column (DTA) | Документация Майкрософт
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
ms.assetid: f93b61de-01fe-4237-ada4-f1e481550564
author: stevestein
ms.author: sstein
ms.openlocfilehash: fad3d9a86a7c5db6b6a7503dc90b5a1540e3618b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727630"
---
# <a name="name-element-for-column-dta"></a><span data-ttu-id="48135-102">Элемент Name описания столбца (DTA)</span><span class="sxs-lookup"><span data-stu-id="48135-102">Name Element for Column (DTA)</span></span>
  <span data-ttu-id="48135-103">Задает имя для столбца индекса в пользовательской конфигурации.</span><span class="sxs-lookup"><span data-stu-id="48135-103">Specifies the name for an index column in a user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48135-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="48135-104">Syntax</span></span>  
  
```  
  
<Index>  
    <Column>  
        <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="48135-105">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="48135-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="48135-106">Характеристика</span><span class="sxs-lookup"><span data-stu-id="48135-106">Characteristic</span></span>|<span data-ttu-id="48135-107">Описание</span><span class="sxs-lookup"><span data-stu-id="48135-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="48135-108">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="48135-108">**Data type and length**</span></span>|<span data-ttu-id="48135-109">`string`, неограниченная длина</span><span class="sxs-lookup"><span data-stu-id="48135-109">`string`, unlimited length.</span></span>|  
|<span data-ttu-id="48135-110">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="48135-110">**Default value**</span></span>|<span data-ttu-id="48135-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="48135-111">None.</span></span>|  
|<span data-ttu-id="48135-112">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="48135-112">**Occurrence**</span></span>|<span data-ttu-id="48135-113">Требуется один раз для каждого элемента `Column`.</span><span class="sxs-lookup"><span data-stu-id="48135-113">Required once for each `Column` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="48135-114">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="48135-114">Element Relationships</span></span>  
  
|<span data-ttu-id="48135-115">Связь</span><span class="sxs-lookup"><span data-stu-id="48135-115">Relationship</span></span>|<span data-ttu-id="48135-116">Элементы</span><span class="sxs-lookup"><span data-stu-id="48135-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="48135-117">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="48135-117">**Parent element**</span></span>|[<span data-ttu-id="48135-118">Элемент Column описания индекса (DTA)</span><span class="sxs-lookup"><span data-stu-id="48135-118">Column Element for Index &#40;DTA&#41;</span></span>](column-element-for-index-dta.md)|  
|<span data-ttu-id="48135-119">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="48135-119">**Child elements**</span></span>|<span data-ttu-id="48135-120">Нет.</span><span class="sxs-lookup"><span data-stu-id="48135-120">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="48135-121">Пример</span><span class="sxs-lookup"><span data-stu-id="48135-121">Example</span></span>  
 <span data-ttu-id="48135-122">Пример использования этого элемента см. в разделе [Образец входного XML-файла с пользовательской конфигурацией (DTA)](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="48135-122">For a usage example of this element, see [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48135-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="48135-123">See Also</span></span>  
 [<span data-ttu-id="48135-124">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="48135-124">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
