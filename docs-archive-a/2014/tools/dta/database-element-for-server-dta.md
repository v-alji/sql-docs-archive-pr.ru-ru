---
title: Элемент Database для сервера (DTA) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Database element
ms.assetid: 5cd9a87a-af4b-45f3-8c18-f7fd7e7d3064
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9a48d255898eff6bd780f8edf2c8d2da7229b0ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727653"
---
# <a name="database-element-for-server-dta"></a><span data-ttu-id="7aa05-102">Элемент Database описания сервера (DTA)</span><span class="sxs-lookup"><span data-stu-id="7aa05-102">Database Element for Server (DTA)</span></span>
  <span data-ttu-id="7aa05-103">Позволяет задать базу данных, которую необходимо настроить на конкретном сервере.</span><span class="sxs-lookup"><span data-stu-id="7aa05-103">Specifies the database you want to tune on a specific server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7aa05-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7aa05-104">Syntax</span></span>  
  
```  
  
<Server>  
...code removed here...  
    <Database>...</Database>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="7aa05-105">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="7aa05-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="7aa05-106">Характеристика</span><span class="sxs-lookup"><span data-stu-id="7aa05-106">Characteristic</span></span>|<span data-ttu-id="7aa05-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7aa05-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="7aa05-108">Тип данных и длина</span><span class="sxs-lookup"><span data-stu-id="7aa05-108">Data type and length</span></span>|<span data-ttu-id="7aa05-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="7aa05-109">None.</span></span>|  
|<span data-ttu-id="7aa05-110">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="7aa05-110">Default value</span></span>|<span data-ttu-id="7aa05-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="7aa05-111">None.</span></span>|  
|<span data-ttu-id="7aa05-112">Наличие</span><span class="sxs-lookup"><span data-stu-id="7aa05-112">Occurrence</span></span>|<span data-ttu-id="7aa05-113">Требуется один или несколько раз для каждого элемента `Server`.</span><span class="sxs-lookup"><span data-stu-id="7aa05-113">Required one or more times per `Server` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="7aa05-114">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="7aa05-114">Element Relationships</span></span>  
  
|<span data-ttu-id="7aa05-115">Связь</span><span class="sxs-lookup"><span data-stu-id="7aa05-115">Relationship</span></span>|<span data-ttu-id="7aa05-116">Элементы</span><span class="sxs-lookup"><span data-stu-id="7aa05-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="7aa05-117">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="7aa05-117">Parent element</span></span>|[<span data-ttu-id="7aa05-118">Элемент Server (DTA)</span><span class="sxs-lookup"><span data-stu-id="7aa05-118">Server Element &#40;DTA&#41;</span></span>](server-element-dta.md)|  
|<span data-ttu-id="7aa05-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7aa05-119">Child elements</span></span>|[<span data-ttu-id="7aa05-120">Элемент Name для базы данных (DTA)</span><span class="sxs-lookup"><span data-stu-id="7aa05-120">Name Element for Database &#40;DTA&#41;</span></span>](name-element-for-database-dta.md)<br /><br /> [<span data-ttu-id="7aa05-121">Элемент Schema описания базы данных (DTA)</span><span class="sxs-lookup"><span data-stu-id="7aa05-121">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="7aa05-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="7aa05-122">Remarks</span></span>  
 <span data-ttu-id="7aa05-123">Этот элемент с именем **DatabaseDetailsTypecomplexType** определен в схеме XML помощника по настройке ядра СУБД.</span><span class="sxs-lookup"><span data-stu-id="7aa05-123">This element is of the **DatabaseDetailsTypecomplexType** name in the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="7aa05-124">Не путайте этот элемент `Database` с элементом, корневым родительским элементом которого является `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="7aa05-124">Do not confuse this `Database` element with the one whose root parent is the `Configuration` element.</span></span> <span data-ttu-id="7aa05-125">Дополнительные сведения см. в разделе [Элемент Database для конфигурации (DTA)](database-element-for-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="7aa05-125">For more information, see [Database Element for Configuration &#40;DTA&#41;](database-element-for-configuration-dta.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7aa05-126">Пример</span><span class="sxs-lookup"><span data-stu-id="7aa05-126">Example</span></span>  
 <span data-ttu-id="7aa05-127">Пример использования `Database` элемента см. в разделе [Server Element &#40;dta&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="7aa05-127">For a usage example of the `Database` element, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aa05-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="7aa05-128">See Also</span></span>  
 [<span data-ttu-id="7aa05-129">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="7aa05-129">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
