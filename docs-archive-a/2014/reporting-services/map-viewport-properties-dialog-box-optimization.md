---
title: Диалоговое окно "Свойства окна просмотра карт", оптимизация | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.mapviewport.optimization.f1
- "10522"
ms.assetid: 8c0310ba-eedd-4c9f-95bd-1f9e2a1a8ed3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1adbeccdedb8d80900047790d94ff35568460ff4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750448"
---
# <a name="map-viewport-properties-dialog-box-optimization"></a><span data-ttu-id="2d322-102">Диалоговое окно «Свойства окна просмотра карты», вкладка «Оптимизация»</span><span class="sxs-lookup"><span data-stu-id="2d322-102">Map Viewport Properties Dialog Box, Optimization</span></span>
  <span data-ttu-id="2d322-103">Вкладка **Оптимизация** диалогового окна **Свойства окна просмотра карты** позволяет управлять разрешением при просмотре карты в отчете.</span><span class="sxs-lookup"><span data-stu-id="2d322-103">Select **Optimization** for the **Map Viewport Properties** dialog box to help control the resolution for viewing a map in a report.</span></span>  
  
 <span data-ttu-id="2d322-104">Если пространственные данные внедрены в отчет, то чем выше разрешение, тем больше данных сохраняется в отчете.</span><span class="sxs-lookup"><span data-stu-id="2d322-104">When spatial data is embedded in the report, higher resolution means more data is stored in the report.</span></span> <span data-ttu-id="2d322-105">Если пространственные данные не внедрены в отчет, то при более высоком разрешении обработчик отчетов затрачивает больше времени на создание подробной карты.</span><span class="sxs-lookup"><span data-stu-id="2d322-105">When spatial data is not embedded in the report, higher resolution means that the report processor spends more time creating the map details.</span></span> <span data-ttu-id="2d322-106">Чем ниже разрешение, тем меньше времени приходится ожидать подготовки отчета к просмотру.</span><span class="sxs-lookup"><span data-stu-id="2d322-106">Lower resolution means less time waiting for the report to render.</span></span>  
  
 <span data-ttu-id="2d322-107">Нажмите кнопку **Выражение** (*fx*), чтобы изменить выражение, задающее значение параметра.</span><span class="sxs-lookup"><span data-stu-id="2d322-107">Click the **Expression** (*fx*) button to edit an expression that sets the value of the option.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2d322-108">Варианты</span><span class="sxs-lookup"><span data-stu-id="2d322-108">Options</span></span>  
 <span data-ttu-id="2d322-109">**Производительность**</span><span class="sxs-lookup"><span data-stu-id="2d322-109">**Performance**</span></span>  
 <span data-ttu-id="2d322-110">Передвиньте указатель ближе к отметке **Производительность** , чтобы упростить карту и отображать меньше подробностей.</span><span class="sxs-lookup"><span data-stu-id="2d322-110">Slide the pointer closer to **Performance** to simplify the map and display less detail.</span></span>  
  
 <span data-ttu-id="2d322-111">**Качество**</span><span class="sxs-lookup"><span data-stu-id="2d322-111">**Quality**</span></span>  
 <span data-ttu-id="2d322-112">Передвиньте указатель ближе к отметке **Качество** , чтобы отрисовывать более подробную карту.</span><span class="sxs-lookup"><span data-stu-id="2d322-112">Slide the pointer closer to **Quality** to draw the map with greater detail.</span></span>  
  
 <span data-ttu-id="2d322-113">**Разрешение карты**</span><span class="sxs-lookup"><span data-stu-id="2d322-113">**Map resolution**</span></span>  
 <span data-ttu-id="2d322-114">Укажите разрешение карты.</span><span class="sxs-lookup"><span data-stu-id="2d322-114">Specify a map resolution.</span></span> <span data-ttu-id="2d322-115">Это значение указывает минимальный размер (в пунктах) элементов, отображаемых на карте, готовой для просмотра.</span><span class="sxs-lookup"><span data-stu-id="2d322-115">This value specifies the smallest detail that you want to see in the rendered map in points.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d322-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="2d322-116">See Also</span></span>  
 <span data-ttu-id="2d322-117">[Карты (построитель отчетов и службы SSRS)](report-design/maps-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2d322-117">[Maps &#40;Report Builder and SSRS&#41;](report-design/maps-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2d322-118">[Устранение неполадок в отчетах: отчеты-карты (построитель отчетов и службы SSRS)](report-design/troubleshoot-reports-map-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2d322-118">[Troubleshoot Reports: Map Reports &#40;Report Builder and SSRS&#41;](report-design/troubleshoot-reports-map-reports-report-builder-and-ssrs.md)</span></span>  
  
  
