---
title: Столбцы сопоставления качества данных (службы DQS), надстройка MDS для Excel | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: f683fdc6-0d4c-4793-8143-567616cb2094
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 939ec9727cc81ce3b206b8bc7ca3ed8dd62c3877
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654376"
---
# <a name="data-quality-matching-columns-mds-add-in-for-excel"></a><span data-ttu-id="8364e-102">Столбцы сопоставления качества данных (службы DQS), надстройка MDS для Excel</span><span class="sxs-lookup"><span data-stu-id="8364e-102">Data Quality Matching Columns (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="8364e-103">В [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]после сопоставления данных в группе **Качество данных** на ленте можно нажать кнопку **Показать подробности** , чтобы вывести столбцы с дополнительными сведениями.</span><span class="sxs-lookup"><span data-stu-id="8364e-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], after you match data, in the **Data Quality** group on the ribbon, you can click **Show Details** to display columns that provide matching details.</span></span>  
  
 <span data-ttu-id="8364e-104">В следующей таблице показаны столбцы, которые отображаются при сопоставлении данных.</span><span class="sxs-lookup"><span data-stu-id="8364e-104">The following table shows the columns that are displayed when matching data.</span></span>  
  
|<span data-ttu-id="8364e-105">Имя</span><span class="sxs-lookup"><span data-stu-id="8364e-105">Name</span></span>|<span data-ttu-id="8364e-106">Описание</span><span class="sxs-lookup"><span data-stu-id="8364e-106">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="8364e-107">**CLUSTER_ID**</span><span class="sxs-lookup"><span data-stu-id="8364e-107">**CLUSTER_ID**</span></span>|<span data-ttu-id="8364e-108">Уникальный идентификатор, используемый для группировки схожих записей.</span><span class="sxs-lookup"><span data-stu-id="8364e-108">A unique identifier used to group similar records.</span></span> <span data-ttu-id="8364e-109">Все схожие строки имеют одинаковый **CLUSTER_ID**.</span><span class="sxs-lookup"><span data-stu-id="8364e-109">All rows that are similar have the same **CLUSTER_ID**.</span></span> <span data-ttu-id="8364e-110">Если значение **CLUSTER_ID** для строки не отображается, значит схожие записи не были найдены.</span><span class="sxs-lookup"><span data-stu-id="8364e-110">If no **CLUSTER_ID** is displayed for a row, then no similar records were found.</span></span>|  
|<span data-ttu-id="8364e-111">**RECORD_ID**</span><span class="sxs-lookup"><span data-stu-id="8364e-111">**RECORD_ID**</span></span>|<span data-ttu-id="8364e-112">Уникальный идентификатор, используемый для идентификации записей.</span><span class="sxs-lookup"><span data-stu-id="8364e-112">A unique identifier used to identify records.</span></span> <span data-ttu-id="8364e-113">Аналогичен значению «Код», которое хранится в репозитории MDS. Используется для идентификации записи.</span><span class="sxs-lookup"><span data-stu-id="8364e-113">Similar to the Code value stored in the MDS repository, it is a value used to identify a record.</span></span> <span data-ttu-id="8364e-114">Создается автоматически при каждом сопоставлении.</span><span class="sxs-lookup"><span data-stu-id="8364e-114">It is generated automatically each time matching takes place.</span></span>|  
|<span data-ttu-id="8364e-115">**PIVOT_MARK**</span><span class="sxs-lookup"><span data-stu-id="8364e-115">**PIVOT_MARK**</span></span>|<span data-ttu-id="8364e-116">Произвольная запись, с которой сравниваются другие записи. У нее нет значения оценки.</span><span class="sxs-lookup"><span data-stu-id="8364e-116">An arbitrary record that other records are compared to; it does not have a score value.</span></span>|  
|<span data-ttu-id="8364e-117">**ПОНЯТЬ**</span><span class="sxs-lookup"><span data-stu-id="8364e-117">**SCORE**</span></span>|<span data-ttu-id="8364e-118">Отражает, насколько схожи записи в группе с эталонной записью.</span><span class="sxs-lookup"><span data-stu-id="8364e-118">Represents how similar the records in the group are to the pivot record.</span></span> <span data-ttu-id="8364e-119">Эта оценка определяется службами DQS.</span><span class="sxs-lookup"><span data-stu-id="8364e-119">This score is determined by DQS.</span></span> <span data-ttu-id="8364e-120">Если оценка не отображается, это означает либо то, что запись является сводной, либо что совпадения не найдены.</span><span class="sxs-lookup"><span data-stu-id="8364e-120">If no score is displayed, either the record is the pivot for other records, or no matches were found.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8364e-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="8364e-121">See Also</span></span>  
 <span data-ttu-id="8364e-122">[Сопоставление качества данных в надстройка MDS для Excel](data-quality-matching-in-the-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="8364e-122">[Data Quality Matching in the MDS Add-in for Excel](data-quality-matching-in-the-mds-add-in-for-excel.md) </span></span>  
 <span data-ttu-id="8364e-123">[Сопоставление схожих &#40;данных надстройка MDS для Excel&#41;](match-similar-data-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="8364e-123">[Match Similar Data &#40;MDS Add-in for Excel&#41;](match-similar-data-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="8364e-124">Сопоставление данных</span><span class="sxs-lookup"><span data-stu-id="8364e-124">Data Matching</span></span>](../../data-quality-services/data-matching.md)  
  
  
