---
title: Элемент Server для Configuration (DTA) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Server element
ms.assetid: da9ff870-9cfd-42fe-994b-7b9292681f7d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 88182cdad2e7313f0910a106ee37d727d840bfed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666309"
---
# <a name="server-element-for-configuration-dta"></a><span data-ttu-id="e8eba-102">Элемент Server описания конфигурации (DTA)</span><span class="sxs-lookup"><span data-stu-id="e8eba-102">Server Element for Configuration (DTA)</span></span>
  <span data-ttu-id="e8eba-103">Содержит сведения идентификации сервера, на котором помощник по настройке ядра СУБД должен произвести оценку гипотетической конфигурации (заданной элементом `Configuration`).</span><span class="sxs-lookup"><span data-stu-id="e8eba-103">Contains the identifying information for the server where you want Database Engine Tuning Advisor to evaluate the hypothetical configuration (specified by the `Configuration` element).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8eba-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e8eba-104">Syntax</span></span>  
  
```  
  
<Configuration>  
    <Server>  
...code removed here...  
    </Server>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="e8eba-105">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="e8eba-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="e8eba-106">Характеристика</span><span class="sxs-lookup"><span data-stu-id="e8eba-106">Characteristic</span></span>|<span data-ttu-id="e8eba-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e8eba-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="e8eba-108">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="e8eba-108">**Data type and length**</span></span>|<span data-ttu-id="e8eba-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="e8eba-109">None.</span></span>|  
|<span data-ttu-id="e8eba-110">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="e8eba-110">**Default value**</span></span>|<span data-ttu-id="e8eba-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="e8eba-111">None.</span></span>|  
|<span data-ttu-id="e8eba-112">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="e8eba-112">**Occurrence**</span></span>|<span data-ttu-id="e8eba-113">Требуется один раз на каждый элемент `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="e8eba-113">Required once per `Configuration` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="e8eba-114">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="e8eba-114">Element Relationships</span></span>  
  
|<span data-ttu-id="e8eba-115">Связь</span><span class="sxs-lookup"><span data-stu-id="e8eba-115">Relationship</span></span>|<span data-ttu-id="e8eba-116">Элементы</span><span class="sxs-lookup"><span data-stu-id="e8eba-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="e8eba-117">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="e8eba-117">**Parent element**</span></span>|[<span data-ttu-id="e8eba-118">Элемент Configuration (DTA)</span><span class="sxs-lookup"><span data-stu-id="e8eba-118">Configuration Element &#40;DTA&#41;</span></span>](configuration-element-dta.md)|  
|<span data-ttu-id="e8eba-119">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="e8eba-119">**Child elements**</span></span>|[<span data-ttu-id="e8eba-120">Элемент Name описания сервера (DTA)</span><span class="sxs-lookup"><span data-stu-id="e8eba-120">Name Element for Server &#40;DTA&#41;</span></span>](name-element-for-server-dta.md)<br /><br /> [<span data-ttu-id="e8eba-121">Элемент Database описания конфигурации (DTA)</span><span class="sxs-lookup"><span data-stu-id="e8eba-121">Database Element for Configuration &#40;DTA&#41;</span></span>](database-element-for-configuration-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="e8eba-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="e8eba-122">Remarks</span></span>  
 <span data-ttu-id="e8eba-123">Для элемента можно указать только один `Server` элемент `Configuration` .</span><span class="sxs-lookup"><span data-stu-id="e8eba-123">You can specify only one `Server` element for the `Configuration` element.</span></span> <span data-ttu-id="e8eba-124">Этот элемент с именем **ServerTypecomplexType** определен в [схеме XML помощника по настройке ядра СУБД](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="e8eba-124">This element is of the **ServerTypecomplexType** name in the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span> <span data-ttu-id="e8eba-125">Не следует путать данный элемент `Server` с дочерним элементом элемента `DTAInput`.</span><span class="sxs-lookup"><span data-stu-id="e8eba-125">Do not confuse this `Server` element with the one that is the child of the `DTAInput` element.</span></span> <span data-ttu-id="e8eba-126">Дополнительные сведения см. в разделе [Элемент Server (DTA)](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="e8eba-126">For more information, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8eba-127">Пример</span><span class="sxs-lookup"><span data-stu-id="e8eba-127">Example</span></span>  
 <span data-ttu-id="e8eba-128">Пример использования см. в разделе [Образец входного XML-файла с пользовательской конфигурацией (DTA)](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="e8eba-128">For a usage example, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8eba-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="e8eba-129">See Also</span></span>  
 [<span data-ttu-id="e8eba-130">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="e8eba-130">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
