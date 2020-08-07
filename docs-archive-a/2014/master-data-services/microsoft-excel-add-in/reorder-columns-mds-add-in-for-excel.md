---
title: Переупорядочение столбцов (надстройка MDS для Excel) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: ac00462e-c0f7-4b8d-86f2-d9eda2598a15
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f0c47a631ffe699936a8d45bcc4e47e0b6f0a985
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730790"
---
# <a name="reorder-columns-mds-add-in-for-excel"></a><span data-ttu-id="ad15c-102">Переупорядочение порядка столбцов (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="ad15c-102">Reorder Columns (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="ad15c-103">В службах [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]можно переупорядочить столбцы, отфильтровав список перед загрузкой.</span><span class="sxs-lookup"><span data-stu-id="ad15c-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], you can reorder columns by filtering the list before loading.</span></span>  
  
 <span data-ttu-id="ad15c-104">При переупорядочивании атрибутов в диалоговом окне **Фильтр** данные загружаются в Excel в новом порядке.</span><span class="sxs-lookup"><span data-stu-id="ad15c-104">When you reorder attributes in the **Filter** dialog box, the data is loaded into Excel with the new order.</span></span> <span data-ttu-id="ad15c-105">Однако при следующей фильтрации данных атрибутов будет использоваться порядок, заданный первоначально.</span><span class="sxs-lookup"><span data-stu-id="ad15c-105">However, the next time that you filter the attribute data, the order will revert to the order in the original design.</span></span> <span data-ttu-id="ad15c-106">Чтобы изменить порядок окончательно, администратор должен сделать это в области **Администрирование системы** диспетчера основных данных.</span><span class="sxs-lookup"><span data-stu-id="ad15c-106">To change the order permanently, an administrator should change the order in the **System Administration** area of Master Data Manager.</span></span> <span data-ttu-id="ad15c-107">Дополнительные сведения см. в статье [Change the Order of Attributes](../change-the-order-of-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="ad15c-107">For more information, see [Change the Order of Attributes](../change-the-order-of-attributes.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ad15c-108">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="ad15c-108">Prerequisites</span></span>  
 <span data-ttu-id="ad15c-109">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="ad15c-109">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="ad15c-110">Необходимо иметь разрешение на доступ к функциональной области **Обозреватель** .</span><span class="sxs-lookup"><span data-stu-id="ad15c-110">You must have permission to access the **Explorer** functional area.</span></span>  
  
### <a name="to-reorder-mds-managed-columns"></a><span data-ttu-id="ad15c-111">Переупорядочение столбцов, управляемых MDS</span><span class="sxs-lookup"><span data-stu-id="ad15c-111">To reorder MDS-managed columns</span></span>  
  
1.  <span data-ttu-id="ad15c-112">Откройте Excel и на вкладке **Основные данные** установите соединение с репозиторием MDS.</span><span class="sxs-lookup"><span data-stu-id="ad15c-112">Open Excel and on the **Master Data** tab, connect to an MDS repository.</span></span> <span data-ttu-id="ad15c-113">Дополнительные сведения см. в разделе [Соединение с репозиторием MDS (надстройка MDS для Excel)](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="ad15c-113">For more information, see [Connect to an MDS Repository &#40;MDS Add-in for Excel&#41;](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span></span>  
  
2.  <span data-ttu-id="ad15c-114">На панели **Обозреватель основных данных** выберите модель и версию.</span><span class="sxs-lookup"><span data-stu-id="ad15c-114">In the **Master Data Explorer** pane, select a model and version.</span></span> <span data-ttu-id="ad15c-115">Заполняется список сущностей.</span><span class="sxs-lookup"><span data-stu-id="ad15c-115">The list of entities is populated.</span></span>  
  
    -   <span data-ttu-id="ad15c-116">Если панель **Обозреватель основных данных** не видна, в группе **Соединение и загрузка** нажмите **Показать обозреватель**.</span><span class="sxs-lookup"><span data-stu-id="ad15c-116">If the **Master Data Explorer** pane is not visible, in the **Connect and Load** group, click **Show Explorer**.</span></span>  
  
    -   <span data-ttu-id="ad15c-117">Если панель **Обозреватель основных данных** отключена, то причина этого заключается в том, что существующий лист уже содержит данные, управляемые MDS.</span><span class="sxs-lookup"><span data-stu-id="ad15c-117">If the **Master Data Explorer** pane is disabled, it is because the existing sheet already contains MDS-managed data.</span></span> <span data-ttu-id="ad15c-118">Чтобы включить эту панель, откройте новый лист.</span><span class="sxs-lookup"><span data-stu-id="ad15c-118">To enable the pane, open a new worksheet.</span></span>  
  
3.  <span data-ttu-id="ad15c-119">На панели **Обозреватель основных данных** щелкните сущность.</span><span class="sxs-lookup"><span data-stu-id="ad15c-119">In the **Master Data Explorer** pane, click an entity.</span></span>  
  
4.  <span data-ttu-id="ad15c-120">В группе **Подключение и загрузка** нажмите кнопку **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="ad15c-120">In the **Connect and Load** group, click **Filter**.</span></span>  
  
5.  <span data-ttu-id="ad15c-121">В диалоговом окне **Фильтр** в разделе **Столбцы** щелкните в списке атрибут, который необходимо переместить.</span><span class="sxs-lookup"><span data-stu-id="ad15c-121">In the **Filter** dialog box, in the **Columns** section, in the list of attributes, click the attribute you want to move.</span></span>  
  
6.  <span data-ttu-id="ad15c-122">Справа от списка нажмите стрелку **Вверх** или **Вниз** , чтобы переместить атрибут на листе вправо или влево.</span><span class="sxs-lookup"><span data-stu-id="ad15c-122">To the right of the list, click the **Up** or **Down** arrow to move the attribute left and right in the worksheet.</span></span>  
  
7.  <span data-ttu-id="ad15c-123">Повторите шаг 7 для каждого из атрибутов, пока они не будут представлены в нужном порядке (порядок сверху вниз соответствует порядку на листе слева направо).</span><span class="sxs-lookup"><span data-stu-id="ad15c-123">Repeat step 7 for each attribute until the top-to-bottom order represents the left-to-right order you want in the worksheet.</span></span>  
  
8.  <span data-ttu-id="ad15c-124">Нажмите кнопку **Загрузить данные**.</span><span class="sxs-lookup"><span data-stu-id="ad15c-124">Click **Load Data**.</span></span> <span data-ttu-id="ad15c-125">Лист заполняется данными, управляемыми MDS, а столбцы отображаются в указанном вами порядке.</span><span class="sxs-lookup"><span data-stu-id="ad15c-125">The sheet is populated with MDS-managed data and the columns are displayed in the order you specified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad15c-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="ad15c-126">See Also</span></span>  
 [<span data-ttu-id="ad15c-127">Загрузка надстройка MDS для Excel &#40;данных&#41;</span><span class="sxs-lookup"><span data-stu-id="ad15c-127">Loading Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-exporting-data-to-excel-mds-add-in-for-excel.md)  
  
  
