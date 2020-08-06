---
title: Просмотр пространственных данных в обозревателе объектов
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 59cca562-e3f5-4257-b868-adcbcc0142cc
author: rothja
ms.author: jroth
ms.openlocfilehash: 881adf69ee83ee4b7536afae0b190fbec90f132c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664840"
---
# <a name="view-spatial-data-in-object-explorer"></a><span data-ttu-id="8618e-102">Просмотр пространственных данных в обозревателе объектов</span><span class="sxs-lookup"><span data-stu-id="8618e-102">View Spatial Data in Object Explorer</span></span>
  <span data-ttu-id="8618e-103">Окно **Пространственные результаты** в редакторе запросов содержит визуальные средства сопоставления для просмотра результатов запроса к пространственным данным в дополнение к данным, отображаемых в формате сетки в окне **Результаты** .</span><span class="sxs-lookup"><span data-stu-id="8618e-103">The **Spatial results** window in Query Editor provides visual mapping tools for viewing spatial data results in addition to the data displayed in grid format in the **Results** window.</span></span> <span data-ttu-id="8618e-104">Чтобы пространственные данные отображались в окне **Пространственные результаты** , результаты запроса должны содержать по крайней мере один столбец пространственных данных с данными геометрического или географического типа.</span><span class="sxs-lookup"><span data-stu-id="8618e-104">To display spatial data in the **Spatial Results** window, your query results must contain at least one spatial data column with either geometry or geography data.</span></span>  
  
### <a name="to-view-spatial-data-in-the-spatial-results-window"></a><span data-ttu-id="8618e-105">Просмотр пространственных данных в окне «Пространственные результаты»</span><span class="sxs-lookup"><span data-stu-id="8618e-105">To view spatial data in the Spatial results window</span></span>  
  
1.  <span data-ttu-id="8618e-106">Перейдите на вкладку **Пространственные результаты** в редакторе запросов.</span><span class="sxs-lookup"><span data-stu-id="8618e-106">In Query Editor, click the **Spatial results** tab.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8618e-107">Это окно будет недоступно, если в результаты запроса не входят пространственные данные или если задано возвращение результатов в виде текста.</span><span class="sxs-lookup"><span data-stu-id="8618e-107">This window is not available if your query results do not contain spatial data or if you specify that your results are returned as text.</span></span>  
  
2.  <span data-ttu-id="8618e-108">Выберите в списке **Выберите пространственный столбец** столбец для просмотра.</span><span class="sxs-lookup"><span data-stu-id="8618e-108">Select the column you want to view from the **Select spatial column** list.</span></span> <span data-ttu-id="8618e-109">Если в таблице присутствует только один пространственный столбец, он будет выбираться в списке по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8618e-109">If there is only one spatial column in your table, this column is the default option in the list.</span></span>  
  
3.  <span data-ttu-id="8618e-110">В списке **Выберите столбцы меток** выберите непространственный столбец для использования в качестве меток данных.</span><span class="sxs-lookup"><span data-stu-id="8618e-110">Select the non-spatial column you want to use as data labels from the **Select label columns** list.</span></span>  
  
4.  <span data-ttu-id="8618e-111">В списке **Выберите проекцию** выберите проекцию для географических данных.</span><span class="sxs-lookup"><span data-stu-id="8618e-111">Select the projection you want for geography data from the **Select projection** list.</span></span> <span data-ttu-id="8618e-112">По умолчанию используется проекция Equirectangular. Также доступны проекции Mercator, Robinson и Bonne.</span><span class="sxs-lookup"><span data-stu-id="8618e-112">The default projection is Equirectangular; other projections available are Mercator, Robinson, or Bonne.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8618e-113">Список**Выберите проекцию** недоступен, если пространственный столбец содержит геометрические данные.</span><span class="sxs-lookup"><span data-stu-id="8618e-113">**Select projection** is not available if your spatial column contains geometry data.</span></span>  
  
5.  <span data-ttu-id="8618e-114">Чтобы увеличить отображаемый размер сопоставленных элементов, передвиньте ползунок **Масштаб** .</span><span class="sxs-lookup"><span data-stu-id="8618e-114">Adjust the **Zoom** slider to increase the visual size of mapped elements.</span></span> <span data-ttu-id="8618e-115">Для фигур-многоугольников метка будет видима только в случае, если фигура достаточно велика, чтобы вместить текст метки.</span><span class="sxs-lookup"><span data-stu-id="8618e-115">For polygon shapes, the label is visible only when the shape is large enough to hold the label text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8618e-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="8618e-116">See Also</span></span>  
 <span data-ttu-id="8618e-117">[Окно «Пространственные результаты»](spatial-results-window.md) </span><span class="sxs-lookup"><span data-stu-id="8618e-117">[Spatial Results Window](spatial-results-window.md) </span></span>  
 <span data-ttu-id="8618e-118">[Редактор запросов компонента Database Engine (среда SQL Server Management Studio)](database-engine-query-editor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="8618e-118">[Database Engine Query Editor &#40;SQL Server Management Studio&#41;](database-engine-query-editor-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="8618e-119">Редакторы запросов и текста (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="8618e-119">Query and Text Editors &#40;SQL Server Management Studio&#41;</span></span>](query-and-text-editors-sql-server-management-studio.md)  
  
  
