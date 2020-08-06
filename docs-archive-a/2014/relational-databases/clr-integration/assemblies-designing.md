---
title: Проектирование сборок | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- designing assemblies [SQL Server]
- assemblies [CLR integration], designing
ms.assetid: 9c07f706-6508-41aa-a4d7-56ce354f9061
author: rothja
ms.author: jroth
ms.openlocfilehash: 785ab80a529140a52ec18ef96ccaaeafd03698cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735358"
---
# <a name="designing-assemblies"></a><span data-ttu-id="d9179-102">Конструирование сборок</span><span class="sxs-lookup"><span data-stu-id="d9179-102">Designing Assemblies</span></span>
  <span data-ttu-id="d9179-103">В этом подразделе описываются факторы, которые следует принять во внимание при конструировании сборок:</span><span class="sxs-lookup"><span data-stu-id="d9179-103">This topic describes the following factors you should consider when you design assemblies:</span></span>  
  
-   <span data-ttu-id="d9179-104">компоновка сборок;</span><span class="sxs-lookup"><span data-stu-id="d9179-104">Packaging assemblies</span></span>  
  
-   <span data-ttu-id="d9179-105">управление безопасностью сборок;</span><span class="sxs-lookup"><span data-stu-id="d9179-105">Managing assembly security</span></span>  
  
-   <span data-ttu-id="d9179-106">ограничения на сборки.</span><span class="sxs-lookup"><span data-stu-id="d9179-106">Restrictions on assemblies</span></span>  
  
## <a name="packaging-assemblies"></a><span data-ttu-id="d9179-107">Компоновка сборок</span><span class="sxs-lookup"><span data-stu-id="d9179-107">Packaging Assemblies</span></span>  
 <span data-ttu-id="d9179-108">Сборка может содержать в своих классах и методах функциональность более чем одной подпрограммы или типа [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d9179-108">An assembly can contain functionality for more than one [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] routine or type in its classes and methods.</span></span> <span data-ttu-id="d9179-109">В большинстве случаев имеет смысл компоновать в одну сборку функциональность подпрограмм, выполняющих связанные функции, особенно если данные подпрограммы относятся к классам, методы которых вызывают друг друга.</span><span class="sxs-lookup"><span data-stu-id="d9179-109">Most of the time, it makes sense to package the functionality of routines that perform related functions within the same assembly, especially if these routines share classes whose methods call one another.</span></span> <span data-ttu-id="d9179-110">Например, классы, выполняющие задачи по управлению вводом данных для триггеров и хранимых процедур среды CLR, могут быть скомпонованы в одной сборке.</span><span class="sxs-lookup"><span data-stu-id="d9179-110">For example, classes that perform data entry management tasks for common language runtime (CLR) triggers and CLR stored procedures can be packaged in the same assembly.</span></span> <span data-ttu-id="d9179-111">Это связано с тем, что методы данных классов с большей вероятностью будут вызывать друг друга, а не методы менее связных задач.</span><span class="sxs-lookup"><span data-stu-id="d9179-111">This is because the methods for these classes are more likely to call each other than those of less related tasks.</span></span>  
  
 <span data-ttu-id="d9179-112">При компоновке кода в сборку надо учитывать следующее.</span><span class="sxs-lookup"><span data-stu-id="d9179-112">When you are packaging code into assembly, you should consider the following:</span></span>  
  
-   <span data-ttu-id="d9179-113">Определяемые пользователем типы данных CLR и индексы, зависящие от определяемых пользователем функций среды CLR, могут вызвать появление в базе данных материализованных данных, зависящих от сборки.</span><span class="sxs-lookup"><span data-stu-id="d9179-113">CLR user-defined types and indexes that depend on CLR user-defined functions can cause persisted data to be in the database that depends on the assembly.</span></span> <span data-ttu-id="d9179-114">Часто изменение кода сборки является более сложным, если в базе данных присутствуют материализованные данные, зависящие от сборки.</span><span class="sxs-lookup"><span data-stu-id="d9179-114">Modifying the code of an assembly is frequently more complex when there is persisted data that depends on the assembly in the database.</span></span> <span data-ttu-id="d9179-115">Таким образом, в общем случае лучше отделять код, от которого зависят материализованные данные (такие как определяемые пользователем типы и индексы, использующие определяемые пользователем функции), от кода, от которого не зависят никакие материализованные данные.</span><span class="sxs-lookup"><span data-stu-id="d9179-115">Therefore, it is generally better to separate code on which persisted data dependencies rely (such as user-defined types and indexes using user-defined functions) from code that does not have such persisted data dependencies.</span></span> <span data-ttu-id="d9179-116">Дополнительные сведения см. в статьях [Реализация сборок](assemblies-implementing.md) и [ALTER ASSEMBLY &#40;&#41;Transact-SQL ](/sql/t-sql/statements/alter-assembly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d9179-116">For more information, see [Implementing Assemblies](assemblies-implementing.md) and [ALTER ASSEMBLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-assembly-transact-sql).</span></span>  
  
-   <span data-ttu-id="d9179-117">Если часть управляемого кода требует разрешения более высокого уровня, лучше поместить данный код в отдельную сборку, отдельно от кода, не требующего этого разрешения.</span><span class="sxs-lookup"><span data-stu-id="d9179-117">If a piece of managed code requires higher permission, it is better to separate that code into a separate assembly from code that does not require higher permission.</span></span>  
  
## <a name="managing-assembly-security"></a><span data-ttu-id="d9179-118">Управление безопасностью сборок</span><span class="sxs-lookup"><span data-stu-id="d9179-118">Managing Assembly Security</span></span>  
 <span data-ttu-id="d9179-119">Можно управлять доступом сборки к ресурсам, защищенным системой безопасности доступа к коду платформы .NET, когда она выполняет управляемый код.</span><span class="sxs-lookup"><span data-stu-id="d9179-119">You can control how much an assembly can access resources protected by .NET Code Access Security when it runs managed code.</span></span> <span data-ttu-id="d9179-120">Это можно сделать, указав один из трех наборов разрешений при создании или изменении сборки: "Сейф", "EXTERNAL_ACCESS" или "ненадежный".</span><span class="sxs-lookup"><span data-stu-id="d9179-120">You do this by specifying one of three permission sets when you create or modify an assembly: SAFE, EXTERNAL_ACCESS, or UNSAFE.</span></span>  
  
### <a name="safe"></a><span data-ttu-id="d9179-121">SAFE</span><span class="sxs-lookup"><span data-stu-id="d9179-121">SAFE</span></span>  
 <span data-ttu-id="d9179-122">Набор SAFE является набором разрешений по умолчанию и наиболее ограничен.</span><span class="sxs-lookup"><span data-stu-id="d9179-122">SAFE is the default permission set and it is the most restrictive.</span></span> <span data-ttu-id="d9179-123">Код, выполняемый в сборке с набором разрешений SAFE, не может получить доступ к внешним системным ресурсам, таким как файлы, сеть, переменные среды или реестр.</span><span class="sxs-lookup"><span data-stu-id="d9179-123">Code run by an assembly with SAFE permissions cannot access external system resources such as files, the network, environment variables, or the registry.</span></span> <span data-ttu-id="d9179-124">Код с набором SAFE может получать доступ к данным из местных баз данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] или производить вычисления и обрабатывать бизнес-логику, для которых доступ к ресурсам за пределами местных баз данных не нужен.</span><span class="sxs-lookup"><span data-stu-id="d9179-124">SAFE code can access data from the local [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] databases or perform computations and business logic that do not involve accessing resources outside the local databases.</span></span>  
  
 <span data-ttu-id="d9179-125">Большинство сборок выполняют вычисления и задачи управления данными, не имея доступа к ресурсам за пределами [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d9179-125">Most assemblies perform computation and data management tasks without having to access resources outside [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d9179-126">Таким образом, набор SAFE рекомендуется в качестве набора разрешений для сборки.</span><span class="sxs-lookup"><span data-stu-id="d9179-126">Therefore, we recommend SAFE as the assembly permission set.</span></span>  
  
### <a name="external_access"></a><span data-ttu-id="d9179-127">EXTERNAL_ACCESS</span><span class="sxs-lookup"><span data-stu-id="d9179-127">EXTERNAL_ACCESS</span></span>  
 <span data-ttu-id="d9179-128">Набор EXTERNAL_ACCESS позволяет сборкам получать доступ к определенным внешним системным ресурсам, таким как файлы, сети, веб-службы, переменные среды и реестр.</span><span class="sxs-lookup"><span data-stu-id="d9179-128">EXTERNAL_ACCESS allows for assemblies to access certain external system resources such as files, networks, Web services, environmental variables, and the registry.</span></span> <span data-ttu-id="d9179-129">Сборки с набором EXTERNAL_ACCESS могут создавать только пользователи [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] с разрешениями EXTERNAL ACCESS.</span><span class="sxs-lookup"><span data-stu-id="d9179-129">Only [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logins with EXTERNAL ACCESS permissions can create EXTERNAL_ACCESS assemblies.</span></span>  
  
 <span data-ttu-id="d9179-130">Сборки с наборами SAFE и EXTERNAL_ACCESS могут содержать только код, который является проверяемым типизированным кодом.</span><span class="sxs-lookup"><span data-stu-id="d9179-130">SAFE and EXTERNAL_ACCESS assemblies can contain only code that is verifiably type-safe.</span></span> <span data-ttu-id="d9179-131">Это означает, что данные сборки могут получать доступ к классам только через правильно определенные точки входа, доступные для определения типа.</span><span class="sxs-lookup"><span data-stu-id="d9179-131">This means that these assemblies can only access classes through well-defined entry points that are valid for the type definition.</span></span> <span data-ttu-id="d9179-132">Таким образом, они не могут произвольно обращаться к буферам памяти, не принадлежащим коду.</span><span class="sxs-lookup"><span data-stu-id="d9179-132">Therefore, they cannot arbitrarily access memory buffers not owned by the code.</span></span> <span data-ttu-id="d9179-133">К тому же они не могут выполнять операции, которые могли бы вызвать отрицательные последствия для устойчивости процесса [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d9179-133">Additionally, they cannot perform operations that might have an adverse effect on the robustness of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] process.</span></span>  
  
### <a name="unsafe"></a><span data-ttu-id="d9179-134">UNSAFE</span><span class="sxs-lookup"><span data-stu-id="d9179-134">UNSAFE</span></span>  
 <span data-ttu-id="d9179-135">Набор UNSAFE предоставляет сборкам неограниченный доступ к ресурсам как внутри, так и за пределами [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d9179-135">UNSAFE gives assemblies unrestricted access to resources, both within and outside [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d9179-136">Код, выполняемый в сборке с набором разрешений UNSAFE, может вызвать неуправляемый код.</span><span class="sxs-lookup"><span data-stu-id="d9179-136">Code that is running from within an UNSAFE assembly can call unmanaged code.</span></span>  
  
 <span data-ttu-id="d9179-137">Кроме того, выбор набора UNSAFE позволяет коду в сборке выполнять операции, которые рассматриваются средством проверки среды CLR как нетипичные.</span><span class="sxs-lookup"><span data-stu-id="d9179-137">Also, specifying UNSAFE allows for the code in the assembly to perform operations that are considered type-unsafe by the CLR verifier.</span></span> <span data-ttu-id="d9179-138">Эти операции потенциально могут получать бесконтрольный доступ к буферам памяти в пространстве процесса [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d9179-138">These operations can potentially access memory buffers in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] process space in an uncontrolled manner.</span></span> <span data-ttu-id="d9179-139">Сборки UNSAFE потенциально могут подвергнуть опасности систему безопасности [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] или среды CLR.</span><span class="sxs-lookup"><span data-stu-id="d9179-139">UNSAFE assemblies can also potentially subvert the security system of either [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or the common language runtime.</span></span> <span data-ttu-id="d9179-140">Разрешения UNSAFE должны предоставляться только высоконадежным сборкам опытными разработчиками или администраторами.</span><span class="sxs-lookup"><span data-stu-id="d9179-140">UNSAFE permissions should be granted only to highly trusted assemblies by experienced developers or administrators.</span></span> <span data-ttu-id="d9179-141">Только члены предопределенной роли сервера **sysadmin** могут создавать ненадежные сборки.</span><span class="sxs-lookup"><span data-stu-id="d9179-141">Only members of the **sysadmin** fixed server role can create UNSAFE assemblies.</span></span>  
  
## <a name="restrictions-on-assemblies"></a><span data-ttu-id="d9179-142">Ограничения на сборки</span><span class="sxs-lookup"><span data-stu-id="d9179-142">Restrictions on Assemblies</span></span>  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="d9179-143">налагает определенные ограничения на управляемый код в сборках, делая их выполнение надежным и масштабируемым.</span><span class="sxs-lookup"><span data-stu-id="d9179-143">puts certain restrictions on managed code in assemblies to make sure that they can run in a reliable and scalable manner.</span></span> <span data-ttu-id="d9179-144">Это означает, что некоторые операции, способные нарушить устойчивость сервера, не разрешены в сборках с набором разрешений SAFE и EXTERNAL_ACCESS.</span><span class="sxs-lookup"><span data-stu-id="d9179-144">This means that certain operations that can compromise the robustness of the server are not permitted in SAFE and EXTERNAL_ACCESS assemblies.</span></span>  
  
### <a name="disallowed-custom-attributes"></a><span data-ttu-id="d9179-145">Запрещенные пользовательские атрибуты</span><span class="sxs-lookup"><span data-stu-id="d9179-145">Disallowed Custom Attributes</span></span>  
 <span data-ttu-id="d9179-146">Сборки не могут иметь следующих пользовательских атрибутов.</span><span class="sxs-lookup"><span data-stu-id="d9179-146">Assemblies cannot be annotated with the following custom attributes:</span></span>  
  
```  
System.ContextStaticAttribute  
System.MTAThreadAttribute  
System.Runtime.CompilerServices.MethodImplAttribute  
System.Runtime.CompilerServices.CompilationRelaxationsAttribute  
System.Runtime.Remoting.Contexts.ContextAttribute  
System.Runtime.Remoting.Contexts.SynchronizationAttribute  
System.Runtime.InteropServices.DllImportAttribute   
System.Security.Permissions.CodeAccessSecurityAttribute  
System.STAThreadAttribute  
System.ThreadStaticAttribute  
```  
  
 <span data-ttu-id="d9179-147">Кроме того, сборки с набором разрешений SAFE и EXTERNAL_ACCESS не могут иметь следующих пользовательских атрибутов.</span><span class="sxs-lookup"><span data-stu-id="d9179-147">Additionally, SAFE and EXTERNAL_ACCESS assemblies cannot be annotated with the following custom attributes:</span></span>  
  
```  
System.Security.SuppressUnmanagedCodeSecurityAttribute  
System.Security.UnverifiableCodeAttribute  
```  
  
### <a name="disallowed-net-framework-apis"></a><span data-ttu-id="d9179-148">Неразрешенные API-интерфейсы платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d9179-148">Disallowed .NET Framework APIs</span></span>  
 <span data-ttu-id="d9179-149">Любой [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] API, помеченный одним из запрещенных **HostProtectionAttributes** , не может быть вызван из сборок из безопасного и EXTERNAL_ACCESS.</span><span class="sxs-lookup"><span data-stu-id="d9179-149">Any [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] API that is annotated with one of the disallowed **HostProtectionAttributes** cannot be called from SAFE and EXTERNAL_ACCESS assemblies.</span></span>  
  
```  
eSelfAffectingProcessMgmt  
eSelfAffectingThreading  
eSynchronization  
eSharedState   
eExternalProcessMgmt  
eExternalThreading  
eSecurityInfrastructure  
eMayLeakOnAbort  
eUI  
```  
  
### <a name="supported-net-framework-assemblies"></a><span data-ttu-id="d9179-150">Поддержка сборок платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d9179-150">Supported .NET Framework Assemblies</span></span>  
 <span data-ttu-id="d9179-151">Любая сборка, на которую ссылается пользовательская сборка, должна загружаться в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] с помощью инструкции CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="d9179-151">Any assembly that is referenced by your custom assembly must be loaded into [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using CREATE ASSEMBLY.</span></span> <span data-ttu-id="d9179-152">Следующие сборки [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] уже загружены в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], и поэтому на них могут ссылаться пользовательские сборки без использования инструкции CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="d9179-152">The following [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] assemblies are already loaded into [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and, therefore, can be referenced by custom assemblies without having to use CREATE ASSEMBLY.</span></span>  
  
```  
custommarshallers.dll  
Microsoft.visualbasic.dll  
Microsoft.visualc.dll  
mscorlib.dll  
system.data.dll  
System.Data.SqlXml.dll  
system.dll  
system.security.dll  
system.web.services.dll  
system.xml.dll  
System.Transactions  
System.Data.OracleClient  
System.Configuration  
```  
  
## <a name="see-also"></a><span data-ttu-id="d9179-153">См. также:</span><span class="sxs-lookup"><span data-stu-id="d9179-153">See Also</span></span>  
 <span data-ttu-id="d9179-154">[Сборки &#40;ядро СУБД&#41;](../../relational-databases/clr-integration/assemblies-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="d9179-154">[Assemblies &#40;Database Engine&#41;](../../relational-databases/clr-integration/assemblies-database-engine.md) </span></span>  
 [<span data-ttu-id="d9179-155">Безопасность интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="d9179-155">CLR Integration Security</span></span>](security/clr-integration-security.md)  
  
  
