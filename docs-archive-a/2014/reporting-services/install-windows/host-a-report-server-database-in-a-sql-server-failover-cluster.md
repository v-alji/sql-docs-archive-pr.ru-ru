---
title: Размещение базы данных сервера отчетов в отказоустойчивом кластере SQL Server | Документы Майкрософт
ms.custom: ''
ms.date: 08/10/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 7bd5f019-2857-452f-a023-cc3b9e93aec4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 921ce03fd08e7820266b828d5848f64db1e257ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732434"
---
# <a name="host-a-report-server-database-in-a-sql-server-failover-cluster"></a><span data-ttu-id="af9d9-102">Размещение базы данных сервера отчетов в отказоустойчивом кластере SQL Server</span><span class="sxs-lookup"><span data-stu-id="af9d9-102">Host a Report Server Database in a SQL Server Failover Cluster</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="af9d9-103">предоставляет поддержку отказоустойчивой кластеризации, поэтому можно использовать несколько дисков для одного или более экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="af9d9-103">provides failover clustering support so that you can use multiple disks for one or more [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances.</span></span> <span data-ttu-id="af9d9-104">Отказоустойчивая кластеризация поддерживается только для базы данных сервера отчетов, служба Report Server не может работать как часть отказоустойчивого кластера.</span><span class="sxs-lookup"><span data-stu-id="af9d9-104">Failover clustering is supported only for the report server database; you cannot run the Report Server service as part of a failover cluster.</span></span>  
  
 <span data-ttu-id="af9d9-105">Чтобы разместить базу данных сервера отчетов в отказоустойчивом кластере [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , кластер должен быть предварительно установлен и настроен.</span><span class="sxs-lookup"><span data-stu-id="af9d9-105">To host a report server database on a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, the cluster must already be installed and configured.</span></span> <span data-ttu-id="af9d9-106">После этого можно выбрать отказоустойчивый кластер в качестве имени сервера при создании базы данных сервера отчетов на странице «Настройка базы данных» программы настройки служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="af9d9-106">You can then select the failover cluster as the server name when you create the report server database in the Database Setup page of the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool.</span></span>  
  
 <span data-ttu-id="af9d9-107">Хотя служба Report Server и не может быть частью отказоустойчивого кластера, службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] можно установить на компьютере с установленным отказоустойчивым кластером [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="af9d9-107">Although the Report Server service cannot participate in a failover cluster, you can install [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] on a computer that has a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster installed.</span></span> <span data-ttu-id="af9d9-108">Сервер отчетов работает независимо от отказоустойчивого кластера.</span><span class="sxs-lookup"><span data-stu-id="af9d9-108">The report server runs independently of the failover cluster.</span></span> <span data-ttu-id="af9d9-109">При установке сервера отчетов на компьютере, являющемся частью экземпляра отработки отказа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не обязательно использовать отказоустойчивый кластер для базы данных сервера отчетов. Для размещения базы данных можно использовать другой экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="af9d9-109">If you install a report server on a computer that is part of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover instance, you are not required to use the failover cluster for the report server database; you can use a different [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance to host the database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af9d9-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="af9d9-110">See Also</span></span>  
 <span data-ttu-id="af9d9-111">[База данных сервера отчетов (службы Reporting Services в собственном режиме)](../report-server/report-server-database-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="af9d9-111">[Report Server Database &#40;SSRS Native Mode&#41;](../report-server/report-server-database-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="af9d9-112">Создание базы данных сервера отчетов (диспетчер конфигурации служб SSRS)</span><span class="sxs-lookup"><span data-stu-id="af9d9-112">Create a Report Server Database  &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/create-a-report-server-database-ssrs-configuration-manager.md)  
  
  
