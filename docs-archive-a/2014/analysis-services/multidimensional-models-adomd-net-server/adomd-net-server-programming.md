---
title: Программирование сервера ADOMD.NET | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- programming [ADOMD.NET]
- ADOMD.NET, programming
ms.assetid: 7f7ff5be-3826-43a5-b94d-ddeec5ddb2eb
author: minewiskan
ms.author: owend
ms.openlocfilehash: 522478af0b19f1745d80f167e40345d4751136b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727438"
---
# <a name="adomdnet-server-programming"></a><span data-ttu-id="67491-102">Программирование сервера ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="67491-102">ADOMD.NET Server Programming</span></span>
  <span data-ttu-id="67491-103">Серверные компоненты ADOMD.NET находятся в пространстве имен `Microsoft.AnalysisServices.AdomdServer` (в файле msmgdsrv.dll).</span><span class="sxs-lookup"><span data-stu-id="67491-103">The ADOMD.NET server components of ADOMD.NET reside within the `Microsoft.AnalysisServices.AdomdServer` namespace (in msmgdsrv.dll).</span></span> <span data-ttu-id="67491-104">Эти серверные компоненты используются для создания пользовательских функций МНОГОМЕРных выражений и хранимых процедур, выполняемых на экземпляре служб [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="67491-104">You use these server components to create custom Multidimensional Expressions (MDX) functions and stored procedures that are run on an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="67491-105">Серверные объекты обеспечивают возможность выполнения запросов к кубам и моделям интеллектуального анализа данных, а также для вычисления выражений в данном контексте.</span><span class="sxs-lookup"><span data-stu-id="67491-105">The server objects provide the capabilities for querying cubes and mining models, and for evaluating expressions in a given context.</span></span> <span data-ttu-id="67491-106">Среди преимуществ создания пользовательских функций и хранимых процедур — быстрое выполнение, централизованное развертывание и удобство поддержки.</span><span class="sxs-lookup"><span data-stu-id="67491-106">The benefits for creating custom functions and stored procedures include fast execution, centralized deployment, and improved maintainability.</span></span>  
  
 <span data-ttu-id="67491-107">Разделы, приведенные в следующей таблице, могут помочь в разработке серверных приложений ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="67491-107">The topics in the following table will help you develop ADOMD.NET server applications.</span></span>  
  
|<span data-ttu-id="67491-108">Раздел</span><span class="sxs-lookup"><span data-stu-id="67491-108">Topic</span></span>|<span data-ttu-id="67491-109">Описание</span><span class="sxs-lookup"><span data-stu-id="67491-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="67491-110">Функциональные возможности сервера ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="67491-110">ADOMD.NET Server Functionality</span></span>](https://docs.microsoft.com/bi-reference/adomd/multidimensional-models-adomd-net-server/adomd-net-server-functionality)|<span data-ttu-id="67491-111">Описывает варианты использования серверных объектов ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="67491-111">Describes the uses for ADOMD.NET server objects.</span></span>|  
|[<span data-ttu-id="67491-112">Архитектура серверных объектов ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="67491-112">ADOMD.NET Server Object Architecture</span></span>](https://docs.microsoft.com/bi-reference/adomd/multidimensional-models-adomd-net-server/adomd-net-server-object-architecture)|<span data-ttu-id="67491-113">Описывает архитектуру серверных объектов ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="67491-113">Describes the object architecture for ADOMD.NET server objects.</span></span>|  
|[<span data-ttu-id="67491-114">Определяемые пользователем функции и хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="67491-114">User Defined Functions and Stored Procedures</span></span>](https://docs.microsoft.com/analysis-services/adomd/multidimensional-models-adomd-net-server/user-defined-functions-and-stored-procedures)|<span data-ttu-id="67491-115">Пошаговое описание процесса создания определяемой пользователем функции или хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="67491-115">Walks you through the process of creating a user defined function or stored Procedure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="67491-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="67491-116">See Also</span></span>  
 <span data-ttu-id="67491-117">[Программирование клиента ADOMD.NET](https://docs.microsoft.com/analysis-services/adomd/multidimensional-models-adomd-net-client/adomd-net-client-programming) </span><span class="sxs-lookup"><span data-stu-id="67491-117">[ADOMD.NET Client Programming](https://docs.microsoft.com/analysis-services/adomd/multidimensional-models-adomd-net-client/adomd-net-client-programming) </span></span>  
 [<span data-ttu-id="67491-118">Разработка с использованием ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="67491-118">Developing with ADOMD.NET</span></span>](https://docs.microsoft.com/bi-reference/adomd/developing-with-adomd-net)  
  
  
