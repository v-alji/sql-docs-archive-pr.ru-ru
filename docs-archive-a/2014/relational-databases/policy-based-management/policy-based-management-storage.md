---
title: Хранение политик управления на основе политик | Документация Майкрософт
ms.custom: ''
ms.date: 08/10/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, storage
ms.assetid: d0cbf214-fc2e-4917-8d31-1d71c9ffa61d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0e775d038c5bb4f7a467f2691e374296f1389d84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731513"
---
# <a name="policy-based-management-storage"></a><span data-ttu-id="13483-102">Хранение политик управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="13483-102">Policy-Based Management Storage</span></span>
  <span data-ttu-id="13483-103">Политики хранятся в базе данных msdb.</span><span class="sxs-lookup"><span data-stu-id="13483-103">Policies are stored in the msdb database.</span></span> <span data-ttu-id="13483-104">После изменения политики или условия необходимо выполнить резервное копирование базы данных msdb.</span><span class="sxs-lookup"><span data-stu-id="13483-104">After a policy or condition is changed, msdb should be backed up.</span></span> <span data-ttu-id="13483-105">Дополнительные сведения см. в статье [Резервное копирование и восстановление системных баз данных (SQL Server)](../backup-restore/back-up-and-restore-of-system-databases-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="13483-105">For more information, see [Back Up and Restore of System Databases &#40;SQL Server&#41;](../backup-restore/back-up-and-restore-of-system-databases-sql-server.md).</span></span>  
  
## <a name="storing-policies"></a><span data-ttu-id="13483-106">Политики хранения</span><span class="sxs-lookup"><span data-stu-id="13483-106">Storing Policies</span></span>  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="13483-107">предусмотрены политики, которые можно использовать для наблюдения за экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="13483-107">includes policies that can be used to monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="13483-108">По умолчанию эти политики не установлены в, [!INCLUDE[ssDE](../../includes/ssde-md.md)] однако их можно импортировать из расположения установки по умолчанию: C:\Program Files (x86) \MICROSOFT SQL Server\120\Tools\Policies\DatabaseEngine\1033.</span><span class="sxs-lookup"><span data-stu-id="13483-108">By default, these policies are not installed on the [!INCLUDE[ssDE](../../includes/ssde-md.md)]; however, they can be imported from the default installation location of C:\Program Files (x86)\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033.</span></span>  
  
 <span data-ttu-id="13483-109">Можно создавать политики напрямую, при помощи меню **Файл/Создать** , и сохранять их в файл.</span><span class="sxs-lookup"><span data-stu-id="13483-109">You can directly create policies by using the **File/New** menu, and then saving them to a file.</span></span> <span data-ttu-id="13483-110">Это позволяет создавать политики при отсутствии подключения к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="13483-110">This enables you to create policies when you are not connected to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="13483-111">Журнал политик, вычисленных в текущем экземпляре компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] , поддерживается в системных таблицах базы данных msdb.</span><span class="sxs-lookup"><span data-stu-id="13483-111">Policy history for policies evaluated in the current instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is maintained in msdb system tables.</span></span> <span data-ttu-id="13483-112">Журнал политик, примененных к другим экземплярам компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] , к службам [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] или службам [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , не сохраняется.</span><span class="sxs-lookup"><span data-stu-id="13483-112">Policy history for policies applied to other instances of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] or applied to [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] or [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] is not retained.</span></span>  
  
  
