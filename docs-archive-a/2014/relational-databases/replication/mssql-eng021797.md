---
title: MSSQL_ENG021797 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021797 error
ms.assetid: 54d83a1e-43fd-449c-a2b2-fdda2609a534
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d33ade7e7eea9fa9e95453a5b232447f7b222b18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730494"
---
# <a name="mssql_eng021797"></a><span data-ttu-id="c073a-102">MSSQL_ENG021797</span><span class="sxs-lookup"><span data-stu-id="c073a-102">MSSQL_ENG021797</span></span>
    
## <a name="message-details"></a><span data-ttu-id="c073a-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="c073a-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c073a-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="c073a-104">Product Name</span></span>|<span data-ttu-id="c073a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c073a-105">SQL Server</span></span>|  
|<span data-ttu-id="c073a-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="c073a-106">Event ID</span></span>|<span data-ttu-id="c073a-107">21797</span><span class="sxs-lookup"><span data-stu-id="c073a-107">21797</span></span>|  
|<span data-ttu-id="c073a-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="c073a-108">Event Source</span></span>|<span data-ttu-id="c073a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c073a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c073a-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="c073a-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="c073a-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="c073a-111">Symbolic Name</span></span>||  
|<span data-ttu-id="c073a-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="c073a-112">Message Text</span></span>|<span data-ttu-id="c073a-113">"%s" должно быть допустимым именем входа Windows, представленным в следующем виде: "КОМПЬЮТЕР\имя_входа" или "ДОМЕН\имя_входа".</span><span class="sxs-lookup"><span data-stu-id="c073a-113">'%s' must be a valid Windows Login in the form: 'MACHINE\Login' or 'DOMAIN\Login'.</span></span> <span data-ttu-id="c073a-114">См. документацию по "%s".»</span><span class="sxs-lookup"><span data-stu-id="c073a-114">Please see the documentation for '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c073a-115">Объяснение</span><span class="sxs-lookup"><span data-stu-id="c073a-115">Explanation</span></span>  
 <span data-ttu-id="c073a-116">Эта ошибка возникает в следующих хранимых процедурах репликации, если значение, указанное для **@job_login** параметра, равно null или недопустимо.</span><span class="sxs-lookup"><span data-stu-id="c073a-116">This error is raised by the following replication stored procedures if the value specified for the **@job_login** parameter is null or not valid.</span></span> <span data-ttu-id="c073a-117">Эта ошибка может возникнуть, если член предопределенной роли базы данных **db_owner** запускает скрипты из предыдущих версий [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c073a-117">This error can occur if a member of the **db_owner** fixed database role runs scripts from previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c073a-118">Модель безопасности в [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]изменилась, поэтому эти скрипты необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="c073a-118">The security model changed in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], and these scripts must be updated.</span></span>  
  
-   [<span data-ttu-id="c073a-119">sp_addlogreader_agent (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c073a-119">sp_addlogreader_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addlogreader-agent-transact-sql)  
  
-   [<span data-ttu-id="c073a-120">sp_addqreader_agent (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c073a-120">sp_addqreader_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addqreader-agent-transact-sql)  
  
-   [<span data-ttu-id="c073a-121">sp_addpublication_snapshot (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c073a-121">sp_addpublication_snapshot &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addpublication-snapshot-transact-sql)  
  
-   [<span data-ttu-id="c073a-122">sp_addpushsubscription_agent (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c073a-122">sp_addpushsubscription_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addpushsubscription-agent-transact-sql)  
  
-   [<span data-ttu-id="c073a-123">sp_addpullsubscription_agent (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c073a-123">sp_addpullsubscription_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-agent-transact-sql)  
  
-   [<span data-ttu-id="c073a-124">sp_addmergepushsubscription_agent (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c073a-124">sp_addmergepushsubscription_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addmergepushsubscription-agent-transact-sql)  
  
-   [<span data-ttu-id="c073a-125">sp_addmergepullsubscription_agent (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c073a-125">sp_addmergepullsubscription_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addmergepullsubscription-agent-transact-sql)  
  
 <span data-ttu-id="c073a-126">Эти хранимые процедуры могут запускаться членом предопределенной роли сервера **sysadmin** на соответствующем сервере или членом предопределенной роли базы данных **db_owner** в соответствующей базе данных.</span><span class="sxs-lookup"><span data-stu-id="c073a-126">These stored procedures can be executed by a member of the **sysadmin** fixed server role on the appropriate server or a member of the **db_owner** fixed database role in the appropriate database.</span></span> <span data-ttu-id="c073a-127">Каждая из этих хранимых процедур создает задание для агента и позволяет задать учетную запись [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, под которой запускается агент.</span><span class="sxs-lookup"><span data-stu-id="c073a-127">The stored procedures each create an agent job and allow you to specify the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the agent runs.</span></span> <span data-ttu-id="c073a-128">Для пользователей в роли **sysadmin** задания агентов создаются неявно, даже если не задана учетная запись Windows (если учетная запись задана, то она должна быть допустимой); агенты запускаются в контексте учетной записи службы агентов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на соответствующем сервере.</span><span class="sxs-lookup"><span data-stu-id="c073a-128">For users in the **sysadmin** role, agent jobs are created implicitly even if a Windows account is not specified (if an account is specified, it must be valid); agents run under the context of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account at the appropriate server.</span></span> <span data-ttu-id="c073a-129">Несмотря на то, что учетная запись не требуется, в целях безопасности рекомендуется задать отдельную учетную запись для каждого агента.</span><span class="sxs-lookup"><span data-stu-id="c073a-129">Although the account is not required, it is a security best practice to specify a separate account for the agents.</span></span> <span data-ttu-id="c073a-130">Дополнительные сведения см. в статье [Модель безопасности агента репликации](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="c073a-130">For more information, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c073a-131">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="c073a-131">User Action</span></span>  
 <span data-ttu-id="c073a-132">Убедитесь, что для параметра каждой процедуры указана допустимая учетная запись Windows **@job_login** .</span><span class="sxs-lookup"><span data-stu-id="c073a-132">Ensure you specify a valid Windows account for the **@job_login** parameter of each procedure.</span></span> <span data-ttu-id="c073a-133">При наличии скриптов репликации из предыдущих версий [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]обновите эти скрипты для включения хранимых процедур и параметров, требуемых [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c073a-133">If you have replication scripts from previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], update these scripts to include the stored procedures and parameters required by [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="c073a-134">Дополнительные сведения см. в статье [Обновление скриптов репликации (программирование репликации на языке Transact-SQL)](administration/upgrade-replication-scripts-replication-transact-sql-programming.md).</span><span class="sxs-lookup"><span data-stu-id="c073a-134">For more information, see [Upgrade Replication Scripts &#40;Replication Transact-SQL Programming&#41;](administration/upgrade-replication-scripts-replication-transact-sql-programming.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c073a-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="c073a-135">See Also</span></span>  
 [<span data-ttu-id="c073a-136">Справочник по ошибкам и событиям (репликация)</span><span class="sxs-lookup"><span data-stu-id="c073a-136">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
