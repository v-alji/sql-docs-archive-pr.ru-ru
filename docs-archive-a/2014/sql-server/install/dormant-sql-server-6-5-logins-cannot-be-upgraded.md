---
title: Не удается обновить неактивные SQL Server 6,5 для входа | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- passwords [SQL Server], dormant logins
- dormant logins
- logins [SQL Server], upgrading dormant logins
- identifying dormant logins
- password hashes [SQL Server]
ms.assetid: ebe18a74-0375-4df4-b894-239f8fdabb64
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f78bca9bf2b99b2ab6f530613b64bc0e46c4001c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659193"
---
# <a name="dormant-sql-server-65-logins-cannot-be-upgraded"></a><span data-ttu-id="00115-102">Невозможно обновить неактивные имена входа SQL Server 6.5</span><span class="sxs-lookup"><span data-stu-id="00115-102">Dormant SQL Server 6.5 logins cannot be upgraded</span></span>
  <span data-ttu-id="00115-103">Советник по переходу обнаружил имя входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], пароль которого нельзя напрямую обновить до [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00115-103">Upgrade Advisor detected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login whose password cannot be directly upgraded to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="00115-104">Чтобы активировать имя входа, необходимо сбросить его пароль.</span><span class="sxs-lookup"><span data-stu-id="00115-104">To enable this login, you must reset its password.</span></span> <span data-ttu-id="00115-105">Можно изменить пароль с помощью инструкции ALTER LOGIN.</span><span class="sxs-lookup"><span data-stu-id="00115-105">You can reset the password by using ALTER LOGIN.</span></span>  
  
```  
ALTER LOGIN <login name> WITH PASSWORD = '<new password>' MUST_CHANGE  
```  
  
 <span data-ttu-id="00115-106">Новый пароль будет проверен на соответствие политике сложности паролей системы, если проверка политики не отключена.</span><span class="sxs-lookup"><span data-stu-id="00115-106">The new password will be validated against your system's password complexity policy, unless policy checking is disabled.</span></span> <span data-ttu-id="00115-107">Рекомендуется использовать сложные пароли и не отключать политику проверки.</span><span class="sxs-lookup"><span data-stu-id="00115-107">We recommend that you use complex passwords and not disable policy checking.</span></span> <span data-ttu-id="00115-108">Параметр MUST_CHANGE принуждает пользователя выбрать новый пароль.</span><span class="sxs-lookup"><span data-stu-id="00115-108">The MUST_CHANGE option forces the user to select a new password.</span></span> <span data-ttu-id="00115-109">Это не обязательно, но рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="00115-109">This is not required, but it is recommended.</span></span>  
  
 <span data-ttu-id="00115-110">Можно определить неактивные имена входа с помощью следующего запроса:</span><span class="sxs-lookup"><span data-stu-id="00115-110">You can identify dormant logins by using the following query:</span></span>  
  
```  
SELECT * FROM sysxlogins WHERE (xstatus & 2048) = 2048;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="00115-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="00115-111">See Also</span></span>  
 <span data-ttu-id="00115-112">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="00115-112">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="00115-113">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="00115-113">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
