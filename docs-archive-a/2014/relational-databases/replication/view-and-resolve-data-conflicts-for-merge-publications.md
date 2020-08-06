---
title: Просмотр и разрешение конфликтов данных для публикаций слиянием (SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- merge replication conflict resolution [SQL Server replication], viewing conflicts
- viewing conflict information
- conflict resolution [SQL Server replication], merge replication
ms.assetid: aeee9546-4480-49f9-8b1e-c71da1f056c7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 77aa9ece0073149c017f6eca35a756b22751a74b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658187"
---
# <a name="view-and-resolve-data-conflicts-for-merge-publications-sql-server-management-studio"></a><span data-ttu-id="13447-102">просмотреть и разрешить конфликты данных для публикации слиянием (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="13447-102">View and Resolve Data Conflicts for Merge Publications (SQL Server Management Studio)</span></span>
  <span data-ttu-id="13447-103">В репликации слиянием конфликты разрешаются на основе сопоставителя, указанного для каждой статьи.</span><span class="sxs-lookup"><span data-stu-id="13447-103">Conflicts in merge replication are resolved based on the resolver specified for each article.</span></span> <span data-ttu-id="13447-104">По умолчанию для разрешения конфликтов не требуется вмешательство пользователя.</span><span class="sxs-lookup"><span data-stu-id="13447-104">By default, conflicts are resolved without the need for user intervention.</span></span> <span data-ttu-id="13447-105">Однако просмотреть конфликты и изменить результат разрешения конфликта можно в средстве просмотра конфликтов репликации [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="13447-105">But conflicts can be viewed, and the outcome of the resolution can be changed, in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Replication Conflict Viewer.</span></span>  
  
 <span data-ttu-id="13447-106">Данные конфликтов доступны в средстве просмотра конфликтов репликации в течение времени, указанном для срока хранения конфликтов (по умолчанию это время равно 14 дням).</span><span class="sxs-lookup"><span data-stu-id="13447-106">Conflict data is available in the Replication Conflict Viewer for the amount of time specified for the conflict retention period (with a default of 14 days).</span></span> <span data-ttu-id="13447-107">Чтобы установить срок хранения конфликтов, выполните любое из указанных ниже действий:</span><span class="sxs-lookup"><span data-stu-id="13447-107">To set the conflict retention period, either:</span></span>  
  
-   <span data-ttu-id="13447-108">Укажите значение срока хранения для **@conflict_retention** параметра [Sp_addmergepublication &#40;TRANSACT-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="13447-108">Specify a retention value for the **@conflict_retention** parameter of [sp_addmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql).</span></span>  
  
-   <span data-ttu-id="13447-109">Укажите значение **conflict_retention** для **@property** параметра и значение срока хранения для **@value** параметра [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="13447-109">Specify a value of **conflict_retention** for the **@property** parameter and a retention value for the **@value** parameter of [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span></span>  
  
 <span data-ttu-id="13447-110">По умолчанию сведения о конфликтах сохраняются:</span><span class="sxs-lookup"><span data-stu-id="13447-110">By default, conflict information is stored:</span></span>  
  
-   <span data-ttu-id="13447-111">На издателе и подписчике, если уровень совместимости публикации 90RTM или выше.</span><span class="sxs-lookup"><span data-stu-id="13447-111">At the Publisher and Subscriber if the publication compatibility level is 90RTM or higher.</span></span>  
  
-   <span data-ttu-id="13447-112">На издателе, если уровень совместимости публикации ниже, чем 80RTM.</span><span class="sxs-lookup"><span data-stu-id="13447-112">At the Publisher if the publication compatibility level is lower than 80RTM.</span></span>  
  
-   <span data-ttu-id="13447-113">На издателе, если подписчики используют [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="13447-113">At the Publisher if Subscribers are running [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span> <span data-ttu-id="13447-114">Данные о конфликтах не могут храниться на подписчиках, использующих [!INCLUDE[ssEW](../../includes/ssew-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="13447-114">Conflict data cannot be stored on [!INCLUDE[ssEW](../../includes/ssew-md.md)] Subscribers.</span></span>  
  
 <span data-ttu-id="13447-115">Хранение информации о конфликте управляется с помощью свойства публикации **conflict_logging** .</span><span class="sxs-lookup"><span data-stu-id="13447-115">Storage of conflict information is controlled by the **conflict_logging** publication property.</span></span> <span data-ttu-id="13447-116">Дополнительные сведения см. в статьях [sp_addmergepublication (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql) и [sp_changemergepublication (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="13447-116">For more information, see [sp_addmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql) and [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span></span>  
  
 <span data-ttu-id="13447-117">Возможно также разрешение конфликтов в интерактивном режиме во время синхронизации с помощью интерактивного сопоставителя [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="13447-117">Conflicts can also be resolved interactively during synchronization using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Interactive Resolver.</span></span> <span data-ttu-id="13447-118">Интерактивный сопоставитель доступен через диспетчер синхронизации [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="13447-118">The Interactive Resolver is available through the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Synchronization Manager.</span></span> <span data-ttu-id="13447-119">Дополнительные сведения см. в статье [Синхронизация подписки с помощью диспетчера синхронизации Windows (диспетчер синхронизации Windows)](synchronize-a-subscription-using-windows-synchronization-manager.md).</span><span class="sxs-lookup"><span data-stu-id="13447-119">For more information, see [Synchronize a Subscription Using Windows Synchronization Manager &#40;Windows Synchronization Manager&#41;](synchronize-a-subscription-using-windows-synchronization-manager.md).</span></span>  
  
### <a name="to-view-and-resolve-conflicts-for-merge-publications"></a><span data-ttu-id="13447-120">Просмотр и разрешение конфликтов для публикаций слиянием</span><span class="sxs-lookup"><span data-stu-id="13447-120">To view and resolve conflicts for merge publications</span></span>  
  
1.  <span data-ttu-id="13447-121">Подключитесь к издателю (или подписчику, если это уместно) в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , а затем разверните узел сервера.</span><span class="sxs-lookup"><span data-stu-id="13447-121">Connect to the Publisher (or Subscriber if appropriate) in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="13447-122">Раскройте папку **Репликация** , а затем папку **Локальные публикации** .</span><span class="sxs-lookup"><span data-stu-id="13447-122">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="13447-123">Щелкните правой кнопкой мыши публикацию, для которой требуется просмотреть конфликты, а затем щелкните **Просмотреть конфликты**.</span><span class="sxs-lookup"><span data-stu-id="13447-123">Right-click the publication for which you want to view conflicts, and then click **View Conflicts**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="13447-124">Если для свойства **conflict_logging** задано значение **'subscriber'** , пункт меню **Просмотреть конфликты** будет недоступен.</span><span class="sxs-lookup"><span data-stu-id="13447-124">If you specified a value of **'subscriber'** for the **conflict_logging** property, the **View Conflicts** menu option is not available.</span></span> <span data-ttu-id="13447-125">Чтобы просмотреть конфликты, запустите в командной строке программу ConflictViewer.exe.</span><span class="sxs-lookup"><span data-stu-id="13447-125">To view conflicts, start ConflictViewer.exe from the command prompt.</span></span> <span data-ttu-id="13447-126">По умолчанию программа ConflictViewer.exe находится в следующем каталоге: Microsoft SQL Server\100\Tools\Binn\VSShell\Common7\IDE.</span><span class="sxs-lookup"><span data-stu-id="13447-126">By default, ConflictViewer.exe is located in the following directory: Microsoft SQL Server\100\Tools\Binn\VSShell\Common7\IDE.</span></span> <span data-ttu-id="13447-127">Чтобы вывести список допустимых параметров запуска, выполните команду ConflictViewer.exe -?.</span><span class="sxs-lookup"><span data-stu-id="13447-127">For a list of valid startup parameters, run ConflictViewer.exe -?.</span></span>  
  
4.  <span data-ttu-id="13447-128">В диалоговом окне **Выбор таблицы с конфликтами** выберите базу данных, публикацию и таблицу, для которой необходимо просмотреть конфликты.</span><span class="sxs-lookup"><span data-stu-id="13447-128">In the **Select Conflict Table** dialog box, select a database, publication, and table for which to view conflicts.</span></span>  
  
5.  <span data-ttu-id="13447-129">В средстве просмотра конфликтов репликации можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="13447-129">In the Replication Conflict Viewer, you can:</span></span>  
  
    -   <span data-ttu-id="13447-130">Отфильтровать строки с помощью кнопок, расположенных справа от верхней сетки.</span><span class="sxs-lookup"><span data-stu-id="13447-130">Filter rows with the buttons to the right of the upper grid.</span></span>  
  
    -   <span data-ttu-id="13447-131">Выбрать строку в верхней сетке для отображения информации об этой строке в нижней сетке.</span><span class="sxs-lookup"><span data-stu-id="13447-131">Select a row in the upper grid to display information on that row in the lower grid.</span></span>  
  
    -   <span data-ttu-id="13447-132">Выберите одну или более строк в верхней сетке, щелкните **Удалить**, что эквивалентно нажатию кнопки **Отправить выигравший** (без внесения каких-либо изменений в данные).</span><span class="sxs-lookup"><span data-stu-id="13447-132">Select one or more rows in the upper grid, and then click **Remove**, which is equivalent to clicking the **Submit Winner** button (without making any changes to the data).</span></span>  
  
    -   <span data-ttu-id="13447-133">Нажмите кнопку свойств (**...**), чтобы просмотреть дополнительные сведения о столбце, участвующем в конфликте.</span><span class="sxs-lookup"><span data-stu-id="13447-133">Click the properties button (**...**) to view more information on a column involved in a conflict.</span></span>  
  
    -   <span data-ttu-id="13447-134">Измените данные в столбце **Выигравший вариант** или **Проигравший вариант** до отправки данных (данные доступны только для чтения, если столбец окрашен в серый цвет).</span><span class="sxs-lookup"><span data-stu-id="13447-134">Edit data in the **Conflict winner** or **Conflict loser** column before submitting the data (data is read-only if the column is gray).</span></span>  
  
    -   <span data-ttu-id="13447-135">Щелкните **Отправить выигравший** , чтобы принять строку, определенную как победитель в конфликте.</span><span class="sxs-lookup"><span data-stu-id="13447-135">Click **Submit Winner** to accept the row designated as the winner of the conflict.</span></span>  
  
    -   <span data-ttu-id="13447-136">Щелкните **Отправить проигравший** , чтобы переопределить разрешение конфликта и передать значение, определенное как проигравший в конфликте на все узлы в топологии.</span><span class="sxs-lookup"><span data-stu-id="13447-136">Click **Submit Loser** to override the resolution and to propagate the value designated as the loser of the conflict to all nodes in the topology.</span></span>  
  
    -   <span data-ttu-id="13447-137">Выбрать **Записать подробности этого конфликта** , чтобы записать данные конфликта в файл.</span><span class="sxs-lookup"><span data-stu-id="13447-137">Select **Log the details of this conflict** to log conflict data to a file.</span></span> <span data-ttu-id="13447-138">Для указания размещения файла наведите указатель на меню **Просмотр** и щелкните **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="13447-138">To specify a location for the file, point to the **View** menu, and then click **Options**.</span></span> <span data-ttu-id="13447-139">Введите значение или нажмите кнопку обзора (**...**), а затем перейдите к необходимому файлу.</span><span class="sxs-lookup"><span data-stu-id="13447-139">Enter a value, or click the browse button (**...**), and then navigate to the appropriate file.</span></span> <span data-ttu-id="13447-140">Нажмите кнопку **ОК** для выхода из диалогового окна **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="13447-140">Click **OK** to exit the **Options** dialog box.</span></span>  
  
6.  <span data-ttu-id="13447-141">Закройте средство просмотра конфликтов репликации.</span><span class="sxs-lookup"><span data-stu-id="13447-141">Close the Replication Conflict Viewer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13447-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="13447-142">See Also</span></span>  
 <span data-ttu-id="13447-143">[Advanced Merge Replication Conflict Detection and Resolution](merge/advanced-merge-replication-conflict-detection-and-resolution.md) </span><span class="sxs-lookup"><span data-stu-id="13447-143">[Advanced Merge Replication Conflict Detection and Resolution](merge/advanced-merge-replication-conflict-detection-and-resolution.md) </span></span>  
 [<span data-ttu-id="13447-144">Определение арбитра для статей публикации слиянием</span><span class="sxs-lookup"><span data-stu-id="13447-144">Specify a Merge Article Resolver</span></span>](publish/specify-a-merge-article-resolver.md)  
  
  
