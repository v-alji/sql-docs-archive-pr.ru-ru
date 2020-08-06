---
title: Определение способа распространения изменений для статей транзакций | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- transactional replication, propagation methods
ms.assetid: a10c5001-22cc-4667-8f0b-3d0818dca2e9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 72d377ba89f1d393eab48bd9c918012b0f503f9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731501"
---
# <a name="specify-how-changes-are-propagated-for-transactional-articles"></a><span data-ttu-id="3f1fd-102">Указание способа распространения изменений для статей транзакций</span><span class="sxs-lookup"><span data-stu-id="3f1fd-102">Specify How Changes Are Propagated for Transactional Articles</span></span>
  <span data-ttu-id="3f1fd-103">Репликация транзакций позволяет указывать, как изменения данных распространяются от издателя к подписчикам.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-103">Transactional replication allows you to specify how data changes are propagated from the Publisher to Subscribers.</span></span> <span data-ttu-id="3f1fd-104">Для каждой опубликованной таблицы можно указать один из четырех способов, которым каждая операция (INSERT, UPDATE или DELETE) должна распространяться на подписчик:</span><span class="sxs-lookup"><span data-stu-id="3f1fd-104">For each published table, you can specify one of four ways that each operation (INSERT, UPDATE, or DELETE) should be propagated to the Subscriber:</span></span>  
  
-   <span data-ttu-id="3f1fd-105">Укажите, что репликации транзакций следует создать скрипт и затем вызвать хранимую процедуру для распространения изменений на подписчики (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="3f1fd-105">Specify that transactional replication should script out and subsequently call a stored procedure to propagate changes to Subscribers (the default).</span></span>  
  
-   <span data-ttu-id="3f1fd-106">Укажите, что изменение должно распространяться с помощью инструкции INSERT, UPDATE или DELETE (по умолчанию для подписчиков, отличных от[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="3f1fd-106">Specify that the change should be propagated using an INSERT, UPDATE, or DELETE statement (the default for non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Subscribers).</span></span>  
  
-   <span data-ttu-id="3f1fd-107">Укажите, что должна использоваться пользовательская хранимая процедура.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-107">Specify that a custom stored procedure should be used.</span></span>  
  
-   <span data-ttu-id="3f1fd-108">Укажите, что данное действие не должно выполняться на любом подписчике.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-108">Specify that this action should not be performed at any Subscriber.</span></span> <span data-ttu-id="3f1fd-109">Транзакции этого типа не реплицируются.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-109">Transactions of that type are not replicated.</span></span>  
  
 <span data-ttu-id="3f1fd-110">По умолчанию, репликация транзакций распространяет изменения на подписчики при помощи набора хранимых процедур, установленных на каждом подписчике.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-110">By default, transactional replication propagates changes to Subscribers through a set of stored procedures that are installed on each Subscriber.</span></span> <span data-ttu-id="3f1fd-111">Операции вставки, обновления или удаления в таблице издателя преобразовываются в вызовы хранимой процедуры на подписчике.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-111">When an insert, update or delete occurs on a table at the Publisher, the operation is translated into a call to a stored procedure at the Subscriber.</span></span> <span data-ttu-id="3f1fd-112">Хранимая процедура принимает параметры, которые соответствуют столбцам в таблице, допуская изменение этих столбцов в подписчике.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-112">The stored procedure accepts parameters that map to the columns in the table, allowing those columns to be changed at the Subscriber.</span></span>  
  
 <span data-ttu-id="3f1fd-113">Чтобы настроить метод распространения изменений данных в статьях транзакций, см. раздел [Задание метода распространения изменений данных в транзакционные статьи](../publish/set-the-propagation-method-for-data-changes-to-transactional-articles.md).</span><span class="sxs-lookup"><span data-stu-id="3f1fd-113">To set the propagation method for data changes to transactional articles, see [Set the Propagation Method for Data Changes to Transactional Articles](../publish/set-the-propagation-method-for-data-changes-to-transactional-articles.md).</span></span>  
  
## <a name="default-and-custom-stored-procedures"></a><span data-ttu-id="3f1fd-114">Стандартные и пользовательские хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="3f1fd-114">Default and custom stored procedures</span></span>  
 <span data-ttu-id="3f1fd-115">Три процедуры, создаваемые репликацией по умолчанию для каждой статьи таблицы:</span><span class="sxs-lookup"><span data-stu-id="3f1fd-115">The three procedures that replication creates by default for each table article are:</span></span>  
  
-   <span data-ttu-id="3f1fd-116">**sp_MSins_\<** *tablename* **>** , обрабатывающая операции вставки;</span><span class="sxs-lookup"><span data-stu-id="3f1fd-116">**sp_MSins_\<** *tablename* **>**, which handles inserts.</span></span>  
  
-   <span data-ttu-id="3f1fd-117">**sp_MSupd_\<** *tablename* **>** , обрабатывающая операции обновления;</span><span class="sxs-lookup"><span data-stu-id="3f1fd-117">**sp_MSupd_\<** *tablename* **>**, which handles updates.</span></span>  
  
-   <span data-ttu-id="3f1fd-118">**sp_MSdel_\<** *tablename* **>** , обрабатывающая операции удаления.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-118">**sp_MSdel_\<** *tablename* **>**, which handles deletes.</span></span>  
  
 <span data-ttu-id="3f1fd-119">Используемое в процедуре **\<***tablename***>** зависит от того, как статья была добавлена в публикацию и содержит ли база данных подписки таблицу с тем же именем, принадлежащую другому владельцу.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-119">The **\<***tablename***>** used in the procedure depends on how the article was added to the publication and whether the subscription database contains a table of the same name with a different owner.</span></span>  
  
 <span data-ttu-id="3f1fd-120">Любая из этих процедур может заменяться пользовательской процедурой, указываемой при добавлении статьи в публикацию.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-120">Any of these procedures can be replaced with a custom procedure that you specify when adding an article to a publication.</span></span> <span data-ttu-id="3f1fd-121">Пользовательские процедуры применимы, если приложению требуется пользовательская логика, такая как вставка данных в проверочную таблицу при обновлении строки в подписчике.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-121">Custom procedures are used if an application requires custom logic, such as inserting data into an audit table when a row is updated at a Subscriber.</span></span> <span data-ttu-id="3f1fd-122">Дополнительные сведения об указываемых пользовательских хранимых процедурах см. в справочных разделах, перечисленных выше.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-122">For more information about specifying custom stored procedures, see the how to topics listed above.</span></span>  
  
 <span data-ttu-id="3f1fd-123">Если указываются стандартные или пользовательские процедуры репликации, указывается также синтаксис вызова для каждой процедуры (при использовании процедур по умолчанию репликация выбирает умолчания).</span><span class="sxs-lookup"><span data-stu-id="3f1fd-123">If you specify the default replication procedures or custom procedures, you also specify call syntax for each procedure (replication selects defaults if you use the default procedures).</span></span> <span data-ttu-id="3f1fd-124">Синтаксис вызова определяет структуру параметров, предоставляемых процедуре, а также количество сведений, посылаемых подписчику с каждым изменением данных.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-124">The call syntax determines the structure of the parameters provided to the procedure and how much information is sent to the Subscriber with each data change.</span></span> <span data-ttu-id="3f1fd-125">Дополнительные сведения см. в подразделе «Синтаксис вызова для хранимых процедур» этого раздела.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-125">For more information, see the section "Call Syntax for Stored Procedures" in this topic.</span></span>  
  
### <a name="considerations-for-using-custom-stored-procedures"></a><span data-ttu-id="3f1fd-126">Аспекты использования пользовательских хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="3f1fd-126">Considerations for Using Custom Stored Procedures</span></span>  
 <span data-ttu-id="3f1fd-127">При использовании пользовательских хранимых процедур примите во внимание следующие соображения:</span><span class="sxs-lookup"><span data-stu-id="3f1fd-127">Keep the following considerations in mind when using custom stored procedures:</span></span>  
  
-   <span data-ttu-id="3f1fd-128">В хранимой процедуре необходимо поддерживать логику; [!INCLUDE[msCoName](../../../includes/msconame-md.md)] не поддерживает пользовательскую логику.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-128">You must support the logic in the stored procedure; [!INCLUDE[msCoName](../../../includes/msconame-md.md)] does not provide support for custom logic.</span></span>  
  
-   <span data-ttu-id="3f1fd-129">Во избежание конфликтов с транзакциями, используемыми репликацией, явные транзакции не должны применяться в пользовательских процедурах.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-129">In order to avoid conflicts with the transactions used by replication, explicit transactions should not be used in custom procedures.</span></span>  
  
-   <span data-ttu-id="3f1fd-130">Схема в подписчике, как правило, идентична схеме в издателе, однако при использовании фильтрации столбцов схема в подписчике может быть подмножеством схемы издателя.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-130">The schema at the Subscriber is typically identical to the schema at the Publisher, but can also be a subset of the Publisher schema if column filtering is used.</span></span> <span data-ttu-id="3f1fd-131">Однако при необходимости преобразования схемы при перемещении данных так, чтобы схема на подписчике не являлась подмножеством схемы на издателе, рекомендованным решением являются службы [!INCLUDE[ssISCurrent](../../../includes/ssiscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3f1fd-131">However, if you need to transform the schema as the data is moved such that the schema on the Subscriber is not a subset of the schema on the Publisher, [!INCLUDE[ssISCurrent](../../../includes/ssiscurrent-md.md)] is the recommended solution.</span></span> <span data-ttu-id="3f1fd-132">Дополнительные сведения см. в разделе [Службы SQL Server Integration Services](../../../integration-services/sql-server-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="3f1fd-132">For more information, see [SQL Server Integration Services](../../../integration-services/sql-server-integration-services.md).</span></span>  
  
-   <span data-ttu-id="3f1fd-133">При внесении изменений схемы в опубликованную таблицу пользовательские процедуры должны быть созданы заново.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-133">If you make schema changes to a published table, the custom procedures must be regenerated.</span></span> <span data-ttu-id="3f1fd-134">Дополнительные сведения см. в статье [Повторное создание пользовательских процедур транзакций с учетом изменений в схеме](transactional-articles-regenerate-to-reflect-schema-changes.md).</span><span class="sxs-lookup"><span data-stu-id="3f1fd-134">For more information, see [Regenerate Custom Transactional Procedures to Reflect Schema Changes](transactional-articles-regenerate-to-reflect-schema-changes.md).</span></span>  
  
-   <span data-ttu-id="3f1fd-135">При использовании значений больше 1 для параметра **-SubscriptionStreams** агента распространителя убедитесь, что обновления первичных ключевых столбцов выполнены успешно.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-135">If you use a value greater than 1 for **-SubscriptionStreams** parameter of the Distribution Agent, you must ensure that updates to primary key columns are successful.</span></span> <span data-ttu-id="3f1fd-136">Пример:</span><span class="sxs-lookup"><span data-stu-id="3f1fd-136">For example:</span></span>  
  
    ```  
    update ... set pk = 2 where pk = 1 -- update 1  
    update ... set pk = 3 where pk = 2 -- update 2  
    ```  
  
     <span data-ttu-id="3f1fd-137">Если агент распространителя использует больше одного соединения, то эти два обновления могут реплицироваться через другие соединения.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-137">If the Distribution Agent uses more than one connection, these two updates might be replicated over different connections.</span></span> <span data-ttu-id="3f1fd-138">Если обновление 1 применяется первым, то проблем не существует; если первым применяется обновление 2, возвращается сообщение «0 строк затронуто», т. к. обновление 1 еще не произошло.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-138">If update 1 is applied first, there is no problem; if update 2 is applied first it will return '0 rows affected' because update 1 has not yet occurred.</span></span> <span data-ttu-id="3f1fd-139">Данная ситуация в процедурах по умолчанию вызывает ошибку, если не существует строк, затронутых при обновлении:</span><span class="sxs-lookup"><span data-stu-id="3f1fd-139">This situation is handled in the default procedures by raising an error if no rows are affected on an update:</span></span>  
  
    ```  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sys.sp_MSreplraiserror 20598  
    ```  
  
     <span data-ttu-id="3f1fd-140">Возникновение ошибки заставляет агент распространителя повторить обновления через одно соединение, которые завершатся успешно.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-140">Raising the error forces the Distribution Agent to retry the updates over a single connection, which will succeed.</span></span> <span data-ttu-id="3f1fd-141">Пользовательские хранимые процедуры должны содержать похожую логику.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-141">Custom stored procedures must include similar logic.</span></span>  
  
### <a name="call-syntax-for-stored-procedures"></a><span data-ttu-id="3f1fd-142">Синтаксис вызова для хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="3f1fd-142">Call syntax for stored procedures</span></span>  
 <span data-ttu-id="3f1fd-143">Существует пять вариантов синтаксиса, который применяется для вызова процедур, используемых репликацией транзакций:</span><span class="sxs-lookup"><span data-stu-id="3f1fd-143">There are five options for the syntax used to call the procedures used by transactional replication:</span></span>  
  
-   <span data-ttu-id="3f1fd-144">Синтаксис функции CALL.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-144">CALL syntax.</span></span> <span data-ttu-id="3f1fd-145">Может использоваться для вставок, обновлений и удалений.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-145">Can be used for inserts, updates, and deletes.</span></span> <span data-ttu-id="3f1fd-146">По умолчанию репликация использует этот синтаксис для вставок и удалений.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-146">By default, replication uses this syntax for inserts and deletes.</span></span>  
  
-   <span data-ttu-id="3f1fd-147">Синтаксис функции SCALL.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-147">SCALL syntax.</span></span> <span data-ttu-id="3f1fd-148">Может применяться только для обновлений.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-148">Can be used for updates only.</span></span> <span data-ttu-id="3f1fd-149">По умолчанию репликация использует этот синтаксис для обновлений.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-149">By default, replication uses this syntax for updates.</span></span>  
  
-   <span data-ttu-id="3f1fd-150">Синтаксис функции MCALL.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-150">MCALL syntax.</span></span> <span data-ttu-id="3f1fd-151">Может применяться только для обновлений.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-151">Can be used for updates only.</span></span>  
  
-   <span data-ttu-id="3f1fd-152">Синтаксис функции XCALL.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-152">XCALL syntax.</span></span> <span data-ttu-id="3f1fd-153">Может использоваться для обновлений и удалений.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-153">Can be used for updates and deletes.</span></span>  
  
-   <span data-ttu-id="3f1fd-154">VCALL.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-154">VCALL.</span></span> <span data-ttu-id="3f1fd-155">Применяется для обновляемых подписок.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-155">Used for updatable subscriptions.</span></span> <span data-ttu-id="3f1fd-156">Только для внутреннего применения.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-156">Internal use only.</span></span>  
  
 <span data-ttu-id="3f1fd-157">Каждый метод отличается по количеству данных, распространяемых на подписчик.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-157">Each method differs in the amount of data that is propagated to the Subscriber.</span></span> <span data-ttu-id="3f1fd-158">Например, SCALL передается в значениях только для столбцов, реально затронутых обновлением.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-158">For example, SCALL passes in values only for the columns that are actually affected by an update.</span></span> <span data-ttu-id="3f1fd-159">Напротив, XCALL запрашивает все столбцы (независимо от того, затронуты ли они обновлением) и все старые значения данных каждого столбца.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-159">XCALL, by contrast, requires all columns (whether affected by an update or not) and all the old data values for each column.</span></span> <span data-ttu-id="3f1fd-160">Во многих случаях синтаксис SCALL целесообразен для обновлений, но если приложению нужны все значения данных во время обновления, это позволяет указать синтаксис XCALL.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-160">In many cases, SCALL is appropriate for updates, but if your application requires all the data values during an update, XCALL allows for this.</span></span>  
  
#### <a name="call-syntax"></a><span data-ttu-id="3f1fd-161">Синтаксис функции CALL</span><span class="sxs-lookup"><span data-stu-id="3f1fd-161">CALL Syntax</span></span>  
 <span data-ttu-id="3f1fd-162">Хранимые процедуры INSERT</span><span class="sxs-lookup"><span data-stu-id="3f1fd-162">INSERT stored procedures</span></span>  
 <span data-ttu-id="3f1fd-163">Хранимым процедурам, обрабатывающим инструкции INSERT, передаются вставляемые значения для всех столбцов:</span><span class="sxs-lookup"><span data-stu-id="3f1fd-163">Stored procedures handling INSERT statements will be passed the inserted values for all columns:</span></span>  
  
```  
c1, c2, c3,... cn  
```  
  
 <span data-ttu-id="3f1fd-164">Хранимые процедуры UPDATE</span><span class="sxs-lookup"><span data-stu-id="3f1fd-164">UPDATE stored procedures</span></span>  
 <span data-ttu-id="3f1fd-165">Хранимым процедурам, обрабатывающим инструкции UPDATE, передаются обновленные значения для всех столбцов, определенных в статье, за ними передаются исходные значения для первичных ключевых столбцов (попыток определить, какие столбцы были изменены, не предпринимается):</span><span class="sxs-lookup"><span data-stu-id="3f1fd-165">Stored procedures handling UPDATE statements will be passed the updated values for all columns defined in the article, followed by the original values for the primary key columns (no attempt is made to determine which columns were changed.):</span></span>  
  
```  
c1, c2, c3,... cn, pkc1, pkc2, pkc3,... pkcn  
```  
  
 <span data-ttu-id="3f1fd-166">Хранимые процедуры DELETE</span><span class="sxs-lookup"><span data-stu-id="3f1fd-166">DELETE stored procedures</span></span>  
 <span data-ttu-id="3f1fd-167">Хранимым процедурам, обрабатывающим инструкции DELETE, передаются значения для всех первичных ключевых столбцов:</span><span class="sxs-lookup"><span data-stu-id="3f1fd-167">Stored procedures handling DELETE statements will be passed values for the primary key columns:</span></span>  
  
```  
pkc1, pkc2, pkc3,... pkcn  
```  
  
#### <a name="scall-syntax"></a><span data-ttu-id="3f1fd-168">Синтаксис функции SCALL</span><span class="sxs-lookup"><span data-stu-id="3f1fd-168">SCALL Syntax</span></span>  
 <span data-ttu-id="3f1fd-169">Хранимые процедуры UPDATE</span><span class="sxs-lookup"><span data-stu-id="3f1fd-169">UPDATE stored procedures</span></span>  
 <span data-ttu-id="3f1fd-170">Хранимым процедурам, обрабатывающим инструкции UPDATE, передаются обновленные значения только для измененных столбцов, затем передаются исходные значения для первичных ключевых столбцов, за которыми следует параметр битовой маски (`binary(n)`), указывающий на измененные столбцы.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-170">Stored procedures handling UPDATE statements will be passed the updated values only for those columns that have changed, followed by the original values for the primary key columns, followed by a bitmask (`binary(n)`) parameter that indicates the changed columns.</span></span> <span data-ttu-id="3f1fd-171">В следующем примере столбец 2 (c2) не был изменен:</span><span class="sxs-lookup"><span data-stu-id="3f1fd-171">In the following example, column 2 (c2) has not changed:</span></span>  
  
```  
c1, , c3,... cn, pkc1, pkc2, pkc3,... pkcn, bitmask  
```  
  
#### <a name="mcall-syntax"></a><span data-ttu-id="3f1fd-172">Синтаксис функции MCALL</span><span class="sxs-lookup"><span data-stu-id="3f1fd-172">MCALL Syntax</span></span>  
 <span data-ttu-id="3f1fd-173">Хранимые процедуры UPDATE</span><span class="sxs-lookup"><span data-stu-id="3f1fd-173">UPDATE stored procedures</span></span>  
 <span data-ttu-id="3f1fd-174">Хранимым процедурам, обрабатывающим инструкции UPDATE, передаются обновленные значения для всех столбцов, определенных в статье, а также исходные значения для первичных ключевых столбцов и параметр битовой маски (`binary(n)`), указывающий на измененные столбцы.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-174">Stored procedures handling UPDATE statements will be passed the updated values for all columns defined in the article, followed by the original values for the primary key columns, followed by a bitmask (`binary(n)`) parameter that indicates the changed columns:</span></span>  
  
```  
c1, c2, c3,... cn, pkc1, pkc2, pkc3,... pkcn, bitmask  
```  
  
#### <a name="xcall-syntax"></a><span data-ttu-id="3f1fd-175">Синтаксис функции XCALL.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-175">XCALL Syntax</span></span>  
 <span data-ttu-id="3f1fd-176">Хранимые процедуры UPDATE</span><span class="sxs-lookup"><span data-stu-id="3f1fd-176">UPDATE stored procedures</span></span>  
 <span data-ttu-id="3f1fd-177">Хранимым процедурам, обрабатывающим инструкции UPDATE, передаются исходные значения (образ до обработки) для всех столбцов, определенных в статье, а затем передаются обновленные значения (образ после обработки) для всех столбцов, определенных в статье:</span><span class="sxs-lookup"><span data-stu-id="3f1fd-177">Stored procedures handling UPDATE statements will be passed the original values (the before image) for all columns defined in the article, followed by the updated values (the after image) for all columns defined in the article:</span></span>  
  
```  
old-c1, old-c2, old-c3,... old-cn, c1, c2, c3,... cn,  
```  
  
 <span data-ttu-id="3f1fd-178">Хранимые процедуры DELETE</span><span class="sxs-lookup"><span data-stu-id="3f1fd-178">DELETE stored procedures</span></span>  
 <span data-ttu-id="3f1fd-179">Хранимым процедурам, обрабатывающим инструкции DELETE, передаются исходные значения (образ до обработки) для всех столбцов, определенных в статье:</span><span class="sxs-lookup"><span data-stu-id="3f1fd-179">Stored procedures handling DELETE statements will be passed the original (the before image) values for all columns defined in the article:</span></span>  
  
```  
old-c1, old-c2, old-c3,... old-cn  
```  
  
> [!NOTE]  
>  <span data-ttu-id="3f1fd-180">При использовании функции XCALL предполагается, что значения двоичного образа до обработки для столбцов **text** и **image** равны NULL.</span><span class="sxs-lookup"><span data-stu-id="3f1fd-180">When using XCALL, the before image values for **text** and **image** columns are expected to be NULL.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="3f1fd-181">Примеры</span><span class="sxs-lookup"><span data-stu-id="3f1fd-181">Examples</span></span>  
 <span data-ttu-id="3f1fd-182">Следующие процедуры являются процедурами по умолчанию, созданными для `Vendor Table` в примере базы данных [!INCLUDE[ssSampleDBCoShort](../../../includes/sssampledbcoshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3f1fd-182">The following procedures are the default procedures created for the `Vendor Table` in the [!INCLUDE[ssSampleDBCoShort](../../../includes/sssampledbcoshort-md.md)] sample database.</span></span>  
  
```  
--INSERT procedure using CALL syntax  
create procedure [sp_MSins_PurchasingVendor]   
  @c1 int,@c2 nvarchar(15),@c3 nvarchar(50),@c4 tinyint,@c5 bit,@c6 bit,@c7 nvarchar(1024),@c8 datetime  
as   
begin   
insert into [Purchasing].[Vendor]([VendorID]  
,[AccountNumber]  
,[Name]  
,[CreditRating]  
,[PreferredVendorStatus]  
,[ActiveFlag]  
,[PurchasingWebServiceURL]  
,[ModifiedDate])  
values (   
 @c1  
,@c2  
,@c3  
,@c4  
,@c5  
,@c6  
,@c7  
,@c8  
 )   
end  
go  
  
--UPDATE procedure using SCALL syntax  
create procedure [sp_MSupd_PurchasingVendor]   
 @c1 int = null,@c2 nvarchar(15) = null,@c3 nvarchar(50) = null,@c4 tinyint = null,@c5 bit = null,@c6 bit = null,@c7 nvarchar(1024) = null,@c8 datetime = null,@pkc1 int  
,@bitmap binary(2)  
as  
begin  
update [Purchasing].[Vendor] set   
 [AccountNumber] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [AccountNumber] end  
,[Name] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [Name] end  
,[CreditRating] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [CreditRating] end  
,[PreferredVendorStatus] = case substring(@bitmap,1,1) & 16 when 16 then @c5 else [PreferredVendorStatus] end  
,[ActiveFlag] = case substring(@bitmap,1,1) & 32 when 32 then @c6 else [ActiveFlag] end  
,[PurchasingWebServiceURL] = case substring(@bitmap,1,1) & 64 when 64 then @c7 else [PurchasingWebServiceURL] end  
,[ModifiedDate] = case substring(@bitmap,1,1) & 128 when 128 then @c8 else [ModifiedDate] end  
where [VendorID] = @pkc1  
if @@rowcount = 0  
    if @@microsoftversion>0x07320000  
        exec sp_MSreplraiserror 20598  
end  
go  
  
--DELETE procedure using CALL syntax  
create procedure [sp_MSdel_PurchasingVendor]   
  @pkc1 int  
as   
begin   
delete [Purchasing].[Vendor]  
where [VendorID] = @pkc1  
if @@rowcount = 0  
    if @@microsoftversion>0x07320000  
        exec sp_MSreplraiserror 20598  
end   
go  
```  
  
## <a name="see-also"></a><span data-ttu-id="3f1fd-183">См. также:</span><span class="sxs-lookup"><span data-stu-id="3f1fd-183">See Also</span></span>  
 [<span data-ttu-id="3f1fd-184">Article Options for Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="3f1fd-184">Article Options for Transactional Replication</span></span>](article-options-for-transactional-replication.md)  
  
  
