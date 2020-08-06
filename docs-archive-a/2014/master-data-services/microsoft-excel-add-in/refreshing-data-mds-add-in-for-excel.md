---
title: Обновление данных (надстройка MDS для Excel) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 58dbe99a-288d-4f1c-9cd5-704d6836c945
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 49b6e7bc19c41911c626965b9d1de132796367f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750011"
---
# <a name="refreshing-data-mds-add-in-for-excel"></a><span data-ttu-id="6751f-102">Обновление данных (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="6751f-102">Refreshing Data (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="6751f-103">В [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]обновление данных можно выполнить, когда необходимо получить последние данные из репозитория MDS без открытия нового листа.</span><span class="sxs-lookup"><span data-stu-id="6751f-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], refresh data when you want to get the latest information from the MDS repository without opening a new worksheet.</span></span> <span data-ttu-id="6751f-104">Обновить можно либо все, либо только выделенные ячейки.</span><span class="sxs-lookup"><span data-stu-id="6751f-104">You can refresh either all cells or a selection of cells.</span></span> <span data-ttu-id="6751f-105">Эта возможность может оказаться полезной при вставке столбцов с пользовательскими формулами или других данных, которые не управляются MDS и которые нужно сохранить.</span><span class="sxs-lookup"><span data-stu-id="6751f-105">This can be useful when you have inserted columns with custom formulas or other data that is not managed in MDS and you want to preserve it.</span></span>  
  
## <a name="when-you-can-refresh-mds-managed-data"></a><span data-ttu-id="6751f-106">Когда можно обновлять данные, управляемые MDS</span><span class="sxs-lookup"><span data-stu-id="6751f-106">When You Can Refresh MDS-Managed Data</span></span>  
 <span data-ttu-id="6751f-107">Можно обновлять на активном листе данные, управляемые MDS, если активный лист уже содержит данные, управляемые MDS.</span><span class="sxs-lookup"><span data-stu-id="6751f-107">You can refresh MDS-managed data in an active worksheet if the active worksheet already contains MDS-managed data.</span></span> <span data-ttu-id="6751f-108">Если на листе изменялись значения атрибутов или добавлялись новые элементы, то необходимо опубликовать изменения, прежде чем появится возможность обновления.</span><span class="sxs-lookup"><span data-stu-id="6751f-108">If you have changed attribute values or added members to the worksheet, you must publish your changes before you can refresh.</span></span>  
  
## <a name="refreshing-a-selection"></a><span data-ttu-id="6751f-109">Обновление выделенных ячеек</span><span class="sxs-lookup"><span data-stu-id="6751f-109">Refreshing a Selection</span></span>  
 <span data-ttu-id="6751f-110">Обновить можно либо все, либо только выделенные ячейки.</span><span class="sxs-lookup"><span data-stu-id="6751f-110">You have the choice of refreshing all cells or refreshing only selected cells.</span></span> <span data-ttu-id="6751f-111">Выбранные ячейки должны быть смежными.</span><span class="sxs-lookup"><span data-stu-id="6751f-111">The selected cells must be contiguous.</span></span> <span data-ttu-id="6751f-112">Если выделена область из непрерывных ячеек, будут обновлены все ячейки, управляемые службами MDS, в этом множестве, при этом будут отображены значения, которые хранятся на сервере в данное время.</span><span class="sxs-lookup"><span data-stu-id="6751f-112">If a set of contiguous cells is selected, all MDS managed cells in that set will be updated to display the values currently stored on the server.</span></span> <span data-ttu-id="6751f-113">Неизмененные строки и столбцы, которые не управляются MDS, не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="6751f-113">Unchanged rows and columns that are not managed by MDS are not affected in any way.</span></span>  
  
## <a name="what-happens-when-you-refresh-mds-managed-data"></a><span data-ttu-id="6751f-114">Что происходит при обновлении данных, управляемых MDS</span><span class="sxs-lookup"><span data-stu-id="6751f-114">What Happens When You Refresh MDS-Managed Data</span></span>  
 <span data-ttu-id="6751f-115">Что именно происходит с данными, управляемыми MDS, на листе при обновлении данных в [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]зависит от того, какие изменения произошли в репозитории MDS с тех пор, когда вы в последний раз загружали эти данные.</span><span class="sxs-lookup"><span data-stu-id="6751f-115">When you refresh data in the [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], what happens to the MDS-managed data in the sheet depends on what has changed in the MDS repository since you last loaded the data.</span></span>  
  
-   <span data-ttu-id="6751f-116">Если в репозиторий были добавлены новые элементы, то они добавляются в конец листа и подсвечиваются зеленым цветом.</span><span class="sxs-lookup"><span data-stu-id="6751f-116">If new members have been added to repository, they are added to the end of the worksheet and are highlighted in green.</span></span>  
  
-   <span data-ttu-id="6751f-117">Если из репозитория удалены элементы, то они удалятся и с листа.</span><span class="sxs-lookup"><span data-stu-id="6751f-117">If members were deleted from the repository, they are deleted from the worksheet.</span></span>  
  
-   <span data-ttu-id="6751f-118">Если в репозитории MDS изменились значения атрибутов, то значение на листе обновляется значением из репозитория MDS.</span><span class="sxs-lookup"><span data-stu-id="6751f-118">If an attribute value has changed in the MDS repository, the value in the worksheet is updated with value from the MDS repository.</span></span> <span data-ttu-id="6751f-119">Цвет ячейки не изменяется.</span><span class="sxs-lookup"><span data-stu-id="6751f-119">The cell color does not change.</span></span>  
  
> [!WARNING]
>  -   <span data-ttu-id="6751f-120">Если на активном листе существуют неуправляемые данные в строках ниже строк с данными, управляемыми MDS, то эти данные могут быть перезаписаны.</span><span class="sxs-lookup"><span data-stu-id="6751f-120">In the active worksheet, if non-managed data exists in rows beneath the MDS-managed data, the non-managed data may be overwritten.</span></span> <span data-ttu-id="6751f-121">Это происходит при обновлении листа и добавлении новых строк, управляемых MDS, которые перекрывают неуправляемые данные.</span><span class="sxs-lookup"><span data-stu-id="6751f-121">This occurs when you refresh the sheet and new rows of MDS-managed data, which overlap with the non-managed data, are added.</span></span>  
> -   <span data-ttu-id="6751f-122">Комментарии в ячейках, управляемых MDS, при обновлении удаляются.</span><span class="sxs-lookup"><span data-stu-id="6751f-122">When you refresh, comments on MDS-managed cells are deleted.</span></span>  
  
## <a name="how-to-refresh-mds-managed-data"></a><span data-ttu-id="6751f-123">Как обновить данные, управляемые MDS</span><span class="sxs-lookup"><span data-stu-id="6751f-123">How to Refresh MDS-Managed Data</span></span>  
 <span data-ttu-id="6751f-124">В группе ленты **Подключение и загрузка** под кнопкой **Обновить** есть две команды: **Обновить все** и **Обновить выделенные**.</span><span class="sxs-lookup"><span data-stu-id="6751f-124">In the **Connect and Load** group on the ribbon, the **Refresh** button has two options, **Refresh All** and **Refresh Selection**.</span></span> <span data-ttu-id="6751f-125">По умолчанию эта кнопка на ленте выполняет действие **Обновить все**.</span><span class="sxs-lookup"><span data-stu-id="6751f-125">The default action of the ribbon button is **Refresh All**.</span></span> <span data-ttu-id="6751f-126">Чтобы обновить весь лист значениями с сервера, нажмите кнопку **Обновить** или выберите команду **Обновить все** .</span><span class="sxs-lookup"><span data-stu-id="6751f-126">To refresh the entire sheet with values from the server, click the **Refresh** button or choose the **Refresh All** option.</span></span> <span data-ttu-id="6751f-127">Чтобы обновить только некоторые ячейки листа, выделите их (выделенные ячейки должны быть смежными) и выберите команду **Обновить выделенные** .</span><span class="sxs-lookup"><span data-stu-id="6751f-127">To refresh only some of the cells in a sheet, select the cells (must be one contiguous selection) and choose the **Refresh Selection** option.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="6751f-128">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="6751f-128">Related Tasks</span></span>  
  
|<span data-ttu-id="6751f-129">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="6751f-129">Task Description</span></span>|<span data-ttu-id="6751f-130">Раздел</span><span class="sxs-lookup"><span data-stu-id="6751f-130">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="6751f-131">Установите соединение с базой данных служб [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6751f-131">Create a connection to a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span>|[<span data-ttu-id="6751f-132">Соединение с репозиторием MDS (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="6751f-132">Connect to an MDS Repository &#40;MDS Add-in for Excel&#41;</span></span>](connect-to-an-mds-repository-mds-add-in-for-excel.md)|  
|<span data-ttu-id="6751f-133">Загрузка данных MDS в Excel.</span><span class="sxs-lookup"><span data-stu-id="6751f-133">Load MDS data into Excel.</span></span>|[<span data-ttu-id="6751f-134">Загрузка данных из MDS в Excel</span><span class="sxs-lookup"><span data-stu-id="6751f-134">Load Data from MDS into Excel</span></span>](export-data-to-excel-from-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="6751f-135">См. также</span><span class="sxs-lookup"><span data-stu-id="6751f-135">Related Content</span></span>  
  
-   [<span data-ttu-id="6751f-136">Соединения (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="6751f-136">Connections &#40;MDS Add-in for Excel&#41;</span></span>](connections-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="6751f-137">Загрузка надстройка MDS для Excel &#40;данных&#41;</span><span class="sxs-lookup"><span data-stu-id="6751f-137">Loading Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-exporting-data-to-excel-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="6751f-138">Надстройка Master Data Services для Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="6751f-138">Master Data Services Add-in for Microsoft Excel</span></span>](master-data-services-add-in-for-microsoft-excel.md)  
  
  
