---
title: Сопоставление схожих данных (надстройка MDS для Excel) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: f6fd6fc1-3569-42a5-b6cb-87a921c88f3b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 70dea36de557c6fda909d06ee19ff8fa2ed6908d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731794"
---
# <a name="match-similar-data-mds-add-in-for-excel"></a><span data-ttu-id="69d20-102">Сопоставление схожих данных (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="69d20-102">Match Similar Data (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="69d20-103">В [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]воспользуйтесь возможностями служб Data Quality Services (DQS) для определения схожести данных.</span><span class="sxs-lookup"><span data-stu-id="69d20-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], use Data Quality Services (DQS) functionality to find similarities in your data.</span></span>  
  
 <span data-ttu-id="69d20-104">Для этого можно:</span><span class="sxs-lookup"><span data-stu-id="69d20-104">To perform this procedure, you can:</span></span>  
  
-   <span data-ttu-id="69d20-105">использовать базу знаний служб Data Quality Services по умолчанию или</span><span class="sxs-lookup"><span data-stu-id="69d20-105">Use the default Data Quality Services knowledge base, or</span></span>  
  
-   <span data-ttu-id="69d20-106">создать собственную пользовательскую базу знаний DQS и политику сопоставления.</span><span class="sxs-lookup"><span data-stu-id="69d20-106">Create your own custom DQS knowledge base and matching policy.</span></span> <span data-ttu-id="69d20-107">Дополнительные сведения см. в статье [Create a Matching Policy](../../data-quality-services/create-a-matching-policy.md).</span><span class="sxs-lookup"><span data-stu-id="69d20-107">For more information, see [Create a Matching Policy](../../data-quality-services/create-a-matching-policy.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="69d20-108">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="69d20-108">Prerequisites</span></span>  
  
-   <span data-ttu-id="69d20-109">Необходимо иметь лист, содержащий данные, управляемые MDS.</span><span class="sxs-lookup"><span data-stu-id="69d20-109">You must have a worksheet that contains MDS-managed data.</span></span> <span data-ttu-id="69d20-110">Дополнительные сведения см. [в статье Загрузка данных из MDS в Excel](export-data-to-excel-from-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="69d20-110">For more information, see [Load Data from MDS into Excel](export-data-to-excel-from-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="69d20-111">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="69d20-111">Optional.</span></span> <span data-ttu-id="69d20-112">Перед проверкой схожести можно объединить другие данные с данными, управляемыми MDS.</span><span class="sxs-lookup"><span data-stu-id="69d20-112">You can combine other data with the MDS-managed data before checking for similarities.</span></span> <span data-ttu-id="69d20-113">Дополнительные сведения см. в разделе [Объединение данных (надстройка MDS для Excel)](combine-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="69d20-113">For more information, see [Combine Data &#40;MDS Add-in for Excel&#41;](combine-data-mds-add-in-for-excel.md).</span></span>  
  
### <a name="to-find-similarities-by-using-the-default-knowledge-base"></a><span data-ttu-id="69d20-114">Поиск схожести с помощью базы знаний по умолчанию</span><span class="sxs-lookup"><span data-stu-id="69d20-114">To find similarities by using the default knowledge base</span></span>  
  
1.  <span data-ttu-id="69d20-115">На листе, который содержит данные, управляемые MDS, в группе **Качество данных** нажмите кнопку **Сопоставить данные**.</span><span class="sxs-lookup"><span data-stu-id="69d20-115">From the worksheet that contains MDS-managed data, in the **Data Quality** group, click **Match Data**.</span></span>  
  
2.  <span data-ttu-id="69d20-116">В диалоговом окне **Сопоставить данные** в списке **База знаний служб DQS** выберите пункт **Данные служб DQS (по умолчанию)**.</span><span class="sxs-lookup"><span data-stu-id="69d20-116">In the **Match Data** dialog box, from the **DQS Knowledge Base** list, select **DQS Data (default)**.</span></span>  
  
3.  <span data-ttu-id="69d20-117">Для каждого столбца, содержащего данные, которые нужно сравнить, добавьте строку в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="69d20-117">For each column that contains data you want to match, add a row in the dialog box.</span></span> <span data-ttu-id="69d20-118">Дополнительные сведения о полях в этом диалоговом окне см. в разделе [How to Set Matching Rule Parameters](../../data-quality-services/create-a-matching-policy.md#MatchingRules).</span><span class="sxs-lookup"><span data-stu-id="69d20-118">For information about the fields in this dialog box, see [How to Set Matching Rule Parameters](../../data-quality-services/create-a-matching-policy.md#MatchingRules).</span></span>  
  
4.  <span data-ttu-id="69d20-119">Когда сумма всех значений веса станет равна 100 %, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="69d20-119">When the total of all weight values equals 100 percent, click **OK**.</span></span>  
  
### <a name="to-find-similarities-by-using-a-custom-knowledge-base"></a><span data-ttu-id="69d20-120">Поиск схожести с помощью пользовательской базы знаний</span><span class="sxs-lookup"><span data-stu-id="69d20-120">To find similarities by using a custom knowledge base</span></span>  
  
1.  <span data-ttu-id="69d20-121">На листе, который содержит данные, управляемые MDS, в группе **Качество данных** нажмите кнопку **Сопоставить данные**.</span><span class="sxs-lookup"><span data-stu-id="69d20-121">From the worksheet that contains MDS-managed data, in the **Data Quality** group, click **Match Data**.</span></span>  
  
2.  <span data-ttu-id="69d20-122">В списке **База знаний служб DQS** выберите имя пользовательской базы знаний.</span><span class="sxs-lookup"><span data-stu-id="69d20-122">From the **DQS Knowledge Base** list, select the name of your custom knowledge base.</span></span>  
  
3.  <span data-ttu-id="69d20-123">Для каждого столбца на листе выберите домен служб DQS.</span><span class="sxs-lookup"><span data-stu-id="69d20-123">For each column in the worksheet, select a DQS domain.</span></span>  
  
4.  <span data-ttu-id="69d20-124">Когда все домены служб DQS будут сопоставлены со столбцами листа, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="69d20-124">When all DQS domains are mapped to columns in the worksheet, click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="69d20-125">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="69d20-125">Next Steps</span></span>  
  
-   <span data-ttu-id="69d20-126">Просмотрите дополнительные сведения для определения схожих данных.</span><span class="sxs-lookup"><span data-stu-id="69d20-126">View additional information to determine which data is similar.</span></span> <span data-ttu-id="69d20-127">Дополнительные сведения см. в разделе [Столбцы сопоставления качества данных (службы DQS)](data-quality-matching-columns-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="69d20-127">For more information, see [Data Quality Matching Columns &#40;MDS Add-in for Excel&#41;](data-quality-matching-columns-mds-add-in-for-excel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69d20-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="69d20-128">See Also</span></span>  
 <span data-ttu-id="69d20-129">[Сопоставление качества данных в надстройка MDS для Excel](data-quality-matching-in-the-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="69d20-129">[Data Quality Matching in the MDS Add-in for Excel](data-quality-matching-in-the-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="69d20-130">Сопоставление данных</span><span class="sxs-lookup"><span data-stu-id="69d20-130">Data Matching</span></span>](../../data-quality-services/data-matching.md)  
  
  
