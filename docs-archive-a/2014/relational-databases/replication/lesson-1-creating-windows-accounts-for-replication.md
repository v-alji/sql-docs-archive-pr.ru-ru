---
title: Занятие 1. Создание учетных записей Windows для репликации | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
- replication [SQL Server], administering
ms.assetid: 65c3816b-47f0-448c-a4a4-ebd3e2a58820
author: rothja
ms.author: jroth
ms.openlocfilehash: 29f1008338b3ba728066ed611108477586a4c899
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655580"
---
# <a name="lesson-1-creating-windows-accounts-for-replication"></a><span data-ttu-id="27fb9-102">Занятие 1. Создание учетных записей Windows для репликации</span><span class="sxs-lookup"><span data-stu-id="27fb9-102">Lesson 1: Creating Windows Accounts for Replication</span></span>
  <span data-ttu-id="27fb9-103">На этом занятии будут созданы учетные записи Windows для запуска агентов репликации.</span><span class="sxs-lookup"><span data-stu-id="27fb9-103">In this lesson, you will create Windows accounts to run replication agents.</span></span> <span data-ttu-id="27fb9-104">На локальном сервере будут созданы отдельные учетные записи Windows для следующих агентов:</span><span class="sxs-lookup"><span data-stu-id="27fb9-104">You will create a separate Windows account on the local server for the following agents:</span></span>  
  
|<span data-ttu-id="27fb9-105">Агент</span><span class="sxs-lookup"><span data-stu-id="27fb9-105">Agent</span></span>|<span data-ttu-id="27fb9-106">Расположение</span><span class="sxs-lookup"><span data-stu-id="27fb9-106">Location</span></span>|<span data-ttu-id="27fb9-107">Имя учетной записи</span><span class="sxs-lookup"><span data-stu-id="27fb9-107">Account name</span></span>|  
|-----------|--------------|------------------|  
|<span data-ttu-id="27fb9-108">агент моментальных снимков</span><span class="sxs-lookup"><span data-stu-id="27fb9-108">Snapshot Agent</span></span>|<span data-ttu-id="27fb9-109">Publisher</span><span class="sxs-lookup"><span data-stu-id="27fb9-109">Publisher</span></span>|<span data-ttu-id="27fb9-110">\<*machine_name*>\ repl_snapshot</span><span class="sxs-lookup"><span data-stu-id="27fb9-110">\<*machine_name*>\repl_snapshot</span></span>|  
|<span data-ttu-id="27fb9-111">Агент чтения журнала.</span><span class="sxs-lookup"><span data-stu-id="27fb9-111">Log Reader Agent</span></span>|<span data-ttu-id="27fb9-112">Publisher</span><span class="sxs-lookup"><span data-stu-id="27fb9-112">Publisher</span></span>|<span data-ttu-id="27fb9-113">\<*machine_name*>\ repl_logreader</span><span class="sxs-lookup"><span data-stu-id="27fb9-113">\<*machine_name*>\repl_logreader</span></span>|  
|<span data-ttu-id="27fb9-114">Агент распространителя</span><span class="sxs-lookup"><span data-stu-id="27fb9-114">Distribution Agent</span></span>|<span data-ttu-id="27fb9-115">Издатель и подписчик</span><span class="sxs-lookup"><span data-stu-id="27fb9-115">Publisher and Subscriber</span></span>|<span data-ttu-id="27fb9-116">\<*machine_name*>\ repl_distribution</span><span class="sxs-lookup"><span data-stu-id="27fb9-116">\<*machine_name*>\repl_distribution</span></span>|  
|<span data-ttu-id="27fb9-117">Агент слияния.</span><span class="sxs-lookup"><span data-stu-id="27fb9-117">Merge Agent</span></span>|<span data-ttu-id="27fb9-118">Издатель и подписчик</span><span class="sxs-lookup"><span data-stu-id="27fb9-118">Publisher and Subscriber</span></span>|<span data-ttu-id="27fb9-119">\<*machine_name*>\ repl_merge</span><span class="sxs-lookup"><span data-stu-id="27fb9-119">\<*machine_name*>\repl_merge</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="27fb9-120">В учебниках по репликации издатель и распространитель совместно используют один и тот же экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="27fb9-120">In the replication tutorials, the Publisher and Distributor share the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="27fb9-121">Издатель и подписчик могут совместно использовать один и тот же экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], но это не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="27fb9-121">The Publisher and Subscriber may share the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], but it is not a requirement.</span></span> <span data-ttu-id="27fb9-122">Если издатель и подписчик совместно используют один и тот же экземпляр, то не требуется выполнять шаги по созданию учетных записей на подписчике.</span><span class="sxs-lookup"><span data-stu-id="27fb9-122">If the Publisher and Subscriber share the same instance, the steps that are used to create accounts at the Subscriber are not required.</span></span>  
  
### <a name="to-create-local-windows-accounts-for-replication-agents-at-the-publisher"></a><span data-ttu-id="27fb9-123">Создание локальных учетных записей Windows для агентов репликации на издателе</span><span class="sxs-lookup"><span data-stu-id="27fb9-123">To create local Windows accounts for replication agents at the Publisher</span></span>  
  
1.  <span data-ttu-id="27fb9-124">На издателе откройте оснастку « **Управление компьютером** » из **меню «Администрирование** » на панели управления.</span><span class="sxs-lookup"><span data-stu-id="27fb9-124">At the Publisher, open **Computer Management** from **Administrative Tools** in Control Panel.</span></span>  
  
2.  <span data-ttu-id="27fb9-125">В оснастке **Служебные программы**разверните узел **Локальные пользователи и группы**.</span><span class="sxs-lookup"><span data-stu-id="27fb9-125">In **System Tools**, expand **Local Users and Groups**.</span></span>  
  
3.  <span data-ttu-id="27fb9-126">Щелкните правой кнопкой мыши элемент **Пользователи** и выберите пункт **Новый пользователь**.</span><span class="sxs-lookup"><span data-stu-id="27fb9-126">Right-click **Users** and then click **New User**.</span></span>  
  
4.  <span data-ttu-id="27fb9-127">Введите `repl_snapshot` в поле **имя пользователя** , укажите пароль и другие важные сведения, а затем нажмите кнопку **создать** , чтобы создать учетную запись repl_snapshot.</span><span class="sxs-lookup"><span data-stu-id="27fb9-127">Enter `repl_snapshot` in the **User name** box, provide the password and other relevant information, and then click **Create** to create the repl_snapshot account.</span></span>  
  
5.  <span data-ttu-id="27fb9-128">Повторите предыдущий шаг, чтобы создать учетные записи repl_logreader, repl_distribution и repl_merge.</span><span class="sxs-lookup"><span data-stu-id="27fb9-128">Repeat the previous step to create the repl_logreader, repl_distribution, and repl_merge accounts.</span></span>  
  
6.  <span data-ttu-id="27fb9-129">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="27fb9-129">Click **Close**.</span></span>  
  
### <a name="to-create-local-windows-accounts-for-replication-agents-at-the-subscriber"></a><span data-ttu-id="27fb9-130">Создание локальных учетных записей Windows для агентов репликации на подписчике</span><span class="sxs-lookup"><span data-stu-id="27fb9-130">To create local Windows accounts for replication agents at the Subscriber</span></span>  
  
1.  <span data-ttu-id="27fb9-131">На подписчике откройте **оснастку «Управление компьютером** » из **меню «Администрирование** » на панели управления.</span><span class="sxs-lookup"><span data-stu-id="27fb9-131">At the Subscriber, open **Computer Management** from **Administrative Tools** in Control Panel.</span></span>  
  
2.  <span data-ttu-id="27fb9-132">В оснастке **Служебные программы**разверните узел **Локальные пользователи и группы**.</span><span class="sxs-lookup"><span data-stu-id="27fb9-132">In **System Tools**, expand **Local Users and Groups**.</span></span>  
  
3.  <span data-ttu-id="27fb9-133">Щелкните правой кнопкой мыши элемент **Пользователи** и выберите пункт **Новый пользователь**.</span><span class="sxs-lookup"><span data-stu-id="27fb9-133">Right-click **Users** and then click **New User**.</span></span>  
  
4.  <span data-ttu-id="27fb9-134">Введите `repl_distribution` в поле **имя пользователя** , укажите пароль и другие важные сведения, а затем нажмите кнопку **создать** , чтобы создать учетную запись repl_distribution.</span><span class="sxs-lookup"><span data-stu-id="27fb9-134">Enter `repl_distribution` in the **User name** box, provide the password and other relevant information, and then click **Create** to create the repl_distribution account.</span></span>  
  
5.  <span data-ttu-id="27fb9-135">Повторите предыдущий шаг, чтобы создать учетную запись repl_merge.</span><span class="sxs-lookup"><span data-stu-id="27fb9-135">Repeat the previous step to create the repl_merge account.</span></span>  
  
6.  <span data-ttu-id="27fb9-136">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="27fb9-136">Click **Close**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="27fb9-137">Next Steps</span><span class="sxs-lookup"><span data-stu-id="27fb9-137">Next Steps</span></span>  
 <span data-ttu-id="27fb9-138">Создание учетных записей Windows для агентов репликации успешно выполнено.</span><span class="sxs-lookup"><span data-stu-id="27fb9-138">You have successfully created Windows accounts for replication agents.</span></span> <span data-ttu-id="27fb9-139">Далее предстоит настроить папку моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="27fb9-139">Next, you will configure the snapshot folder.</span></span> <span data-ttu-id="27fb9-140">См. раздел [Занятие 2. Подготовка папки моментальных снимков](lesson-2-preparing-the-snapshot-folder.md).</span><span class="sxs-lookup"><span data-stu-id="27fb9-140">See [Lesson 2: Preparing the Snapshot Folder](lesson-2-preparing-the-snapshot-folder.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27fb9-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="27fb9-141">See Also</span></span>  
 [<span data-ttu-id="27fb9-142">Replication Agents Overview</span><span class="sxs-lookup"><span data-stu-id="27fb9-142">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
