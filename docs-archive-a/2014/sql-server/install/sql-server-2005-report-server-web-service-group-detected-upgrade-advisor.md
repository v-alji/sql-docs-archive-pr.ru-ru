---
title: Обнаружена группа веб-служб сервера отчетов SQL Server 2005 (советник по переходу) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- deployment [Reporting Services]
ms.assetid: 699d24eb-7756-4b41-9294-ef1a94b2f267
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 70be2b9c4e7abd55daaa752830a73cbe6e222659
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751692"
---
# <a name="sql-server-2005-report-server-web-service-group-detected-upgrade-advisor"></a><span data-ttu-id="c3799-102">Обнаружена группа веб-служб сервера отчетов SQL Server 2005 (советник по переходу)</span><span class="sxs-lookup"><span data-stu-id="c3799-102">SQL Server 2005 Report Server Web Service group detected (Upgrade Advisor)</span></span>
  <span data-ttu-id="c3799-103">Советник по переходу обнаружил, что [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] экземпляр связан с [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] группой веб-служб сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="c3799-103">Upgrade Advisor detected that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance is associated with a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Report Server Web service group.</span></span>  
  
||  
|-|  
|<span data-ttu-id="c3799-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Собственный режим.</span><span class="sxs-lookup"><span data-stu-id="c3799-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="c3799-105">Компонент</span><span class="sxs-lookup"><span data-stu-id="c3799-105">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="c3799-106">Описание</span><span class="sxs-lookup"><span data-stu-id="c3799-106">Description</span></span>  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]<span data-ttu-id="c3799-107">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]не использует [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Группа веб-службы сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="c3799-107">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] does not use the [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Report Server Web service group.</span></span> <span data-ttu-id="c3799-108">При обновлении с [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] до [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] эта группа служб удаляется, а пользовательские списки управления доступом (ACL) для этой группы или пользователи, входящие в группу, при обновлении не сохраняются.</span><span class="sxs-lookup"><span data-stu-id="c3799-108">When you upgrade from [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], this service group is deleted and custom Access Control Lists (ACLs) for this group or users who belong to the group are not retained during the upgrade.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="c3799-109">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="c3799-109">Corrective Action</span></span>  
 <span data-ttu-id="c3799-110">Перед обновлением выполните резервное копирование всех списков управления доступом или пользователей, относящихся к группе веб-служб сервера отчетов [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3799-110">Before you upgrade, back up any custom ACLs or users who belong to the [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Report Server Web service group.</span></span> <span data-ttu-id="c3799-111">Для этого можно использовать средство командной строки **Icacls.exe** с [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] пакетом обновления 2 (SP2) и более поздней версии или средство командной строки Cacls.exe в операционных системах Windows до [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] SP2.</span><span class="sxs-lookup"><span data-stu-id="c3799-111">To do this, you can use the **Icacls.exe** command-line tool in [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] SP2 and later or the Cacls.exe command-line tool in Windows operating systems prior to [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] SP2.</span></span> <span data-ttu-id="c3799-112">Дополнительные сведения о синтаксисе этих средств см. в документации по продукту Windows.</span><span class="sxs-lookup"><span data-stu-id="c3799-112">For more information about the syntax for these tools, see the Windows product documentation.</span></span> <span data-ttu-id="c3799-113">После успешного завершения установки примените пользовательские списки управления доступом или пользователей к группе Windows сервера отчетов [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] для конкретного экземпляра сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="c3799-113">After setup successfully completes, apply the custom ACLs or users to the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Report Server Windows group for your report server instance.</span></span> <span data-ttu-id="c3799-114">[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]Группа Windows сервера отчетов имеет вид SQLServerReportServerUser $ \<*computer_name*> $ \<*instance_name*> .</span><span class="sxs-lookup"><span data-stu-id="c3799-114">The [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Report Server Windows group takes the form of SQLServerReportServerUser$\<*computer_name*>$\<*instance_name*>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3799-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="c3799-115">See Also</span></span>  
 [<span data-ttu-id="c3799-116">Reporting Services проблем обновления &#40;советник по переходу&#41;</span><span class="sxs-lookup"><span data-stu-id="c3799-116">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
