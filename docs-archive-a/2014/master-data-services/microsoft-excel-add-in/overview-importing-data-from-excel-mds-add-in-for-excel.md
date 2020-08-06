---
title: Публикация данных (надстройка MDS для Excel) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: ea84a9aa-aeec-411b-ab8d-bc1b14f864a3
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ab37a353469d1902394a3e2cd8060d9be82abb40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735453"
---
# <a name="publishing-data-mds-add-in-for-excel"></a><span data-ttu-id="89865-102">Публикация данных (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="89865-102">Publishing Data (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="89865-103">В [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]можно опубликовать данные в репозитории MDS, если их необходимо передать другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="89865-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], publish data to the MDS repository when you want to share it with other users.</span></span> <span data-ttu-id="89865-104">После публикации они станут доступными для загрузки другим пользователям надстройки.</span><span class="sxs-lookup"><span data-stu-id="89865-104">As soon as data is published, it is available for other users of the Add-in to download.</span></span>  
  
 <span data-ttu-id="89865-105">Все добавленные и обновившиеся при публикации данные публикуются в репозитории MDS.</span><span class="sxs-lookup"><span data-stu-id="89865-105">When you publish data, any data you've added or updated is published to the MDS repository.</span></span> <span data-ttu-id="89865-106">Удаленные данные не публикуются, их необходимо удалить отдельно.</span><span class="sxs-lookup"><span data-stu-id="89865-106">Data you've deleted is not published-you must delete data separately.</span></span> <span data-ttu-id="89865-107">Дополнительные сведения см. в разделе [Удаление строки (надстройка MDS для Excel)](delete-a-row-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="89865-107">For more information, see [Delete a Row &#40;MDS Add-in for Excel&#41;](delete-a-row-mds-add-in-for-excel.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="89865-108">Публикация не может быть использована для создания новой сущности.</span><span class="sxs-lookup"><span data-stu-id="89865-108">Publishing cannot be used to create a new entity.</span></span> <span data-ttu-id="89865-109">Дополнительные сведения о создании сущностей см. в разделе [Создание сущности (надстройка MDS для Excel)](create-an-entity-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="89865-109">For more information about creating entities, see [Create an Entity &#40;MDS Add-in for Excel&#41;](create-an-entity-mds-add-in-for-excel.md).</span></span>  
  
## <a name="when-multiple-users-publish-at-the-same-time"></a><span data-ttu-id="89865-110">Одновременная публикация несколькими пользователями</span><span class="sxs-lookup"><span data-stu-id="89865-110">When Multiple Users Publish at the Same Time</span></span>  
 <span data-ttu-id="89865-111">Несколько пользователей могут публиковать обновления одних и тех же данных одновременно.</span><span class="sxs-lookup"><span data-stu-id="89865-111">Multiple users can publish updates to the same data.</span></span> <span data-ttu-id="89865-112">В результате каждой публикации в базу данных записывается обновление.</span><span class="sxs-lookup"><span data-stu-id="89865-112">As each user publishes, the update is saved to the database.</span></span> <span data-ttu-id="89865-113">Это означает, что пользователь, не имеющий самых последних обновленных данных, может изменять значения во время публикации.</span><span class="sxs-lookup"><span data-stu-id="89865-113">This means that a user who was not working with the most recently-updated data can still change the value when he or she publishes.</span></span>  
  
 <span data-ttu-id="89865-114">В базе данных публикуются только внесенные вами изменения.</span><span class="sxs-lookup"><span data-stu-id="89865-114">Only the updates you make are published to the database.</span></span> <span data-ttu-id="89865-115">Устаревшие данные на листе не публикуются.</span><span class="sxs-lookup"><span data-stu-id="89865-115">Any out-of-date data in the worksheet is not published.</span></span>  
  
## <a name="transactions-and-annotations"></a><span data-ttu-id="89865-116">Транзакции и заметки</span><span class="sxs-lookup"><span data-stu-id="89865-116">Transactions and Annotations</span></span>  
 <span data-ttu-id="89865-117">Каждое опубликованное изменение сохраняется в виде транзакции.</span><span class="sxs-lookup"><span data-stu-id="89865-117">Each published change is saved as a transaction.</span></span> <span data-ttu-id="89865-118">По вашему выбору в транзакцию можно добавить заметки (комментарии), объясняющие причины внесения изменений.</span><span class="sxs-lookup"><span data-stu-id="89865-118">If you choose, you can add annotations (comments) to a transaction, to explain why you made the change.</span></span>  
  
-   <span data-ttu-id="89865-119">Заметки к операциям удаления не добавляются, хотя они сохраняются в виде транзакций, которые могут использоваться для выполнения обратной операции администратором.</span><span class="sxs-lookup"><span data-stu-id="89865-119">You cannot annotate deletions, although deletions are saved as transactions that can be reversed by an administrator.</span></span>  
  
-   <span data-ttu-id="89865-120">Если изменить значение **кода** для элемента, оно не будет записано как транзакция, а все предыдущие транзакции для этого элемента будут недоступны.</span><span class="sxs-lookup"><span data-stu-id="89865-120">If you change the **Code** value for a member, it is not recorded as a transaction, and all previous transactions for the member are unavailable.</span></span>  
  
-   <span data-ttu-id="89865-121">Можно просмотреть транзакции для элемента, сделанные другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="89865-121">You can view transactions made to a member by other users.</span></span> <span data-ttu-id="89865-122">Можно также просмотреть все свои транзакции для элемента, даже если вы больше не имеете разрешений на определенные атрибуты.</span><span class="sxs-lookup"><span data-stu-id="89865-122">You can also view all transactions you've made to a member, even if you no longer have permission to specific attributes.</span></span>  
  
 <span data-ttu-id="89865-123">Можно просмотреть все транзакции, выполненные для элемента.</span><span class="sxs-lookup"><span data-stu-id="89865-123">You can view all transactions made to a member.</span></span> <span data-ttu-id="89865-124">Дополнительные сведения см. в разделе [Просмотр всех заметок или транзакций для элемента (надстройка MDS для Excel)](view-all-annotations-or-transactions-for-a-member-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="89865-124">For more information, see [View All Annotations or Transactions for a Member &#40;MDS Add-in for Excel&#41;](view-all-annotations-or-transactions-for-a-member-mds-add-in-for-excel.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="89865-125">Если введена заметка длиной более 500 символов, то она автоматически усекается.</span><span class="sxs-lookup"><span data-stu-id="89865-125">If you enter an annotation of more than 500 characters, the annotation is automatically truncated.</span></span>  
  
## <a name="business-rule-and-other-validation"></a><span data-ttu-id="89865-126">Проверка бизнес-правил и другие проверки</span><span class="sxs-lookup"><span data-stu-id="89865-126">Business Rule and Other Validation</span></span>  
 <span data-ttu-id="89865-127">При публикации данных выполняется проверка, чтобы обеспечить точность данных перед их добавлением в репозиторий MDS.</span><span class="sxs-lookup"><span data-stu-id="89865-127">When you publish data, validation is performed to ensure data is accurate before it's added to the MDS repository.</span></span> <span data-ttu-id="89865-128">Если данные не соответствуют заданным условиям, то они не будут опубликованы.</span><span class="sxs-lookup"><span data-stu-id="89865-128">If the data does not meet specified criteria, it will not be published to the repository.</span></span> <span data-ttu-id="89865-129">Дополнительные сведения см. в разделе [Проверка данных (надстройка MDS для Excel)](validating-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="89865-129">For more information, see [Validating Data &#40;MDS Add-in for Excel&#41;](validating-data-mds-add-in-for-excel.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="89865-130">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="89865-130">Related Tasks</span></span>  
  
|<span data-ttu-id="89865-131">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="89865-131">Task Description</span></span>|<span data-ttu-id="89865-132">Раздел</span><span class="sxs-lookup"><span data-stu-id="89865-132">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="89865-133">Публикация данных из активного листа в репозитории MDS.</span><span class="sxs-lookup"><span data-stu-id="89865-133">Publish data from the active worksheet back to the MDS repository.</span></span>|[<span data-ttu-id="89865-134">Публикация данных из Excel в службах MDS &#40;надстройка MDS для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="89865-134">Publish Data from Excel to MDS &#40;MDS Add-in for Excel&#41;</span></span>](import-data-from-excel-to-master-data-services-mds-add-in-for-excel.md)|  
|<span data-ttu-id="89865-135">Одновременное удаление строки из репозитория MDS и с листа.</span><span class="sxs-lookup"><span data-stu-id="89865-135">Delete a row from the MDS repository and from the worksheet at the same time.</span></span>|[<span data-ttu-id="89865-136">Удаление строки (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="89865-136">Delete a Row &#40;MDS Add-in for Excel&#41;</span></span>](delete-a-row-mds-add-in-for-excel.md)|  
  
## <a name="related-content"></a><span data-ttu-id="89865-137">См. также</span><span class="sxs-lookup"><span data-stu-id="89865-137">Related Content</span></span>  
  
-   [<span data-ttu-id="89865-138">Обновление данных (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="89865-138">Refreshing Data &#40;MDS Add-in for Excel&#41;</span></span>](refreshing-data-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="89865-139">Надстройка Master Data Services для Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="89865-139">Master Data Services Add-in for Microsoft Excel</span></span>](master-data-services-add-in-for-microsoft-excel.md)  
  
  
