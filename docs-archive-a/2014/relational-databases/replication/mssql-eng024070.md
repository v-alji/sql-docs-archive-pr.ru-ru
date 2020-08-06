---
title: MSSQL_ENG024070 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG024070 error
ms.assetid: 23ac7e00-fab6-429b-9f85-2736a322aa65
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 07fcfcb96b284d46d46f63af4a650f925ef2de73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730486"
---
# <a name="mssql_eng024070"></a><span data-ttu-id="35a62-102">MSSQL_ENG024070</span><span class="sxs-lookup"><span data-stu-id="35a62-102">MSSQL_ENG024070</span></span>
    
## <a name="message-details"></a><span data-ttu-id="35a62-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="35a62-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="35a62-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="35a62-104">Product Name</span></span>|<span data-ttu-id="35a62-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="35a62-105">SQL Server</span></span>|  
|<span data-ttu-id="35a62-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="35a62-106">Event ID</span></span>|<span data-ttu-id="35a62-107">24070</span><span class="sxs-lookup"><span data-stu-id="35a62-107">24070</span></span>|  
|<span data-ttu-id="35a62-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="35a62-108">Event Source</span></span>|<span data-ttu-id="35a62-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="35a62-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="35a62-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="35a62-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="35a62-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="35a62-111">Symbolic Name</span></span>||  
|<span data-ttu-id="35a62-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="35a62-112">Message Text</span></span>|<span data-ttu-id="35a62-113">Клиент не располагает требуемыми правами доступа.</span><span class="sxs-lookup"><span data-stu-id="35a62-113">A required privilege is not held by the client.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="35a62-114">Объяснение</span><span class="sxs-lookup"><span data-stu-id="35a62-114">Explanation</span></span>  
 <span data-ttu-id="35a62-115">Это общая ошибка, которая может возникнуть независимо от того, реплицируется база данных или нет.</span><span class="sxs-lookup"><span data-stu-id="35a62-115">This is a general error that can be raised regardless of whether replication is being used.</span></span> <span data-ttu-id="35a62-116">Для сервера в топологии репликации эта ошибка обычно означает, что учетная запись службы агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] была изменена с использованием диспетчера управления службами [!INCLUDE[msCoName](../../includes/msconame-md.md)] , а не с помощью диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="35a62-116">For a server in a replication topology, the error is typically raised because the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account is changed by using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Service Control Manager instead of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="35a62-117">Если попытаться выполнить задание агента после изменения учетной записи службы, выполнение задания может закончится выдачей примерно следующего сообщения об ошибке:</span><span class="sxs-lookup"><span data-stu-id="35a62-117">When you try to run an agent job after changing the service account, the job might fail with an error message that is similar to the following:</span></span>  
  
 <span data-ttu-id="35a62-118">"Выполняется от имени пользователя: \<UserAccount> .</span><span class="sxs-lookup"><span data-stu-id="35a62-118">"Executed as user: \<UserAccount>.</span></span> <span data-ttu-id="35a62-119">Репликация — подсистема моментальных снимков репликации: \<AgentName> сбой агента.</span><span class="sxs-lookup"><span data-stu-id="35a62-119">Replication-Replication Snapshot Subsystem: agent \<AgentName> failed.</span></span> <span data-ttu-id="35a62-120">Выполняется от имени пользователя: \<UserAccount> .</span><span class="sxs-lookup"><span data-stu-id="35a62-120">Executed as user: \<UserAccount>.</span></span> <span data-ttu-id="35a62-121">Клиент не располагает требуемыми правами доступа.</span><span class="sxs-lookup"><span data-stu-id="35a62-121">A required privilege is not held by the client.</span></span> <span data-ttu-id="35a62-122">Шаг завершился с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="35a62-122">The step failed.</span></span> <span data-ttu-id="35a62-123">`[SQLSTATE 42000] (Error 14151)`.</span><span class="sxs-lookup"><span data-stu-id="35a62-123">`[SQLSTATE 42000] (Error 14151)`.</span></span> <span data-ttu-id="35a62-124">Шаг завершился с ошибкой».</span><span class="sxs-lookup"><span data-stu-id="35a62-124">The step failed."</span></span>  
  
 <span data-ttu-id="35a62-125">Эта проблема возникает из-за того, что диспетчер управления службами Windows не может предоставить новой учетной записи службы для агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] требуемые разрешения.</span><span class="sxs-lookup"><span data-stu-id="35a62-125">This problem occurs because the Windows Service Control Manager cannot grant the required permissions to the new service account for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="35a62-126">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="35a62-126">User Action</span></span>  
 <span data-ttu-id="35a62-127">Чтобы в дальнейшем избежать появления этой проблемы, при изменении учетных записей служб и паролей всегда пользуйтесь диспетчером конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , а не диспетчером управления службами Windows.</span><span class="sxs-lookup"><span data-stu-id="35a62-127">To avoid this problem in the future, always use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager instead of the Windows Service Control Manager to change service accounts and passwords.</span></span>  
  
 <span data-ttu-id="35a62-128">Чтобы устранить эту проблему, при помощи диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] смените учетную запись службы обратно на исходную.</span><span class="sxs-lookup"><span data-stu-id="35a62-128">To resolve this problem, use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to change the service account back to the original account.</span></span> <span data-ttu-id="35a62-129">Затем при помощи диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] перейдите на новую учетную запись.</span><span class="sxs-lookup"><span data-stu-id="35a62-129">Then, use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to change to the new account.</span></span> <span data-ttu-id="35a62-130">При этом диспетчер конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] добавляет новую учетную запись в следующую группу безопасности:</span><span class="sxs-lookup"><span data-stu-id="35a62-130">When you do this, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager adds the new account to the following security group:</span></span>  
  
 <span data-ttu-id="35a62-131">SQLServer2008SQLAgentUser$ComputerName$InstanceName</span><span class="sxs-lookup"><span data-stu-id="35a62-131">SQLServer2008SQLAgentUser$ComputerName$InstanceName</span></span>  
  
 <span data-ttu-id="35a62-132">Членство в ней предоставляет новой учетной записи разрешения, необходимые для выполнения задания агента репликации.</span><span class="sxs-lookup"><span data-stu-id="35a62-132">Being a member of this security group grants to the new account the required permissions to run the replication agent job.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35a62-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="35a62-133">See Also</span></span>  
 <span data-ttu-id="35a62-134">[Справочник по ошибкам и событиям (репликация)](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="35a62-134">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 <span data-ttu-id="35a62-135">[Управление именами для входа и паролями при репликации](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span><span class="sxs-lookup"><span data-stu-id="35a62-135">[Manage Logins and Passwords in Replication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span></span>  
 [<span data-ttu-id="35a62-136">Диспетчер конфигурации SQL Server</span><span class="sxs-lookup"><span data-stu-id="35a62-136">SQL Server Configuration Manager</span></span>](../sql-server-configuration-manager.md)  
  
  
