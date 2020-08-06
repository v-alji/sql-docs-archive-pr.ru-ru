---
title: Элемент Name для Server (DTA) | Документация Майкрософт
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
ms.assetid: 4c94754d-6d62-4357-8ce7-f107ebf90c71
author: stevestein
ms.author: sstein
ms.openlocfilehash: 202258c3c87f8a35d1ee30b19880f5e9423fa394
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666320"
---
# <a name="name-element-for-server-dta"></a><span data-ttu-id="d372f-102">Элемент Name описания сервера (DTA)</span><span class="sxs-lookup"><span data-stu-id="d372f-102">Name Element for Server (DTA)</span></span>
  <span data-ttu-id="d372f-103">Содержит имя сервера, на котором расположены базы данных, подлежащие настройке.</span><span class="sxs-lookup"><span data-stu-id="d372f-103">Contains the name of the server where the databases you want to tune reside.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d372f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d372f-104">Syntax</span></span>  
  
```  
  
...code removed here...  
<Server>  
    <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="d372f-105">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="d372f-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="d372f-106">Характеристика</span><span class="sxs-lookup"><span data-stu-id="d372f-106">Characteristic</span></span>|<span data-ttu-id="d372f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d372f-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="d372f-108">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="d372f-108">**Data type and length**</span></span>|<span data-ttu-id="d372f-109">`string`, от 1 до 255 символов</span><span class="sxs-lookup"><span data-stu-id="d372f-109">`string`, between 1 and 255 characters.</span></span>|  
|<span data-ttu-id="d372f-110">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="d372f-110">**Default value**</span></span>|<span data-ttu-id="d372f-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="d372f-111">None.</span></span>|  
|<span data-ttu-id="d372f-112">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="d372f-112">**Occurrence**</span></span>|<span data-ttu-id="d372f-113">Требуется один раз для каждого элемента **Server** .</span><span class="sxs-lookup"><span data-stu-id="d372f-113">Required once per **Server** element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="d372f-114">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="d372f-114">Element Relationships</span></span>  
  
|<span data-ttu-id="d372f-115">Связь</span><span class="sxs-lookup"><span data-stu-id="d372f-115">Relationship</span></span>|<span data-ttu-id="d372f-116">Элементы</span><span class="sxs-lookup"><span data-stu-id="d372f-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="d372f-117">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="d372f-117">**Parent element**</span></span>|[<span data-ttu-id="d372f-118">Элемент Server (DTA)</span><span class="sxs-lookup"><span data-stu-id="d372f-118">Server Element &#40;DTA&#41;</span></span>](server-element-dta.md)|  
|<span data-ttu-id="d372f-119">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="d372f-119">**Child elements**</span></span>|<span data-ttu-id="d372f-120">Нет.</span><span class="sxs-lookup"><span data-stu-id="d372f-120">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d372f-121">Пример</span><span class="sxs-lookup"><span data-stu-id="d372f-121">Example</span></span>  
 <span data-ttu-id="d372f-122">Пример использования этого элемента **Name** см. в статье [Элемент Server (DTA)](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="d372f-122">For an example of how this **Name** element is used, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d372f-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="d372f-123">See Also</span></span>  
 [<span data-ttu-id="d372f-124">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="d372f-124">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
