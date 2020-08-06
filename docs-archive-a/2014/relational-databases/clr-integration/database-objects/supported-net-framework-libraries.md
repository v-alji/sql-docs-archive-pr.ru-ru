---
title: Поддерживаемые библиотеки .NET Framework | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- common language runtime [SQL Server], .NET Framework libraries
- .NET Framework [CLR Integration]
ms.assetid: 417544ff-c25c-496e-add4-2f278f8a4911
author: rothja
ms.author: jroth
ms.openlocfilehash: 22f92e3eadccc869452cf35534f786724c8e259a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654343"
---
# <a name="supported-net-framework-libraries"></a><span data-ttu-id="8e14b-102">Поддерживаемые библиотеки платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8e14b-102">Supported .NET Framework Libraries</span></span>
  <span data-ttu-id="8e14b-103">Если среда CLR размещается в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], то появляется возможность разрабатывать на управляемом коде хранимые процедуры, триггеры, определяемые пользователем функции, определяемые пользователем типы и определяемые пользователем статистические функции.</span><span class="sxs-lookup"><span data-stu-id="8e14b-103">With the common language runtime (CLR) hosted in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], you can author stored procedures, triggers, user-defined functions, user-defined types, and user-defined aggregates in managed code.</span></span> <span data-ttu-id="8e14b-104">Функциональность, реализованная в библиотеках классов платформы .NET Framework, предоставляет доступ к предварительно построенным классам для операций со строками, сложных математических операций, доступа к файлам, шифрования и т. д.</span><span class="sxs-lookup"><span data-stu-id="8e14b-104">With the functionality found in the .NET Framework class libraries, you have access to pre-built classes that provide functionality for string manipulation, advanced math operations, file access, cryptography, and more.</span></span> <span data-ttu-id="8e14b-105">Доступ к этим классам легко получить из любой управляемой хранимой процедуры, определяемого пользователем типа, триггера, определяемой пользователем функции или определяемой пользователем статистической функции.</span><span class="sxs-lookup"><span data-stu-id="8e14b-105">These classes can be accessed from any managed stored procedure, user-defined type, trigger, user-defined function, or user-defined aggregate.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8e14b-106">При обслуживании или обновлении неподдерживаемых сборок в глобальном кэше сборок (GAC) ваш [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8e14b-106">If you service or upgrade unsupported assemblies in the global assembly cache (GAC), your [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8e14b-107">Если сборка существует и в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] интеграции со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="8e14b-107">If an assembly exists both in a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] CLR integration.</span></span> <span data-ttu-id="8e14b-108">При обслуживании или обновлении любых сборок в глобальном кэше сборок, которые также зарегистрированы в базе данных, в том числе неподдерживаемых сборок платформы .NET Framework, необходимо обеспечить обслуживание или обновление копии сборки в базах данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] с помощью инструкции `ALTER ASSEMBLY`.</span><span class="sxs-lookup"><span data-stu-id="8e14b-108">If you service or upgrade any assemblies in the GAC that are also registered in the database, including unsupported .NET Framework assemblies, make sure to also service or upgrade the copy of the assembly inside your [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] databases with the `ALTER ASSEMBLY` statement.</span></span> <span data-ttu-id="8e14b-109">Дополнительные сведения см. в [статье базы знаний 949080](https://support.microsoft.com/kb/949080).</span><span class="sxs-lookup"><span data-stu-id="8e14b-109">For more information, see [Knowledge Base article 949080](https://support.microsoft.com/kb/949080).</span></span>  
  
## <a name="supported-libraries"></a><span data-ttu-id="8e14b-110">Поддерживаемые библиотеки</span><span class="sxs-lookup"><span data-stu-id="8e14b-110">Supported Libraries</span></span>  
 <span data-ttu-id="8e14b-111">Начиная с [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)] имеет список поддерживаемых .NET Framework библиотек, проверенных на соответствие стандартам надежности и безопасности для взаимодействия с [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] загрузкой их непосредственно из глобального кэша сборок (GAC).</span><span class="sxs-lookup"><span data-stu-id="8e14b-111">Beginning with [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)] has a list of supported .NET Framework libraries, which have been tested to ensure that they meet reliability and security standards for interaction with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] loads them directly from the Global Assembly Cache (GAC).</span></span>  
  
 <span data-ttu-id="8e14b-112">Библиотеки и пространства имен, поддерживаемые интеграцией со средой CLR в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="8e14b-112">The libraries/namespaces supported by CLR integration in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] are:</span></span>  
  
-   <span data-ttu-id="8e14b-113">CustomMarshalers</span><span class="sxs-lookup"><span data-stu-id="8e14b-113">CustomMarshalers</span></span>  
  
-   <span data-ttu-id="8e14b-114">Microsoft.VisualBasic</span><span class="sxs-lookup"><span data-stu-id="8e14b-114">Microsoft.VisualBasic</span></span>  
  
-   <span data-ttu-id="8e14b-115">Microsoft.VisualC</span><span class="sxs-lookup"><span data-stu-id="8e14b-115">Microsoft.VisualC</span></span>  
  
-   <span data-ttu-id="8e14b-116">mscorlib</span><span class="sxs-lookup"><span data-stu-id="8e14b-116">mscorlib</span></span>  
  
-   <span data-ttu-id="8e14b-117">Система</span><span class="sxs-lookup"><span data-stu-id="8e14b-117">System</span></span>  
  
-   <span data-ttu-id="8e14b-118">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="8e14b-118">System.Configuration</span></span>  
  
-   <span data-ttu-id="8e14b-119">System.Data</span><span class="sxs-lookup"><span data-stu-id="8e14b-119">System.Data</span></span>  
  
-   <span data-ttu-id="8e14b-120">System.Data.OracleClient</span><span class="sxs-lookup"><span data-stu-id="8e14b-120">System.Data.OracleClient</span></span>  
  
-   <span data-ttu-id="8e14b-121">System.Data.SqlXml</span><span class="sxs-lookup"><span data-stu-id="8e14b-121">System.Data.SqlXml</span></span>  
  
-   <span data-ttu-id="8e14b-122">System.Deployment</span><span class="sxs-lookup"><span data-stu-id="8e14b-122">System.Deployment</span></span>  
  
-   <span data-ttu-id="8e14b-123">System.Security</span><span class="sxs-lookup"><span data-stu-id="8e14b-123">System.Security</span></span>  
  
-   <span data-ttu-id="8e14b-124">System.Transactions</span><span class="sxs-lookup"><span data-stu-id="8e14b-124">System.Transactions</span></span>  
  
-   <span data-ttu-id="8e14b-125">System.Web.Services</span><span class="sxs-lookup"><span data-stu-id="8e14b-125">System.Web.Services</span></span>  
  
-   <span data-ttu-id="8e14b-126">System.Xml</span><span class="sxs-lookup"><span data-stu-id="8e14b-126">System.Xml</span></span>  
  
-   <span data-ttu-id="8e14b-127">System.Core.dll</span><span class="sxs-lookup"><span data-stu-id="8e14b-127">System.Core.dll</span></span>  
  
-   <span data-ttu-id="8e14b-128">System.Xml.Linq.dll</span><span class="sxs-lookup"><span data-stu-id="8e14b-128">System.Xml.Linq.dll</span></span>  
  
## <a name="unsupported-libraries"></a><span data-ttu-id="8e14b-129">Неподдерживаемые библиотеки</span><span class="sxs-lookup"><span data-stu-id="8e14b-129">Unsupported Libraries</span></span>  
 <span data-ttu-id="8e14b-130">Неподдерживаемые библиотеки могут быть вызваны из управляемых хранимых процедур, триггеров, определяемых пользователем функций, определяемых пользователем типов и определяемых пользователем статистических функций.</span><span class="sxs-lookup"><span data-stu-id="8e14b-130">Unsupported libraries can still be called from your managed stored procedures, triggers, user-defined functions, user-defined types, and user-defined aggregates.</span></span> <span data-ttu-id="8e14b-131">Неподдерживаемые библиотеки должны быть сначала зарегистрированы в базе данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] с помощью инструкции `CREATE ASSEMBLY`, прежде чем ее можно будет использовать в пользовательском коде.</span><span class="sxs-lookup"><span data-stu-id="8e14b-131">The unsupported library must first be registered in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database, using the `CREATE ASSEMBLY` statement, before it can be used in your code.</span></span> <span data-ttu-id="8e14b-132">Любая неподдерживаемая библиотека, зарегистрированная и работающая на сервере, должна быть просмотрена и проверена в отношении безопасности и надежности.</span><span class="sxs-lookup"><span data-stu-id="8e14b-132">Any unsupported library that is registered and run on the server should be reviewed and tested for security and reliability.</span></span>  
  
 <span data-ttu-id="8e14b-133">Например, не поддерживается пространство имен `System.DirectoryServices`.</span><span class="sxs-lookup"><span data-stu-id="8e14b-133">For example, the `System.DirectoryServices` namespace is not supported.</span></span> <span data-ttu-id="8e14b-134">Необходимо зарегистрировать сборку System.DirectoryServices.dll с разрешением `UNSAFE`, прежде чем ее можно будет вызвать из пользовательского кода.</span><span class="sxs-lookup"><span data-stu-id="8e14b-134">You must register the System.DirectoryServices.dll assembly with `UNSAFE` permissions before you can call it from your code.</span></span> <span data-ttu-id="8e14b-135">Разрешение `UNSAFE` необходимо, так как классы в пространстве имен `System.DirectoryServices` не соответствуют требованиям для разрешений `SAFE` и `EXTERNAL_ACCESS`.</span><span class="sxs-lookup"><span data-stu-id="8e14b-135">The `UNSAFE` permission is necessary because classes in the `System.DirectoryServices` namespace do not meet the requirements for `SAFE` or `EXTERNAL_ACCESS`.</span></span> <span data-ttu-id="8e14b-136">Дополнительные сведения см. в разделе [ограничения модели программирования интеграции со средой CLR](clr-integration-programming-model-restrictions.md) и [Безопасность доступа к коду интеграции CLR](../security/clr-integration-code-access-security.md).</span><span class="sxs-lookup"><span data-stu-id="8e14b-136">For more information, see [CLR Integration Programming Model Restrictions](clr-integration-programming-model-restrictions.md) and [CLR Integration Code Access Security](../security/clr-integration-code-access-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e14b-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="8e14b-137">See Also</span></span>  
 <span data-ttu-id="8e14b-138">[Создание сборки](../assemblies/creating-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="8e14b-138">[Creating an Assembly](../assemblies/creating-an-assembly.md) </span></span>  
 <span data-ttu-id="8e14b-139">[Безопасность доступа к коду при интеграции со средой CLR](../security/clr-integration-code-access-security.md) </span><span class="sxs-lookup"><span data-stu-id="8e14b-139">[CLR Integration Code Access Security](../security/clr-integration-code-access-security.md) </span></span>  
 [<span data-ttu-id="8e14b-140">Ограничения модели программирования на основе интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="8e14b-140">CLR Integration Programming Model Restrictions</span></span>](clr-integration-programming-model-restrictions.md)  
  
  
