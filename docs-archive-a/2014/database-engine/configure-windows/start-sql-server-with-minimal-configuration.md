---
title: Запуск SQL Server с минимальной конфигурацией | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- minimal configuration [SQL Server]
- starting SQL Server, minimal configuration
ms.assetid: 4d733c99-28b3-42d8-b7f6-7b943b548173
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5c78fc10be584803b438b2cd125a77400ff369b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655346"
---
# <a name="start-sql-server-with-minimal-configuration"></a><span data-ttu-id="06e26-102">Запустите SQL Server с минимальной конфигурацией</span><span class="sxs-lookup"><span data-stu-id="06e26-102">Start SQL Server with Minimal Configuration</span></span>
  <span data-ttu-id="06e26-103">При наличии ошибок в конфигурации, не позволяющих осуществить запуск сервера, можно применить параметр запуска в минимальной конфигурации для запуска экземпляра [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06e26-103">If you have configuration problems that prevent the server from starting, you can start an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using the minimal configuration startup option.</span></span> <span data-ttu-id="06e26-104">Это параметр запуска **-f**.</span><span class="sxs-lookup"><span data-stu-id="06e26-104">This is the startup option **-f**.</span></span> <span data-ttu-id="06e26-105">Запуск экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с минимальной конфигурацией автоматически переводит сервер в однопользовательский режим.</span><span class="sxs-lookup"><span data-stu-id="06e26-105">Starting an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with minimal configuration automatically puts the server in single-user mode.</span></span>  
  
 <span data-ttu-id="06e26-106">При запуске экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в режиме минимальной конфигурации обратите внимание на следующее:</span><span class="sxs-lookup"><span data-stu-id="06e26-106">When you start an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in minimal configuration mode, note the following:</span></span>  
  
-   <span data-ttu-id="06e26-107">может подключиться только один пользователь, операция CHECKPOINT не выполняется;</span><span class="sxs-lookup"><span data-stu-id="06e26-107">Only a single user can connect, and the CHECKPOINT process is not executed.</span></span>  
  
-   <span data-ttu-id="06e26-108">удаленный доступ и упреждающее чтение отключены;</span><span class="sxs-lookup"><span data-stu-id="06e26-108">Remote access and read-ahead are disabled.</span></span>  
  
-   <span data-ttu-id="06e26-109">запуск хранимых процедур не осуществляется.</span><span class="sxs-lookup"><span data-stu-id="06e26-109">Startup stored procedures do not run.</span></span>  
  
 <span data-ttu-id="06e26-110">После запуска сервера с минимальной конфигурацией необходимо изменить значение или значения параметра соответствующего сервера, остановить сервер и заново запустить его.</span><span class="sxs-lookup"><span data-stu-id="06e26-110">After the server has been started with minimal configuration, you should change the appropriate server option value or values, stop, and then restart the server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="06e26-111">Используйте программу **sqlcmd** и выделенное административное соединение (DAC) для подключения к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06e26-111">Use the **sqlcmd** utility and the dedicated administrator connection (DAC) to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="06e26-112">При использовании обычного соединения, перед тем как соединяться с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в режиме минимальной конфигурации, необходимо остановить службу агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="06e26-112">If you use a typical connection, stop the SQL Server Agent service before connecting to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in minimal configuration mode.</span></span> <span data-ttu-id="06e26-113">В противном случае служба агента SQL Server использует это соединение, тем самым блокируя его.</span><span class="sxs-lookup"><span data-stu-id="06e26-113">Otherwise, the SQL Server Agent service uses the connection, thereby blocking it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06e26-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="06e26-114">See Also</span></span>  
 <span data-ttu-id="06e26-115">[Запуск, остановка или приостановка службы агента SQL Server](../../ssms/agent/start-stop-or-pause-the-sql-server-agent-service.md) </span><span class="sxs-lookup"><span data-stu-id="06e26-115">[Start, Stop, or Pause the SQL Server Agent Service](../../ssms/agent/start-stop-or-pause-the-sql-server-agent-service.md) </span></span>  
 <span data-ttu-id="06e26-116">[Диагностическое соединение для администраторов баз данных](diagnostic-connection-for-database-administrators.md) </span><span class="sxs-lookup"><span data-stu-id="06e26-116">[Diagnostic Connection for Database Administrators](diagnostic-connection-for-database-administrators.md) </span></span>  
 <span data-ttu-id="06e26-117">[sqlcmd Utility](../../tools/sqlcmd-utility.md) </span><span class="sxs-lookup"><span data-stu-id="06e26-117">[sqlcmd Utility](../../tools/sqlcmd-utility.md) </span></span>  
 <span data-ttu-id="06e26-118">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="06e26-118">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="06e26-119">[sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="06e26-119">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="06e26-120">Параметры запуска службы Database Engine</span><span class="sxs-lookup"><span data-stu-id="06e26-120">Database Engine Service Startup Options</span></span>](database-engine-service-startup-options.md)  
  
  
