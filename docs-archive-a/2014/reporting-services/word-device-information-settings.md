---
title: Настройки сведений об устройстве Word | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Word [Reporting Services]
- device information settings [Reporting Services], Word
ms.assetid: 28146498-fae7-4b13-b47f-6ec05aa8e057
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ddd145c5073003a8dc189e3ed9b1bbb25dc11d09
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654770"
---
# <a name="word-device-information-settings"></a><span data-ttu-id="9acfb-102">Настройки сведений об устройстве Word</span><span class="sxs-lookup"><span data-stu-id="9acfb-102">Word Device Information Settings</span></span>
  <span data-ttu-id="9acfb-103">В следующей таблице перечислены настройки сведений об устройстве для подготовки к просмотру в формате [!INCLUDE[ofprword](../includes/ofprword-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9acfb-103">The following table lists the device information settings for rendering in [!INCLUDE[ofprword](../includes/ofprword-md.md)] format.</span></span>  
  
|<span data-ttu-id="9acfb-104">Параметр</span><span class="sxs-lookup"><span data-stu-id="9acfb-104">Setting</span></span>|<span data-ttu-id="9acfb-105">Значение</span><span class="sxs-lookup"><span data-stu-id="9acfb-105">Value</span></span>|  
|-------------|-----------|  
|`AutoFit`|<span data-ttu-id="9acfb-106">`False`.</span><span class="sxs-lookup"><span data-stu-id="9acfb-106">`False`.</span></span> <span data-ttu-id="9acfb-107">Для автоподбора установлено значение `false` в какой-либо таблице Word.</span><span class="sxs-lookup"><span data-stu-id="9acfb-107">AutoFit is set to `false` set on any Word table.</span></span><br /><br /> <span data-ttu-id="9acfb-108">`True`.</span><span class="sxs-lookup"><span data-stu-id="9acfb-108">`True`.</span></span> <span data-ttu-id="9acfb-109">Для автоподбора установлено значение `true` во всех таблицах Word.</span><span class="sxs-lookup"><span data-stu-id="9acfb-109">AutoFit is set to `true` on every Word table.</span></span><br /><br /> <span data-ttu-id="9acfb-110">`Never`.</span><span class="sxs-lookup"><span data-stu-id="9acfb-110">`Never`.</span></span> <span data-ttu-id="9acfb-111">Значения автоподбора не установлены ни в одной из таблиц Word, производится возврат к поведению по умолчанию для Word.</span><span class="sxs-lookup"><span data-stu-id="9acfb-111">AutoFit values are not set on any Word table and behavior reverts to the Word default.</span></span><br /><br /> <span data-ttu-id="9acfb-112">`Default`.</span><span class="sxs-lookup"><span data-stu-id="9acfb-112">`Default`.</span></span> <span data-ttu-id="9acfb-113">Автоподбор установлен для таблиц, более узких, чем физическая область отрисовки (ширина физической страницы, включая поля) на логической странице.</span><span class="sxs-lookup"><span data-stu-id="9acfb-113">AutoFit is set on tables that are narrower than the physical drawing area (physical page width excluding margins) per logical page.</span></span>|  
|`ExpandToggles`|<span data-ttu-id="9acfb-114">Указывает, должны ли все переключаемые элементы отображаться в полностью раскрытом состоянии.</span><span class="sxs-lookup"><span data-stu-id="9acfb-114">Indicates whether all items that can be toggled should render in their fully-expanded state.</span></span> <span data-ttu-id="9acfb-115">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="9acfb-115">The default value is `false`.</span></span>|  
|`FixedPageWidth`|<span data-ttu-id="9acfb-116">Указывает, будет ли ширина страницы, записанная в DOC-файл, увеличиваться, чтобы уместилась самая широкая страница в тексте отчета.</span><span class="sxs-lookup"><span data-stu-id="9acfb-116">Indicates whether the Page Width written to the DOC file will grow to accommodate the width of the largest page in the Report Body.</span></span> <span data-ttu-id="9acfb-117">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="9acfb-117">The default value is `false`.</span></span>|  
|<span data-ttu-id="9acfb-118">**OmitHyperlinks**</span><span class="sxs-lookup"><span data-stu-id="9acfb-118">**OmitHyperlinks**</span></span>|<span data-ttu-id="9acfb-119">Указывает, опускать ли действие гиперссылки для всех элементов, где оно установлено.</span><span class="sxs-lookup"><span data-stu-id="9acfb-119">Indicates whether to omit the Hyperlink action on all items where it is set.</span></span> <span data-ttu-id="9acfb-120">Значение по умолчанию — `false`</span><span class="sxs-lookup"><span data-stu-id="9acfb-120">The default value is `false`</span></span>|  
|`OmitDrillthroughs`|<span data-ttu-id="9acfb-121">Указывает, опускать ли действие детализации для всех элементов, где оно установлено.</span><span class="sxs-lookup"><span data-stu-id="9acfb-121">Indicates whether to omit the Drillthrough action on all items where it is set.</span></span> <span data-ttu-id="9acfb-122">Значение по умолчанию — `false`</span><span class="sxs-lookup"><span data-stu-id="9acfb-122">The default value is `false`</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9acfb-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="9acfb-123">See Also</span></span>  
 <span data-ttu-id="9acfb-124">[Передача настроек сведений об устройстве в модули подготовки отчетов](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="9acfb-124">[Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span></span>  
 <span data-ttu-id="9acfb-125">[Настройка параметров модуля подготовки отчетов в RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span><span class="sxs-lookup"><span data-stu-id="9acfb-125">[Customize Rendering Extension Parameters in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span></span>  
 [<span data-ttu-id="9acfb-126">Технический справочник (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="9acfb-126">Technical Reference &#40;SSRS&#41;</span></span>](../../2014/reporting-services/technical-reference-ssrs.md)  
  
  
