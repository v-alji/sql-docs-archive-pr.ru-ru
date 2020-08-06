---
title: Автономные базы данных с группами доступности AlwaysOn (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- contained database [SQL Server], AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: cacce3ae-e940-4566-8298-6607c4268e74
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 74c8a0b41ee7224dad83fb41691a4898c15b7b38
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655374"
---
# <a name="contained-databases-with-always-on-availability-groups-sql-server"></a><span data-ttu-id="7ef9d-102">Автономные базы данных с группами доступности AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7ef9d-102">Contained Databases with Always On Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="7ef9d-103">Этот раздел содержит сведения об использовании автономной базы данных с [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7ef9d-103">This topic contains information about the using a contained database with [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="7ef9d-104">**В этом разделе.**</span><span class="sxs-lookup"><span data-stu-id="7ef9d-104">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="7ef9d-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="7ef9d-105">Prerequisites</span></span>](#Prerequisites)  
  
-   [<span data-ttu-id="7ef9d-106">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="7ef9d-106">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="7ef9d-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="7ef9d-107">Prerequisites</span></span>  
  
-   <span data-ttu-id="7ef9d-108">Перед добавлением автономной базы данных в группу доступности убедитесь, что параметру сервера `contained database authentication` присвоено значение `1` на каждом экземпляре, на котором размещена реплика доступности.</span><span class="sxs-lookup"><span data-stu-id="7ef9d-108">Before adding a contained database to an availability group, ensure that the `contained database authentication` server option is set to `1` on every server instance that hosts an availability replica for the availability group.</span></span> <span data-ttu-id="7ef9d-109">Дополнительные сведения см. в разделах [Параметр конфигурации сервера "проверка подлинности автономной базы данных"](../../configure-windows/contained-database-authentication-server-configuration-option.md) и [Параметры конфигурации сервера (SQL Server)](../../configure-windows/server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7ef9d-109">For more information, see [contained database authentication Server Configuration Option](../../configure-windows/contained-database-authentication-server-configuration-option.md) and [Server Configuration Options &#40;SQL Server&#41;](../../configure-windows/server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="7ef9d-110">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="7ef9d-110">Related Tasks</span></span>  
  
-   [<span data-ttu-id="7ef9d-111">Параметры конфигурации сервера (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7ef9d-111">Server Configuration Options &#40;SQL Server&#41;</span></span>](../../configure-windows/server-configuration-options-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="7ef9d-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="7ef9d-112">See Also</span></span>  
 <span data-ttu-id="7ef9d-113">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7ef9d-113">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="7ef9d-114">Автономные базы данных</span><span class="sxs-lookup"><span data-stu-id="7ef9d-114">Contained Databases</span></span>](../../../relational-databases/databases/contained-databases.md)  
  
  
