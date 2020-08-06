---
title: Просмотр конфликтов данных для публикаций транзакций (SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- conflict resolution [SQL Server replication], queued updating subscriptions
- queued updating subscriptions [SQL Server replication]
- viewing conflict information
ms.assetid: 9977dd75-b0de-4376-9c13-86d80567d8aa
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 228753c113bcf43ed276d989a3996e9bf23bfc16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667029"
---
# <a name="view-data-conflicts-for-transactional-publications-sql-server-management-studio"></a><span data-ttu-id="cd760-102">просмотреть конфликты данных для публикаций транзакций (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="cd760-102">View Data Conflicts for Transactional Publications (SQL Server Management Studio)</span></span>
  <span data-ttu-id="cd760-103">В средстве просмотра конфликтов репликации [!INCLUDE[msCoName](../../includes/msconame-md.md)] можно просматривать конфликты одноранговой репликации транзакций и репликации транзакций с подписками, обновляемыми посредством очередей.</span><span class="sxs-lookup"><span data-stu-id="cd760-103">You can view conflicts for peer-to-peer transactional replication and transactional replication with queued updating subscriptions in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Replication Conflict Viewer.</span></span> <span data-ttu-id="cd760-104">Сведения о том, как обнаруживать и разрешать конфликты, см. в статьях [Обнаружение конфликтов в одноранговой репликации](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md) и [Настройка параметров разрешения конфликтов для обновления посредством очередей (среда SQL Server Management Studio)](publish/create-an-updatable-subscription-to-a-transactional-publication.md).</span><span class="sxs-lookup"><span data-stu-id="cd760-104">For information about how conflicts are detected and resolved, see [Conflict Detection in Peer-to-Peer Replication](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md) and [Set Queued Updating Conflict Resolution Options &#40;SQL Server Management Studio&#41;](publish/create-an-updatable-subscription-to-a-transactional-publication.md).</span></span>  
  
 <span data-ttu-id="cd760-105">Доступность данных конфликта зависит от типа репликации и срока хранения конфликта.</span><span class="sxs-lookup"><span data-stu-id="cd760-105">The availability of conflict data depends on the type of replication and the conflict retention period:</span></span>  
  
-   <span data-ttu-id="cd760-106">При одноранговой репликации агент распространителя при обнаружении конфликта завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="cd760-106">For peer-to-peer replication, by default, the Distribution Agent fails when it detects a conflict.</span></span> <span data-ttu-id="cd760-107">Эта ошибка заносится в журнал, но данные конфликта не записываются в таблицу конфликтов и поэтому недоступны для просмотра.</span><span class="sxs-lookup"><span data-stu-id="cd760-107">A conflict error is logged into the error log, but no conflict data is logged into the conflict table; therefore it is not available for viewing.</span></span> <span data-ttu-id="cd760-108">Если агенту распространителя разрешено продолжение работы, то конфликт заносится в локальный журнал на каждом из узлов, где он обнаружен.</span><span class="sxs-lookup"><span data-stu-id="cd760-108">If the Distribution Agent is allowed to continue, a conflict is logged locally on each node where it was detected.</span></span> <span data-ttu-id="cd760-109">Дополнительные сведения см. в подразделе «Обработка конфликтов» раздела [Conflict Detection in Peer-to-Peer Replication](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md).</span><span class="sxs-lookup"><span data-stu-id="cd760-109">For more information, see "Handling Conflicts" in [Conflict Detection in Peer-to-Peer Replication](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md).</span></span>  
  
-   <span data-ttu-id="cd760-110">В подписках, обновляемых посредством очередей, доступны данные любого конфликта.</span><span class="sxs-lookup"><span data-stu-id="cd760-110">For queued updating subscriptions, data is available for every conflict.</span></span> <span data-ttu-id="cd760-111">Данные конфликтов доступны в средстве просмотра конфликтов репликации в течение времени, указанного для срока хранения конфликтов (по умолчанию это время равно 14 дням).</span><span class="sxs-lookup"><span data-stu-id="cd760-111">Conflict data is available in the Replication Conflict Viewer for the amount of time specified for the conflict retention period, with a default of 14 days.</span></span> <span data-ttu-id="cd760-112">Чтобы настроить срок хранения конфликтов, выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="cd760-112">To set the conflict retention period, perform either of the following:</span></span>  
  
    -   <span data-ttu-id="cd760-113">Укажите значение срока хранения для параметра @conflict_retention хранимой процедуры [sp_addpublication](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cd760-113">Specify a retention value for the @conflict_retention parameter of [sp_addpublication](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql).</span></span>  
  
    -   <span data-ttu-id="cd760-114">Укажите значение `'conflict_retention'` для @property параметра и значение срока хранения для @value параметра [sp_changepublication](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cd760-114">Specify a value of `'conflict_retention'` for the @property parameter and a retention value for the @value parameter of [sp_changepublication](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql).</span></span>  
  
### <a name="to-view-conflicts"></a><span data-ttu-id="cd760-115">Просмотр конфликтов</span><span class="sxs-lookup"><span data-stu-id="cd760-115">To view conflicts</span></span>  
  
1.  <span data-ttu-id="cd760-116">Подключитесь к соответствующему серверу в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], затем раскройте узел сервера.</span><span class="sxs-lookup"><span data-stu-id="cd760-116">Connect to the appropriate server in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node:</span></span>  
  
    -   <span data-ttu-id="cd760-117">Для одноранговой репликации это узел, на котором произошел конфликт.</span><span class="sxs-lookup"><span data-stu-id="cd760-117">For peer-to-peer replication, this is the node at which the conflict occurred.</span></span>  
  
    -   <span data-ttu-id="cd760-118">Для подписок, обновляемых посредством очередей, это издатель.</span><span class="sxs-lookup"><span data-stu-id="cd760-118">For queued updating subscriptions, this is the Publisher.</span></span>  
  
2.  <span data-ttu-id="cd760-119">Раскройте папку **Репликация** , а затем папку **Локальные публикации** .</span><span class="sxs-lookup"><span data-stu-id="cd760-119">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="cd760-120">Щелкните правой кнопкой мыши публикацию, для которой требуется просмотреть конфликты, а затем щелкните **Просмотреть конфликты**.</span><span class="sxs-lookup"><span data-stu-id="cd760-120">Right-click the publication for which you want to view conflicts, and then click **View Conflicts**.</span></span>  
  
4.  <span data-ttu-id="cd760-121">В диалоговом окне **Выбор таблицы с конфликтами** выберите базу данных, публикацию и таблицу, для которой необходимо просмотреть конфликты.</span><span class="sxs-lookup"><span data-stu-id="cd760-121">In the **Select Conflict Table** dialog box, select a database, publication, and table for which to view conflicts.</span></span>  
  
5.  <span data-ttu-id="cd760-122">В средстве просмотра конфликтов репликации можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="cd760-122">In the Replication Conflict Viewer, you can:</span></span>  
  
    -   <span data-ttu-id="cd760-123">Отфильтровать строки с помощью кнопок, расположенных справа от верхней сетки.</span><span class="sxs-lookup"><span data-stu-id="cd760-123">Filter rows with the buttons to the right of the upper grid.</span></span>  
  
    -   <span data-ttu-id="cd760-124">Выбрать строку в верхней сетке для отображения информации об этой строке в нижней сетке.</span><span class="sxs-lookup"><span data-stu-id="cd760-124">Select a row in the upper grid to display information on that row in the lower grid.</span></span>  
  
    -   <span data-ttu-id="cd760-125">Выбрать одну или несколько строк в верхней сетке, а затем щелкнуть **Удалить**, чтобы удалить строку из таблицы метаданных конфликтов.</span><span class="sxs-lookup"><span data-stu-id="cd760-125">Select one or more rows in the upper grid, and then click **Remove**, which removes the row from the conflicts metadata table.</span></span>  
  
    -   <span data-ttu-id="cd760-126">Нажмите кнопку свойств (**...**), чтобы просмотреть дополнительные сведения о столбце, участвующем в конфликте.</span><span class="sxs-lookup"><span data-stu-id="cd760-126">Click the properties button (**...**) to view more information on a column involved in a conflict.</span></span>  
  
    -   <span data-ttu-id="cd760-127">Выбрать **Записать подробности этого конфликта** , чтобы записать данные конфликта в файл.</span><span class="sxs-lookup"><span data-stu-id="cd760-127">Select **Log the details of this conflict** to log conflict data to a file.</span></span> <span data-ttu-id="cd760-128">Для указания размещения файла наведите указатель на меню **Просмотр** и щелкните **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="cd760-128">To specify a location for the file, point to the **View** menu, and then click **Options**.</span></span> <span data-ttu-id="cd760-129">Введите значение или нажмите кнопку обзора (**...**), а затем перейдите к необходимому файлу.</span><span class="sxs-lookup"><span data-stu-id="cd760-129">Enter a value, or click the browse button (**...**), and then navigate to the appropriate file.</span></span> <span data-ttu-id="cd760-130">Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="cd760-130">Click **OK** to close the **Options** dialog box.</span></span>  
  
6.  <span data-ttu-id="cd760-131">Закройте средство просмотра конфликтов репликации.</span><span class="sxs-lookup"><span data-stu-id="cd760-131">Close the Replication Conflict Viewer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd760-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="cd760-132">See Also</span></span>  
 <span data-ttu-id="cd760-133">[Одноранговая репликация транзакций](transactional/peer-to-peer-transactional-replication.md) </span><span class="sxs-lookup"><span data-stu-id="cd760-133">[Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md) </span></span>  
 [<span data-ttu-id="cd760-134">Queued Updating Conflict Detection and Resolution</span><span class="sxs-lookup"><span data-stu-id="cd760-134">Queued Updating Conflict Detection and Resolution</span></span>](transactional/updatable-subscriptions-queued-updating-conflict-resolution.md)  
  
  
