---
title: Общие сведения об интеграции со средой CLR | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- managed code [SQL Server]
- common language runtime [SQL Server], about CLR integration
- cross-language integration
- integrating CLR [SQL Server]
- .NET Framework [SQL Server], common language runtime
- code access security [CLR integration]
- managed code [SQL Server], CLR integration
ms.assetid: 7be9e644-36a2-48fc-9206-faf59fdff4d7
author: rothja
ms.author: jroth
ms.openlocfilehash: 25345fd39fb8a77f62e4e352b75629a98cb9d7af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658833"
---
# <a name="common-language-runtime-clr-integration-overview"></a><span data-ttu-id="9ea55-102">Общие сведения об интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="9ea55-102">Common Language Runtime (CLR) Integration Overview</span></span>
  [!INCLUDE[msCoName](../../../includes/msconame-md.md)]<span data-ttu-id="9ea55-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]теперь включает в себя интеграцию компонента среды clr .NET Framework для [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="9ea55-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] now features the integration of the common language runtime (CLR) component of the .NET Framework for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows.</span></span> <span data-ttu-id="9ea55-104">Среда CLR предоставляет управляемому коду такие услуги, как межъязыковая интеграция, управление доступом для кода, управление временем существования объекта, а также поддержку отладки и профилирования.</span><span class="sxs-lookup"><span data-stu-id="9ea55-104">The CLR supplies managed code with services such as cross-language integration, code access security, object lifetime management, and debugging and profiling support.</span></span> <span data-ttu-id="9ea55-105">Для пользователей и разработчиков [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] интеграция со средой CLR означает, что теперь можно писать хранимые процедуры, триггеры, определяемые пользователем типы и функции (скалярные и возвращающие табличное значение), а также определяемые пользователем агрегатные функции на любом языке среды .NET, включая [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic и [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="9ea55-105">For [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] users and application developers, CLR integration means that you can now write stored procedures, triggers, user-defined types, user-defined functions (scalar and table-valued), and user-defined aggregate functions using any .NET Framework language, including [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET and [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="9ea55-106">включает в себя предварительно установленную платформу .NET Framework (версия 4).</span><span class="sxs-lookup"><span data-stu-id="9ea55-106">includes the .NET Framework version 4 pre-installed.</span></span>  
  
 <span data-ttu-id="9ea55-107">Далее перечислены основные преимущества этой интеграции.</span><span class="sxs-lookup"><span data-stu-id="9ea55-107">Among the major benefits of this integration are:</span></span>  
  
-   <span data-ttu-id="9ea55-108">**Улучшенная модель программирования.**</span><span class="sxs-lookup"><span data-stu-id="9ea55-108">**A better programming model.**</span></span> <span data-ttu-id="9ea55-109">Языки платформы .NET Framework во многих отношениях богаче языка Transact-SQL. Они предлагают конструкции и возможности, ранее не доступные разработчикам программ для [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ea55-109">The .NET Framework languages are in many respects richer than Transact-SQL, offering constructs and capabilities previously not available to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] developers.</span></span> <span data-ttu-id="9ea55-110">Разработчики могут также использовать всю мощь библиотеки платформы .NET Framework (.NET Framework Library), предоставляющей обширный набор классов, которые позволяют быстро и эффективно решать возникающие при разработке проблемы. </span><span class="sxs-lookup"><span data-stu-id="9ea55-110">Developers may also leverage the power of the .NET Framework Library, which provides an extensive set of classes that can be used to quickly and efficiently solve programming problems.</span></span>  
  
-   <span data-ttu-id="9ea55-111">**Улучшенная надежность и безопасность.**</span><span class="sxs-lookup"><span data-stu-id="9ea55-111">**Improved safety and security.**</span></span> <span data-ttu-id="9ea55-112">Управляемый код выполняется в среде CLR, размещаемой в компоненте Database Engine.</span><span class="sxs-lookup"><span data-stu-id="9ea55-112">Managed code runs in a common language run-time environment, hosted by the Database Engine.</span></span> <span data-ttu-id="9ea55-113">В [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] таким образом обеспечивается более безопасная и надежная альтернатива расширенным хранимым процедурам, доступным в предыдущих версиях [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ea55-113">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] leverages this to provide a safer and more secure alternative to the extended stored procedures available in earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="9ea55-114">**Возможность определять типы данных и агрегатные функции.**</span><span class="sxs-lookup"><span data-stu-id="9ea55-114">**Ability to define data types and aggregate functions.**</span></span> <span data-ttu-id="9ea55-115">Определяемые пользователем типы данных и статистические функции — два новых вида объектов в базе данных, расширяющие возможности запросов и хранения данных СУБД [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ea55-115">User defined types and user defined aggregates are two new managed database objects which expand the storage and querying capabilities of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="9ea55-116">**Упрощение процесса разработки в результате стандартизации среды.**</span><span class="sxs-lookup"><span data-stu-id="9ea55-116">**Streamlined development through a standardized environment.**</span></span> <span data-ttu-id="9ea55-117">Разработка базы данных интегрирована в будущие версии среды разработки [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio .NET.</span><span class="sxs-lookup"><span data-stu-id="9ea55-117">Database development is integrated into future releases of the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio .NET development environment.</span></span> <span data-ttu-id="9ea55-118">Для разработки и отладки объектов и скриптов баз данных разработчики используют те же инструментальные средства, что и для разработки компонентов и служб платформы .NET Framework клиентского и среднего уровня.</span><span class="sxs-lookup"><span data-stu-id="9ea55-118">Developers use the same tools for developing and debugging database objects and scripts as they use to write middle-tier or client-tier .NET Framework components and services.</span></span>  
  
-   <span data-ttu-id="9ea55-119">**Возможность повышения производительности и масштабируемости.**</span><span class="sxs-lookup"><span data-stu-id="9ea55-119">**Potential for improved performance and scalability.**</span></span> <span data-ttu-id="9ea55-120">Во многих случаях средства компиляции и модели выполнения платформы .NET Framework предоставляют выигрыш в производительности по сравнению с Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="9ea55-120">In many situations, the .NET Framework language compilation and execution models deliver improved performance over Transact-SQL.</span></span>  
  
 <span data-ttu-id="9ea55-121">В следующей таблице перечислены подразделы этого раздела.</span><span class="sxs-lookup"><span data-stu-id="9ea55-121">This following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="9ea55-122">Общие сведения об интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="9ea55-122">Overview of CLR Integration</span></span>](clr-integration-overview.md)  
 <span data-ttu-id="9ea55-123">Описание видов объектов, которые можно построить с помощью интеграции со средой CLR, и обзор требований к построению объектов баз данных с помощью интеграции со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="9ea55-123">Describes the kinds of objects that can be built using CLR integration, and reviews the requirements for building database objects using CLR integration.</span></span>  
  
 [<span data-ttu-id="9ea55-124">новые возможности в интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="9ea55-124">What's New in CLR Integration</span></span>](clr-integration-what-s-new.md)  
 <span data-ttu-id="9ea55-125">Описывает новые возможности в данном выпуске.</span><span class="sxs-lookup"><span data-stu-id="9ea55-125">Describes the new features in this release.</span></span>  
  
 [<span data-ttu-id="9ea55-126">Архитектура интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="9ea55-126">Architecture of CLR Integration</span></span>](../../database-engine/dev-guide/architecture-of-clr-integration.md)  
 <span data-ttu-id="9ea55-127">Описание целей разработки интеграции со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="9ea55-127">Describes the design goals of CLR integration.</span></span>  
  
 [<span data-ttu-id="9ea55-128">Включение интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="9ea55-128">Enabling CLR Integration</span></span>](clr-integration-enabling.md)  
 <span data-ttu-id="9ea55-129">Описание включения интеграции со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="9ea55-129">Describes how to enable CLR integration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ea55-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="9ea55-130">See Also</span></span>  
 <span data-ttu-id="9ea55-131">[Установка .NET Framework](https://technet.microsoft.com/library/ms166014\(v=SQL.105\).aspx) </span><span class="sxs-lookup"><span data-stu-id="9ea55-131">[Installing the .NET Framework](https://technet.microsoft.com/library/ms166014\(v=SQL.105\).aspx) </span></span>  
 [<span data-ttu-id="9ea55-132">Производительность интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="9ea55-132">Performance of CLR Integration</span></span>](clr-integration-architecture-performance.md)  
  
  
