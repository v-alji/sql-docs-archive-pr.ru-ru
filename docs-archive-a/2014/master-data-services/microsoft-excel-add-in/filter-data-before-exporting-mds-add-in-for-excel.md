---
title: Фильтрация данных перед загрузкой (надстройка MDS для Excel) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 9e30eae0-776b-4a09-aac3-0c0249d92ca5
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 6d0ccf667f37763326e27dcd8d0cfc005627ebc2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731801"
---
# <a name="filter-data-before-loading-mds-add-in-for-excel"></a><span data-ttu-id="8c6fc-102">Фильтрация данных перед их загрузкой (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="8c6fc-102">Filter Data before Loading (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="8c6fc-103">В [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] данные отфильтруются, если требуется ограничить размер или область данных, загружаемых в Excel.</span><span class="sxs-lookup"><span data-stu-id="8c6fc-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], filter data when you want to limit the size or scope of data that you are loading into Excel.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8c6fc-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="8c6fc-104">Prerequisites</span></span>  
 <span data-ttu-id="8c6fc-105">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="8c6fc-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="8c6fc-106">Необходимо иметь разрешение на доступ к функциональной области **Обозреватель** .</span><span class="sxs-lookup"><span data-stu-id="8c6fc-106">You must have permission to access the **Explorer** functional area.</span></span>  
  
### <a name="to-filter-data-before-loading"></a><span data-ttu-id="8c6fc-107">Фильтрация данных перед загрузкой</span><span class="sxs-lookup"><span data-stu-id="8c6fc-107">To filter data before loading</span></span>  
  
1.  <span data-ttu-id="8c6fc-108">Откройте Excel и на вкладке **Основные данные** установите соединение с репозиторием MDS.</span><span class="sxs-lookup"><span data-stu-id="8c6fc-108">Open Excel and on the **Master Data** tab, connect to an MDS repository.</span></span> <span data-ttu-id="8c6fc-109">Дополнительные сведения см. в разделе [Соединение с репозиторием MDS (надстройка MDS для Excel)](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="8c6fc-109">For more information, see [Connect to an MDS Repository &#40;MDS Add-in for Excel&#41;](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span></span>  
  
2.  <span data-ttu-id="8c6fc-110">На панели **Обозреватель основных данных** выберите модель и версию.</span><span class="sxs-lookup"><span data-stu-id="8c6fc-110">In the **Master Data Explorer** pane, select a model and version.</span></span> <span data-ttu-id="8c6fc-111">Заполняется список сущностей.</span><span class="sxs-lookup"><span data-stu-id="8c6fc-111">The list of entities is populated.</span></span>  
  
    -   <span data-ttu-id="8c6fc-112">Если панель **Обозреватель основных данных** не видна, в группе **Соединение и загрузка** нажмите **Показать обозреватель**.</span><span class="sxs-lookup"><span data-stu-id="8c6fc-112">If the **Master Data Explorer** pane is not visible, in the **Connect and Load** group, click **Show Explorer**.</span></span>  
  
    -   <span data-ttu-id="8c6fc-113">Если панель **Обозреватель основных данных** отключена, то причина этого заключается в том, что существующий лист уже содержит данные, управляемые MDS.</span><span class="sxs-lookup"><span data-stu-id="8c6fc-113">If the **Master Data Explorer** pane is disabled, it is because the existing sheet already contains MDS-managed data.</span></span> <span data-ttu-id="8c6fc-114">Чтобы включить эту панель, откройте новый лист.</span><span class="sxs-lookup"><span data-stu-id="8c6fc-114">To enable the pane, open a new worksheet.</span></span>  
  
3.  <span data-ttu-id="8c6fc-115">На панели **Обозреватель основных данных** в списке сущностей выберите сущность, которую нужно отфильтровать.</span><span class="sxs-lookup"><span data-stu-id="8c6fc-115">In the **Master Data Explorer** pane, in the list of entities, click the entity you want to filter.</span></span>  
  
4.  <span data-ttu-id="8c6fc-116">На ленте в группе **Подключение и загрузка** нажмите кнопку **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="8c6fc-116">On the ribbon, in the **Connect and Load** group, click **Filter**.</span></span>  
  
5.  <span data-ttu-id="8c6fc-117">В диалоговом окне **Фильтр** выберите атрибуты (столбцы) для отображения, определите их порядок и при необходимости отфильтруйте данные так, чтобы возвращалось меньшее число строк.</span><span class="sxs-lookup"><span data-stu-id="8c6fc-117">Complete the **Filter** dialog box by selecting the attributes (columns) to display, setting the order of the columns, and if needed, filtering the data so fewer rows are returned.</span></span> <span data-ttu-id="8c6fc-118">На панели **Сводка** можно увидеть, сколько данных будет возвращено.</span><span class="sxs-lookup"><span data-stu-id="8c6fc-118">View the **Summary** pane for how much data will be returned.</span></span> <span data-ttu-id="8c6fc-119">Дополнительные сведения см. в разделе [Диалоговое окно "Фильтр" (надстройка MDS для Excel)](filter-dialog-box-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="8c6fc-119">For more information, see [Filter Dialog Box &#40;MDS Add-in for Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md).</span></span>  
  
6.  <span data-ttu-id="8c6fc-120">Нажмите кнопку **Загрузить данные**.</span><span class="sxs-lookup"><span data-stu-id="8c6fc-120">Click **Load Data**.</span></span> <span data-ttu-id="8c6fc-121">Лист заполняется данными, управляемыми MDS.</span><span class="sxs-lookup"><span data-stu-id="8c6fc-121">The sheet is populated with MDS-managed data.</span></span>  
  
    > [!NOTE]  
    >  -   <span data-ttu-id="8c6fc-122">В Excel загружается только первый миллион элементов.</span><span class="sxs-lookup"><span data-stu-id="8c6fc-122">Only the first one million members are loaded into Excel.</span></span>  
    > -   <span data-ttu-id="8c6fc-123">В столбцах, которые являются ограниченными списками (атрибутами на основе домена), загружается только первая тысяча значений.</span><span class="sxs-lookup"><span data-stu-id="8c6fc-123">In columns that are constrained lists (domain-based attributes), only the first 1000 values are loaded.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8c6fc-124">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="8c6fc-124">Next Steps</span></span>  
 [<span data-ttu-id="8c6fc-125">Публикация данных из Excel в службах MDS &#40;надстройка MDS для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="8c6fc-125">Publish Data from Excel to MDS &#40;MDS Add-in for Excel&#41;</span></span>](import-data-from-excel-to-master-data-services-mds-add-in-for-excel.md)  
  
## <a name="see-also"></a><span data-ttu-id="8c6fc-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="8c6fc-126">See Also</span></span>  
 <span data-ttu-id="8c6fc-127">[Загрузка надстройка MDS для Excel &#40;данных&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="8c6fc-127">[Loading Data &#40;MDS Add-in for Excel&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span></span>  
 <span data-ttu-id="8c6fc-128">[Диалоговое окно "фильтр" &#40;надстройка MDS для Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="8c6fc-128">[Filter Dialog Box &#40;MDS Add-in for Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="8c6fc-129">Переупорядочение столбцов (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="8c6fc-129">Reorder Columns &#40;MDS Add-in for Excel&#41;</span></span>](reorder-columns-mds-add-in-for-excel.md)  
  
  
