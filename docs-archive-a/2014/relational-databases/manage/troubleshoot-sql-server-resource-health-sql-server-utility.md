---
title: Устранение неполадок исправности ресурсов SQL Server (служебная программа SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 614f07b5-f221-4013-9f8d-22964cf42270
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 182225dd618dd1e9e058c549bdc07818813ba764
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656398"
---
# <a name="troubleshoot-sql-server-resource-health-sql-server-utility"></a><span data-ttu-id="6e19f-102">Устранение неполадок исправности ресурсов SQL Server (служебная программа SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6e19f-102">Troubleshoot SQL Server Resource Health (SQL Server Utility)</span></span>
  <span data-ttu-id="6e19f-103">Устранение неполадок исправности ресурсов, обнаруженных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] UCP, может потребовать устранения перегрузки ЦП на компьютере или экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], а также устранения перегрузки ЦП для приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="6e19f-103">Troubleshooting resource health issues identified by a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] UCP might include mitigating overutilized CPU on a computer or on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or mitigating overutilized CPU for a data-tier application.</span></span> <span data-ttu-id="6e19f-104">Также могут потребовать устранения такие проблемы, как использование файлами баз данных слишком большой части файлового пространства или выделение слишком большого места на диске в томе хранилища.</span><span class="sxs-lookup"><span data-stu-id="6e19f-104">Other issues might include resolving overutilized file space for database files or resolving overutilization of allocated disk space on a storage volume.</span></span>  
  
 <span data-ttu-id="6e19f-105">Обратите внимание, что если база данных находится в аварийном режиме, состояние работоспособности покажет чрезмерное использование пространства для файла журнала.</span><span class="sxs-lookup"><span data-stu-id="6e19f-105">Note that if a database is in "emergency" state, the health state will display overutilized log file space.</span></span>  
  
 <span data-ttu-id="6e19f-106">Дополнительные сведения об ошибках при сборе данных, вызывающих отображение серых значков в представлении списка управляемых экземпляров в UCP, см. в разделе [Устранение неполадок служебной программы SQL Server](../../database-engine/troubleshoot-the-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="6e19f-106">For more information about failed data collection resulting in gray status icons in the managed instance list view on a UCP, see [Troubleshoot the SQL Server Utility](../../database-engine/troubleshoot-the-sql-server-utility.md).</span></span> <span data-ttu-id="6e19f-107">Дополнительные сведения о начале работы со служебной программой [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] см. в разделе [Функции и задачи служебной программы SQL Server](sql-server-utility-features-and-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="6e19f-107">For more information about getting started with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility, see [SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md).</span></span>  
  
 <span data-ttu-id="6e19f-108">Дополнительные сведения об устранении конкретных проблем, связанных с исправностью ресурсов, обнаруженных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] UCP, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="6e19f-108">For more information about mitigating specific resource health issues identified by a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] UCP, see the following topics:</span></span>  
  
-   [<span data-ttu-id="6e19f-109">Как определить версию и выпуск установленного SQL Server</span><span class="sxs-lookup"><span data-stu-id="6e19f-109">How to identify your SQL Server version and edition</span></span>](https://go.microsoft.com/fwlink/?LinkID=178504)  
  
-   [<span data-ttu-id="6e19f-110">Устранение связанных с производительностью неполадок в SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="6e19f-110">Troubleshooting Performance Problems in SQL Server 2008</span></span>](https://go.microsoft.com/fwlink/?LinkId=151354)  
  
  
