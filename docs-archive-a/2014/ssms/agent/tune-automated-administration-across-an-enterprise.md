---
title: Настройка автоматизированного администрирования в организации | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- performance [SQL Server], automated administration
- tuning automated administration [SQL Server]
- monitoring performance [SQL Server], automated administration
ms.assetid: 671fed35-3859-4b0d-8f38-4dd07436857e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 52fef95cd13beafef89701196a445a90e6fc1eb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665750"
---
# <a name="tune-automated-administration-across-an-enterprise"></a><span data-ttu-id="cb964-102">Настройка автоматизированного администрирования в организации</span><span class="sxs-lookup"><span data-stu-id="cb964-102">Tune Automated Administration Across an Enterprise</span></span>
  <span data-ttu-id="cb964-103">Система многосерверного администрирования с применением агента Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] использует преимущества средств автоматической настройки, реализованных в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb964-103">Multiserver administration with Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent takes advantage of the self-tuning features of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cb964-104">Таким образом, в нормальных условиях дополнительная настройка заданий не требуется.</span><span class="sxs-lookup"><span data-stu-id="cb964-104">Therefore, under normal conditions, additional job tuning is not necessary.</span></span> <span data-ttu-id="cb964-105">Тем не менее при выполнении заданий, формировании предупреждений и уведомлении операторов нагрузка на сеть увеличивается.</span><span class="sxs-lookup"><span data-stu-id="cb964-105">However, network loads increase when you run jobs, generate alerts, and notify operators.</span></span> <span data-ttu-id="cb964-106">Чтобы свести к минимуму объем трафика, передаваемого при этих операциях, можно настроить систему автоматизированного администрирования во всей организации.</span><span class="sxs-lookup"><span data-stu-id="cb964-106">You can tune automated administration across an enterprise to minimize the network traffic these activities cause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb964-107">См. также:</span><span class="sxs-lookup"><span data-stu-id="cb964-107">See Also</span></span>  
 [<span data-ttu-id="cb964-108">Счетчики производительности</span><span class="sxs-lookup"><span data-stu-id="cb964-108">Performance Counters</span></span>](../../integration-services/performance/performance-counters.md)  
  
  
