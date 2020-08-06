---
title: Занятие 3. Синхронизация подписки на публикацию слиянием | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: 49008384-2c55-4080-a890-9bceb40e4d6d
author: rothja
ms.author: jroth
ms.openlocfilehash: bf0256c69d69d1236869fa83285bf4dbf5c462da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739698"
---
# <a name="lesson-3-synchronizing-the-subscription-to-the-merge-publication"></a><span data-ttu-id="c2b9d-102">Занятие 3. Синхронизация подписки на публикацию слиянием</span><span class="sxs-lookup"><span data-stu-id="c2b9d-102">Lesson 3: Synchronizing the Subscription to the Merge Publication</span></span>
  <span data-ttu-id="c2b9d-103">На этом занятии будет запущен агент слияния для инициализации подписки с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2b9d-103">In this lesson, you will start the Merge Agent to initialize the subscription using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="c2b9d-104">Эта процедура также используется для синхронизации с издателем.</span><span class="sxs-lookup"><span data-stu-id="c2b9d-104">You also use this procedure to synchronize with the Publisher.</span></span> <span data-ttu-id="c2b9d-105">Приступать к этому занятию нужно только по завершении предыдущего: [Занятие 2. Создание подписки на публикацию слиянием](lesson-2-creating-a-subscription-to-the-merge-publication.md).</span><span class="sxs-lookup"><span data-stu-id="c2b9d-105">This lesson requires that you have completed the previous lesson, [Lesson 2: Creating a Subscription to the Merge Publication](lesson-2-creating-a-subscription-to-the-merge-publication.md).</span></span>  
  
### <a name="to-start-synchronization-and-initialize-the-subscription"></a><span data-ttu-id="c2b9d-106">Запуск синхронизации и инициализация подписки</span><span class="sxs-lookup"><span data-stu-id="c2b9d-106">To start synchronization and initialize the subscription</span></span>  
  
1.  <span data-ttu-id="c2b9d-107">Подключитесь к подписчику в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], раскройте узел сервера, а затем папку **Репликация** .</span><span class="sxs-lookup"><span data-stu-id="c2b9d-107">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="c2b9d-108">В папке **Локальные подписки** щелкните правой кнопкой мыши подписку в базе данных **SalesOrdersReplica** и выберите пункт **Просмотр состояния синхронизации**.</span><span class="sxs-lookup"><span data-stu-id="c2b9d-108">In the **Local Subscriptions** folder, right-click the subscription in the **SalesOrdersReplica** database, and then click **View Synchronization Status**.</span></span>  
  
3.  <span data-ttu-id="c2b9d-109">Нажмите кнопку **Пуск** , чтобы инициализировать подписку.</span><span class="sxs-lookup"><span data-stu-id="c2b9d-109">Click **Start** to initialize the subscription.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c2b9d-110">Next Steps</span><span class="sxs-lookup"><span data-stu-id="c2b9d-110">Next Steps</span></span>  
 <span data-ttu-id="c2b9d-111">Был запущен агент слияния для синхронизации и инициализации подписки.</span><span class="sxs-lookup"><span data-stu-id="c2b9d-111">You have successfully run the Merge Agent to start synchronization and initialize the subscription.</span></span> <span data-ttu-id="c2b9d-112">Можно вставить, обновить или удалить данные из таблицы **SalesOrderHeader** или **SalesOrderDetail** на стороне издателя или подписчика, повторить эту процедуру, когда доступно соединение сети, для синхронизации данных между издателем и подписчиком, после чего выполнить запросы к таблице **SalesOrderHeader** или **SalesOrderDetail** на другом сервере, чтобы просмотреть реплицированные изменения.</span><span class="sxs-lookup"><span data-stu-id="c2b9d-112">You can also insert, update, or delete data in the **SalesOrderHeader** or **SalesOrderDetail** tables at the Publisher or Subscriber, repeat this procedure when network connectivity is available to synchronize data between the Publisher and the Subscriber, and then query the **SalesOrderHeader** or **SalesOrderDetail** tables at the other server to view the replicated changes.</span></span>  
  
 <span data-ttu-id="c2b9d-113">На этом раздел «Репликация данных с мобильными клиентами» завершается.</span><span class="sxs-lookup"><span data-stu-id="c2b9d-113">This completes the Replicating Data with Mobile Clients tutorial.</span></span> <span data-ttu-id="c2b9d-114">Похожий учебник, использующий репликацию транзакций, см. в разделе [Tutorial: Replicating Data Between Continuously Connected Servers](tutorial-replicating-data-between-continuously-connected-servers.md).</span><span class="sxs-lookup"><span data-stu-id="c2b9d-114">For a similar tutorial that uses transactional replication, see [Tutorial: Replicating Data Between Continuously Connected Servers](tutorial-replicating-data-between-continuously-connected-servers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2b9d-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="c2b9d-115">See Also</span></span>  
 <span data-ttu-id="c2b9d-116">[Инициализация подписки с помощью моментального снимка](initialize-a-subscription-with-a-snapshot.md) </span><span class="sxs-lookup"><span data-stu-id="c2b9d-116">[Initialize a Subscription with a Snapshot](initialize-a-subscription-with-a-snapshot.md) </span></span>  
 <span data-ttu-id="c2b9d-117">[Синхронизация данных](synchronize-data.md) </span><span class="sxs-lookup"><span data-stu-id="c2b9d-117">[Synchronize Data](synchronize-data.md) </span></span>  
 [<span data-ttu-id="c2b9d-118">Синхронизация подписки по запросу</span><span class="sxs-lookup"><span data-stu-id="c2b9d-118">Synchronize a Pull Subscription</span></span>](synchronize-a-pull-subscription.md)  
  
  
