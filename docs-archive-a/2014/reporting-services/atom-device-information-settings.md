---
title: Настройки сведений об устройстве ATOM | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fe4a56a4-5552-423c-85c1-895e2e212fee
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bdbac1500063accf868d4b538b82ba9f3b5aebb0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664036"
---
# <a name="atom-device-information-settings"></a><span data-ttu-id="94d22-102">Настройки сведений об устройстве ATOM</span><span class="sxs-lookup"><span data-stu-id="94d22-102">ATOM Device Information Settings</span></span>
  <span data-ttu-id="94d22-103">Настройки сведений об устройстве для модуля подготовки отчетов Atom включают параметры отправки имени веб-канала Atom и используемую кодировку.</span><span class="sxs-lookup"><span data-stu-id="94d22-103">The device information settings for the Atom rendering extension support submittal of the name of an Atom feed and character encoding to use.</span></span>  
  
 <span data-ttu-id="94d22-104">В следующей таблице перечислены настройки сведений об устройстве для подготовки к просмотру в документе службы данных.</span><span class="sxs-lookup"><span data-stu-id="94d22-104">The following table lists the device information settings for rendering to a data service document.</span></span>  
  
|<span data-ttu-id="94d22-105">Параметр</span><span class="sxs-lookup"><span data-stu-id="94d22-105">Setting</span></span>|<span data-ttu-id="94d22-106">Значение</span><span class="sxs-lookup"><span data-stu-id="94d22-106">Value</span></span>|  
|-------------|-----------|  
|`DataFeed`|<span data-ttu-id="94d22-107">Если указано, веб-канал Atom подготавливается к просмотру в соответствии с именем канала, указанным в этой настройке.</span><span class="sxs-lookup"><span data-stu-id="94d22-107">If specified, renders the Atom feed corresponding to the feed name provided in this setting.</span></span> <span data-ttu-id="94d22-108">В противном случае производится подготовка к просмотру сервисного документа Atom для отчета.</span><span class="sxs-lookup"><span data-stu-id="94d22-108">If not, renders the Atom service document for the report.</span></span> <span data-ttu-id="94d22-109">Уникальный автоматически сформированный идентификатор канала данных.</span><span class="sxs-lookup"><span data-stu-id="94d22-109">The unique auto-generated identifier of the data feed.</span></span> <span data-ttu-id="94d22-110">Это значение используется для внутренних целей и не подлежит изменению.</span><span class="sxs-lookup"><span data-stu-id="94d22-110">This  value is used internally and you should not change it.</span></span>|  
|<span data-ttu-id="94d22-111">**Кодирование**</span><span class="sxs-lookup"><span data-stu-id="94d22-111">**Encoding**</span></span>|<span data-ttu-id="94d22-112">Определенное комитетом по цифровым адресам в Интернете (IANA) название кодировки символов, поддерживаемой платформой .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="94d22-112">The Internet Assigned Numbers Authority (IANA) name of a character encoding that is supported by the .NET Framework.</span></span> <span data-ttu-id="94d22-113">Значение по умолчанию — `UTF-8`.</span><span class="sxs-lookup"><span data-stu-id="94d22-113">The default value is `UTF-8`.</span></span> <span data-ttu-id="94d22-114">В качестве примеров других значений можно привести ASCII, UTF-7 и UTF-16.</span><span class="sxs-lookup"><span data-stu-id="94d22-114">Examples of other values include ASCII, UTF-7, and UTF-16.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="94d22-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="94d22-115">See Also</span></span>  
 <xref:ReportExecution2005.ReportExecutionService.Render%2A>   
 <span data-ttu-id="94d22-116">[Передача настроек сведений об устройстве в модули подготовки отчетов](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="94d22-116">[Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span></span>  
 <span data-ttu-id="94d22-117">[Настройка параметров модуля подготовки отчетов в RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span><span class="sxs-lookup"><span data-stu-id="94d22-117">[Customize Rendering Extension Parameters in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span></span>  
 [<span data-ttu-id="94d22-118">Технический справочник (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="94d22-118">Technical Reference &#40;SSRS&#41;</span></span>](../../2014/reporting-services/technical-reference-ssrs.md)  
  
  
