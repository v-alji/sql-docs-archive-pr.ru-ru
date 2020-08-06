---
title: Копировать элементы проекта | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- data sources [Integration Services], copying
- packages [Integration Services], copying
- copying data source views
- copying data sources
- copying packages
- data source views [Integration Services], copying
ms.assetid: 1606c54d-20f9-49f3-a4ef-caad83a772aa
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3456209c467c3b8474e130181d02304911098d2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665054"
---
# <a name="copy-project-items"></a><span data-ttu-id="98e0e-102">Копирование элементов проекта</span><span class="sxs-lookup"><span data-stu-id="98e0e-102">Copy Project Items</span></span>
  <span data-ttu-id="98e0e-103">В этом разделе описывается, как копировать объекты в проекте [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] или между проектами [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="98e0e-103">This topic describes how to copy objects within an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project or between [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects.</span></span> <span data-ttu-id="98e0e-104">Также вы можете скопировать объекты между другими типами проектов [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] и [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98e0e-104">You can also copy objects between the other types of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] projects, [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] and [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="98e0e-105">Чтобы можно было выполнить копирование между проектами, они должны быть частью одного решения среды [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="98e0e-105">To copy between projects, the project must be part of the same [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] solution.</span></span> <span data-ttu-id="98e0e-106">Дополнительные сведения см. в разделе [Проекты служб Integration Services (SSIS)](integration-services-ssis-projects-and-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="98e0e-106">For more information, see [Integration Services &#40;SSIS&#41; Projects](integration-services-ssis-projects-and-solutions.md).</span></span>  
  
### <a name="to-copy-project-level-items"></a><span data-ttu-id="98e0e-107">Копирование элементов уровня проекта</span><span class="sxs-lookup"><span data-stu-id="98e0e-107">To copy project level items</span></span>  
  
1.  <span data-ttu-id="98e0e-108">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] или решение, с которым собираетесь работать.</span><span class="sxs-lookup"><span data-stu-id="98e0e-108">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project or solution that you want to work with.</span></span>  
  
2.  <span data-ttu-id="98e0e-109">Разверните проект и папку, из которой будет выполняться копирование.</span><span class="sxs-lookup"><span data-stu-id="98e0e-109">Expand the project and item folder to copy from.</span></span>  
  
3.  <span data-ttu-id="98e0e-110">Щелкните правой кнопкой мыши элемент и выберите **Копировать**.</span><span class="sxs-lookup"><span data-stu-id="98e0e-110">Right-click the item and click **Copy**.</span></span>  
  
4.  <span data-ttu-id="98e0e-111">Щелкните правой кнопкой мыши проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], в который будет выполняться копирование, и выберите **Вставить**.</span><span class="sxs-lookup"><span data-stu-id="98e0e-111">Right-click the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project to copy to and click **Paste**.</span></span>  
  
     <span data-ttu-id="98e0e-112">Элементы автоматически копируются в нужную папку.</span><span class="sxs-lookup"><span data-stu-id="98e0e-112">The items are automatically copied to the correct folder.</span></span> <span data-ttu-id="98e0e-113">При копировании элементов в проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , которые не являются пакетами, элементы копируются в папку **Разное** .</span><span class="sxs-lookup"><span data-stu-id="98e0e-113">If you copy items to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that are not packages, the items are copied to the **Miscellaneous** folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98e0e-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="98e0e-114">See Also</span></span>  
 <span data-ttu-id="98e0e-115">[Integration Services &#40;пакетов&#41; SSIS](../../2014/integration-services/integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="98e0e-115">[Integration Services &#40;SSIS&#41; Packages](../../2014/integration-services/integration-services-ssis-packages.md) </span></span>  
 [<span data-ttu-id="98e0e-116">Копирование объектов пакета</span><span class="sxs-lookup"><span data-stu-id="98e0e-116">Copy Package Objects</span></span>](../../2014/integration-services/copy-package-objects.md)  
  
  
