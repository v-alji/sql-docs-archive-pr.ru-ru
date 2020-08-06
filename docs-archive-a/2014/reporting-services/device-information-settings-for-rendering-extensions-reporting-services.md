---
title: Параметры сведений об устройстве для модулей подготовки отчетов к просмотру (службы Reporting Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 947b0ee1-bb35-4b4e-9527-dc501566e7d1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f15e27e01cd43bafda3aede3deca7729f2c89756
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735082"
---
# <a name="device-information-settings-for-rendering-extensions-reporting-services"></a><span data-ttu-id="cc98b-102">Параметры сведений об устройстве для модулей подготовки отчетов к просмотру (службы Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="cc98b-102">Device Information Settings for Rendering Extensions (Reporting Services)</span></span>
  <span data-ttu-id="cc98b-103">В службах [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]настройки сведений об устройстве используются для передачи параметров подготовки к просмотру модуля подготовки отчетов.</span><span class="sxs-lookup"><span data-stu-id="cc98b-103">In [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], device information settings are used to pass rendering parameters to a rendering extension.</span></span> <span data-ttu-id="cc98b-104">Каждый модуль подготовки отчетов принимает определенный набор параметров.</span><span class="sxs-lookup"><span data-stu-id="cc98b-104">Each rendering extension accepts a specific set of settings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cc98b-105">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="cc98b-105">In This Section</span></span>  
  
|<span data-ttu-id="cc98b-106">Раздел</span><span class="sxs-lookup"><span data-stu-id="cc98b-106">Topic</span></span>|<span data-ttu-id="cc98b-107">Description</span><span class="sxs-lookup"><span data-stu-id="cc98b-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="cc98b-108">Настройки сведений об устройстве ATOM</span><span class="sxs-lookup"><span data-stu-id="cc98b-108">ATOM Device Information Settings</span></span>](../../2014/reporting-services/atom-device-information-settings.md)|<span data-ttu-id="cc98b-109">Описывает настройки сведений об устройстве, связанные с подготовкой к просмотру в формате, совместимом с Atom.</span><span class="sxs-lookup"><span data-stu-id="cc98b-109">Describes the device information settings that are associated with Atom compliant rendering output.</span></span>|  
|[<span data-ttu-id="cc98b-110">Настройки сведений об устройстве CSV</span><span class="sxs-lookup"><span data-stu-id="cc98b-110">CSV Device Information Settings</span></span>](csv-device-information-settings.md)|<span data-ttu-id="cc98b-111">Описывает настройки сведений об устройстве, связанные с подготовкой к просмотру в формате CSV.</span><span class="sxs-lookup"><span data-stu-id="cc98b-111">Describes the device information settings that are associated with CSV rendering output.</span></span>|  
|[<span data-ttu-id="cc98b-112">Настройки сведений об устройстве Excel</span><span class="sxs-lookup"><span data-stu-id="cc98b-112">Excel Device Information Settings</span></span>](excel-device-information-settings.md)|<span data-ttu-id="cc98b-113">Описывает настройки сведений об устройстве, связанные с подготовкой к просмотру в формате Excel.</span><span class="sxs-lookup"><span data-stu-id="cc98b-113">Describes the device information settings that are associated with Excel rendering output.</span></span>|  
|[<span data-ttu-id="cc98b-114">Настройки сведений об устройстве Word</span><span class="sxs-lookup"><span data-stu-id="cc98b-114">Word Device Information Settings</span></span>](word-device-information-settings.md)|<span data-ttu-id="cc98b-115">Описывает настройки сведений об устройстве, связанные с подготовкой к просмотру в формате Word.</span><span class="sxs-lookup"><span data-stu-id="cc98b-115">Describes the device information settings that are associated with Word rendering output.</span></span>|  
|[<span data-ttu-id="cc98b-116">Настройки сведений об устройстве HTML</span><span class="sxs-lookup"><span data-stu-id="cc98b-116">HTML Device Information Settings</span></span>](html-device-information-settings.md)|<span data-ttu-id="cc98b-117">Описывает настройки сведений об устройстве, связанные с подготовкой к просмотру в формате HTML.</span><span class="sxs-lookup"><span data-stu-id="cc98b-117">Describes the device information settings that are associated with HTML rendering output.</span></span>|  
|[<span data-ttu-id="cc98b-118">Настройки сведений об устройстве вывода изображений</span><span class="sxs-lookup"><span data-stu-id="cc98b-118">Image Device Information Settings</span></span>](image-device-information-settings.md)|<span data-ttu-id="cc98b-119">Описывает настройки сведений об устройстве, связанные с подготовкой к просмотру в формате IMAGE.</span><span class="sxs-lookup"><span data-stu-id="cc98b-119">Describes the device information settings that are associated with IMAGE rendering output.</span></span>|  
|[<span data-ttu-id="cc98b-120">Настройки сведений об устройстве MHTML</span><span class="sxs-lookup"><span data-stu-id="cc98b-120">MHTML Device Information Settings</span></span>](mhtml-device-information-settings.md)|<span data-ttu-id="cc98b-121">Описывает настройки сведений об устройстве, связанные с подготовкой к просмотру в формате MHTML.</span><span class="sxs-lookup"><span data-stu-id="cc98b-121">Describes the device information settings that are associated with MHTML rendering output.</span></span>|  
|[<span data-ttu-id="cc98b-122">Настройки сведений об устройстве PDF</span><span class="sxs-lookup"><span data-stu-id="cc98b-122">PDF Device Information Settings</span></span>](pdf-device-information-settings.md)|<span data-ttu-id="cc98b-123">Описывает настройки сведений об устройстве, связанные с подготовкой к просмотру в формате PDF.</span><span class="sxs-lookup"><span data-stu-id="cc98b-123">Describes the device information settings that are associated with PDF rendering output.</span></span>|  
|[<span data-ttu-id="cc98b-124">Настройки сведений об устройстве XML</span><span class="sxs-lookup"><span data-stu-id="cc98b-124">XML Device Information Settings</span></span>](xml-device-information-settings.md)|<span data-ttu-id="cc98b-125">Описывает настройки сведений об устройстве, связанные с подготовкой к просмотру в формате XML.</span><span class="sxs-lookup"><span data-stu-id="cc98b-125">Describes the device information settings that are associated with XML rendering output.</span></span>|  
|[<span data-ttu-id="cc98b-126">Настройки сведений об устройстве RGDI</span><span class="sxs-lookup"><span data-stu-id="cc98b-126">RGDI Device Information Settings</span></span>](rgdi-device-information-settings.md)|<span data-ttu-id="cc98b-127">Описывает настройки сведений об устройстве, связанные с подготовкой к просмотру в формате RGDI.</span><span class="sxs-lookup"><span data-stu-id="cc98b-127">Describes the device information settings that are associated with RGDI rendering output.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cc98b-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="cc98b-128">See Also</span></span>  
 [<span data-ttu-id="cc98b-129">Настройка параметров модулей подготовки отчетов в RSReportServer.Config</span><span class="sxs-lookup"><span data-stu-id="cc98b-129">Customize Rendering Extension Parameters in RSReportServer.Config</span></span>](customize-rendering-extension-parameters-in-rsreportserver-config.md)  
  
  
