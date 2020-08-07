---
title: Настройка уровня «все» для иерархий атрибутов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- All members
- IsAggregatable property
- topmost levels [Analysis Services]
- (All) levels
- AttributeAllMemberName property
- levels [Analysis Services]
- members [Analysis Services], All
- AllMemberName property
ms.assetid: 0cb35e6f-b10f-483d-b893-78f6ca3979fd
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9874a8c8a6861bc7d9e44271b089e8af3a4c0ae2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731005"
---
# <a name="configure-the-all-level-for-attribute-hierarchies"></a><span data-ttu-id="fe744-102">Настройка уровня «Все» для иерархий атрибутов</span><span class="sxs-lookup"><span data-stu-id="fe744-102">Configure the (All) Level for Attribute Hierarchies</span></span>
  <span data-ttu-id="fe744-103">В [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] уровень (все) является необязательным, созданным системой уровнем.</span><span class="sxs-lookup"><span data-stu-id="fe744-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], the (All) level is an optional, system-generated level.</span></span> <span data-ttu-id="fe744-104">Он содержит только один элемент, значение которого является результатом статистической обработки значений всех членов на ближайшем подчиненном уровне.</span><span class="sxs-lookup"><span data-stu-id="fe744-104">It contains only one member whose value is the aggregation of the values of all members in the immediately subordinate level.</span></span> <span data-ttu-id="fe744-105">Этот элемент называется «Все».</span><span class="sxs-lookup"><span data-stu-id="fe744-105">This member is called the All member.</span></span> <span data-ttu-id="fe744-106">Он создается системой и отсутствует в таблице измерений.</span><span class="sxs-lookup"><span data-stu-id="fe744-106">It is a system-generated member that is not contained in the dimension table.</span></span> <span data-ttu-id="fe744-107">Поскольку элемент уровня «Все» находится на вершине иерархии, его значение является результатом статистической обработки значений всех элементов иерархии.</span><span class="sxs-lookup"><span data-stu-id="fe744-107">Because the member in the (All) level is at the top of the hierarchy, the member's value is the consolidated aggregation of the values of all members in the hierarchy.</span></span> <span data-ttu-id="fe744-108">Элемент (Все) часто служит в качестве члена иерархии по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fe744-108">The All member often serves as the default member of a hierarchy.</span></span>  
  
 <span data-ttu-id="fe744-109">Присутствие уровня «Все» в иерархии атрибутов определяет свойство `IsAggregatable` атрибута, а наличие уровня «Все» в пользовательской иерархии — свойство `IsAggregatable` атрибута на верхнем ее уровне.</span><span class="sxs-lookup"><span data-stu-id="fe744-109">The presence of an (All) level in an attribute hierarchy depends on the `IsAggregatable` property setting for the attribute and the presence of an (All) level in a user-defined hierarchy depends on the `IsAggregatable` property of the attribute at the top-most level of user-defined hierarchy.</span></span> <span data-ttu-id="fe744-110">Уровень (Все) существует, если свойство `IsAggregatable` имеет значение `True`.</span><span class="sxs-lookup"><span data-stu-id="fe744-110">If the `IsAggregatable` property is set to `True`, an (All) level will exist.</span></span> <span data-ttu-id="fe744-111">Уровня (Все) не будет в иерархии, если свойство `IsAggregatable` имеет значение `False`.</span><span class="sxs-lookup"><span data-stu-id="fe744-111">A hierarchy has no (All) level if the `IsAggregatable` property is set to `False`.</span></span>  
  
## <a name="establishing-the-topmost-level"></a><span data-ttu-id="fe744-112">Установление высшего уровня</span><span class="sxs-lookup"><span data-stu-id="fe744-112">Establishing the Topmost Level</span></span>  
 <span data-ttu-id="fe744-113">Если свойство `IsAggregatable` исходного атрибута уровня иерархии имеет значение `False`, то выше этого уровня не могут появляться уровни, подлежащие статистической обработке.</span><span class="sxs-lookup"><span data-stu-id="fe744-113">If the `IsAggregatable` property is set to `False` on the source attribute of a level in a hierarchy, then no aggregatable level can appear in the hierarchy above that level.</span></span> <span data-ttu-id="fe744-114">Уровень, не подлежащий статистической обработке, должен быть высшим уровнем иерархии. В противном случае свойство `IsAggregatable` исходных атрибутов всех уровней выше этого должно также иметь значение `False`.</span><span class="sxs-lookup"><span data-stu-id="fe744-114">A non-aggregatable level must be the topmost level of any hierarchy or the `IsAggregatable` property of the source attributes for any levels above it must also be set to `False`.</span></span>  
  
## <a name="all-member-and-all-level"></a><span data-ttu-id="fe744-115">Уровень (Все) и элемент «Все»</span><span class="sxs-lookup"><span data-stu-id="fe744-115">All Member and (All) Level</span></span>  
 <span data-ttu-id="fe744-116">Единственный элемент уровня (Все) называется элементом «Все».</span><span class="sxs-lookup"><span data-stu-id="fe744-116">The single member of the (All) level is called the All member.</span></span> <span data-ttu-id="fe744-117">`AttributeAllMemberName`Свойство в измерении задает имя элемента «все» для атрибутов в измерении.</span><span class="sxs-lookup"><span data-stu-id="fe744-117">The `AttributeAllMemberName`property on a dimension specifies the name of the All member for attributes in a dimension.</span></span> <span data-ttu-id="fe744-118">Свойство `AllMemberName` иерархии задает имя элемента «Все» для иерархии.</span><span class="sxs-lookup"><span data-stu-id="fe744-118">The `AllMemberName` property on a hierarchy specifies the name of the All member for the hierarchy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe744-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="fe744-119">See Also</span></span>  
 [<span data-ttu-id="fe744-120">Определение элемента по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fe744-120">Define a Default Member</span></span>](attribute-properties-define-a-default-member.md)  
  
  
