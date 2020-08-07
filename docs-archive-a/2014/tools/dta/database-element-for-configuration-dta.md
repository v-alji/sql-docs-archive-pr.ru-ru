---
title: Элемент Database для Configuration (DTA) | Документация Майкрософт
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
ms.assetid: e91ba243-6cc9-457a-8f5a-134f3c71ae69
author: stevestein
ms.author: sstein
ms.openlocfilehash: 69ce1a0ac9912907f6d22916dd6243621e0778db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727654"
---
# <a name="database-element-for-configuration-dta"></a><span data-ttu-id="a7169-102">Элемент Database описания конфигурации (DTA)</span><span class="sxs-lookup"><span data-stu-id="a7169-102">Database Element for Configuration (DTA)</span></span>
  <span data-ttu-id="a7169-103">Задает базу данных, в которой помощник по настройке ядра СУБД будет оценивать гипотетическую настройку (заданную элементом `Configuration`).</span><span class="sxs-lookup"><span data-stu-id="a7169-103">Specifies the database against which you want the Database Engine Tuning Advisor to evaluate the hypothetical configuration (specified by the `Configuration` element).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7169-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a7169-104">Syntax</span></span>  
  
```  
  
<Server>  
...code removed here...  
    <Database>...</Database>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="a7169-105">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="a7169-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="a7169-106">Характеристика</span><span class="sxs-lookup"><span data-stu-id="a7169-106">Characteristic</span></span>|<span data-ttu-id="a7169-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a7169-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="a7169-108">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="a7169-108">**Data type and length**</span></span>|<span data-ttu-id="a7169-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="a7169-109">None.</span></span>|  
|<span data-ttu-id="a7169-110">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="a7169-110">**Default value**</span></span>|<span data-ttu-id="a7169-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="a7169-111">None.</span></span>|  
|<span data-ttu-id="a7169-112">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="a7169-112">**Occurrence**</span></span>|<span data-ttu-id="a7169-113">Требуется один или несколько раз для каждого элемента `Server`.</span><span class="sxs-lookup"><span data-stu-id="a7169-113">Required one or more times per `Server` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="a7169-114">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="a7169-114">Element Relationships</span></span>  
  
|<span data-ttu-id="a7169-115">Связь</span><span class="sxs-lookup"><span data-stu-id="a7169-115">Relationship</span></span>|<span data-ttu-id="a7169-116">Элементы</span><span class="sxs-lookup"><span data-stu-id="a7169-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="a7169-117">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="a7169-117">**Parent element**</span></span>|[<span data-ttu-id="a7169-118">Элемент Server описания конфигурации (DTA)</span><span class="sxs-lookup"><span data-stu-id="a7169-118">Server Element for Configuration &#40;DTA&#41;</span></span>](server-element-for-configuration-dta.md)|  
|<span data-ttu-id="a7169-119">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="a7169-119">**Child elements**</span></span>|[<span data-ttu-id="a7169-120">Элемент Name для базы данных (DTA)</span><span class="sxs-lookup"><span data-stu-id="a7169-120">Name Element for Database &#40;DTA&#41;</span></span>](name-element-for-database-dta.md)<br /><br /> [<span data-ttu-id="a7169-121">Элемент Schema описания базы данных (DTA)</span><span class="sxs-lookup"><span data-stu-id="a7169-121">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)<br /><br /> [<span data-ttu-id="a7169-122">Элемент Recommendation (DTA)</span><span class="sxs-lookup"><span data-stu-id="a7169-122">Recommendation Element &#40;DTA&#41;</span></span>](recommendation-element-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="a7169-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="a7169-123">Remarks</span></span>  
 <span data-ttu-id="a7169-124">Этот элемент с именем **DatabaseTypecomplexType** определен в схеме XML помощника по настройке ядра СУБД.</span><span class="sxs-lookup"><span data-stu-id="a7169-124">This element is of the **DatabaseTypecomplexType** name in the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="a7169-125">Не путайте этот элемент `Database` с элементом, родительским корневым элементом которого является элемент `Server`, находящийся в верхней части входного XML-файла.</span><span class="sxs-lookup"><span data-stu-id="a7169-125">Do not confuse this `Database` element with the one whose root parent is the `Server` element, which occurs at the top of the XML input file.</span></span> <span data-ttu-id="a7169-126">Дополнительные сведения см. в разделе [Элемент Database описания сервера (DTA)](database-element-for-server-dta.md).</span><span class="sxs-lookup"><span data-stu-id="a7169-126">For more information, see [Database Element for Server &#40;DTA&#41;](database-element-for-server-dta.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7169-127">Пример</span><span class="sxs-lookup"><span data-stu-id="a7169-127">Example</span></span>  
 <span data-ttu-id="a7169-128">Пример использования этого `Database` элемента см. в разделе [Образец входного XML-файла с заданной пользователем конфигурацией &#40;dta&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="a7169-128">For a usage example of this `Database` element, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7169-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="a7169-129">See Also</span></span>  
 [<span data-ttu-id="a7169-130">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="a7169-130">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
