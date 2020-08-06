---
title: SQL Server Service Broker | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.SSBQUEUEPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBREMSVCBINDPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBMSGTYPEPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBROUTEPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBCONTRACTPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBSERVICEPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBPRIORITYPROPERTIES.GENERAL.F1
helpviewer_keywords:
- Broker See Service Broker
- SQL Server Service Broker
- Service Broker
ms.assetid: 8b8b3b57-fd46-44de-9a4e-e3a8e3999c1e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3d3877dd8311e0fe5b65bd4b1e7f9c40fbd84751
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740385"
---
# <a name="sql-server-service-broker"></a><span data-ttu-id="1f0e5-102">Служба SQL Server Service Broker</span><span class="sxs-lookup"><span data-stu-id="1f0e5-102">SQL Server Service Broker</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="1f0e5-103">[!INCLUDE[ssSB](../../includes/sssb-md.md)]обеспечивает встроенную поддержку приложений обмена сообщениями и очередей в [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1f0e5-103">[!INCLUDE[ssSB](../../includes/sssb-md.md)] provides native support for messaging and queuing applications in the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="1f0e5-104">Это облегчает разработчикам создание сложных приложений, использующих компоненты [!INCLUDE[ssDE](../../includes/ssde-md.md)] для связи между разнородными базами данных.</span><span class="sxs-lookup"><span data-stu-id="1f0e5-104">This makes it easier for developers to create sophisticated applications that use the [!INCLUDE[ssDE](../../includes/ssde-md.md)] components to communicate between disparate databases.</span></span> <span data-ttu-id="1f0e5-105">Разработчики могут использовать компонент [!INCLUDE[ssSB](../../includes/sssb-md.md)] для облегчения создания распределенных и надежных приложений.</span><span class="sxs-lookup"><span data-stu-id="1f0e5-105">Developers can use [!INCLUDE[ssSB](../../includes/sssb-md.md)] to easily build distributed and reliable applications.</span></span>  
  
 <span data-ttu-id="1f0e5-106">Разработчики приложений, использующие компонент [!INCLUDE[ssSB](../../includes/sssb-md.md)] , могут распределять рабочую нагрузку между несколькими базами данных без программирования сложного взаимодействия и создания внутреннего обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="1f0e5-106">Application developers who use [!INCLUDE[ssSB](../../includes/sssb-md.md)] can distribute data workloads across several databases without programming complex communication and messaging internals.</span></span> <span data-ttu-id="1f0e5-107">Это сокращает разработку и проверочную работу, потому что компонент [!INCLUDE[ssSB](../../includes/sssb-md.md)] обеспечивает взаимодействие в контексте диалога.</span><span class="sxs-lookup"><span data-stu-id="1f0e5-107">This reduces development and test work because [!INCLUDE[ssSB](../../includes/sssb-md.md)] handles the communication paths in the context of a conversation.</span></span> <span data-ttu-id="1f0e5-108">Кроме того, это повышает производительность.</span><span class="sxs-lookup"><span data-stu-id="1f0e5-108">It also improves performance.</span></span> <span data-ttu-id="1f0e5-109">Например, сервер, обслуживающий клиентские запросы базы данных, поддерживающие веб-сайты, может записывать информацию и отправлять ресурсоемкие задачи в очереди серверных баз данных.</span><span class="sxs-lookup"><span data-stu-id="1f0e5-109">For example, front-end databases supporting Web sites can record information and send process intensive tasks to queue in back-end databases.</span></span> [!INCLUDE[ssSB](../../includes/sssb-md.md)] <span data-ttu-id="1f0e5-110">гарантирует, что управление всеми задачами ведется в контексте транзакций, чтобы обеспечить надежность и техническое единообразие.</span><span class="sxs-lookup"><span data-stu-id="1f0e5-110">ensures that all tasks are managed in the context of transactions to assure reliability and technical consistency.</span></span>  
  
## <a name="where-is-the-documentation-for-service-broker"></a><span data-ttu-id="1f0e5-111">Где найти документацию по компоненту Service Broker?</span><span class="sxs-lookup"><span data-stu-id="1f0e5-111">Where is the documentation for Service Broker?</span></span>  
 <span data-ttu-id="1f0e5-112">Справочная документация по компоненту [!INCLUDE[ssSB](../../includes/sssb-md.md)] входит в документацию по [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1f0e5-112">The reference documentation for [!INCLUDE[ssSB](../../includes/sssb-md.md)] is included in the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] documentation.</span></span> <span data-ttu-id="1f0e5-113">В эту справочную документацию входят следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="1f0e5-113">This reference documentation includes the following sections:</span></span>  
  
-   <span data-ttu-id="1f0e5-114">См. информацию об инструкциях CREATE, ALTER и DROP в разделе [Инструкции на языке описания данных (DDL) (Transact-SQL)](/sql/odbc/reference/develop-app/ddl-statements)</span><span class="sxs-lookup"><span data-stu-id="1f0e5-114">[Data Definition Language &#40;DDL&#41; Statements &#40;Transact-SQL&#41;](/sql/odbc/reference/develop-app/ddl-statements) for CREATE, ALTER, and DROP statements</span></span>  
  
-   [<span data-ttu-id="1f0e5-115">Представления каталога компонента Service Broker (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1f0e5-115">Service Broker Catalog Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/service-broker-catalog-views-transact-sql)  
  
-   [<span data-ttu-id="1f0e5-116">Динамические административные представления, связанные с компонентом Service Broker (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1f0e5-116">Service Broker Related Dynamic Management Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/service-broker-related-dynamic-management-views-transact-sql)  
  
-   [<span data-ttu-id="1f0e5-117">Программа ssbdiagnose (компонент Service Broker)</span><span class="sxs-lookup"><span data-stu-id="1f0e5-117">ssbdiagnose Utility &#40;Service Broker&#41;</span></span>](../../tools/ssbdiagnose/ssbdiagnose-utility-service-broker.md)  
  
 <span data-ttu-id="1f0e5-118">Сведения об основных понятиях компонента [, а также задачах разработки и управления см. в](https://go.microsoft.com/fwlink/?LinkId=231312) ранее опубликованной документации [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1f0e5-118">See the [previously published documentation](https://go.microsoft.com/fwlink/?LinkId=231312) for [!INCLUDE[ssSB](../../includes/sssb-md.md)] concepts and for development and management tasks.</span></span> <span data-ttu-id="1f0e5-119">Эта документация не повторяется в документации по [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] из-за малого числа изменений в компоненте [!INCLUDE[ssSB](../../includes/sssb-md.md)] в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f0e5-119">This documentation is not reproduced in the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] documentation due to the small number of changes in [!INCLUDE[ssSB](../../includes/sssb-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="whats-new-in-service-broker"></a><span data-ttu-id="1f0e5-120">Новые возможности (компонент Service Broker)</span><span class="sxs-lookup"><span data-stu-id="1f0e5-120">What's new in Service Broker</span></span>  
 <span data-ttu-id="1f0e5-121">В [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]не были внесены значимые изменения.</span><span class="sxs-lookup"><span data-stu-id="1f0e5-121">No significant changes are introduced in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  <span data-ttu-id="1f0e5-122">В [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]появились следующие изменения.</span><span class="sxs-lookup"><span data-stu-id="1f0e5-122">The following changes were introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span></span>  
  
### <a name="messages-can-be-sent-to-multiple-target-services-multicast"></a><span data-ttu-id="1f0e5-123">Сообщения могут отправляться в несколько целевых служб (многоадресная рассылка)</span><span class="sxs-lookup"><span data-stu-id="1f0e5-123">Messages can be sent to multiple target services (multicast)</span></span>  
 <span data-ttu-id="1f0e5-124">Синтаксис инструкции [SEND (Transact-SQL)](/sql/t-sql/statements/send-transact-sql) расширен для включения многоадресной рассылки благодаря поддержке нескольких дескрипторов диалога.</span><span class="sxs-lookup"><span data-stu-id="1f0e5-124">The syntax of the [SEND &#40;Transact-SQL&#41;](/sql/t-sql/statements/send-transact-sql) statement has been extended to enable multicast by supporting multiple conversation handles.</span></span>  
  
### <a name="queues-expose-the-message-enqueued-time"></a><span data-ttu-id="1f0e5-125">Очереди предоставляют время нахождения сообщения в очереди</span><span class="sxs-lookup"><span data-stu-id="1f0e5-125">Queues expose the message enqueued time</span></span>  
 <span data-ttu-id="1f0e5-126">Очереди содержат новый столбец **message_enqueue_time**, в котором показано время нахождения сообщения в очереди.</span><span class="sxs-lookup"><span data-stu-id="1f0e5-126">Queues have a new column, **message_enqueue_time**, that shows how long a message has been in the queue.</span></span>  
  
### <a name="poison-message-handling-can-be-disabled"></a><span data-ttu-id="1f0e5-127">Можно отключить обработку сообщений о сбое</span><span class="sxs-lookup"><span data-stu-id="1f0e5-127">Poison message handling can be disabled</span></span>  
 <span data-ttu-id="1f0e5-128">Теперь в инструкциях [CREATE QUEUE (Transact-SQL)](/sql/t-sql/statements/create-queue-transact-sql) и [ALTER QUEUE (Transact-SQL)](/sql/t-sql/statements/alter-queue-transact-sql) можно включать или отключать обработку сообщений о сбое, добавляя предложение `POISON_MESSAGE_HANDLING (STATUS = ON | OFF)`.</span><span class="sxs-lookup"><span data-stu-id="1f0e5-128">The [CREATE QUEUE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-queue-transact-sql) and [ALTER QUEUE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-queue-transact-sql) statements now have the ability to enable or disable poison message handling by adding the clause, `POISON_MESSAGE_HANDLING (STATUS = ON | OFF)`.</span></span> <span data-ttu-id="1f0e5-129">Представление каталога **sys.service_queues** теперь содержит столбец **is_poison_message_handling_enabled** , показывающий, включено ли сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="1f0e5-129">The catalog view **sys.service_queues** now has the column **is_poison_message_handling_enabled** to indicate whether poison message is enabled or disabled.</span></span>  
  
### <a name="alwayson-support-in-service-broker"></a><span data-ttu-id="1f0e5-130">Поддержка AlwaysOn в компоненте Service Broker</span><span class="sxs-lookup"><span data-stu-id="1f0e5-130">AlwaysOn support in Service Broker</span></span>  
 <span data-ttu-id="1f0e5-131">Дополнительные сведения см. в статье [Компонент Service Broker с группами доступности AlwaysOn (SQL Server)](../availability-groups/windows/service-broker-with-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1f0e5-131">For more information, see [Service Broker with AlwaysOn Availability Groups &#40;SQL Server&#41;](../availability-groups/windows/service-broker-with-always-on-availability-groups-sql-server.md).</span></span>  
  
  
