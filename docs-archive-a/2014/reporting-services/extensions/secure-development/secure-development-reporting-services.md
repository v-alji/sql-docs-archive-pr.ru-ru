---
title: Разработка безопасных приложений (Reporting Services) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- development security [Reporting Services]
- security [Reporting Services], development
- security [Reporting Services], strategies
ms.assetid: 12161a6c-b93b-4312-9d27-0c922561eb9b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7ba284b9013c5da6b03cce06ec72deccb045cfad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669285"
---
# <a name="secure-development-reporting-services"></a><span data-ttu-id="1df7e-102">Разработка безопасных приложений (службы Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="1df7e-102">Secure Development (Reporting Services)</span></span>
  <span data-ttu-id="1df7e-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] обеспечивает надежную систему безопасности, которая может выполнять код в строго определенных рамках заданного администратором контекста безопасности.</span><span class="sxs-lookup"><span data-stu-id="1df7e-103">The [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] provides a robust security system that can run code in tightly constrained, administrator-defined security contexts.</span></span> <span data-ttu-id="1df7e-104">Службы [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] используют систему безопасности платформы [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], известную как защита доступа к коду (или защита доступа на основе признаков).</span><span class="sxs-lookup"><span data-stu-id="1df7e-104">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] uses the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] security system, known as code access security (or evidence-based security).</span></span> <span data-ttu-id="1df7e-105">Если в защите доступа доступа к коду пользователю предоставлен доверенный доступ к ресурсу, но выполняемый пользователем код не является доверенным, то доступ к ресурсу будет запрещен.</span><span class="sxs-lookup"><span data-stu-id="1df7e-105">Under code access security, a user may be trusted to access a resource, but if the code the user executes is not trusted, access to the resource will be denied.</span></span>  
  
 <span data-ttu-id="1df7e-106">Система безопасности, основанная на коде, в противоположность отдельным пользователям, позволяет распространять правила безопасности на пользовательские сборки или модули данных, доставки, подготовки к просмотру и безопасности, создаваемые разработчиками для служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1df7e-106">Security based on code, as opposed to specific users, permits security to be expressed for custom assemblies or data, delivery, rendering, and security extensions that you develop for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="1df7e-107">Модуль может выполняться любым количеством пользователей служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], которые были неизвестны на этапе разработки.</span><span class="sxs-lookup"><span data-stu-id="1df7e-107">Your extension code may be executed by any number of [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] users, all of whom are unknown at development time.</span></span> <span data-ttu-id="1df7e-108">Пользовательским сборкам или модулям необходимы конкретные политики безопасности служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1df7e-108">The custom assemblies or extensions that you develop require specific security policies in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="1df7e-109">Эти политики безопасности представлены в платформе [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] как типы.</span><span class="sxs-lookup"><span data-stu-id="1df7e-109">These security policies are represented as types in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="1df7e-110">Дополнительные сведения о защите доступа к коду см. в разделе «Защита доступа к коду» в документации по платформе [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1df7e-110">For a more information about code access security, see "Code Access Security" in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] documentation.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1df7e-111">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="1df7e-111">In This Section</span></span>  
 [<span data-ttu-id="1df7e-112">Управление доступом для кода в службах Reporting Services</span><span class="sxs-lookup"><span data-stu-id="1df7e-112">Code Access Security in Reporting Services</span></span>](code-access-security-in-reporting-services.md)  
 <span data-ttu-id="1df7e-113">Основы защиты доступа к коду и настройка политики для пользовательских сборок и модулей в службах [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1df7e-113">Introduces code access security and policy configuration for custom assemblies and extensions in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="1df7e-114">Основные сведения о политиках безопасности</span><span class="sxs-lookup"><span data-stu-id="1df7e-114">Understanding Security Policies</span></span>](understanding-security-policies.md)  
 <span data-ttu-id="1df7e-115">Описание различных типов сборок в службах [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] и влияние защиты доступа к коду на разрешения кода.</span><span class="sxs-lookup"><span data-stu-id="1df7e-115">Describes the various assembly types in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] and how code access security affects code permissions.</span></span>  
  
 [<span data-ttu-id="1df7e-116">Использование файлов политики безопасности служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="1df7e-116">Using Reporting Services Security Policy Files</span></span>](using-reporting-services-security-policy-files.md)  
 <span data-ttu-id="1df7e-117">Описание различных компонент служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] и соответствующих файлов конфигурации политик.</span><span class="sxs-lookup"><span data-stu-id="1df7e-117">Describes the different [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] components and the corresponding policy configuration files.</span></span>  
  
  
