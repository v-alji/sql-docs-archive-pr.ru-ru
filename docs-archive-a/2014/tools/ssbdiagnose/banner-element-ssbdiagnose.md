---
title: Элемент Banner (ssbdiagnose) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- banner element
- XML output file format [ssbdiagnose], banner element
- ssbdiagnose
ms.assetid: cc6cd49a-acf0-4cfb-8c6a-554692b89de2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 13238ac4ef1745dea4fbf3392484ac6137c09df1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751623"
---
# <a name="banner-element-ssbdiagnose"></a><span data-ttu-id="4ca48-102">Элемент Banner (программа ssbdiagnose)</span><span class="sxs-lookup"><span data-stu-id="4ca48-102">Banner Element (ssbdiagnose)</span></span>
  <span data-ttu-id="4ca48-103">Определяет программу, сформировавшую выходной XML-файл **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="4ca48-103">Identifies which utility generated the **ssbdiagnose** output XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ca48-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4ca48-104">Syntax</span></span>  
  
```  
  
<Banner  
    title="..."   
    product="..."   
    version="..." />  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="4ca48-105">Атрибуты элемента</span><span class="sxs-lookup"><span data-stu-id="4ca48-105">Element Attributes</span></span>  
  
|<span data-ttu-id="4ca48-106">attribute</span><span class="sxs-lookup"><span data-stu-id="4ca48-106">Attribute</span></span>|<span data-ttu-id="4ca48-107">Description</span><span class="sxs-lookup"><span data-stu-id="4ca48-107">Description</span></span>|  
|---------------|-----------------|  
|`title`|<span data-ttu-id="4ca48-108">Определяет программу, сформировавшую выходной XML-файл **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="4ca48-108">Identifies the utility that generated the **ssbdiagnose** XML output file.</span></span>|  
|`product`|<span data-ttu-id="4ca48-109">Определяет продукт, сформировавший выходной XML-файл **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="4ca48-109">Identifies the product that generated the **ssbdiagnose** XML output file.</span></span>|  
|`version`|<span data-ttu-id="4ca48-110">Определяет версию программы, которой был сформирован выходной XML-файл.</span><span class="sxs-lookup"><span data-stu-id="4ca48-110">Identifies which version of the utility generated the XML output file.</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="4ca48-111">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="4ca48-111">Element Characteristics</span></span>  
  
|<span data-ttu-id="4ca48-112">Характеристика</span><span class="sxs-lookup"><span data-stu-id="4ca48-112">Characteristic</span></span>|<span data-ttu-id="4ca48-113">Описание</span><span class="sxs-lookup"><span data-stu-id="4ca48-113">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="4ca48-114">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="4ca48-114">**Data type and length**</span></span>|<span data-ttu-id="4ca48-115">Нет.</span><span class="sxs-lookup"><span data-stu-id="4ca48-115">None.</span></span>|  
|<span data-ttu-id="4ca48-116">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="4ca48-116">**Default value**</span></span>|<span data-ttu-id="4ca48-117">Нет.</span><span class="sxs-lookup"><span data-stu-id="4ca48-117">None.</span></span>|  
|<span data-ttu-id="4ca48-118">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="4ca48-118">**Occurrence**</span></span>|<span data-ttu-id="4ca48-119">Один раз в каждом выходном XML-файле программы **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="4ca48-119">Occurs once per **ssbdiagnose** output XML file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="4ca48-120">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="4ca48-120">Element Relationships</span></span>  
  
|<span data-ttu-id="4ca48-121">Связь</span><span class="sxs-lookup"><span data-stu-id="4ca48-121">Relationship</span></span>|<span data-ttu-id="4ca48-122">Элементы</span><span class="sxs-lookup"><span data-stu-id="4ca48-122">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="4ca48-123">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="4ca48-123">**Parent element**</span></span>|[<span data-ttu-id="4ca48-124">Элемент DiagnosticInformation (программа ssbdiagnose)</span><span class="sxs-lookup"><span data-stu-id="4ca48-124">DiagnosticInformation Element &#40;ssbdiagnose&#41;</span></span>](diagnosticinformation-element-ssbdiagnose.md)|  
|<span data-ttu-id="4ca48-125">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="4ca48-125">**Child elements**</span></span>|<span data-ttu-id="4ca48-126">Нет.</span><span class="sxs-lookup"><span data-stu-id="4ca48-126">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4ca48-127">Пример</span><span class="sxs-lookup"><span data-stu-id="4ca48-127">Example</span></span>  
 <span data-ttu-id="4ca48-128">Ниже приведен пример элемента Banner.</span><span class="sxs-lookup"><span data-stu-id="4ca48-128">This is an example of a banner element.</span></span>  
  
```  
<Banner title="Service Broker Diagnostics Utility" product="Microsoft SQL Server" version="10.0.1073.0" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="4ca48-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="4ca48-129">See Also</span></span>  
 [<span data-ttu-id="4ca48-130">Программа ssbdiagnose (компонент Service Broker)</span><span class="sxs-lookup"><span data-stu-id="4ca48-130">ssbdiagnose Utility &#40;Service Broker&#41;</span></span>](ssbdiagnose-utility-service-broker.md)  
  
  
