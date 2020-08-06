---
title: rsInternalError — ошибка служб Reporting Services | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- rsInternalError
ms.assetid: 52613d52-fc78-4870-93f0-7d393ab9c335
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 85b88519df810f60c580ad2d6eb355dde236d081
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664678"
---
# <a name="rsinternalerror---reporting-services-error"></a><span data-ttu-id="85fc0-102">rsInternalError - Ошибка службы Reporting Services</span><span class="sxs-lookup"><span data-stu-id="85fc0-102">rsInternalError - Reporting Services Error</span></span>
    
## <a name="details"></a><span data-ttu-id="85fc0-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="85fc0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="85fc0-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="85fc0-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="85fc0-105">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="85fc0-105">Event ID</span></span>|<span data-ttu-id="85fc0-106">rsInternalError</span><span class="sxs-lookup"><span data-stu-id="85fc0-106">rsInternalError</span></span>|  
|<span data-ttu-id="85fc0-107">Источник события</span><span class="sxs-lookup"><span data-stu-id="85fc0-107">Event Source</span></span>|<span data-ttu-id="85fc0-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span><span class="sxs-lookup"><span data-stu-id="85fc0-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span></span>|  
|<span data-ttu-id="85fc0-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="85fc0-109">Component</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="85fc0-110">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="85fc0-110">Message Text</span></span>|<span data-ttu-id="85fc0-111">Произошла внутренняя ошибка на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="85fc0-111">An internal error occurred on the report server.</span></span> <span data-ttu-id="85fc0-112">Дополнительные подробности см. в журнале ошибок.</span><span class="sxs-lookup"><span data-stu-id="85fc0-112">See the error log for more details.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="85fc0-113">Объяснение</span><span class="sxs-lookup"><span data-stu-id="85fc0-113">Explanation</span></span>  
 <span data-ttu-id="85fc0-114">Это общее сообщение об ошибке, за которым часто следует более описательное сообщение об ошибке, предоставляющее больше сведений.</span><span class="sxs-lookup"><span data-stu-id="85fc0-114">This is a generic error message that is often followed by a more descriptive error that provides more detail.</span></span>  
  
 <span data-ttu-id="85fc0-115">Внутренние ошибки случаются редко.</span><span class="sxs-lookup"><span data-stu-id="85fc0-115">Internal errors are uncommon.</span></span> <span data-ttu-id="85fc0-116">При возникновении такой ошибки дополнительные сведения можно получить в журналах трассировки сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="85fc0-116">If you get this error, more information is available in report server trace logs.</span></span> <span data-ttu-id="85fc0-117">Помимо этого, если вы работаете на компьютере, где произошла ошибка, под учетной записью локального администратора, можно также просмотреть стек вызовов.</span><span class="sxs-lookup"><span data-stu-id="85fc0-117">In addition, if you are running as local administrator on the same computer on which the error occurs, you can view the call stack for more information.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="85fc0-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="85fc0-118">User Action</span></span>  
 <span data-ttu-id="85fc0-119">Чтобы определить конкретную причину этого сообщения, просмотрите файлы журнала сервера отчетов, расположенные по адресу \Microsoft SQL Server\MSRS12. \<instancename > \Reporting Services\LogFiles.</span><span class="sxs-lookup"><span data-stu-id="85fc0-119">To determine the specific cause for this message, review the report server log files, which are located at \Microsoft SQL Server\MSRS12.\<instancename >\Reporting Services\LogFiles.</span></span> <span data-ttu-id="85fc0-120">Дополнительные сведения см. в разделе [Файлы и источники журналов служб Reporting Services](../report-server/reporting-services-log-files-and-sources.md).</span><span class="sxs-lookup"><span data-stu-id="85fc0-120">For more information, see [Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md).</span></span>  
  
 <span data-ttu-id="85fc0-121">Для просмотра стека вызова щелкните правой кнопкой мыши на странице, где произошла ошибка, и выберите команду **Исходный код**.</span><span class="sxs-lookup"><span data-stu-id="85fc0-121">To view the call stack, right-click the page on which the error occurs and point to **View Source**.</span></span> <span data-ttu-id="85fc0-122">Для просмотра стека вызовов необходимы разрешения администратора на том компьютере, где возникла ошибка.</span><span class="sxs-lookup"><span data-stu-id="85fc0-122">Viewing the call stack requires administrator permissions on the same computer on which the error occurs.</span></span>  
  
 <span data-ttu-id="85fc0-123">Если дополнительные сведения недоступны, можно повторить попытку запроса.</span><span class="sxs-lookup"><span data-stu-id="85fc0-123">If there is no additional information available, you can try your request again.</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="85fc0-124">Только для внутреннего использования</span><span class="sxs-lookup"><span data-stu-id="85fc0-124">Internal-Only</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85fc0-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="85fc0-125">See Also</span></span>  
 [<span data-ttu-id="85fc0-126">Запуск и остановка службы сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="85fc0-126">Start and Stop the Report Server Service</span></span>](../report-server/start-and-stop-the-report-server-service.md)  
  
  
