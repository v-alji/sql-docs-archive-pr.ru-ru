---
title: Диалоговое окно «Ход обработки» (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.processprogress.f1
ms.assetid: f3bd5278-3a83-4fd9-9903-e81bdd4b6892
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4e436eeab21a37ae174a5003c01e77c05240238b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750252"
---
# <a name="process-progress-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="bbfb2-102">Диалоговое окно «Ход обработки» (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="bbfb2-102">Process Progress Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="bbfb2-103">Используйте диалоговое окно **Развитие процесса** в средах [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] и [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] для отслеживания состояния обработки в службах [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bbfb2-103">Use the **Process Progress** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to monitor processing in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="bbfb2-104">Диалоговое окно **Ход обработки** появляется при начале обработки объекта служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bbfb2-104">The **Process Progress** dialog box appears when processing begins on an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bbfb2-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="bbfb2-105">Options</span></span>  
 <span data-ttu-id="bbfb2-106">**Дерево состояния**</span><span class="sxs-lookup"><span data-stu-id="bbfb2-106">**Status tree view**</span></span>  
 <span data-ttu-id="bbfb2-107">Показывает сообщения о состоянии от экземпляра служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , касающиеся обрабатываемых объектов, включая время начала, время остановки и сведения о развитии процесса.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-107">Displays status messages from the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance regarding the objects being processed, including start time, stop time, and progress information.</span></span> <span data-ttu-id="bbfb2-108">Чтобы скопировать детали сообщения о состоянии в буфер обмена, щелкните элемент правой кнопкой мыши и выберите команду **Копировать**, или двойным щелчком откройте диалоговое окно **Просмотр подробностей**.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-108">Right-click an item and select **Copy** to copy the details of a status message to the clipboard, or double-click an item to display the **View Details** dialog box.</span></span> <span data-ttu-id="bbfb2-109">Дополнительные сведения о диалоговом окне **Просмотр сведений** см. в разделе [Диалоговое окно "Просмотр подробностей" (службы Analysis Services — многомерные данные)](view-details-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-109">For more information about the **View Details** dialog box, see [View Details Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](view-details-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="bbfb2-110">**Описание состояния**</span><span class="sxs-lookup"><span data-stu-id="bbfb2-110">**Status description**</span></span>  
 <span data-ttu-id="bbfb2-111">Показывает текущее состояние операции обработки.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-111">Displays the current status of the processing operation.</span></span>  
  
 <span data-ttu-id="bbfb2-112">**Остановить**</span><span class="sxs-lookup"><span data-stu-id="bbfb2-112">**Stop**</span></span>  
 <span data-ttu-id="bbfb2-113">Нажмите «Остановить», чтобы прервать операцию.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-113">Click to stop the processing operation.</span></span>  
  
 <span data-ttu-id="bbfb2-114">**Обработать заново**</span><span class="sxs-lookup"><span data-stu-id="bbfb2-114">**Reprocess**</span></span>  
 <span data-ttu-id="bbfb2-115">Нажмите для повторения операции обработки, которую отображало диалоговое окно **Ход обработки** .</span><span class="sxs-lookup"><span data-stu-id="bbfb2-115">Click to repeat the processing operation that displayed the **Process Progress** dialog box.</span></span>  
  
 <span data-ttu-id="bbfb2-116">**Просмотреть сведения**</span><span class="sxs-lookup"><span data-stu-id="bbfb2-116">**View Details**</span></span>  
 <span data-ttu-id="bbfb2-117">Нажмите, чтобы открыть диалоговое окно **Просмотр подробностей** и показать детали элемента, выбранного в **Дереве состояния**.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-117">Click to open the **View Details** dialog box and display details regarding the item selected in **Status tree view**.</span></span> <span data-ttu-id="bbfb2-118">Дополнительные сведения о диалоговом окне **Просмотр сведений** см. в разделе [Диалоговое окно "Просмотр подробностей" (службы Analysis Services — многомерные данные)](view-details-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-118">For more information about the **View Details** dialog box, see [View Details Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](view-details-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbfb2-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="bbfb2-119">See Also</span></span>  
 <span data-ttu-id="bbfb2-120">[Analysis Services конструкторов и диалоговых окон &#40;многомерных данных&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="bbfb2-120">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="bbfb2-121">Обработка объектов многомерной модели</span><span class="sxs-lookup"><span data-stu-id="bbfb2-121">Multidimensional Model Object Processing</span></span>](multidimensional-models/processing-a-multidimensional-model-analysis-services.md)  
  
  
