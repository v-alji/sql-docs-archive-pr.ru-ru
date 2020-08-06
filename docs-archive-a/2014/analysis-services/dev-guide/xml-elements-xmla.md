---
title: XML-элементы (XMLA) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- XMLA, elements
- XML for Analysis, elements
- elements [XML for Analysis]
ms.assetid: 40ab2360-efb6-4ba6-bf23-e84964e51008
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5c1e5b046bfa57302baefc43a4da989be9c70e08
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667478"
---
# <a name="xml-elements-xmla"></a><span data-ttu-id="4ff69-102">Элементы XML (XML для аналитики)</span><span class="sxs-lookup"><span data-stu-id="4ff69-102">XML Elements (XMLA)</span></span>
  <span data-ttu-id="4ff69-103">В следующих разделах описываются различные категории элементов XML для аналитики (XMLA), поддерживаемые [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4ff69-103">The following topics describe the various XML for Analysis (XMLA) element categories supported by [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4ff69-104">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="4ff69-104">In This Section</span></span>  
  
|<span data-ttu-id="4ff69-105">Свойство</span><span class="sxs-lookup"><span data-stu-id="4ff69-105">Property</span></span>|<span data-ttu-id="4ff69-106">Описание</span><span class="sxs-lookup"><span data-stu-id="4ff69-106">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="4ff69-107">Заголовки &#40;XMLA&#41;</span><span class="sxs-lookup"><span data-stu-id="4ff69-107">Headers &#40;XMLA&#41;</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/xml-elements-headers)|<span data-ttu-id="4ff69-108">Описывает элементы, передаваемые в заголовке SOAP конверта SOAP приложением или экземпляром служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], предназначенные для управления функциями на уровне протокола.</span><span class="sxs-lookup"><span data-stu-id="4ff69-108">Describes those elements sent in the SOAP header of a SOAP envelope, either by an application or by an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance, to manage protocol-level features.</span></span>|  
|[<span data-ttu-id="4ff69-109">Методы &#40;XMLA&#41;</span><span class="sxs-lookup"><span data-stu-id="4ff69-109">Methods &#40;XMLA&#41;</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods)|<span data-ttu-id="4ff69-110">Описывает самые верхние элементы, передаваемые приложением в конверте SOAP экземпляру служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] для получения данных или метаданных, либо для выполнения действий в экземпляре.</span><span class="sxs-lookup"><span data-stu-id="4ff69-110">Describes the topmost elements sent by an application in a SOAP envelope to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance to retrieve data or metadata, or to perform actions on the instance.</span></span>|  
|[<span data-ttu-id="4ff69-111">Команды &#40;XMLA&#41;</span><span class="sxs-lookup"><span data-stu-id="4ff69-111">Commands &#40;XMLA&#41;</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/xml-elements-commands)|<span data-ttu-id="4ff69-112">Описывает элементы, передаваемые в методе XMLA для выполнения конкретного действия.</span><span class="sxs-lookup"><span data-stu-id="4ff69-112">Describes the elements sent within an XMLA method to perform a specific action.</span></span>|  
|[<span data-ttu-id="4ff69-113">Объекты &#40;XMLA&#41;</span><span class="sxs-lookup"><span data-stu-id="4ff69-113">Objects &#40;XMLA&#41;</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-objects)|<span data-ttu-id="4ff69-114">Описывает самые верхние элементы, получаемые приложением в конверте SOAP от экземпляра служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] в ответ на вызов метода XMLA.</span><span class="sxs-lookup"><span data-stu-id="4ff69-114">Describes the topmost elements received by an application in a SOAP envelope from an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance in response to an XMLA method.</span></span>|  
|[<span data-ttu-id="4ff69-115">Свойства &#40;XMLA&#41;</span><span class="sxs-lookup"><span data-stu-id="4ff69-115">Properties &#40;XMLA&#41;</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/xml-elements-properties)|<span data-ttu-id="4ff69-116">Описывает дочерние элементы для заголовков, методов, объектов или команд XMLA.</span><span class="sxs-lookup"><span data-stu-id="4ff69-116">Describes the child elements for XMLA headers, methods, objects, or commands.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4ff69-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="4ff69-117">See Also</span></span>  
 <span data-ttu-id="4ff69-118">[Типы данных XML &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-data-types/xml-data-types-xmla) </span><span class="sxs-lookup"><span data-stu-id="4ff69-118">[XML Data Types &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-data-types/xml-data-types-xmla) </span></span>  
 [<span data-ttu-id="4ff69-119">Разработка на языке ASSL (язык ASSL)</span><span class="sxs-lookup"><span data-stu-id="4ff69-119">Developing with Analysis Services Scripting Language &#40;ASSL&#41;</span></span>](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md)  
  
  
