---
title: Элемент Schema для Database (DTA) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Schema element
ms.assetid: d932e59c-953f-4ab4-934d-b6baf344835c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7653177878f3a832abd2d1ca266bc5feb17b9a29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656126"
---
# <a name="schema-element-for-database-dta"></a><span data-ttu-id="7e5de-102">Элемент Schema описания базы данных (DTA)</span><span class="sxs-lookup"><span data-stu-id="7e5de-102">Schema Element for Database (DTA)</span></span>
  <span data-ttu-id="7e5de-103">Указывает схему базы данных, которую необходимо настроить.</span><span class="sxs-lookup"><span data-stu-id="7e5de-103">Specifies the schema of the database that you want to tune.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e5de-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e5de-104">Syntax</span></span>  
  
```  
  
<Database>  
...code removed here...  
    <Schema>...</Schema>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="7e5de-105">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="7e5de-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="7e5de-106">Характеристика</span><span class="sxs-lookup"><span data-stu-id="7e5de-106">Characteristic</span></span>|<span data-ttu-id="7e5de-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7e5de-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="7e5de-108">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="7e5de-108">**Data type and length**</span></span>|<span data-ttu-id="7e5de-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="7e5de-109">None.</span></span>|  
|<span data-ttu-id="7e5de-110">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="7e5de-110">**Default value**</span></span>|<span data-ttu-id="7e5de-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="7e5de-111">None.</span></span>|  
|<span data-ttu-id="7e5de-112">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="7e5de-112">**Occurrence**</span></span>|<span data-ttu-id="7e5de-113">Требуется один раз для элемента **Database** , указанного в элементе **Server** .</span><span class="sxs-lookup"><span data-stu-id="7e5de-113">Required once for the **Database** element that is specified under the **Server** element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="7e5de-114">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="7e5de-114">Element Relationships</span></span>  
  
|<span data-ttu-id="7e5de-115">Связь</span><span class="sxs-lookup"><span data-stu-id="7e5de-115">Relationship</span></span>|<span data-ttu-id="7e5de-116">Элементы</span><span class="sxs-lookup"><span data-stu-id="7e5de-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="7e5de-117">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="7e5de-117">**Parent element**</span></span>|[<span data-ttu-id="7e5de-118">Элемент Database описания сервера (DTA)</span><span class="sxs-lookup"><span data-stu-id="7e5de-118">Database Element for Server &#40;DTA&#41;</span></span>](database-element-for-server-dta.md)|  
|<span data-ttu-id="7e5de-119">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="7e5de-119">**Child elements**</span></span>|[<span data-ttu-id="7e5de-120">Элемент Name для схемы (DTA)</span><span class="sxs-lookup"><span data-stu-id="7e5de-120">Name Element for Schema &#40;DTA&#41;</span></span>](name-element-for-schema-dta.md)<br /><br /> [<span data-ttu-id="7e5de-121">Элемент Table для схемы (DTA)</span><span class="sxs-lookup"><span data-stu-id="7e5de-121">Table Element for Schema &#40;DTA&#41;</span></span>](table-element-for-schema-dta.md)|  
  
## <a name="example"></a><span data-ttu-id="7e5de-122">Пример</span><span class="sxs-lookup"><span data-stu-id="7e5de-122">Example</span></span>  
 <span data-ttu-id="7e5de-123">Пример использования этого элемента см. в разделе [Элемент Server (DTA)](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="7e5de-123">For a usage example of this element, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e5de-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="7e5de-124">See Also</span></span>  
 [<span data-ttu-id="7e5de-125">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="7e5de-125">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
