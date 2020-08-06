---
title: Параметр конфигурации сервера "Agent XPs" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Agent XPs option
- extended stored procedures [SQL Server], SQL Server Agent
ms.assetid: 2e1c6c64-5ce7-4357-98c7-ac7763a9f9de
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 541c81ea8d9f782a9c1ea391824b90a6fee772d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665567"
---
# <a name="agent-xps-server-configuration-option"></a><span data-ttu-id="63fd3-102">Параметр конфигурации сервера «Agent XPs»</span><span class="sxs-lookup"><span data-stu-id="63fd3-102">Agent XPs Server Configuration Option</span></span>
  <span data-ttu-id="63fd3-103">Используйте параметр **Agent XPs** , чтобы включить расширенные хранимые процедуры агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на этом сервере.</span><span class="sxs-lookup"><span data-stu-id="63fd3-103">Use the **Agent XPs** option to enable the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent extended stored procedures on this server.</span></span> <span data-ttu-id="63fd3-104">Если этот параметр отключен, узел агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] недоступен в обозревателе объектов [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="63fd3-104">When this option is not enabled, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node is not available in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Object Explorer.</span></span>  
  
 <span data-ttu-id="63fd3-105">При использовании среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] для запуска службы агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] эти расширенные хранимые процедуры включаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="63fd3-105">When you use the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] tool to start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service, these extended stored procedures are enabled automatically.</span></span> <span data-ttu-id="63fd3-106">Дополнительные сведения см. в разделе [Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="63fd3-106">For more information, see [Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] <span data-ttu-id="63fd3-107">В обозревателе объектов среды содержимое узла агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не отображается до тех пор, пока эти расширенные хранимые процедуры не будут включены, вне зависимости от состояния службы агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63fd3-107">Object Explorer does not display the contents of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Agent node unless these extended stored procedures are enabled regardless of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service state.</span></span>  
  
 <span data-ttu-id="63fd3-108">Вы можете выбрать</span><span class="sxs-lookup"><span data-stu-id="63fd3-108">The possible values are:</span></span>  
  
-   <span data-ttu-id="63fd3-109">**0**, является признаком того, что расширенные хранимые процедуры агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] недоступны (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="63fd3-109">**0**, indicating that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent extended stored procedures are not available (the default).</span></span>  
  
-   <span data-ttu-id="63fd3-110">**1**, является признаком того, что расширенные хранимые процедуры агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] доступны.</span><span class="sxs-lookup"><span data-stu-id="63fd3-110">**1**, indicating that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent extended stored procedures are available.</span></span>  
  
 <span data-ttu-id="63fd3-111">Новые настройки вступают в силу сразу же, без остановки или перезапуска сервера.</span><span class="sxs-lookup"><span data-stu-id="63fd3-111">The setting takes effect immediately without a server stop and restart.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="63fd3-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="63fd3-112">Examples</span></span>  
 <span data-ttu-id="63fd3-113">В следующем примере включаются расширенные хранимые процедуры агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="63fd3-113">The following example enables the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent extended stored procedures.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'Agent XPs', 1;  
GO  
RECONFIGURE  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="63fd3-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="63fd3-114">See Also</span></span>  
 <span data-ttu-id="63fd3-115">[Задачи автоматизированного администрирования (агент SQL Server)](../../ssms/agent/sql-server-agent.md) </span><span class="sxs-lookup"><span data-stu-id="63fd3-115">[Automated Administration Tasks &#40;SQL Server Agent&#41;](../../ssms/agent/sql-server-agent.md) </span></span>  
 [<span data-ttu-id="63fd3-116">Запуск, остановка или приостановка службы агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="63fd3-116">Start, Stop, or Pause the SQL Server Agent Service</span></span>](../../ssms/agent/start-stop-or-pause-the-sql-server-agent-service.md)  
  
  
