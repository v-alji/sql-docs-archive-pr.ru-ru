---
title: Создание скриптов репликации | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- scripts [SQL Server replication], replication objects
- merge replication scripting [SQL Server replication]
- replication [SQL Server], scripting
- snapshot replication [SQL Server], scripting
- scripts [SQL Server replication]
- transactional replication, scripting
ms.assetid: e50fac44-54c0-470c-a4ea-9c111fa4322b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2e865e2664a399bca4738c1fc157bef176f35e96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655028"
---
# <a name="scripting-replication"></a><span data-ttu-id="4465d-102">Создание сценариев репликации</span><span class="sxs-lookup"><span data-stu-id="4465d-102">Scripting Replication</span></span>
  <span data-ttu-id="4465d-103">Все компоненты репликации в топологии должны использоваться в скриптах как часть плана аварийного восстановления, а скрипты могут также использоваться для автоматизации повторяющихся задач.</span><span class="sxs-lookup"><span data-stu-id="4465d-103">All replication components in a topology should be scripted as part of a disaster recovery plan, and scripts can also be used to automate repetitive tasks.</span></span> <span data-ttu-id="4465d-104">Скрипт содержит системные хранимые процедуры Transact-SQL, необходимые для выполнения элементов скрипта репликации, таких как публикация или подписка.</span><span class="sxs-lookup"><span data-stu-id="4465d-104">A script contains the Transact-SQL system stored procedures necessary to implement the replication component(s) scripted, such as a publication or subscription.</span></span> <span data-ttu-id="4465d-105">Скрипты могут быть созданы с помощью мастера (например, мастера создания публикаций) или в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] после создания компонента.</span><span class="sxs-lookup"><span data-stu-id="4465d-105">Scripts can be created in a wizard (such as the New Publication Wizard) or in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] after you create a component.</span></span> <span data-ttu-id="4465d-106">Скрипт можно просмотреть, изменить и запустить с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или **sqlcmd**.</span><span class="sxs-lookup"><span data-stu-id="4465d-106">You can view, modify, and run the script using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or **sqlcmd**.</span></span> <span data-ttu-id="4465d-107">Скрипты могут сохраняться с файлами резервных копий для использования в случае, если необходимо перенастроить топологию репликации.</span><span class="sxs-lookup"><span data-stu-id="4465d-107">Scripts can be stored with backup files to be used in case a replication topology must be reconfigured.</span></span>  
  
 <span data-ttu-id="4465d-108">Компонент должен быть заново включен в сценарий при внесении изменений любого из его свойств.</span><span class="sxs-lookup"><span data-stu-id="4465d-108">A component should be re-scripted if any property changes are made.</span></span> <span data-ttu-id="4465d-109">Если с репликацией транзакций используются специальные хранимые процедуры, копия каждой процедуры должна сохраняться со скриптами. Если процедура изменяется, ее копия должна обновляться (процедуры обычно обновляются в связи с изменениями схемы или изменениями требований приложения).</span><span class="sxs-lookup"><span data-stu-id="4465d-109">If you use custom stored procedures with transactional replication, a copy of each procedure should be stored with the scripts; the copy should be updated if the procedure changes (procedures are typically updated due to schema changes or changing application requirements).</span></span> <span data-ttu-id="4465d-110">Дополнительные сведения о хранимых процедурах см. в статье [Указание способа распространения изменений для статей транзакций](transactional/transactional-articles-specify-how-changes-are-propagated.md).</span><span class="sxs-lookup"><span data-stu-id="4465d-110">For more information about custom procedures, see [Specify How Changes Are Propagated for Transactional Articles](transactional/transactional-articles-specify-how-changes-are-propagated.md).</span></span>  
  
 <span data-ttu-id="4465d-111">Для публикаций слиянием, использующих параметризованные фильтры, скрипты публикации содержат вызовы хранимых процедур для создания секций данных.</span><span class="sxs-lookup"><span data-stu-id="4465d-111">For merge publications that use parameterized filters, publication scripts contain the stored procedure calls to create data partitions.</span></span> <span data-ttu-id="4465d-112">Скрипт содержит справочную информацию для созданных секций и способ воссоздания одной или нескольких секций в случае необходимости.</span><span class="sxs-lookup"><span data-stu-id="4465d-112">The script provides a reference for the partitions created and a way in which to re-create one or more partitions if necessary.</span></span>  
  
## <a name="example-of-automating-a-task-with-scripts"></a><span data-ttu-id="4465d-113">Пример автоматизации задачи с помощью скриптов</span><span class="sxs-lookup"><span data-stu-id="4465d-113">Example of Automating a Task with Scripts</span></span>  
 <span data-ttu-id="4465d-114">Рассмотрим компанию [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)], которая реализует репликацию слиянием, чтобы передавать данные своим удаленным торговым подразделениям.</span><span class="sxs-lookup"><span data-stu-id="4465d-114">Consider [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)], which implements merge replication to distribute data to its remote sales force.</span></span> <span data-ttu-id="4465d-115">Представитель отдела продаж загружает все данные клиентов на территории своей ответственности с помощью подписки по запросу.</span><span class="sxs-lookup"><span data-stu-id="4465d-115">A sales representative downloads all the data that pertains to the customers in her territory using pull subscriptions.</span></span> <span data-ttu-id="4465d-116">При работе в режиме «в сети» представитель отдела продаж обновляет данные и вводит новых клиентов и заказы.</span><span class="sxs-lookup"><span data-stu-id="4465d-116">When working offline, the sales representative updates data and enters new customers and orders.</span></span> <span data-ttu-id="4465d-117">Так как [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] имеет более пятидесяти коммерческих представителей в разных территориях, то использование мастера создания подписки отнимало бы слишком много времени при создании подписок на каждом подписчике.</span><span class="sxs-lookup"><span data-stu-id="4465d-117">Because [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] has more than fifty sales representatives in different territories, it would be time-consuming to create the different subscriptions at each Subscriber with the New Subscription Wizard.</span></span> <span data-ttu-id="4465d-118">Вместо этого администратор репликации может выполнить следующие шаги:</span><span class="sxs-lookup"><span data-stu-id="4465d-118">Instead, the replication administrator can follow these steps:</span></span>  
  
1.  <span data-ttu-id="4465d-119">Настроить необходимые публикации слиянием с использованием секций, разделенных по представителям отдела продаж или их территориям.</span><span class="sxs-lookup"><span data-stu-id="4465d-119">Set up the necessary merge publications with partitions based on the sales representative or their territory.</span></span>  
  
2.  <span data-ttu-id="4465d-120">Создать подписку по запросу для одного подписчика.</span><span class="sxs-lookup"><span data-stu-id="4465d-120">Create a pull subscription for one Subscriber.</span></span>  
  
3.  <span data-ttu-id="4465d-121">Создать скрипт на основе этой подписки по запросу.</span><span class="sxs-lookup"><span data-stu-id="4465d-121">Generate a script based on that pull subscription.</span></span>  
  
4.  <span data-ttu-id="4465d-122">Изменить скрипт, изменяя такие значения, как имя подписчика.</span><span class="sxs-lookup"><span data-stu-id="4465d-122">Modify the script, changing such values as the name of the Subscriber.</span></span>  
  
5.  <span data-ttu-id="4465d-123">Выполнить скрипт на нескольких подписчиках для создания необходимых подписок по запросу.</span><span class="sxs-lookup"><span data-stu-id="4465d-123">Run the script at multiple Subscribers to generate the required pull subscriptions.</span></span>  
  
## <a name="script-replication-objects"></a><span data-ttu-id="4465d-124">Создать скрипт репликации объектов</span><span class="sxs-lookup"><span data-stu-id="4465d-124">Script Replication Objects</span></span>  
 <span data-ttu-id="4465d-125">Создание скриптов для репликации объектов производится при помощи мастеров репликации или из папки **Репликация** в среде [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4465d-125">Script replication objects from the replication wizards or from the **Replication** folder in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="4465d-126">При создании скриптов при помощи мастеров можно выбрать создание объектов и скриптов для них или только создание скриптов.</span><span class="sxs-lookup"><span data-stu-id="4465d-126">If you script from the wizards, you can choose to create objects and script them, or you can choose only to script them.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4465d-127">Все пароли в сценариях имеют значение NULL.</span><span class="sxs-lookup"><span data-stu-id="4465d-127">All passwords are scripted as NULL.</span></span> <span data-ttu-id="4465d-128">По возможности предлагайте пользователям вводить учетные данные системы безопасности во время выполнения приложения.</span><span class="sxs-lookup"><span data-stu-id="4465d-128">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="4465d-129">При хранении учетных данных в файле скрипта необходимо защитить этот файл во избежание несанкционированного доступа.</span><span class="sxs-lookup"><span data-stu-id="4465d-129">If you store credentials in a script file, you must secure the file to prevent unauthorized access.</span></span>  
  
 <span data-ttu-id="4465d-130">Дополнительные сведения об использовании мастеров репликации см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="4465d-130">For more information about using the replication wizards, see:</span></span>  
  
-   [<span data-ttu-id="4465d-131">Настройка публикации и распространения</span><span class="sxs-lookup"><span data-stu-id="4465d-131">Configure Publishing and Distribution</span></span>](configure-publishing-and-distribution.md)  
  
-   [<span data-ttu-id="4465d-132">Create a Publication</span><span class="sxs-lookup"><span data-stu-id="4465d-132">Create a Publication</span></span>](publish/create-a-publication.md)  
  
-   [<span data-ttu-id="4465d-133">Создание принудительной подписки</span><span class="sxs-lookup"><span data-stu-id="4465d-133">Create a Push Subscription</span></span>](create-a-push-subscription.md)  
  
-   [<span data-ttu-id="4465d-134">Создание подписки по запросу</span><span class="sxs-lookup"><span data-stu-id="4465d-134">Create a Pull Subscription</span></span>](create-a-pull-subscription.md)  
  
#### <a name="to-script-an-object-from-a-replication-wizard"></a><span data-ttu-id="4465d-135">Создание скрипта объекта при помощи мастера репликации</span><span class="sxs-lookup"><span data-stu-id="4465d-135">To script an object from a replication wizard</span></span>  
  
1.  <span data-ttu-id="4465d-136">На странице **Действия мастера** установите флажок, соответствующий мастеру.</span><span class="sxs-lookup"><span data-stu-id="4465d-136">On the **Wizard Actions** page of a wizard, select the check box appropriate for the wizard:</span></span>  
  
    -   <span data-ttu-id="4465d-137">**Создать файл скрипта, содержащий шаги по созданию публикации.**</span><span class="sxs-lookup"><span data-stu-id="4465d-137">**Generate a script file with steps to create a publication**</span></span>  
  
    -   <span data-ttu-id="4465d-138">**Создать файл скрипта, содержащий шаги по созданию подписки (подписок).**</span><span class="sxs-lookup"><span data-stu-id="4465d-138">**Generate a script file with steps to create the subscription(s)**</span></span>  
  
    -   <span data-ttu-id="4465d-139">**Создать файл скрипта, содержащий шаги по настройке распространения.**</span><span class="sxs-lookup"><span data-stu-id="4465d-139">**Generate a script file with steps to configure distribution**</span></span>  
  
2.  <span data-ttu-id="4465d-140">Задайте параметры на странице **Свойства файла скрипта** .</span><span class="sxs-lookup"><span data-stu-id="4465d-140">Specify options on the **Script File Properties** page.</span></span>  
  
3.  <span data-ttu-id="4465d-141">Завершите работу мастера.</span><span class="sxs-lookup"><span data-stu-id="4465d-141">Complete the wizard.</span></span>  
  
#### <a name="to-script-an-object-from-management-studio"></a><span data-ttu-id="4465d-142">Создание скрипта объекта из среды Management Studio</span><span class="sxs-lookup"><span data-stu-id="4465d-142">To script an object from Management Studio</span></span>  
  
1.  <span data-ttu-id="4465d-143">Подключитесь к распространителю, издателю или подписчику [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], затем разверните узел сервера.</span><span class="sxs-lookup"><span data-stu-id="4465d-143">Connect to the Distributor, Publisher, or Subscriber in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="4465d-144">Раскройте папку **Репликация** , затем раскройте папку **Локальные публикации** или **Локальные подписки** .</span><span class="sxs-lookup"><span data-stu-id="4465d-144">Expand the **Replication** folder, and then expand the **Local Publications** folder or the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="4465d-145">Щелкните правой кнопкой мыши публикацию или подписку, затем щелкните **Сформировать скрипты**.</span><span class="sxs-lookup"><span data-stu-id="4465d-145">Right-click a publication or subscription, and then click **Generate Scripts**.</span></span>  
  
4.  <span data-ttu-id="4465d-146">Укажите параметры в диалоговом окне **Формирование скрипта SQL — \<ReplicationObject>** .</span><span class="sxs-lookup"><span data-stu-id="4465d-146">Specify options in the **Generate SQL Script - \<ReplicationObject>** dialog box.</span></span>  
  
5.  <span data-ttu-id="4465d-147">Щелкните **Вывести скрипт в файл**.</span><span class="sxs-lookup"><span data-stu-id="4465d-147">Click **Script to File**.</span></span>  
  
6.  <span data-ttu-id="4465d-148">Введите имя файла в диалоговом окне **Расположение файла скрипта** , а затем нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4465d-148">Enter a file name in the **Script File Location** dialog box, and then click **Save**.</span></span> <span data-ttu-id="4465d-149">Будет выведено сообщение о состоянии.</span><span class="sxs-lookup"><span data-stu-id="4465d-149">A status message is displayed.</span></span>  
  
7.  <span data-ttu-id="4465d-150">Нажмите кнопку **ОК**, затем кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="4465d-150">Click **OK**, and then click **Close**.</span></span>  
  
#### <a name="to-script-multiple-objects-from-management-studio"></a><span data-ttu-id="4465d-151">Создание скрипта нескольких объектов из среды Management Studio</span><span class="sxs-lookup"><span data-stu-id="4465d-151">To script multiple objects from Management Studio</span></span>  
  
1.  <span data-ttu-id="4465d-152">Подключитесь к распространителю, издателю или подписчику [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], затем разверните узел сервера.</span><span class="sxs-lookup"><span data-stu-id="4465d-152">Connect to the Distributor, Publisher, or Subscriber in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="4465d-153">Щелкните правой кнопкой мыши папку **Репликация** , затем щелкните **Сформировать скрипты**.</span><span class="sxs-lookup"><span data-stu-id="4465d-153">Right-click the **Replication** folder, and then click **Generate Scripts**.</span></span>  
  
3.  <span data-ttu-id="4465d-154">Укажите параметры в диалоговом окне **Формирование скрипта SQL** .</span><span class="sxs-lookup"><span data-stu-id="4465d-154">Specify options in the **Generate SQL Script** dialog box.</span></span>  
  
4.  <span data-ttu-id="4465d-155">Щелкните **Вывести скрипт в файл**.</span><span class="sxs-lookup"><span data-stu-id="4465d-155">Click **Script to File**.</span></span>  
  
5.  <span data-ttu-id="4465d-156">Введите имя файла в диалоговом окне **Расположение файла скрипта** , а затем нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4465d-156">Enter a file name in the **Script File Location** dialog box, and then click **Save**.</span></span> <span data-ttu-id="4465d-157">Будет выведено сообщение о состоянии.</span><span class="sxs-lookup"><span data-stu-id="4465d-157">A status message is displayed.</span></span>  
  
6.  <span data-ttu-id="4465d-158">Нажмите кнопку **OK** , затем кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="4465d-158">Click **OK, and then** click **Close**.</span></span>  
  
  
