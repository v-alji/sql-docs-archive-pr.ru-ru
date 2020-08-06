---
title: Атрибуты защиты узла и программирование интеграции со средой CLR | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- host protection attributes [CLR integration]
- HostProtectionAttribute [CLR integration]
- common language runtime [SQL Server], host protection attributes
- disallowed types and members [CLR integration]
- common language runtime [SQL Server], disallowed types and members
- HPAs [CLR integration]
ms.assetid: 268078df-63ca-4c03-a8e7-7108bcea9697
author: rothja
ms.author: jroth
ms.openlocfilehash: 16ca1e4734e66b0eca85523764739e8f8b32634a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735365"
---
# <a name="host-protection-attributes-and-clr-integration-programming"></a><span data-ttu-id="32873-102">Атрибуты защиты узла и программирование средств интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="32873-102">Host Protection Attributes and CLR Integration Programming</span></span>
  <span data-ttu-id="32873-103">Среда CLR предоставляет механизм для аннотирования управляемых API, входящих в состав платформы .NET Framework, при помощи определенных атрибутов, которые могут потребоваться серверу CLR (такому как [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]), начиная с версии [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32873-103">The common language runtime (CLR) provides a mechanism to annotate managed application programming interfaces (APIs) that are part of the .NET Framework with certain attributes that may be of interest to a host of the CLR, such as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="32873-104">Примеры таких атрибутов защиты сервера включают следующее:</span><span class="sxs-lookup"><span data-stu-id="32873-104">Examples of such host protection attributes (HPAs) include:</span></span>  
  
-   <span data-ttu-id="32873-105">`SharedState`, который указывает, предоставляет ли API доступ к средствам создания или управления общим состоянием (например, к полям статического класса).</span><span class="sxs-lookup"><span data-stu-id="32873-105">`SharedState`, which indicates whether the API exposes the ability to create or manage shared state (for example, static class fields).</span></span>  
  
-   <span data-ttu-id="32873-106">`Synchronization`, который указывает, предоставляет ли API возможность выполнять синхронизацию потоков.</span><span class="sxs-lookup"><span data-stu-id="32873-106">`Synchronization`, which indicates whether the API exposes the ability to perform synchronization between threads.</span></span>  
  
-   <span data-ttu-id="32873-107">`ExternalProcessMgmt`, который указывает, предоставляет ли API способ управления процессом узла.</span><span class="sxs-lookup"><span data-stu-id="32873-107">`ExternalProcessMgmt`, which indicates whether the API exposes a way to control the host process.</span></span>  
  
 <span data-ttu-id="32873-108">C учетом этих атрибутов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] при помощи управления доступом для кода определяет список атрибутов защиты сервера, которые запрещены в размещенной среде.</span><span class="sxs-lookup"><span data-stu-id="32873-108">Given these attributes, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] specifies a list of HPAs that are disallowed in the hosted environment through code access security (CAS).</span></span> <span data-ttu-id="32873-109">Требования к CAS задаются одним из трех [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] наборов разрешений: `SAFE` , `EXTERNAL_ACCESS` или `UNSAFE` .</span><span class="sxs-lookup"><span data-stu-id="32873-109">The CAS requirements are specified by one of three [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permission sets: `SAFE`, `EXTERNAL_ACCESS`, or `UNSAFE`.</span></span> <span data-ttu-id="32873-110">Один из этих трех уровней безопасности задается с помощью инструкции `CREATE ASSEMBLY` при регистрации сборки на сервере.</span><span class="sxs-lookup"><span data-stu-id="32873-110">One of these three security levels is specified when the assembly is registered on the server, using the `CREATE ASSEMBLY` statement.</span></span> <span data-ttu-id="32873-111">В коде, выполняющемся с наборами разрешений `SAFE` или `EXTERNAL_ACCESS`, необходимо избегать использования элементов определенных типов, к которым применен атрибут `System.Security.Permissions.HostProtectionAttribute`.</span><span class="sxs-lookup"><span data-stu-id="32873-111">Code executing within the `SAFE` or `EXTERNAL_ACCESS` permission sets must avoid certain types or members that have the `System.Security.Permissions.HostProtectionAttribute` attribute applied.</span></span> <span data-ttu-id="32873-112">Дополнительные сведения см. в разделе [Создание сборки](../clr-integration/assemblies/creating-an-assembly.md) и [ограничения модели программирования интеграции со средой CLR](../clr-integration/database-objects/clr-integration-programming-model-restrictions.md).</span><span class="sxs-lookup"><span data-stu-id="32873-112">For more information, see [Creating an Assembly](../clr-integration/assemblies/creating-an-assembly.md) and [CLR Integration Programming Model Restrictions](../clr-integration/database-objects/clr-integration-programming-model-restrictions.md).</span></span>  
  
 <span data-ttu-id="32873-113">Атрибут `HostProtectionAttribute` представляет собой скорее не право доступа, а способ повышения надежности, поскольку он определяет конкретные конструкции в коде (типы или методы), которые могут быть запрещены сервером.</span><span class="sxs-lookup"><span data-stu-id="32873-113">The `HostProtectionAttribute` is not a security permission as much as a way to improve reliability, in that it identifies specific code constructs, either types or methods, that the host may disallow.</span></span> <span data-ttu-id="32873-114">В результате применения атрибута `HostProtectionAttribute` в действие вводится модель программирования, которая позволяет защитить стабильность сервера.</span><span class="sxs-lookup"><span data-stu-id="32873-114">The use of the `HostProtectionAttribute` enforces a programming model that helps protect the stability of the host.</span></span>  
  
## <a name="host-protection-attributes"></a><span data-ttu-id="32873-115">Атрибуты защиты сервера</span><span class="sxs-lookup"><span data-stu-id="32873-115">Host Protection Attributes</span></span>  
 <span data-ttu-id="32873-116">Атрибуты защиты сервера определяют типы или элементы, которые не подходят для серверной модели программирования и представляют следующие возрастающие уровни угрозы надежности:</span><span class="sxs-lookup"><span data-stu-id="32873-116">HPAs identify types or members that do not fit the host programming model and represent the following increasing levels of reliability threat:</span></span>  
  
-   <span data-ttu-id="32873-117">Во всем остальном являются безопасными.</span><span class="sxs-lookup"><span data-stu-id="32873-117">Are otherwise benign.</span></span>  
  
-   <span data-ttu-id="32873-118">Могут привести к дестабилизации управляемого сервером кода пользователя.</span><span class="sxs-lookup"><span data-stu-id="32873-118">Could lead to destabilization of server-managed user code.</span></span>  
  
-   <span data-ttu-id="32873-119">Могут привести к дестабилизации самого процесса сервера.</span><span class="sxs-lookup"><span data-stu-id="32873-119">Could lead to destabilization of the server process itself.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="32873-120">запрещает использование типа или члена, имеющего тип `HostProtectionAttribute` , который задает `System.Security.Permissions.HostProtectionResource` перечисление со значением `ExternalProcessMgmt` ,, `ExternalThreading` `MayLeakOnAbort` , `SecurityInfrastructure` ,, `SelfAffectingProcessMgmnt` `SelfAffectingThreading` , `SharedState` , `Synchronization` или `UI` .</span><span class="sxs-lookup"><span data-stu-id="32873-120">disallows the use of a type or member that has a `HostProtectionAttribute` that specifies a `System.Security.Permissions.HostProtectionResource` enumeration with a value of `ExternalProcessMgmt`, `ExternalThreading`, `MayLeakOnAbort`, `SecurityInfrastructure`, `SelfAffectingProcessMgmnt`, `SelfAffectingThreading`, `SharedState`, `Synchronization`, or `UI`.</span></span> <span data-ttu-id="32873-121">В силу этого сборки утрачивают возможность вызывать элементы, которые включают общее состояние, выполняют синхронизацию, могут вызвать утечку ресурсов при завершении или повлиять на целостность процесса [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32873-121">This prevents the assemblies from calling members that enable sharing state, perform synchronization, might cause a resource leak on termination, or affect the integrity of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process.</span></span>  
  
### <a name="disallowed-types-and-members"></a><span data-ttu-id="32873-122">Запрещенные типы и элементы</span><span class="sxs-lookup"><span data-stu-id="32873-122">Disallowed Types and Members</span></span>  
 <span data-ttu-id="32873-123">В следующих разделах приведены типы и элементы, значения `HostProtectionResource` которых запрещены в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32873-123">The following topics identify types and members whose `HostProtectionResource` values are disallowed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="32873-124">Списки в этих разделах содержат поддерживаемые сборки.</span><span class="sxs-lookup"><span data-stu-id="32873-124">The lists in these topics were generated from the supported assemblies.</span></span>  <span data-ttu-id="32873-125">Дополнительные сведения см. в разделе [supported .NET Framework librarys](../clr-integration/database-objects/supported-net-framework-libraries.md).</span><span class="sxs-lookup"><span data-stu-id="32873-125">For more information, see [Supported .NET Framework Libraries](../clr-integration/database-objects/supported-net-framework-libraries.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="32873-126">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="32873-126">In This Section</span></span>  
 [<span data-ttu-id="32873-127">Запрещенные типы и элементы в Microsoft.VisualBasic.dll</span><span class="sxs-lookup"><span data-stu-id="32873-127">Disallowed Types and Members in Microsoft.VisualBasic.dll</span></span>](disallowed-types-and-members-in-microsoft-visualbasic-dll.md)  
 <span data-ttu-id="32873-128">Приведены типы и элементы из файла Microsoft.VisualBasic.dll, для которых запрещены значения атрибутов защиты сервера.</span><span class="sxs-lookup"><span data-stu-id="32873-128">Lists the types and members in Microsoft.VisualBasic.dll whose HPA values are disallowed.</span></span>  
  
 [<span data-ttu-id="32873-129">Недопустимые типы и элементы в библиотеке mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="32873-129">Disallowed Types and Members in mscorlib.dll</span></span>](disallowed-types-and-members-in-mscorlib-dll.md)  
 <span data-ttu-id="32873-130">Приведены типы и элементы из файла mscorlib.dll, для которых запрещены значения атрибутов защиты сервера.</span><span class="sxs-lookup"><span data-stu-id="32873-130">Lists the types and members in mscorlib.dll whose HPA values are disallowed.</span></span>  
  
 [<span data-ttu-id="32873-131">Запрещенные типы и элементы в System.dll</span><span class="sxs-lookup"><span data-stu-id="32873-131">Disallowed Types and Members in System.dll</span></span>](disallowed-types-and-members-in-system-dll.md)  
 <span data-ttu-id="32873-132">Приведены типы и элементы из файла System.dll, для которых запрещены значения атрибутов защиты сервера.</span><span class="sxs-lookup"><span data-stu-id="32873-132">Lists the types and members in System.dll whose HPA values are disallowed.</span></span>  
  
 [<span data-ttu-id="32873-133">Недопустимые типы и элементы в библиотеке System.Data.dll</span><span class="sxs-lookup"><span data-stu-id="32873-133">Disallowed Types and Members in System.Data.dll</span></span>](disallowed-types-and-members-in-system-data-dll.md)  
 <span data-ttu-id="32873-134">Приведены типы и элементы из файла System.Data.dll, для которых запрещены значения атрибутов защиты сервера.</span><span class="sxs-lookup"><span data-stu-id="32873-134">Lists the types and members in System.Data.dll whose HPA values are disallowed.</span></span>  
  
 [<span data-ttu-id="32873-135">Недопустимые типы и элементы в библиотеке System.Core.dll</span><span class="sxs-lookup"><span data-stu-id="32873-135">Disallowed Types and Members in System.Core.dll</span></span>](disallowed-types-and-members-in-system-core-dll.md)  
 <span data-ttu-id="32873-136">Приведены типы и элементы из файла System.Core.dll, для которых запрещены значения атрибутов защиты сервера.</span><span class="sxs-lookup"><span data-stu-id="32873-136">Lists the types and members in System.Core.dll whose HPA values are disallowed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32873-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="32873-137">See Also</span></span>  
 <span data-ttu-id="32873-138">[Безопасность доступа к коду при интеграции со средой CLR](../clr-integration/security/clr-integration-code-access-security.md) </span><span class="sxs-lookup"><span data-stu-id="32873-138">[CLR Integration Code Access Security](../clr-integration/security/clr-integration-code-access-security.md) </span></span>  
 <span data-ttu-id="32873-139">[Ограничения модели программирования интеграции со средой CLR](../clr-integration/database-objects/clr-integration-programming-model-restrictions.md) </span><span class="sxs-lookup"><span data-stu-id="32873-139">[CLR Integration Programming Model Restrictions](../clr-integration/database-objects/clr-integration-programming-model-restrictions.md) </span></span>  
 [<span data-ttu-id="32873-140">Создание сборки</span><span class="sxs-lookup"><span data-stu-id="32873-140">Creating an Assembly</span></span>](../clr-integration/assemblies/creating-an-assembly.md)  
  
  
