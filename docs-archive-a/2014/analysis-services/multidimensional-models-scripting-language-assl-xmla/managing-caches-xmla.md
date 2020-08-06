---
title: Управление кэшами (XMLA) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- XMLA, cache
- XML for Analysis, cache
- clearing cache
- cache [Analysis Services]
ms.assetid: afad5c39-d4c3-4307-b3b9-a06617da0028
author: minewiskan
ms.author: owend
ms.openlocfilehash: cdc5bcd2e0500749edfa298a871b6fec7243ddfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658487"
---
# <a name="managing-caches-xmla"></a><span data-ttu-id="2957d-102">Управление кэшами (XMLA)</span><span class="sxs-lookup"><span data-stu-id="2957d-102">Managing Caches (XMLA)</span></span>
  <span data-ttu-id="2957d-103">Для очистки кэша указанного измерения или секции можно использовать команду [ClearCache](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/clearcache-element-xmla) в XML для АНАЛИТИКИ (XMLA).</span><span class="sxs-lookup"><span data-stu-id="2957d-103">You can use the [ClearCache](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/clearcache-element-xmla) command in XML for Analysis (XMLA) to clear the cache of a specified dimension or partition.</span></span> <span data-ttu-id="2957d-104">Очистка кэша приводит [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] к перестроению кэша для этого объекта.</span><span class="sxs-lookup"><span data-stu-id="2957d-104">Clearing the cache forces [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to rebuild the cache for that object.</span></span>  
  
## <a name="specifying-objects"></a><span data-ttu-id="2957d-105">Указание объектов</span><span class="sxs-lookup"><span data-stu-id="2957d-105">Specifying Objects</span></span>  
 <span data-ttu-id="2957d-106">Свойство [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) `ClearCache` команды может содержать ссылку на объект только для одного из следующих объектов.</span><span class="sxs-lookup"><span data-stu-id="2957d-106">The [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) property of the `ClearCache` command can contain an object reference only for one of the following objects.</span></span> <span data-ttu-id="2957d-107">Если ссылка объекта указывает на объект, отличный от объекта из следующего списка, возникает ошибка:</span><span class="sxs-lookup"><span data-stu-id="2957d-107">An error occurs if an object reference is for an object other than one of following objects:</span></span>  
  
 <span data-ttu-id="2957d-108">База данных</span><span class="sxs-lookup"><span data-stu-id="2957d-108">Database</span></span>  
 <span data-ttu-id="2957d-109">Очищает кэш для всех измерений и секций, содержащихся в базе данных.</span><span class="sxs-lookup"><span data-stu-id="2957d-109">Clears the cache for all dimensions and partitions contained in the database.</span></span>  
  
 <span data-ttu-id="2957d-110">Измерение</span><span class="sxs-lookup"><span data-stu-id="2957d-110">Dimension</span></span>  
 <span data-ttu-id="2957d-111">Очищает кэш для указанного измерения.</span><span class="sxs-lookup"><span data-stu-id="2957d-111">Clears the cache for the specified dimension.</span></span>  
  
 <span data-ttu-id="2957d-112">Куб</span><span class="sxs-lookup"><span data-stu-id="2957d-112">Cube</span></span>  
 <span data-ttu-id="2957d-113">Очищает кэш для всех секций, содержащихся в группе мер для куба.</span><span class="sxs-lookup"><span data-stu-id="2957d-113">Clears the cache for all partitions contained in the measure groups for the cube.</span></span>  
  
 <span data-ttu-id="2957d-114">Группа мер</span><span class="sxs-lookup"><span data-stu-id="2957d-114">Measure group</span></span>  
 <span data-ttu-id="2957d-115">Очищает кэш для всех секций, содержащихся в группе мер.</span><span class="sxs-lookup"><span data-stu-id="2957d-115">Clears the cache for all partitions contained in the measure group.</span></span>  
  
 <span data-ttu-id="2957d-116">Секция</span><span class="sxs-lookup"><span data-stu-id="2957d-116">Partition</span></span>  
 <span data-ttu-id="2957d-117">Очищает кэш для указанной секции.</span><span class="sxs-lookup"><span data-stu-id="2957d-117">Clears the cache for the specified partition.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2957d-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="2957d-118">See Also</span></span>  
 [<span data-ttu-id="2957d-119">Разработка с использованием XMLA в службах Analysis Services</span><span class="sxs-lookup"><span data-stu-id="2957d-119">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
