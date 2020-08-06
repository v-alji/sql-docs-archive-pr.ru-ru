---
title: Управление базой знаний | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 27f306f4-d67c-47f5-b35c-4260cc5d36e3
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: cc5fdd87ddb3ea687db10a29d7001564fd8ff107
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667905"
---
# <a name="manage-a-knowledge-base"></a><span data-ttu-id="75e3e-102">Управление базой знаний</span><span class="sxs-lookup"><span data-stu-id="75e3e-102">Manage a Knowledge Base</span></span>
  <span data-ttu-id="75e3e-103">В этом разделе описано, как выполнять функции управления в базе знаний служб [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="75e3e-103">This topic describes how to perform management functions on a knowledge base in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="75e3e-104">Вы можете удалить базу знаний, разблокировать ее, отменить работу в ней, переименовать ее и отобразить ее свойства.</span><span class="sxs-lookup"><span data-stu-id="75e3e-104">You can delete a knowledge base, unlock it, discard your work on it, rename it, and display its properties.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="75e3e-105">Перед началом</span><span class="sxs-lookup"><span data-stu-id="75e3e-105">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="75e3e-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="75e3e-106">Prerequisites</span></span>  
 <span data-ttu-id="75e3e-107">Чтобы управлять базой знаний, база знаний уже должна быть создана и либо опубликована (если ее создал другой пользователь), либо закрыта (если ее создали вы).</span><span class="sxs-lookup"><span data-stu-id="75e3e-107">To manage a knowledge base, the knowledge base must have already been created, and either published (if another person created it) or have been closed (if you created it).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="75e3e-108">безопасность</span><span class="sxs-lookup"><span data-stu-id="75e3e-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="75e3e-109">Permissions</span><span class="sxs-lookup"><span data-stu-id="75e3e-109">Permissions</span></span>  
 <span data-ttu-id="75e3e-110">Для открытия базы знаний необходима роль dqs_kb_editor или dqs_administrator в базе данных DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="75e3e-110">You must have the dqs_kb_editor role or the dqs_administrator on the DQS_MAIN database to open a knowledge base.</span></span>  
  
##  <a name="manage-a-knowledge-base"></a><a name="Manage"></a><span data-ttu-id="75e3e-111">Управление базой знаний</span><span class="sxs-lookup"><span data-stu-id="75e3e-111">Manage a Knowledge Base</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="75e3e-112">[Запустите приложение Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="75e3e-112">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="75e3e-113">На главной странице [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] нажмите кнопку **Открыть базу знаний**.</span><span class="sxs-lookup"><span data-stu-id="75e3e-113">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open knowledge base**.</span></span>  
  
3.  <span data-ttu-id="75e3e-114">Щелкните правой кнопкой мыши базу знаний в таблице баз знаний.</span><span class="sxs-lookup"><span data-stu-id="75e3e-114">Right-click a knowledge base in the knowledge base table.</span></span>  
  
4.  <span data-ttu-id="75e3e-115">В контекстном меню вы можете выбрать следующее:</span><span class="sxs-lookup"><span data-stu-id="75e3e-115">In the context menu, you can do the following:</span></span>  
  
    1.  <span data-ttu-id="75e3e-116">**Открыть**: щелкните, чтобы открыть базу знаний в действии, выбранном на панели **Выбор действия** .</span><span class="sxs-lookup"><span data-stu-id="75e3e-116">**Open**: Click to open the knowledge base in the activity selected in the **Select Activity** pane.</span></span>  
  
    2.  <span data-ttu-id="75e3e-117">**Разблокировать**: вы можете разблокировать базу знаний, если работали с базой знаний во время управления доменами, обнаружения знаний или операции политики сопоставления, и закрыли ее.</span><span class="sxs-lookup"><span data-stu-id="75e3e-117">**Unlock**: You can unlock the knowledge base if you are the user who was working on the knowledge base in one of the steps of domain management, knowledge discovery, and the matching policy activity, and closed it.</span></span> <span data-ttu-id="75e3e-118">Если вы выгрузите базу знаний, другой пользователь сможет открыть ее и работать с ней.</span><span class="sxs-lookup"><span data-stu-id="75e3e-118">If you unload the knowledge base, another person will be able to open it and work on it.</span></span> <span data-ttu-id="75e3e-119">Эта команда недоступна, если база знаний не находится в состоянии деятельности.</span><span class="sxs-lookup"><span data-stu-id="75e3e-119">This command is not available if the knowledge base is not in a state of an activity.</span></span> <span data-ttu-id="75e3e-120">Дополнительные сведения см. в разделе [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span><span class="sxs-lookup"><span data-stu-id="75e3e-120">For more information, see [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span></span>  
  
    3.  <span data-ttu-id="75e3e-121">**Отменить работу**: выберите, если база знаний обрабатывается, как показывает запись в поле State таблицы.</span><span class="sxs-lookup"><span data-stu-id="75e3e-121">**Discard work**: Click when the knowledge base is in a state of being worked on, as shown with an entry in the State field in the table.</span></span> <span data-ttu-id="75e3e-122">Эта команда недоступна, если база знаний не находится в состоянии активности; она также недоступна, если база знаний заблокирована.</span><span class="sxs-lookup"><span data-stu-id="75e3e-122">This command is not available if the knowledge base is not in a state of an activity, and it is not available if the knowledge base is locked.</span></span> <span data-ttu-id="75e3e-123">Дополнительные сведения см. в разделе [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span><span class="sxs-lookup"><span data-stu-id="75e3e-123">For more information, see [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span></span>  
  
    4.  <span data-ttu-id="75e3e-124">**Переименовать**: выберите, чтобы разрешить изменение поля Knowledge Base таблицы для базы знаний, выбранной правой кнопкой мыши.</span><span class="sxs-lookup"><span data-stu-id="75e3e-124">**Rename**: Click to make the Knowledge Base field of the table editable for the knowledge base that you right-clicked on.</span></span> <span data-ttu-id="75e3e-125">Измените имя, затем щелкните эту базу знаний и другую в этом поле, чтобы изменение имени было принято.</span><span class="sxs-lookup"><span data-stu-id="75e3e-125">Change the name, and then click on that knowledge base and another one in the field to accept the name change.</span></span>  
  
    5.  <span data-ttu-id="75e3e-126">**Удалить**: выберите, чтобы удалить базу знаний из базы данных DQS_MAIN в [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75e3e-126">**Delete**: Click to remove the knowledge base from the DQS_MAIN database on [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span>  
  
    6.  <span data-ttu-id="75e3e-127">**Свойства**: выберите, чтобы отобразить свойства базы данных в окне только для чтения.</span><span class="sxs-lookup"><span data-stu-id="75e3e-127">**Properties**: Click to display properties for the database in a read-only display.</span></span>  
  
        1.  <span data-ttu-id="75e3e-128">**Исходная база знаний**: база знаний, легшая в основу этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="75e3e-128">**Source Knowledge Base**: the knowledge base that this database was based on.</span></span> <span data-ttu-id="75e3e-129">Делать это не обязательно.</span><span class="sxs-lookup"><span data-stu-id="75e3e-129">This is optional.</span></span>  
  
        2.  <span data-ttu-id="75e3e-130">**Состояние**: указывает, находится ли база знаний в состоянии **В работе** и находится ли она в каком-либо определенном действии управления знаниями, как было определено при ее последнем закрытии.</span><span class="sxs-lookup"><span data-stu-id="75e3e-130">**State**: Indicates if the knowledge base is **In Work** and if it is in a specific knowledge management activity, as determined when it was last closed.</span></span> <span data-ttu-id="75e3e-131">Состоянием может быть **В работе**, при этом база знаний была открыта в сеансе управления наборами знаний, но конкретное действие с ней не производится; или **В работе** плюс действие управления наборами знаний, при этом база знаний была открыта в сеансе управления наборами знаний, и с ней выполняется конкретное действие.</span><span class="sxs-lookup"><span data-stu-id="75e3e-131">The state can be **In Work**, in which the knowledge base is opened in a knowledge management session, but not in a specific activity, or **In Work** plus a knowledge management activity, in which the knowledge base is opened in a knowledge management session, and in a specific activity.</span></span>  
  
        3.  <span data-ttu-id="75e3e-132">**Заблокирована**: значение **True** , если база знаний заблокирована, иначе значение **False** .</span><span class="sxs-lookup"><span data-stu-id="75e3e-132">**Is Locked**: **True** if the knowledge base was locked, **False** if not</span></span>  
  
        4.  <span data-ttu-id="75e3e-133">**Содержит неопубликованное содержимое**: значение True, если в базе знаний имеется содержание, которое не было сохранено путем публикации, иначе значение False.</span><span class="sxs-lookup"><span data-stu-id="75e3e-133">**Contains unpublished content**: True if the knowledge base contains content that has not been saved by publishing, False if not</span></span>  
  
        5.  <span data-ttu-id="75e3e-134">**Кем заблокирована**: имя пользователя, который закрыл базу знаний, заблокировав ее.</span><span class="sxs-lookup"><span data-stu-id="75e3e-134">**Locked By**: the name of the user who closed the knowledge base, locking it</span></span>  
  
        6.  <span data-ttu-id="75e3e-135">**Дата блокировки**: дата, когда была выполнена блокировка.</span><span class="sxs-lookup"><span data-stu-id="75e3e-135">**Locked Date**: date when locked</span></span>  
  
        7.  <span data-ttu-id="75e3e-136">**Автор**: имя пользователя, который создал базу знаний, с указанием сети, к которой он или она принадлежит.</span><span class="sxs-lookup"><span data-stu-id="75e3e-136">**Created By**: the name of the user who created the knowledge base, with the network that he or she belongs to</span></span>  
  
        8.  <span data-ttu-id="75e3e-137">**Дата создания**: дата создания базы знаний.</span><span class="sxs-lookup"><span data-stu-id="75e3e-137">**Created Date**: date when created</span></span>  
  
##  <a name="follow-up-after-managing-a-knowledge-base"></a><a name="FollowUp"></a><span data-ttu-id="75e3e-138">Дальнейшие действия. после управления базой знаний</span><span class="sxs-lookup"><span data-stu-id="75e3e-138">Follow Up: After Managing a Knowledge Base</span></span>  
 <span data-ttu-id="75e3e-139">После проведения управления базой знаний следующий шаг зависит от того, какое действие вы выполнили с базой знаний:</span><span class="sxs-lookup"><span data-stu-id="75e3e-139">After you manage a knowledge base, your next step depends upon the action you took on the knowledge base:</span></span>  
  
-   <span data-ttu-id="75e3e-140">Если вы открыли базу знаний, вы будете продолжать выбранное действие.</span><span class="sxs-lookup"><span data-stu-id="75e3e-140">If you opened the knowledge base, you will continue in the activity that you selected.</span></span>  
  
-   <span data-ttu-id="75e3e-141">Если вы разблокировали ее, она будет доступна в указанном состоянии другому пользователю для открытия и работы.</span><span class="sxs-lookup"><span data-stu-id="75e3e-141">If you unlocked it, it will be available for another person to open and work on, in the state indicated.</span></span>  
  
-   <span data-ttu-id="75e3e-142">Если вы отменили работу с ней, база знаний будет доступна в своем последнем опубликованном состоянии.</span><span class="sxs-lookup"><span data-stu-id="75e3e-142">If you discarded the work on it, the knowledge base will be available in its last published state.</span></span>  
  
-   <span data-ttu-id="75e3e-143">Если вы переименовали ее, вам придется открыть переименованную базу знаний для работы с ней.</span><span class="sxs-lookup"><span data-stu-id="75e3e-143">If you renamed it, you will have to open the renamed knowledge base to work on it.</span></span>  
  
-   <span data-ttu-id="75e3e-144">Если вы удалили ее, вам придется выбрать другую базу знаний для работы или создать новую базу знаний.</span><span class="sxs-lookup"><span data-stu-id="75e3e-144">If you delete it, you will have to select another knowledge base to work on, or create a new one.</span></span>  
  
  
