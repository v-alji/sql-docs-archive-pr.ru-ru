---
title: Ведение журнала для пакетов с балансировкой нагрузки на удаленных серверах | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- logs [Integration Services], remote packages
ms.assetid: fd571567-b625-4f9a-8b7e-42c5c588b11b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b45fa6607d6edc1559d8ebcbbbc7598e11eac408
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664325"
---
# <a name="logging-for-load-balanced-packages-on-remote-servers"></a><span data-ttu-id="fed18-102">Ведение журнала для пакетов с балансировкой нагрузки на удаленных серверах</span><span class="sxs-lookup"><span data-stu-id="fed18-102">Logging for Load Balanced Packages on Remote Servers</span></span>
  <span data-ttu-id="fed18-103">Для администратора проще управлять журналами для всех дочерних пакетов, выполняющихся на разных серверах, когда все дочерние пакеты используют один регистратор и все они выполняют запись в одно назначение.</span><span class="sxs-lookup"><span data-stu-id="fed18-103">It is easier for an administrator to manage the logs for all the child packages that are running on various servers when all the child packages use the same log provider and they all write to the same destination.</span></span> <span data-ttu-id="fed18-104">Одним из способов создания общего файла журнала для всех дочерних пакетов является настройка дочерних пакетов на запись своих событий в регистратор служб SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fed18-104">One way that you can create a common log file for all child packages is to configure the child packages to log their events to a SQL Server log provider.</span></span> <span data-ttu-id="fed18-105">Для всех пакетов можно задать использование одной базы данных, одного сервера и одного экземпляра сервера.</span><span class="sxs-lookup"><span data-stu-id="fed18-105">You can configure all the packages to use the same database, the same server, and the same instance of the server.</span></span>  
  
 <span data-ttu-id="fed18-106">При просмотре журналов администратору достаточно подключиться к одному серверу, чтобы просмотреть файлы журналов для всех дочерних пакетов.</span><span class="sxs-lookup"><span data-stu-id="fed18-106">To view the log files, the administrator only has to log on to a single server to view the log files for all child packages.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="fed18-107">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="fed18-107">Related Tasks</span></span>  
 <span data-ttu-id="fed18-108">Дополнительные сведения о способах включения ведения журналов в пакете см. в разделе [Включение средств ведения журналов в SQL Server Data Tools](../../2014/integration-services/enable-package-logging-in-sql-server-data-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fed18-108">For information about how to enable logging in a package, see [Enable Package Logging in SQL Server Data Tools](../../2014/integration-services/enable-package-logging-in-sql-server-data-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fed18-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="fed18-109">See Also</span></span>  
 [<span data-ttu-id="fed18-110">Ведение журналов в службах Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="fed18-110">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
  
