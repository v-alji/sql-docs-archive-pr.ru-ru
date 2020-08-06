---
title: Занятие 2. Создание подписки на публикацию слиянием | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: 06722baa-9065-443e-b1d5-99036cf89074
author: rothja
ms.author: jroth
ms.openlocfilehash: 2ca4f9cdf9c40d80b428d65b4201be61c2ea3eae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665290"
---
# <a name="lesson-2-creating-a-subscription-to-the-merge-publication"></a><span data-ttu-id="ce646-102">Занятие 2. Создание подписки на публикацию слиянием</span><span class="sxs-lookup"><span data-stu-id="ce646-102">Lesson 2: Creating a Subscription to the Merge Publication</span></span>
  <span data-ttu-id="ce646-103">На этом занятии будет создана подписка с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce646-103">In this lesson, you will create the subscription using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="ce646-104">Затем будут установлены разрешения на базу данных подписки и вручную будет сформирован моментальный снимок отфильтрованных данных для новой подписки.</span><span class="sxs-lookup"><span data-stu-id="ce646-104">You will then set permissions on the subscription database and manually generate the filtered data snapshot for the new subscription.</span></span> <span data-ttu-id="ce646-105">Приступать к этому занятию нужно только по завершении предыдущего: [Занятие 1. Публикация данных с помощью репликации слиянием](lesson-1-publishing-data-using-merge-replication.md).</span><span class="sxs-lookup"><span data-stu-id="ce646-105">This lesson requires that you have completed the previous lesson, [Lesson 1: Publishing Data Using Merge Replication](lesson-1-publishing-data-using-merge-replication.md).</span></span>  
  
### <a name="to-create-the-subscription"></a><span data-ttu-id="ce646-106">Создание подписки</span><span class="sxs-lookup"><span data-stu-id="ce646-106">To create the subscription</span></span>  
  
1.  <span data-ttu-id="ce646-107">Подключитесь к подписчику в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], разверните узел сервера и папку **Репликация** , щелкните правой кнопкой мыши папку **Локальные подписки** и выберите пункт **Создать подписку**.</span><span class="sxs-lookup"><span data-stu-id="ce646-107">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, expand the **Replication** folder, right-click the **Local Subscriptions** folder, and then click **New Subscriptions**.</span></span>  
  
     <span data-ttu-id="ce646-108">Откроется мастер создания подписки.</span><span class="sxs-lookup"><span data-stu-id="ce646-108">The New Subscription Wizard launches.</span></span>  
  
2.  <span data-ttu-id="ce646-109">На странице **Публикация** из списка **Издатель** выберите **Найти издатель SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="ce646-109">On the **Publication** page, click **Find SQL Server Publisher** in the **Publisher** list.</span></span>  
  
3.  <span data-ttu-id="ce646-110">В диалоговом окне **Соединение с сервером** введите имя экземпляра издателя в поле **Имя сервера** , а затем щелкните **Подключиться**.</span><span class="sxs-lookup"><span data-stu-id="ce646-110">In the **Connect to Server** dialog box, enter the name of the Publisher instance in the **Server name** box, and click **Connect**.</span></span>  
  
4.  <span data-ttu-id="ce646-111">Щелкните элемент **AdvWorksSalesOrdersMerge**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ce646-111">Click **AdvWorksSalesOrdersMerge**, and click **Next**.</span></span>  
  
5.  <span data-ttu-id="ce646-112">На странице "Расположение агента слияния" щелкните **Выполнять каждый агент на своем подписчике**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ce646-112">On the Merge Agent Location page, click **Run each agent at its Subscriber**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="ce646-113">На странице "Подписчики" выберите имя экземпляра сервера подписчика и в списке **База данных подписки**выберите **\<New Database>** .</span><span class="sxs-lookup"><span data-stu-id="ce646-113">On the Subscribers page, select the instance name of the Subscriber server, and under **Subscription Database**, select **\<New Database>** from the list.</span></span>  
  
7.  <span data-ttu-id="ce646-114">В диалоговом окне **Новая база данных** в поле **Имя базы данных** введите **SalesOrdersReplica** , нажмите кнопку **ОК**, а затем кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ce646-114">In the **New Database** dialog box, enter **SalesOrdersReplica** in the **Database name** box, click **OK**, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="ce646-115">На странице Безопасность агент слияния нажмите кнопку с многоточием (**...**), введите \<_Machine_Name> _**\ repl_merge** в поле **учетная запись процесса** , укажите пароль для этой учетной записи, нажмите **кнопку ОК**, нажмите кнопку **Далее**, а затем кнопку **Далее** еще раз.</span><span class="sxs-lookup"><span data-stu-id="ce646-115">On the Merge Agent Security page, click the ellipsis (**...**) button, enter \<_Machine_Name>_**\repl_merge** in the **Process account** box, supply the password for this account, click **OK**, click **Next**, and then click **Next** again.</span></span>  
  
9. <span data-ttu-id="ce646-116">На странице "Инициализация подписок" выберите из списка **Инициализировать, когда** пункт **При первой синхронизации** , нажмите кнопку **Далее**, а затем снова кнопку **Далее** .</span><span class="sxs-lookup"><span data-stu-id="ce646-116">On the Initialize Subscriptions page, select **At first synchronization** from the **Initialize When** list, click **Next**, and then click **Next** again.</span></span>  
  
10. <span data-ttu-id="ce646-117">На странице значения HOST_NAME введите значение `adventure-works\pamela0` в поле **HOST_NAME значение** и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="ce646-117">On the HOST_NAME Values page, enter a value of `adventure-works\pamela0` in the **HOST_NAME Value** box, and then click **Finish**.</span></span>  
  
11. <span data-ttu-id="ce646-118">Нажмите снова кнопку **Готово** и после создания подписки нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="ce646-118">Click **Finish** again, and after the subscription is created, click **Close**.</span></span>  
  
### <a name="setting-database-permissions-at-the-subscriber"></a><span data-ttu-id="ce646-119">Установка разрешений базы данных на подписчике</span><span class="sxs-lookup"><span data-stu-id="ce646-119">Setting database permissions at the Subscriber</span></span>  
  
1.  <span data-ttu-id="ce646-120">Подключитесь к подписчику в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], разверните узлы **Базы данных**, **SalesOrdersReplica**и **Безопасность**, щелкните правой кнопкой мыши элемент **Пользователи**и выберите пункт **Новый пользователь**.</span><span class="sxs-lookup"><span data-stu-id="ce646-120">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand **Databases**, **SalesOrdersReplica**, and **Security**, right-click **Users**, and then select **New User**.</span></span>  
  
2.  <span data-ttu-id="ce646-121">На странице **Общие** введите \<_Machine_Name> _ **\ repl_merge** в поле **имя пользователя** нажмите кнопку с многоточием (**...**), нажмите кнопку **Обзор**, \<_Machine_Name> выберите _ **\ repl_merge**, нажмите кнопку **ОК**, щелкните **Проверить имена**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ce646-121">On the **General** page, enter \<_Machine_Name>_**\repl_merge** in the **User name** box, click the ellipsis (**...**) button, click **Browse**, select \<_Machine_Name>_**\repl_merge**, click **OK**, click **Check Names**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="ce646-122">Чтобы создать пользователя, в поле **Членство в роли базы данных**выберите **db_owner**и нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="ce646-122">In **Database role membership**, select **db_owner**, and then click **OK** to create the user.</span></span>  
  
### <a name="to-create-the-filtered-data-snapshot-for-the-subscription"></a><span data-ttu-id="ce646-123">Создание моментального снимка отфильтрованных данных подписки</span><span class="sxs-lookup"><span data-stu-id="ce646-123">To create the filtered data snapshot for the subscription</span></span>  
  
1.  <span data-ttu-id="ce646-124">Подключитесь к издателю в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], а затем раскройте узел сервера и папку **Репликация** .</span><span class="sxs-lookup"><span data-stu-id="ce646-124">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="ce646-125">В папке **Локальные публикации** щелкните правой кнопкой мыши публикацию **AdvWorksSalesOrdersMerge** и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="ce646-125">In the **Local Publications** folder, right-click the **AdvWorksSalesOrdersMerge** publication, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="ce646-126">Откроется диалоговое окно **Свойства публикации** .</span><span class="sxs-lookup"><span data-stu-id="ce646-126">The **Publication Properties** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="ce646-127">Выберите страницу **Секции данных** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="ce646-127">Select the **Data Partitions** page, and click **Add**.</span></span>  
  
4.  <span data-ttu-id="ce646-128">В диалоговом окне **Добавление секции данных** введите `adventure-works\pamela0` в поле **HOST_NAME значение** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ce646-128">In the **Add Data Partition** dialog box, type `adventure-works\pamela0` in the **HOST_NAME Value** box, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="ce646-129">Выберите добавленную секцию, щелкните **Создать выбранные моментальные снимки**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ce646-129">Select the newly added partition, click **Generate the selected snapshots now**, and then click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ce646-130">Next Steps</span><span class="sxs-lookup"><span data-stu-id="ce646-130">Next Steps</span></span>  
 <span data-ttu-id="ce646-131">Подписка на публикацию слиянием создана успешно, и сформирован отфильтрованный моментальный снимок секций данных новой подписки, так что снимок будет доступен при инициализации подписки.</span><span class="sxs-lookup"><span data-stu-id="ce646-131">You have successfully created a subscription to the merge publication and generated the filtered snapshot for the new subscription's data partition so that it will be available when the subscription is initialized.</span></span> <span data-ttu-id="ce646-132">Далее предстоит предоставить права агенту слияния на базу данных подписки и запустить агент слияния, чтобы приступить к синхронизации и инициализировать подписку.</span><span class="sxs-lookup"><span data-stu-id="ce646-132">Next, you will grant rights to the Merge Agent on the subscription database and run the Merge Agent to start synchronization and initialize the subscription.</span></span> <span data-ttu-id="ce646-133">См. [Занятие 3. Синхронизация подписки на публикацию слиянием](lesson-3-synchronizing-the-subscription-to-the-merge-publication.md).</span><span class="sxs-lookup"><span data-stu-id="ce646-133">See [Lesson 3: Synchronizing the Subscription to the Merge Publication](lesson-3-synchronizing-the-subscription-to-the-merge-publication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce646-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="ce646-134">See Also</span></span>  
 <span data-ttu-id="ce646-135">[Subscribe to Publications](subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="ce646-135">[Subscribe to Publications](subscribe-to-publications.md) </span></span>  
 <span data-ttu-id="ce646-136">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="ce646-136">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 [<span data-ttu-id="ce646-137">Snapshots for Merge Publications with Parameterized Filters</span><span class="sxs-lookup"><span data-stu-id="ce646-137">Snapshots for Merge Publications with Parameterized Filters</span></span>](snapshots-for-merge-publications-with-parameterized-filters.md)  
  
  
