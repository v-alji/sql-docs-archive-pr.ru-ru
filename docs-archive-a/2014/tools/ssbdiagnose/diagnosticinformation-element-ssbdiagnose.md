---
title: Элемент DiagnosticInformation (ssbdiagnose) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- XML output file format [ssbdiagnose], diagnosticinformation element
- diagnosticinformation element
- ssbdiagnose
ms.assetid: 0cfda544-542c-4cf4-86d2-8031c91b10f6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 92d76a065c24ddc1fc8d85989ed3202308571951
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656967"
---
# <a name="diagnosticinformation-element-ssbdiagnose"></a><span data-ttu-id="d716a-102">Элемент DiagnosticInformation (программа ssbdiagnose)</span><span class="sxs-lookup"><span data-stu-id="d716a-102">DiagnosticInformation Element (ssbdiagnose)</span></span>
  <span data-ttu-id="d716a-103">В элементе **DiagnosticInformation** содержатся все элементы, сообщающие о диагностических данных, обнаруженных программой.</span><span class="sxs-lookup"><span data-stu-id="d716a-103">The **DiagnosticInformation** element contains all elements that report the diagnostic information found by the utility.</span></span> <span data-ttu-id="d716a-104">**DiagnosticInformation** — корневой элемент выходного XML-файла программы **ssbdiagnostic** .</span><span class="sxs-lookup"><span data-stu-id="d716a-104">**DiagnosticInformation** is the root element of a **ssbdiagnostic** XML output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d716a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d716a-105">Syntax</span></span>  
  
```  
  
<DiagnosticInformation>   
    ...   
</DiagnosticInformation>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="d716a-106">Атрибуты элемента</span><span class="sxs-lookup"><span data-stu-id="d716a-106">Element Attributes</span></span>  
  
|<span data-ttu-id="d716a-107">attribute</span><span class="sxs-lookup"><span data-stu-id="d716a-107">Attribute</span></span>|<span data-ttu-id="d716a-108">Описание</span><span class="sxs-lookup"><span data-stu-id="d716a-108">Description</span></span>|  
|---------------|-----------------|  
|`None`|<span data-ttu-id="d716a-109">Недоступно</span><span class="sxs-lookup"><span data-stu-id="d716a-109">N/A</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="d716a-110">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="d716a-110">Element Characteristics</span></span>  
  
|<span data-ttu-id="d716a-111">Характеристика</span><span class="sxs-lookup"><span data-stu-id="d716a-111">Characteristic</span></span>|<span data-ttu-id="d716a-112">Описание</span><span class="sxs-lookup"><span data-stu-id="d716a-112">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="d716a-113">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="d716a-113">**Data type and length**</span></span>|<span data-ttu-id="d716a-114">Нет.</span><span class="sxs-lookup"><span data-stu-id="d716a-114">None.</span></span>|  
|<span data-ttu-id="d716a-115">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="d716a-115">**Default value**</span></span>|<span data-ttu-id="d716a-116">Нет.</span><span class="sxs-lookup"><span data-stu-id="d716a-116">None.</span></span>|  
|<span data-ttu-id="d716a-117">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="d716a-117">**Occurrence**</span></span>|<span data-ttu-id="d716a-118">Один раз на выходной XML-файла программы **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="d716a-118">Once per **ssbdiagnose** XML output file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="d716a-119">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="d716a-119">Element Relationships</span></span>  
  
|<span data-ttu-id="d716a-120">Связь</span><span class="sxs-lookup"><span data-stu-id="d716a-120">Relationship</span></span>|<span data-ttu-id="d716a-121">Элементы</span><span class="sxs-lookup"><span data-stu-id="d716a-121">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="d716a-122">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="d716a-122">**Parent element**</span></span>|<span data-ttu-id="d716a-123">Нет.</span><span class="sxs-lookup"><span data-stu-id="d716a-123">None.</span></span>|  
|<span data-ttu-id="d716a-124">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="d716a-124">**Child elements**</span></span>|[<span data-ttu-id="d716a-125">Элемент Banner (программа ssbdiagnose)</span><span class="sxs-lookup"><span data-stu-id="d716a-125">Banner Element &#40;ssbdiagnose&#41;</span></span>](banner-element-ssbdiagnose.md)<br /><br /> [<span data-ttu-id="d716a-126">Элемент Issue (программа ssbdiagnose)</span><span class="sxs-lookup"><span data-stu-id="d716a-126">Issue Element &#40;ssbdiagnose&#41;</span></span>](issue-element-ssbdiagnose.md)|  
  
## <a name="remarks"></a><span data-ttu-id="d716a-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="d716a-127">Remarks</span></span>  
 <span data-ttu-id="d716a-128">Дополнительные сведения о пространствах имен XML см. в статье [Пространства имен в XML-документе](https://go.microsoft.com/fwlink/?LinkId=7341) в библиотеке [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN.</span><span class="sxs-lookup"><span data-stu-id="d716a-128">For more information about XML namespaces, see [Namespaces in an XML Document](https://go.microsoft.com/fwlink/?LinkId=7341) in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN Library.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d716a-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="d716a-129">See Also</span></span>  
 [<span data-ttu-id="d716a-130">Программа ssbdiagnose (компонент Service Broker)</span><span class="sxs-lookup"><span data-stu-id="d716a-130">ssbdiagnose Utility &#40;Service Broker&#41;</span></span>](ssbdiagnose-utility-service-broker.md)  
  
  
