---
title: Причины ошибок служб Reporting Services и способы их устранения | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- messages [Reporting Services]
- errors [Reporting Services]
- troubleshooting [Reporting Services], errors
ms.assetid: 3db0fef3-37f8-40d0-acc7-1928760dc0e9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fa98b9f760485b80f4fa4ac74f3b8008dc3bbec3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732309"
---
# <a name="cause-and-resolution-of-reporting-services-errors"></a><span data-ttu-id="9f53a-102">Причины ошибок служб Reporting Services и способы их устранения</span><span class="sxs-lookup"><span data-stu-id="9f53a-102">Cause and Resolution of Reporting Services Errors</span></span>
  <span data-ttu-id="9f53a-103">Этот раздел содержит сведения о причинах некоторых ошибок компонента служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]и способах их устранения.</span><span class="sxs-lookup"><span data-stu-id="9f53a-103">This topic contains cause and resolution information for a number of errors related to [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="9f53a-104">Подразделы по сообщениям об ошибках в этом разделе содержат объяснения сообщений об ошибке, возможные причины и действия по устранению проблемы.</span><span class="sxs-lookup"><span data-stu-id="9f53a-104">The error message topics in this section provide an explanation of the error message, possible causes, and any actions you can take to correct the problem.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9f53a-105">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="9f53a-105">In This Section</span></span>  
  
|<span data-ttu-id="9f53a-106">Error</span><span class="sxs-lookup"><span data-stu-id="9f53a-106">Error</span></span>|<span data-ttu-id="9f53a-107">Сообщение</span><span class="sxs-lookup"><span data-stu-id="9f53a-107">Message</span></span>|  
|-----------|-------------|  
|[<span data-ttu-id="9f53a-108">rsAccessedDenied — ошибка служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="9f53a-108">rsAccessedDenied - Reporting Services Error</span></span>](rsaccesseddenied-reporting-services-error.md)|<span data-ttu-id="9f53a-109">Предоставленные пользователю 'mydomain\myAccount' разрешения недостаточны для выполнения данной операции.</span><span class="sxs-lookup"><span data-stu-id="9f53a-109">The permissions granted to user 'mydomain\myAccount' are insufficient for performing this operation.</span></span> <span data-ttu-id="9f53a-110">(rsAccessDenied) (ReportingServicesLibrary).</span><span class="sxs-lookup"><span data-stu-id="9f53a-110">(rsAccessDenied) (ReportingServicesLibrary).</span></span>|  
|[<span data-ttu-id="9f53a-111">rsInternalError — ошибка служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="9f53a-111">rsInternalError - Reporting Services Error</span></span>](rsinternalerror-reporting-services-error.md)|<span data-ttu-id="9f53a-112">Произошла внутренняя ошибка на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="9f53a-112">An internal error occurred on the report server.</span></span> <span data-ttu-id="9f53a-113">Дополнительные подробности см. в журнале ошибок.</span><span class="sxs-lookup"><span data-stu-id="9f53a-113">See the error log for more details.</span></span>|  
|[<span data-ttu-id="9f53a-114">rsModelGenerationError — ошибка служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="9f53a-114">rsModelGenerationError - Reporting Services Error</span></span>](rsmodelgenerationerror-reporting-services-error.md)|<span data-ttu-id="9f53a-115">Во время построения модели произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="9f53a-115">An error occurred while generating model.</span></span> <span data-ttu-id="9f53a-116">(rsModelGenerationError) (ReportingServicesLibrary) %1.</span><span class="sxs-lookup"><span data-stu-id="9f53a-116">(rsModelGenerationError) (ReportingServicesLibrary) %1.</span></span>|  
|[<span data-ttu-id="9f53a-117">rsProcessingError — ошибка служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="9f53a-117">rsProcessingError - Reporting Services Error</span></span>](rsprocessingerror-reporting-services-error.md)|<span data-ttu-id="9f53a-118">Во время обработки отчета произошли ошибки.</span><span class="sxs-lookup"><span data-stu-id="9f53a-118">Errors have occurred in report processing.</span></span>|  
|[<span data-ttu-id="9f53a-119">rsServerConfigurationError — ошибка служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="9f53a-119">rsServerConfigurationError - Reporting Services Error</span></span>](rsserverconfigurationerror-reporting-services-error.md)|<span data-ttu-id="9f53a-120">Сервер отчетов обнаружил ошибку конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9f53a-120">The report server has encountered a configuration error.</span></span>|  
|[<span data-ttu-id="9f53a-121">rrRenderingError — ошибка служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="9f53a-121">rrRenderingError - Reporting Services Error</span></span>](rrrenderingerror-reporting-services-error.md)|<span data-ttu-id="9f53a-122">Во время подготовки отчета к просмотру произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="9f53a-122">An error occurred during rendering of the report.</span></span> <span data-ttu-id="9f53a-123">(rrRenderingError) %1.</span><span class="sxs-lookup"><span data-stu-id="9f53a-123">(rrRenderingError) %1.</span></span>|  
|[<span data-ttu-id="9f53a-124">Служба Windows сервера отчетов (MSSQLServer) 107</span><span class="sxs-lookup"><span data-stu-id="9f53a-124">Report Server Windows Service &#40;MSSQLServer&#41; 107</span></span>](../../relational-databases/errors-events/mssqlserver-107-database-engine-error.md)|<span data-ttu-id="9f53a-125">Службе Windows сервера отчетов (MSSQLSERVER) не удается соединиться с базой данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="9f53a-125">Report Server Windows service (MSSQLSERVER) cannot connect to the report server database.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9f53a-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="9f53a-126">See Also</span></span>  
 <span data-ttu-id="9f53a-127">[Файлы и источники журналов служб Reporting Services](../report-server/reporting-services-log-files-and-sources.md) </span><span class="sxs-lookup"><span data-stu-id="9f53a-127">[Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md) </span></span>  
 [<span data-ttu-id="9f53a-128">Справочник по ошибкам и событиям (службы Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="9f53a-128">Errors and Events Reference &#40;Reporting Services&#41;</span></span>](errors-and-events-reference-reporting-services.md)  
  
  
