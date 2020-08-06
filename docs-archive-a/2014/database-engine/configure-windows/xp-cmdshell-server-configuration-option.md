---
title: Параметр конфигурации сервера "xp_cmdshell" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- xp_cmdshell
ms.assetid: c147c9e1-b81d-49c8-b800-3019f4d86a13
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a7feec1765cf6ffaa3e46a300a5155ae73fb13db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669092"
---
# <a name="xp_cmdshell-server-configuration-option"></a><span data-ttu-id="d21d9-102">Параметр конфигурации сервера «xp_cmdshell»</span><span class="sxs-lookup"><span data-stu-id="d21d9-102">xp_cmdshell Server Configuration Option</span></span>
  <span data-ttu-id="d21d9-103">Параметр **xp_cmdshell** — это параметр конфигурации сервера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , который позволяет системным администраторам контролировать, можно ли выполнять в системе расширенную хранимую процедуру **xp_cmdshell** .</span><span class="sxs-lookup"><span data-stu-id="d21d9-103">The **xp_cmdshell** option is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] server configuration option that enables system administrators to control whether the **xp_cmdshell** extended stored procedure can be executed on a system.</span></span> <span data-ttu-id="d21d9-104">По умолчанию в новых установках параметр **xp_cmdshell** отключен и может быть включен с помощью управления на основе политики или путем выполнения системной хранимой процедуры **sp_configure** , как показано в следующем примере кода:</span><span class="sxs-lookup"><span data-stu-id="d21d9-104">By default, the **xp_cmdshell** option is disabled on new installations and can be enabled by using the Policy-Based Management or by running the **sp_configure** system stored procedure as shown in the following code example:</span></span>  
  
```  
-- To allow advanced options to be changed.  
EXEC sp_configure 'show advanced options', 1;  
GO  
-- To update the currently configured value for advanced options.  
RECONFIGURE;  
GO  
-- To enable the feature.  
EXEC sp_configure 'xp_cmdshell', 1;  
GO  
-- To update the currently configured value for this feature.  
RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="d21d9-105">См. также:</span><span class="sxs-lookup"><span data-stu-id="d21d9-105">See Also</span></span>  
 <span data-ttu-id="d21d9-106">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d21d9-106">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="d21d9-107">Администрирование серверов с помощью управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="d21d9-107">Administer Servers by Using Policy-Based Management</span></span>](../../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md)  
  
  
