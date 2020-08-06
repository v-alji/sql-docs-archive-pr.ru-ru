---
title: Восстановление базы данных до помеченной транзакции (среда SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.restoretlog.markedtransaction.f1
helpviewer_keywords:
- database restores [SQL Server], marked transactions
- restoring databases [SQL Server], marked transactions
- marked transactions [SQL Server], restoring
ms.assetid: 8f0ea144-1819-4832-905f-e5d0f49b066b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8de9ef5bed389f020f14e60ccd99f39698e7110f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666686"
---
# <a name="restore-a-database-to-a-marked-transaction-sql-server-management-studio"></a><span data-ttu-id="9ed21-102">Восстановление базы данных до помеченной транзакции (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="9ed21-102">Restore a Database to a Marked Transaction (SQL Server Management Studio)</span></span>
  <span data-ttu-id="9ed21-103">Если база данных находится в состоянии восстановления, то для ее восстановления в какое-либо состояние, доступное среди резервных копий, можно использовать диалоговое окно **Восстановление журнала транзакций** .</span><span class="sxs-lookup"><span data-stu-id="9ed21-103">When a database is in the restoring state, you can use the **Restore Transaction Log** dialog box to restore the database to a marked transaction in the available log backups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9ed21-104">Дополнительные сведения см. в статье [Использование помеченных транзакций для согласованного восстановления связанных баз данных (модель полного восстановления)](use-marked-transactions-to-recover-related-databases-consistently.md) and [Восстановление связанных баз данных, которые содержат помеченную транзакцию](recovery-of-related-databases-that-contain-marked-transaction.md).</span><span class="sxs-lookup"><span data-stu-id="9ed21-104">For more information, see [Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md) and [Recovery of Related  Databases That Contain Marked Transaction](recovery-of-related-databases-that-contain-marked-transaction.md).</span></span>  
  
### <a name="to-restore-a-marked-transaction"></a><span data-ttu-id="9ed21-105">Восстановление помеченной транзакции</span><span class="sxs-lookup"><span data-stu-id="9ed21-105">To restore a marked transaction</span></span>  
  
1.  <span data-ttu-id="9ed21-106">После подключения к соответствующему экземпляру [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] в обозревателе объектов разверните дерево сервера, щелкнув его имя.</span><span class="sxs-lookup"><span data-stu-id="9ed21-106">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="9ed21-107">Раскройте узел **Базы данных**и в зависимости от типа восстанавливаемой базы данных выберите пользовательскую базу данных или раскройте узел **Системные базы данных** и выберите системную базу данных.</span><span class="sxs-lookup"><span data-stu-id="9ed21-107">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="9ed21-108">Щелкните правой кнопкой мыши базу данных, укажите на пункт **Задачи**и щелкните **Восстановить**.</span><span class="sxs-lookup"><span data-stu-id="9ed21-108">Right-click the database, point to **Tasks**, and then click **Restore**.</span></span>  
  
4.  <span data-ttu-id="9ed21-109">Выберите **Журнал транзакций**, после чего откроется диалоговое окно **Восстановление журнала транзакций** .</span><span class="sxs-lookup"><span data-stu-id="9ed21-109">Click **Transaction Log**, which opens the **Restore Transaction Log** dialog box.</span></span>  
  
5.  <span data-ttu-id="9ed21-110">На странице **Общие** в разделе **Восстановление** выберите пункт **До помеченной транзакции**, после чего откроется диалоговое окно **Выбор помеченной транзакции** .</span><span class="sxs-lookup"><span data-stu-id="9ed21-110">On the **General** page, in the **Restore To** section, select **Marked transaction**, which opens the **Select Marked Transaction** dialog box.</span></span> <span data-ttu-id="9ed21-111">В указанном диалоговом окне содержится список помеченных транзакций, доступных в выбранных резервных копиях журналов транзакций.</span><span class="sxs-lookup"><span data-stu-id="9ed21-111">This dialog box displays a grid listing the marked transactions available in the selected transaction log backups.</span></span>  
  
     <span data-ttu-id="9ed21-112">По умолчанию восстановление проводится до помеченной транзакции, не включая ее.</span><span class="sxs-lookup"><span data-stu-id="9ed21-112">By default, the restore is up to, but excluding, the marked transaction.</span></span> <span data-ttu-id="9ed21-113">Чтобы восстановить и помеченную транзакцию, выберите пункт **Включая помеченную транзакцию**.</span><span class="sxs-lookup"><span data-stu-id="9ed21-113">To restore the marked transaction also, select **Include marked transaction**.</span></span>  
  
     <span data-ttu-id="9ed21-114">В приведенной ниже таблице перечислены заголовки столбцов сетки, а также даны описания их значений.</span><span class="sxs-lookup"><span data-stu-id="9ed21-114">The following table lists the column headers of the grid and describes their values.</span></span>  
  
    |<span data-ttu-id="9ed21-115">Заголовок</span><span class="sxs-lookup"><span data-stu-id="9ed21-115">Header</span></span>|<span data-ttu-id="9ed21-116">Значение</span><span class="sxs-lookup"><span data-stu-id="9ed21-116">Value</span></span>|  
    |------------|-----------|  
    |\<blank>|<span data-ttu-id="9ed21-117">Отображает флажок для выбора маркера.</span><span class="sxs-lookup"><span data-stu-id="9ed21-117">Displays a checkbox for selecting the mark.</span></span>|  
    |<span data-ttu-id="9ed21-118">**Отметка транзакции**</span><span class="sxs-lookup"><span data-stu-id="9ed21-118">**Transaction Mark**</span></span>|<span data-ttu-id="9ed21-119">Имя помеченной транзакции, заданное пользователем при фиксации транзакции.</span><span class="sxs-lookup"><span data-stu-id="9ed21-119">Name of the marked transaction specified by the user when the transaction was committed.</span></span>|  
    |<span data-ttu-id="9ed21-120">**Дата**</span><span class="sxs-lookup"><span data-stu-id="9ed21-120">**Date**</span></span>|<span data-ttu-id="9ed21-121">Дата и время фиксации транзакции.</span><span class="sxs-lookup"><span data-stu-id="9ed21-121">Date and time of the transaction when it was committed.</span></span> <span data-ttu-id="9ed21-122">Дата и время транзакции отображаются, в соответствии с данными в таблице **msdbgmarkhistory** , а не с датой и временем на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="9ed21-122">Transaction date and time are displayed as recorded in the **msdbgmarkhistory** table, not in the client computer's date and time.</span></span>|  
    |<span data-ttu-id="9ed21-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="9ed21-123">**Description**</span></span>|<span data-ttu-id="9ed21-124">Описание помеченной транзакции, заданное пользователем при ее фиксации (при его наличии).</span><span class="sxs-lookup"><span data-stu-id="9ed21-124">Description of marked transaction specified by the user when the transaction was committed (if any).</span></span>|  
    |<span data-ttu-id="9ed21-125">**Номер LSN**</span><span class="sxs-lookup"><span data-stu-id="9ed21-125">**LSN**</span></span>|<span data-ttu-id="9ed21-126">Регистрационный номер помеченной транзакции в журнале.</span><span class="sxs-lookup"><span data-stu-id="9ed21-126">Log sequence number of the marked transaction.</span></span>|  
    |<span data-ttu-id="9ed21-127">**База данных**</span><span class="sxs-lookup"><span data-stu-id="9ed21-127">**Database**</span></span>|<span data-ttu-id="9ed21-128">Имя базы данных, в которой была зафиксирована помеченная транзакция.</span><span class="sxs-lookup"><span data-stu-id="9ed21-128">Name of the database where the marked transaction was committed.</span></span>|  
    |<span data-ttu-id="9ed21-129">**Имя пользователя**</span><span class="sxs-lookup"><span data-stu-id="9ed21-129">**User Name**</span></span>|<span data-ttu-id="9ed21-130">Имя пользователя базы данных, зафиксировавшего помеченную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="9ed21-130">Name of the database user who committed the marked transaction.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ed21-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="9ed21-131">See Also</span></span>  
 <span data-ttu-id="9ed21-132">[Восстановление резервной копии базы данных &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="9ed21-132">[Restore a Database Backup &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span></span>  
 [<span data-ttu-id="9ed21-133">Восстановление резервной копии журнала транзакций (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9ed21-133">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
  
