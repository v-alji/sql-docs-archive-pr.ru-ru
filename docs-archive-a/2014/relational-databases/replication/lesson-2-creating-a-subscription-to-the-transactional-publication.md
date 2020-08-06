---
title: Занятие 2. Создание подписки на публикацию транзакций | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: 5995b7d2-7c06-46f5-b96c-2bee879bcda2
author: rothja
ms.author: jroth
ms.openlocfilehash: dbf40fa259302dffdd6c0b8e8717b7c35b0cf92d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655579"
---
# <a name="lesson-2-creating-a-subscription-to-the-transactional-publication"></a><span data-ttu-id="d803b-102">Занятие 2. Создание подписки на публикацию транзакций</span><span class="sxs-lookup"><span data-stu-id="d803b-102">Lesson 2: Creating a Subscription to the Transactional Publication</span></span>
  <span data-ttu-id="d803b-103">На этом занятии с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]будет создана подписка.</span><span class="sxs-lookup"><span data-stu-id="d803b-103">In this lesson, you will create a subscription using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="d803b-104">Приступать к этому занятию нужно только по завершении предыдущего: [Занятие 1. Публикация данных с помощью репликации транзакций](lesson-1-publishing-data-using-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="d803b-104">This lesson requires that you have completed the previous lesson, [Lesson 1: Publishing Data Using Transactional Replication](lesson-1-publishing-data-using-transactional-replication.md).</span></span>  
  
### <a name="to-create-the-subscription"></a><span data-ttu-id="d803b-105">Создание подписки</span><span class="sxs-lookup"><span data-stu-id="d803b-105">To create the subscription</span></span>  
  
1.  <span data-ttu-id="d803b-106">Подключитесь к издателю в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], а затем раскройте узел сервера и папку **Репликация** .</span><span class="sxs-lookup"><span data-stu-id="d803b-106">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="d803b-107">В папке **Локальные публикации** щелкните правой кнопкой мыши публикацию **AdvWorksProductTrans** и выберите команду **Создать подписку**.</span><span class="sxs-lookup"><span data-stu-id="d803b-107">In the **Local Publications** folder, right-click the **AdvWorksProductTrans** publication, and then click **New Subscriptions**.</span></span>  
  
     <span data-ttu-id="d803b-108">Откроется мастер создания подписки.</span><span class="sxs-lookup"><span data-stu-id="d803b-108">The New Subscription Wizard launches.</span></span>  
  
3.  <span data-ttu-id="d803b-109">На странице «Публикация» выберите публикацию **AdvWorksProductTrans**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d803b-109">On the Publication page, select **AdvWorksProductTrans**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="d803b-110">На странице «Расположение агента распространителя» установите флажок **Выполнять все агенты на распространителе**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d803b-110">On the Distribution Agent Location page, select **Run all agents at the Distributor**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="d803b-111">Если имя экземпляра подписчика не отображается, на странице «Подписчики» нажмите кнопку **Добавить подписчик**, выберите **Добавить подписчик SQL Server**, в диалоговом окне **Соединение с сервером** введите имя экземпляра подписчика, затем нажмите кнопку **Соединить**.</span><span class="sxs-lookup"><span data-stu-id="d803b-111">On the Subscribers page, if the name of the Subscriber instance is not displayed, click **Add Subscriber**, click **Add SQL Server Subscriber**, enter the Subscriber instance name in the **Connect to Server** dialog box, and then click **Connect**.</span></span>  
  
6.  <span data-ttu-id="d803b-112">На странице Подписчики выберите имя экземпляра сервера подписчика и выберите **\<New Database>** в разделе **база данных подписки**.</span><span class="sxs-lookup"><span data-stu-id="d803b-112">On the Subscribers page, select the instance name of the Subscriber server, and select **\<New Database>** under **Subscription Database**.</span></span>  
  
7.  <span data-ttu-id="d803b-113">В диалоговом окне **Создание базы данных** в поле **Имя базы данных** введите **ProductReplica** , нажмите кнопку **ОК**, затем **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d803b-113">On the **New Database** dialog box, enter **ProductReplica** in the **Database name** box, click **OK**, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="d803b-114">В диалоговом окне **безопасность агент распространения** нажмите кнопку с многоточием (**...**), введите \<_Machine_Name> _**\ Repl_distribution** в поле **учетная запись процесса** , введите пароль для этой учетной записи, нажмите кнопку **ОК**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d803b-114">In the **Distribution Agent Security** dialog box, click the ellipsis (**...**) button, enter \<_Machine_Name>_**\repl_distribution** in the **Process account** box, enter the password for this account, click **OK**, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="d803b-115">Нажмите кнопку **Готово** , чтобы принять значения по умолчанию на оставшихся страницах и завершить работу мастера.</span><span class="sxs-lookup"><span data-stu-id="d803b-115">Click **Finish** to accept the default values on the remaining pages and complete the wizard.</span></span>  
  
### <a name="setting-database-permissions-at-the-subscriber"></a><span data-ttu-id="d803b-116">Установка разрешений базы данных на подписчике</span><span class="sxs-lookup"><span data-stu-id="d803b-116">Setting database permissions at the Subscriber</span></span>  
  
1.  <span data-ttu-id="d803b-117">Подключитесь к подписчику в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], последовательно разверните узлы **Базы данных**, **ProductReplica**и **Безопасность**, щелкните правой кнопкой мыши элемент **Пользователи**и выберите пункт **Создать пользователя**.</span><span class="sxs-lookup"><span data-stu-id="d803b-117">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand **Databases**, **ProductReplica**, and **Security**, right-click **Users**, and then select **New User**.</span></span>  
  
2.  <span data-ttu-id="d803b-118">На странице **Общие** в списке **Тип пользователя** выберите **Пользователь Windows**.</span><span class="sxs-lookup"><span data-stu-id="d803b-118">On the **General** page, in the **User type** list, select **Windows user**.</span></span>  
  
3.  <span data-ttu-id="d803b-119">Выберите поле **имя пользователя** и нажмите кнопку с многоточием (...) в поле **введите имя объекта для выбора** введите <Machine_Name>**\ repl_distribution**, щелкните **Проверить имена**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d803b-119">Select the **User name** box and click the ellipsis (...) button, in the **Enter the object name to select** box type <Machine_Name>**\repl_distribution**, click **Check Names**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="d803b-120">Чтобы создать пользователя, на странице **Членство** в поле **Членство в роли базы данных** выберите **db_owner**и нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="d803b-120">On the **Membership** page, in **Database role membership** area, select **db_owner**, and then click **OK** to create the user.</span></span>  
  
### <a name="to-view-the-synchronization-status-of-the-subscription"></a><span data-ttu-id="d803b-121">Просмотр состояния синхронизации подписки</span><span class="sxs-lookup"><span data-stu-id="d803b-121">To view the synchronization status of the subscription</span></span>  
  
1.  <span data-ttu-id="d803b-122">Подключитесь к издателю в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], а затем раскройте узел сервера и папку **Репликация** .</span><span class="sxs-lookup"><span data-stu-id="d803b-122">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="d803b-123">В папке **Локальные публикации** разверните публикацию **AdvWorksProductTrans** , щелкните правой кнопкой мыши подписку в базе данных **ProductReplica** и выберите пункт **Просмотр состояния синхронизации**.</span><span class="sxs-lookup"><span data-stu-id="d803b-123">In the **Local Publications** folder, expand the **AdvWorksProductTrans** publication, right-click the subscription in the **ProductReplica** database, and then click **View Synchronization Status**.</span></span>  
  
     <span data-ttu-id="d803b-124">Отобразится текущее состояние синхронизации подписки.</span><span class="sxs-lookup"><span data-stu-id="d803b-124">The current synchronization status of the subscription is displayed.</span></span>  
  
3.  <span data-ttu-id="d803b-125">Если подписка не отображается под публикацией **AdvWorksProductTrans**, нажмите клавишу F5 для обновления списка.</span><span class="sxs-lookup"><span data-stu-id="d803b-125">If the subscription is not visible under **AdvWorksProductTrans**, press F5 to refresh the list.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d803b-126">Next Steps</span><span class="sxs-lookup"><span data-stu-id="d803b-126">Next Steps</span></span>  
 <span data-ttu-id="d803b-127">Создание подписки на публикацию транзакций успешно завершено.</span><span class="sxs-lookup"><span data-stu-id="d803b-127">You have successfully created a subscription to the transactional publication.</span></span> <span data-ttu-id="d803b-128">Ввиду того, что агент распространителя для этой подписки постоянно запущен, подписка инициализируется при создании.</span><span class="sxs-lookup"><span data-stu-id="d803b-128">Because the Distribution Agent for this subscription runs continuously, the subscription is initialized when it is created.</span></span> <span data-ttu-id="d803b-129">Далее необходимо использовать трассировочные токены, чтобы проверить выполнение репликации изменений и определить задержку.</span><span class="sxs-lookup"><span data-stu-id="d803b-129">Next, you will use tracer tokens to verify that changes are being replicated to the Subscriber and to determine latency.</span></span> <span data-ttu-id="d803b-130">См. раздел [Lesson 3: Validating the Subscription and Measuring Latency](lesson-3-validating-the-subscription-and-measuring-latency.md).</span><span class="sxs-lookup"><span data-stu-id="d803b-130">See [Lesson 3: Validating the Subscription and Measuring Latency](lesson-3-validating-the-subscription-and-measuring-latency.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d803b-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="d803b-131">See Also</span></span>  
 <span data-ttu-id="d803b-132">[Инициализация подписки с помощью моментального снимка](initialize-a-subscription-with-a-snapshot.md) </span><span class="sxs-lookup"><span data-stu-id="d803b-132">[Initialize a Subscription with a Snapshot](initialize-a-subscription-with-a-snapshot.md) </span></span>  
 <span data-ttu-id="d803b-133">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="d803b-133">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 [<span data-ttu-id="d803b-134">Подписка на публикации</span><span class="sxs-lookup"><span data-stu-id="d803b-134">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
