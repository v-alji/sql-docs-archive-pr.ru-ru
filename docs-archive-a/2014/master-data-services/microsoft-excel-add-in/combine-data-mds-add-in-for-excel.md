---
title: Объединение данных (надстройка MDS для Excel) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: a867dc15-5a0d-457c-8304-ac323bcf9377
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: bc2d5bffb6d7a12164a8643e9a790b32538f8979
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730798"
---
# <a name="combine-data-mds-add-in-for-excel"></a><span data-ttu-id="51901-102">Объединение данных (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="51901-102">Combine Data (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="51901-103">В [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]объедините данные из двух листов, чтобы сравнить их перед публикацией.</span><span class="sxs-lookup"><span data-stu-id="51901-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], combine data from two worksheets when you want to compare data before publishing.</span></span> <span data-ttu-id="51901-104">В этой процедуре данные из двух таблиц объединяются в одну.</span><span class="sxs-lookup"><span data-stu-id="51901-104">In this procedure, you combine data from a two worksheets into one.</span></span> <span data-ttu-id="51901-105">Затем можно выполнить сравнения и определить, какие данные (если имеются) следует опубликовать в репозитории MDS.</span><span class="sxs-lookup"><span data-stu-id="51901-105">Then you can perform further comparisons and determine which data, if any, to publish to the MDS repository.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="51901-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="51901-106">Prerequisites</span></span>  
  
-   <span data-ttu-id="51901-107">Необходимо иметь лист, содержащий данные, управляемые MDS.</span><span class="sxs-lookup"><span data-stu-id="51901-107">You must have a worksheet that contains MDS-managed data.</span></span> <span data-ttu-id="51901-108">Дополнительные сведения см. [в статье Загрузка данных из MDS в Excel](export-data-to-excel-from-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="51901-108">For more information, see [Load Data from MDS into Excel](export-data-to-excel-from-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="51901-109">Необходимо иметь лист, содержащий данные, которые нужно объединить с данными, управляемыми MDS.</span><span class="sxs-lookup"><span data-stu-id="51901-109">You must have a worksheet that contains data you want to combine with MDS-managed data.</span></span> <span data-ttu-id="51901-110">Этот лист должен иметь строку заголовка.</span><span class="sxs-lookup"><span data-stu-id="51901-110">This sheet must have a header row.</span></span>  
  
### <a name="to-combine-non-managed-data-into-an-mds-managed-sheet"></a><span data-ttu-id="51901-111">Объединение неуправляемых данных на листе, управляемом MDS</span><span class="sxs-lookup"><span data-stu-id="51901-111">To combine non-managed data into an MDS-managed sheet</span></span>  
  
1.  <span data-ttu-id="51901-112">На листе, содержащем данные, управляемые MDS, в группе **Публикация и проверка** нажмите кнопку **Объединить данные**.</span><span class="sxs-lookup"><span data-stu-id="51901-112">On the sheet that contains MDS-managed data, in the **Publish and Validate** group, click **Combine Data**.</span></span>  
  
2.  <span data-ttu-id="51901-113">В диалоговом окне **Объединение данных** рядом с текстовым полем **Диапазон для объединения с данными MDS** щелкните значок.</span><span class="sxs-lookup"><span data-stu-id="51901-113">In the **Combine Data** dialog box, next to the **Range to combine with MDS data** text box, click the icon.</span></span> <span data-ttu-id="51901-114">Диалоговое окно свернется.</span><span class="sxs-lookup"><span data-stu-id="51901-114">The dialog box contracts.</span></span>  
  
3.  <span data-ttu-id="51901-115">Щелкните лист, содержащий данные, которые нужно объединить.</span><span class="sxs-lookup"><span data-stu-id="51901-115">Click the sheet that contains the data you want to combine.</span></span>  
  
4.  <span data-ttu-id="51901-116">Выделите все ячейки на листе, которые нужно объединить, включая строку заголовка.</span><span class="sxs-lookup"><span data-stu-id="51901-116">Highlight all cells on the sheet that you want to combine, including the header row.</span></span>  
  
5.  <span data-ttu-id="51901-117">В диалоговом окне **Объединение данных** щелкните значок.</span><span class="sxs-lookup"><span data-stu-id="51901-117">In the **Combine Data** dialog box, click the icon.</span></span> <span data-ttu-id="51901-118">Диалоговое окно раскроется.</span><span class="sxs-lookup"><span data-stu-id="51901-118">The dialog box expands.</span></span>  
  
6.  <span data-ttu-id="51901-119">Для столбца, указанного для сущности MDS, выберите столбец в поле **Соответствующий столбец**.</span><span class="sxs-lookup"><span data-stu-id="51901-119">For a column listed for the MDS entity, select a column under **Corresponding Column**.</span></span> <span data-ttu-id="51901-120">Соответствующие столбцы нужны не для всех столбцов MDS.</span><span class="sxs-lookup"><span data-stu-id="51901-120">All MDS columns do not need corresponding columns.</span></span>  
  
7.  <span data-ttu-id="51901-121">Нажмите кнопку **Объединить**.</span><span class="sxs-lookup"><span data-stu-id="51901-121">Click **Combine**.</span></span> <span data-ttu-id="51901-122">Появится столбец **SOURCE** , указывающий, берутся ли данные из MDS или внешнего источника.</span><span class="sxs-lookup"><span data-stu-id="51901-122">A **SOURCE** column is displayed, indicating whether the data is from MDS or an external source.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="51901-123">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="51901-123">Next Steps</span></span>  
  
-   <span data-ttu-id="51901-124">Сведения об определении подобия между данными, управляемыми MDS, и внешними данными см. в разделе [Сопоставление схожих данных (надстройка MDS для Excel)](match-similar-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="51901-124">To find similarities between the MDS-managed and external data, see [Match Similar Data &#40;MDS Add-in for Excel&#41;](match-similar-data-mds-add-in-for-excel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51901-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="51901-125">See Also</span></span>  
 <span data-ttu-id="51901-126">[Загрузка надстройка MDS для Excel &#40;данных&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="51901-126">[Loading Data &#40;MDS Add-in for Excel&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="51901-127">Сопоставление качества данных в надстройке MDS для Excel</span><span class="sxs-lookup"><span data-stu-id="51901-127">Data Quality Matching in the MDS Add-in for Excel</span></span>](data-quality-matching-in-the-mds-add-in-for-excel.md)  
  
  
