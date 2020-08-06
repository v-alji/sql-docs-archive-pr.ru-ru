---
title: Окно «Пространственные результаты»
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c2d5a477-6496-4d01-adee-7322ebdfadf3
author: rothja
ms.author: jroth
ms.openlocfilehash: 5e018ec9f016dfc51ed1bb055ba94abf12bc878f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752083"
---
# <a name="spatial-results-window"></a><span data-ttu-id="637f0-102">Окно «Пространственные результаты»</span><span class="sxs-lookup"><span data-stu-id="637f0-102">Spatial Results Window</span></span>
  <span data-ttu-id="637f0-103">Окно **Пространственные результаты** содержит визуальные средства сопоставления для просмотра пространственных данных.</span><span class="sxs-lookup"><span data-stu-id="637f0-103">The **Spatial results** window provides visual mapping tools for viewing spatial data.</span></span> <span data-ttu-id="637f0-104">Чтобы использовать окно «Пространственные результаты», результаты запроса должны содержать по крайней мере один пространственный столбец с данными геометрического или географического типа.</span><span class="sxs-lookup"><span data-stu-id="637f0-104">To view spatial results, your query results must include a spatial column with either geometry or geography data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="637f0-105">Окно **Пространственные результаты** доступно только в случае, если результаты возвращаются в сетку в окне **Результаты** .</span><span class="sxs-lookup"><span data-stu-id="637f0-105">The **Spatial results** window is only available if your results are returned to a grid in the **Results** window.</span></span> <span data-ttu-id="637f0-106">Если для результатов задано возвращение в виде текста, это окно будет недоступно.</span><span class="sxs-lookup"><span data-stu-id="637f0-106">If you specify that your results are returned as text, this window is not available.</span></span>  
  
## <a name="options"></a><span data-ttu-id="637f0-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="637f0-107">Options</span></span>  
 <span data-ttu-id="637f0-108">**Выберите пространственный столбец**</span><span class="sxs-lookup"><span data-stu-id="637f0-108">**Select spatial column**</span></span>  
 <span data-ttu-id="637f0-109">Укажите пространственный столбец для просмотра из числа пространственных столбцов в результатах запроса.</span><span class="sxs-lookup"><span data-stu-id="637f0-109">Specify the spatial column you want to view from the spatial columns in the query results.</span></span> <span data-ttu-id="637f0-110">В один момент времени можно выбрать только один столбец.</span><span class="sxs-lookup"><span data-stu-id="637f0-110">Only one column can be selected at a time.</span></span>  
  
 <span data-ttu-id="637f0-111">**Выберите столбец меток**</span><span class="sxs-lookup"><span data-stu-id="637f0-111">**Select label column**</span></span>  
 <span data-ttu-id="637f0-112">Укажите непространственный столбец из числа столбцов, возвращаемых в результатах запроса, чтобы задать метки для пространственных данных.</span><span class="sxs-lookup"><span data-stu-id="637f0-112">Specify the non-spatial column from the columns returned in the query results to label the spatial data.</span></span> <span data-ttu-id="637f0-113">В один момент времени можно выбрать только один столбец.</span><span class="sxs-lookup"><span data-stu-id="637f0-113">Only one column can be selected at a time.</span></span>  
  
 <span data-ttu-id="637f0-114">Этот параметр недоступен, если в запросе возвращаются только объекты Point.</span><span class="sxs-lookup"><span data-stu-id="637f0-114">This option is not available when only point instances are returned in a query.</span></span>  
  
 <span data-ttu-id="637f0-115">**Выберите проекцию**</span><span class="sxs-lookup"><span data-stu-id="637f0-115">**Select projection**</span></span>  
 <span data-ttu-id="637f0-116">Географические данные отображаются в одной из четырех проекций: равноугольная проекция, проекция Меркатора, проекция Робинзона или проекция Бонна.</span><span class="sxs-lookup"><span data-stu-id="637f0-116">Display geography data in one of four projections: Equirectangular, Mercator, Robinson, or Bonne.</span></span>  
  
 <span data-ttu-id="637f0-117">Этот параметр недоступен для геометрических данных.</span><span class="sxs-lookup"><span data-stu-id="637f0-117">This option is not available for geometry data.</span></span>  
  
 <span data-ttu-id="637f0-118">**Zoom**</span><span class="sxs-lookup"><span data-stu-id="637f0-118">**Zoom**</span></span>  
 <span data-ttu-id="637f0-119">Регулирует отображение карты по экспоненциальной шкале.</span><span class="sxs-lookup"><span data-stu-id="637f0-119">Adjust the map display on an exponential scale.</span></span>  
  
 <span data-ttu-id="637f0-120">**Отобразить линии сетки**</span><span class="sxs-lookup"><span data-stu-id="637f0-120">**Show grid lines**</span></span>  
 <span data-ttu-id="637f0-121">Включает или выключает линии координатной сетки.</span><span class="sxs-lookup"><span data-stu-id="637f0-121">Toggle coordinate gridlines on or off.</span></span>  
  
 <span data-ttu-id="637f0-122">Для фигур-многоугольников метка будет отображаться только в случае, если фигура достаточно велика, чтобы вместить текст метки.</span><span class="sxs-lookup"><span data-stu-id="637f0-122">For polygon shapes, the label is displayed only when the shape is large enough to hold the label text.</span></span> <span data-ttu-id="637f0-123">Чтобы показать метки для маленьких фигур, увеличьте масштаб.</span><span class="sxs-lookup"><span data-stu-id="637f0-123">To display labels for small shapes, adjust the zoom.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="637f0-124">Для экземпляров Point нельзя задавать метки.</span><span class="sxs-lookup"><span data-stu-id="637f0-124">Point instances cannot be labeled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="637f0-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="637f0-125">See Also</span></span>  
 <span data-ttu-id="637f0-126">[Просмотр пространственных данных в обозревателе объектов](view-spatial-data-in-object-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="637f0-126">[View Spatial Data in Object Explorer](view-spatial-data-in-object-explorer.md) </span></span>  
 <span data-ttu-id="637f0-127">[Пространственные данные (SQL Server)](../spatial/spatial-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="637f0-127">[Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md) </span></span>  
 <span data-ttu-id="637f0-128">[Редактор запросов компонента Database Engine (среда SQL Server Management Studio)](database-engine-query-editor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="637f0-128">[Database Engine Query Editor &#40;SQL Server Management Studio&#41;](database-engine-query-editor-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="637f0-129">Редакторы запросов и текста (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="637f0-129">Query and Text Editors &#40;SQL Server Management Studio&#41;</span></span>](query-and-text-editors-sql-server-management-studio.md)  
  
  
