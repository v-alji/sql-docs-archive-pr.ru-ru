---
title: Создание библиотеки модулей доставки | Документы Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- delivery extensions [Reporting Services], namespace assignments
- library [Reporting Services]
- assigning namespaces to extensions
ms.assetid: 63b32f93-4bab-4b07-bd72-39a47aca1cda
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c9891c2b0c1bb9c7d495b3ab1f8f2267ce04b79f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750468"
---
# <a name="creating-a-delivery-extension-library"></a><span data-ttu-id="704ee-102">Создание библиотеки модулей доставки</span><span class="sxs-lookup"><span data-stu-id="704ee-102">Creating a Delivery Extension Library</span></span>
  <span data-ttu-id="704ee-103">Каждому созданному модулю доставки служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] необходимо присвоить уникальное пространство имен. Также он должен быть встроен в библиотеку или файл сборки.</span><span class="sxs-lookup"><span data-stu-id="704ee-103">Each [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension you create should be assigned to a unique namespace and built into a library or assembly file.</span></span> <span data-ttu-id="704ee-104">Конкретное имя пространства имен не имеет значения, однако оно должно быть уникальным и не должно использоваться в других расширениях.</span><span class="sxs-lookup"><span data-stu-id="704ee-104">The exact name of the namespace is not important, but it must be unique and not shared with any other extension.</span></span> <span data-ttu-id="704ee-105">Для модулей доставки своей компании следует создавать собственные уникальные пространства имен.</span><span class="sxs-lookup"><span data-stu-id="704ee-105">You should create your own unique namespaces for your company's delivery extensions.</span></span>  
  
 <span data-ttu-id="704ee-106">В следующем примере показывается код, позволяющий начать создание модуля доставки служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], использующего пространства имен, содержащие интерфейсы доставки и служебные классы.</span><span class="sxs-lookup"><span data-stu-id="704ee-106">The following example shows the code to begin a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension, which uses the namespaces that contain the delivery interfaces and any utility classes.</span></span>  
  
```vb  
Imports System  
Imports Microsoft.ReportingServices.Interfaces  
  
Namespace CompanyName.ExtensionName  
   ...  
```  
  
```csharp  
using System;  
using Microsoft.ReportingServices.Interfaces;  
  
namespace CompanyName.ExtensionName  
{  
   ...  
```  
  
 <span data-ttu-id="704ee-107">При компиляции модуля доставки служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] следует предоставить компилятору ссылку на файл Microsoft.ReportingServices.Interfaces.dll, поскольку в нем хранятся интерфейсы модуля доставки и классы.</span><span class="sxs-lookup"><span data-stu-id="704ee-107">When compiling a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension, you must supply to the compiler a reference to Microsoft.ReportingServices.Interfaces.dll, because the delivery extension interfaces and classes are contained there.</span></span> <span data-ttu-id="704ee-108">Пространство имен <xref:Microsoft.ReportingServices.Interfaces> необходимо для реализации интерфейсов <xref:Microsoft.ReportingServices.Interfaces.IExtension>, <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> и др.</span><span class="sxs-lookup"><span data-stu-id="704ee-108">The <xref:Microsoft.ReportingServices.Interfaces> namespace is needed to implement the <xref:Microsoft.ReportingServices.Interfaces.IExtension> interface, the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> interface, and more.</span></span> <span data-ttu-id="704ee-109">Например, если бы все файлы, содержащие код на языке C#, необходимый для реализации модуля доставки служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], находились в одном каталоге с расширением CS, то для компиляции файлов, хранящихся в библиотеке CompanyName.ExtensionName.dll, из данного каталога нужно было бы использовать приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="704ee-109">For example, if all the files containing the code to implement a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension written in C# were in a single directory with the extension .cs, the following command would be issued from that directory to compile the files stored in CompanyName.ExtensionName.dll.</span></span>  
  
```csharp  
csc /t:library /out:CompanyName.ExtensionName.dll *.cs /r:System.dll   
/r:Microsoft.ReportingServices.Interfaces.dll  
```  
  
 <span data-ttu-id="704ee-110">В следующем примере кода показана команда, которая используется для файлов [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] с расширением VB.</span><span class="sxs-lookup"><span data-stu-id="704ee-110">The following code example shows the command that would be used for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] files with the extension .vb.</span></span>  
  
```vb  
vbc /t:library /out:CompanyName.ExtensionName.dll *.vb /r:System.dll   
/r:Microsoft.ReportingServices.Interfaces.dll  
```  
  
> [!NOTE]  
>  <span data-ttu-id="704ee-111">Также можно проектировать, разрабатывать и строить модуль доставки в среде [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="704ee-111">You can also design, develop, and build your delivery extension using [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="704ee-112">Дополнительные сведения о разработке сборок в среде [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] см. в документации по среде [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="704ee-112">For more information about developing assemblies in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], see your [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="704ee-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="704ee-113">See Also</span></span>  
 <span data-ttu-id="704ee-114">[Модули служб Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="704ee-114">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="704ee-115">[Реализация модуля доставки](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="704ee-115">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="704ee-116">Библиотека модулей Reporting Services</span><span class="sxs-lookup"><span data-stu-id="704ee-116">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
