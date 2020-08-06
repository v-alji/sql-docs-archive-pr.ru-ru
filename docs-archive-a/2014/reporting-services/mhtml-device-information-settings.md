---
title: Настройки сведений об устройстве MHTML | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- device information settings [Reporting Services], MHTML rendering
- MHTML [Reporting Services]
ms.assetid: 60b85dd8-b4fb-4ad9-be6a-e7c89ac076fe
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 076a0179871775984799fc8ce5366a220f812867
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666463"
---
# <a name="mhtml-device-information-settings"></a><span data-ttu-id="53875-102">Настройки сведений об устройстве MHTML</span><span class="sxs-lookup"><span data-stu-id="53875-102">MHTML Device Information Settings</span></span>
  <span data-ttu-id="53875-103">В следующей таблице перечислены настройки сведений об устройстве, предназначенные для подготовки отчетов к просмотру в формате веб-архива (MHTML).</span><span class="sxs-lookup"><span data-stu-id="53875-103">The following table lists the device information settings for rendering reports in Web archive (MHTML) format.</span></span>  
  
|<span data-ttu-id="53875-104">Параметр</span><span class="sxs-lookup"><span data-stu-id="53875-104">Setting</span></span>|<span data-ttu-id="53875-105">Значение</span><span class="sxs-lookup"><span data-stu-id="53875-105">Value</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="53875-106">**JavaScript**</span><span class="sxs-lookup"><span data-stu-id="53875-106">**JavaScript**</span></span>|<span data-ttu-id="53875-107">Указывает, поддерживается ли JavaScript в отчете, готовом для просмотра.</span><span class="sxs-lookup"><span data-stu-id="53875-107">Indicates whether JavaScript is supported in the rendered report.</span></span>|  
|<span data-ttu-id="53875-108">**OutlookCompat**</span><span class="sxs-lookup"><span data-stu-id="53875-108">**OutlookCompat**</span></span>|<span data-ttu-id="53875-109">Указывает, нужно ли использовать при подготовке к просмотру дополнительные метаданные для улучшения отображения отчета в Outlook.</span><span class="sxs-lookup"><span data-stu-id="53875-109">Indicates whether to render with extra metadata that makes the report look better in Outlook.</span></span> <span data-ttu-id="53875-110">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="53875-110">The default value is `true`.</span></span>|  
|<span data-ttu-id="53875-111">**Фрагмент MHTML**</span><span class="sxs-lookup"><span data-stu-id="53875-111">**MHTML Fragment**</span></span>|<span data-ttu-id="53875-112">Показывает, создается ли MHTML-фрагмент вместо полного MHTML-документа.</span><span class="sxs-lookup"><span data-stu-id="53875-112">Indicates whether an MHTML fragment is created in place of a full MHTML document.</span></span> <span data-ttu-id="53875-113">MHTML-фрагмент включает содержимое отчета в элементе TABLE и не содержит элементы MHTML и BODY.</span><span class="sxs-lookup"><span data-stu-id="53875-113">An MHTML fragment includes the report content in a TABLE element and omits the HTML and BODY elements.</span></span> <span data-ttu-id="53875-114">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="53875-114">The default value is `false`.</span></span>|  
|<span data-ttu-id="53875-115">**DataVisualizationFitSizing**</span><span class="sxs-lookup"><span data-stu-id="53875-115">**DataVisualizationFitSizing**</span></span>|<span data-ttu-id="53875-116">Указывает поведение визуализации данных при ее использовании в табликсе.</span><span class="sxs-lookup"><span data-stu-id="53875-116">Indicates data visualization fit behavior when inside a tablix.</span></span> <span data-ttu-id="53875-117">Сюда входят: диаграмма, датчик и карта.</span><span class="sxs-lookup"><span data-stu-id="53875-117">This includes chart, gauge, and map.</span></span><br /><br /> <span data-ttu-id="53875-118">Возможные значения: **Приблизительно** и **Точно**.</span><span class="sxs-lookup"><span data-stu-id="53875-118">The possible values are **Approximate** and **Exact**.</span></span><br /><br /> <span data-ttu-id="53875-119">Значение по умолчанию ― **Приблизительно**.</span><span class="sxs-lookup"><span data-stu-id="53875-119">The default value is **Approximate**.</span></span> <span data-ttu-id="53875-120">Если параметр удаляется из файла **rsreportserver.config** , то по умолчанию будет использоваться поведение **Точно**.</span><span class="sxs-lookup"><span data-stu-id="53875-120">If the setting is removed from the **rsreportserver.config** file then the default behavior is **Exact**.</span></span><br /><br /> <span data-ttu-id="53875-121">Выбор значения **Точно** может негативно сказаться на производительности, поскольку на обработку для определения точного размера может уйти больше времени.</span><span class="sxs-lookup"><span data-stu-id="53875-121">Enabling **Exact** may have performance impact because the processing to determine the exact size may take longer.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="53875-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="53875-122">See Also</span></span>  
 <xref:ReportExecution2005.ReportExecutionService.Render%2A>   
 <span data-ttu-id="53875-123">[Передача настроек сведений об устройстве модулям подготовки отчетов к просмотру](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="53875-123">[Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span></span>  
 <span data-ttu-id="53875-124">[Настройка параметров модулей подготовки отчетов в RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span><span class="sxs-lookup"><span data-stu-id="53875-124">[Customize Rendering Extension Parameters in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span></span>  
 [<span data-ttu-id="53875-125">Технический справочник (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="53875-125">Technical Reference &#40;SSRS&#41;</span></span>](../../2014/reporting-services/technical-reference-ssrs.md)  
  
  
