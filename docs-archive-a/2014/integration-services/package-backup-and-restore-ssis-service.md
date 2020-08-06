---
title: Резервное копирование и восстановление пакетов (службы SSIS) | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SSIS packages, backup and restore
- backing up packages [Integration Services]
- packages [Integration Services], backup and restore
- SQL Server Integration Services packages, backup and restore
- restoring packages [Integration Services]
- Integration Services packages, backup and restore
ms.assetid: c67d3b83-a6c8-40de-920f-9236de4ac87f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c4cd6f3856b69485c01e4b38d89e2f7e2ec56f74
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667804"
---
# <a name="package-backup-and-restore-ssis-service"></a><span data-ttu-id="08fb7-102">Резервное копирование и восстановление пакетов (службы SSIS)</span><span class="sxs-lookup"><span data-stu-id="08fb7-102">Package Backup and Restore (SSIS Service)</span></span>
    
> [!IMPORTANT]  
>  <span data-ttu-id="08fb7-103">В данном разделе описывается компонент [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] — служба Windows для управления пакетами служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="08fb7-103">This topic discusses the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, a Windows service for managing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span> [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] <span data-ttu-id="08fb7-104">поддерживает эту службу для обеспечения обратной совместимости с более ранними версиями служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="08fb7-104">supports the service for backward compatibility with earlier releases of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="08fb7-105">Начиная с [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], на сервере служб Integration Services можно управлять пакетами.</span><span class="sxs-lookup"><span data-stu-id="08fb7-105">Starting in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], you can manage objects such as packages on the Integration Services server.</span></span>  
  
 <span data-ttu-id="08fb7-106">Пакеты [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] могут быть сохранены в файловой системе или в msdb — системной базе данных [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="08fb7-106">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages can be saved to the file system or msdb, a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] system database.</span></span> <span data-ttu-id="08fb7-107">Для пакетов, сохраненных в msdb, может выполняться резервное копирование и восстановление с помощью функций резервного копирования и восстановления [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="08fb7-107">Packages saved to msdb can be backed up and restored using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] backup and restore features.</span></span>  
  
 <span data-ttu-id="08fb7-108">Дополнительные сведения о резервном копировании и восстановлении базы данных msdb см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="08fb7-108">For more information about backing up and restoring the msdb database, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="08fb7-109">Резервное копирование и восстановление баз данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="08fb7-109">Back Up and Restore of SQL Server Databases</span></span>](../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md)  
  
-   [<span data-ttu-id="08fb7-110">Резервное копирование и восстановление системных баз данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="08fb7-110">Back Up and Restore of System Databases &#40;SQL Server&#41;</span></span>](../relational-databases/backup-restore/back-up-and-restore-of-system-databases-sql-server.md)  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="08fb7-111">включают в себя программу командной строки **dtutil** (dtutil.exec), которая может использоваться для управления пакетами.</span><span class="sxs-lookup"><span data-stu-id="08fb7-111">includes the **dtutil** command-prompt utility (dtutil.exec), which you can use to manage packages.</span></span> <span data-ttu-id="08fb7-112">Дополнительные сведения см. в статье [dtutil Utility](dtutil-utility.md).</span><span class="sxs-lookup"><span data-stu-id="08fb7-112">For more information, see [dtutil Utility](dtutil-utility.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="08fb7-113">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="08fb7-113">Configuration Files</span></span>  
 <span data-ttu-id="08fb7-114">Файлы конфигурации, содержащиеся в пакетах, сохраняются в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="08fb7-114">Any configuration files that the packages include are stored in the file system.</span></span> <span data-ttu-id="08fb7-115">Эти файлы не копируются при создании резервной копии базы данных msdb, поэтому необходимо регулярно выполнять резервное копирование файлов конфигурации в рамках плана защиты пакетов, сохраняемых в msdb.</span><span class="sxs-lookup"><span data-stu-id="08fb7-115">These files are not backed up when you back up the msdb database; therefore, you should make sure that the configuration files are backed up regularly as part of your plan for securing packages saved to msdb.</span></span> <span data-ttu-id="08fb7-116">Чтобы включить конфигурации в резервную копию базы данных msdb, следует рассмотреть использование типа конфигурации [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] вместо файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="08fb7-116">To include configurations in the backup of the msdb database, you should consider using the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] configuration type instead of file-based configurations.</span></span>  
  
## <a name="packages-stored-in-the-file-system"></a><span data-ttu-id="08fb7-117">Пакеты, хранимые в файловой системе</span><span class="sxs-lookup"><span data-stu-id="08fb7-117">Packages Stored in the File System</span></span>  
 <span data-ttu-id="08fb7-118">Резервная копия пакетов, сохраненных в файловой системе, должна быть включена в план резервного копирования для защиты файловой системы сервера.</span><span class="sxs-lookup"><span data-stu-id="08fb7-118">The backup of packages that are saved to the file system should be included in the plan for backing up the file system of the server.</span></span> <span data-ttu-id="08fb7-119">В файле конфигурации служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , по умолчанию называющемся MsDtsSrvr.ini.xml, перечисляются папки на сервере, который контролируется службой.</span><span class="sxs-lookup"><span data-stu-id="08fb7-119">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service configuration file, which has the default name MsDtsSrvr.ini.xml, lists the folders on the server that the service monitors.</span></span> <span data-ttu-id="08fb7-120">Должно быть обеспечено резервное копирование этих папок.</span><span class="sxs-lookup"><span data-stu-id="08fb7-120">You should make sure these folders are backed up.</span></span> <span data-ttu-id="08fb7-121">Кроме того, пакеты могут сохраняться в других папках на сервере, поэтому необходимо включить эти папки в план резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="08fb7-121">Additionally, packages may be stored in other folders on the server and you should make sure to include these folders in the backup.</span></span>  
  
  
