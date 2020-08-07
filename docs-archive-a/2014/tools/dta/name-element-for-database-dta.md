---
title: Элемент Name для Database (DTA) | Документация Майкрософт
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
ms.assetid: e871c4fa-3b57-46cf-b4f8-e3be86f92dc4
author: stevestein
ms.author: sstein
ms.openlocfilehash: c692e31b9175bf05dcfb0504ea79e98cbb82f36b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727618"
---
# <a name="name-element-for-database-dta"></a><span data-ttu-id="b28c2-102">Элемент Name описания базы данных (DTA)</span><span class="sxs-lookup"><span data-stu-id="b28c2-102">Name Element for Database (DTA)</span></span>
  <span data-ttu-id="b28c2-103">Задает имя базы данных, подлежащей настройке.</span><span class="sxs-lookup"><span data-stu-id="b28c2-103">Specifies the name of a database that you want to tune.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b28c2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b28c2-104">Syntax</span></span>  
  
```  
  
<Server>  
    <Database>  
        <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="b28c2-105">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="b28c2-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="b28c2-106">Характеристика</span><span class="sxs-lookup"><span data-stu-id="b28c2-106">Characteristic</span></span>|<span data-ttu-id="b28c2-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b28c2-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="b28c2-108">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="b28c2-108">**Data type and length**</span></span>|<span data-ttu-id="b28c2-109">`string`, неограниченная длина</span><span class="sxs-lookup"><span data-stu-id="b28c2-109">`string`, unlimited length.</span></span>|  
|<span data-ttu-id="b28c2-110">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="b28c2-110">**Default value**</span></span>|<span data-ttu-id="b28c2-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="b28c2-111">None.</span></span>|  
|<span data-ttu-id="b28c2-112">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="b28c2-112">**Occurrence**</span></span>|<span data-ttu-id="b28c2-113">Требуется один раз на каждый элемент `Database`.</span><span class="sxs-lookup"><span data-stu-id="b28c2-113">Required once per `Database` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="b28c2-114">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="b28c2-114">Element Relationships</span></span>  
  
|<span data-ttu-id="b28c2-115">Связь</span><span class="sxs-lookup"><span data-stu-id="b28c2-115">Relationship</span></span>|<span data-ttu-id="b28c2-116">Элементы</span><span class="sxs-lookup"><span data-stu-id="b28c2-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="b28c2-117">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="b28c2-117">**Parent element**</span></span>|[<span data-ttu-id="b28c2-118">Элемент Database описания сервера (DTA)</span><span class="sxs-lookup"><span data-stu-id="b28c2-118">Database Element for Server &#40;DTA&#41;</span></span>](database-element-for-server-dta.md)|  
|<span data-ttu-id="b28c2-119">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="b28c2-119">**Child elements**</span></span>|<span data-ttu-id="b28c2-120">Нет.</span><span class="sxs-lookup"><span data-stu-id="b28c2-120">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b28c2-121">Пример</span><span class="sxs-lookup"><span data-stu-id="b28c2-121">Example</span></span>  
 <span data-ttu-id="b28c2-122">Пример использования этого элемента см. в разделе [Элемент Server (DTA)](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="b28c2-122">For a usage example of this element, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b28c2-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="b28c2-123">See Also</span></span>  
 [<span data-ttu-id="b28c2-124">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="b28c2-124">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
