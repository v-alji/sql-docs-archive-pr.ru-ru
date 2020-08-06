---
title: Использование пользовательских сборок со строгими именами | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- AllowPartiallyTrustedCallersAttribute attribute
- strong-named custom assemblies [Reporting Services]
- strong names [Reporting Services]
- assemblies [Reporting Services], strong names
- custom assemblies [Reporting Services], strong-named
ms.assetid: ca9f19d7-6e86-46f2-b9ad-9bf807eaa52e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5e685ecda39e0487eb4b469920820fa6e4a10daa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654924"
---
# <a name="using-strong-named-custom-assemblies"></a><span data-ttu-id="deeb5-102">Использование пользовательских сборок со строгими именами</span><span class="sxs-lookup"><span data-stu-id="deeb5-102">Using Strong-Named Custom Assemblies</span></span>
  <span data-ttu-id="deeb5-103">Строгое имя идентифицирует сборку и включает текстовое имя сборки, четырехкомпонентный номер версии, сведения о культуре (если они указаны), открытый ключ и цифровую подпись, хранящуюся в манифесте сборки.</span><span class="sxs-lookup"><span data-stu-id="deeb5-103">A strong name identifies an assembly and includes the assembly's text name, four-part version number, culture information (if provided), a public key, and a digital signature stored in the assembly's manifest.</span></span> <span data-ttu-id="deeb5-104">Строгое имя уникальным образом определяет сборку в среде CLR и гарантирует целостность двоичных файлов.</span><span class="sxs-lookup"><span data-stu-id="deeb5-104">A strong name uniquely identifies an assembly to the common language runtime (CLR) and ensures binary integrity.</span></span>  
  
## <a name="using-allowpartiallytrustedcallersattribute"></a><span data-ttu-id="deeb5-105">Использование атрибута AllowPartiallyTrustedCallersAttribute</span><span class="sxs-lookup"><span data-stu-id="deeb5-105">Using AllowPartiallyTrustedCallersAttribute</span></span>  
 <span data-ttu-id="deeb5-106">Чтобы использовать с отчетами сборки со строгими именами, необходимо разрешить вызов сборки со строгим именем из частично доверенного кода. Для этого используется атрибут **AllowPartiallyTrustedCallers** сборки.</span><span class="sxs-lookup"><span data-stu-id="deeb5-106">To use strong-named assemblies with reports, you must allow your strong-named assembly to be called by partially trusted code using the assembly's **AllowPartiallyTrustedCallers** attribute.</span></span> <span data-ttu-id="deeb5-107">С помощью атрибута **AllowPartiallyTrustedCallersAttribute** можно разрешить вызов сборок со строгими именами в выражениях отчетов из конструктора отчетов или с сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="deeb5-107">You can use **AllowPartiallyTrustedCallersAttribute** to allow strong-named assemblies to be called by Report Designer or the report server in report expressions.</span></span> <span data-ttu-id="deeb5-108">Чтобы разрешить вызов сборок со строгими именами из частично доверенного кода, добавьте в файл атрибутов сборки следующий атрибут уровня сборки.</span><span class="sxs-lookup"><span data-stu-id="deeb5-108">To allow partially trusted code to call strong-named assemblies, add the following assembly-level attribute to your assembly attribute file.</span></span>  
  
```vb  
<assembly:AllowPartiallyTrustedCallers>  
```  
  
```csharp  
[assembly:AllowPartiallyTrustedCallers]  
```  
  
 <span data-ttu-id="deeb5-109">Атрибут **AllowPartiallyTrustedCallersAttribute** действует только при применении сборкой со строгим именем на уровне сборки.</span><span class="sxs-lookup"><span data-stu-id="deeb5-109">**AllowPartiallyTrustedCallersAttribute** is effective only when applied by a strong-named assembly at the assembly level.</span></span> <span data-ttu-id="deeb5-110">Дополнительные сведения о применении атрибутов на уровне сборки см. в разделе «Применение атрибутов» документации по [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] пакету SDK.</span><span class="sxs-lookup"><span data-stu-id="deeb5-110">For more information about applying attributes at the assembly level, see "Applying Attributes" in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="deeb5-111">Если присутствует атрибут **AllowPartiallyTrustedCallersAttribute**, то стандартная проверка безопасности **FullTrustLinkDemand** блокируется, что позволяет вызывать сборку из любой другой частично доверенной сборки.</span><span class="sxs-lookup"><span data-stu-id="deeb5-111">When **AllowPartiallyTrustedCallersAttribute** is present, the default **FullTrustLinkDemand** security checks are prevented, making the assembly callable from any other partially trusted assembly.</span></span> <span data-ttu-id="deeb5-112">Все виды проверки безопасности, в том числе декларативные атрибуты безопасности уровня класса или уровня метода, необходимо указывать явно.</span><span class="sxs-lookup"><span data-stu-id="deeb5-112">All security checks, including class-level or method-level declarative security attributes, must be explicitly stated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="deeb5-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="deeb5-113">See Also</span></span>  
 [<span data-ttu-id="deeb5-114">Использование пользовательских сборок с отчетами</span><span class="sxs-lookup"><span data-stu-id="deeb5-114">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
