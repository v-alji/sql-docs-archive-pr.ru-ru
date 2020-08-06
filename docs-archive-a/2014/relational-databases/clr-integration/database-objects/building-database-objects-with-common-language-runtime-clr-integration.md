---
title: Создание объектов базы данных с интеграцией среды CLR | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- routines [CLR integration]
- database objects [CLR integration], building
- common language runtime [SQL Server], building database objects
- managed code [SQL Server], database objects
- building database objects [CLR integration]
- .NET Framework routines [SQL Server]
ms.assetid: ce34132c-bfa3-447b-9131-b6e17c672efe
author: rothja
ms.author: jroth
ms.openlocfilehash: 3c849c095a3be1c590e6fcb3ce87a0725eb795c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665379"
---
# <a name="building-database-objects-with-common-language-runtime-clr-integration"></a><span data-ttu-id="dbf2d-102">Создание объектов базы данных с интеграцией со средой CLR</span><span class="sxs-lookup"><span data-stu-id="dbf2d-102">Building Database Objects with Common Language Runtime (CLR) Integration</span></span>
  <span data-ttu-id="dbf2d-103">Вы можете создавать объекты базы данных с помощью [!INCLUDE[ssNoVersion](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] среды, называемой "подпрограммы CLR".</span><span class="sxs-lookup"><span data-stu-id="dbf2d-103">You can build database objects using the [!INCLUDE[ssNoVersion](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is referred to as a "CLR routine."</span></span> <span data-ttu-id="dbf2d-104">Эти подпрограммы включают:</span><span class="sxs-lookup"><span data-stu-id="dbf2d-104">These routines include:</span></span>  
  
-   <span data-ttu-id="dbf2d-105">определяемые пользователем функции, возвращающие скалярное значение (скалярные определяемые пользователем функции);</span><span class="sxs-lookup"><span data-stu-id="dbf2d-105">Scalar-valued user-defined functions (scalar UDFs)</span></span>  
  
-   <span data-ttu-id="dbf2d-106">определяемые пользователем функции, возвращающие табличные значения (возвращающие табличное значение функции);</span><span class="sxs-lookup"><span data-stu-id="dbf2d-106">Table-valued user-defined functions (TVFs)</span></span>  
  
-   <span data-ttu-id="dbf2d-107">определяемые пользователем процедуры (определяемые пользователем процедуры);</span><span class="sxs-lookup"><span data-stu-id="dbf2d-107">User-defined procedures (UDPs)</span></span>  
  
-   <span data-ttu-id="dbf2d-108">определяемые пользователем триггеры.</span><span class="sxs-lookup"><span data-stu-id="dbf2d-108">User-defined triggers</span></span>  
  
 <span data-ttu-id="dbf2d-109">Подпрограммы CLR в управляемом коде имеют одинаковую структуру.</span><span class="sxs-lookup"><span data-stu-id="dbf2d-109">CLR routines have the same structure in managed code.</span></span> <span data-ttu-id="dbf2d-110">Они сопоставляются с публичными статическими методами класса (используемыми совместно с [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET).</span><span class="sxs-lookup"><span data-stu-id="dbf2d-110">They are mapped to public, static (shared in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET) methods of a class.</span></span> <span data-ttu-id="dbf2d-111">Кроме подпрограмм, с помощью .NET Framework можно определять пользовательские типы (UDT) и определяемые пользователем агрегатные функции.</span><span class="sxs-lookup"><span data-stu-id="dbf2d-111">In addition to routines, user-defined types (UDTs) and user-defined aggregate functions can also be defined using the .NET Framework.</span></span> <span data-ttu-id="dbf2d-112">Определяемые пользователем типы и определяемые пользователем статистические функции сопоставляются с целыми классами .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dbf2d-112">UDTs and user-defined aggregates are mapped to entire .NET Framework classes.</span></span>  
  
 <span data-ttu-id="dbf2d-113">Каждый тип .NET Framework подпрограммы имеет то [!INCLUDE[tsql](../../../includes/ssnoversion-md.md)] , что [!INCLUDE[tsql](../../../includes/tsql-md.md)] можно использовать эквивалент.</span><span class="sxs-lookup"><span data-stu-id="dbf2d-113">Each type of .NET Framework routine has a [!INCLUDE[tsql](../../../includes/ssnoversion-md.md)] that the [!INCLUDE[tsql](../../../includes/tsql-md.md)] equivalent can be used.</span></span> <span data-ttu-id="dbf2d-114">Например, скалярные определяемые пользователем функции могут использоваться во всех скалярных выражениях.</span><span class="sxs-lookup"><span data-stu-id="dbf2d-114">For instance, scalar UDFs can be used in any scalar expression.</span></span> <span data-ttu-id="dbf2d-115">Возвращающая табличное значение функция может использоваться в любом предложении FROM.</span><span class="sxs-lookup"><span data-stu-id="dbf2d-115">A TVF can be used in any FROM clause.</span></span> <span data-ttu-id="dbf2d-116">Процедура может вызываться в инструкции EXEC или из клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="dbf2d-116">A procedure can be invoked in an EXEC statement or invoked from a client application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dbf2d-117">Выполнение объекта CLR (определяемой пользователем функции, определяемого пользователем типа или триггера) в среде CLR может производиться в нескольких потоках (параллельный план), если оптимизатор запросов посчитает это более выгодным.</span><span class="sxs-lookup"><span data-stu-id="dbf2d-117">Execution of a CLR object (user-defined function, user-defined type, or trigger) on the common language runtime can take place on multiple threads (parallel plan), if the query optimizer decides it is beneficial.</span></span> <span data-ttu-id="dbf2d-118">Однако, если доступ к данным выполняет определяемая пользователем функция, выполнение будет осуществляться согласно последовательному плану.</span><span class="sxs-lookup"><span data-stu-id="dbf2d-118">However, if a user-defined function accesses data, execution will be  on a serial plan.</span></span> <span data-ttu-id="dbf2d-119">При выполнении на сервере, имеющем версию, предшествующую [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)], в случае, если определяемая пользователем функция содержит параметры или возвращает значения больших объектов (LOB), выполнение также должно производиться согласно последовательному плану.</span><span class="sxs-lookup"><span data-stu-id="dbf2d-119">When executed on a server version prior to [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)], if a user-defined function contains LOB parameters or return values, execution also must be on a serial plan.</span></span>  
  
 <span data-ttu-id="dbf2d-120">В следующей таблице приводится список подразделов этого раздела.</span><span class="sxs-lookup"><span data-stu-id="dbf2d-120">The following table lists the topics covered in this section.</span></span>  
  
 [<span data-ttu-id="dbf2d-121">Приступая к работе с интеграцией со средой CLR</span><span class="sxs-lookup"><span data-stu-id="dbf2d-121">Getting Started with CLR Integration</span></span>](getting-started-with-clr-integration.md)  
 <span data-ttu-id="dbf2d-122">Содержит краткие общие сведения о библиотеках и пространствах имен, необходимых для компиляции объектов с помощью интеграции со средой CLR в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dbf2d-122">Provides a brief overview of the libraries and namespaces required to compile object using CLR integration with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="dbf2d-123">Включает пример хранимой процедуры CLR «Hello World».</span><span class="sxs-lookup"><span data-stu-id="dbf2d-123">Includes an example "Hello World" CLR stored procedure.</span></span>  
  
 [<span data-ttu-id="dbf2d-124">Поддерживаемые библиотеки платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="dbf2d-124">Supported .NET Framework Libraries</span></span>](supported-net-framework-libraries.md)  
 <span data-ttu-id="dbf2d-125">Содержит сведения о библиотеках .NET Framework, поддерживаемых интеграцией со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="dbf2d-125">Provides information on the .NET Framework libraries supported by CLR integration.</span></span>  
  
 [<span data-ttu-id="dbf2d-126">Ограничения модели программирования на основе интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="dbf2d-126">CLR Integration Programming Model Restrictions</span></span>](clr-integration-programming-model-restrictions.md)  
 <span data-ttu-id="dbf2d-127">Содержит сведения об ограничениях модели программирования интеграции со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="dbf2d-127">Provides information about CLR integration programming model restrictions.</span></span>  
  
 [<span data-ttu-id="dbf2d-128">Типы данных SQL Server в платформе .NET Framework</span><span class="sxs-lookup"><span data-stu-id="dbf2d-128">SQL Server Data Types in the .NET Framework</span></span>](../../clr-integration-database-objects-types-net-framework/sql-server-data-types-in-the-net-framework.md)  
 <span data-ttu-id="dbf2d-129">Общие сведения о типах данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] и их эквивалентах в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dbf2d-129">An overview of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types and their .NET Framework equivalents.</span></span>  
  
 [<span data-ttu-id="dbf2d-130">Общие сведения о пользовательских атрибутах интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="dbf2d-130">Overview of CLR Integration Custom Attributes</span></span>](../../../database-engine/dev-guide/overview-of-clr-integration-custom-attributes.md)  
 <span data-ttu-id="dbf2d-131">Содержит сведения о пользовательских атрибутах интеграции со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="dbf2d-131">Provides information about CLR integration custom attributes.</span></span>  
  
 [<span data-ttu-id="dbf2d-132">Определяемые пользователем функции среды CLR</span><span class="sxs-lookup"><span data-stu-id="dbf2d-132">CLR User-Defined Functions</span></span>](../../clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md)  
 <span data-ttu-id="dbf2d-133">Описывает реализацию и использование различных типов функций CLR: возвращающих табличное значение, скалярных и определяемых пользователем агрегатных функций.</span><span class="sxs-lookup"><span data-stu-id="dbf2d-133">Describes how to implement and use the various types of CLR functions: table-valued, scalar, and user-defined aggregate functions.</span></span>  
  
 [<span data-ttu-id="dbf2d-134">Определяемые пользователем типы CLR</span><span class="sxs-lookup"><span data-stu-id="dbf2d-134">CLR User-Defined Types</span></span>](../../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md)  
 <span data-ttu-id="dbf2d-135">Показывает, как реализовать и использовать определяемые пользователем типы данных CLR.</span><span class="sxs-lookup"><span data-stu-id="dbf2d-135">Describes how to implement and use CLR user-defined types.</span></span>  
  
 [<span data-ttu-id="dbf2d-136">Хранимые процедуры CLR</span><span class="sxs-lookup"><span data-stu-id="dbf2d-136">CLR Stored Procedures</span></span>](../../../database-engine/dev-guide/clr-stored-procedures.md)  
 <span data-ttu-id="dbf2d-137">Показывает, как реализовать и использовать хранимые процедуры CLR.</span><span class="sxs-lookup"><span data-stu-id="dbf2d-137">Describes how to implement and use CLR stored procedures.</span></span>  
  
 [<span data-ttu-id="dbf2d-138">Триггеры CLR</span><span class="sxs-lookup"><span data-stu-id="dbf2d-138">CLR Triggers</span></span>](../../../database-engine/dev-guide/clr-triggers.md)  
 <span data-ttu-id="dbf2d-139">Показывает, как реализовать и использовать триггеры CLR.</span><span class="sxs-lookup"><span data-stu-id="dbf2d-139">Describes how to implement and use CLR triggers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbf2d-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="dbf2d-140">See Also</span></span>  
 [<span data-ttu-id="dbf2d-141">Общие сведения об интеграции&#41; среды CLR &#40;</span><span class="sxs-lookup"><span data-stu-id="dbf2d-141">Common Language Runtime &#40;CLR&#41; Integration Overview</span></span>](../common-language-runtime-integration-overview.md)  
  
  
