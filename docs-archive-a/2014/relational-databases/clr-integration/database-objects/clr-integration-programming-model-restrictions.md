---
title: Ограничения модели программирования интеграции со средой CLR | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- common language runtime [SQL Server], programming model restrictions
- assemblies [CLR integration], CREATE ASSEMBLY checks
- programming model restrictions [CLR integration]
- assemblies [CLR integration], runtime checks
ms.assetid: 2446afc2-9d21-42d3-9847-7733d3074de9
author: rothja
ms.author: jroth
ms.openlocfilehash: 01a32e1460ad9c49061b39b1bdc419c7cd2f1342
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654347"
---
# <a name="clr-integration-programming-model-restrictions"></a><span data-ttu-id="0987d-102">Ограничения модели программирования на основе интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="0987d-102">CLR Integration Programming Model Restrictions</span></span>
  <span data-ttu-id="0987d-103">При построении управляемой хранимой процедуры или другого управляемого объекта базы данных выполняются определенные проверки кода, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] выполняющие проверки сборки управляемого кода при ее первой регистрации в базе данных с помощью `CREATE ASSEMBLY` инструкции, а также во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="0987d-103">When you are building a managed stored procedure or other managed database object, there are certain code checks performed by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] performs checks on the managed code assembly when it is first registered in the database, using the `CREATE ASSEMBLY` statement, and also at runtime.</span></span> <span data-ttu-id="0987d-104">Управляемый код проверяется также во время выполнения, поскольку в сборке могут быть кодовые пути, фактически не достижимые во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="0987d-104">The managed code is also checked at runtime because in an assembly there may be code paths that may never actually be reached at runtime.</span></span>  <span data-ttu-id="0987d-105">Благодаря этому достигается гибкость при регистрации сборок сторонних производителей, поскольку сборка не блокируется из-за наличия в ней «небезопасного» кода, предназначенного для выполнения в клиентской среде, но никогда не выполняющегося во внутрипроцессной среде CLR.</span><span class="sxs-lookup"><span data-stu-id="0987d-105">This provides flexibility for registering third party assemblies, especially, so that an assembly wouldn't be blocked where there is 'unsafe' code designed to run in a client environment but would never be executed in the hosted CLR.</span></span> <span data-ttu-id="0987d-106">Требования, которым должен удовлетворять управляемый код, зависят от того, зарегистрирована ли сборка как `SAFE` , `EXTERNAL_ACCESS` , или, которая является максимально допустимой `UNSAFE` `SAFE` и приведена ниже.</span><span class="sxs-lookup"><span data-stu-id="0987d-106">The requirements that the managed code must meet depend on whether the assembly is registered as `SAFE`, `EXTERNAL_ACCESS`, or `UNSAFE`, `SAFE` being the strictest, and are listed below.</span></span>  
  
 <span data-ttu-id="0987d-107">Кроме ограничений, которые распространяются на сборки управляемого кода, им также предоставляются права доступа к коду.</span><span class="sxs-lookup"><span data-stu-id="0987d-107">In addition to restrictions being placed on the managed code assemblies, there are also code security permissions that are granted.</span></span> <span data-ttu-id="0987d-108">Среда CLR поддерживает модель безопасности, называемую управлением доступом для кода (CAS).</span><span class="sxs-lookup"><span data-stu-id="0987d-108">The common language runtime (CLR) supports a security model called code access security (CAS) for managed code.</span></span> <span data-ttu-id="0987d-109">В этой модели разрешения предоставляются сборкам на основе идентификатора кода.</span><span class="sxs-lookup"><span data-stu-id="0987d-109">In this model, permissions are granted to assemblies based on the identity of the code.</span></span> <span data-ttu-id="0987d-110">Сборки `SAFE`, `EXTERNAL_ACCESS` и `UNSAFE` имеют различные разрешения CAS.</span><span class="sxs-lookup"><span data-stu-id="0987d-110">`SAFE`, `EXTERNAL_ACCESS`, and `UNSAFE` assemblies have different CAS permissions.</span></span> <span data-ttu-id="0987d-111">Дополнительные сведения см. в статье [Безопасность доступа к коду для интеграции со средой CLR](../security/clr-integration-code-access-security.md).</span><span class="sxs-lookup"><span data-stu-id="0987d-111">For more information, see [CLR Integration Code Access Security](../security/clr-integration-code-access-security.md).</span></span>  
  
## <a name="create-assembly-checks"></a><span data-ttu-id="0987d-112">Проверки CREATE ASSEMBLY</span><span class="sxs-lookup"><span data-stu-id="0987d-112">CREATE ASSEMBLY Checks</span></span>  
 <span data-ttu-id="0987d-113">При запуске инструкции `CREATE ASSEMBLY` для каждого уровня безопасности выполняются следующие проверки.</span><span class="sxs-lookup"><span data-stu-id="0987d-113">When the `CREATE ASSEMBLY` statement is run, the following checks are performed for each security level.</span></span>  <span data-ttu-id="0987d-114">В случае неудачного завершения любой из проверок выполнение инструкции `CREATE ASSEMBLY` оканчивается неудачей с возвратом сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="0987d-114">If any check fails, `CREATE ASSEMBLY` will fail with an error message.</span></span>  
  
### <a name="global-any-security-level"></a><span data-ttu-id="0987d-115">Глобальная проверка (любой уровень безопасности)</span><span class="sxs-lookup"><span data-stu-id="0987d-115">Global (any security level)</span></span>  
 <span data-ttu-id="0987d-116">Все сборки, на которые имеются ссылки, должны удовлетворять одному или нескольким из следующих критериев.</span><span class="sxs-lookup"><span data-stu-id="0987d-116">All referenced assemblies must meet one or more of the following criteria:</span></span>  
  
-   <span data-ttu-id="0987d-117">Сборка уже зарегистрирована в базе данных.</span><span class="sxs-lookup"><span data-stu-id="0987d-117">The assembly is already registered in the database.</span></span>  
  
-   <span data-ttu-id="0987d-118">Сборка принадлежит к числу поддерживаемых сборок.</span><span class="sxs-lookup"><span data-stu-id="0987d-118">The assembly is one of the supported assemblies.</span></span> <span data-ttu-id="0987d-119">Дополнительные сведения см. в разделе [supported .NET Framework librarys](supported-net-framework-libraries.md).</span><span class="sxs-lookup"><span data-stu-id="0987d-119">For more information, see [Supported .NET Framework Libraries](supported-net-framework-libraries.md).</span></span>  
  
-   <span data-ttu-id="0987d-120">Вы используете `CREATE ASSEMBLY FROM` \* \<location> ,\* а все сборки, на которые имеются ссылки, и их зависимости доступны в *\<location>* .</span><span class="sxs-lookup"><span data-stu-id="0987d-120">You are using `CREATE ASSEMBLY FROM`*\<location>,* and all the referenced assemblies and their dependencies are available in *\<location>*.</span></span>  
  
-   <span data-ttu-id="0987d-121">Вы используете `CREATE ASSEMBLY FROM` \* \<bytes ...> ,\* и все ссылки указываются с помощью разделенных пробелами байтов.</span><span class="sxs-lookup"><span data-stu-id="0987d-121">You are using `CREATE ASSEMBLY FROM`*\<bytes ...>,* and all the references are specified via space separated bytes.</span></span>  
  
### <a name="external_access"></a><span data-ttu-id="0987d-122">EXTERNAL_ACCESS</span><span class="sxs-lookup"><span data-stu-id="0987d-122">EXTERNAL_ACCESS</span></span>  
 <span data-ttu-id="0987d-123">Все сборки `EXTERNAL_ACCESS` должны отвечать следующим требованиям.</span><span class="sxs-lookup"><span data-stu-id="0987d-123">All `EXTERNAL_ACCESS` assemblies must meet the following criteria:</span></span>  
  
-   <span data-ttu-id="0987d-124">Статические поля не используются для хранения информации.</span><span class="sxs-lookup"><span data-stu-id="0987d-124">Static fields are not used to store information.</span></span> <span data-ttu-id="0987d-125">Допускаются статические поля только для чтения.</span><span class="sxs-lookup"><span data-stu-id="0987d-125">Read-only static fields are allowed.</span></span>  
  
-   <span data-ttu-id="0987d-126">Тест PEVerify пройден успешно.</span><span class="sxs-lookup"><span data-stu-id="0987d-126">PEVerify test is passed.</span></span> <span data-ttu-id="0987d-127">Средство проверки PEVerify (peverify.exe), проверяющее соответствие кода MSIL и связанных с ним метаданных требованиям безопасности, поставляется в комплекте с пакетом разработчика .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="0987d-127">The PEVerify tool (peverify.exe), which checks that the MSIL code and associated metadata meet type safety requirements, is provided with the .NET Framework SDK.</span></span>  
  
-   <span data-ttu-id="0987d-128">Синхронизация (например, с помощью класса `SynchronizationAttribute`) не используется.</span><span class="sxs-lookup"><span data-stu-id="0987d-128">Synchronization, for example with the `SynchronizationAttribute` class, is not used.</span></span>  
  
-   <span data-ttu-id="0987d-129">Методы завершения не используются.</span><span class="sxs-lookup"><span data-stu-id="0987d-129">Finalizer methods are not used.</span></span>  
  
 <span data-ttu-id="0987d-130">В сборках `EXTERNAL_ACCESS` запрещено использовать следующие настраиваемые атрибуты.</span><span class="sxs-lookup"><span data-stu-id="0987d-130">The following custom attributes are disallowed in `EXTERNAL_ACCESS` assemblies:</span></span>  
  
-   <span data-ttu-id="0987d-131">System.ContextStaticAttribute</span><span class="sxs-lookup"><span data-stu-id="0987d-131">System.ContextStaticAttribute</span></span>  
  
-   <span data-ttu-id="0987d-132">System.MTAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="0987d-132">System.MTAThreadAttribute</span></span>  
  
-   <span data-ttu-id="0987d-133">System.Runtime.CompilerServices.MethodImplAttribute</span><span class="sxs-lookup"><span data-stu-id="0987d-133">System.Runtime.CompilerServices.MethodImplAttribute</span></span>  
  
-   <span data-ttu-id="0987d-134">System.Runtime.CompilerServices.CompilationRelaxationsAttribute</span><span class="sxs-lookup"><span data-stu-id="0987d-134">System.Runtime.CompilerServices.CompilationRelaxationsAttribute</span></span>  
  
-   <span data-ttu-id="0987d-135">System.Runtime.Remoting.Contexts.ContextAttribute</span><span class="sxs-lookup"><span data-stu-id="0987d-135">System.Runtime.Remoting.Contexts.ContextAttribute</span></span>  
  
-   <span data-ttu-id="0987d-136">System.Runtime.Remoting.Contexts.SynchronizationAttribute</span><span class="sxs-lookup"><span data-stu-id="0987d-136">System.Runtime.Remoting.Contexts.SynchronizationAttribute</span></span>  
  
-   <span data-ttu-id="0987d-137">System.Runtime.InteropServices.DllImportAttribute</span><span class="sxs-lookup"><span data-stu-id="0987d-137">System.Runtime.InteropServices.DllImportAttribute</span></span>  
  
-   <span data-ttu-id="0987d-138">System.Security.Permissions.CodeAccessSecurityAttribute</span><span class="sxs-lookup"><span data-stu-id="0987d-138">System.Security.Permissions.CodeAccessSecurityAttribute</span></span>  
  
-   <span data-ttu-id="0987d-139">System.Security.SuppressUnmanagedCodeSecurityAttribute</span><span class="sxs-lookup"><span data-stu-id="0987d-139">System.Security.SuppressUnmanagedCodeSecurityAttribute</span></span>  
  
-   <span data-ttu-id="0987d-140">System.Security.UnverifiableCodeAttribute</span><span class="sxs-lookup"><span data-stu-id="0987d-140">System.Security.UnverifiableCodeAttribute</span></span>  
  
-   <span data-ttu-id="0987d-141">System.STAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="0987d-141">System.STAThreadAttribute</span></span>  
  
-   <span data-ttu-id="0987d-142">System.ThreadStaticAttribute</span><span class="sxs-lookup"><span data-stu-id="0987d-142">System.ThreadStaticAttribute</span></span>  
  
### <a name="safe"></a><span data-ttu-id="0987d-143">SAFE</span><span class="sxs-lookup"><span data-stu-id="0987d-143">SAFE</span></span>  
  
-   <span data-ttu-id="0987d-144">Проверяются все условия, относящиеся к сборкам `EXTERNAL_ACCESS`.</span><span class="sxs-lookup"><span data-stu-id="0987d-144">All `EXTERNAL_ACCESS` assembly conditions are checked.</span></span>  
  
## <a name="runtime-checks"></a><span data-ttu-id="0987d-145">Проверки времени выполнения</span><span class="sxs-lookup"><span data-stu-id="0987d-145">Runtime Checks</span></span>  
 <span data-ttu-id="0987d-146">Во время выполнения код сборки проверяется на соответствие ряду условий.</span><span class="sxs-lookup"><span data-stu-id="0987d-146">At runtime, the code assembly is checked for the following conditions.</span></span> <span data-ttu-id="0987d-147">Если имеет место хотя бы одно из этих условий, выполнение управляемого кода не разрешается и активизируется исключение.</span><span class="sxs-lookup"><span data-stu-id="0987d-147">If any of these conditions are found, the managed code will not be allowed to run and an exception will be thrown.</span></span>  
  
### <a name="unsafe"></a><span data-ttu-id="0987d-148">UNSAFE</span><span class="sxs-lookup"><span data-stu-id="0987d-148">UNSAFE</span></span>  
 <span data-ttu-id="0987d-149">Не допускается загрузка сборки явным образом путем вызова `System.Reflection.Assembly.Load()` метода из массива байтов или неявного использования `Reflection.Emit` пространства имен.</span><span class="sxs-lookup"><span data-stu-id="0987d-149">Loading an assembly-either explicitly by calling the `System.Reflection.Assembly.Load()` method from a byte array, or implicitly through the use of `Reflection.Emit` namespace-is not permitted.</span></span>  
  
### <a name="external_access"></a><span data-ttu-id="0987d-150">EXTERNAL_ACCESS</span><span class="sxs-lookup"><span data-stu-id="0987d-150">EXTERNAL_ACCESS</span></span>  
 <span data-ttu-id="0987d-151">Проверяются все условия `UNSAFE`.</span><span class="sxs-lookup"><span data-stu-id="0987d-151">All `UNSAFE` conditions are checked.</span></span>  
  
 <span data-ttu-id="0987d-152">Не допускаются все типы и методы, помеченные следующими значениями атрибутов защиты сервера в поддерживаемом списке сборок.</span><span class="sxs-lookup"><span data-stu-id="0987d-152">All types and methods annotated with the following host protection attribute (HPA) values in the supported list of assemblies are disallowed.</span></span>  
  
-   <span data-ttu-id="0987d-153">SelfAffectingProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="0987d-153">SelfAffectingProcessMgmt</span></span>  
  
-   <span data-ttu-id="0987d-154">SelfAffectingThreading</span><span class="sxs-lookup"><span data-stu-id="0987d-154">SelfAffectingThreading</span></span>  
  
-   <span data-ttu-id="0987d-155">Синхронизация</span><span class="sxs-lookup"><span data-stu-id="0987d-155">Synchronization</span></span>  
  
-   <span data-ttu-id="0987d-156">SharedState</span><span class="sxs-lookup"><span data-stu-id="0987d-156">SharedState</span></span>  
  
-   <span data-ttu-id="0987d-157">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="0987d-157">ExternalProcessMgmt</span></span>  
  
-   <span data-ttu-id="0987d-158">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="0987d-158">ExternalThreading</span></span>  
  
-   <span data-ttu-id="0987d-159">SecurityInfrastructure</span><span class="sxs-lookup"><span data-stu-id="0987d-159">SecurityInfrastructure</span></span>  
  
-   <span data-ttu-id="0987d-160">MayLeakOnAbort</span><span class="sxs-lookup"><span data-stu-id="0987d-160">MayLeakOnAbort</span></span>  
  
-   <span data-ttu-id="0987d-161">ИП</span><span class="sxs-lookup"><span data-stu-id="0987d-161">UI</span></span>  
  
 <span data-ttu-id="0987d-162">Дополнительные сведения о hPa и списке запрещенных типов и членов в поддерживаемых сборках см. в разделе [атрибуты защиты узла и программирование интеграции со средой CLR](../../clr-integration-security-host-protection-attributes/host-protection-attributes-and-clr-integration-programming.md).</span><span class="sxs-lookup"><span data-stu-id="0987d-162">For more information about HPAs and a list of disallowed types and members in the supported assemblies, see [Host Protection Attributes and CLR Integration Programming](../../clr-integration-security-host-protection-attributes/host-protection-attributes-and-clr-integration-programming.md).</span></span>  
  
### <a name="safe"></a><span data-ttu-id="0987d-163">SAFE</span><span class="sxs-lookup"><span data-stu-id="0987d-163">SAFE</span></span>  
 <span data-ttu-id="0987d-164">Проверяются все условия `EXTERNAL_ACCESS`.</span><span class="sxs-lookup"><span data-stu-id="0987d-164">All `EXTERNAL_ACCESS` conditions are checked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0987d-165">См. также:</span><span class="sxs-lookup"><span data-stu-id="0987d-165">See Also</span></span>  
 <span data-ttu-id="0987d-166">[Поддерживаемые библиотеки .NET Framework](supported-net-framework-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="0987d-166">[Supported .NET Framework Libraries](supported-net-framework-libraries.md) </span></span>  
 <span data-ttu-id="0987d-167">[Безопасность доступа к коду при интеграции со средой CLR](../security/clr-integration-code-access-security.md) </span><span class="sxs-lookup"><span data-stu-id="0987d-167">[CLR Integration Code Access Security](../security/clr-integration-code-access-security.md) </span></span>  
 <span data-ttu-id="0987d-168">[Атрибуты защиты узла и программирование интеграции со средой CLR](../../clr-integration-security-host-protection-attributes/host-protection-attributes-and-clr-integration-programming.md) </span><span class="sxs-lookup"><span data-stu-id="0987d-168">[Host Protection Attributes and CLR Integration Programming](../../clr-integration-security-host-protection-attributes/host-protection-attributes-and-clr-integration-programming.md) </span></span>  
 [<span data-ttu-id="0987d-169">Создание сборки</span><span class="sxs-lookup"><span data-stu-id="0987d-169">Creating an Assembly</span></span>](../assemblies/creating-an-assembly.md)  
  
  
