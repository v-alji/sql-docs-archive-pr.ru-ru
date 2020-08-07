---
title: Загрузка данных из MDS в Excel | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: dd29389b-928c-4e50-995c-c6af27f97805
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 35672807d5bb108e9386f892aea1847d45ebeb33
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731802"
---
# <a name="load-data-from-mds-into-excel"></a><span data-ttu-id="776b1-102">Загрузка данных из MDS в Excel</span><span class="sxs-lookup"><span data-stu-id="776b1-102">Load Data from MDS into Excel</span></span>
  <span data-ttu-id="776b1-103">В необходимо [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] загрузить данные из репозитория MDS, чтобы работать с ними.</span><span class="sxs-lookup"><span data-stu-id="776b1-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], you must load data from the MDS repository in order to work with it.</span></span>  
  
 <span data-ttu-id="776b1-104">Если необходимо отфильтровать набор данных перед загрузкой, см. раздел [Фильтрация данных перед Загрузкой &#40;надстройка MDS для Excel&#41;](filter-data-before-exporting-mds-add-in-for-excel.md) .</span><span class="sxs-lookup"><span data-stu-id="776b1-104">If you want to filter the dataset before loading, see [Filter Data before Loading &#40;MDS Add-in for Excel&#41;](filter-data-before-exporting-mds-add-in-for-excel.md) instead.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="776b1-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="776b1-105">Prerequisites</span></span>  
 <span data-ttu-id="776b1-106">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="776b1-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="776b1-107">Необходимо иметь разрешение на доступ к функциональной области **Обозреватель** .</span><span class="sxs-lookup"><span data-stu-id="776b1-107">You must have permission to access the **Explorer** functional area.</span></span>  
  
### <a name="to-load-data-from-mds-into-excel"></a><span data-ttu-id="776b1-108">Загрузка данных из MDS в Excel</span><span class="sxs-lookup"><span data-stu-id="776b1-108">To load data from MDS into Excel</span></span>  
  
1.  <span data-ttu-id="776b1-109">Откройте Excel и на вкладке **Основные данные** установите соединение с репозиторием MDS.</span><span class="sxs-lookup"><span data-stu-id="776b1-109">Open Excel and on the **Master Data** tab, connect to an MDS repository.</span></span> <span data-ttu-id="776b1-110">Дополнительные сведения см. в разделе [Соединение с репозиторием MDS (надстройка MDS для Excel)](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="776b1-110">For more information, see [Connect to an MDS Repository &#40;MDS Add-in for Excel&#41;](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span></span>  
  
2.  <span data-ttu-id="776b1-111">На панели **Обозреватель основных данных** выберите модель и версию.</span><span class="sxs-lookup"><span data-stu-id="776b1-111">In the **Master Data Explorer** pane, select a model and version.</span></span> <span data-ttu-id="776b1-112">Заполняется список сущностей.</span><span class="sxs-lookup"><span data-stu-id="776b1-112">The list of entities is populated.</span></span>  
  
    -   <span data-ttu-id="776b1-113">Если панель **Обозреватель основных данных** не видна, в группе **Соединение и загрузка** нажмите **Показать обозреватель**.</span><span class="sxs-lookup"><span data-stu-id="776b1-113">If the **Master Data Explorer** pane is not visible, in the **Connect and Load** group, click **Show Explorer**.</span></span>  
  
    -   <span data-ttu-id="776b1-114">Если панель **Обозреватель основных данных** отключена, то причина этого заключается в том, что существующий лист уже содержит данные, управляемые MDS.</span><span class="sxs-lookup"><span data-stu-id="776b1-114">If the **Master Data Explorer** pane is disabled, it is because the existing sheet already contains MDS-managed data.</span></span> <span data-ttu-id="776b1-115">Чтобы включить эту панель, откройте новый лист.</span><span class="sxs-lookup"><span data-stu-id="776b1-115">To enable the pane, open a new worksheet.</span></span>  
  
3.  <span data-ttu-id="776b1-116">В области **Обозреватель основных данных** в списке сущностей дважды щелкните сущность, которую нужно загрузить.</span><span class="sxs-lookup"><span data-stu-id="776b1-116">In the **Master Data Explorer** pane, in the list of entities, double-click the entity you want to load.</span></span>  
  
    > [!NOTE]  
    >  -   <span data-ttu-id="776b1-117">В Excel загружается только первый миллион элементов.</span><span class="sxs-lookup"><span data-stu-id="776b1-117">Only the first one million members are loaded into Excel.</span></span> <span data-ttu-id="776b1-118">Чтобы отфильтровать список перед загрузкой, на ленте в группе **Подключение и загрузка** нажмите кнопку **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="776b1-118">To filter the list before loading, on the ribbon in the **Connect and Load** group, click **Filter**.</span></span>  
    > -   <span data-ttu-id="776b1-119">В столбцах, которые являются ограниченными списками (атрибутами на основе домена), загружаются только первые 25 000 значений.</span><span class="sxs-lookup"><span data-stu-id="776b1-119">In columns that are constrained lists (domain-based attributes), only the first 25,000 values are loaded.</span></span> <span data-ttu-id="776b1-120">Это число можно изменить в свойстве MaximumDbaEntitySize в файле excelusersettings.config, расположенном на компьютере, на котором установлена программа Excel.</span><span class="sxs-lookup"><span data-stu-id="776b1-120">You can change this number in the MaximumDbaEntitySize property in the excelusersettings.config file located on the computer that Excel is installed on.</span></span> <span data-ttu-id="776b1-121">Этот файл находится в папке C:\Users \\<user \> \AppData\Local\Microsoft\Microsoft SQL Server\120\MasterDataServices \\ .</span><span class="sxs-lookup"><span data-stu-id="776b1-121">This file is located in C:\Users\\<user\>\AppData\Local\Microsoft\Microsoft SQL Server\120\MasterDataServices\\.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="776b1-122">Если при загрузке разделенных текстом данных с помощью надстройки для Microsoft Excel в 32-разрядную версию Excel свойствам **Число ячеек для загрузки** и **Число ячеек для публикации** присвоено максимальное значение 1000, возникнет ошибка нехватки памяти.</span><span class="sxs-lookup"><span data-stu-id="776b1-122">When you load text-delimited data using the Add-in for Microsoft Excel with 32-bit Excel, and the settings for the **Cell Count to Load** and **Cell Count to Publish** properties are both set to the maximum of 1000, an out-of-memory error will occur.</span></span> <span data-ttu-id="776b1-123">Для использования максимальных значений свойств **Число ячеек для загрузки** и **Число ячеек для публикации**необходимо использовать 64-разрядную версию Excel.</span><span class="sxs-lookup"><span data-stu-id="776b1-123">You have to use 64-bit Excel to use the maximum settings for **Cell Count to Load** and **Cell Count to Publish**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="776b1-124">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="776b1-124">Next Steps</span></span>  
 [<span data-ttu-id="776b1-125">Публикация данных из Excel в службах MDS &#40;надстройка MDS для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="776b1-125">Publish Data from Excel to MDS &#40;MDS Add-in for Excel&#41;</span></span>](import-data-from-excel-to-master-data-services-mds-add-in-for-excel.md)  
  
## <a name="see-also"></a><span data-ttu-id="776b1-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="776b1-126">See Also</span></span>  
 <span data-ttu-id="776b1-127">[Загрузка надстройка MDS для Excel &#40;данных&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="776b1-127">[Loading Data &#40;MDS Add-in for Excel&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span></span>  
 <span data-ttu-id="776b1-128">[Диалоговое окно "фильтр" &#40;надстройка MDS для Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="776b1-128">[Filter Dialog Box &#40;MDS Add-in for Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="776b1-129">Публикация &#40;данных надстройка MDS для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="776b1-129">Publishing Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-importing-data-from-excel-mds-add-in-for-excel.md)  
  
  
