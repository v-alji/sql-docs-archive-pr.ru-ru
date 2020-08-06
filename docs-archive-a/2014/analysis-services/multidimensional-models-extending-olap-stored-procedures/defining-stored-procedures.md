---
title: Определение хранимых процедур | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- stored procedures [Analysis Services]
- OLAP [Analysis Services], stored procedures
- external routines [Analysis Services]
- stored procedures [Analysis Services], about stored procedures
ms.assetid: f9c57d91-f60f-4f0e-8f7f-d87f4ba97b7c
author: minewiskan
ms.author: owend
ms.openlocfilehash: cc1f028f822d2289ee79702feb2494487040977c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732158"
---
# <a name="defining-stored-procedures"></a><span data-ttu-id="72a16-102">Определение хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="72a16-102">Defining Stored Procedures</span></span>
  <span data-ttu-id="72a16-103">Хранимые процедуры можно использовать для вызова внешних подпрограмм из [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="72a16-103">You can use stored procedures to call external routines from [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="72a16-104">Для написания внешней подпрограммы, вызываемой хранимой процедурой, можно использовать любой язык среды CLR, например C, C++, C#, Visual Basic или Visual Basic .NET.</span><span class="sxs-lookup"><span data-stu-id="72a16-104">You can write an external routines called by a stored procedure in any common language runtime (CLR) language, such as C, C++, C#, Visual Basic, or Visual Basic .NET.</span></span> <span data-ttu-id="72a16-105">Хранимую процедуру можно создать один раз и затем вызывать из множества контекстов, например из других хранимых процедур, вычисляемых мер или клиентских приложений.</span><span class="sxs-lookup"><span data-stu-id="72a16-105">A stored procedure can be created once and called from many contexts, such as other stored procedures, calculated measures, or client applications.</span></span> <span data-ttu-id="72a16-106">Хранимые процедуры упрощают разработку и реализацию базы данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] благодаря тому, что общий код создается один раз и сохраняется в одном месте.</span><span class="sxs-lookup"><span data-stu-id="72a16-106">Stored procedures simplify [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database development and implementation by allowing common code to be developed once and stored in a single location.</span></span> <span data-ttu-id="72a16-107">Хранимые процедуры можно использовать для расширения функциональности приложений за счет добавления дополнительных функций к собственной функциональности многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="72a16-107">Stored procedures can be used to add business functionality to your applications that is not provided by the native functionality of MDX.</span></span>  
  
 <span data-ttu-id="72a16-108">В данном разделе приводятся сведения, необходимые для понимания, проектирования и реализации хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="72a16-108">This section provides the information necessary to understand, design, and implement stored procedures.</span></span>  
  
|<span data-ttu-id="72a16-109">Раздел</span><span class="sxs-lookup"><span data-stu-id="72a16-109">Topic</span></span>|<span data-ttu-id="72a16-110">Описание</span><span class="sxs-lookup"><span data-stu-id="72a16-110">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="72a16-111">Конструирование хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="72a16-111">Designing Stored Procedures</span></span>](../multidimensional-models-extending-olap-stored-procedures/designing-stored-procedures.md)|<span data-ttu-id="72a16-112">Содержит описание проектирования сборок для использования со службами [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72a16-112">Describes how to design assemblies for use with [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="72a16-113">Создание хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="72a16-113">Creating Stored Procedures</span></span>](creating-stored-procedures.md)|<span data-ttu-id="72a16-114">Содержит описание создания сборок для служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72a16-114">Describes how to create assemblies for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="72a16-115">Вызов хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="72a16-115">Calling Stored Procedures</span></span>](calling-stored-procedures.md)|<span data-ttu-id="72a16-116">Предоставляет сведения об использовании сборок в службах [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72a16-116">Provides information on how to use assemblies in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="72a16-117">Доступ к контексту запросов в хранимых процедурах</span><span class="sxs-lookup"><span data-stu-id="72a16-117">Accessing Query Context in Stored Procedures</span></span>](accessing-query-context-in-stored-procedures.md)|<span data-ttu-id="72a16-118">Содержит описание получения доступа к данным области и контекстным данным при помощи сборок.</span><span class="sxs-lookup"><span data-stu-id="72a16-118">Describes how to access scope and context information with assemblies.</span></span>|  
|[<span data-ttu-id="72a16-119">Настройка безопасности хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="72a16-119">Setting Security for Stored Procedures</span></span>](setting-security-for-stored-procedures.md)|<span data-ttu-id="72a16-120">Содержит описание настройки безопасности для сборок в службах [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72a16-120">Describes how to configure security for assemblies in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="72a16-121">Отладка хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="72a16-121">Debugging Stored Procedures</span></span>](debugging-stored-procedures.md)|<span data-ttu-id="72a16-122">Содержит описание отладки сборок в службах [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72a16-122">Describes how to debug assemblies in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="72a16-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="72a16-123">See Also</span></span>  
 [<span data-ttu-id="72a16-124">Управление сборками многомерной модели</span><span class="sxs-lookup"><span data-stu-id="72a16-124">Multidimensional Model Assemblies Management</span></span>](../multidimensional-models/multidimensional-model-assemblies-management.md)  
  
  
