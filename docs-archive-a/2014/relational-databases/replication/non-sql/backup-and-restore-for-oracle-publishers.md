---
title: Резервное копирование и восстановление для издателей Oracle | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- recovery [SQL Server replication], Oracle publishing
- backups [SQL Server replication], Oracle publishing
- Oracle publishing [SQL Server replication], backup and restore
- restoring [SQL Server replication], Oracle publishing
ms.assetid: e5f181d0-cacf-442b-8b7a-202b3cfc358b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e6b994c34e4f4bebc010fe6d71bbd43f6e557cbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655068"
---
# <a name="backup-and-restore-for-oracle-publishers"></a><span data-ttu-id="8b3fc-102">Резервное копирование и восстановление для издателей Oracle</span><span class="sxs-lookup"><span data-stu-id="8b3fc-102">Backup and Restore for Oracle Publishers</span></span>
  <span data-ttu-id="8b3fc-103">При резервном копировании и восстановлении соблюдайте следующие рекомендации:</span><span class="sxs-lookup"><span data-stu-id="8b3fc-103">Follow these guidelines when backing up and restoring:</span></span>  
  
-   <span data-ttu-id="8b3fc-104">Убедитесь в том, что при резервном копировании издателя не запущен агент чтения журнала, а также в отсутствии любой активности в опубликованных таблицах баз данных.</span><span class="sxs-lookup"><span data-stu-id="8b3fc-104">Ensure the Log Reader Agent does not run and that other database activity on the published tables does not occur while the Publisher is being backed up.</span></span>  
  
-   <span data-ttu-id="8b3fc-105">Производите резервное копирование издателя и распространителя одновременно.</span><span class="sxs-lookup"><span data-stu-id="8b3fc-105">Backup up the Publisher and Distributor at the same time.</span></span>  
  
-   <span data-ttu-id="8b3fc-106">Если издатель или распространитель подлежат восстановлению, то повторно инициализируйте все подписки.</span><span class="sxs-lookup"><span data-stu-id="8b3fc-106">If the Publisher or Distributor must be restored, reinitialize all subscriptions.</span></span>  
  
-   <span data-ttu-id="8b3fc-107">Чтобы восстановить подписчика из резервной копии (без необходимости повторной инициализации подписки), должны быть сохранены транзакции, доставленные в базу данных подписки после последнего завершенного резервного копирования этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="8b3fc-107">To restore a Subscriber from a backup (without having to reinitialize subscriptions), the transactions delivered to the distribution database after the last subscription database backup was completed must still be available.</span></span> <span data-ttu-id="8b3fc-108">Отрезок времени, в течение которого транзакции все еще доступны, зависит от установок хранения распространения.</span><span class="sxs-lookup"><span data-stu-id="8b3fc-108">The length of time transactions are available depends on distribution retention settings.</span></span> <span data-ttu-id="8b3fc-109">Сведения об этих настройках см. в статье [Окончание срока действия и отключение подписки](../subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="8b3fc-109">For information on these settings, see [Subscription Expiration and Deactivation](../subscription-expiration-and-deactivation.md).</span></span>  
  
-   <span data-ttu-id="8b3fc-110">Если издатель или распространитель становятся несинхронизированными в результате восстановления базы данных, агент репликации производит в журнал записи об ошибке.</span><span class="sxs-lookup"><span data-stu-id="8b3fc-110">If the Publisher or Distributor becomes out of sync as the result of a database restore, the replication agents log error messages.</span></span> <span data-ttu-id="8b3fc-111">В этом случае следует удалить и повторно создать все соответствующие публикации и подписки:</span><span class="sxs-lookup"><span data-stu-id="8b3fc-111">At this point, you must drop and recreate all relevant publications and subscriptions:</span></span>  
  
    1.  <span data-ttu-id="8b3fc-112">Напишите скрипт определений публикаций и подписок.</span><span class="sxs-lookup"><span data-stu-id="8b3fc-112">Script the definition of the publications and subscriptions.</span></span> <span data-ttu-id="8b3fc-113">Дополнительные сведения см. в разделе [Scripting Replication](../scripting-replication.md).</span><span class="sxs-lookup"><span data-stu-id="8b3fc-113">For more information, see [Scripting Replication](../scripting-replication.md).</span></span>  
  
         <span data-ttu-id="8b3fc-114">Если определение публикации изменило версию состояния издателя и распространителя, потребуется изменить скрипты.</span><span class="sxs-lookup"><span data-stu-id="8b3fc-114">If the definition of the publications has changed between the versions of the Publisher and Distributor states, you will need to modify the scripts.</span></span>  
  
    2.  <span data-ttu-id="8b3fc-115">Удалите публикации и подписки.</span><span class="sxs-lookup"><span data-stu-id="8b3fc-115">Drop the publications and subscriptions.</span></span>  
  
    3.  <span data-ttu-id="8b3fc-116">Выполните скрипты, созданные на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="8b3fc-116">Run the scripts created in step 1.</span></span>  
  
     <span data-ttu-id="8b3fc-117">Если издатель должен быть удален и перенастроен заново, удалите открытый синоним **MSSQLSERVERDISTRIBUTOR** и пользователя настроенной репликации Oracle с помощью параметра **CASCADE** для удаления всех объектов репликации из издателя Oracle.</span><span class="sxs-lookup"><span data-stu-id="8b3fc-117">If the Publisher must be dropped and reconfigured, drop the **MSSQLSERVERDISTRIBUTOR** public synonym and the configured Oracle replication user with the **CASCADE** option to remove all replication objects from the Oracle Publisher.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b3fc-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="8b3fc-118">See Also</span></span>  
 <span data-ttu-id="8b3fc-119">[Создание резервной копии и восстановление из копий реплицируемых баз данных](../administration/back-up-and-restore-replicated-databases.md) </span><span class="sxs-lookup"><span data-stu-id="8b3fc-119">[Back Up and Restore Replicated Databases](../administration/back-up-and-restore-replicated-databases.md) </span></span>  
 <span data-ttu-id="8b3fc-120">[Настройка издателя Oracle](configure-an-oracle-publisher.md) </span><span class="sxs-lookup"><span data-stu-id="8b3fc-120">[Configure an Oracle Publisher](configure-an-oracle-publisher.md) </span></span>  
 [<span data-ttu-id="8b3fc-121">Обзор публикации Oracle</span><span class="sxs-lookup"><span data-stu-id="8b3fc-121">Oracle Publishing Overview</span></span>](oracle-publishing-overview.md)  
  
  
