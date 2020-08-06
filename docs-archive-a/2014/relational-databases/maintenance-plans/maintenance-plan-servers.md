---
title: План обслуживания (серверы) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.maintplanproperties.server.f1
- sql12.swb.maint.servers.f1
ms.assetid: ac24d1a8-dd2f-4162-b804-c0df1fc1e61d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c971edc9b641846068313f47ca410715ec552014
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658239"
---
# <a name="maintenance-plan-servers"></a><span data-ttu-id="f2718-102">План обслуживания (серверы)</span><span class="sxs-lookup"><span data-stu-id="f2718-102">Maintenance Plan (Servers)</span></span>
  <span data-ttu-id="f2718-103">Диалоговое окно **Серверы** используется для выбора серверов, для которых нужно запустить план обслуживания.</span><span class="sxs-lookup"><span data-stu-id="f2718-103">Use the **Servers** dialog box to select the servers where you want to run the maintenance plan.</span></span>  
  
 <span data-ttu-id="f2718-104">Многосерверную среду, содержащую один главный сервер и один или несколько целевых серверов, необходимо настроить для создания многосерверного плана обслуживания.</span><span class="sxs-lookup"><span data-stu-id="f2718-104">A multiserver environment containing one master server and one or more target servers must be configured to create a multiserver maintenance plan.</span></span> <span data-ttu-id="f2718-105">В многосерверных планах обслуживания локальный сервер настраивается, как и главный сервер.</span><span class="sxs-lookup"><span data-stu-id="f2718-105">For multiserver maintenance plans, the local server should be configured as a master server.</span></span> <span data-ttu-id="f2718-106">В многосерверной среде это диалоговое окно отображает главный **(локальный)** сервер и все соответствующие целевые серверы.</span><span class="sxs-lookup"><span data-stu-id="f2718-106">In multiserver environments, this dialog box displays the **(local)** master server and all corresponding target servers.</span></span> <span data-ttu-id="f2718-107">Для локального сервера создается одно задание агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f2718-107">One [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job is created for the local server.</span></span> <span data-ttu-id="f2718-108">Оно включается или отключается в зависимости от текущего выбора **(локального)** сервера.</span><span class="sxs-lookup"><span data-stu-id="f2718-108">It is enabled or disabled depending on whether you select the **(local)** server.</span></span> <span data-ttu-id="f2718-109">Если выбраны целевые серверы, то создается многосерверное задание, которое загружается на выделенные целевые серверы.</span><span class="sxs-lookup"><span data-stu-id="f2718-109">If target servers are selected, a multiserver job is created and downloaded to each of the selected target servers.</span></span> <span data-ttu-id="f2718-110">Если не выбран ни один целевой сервер, многосерверное задание удаляется.</span><span class="sxs-lookup"><span data-stu-id="f2718-110">If no target servers are selected, the multiserver job is deleted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2718-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="f2718-111">See Also</span></span>  
 <span data-ttu-id="f2718-112">[Планы обслуживания](maintenance-plans.md) </span><span class="sxs-lookup"><span data-stu-id="f2718-112">[Maintenance Plans](maintenance-plans.md) </span></span>  
 <span data-ttu-id="f2718-113">[Создание многосерверной среды](../../ssms/agent/create-a-multiserver-environment.md) </span><span class="sxs-lookup"><span data-stu-id="f2718-113">[Create a Multiserver Environment](../../ssms/agent/create-a-multiserver-environment.md) </span></span>  
 <span data-ttu-id="f2718-114">[Создание главного сервера](../../ssms/agent/make-a-master-server.md) </span><span class="sxs-lookup"><span data-stu-id="f2718-114">[Make a Master Server](../../ssms/agent/make-a-master-server.md) </span></span>  
 [<span data-ttu-id="f2718-115">Создание целевого сервера</span><span class="sxs-lookup"><span data-stu-id="f2718-115">Make a Target Server</span></span>](../../ssms/agent/make-a-target-server.md)  
  
  
