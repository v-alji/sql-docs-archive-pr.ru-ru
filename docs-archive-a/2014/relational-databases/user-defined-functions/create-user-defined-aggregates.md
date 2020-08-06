---
title: Создание определяемых пользователем агрегатных функций | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- aggregate functions [SQL Server], user-defined
- user-defined functions [CLR integration]
ms.assetid: c278b746-6323-4b32-b460-239915acc067
author: rothja
ms.author: jroth
ms.openlocfilehash: c91179cb194bbfb79e8e7a8476e9725877b88afa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749680"
---
# <a name="create-user-defined-aggregates"></a><span data-ttu-id="abc55-102">Создание определяемых пользователем агрегатных функций</span><span class="sxs-lookup"><span data-stu-id="abc55-102">Create User-defined Aggregates</span></span>
  <span data-ttu-id="abc55-103">Можно создать объект базы данных внутри [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , который запрограммирован в сборке среды CLR.</span><span class="sxs-lookup"><span data-stu-id="abc55-103">You can create a database object inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is programmed in a CLR assembly.</span></span> <span data-ttu-id="abc55-104">В число объектов базы данных, способных эффективно использовать предоставляемую средой CLR многофункциональную модель программирования, входят триггеры, хранимые процедуры, функции, агрегатные функции и типы.</span><span class="sxs-lookup"><span data-stu-id="abc55-104">Database objects that can leverage the rich programming model provided by the CLR include triggers, stored procedures, functions, aggregate functions, and types.</span></span>  
  
 <span data-ttu-id="abc55-105">Подобно встроенным агрегатным функциям, предоставленным в [!INCLUDE[tsql](../../includes/tsql-md.md)], пользовательские агрегатные функции производят вычисление в ряде значений и возвращают одиночное значение.</span><span class="sxs-lookup"><span data-stu-id="abc55-105">Like the built-in aggregate functions provided in [!INCLUDE[tsql](../../includes/tsql-md.md)], user-defined aggregate functions perform a calculation on a set of values and return a single value.</span></span>  
  
 <span data-ttu-id="abc55-106">Создание пользовательской агрегатной функции в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] включает в себя следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="abc55-106">Creating a user-defined aggregate function in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] involves the following steps:</span></span>  
  
-   <span data-ttu-id="abc55-107">Определите пользовательскую агрегатную функцию как класс на языке, поддерживаемом платформой [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET.</span><span class="sxs-lookup"><span data-stu-id="abc55-107">Define the user-defined aggregate function as a class in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework-supported language.</span></span> <span data-ttu-id="abc55-108">Дополнительные сведения о программировании определяемых пользователем статистических функций в среде CLR см. в статье [Пользовательские агрегатные функции среды CLR](../clr-integration-database-objects-user-defined-functions/clr-user-defined-aggregates.md).</span><span class="sxs-lookup"><span data-stu-id="abc55-108">For more information about how to program user-defined aggregates in the CLR, see [CLR User-Defined Aggregates](../clr-integration-database-objects-user-defined-functions/clr-user-defined-aggregates.md).</span></span> <span data-ttu-id="abc55-109">Скомпилируйте этот класс для построения сборки среды CLR, используя соответствующий языку компилятор.</span><span class="sxs-lookup"><span data-stu-id="abc55-109">Compile this class to build a CLR assembly using the appropriate language compiler.</span></span>  
  
-   <span data-ttu-id="abc55-110">Зарегистрируйте сборку в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с помощью инструкции CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="abc55-110">Register the assembly in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the CREATE ASSEMBLY statement.</span></span> <span data-ttu-id="abc55-111">Дополнительные сведения о работе со сборками в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] см. в разделе [Сборки (компонент Database Engine)](../clr-integration/assemblies-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="abc55-111">For more information about assemblies in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Assemblies &#40;Database Engine&#41;](../clr-integration/assemblies-database-engine.md).</span></span>  
  
-   <span data-ttu-id="abc55-112">Создайте пользовательское статистическое выражение, которое ссылается на зарегистрированную сборку, используя инструкцию CREATE AGGREGATE.</span><span class="sxs-lookup"><span data-stu-id="abc55-112">Create the user-defined aggregate that references the registered assembly using the CREATE AGGREGATE statement.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="abc55-113">Развертывание проекта SQL Server в [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] регистрирует сборку в базе данных, указанной для проекта.</span><span class="sxs-lookup"><span data-stu-id="abc55-113">Deploying a SQL Server Project in [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] registers an assembly in the database that was specified for the project.</span></span> <span data-ttu-id="abc55-114">Развертывание проекта также создает пользовательские статистические функции в базе данных для всех классов, которые могут иметь атрибут `SqlUserDefinedAggregate`.</span><span class="sxs-lookup"><span data-stu-id="abc55-114">Deploying the project also creates a user-defined aggregate in the database for all class definitions annotated with the `SqlUserDefinedAggregate` attribute.</span></span> <span data-ttu-id="abc55-115">Дополнительные сведения см. в статье [Deploying CLR Database Objects](../clr-integration/deploying-clr-database-objects.md).</span><span class="sxs-lookup"><span data-stu-id="abc55-115">For more information, see [Deploying CLR Database Objects](../clr-integration/deploying-clr-database-objects.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="abc55-116">Возможность [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выполнять код CLR по умолчанию отключена.</span><span class="sxs-lookup"><span data-stu-id="abc55-116">The ability of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to execute CLR code is off by default.</span></span> <span data-ttu-id="abc55-117">Можно создавать, изменять и удалять объекты базы данных, которые ссылаются на модули управляемого кода, но эти ссылки не будут выполнены в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , пока параметр [clr enabled](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md) не получит значение True с помощью хранимой процедуры [sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="abc55-117">You can create, alter and drop database objects that reference managed code modules, but these references will not execute in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unless the [clr enabled Option](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md) is enabled using [sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql).</span></span>  
  
 <span data-ttu-id="abc55-118">**Создание, изменение или удаление сборки**</span><span class="sxs-lookup"><span data-stu-id="abc55-118">**To create, modify, or drop an assembly**</span></span>  
  
-   [<span data-ttu-id="abc55-119">CREATE ASSEMBLY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="abc55-119">CREATE ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-assembly-transact-sql)  
  
-   [<span data-ttu-id="abc55-120">ALTER ASSEMBLY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="abc55-120">ALTER ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-assembly-transact-sql)  
  
-   [<span data-ttu-id="abc55-121">DROP ASSEMBLY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="abc55-121">DROP ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-assembly-transact-sql)  
  
 <span data-ttu-id="abc55-122">**Создание пользовательской статистической функции**</span><span class="sxs-lookup"><span data-stu-id="abc55-122">**To create a user-defined aggregate**</span></span>  
  
-   [<span data-ttu-id="abc55-123">CREATE AGGREGATE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="abc55-123">CREATE AGGREGATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-aggregate-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="abc55-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="abc55-124">See Also</span></span>  
 [<span data-ttu-id="abc55-125">Основные понятия о программировании интеграции со средой (CLR)</span><span class="sxs-lookup"><span data-stu-id="abc55-125">Common Language Runtime &#40;CLR&#41; Integration Programming Concepts</span></span>](../clr-integration/common-language-runtime-clr-integration-programming-concepts.md)  
  
  
