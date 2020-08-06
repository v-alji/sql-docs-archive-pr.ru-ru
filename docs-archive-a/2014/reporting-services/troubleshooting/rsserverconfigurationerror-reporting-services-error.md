---
title: rsServerConfigurationError — ошибка служб Reporting Services | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- rsServerConfigurationError
ms.assetid: 0913afc2-34b4-4713-b570-cfd5718975ac
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 02f8a18c42715d1f118920614eb425820130dacb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737859"
---
# <a name="rsserverconfigurationerror---reporting-services-error"></a><span data-ttu-id="934e7-102">rsServerConfigurationError - Ошибка службы Reporting Services</span><span class="sxs-lookup"><span data-stu-id="934e7-102">rsServerConfigurationError - Reporting Services Error</span></span>
    
## <a name="details"></a><span data-ttu-id="934e7-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="934e7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="934e7-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="934e7-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="934e7-105">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="934e7-105">Event ID</span></span>|<span data-ttu-id="934e7-106">rsServerConfiguration</span><span class="sxs-lookup"><span data-stu-id="934e7-106">rsServerConfiguration</span></span>|  
|<span data-ttu-id="934e7-107">Источник события</span><span class="sxs-lookup"><span data-stu-id="934e7-107">Event Source</span></span>|<span data-ttu-id="934e7-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span><span class="sxs-lookup"><span data-stu-id="934e7-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span></span>|  
|<span data-ttu-id="934e7-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="934e7-109">Component</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="934e7-110">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="934e7-110">Message Text</span></span>|<span data-ttu-id="934e7-111">Сервер отчетов обнаружил ошибку конфигурации.</span><span class="sxs-lookup"><span data-stu-id="934e7-111">The report server has encountered a configuration error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="934e7-112">Объяснение</span><span class="sxs-lookup"><span data-stu-id="934e7-112">Explanation</span></span>  
 <span data-ttu-id="934e7-113">Это общая ошибка, возникающая в том случае, когда сервер отчетов или средство разработки отчетов имеет недопустимые параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="934e7-113">This is a general purpose error that occurs when either the report server or a report authoring tool has invalid configuration settings.</span></span> <span data-ttu-id="934e7-114">Эта ошибка обычно сопровождается вторым сообщением, в котором содержится действительная причина первой ошибки.</span><span class="sxs-lookup"><span data-stu-id="934e7-114">The error is usually accompanied by a second message that states the actual cause of the error.</span></span>  
  
 <span data-ttu-id="934e7-115">В следующем списке приведены основные возможные причины.</span><span class="sxs-lookup"><span data-stu-id="934e7-115">The following list summarizes possible causes:</span></span>  
  
-   <span data-ttu-id="934e7-116">Не удалось найти или считать файл RSReportServer.config или RSReportDesigner.config.</span><span class="sxs-lookup"><span data-stu-id="934e7-116">The RSReportServer.config or RSReportDesigner.config file cannot be found or read.</span></span>  
  
-   <span data-ttu-id="934e7-117">XML-элементы в одном из файлов конфигурации отсутствуют или являются недопустимыми.</span><span class="sxs-lookup"><span data-stu-id="934e7-117">XML elements in either configuration file are missing or invalid.</span></span>  
  
-   <span data-ttu-id="934e7-118">Значения одного или нескольких XML-элементов отсутствуют или являются недопустимыми.</span><span class="sxs-lookup"><span data-stu-id="934e7-118">Values for one or more XML elements are missing or invalid.</span></span>  
  
-   <span data-ttu-id="934e7-119">Параметры реестра являются недопустимыми.</span><span class="sxs-lookup"><span data-stu-id="934e7-119">Registry settings are invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="934e7-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="934e7-120">User Action</span></span>  
 <span data-ttu-id="934e7-121">Если эта ошибка возникла после того, как файл конфигурации был изменен вручную, удалите внесенные изменения, вернув прежние значения, либо, при наличии резервной копии, восстановите предыдущую версию файла.</span><span class="sxs-lookup"><span data-stu-id="934e7-121">If this error began to occur after you manually edited a configuration file, remove your changes and enter the previous value, or restore a previous version if you have a backup.</span></span>  
  
 <span data-ttu-id="934e7-122">Для просмотра дополнительных сведений об ошибке, сопровождающих `rsServerConfiguration` ошибку, просмотрите файлы журнала трассировки сервера отчетов, которые находятся в папке \MICROSOFT SQL Server\MSRS12. \<instancename > \Reporting Services\LogFiles.</span><span class="sxs-lookup"><span data-stu-id="934e7-122">To review additional error message information that accompanies the `rsServerConfiguration` error, review the report server trace log files, which are located at \Microsoft SQL Server\MSRS12.\<instancename >\Reporting Services\LogFiles.</span></span> <span data-ttu-id="934e7-123">Дополнительные сведения см. в разделе [Файлы и источники журналов служб Reporting Services](../report-server/reporting-services-log-files-and-sources.md).</span><span class="sxs-lookup"><span data-stu-id="934e7-123">For more information, see [Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md).</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="934e7-124">Только для внутреннего использования</span><span class="sxs-lookup"><span data-stu-id="934e7-124">Internal-Only</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="934e7-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="934e7-125">See Also</span></span>  
 <span data-ttu-id="934e7-126">[Файлы конфигурации служб Reporting Services](../report-server/reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="934e7-126">[Reporting Services Configuration Files](../report-server/reporting-services-configuration-files.md) </span></span>  
 [<span data-ttu-id="934e7-127">Изменение файла конфигурации служб Reporting Services (RSreportserver.config)</span><span class="sxs-lookup"><span data-stu-id="934e7-127">Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;</span></span>](../report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md)  
  
  
