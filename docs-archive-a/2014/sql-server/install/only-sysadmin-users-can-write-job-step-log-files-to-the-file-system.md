---
title: Только пользователи sysadmin могут записывать файлы журнала шагов задания в файловую систему | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- job step log files [SQL Server Agent]
- log files [SQL Server Agent]
- writing job step log files
ms.assetid: d26a7cef-1a60-4c95-b9df-f8b4fec59f9b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9e2bf5095ac1e6b67f6c6f3f87444879913916e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664667"
---
# <a name="only-sysadmin-users-can-write-job-step-log-files-to-the-file-system"></a><span data-ttu-id="7911a-102">Только пользователи с правами sysadmin могут записывать файлы журнала шага задания в файловую систему</span><span class="sxs-lookup"><span data-stu-id="7911a-102">Only sysadmin users can write job step log files to the file system</span></span>
  <span data-ttu-id="7911a-103">По желанию пользователя [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] ведет журнал шагов задания.</span><span class="sxs-lookup"><span data-stu-id="7911a-103">[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] optionally writes a log for each job step.</span></span>  
  
## <a name="component"></a><span data-ttu-id="7911a-104">Компонент</span><span class="sxs-lookup"><span data-stu-id="7911a-104">Component</span></span>  
 <span data-ttu-id="7911a-105">Агент[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7911a-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span></span>  
  
## <a name="description"></a><span data-ttu-id="7911a-106">Описание</span><span class="sxs-lookup"><span data-stu-id="7911a-106">Description</span></span>  
 <span data-ttu-id="7911a-107">В [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Агент может записывать журналы в файловую систему для заданий, принадлежащих членам предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="7911a-107">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can write logs to the file system for jobs that are owned by members of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="7911a-108">Если владелец задания не является членом роли **sysadmin** , а учетная запись-посредник включена, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Агент может записывать журналы в файловую систему, используя учетные данные учетной записи-посредника.</span><span class="sxs-lookup"><span data-stu-id="7911a-108">If the job owner is not a member of the **sysadmin** role and if the proxy account is enabled, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can write logs to the file system by using the credentials of the proxy account.</span></span>  
  
 <span data-ttu-id="7911a-109">После обновления задания, которые принадлежат пользователям, не являющимся членами предопределенной роли сервера **sysadmin** , больше не могут записывать журналы в файловую систему.</span><span class="sxs-lookup"><span data-stu-id="7911a-109">After you upgrade, jobs that are owned by users who are not members of the **sysadmin** fixed server role can no longer write logs to the file system.</span></span> <span data-ttu-id="7911a-110">Вместо этого эти пользователи могут выбрать параметр для записи журналов в таблицу в базе данных **msdb** .</span><span class="sxs-lookup"><span data-stu-id="7911a-110">Instead, these users can select the option to write their logs to a table in the **msdb** database.</span></span> <span data-ttu-id="7911a-111">Члены роли **sysadmin** могут по-прежнему записывать файлы журнала в файловую систему.</span><span class="sxs-lookup"><span data-stu-id="7911a-111">Members of the **sysadmin** role can still write log files to the file system.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="7911a-112">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="7911a-112">Corrective Action</span></span>  
 <span data-ttu-id="7911a-113">После обновления задания, которые принадлежат пользователям, не являющимся членами роли **sysadmin** , будут по-прежнему выполняться, но журналы не будут созданы.</span><span class="sxs-lookup"><span data-stu-id="7911a-113">After you upgrade, jobs that are owned by users who are not members of the **sysadmin** role will continue to run, but logs will not be created.</span></span> <span data-ttu-id="7911a-114">Для регистрации шагов заданий в таблице пользователи, не являющиеся членами роли **sysadmin** , должны вручную обновить свои задания.</span><span class="sxs-lookup"><span data-stu-id="7911a-114">To log job steps to a table, users who are not members of the **sysadmin** role must manually update their jobs.</span></span>  
  
 <span data-ttu-id="7911a-115">Дополнительные сведения см. в разделах «Создание заданий», «Создание шагов задания» и «Обработка множественных шагов задания» электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7911a-115">For more information, see the topics "Creating Jobs," "Creating Job Steps," and "Handling Multiple Job Steps" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7911a-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="7911a-116">See Also</span></span>  
 [<span data-ttu-id="7911a-117">Проблемы обновления агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="7911a-117">SQL Server Agent Upgrade Issues</span></span>](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
  
