---
title: Требования к учетной записи службы для обновления до SQL Server 2008 на контроллере домена | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- domain controllers
- service accounts
- network service accounts
- local service accounts
ms.assetid: 574245b6-11e2-4849-b0ca-836d673ecd0d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0680e09548e38760f6ac317fec63152486a4e5fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659166"
---
# <a name="service-account-requirements-for-upgrading-to-sql-server-2008-on-a-domain-controller"></a><span data-ttu-id="85400-102">Требования к учетной записи службы для обновления до SQL Server 2008 на контроллере домена</span><span class="sxs-lookup"><span data-stu-id="85400-102">Service account requirements for upgrading to SQL Server 2008 on a domain controller</span></span>
  <span data-ttu-id="85400-103">Советник по переходу обнаружил экземпляр, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] работающий под сетевой службой или учетной записью локальной службы на [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] контроллере домена.</span><span class="sxs-lookup"><span data-stu-id="85400-103">Upgrade Advisor detected an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running under a Network Service or Local Service account on a [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] domain controller.</span></span> <span data-ttu-id="85400-104">При установке [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на контроллере домена [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не могут выполняться с правами доступа учетной записи Local Service или Network Service.</span><span class="sxs-lookup"><span data-stu-id="85400-104">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed on a [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] domain controller, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services cannot run under Local Service account or Network Service account privileges.</span></span>  
  
## <a name="component"></a><span data-ttu-id="85400-105">Компонент</span><span class="sxs-lookup"><span data-stu-id="85400-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="85400-106">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="85400-106">Corrective Action</span></span>  
 <span data-ttu-id="85400-107">Убедитесь, что все учетные записи служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] назначены учетным записям домена или локальной системы.</span><span class="sxs-lookup"><span data-stu-id="85400-107">Make sure that all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service accounts are assigned to either Domain accounts or Local System accounts.</span></span> <span data-ttu-id="85400-108">Если этого не сделать перед обновлением, процесс установки будет заблокирован.</span><span class="sxs-lookup"><span data-stu-id="85400-108">Failure to make this change before upgrading will block Setup.</span></span> <span data-ttu-id="85400-109">Исключениями являются учетные записи службы SQL Writer, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и службы поддержки Active Directory, так как в них использование учетной записи сетевой службы жестко закодировано и не может быть изменено.</span><span class="sxs-lookup"><span data-stu-id="85400-109">The service accounts SQL Writer, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Active Directory Helper services are exceptions because they are hard-coded to the Network Service account and cannot be changed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85400-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="85400-110">See Also</span></span>  
 <span data-ttu-id="85400-111">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="85400-111">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="85400-112">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="85400-112">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
