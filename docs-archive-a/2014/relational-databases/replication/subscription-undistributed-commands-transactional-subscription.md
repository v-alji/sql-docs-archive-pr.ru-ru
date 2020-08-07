---
title: Подписка, нераспространенные команды (подписка на публикацию транзакций, SQL Server 2005 и более поздних версий) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.subscription.performance.f1
ms.assetid: 5451561e-0ce3-4bb5-844a-88cd15b0b371
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6bbd82b4f4855c99076404d8b621edca11a7e1e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731505"
---
# <a name="subscription-undistributed-commands-transactional-subscription-sql-server-2005-and-later"></a><span data-ttu-id="961e9-102">Подписка, нераспространенные команды (подписка на публикацию транзакций, SQL Server 2005 и более поздние версии)</span><span class="sxs-lookup"><span data-stu-id="961e9-102">Subscription, Undistributed Commands (Transactional Subscription, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="961e9-103">На вкладке **Нераспространенные команды** отображаются сведения о количестве команд в базе данных распространителя, которые не были доставлены выбранному подписчику, и приблизительное время для доставки этих команд.</span><span class="sxs-lookup"><span data-stu-id="961e9-103">The **Undistributed Commands** tab displays information about the number of commands in the distribution database that have not been delivered to the selected Subscriber, and the estimated time to deliver those commands.</span></span> <span data-ttu-id="961e9-104">Дополнительные сведения о просмотре этих команд в базе данных распространителя см. в статье [sp_replshowcmds &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replshowcmds-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="961e9-104">For information about viewing the commands in the distribution database, see [sp_replshowcmds &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replshowcmds-transact-sql).</span></span>  
  
## <a name="options"></a><span data-ttu-id="961e9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="961e9-105">Options</span></span>  
 <span data-ttu-id="961e9-106">**Число команд в базе данных распространителя, которые ожидают применения к этому подписчику.**</span><span class="sxs-lookup"><span data-stu-id="961e9-106">**Number of commands in the distribution database waiting to be applied to this Subscriber**</span></span>  
 <span data-ttu-id="961e9-107">Количество команд в базе данных распространителя, которые не были доставлены выбранному подписчику.</span><span class="sxs-lookup"><span data-stu-id="961e9-107">The number of commands in the distribution database that have not been delivered to the selected Subscriber.</span></span> <span data-ttu-id="961e9-108">Команда состоит из одной инструкции языка обработки данных (DML) или одной инструкции языка определения данных (DDL) языка Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="961e9-108">A command consists of one Transact-SQL data manipulation language (DML) statement or one data definition language (DDL) statement.</span></span>  
  
 <span data-ttu-id="961e9-109">**Расчетное время применения этих команд, вычисленное по результатам предыдущего выполнения.**</span><span class="sxs-lookup"><span data-stu-id="961e9-109">**Estimated time to apply these commands, based on past performance**</span></span>  
 <span data-ttu-id="961e9-110">Примерное количество времени, необходимое для доставки команд на подписчик.</span><span class="sxs-lookup"><span data-stu-id="961e9-110">The estimated amount of time to deliver commands to the Subscriber.</span></span> <span data-ttu-id="961e9-111">Если это значение превышает количество времени, требуемое для создания и применения моментального снимка на подписчике, рассмотрите возможность повторной инициализации подписчика.</span><span class="sxs-lookup"><span data-stu-id="961e9-111">If this value is greater than the amount of time required to generate and apply a snapshot to the Subscriber, consider reinitializing the Subscriber.</span></span> <span data-ttu-id="961e9-112">Дополнительные сведения см. в статье [Повторная инициализация подписок](reinitialize-subscriptions.md).</span><span class="sxs-lookup"><span data-stu-id="961e9-112">For more information, see [Reinitialize Subscriptions](reinitialize-subscriptions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="961e9-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="961e9-113">See Also</span></span>  
 <span data-ttu-id="961e9-114">[Запуск монитора репликации](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="961e9-114">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="961e9-115">[Мониторинг производительности с помощью монитора репликации](monitor/monitor-performance-with-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="961e9-115">[Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) </span></span>  
 [<span data-ttu-id="961e9-116">Наблюдение за репликацией</span><span class="sxs-lookup"><span data-stu-id="961e9-116">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
