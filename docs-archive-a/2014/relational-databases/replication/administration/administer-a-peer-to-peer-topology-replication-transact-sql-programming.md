---
title: Администрирование одноранговой топологии (программирование репликации на языке Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- transactional replication, peer-to-peer replication
ms.assetid: 4d0fa941-f9ea-4a14-aed9-34df593fc6f2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3a73af1c1f3a7196d87f77681ee9d62a3ef248a4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657680"
---
# <a name="administer-a-peer-to-peer-topology-replication-transact-sql-programming"></a><span data-ttu-id="4a32a-102">Администрирование одноранговой топологии (программирование репликации на языке Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4a32a-102">Administer a Peer-to-Peer Topology (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="4a32a-103">Администрирование одноранговой топологии напоминает администрирование обычное топологии репликации транзакций, оно имеет некоторые специфические особенности.</span><span class="sxs-lookup"><span data-stu-id="4a32a-103">Administering a peer-to-peer topology is similar to administering a typical transactional replication topology, but there are a number of areas with special considerations.</span></span> <span data-ttu-id="4a32a-104">Главное отличие состоит в том, что при администрировании одноранговой топологии некоторые изменения требуют *замораживания*системы.</span><span class="sxs-lookup"><span data-stu-id="4a32a-104">The principal difference in administering a peer-to-peer topology is that some changes require the system to be *quiesced*.</span></span> <span data-ttu-id="4a32a-105">Замораживание системы предполагает прекращение операций с опубликованными таблицами на всех узлах и проверку того, что каждый узел получил все изменения со всех других узлов.</span><span class="sxs-lookup"><span data-stu-id="4a32a-105">Quiescing a system involves stopping activity on published tables at all nodes and ensuring that each node has received all changes from all other nodes.</span></span> <span data-ttu-id="4a32a-106">Дополнительные сведения см. в разделе [Замораживание топологии репликации (программирование репликации на языке Transact-SQL)](quiesce-a-replication-topology-replication-transact-sql-programming.md).</span><span class="sxs-lookup"><span data-stu-id="4a32a-106">For more information, see [Quiesce a Replication Topology &#40;Replication Transact-SQL Programming&#41;](quiesce-a-replication-topology-replication-transact-sql-programming.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4a32a-107">В одноранговой топологии распространитель не может использовать более раннюю версию [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , чем подписчик по запросу.</span><span class="sxs-lookup"><span data-stu-id="4a32a-107">In a peer-to-peer topology, the distributor cannot be using an earlier version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] than a pull subscriber.</span></span>  
  
### <a name="to-add-an-article-to-an-existing-configuration"></a><span data-ttu-id="4a32a-108">Добавление статьи к существующей конфигурации</span><span class="sxs-lookup"><span data-stu-id="4a32a-108">To add an article to an existing configuration</span></span>  
  
1.  <span data-ttu-id="4a32a-109">Заморозьте систему.</span><span class="sxs-lookup"><span data-stu-id="4a32a-109">Quiesce the system.</span></span>  
  
2.  <span data-ttu-id="4a32a-110">Остановите агент распространителя в каждом узле топологии.</span><span class="sxs-lookup"><span data-stu-id="4a32a-110">Stop the Distribution Agent at each node in the topology.</span></span> <span data-ttu-id="4a32a-111">Дополнительные сведения см. в разделах [Основные понятия исполняемых файлов агента репликации](../concepts/replication-agent-executables-concepts.md) и [Запуск и остановка агента репликации (среда SQL Server Management Studio)](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="4a32a-111">For more information, see [Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) or [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span></span>  
  
3.  <span data-ttu-id="4a32a-112">При помощи инструкции CREATE TABLE добавьте новую таблицу в каждом из узлов топологии.</span><span class="sxs-lookup"><span data-stu-id="4a32a-112">Execute the CREATE TABLE statement to add the new table at each node in the topology.</span></span>  
  
4.  <span data-ttu-id="4a32a-113">Вручную выполните массовое копирование данных во всех узлах при помощи [программы bcp](../../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="4a32a-113">Bulk copy the data for the new table manually at all nodes by using the [bcp utility](../../../tools/bcp-utility.md).</span></span>  
  
5.  <span data-ttu-id="4a32a-114">При помощи хранимой процедуры [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql) создайте новую статью в каждом узле топологии.</span><span class="sxs-lookup"><span data-stu-id="4a32a-114">Execute [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql) to create the new article at each node in the topology.</span></span> <span data-ttu-id="4a32a-115">Дополнительные сведения см. в статье [определить статью](../publish/define-an-article.md).</span><span class="sxs-lookup"><span data-stu-id="4a32a-115">For more information, see [Define an Article](../publish/define-an-article.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4a32a-116">После завершения хранимой процедуры [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql) репликация автоматически добавит статью в подписки топологии.</span><span class="sxs-lookup"><span data-stu-id="4a32a-116">After [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql) is executed, replication automatically adds the article to the subscriptions in the topology.</span></span>  
  
6.  <span data-ttu-id="4a32a-117">Перезапустите агент распространителя в каждом из узлов топологии.</span><span class="sxs-lookup"><span data-stu-id="4a32a-117">Restart the Distribution Agents at each node in the topology.</span></span>  
  
### <a name="to-make-schema-changes-to-a-publication-database"></a><span data-ttu-id="4a32a-118">Внесение изменений в схему баз данных публикации</span><span class="sxs-lookup"><span data-stu-id="4a32a-118">To make schema changes to a publication database</span></span>  
  
1.  <span data-ttu-id="4a32a-119">Заморозьте систему.</span><span class="sxs-lookup"><span data-stu-id="4a32a-119">Quiesce the system.</span></span>  
  
2.  <span data-ttu-id="4a32a-120">При помощи инструкций языка DDL внесите изменения в схему опубликованных таблиц.</span><span class="sxs-lookup"><span data-stu-id="4a32a-120">Execute the data definition language (DDL) statements to modify the schema of published tables.</span></span> <span data-ttu-id="4a32a-121">Дополнительные сведения о поддерживаемых изменениях схем см. в разделе [Внесение изменений в схемы баз данных публикации](../publish/make-schema-changes-on-publication-databases.md).</span><span class="sxs-lookup"><span data-stu-id="4a32a-121">For more information about supported schema changes, see [Make Schema Changes on Publication Databases](../publish/make-schema-changes-on-publication-databases.md).</span></span>  
  
3.  <span data-ttu-id="4a32a-122">Прежде чем возобновить работу с опубликованными таблицами, вновь заморозьте систему.</span><span class="sxs-lookup"><span data-stu-id="4a32a-122">Before you resume activity on published tables, quiesce the system again.</span></span> <span data-ttu-id="4a32a-123">Это необходимо для того, чтобы изменения в схеме были приняты всеми узлами до репликации новых изменений данных.</span><span class="sxs-lookup"><span data-stu-id="4a32a-123">This ensures that schema changes have been received by all nodes before any new data changes are replicated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a32a-124">Пример</span><span class="sxs-lookup"><span data-stu-id="4a32a-124">Example</span></span>  
 <span data-ttu-id="4a32a-125">Следующий пример показывает, как нужно добавлять новую статью таблицы к существующей одноранговой топологии репликации с двумя узлами.</span><span class="sxs-lookup"><span data-stu-id="4a32a-125">The following example demonstrates how to add a new table article to an existing peer-to-peer replication topology that has two nodes.</span></span>  
  
 [!code-sql[HowTo#sp_addp2particle_createtables](../../../snippets/tsql/SQL15/replication/howto/tsql/addp2particle.sql#sp_addp2particle_createtables)]  
  
 [!code-sql[HowTo#sp_addp2particle_cmdline](../../../snippets/tsql/SQL15/replication/howto/tsql/addp2particle.sql#sp_addp2particle_cmdline)]  
  
 [!code-sql[HowTo#sp_addp2particle_createarticle](../../../snippets/tsql/SQL15/replication/howto/tsql/addp2particle.sql#sp_addp2particle_createarticle)]  
  
## <a name="see-also"></a><span data-ttu-id="4a32a-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="4a32a-126">See Also</span></span>  
 <span data-ttu-id="4a32a-127">[Вопросы и ответы об администрировании репликации](frequently-asked-questions-for-replication-administrators.md) </span><span class="sxs-lookup"><span data-stu-id="4a32a-127">[Replication Administration FAQ](frequently-asked-questions-for-replication-administrators.md) </span></span>  
 <span data-ttu-id="4a32a-128">[Резервное копирование и восстановление баз данных SQL Server](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="4a32a-128">[Back Up and Restore of SQL Server Databases](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 [<span data-ttu-id="4a32a-129">Peer-to-Peer Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="4a32a-129">Peer-to-Peer Transactional Replication</span></span>](../transactional/peer-to-peer-transactional-replication.md)  
  
  
