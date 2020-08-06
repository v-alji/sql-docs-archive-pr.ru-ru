---
title: Реализация пользовательского арбитра конфликтов для статьи публикации слиянием | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- merge replication conflict resolution [SQL Server replication], stored procedure-based resolvers
- articles [SQL Server replication], conflict resolution
- conflict resolution [SQL Server replication], merge replication
ms.assetid: 76bd8524-ebc1-4d80-b5a2-4169944d6ac0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 23e684213114f3c9bb2f1ad56de06fcfc89b819a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655597"
---
# <a name="implement-a-custom-conflict-resolver-for-a-merge-article"></a><span data-ttu-id="0d7de-102">Реализация пользовательского арбитра конфликтов для статьи публикации слиянием</span><span class="sxs-lookup"><span data-stu-id="0d7de-102">Implement a Custom Conflict Resolver for a Merge Article</span></span>
  <span data-ttu-id="0d7de-103"> В данном разделе описывается реализация пользовательского арбитра конфликтов для статьи слияния в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[tsql](../../includes/tsql-md.md)] или [пользовательского арбитра конфликтов на основе COM](merge/advanced-merge-replication-conflict-com-based-custom-resolvers.md).</span><span class="sxs-lookup"><span data-stu-id="0d7de-103">This topic describes how to implement custom conflict resolver for a merge article in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)] or a [COM-based custom resolver](merge/advanced-merge-replication-conflict-com-based-custom-resolvers.md).</span></span>  
  
 <span data-ttu-id="0d7de-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="0d7de-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0d7de-105">**Для реализации пользовательского арбитра конфликтов для статьи публикации слиянием используется:**</span><span class="sxs-lookup"><span data-stu-id="0d7de-105">**To implement custom conflict resolver for a merge article, using:**</span></span>  
  
     [<span data-ttu-id="0d7de-106">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0d7de-106">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="0d7de-107">Арбитр конфликтов на основе COM</span><span class="sxs-lookup"><span data-stu-id="0d7de-107">COM-based Resolver</span></span>](#COM)  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0d7de-108">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0d7de-108">Using Transact-SQL</span></span>  
 <span data-ttu-id="0d7de-109">Собственный пользовательский арбитр конфликтов можно записать в виде хранимой процедуры [!INCLUDE[tsql](../../includes/tsql-md.md)] на каждом издателе.</span><span class="sxs-lookup"><span data-stu-id="0d7de-109">You can write your own custom conflict resolver as a [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure at each Publisher.</span></span> <span data-ttu-id="0d7de-110">Во время синхронизации эта хранимая процедура вызывается при возникновении конфликтов в статье, для которой был зарегистрирован сопоставитель, и данные о строке с конфликтом передаются агентом слияния в необходимые параметры этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="0d7de-110">During synchronization, this stored procedure is invoked when conflicts are encountered in an article to which the resolver was registered, and information on the conflict row is passed by the Merge Agent to the required parameters of the procedure.</span></span> <span data-ttu-id="0d7de-111">Пользовательские сопоставители конфликтов на основе хранимых процедур всегда создаются на издателе.</span><span class="sxs-lookup"><span data-stu-id="0d7de-111">Stored procedure-based custom conflict resolvers are always created at the Publisher.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="0d7de-112">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]разрешения на хранимые процедуры вызываются только для обработки конфликтов на основе изменений строк.</span><span class="sxs-lookup"><span data-stu-id="0d7de-112">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedure resolvers are only invoked to handle row change-based conflicts.</span></span> <span data-ttu-id="0d7de-113">Их нельзя использовать для обработки других типов конфликтов, таких как ошибки вставки, возникшие из-за нарушения ограничений PRIMARY KEY или ограничений уникального индекса.</span><span class="sxs-lookup"><span data-stu-id="0d7de-113">They cannot be used to handle other types of conflicts such as insert failures due to PRIMARY KEY violations or unique index constraint violations.</span></span>  
  
#### <a name="to-create-a-stored-procedure-based-custom-conflict-resolver"></a><span data-ttu-id="0d7de-114">Создание пользовательского сопоставителя конфликтов на основе хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="0d7de-114">To create a stored procedure-based custom conflict resolver</span></span>  
  
1.  <span data-ttu-id="0d7de-115">На издателе в базе данных публикации или **msdb** создайте новую системную хранимую процедуру, реализующую следующие обязательные параметры.</span><span class="sxs-lookup"><span data-stu-id="0d7de-115">At the Publisher in either the publication or **msdb** database, create a new system stored procedure that implements the following required parameters:</span></span>  
  
    |<span data-ttu-id="0d7de-116">Параметр</span><span class="sxs-lookup"><span data-stu-id="0d7de-116">Parameter</span></span>|<span data-ttu-id="0d7de-117">Тип данных</span><span class="sxs-lookup"><span data-stu-id="0d7de-117">Data type</span></span>|<span data-ttu-id="0d7de-118">Описание</span><span class="sxs-lookup"><span data-stu-id="0d7de-118">Description</span></span>|  
    |---------------|---------------|-----------------|  
    |**@tableowner**|`sysname`|<span data-ttu-id="0d7de-119">Имя владельца таблицы, в которой разрешается конфликт.</span><span class="sxs-lookup"><span data-stu-id="0d7de-119">Name of the owner of the table for which a conflict is being resolved.</span></span> <span data-ttu-id="0d7de-120">Это владелец таблицы в базе данных публикации.</span><span class="sxs-lookup"><span data-stu-id="0d7de-120">This is the owner for the table in the publication database.</span></span>|  
    |**@tablename**|`sysname`|<span data-ttu-id="0d7de-121">Имя таблицы, в которой разрешается конфликт.</span><span class="sxs-lookup"><span data-stu-id="0d7de-121">Name of the table for which a conflict is being resolved.</span></span>|  
    |**@rowguid**|`uniqueidentifier`|<span data-ttu-id="0d7de-122">Уникальный идентификатор строки конфликта.</span><span class="sxs-lookup"><span data-stu-id="0d7de-122">Unique identifier for the row having the conflict.</span></span>|  
    |**@subscriber**|`sysname`|<span data-ttu-id="0d7de-123">Имя сервера, с которого распространяется вызвавшее конфликт изменение.</span><span class="sxs-lookup"><span data-stu-id="0d7de-123">Name of the server from where a conflicting change is being propagated.</span></span>|  
    |**@subscriber_db**|`sysname`|<span data-ttu-id="0d7de-124">Имя базы данных, из которой распространяется вызвавшее конфликт изменение.</span><span class="sxs-lookup"><span data-stu-id="0d7de-124">Name of the database from where conflicting change is being propagated.</span></span>|  
    |<span data-ttu-id="0d7de-125">**@log_conflictПРОВЕРКИ**</span><span class="sxs-lookup"><span data-stu-id="0d7de-125">**@log_conflict OUTPUT**</span></span>|`int`|<span data-ttu-id="0d7de-126">Определяет, должен ли процесс слияния зарегистрировать конфликт для последующего разрешения.</span><span class="sxs-lookup"><span data-stu-id="0d7de-126">Whether the merge process should log a conflict for later resolution:</span></span><br /><br /> <span data-ttu-id="0d7de-127">**0** = не регистрировать конфликт.</span><span class="sxs-lookup"><span data-stu-id="0d7de-127">**0** = Do not log the conflict.</span></span><br /><br /> <span data-ttu-id="0d7de-128">**1** = разрешение конфликта в пользу издателя.</span><span class="sxs-lookup"><span data-stu-id="0d7de-128">**1** = Subscriber is the conflict loser.</span></span><br /><br /> <span data-ttu-id="0d7de-129">**2** = разрешение конфликта в пользу подписчика.</span><span class="sxs-lookup"><span data-stu-id="0d7de-129">**2** = Publisher is the conflict loser.</span></span>|  
    |<span data-ttu-id="0d7de-130">**@conflict_messageПРОВЕРКИ**</span><span class="sxs-lookup"><span data-stu-id="0d7de-130">**@conflict_message OUTPUT**</span></span>|`nvarchar(512)`|<span data-ttu-id="0d7de-131">Сообщения, которые должны быть выданы о разрешении конфликта, если конфликт был зарегистрирован.</span><span class="sxs-lookup"><span data-stu-id="0d7de-131">Message to be given about the resolution if the conflict is logged.</span></span>|  
    |**@destowner**|`sysname`|<span data-ttu-id="0d7de-132">Владелец опубликованной таблицы на подписчике.</span><span class="sxs-lookup"><span data-stu-id="0d7de-132">The owner of the published table at the Subscriber.</span></span>|  
  
     <span data-ttu-id="0d7de-133">Эта хранимая процедура использует значения, переданные агентом слияния этим параметрам для применения пользовательской логики устранения конфликтов. Она должна вернуть результирующий набор, содержащий одну строку, соответствующий структуре базовой таблицы и содержащий значения данных для приоритетной версии строки.</span><span class="sxs-lookup"><span data-stu-id="0d7de-133">This stored procedure uses the values passed by the Merge Agent to these parameters to implement your custom conflict resolution logic; it must return a single row result set that is identical in structure to the base table and contains the data values for the winning version of the row.</span></span>  
  
2.  <span data-ttu-id="0d7de-134">Предоставьте разрешения EXECUTE на хранимую процедуру любым именам входа, используемым подписчиками для соединения с издателем.</span><span class="sxs-lookup"><span data-stu-id="0d7de-134">Grant EXECUTE permissions on the stored procedure to any logins used by Subscribers to connect to the Publisher.</span></span>  
  
#### <a name="to-use-a-custom-conflict-resolver-with-a-new-table-article"></a><span data-ttu-id="0d7de-135">Использование нестандартного сопоставителя конфликтов с новой статьей таблицы</span><span class="sxs-lookup"><span data-stu-id="0d7de-135">To use a custom conflict resolver with a new table article</span></span>  
  
1.  <span data-ttu-id="0d7de-136">Выполните хранимую процедуру [sp_addmergearticle](/sql/relational-databases/system-stored-procedures/sp-addmergearticle-transact-sql) , чтобы определить статью. При этом укажите значение **MicrosoftSQL** **Server Stored Procedure Resolver** в параметре **@article_resolver** и имя хранимой процедуры, реализующей логику сопоставителя конфликтов в параметре **@resolver_info** .</span><span class="sxs-lookup"><span data-stu-id="0d7de-136">Execute [sp_addmergearticle](/sql/relational-databases/system-stored-procedures/sp-addmergearticle-transact-sql) to define an article, specifying a value of **MicrosoftSQL** **Server Stored Procedure Resolver** for the **@article_resolver** parameter and the name of the stored procedure that implements the conflict resolver logic for the **@resolver_info** parameter.</span></span> <span data-ttu-id="0d7de-137">Дополнительные сведения см. в статье [определить статью](publish/define-an-article.md).</span><span class="sxs-lookup"><span data-stu-id="0d7de-137">For more information, see [Define an Article](publish/define-an-article.md).</span></span>  
  
#### <a name="to-use-a-custom-conflict-resolver-with-an-existing-table-article"></a><span data-ttu-id="0d7de-138">Использование нестандартного сопоставителя конфликтов с существующей статьей таблицы</span><span class="sxs-lookup"><span data-stu-id="0d7de-138">To use a custom conflict resolver with an existing table article</span></span>  
  
1.  <span data-ttu-id="0d7de-139">Выполните [sp_changemergearticle](/sql/relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql), указав **@publication** , **@article** , значение **article_resolver** в параметре **@property** и значение **MicrosoftSQL** **Server stored процедурересолвер** для **@value** .</span><span class="sxs-lookup"><span data-stu-id="0d7de-139">Execute [sp_changemergearticle](/sql/relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql), specifying **@publication**, **@article**, a value of **article_resolver** for **@property**, and a value of **MicrosoftSQL** **Server Stored ProcedureResolver** for **@value**.</span></span>  
  
2.  <span data-ttu-id="0d7de-140">Выполните [sp_changemergearticle](/sql/relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql), указав **@publication** , **@article** , значение **resolver_info** в параметре **@property** и имя хранимой процедуры, которая реализует логику сопоставителя конфликтов для **@value** .</span><span class="sxs-lookup"><span data-stu-id="0d7de-140">Execute [sp_changemergearticle](/sql/relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql), specifying **@publication**, **@article**, a value of **resolver_info** for **@property**, and the name of the stored procedure that implements the conflict resolver logic for **@value**.</span></span>  
  
##  <a name="using-a-com-based-custom-resolver"></a><a name="COM"></a><span data-ttu-id="0d7de-141">Использование пользовательского арбитра конфликтов на основе COM</span><span class="sxs-lookup"><span data-stu-id="0d7de-141">Using a COM-based Custom Resolver</span></span>  
 <span data-ttu-id="0d7de-142">Пространство имен <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport> реализует интерфейс, позволяющий писать сложную бизнес-логику для обработки событий и разрешения конфликтов, происходящих во время синхронизации репликации слиянием.</span><span class="sxs-lookup"><span data-stu-id="0d7de-142">The <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport> namespace implements an interface that enables you to write complex business logic to handle events and resolve conflicts that occur during the merge replication synchronization process.</span></span> <span data-ttu-id="0d7de-143">Дополнительные сведения см. в статье [Реализация обработчика бизнес-логики для статьи публикации слиянием](implement-a-business-logic-handler-for-a-merge-article.md).</span><span class="sxs-lookup"><span data-stu-id="0d7de-143">For more information, see [Implement a Business Logic Handler for a Merge Article](implement-a-business-logic-handler-for-a-merge-article.md).</span></span> <span data-ttu-id="0d7de-144">Для разрешения конфликтов можно записать в машинном коде собственную бизнес-логику.</span><span class="sxs-lookup"><span data-stu-id="0d7de-144">You can also write your own native code-based custom business logic to resolve conflicts.</span></span> <span data-ttu-id="0d7de-145">Эта логика построена как COM-компонент и компилируется в динамические библиотеки (DLL) с помощью таких продуктов, как [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C++.</span><span class="sxs-lookup"><span data-stu-id="0d7de-145">This logic is built as a COM component and compiled into dynamic-link libraries (DLL), using products such as [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C++.</span></span> <span data-ttu-id="0d7de-146">Такой пользовательский сопоставитель конфликтов на основе COM должен реализовывать интерфейс **ICustomResolver** , разработанный специально для разрешения конфликтов.</span><span class="sxs-lookup"><span data-stu-id="0d7de-146">Such a COM-based custom conflict resolver must implement the **ICustomResolver** interface, which is designed specifically for conflict resolution.</span></span>  
  
#### <a name="to-create-and-register-a-com-based-custom-conflict-resolver"></a><span data-ttu-id="0d7de-147">Создание и регистрация пользовательского сопоставителя конфликтов на основе COM</span><span class="sxs-lookup"><span data-stu-id="0d7de-147">To create and register a COM-based custom conflict resolver</span></span>  
  
1.  <span data-ttu-id="0d7de-148">В COM-совместимой среде разработчика добавьте ссылки на библиотеку пользовательского сопоставителя.</span><span class="sxs-lookup"><span data-stu-id="0d7de-148">In a COM-compatible authoring environment, add references to the Custom Conflict Resolver library.</span></span>  
  
2.  <span data-ttu-id="0d7de-149">В проекте Visual C++ используйте директиву #import для импорта этой библиотеки.</span><span class="sxs-lookup"><span data-stu-id="0d7de-149">For a Visual C++ project, use the #import directive to import this library into your project.</span></span>  
  
3.  <span data-ttu-id="0d7de-150">Создайте класс, реализующий интерфейс **ICustomResolver** .</span><span class="sxs-lookup"><span data-stu-id="0d7de-150">Create a class that implements the **ICustomResolver** interface.</span></span>  
  
4.  <span data-ttu-id="0d7de-151">Обеспечьте выполнение соответствующих методов и свойств.</span><span class="sxs-lookup"><span data-stu-id="0d7de-151">Implement certain methods and properties.</span></span>  
  
5.  <span data-ttu-id="0d7de-152">Постройте проект, создающий файл библиотеки пользовательского сопоставителя.</span><span class="sxs-lookup"><span data-stu-id="0d7de-152">Build the project to create the custom conflict resolver library file.</span></span>  
  
6.  <span data-ttu-id="0d7de-153">Разверните эту библиотеку в каталоге, содержащем исполняемый файл агента слияния (обычно «\Microsoft SQL Server\100\COM»).</span><span class="sxs-lookup"><span data-stu-id="0d7de-153">Deploy the library in the directory containing the merge agent executable (usually \Microsoft SQL Server\100\COM).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0d7de-154">Пользовательский сопоставитель конфликтов необходимо развернуть на подписчике для подписки по запросу, на распространителе для принудительной подписки или на веб-сервере, который используется для веб-синхронизации.</span><span class="sxs-lookup"><span data-stu-id="0d7de-154">A custom conflict resolver must be deployed at the Subscriber for a pull subscription, at the Distributor for a push subscription, or at the Web server used with Web synchronization.</span></span>  
  
7.  <span data-ttu-id="0d7de-155">Зарегистрируйте библиотеку пользовательского сопоставителя конфликтов с помощью программы regsvr32.exe из каталога развертывания следующим образом.</span><span class="sxs-lookup"><span data-stu-id="0d7de-155">Register the custom conflict resolver library using regsvr32.exe from the deployment directory as follows:</span></span>  
  
    ```  
    regsvr32.exe mycustomresolver.dll  
    ```  
  
8.  <span data-ttu-id="0d7de-156">На издателе выполните хранимую процедуру [sp_enumcustomresolvers (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-enumcustomresolvers-transact-sql), чтобы проверить, не зарегистрирована ли уже эта библиотека в качестве пользовательского арбитра конфликтов.</span><span class="sxs-lookup"><span data-stu-id="0d7de-156">At the Publisher, execute [sp_enumcustomresolvers &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-enumcustomresolvers-transact-sql) to verify that the library is not already registered as a custom conflict resolver.</span></span>  
  
9. <span data-ttu-id="0d7de-157">Чтобы зарегистрировать библиотеку в качестве пользовательского арбитра конфликтов, выполните хранимую процедуру [sp_registercustomresolver (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-registercustomresolver-transact-sql) на распространителе.</span><span class="sxs-lookup"><span data-stu-id="0d7de-157">To register the library as a custom conflict resolver, execute [sp_registercustomresolver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-registercustomresolver-transact-sql), at the Distributor.</span></span> <span data-ttu-id="0d7de-158">Укажите понятное имя COM-объекта для **@article_resolver** , идентификатор библиотеки (CLSID) для **@resolver_clsid** и значение `false` для **@is_dotnet_assembly** .</span><span class="sxs-lookup"><span data-stu-id="0d7de-158">Specify the friendly name of the COM object for **@article_resolver**, the library's ID (CLSID) for **@resolver_clsid**, and a value of `false` for **@is_dotnet_assembly**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0d7de-159">Если пользовательский арбитр конфликтов больше не нужен, вы можете отменить его регистрацию с помощью хранимой процедуры [sp_unregistercustomresolver (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-unregistercustomresolver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0d7de-159">When no longer needed, a custom conflict resolver can be unregistered using [sp_unregistercustomresolver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-unregistercustomresolver-transact-sql).</span></span>  
  
10. <span data-ttu-id="0d7de-160">В кластере повторите шаги 5-8, чтобы зарегистрировать пользовательский сопоставитель на всех узлах кластера (необязательно).</span><span class="sxs-lookup"><span data-stu-id="0d7de-160">(Optional) On a cluster, repeat steps 5-8 to register the custom resolver on all nodes of the cluster.</span></span> <span data-ttu-id="0d7de-161">Это нужно для того, чтобы пользовательский сопоставитель смог правильно загрузить посредник после отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="0d7de-161">This is required to ensure that the custom resolver will be able to properly load the reconciler following a failover.</span></span>  
  
#### <a name="to-use-a-custom-conflict-resolver-with-a-new-table-article"></a><span data-ttu-id="0d7de-162">Использование нестандартного сопоставителя конфликтов с новой статьей таблицы</span><span class="sxs-lookup"><span data-stu-id="0d7de-162">To use a custom conflict resolver with a new table article</span></span>  
  
1.  <span data-ttu-id="0d7de-163">Выполните процедуру [sp_enumcustomresolvers (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-enumcustomresolvers-transact-sql) на издателе и запомните понятное имя требуемого арбитра.</span><span class="sxs-lookup"><span data-stu-id="0d7de-163">At the Publisher, execute [sp_enumcustomresolvers &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-enumcustomresolvers-transact-sql) and note the friendly name of the desired resolver.</span></span>  
  
2.  <span data-ttu-id="0d7de-164">Чтобы определить статью, в базе данных публикации издателя выполните процедуру [sp_addmergearticle (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-addmergearticle-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0d7de-164">At the Publisher on the publication database, execute [sp_addmergearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergearticle-transact-sql) to define an article.</span></span> <span data-ttu-id="0d7de-165">Укажите понятное имя арбитра статей из шага 1 в параметре **@article_resolver** .</span><span class="sxs-lookup"><span data-stu-id="0d7de-165">Specify the friendly name of the article resolver from step 1 for **@article_resolver**.</span></span> <span data-ttu-id="0d7de-166">Дополнительные сведения см. в статье [определить статью](publish/define-an-article.md).</span><span class="sxs-lookup"><span data-stu-id="0d7de-166">For more information, see [Define an Article](publish/define-an-article.md).</span></span>  
  
#### <a name="to-use-a-custom-conflict-resolver-with-an-existing-table-article"></a><span data-ttu-id="0d7de-167">Использование нестандартного сопоставителя конфликтов с существующей статьей таблицы</span><span class="sxs-lookup"><span data-stu-id="0d7de-167">To use a custom conflict resolver with an existing table article</span></span>  
  
1.  <span data-ttu-id="0d7de-168">Выполните процедуру [sp_enumcustomresolvers (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-enumcustomresolvers-transact-sql) на издателе и запомните понятное имя требуемого арбитра.</span><span class="sxs-lookup"><span data-stu-id="0d7de-168">At the Publisher, execute [sp_enumcustomresolvers &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-enumcustomresolvers-transact-sql) and note the friendly name of the desired resolver.</span></span>  
  
2.  <span data-ttu-id="0d7de-169">Выполните [sp_changemergearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql), указав **@publication** , **@article** , значение **article_resolver** в параметре **@property** и понятное имя арбитра статей из шага 1 в параметре **@value** .</span><span class="sxs-lookup"><span data-stu-id="0d7de-169">Execute [sp_changemergearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql), specifying **@publication**, **@article**, a value of **article_resolver** for **@property**, and the friendly name of the article resolver from step 1 for **@value**.</span></span>  
  
#### <a name="viewing-a-sample-custom-resolver"></a><span data-ttu-id="0d7de-170">Просмотр образца пользовательского сопоставителя</span><span class="sxs-lookup"><span data-stu-id="0d7de-170">Viewing a Sample Custom Resolver</span></span>  
  
1.  <span data-ttu-id="0d7de-171">Пример доступен в образцах файлов SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="0d7de-171">A sample is available in the SQL Server 2000 sample files.</span></span> <span data-ttu-id="0d7de-172">Скачайте [**sql2000samples.zip**](https://github.com/Microsoft/sql-server-samples/blob/master/samples/tutorials/Miscellaneous/sql2000samples.zip).</span><span class="sxs-lookup"><span data-stu-id="0d7de-172">Download the [**sql2000samples.zip**](https://github.com/Microsoft/sql-server-samples/blob/master/samples/tutorials/Miscellaneous/sql2000samples.zip).</span></span> <span data-ttu-id="0d7de-173">Это позволит загрузить 3 файла, объем которых составляет 6,9 МБ.</span><span class="sxs-lookup"><span data-stu-id="0d7de-173">This downloads 3 files amounting to 6.9 MB.</span></span>  
  
2.  <span data-ttu-id="0d7de-174">Извлеките файлы из загруженного сжатого CAB-файла.</span><span class="sxs-lookup"><span data-stu-id="0d7de-174">Extract the files from downloaded compressed .cab file.</span></span>  
  
3.  <span data-ttu-id="0d7de-175">Запустить **setup.exe**</span><span class="sxs-lookup"><span data-stu-id="0d7de-175">Run **setup.exe**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0d7de-176">При выборе параметров установки необходимо установить только образцы **Репликации** .</span><span class="sxs-lookup"><span data-stu-id="0d7de-176">When choosing the installation options, it is only necessary to install the **Replication** samples.</span></span> <span data-ttu-id="0d7de-177">(Путь установки по умолчанию — **C:\Program Files (x86) \Microsoft SQL Server \\ 2000 Samples\1033**)</span><span class="sxs-lookup"><span data-stu-id="0d7de-177">(The default installation path is **C:\Program Files (x86)\Microsoft SQL Server 2000 Samples\1033\\**)</span></span>  
  
4.  <span data-ttu-id="0d7de-178">Перейдите в папку установки.</span><span class="sxs-lookup"><span data-stu-id="0d7de-178">Go to installation folder.</span></span> <span data-ttu-id="0d7de-179">(По умолчанию используется папка **C:\Program Files (x86)\Microsoft SQL Server 2000 Samples\1033\sqlrepl\unzip_sqlreplSP3.exe**)</span><span class="sxs-lookup"><span data-stu-id="0d7de-179">(The default folder is **C:\Program Files (x86)\Microsoft SQL Server 2000 Samples\1033\sqlrepl\unzip_sqlreplSP3.exe**)</span></span>  
  
5.  <span data-ttu-id="0d7de-180">Выполните программу **unzip_sqlreplSP3.exe** .</span><span class="sxs-lookup"><span data-stu-id="0d7de-180">Run the **unzip_sqlreplSP3.exe** program.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0d7de-181">Пример сопоставителя com будет установлен (по умолчанию) в папку **C:\Program Files (x86) \Microsoft SQL Server 2000 Samples\1033\sqlrepl\resolver\subspres** .</span><span class="sxs-lookup"><span data-stu-id="0d7de-181">The sample com resolver will install (by default) to the **C:\Program Files (x86)\Microsoft SQL Server 2000 Samples\1033\sqlrepl\resolver\subspres** folder.</span></span>  
  
6.  <span data-ttu-id="0d7de-182">В папке **subspres** найдите все вхождения **#include sqlres.h** во всех исходных файлах и замените их значением **#import "replrec.dll" no_namespace, raw_interfaces_only**</span><span class="sxs-lookup"><span data-stu-id="0d7de-182">In the **subspres** folder, find all occurrences of **#include sqlres.h** in all of the source files and replace them with **#import "replrec.dll" no_namespace, raw_interfaces_only**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d7de-183">См. также:</span><span class="sxs-lookup"><span data-stu-id="0d7de-183">See Also</span></span>  
 <span data-ttu-id="0d7de-184">[Advanced Merge Replication Conflict Detection and Resolution](merge/advanced-merge-replication-conflict-detection-and-resolution.md) </span><span class="sxs-lookup"><span data-stu-id="0d7de-184">[Advanced Merge Replication Conflict Detection and Resolution](merge/advanced-merge-replication-conflict-detection-and-resolution.md) </span></span>  
 <span data-ttu-id="0d7de-185">[Пользовательские арбитры конфликтов на основе COM](merge/advanced-merge-replication-conflict-com-based-custom-resolvers.md) </span><span class="sxs-lookup"><span data-stu-id="0d7de-185">[COM-Based Custom Resolvers](merge/advanced-merge-replication-conflict-com-based-custom-resolvers.md) </span></span>  
 [<span data-ttu-id="0d7de-186">Рекомендации по защите репликации</span><span class="sxs-lookup"><span data-stu-id="0d7de-186">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  