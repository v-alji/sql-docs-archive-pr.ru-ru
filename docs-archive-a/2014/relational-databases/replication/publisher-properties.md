---
title: Свойства Репликация SQL Server издателя | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.configdistwizard.distpubproperties.f1
- sql12.rep.configdistwizard.pubproperties.general.f1
- sql12.rep.configdistwizard.pubproperties.pubdb.f1
- sql12.rep.configdistwizard.pubproperties.subscribers.f1
ms.assetid: 98df1aea-0406-40bf-a917-4bd80464125c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f3e14f82e855cc29f83859d85dfdaaf85a1bda37
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732573"
---
# <a name="sql-server-replication-publisher-properties"></a><span data-ttu-id="c3cb5-102">Свойства Репликация SQL Server издателя</span><span class="sxs-lookup"><span data-stu-id="c3cb5-102">SQL Server Replication Publisher Properties</span></span>
  <span data-ttu-id="c3cb5-103">Этот раздел содержит сведения о свойствах издателя, доступных на распространителе и издателе.</span><span class="sxs-lookup"><span data-stu-id="c3cb5-103">This section contains information on Publisher properties available at the Distributor and the Publisher.</span></span> 

## <a name="general"></a><span data-ttu-id="c3cb5-104">Общие</span><span class="sxs-lookup"><span data-stu-id="c3cb5-104">General</span></span>  
  <span data-ttu-id="c3cb5-105"> Страница **Общие** диалогового окна **Свойства издателя** отображает доступные только для чтения сведения о распространителе и базе данных распространителя, используемой издателем.</span><span class="sxs-lookup"><span data-stu-id="c3cb5-105">The **General** page of the **Publisher Properties** dialog box displays read-only information on the Distributor and distribution database that the Publisher uses.</span></span> <span data-ttu-id="c3cb5-106">Чтобы изменить распространителя или базу данных распространителя для издателя:</span><span class="sxs-lookup"><span data-stu-id="c3cb5-106">To change the Distributor or distribution database for a Publisher:</span></span>  
  
1.  <span data-ttu-id="c3cb5-107">Отключите публикацию на сервере издателя.</span><span class="sxs-lookup"><span data-stu-id="c3cb5-107">Disable publishing on the Publisher.</span></span> <span data-ttu-id="c3cb5-108">Дополнительные сведения см. в статье [Отключение публикации и распространения](disable-publishing-and-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="c3cb5-108">For more information, see [Disable Publishing and Distribution](disable-publishing-and-distribution.md).</span></span>    
2.  <span data-ttu-id="c3cb5-109">Повторно настройте публикацию и распространение.</span><span class="sxs-lookup"><span data-stu-id="c3cb5-109">Reconfigure publishing and distribution.</span></span> <span data-ttu-id="c3cb5-110">Дополнительные сведения см. в статье [Configure Publishing and Distribution](configure-publishing-and-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="c3cb5-110">For more information, see [Configure Publishing and Distribution](configure-publishing-and-distribution.md).</span></span>  

## <a name="distributor"></a><span data-ttu-id="c3cb5-111">Распространитель</span><span class="sxs-lookup"><span data-stu-id="c3cb5-111">Distributor</span></span>
  <span data-ttu-id="c3cb5-112"> Диалоговое окно **Свойства издателя** позволяет просматривать и изменять свойства, относящиеся к связи между издателем и его распространителем.</span><span class="sxs-lookup"><span data-stu-id="c3cb5-112">The **Publisher Properties** dialog box allows you to view and modify properties associated with the relationship between the Publisher and its Distributor.</span></span>  
  
### <a name="options"></a><span data-ttu-id="c3cb5-113">Параметры</span><span class="sxs-lookup"><span data-stu-id="c3cb5-113">Options</span></span>  
 <span data-ttu-id="c3cb5-114">**Соединение агента с издателем**</span><span class="sxs-lookup"><span data-stu-id="c3cb5-114">**Agent Connection to the Publisher**</span></span>  
 <span data-ttu-id="c3cb5-115">Укажите контекст, в котором следующие агенты выполняют соединения распространителя с издателем.</span><span class="sxs-lookup"><span data-stu-id="c3cb5-115">Specify the context under which the following agents make connections from the Distributor to the Publisher:</span></span>  
  
-   <span data-ttu-id="c3cb5-116">Агент чтения очереди для публикаций транзакций, допускающих подписки, обновляемые посредством очередей.</span><span class="sxs-lookup"><span data-stu-id="c3cb5-116">The Queue Reader Agent for transactional publications that allow queued updating subscriptions.</span></span>  
  
-   <span data-ttu-id="c3cb5-117">Агент моментальных снимков и агент чтения журнала для публикаций Oracle.</span><span class="sxs-lookup"><span data-stu-id="c3cb5-117">The Snapshot Agent and Log Reader Agent for Oracle publications.</span></span>  
  
 <span data-ttu-id="c3cb5-118">Выберите **Выполнять олицетворение учетной записи процесса агента** для соединения с издателем при помощи контекста учетной записи [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, с которой работают эти агенты, или выберите **Проверка подлинности SQL Server**и введите **Имя входа** и **Пароль**.</span><span class="sxs-lookup"><span data-stu-id="c3cb5-118">Select **Impersonate agent process account** to make connections to the Publisher using the context of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which these agents run, or specify **SQL Server Authentication**, and then enter a value for **Login** and **Password**.</span></span> <span data-ttu-id="c3cb5-119">Рекомендуется выбрать **Выполнять олицетворение учетной записи процесса агента**.</span><span class="sxs-lookup"><span data-stu-id="c3cb5-119">It is recommended that you select **Impersonate agent process account**.</span></span> <span data-ttu-id="c3cb5-120">Дополнительные сведения о безопасности агента см. в статье [Модель безопасности агента репликации](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="c3cb5-120">For more information on agent security, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
 <span data-ttu-id="c3cb5-121">Учетные записи Windows, с которыми работают эти агенты, задаются в мастере создания публикаций.</span><span class="sxs-lookup"><span data-stu-id="c3cb5-121">The Windows accounts under which these agents run are specified in the New Publication Wizard.</span></span> <span data-ttu-id="c3cb5-122">Эти учетные записи могут быть изменены двумя способами.</span><span class="sxs-lookup"><span data-stu-id="c3cb5-122">These accounts can be changed:</span></span>  
  
-   <span data-ttu-id="c3cb5-123">В диалоговом окне **Свойства распространителя** для агента чтения очереди.</span><span class="sxs-lookup"><span data-stu-id="c3cb5-123">In the **Distributor Properties** dialog box for the Queue Reader Agent.</span></span>  
  
-   <span data-ttu-id="c3cb5-124">В диалоговом окне **Свойства публикации** для агента моментальных снимков и агента чтения журнала.</span><span class="sxs-lookup"><span data-stu-id="c3cb5-124">In the **Publication Properties** dialog box for the Snapshot Agent and Log Reader Agent.</span></span>  
  
 <span data-ttu-id="c3cb5-125">**Прочее**</span><span class="sxs-lookup"><span data-stu-id="c3cb5-125">**Miscellaneous**</span></span>  
 <span data-ttu-id="c3cb5-126">Свойства **Тип издателя** и **Имя базы данных распространителя** доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="c3cb5-126">The properties **Publisher Type** and **Distribution Database Name** are read-only.</span></span> <span data-ttu-id="c3cb5-127">Свойство **Папка моментальных снимков по умолчанию** может быть изменено.</span><span class="sxs-lookup"><span data-stu-id="c3cb5-127">The property **Default Snapshot Folder** can be changed.</span></span> <span data-ttu-id="c3cb5-128">Дополнительные сведения о папке моментальных снимков см. в статье [Организация безопасности папки моментальных снимков](security/secure-the-snapshot-folder.md).</span><span class="sxs-lookup"><span data-stu-id="c3cb5-128">For more information about the snapshot folder, see [Secure the Snapshot Folder](security/secure-the-snapshot-folder.md).</span></span>  
  

## <a name="publication-databases"></a><span data-ttu-id="c3cb5-129">Базы данных публикации</span><span class="sxs-lookup"><span data-stu-id="c3cb5-129">Publication Databases</span></span>
  <span data-ttu-id="c3cb5-130">Страница **Базы данных публикации** диалогового окна **Свойства издателя** позволяет пользователю в предопределенной роли сервера **sysadmin** включить базы данных для репликации.</span><span class="sxs-lookup"><span data-stu-id="c3cb5-130">The **Publication Databases** page of the **Publisher Properties** dialog box allows a user in the **sysadmin** fixed server role to enable databases for replication.</span></span> <span data-ttu-id="c3cb5-131">Включение базы данных не приводит к публикации базы данных, но позволяет любому пользователю в предопределенной роли базы данных **db_owner** создать одну или несколько публикаций этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="c3cb5-131">Enabling a database does not publish that database; rather, it allows any user in the **db_owner** fixed database role for that database to create one or more publications on the database.</span></span>  
  
### <a name="options"></a><span data-ttu-id="c3cb5-132">Параметры</span><span class="sxs-lookup"><span data-stu-id="c3cb5-132">Options</span></span>  
 <span data-ttu-id="c3cb5-133">**Транзакционная**</span><span class="sxs-lookup"><span data-stu-id="c3cb5-133">**Transactional**</span></span>  
 <span data-ttu-id="c3cb5-134">Установите этот флажок, чтобы пользователи в предопределенной роли базы данных **db_owner** могли создавать публикации моментальных снимков или публикации транзакций в базе данных.</span><span class="sxs-lookup"><span data-stu-id="c3cb5-134">Select this check box to allow users in the **db_owner** fixed database role to create snapshot publications or transactional publications in the database.</span></span> 
  
 <span data-ttu-id="c3cb5-135">**Объединить**</span><span class="sxs-lookup"><span data-stu-id="c3cb5-135">**Merge**</span></span>  
 <span data-ttu-id="c3cb5-136">Установите этот флажок, чтобы пользователи в предопределенной роли базы данных **db_owner** могли создавать публикации слиянием в базе данных.</span><span class="sxs-lookup"><span data-stu-id="c3cb5-136">Select this check box to allow users in the **db_owner** fixed database role to create merge publications in the database.</span></span>  

## <a name="subscribers"></a><span data-ttu-id="c3cb5-137">Подписчики</span><span class="sxs-lookup"><span data-stu-id="c3cb5-137">Subscribers</span></span>

  <span data-ttu-id="c3cb5-138">Страница **Подписчики** диалогового окна **Свойства издателя** используется для издателей, использующих версии [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], более ранние, чем [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3cb5-138">The **Subscribers** page of the **Publisher Properties** dialog box is used for Publishers running versions of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="c3cb5-139">Эта страница дает возможность включить получение данных подписчиками из публикаций на данном издателе.</span><span class="sxs-lookup"><span data-stu-id="c3cb5-139">The page allows you to enable Subscribers to receive data from publications on this Publisher.</span></span> <span data-ttu-id="c3cb5-140">Включение получения данных подписчиком от данного издателя не создает подписки на публикации на данном издателе.</span><span class="sxs-lookup"><span data-stu-id="c3cb5-140">Enabling a Subscriber to receive data from this Publisher does not create subscriptions to publications on this Publisher.</span></span> <span data-ttu-id="c3cb5-141">Для создания подписки нужно использовать мастер создания подписки.</span><span class="sxs-lookup"><span data-stu-id="c3cb5-141">To create a subscription, you must use the New Subscription Wizard.</span></span>  
  
### <a name="options"></a><span data-ttu-id="c3cb5-142">Параметры</span><span class="sxs-lookup"><span data-stu-id="c3cb5-142">Options</span></span>  
 <span data-ttu-id="c3cb5-143">**Подписчики**</span><span class="sxs-lookup"><span data-stu-id="c3cb5-143">**Subscribers**</span></span>  
 <span data-ttu-id="c3cb5-144">Сетка свойств **Подписчики** отображает подписчиков, для которых включено получение данных из публикаций на данном издателе.</span><span class="sxs-lookup"><span data-stu-id="c3cb5-144">The **Subscribers** property grid shows Subscribers that are enabled to receive data from publications on this Publisher.</span></span> <span data-ttu-id="c3cb5-145">Нажмите кнопку свойств **(...)** рядом с подписчиком для просмотра и установки дополнительных свойств.</span><span class="sxs-lookup"><span data-stu-id="c3cb5-145">Click the properties button (**...**) next to a Subscriber to view and set additional properties.</span></span>  
  
 <span data-ttu-id="c3cb5-146">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="c3cb5-146">**Add**</span></span>  
 <span data-ttu-id="c3cb5-147">Нажмите кнопку **Добавить** для добавления подписчика, а затем выберите пункт **Добавить подписчик SQL Server** или **Добавить подписчик, отличный от подписчика SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="c3cb5-147">Click **Add** to add a Subscriber, and then click **Add SQL Server Subscriber** or **Add Non-SQL Server Subscriber**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="c3cb5-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="c3cb5-148">See Also</span></span>  
 [<span data-ttu-id="c3cb5-149">Просмотр и изменение свойств издателя и распространителя</span><span class="sxs-lookup"><span data-stu-id="c3cb5-149">View and Modify Distributor and Publisher Properties</span></span>](view-and-modify-distributor-and-publisher-properties.md)   

  
  
