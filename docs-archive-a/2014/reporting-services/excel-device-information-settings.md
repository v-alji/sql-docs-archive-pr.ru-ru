---
title: Настройки сведений об устройстве Excel | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- device information settings [Reporting Services], Excel rendering
- Excel [Reporting Services], rendering
ms.assetid: bb5f3566-f033-4470-be87-1f52fb7a4ab6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d71c83195c8f91984bbbce95bd00402928fdb36e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735050"
---
# <a name="excel-device-information-settings"></a><span data-ttu-id="a592b-102">Настройки сведений об устройстве Excel</span><span class="sxs-lookup"><span data-stu-id="a592b-102">Excel Device Information Settings</span></span>
  <span data-ttu-id="a592b-103">В следующей таблице перечислены настройки сведений об устройстве для подготовки к просмотру в формате [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a592b-103">The following table lists the device information settings for rendering in [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] format.</span></span>  
  
|<span data-ttu-id="a592b-104">Параметр</span><span class="sxs-lookup"><span data-stu-id="a592b-104">Setting</span></span>|<span data-ttu-id="a592b-105">Значение</span><span class="sxs-lookup"><span data-stu-id="a592b-105">Value</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="a592b-106">**OmitDocumentMap**</span><span class="sxs-lookup"><span data-stu-id="a592b-106">**OmitDocumentMap**</span></span>|<span data-ttu-id="a592b-107">Показывает, нужно ли исключать схему документа из параметров отчетов, поддерживающих ее.</span><span class="sxs-lookup"><span data-stu-id="a592b-107">Indicates whether to omit the document map for reports that support it.</span></span> <span data-ttu-id="a592b-108">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="a592b-108">The default value is `false`.</span></span>|  
|<span data-ttu-id="a592b-109">**OmitFormulas**</span><span class="sxs-lookup"><span data-stu-id="a592b-109">**OmitFormulas**</span></span>|<span data-ttu-id="a592b-110">Показывает, нужно ли исключать формулы из отчета, готового для просмотра.</span><span class="sxs-lookup"><span data-stu-id="a592b-110">Indicates whether to omit formulas from the rendered report.</span></span> <span data-ttu-id="a592b-111">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="a592b-111">The default value is `false`.</span></span>|  
|<span data-ttu-id="a592b-112">`SimplePageHeade`rs</span><span class="sxs-lookup"><span data-stu-id="a592b-112">`SimplePageHeade`rs</span></span>|<span data-ttu-id="a592b-113">Показывает, преобразуется ли верхний колонтитул страницы отчетов в верхний колонтитул Excel при подготовке к просмотру.</span><span class="sxs-lookup"><span data-stu-id="a592b-113">Indicates whether the page header of the report is rendered to the Excel page header.</span></span> <span data-ttu-id="a592b-114">Значение `false` показывает, что верхний колонтитул страницы при подготовке к просмотру преобразуется в первую строку листа.</span><span class="sxs-lookup"><span data-stu-id="a592b-114">A value of `false` indicates that the page header is rendered to the first row of the worksheet.</span></span> <span data-ttu-id="a592b-115">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="a592b-115">The default value is `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a592b-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="a592b-116">See Also</span></span>  
 <xref:ReportExecution2005.ReportExecutionService.Render%2A>   
 <span data-ttu-id="a592b-117">[Передача настроек сведений об устройстве в модули подготовки отчетов](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="a592b-117">[Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span></span>  
 <span data-ttu-id="a592b-118">[Настройка параметров модуля подготовки отчетов в RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span><span class="sxs-lookup"><span data-stu-id="a592b-118">[Customize Rendering Extension Parameters in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span></span>  
 [<span data-ttu-id="a592b-119">Технический справочник (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="a592b-119">Technical Reference &#40;SSRS&#41;</span></span>](../../2014/reporting-services/technical-reference-ssrs.md)  
  
  
