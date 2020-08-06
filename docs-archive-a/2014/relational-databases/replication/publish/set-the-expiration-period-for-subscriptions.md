---
title: Установка срока действия подписок | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- subscriptions [SQL Server replication], expiration
- expiration [SQL Server replication]
- retention periods [SQL Server replication]
- deactivating subscriptions
ms.assetid: 542f0613-5817-42d0-b841-fb2c94010665
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bc0ecb449af64b88cf3ded032c78c2e399dd4234
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664867"
---
# <a name="set-the-expiration-period-for-subscriptions"></a><span data-ttu-id="424d8-102">Установка срока действия подписок</span><span class="sxs-lookup"><span data-stu-id="424d8-102">Set the Expiration Period for Subscriptions</span></span>
  <span data-ttu-id="424d8-103">В этом разделе описывается установка срока действия подписок в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="424d8-103">This topic describes how to set the expiration period for subscriptions in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="424d8-104">Срок действия подписок определяет период времени до истечения и удаления подписки.</span><span class="sxs-lookup"><span data-stu-id="424d8-104">The expiration period for subscriptions determines the period of time before a subscription expires and is removed.</span></span> <span data-ttu-id="424d8-105">Дополнительные сведения см. в разделе [Subscription Expiration and Deactivation](../subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="424d8-105">For more information, see [Subscription Expiration and Deactivation](../subscription-expiration-and-deactivation.md).</span></span>  
  
 <span data-ttu-id="424d8-106">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="424d8-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="424d8-107">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="424d8-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="424d8-108">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="424d8-108">Recommendations</span></span>](#Recommendations)  
  
-   <span data-ttu-id="424d8-109">**Для установки срока действия подписок используется:**</span><span class="sxs-lookup"><span data-stu-id="424d8-109">**To set the expiration period for subscriptions, using:**</span></span>  
  
     [<span data-ttu-id="424d8-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="424d8-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="424d8-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="424d8-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="424d8-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="424d8-112">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="424d8-113">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="424d8-113">Recommendations</span></span>  
  
-   <span data-ttu-id="424d8-114">Срок действия подписки также может называться *сроком хранения публикации*.</span><span class="sxs-lookup"><span data-stu-id="424d8-114">The subscription expiration period is also referred to as the *publication retention period*.</span></span> <span data-ttu-id="424d8-115">Очистка метаданных репликации слиянием зависит от этой настройки:</span><span class="sxs-lookup"><span data-stu-id="424d8-115">Cleanup of merge replication metadata is dependent on this setting:</span></span>  
  
    -   <span data-ttu-id="424d8-116">Репликации не удастся очистить метаданные в базах данных публикации и подписки, пока не закончится срок хранения.</span><span class="sxs-lookup"><span data-stu-id="424d8-116">Replication cannot clean up metadata in the publication and subscription databases until the retention period is reached.</span></span> <span data-ttu-id="424d8-117">Будьте осмотрительны при указании больших значений срока хранения, так как они могут негативно сказываться на производительности репликации.</span><span class="sxs-lookup"><span data-stu-id="424d8-117">Use caution in specifying a high value for the retention period, because it can negatively impact replication performance.</span></span> <span data-ttu-id="424d8-118">Рекомендуется использовать небольшие значения, если можно надежно предсказать, что все подписчики будут синхронизироваться регулярно в течение указанного периода времени.</span><span class="sxs-lookup"><span data-stu-id="424d8-118">It is recommended that you use a lower setting if you can reliably predict that all Subscribers will synchronize regularly within that time period.</span></span>  
  
         <span data-ttu-id="424d8-119">Срок хранения для публикаций слиянием содержит 24-часовой льготный период для размещения подписчиков в разных часовых поясах.</span><span class="sxs-lookup"><span data-stu-id="424d8-119">The retention period for merge publications has a 24-hour grace period to accommodate Subscribers in different time zones.</span></span> <span data-ttu-id="424d8-120">Например, если установить срок хранения продолжительностью в один день, то действительный срок хранения будет равен 48 часам.</span><span class="sxs-lookup"><span data-stu-id="424d8-120">If, for example, you set a retention period of one day, the actual retention period is 48 hours.</span></span>  
  
    -   <span data-ttu-id="424d8-121">Можно задать неограниченный срок действия подписок, но настоятельно рекомендуется не использовать такое значение, так как нельзя будет очистить метаданные.</span><span class="sxs-lookup"><span data-stu-id="424d8-121">It is possible to specify that subscriptions never expire, but it is strongly recommended that you do not use this value, because metadata cannot be cleaned up.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="424d8-122">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="424d8-122">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="424d8-123">Установите срок действия для подписок на странице **Общее** диалогового окна **Свойства публикации — \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="424d8-123">Set the expiration period for subscriptions on the **General** page of the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="424d8-124">Дополнительные сведения о доступе к этому диалоговому окну см. в разделе [Просмотр и изменение свойств публикации](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="424d8-124">For more information about accessing this dialog box, see [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span>  
  
#### <a name="to-set-the-expiration-period-for-subscriptions"></a><span data-ttu-id="424d8-125">Установка срока действия подписок</span><span class="sxs-lookup"><span data-stu-id="424d8-125">To set the expiration period for subscriptions</span></span>  
  
1.  <span data-ttu-id="424d8-126">В разделе **Окончание действия подписки** на странице **Общее** диалогового окна **Свойства публикации — \<Publication>** укажите, имеет ли подписка срок действия.</span><span class="sxs-lookup"><span data-stu-id="424d8-126">In the **Subscription expiration** section on the **General** page of the **Publication Properties - \<Publication>** dialog box, specify whether subscriptions should expire.</span></span>  
  
2.  <span data-ttu-id="424d8-127">Если срок действия подписок должен быть ограничен, задайте время, по истечении которого подписки перестают действовать.</span><span class="sxs-lookup"><span data-stu-id="424d8-127">If they should expire, specify an expiration time period.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="424d8-128">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="424d8-128">Using Transact-SQL</span></span>  
 <span data-ttu-id="424d8-129">Можно использовать хранимые процедуры репликации, чтобы задать это значение при создании публикации, либо изменить это значение позднее.</span><span class="sxs-lookup"><span data-stu-id="424d8-129">You can use replication stored procedures to either set this value when a publication is created or modify this value at a later time.</span></span>  
  
#### <a name="to-set-the-expiration-period-for-a-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="424d8-130">Настройка срока действия подписки на моментальный снимок или публикацию транзакций</span><span class="sxs-lookup"><span data-stu-id="424d8-130">To set the expiration period for a subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="424d8-131">Выполните процедуру [sp_addpublication](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql)на издателе.</span><span class="sxs-lookup"><span data-stu-id="424d8-131">At the Publisher, execute [sp_addpublication](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql).</span></span> <span data-ttu-id="424d8-132">Укажите нужный срок действия подписки в часах в параметре **\@retention**.</span><span class="sxs-lookup"><span data-stu-id="424d8-132">Specify the desired subscription expiration period, in hours, for **\@retention**.</span></span> <span data-ttu-id="424d8-133">По умолчанию срок хранения равен 336 часам.</span><span class="sxs-lookup"><span data-stu-id="424d8-133">The default expiration period is 336 hours.</span></span> <span data-ttu-id="424d8-134">Дополнительные сведения см. в разделе [Create a Publication](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="424d8-134">For more information, see [Create a Publication](create-a-publication.md).</span></span>  
  
#### <a name="to-set-the-expiration-period-for-a-subscription-to-a-merge-publication"></a><span data-ttu-id="424d8-135">Настройка срока действия подписки на публикацию слиянием</span><span class="sxs-lookup"><span data-stu-id="424d8-135">To set the expiration period for a subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="424d8-136">Выполните процедуру [sp_addmergepublication](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql)на издателе.</span><span class="sxs-lookup"><span data-stu-id="424d8-136">At the Publisher, execute [sp_addmergepublication](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql).</span></span> <span data-ttu-id="424d8-137">Укажите нужный срок действия подписки в параметре **\@retention**.</span><span class="sxs-lookup"><span data-stu-id="424d8-137">Specify the desired value for the subscription expiration period for **\@retention**.</span></span> <span data-ttu-id="424d8-138">Укажите единицы измерения, в которых выражается период хранения, в параметре **\@retention_period_unit**. Возможны следующие варианты:</span><span class="sxs-lookup"><span data-stu-id="424d8-138">Specify the units in which the expiration period is expressed for **\@retention_period_unit**, which can be one of the following:</span></span>  
  
    -   <span data-ttu-id="424d8-139">**1** = Неделя</span><span class="sxs-lookup"><span data-stu-id="424d8-139">**1** = week</span></span>  
  
    -   <span data-ttu-id="424d8-140">**2** = Месяц</span><span class="sxs-lookup"><span data-stu-id="424d8-140">**2** = month</span></span>  
  
    -   <span data-ttu-id="424d8-141">**3** = Год</span><span class="sxs-lookup"><span data-stu-id="424d8-141">**3** = year</span></span>  
  
     <span data-ttu-id="424d8-142">По умолчанию срок хранения равен 14 дням.</span><span class="sxs-lookup"><span data-stu-id="424d8-142">The default expiration period is 14 days.</span></span> <span data-ttu-id="424d8-143">Дополнительные сведения см. в разделе [Create a Publication](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="424d8-143">For more information, see [Create a Publication](create-a-publication.md).</span></span>  
  
#### <a name="to-change-the-expiration-period-for-a-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="424d8-144">Изменение срока действия подписки на моментальный снимок или публикацию транзакций</span><span class="sxs-lookup"><span data-stu-id="424d8-144">To change the expiration period for a subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="424d8-145">На издателе выполните хранимую процедуру [sp_changepublication](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="424d8-145">At the Publisher, execute [sp_changepublication](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql).</span></span> <span data-ttu-id="424d8-146">Укажите значение **retention** в параметре **\@property** и новый срок действия подписки в часах в параметре **\@value**.</span><span class="sxs-lookup"><span data-stu-id="424d8-146">Specify **retention** for **\@property** and the new subscription expiration period, in hours, for **\@value**.</span></span>  
  
#### <a name="to-change-the-expiration-period-for-a-subscription-to-a-merge-publication"></a><span data-ttu-id="424d8-147">Изменение срока действия подписки на публикацию слиянием</span><span class="sxs-lookup"><span data-stu-id="424d8-147">To change the expiration period for a subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="424d8-148">В издателе выполните хранимую процедуру [sp_helpmergepublication](/sql/relational-databases/system-stored-procedures/sp-helpmergepublication-transact-sql), указав параметры **\@publication** и **\@publisher**.</span><span class="sxs-lookup"><span data-stu-id="424d8-148">At the Publisher, execute [sp_helpmergepublication](/sql/relational-databases/system-stored-procedures/sp-helpmergepublication-transact-sql), specifying **\@publication** and **\@publisher**.</span></span> <span data-ttu-id="424d8-149">Запомните значение **retention_period_unit** в результирующем наборе, которое может быть одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="424d8-149">Note the value of **retention_period_unit** in the result set, which can be one of the following:</span></span>  
  
    -   <span data-ttu-id="424d8-150">**0** = сутки;</span><span class="sxs-lookup"><span data-stu-id="424d8-150">**0** = day</span></span>  
  
    -   <span data-ttu-id="424d8-151">**1** = Неделя</span><span class="sxs-lookup"><span data-stu-id="424d8-151">**1** = week</span></span>  
  
    -   <span data-ttu-id="424d8-152">**2** = Месяц</span><span class="sxs-lookup"><span data-stu-id="424d8-152">**2** = month</span></span>  
  
    -   <span data-ttu-id="424d8-153">**3** = Год</span><span class="sxs-lookup"><span data-stu-id="424d8-153">**3** = year</span></span>  
  
2.  <span data-ttu-id="424d8-154">На издателе выполните хранимую процедуру [sp_changemergepublication](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="424d8-154">At the Publisher, execute [sp_changemergepublication](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span></span> <span data-ttu-id="424d8-155">Укажите значение **retention** в параметре **\@property** и новый срок действия подписки в виде текста на основе единицы измерения срока хранения из шага 1 в параметре **\@value**.</span><span class="sxs-lookup"><span data-stu-id="424d8-155">Specify **retention** for **\@property** and the new subscription expiration period, as text based on the retention period unit from step 1, for **\@value**.</span></span>  
  
3.  <span data-ttu-id="424d8-156">(Необязательно) На издателе выполните хранимую процедуру [sp_changemergepublication](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="424d8-156">(Optional) At the Publisher, execute [sp_changemergepublication](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span></span> <span data-ttu-id="424d8-157">Укажите значение **retention_period_unit** в параметре **\@property** и новую единицу измерения для срока действия подписки в параметре **\@value**.</span><span class="sxs-lookup"><span data-stu-id="424d8-157">Specify **retention_period_unit** for **\@property** and a new unit for the subscription expiration period for **\@value**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="424d8-158">См. также:</span><span class="sxs-lookup"><span data-stu-id="424d8-158">See Also</span></span>  
 <span data-ttu-id="424d8-159">[Replication System Stored Procedures Concepts](../concepts/replication-system-stored-procedures-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="424d8-159">[Replication System Stored Procedures Concepts](../concepts/replication-system-stored-procedures-concepts.md) </span></span>  
 [<span data-ttu-id="424d8-160">Окончание срока действия и отключение подписки</span><span class="sxs-lookup"><span data-stu-id="424d8-160">Subscription Expiration and Deactivation</span></span>](../subscription-expiration-and-deactivation.md)  
  
  
