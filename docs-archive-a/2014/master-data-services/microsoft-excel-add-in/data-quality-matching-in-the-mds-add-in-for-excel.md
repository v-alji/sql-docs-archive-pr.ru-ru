---
title: Сопоставление качества данных в надстройке MDS для Excel | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: be78d051-0d56-46d3-bb89-327e218dadd6
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 037e535452e7f19644837e0cbcfd02efec5422b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667255"
---
# <a name="data-quality-matching-in-the-mds-add-in-for-excel"></a><span data-ttu-id="8d905-102">Сопоставление качества данных в надстройке MDS для Excel</span><span class="sxs-lookup"><span data-stu-id="8d905-102">Data Quality Matching in the MDS Add-in for Excel</span></span>
  <span data-ttu-id="8d905-103">Со временем в репозиторий MDS потребуется добавить дополнительные данные.</span><span class="sxs-lookup"><span data-stu-id="8d905-103">Over time, you will want to add more data to the MDS repository.</span></span> <span data-ttu-id="8d905-104">Перед добавлением может быть полезно сравнить новые данные с данными, которые уже управляются в MDS, чтобы избежать дублирования или добавления неточных данных.</span><span class="sxs-lookup"><span data-stu-id="8d905-104">Before adding data, it can be useful to compare the new data to the data that's already managed in MDS, to ensure you are not adding duplicate or inaccurate data.</span></span>  
  
 <span data-ttu-id="8d905-105">Для сопоставления данных MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] использует службы Data Quality Services (DQS) из [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d905-105">The MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] uses the Data Quality Services (DQS) feature of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to match data that's similar.</span></span> <span data-ttu-id="8d905-106">При использовании функции сопоставления в надстройке одинаковые записи группируются вместе и выводится показатель, отражающий точность результата.</span><span class="sxs-lookup"><span data-stu-id="8d905-106">When you use the matching functionality in the Add-in, similar records are grouped together and a score that represents the accuracy of the result is displayed.</span></span> <span data-ttu-id="8d905-107">Дополнительные сведения о возможностях сопоставления в службах DQS см. в разделе [Data Matching](../../data-quality-services/data-matching.md).</span><span class="sxs-lookup"><span data-stu-id="8d905-107">For more information about the matching functionality provided by DQS, see [Data Matching](../../data-quality-services/data-matching.md).</span></span>  
  
## <a name="workflow-for-data-quality-matching"></a><span data-ttu-id="8d905-108">Рабочий процесс для сопоставления качества данных</span><span class="sxs-lookup"><span data-stu-id="8d905-108">Workflow for Data Quality Matching</span></span>  
 <span data-ttu-id="8d905-109">При использовании служб DQS с MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]используйте следующий рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="8d905-109">When using DQS with the MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], use the following workflow:</span></span>  
  
1.  <span data-ttu-id="8d905-110">Получите список данных, управляемых MDS, и объедините его со списком данных, которые не управляются в MDS.</span><span class="sxs-lookup"><span data-stu-id="8d905-110">Retrieve a list of MDS-managed data and combine it with a list that is not managed in MDS.</span></span> <span data-ttu-id="8d905-111">Дополнительные сведения см. в разделе [Объединение данных (надстройка MDS для Excel)](combine-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="8d905-111">For more information, see [Combine Data &#40;MDS Add-in for Excel&#41;](combine-data-mds-add-in-for-excel.md).</span></span>  
  
2.  <span data-ttu-id="8d905-112">Используйте базу набора знаний служб DQS для сравнения данных в объединенном списке.</span><span class="sxs-lookup"><span data-stu-id="8d905-112">Use DQS knowledge to compare the data in the combined list.</span></span> <span data-ttu-id="8d905-113">Дополнительные сведения см. в разделе [Сопоставление схожих данных (надстройка MDS для Excel)](match-similar-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="8d905-113">For more information, see [Match Similar Data &#40;MDS Add-in for Excel&#41;](match-similar-data-mds-add-in-for-excel.md).</span></span>  
  
3.  <span data-ttu-id="8d905-114">Чтобы просмотреть дополнительные сведения о схожести, обнаруженной службами DQS, отобразите столбцы со сведениями.</span><span class="sxs-lookup"><span data-stu-id="8d905-114">To view more details about the similarities found by DQS, show the detail columns.</span></span>  
  
4.  <span data-ttu-id="8d905-115">Просмотрите результаты и определите, какие данные следует добавить в репозиторий MDS и какие данные дублируются.</span><span class="sxs-lookup"><span data-stu-id="8d905-115">Go through the results and determine which data should be added to the MDS repository and which data is duplicated.</span></span>  
  
5.  <span data-ttu-id="8d905-116">Опубликуйте новые и/или обновленные данных в репозитории MDS.</span><span class="sxs-lookup"><span data-stu-id="8d905-116">Publish the new and/or updated data to the MDS repository.</span></span>  
  
## <a name="knowledge-bases"></a><span data-ttu-id="8d905-117">Базы знаний</span><span class="sxs-lookup"><span data-stu-id="8d905-117">Knowledge Bases</span></span>  
 <span data-ttu-id="8d905-118">Результаты сопоставления, предлагаемые в надстройке, основаны на базе знаний служб DQS.</span><span class="sxs-lookup"><span data-stu-id="8d905-118">The matching results provided in the Add-in are based on a DQS knowledge base.</span></span>  
  
-   <span data-ttu-id="8d905-119">База знаний по умолчанию (DQS Data) создается при установке служб DQS.</span><span class="sxs-lookup"><span data-stu-id="8d905-119">The default knowledge base (DQS Data) is created when DQS is installed.</span></span> <span data-ttu-id="8d905-120">Если выбрать для использования базу знаний по умолчанию (без добавления политики сопоставления по умолчанию в базу знаний клиента DQS Data Quality), необходимо сопоставить столбцы в листе с доменами в базе знаний, затем присвоить значение веса с выбранными доменами.</span><span class="sxs-lookup"><span data-stu-id="8d905-120">If you choose to use the default knowledge base (without adding a matching policy to the default knowledge base in the Data Quality Client), you must map columns in the worksheet to domains in the knowledge base, and then assign a weight value to the domains you choose.</span></span>  
  
-   <span data-ttu-id="8d905-121">Для создания новой базы знаний с политикой маршрутов можно использовать клиент DQS, а можно добавить политику сопоставления в базе знаний по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8d905-121">You can use the Data Quality Client to create a new knowledge base with a matching policy, or to add a matching policy to the default knowledge base.</span></span> <span data-ttu-id="8d905-122">В этом случае значения веса определяются уже созданной политикой сопоставления и потребуется только сопоставить столбцы и домены.</span><span class="sxs-lookup"><span data-stu-id="8d905-122">In this case, the weight values are determined by the matching policy you already created and you need only to map the columns to the domains.</span></span> <span data-ttu-id="8d905-123">Дополнительные сведения см. в статье [Create a Matching Policy](../../data-quality-services/create-a-matching-policy.md).</span><span class="sxs-lookup"><span data-stu-id="8d905-123">For more information, see [Create a Matching Policy](../../data-quality-services/create-a-matching-policy.md).</span></span>  
  
 <span data-ttu-id="8d905-124">Дополнительные сведения о базах знаний см. в разделе [DQS Knowledge Bases and Domains](../../data-quality-services/dqs-knowledge-bases-and-domains.md).</span><span class="sxs-lookup"><span data-stu-id="8d905-124">For more information about knowledge bases, see [DQS Knowledge Bases and Domains](../../data-quality-services/dqs-knowledge-bases-and-domains.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="8d905-125">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="8d905-125">Related Tasks</span></span>  
  
|<span data-ttu-id="8d905-126">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="8d905-126">Task Description</span></span>|<span data-ttu-id="8d905-127">Раздел</span><span class="sxs-lookup"><span data-stu-id="8d905-127">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="8d905-128">Объедините внешние данные с данными, управляемыми MDS, и подготовьтесь к их сравнению.</span><span class="sxs-lookup"><span data-stu-id="8d905-128">Combine external data with MDS-managed data in preparation to compare it.</span></span>|[<span data-ttu-id="8d905-129">Объединение данных (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="8d905-129">Combine Data &#40;MDS Add-in for Excel&#41;</span></span>](combine-data-mds-add-in-for-excel.md)|  
|<span data-ttu-id="8d905-130">Воспользуйтесь базой набора знаний служб DQS для определения схожести данных.</span><span class="sxs-lookup"><span data-stu-id="8d905-130">Use DQS knowledge to find similarities in your data.</span></span>|[<span data-ttu-id="8d905-131">Сопоставление схожих данных (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="8d905-131">Match Similar Data &#40;MDS Add-in for Excel&#41;</span></span>](match-similar-data-mds-add-in-for-excel.md)|  
  
## <a name="related-content"></a><span data-ttu-id="8d905-132">См. также</span><span class="sxs-lookup"><span data-stu-id="8d905-132">Related Content</span></span>  
  
-   [<span data-ttu-id="8d905-133">Публикация &#40;данных надстройка MDS для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="8d905-133">Publishing Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-importing-data-from-excel-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="8d905-134">Сопоставление данных</span><span class="sxs-lookup"><span data-stu-id="8d905-134">Data Matching</span></span>](../../data-quality-services/data-matching.md)  
  
  
