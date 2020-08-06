---
title: Урок 1. Публикация данных с помощью репликации транзакций | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: 9c55aa3c-4664-41fc-943f-e817c31aad5e
author: rothja
ms.author: jroth
ms.openlocfilehash: ce20f4ed8863ede34c8709d2b77bf032e7d14a97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729353"
---
# <a name="lesson-1-publishing-data-using-transactional-replication"></a><span data-ttu-id="8551f-102">Урок 1. Публикация данных с помощью репликации транзакций</span><span class="sxs-lookup"><span data-stu-id="8551f-102">Lesson 1: Publishing Data Using Transactional Replication</span></span>
  <span data-ttu-id="8551f-103"> На этом занятии с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] создается публикация транзакций с целью публикации фильтрованного подмножества таблицы **Product** из образца базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8551f-103">In this lesson, you will create a transactional publication using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to publish a filtered subset of the **Product** table in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="8551f-104">Также в список доступа к публикации (PAL) добавляется имя входа SQL Server, используемое агентом распространителя.</span><span class="sxs-lookup"><span data-stu-id="8551f-104">You will also add the SQL Server login used by the Distribution Agent to the publication access list (PAL).</span></span> <span data-ttu-id="8551f-105">Перед началом работы с этим учебником необходимо завершить работу с предыдущим учебником, [Подготовка сервера к репликации](tutorial-preparing-the-server-for-replication.md).</span><span class="sxs-lookup"><span data-stu-id="8551f-105">Before starting this tutorial, you should have completed the previous tutorial, [Preparing the Server for Replication](tutorial-preparing-the-server-for-replication.md).</span></span>  
  
### <a name="to-create-a-publication-and-define-articles"></a><span data-ttu-id="8551f-106">Создание публикации и определение статей</span><span class="sxs-lookup"><span data-stu-id="8551f-106">To create a publication and define articles</span></span>  
  
1.  <span data-ttu-id="8551f-107">Подключитесь к издателю в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], а затем раскройте узел сервера.</span><span class="sxs-lookup"><span data-stu-id="8551f-107">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="8551f-108">Разверните папку **Репликация** , щелкните правой кнопкой мыши папку **Локальные публикации** и выберите пункт **Создать публикацию**.</span><span class="sxs-lookup"><span data-stu-id="8551f-108">Expand the **Replication** folder, right-click the **Local Publications** folder, and click **New Publication**.</span></span>  
  
     <span data-ttu-id="8551f-109">Будет запущен мастер настройки публикации.</span><span class="sxs-lookup"><span data-stu-id="8551f-109">The Publication Configuration Wizard launches.</span></span>  
  
3.  <span data-ttu-id="8551f-110">На странице «База данных публикации» выберите [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8551f-110">On the Publication Database page, select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="8551f-111">На странице «Тип публикации» выберите **Публикация транзакций**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8551f-111">On the Publication Type page, select **Transactional publication**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="8551f-112">На странице "Статьи" разверните узел **Таблицы** , установите флажок **Product** , затем разверните **Product** и снимите флажки **ListPrice** и **StandardCost** .</span><span class="sxs-lookup"><span data-stu-id="8551f-112">On the Articles page, expand the **Tables** node, select the **Product** check box, then expand **Product** and clear the **ListPrice** and **StandardCost** check boxes.</span></span> <span data-ttu-id="8551f-113">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8551f-113">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="8551f-114">На странице «Фильтр строк таблицы» нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="8551f-114">On the Filter Table Rows page, click **Add**.</span></span>  
  
7.  <span data-ttu-id="8551f-115">В диалоговом окне **Добавление фильтра** щелкните столбец **SafetyStockLevel** , щелкните стрелку вправо, чтобы добавить столбец в предложение WHERE инструкции фильтра запроса, и измените предложение WHERE следующим образом.</span><span class="sxs-lookup"><span data-stu-id="8551f-115">In the **Add Filter** dialog box, click the **SafetyStockLevel** column, click the right arrow to add the column to the Filter statement WHERE clause of the filter query, and modify the WHERE clause as follows:</span></span>  
  
    ```  
    WHERE [SafetyStockLevel] < 500  
    ```  
  
8.  <span data-ttu-id="8551f-116">Нажмите кнопку **ОК** и затем кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8551f-116">Click **OK**, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="8551f-117">Установите флажок **Создать моментальный снимок немедленно и обеспечить доступ к нему для инициализации подписок** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8551f-117">Select the **Create a snapshot immediately and keep the snapshot available to initialize subscriptions** check box, and click **Next**.</span></span>  
  
10. <span data-ttu-id="8551f-118">На странице "Безопасность агента" снимите флажок **Использовать настройки безопасности агента моментальных снимков** .</span><span class="sxs-lookup"><span data-stu-id="8551f-118">On the Agent Security page, clear **Use the security settings from the Snapshot Agent** check box.</span></span>  
  
11. <span data-ttu-id="8551f-119">Щелкните **настройки безопасности** для агент моментальных снимков, введите \<_Machine_Name> _**\ repl_snapshot** в поле **учетная запись процесса** , укажите пароль для этой учетной записи и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8551f-119">Click **Security Settings** for the Snapshot Agent, enter \<_Machine_Name>_**\repl_snapshot** in the **Process account** box, supply the password for this account, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="8551f-120">Повторите предыдущий шаг, чтобы установить repl_logreader в качестве учетной записи процесса для агента чтения журнала, а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="8551f-120">Repeat the previous step to set repl_logreader as the process account for the Log Reader Agent, and then click **Finish**.</span></span>  
  
13. <span data-ttu-id="8551f-121">На странице "Завершение работы мастера" введите **AdvWorksProductTrans** в поле **Имя публикации** и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="8551f-121">On the Complete the Wizard page, type **AdvWorksProductTrans** in the **Publication name** box, and click **Finish**.</span></span>  
  
14. <span data-ttu-id="8551f-122">После создания публикации нажмите кнопку **Закрыть** , чтобы закрыть мастер.</span><span class="sxs-lookup"><span data-stu-id="8551f-122">After the publication is created, click **Close** to complete the wizard.</span></span>  
  
### <a name="to-view-the-status-of-snapshot-generation"></a><span data-ttu-id="8551f-123">Просмотр состояния создания моментального снимка</span><span class="sxs-lookup"><span data-stu-id="8551f-123">To view the status of snapshot generation</span></span>  
  
1.  <span data-ttu-id="8551f-124">Подключитесь к издателю в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], а затем раскройте узел сервера и папку **Репликация** .</span><span class="sxs-lookup"><span data-stu-id="8551f-124">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="8551f-125">В папке **Локальные публикации** щелкните правой кнопкой мыши публикацию **AdvWorksProductTrans**и выберите пункт **Просмотр состояния агента моментальных снимков**.</span><span class="sxs-lookup"><span data-stu-id="8551f-125">In the **Local Publications** folder, right-click **AdvWorksProductTrans**, and then click **View Snapshot Agent Status**.</span></span>  
  
3.  <span data-ttu-id="8551f-126">Отобразится текущее состояние задания агента моментальных снимков для публикации.</span><span class="sxs-lookup"><span data-stu-id="8551f-126">The current status of the Snapshot Agent job for the publication is displayed.</span></span> <span data-ttu-id="8551f-127">Перед тем как перейти к следующему занятию, убедитесь, что задание моментального снимка выполнено успешно.</span><span class="sxs-lookup"><span data-stu-id="8551f-127">Verify that the snapshot job has succeeded before you continue to the next lesson.</span></span>  
  
### <a name="to-add-the-distribution-agent-login-to-the-pal"></a><span data-ttu-id="8551f-128">Добавление имени входа агента распространителя в список доступа к публикации</span><span class="sxs-lookup"><span data-stu-id="8551f-128">To add the Distribution Agent login to the PAL</span></span>  
  
1.  <span data-ttu-id="8551f-129">Подключитесь к издателю в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], а затем раскройте узел сервера и папку **Репликация** .</span><span class="sxs-lookup"><span data-stu-id="8551f-129">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="8551f-130">В папке **Локальные публикации** щелкните правой кнопкой мыши публикацию **AdvWorksProductTrans**и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="8551f-130">In the **Local Publications** folder, right-click **AdvWorksProductTrans**, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="8551f-131">Откроется диалоговое окно **Свойства публикации** .</span><span class="sxs-lookup"><span data-stu-id="8551f-131">The **Publication Properties** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="8551f-132">Выберите страницу **Список доступа к публикации** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="8551f-132">Select the **Publication Access List** page, and click **Add**.</span></span>  
  
4.  <span data-ttu-id="8551f-133">В диалоговом окне **Добавление доступа к публикации** выберите _<Имя_компьютера>_**\repl_distribution** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8551f-133">\In the **Add Publication Access** dialog box, select _<Machine_Name>_**\repl_distribution** and click **OK**.</span></span> <span data-ttu-id="8551f-134">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8551f-134">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8551f-135">Next Steps</span><span class="sxs-lookup"><span data-stu-id="8551f-135">Next Steps</span></span>  
 <span data-ttu-id="8551f-136">Публикация транзакций успешно создана.</span><span class="sxs-lookup"><span data-stu-id="8551f-136">You have successfully created the transactional publication.</span></span> <span data-ttu-id="8551f-137">Далее будет создана подписка на эту публикацию.</span><span class="sxs-lookup"><span data-stu-id="8551f-137">Next, you will subscribe to this publication.</span></span> <span data-ttu-id="8551f-138">См. [Занятие 2. Создание подписки на публикацию транзакций](lesson-2-creating-a-subscription-to-the-transactional-publication.md).</span><span class="sxs-lookup"><span data-stu-id="8551f-138">See [Lesson 2: Creating a Subscription to the Transactional Publication](lesson-2-creating-a-subscription-to-the-transactional-publication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8551f-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="8551f-139">See Also</span></span>  
 <span data-ttu-id="8551f-140">[Фильтрация опубликованных данных](publish/filter-published-data.md) </span><span class="sxs-lookup"><span data-stu-id="8551f-140">[Filter Published Data](publish/filter-published-data.md) </span></span>  
 <span data-ttu-id="8551f-141">[Define an Article](publish/define-an-article.md) </span><span class="sxs-lookup"><span data-stu-id="8551f-141">[Define an Article](publish/define-an-article.md) </span></span>  
 [<span data-ttu-id="8551f-142">Создание и применение моментального снимка</span><span class="sxs-lookup"><span data-stu-id="8551f-142">Create and Apply the Snapshot</span></span>](create-and-apply-the-snapshot.md)  
  
  
