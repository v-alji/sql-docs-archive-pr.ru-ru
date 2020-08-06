---
title: Реализация модуля безопасности | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- security [Reporting Services], extensions
- forms-based authentication [Reporting Services]
- custom authentication [Reporting Services]
- extensions [Reporting Services], custom security
ms.assetid: d2327e7c-0d48-49e3-bcd9-3bba4e67a68b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e5cf1fa6ce0e0a02a52e6a27f693c152d1f97152
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664730"
---
# <a name="implementing-a-security-extension"></a><span data-ttu-id="d41d2-102">Реализация модуля безопасности</span><span class="sxs-lookup"><span data-stu-id="d41d2-102">Implementing a Security Extension</span></span>
  <span data-ttu-id="d41d2-103">Проверка подлинности [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows является основной системой защиты отчетов в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d41d2-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows Authentication is the primary system for securing reports in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="d41d2-104">Однако в определенных случаях может понадобиться расширить систему безопасности служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], чтобы обеспечить соответствие требованиям системы безопасности предприятия.</span><span class="sxs-lookup"><span data-stu-id="d41d2-104">In certain cases, however, you may need to extend the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] security system to accommodate custom security in your enterprise.</span></span> <span data-ttu-id="d41d2-105">Для этого используется платформа разработки, предоставляемая API служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d41d2-105">You can do this using the development platform provided by the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] API.</span></span> <span data-ttu-id="d41d2-106">В этом разделе представлены общие сведения о модулях безопасности в службах [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d41d2-106">This section will present an overview of security extensions in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="d41d2-107">Полные сведения о реализации, развертывании и удалении модулей безопасности служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] см. на странице [Образцы продуктов служб SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="d41d2-107">For complete details about implementing, deploying, and removing a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] security extension, please see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d41d2-108">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="d41d2-108">In This Section</span></span>  
 [<span data-ttu-id="d41d2-109">Общие сведения о модулях безопасности</span><span class="sxs-lookup"><span data-stu-id="d41d2-109">Security Extensions Overview</span></span>](security-extensions-overview.md)  
 <span data-ttu-id="d41d2-110">Приводит общие сведения о модулях безопасности служб Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="d41d2-110">Provides an overview of Reporting Services Security Extensions.</span></span>  
  
 [<span data-ttu-id="d41d2-111">Проверка подлинности в службах Reporting Services</span><span class="sxs-lookup"><span data-stu-id="d41d2-111">Authentication in Reporting Services</span></span>](authentication-in-reporting-services.md)  
 <span data-ttu-id="d41d2-112">Обсуждается проверка подлинности в службах [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d41d2-112">Discusses authentication in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="d41d2-113">Авторизация в службах Reporting Services</span><span class="sxs-lookup"><span data-stu-id="d41d2-113">Authorization in Reporting Services</span></span>](authorization-in-reporting-services.md)  
 <span data-ttu-id="d41d2-114">Рассматривает авторизацию в службах [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d41d2-114">Covers authorization in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d41d2-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="d41d2-115">See Also</span></span>  
 <xref:Microsoft.ReportingServices.Interfaces>   
 <span data-ttu-id="d41d2-116">[Модули служб Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="d41d2-116">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 [<span data-ttu-id="d41d2-117">Библиотека модулей Reporting Services</span><span class="sxs-lookup"><span data-stu-id="d41d2-117">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
