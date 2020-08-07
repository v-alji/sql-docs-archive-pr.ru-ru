---
title: Создание пользовательских иерархий | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- user-defined hierarchies [Analysis Services]
ms.assetid: 16715b85-0630-4a8e-99b0-c0d213cade26
author: minewiskan
ms.author: owend
ms.openlocfilehash: 17e870a2b20125132342db1845689b7c2481d623
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732090"
---
# <a name="create-user-defined-hierarchies"></a><span data-ttu-id="e40ef-102">Создание пользовательских иерархий</span><span class="sxs-lookup"><span data-stu-id="e40ef-102">Create User-Defined Hierarchies</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="e40ef-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]позволяет создавать пользовательские иерархии.</span><span class="sxs-lookup"><span data-stu-id="e40ef-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] lets you create user-defined hierarchies.</span></span> <span data-ttu-id="e40ef-104">Иерархия — это набор уровней на основе атрибутов.</span><span class="sxs-lookup"><span data-stu-id="e40ef-104">A hierarchy is a collection of levels based on attributes.</span></span> <span data-ttu-id="e40ef-105">Например, иерархия, связанная со временем, может содержать такие уровни, как «Год», «Месяц» и «День».</span><span class="sxs-lookup"><span data-stu-id="e40ef-105">For example, a time hierarchy might contain the Year, Quarter, Month, Week, and Day levels.</span></span> <span data-ttu-id="e40ef-106">В некоторых иерархиях каждый атрибут однозначно задает атрибут родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="e40ef-106">In some hierarchies, each member attribute uniquely implies the member attribute above it.</span></span> <span data-ttu-id="e40ef-107">Такую иерархию иногда называют естественной.</span><span class="sxs-lookup"><span data-stu-id="e40ef-107">This is sometimes referred to as a natural hierarchy.</span></span> <span data-ttu-id="e40ef-108">Конечные пользователи могут использовать иерархии для просмотра данных в кубе.</span><span class="sxs-lookup"><span data-stu-id="e40ef-108">A hierarchy can be used by end users to browse cube data.</span></span> <span data-ttu-id="e40ef-109">Иерархии задаются с помощью панели «Иерархии» конструктора измерений в среде разработки [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e40ef-109">Define hierarchies by using the Hierarchies pane of Dimension Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="e40ef-110">Вновь созданная пользовательская иерархия может оказаться *неровной*.</span><span class="sxs-lookup"><span data-stu-id="e40ef-110">When you create a user-defined hierarchy, the hierarchy might become *ragged*.</span></span> <span data-ttu-id="e40ef-111">Неровная иерархия — это иерархия, в которой по крайней мере у одного элемента логический родительский элемент не находится ровно на один уровень выше самого элемента.</span><span class="sxs-lookup"><span data-stu-id="e40ef-111">A ragged hierarchy is where the logical parent member of at least one member is not in the level immediately above the member.</span></span> <span data-ttu-id="e40ef-112">Существуют настройки, управляющие видимостью недостающих элементов в неровных иерархиях и способом их отображения.</span><span class="sxs-lookup"><span data-stu-id="e40ef-112">If you have a ragged hierarchy, there are settings that control whether the missing members are visible and how to display the missing members.</span></span> <span data-ttu-id="e40ef-113">Дополнительные сведения об иерархиях см. в разделе [Неоднородные иерархии](user-defined-hierarchies-ragged-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="e40ef-113">For more information, see [Ragged Hierarchies](user-defined-hierarchies-ragged-hierarchies.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e40ef-114">Дополнительные сведения о проблемах производительности, связанных с конструированием и настройкой пользовательских иерархий, см. в [руководстве по производительности служб SQL Server 2005 Analysis Services](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span><span class="sxs-lookup"><span data-stu-id="e40ef-114">For more information about performance issues related to the design and configuration of user-defined hierarchies, see the [SQL Server 2005 Analysis Services Performance Guide](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e40ef-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="e40ef-115">See Also</span></span>  
 <span data-ttu-id="e40ef-116">[Свойства пользовательской иерархии](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md) </span><span class="sxs-lookup"><span data-stu-id="e40ef-116">[User Hierarchy Properties](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md) </span></span>  
 <span data-ttu-id="e40ef-117">[Свойства уровня &#91;Павед поверх&#93;](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-level-properties.md) </span><span class="sxs-lookup"><span data-stu-id="e40ef-117">[Level Properties &#91;Paved Over&#93;](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-level-properties.md) </span></span>  
 [<span data-ttu-id="e40ef-118">Иерархия "родители-потомки"</span><span class="sxs-lookup"><span data-stu-id="e40ef-118">Parent-Child Hierarchy</span></span>](parent-child-dimension.md)  
  
  
