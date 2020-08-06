---
title: MSSQL_ENG021798 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021798 error
ms.assetid: 596f5092-75ab-4a19-8582-588687c7b089
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 327b4a373c28376701ea12400215ab00367df66a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730490"
---
# <a name="mssql_eng021798"></a><span data-ttu-id="a8a1c-102">MSSQL_ENG021798</span><span class="sxs-lookup"><span data-stu-id="a8a1c-102">MSSQL_ENG021798</span></span>
    
## <a name="message-details"></a><span data-ttu-id="a8a1c-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="a8a1c-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a8a1c-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="a8a1c-104">Product Name</span></span>|<span data-ttu-id="a8a1c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a8a1c-105">SQL Server</span></span>|  
|<span data-ttu-id="a8a1c-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="a8a1c-106">Event ID</span></span>|<span data-ttu-id="a8a1c-107">21798</span><span class="sxs-lookup"><span data-stu-id="a8a1c-107">21798</span></span>|  
|<span data-ttu-id="a8a1c-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="a8a1c-108">Event Source</span></span>|<span data-ttu-id="a8a1c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a8a1c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a8a1c-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="a8a1c-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="a8a1c-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="a8a1c-111">Symbolic Name</span></span>||  
|<span data-ttu-id="a8a1c-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="a8a1c-112">Message Text</span></span>|<span data-ttu-id="a8a1c-113">Перед продолжением необходимо добавить задание агента '%s' с помощью '%s'.</span><span class="sxs-lookup"><span data-stu-id="a8a1c-113">The '%s' agent job must be added through '%s' before continuing.</span></span> <span data-ttu-id="a8a1c-114">См. документацию по "%s".»</span><span class="sxs-lookup"><span data-stu-id="a8a1c-114">Please see the documentation for '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a8a1c-115">Объяснение</span><span class="sxs-lookup"><span data-stu-id="a8a1c-115">Explanation</span></span>  
 <span data-ttu-id="a8a1c-116">Для создания публикации необходимо быть членом предопределенной роли сервера **sysadmin** на издателе или членом предопределенной роли базы данных **db_owner** в базе данных публикации.</span><span class="sxs-lookup"><span data-stu-id="a8a1c-116">To create a publication, you must be a member of the **sysadmin** fixed server role on the Publisher or a member of the **db_owner** fixed database role in the publication database.</span></span> <span data-ttu-id="a8a1c-117">Если вы являетесь членом роли базы данных **db_owner** , эта ошибка возникает в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="a8a1c-117">If you are a member of the **db_owner** role, this error is raised if:</span></span>  
  
-   <span data-ttu-id="a8a1c-118">Выполняются скрипты из [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8a1c-118">You run scripts from [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span></span> <span data-ttu-id="a8a1c-119">Модель безопасности в [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]изменилась, поэтому эти скрипты необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="a8a1c-119">The security model changed in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], and these scripts must be updated.</span></span>  
  
-   <span data-ttu-id="a8a1c-120">Хранимая процедура **sp_addpublication** выполняется перед выполнением процедуры [sp_addlogreader_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlogreader-agent-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a8a1c-120">The stored procedure **sp_addpublication** is executed before executing [sp_addlogreader_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlogreader-agent-transact-sql).</span></span> <span data-ttu-id="a8a1c-121">Это относится ко всем публикациям транзакций.</span><span class="sxs-lookup"><span data-stu-id="a8a1c-121">This applies to all transactional publications.</span></span>  
  
-   <span data-ttu-id="a8a1c-122">Хранимая процедура **sp_addpublication** выполняется перед выполнением процедуры [sp_addqreader_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addqreader-agent-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a8a1c-122">The stored procedure **sp_addpublication** is executed before executing [sp_addqreader_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addqreader-agent-transact-sql).</span></span> <span data-ttu-id="a8a1c-123">Это относится к публикациям транзакций, для которых включены обновляемые посредством очередей подписки (значение TRUE для **@allow_queued_tran** параметра **sp_addpublication**).</span><span class="sxs-lookup"><span data-stu-id="a8a1c-123">This applies to transactional publications that are enabled for queued updating subscriptions (a value of TRUE for the **@allow_queued_tran** parameter of **sp_addpublication**).</span></span>  
  
 <span data-ttu-id="a8a1c-124">Хранимые процедуры **sp_addlogreader_agent** и **sp_addqreader_agent** создают задание агента и позволяют задать учетную запись [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, под которой запускается агент.</span><span class="sxs-lookup"><span data-stu-id="a8a1c-124">The stored procedures **sp_addlogreader_agent** and **sp_addqreader_agent** each create an agent job and allow you to specify the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the agent runs.</span></span> <span data-ttu-id="a8a1c-125">Для пользователей в роли **sysadmin** задания агентов создаются явно, если процедуры **sp_addlogreader_agent** и **sp_addqreader_agent** не выполняются. Агент запускается в контексте учетной записи службы агентов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на распространителе.</span><span class="sxs-lookup"><span data-stu-id="a8a1c-125">For users in the **sysadmin** role, agent jobs are created implicitly if **sp_addlogreader_agent** and **sp_addqreader_agent** are not executed; agents run under the context of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account at the Distributor.</span></span> <span data-ttu-id="a8a1c-126">Несмотря на то, что процедуры **sp_addlogreader_agent** и **sp_addqreader_agent** необязательны для пользователей в роли **sysadmin** , в целях обеспечения надлежащей безопасности рекомендуется задать отдельную учетную запись для агентов.</span><span class="sxs-lookup"><span data-stu-id="a8a1c-126">Although **sp_addlogreader_agent** and **sp_addqreader_agent** are not required for users in the **sysadmin** role, it is a security best practice to specify a separate account for the agents.</span></span> <span data-ttu-id="a8a1c-127">Дополнительные сведения см. в статье [Модель безопасности агента репликации](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="a8a1c-127">For more information, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a8a1c-128">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="a8a1c-128">User Action</span></span>  
 <span data-ttu-id="a8a1c-129">Убедитесь в том, что процедуры выполняются в правильном порядке.</span><span class="sxs-lookup"><span data-stu-id="a8a1c-129">Ensure you execute procedures in the correct order.</span></span> <span data-ttu-id="a8a1c-130">Дополнительные сведения см. в статьях [Создание публикации](publish/create-a-publication.md), обновление этих скриптов для включения хранимых процедур и параметров, необходимых для [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="a8a1c-130">For more information, see [Create a Publication](publish/create-a-publication.md), update these scripts to include the stored procedures and parameters required by [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions.</span></span> <span data-ttu-id="a8a1c-131">Дополнительные сведения см. в статье [Обновление скриптов репликации (программирование репликации на языке Transact-SQL)](administration/upgrade-replication-scripts-replication-transact-sql-programming.md).</span><span class="sxs-lookup"><span data-stu-id="a8a1c-131">For more information, see [Upgrade Replication Scripts &#40;Replication Transact-SQL Programming&#41;](administration/upgrade-replication-scripts-replication-transact-sql-programming.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8a1c-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="a8a1c-132">See Also</span></span>  
 [<span data-ttu-id="a8a1c-133">Справочник по ошибкам и событиям (репликация)</span><span class="sxs-lookup"><span data-stu-id="a8a1c-133">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
