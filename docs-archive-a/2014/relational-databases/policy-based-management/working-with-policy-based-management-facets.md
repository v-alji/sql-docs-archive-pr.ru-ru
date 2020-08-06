---
title: Работа с аспектами управления на основе политик | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- viewing Policy-Based Management facets
- facets [Policy-Based Management], copying
- facets [Policy-Based Management], viewing
- copying Policy-Based Management facets
ms.assetid: 88d025c4-07c2-4e4d-8634-204249a8c82c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5a356550796cc682b2292defffd6565b7fea0783
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657688"
---
# <a name="working-with-policy-based-management-facets"></a><span data-ttu-id="da5d6-102">Работа с аспектами управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="da5d6-102">Working with Policy-Based Management Facets</span></span>
  <span data-ttu-id="da5d6-103">Аспект управления на основе политик — это ряд логических свойств, которые связаны с определенной областью, представляющей интерес с точки зрения управления.</span><span class="sxs-lookup"><span data-stu-id="da5d6-103">A Policy-Based Management facet is a set of logical properties that are related to an area of management interest.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="da5d6-104">включает несколько стандартных аспектов.</span><span class="sxs-lookup"><span data-stu-id="da5d6-104">includes several predefined facets.</span></span> <span data-ttu-id="da5d6-105">Например, средство настройки контактной зоны, определяющее функции, отключенные по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="da5d6-105">For example, the Surface Area Configuration facet defines, as properties, the features that are off by default.</span></span>  
  
 <span data-ttu-id="da5d6-106">При управлении несколькими похожими средами [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] можно настроить аспект в одном экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], скопировать состояние аспекта в файл и импортировать этот файл на другой экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в качестве политики.</span><span class="sxs-lookup"><span data-stu-id="da5d6-106">When you manage many similar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] environments, you can configure a facet in one instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], copy the state of the facet to a file, and then import that file into another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as a policy.</span></span> <span data-ttu-id="da5d6-107">При преобразовании состояния в политику она может быть применена к другим экземплярам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], объектам экземпляров, базам данных или объектам баз данных.</span><span class="sxs-lookup"><span data-stu-id="da5d6-107">When the state has been converted to a policy, the policy can be applied to other instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], instance objects, databases, or database objects.</span></span>  
  
 <span data-ttu-id="da5d6-108">Этот раздел описывает способ копирования состояния аспекта в XML-файл.</span><span class="sxs-lookup"><span data-stu-id="da5d6-108">This topic describes how to copy the state of a facet to an XML file.</span></span>  
  
##  <a name="permissions"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="da5d6-109">Permissions</span><span class="sxs-lookup"><span data-stu-id="da5d6-109">Permissions</span></span>  
 <span data-ttu-id="da5d6-110">Для процедуры в этом разделе требуется членство в роли PolicyAdministratorRole базы данных msdb.</span><span class="sxs-lookup"><span data-stu-id="da5d6-110">The procedures in this topic require membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
## <a name="viewing-and-copying-facet-states"></a><span data-ttu-id="da5d6-111">Просмотр и копирование состояний аспекта</span><span class="sxs-lookup"><span data-stu-id="da5d6-111">Viewing and Copying Facet States</span></span>  
 [<span data-ttu-id="da5d6-112">Просмотр аспектов управления на основе политик в объекте SQL Server</span><span class="sxs-lookup"><span data-stu-id="da5d6-112">View the Policy-Based Management Facets on a SQL Server Object</span></span>](view-the-policy-based-management-facets-on-a-sql-server-object.md)  
  
 [<span data-ttu-id="da5d6-113">Копирование состояния аспекта управления на основе политик в XML-файл</span><span class="sxs-lookup"><span data-stu-id="da5d6-113">Copy a Policy-Based Management Facet State to an XML File</span></span>](copy-a-policy-based-management-facet-state-to-an-xml-file.md)  
  
## <a name="see-also"></a><span data-ttu-id="da5d6-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="da5d6-114">See Also</span></span>  
 [<span data-ttu-id="da5d6-115">Администрирование серверов с помощью управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="da5d6-115">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
