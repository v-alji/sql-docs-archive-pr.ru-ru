---
title: Настройка задания набора транзакций для издателя Oracle (программирование репликации на языке Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- sp_publisherproperty
- Oracle publishing [SQL Server replication], configuring
ms.assetid: beea1a5c-0053-4971-a68f-0da53063fcbb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 43a25ce755a505f0efd7c25243b8969a962ea701
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750788"
---
# <a name="configure-the-transaction-set-job-for-an-oracle-publisher-replication-transact-sql-programming"></a><span data-ttu-id="bf9f5-102">настроить задание набора транзакции для издателя Oracle (программирование репликации на языке Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="bf9f5-102">Configure the Transaction Set Job for an Oracle Publisher (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="bf9f5-103">**Xactset** – это задание базы данных Oracle, создаваемое репликацией, которая выполняется на издателе Oracle и создает наборы транзакций, когда агент чтения журнала не подключен к издателю.</span><span class="sxs-lookup"><span data-stu-id="bf9f5-103">The **Xactset** job is an Oracle database job created by replication that runs at an Oracle Publisher to create transaction sets when the Log Reader Agent is not connected to the Publisher.</span></span> <span data-ttu-id="bf9f5-104">Включить и настроить это задание можно программным способом с распространителя с помощью хранимых процедур репликации.</span><span class="sxs-lookup"><span data-stu-id="bf9f5-104">You can enable and configure this job from the Distributor programmatically using replication stored procedures.</span></span> <span data-ttu-id="bf9f5-105">Дополнительные сведения см. в статье [Настройка производительности для издателей Oracle](../non-sql/performance-tuning-for-oracle-publishers.md).</span><span class="sxs-lookup"><span data-stu-id="bf9f5-105">For more information, see [Performance Tuning for Oracle Publishers](../non-sql/performance-tuning-for-oracle-publishers.md).</span></span>  
  
### <a name="to-enable-the-transaction-set-job"></a><span data-ttu-id="bf9f5-106">Включение задания наборов транзакций</span><span class="sxs-lookup"><span data-stu-id="bf9f5-106">To enable the transaction set job</span></span>  
  
1.  <span data-ttu-id="bf9f5-107">На издателе Oracle задайте достаточно большое значение параметра инициализации **job_queue_processes** , чтобы могло выполняться задание «Xactset».</span><span class="sxs-lookup"><span data-stu-id="bf9f5-107">At the Oracle Publisher, set the **job_queue_processes** initialization parameter to a sufficient value to allow the Xactset job run.</span></span> <span data-ttu-id="bf9f5-108">Дополнительные сведения об этом параметре см. в документации по базе данных для издателя Oracle.</span><span class="sxs-lookup"><span data-stu-id="bf9f5-108">For more information about this parameter, see the database documentation for the Oracle Publisher.</span></span>  
  
2.  <span data-ttu-id="bf9f5-109">На распространителе выполните хранимую процедуру [sp_publisherproperty (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bf9f5-109">At the Distributor, execute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span></span> <span data-ttu-id="bf9f5-110">Укажите имя издателя Oracle для \*\* \@ издателя**, значение `xactsetbatching` для \*\* \@ PropertyName**и значение `enabled` для параметра \*\* \@ propertyvalue\*\*.</span><span class="sxs-lookup"><span data-stu-id="bf9f5-110">Specify the name of the Oracle Publisher for **\@publisher**, a value of `xactsetbatching` for **\@propertyname**, and a value of `enabled` for **\@propertyvalue**.</span></span>  
  
3.  <span data-ttu-id="bf9f5-111">На распространителе выполните хранимую процедуру [sp_publisherproperty (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bf9f5-111">At the Distributor, execute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span></span> <span data-ttu-id="bf9f5-112">Укажите имя издателя Oracle для \*\* \@ издателя**, значение `xactsetjobinterval` для \*\* \@ PropertyName**и интервал задания в минутах для \*\* \@ propertyvalue\*\*.</span><span class="sxs-lookup"><span data-stu-id="bf9f5-112">Specify the name of the Oracle Publisher for **\@publisher**, a value of `xactsetjobinterval` for **\@propertyname**, and the job interval, in minutes, for **\@propertyvalue**.</span></span>  
  
4.  <span data-ttu-id="bf9f5-113">На распространителе выполните хранимую процедуру [sp_publisherproperty (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bf9f5-113">At the Distributor, execute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span></span> <span data-ttu-id="bf9f5-114">Укажите имя издателя Oracle для \*\* \@ издателя**, значение `xactsetjob` для \*\* \@ PropertyName**и значение `enabled` для параметра \*\* \@ propertyvalue\*\*.</span><span class="sxs-lookup"><span data-stu-id="bf9f5-114">Specify the name of the Oracle Publisher for **\@publisher**, a value of `xactsetjob` for **\@propertyname**, and a value of `enabled` for **\@propertyvalue**.</span></span>  
  
### <a name="to-configure-the-transaction-set-job"></a><span data-ttu-id="bf9f5-115">Настройка задания набора транзакций</span><span class="sxs-lookup"><span data-stu-id="bf9f5-115">To configure the transaction set job</span></span>  
  
1.  <span data-ttu-id="bf9f5-116">На распространителе выполните хранимую процедуру [sp_publisherproperty (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql) (необязательно).</span><span class="sxs-lookup"><span data-stu-id="bf9f5-116">(Optional) At the Distributor, execute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span></span> <span data-ttu-id="bf9f5-117">В параметре **\@publisher** укажите имя издателя Oracle.</span><span class="sxs-lookup"><span data-stu-id="bf9f5-117">Specify the name of the Oracle Publisher for **\@publisher**.</span></span> <span data-ttu-id="bf9f5-118">Система выдаст свойства задания **Xactset** на издателе.</span><span class="sxs-lookup"><span data-stu-id="bf9f5-118">This returns properties of the **Xactset** job at the Publisher.</span></span>  
  
2.  <span data-ttu-id="bf9f5-119">На распространителе выполните хранимую процедуру [sp_publisherproperty (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bf9f5-119">At the Distributor, execute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span></span> <span data-ttu-id="bf9f5-120">Укажите имя издателя Oracle для \*\* \@ издателя**, имя свойства задания набора транзакций, устанавливаемое для \*\* \@ PropertyName**, и новый параметр для \*\* \@ propertyvalue\*\*.</span><span class="sxs-lookup"><span data-stu-id="bf9f5-120">Specify the name of the Oracle Publisher for **\@publisher**, the name of the Xactset job property being set for **\@propertyname**, and new setting for **\@propertyvalue**.</span></span>  
  
3.  <span data-ttu-id="bf9f5-121">Повторите шаг 2 для каждого устанавливаемого свойства задания набора транзакций (необязательно).</span><span class="sxs-lookup"><span data-stu-id="bf9f5-121">(Optional) Repeat step 2 for each Xactset job property being set.</span></span> <span data-ttu-id="bf9f5-122">При изменении `xactsetjobinterval` свойства необходимо перезапустить задание на издателе Oracle, чтобы новый интервал вступил в силу.</span><span class="sxs-lookup"><span data-stu-id="bf9f5-122">When changing the `xactsetjobinterval` property, you must restart the job on the Oracle Publisher for the new interval to take effect.</span></span>  
  
### <a name="to-view-properties-of-the-transaction-set-job"></a><span data-ttu-id="bf9f5-123">Просмотр свойств задания набора транзакций</span><span class="sxs-lookup"><span data-stu-id="bf9f5-123">To view properties of the transaction set job</span></span>  
  
1.  <span data-ttu-id="bf9f5-124">На распространителе выполните процедуру [sp_helpxactsetjob](/sql/relational-databases/system-stored-procedures/sp-helpxactsetjob-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bf9f5-124">At the Distributor, execute [sp_helpxactsetjob](/sql/relational-databases/system-stored-procedures/sp-helpxactsetjob-transact-sql).</span></span> <span data-ttu-id="bf9f5-125">В параметре **\@publisher** укажите имя издателя Oracle.</span><span class="sxs-lookup"><span data-stu-id="bf9f5-125">Specify the name of the Oracle Publisher for **\@publisher**.</span></span>  
  
### <a name="to-disable-the-transaction-set-job"></a><span data-ttu-id="bf9f5-126">Отключение задания набора транзакций</span><span class="sxs-lookup"><span data-stu-id="bf9f5-126">To disable the transaction set job</span></span>  
  
1.  <span data-ttu-id="bf9f5-127">На распространителе выполните хранимую процедуру [sp_publisherproperty (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bf9f5-127">At the Distributor, execute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span></span> <span data-ttu-id="bf9f5-128">Укажите имя издателя Oracle для \*\* \@ издателя**, значение `xactsetjob` для \*\* \@ PropertyName**и значение `disabled` для параметра \*\* \@ propertyvalue\*\*.</span><span class="sxs-lookup"><span data-stu-id="bf9f5-128">Specify the name of the Oracle Publisher for **\@publisher**, a value of `xactsetjob` for **\@propertyname**, and a value of `disabled` for **\@propertyvalue**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf9f5-129">Пример</span><span class="sxs-lookup"><span data-stu-id="bf9f5-129">Example</span></span>  
 <span data-ttu-id="bf9f5-130">В следующем примере включается задание `Xactset` и устанавливается интервал запуска, равный трем минутам.</span><span class="sxs-lookup"><span data-stu-id="bf9f5-130">The following example enables the `Xactset` job and sets an interval of three minutes between runs.</span></span>  
  
 [!code-sql[HowTo#sp_enable_xactsetjob](../../../snippets/tsql/SQL15/replication/howto/tsql/enablexactsetjob.sql#sp_enable_xactsetjob)]  
  
## <a name="see-also"></a><span data-ttu-id="bf9f5-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="bf9f5-131">See Also</span></span>  
 <span data-ttu-id="bf9f5-132">[Настройка производительности для издателей Oracle](../non-sql/performance-tuning-for-oracle-publishers.md) </span><span class="sxs-lookup"><span data-stu-id="bf9f5-132">[Performance Tuning for Oracle Publishers](../non-sql/performance-tuning-for-oracle-publishers.md) </span></span>  
 [<span data-ttu-id="bf9f5-133">Replication System Stored Procedures Concepts</span><span class="sxs-lookup"><span data-stu-id="bf9f5-133">Replication System Stored Procedures Concepts</span></span>](../concepts/replication-system-stored-procedures-concepts.md)  
  
  
