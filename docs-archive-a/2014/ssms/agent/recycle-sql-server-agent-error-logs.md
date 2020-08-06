---
title: Очистка журналов ошибок агента SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.errorlog.recyclesqlagenterrorlogs.f1
ms.assetid: 10bc2dd1-0505-4527-8ec7-d3b4e5d6352b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2b30f0a2ba9a2d861d4a36a86489757cde512fea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668579"
---
# <a name="recycle-sql-server-agent-error-logs"></a><span data-ttu-id="d099c-102">Очистка журналов ошибок агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="d099c-102">Recycle SQL Server Agent Error Logs</span></span>
  <span data-ttu-id="d099c-103">Используйте эту страницу для очистки [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] журналов ошибок агента.</span><span class="sxs-lookup"><span data-stu-id="d099c-103">Use this page to recycle the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Error Logs.</span></span> <span data-ttu-id="d099c-104">Очистка журнала закрывает текущий журнал ошибок агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и начинает новый журнал ошибок без перезапуска службы агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d099c-104">Recycling the log closes the current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log and starts a new error log without restarting the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span> <span data-ttu-id="d099c-105">Учтите, что агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] содержит девять самых последних журналов ошибок.</span><span class="sxs-lookup"><span data-stu-id="d099c-105">Notice that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent maintains the nine most recent error logs.</span></span> <span data-ttu-id="d099c-106">Если в наличии все девять журналов, при очистке журнала ошибок агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] удаляет самый старый журнал.</span><span class="sxs-lookup"><span data-stu-id="d099c-106">If there are already nine error logs present, recycling the error log causes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to remove the oldest error log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d099c-107">См. также:</span><span class="sxs-lookup"><span data-stu-id="d099c-107">See Also</span></span>  
 [<span data-ttu-id="d099c-108">Журнал ошибок агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="d099c-108">SQL Server Agent Error Log</span></span>](sql-server-agent-error-log.md)  
  
  
