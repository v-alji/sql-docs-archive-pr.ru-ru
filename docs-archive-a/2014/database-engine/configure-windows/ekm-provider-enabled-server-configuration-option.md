---
title: Параметр конфигурации сервера "EKM provider enabled" | Документы Майкрософт
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- external encryption provider
helpviewer_keywords:
- EKM provider enabled option
ms.assetid: da58ed50-3a13-4172-9065-960559d8f383
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1b44e7f5e0801bb370a98abe79a6ea449c6f7409
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750143"
---
# <a name="ekm-provider-enabled-server-configuration-option"></a><span data-ttu-id="f5bb3-102">Включенный параметр конфигурации сервера поставщика расширенного управления ключами</span><span class="sxs-lookup"><span data-stu-id="f5bb3-102">EKM provider enabled Server Configuration Option</span></span>
  <span data-ttu-id="f5bb3-103">Параметр `EKM provider enabled` управляет поддержкой устройства расширенного управления ключами в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5bb3-103">The `EKM provider enabled` option controls Extensible Key Management device support in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f5bb3-104">По умолчанию этот параметр отключен.</span><span class="sxs-lookup"><span data-stu-id="f5bb3-104">By default this option is off.</span></span>  
  
 <span data-ttu-id="f5bb3-105">Чтобы включить или отключить эту функцию, выполните одну из приведенных ниже команд `sp_configure`:</span><span class="sxs-lookup"><span data-stu-id="f5bb3-105">To enable or disable the feature, issue one of the following `sp_configure` commands:</span></span>  
  
```  
/* Enable the external encryption provider option */  
sp_configure 'EKM provider enabled', 1  
/* Disable the external encryption provider option */  
sp_configure 'EKM provider enabled', 0  
```  
  
> [!NOTE]  
>  <span data-ttu-id="f5bb3-106">Этот параметр не включен ни в один из выпусков [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5bb3-106">This option is not enabled in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f5bb3-107">Перечень функций, поддерживаемых в разных выпусках [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], см. в разделе [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="f5bb3-107">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5bb3-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="f5bb3-108">See Also</span></span>  
 <span data-ttu-id="f5bb3-109">[Расширенное управление ключами (EKM)](../../relational-databases/security/encryption/extensible-key-management-ekm.md) </span><span class="sxs-lookup"><span data-stu-id="f5bb3-109">[Extensible Key Management &#40;EKM&#41;](../../relational-databases/security/encryption/extensible-key-management-ekm.md) </span></span>  
 <span data-ttu-id="f5bb3-110">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f5bb3-110">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="f5bb3-111">[Наблюдение за использованием ресурсов (системный монитор)](../../relational-databases/performance-monitor/monitor-resource-usage-system-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="f5bb3-111">[Monitor Resource Usage &#40;System Monitor&#41;](../../relational-databases/performance-monitor/monitor-resource-usage-system-monitor.md) </span></span>  
 <span data-ttu-id="f5bb3-112">[sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f5bb3-112">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="f5bb3-113">RECONFIGURE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f5bb3-113">RECONFIGURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/reconfigure-transact-sql)  
  
  
