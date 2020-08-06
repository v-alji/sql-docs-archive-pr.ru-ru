---
title: Замена использования расширенной хранимой процедуры xp_sqlagent_proxy_account новыми хранимыми процедурами | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- xp_sqlagent_proxy_account
ms.assetid: 0e3cc931-6237-41dd-bf0d-0c03f4d8fff2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d124ab73f4b4315550134f28ffad232b4a1c0ec2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666356"
---
# <a name="replace-usage-of-the-xp_sqlagent_proxy_account-extended-stored-procedure-with-new-stored-procedures"></a><span data-ttu-id="a8076-102">Замена вызовов расширенной хранимой процедуры xp_sqlagent_proxy_account на вызовы новых хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="a8076-102">Replace usage of the xp_sqlagent_proxy_account extended stored procedure with new stored procedures</span></span>
  <span data-ttu-id="a8076-103">Агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживает несколько посредников.</span><span class="sxs-lookup"><span data-stu-id="a8076-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent supports multiple proxies.</span></span> <span data-ttu-id="a8076-104">Они должны быть определены при помощи нового набора хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="a8076-104">You define these proxies by using a new set of stored procedures.</span></span> <span data-ttu-id="a8076-105">Дополнительные сведения о новых хранимых процедурах агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] см. в следующих разделах электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8076-105">For more information about the new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent stored procedures, see the following topics in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online:</span></span>  
  
-   <span data-ttu-id="a8076-106">sp_add_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])</span><span class="sxs-lookup"><span data-stu-id="a8076-106">"sp_add_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="a8076-107">sp_delete_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])</span><span class="sxs-lookup"><span data-stu-id="a8076-107">"sp_delete_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="a8076-108">sp_enum_login_for_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])</span><span class="sxs-lookup"><span data-stu-id="a8076-108">"sp_enum_login_for_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="a8076-109">sp_enum_proxy_for_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])</span><span class="sxs-lookup"><span data-stu-id="a8076-109">"sp_enum_proxy_for_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="a8076-110">sp_enum_sqlagent_subsystems ([!INCLUDE[tsql](../../includes/tsql-md.md)])</span><span class="sxs-lookup"><span data-stu-id="a8076-110">"sp_enum_sqlagent_subsystems ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="a8076-111">sp_grant_proxy_to_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])</span><span class="sxs-lookup"><span data-stu-id="a8076-111">"sp_grant_proxy_to_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="a8076-112">sp_grant_login_to_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])</span><span class="sxs-lookup"><span data-stu-id="a8076-112">"sp_grant_login_to_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="a8076-113">sp_help_proxy" ([!INCLUDE[tsql](../../includes/tsql-md.md)])</span><span class="sxs-lookup"><span data-stu-id="a8076-113">"sp_help_proxy" ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="a8076-114">sp_revoke_login_from_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])</span><span class="sxs-lookup"><span data-stu-id="a8076-114">"sp_revoke_login_from_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="a8076-115">sp_revoke_proxy_from_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])</span><span class="sxs-lookup"><span data-stu-id="a8076-115">"sp_revoke_proxy_from_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="a8076-116">sp_update_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])</span><span class="sxs-lookup"><span data-stu-id="a8076-116">"sp_update_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a8076-117">После обновления до [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] все инструкции, использующие **xp_sqlagent_proxy_account** расширенную хранимую процедуру, не будут работать.</span><span class="sxs-lookup"><span data-stu-id="a8076-117">After you upgrade to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], any statements that use the **xp_sqlagent_proxy_account** extended stored procedure will not work.</span></span> <span data-ttu-id="a8076-118">Используйте **sp_xp_cmdshell_proxy_account** вместо **xp_sqlagent_proxy_account** , чтобы задать прокси-сервер для **xp_cmdshell**.</span><span class="sxs-lookup"><span data-stu-id="a8076-118">Use **sp_xp_cmdshell_proxy_account** instead of **xp_sqlagent_proxy_account** to set the proxy for **xp_cmdshell**.</span></span>  
  
## <a name="component"></a><span data-ttu-id="a8076-119">Компонент</span><span class="sxs-lookup"><span data-stu-id="a8076-119">Component</span></span>  
 <span data-ttu-id="a8076-120">Агент[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8076-120">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8076-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="a8076-121">See Also</span></span>  
 [<span data-ttu-id="a8076-122">Проблемы обновления агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="a8076-122">SQL Server Agent Upgrade Issues</span></span>](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
  
