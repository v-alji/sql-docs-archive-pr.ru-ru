---
title: Занятие 3. Проверка подписки и измерение задержки | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: 147f7b93-1804-4e0b-9e17-57a51d035b2a
author: rothja
ms.author: jroth
ms.openlocfilehash: e4893c054d25d131eb2f88f32291606b0b789af7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739695"
---
# <a name="lesson-3-validating-the-subscription-and-measuring-latency"></a><span data-ttu-id="fbc4c-102">Занятие 3. Проверка подписки и измерение задержки</span><span class="sxs-lookup"><span data-stu-id="fbc4c-102">Lesson 3: Validating the Subscription and Measuring Latency</span></span>
  <span data-ttu-id="fbc4c-103">На этом занятии изучаются трассировочные токены для проверки реплицируемых для подписчика изменений и определения задержки, т.е. времени, когда изменение, внесенное на стороне издателя, должно перейти на сторону подписчика.</span><span class="sxs-lookup"><span data-stu-id="fbc4c-103">In this lesson, you will use tracer tokens to verify that changes are being replicated to the Subscriber and to determine latency, the time it takes for a change made at the Publisher to appear to the Subscriber.</span></span> <span data-ttu-id="fbc4c-104">Приступать к этому занятию нужно только по завершении предыдущего: [Занятие 2. Создание подписки на публикацию транзакций](lesson-2-creating-a-subscription-to-the-transactional-publication.md).</span><span class="sxs-lookup"><span data-stu-id="fbc4c-104">This lesson requires that you have completed the previous lesson, [Lesson 2: Creating a Subscription to the Transactional Publication](lesson-2-creating-a-subscription-to-the-transactional-publication.md).</span></span>  
  
### <a name="to-insert-a-tracer-token-and-view-information-on-the-token"></a><span data-ttu-id="fbc4c-105">Вставка трассировочного токена и просмотр сведений о токене</span><span class="sxs-lookup"><span data-stu-id="fbc4c-105">To insert a tracer token and view information on the token</span></span>  
  
1.  <span data-ttu-id="fbc4c-106">Подключитесь к издателю в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], разверните узел сервера, щелкните правой кнопкой мыши папку **Репликация** и выберите пункт **Запустить монитор репликации**.</span><span class="sxs-lookup"><span data-stu-id="fbc4c-106">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, right-click the **Replication** folder, and then click **Launch Replication Monitor**.</span></span>  
  
     <span data-ttu-id="fbc4c-107">Запустится монитор репликации.</span><span class="sxs-lookup"><span data-stu-id="fbc4c-107">Replication Monitor launches.</span></span>  
  
2.  <span data-ttu-id="fbc4c-108">Раскройте группу издателей на левой панели, затем экземпляр издателя и выберите публикацию **AdvWorksProductTrans** .</span><span class="sxs-lookup"><span data-stu-id="fbc4c-108">Expand a Publisher group in the left pane, expand the Publisher instance, and then click the **AdvWorksProductTrans** publication.</span></span>  
  
3.  <span data-ttu-id="fbc4c-109">Щелкните вкладку **Трассировочные токены** .</span><span class="sxs-lookup"><span data-stu-id="fbc4c-109">Click the **Tracer Tokens** tab.</span></span>  
  
4.  <span data-ttu-id="fbc4c-110">Выберите команду **Вставить трассировочный маркер**.</span><span class="sxs-lookup"><span data-stu-id="fbc4c-110">Click **Insert Tracer**.</span></span>  
  
5.  <span data-ttu-id="fbc4c-111">Просмотрите затраченное время для трассировочного маркера в следующих столбцах: **От издателя к распространителю**, **От распространителя к подписчику**, **Общая задержка**.</span><span class="sxs-lookup"><span data-stu-id="fbc4c-111">View elapsed time for the tracer token in the following columns: **Publisher to Distributor**, **Distributor to Subscriber**, **Total Latency**.</span></span> <span data-ttu-id="fbc4c-112">Значение **Pending** указывает, что маркер не достиг данной точки.</span><span class="sxs-lookup"><span data-stu-id="fbc4c-112">A value of **Pending** indicates that the token has not reached a given point.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="fbc4c-113">Next Steps</span><span class="sxs-lookup"><span data-stu-id="fbc4c-113">Next Steps</span></span>  
 <span data-ttu-id="fbc4c-114">На этом занятии показывается, как использовать трассировочные токены для проверки изменений, реплицируемых от издателя подписчику.</span><span class="sxs-lookup"><span data-stu-id="fbc4c-114">In this lesson, you successfully used tracer tokens to validate that data changes are being replicated from the Publisher to the Subscriber.</span></span> <span data-ttu-id="fbc4c-115">Кроме того, показывается, как вставлять, обновлять и удалять данные из таблицы **Product** на стороне издателя и строить запрос к таблице **Product** на стороне подписчика для проверки изменений после репликации.</span><span class="sxs-lookup"><span data-stu-id="fbc4c-115">You can also insert, update, or delete data in the **Product** table at the Publisher and query the **Product** table at the Subscriber to view these changes after they are replicated.</span></span>  
  
 <span data-ttu-id="fbc4c-116">На этом учебник «Репликация данных между постоянно соединенными серверами» завершается.</span><span class="sxs-lookup"><span data-stu-id="fbc4c-116">This completes the Replicating Data Between Continuously Connected Servers tutorial.</span></span> <span data-ttu-id="fbc4c-117">Похожий учебник, использующий репликацию слиянием, см. в разделе [Tutorial: Replicating Data with Mobile Clients](tutorial-replicating-data-with-mobile-clients.md).</span><span class="sxs-lookup"><span data-stu-id="fbc4c-117">For a similar tutorial that uses merge replication, see [Tutorial: Replicating Data with Mobile Clients](tutorial-replicating-data-with-mobile-clients.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbc4c-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="fbc4c-118">See Also</span></span>  
 [<span data-ttu-id="fbc4c-119">Измерение задержки и проверка правильности соединений для репликации транзакций</span><span class="sxs-lookup"><span data-stu-id="fbc4c-119">Measure Latency and Validate Connections for Transactional Replication</span></span>](monitor/measure-latency-and-validate-connections-for-transactional-replication.md)  
  
  
