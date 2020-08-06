---
title: Добавление на карту пользовательских местоположений (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- MICROSOFT.REPORTDESIGNER.MAPPOINT.POINTTEMPLATE
ms.assetid: 7d36faae-5bcc-446a-9eba-f42349cafacb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 167558534280f08d576205b5ff1b94d0588fcb78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738003"
---
# <a name="add-custom-locations-to-a-map-report-builder-and-ssrs"></a><span data-ttu-id="4f588-102">Добавление на карту пользовательских местоположений (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="4f588-102">Add Custom Locations to a Map (Report Builder and SSRS)</span></span>
  <span data-ttu-id="4f588-103">После добавления карты в отчет в нее можно добавлять собственные точечные местоположения.</span><span class="sxs-lookup"><span data-stu-id="4f588-103">After you add a map to a report, you can add your own point locations.</span></span>  
  
 <span data-ttu-id="4f588-104">Параметры отображения всех точек слоя управляются путем задания свойств точек слоя.</span><span class="sxs-lookup"><span data-stu-id="4f588-104">Display properties for all points on a layer are controlled by setting options for the point properties for the layer.</span></span> <span data-ttu-id="4f588-105">Для выбранной внедренной точки можно переопределить свойства отображения.</span><span class="sxs-lookup"><span data-stu-id="4f588-105">For a selected embedded point, you can override the display properties.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4f588-106">При переопределении свойств отображения слоя для внедренной точки произведенные изменения необратимы.</span><span class="sxs-lookup"><span data-stu-id="4f588-106">When you override the layer display properties for the embedded point, the changes that you make are not reversible.</span></span>  
  
 <span data-ttu-id="4f588-107">Дополнительные сведения см. в разделе [Изменение параметров отображения многоугольников, линий и точек с помощью правил и аналитических данных (построитель отчетов и службы SSRS)](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span><span class="sxs-lookup"><span data-stu-id="4f588-107">For more information, see [Vary Polygon, Line, and Point Display by Rules and Analytical Data &#40;Report Builder and SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-point-layer"></a><span data-ttu-id="4f588-108">Добавление слоя точек</span><span class="sxs-lookup"><span data-stu-id="4f588-108">To add a point layer</span></span>  
  
1.  <span data-ttu-id="4f588-109">Чтобы выбрать карту и отобразить панель «Карта», щелкните карту в области конструктора отчетов.</span><span class="sxs-lookup"><span data-stu-id="4f588-109">On the report design surface, click the map to select it and display the Map pane.</span></span>  
  
2.  <span data-ttu-id="4f588-110">На панели инструментов нажмите кнопку **Добавить слой**.</span><span class="sxs-lookup"><span data-stu-id="4f588-110">On the toolbar, click **Add Layer**.</span></span>  
  
3.  <span data-ttu-id="4f588-111">Из раскрывающегося списка выберите **Добавить слой точек**.</span><span class="sxs-lookup"><span data-stu-id="4f588-111">From the drop-down list, click **Add Point Layer**.</span></span> <span data-ttu-id="4f588-112">На карту добавляется слой точек без точек.</span><span class="sxs-lookup"><span data-stu-id="4f588-112">A point layer with no points is added to the map.</span></span> <span data-ttu-id="4f588-113">По умолчанию слой точек готов к добавлению внедренных точек.</span><span class="sxs-lookup"><span data-stu-id="4f588-113">By default, the point layer is ready for embedded points.</span></span>  
  
### <a name="to-add-a-custom-point"></a><span data-ttu-id="4f588-114">Добавление пользовательской точки</span><span class="sxs-lookup"><span data-stu-id="4f588-114">To add a custom point</span></span>  
  
1.  <span data-ttu-id="4f588-115">Чтобы выбрать карту и отобразить панель «Карта», щелкните карту в области конструктора отчетов.</span><span class="sxs-lookup"><span data-stu-id="4f588-115">On the report design surface, click the map to select it and display the Map pane.</span></span>  
  
2.  <span data-ttu-id="4f588-116">На панели "Карта" щелкните правой кнопкой мыши слой точек типа **Внедренный**, а затем выберите пункт **Добавить точку**.</span><span class="sxs-lookup"><span data-stu-id="4f588-116">In the Map pane, right-click a point layer that has type **Embedded**, and then click **Add Point**.</span></span> <span data-ttu-id="4f588-117">Курсор превращается в перекрестье.</span><span class="sxs-lookup"><span data-stu-id="4f588-117">The cursor changes to crosshairs.</span></span>  
  
3.  <span data-ttu-id="4f588-118">Чтобы добавить точку, щелкните определенное положение на карте.</span><span class="sxs-lookup"><span data-stu-id="4f588-118">To add a point, click a location on the map.</span></span> <span data-ttu-id="4f588-119">Внедренная точка добавляется в выбранный слой в местоположении щелчка.</span><span class="sxs-lookup"><span data-stu-id="4f588-119">An embedded point is added to the selected layer at the location where you click.</span></span>  
  
### <a name="to-customize-the-display-for-an-embedded-point"></a><span data-ttu-id="4f588-120">Настройка отображения внедренной точки</span><span class="sxs-lookup"><span data-stu-id="4f588-120">To customize the display for an embedded point</span></span>  
  
1.  <span data-ttu-id="4f588-121">Щелкните правой кнопкой мыши точку и выберите пункт **Свойства точки**.</span><span class="sxs-lookup"><span data-stu-id="4f588-121">Right-click the point, and then click **Point Properties**.</span></span> <span data-ttu-id="4f588-122">Открывается диалоговое окно **Свойства внедренных точек карты** .</span><span class="sxs-lookup"><span data-stu-id="4f588-122">The **Map Embedded Point Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="4f588-123">Установите флажок **Переопределить параметры точек для данного слоя**.</span><span class="sxs-lookup"><span data-stu-id="4f588-123">Click **Override point options for this layer**.</span></span> <span data-ttu-id="4f588-124">На левой панели появится несколько страниц свойств.</span><span class="sxs-lookup"><span data-stu-id="4f588-124">Multiple property pages appear in the left pane.</span></span>  
  
3.  <span data-ttu-id="4f588-125">Переходите по страницам и задавайте свойства отображения, которые необходимо применить к данной точке.</span><span class="sxs-lookup"><span data-stu-id="4f588-125">Click the pages and set the display properties that you want to apply to this point.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f588-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="4f588-126">See Also</span></span>  
 <span data-ttu-id="4f588-127">[Карты (построитель отчетов и службы SSRS)](maps-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4f588-127">[Maps &#40;Report Builder and SSRS&#41;](maps-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="4f588-128">Изменение параметров отображения многоугольников, линий и точек с помощью правил и аналитических данных (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="4f588-128">Vary Polygon, Line, and Point Display by Rules and Analytical Data &#40;Report Builder and SSRS&#41;</span></span>](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md)  
  
  
