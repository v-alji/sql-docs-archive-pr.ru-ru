---
title: Интеграция служб Reporting Services с помощью доступа по URL-адресу | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- URL access [Reporting Services], about URL access
- integrating reports [Reporting Services]
ms.assetid: f1014f7d-fafa-4aa8-8bd2-5bdba835d9b6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fedf4ce3011d9caae9d673acf354265537115057
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735125"
---
# <a name="integrating-reporting-services-using-url-access"></a><span data-ttu-id="ea317-102">Интеграция служб Reporting Services с помощью доступа по URL-адресу</span><span class="sxs-lookup"><span data-stu-id="ea317-102">Integrating Reporting Services Using URL Access</span></span>
  <span data-ttu-id="ea317-103">Доступ по URL-адресу позволяет получать доступ к отчетам с помощью URL-адреса сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="ea317-103">With URL access, you access reports through a report server URL.</span></span> <span data-ttu-id="ea317-104">Запрос по URL-адресу позволяет получить доступ к выбранному серверу отчетов, а также к отчетам, ресурсам и другим элементам в базе данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="ea317-104">A URL request enables you to access a specific report server as well as the reports, resources, and other items in the report server database.</span></span> <span data-ttu-id="ea317-105">Также можно настроить параметры просмотра отчетов и функции навигации для пользователей.</span><span class="sxs-lookup"><span data-stu-id="ea317-105">You can also customize the report viewing and navigation experience for your users.</span></span> <span data-ttu-id="ea317-106">Строка запроса URL-адреса содержит настройки сведений об устройстве, а также параметры отчета и выбранный формат подготовки к просмотру.</span><span class="sxs-lookup"><span data-stu-id="ea317-106">The query string of the URL contains device information settings, as well as report parameters targeted at your report and the chosen rendering output.</span></span> <span data-ttu-id="ea317-107">Способ обработки запросов по URL-адресу на сервере отчетов зависит от параметров, префиксов параметров и типа элемента, к которому выполняется доступ по URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="ea317-107">The way the report server handles URL requests depends on the parameters, parameter prefixes, and type of item that you are accessing through the URL.</span></span>  
  
 <span data-ttu-id="ea317-108">С помощью доступа по URL-адресу можно внедрять гиперссылки на отчеты и другие элементы сервера отчетов в приложения, разрабатываемые в Windows или в веб-среде.</span><span class="sxs-lookup"><span data-stu-id="ea317-108">You can use URL access to embed hyperlinks to reports and other report server items in the applications that you develop, whether in a Windows or Web environment.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ea317-109">Подразделы этого раздела содержат основные принципы интеграции.</span><span class="sxs-lookup"><span data-stu-id="ea317-109">The topics in the section provide you with some basic ideas for integration.</span></span> <span data-ttu-id="ea317-110">Эти сведения можно использовать для начала проектирования и разработки собственных сценариев интеграции для служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea317-110">You can use the information to begin to design and develop your own [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] integration scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ea317-111">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="ea317-111">In This Section</span></span>  
 [<span data-ttu-id="ea317-112">Использование доступа по URL-адресу в веб-приложении</span><span class="sxs-lookup"><span data-stu-id="ea317-112">Using URL Access in a Web Application</span></span>](integrating-reporting-services-using-url-access-web-application.md)  
 <span data-ttu-id="ea317-113">Описывает использование доступа по URL-адресу для интеграции служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] в веб-среду.</span><span class="sxs-lookup"><span data-stu-id="ea317-113">Describes how to use URL access to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into a Web environment.</span></span>  
  
 [<span data-ttu-id="ea317-114">Использование доступа по URL-адресу в приложении Windows</span><span class="sxs-lookup"><span data-stu-id="ea317-114">Using URL Access in a Windows Application</span></span>](integrating-reporting-services-using-url-access-windows-application.md)  
 <span data-ttu-id="ea317-115">Описывает использование доступа по URL-адресу для интеграции служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] в среду [!INCLUDE[msCoName](../../includes/msconame-md.md)] Win32.</span><span class="sxs-lookup"><span data-stu-id="ea317-115">Describes how to use URL access to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Win32 environment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea317-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="ea317-116">See Also</span></span>  
 <span data-ttu-id="ea317-117">[Интеграция Reporting Services в приложения](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="ea317-117">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 [<span data-ttu-id="ea317-118">Доступ по URL-адресу (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="ea317-118">URL Access &#40;SSRS&#41;</span></span>](../url-access-ssrs.md)  
  
  
