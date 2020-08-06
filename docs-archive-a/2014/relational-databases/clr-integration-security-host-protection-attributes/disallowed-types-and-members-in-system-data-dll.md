---
title: Недопустимые типы и члены в System.Data.dll | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- host protection attributes [CLR integration]
- common language runtime [SQL Server], host protection attributes
ms.assetid: ee5f55e9-fbef-401a-be18-a2e5873c8720
author: rothja
ms.author: jroth
ms.openlocfilehash: cd62f6f0a90bd167f20a33f8de749acc982f39b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657819"
---
# <a name="disallowed-types-and-members-in-systemdatadll"></a><span data-ttu-id="e747a-102">Недопустимые типы и элементы в библиотеке System.Data.dll</span><span class="sxs-lookup"><span data-stu-id="e747a-102">Disallowed Types and Members in System.Data.dll</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="e747a-103">Программирование в среде CLR запрещает использование типа или члена, имеющего тип `HostProtectionAttribute` , который задает `System.Security.Permissions.HostProtectionResource` перечисление со значением `ExternalProcessMgmt` ,, `ExternalThreading` `MayLeakOnAbort` , `SecurityInfrastructure` ,, `SelfAffectingProcessMgmnt` `SelfAffectingThreading` , **шаредстате**, `Synchronization` или `UI` .</span><span class="sxs-lookup"><span data-stu-id="e747a-103">common language integration (CLR) programming disallows the use of a type or member that has a `HostProtectionAttribute` that specifies a `System.Security.Permissions.HostProtectionResource` enumeration with a value of `ExternalProcessMgmt`, `ExternalThreading`, `MayLeakOnAbort`, `SecurityInfrastructure`, `SelfAffectingProcessMgmnt`, `SelfAffectingThreading`, **SharedState**, `Synchronization`, or `UI`.</span></span> <span data-ttu-id="e747a-104">В следующей таблице приводится перечень членов и типов сборки System.Data.dll, чьи значения атрибутов защиты узла недопустимы.</span><span class="sxs-lookup"><span data-stu-id="e747a-104">The following table lists the members and types of the System.Data.dll assembly whose Host Protection Attribute (HPA) values are disallowed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e747a-105">Этот список был создан из поддерживаемых сборок.</span><span class="sxs-lookup"><span data-stu-id="e747a-105">This list was generated from the supported assemblies.</span></span> <span data-ttu-id="e747a-106">Дополнительные сведения см. в разделе [supported .NET Framework librarys](../clr-integration/database-objects/supported-net-framework-libraries.md).</span><span class="sxs-lookup"><span data-stu-id="e747a-106">For more information, see [Supported .NET Framework Libraries](../clr-integration/database-objects/supported-net-framework-libraries.md).</span></span>  
  
|<span data-ttu-id="e747a-107">Тип или элемент</span><span class="sxs-lookup"><span data-stu-id="e747a-107">Type or Member</span></span>|<span data-ttu-id="e747a-108">Значения атрибутов защиты узла</span><span class="sxs-lookup"><span data-stu-id="e747a-108">HPA Value(s)</span></span>|  
|--------------------|--------------------|  
|<span data-ttu-id="e747a-109">System.Data.SqlClient.SqlCommand.BeginExecuteNonQuery()</span><span class="sxs-lookup"><span data-stu-id="e747a-109">System.Data.SqlClient.SqlCommand.BeginExecuteNonQuery()</span></span>|<span data-ttu-id="e747a-110">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="e747a-110">ExternalThreading</span></span>|  
|<span data-ttu-id="e747a-111">System.Data.SqlClient.SqlCommand.BeginExecuteReader()</span><span class="sxs-lookup"><span data-stu-id="e747a-111">System.Data.SqlClient.SqlCommand.BeginExecuteReader()</span></span>|<span data-ttu-id="e747a-112">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="e747a-112">ExternalThreading</span></span>|  
|<span data-ttu-id="e747a-113">System.Data.SqlClient.SqlCommand.BeginExecuteXmlReader()</span><span class="sxs-lookup"><span data-stu-id="e747a-113">System.Data.SqlClient.SqlCommand.BeginExecuteXmlReader()</span></span>|<span data-ttu-id="e747a-114">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="e747a-114">ExternalThreading</span></span>|  
|<span data-ttu-id="e747a-115">System.Data.SqlClient.SqlDependency..ctor()</span><span class="sxs-lookup"><span data-stu-id="e747a-115">System.Data.SqlClient.SqlDependency..ctor()</span></span>|<span data-ttu-id="e747a-116">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="e747a-116">ExternalThreading</span></span>|  
|<span data-ttu-id="e747a-117">System.Data.SqlClient.SqlDependency.Start()</span><span class="sxs-lookup"><span data-stu-id="e747a-117">System.Data.SqlClient.SqlDependency.Start()</span></span>|<span data-ttu-id="e747a-118">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="e747a-118">ExternalThreading</span></span>|  
|<span data-ttu-id="e747a-119">System.Data.SqlClient.SqlDependency.Stop()</span><span class="sxs-lookup"><span data-stu-id="e747a-119">System.Data.SqlClient.SqlDependency.Stop()</span></span>|<span data-ttu-id="e747a-120">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="e747a-120">ExternalThreading</span></span>|  
|<span data-ttu-id="e747a-121">System.Data.TypedDataSetGenerator</span><span class="sxs-lookup"><span data-stu-id="e747a-121">System.Data.TypedDataSetGenerator</span></span>|<span data-ttu-id="e747a-122">SharedState, Synchronization</span><span class="sxs-lookup"><span data-stu-id="e747a-122">SharedState, Synchronization</span></span>|  
|<span data-ttu-id="e747a-123">System.Xml.XmlDataDocument</span><span class="sxs-lookup"><span data-stu-id="e747a-123">System.Xml.XmlDataDocument</span></span>|<span data-ttu-id="e747a-124">Синхронизация</span><span class="sxs-lookup"><span data-stu-id="e747a-124">Synchronization</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e747a-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="e747a-125">See Also</span></span>  
 <span data-ttu-id="e747a-126">[Атрибуты защиты узла и программирование интеграции со средой CLR](host-protection-attributes-and-clr-integration-programming.md) </span><span class="sxs-lookup"><span data-stu-id="e747a-126">[Host Protection Attributes and CLR Integration Programming](host-protection-attributes-and-clr-integration-programming.md) </span></span>  
 <span data-ttu-id="e747a-127">[Недопустимые типы и члены в Microsoft.VisualBasic.dll](disallowed-types-and-members-in-microsoft-visualbasic-dll.md) </span><span class="sxs-lookup"><span data-stu-id="e747a-127">[Disallowed Types and Members in Microsoft.VisualBasic.dll](disallowed-types-and-members-in-microsoft-visualbasic-dll.md) </span></span>  
 <span data-ttu-id="e747a-128">[Недопустимые типы и члены в mscorlib.dll](disallowed-types-and-members-in-mscorlib-dll.md) </span><span class="sxs-lookup"><span data-stu-id="e747a-128">[Disallowed Types and Members in mscorlib.dll](disallowed-types-and-members-in-mscorlib-dll.md) </span></span>  
 <span data-ttu-id="e747a-129">[Недопустимые типы и члены в System.dll](disallowed-types-and-members-in-system-dll.md) </span><span class="sxs-lookup"><span data-stu-id="e747a-129">[Disallowed Types and Members in System.dll](disallowed-types-and-members-in-system-dll.md) </span></span>  
 [<span data-ttu-id="e747a-130">Недопустимые типы и элементы в библиотеке System.Core.dll</span><span class="sxs-lookup"><span data-stu-id="e747a-130">Disallowed Types and Members in System.Core.dll</span></span>](disallowed-types-and-members-in-system-core-dll.md)  
  
  
