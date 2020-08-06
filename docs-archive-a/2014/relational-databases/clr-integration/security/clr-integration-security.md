---
title: Безопасность интеграции со средой CLR | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- security [CLR integration]
- authorization [CLR integration]
- common language runtime [SQL Server], security
- database objects [CLR integration], security
ms.assetid: 05d7a471-c5d5-4730-b903-e4edc8157bb4
author: rothja
ms.author: jroth
ms.openlocfilehash: 0d99d32a061d8fe78a8ac3642a503cceb45f3809
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658297"
---
# <a name="clr-integration-security"></a><span data-ttu-id="36c67-102">Безопасность интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="36c67-102">CLR Integration Security</span></span>
  <span data-ttu-id="36c67-103">Модель безопасности среды CLR [!INCLUDE[ssNoVersion](../../../includes/dnprdnshort-md.md)] управляет доступом между различными типами объектов CLR и не-CLR объектами, выполняющимися в [!INCLUDE[ssNoVersion](../../../includes/tsql-md.md)] операторе или другом объекте CLR, выполняемом на сервере.</span><span class="sxs-lookup"><span data-stu-id="36c67-103">The security model of the [!INCLUDE[ssNoVersion](../../../includes/dnprdnshort-md.md)] common language runtime (CLR) manages and secures access between different types of CLR and non-CLR objects running within [!INCLUDE[ssNoVersion](../../../includes/tsql-md.md)] statement or another CLR object running in the server.</span></span> <span data-ttu-id="36c67-104">Вызовы между этими объектами называются связями.</span><span class="sxs-lookup"><span data-stu-id="36c67-104">The calls between objects are referred to as links.</span></span> <span data-ttu-id="36c67-105">Тип проверки безопасности, которая выполняется на этих объектах, зависит от типа связи.</span><span class="sxs-lookup"><span data-stu-id="36c67-105">The types of security checks performed on these objects depend on the types of links involved.</span></span>  
  
 <span data-ttu-id="36c67-106">Модель безопасности для интеграции со средой CLR решает следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="36c67-106">The CLR integration security model has the following goals:</span></span>  
  
-   <span data-ttu-id="36c67-107">По умолчанию запускает управляемый пользовательский код в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="36c67-107">By default, running managed user code on [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="36c67-108">Выполнение операций, потенциально небезопасных для устойчивости [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], должно быть защищено соответствующими разрешениями высокого уровня.</span><span class="sxs-lookup"><span data-stu-id="36c67-108">Performing operations that potentially compromise the robustness of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] should be protected by appropriate high-level permissions.</span></span>  
  
-   <span data-ttu-id="36c67-109">Управляемый пользовательский код не должен получать несанкционированный доступ к пользовательским данным или коду других пользователей в базе данных.</span><span class="sxs-lookup"><span data-stu-id="36c67-109">Managed user code should not gain unauthorized access to user data or other user code in the database.</span></span> <span data-ttu-id="36c67-110">Пользовательский программный код должен выполняться в контексте безопасности пользовательского сеанса, который его вызывает, и обладать нужными правами для этого контекста безопасности.</span><span class="sxs-lookup"><span data-stu-id="36c67-110">User-defined code should run under the security context of the user-session that invoked it, and with the correct privileges for that security context.</span></span>  
  
-   <span data-ttu-id="36c67-111">Должны существовать элементы управления, ограничивающие доступ пользовательского кода к любым ресурсам за пределами сервера. Он должен использоваться только для доступа к местным данным и для вычислений.</span><span class="sxs-lookup"><span data-stu-id="36c67-111">There should be controls for restricting user code from accessing any resources outside the server, using it strictly for local data access and computation.</span></span>  
  
-   <span data-ttu-id="36c67-112">Пользовательский программный код не должен получать несанкционированный доступ к системным ресурсам только потому, что он выполняется в процессе [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36c67-112">User-defined code should not be able to gain unauthorized access to system resources by virtue of running in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] process.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="36c67-113">с моделью безопасности на основе доступа к коду в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="36c67-113">with the code access-based security model of the CLR.</span></span> <span data-ttu-id="36c67-114">В этом разделе обсуждаются некоторые преимущества такого интегрированного подхода.</span><span class="sxs-lookup"><span data-stu-id="36c67-114">Some of the advantages of this combined approach to security are discussed in this section.</span></span>  
  
 <span data-ttu-id="36c67-115">В следующей таблице приводится список подразделов данного раздела.</span><span class="sxs-lookup"><span data-stu-id="36c67-115">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="36c67-116">Управление доступом для кода на основе интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="36c67-116">CLR Integration Code Access Security</span></span>](clr-integration-code-access-security.md)  
 <span data-ttu-id="36c67-117">Обсуждается модель безопасности для управляемого кода, основанная на управлении доступом для кода (CAS).</span><span class="sxs-lookup"><span data-stu-id="36c67-117">Discusses the code access security (CAS) model for managed code.</span></span>  
  
 [<span data-ttu-id="36c67-118">Атрибуты защиты узла и программирование средств интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="36c67-118">Host Protection Attributes and CLR Integration Programming</span></span>](../../clr-integration-security-host-protection-attributes/host-protection-attributes-and-clr-integration-programming.md)  
 <span data-ttu-id="36c67-119">Содержит сведения о значениях атрибутов защиты узла (host protection attribute, HPA), запрещенных в сборках SAFE и EXTERNAL_ACCESS.</span><span class="sxs-lookup"><span data-stu-id="36c67-119">Provides information about the host protection attribute (HPA) values that are disallowed in SAFE and EXTERNAL_ACCESS assemblies.</span></span>  
  
 [<span data-ttu-id="36c67-120">Ссылки в средствах безопасности интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="36c67-120">Links in CLR Integration Security</span></span>](../../../database-engine/dev-guide/links-in-clr-integration-security.md)  
 <span data-ttu-id="36c67-121">Описывает механизм вызова фрагментов пользовательского кода друг из друга в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36c67-121">Describes how pieces of user-code can call each other in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="36c67-122">Олицетворение и средства обеспечения безопасности при интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="36c67-122">Impersonation and CLR Integration Security</span></span>](../../../database-engine/dev-guide/impersonation-and-clr-integration-security.md)  
 <span data-ttu-id="36c67-123">Описывает доступ управляемого кода к внешним ресурсам с использованием олицетворения.</span><span class="sxs-lookup"><span data-stu-id="36c67-123">Discusses how managed code accesses external resources using impersonation.</span></span>  
  
 [<span data-ttu-id="36c67-124">Частично доверенный вызывающий код</span><span class="sxs-lookup"><span data-stu-id="36c67-124">Allowing Partially Trusted Callers</span></span>](../../../database-engine/dev-guide/allowing-partially-trusted-callers.md)  
 <span data-ttu-id="36c67-125">Описывает проблемы, возникающие, когда управляемый метод вызывает метод класса, содержащегося в другой сборке.</span><span class="sxs-lookup"><span data-stu-id="36c67-125">Discusses issues that arise when a managed method invokes a method in a class contained in another assembly.</span></span>  
  
 [<span data-ttu-id="36c67-126">Домены приложений и безопасность интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="36c67-126">Application Domains and CLR Integration Security</span></span>](../../../database-engine/dev-guide/application-domains-and-clr-integration-security.md)  
 <span data-ttu-id="36c67-127">Описывает загрузку сборок в домены приложений.</span><span class="sxs-lookup"><span data-stu-id="36c67-127">Describes how assemblies are loaded into application domains.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36c67-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="36c67-128">See Also</span></span>  
 [<span data-ttu-id="36c67-129">Управление сборками интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="36c67-129">Managing CLR Integration Assemblies</span></span>](../assemblies/managing-clr-integration-assemblies.md)  
  
  
