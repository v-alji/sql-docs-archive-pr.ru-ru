---
title: Урок 1. Публикация данных с помощью репликации слиянием | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: c3c6e0b6-54cd-4b7d-8efb-2cefe14fcd7f
author: rothja
ms.author: jroth
ms.openlocfilehash: ba1d8829d84c02d1436013af80de4bf0979049e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736222"
---
# <a name="lesson-1-publishing-data-using-merge-replication"></a><span data-ttu-id="71ae8-102">Урок 1. Публикация данных с помощью репликации слиянием</span><span class="sxs-lookup"><span data-stu-id="71ae8-102">Lesson 1: Publishing Data Using Merge Replication</span></span>
  <span data-ttu-id="71ae8-103">На этом занятии с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] создается публикация слиянием с целью публикации подмножества таблиц **Employee**, **SalesOrderHeader**и **SalesOrderDetail** в образце базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="71ae8-103">In this lesson, you will create a merge publication using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to publish a subset of the **Employee**, **SalesOrderHeader**, and **SalesOrderDetail** tables in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="71ae8-104">Эти таблицы фильтруются с помощью параметризованных фильтров строк, так что каждая подписка содержит уникальную секцию данных.</span><span class="sxs-lookup"><span data-stu-id="71ae8-104">These tables are filtered with parameterized row filters so that each subscription contains a unique partition of the data.</span></span> <span data-ttu-id="71ae8-105">Также в список доступа к публикации добавляется имя входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , используемое агентом слияния.</span><span class="sxs-lookup"><span data-stu-id="71ae8-105">You will also add the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login used by the Merge Agent to the publication access list (PAL).</span></span> <span data-ttu-id="71ae8-106">Для работы с этим учебником требуется завершить работу с предыдущим учебником, [Подготовка сервера для репликации](tutorial-preparing-the-server-for-replication.md).</span><span class="sxs-lookup"><span data-stu-id="71ae8-106">This tutorial requires that you have completed the previous tutorial, [Preparing the Server for Replication](tutorial-preparing-the-server-for-replication.md).</span></span>  
  
### <a name="to-create-a-publication-and-define-articles"></a><span data-ttu-id="71ae8-107">Создание публикации и определение статей</span><span class="sxs-lookup"><span data-stu-id="71ae8-107">To create a publication and define articles</span></span>  
  
1.  <span data-ttu-id="71ae8-108">Подключитесь к издателю в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], а затем раскройте узел сервера.</span><span class="sxs-lookup"><span data-stu-id="71ae8-108">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="71ae8-109">Разверните папку **Репликация** , щелкните правой кнопкой мыши элемент **Локальные публикации**и выберите пункт **Создать публикацию**.</span><span class="sxs-lookup"><span data-stu-id="71ae8-109">Expand the **Replication** folder, right-click **Local Publications**, and click **New Publication**.</span></span>  
  
     <span data-ttu-id="71ae8-110">Будет запущен мастер настройки публикации.</span><span class="sxs-lookup"><span data-stu-id="71ae8-110">The Publication Configuration Wizard launches.</span></span>  
  
3.  <span data-ttu-id="71ae8-111">На странице «База данных публикации» выберите [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="71ae8-111">On the Publication Database page, select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="71ae8-112">На странице «Тип публикации» выберите **Публикация слиянием**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="71ae8-112">On the Publication Type page, select **Merge publication**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="71ae8-113">На странице «Типы подписчиков» убедитесь, что выбрана только [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] или более поздняя версия, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="71ae8-113">On the Subscriber Types page, ensure that only [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] or later is selected, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="71ae8-114">На странице «Статьи» разверните узел **Таблицы** , выберите **SalesOrderHeader** и **SalesOrderDetail**, затем разверните узел **Employee**, выберите **EmployeeID** или **LoginID**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="71ae8-114">On the Articles page, expand the **Tables** node, select **SalesOrderHeader** and **SalesOrderDetail**, then expand **Employee**, select **EmployeeID** or **LoginID**, and then click **Next**.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="71ae8-115">Дополнительные требуемые столбцы выделяются автоматически.</span><span class="sxs-lookup"><span data-stu-id="71ae8-115">Additional required columns are automatically selected.</span></span> <span data-ttu-id="71ae8-116">Выберите один из автоматически выбранных столбцов и просмотрите примечание под списком **Объекты для публикации** , объясняющее причину обязательного наличия столбца.</span><span class="sxs-lookup"><span data-stu-id="71ae8-116">Select any of  the automatically selected columns and view the note below the **Objects to publish** list for an explanation why the column is required.</span></span>  
  
7.  <span data-ttu-id="71ae8-117">На странице «Фильтрация строк таблицы» нажмите кнопку **Добавить** , а затем щелкните **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="71ae8-117">On the Filter Table Rows page, click **Add** and then click **Add Filter**.</span></span>  
  
8.  <span data-ttu-id="71ae8-118">В диалоговом окне **Добавление фильтра** выберите **Сотрудник (HumanResources)** в поле **Выберите таблицу для фильтрации**, щелкните столбец **LoginID** , нажмите кнопку со стрелкой вправо, чтобы добавить столбец в предложение WHERE фильтра запроса, и измените предложение WHERE следующим образом:</span><span class="sxs-lookup"><span data-stu-id="71ae8-118">In the **Add Filter** dialog box, select **Employee (HumanResources)** in **Select the table to filter**, click the **LoginID** column, click the right arrow to add the column to the WHERE clause of the filter query, and modify the WHERE clause as follows:</span></span>  
  
    ```  
    WHERE [LoginID] = HOST_NAME()  
    ```  
  
9. <span data-ttu-id="71ae8-119">Щелкните элемент **Строка из этой таблицы будет отправлена только одной подписке**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="71ae8-119">Click **A row from this table will go to only one subscription**, and click **OK**.</span></span>  
  
10. <span data-ttu-id="71ae8-120">На странице **Фильтрация строк таблицы** выберите **Сотрудник (кадры)**, нажмите **Добавить** , а затем **Добавить соединение для расширения выбранного фильтра**.</span><span class="sxs-lookup"><span data-stu-id="71ae8-120">On the **Filter Table Rows** page, click **Employee (Human Resources)**, click **Add,** and then click **Add Join to Extend the Selected Filter**.</span></span>  
  
11. <span data-ttu-id="71ae8-121">В диалоговом окне **Добавление соединения** выберите **Sales.SalesOrderHeader** в **Соединяемая таблица**, щелкните **Создать инструкцию соединения вручную**и завершите инструкцию соединения следующим образом:</span><span class="sxs-lookup"><span data-stu-id="71ae8-121">In the **Add Join** dialog box, select **Sales.SalesOrderHeader** under **Joined table**, click **Write the join statement manually**, and complete the join statement as follows:</span></span>  
  
    ```  
    ON Employee.EmployeeID = SalesOrderHeader.SalesPersonID  
    ```  
  
12. <span data-ttu-id="71ae8-122">В поле **Укажите параметры соединения**выберите **Уникальный ключ**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="71ae8-122">In **Specify join options**, select **Unique key**, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="71ae8-123">На странице «Фильтрация строк таблицы» щелкните **SalesOrderHeader**, нажмите кнопку **Добавить**, а затем щелкните **Добавить соединение для расширения выбранного фильтра**.</span><span class="sxs-lookup"><span data-stu-id="71ae8-123">On the Filter Table Rows page, click **SalesOrderHeader**, click **Add**, and then click **Add Join to Extend the Selected Filter**.</span></span>  
  
14. <span data-ttu-id="71ae8-124">В диалоговом окне **Добавление соединения** выберите **Sales.SalesOrderDetail** в поле **Соединяемая таблица**.</span><span class="sxs-lookup"><span data-stu-id="71ae8-124">In the **Add Join** dialog box, select **Sales.SalesOrderDetail** under **Joined table**.</span></span>  
  
15. <span data-ttu-id="71ae8-125">Нажмите **Создать инструкцию соединения вручную**.</span><span class="sxs-lookup"><span data-stu-id="71ae8-125">Click **Write the join statement manually**.</span></span>  
  
16. <span data-ttu-id="71ae8-126">В поле **Столбцы отфильтрованной таблицы**выберите **BusinessEntityID**, затем нажмите кнопку со стрелкой, чтобы скопировать имя столбца в инструкцию соединения.</span><span class="sxs-lookup"><span data-stu-id="71ae8-126">In **Filtered table columns**, select **BusinessEntityID**, then click the arrow button to copy the column name to the loin statement.</span></span>  
  
17. <span data-ttu-id="71ae8-127">В поле **Инструкция соединения** завершите инструкцию соединения следующим образом:</span><span class="sxs-lookup"><span data-stu-id="71ae8-127">In the **Join statement** box, complete the join statement as follows:</span></span>  
  
    ```  
    ON Employee.BusinessEntityID = SalesOrderHeader.SalesPersonID  
    ```  
  
18. <span data-ttu-id="71ae8-128">В поле **Укажите параметры соединения**выберите **Уникальный ключ**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="71ae8-128">In **Specify join options**, select **Unique key**, and then click **OK**.</span></span>  
  
19. <span data-ttu-id="71ae8-129">На странице **Фильтрация строк таблицы** выберите **SalesOrderHeader (Sales)**, нажмите **Добавить**, а затем **Добавить соединение для расширения выбранного фильтра**.</span><span class="sxs-lookup"><span data-stu-id="71ae8-129">On the **Filter Table Rows** page, click **SalesOrderHeader (Sales)**, click **Add**, and then click **Add Join to Extend the Selected Filter**.</span></span>  
  
20. <span data-ttu-id="71ae8-130">В диалоговом окне **Добавление соединения** выберите **Sales.SalesOrderDetail** в поле **Соединяемая таблица**, нажмите кнопку **ОК**, а затем кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="71ae8-130">In the **Add Join** dialog box, select **Sales.SalesOrderDetail** under **Joined table**, click **OK**, and then click **Next**.</span></span>  
  
21. <span data-ttu-id="71ae8-131">Установите флажок **Создать моментальный снимок немедленно**, снимите флажок **Запланировать запуск агента моментальных снимков в следующее время**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="71ae8-131">Select **Create a snapshot immediately**, clear **Schedule the snapshot agent to run at the following times**, and click **Next**.</span></span>  
  
22. <span data-ttu-id="71ae8-132">На странице Безопасность агента щелкните **Параметры безопасности**, введите \<_Machine_Name> _**\ repl_snapshot** в поле **учетная запись процесса** , укажите пароль для этой учетной записи и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="71ae8-132">On the Agent Security page, click **Security Settings**, type \<_Machine_Name>_**\repl_snapshot** in the **Process account** box, supply the password for this account, and then click **OK**.</span></span> <span data-ttu-id="71ae8-133">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="71ae8-133">Click **Finish**.</span></span>  
  
23. <span data-ttu-id="71ae8-134">На странице «Завершение работы мастера» введите **AdvWorksSalesOrdersMerge** в поле **Имя публикации** и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="71ae8-134">On the Complete the Wizard page, enter **AdvWorksSalesOrdersMerge** in the **Publication name** box and click **Finish**.</span></span>  
  
24. <span data-ttu-id="71ae8-135">По завершении создания публикации нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="71ae8-135">After the publication is created, click **Close**.</span></span>  
  
### <a name="to-view-the-status-of-snapshot-generation"></a><span data-ttu-id="71ae8-136">Просмотр состояния создания моментального снимка</span><span class="sxs-lookup"><span data-stu-id="71ae8-136">To view the status of snapshot generation</span></span>  
  
1.  <span data-ttu-id="71ae8-137">Подключитесь к издателю в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], а затем раскройте узел сервера и папку **Репликация** .</span><span class="sxs-lookup"><span data-stu-id="71ae8-137">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="71ae8-138">В папке "Локальные публикации" щелкните правой кнопкой мыши публикацию **AdvWorksSalesOrdersMerge**и выберите пункт **Просмотр состояния агента моментальных снимков**.</span><span class="sxs-lookup"><span data-stu-id="71ae8-138">In the Local Publications folder, right-click **AdvWorksSalesOrdersMerge**, and then click **View Snapshot Agent Status**.</span></span>  
  
3.  <span data-ttu-id="71ae8-139">Отобразится текущее состояние задания агента моментальных снимков для публикации.</span><span class="sxs-lookup"><span data-stu-id="71ae8-139">The current status of the Snapshot Agent job for the publication is displayed.</span></span> <span data-ttu-id="71ae8-140">Перед тем как перейти к следующему занятию, убедитесь, что задание моментального снимка выполнено успешно.</span><span class="sxs-lookup"><span data-stu-id="71ae8-140">Ensure that the snapshot job has succeeded before you continue to the next lesson.</span></span>  
  
### <a name="to-add-the-merge-agent-login-to-the-pal"></a><span data-ttu-id="71ae8-141">Добавление имени входа агента слияния в список доступа к публикации</span><span class="sxs-lookup"><span data-stu-id="71ae8-141">To add the Merge Agent login to the PAL</span></span>  
  
1.  <span data-ttu-id="71ae8-142">Подключитесь к издателю в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], а затем раскройте узел сервера и папку **Репликация** .</span><span class="sxs-lookup"><span data-stu-id="71ae8-142">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="71ae8-143">В папке "Локальные публикации" щелкните правой кнопкой мыши публикацию **AdvWorksSalesOrdersMerge**и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="71ae8-143">In the Local Publications folder, right-click **AdvWorksSalesOrdersMerge**, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="71ae8-144">Откроется диалоговое окно **Свойства публикации** .</span><span class="sxs-lookup"><span data-stu-id="71ae8-144">The **Publication Properties** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="71ae8-145">Выберите страницу **Список доступа к публикации** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="71ae8-145">Select the **Publication Access List** page, and click **Add**.</span></span>  
  
4.  <span data-ttu-id="71ae8-146">В диалоговом окне "Добавление доступа к публикации" выберите _<Имя_компьютера>_**\repl_merge** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="71ae8-146">In the Add Publication Access dialog box, select _<Machine_Name>_**\repl_merge** and click **OK**.</span></span> <span data-ttu-id="71ae8-147">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="71ae8-147">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="71ae8-148">Next Steps</span><span class="sxs-lookup"><span data-stu-id="71ae8-148">Next Steps</span></span>  
 <span data-ttu-id="71ae8-149">Публикация слиянием успешно создана.</span><span class="sxs-lookup"><span data-stu-id="71ae8-149">You have successfully created the merge publication.</span></span> <span data-ttu-id="71ae8-150">Далее будет создана подписка на эту публикацию.</span><span class="sxs-lookup"><span data-stu-id="71ae8-150">Next, you will subscribe to this publication.</span></span> <span data-ttu-id="71ae8-151">См. [Занятие 2. Создание подписки на публикацию слиянием](lesson-2-creating-a-subscription-to-the-merge-publication.md).</span><span class="sxs-lookup"><span data-stu-id="71ae8-151">See [Lesson 2: Creating a Subscription to the Merge Publication](lesson-2-creating-a-subscription-to-the-merge-publication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71ae8-152">См. также:</span><span class="sxs-lookup"><span data-stu-id="71ae8-152">See Also</span></span>  
 <span data-ttu-id="71ae8-153">[Фильтрация опубликованных данных](publish/filter-published-data.md) </span><span class="sxs-lookup"><span data-stu-id="71ae8-153">[Filter Published Data](publish/filter-published-data.md) </span></span>  
 <span data-ttu-id="71ae8-154">[Parameterized Row Filters](merge/parameterized-filters-parameterized-row-filters.md) </span><span class="sxs-lookup"><span data-stu-id="71ae8-154">[Parameterized Row Filters](merge/parameterized-filters-parameterized-row-filters.md) </span></span>  
 [<span data-ttu-id="71ae8-155">Определение статьи</span><span class="sxs-lookup"><span data-stu-id="71ae8-155">Define an Article</span></span>](publish/define-an-article.md)  
  
  
