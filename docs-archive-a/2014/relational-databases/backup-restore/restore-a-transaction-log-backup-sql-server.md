---
title: Восстановление резервной копии журнала транзакций (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.restoretlog.options.f1
- sql12.swb.restoretlog.general.f1
helpviewer_keywords:
- restore log
- backing up transaction logs [SQL Server], restoring
- transaction log backups [SQL Server], restoring
- restoring transaction logs [SQL Server], restoring backups
- transaction log restores [SQL Server], SQL Server Management Studio
ms.assetid: 1de2b888-78a6-4fb2-a647-ba4bf097caf3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 68fe4bbc199d6555bd490d25f92491100b8bbfcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666680"
---
# <a name="restore-a-transaction-log-backup-sql-server"></a><span data-ttu-id="2a8e5-102">Восстановление резервной копии журнала транзакций (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2a8e5-102">Restore a Transaction Log Backup (SQL Server)</span></span>
  <span data-ttu-id="2a8e5-103">В этом разделе описывается восстановление журнала транзакций из резервной копии в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a8e5-103">This topic describes how to restore a transaction log backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="2a8e5-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="2a8e5-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2a8e5-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="2a8e5-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2a8e5-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="2a8e5-106">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="2a8e5-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="2a8e5-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2a8e5-108">**Для восстановления резервной копии журнала транзакций используется:**</span><span class="sxs-lookup"><span data-stu-id="2a8e5-108">**To restore a transaction log backup, using:**</span></span>  
  
     [<span data-ttu-id="2a8e5-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2a8e5-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2a8e5-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2a8e5-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="2a8e5-111">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="2a8e5-111">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2a8e5-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="2a8e5-112">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="2a8e5-113">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="2a8e5-113">Prerequisites</span></span>  
  
-   <span data-ttu-id="2a8e5-114">Резервные копии должны восстанавливаться в том же порядке, в котором они были созданы.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-114">Backups must be restored in the order in which they were created.</span></span> <span data-ttu-id="2a8e5-115">Перед тем как можно будет восстановить определенную резервную копию журнала транзакций, вначале должны быть восстановлены следующие более ранние резервные копии без отката незафиксированных транзакций, т.е.с параметром WITH NORECOVERY:</span><span class="sxs-lookup"><span data-stu-id="2a8e5-115">Before you can restore a particular transaction log backup, you must first restore the following previous backups without rolling back uncommitted transactions, that is WITH NORECOVERY:</span></span>  
  
    -   <span data-ttu-id="2a8e5-116">Полная резервная копия и последняя разностная резервная копия, если таковая имеется, созданные перед заданной резервной копией журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-116">The full database backup and the last differential backup, if any, taken before the particular transaction log backup.</span></span> <span data-ttu-id="2a8e5-117">Перед созданием самой последней полной или разностной резервной копии базы данных необходимо, чтобы в базе данных использовалась модель полного восстановления (или модель восстановления с неполным протоколированием).</span><span class="sxs-lookup"><span data-stu-id="2a8e5-117">Before the most recent full or differential database backup was created, the database must have been using the full recovery model or bulk-logged recovery model.</span></span>  
  
    -   <span data-ttu-id="2a8e5-118">Все резервные копии журнала транзакций, созданные после полной резервной копии базы данных или разностной резервной копии (если она восстанавливается), и перед заданной резервной копией журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-118">All transaction log backups taken after the full database backup or the differential backup (if you restore one) and before the particular transaction log backup.</span></span> <span data-ttu-id="2a8e5-119">Резервные копии журналов необходимо применять в порядке их создания, без разрывов в цепочке журналов.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-119">Log backups must be applied in the sequence in which they were created, without any gaps in the log chain.</span></span>  
  
         <span data-ttu-id="2a8e5-120">Дополнительные сведения о резервных копиях журналов транзакций см. в статье [Резервные копии журналов транзакций (SQL Server)](transaction-log-backups-sql-server.md) и [Применение резервных копий журналов транзакций (SQL Server)](apply-transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2a8e5-120">For more information about transaction log backups, see [Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) and [Apply Transaction Log Backups &#40;SQL Server&#41;](apply-transaction-log-backups-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2a8e5-121">безопасность</span><span class="sxs-lookup"><span data-stu-id="2a8e5-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2a8e5-122">Permissions</span><span class="sxs-lookup"><span data-stu-id="2a8e5-122">Permissions</span></span>  
 <span data-ttu-id="2a8e5-123">Разрешения на выполнение инструкции RESTORE даются ролям, в которых данные о членстве всегда доступны серверу.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-123">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="2a8e5-124">Так как членство в предопределенной роли базы данных может быть проверено только тогда, когда база данных доступна и не повреждена, что не всегда имеет место при выполнении инструкции RESTORE, члены предопределенной роли базы данных **db_owner** не имеют разрешений RESTORE.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-124">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2a8e5-125">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2a8e5-125">Using SQL Server Management Studio</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="2a8e5-126">Обычно процесс восстановления заключается в выборе в диалоговом окне **Восстановление базы данных** резервных копий журналов, данных и разностных резервных копий.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-126">The normal process of a restore is to select the log backups in the **Restore Database** dialog box along with the data and differential backups.</span></span>  
  
#### <a name="to-restore-a-transaction-log-backup"></a><span data-ttu-id="2a8e5-127">Восстановление резервной копии журнала транзакций</span><span class="sxs-lookup"><span data-stu-id="2a8e5-127">To restore a transaction log backup</span></span>  
  
1.  <span data-ttu-id="2a8e5-128">После подключения к соответствующему экземпляру [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] в обозревателе объектов разверните дерево сервера, щелкнув его имя.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-128">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="2a8e5-129">Раскройте узел **Базы данных**и в зависимости от типа восстанавливаемой базы данных выберите пользовательскую базу данных или раскройте узел **Системные базы данных** и выберите системную базу данных.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-129">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="2a8e5-130">Щелкните правой кнопкой мыши базу данных, выберите пункт **Задачи**, затем пункт **Восстановить**и пункт **Журнал транзакций**. В результате откроется диалоговое окно **Восстановление журнала транзакций** .</span><span class="sxs-lookup"><span data-stu-id="2a8e5-130">Right-click the database, point to **Tasks**, point to **Restore**, and then click **Transaction Log**, which opens the **Restore Transaction Log** dialog box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2a8e5-131">Если **Журнал транзакций** неактивен, возможно, сначала потребуется восстановление из полной или разностной резервной копии.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-131">If **Transaction Log** is grayed out, you may need to restore a full or differential backup first.</span></span> <span data-ttu-id="2a8e5-132">Воспользуйтесь диалоговым окном резервного копирования **База данных** .</span><span class="sxs-lookup"><span data-stu-id="2a8e5-132">Use the **Database** backup dialog box.</span></span>  
  
4.  <span data-ttu-id="2a8e5-133">На странице **Общие** в списке **База данных** выберите имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-133">On the **General** page, in the **Database** list box, select the name of a database.</span></span> <span data-ttu-id="2a8e5-134">Перечислены только базы данных, которые находятся в состоянии восстановления.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-134">Only databases in the restoring state are listed.</span></span>  
  
5.  <span data-ttu-id="2a8e5-135">Чтобы указать источник и расположение восстанавливаемых резервных наборов данных, выберите один из следующих вариантов.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-135">To specify the source and location of the backup sets to restore, click one of the following options:</span></span>  
  
    -   <span data-ttu-id="2a8e5-136">**Из предыдущих резервных копий базы данных**</span><span class="sxs-lookup"><span data-stu-id="2a8e5-136">**From previous backups of database**</span></span>  
  
         <span data-ttu-id="2a8e5-137">Выберите из раскрывающегося списка базу данных для восстановления.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-137">Select the database to restore from the drop-down list.</span></span> <span data-ttu-id="2a8e5-138">Данный список содержит только базы данных, резервное копирование которых было выполнено в соответствии с журналом резервного копирования **msdb** .</span><span class="sxs-lookup"><span data-stu-id="2a8e5-138">The list contains only databases that have been backed up according to the **msdb** backup history.</span></span>  
  
    -   <span data-ttu-id="2a8e5-139">**Из файла или с ленты**</span><span class="sxs-lookup"><span data-stu-id="2a8e5-139">**From file or tape**</span></span>  
  
         <span data-ttu-id="2a8e5-140">Нажмите кнопку обзора ( **...** ), после чего откроется диалоговое окно **Выбор устройств резервного копирования** .</span><span class="sxs-lookup"><span data-stu-id="2a8e5-140">Click the browse (**...**) button to open the **Select backup devices** dialog box.</span></span> <span data-ttu-id="2a8e5-141">В окне **Тип носителя резервной копии** выберите один из перечисленных типов устройств.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-141">In the **Backup media type** box, select one of the listed device types.</span></span> <span data-ttu-id="2a8e5-142">Чтобы выбрать одно или несколько устройств в окне **Носитель резервной копии** , нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-142">To select one or more devices for the **Backup media** box, click **Add**.</span></span>  
  
         <span data-ttu-id="2a8e5-143">После добавления нужных устройств в списке **Носитель резервной копии** нажмите кнопку **ОК** для возвращения на страницу **Общие** .</span><span class="sxs-lookup"><span data-stu-id="2a8e5-143">After you add the devices you want to the **Backup media** list box, click **OK** to return to the **General** page.</span></span>  
  
6.  <span data-ttu-id="2a8e5-144">В сетке **Выберите резервные копии журнала транзакций для восстановления** выберите нужные резервные наборы.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-144">In the **Select the transaction log backups to restore** grid, select the backups to restore.</span></span> <span data-ttu-id="2a8e5-145">В этой сетке перечислены резервные копии журналов транзакций, доступные для выбранной базы данных.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-145">This grid lists the transaction log backups available for the selected database.</span></span> <span data-ttu-id="2a8e5-146">Резервная копия журналов доступна только в том случае, если ее **первый номер LSN** больше, чем **последний номер LSN** базы данных.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-146">A log backup is available only if its **First LSN** greater than the **Last LSN** of the database.</span></span> <span data-ttu-id="2a8e5-147">Резервные копии журналов перечислены в порядке содержащихся в них номеров LSN и должны быть восстановлены в этом порядке.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-147">Log backups are listed in the order of the log sequence numbers (LSN) they contain, and they must be restored in this order.</span></span>  
  
     <span data-ttu-id="2a8e5-148">В приведенной ниже таблице перечислены заголовки столбцов сетки, а также даны описания их значений.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-148">The following table lists the column headers of the grid and describes their values.</span></span>  
  
    |<span data-ttu-id="2a8e5-149">Заголовок</span><span class="sxs-lookup"><span data-stu-id="2a8e5-149">Header</span></span>|<span data-ttu-id="2a8e5-150">Значение</span><span class="sxs-lookup"><span data-stu-id="2a8e5-150">Value</span></span>|  
    |------------|-----------|  
    |<span data-ttu-id="2a8e5-151">**Восстановление**</span><span class="sxs-lookup"><span data-stu-id="2a8e5-151">**Restore**</span></span>|<span data-ttu-id="2a8e5-152">Установленные флажки показывают резервные наборы данных для восстановления.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-152">Selected check boxes indicate the backup sets to be restored.</span></span>|  
    |<span data-ttu-id="2a8e5-153">**имя**;</span><span class="sxs-lookup"><span data-stu-id="2a8e5-153">**Name**</span></span>|<span data-ttu-id="2a8e5-154">Имя резервного набора.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-154">Name of the backup set.</span></span>|  
    |<span data-ttu-id="2a8e5-155">**Компонент**</span><span class="sxs-lookup"><span data-stu-id="2a8e5-155">**Component**</span></span>|<span data-ttu-id="2a8e5-156">Компонент, для которого выполнено резервное копирование: **база данных**, **Файл** или \<blank> (для журналов транзакций).</span><span class="sxs-lookup"><span data-stu-id="2a8e5-156">Backed-up component: **Database**, **File**, or \<blank> (for transaction logs).</span></span>|  
    |<span data-ttu-id="2a8e5-157">**База данных**</span><span class="sxs-lookup"><span data-stu-id="2a8e5-157">**Database**</span></span>|<span data-ttu-id="2a8e5-158">Имя базы данных, участвовавшей в операции резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-158">Name of the database involved in the backup operation.</span></span>|  
    |<span data-ttu-id="2a8e5-159">**Дата начала**</span><span class="sxs-lookup"><span data-stu-id="2a8e5-159">**Start Date**</span></span>|<span data-ttu-id="2a8e5-160">Дата и время начала резервного копирования, представленные в соответствии с региональными стандартами клиента.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-160">Date and time when the backup operation began, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="2a8e5-161">**Дата завершения**</span><span class="sxs-lookup"><span data-stu-id="2a8e5-161">**Finish Date**</span></span>|<span data-ttu-id="2a8e5-162">Дата и время окончания резервного копирования, представленные в соответствии с региональными настройками клиента.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-162">Date and time when the backup operation finished, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="2a8e5-163">**Первый номер LSN**</span><span class="sxs-lookup"><span data-stu-id="2a8e5-163">**First LSN**</span></span>|<span data-ttu-id="2a8e5-164">Регистрационный номер транзакции в журнале для первой транзакции резервного набора данных</span><span class="sxs-lookup"><span data-stu-id="2a8e5-164">Log sequence number of the first transaction in the backup set.</span></span> <span data-ttu-id="2a8e5-165">Пустой для резервных копий файлов.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-165">Blank for file backups.</span></span>|  
    |<span data-ttu-id="2a8e5-166">**Последний номер LSN**</span><span class="sxs-lookup"><span data-stu-id="2a8e5-166">**Last LSN**</span></span>|<span data-ttu-id="2a8e5-167">Регистрационный номер в журнале для первой транзакции резервного набора данных</span><span class="sxs-lookup"><span data-stu-id="2a8e5-167">Log sequence number of the last transaction in the backup set.</span></span> <span data-ttu-id="2a8e5-168">Пустой для резервных копий файлов.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-168">Blank for file backups.</span></span>|  
    |<span data-ttu-id="2a8e5-169">**Номер LSN для контрольной точки**</span><span class="sxs-lookup"><span data-stu-id="2a8e5-169">**Checkpoint LSN**</span></span>|<span data-ttu-id="2a8e5-170">Регистрационный номер транзакции в журнале для последней контрольной точки на момент создания резервной копии.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-170">Log sequence number of the most recent checkpoint at the time the backup was created.</span></span>|  
    |<span data-ttu-id="2a8e5-171">**Полный номер LSN**</span><span class="sxs-lookup"><span data-stu-id="2a8e5-171">**Full LSN**</span></span>|<span data-ttu-id="2a8e5-172">Регистрационный номер транзакции в журнале для последней полной резервной копии базы данных.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-172">Log sequence number of the most recent full database backup.</span></span>|  
    |<span data-ttu-id="2a8e5-173">**Server**</span><span class="sxs-lookup"><span data-stu-id="2a8e5-173">**Server**</span></span>|<span data-ttu-id="2a8e5-174">Имя экземпляра ядра СУБД, выполнившего операцию резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-174">Name of the Database Engine instance that performed the backup operation.</span></span>|  
    |<span data-ttu-id="2a8e5-175">**Имя пользователя**</span><span class="sxs-lookup"><span data-stu-id="2a8e5-175">**User Name**</span></span>|<span data-ttu-id="2a8e5-176">Имя пользователя, выполнившего операцию резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-176">Name of the user who performed the backup operation.</span></span>|  
    |<span data-ttu-id="2a8e5-177">**Размер**</span><span class="sxs-lookup"><span data-stu-id="2a8e5-177">**Size**</span></span>|<span data-ttu-id="2a8e5-178">Размер резервного набора данных в байтах.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-178">Size of the backup set in bytes.</span></span>|  
    |<span data-ttu-id="2a8e5-179">**Положение**</span><span class="sxs-lookup"><span data-stu-id="2a8e5-179">**Position**</span></span>|<span data-ttu-id="2a8e5-180">Позиция резервного набора данных в томе.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-180">Position of the backup set in the volume.</span></span>|  
    |<span data-ttu-id="2a8e5-181">**Истечение срока**</span><span class="sxs-lookup"><span data-stu-id="2a8e5-181">**Expiration**</span></span>|<span data-ttu-id="2a8e5-182">Дата и время окончания срока действия для резервного набора.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-182">Date and time the backup set expires.</span></span>|  
  
7.  <span data-ttu-id="2a8e5-183">Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="2a8e5-183">Select one of the following:</span></span>  
  
    -   <span data-ttu-id="2a8e5-184">**На момент времени**</span><span class="sxs-lookup"><span data-stu-id="2a8e5-184">**Point in time**</span></span>  
  
         <span data-ttu-id="2a8e5-185">Либо сохраните значение по умолчанию (**Самый последний**), либо выберите конкретную дату и время, нажав кнопку обзора и открыв диалоговое окно **Восстановление на момент времени** .</span><span class="sxs-lookup"><span data-stu-id="2a8e5-185">Either retain the default (**Most recent possible**) or select a specific date and time by clicking the browse button, which opens the **Point in Time Restore** dialog box.</span></span>  
  
    -   <span data-ttu-id="2a8e5-186">**До помеченной транзакции**</span><span class="sxs-lookup"><span data-stu-id="2a8e5-186">**Marked transaction**</span></span>  
  
         <span data-ttu-id="2a8e5-187">Восстановите базу данных до помеченной транзакции.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-187">Restore the database to a previously marked transaction.</span></span> <span data-ttu-id="2a8e5-188">Выбор данного параметра открывает диалоговое окно **Выбор помеченной транзакции** , в котором отображается сетка; в ней перечислены помеченные транзакции, доступные в выбранных резервных копиях журналов транзакций.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-188">Selecting this option launches the **Select Marked Transaction** dialog box, which displays a grid listing the marked transactions available in the selected transaction log backups.</span></span>  
  
         <span data-ttu-id="2a8e5-189">По умолчанию восстановление проводится до помеченной транзакции, не включая ее.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-189">By default, the restore is up to, but excluding, the marked transaction.</span></span> <span data-ttu-id="2a8e5-190">Чтобы восстановить и помеченную транзакцию, выберите пункт **Включая помеченную транзакцию**.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-190">To restore the marked transaction also, select **Include marked transaction**.</span></span>  
  
         <span data-ttu-id="2a8e5-191">В приведенной ниже таблице перечислены заголовки столбцов сетки, а также даны описания их значений.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-191">The following table lists the column headers of the grid and describes their values.</span></span>  
  
        |<span data-ttu-id="2a8e5-192">Заголовок</span><span class="sxs-lookup"><span data-stu-id="2a8e5-192">Header</span></span>|<span data-ttu-id="2a8e5-193">Значение</span><span class="sxs-lookup"><span data-stu-id="2a8e5-193">Value</span></span>|  
        |------------|-----------|  
        |\<blank>|<span data-ttu-id="2a8e5-194">Отображает флажок для выбора маркера.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-194">Displays a checkbox for selecting the mark.</span></span>|  
        |<span data-ttu-id="2a8e5-195">**Отметка транзакции**</span><span class="sxs-lookup"><span data-stu-id="2a8e5-195">**Transaction Mark**</span></span>|<span data-ttu-id="2a8e5-196">Имя помеченной транзакции, заданное пользователем при фиксации транзакции.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-196">Name of the marked transaction specified by the user when the transaction was committed.</span></span>|  
        |<span data-ttu-id="2a8e5-197">**Дата**</span><span class="sxs-lookup"><span data-stu-id="2a8e5-197">**Date**</span></span>|<span data-ttu-id="2a8e5-198">Дата и время фиксации транзакции.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-198">Date and time of the transaction when it was committed.</span></span> <span data-ttu-id="2a8e5-199">Дата и время транзакции отображаются, в соответствии с данными в таблице **msdbgmarkhistory** , а не с датой и временем на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-199">Transaction date and time are displayed as recorded in the **msdbgmarkhistory** table, not in the client computer's date and time.</span></span>|  
        |<span data-ttu-id="2a8e5-200">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2a8e5-200">**Description**</span></span>|<span data-ttu-id="2a8e5-201">Описание помеченной транзакции, заданное пользователем при ее фиксации (при его наличии).</span><span class="sxs-lookup"><span data-stu-id="2a8e5-201">Description of marked transaction specified by the user when the transaction was committed (if any).</span></span>|  
        |<span data-ttu-id="2a8e5-202">**Номер LSN**</span><span class="sxs-lookup"><span data-stu-id="2a8e5-202">**LSN**</span></span>|<span data-ttu-id="2a8e5-203">Регистрационный номер помеченной транзакции в журнале.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-203">Log sequence number of the marked transaction.</span></span>|  
        |<span data-ttu-id="2a8e5-204">**База данных**</span><span class="sxs-lookup"><span data-stu-id="2a8e5-204">**Database**</span></span>|<span data-ttu-id="2a8e5-205">Имя базы данных, в которой была зафиксирована помеченная транзакция.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-205">Name of the database where the marked transaction was committed.</span></span>|  
        |<span data-ttu-id="2a8e5-206">**Имя пользователя**</span><span class="sxs-lookup"><span data-stu-id="2a8e5-206">**User Name**</span></span>|<span data-ttu-id="2a8e5-207">Имя пользователя базы данных, зафиксировавшего помеченную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-207">Name of the database user who committed the marked transaction.</span></span>|  
  
8.  <span data-ttu-id="2a8e5-208">Чтобы просмотреть или выбрать дополнительные параметры, нажмите кнопку **Параметры** на панели **Выбор страницы** .</span><span class="sxs-lookup"><span data-stu-id="2a8e5-208">To view or select the advanced options, click **Options** in the **Select a page** pane.</span></span>  
  
9. <span data-ttu-id="2a8e5-209">В разделе **Восстановление параметров** предусмотрены следующие варианты выбора:</span><span class="sxs-lookup"><span data-stu-id="2a8e5-209">In the **Restore options** section, the choices are:</span></span>  
  
    -   <span data-ttu-id="2a8e5-210">**Сохранить параметры репликации (WITH KEEP_REPLICATION)**</span><span class="sxs-lookup"><span data-stu-id="2a8e5-210">**Preserve the replication settings (WITH KEEP_REPLICATION)**</span></span>  
  
         <span data-ttu-id="2a8e5-211">Сохраняет настройки репликации при восстановлении опубликованной базы данных на сервере, отличном от сервера, на котором была создана база данных.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-211">Preserves the replication settings when restoring a published database to a server other than the server where the database was created.</span></span>  
  
         <span data-ttu-id="2a8e5-212">Этот параметр доступен только с параметром **оставить базу данных готовой к использованию, выполнив откат незафиксированных транзакций...** (описывается далее), что эквивалентно восстановлению резервной копии с `RECOVERY` параметром.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-212">This option is available only with the **Leave the database ready for use by rolling back the uncommitted transactions...** option (described later), which is equivalent to restoring a backup with the `RECOVERY` option.</span></span>  
  
         <span data-ttu-id="2a8e5-213">Установка этого параметра эквивалентна использованию `KEEP_REPLICATION` параметра в [!INCLUDE[tsql](../../includes/tsql-md.md)] `RESTORE` инструкции.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-213">Checking this option is equivalent to using the `KEEP_REPLICATION` option in a [!INCLUDE[tsql](../../includes/tsql-md.md)]`RESTORE` statement.</span></span>  
  
    -   <span data-ttu-id="2a8e5-214">**Выдавать приглашение перед восстановлением каждой резервной копии**</span><span class="sxs-lookup"><span data-stu-id="2a8e5-214">**Prompt before restoring each backup**</span></span>  
  
         <span data-ttu-id="2a8e5-215">Перед восстановлением каждого резервного набора данных (после первого) этот параметр вызывает диалоговое окно **Продолжение восстановления** , в котором выводится вопрос, нужно ли продолжать последовательность восстановления.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-215">Before restoring each backup set (after the first), this option brings up the **Continue with Restore** dialog box, which asks you to indicate whether you want to continue the restore sequence.</span></span> <span data-ttu-id="2a8e5-216">В этом окне отображается имя следующего набора носителей (если он доступен), имя резервного набора данных и его описание.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-216">This dialog displays the name of the next media set (if available), the backup set name, and backup set description.</span></span>  
  
         <span data-ttu-id="2a8e5-217">Этот параметр особенно полезен, если необходимо поочередно менять ленты для различных наборов носителей.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-217">This option is particularly useful when you must swap tapes for different media sets.</span></span> <span data-ttu-id="2a8e5-218">Например, можно использовать этот параметр, когда на сервере установлено только одно ленточное устройство.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-218">For example, you can use it when the server has only one tape device.</span></span> <span data-ttu-id="2a8e5-219">Перед нажатием кнопки **ОК**дождитесь готовности к продолжению.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-219">Wait until you are ready to proceed before clicking **OK**.</span></span>  
  
         <span data-ttu-id="2a8e5-220">Чтобы оставить базу данных в состоянии восстановления, нажмите кнопку **Нет** .</span><span class="sxs-lookup"><span data-stu-id="2a8e5-220">Clicking **No** leaves the database in the restoring state.</span></span> <span data-ttu-id="2a8e5-221">Для удобства можно продолжить последовательность восстановления после завершения последнего восстановления.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-221">At your convenience, you can continue the restore sequence after the last restore that completed.</span></span> <span data-ttu-id="2a8e5-222">Если очередная резервная копия представляет собой резервную копию данных или разностную резервную копию, следует вновь использовать задачу **Восстановление базы данных** .</span><span class="sxs-lookup"><span data-stu-id="2a8e5-222">If the next backup is a data or differential backup, use the **Restore Database** task again.</span></span> <span data-ttu-id="2a8e5-223">Если очередная резервная копия представляет собой резервную копию журнала, следует использовать задачу **Восстановление журнала транзакций** .</span><span class="sxs-lookup"><span data-stu-id="2a8e5-223">If the next backup is a log backup, use the **Restore Transaction Log** task.</span></span>  
  
    -   <span data-ttu-id="2a8e5-224">**Ограничить доступ к восстановленной базе данных (WITH RESTRICTED_USER)**</span><span class="sxs-lookup"><span data-stu-id="2a8e5-224">**Restrict access to the restored database (WITH RESTRICTED_USER)**</span></span>  
  
         <span data-ttu-id="2a8e5-225">Доступ к восстановленной базе данных будет только у пользователей **db_owner**, **dbcreator**или **sysadmin**.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-225">Makes the restored database available only to the members of **db_owner**, **dbcreator**, or **sysadmin**.</span></span>  
  
         <span data-ttu-id="2a8e5-226">Установка этого параметра является синонимом использования `RESTRICTED_USER` параметра в [!INCLUDE[tsql](../../includes/tsql-md.md)] `RESTORE` инструкции.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-226">Checking this option is synonymous to using the `RESTRICTED_USER` option in a [!INCLUDE[tsql](../../includes/tsql-md.md)]`RESTORE` statement.</span></span>  
  
10. <span data-ttu-id="2a8e5-227">В качестве значения параметра **Состояние восстановления** укажите состояние базы данных после операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-227">For the **Recovery state** options, specify the state of the database after the restore operation.</span></span>  
  
    -   <span data-ttu-id="2a8e5-228">**Восстановить готовность базы данных к работе, выполнив откат незафиксированных транзакций. Невозможно восстановить дополнительные журналы транзакций. (RESTORE WITH RECOVERY)**</span><span class="sxs-lookup"><span data-stu-id="2a8e5-228">**Leave the database ready for use by rolling back uncommitted transactions. Additional transaction logs cannot be restored. (RESTORE WITH RECOVERY)**</span></span>  
  
         <span data-ttu-id="2a8e5-229">Восстанавливает базу данных.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-229">Recovers the database.</span></span> <span data-ttu-id="2a8e5-230">Этот параметр эквивалентен `RECOVERY` параметру в [!INCLUDE[tsql](../../includes/tsql-md.md)] `RESTORE` инструкции.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-230">This option is equivalent to the `RECOVERY` option in a [!INCLUDE[tsql](../../includes/tsql-md.md)]`RESTORE` statement.</span></span>  
  
         <span data-ttu-id="2a8e5-231">Этот параметр следует выбирать только в том случае, если нет файлов журнала, подлежащих восстановлению.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-231">Choose this option only if you have no log files you want to restore.</span></span>  
  
    -   <span data-ttu-id="2a8e5-232">**Оставить базу данных в нерабочем состоянии и не производить откат незафиксированных транзакций. Можно восстановить дополнительные журналы транзакций. (RESTORE WITH NORECOVERY)**</span><span class="sxs-lookup"><span data-stu-id="2a8e5-232">**Leave the database non-operational, and do not roll back uncommitted transactions. Additional transaction logs can be restored. (RESTORE WITH NORECOVERY)**</span></span>  
  
         <span data-ttu-id="2a8e5-233">Оставить базу данных в состоянии `RESTORING` (невосстановленном).</span><span class="sxs-lookup"><span data-stu-id="2a8e5-233">Leaves the database unrecovered, in the `RESTORING` state.</span></span> <span data-ttu-id="2a8e5-234">Этот параметр эквивалентен использованию `NORECOVERY` параметра в [!INCLUDE[tsql](../../includes/tsql-md.md)] `RESTORE` инструкции.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-234">This option is equivalent to using the `NORECOVERY` option in a [!INCLUDE[tsql](../../includes/tsql-md.md)]`RESTORE` statement.</span></span>  
  
         <span data-ttu-id="2a8e5-235">При выборе данного параметра параметр **Сохранить настройки репликации** становится недоступным.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-235">When you choose this option, the **Preserve replication settings** option is unavailable.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="2a8e5-236">Всегда выбирайте этот параметр для зеркальной или второстепенной базы данных.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-236">For a mirror or secondary database, always select this option.</span></span>  
  
    -   <span data-ttu-id="2a8e5-237">**Оставить базу данных в режиме «только для чтения». Отменить незафиксированные транзакции, но сохранить отмененные действия в файле, чтобы результаты восстановления могли быть отменены. (RESTORE WITH STANDBY)**</span><span class="sxs-lookup"><span data-stu-id="2a8e5-237">**Leave the database in read-only mode. Undo uncommitted transactions, but save the undo actions in a file so that recovery effects can be reversed. (RESTORE WITH STANDBY)**</span></span>  
  
         <span data-ttu-id="2a8e5-238">Оставляет базу данных в резервном состоянии.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-238">Leaves the database in a standby state.</span></span> <span data-ttu-id="2a8e5-239">Этот параметр эквивалентен использованию `STANDBY` параметра в [!INCLUDE[tsql](../../includes/tsql-md.md)] `RESTORE` инструкции.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-239">This option is equivalent to using the `STANDBY` option in a [!INCLUDE[tsql](../../includes/tsql-md.md)]`RESTORE` statement.</span></span>  
  
         <span data-ttu-id="2a8e5-240">При выборе этого параметра необходимо указать резервный файл.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-240">Choosing this option requires that you specify a standby file.</span></span>  
  
11. <span data-ttu-id="2a8e5-241">При необходимости укажите имя резервного файла в текстовом поле **Резервный файл** .</span><span class="sxs-lookup"><span data-stu-id="2a8e5-241">Optionally, specify a standby file name in the **Standby file** text box.</span></span> <span data-ttu-id="2a8e5-242">Этот параметр необходим, чтобы оставить базу данных в режиме только для чтения.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-242">This option is required if you leave the database in read-only mode.</span></span> <span data-ttu-id="2a8e5-243">Резервный файл можно выбрать в проводнике или ввести полный путь к нему в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-243">You can browse for the standby file or type its pathname in the text box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2a8e5-244">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2a8e5-244">Using Transact-SQL</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2a8e5-245">Во избежание неоднозначности в каждой инструкции WITH RECOVERY рекомендуется явное задание параметра WITH NORECOVERY или WITH RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-245">We recommend that you always explicitly specify either WITH NORECOVERY or WITH RECOVERY in every RESTORE statement to eliminate ambiguity.</span></span> <span data-ttu-id="2a8e5-246">Это особенно важно учитывать при написании скриптов.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-246">This is particularly important when writing scripts.</span></span>  
  
#### <a name="to-restore-a-transaction-log-backup"></a><span data-ttu-id="2a8e5-247">Восстановление резервной копии журнала транзакций</span><span class="sxs-lookup"><span data-stu-id="2a8e5-247">To restore a transaction log backup</span></span>  
  
1.  <span data-ttu-id="2a8e5-248">Чтобы применить резервную копию журналов транзакций, выполните инструкцию RESTORE LOG, указав при этом:</span><span class="sxs-lookup"><span data-stu-id="2a8e5-248">Execute the RESTORE LOG statement to apply the transaction log backup, specifying:</span></span>  
  
    -   <span data-ttu-id="2a8e5-249">Имя базы данных, к которой будет применен журнал транзакций.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-249">The name of the database to which the transaction log will be applied.</span></span>  
  
    -   <span data-ttu-id="2a8e5-250">устройство резервного копирования, с которого будет восстановлена резервная копия журналов транзакций;</span><span class="sxs-lookup"><span data-stu-id="2a8e5-250">The backup device where the transaction log backup will be restored from.</span></span>  
  
    -   <span data-ttu-id="2a8e5-251">Предложение NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-251">The NORECOVERY clause.</span></span>  
  
     <span data-ttu-id="2a8e5-252">В этой инструкции применяется следующая основная синтаксическая конструкция:</span><span class="sxs-lookup"><span data-stu-id="2a8e5-252">The basic syntax for this statement is as follows:</span></span>  
  
     <span data-ttu-id="2a8e5-253">RESTORE LOG *имя_базы_данных* FROM <устройство_резервного_копирования> WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-253">RESTORE LOG *database_name* FROM <backup_device> WITH NORECOVERY.</span></span>  
  
     <span data-ttu-id="2a8e5-254">Здесь *имя_базы_данных* — имя базы данных, а <устройство_резервного_копирования> — имя устройства, содержащего восстанавливаемую резервную копию журнала.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-254">Where *database_name* is the name of database and <backup_device>is the name of the device that contains the log backup being restored.</span></span>  
  
2.  <span data-ttu-id="2a8e5-255">Повторите шаг 1 для каждой резервной копии журналов транзакций, которые необходимо применить.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-255">Repeat step 1 for each transaction log backup you have to apply.</span></span>  
  
3.  <span data-ttu-id="2a8e5-256">После восстановления последней резервной копии из последовательности восстановления базу данных следует восстановить при помощи одной из следующих инструкций.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-256">After restoring the last backup in your restore sequence, to recover the database use one of the following statements:</span></span>  
  
    -   <span data-ttu-id="2a8e5-257">Восстановить базу данных в составе последней инструкции RESTORE LOG:</span><span class="sxs-lookup"><span data-stu-id="2a8e5-257">Recover the database as part of the last RESTORE LOG statement:</span></span>  
  
        ```  
        RESTORE LOG <database_name> FROM <backup_device> WITH RECOVERY;  
        GO  
        ```  
  
    -   <span data-ttu-id="2a8e5-258">Подождать, а затем восстановить базу данных отдельной инструкцией RESTORE DATABASE:</span><span class="sxs-lookup"><span data-stu-id="2a8e5-258">Wait to recover the database by using a separate RESTORE DATABASE statement:</span></span>  
  
        ```  
        RESTORE LOG <database_name> FROM <backup_device> WITH NORECOVERY;   
        RESTORE DATABASE <database_name> WITH RECOVERY;  
        GO  
        ```  
  
         <span data-ttu-id="2a8e5-259">В последнем случае можно проверить, восстановлены ли все нужные резервные копии журналов.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-259">Waiting to recover the database gives you the opportunity to verify that you have restored all of the necessary log backups.</span></span> <span data-ttu-id="2a8e5-260">Такой подход часто полезен при выполнении восстановления на момент времени.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-260">This approach is often advisable when you are performing a point-in-time restore.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="2a8e5-261">При создании зеркальной базы данных этап восстановления можно пропустить.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-261">If you are creating a mirror database, omit the recovery step.</span></span> <span data-ttu-id="2a8e5-262">Зеркальная база данных должна остаться в состоянии RESTORING.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-262">A mirror database must remain in the RESTORING state.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="2a8e5-263">Примеры (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="2a8e5-263">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="2a8e5-264">По умолчанию для базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] используется простая модель восстановления.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-264">By default, the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database uses the simple recovery model.</span></span> <span data-ttu-id="2a8e5-265">В следующем примере для перехода на модель полного восстановления требуется изменить базу данных следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2a8e5-265">The following examples require modifying the database to use the full recovery model, as follows:</span></span>  
  
```sql  
ALTER DATABASE AdventureWorks2012 SET RECOVERY FULL;  
```  
  
#### <a name="a-applying-a-single-transaction-log-backup"></a><span data-ttu-id="2a8e5-266">A.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-266">A.</span></span> <span data-ttu-id="2a8e5-267">Применение одной резервной копии журнала транзакций</span><span class="sxs-lookup"><span data-stu-id="2a8e5-267">Applying a single transaction log backup</span></span>  
 <span data-ttu-id="2a8e5-268">В следующем примере база данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] восстанавливается с помощью полной резервной копии базы данных, которая находится на устройстве резервного копирования с именем `AdventureWorks2012_1`.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-268">The following example starts by restoring the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database by using a full database backup that resides on a backup device named `AdventureWorks2012_1`.</span></span> <span data-ttu-id="2a8e5-269">Затем применяется первая резервная копия журнала транзакций, находящаяся на устройстве с именем `AdventureWorks2012_log`.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-269">The example then applies the first transaction log backup that resides on a backup device named `AdventureWorks2012_log`.</span></span> <span data-ttu-id="2a8e5-270">В заключение происходит восстановление базы данных.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-270">Finally, the example recovers the database.</span></span>  
  
```sql  
RESTORE DATABASE AdventureWorks2012  
   FROM AdventureWorks2012_1  
   WITH NORECOVERY;  
GO  
RESTORE LOG AdventureWorks2012  
   FROM AdventureWorks2012_log  
   WITH FILE = 1,  
   WITH NORECOVERY;  
GO  
RESTORE DATABASE AdventureWorks2012  
   WITH RECOVERY;  
GO  
```  
  
#### <a name="b-applying-multiple-transaction-log-backups"></a><span data-ttu-id="2a8e5-271">Б.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-271">B.</span></span> <span data-ttu-id="2a8e5-272">Применение нескольких резервных копий журналов транзакций</span><span class="sxs-lookup"><span data-stu-id="2a8e5-272">Applying multiple transaction log backups</span></span>  
 <span data-ttu-id="2a8e5-273">В следующем примере база данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] восстанавливается с помощью полной резервной копии базы данных, которая находится на устройстве резервного копирования с именем `AdventureWorks2012_1`.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-273">The following example starts by restoring the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database by using a full database backup that resides on a backup device named `AdventureWorks2012_1`.</span></span> <span data-ttu-id="2a8e5-274">Затем последовательно применяются первые три копии журнала транзакций, находящиеся на устройстве с именем `AdventureWorks2012_log`.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-274">The example then applies, one by one, the first three transaction log backups that reside on a backup device named `AdventureWorks2012_log`.</span></span> <span data-ttu-id="2a8e5-275">В заключение происходит восстановление базы данных.</span><span class="sxs-lookup"><span data-stu-id="2a8e5-275">Finally, the example recovers the database.</span></span>  
  
```sql  
RESTORE DATABASE AdventureWorks2012  
   FROM AdventureWorks2012_1  
   WITH NORECOVERY;  
GO  
RESTORE LOG AdventureWorks2012  
   FROM AdventureWorks2012_log  
   WITH FILE = 1,  
   NORECOVERY;  
GO  
RESTORE LOG AdventureWorks2012  
   FROM AdventureWorks2012_log  
   WITH FILE = 2,  
   WITH NORECOVERY;  
GO  
RESTORE LOG AdventureWorks2012  
   FROM AdventureWorks2012_log  
   WITH FILE = 3,  
   WITH NORECOVERY;  
GO  
RESTORE DATABASE AdventureWorks2012  
   WITH RECOVERY;  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="2a8e5-276">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="2a8e5-276">Related Tasks</span></span>  
  
-   [<span data-ttu-id="2a8e5-277">Создание резервной копии журнала транзакций (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2a8e5-277">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
-   [<span data-ttu-id="2a8e5-278">Восстановление резервной копии базы данных &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="2a8e5-278">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="2a8e5-279">Восстановление базы данных до точки сбоя в модели полного восстановления (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="2a8e5-279">Restore a Database to the Point of Failure Under the Full Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-database-to-point-of-failure-full-recovery.md)  
  
-   [<span data-ttu-id="2a8e5-280">Восстановление базы данных SQL Server до определенного момента времени (модель полного восстановления)</span><span class="sxs-lookup"><span data-stu-id="2a8e5-280">Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;</span></span>](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md)  
  
-   [<span data-ttu-id="2a8e5-281">Восстановление базы данных до помеченной транзакции (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="2a8e5-281">Restore a Database to a Marked Transaction &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-to-a-marked-transaction-sql-server-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="2a8e5-282">См. также:</span><span class="sxs-lookup"><span data-stu-id="2a8e5-282">See Also</span></span>  
 <span data-ttu-id="2a8e5-283">[RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2a8e5-283">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="2a8e5-284">Применение резервных копий журналов транзакций (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2a8e5-284">Apply Transaction Log Backups &#40;SQL Server&#41;</span></span>](apply-transaction-log-backups-sql-server.md)  
  
  
