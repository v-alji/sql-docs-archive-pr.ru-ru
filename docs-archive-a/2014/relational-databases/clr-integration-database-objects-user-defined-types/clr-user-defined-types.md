---
title: Определяемые пользователем типы данных CLR | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- validation [CLR integration]
- types [CLR integration]
- UserDefined serialization format [CLR integration]
- null values [CLR integration]
- serialization
- Native serialization format [CLR integration]
- databases [CLR integration]
- building database objects [CLR integration], user-defined types
- user-defined types [CLR integration]
- common language runtime [SQL Server], user-defined types
- UDTs [CLR integration]
- database objects [CLR integration], user-defined types
- turning on CLR functionality
- customizing UDT expression return types [CLR integration]
- UDTs [CLR integration], about UDTs
- comparing UDT values
- annotations [CLR integration]
- user-defined types [CLR integration], about UDTs
- variables [CLR integration]
- invoking UDT methods
- indexes [CLR integration]
ms.assetid: 27c4889b-c543-47a8-a630-ad06804f92df
author: rothja
ms.author: jroth
ms.openlocfilehash: e4e19323eeac9e0a1148924543f71aa7de5619b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668925"
---
# <a name="clr-user-defined-types"></a><span data-ttu-id="33d4f-102">Определяемые пользователем типы данных CLR</span><span class="sxs-lookup"><span data-stu-id="33d4f-102">CLR User-Defined Types</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="33d4f-103">позволяет создавать объекты базы данных, которые программируются по сборке, созданной в среде CLR платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="33d4f-103">gives you the ability to create database objects that are programmed against an assembly created in the.NET Framework common language runtime (CLR).</span></span> <span data-ttu-id="33d4f-104">Объекты базы данных, которые способны пользоваться преимуществами многофункциональной модели программирования, предоставляемыми средой CLR, содержат триггеры, хранимые процедуры, функции, агрегатные функции и типы.</span><span class="sxs-lookup"><span data-stu-id="33d4f-104">Database objects that can take advantage of the rich programming model provided by the CLR include triggers, stored procedures, functions, aggregate functions, and types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="33d4f-105">По умолчанию возможность выполнять код CLR в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] отключена.</span><span class="sxs-lookup"><span data-stu-id="33d4f-105">The ability to execute CLR code is set to OFF by default in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="33d4f-106">Среду CLR можно включить с помощью системной хранимой процедуры **sp_configure** .</span><span class="sxs-lookup"><span data-stu-id="33d4f-106">The CLR can be enabled by using the **sp_configure** system stored procedure.</span></span>  
  
 <span data-ttu-id="33d4f-107">Начиная с [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , можно использовать определяемые пользователем типы для расширения системы скалярных типов сервера, что позволяет хранить объекты среды CLR в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] базе данных.</span><span class="sxs-lookup"><span data-stu-id="33d4f-107">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], you can use user-defined types (UDTs) to extend the scalar type system of the server, enabling storage of CLR objects in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="33d4f-108">Определяемые пользователем типы могут состоять из несколько элементов, а их поведение может отличаться от обычных типов данных, обозначенных псевдонимами, каждый из которых состоит из одного системного типа данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33d4f-108">UDTs can contain multiple elements and can have behaviors, differentiating them from the traditional alias data types which consist of a single [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system data type.</span></span>  
  
 <span data-ttu-id="33d4f-109">Система обращается к определяемым пользователем типам как к единым объектам, поэтому их использование для сложных типов данных может негативно отразиться на производительности.</span><span class="sxs-lookup"><span data-stu-id="33d4f-109">Because UDTs are accessed by the system as a whole, their use for complex data types may negatively impact performance.</span></span> <span data-ttu-id="33d4f-110">Для моделирования сложных данных лучше подходят обычные строки и таблицы.</span><span class="sxs-lookup"><span data-stu-id="33d4f-110">Complex data is generally best modeled using traditional rows and tables.</span></span> <span data-ttu-id="33d4f-111">В [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] определяемые пользователем типы хорошо подходят для представления следующих данных:</span><span class="sxs-lookup"><span data-stu-id="33d4f-111">UDTs in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are well suited to the following:</span></span>  
  
-   <span data-ttu-id="33d4f-112">Значения даты, времени, валюты и расширенные числовые типы</span><span class="sxs-lookup"><span data-stu-id="33d4f-112">Date, time, currency, and extended numeric types</span></span>  
  
-   <span data-ttu-id="33d4f-113">Данные геопространственных приложений</span><span class="sxs-lookup"><span data-stu-id="33d4f-113">Geospatial applications</span></span>  
  
-   <span data-ttu-id="33d4f-114">Закодированные или зашифрованные данные</span><span class="sxs-lookup"><span data-stu-id="33d4f-114">Encoded or encrypted data</span></span>  
  
 <span data-ttu-id="33d4f-115">Процесс разработки определяемых пользователем типов в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] состоит из следующих шагов.</span><span class="sxs-lookup"><span data-stu-id="33d4f-115">The process of developing UDTs in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consists of the following steps:</span></span>  
  
1.  <span data-ttu-id="33d4f-116">**Кодирование и построение сборки, определяющей определяемый пользователем тип.**</span><span class="sxs-lookup"><span data-stu-id="33d4f-116">**Code and build the assembly that defines the UDT.**</span></span> <span data-ttu-id="33d4f-117">Определяемые пользователем типы определяются с помощью любого языка, поддерживаемого средой CLR платформы .NET Framework и создающего проверяемый код.</span><span class="sxs-lookup"><span data-stu-id="33d4f-117">UDTs are defined using any of the languages supported by the.NET Framework common language runtime (CLR) that produce verifiable code.</span></span> <span data-ttu-id="33d4f-118">Среди таких языков Visual C# и Visual Basic .NET.</span><span class="sxs-lookup"><span data-stu-id="33d4f-118">This includes Visual C# and Visual Basic .NET.</span></span> <span data-ttu-id="33d4f-119">Доступ к данным предоставляется как к полям и свойствам класса или структуры платформы .NET Framework, а поведение определяется методами класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="33d4f-119">The data is exposed as fields and properties of a .NET Framework class or structure, and behaviors are defined by methods of the class or structure.</span></span>  
  
2.  <span data-ttu-id="33d4f-120">**Регистрирует сборку.**</span><span class="sxs-lookup"><span data-stu-id="33d4f-120">**Register the assembly.**</span></span> <span data-ttu-id="33d4f-121">Развертывание определяемых пользователем типов в проекте базы данных может быть выполнено с помощью пользовательского интерфейса Visual Studio или с помощью инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE ASSEMBLY, которая копирует сборку, содержащую класс или структуру, в базу данных.</span><span class="sxs-lookup"><span data-stu-id="33d4f-121">UDTs can be deployed through the Visual Studio user interface in a database project, or by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE ASSEMBLY statement, which copies the assembly containing the class or structure into a database.</span></span>  
  
3.  <span data-ttu-id="33d4f-122">**Создание определяемого пользователем типа в SQL Server.**</span><span class="sxs-lookup"><span data-stu-id="33d4f-122">**Create the UDT in SQL Server.**</span></span> <span data-ttu-id="33d4f-123">После загрузки сборки в базу данных определяемый пользователем тип создается с помощью инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)], а доступ к элементам класса или структуры представляется как к элементам этого типа.</span><span class="sxs-lookup"><span data-stu-id="33d4f-123">Once an assembly is loaded into a host database, you use the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE TYPE statement to create a UDT and expose the members of the class or structure as members of the UDT.</span></span> <span data-ttu-id="33d4f-124">Определяемые пользователем типы существуют только в контексте одной базы данных, а после регистрации они не имеют зависимостей от внешних файлов, из которых были созданы.</span><span class="sxs-lookup"><span data-stu-id="33d4f-124">UDTs exist only in the context of a single database, and, once registered, have no dependencies on the external files from which they were created.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="33d4f-125">До выхода версии [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] определяемые пользователем типы, созданные на основе сборок платформы .NET Framework, не поддерживались.</span><span class="sxs-lookup"><span data-stu-id="33d4f-125">Before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], UDTs created from .NET Framework assemblies were not supported.</span></span> <span data-ttu-id="33d4f-126">Однако вы по-прежнему можете использовать [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] псевдонимы типов данных с помощью **sp_addtype**.</span><span class="sxs-lookup"><span data-stu-id="33d4f-126">However, you can still use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alias data types by using **sp_addtype**.</span></span> <span data-ttu-id="33d4f-127">Синтаксис CREATE TYPE можно использовать для создания собственных определяемых пользователем типов данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и определяемых пользователем типов.</span><span class="sxs-lookup"><span data-stu-id="33d4f-127">The CREATE TYPE syntax can be used for creating both native [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user-defined data types and UDTs.</span></span>  
  
4.  <span data-ttu-id="33d4f-128">**Создание таблиц, переменных или параметров с помощью определяемого пользователем типа** Начиная с [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , определяемый пользователем тип может использоваться в качестве определения столбца таблицы, в виде переменной в [!INCLUDE[tsql](../../includes/tsql-md.md)] пакете или в качестве аргумента [!INCLUDE[tsql](../../includes/tsql-md.md)] функции или хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="33d4f-128">**Create tables, variables, or parameters using the UDT** Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], a user-defined type can be used as the column definition of a table, as a variable in a [!INCLUDE[tsql](../../includes/tsql-md.md)] batch, or as an argument of a [!INCLUDE[tsql](../../includes/tsql-md.md)] function or stored procedure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="33d4f-129">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="33d4f-129">In This Section</span></span>  
 [<span data-ttu-id="33d4f-130">Создание определяемого пользователем типа</span><span class="sxs-lookup"><span data-stu-id="33d4f-130">Creating a User-Defined Type</span></span>](creating-user-defined-types.md)  
 <span data-ttu-id="33d4f-131">Описывает способ создания определяемых пользователем типов.</span><span class="sxs-lookup"><span data-stu-id="33d4f-131">Describes how to create UDTs.</span></span>  
  
 [<span data-ttu-id="33d4f-132">Регистрация определяемых пользователем типов в SQL Server</span><span class="sxs-lookup"><span data-stu-id="33d4f-132">Registering User-Defined Types in SQL Server</span></span>](registering-user-defined-types-in-sql-server.md)  
 <span data-ttu-id="33d4f-133">Описывает, как регистрировать определяемые пользователем типы в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и как управлять ими.</span><span class="sxs-lookup"><span data-stu-id="33d4f-133">Describes how to register and manage UDTs in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="33d4f-134">Работа с определяемыми пользователем типами в SQL Server</span><span class="sxs-lookup"><span data-stu-id="33d4f-134">Working with User-Defined Types in SQL Server</span></span>](working-with-user-defined-types-in-sql-server.md)  
 <span data-ttu-id="33d4f-135">Описывает способ создания запросов при помощи определяемых пользователем типов.</span><span class="sxs-lookup"><span data-stu-id="33d4f-135">Describes how to create queries using UDTs.</span></span>  
  
 [<span data-ttu-id="33d4f-136">Доступ к определяемым пользователем типам в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="33d4f-136">Accessing User-Defined Types in ADO.NET</span></span>](accessing-user-defined-types-in-ado-net.md)  
 <span data-ttu-id="33d4f-137">Описывает способ работы с определяемыми пользователем типами при помощи поставщика данных .NET Framework для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="33d4f-137">Describes how to work with UDTs using the .NET Framework Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in ADO.NET.</span></span>  
  
  
