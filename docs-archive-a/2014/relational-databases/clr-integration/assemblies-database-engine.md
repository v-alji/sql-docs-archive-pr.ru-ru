---
title: Сборки (ядро СУБД) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- assemblies [CLR integration]
- assemblies [CLR integration], about assemblies
- managed code [SQL Server], assemblies
ms.assetid: 4b146437-3061-47f6-9e8c-26eeea10b54e
author: rothja
ms.author: jroth
ms.openlocfilehash: 7edb18ccfa9954fe52093f87948f956c2eacc1b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735362"
---
# <a name="assemblies-database-engine"></a><span data-ttu-id="617f4-102">Сборки (компонент Database Engine)</span><span class="sxs-lookup"><span data-stu-id="617f4-102">Assemblies (Database Engine)</span></span>
  <span data-ttu-id="617f4-103">В этом разделе содержатся сведения, которые помогут понять, сконструировать и применить сборки.</span><span class="sxs-lookup"><span data-stu-id="617f4-103">The topics in this section provide information to help you understand, design, and implement assemblies.</span></span>  
  
 <span data-ttu-id="617f4-104">Сборки — это файлы DLL, используемые в экземпляре служб [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] для развертывания функций, хранимых процедур, триггеров, определяемых пользователем агрегатов и определяемых пользователем типов, написанных на одном из языков управляемого кода, размещенных в среде CLR [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] , а не в [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="617f4-104">Assemblies are DLL files used in an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to deploy functions, stored procedures, triggers, user-defined aggregates, and user-defined types that are written in one of the managed code languages hosted by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] common language runtime (CLR), instead of in [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="617f4-105">Сборка в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] представляет собой объект, который ссылается на управляемый модуль приложений (DLL-файл), созданный в среде CLR [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="617f4-105">An assembly in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is an object that references a managed application module (.dll file) that was created in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] common language runtime.</span></span> <span data-ttu-id="617f4-106">Сборка содержит метаданные класса и управляемый код.</span><span class="sxs-lookup"><span data-stu-id="617f4-106">An assembly contains class metadata and managed code.</span></span> <span data-ttu-id="617f4-107">Передача сборки на экземпляр SQL Server — это первый шаг к созданию любого из следующих объектов базы данных.</span><span class="sxs-lookup"><span data-stu-id="617f4-107">Uploading an assembly to an instance of SQL Server is the first step toward creating any of the following database objects:</span></span>  
  
-   <span data-ttu-id="617f4-108">Функции среды CLR.</span><span class="sxs-lookup"><span data-stu-id="617f4-108">CLR functions.</span></span> <span data-ttu-id="617f4-109">Дополнительные сведения см. в разделе [Создание функций CLR](../user-defined-functions/create-clr-functions.md).</span><span class="sxs-lookup"><span data-stu-id="617f4-109">For more information, see [Create CLR Functions](../user-defined-functions/create-clr-functions.md).</span></span>  
  
-   <span data-ttu-id="617f4-110">Хранимые процедуры среды CLR.</span><span class="sxs-lookup"><span data-stu-id="617f4-110">CLR stored procedures.</span></span> <span data-ttu-id="617f4-111">Дополнительные сведения см. в разделе [хранимые процедуры CLR](../../database-engine/dev-guide/clr-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="617f4-111">For more information, see [CLR Stored Procedures](../../database-engine/dev-guide/clr-stored-procedures.md).</span></span>  
  
-   <span data-ttu-id="617f4-112">Триггеры среды CLR.</span><span class="sxs-lookup"><span data-stu-id="617f4-112">CLR triggers.</span></span> <span data-ttu-id="617f4-113">Дополнительные сведения см. в разделе [Создание триггеров CLR](../triggers/create-clr-triggers.md).</span><span class="sxs-lookup"><span data-stu-id="617f4-113">For more information, see [Create CLR Triggers](../triggers/create-clr-triggers.md).</span></span>  
  
-   <span data-ttu-id="617f4-114">Определяемые пользователем агрегатные функции.</span><span class="sxs-lookup"><span data-stu-id="617f4-114">User-defined aggregate functions.</span></span> <span data-ttu-id="617f4-115">Дополнительные сведения см. в разделе [Создание определяемых пользователем статистических функций](../user-defined-functions/create-user-defined-aggregates.md).</span><span class="sxs-lookup"><span data-stu-id="617f4-115">For more information, see [Create User-defined Aggregates](../user-defined-functions/create-user-defined-aggregates.md).</span></span>  
  
-   <span data-ttu-id="617f4-116">Определяемые пользователем типы.</span><span class="sxs-lookup"><span data-stu-id="617f4-116">User-defined types.</span></span> <span data-ttu-id="617f4-117">Дополнительные сведения см. в статье [Использование пользовательских типов](../native-client/features/using-user-defined-types.md).</span><span class="sxs-lookup"><span data-stu-id="617f4-117">For more information, see [Using User-Defined Types](../native-client/features/using-user-defined-types.md).</span></span>  
  
 <span data-ttu-id="617f4-118">В [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] сборки выполняют следующие функции.</span><span class="sxs-lookup"><span data-stu-id="617f4-118">Assemblies perform the following functions in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="617f4-119">Содержат управляемый код, который выполняет функциональность одного или нескольких объектов базы данных среды CLR, перечисленных ранее.</span><span class="sxs-lookup"><span data-stu-id="617f4-119">Contain the managed code that runs the functionality of one or more of the CLR database objects previously listed.</span></span>  
  
-   <span data-ttu-id="617f4-120">Содержат метаданные, которые включают в себя номер версии и культуру сборки, дополнительный открытый ключ, который уникально идентифицирует список классов сборки, методы, определенные в сборке, и архитектуру процессора сборки.</span><span class="sxs-lookup"><span data-stu-id="617f4-120">Contain metadata that includes the version number and culture of the assembly, an optional public key that uniquely identifies the list of classes of the assembly, the methods that are defined in the assembly, and the processor architecture of the assembly.</span></span>  
  
-   <span data-ttu-id="617f4-121">Управляют степенью, к которой управляемый код может получить доступ внешних ресурсов с помощью регулирования разрешений кода доступа.</span><span class="sxs-lookup"><span data-stu-id="617f4-121">Manage the degree to which managed code can access outside resources by regulating code access permissions.</span></span>  
  
-   <span data-ttu-id="617f4-122">Содержат метаданные о зависимостях от других сборок, на которые ссылается сборка.</span><span class="sxs-lookup"><span data-stu-id="617f4-122">Contain metadata about dependencies on other assemblies that are referenced by the assembly.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="617f4-123">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="617f4-123">In This Section</span></span>  
  
|<span data-ttu-id="617f4-124">Раздел</span><span class="sxs-lookup"><span data-stu-id="617f4-124">Topic</span></span>|<span data-ttu-id="617f4-125">Описание</span><span class="sxs-lookup"><span data-stu-id="617f4-125">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="617f4-126">Конструирование сборок</span><span class="sxs-lookup"><span data-stu-id="617f4-126">Designing Assemblies</span></span>](assemblies-designing.md)|<span data-ttu-id="617f4-127">Объясняет, что необходимо учесть перед созданием сборки.</span><span class="sxs-lookup"><span data-stu-id="617f4-127">Explains what you have to consider before creating an assembly.</span></span> <span data-ttu-id="617f4-128">Включает в себя упаковку сборок, разрешения кода доступа и другие ограничения.</span><span class="sxs-lookup"><span data-stu-id="617f4-128">This includes packaging assemblies, code access permissions, and other restrictions.</span></span>|  
|[<span data-ttu-id="617f4-129">Реализация сборок</span><span class="sxs-lookup"><span data-stu-id="617f4-129">Implementing Assemblies</span></span>](assemblies-implementing.md)|<span data-ttu-id="617f4-130">Объясняет, как правильно создать и удалить сборку, как и когда необходимо изменить сборку, а также как получить метаданные о сборке.</span><span class="sxs-lookup"><span data-stu-id="617f4-130">Explains how to create and drop assemblies, how and when to modify assemblies, and how to retrieve metadata about assemblies.</span></span>|  
|[<span data-ttu-id="617f4-131">Получение сведений о сборках</span><span class="sxs-lookup"><span data-stu-id="617f4-131">Getting Information About Assemblies</span></span>](assemblies-getting-information.md)|<span data-ttu-id="617f4-132">Перечисляет представления и функции каталога, которые могут запрашиваться для метаданных о сборках.</span><span class="sxs-lookup"><span data-stu-id="617f4-132">Lists the catalog views and functions that can be queried for metadata about assemblies.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="617f4-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="617f4-133">See Also</span></span>  
 [<span data-ttu-id="617f4-134">Основные понятия о программировании интеграции со средой (CLR)</span><span class="sxs-lookup"><span data-stu-id="617f4-134">Common Language Runtime &#40;CLR&#41; Integration Programming Concepts</span></span>](common-language-runtime-clr-integration-programming-concepts.md)  
  
  
