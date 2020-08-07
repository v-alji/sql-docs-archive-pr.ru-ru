---
title: Недопустимые типы и члены в Microsoft.VisualBasic.dll | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- host protection attributes [CLR integration]
- common language runtime [SQL Server], host protection attributes
ms.assetid: 45f55646-4bf1-4493-9f72-d1363c9a9ac6
author: rothja
ms.author: jroth
ms.openlocfilehash: ab42e2a58dec340d32c182dc9baeda37c456104f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730741"
---
# <a name="disallowed-types-and-members-in-microsoftvisualbasicdll"></a><span data-ttu-id="fc626-102">Запрещенные типы и элементы в Microsoft.VisualBasic.dll</span><span class="sxs-lookup"><span data-stu-id="fc626-102">Disallowed Types and Members in Microsoft.VisualBasic.dll</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="fc626-103">Программирование в среде CLR запрещает использование типа или члена, имеющего тип `HostProtectionAttribute` , который задает `System.Security.Permissions.HostProtectionResource` перечисление со значением `ExternalProcessMgmt` ,, `ExternalThreading` `MayLeakOnAbort` , `SecurityInfrastructure` ,, `SelfAffectingProcessMgmnt` `SelfAffectingThreading` , **шаредстате**, `Synchronization` или `UI` .</span><span class="sxs-lookup"><span data-stu-id="fc626-103">common language integration (CLR) programming disallows the use of a type or member that has a `HostProtectionAttribute` that specifies a `System.Security.Permissions.HostProtectionResource` enumeration with a value of `ExternalProcessMgmt`, `ExternalThreading`, `MayLeakOnAbort`, `SecurityInfrastructure`, `SelfAffectingProcessMgmnt`, `SelfAffectingThreading`, **SharedState**, `Synchronization`, or `UI`.</span></span> <span data-ttu-id="fc626-104">В следующей таблице перечислены элементы и типы сборки `Microsoft.VisualBasic.dll`, значения атрибута защиты узла которых недопустимы.</span><span class="sxs-lookup"><span data-stu-id="fc626-104">The following table lists the members and types of the `Microsoft.VisualBasic.dll` assembly whose Host Protection Attribute (HPA) values are disallowed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fc626-105">Этот список был создан из поддерживаемых сборок.</span><span class="sxs-lookup"><span data-stu-id="fc626-105">This list was generated from the supported assemblies.</span></span> <span data-ttu-id="fc626-106">Дополнительные сведения см. в разделе [supported .NET Framework librarys](../clr-integration/database-objects/supported-net-framework-libraries.md).</span><span class="sxs-lookup"><span data-stu-id="fc626-106">For more information, see [Supported .NET Framework Libraries](../clr-integration/database-objects/supported-net-framework-libraries.md).</span></span>  
  
|<span data-ttu-id="fc626-107">**Тип или элемент**</span><span class="sxs-lookup"><span data-stu-id="fc626-107">**Type or Member**</span></span>|<span data-ttu-id="fc626-108">**Значения атрибутов защиты узла**</span><span class="sxs-lookup"><span data-stu-id="fc626-108">**HPA Value(s)**</span></span>|  
|------------------------|------------------------|  
|<span data-ttu-id="fc626-109">Microsoft.VisualBasic.ApplicationServices.ApplicationBase</span><span class="sxs-lookup"><span data-stu-id="fc626-109">Microsoft.VisualBasic.ApplicationServices.ApplicationBase</span></span>|<span data-ttu-id="fc626-110">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-110">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-111">Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeCulture()</span><span class="sxs-lookup"><span data-stu-id="fc626-111">Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeCulture()</span></span>|<span data-ttu-id="fc626-112">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-112">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-113">Microsoft.VisualBasic.ApplicationServices.ApplicationBase.get_Info()</span><span class="sxs-lookup"><span data-stu-id="fc626-113">Microsoft.VisualBasic.ApplicationServices.ApplicationBase.get_Info()</span></span>|<span data-ttu-id="fc626-114">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-114">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-115">Microsoft.VisualBasic.ApplicationServices.AssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="fc626-115">Microsoft.VisualBasic.ApplicationServices.AssemblyInfo</span></span>|<span data-ttu-id="fc626-116">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-116">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-117">Microsoft.VisualBasic.ApplicationServices.BuiltInRoleConverter</span><span class="sxs-lookup"><span data-stu-id="fc626-117">Microsoft.VisualBasic.ApplicationServices.BuiltInRoleConverter</span></span>|<span data-ttu-id="fc626-118">SharedState</span><span class="sxs-lookup"><span data-stu-id="fc626-118">SharedState</span></span>|  
|<span data-ttu-id="fc626-119">Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase</span><span class="sxs-lookup"><span data-stu-id="fc626-119">Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase</span></span>|<span data-ttu-id="fc626-120">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-120">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-121">Microsoft.VisualBasic.ApplicationServices.User</span><span class="sxs-lookup"><span data-stu-id="fc626-121">Microsoft.VisualBasic.ApplicationServices.User</span></span>|<span data-ttu-id="fc626-122">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-122">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-123">Microsoft.VisualBasic.ApplicationServices.WebUser</span><span class="sxs-lookup"><span data-stu-id="fc626-123">Microsoft.VisualBasic.ApplicationServices.WebUser</span></span>|<span data-ttu-id="fc626-124">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-124">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-125">Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase</span><span class="sxs-lookup"><span data-stu-id="fc626-125">Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase</span></span>|<span data-ttu-id="fc626-126">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-126">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-127">Microsoft.VisualBasic.CompilerServices.HostServices</span><span class="sxs-lookup"><span data-stu-id="fc626-127">Microsoft.VisualBasic.CompilerServices.HostServices</span></span>|<span data-ttu-id="fc626-128">SharedState</span><span class="sxs-lookup"><span data-stu-id="fc626-128">SharedState</span></span>|  
|<span data-ttu-id="fc626-129">Microsoft.VisualBasic.CompilerServices.ProjectData.EndApp()</span><span class="sxs-lookup"><span data-stu-id="fc626-129">Microsoft.VisualBasic.CompilerServices.ProjectData.EndApp()</span></span>|<span data-ttu-id="fc626-130">SelfAffectingProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-130">SelfAffectingProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-131">Microsoft.VisualBasic.CompilerServices.Utils.SetCultureInfo()</span><span class="sxs-lookup"><span data-stu-id="fc626-131">Microsoft.VisualBasic.CompilerServices.Utils.SetCultureInfo()</span></span>|<span data-ttu-id="fc626-132">SelfAffectingThreading</span><span class="sxs-lookup"><span data-stu-id="fc626-132">SelfAffectingThreading</span></span>|  
|<span data-ttu-id="fc626-133">Microsoft.VisualBasic.DateAndTime.set_DateString()</span><span class="sxs-lookup"><span data-stu-id="fc626-133">Microsoft.VisualBasic.DateAndTime.set_DateString()</span></span>|<span data-ttu-id="fc626-134">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-134">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-135">Microsoft.VisualBasic.DateAndTime.set_TimeOfDay()</span><span class="sxs-lookup"><span data-stu-id="fc626-135">Microsoft.VisualBasic.DateAndTime.set_TimeOfDay()</span></span>|<span data-ttu-id="fc626-136">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-136">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-137">Microsoft.VisualBasic.DateAndTime.set_TimeString()</span><span class="sxs-lookup"><span data-stu-id="fc626-137">Microsoft.VisualBasic.DateAndTime.set_TimeString()</span></span>|<span data-ttu-id="fc626-138">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-138">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-139">Microsoft.VisualBasic.DateAndTime.set_Today()</span><span class="sxs-lookup"><span data-stu-id="fc626-139">Microsoft.VisualBasic.DateAndTime.set_Today()</span></span>|<span data-ttu-id="fc626-140">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-140">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-141">Microsoft.VisualBasic.Devices.Audio</span><span class="sxs-lookup"><span data-stu-id="fc626-141">Microsoft.VisualBasic.Devices.Audio</span></span>|<span data-ttu-id="fc626-142">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-142">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-143">Microsoft.VisualBasic.Devices.Clock</span><span class="sxs-lookup"><span data-stu-id="fc626-143">Microsoft.VisualBasic.Devices.Clock</span></span>|<span data-ttu-id="fc626-144">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-144">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-145">Microsoft.VisualBasic.Devices.Computer</span><span class="sxs-lookup"><span data-stu-id="fc626-145">Microsoft.VisualBasic.Devices.Computer</span></span>|<span data-ttu-id="fc626-146">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-146">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-147">Microsoft.VisualBasic.Devices.ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="fc626-147">Microsoft.VisualBasic.Devices.ComputerInfo</span></span>|<span data-ttu-id="fc626-148">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-148">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-149">Microsoft.VisualBasic.Devices.Keyboard</span><span class="sxs-lookup"><span data-stu-id="fc626-149">Microsoft.VisualBasic.Devices.Keyboard</span></span>|<span data-ttu-id="fc626-150">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-150">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-151">Microsoft.VisualBasic.Devices.Mouse</span><span class="sxs-lookup"><span data-stu-id="fc626-151">Microsoft.VisualBasic.Devices.Mouse</span></span>|<span data-ttu-id="fc626-152">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-152">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-153">Microsoft.VisualBasic.Devices.Network</span><span class="sxs-lookup"><span data-stu-id="fc626-153">Microsoft.VisualBasic.Devices.Network</span></span>|<span data-ttu-id="fc626-154">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-154">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-155">Microsoft.VisualBasic.Devices.Ports</span><span class="sxs-lookup"><span data-stu-id="fc626-155">Microsoft.VisualBasic.Devices.Ports</span></span>|<span data-ttu-id="fc626-156">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-156">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-157">Microsoft.VisualBasic.Devices.ServerComputer</span><span class="sxs-lookup"><span data-stu-id="fc626-157">Microsoft.VisualBasic.Devices.ServerComputer</span></span>|<span data-ttu-id="fc626-158">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-158">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-159">Microsoft.VisualBasic.FileIO.FileSystem</span><span class="sxs-lookup"><span data-stu-id="fc626-159">Microsoft.VisualBasic.FileIO.FileSystem</span></span>|<span data-ttu-id="fc626-160">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-160">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-161">Microsoft.VisualBasic.FileIO.SpecialDirectories</span><span class="sxs-lookup"><span data-stu-id="fc626-161">Microsoft.VisualBasic.FileIO.SpecialDirectories</span></span>|<span data-ttu-id="fc626-162">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-162">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-163">Microsoft.VisualBasic.FileIO.TextFieldParser..ctor()</span><span class="sxs-lookup"><span data-stu-id="fc626-163">Microsoft.VisualBasic.FileIO.TextFieldParser..ctor()</span></span>|<span data-ttu-id="fc626-164">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-164">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-165">Microsoft.VisualBasic.FileSystem</span><span class="sxs-lookup"><span data-stu-id="fc626-165">Microsoft.VisualBasic.FileSystem</span></span>|<span data-ttu-id="fc626-166">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-166">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-167">Microsoft.VisualBasic.Interaction.CreateObject()</span><span class="sxs-lookup"><span data-stu-id="fc626-167">Microsoft.VisualBasic.Interaction.CreateObject()</span></span>|<span data-ttu-id="fc626-168">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-168">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-169">Microsoft.VisualBasic.Interaction.DeleteSetting()</span><span class="sxs-lookup"><span data-stu-id="fc626-169">Microsoft.VisualBasic.Interaction.DeleteSetting()</span></span>|<span data-ttu-id="fc626-170">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-170">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-171">Microsoft.VisualBasic.Interaction.GetObject()</span><span class="sxs-lookup"><span data-stu-id="fc626-171">Microsoft.VisualBasic.Interaction.GetObject()</span></span>|<span data-ttu-id="fc626-172">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-172">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-173">Microsoft.VisualBasic.Interaction.InputBox()</span><span class="sxs-lookup"><span data-stu-id="fc626-173">Microsoft.VisualBasic.Interaction.InputBox()</span></span>|<span data-ttu-id="fc626-174">ИП</span><span class="sxs-lookup"><span data-stu-id="fc626-174">UI</span></span>|  
|<span data-ttu-id="fc626-175">Microsoft.VisualBasic.Interaction.MsgBox()</span><span class="sxs-lookup"><span data-stu-id="fc626-175">Microsoft.VisualBasic.Interaction.MsgBox()</span></span>|<span data-ttu-id="fc626-176">ИП</span><span class="sxs-lookup"><span data-stu-id="fc626-176">UI</span></span>|  
|<span data-ttu-id="fc626-177">Microsoft.VisualBasic.Logging.AspLog</span><span class="sxs-lookup"><span data-stu-id="fc626-177">Microsoft.VisualBasic.Logging.AspLog</span></span>|<span data-ttu-id="fc626-178">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-178">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-179">Microsoft.VisualBasic.Logging.FileLogTraceListener..ctor()</span><span class="sxs-lookup"><span data-stu-id="fc626-179">Microsoft.VisualBasic.Logging.FileLogTraceListener..ctor()</span></span>|<span data-ttu-id="fc626-180">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-180">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-181">Microsoft.VisualBasic.Logging.FileLogTraceListener.Close()</span><span class="sxs-lookup"><span data-stu-id="fc626-181">Microsoft.VisualBasic.Logging.FileLogTraceListener.Close()</span></span>|<span data-ttu-id="fc626-182">Синхронизация</span><span class="sxs-lookup"><span data-stu-id="fc626-182">Synchronization</span></span>|  
|<span data-ttu-id="fc626-183">Microsoft.VisualBasic.Logging.FileLogTraceListener.Dispose()</span><span class="sxs-lookup"><span data-stu-id="fc626-183">Microsoft.VisualBasic.Logging.FileLogTraceListener.Dispose()</span></span>|<span data-ttu-id="fc626-184">Синхронизация</span><span class="sxs-lookup"><span data-stu-id="fc626-184">Synchronization</span></span>|  
|<span data-ttu-id="fc626-185">Microsoft.VisualBasic.Logging.FileLogTraceListener.Flush()</span><span class="sxs-lookup"><span data-stu-id="fc626-185">Microsoft.VisualBasic.Logging.FileLogTraceListener.Flush()</span></span>|<span data-ttu-id="fc626-186">Синхронизация</span><span class="sxs-lookup"><span data-stu-id="fc626-186">Synchronization</span></span>|  
|<span data-ttu-id="fc626-187">Microsoft.VisualBasic.Logging.FileLogTraceListener.GetSupportedAttributes()</span><span class="sxs-lookup"><span data-stu-id="fc626-187">Microsoft.VisualBasic.Logging.FileLogTraceListener.GetSupportedAttributes()</span></span>|<span data-ttu-id="fc626-188">Синхронизация</span><span class="sxs-lookup"><span data-stu-id="fc626-188">Synchronization</span></span>|  
|<span data-ttu-id="fc626-189">Microsoft.VisualBasic.Logging.FileLogTraceListener.TraceData()</span><span class="sxs-lookup"><span data-stu-id="fc626-189">Microsoft.VisualBasic.Logging.FileLogTraceListener.TraceData()</span></span>|<span data-ttu-id="fc626-190">Синхронизация</span><span class="sxs-lookup"><span data-stu-id="fc626-190">Synchronization</span></span>|  
|<span data-ttu-id="fc626-191">Microsoft.VisualBasic.Logging.FileLogTraceListener.TraceEvent()</span><span class="sxs-lookup"><span data-stu-id="fc626-191">Microsoft.VisualBasic.Logging.FileLogTraceListener.TraceEvent()</span></span>|<span data-ttu-id="fc626-192">Синхронизация</span><span class="sxs-lookup"><span data-stu-id="fc626-192">Synchronization</span></span>|  
|<span data-ttu-id="fc626-193">Microsoft.VisualBasic.Logging.FileLogTraceListener.Write()</span><span class="sxs-lookup"><span data-stu-id="fc626-193">Microsoft.VisualBasic.Logging.FileLogTraceListener.Write()</span></span>|<span data-ttu-id="fc626-194">Синхронизация</span><span class="sxs-lookup"><span data-stu-id="fc626-194">Synchronization</span></span>|  
|<span data-ttu-id="fc626-195">Microsoft.VisualBasic.Logging.FileLogTraceListener.WriteLine()</span><span class="sxs-lookup"><span data-stu-id="fc626-195">Microsoft.VisualBasic.Logging.FileLogTraceListener.WriteLine()</span></span>|<span data-ttu-id="fc626-196">Синхронизация</span><span class="sxs-lookup"><span data-stu-id="fc626-196">Synchronization</span></span>|  
|<span data-ttu-id="fc626-197">Microsoft.VisualBasic.Logging.Log</span><span class="sxs-lookup"><span data-stu-id="fc626-197">Microsoft.VisualBasic.Logging.Log</span></span>|<span data-ttu-id="fc626-198">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-198">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-199">Microsoft.VisualBasic.MyServices.ClipboardProxy</span><span class="sxs-lookup"><span data-stu-id="fc626-199">Microsoft.VisualBasic.MyServices.ClipboardProxy</span></span>|<span data-ttu-id="fc626-200">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-200">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-201">Microsoft.VisualBasic.MyServices.FileSystemProxy</span><span class="sxs-lookup"><span data-stu-id="fc626-201">Microsoft.VisualBasic.MyServices.FileSystemProxy</span></span>|<span data-ttu-id="fc626-202">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-202">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-203">Microsoft.VisualBasic.MyServices.RegistryProxy</span><span class="sxs-lookup"><span data-stu-id="fc626-203">Microsoft.VisualBasic.MyServices.RegistryProxy</span></span>|<span data-ttu-id="fc626-204">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-204">ExternalProcessMgmt</span></span>|  
|<span data-ttu-id="fc626-205">Microsoft.VisualBasic.MyServices.SpecialDirectoriesProxy</span><span class="sxs-lookup"><span data-stu-id="fc626-205">Microsoft.VisualBasic.MyServices.SpecialDirectoriesProxy</span></span>|<span data-ttu-id="fc626-206">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="fc626-206">ExternalProcessMgmt</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fc626-207">См. также:</span><span class="sxs-lookup"><span data-stu-id="fc626-207">See Also</span></span>  
 <span data-ttu-id="fc626-208">[Атрибуты защиты узла и программирование интеграции со средой CLR](host-protection-attributes-and-clr-integration-programming.md) </span><span class="sxs-lookup"><span data-stu-id="fc626-208">[Host Protection Attributes and CLR Integration Programming](host-protection-attributes-and-clr-integration-programming.md) </span></span>  
 <span data-ttu-id="fc626-209">[Недопустимые типы и члены в mscorlib.dll](disallowed-types-and-members-in-mscorlib-dll.md) </span><span class="sxs-lookup"><span data-stu-id="fc626-209">[Disallowed Types and Members in mscorlib.dll](disallowed-types-and-members-in-mscorlib-dll.md) </span></span>  
 <span data-ttu-id="fc626-210">[Недопустимые типы и члены в System.dll](disallowed-types-and-members-in-system-dll.md) </span><span class="sxs-lookup"><span data-stu-id="fc626-210">[Disallowed Types and Members in System.dll](disallowed-types-and-members-in-system-dll.md) </span></span>  
 <span data-ttu-id="fc626-211">[Недопустимые типы и члены в System.Data.dll](disallowed-types-and-members-in-system-data-dll.md) </span><span class="sxs-lookup"><span data-stu-id="fc626-211">[Disallowed Types and Members in System.Data.dll](disallowed-types-and-members-in-system-data-dll.md) </span></span>  
 [<span data-ttu-id="fc626-212">Недопустимые типы и элементы в библиотеке System.Core.dll</span><span class="sxs-lookup"><span data-stu-id="fc626-212">Disallowed Types and Members in System.Core.dll</span></span>](disallowed-types-and-members-in-system-core-dll.md)  
  
  