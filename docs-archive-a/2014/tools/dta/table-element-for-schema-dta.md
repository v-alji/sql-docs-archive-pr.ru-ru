---
title: Элемент Table для Schema (DTA) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Table element [DTA]
ms.assetid: a59e8319-05d1-47f3-af39-7d970ab8e7dc
author: stevestein
ms.author: sstein
ms.openlocfilehash: dd444b1da99b22e0259dc1f50818c1763b7052ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735745"
---
# <a name="table-element-for-schema-dta"></a><span data-ttu-id="f1d38-102">Элемент Table описания схемы (DTA)</span><span class="sxs-lookup"><span data-stu-id="f1d38-102">Table Element for Schema (DTA)</span></span>
  <span data-ttu-id="f1d38-103">Указывает таблицу для настройки.</span><span class="sxs-lookup"><span data-stu-id="f1d38-103">Specifies the table for tuning.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1d38-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f1d38-104">Syntax</span></span>  
  
```  
  
<Schema>  
...code removed here...  
    <Table>...</Table>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="f1d38-105">Атрибуты элемента</span><span class="sxs-lookup"><span data-stu-id="f1d38-105">Element Attributes</span></span>  
  
|<span data-ttu-id="f1d38-106">attribute</span><span class="sxs-lookup"><span data-stu-id="f1d38-106">Attribute</span></span>|<span data-ttu-id="f1d38-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f1d38-107">Description</span></span>|  
|---------------|-----------------|  
|`NumberOfRows`|<span data-ttu-id="f1d38-108">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="f1d38-108">Optional.</span></span> <span data-ttu-id="f1d38-109">Целое число, позволяющее имитировать таблицы различных размеров.</span><span class="sxs-lookup"><span data-stu-id="f1d38-109">Integer that allows you to simulate tables of different sizes.</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="f1d38-110">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="f1d38-110">Element Characteristics</span></span>  
  
|<span data-ttu-id="f1d38-111">Характеристика</span><span class="sxs-lookup"><span data-stu-id="f1d38-111">Characteristic</span></span>|<span data-ttu-id="f1d38-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f1d38-112">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="f1d38-113">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="f1d38-113">**Data type and length**</span></span>|<span data-ttu-id="f1d38-114">**string**, от 1 до 255 символов</span><span class="sxs-lookup"><span data-stu-id="f1d38-114">**string**, between 1 and 255 characters.</span></span>|  
|<span data-ttu-id="f1d38-115">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="f1d38-115">**Default value**</span></span>|<span data-ttu-id="f1d38-116">Нет.</span><span class="sxs-lookup"><span data-stu-id="f1d38-116">None.</span></span>|  
|<span data-ttu-id="f1d38-117">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="f1d38-117">**Occurrence**</span></span>|<span data-ttu-id="f1d38-118">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="f1d38-118">Optional.</span></span> <span data-ttu-id="f1d38-119">Перечисляет необходимое число таблиц для рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="f1d38-119">List as many tables as appropriate for your workload.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="f1d38-120">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="f1d38-120">Element Relationships</span></span>  
  
|<span data-ttu-id="f1d38-121">Связь</span><span class="sxs-lookup"><span data-stu-id="f1d38-121">Relationship</span></span>|<span data-ttu-id="f1d38-122">Элементы</span><span class="sxs-lookup"><span data-stu-id="f1d38-122">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="f1d38-123">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="f1d38-123">**Parent element**</span></span>|[<span data-ttu-id="f1d38-124">Элемент Schema описания базы данных (DTA)</span><span class="sxs-lookup"><span data-stu-id="f1d38-124">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)|  
|<span data-ttu-id="f1d38-125">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="f1d38-125">**Child elements**</span></span>|[<span data-ttu-id="f1d38-126">Элемент Name описания таблицы (DTA)</span><span class="sxs-lookup"><span data-stu-id="f1d38-126">Name Element for Table &#40;DTA&#41;</span></span>](name-element-for-table-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="f1d38-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="f1d38-127">Remarks</span></span>  
 <span data-ttu-id="f1d38-128">Если элемент `Table` не указан, помощник по настройке ядра СУБД считает все таблицы в указанной базе данных доступными для настройки.</span><span class="sxs-lookup"><span data-stu-id="f1d38-128">If you do not specify a `Table` element, Database Engine Tuning Advisor will assume all tables on the specified database can be tuned.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1d38-129">Пример</span><span class="sxs-lookup"><span data-stu-id="f1d38-129">Example</span></span>  
 <span data-ttu-id="f1d38-130">Пример использования см. в разделе [Элемент Server (DTA)](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="f1d38-130">For a usage example, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1d38-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="f1d38-131">See Also</span></span>  
 [<span data-ttu-id="f1d38-132">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="f1d38-132">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
