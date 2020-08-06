---
title: Проверка используемых файлов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ccd65867-d4c0-43b2-8361-7fd41c6f79ac
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 51505b0dece146b7f6fcdf982e6f88a5715357e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659226"
---
# <a name="check-files-in-use"></a><span data-ttu-id="5569d-102">Проверка используемых файлов</span><span class="sxs-lookup"><span data-stu-id="5569d-102">Check Files In Use</span></span>
  <span data-ttu-id="5569d-103">Чтобы избежать необходимости перезагрузки Windows после установки обновлений для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , на странице «Проверка используемых файлов» можно найти процессы, которые блокируют файлы, необходимые программе установки обновлений [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5569d-103">To avoid restarting Windows after you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] updates, use the Check Files in Use page to identify processes that are locking files required by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] update Setup program.</span></span>  
  
 <span data-ttu-id="5569d-104">Остановите все приложения и службы, которые соединяются с обновляемыми экземплярами [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5569d-104">Stop all applications and services that make connections to the instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are being updated.</span></span> <span data-ttu-id="5569d-105">Это также касается среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] и среды [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5569d-105">This includes stopping [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="5569d-106">Если программа установки обнаруживает заблокированные файлы во время установки, может возникнуть необходимость в перезагрузке компьютера после завершения установки.</span><span class="sxs-lookup"><span data-stu-id="5569d-106">If Setup determines that files are locked during installation, you might have to restart your computer after installation is completed.</span></span> <span data-ttu-id="5569d-107">При необходимости программа установки запрашивает пользователя о перезагрузке компьютера.</span><span class="sxs-lookup"><span data-stu-id="5569d-107">If necessary, Setup prompts you to restart your computer.</span></span> <span data-ttu-id="5569d-108">Если программе установки необходимо остановить работу службы во время установки, эта служба будет перезапущена после завершения установки.</span><span class="sxs-lookup"><span data-stu-id="5569d-108">If the Setup program must stop a service during installation, it will restart the service after installation is completed.</span></span>  
  
 <span data-ttu-id="5569d-109">Чтобы устранить необходимость в перезагрузке компьютера после установки, программа установки отобразит список процессов, блокирующих файлы.</span><span class="sxs-lookup"><span data-stu-id="5569d-109">To eliminate the requirement to restart your computer after installation, Setup displays a list of processes that are locking files.</span></span> <span data-ttu-id="5569d-110">Остановите процессы или приложения, указанные в списке.</span><span class="sxs-lookup"><span data-stu-id="5569d-110">Stop or end the processes and applications in the list.</span></span> <span data-ttu-id="5569d-111">После этого нажмите кнопку **Обновить проверку** , чтобы выполнить проверку повторно.</span><span class="sxs-lookup"><span data-stu-id="5569d-111">Then click **Refresh check** to rerun the check.</span></span> <span data-ttu-id="5569d-112">Нажмите кнопку **Остановить проверку** , чтобы прервать выполнение проверки.</span><span class="sxs-lookup"><span data-stu-id="5569d-112">Click **Stop check** to end a check that is running.</span></span> <span data-ttu-id="5569d-113">Если заблокированные файлы не обнаружены, таблица будет пустой.</span><span class="sxs-lookup"><span data-stu-id="5569d-113">If locked files are not found, the table is empty.</span></span> <span data-ttu-id="5569d-114">После того как все заблокированные процессы были закрыты или остановлены, нажмите кнопку **Далее** , чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="5569d-114">When all locked processes have been closed or stopped, click **Next** to continue.</span></span>  
  
 <span data-ttu-id="5569d-115">Программа установки записывает сведения в файлы журналов.</span><span class="sxs-lookup"><span data-stu-id="5569d-115">Setup logs the information in the log files.</span></span> <span data-ttu-id="5569d-116">Дополнительные сведения о просмотре файлов журналов см. в статьях [Просмотр и чтение файлов журнала настройки SQL Server](../../database-engine/install-windows/view-and-read-sql-server-setup-log-files.md) и [Инструкция по чтению файла журнала настройки SQL Server](https://go.microsoft.com/fwlink/?LinkID=134490).</span><span class="sxs-lookup"><span data-stu-id="5569d-116">For more information about how to view the log files, see [View and Read SQL Server Setup Log Files](../../database-engine/install-windows/view-and-read-sql-server-setup-log-files.md) and [How to: Read a SQL Server Setup Log File](https://go.microsoft.com/fwlink/?LinkID=134490).</span></span>  
  
 <span data-ttu-id="5569d-117">В файл журнала включается следующая информация.</span><span class="sxs-lookup"><span data-stu-id="5569d-117">The following information is included in the log file:</span></span>  
  
-   <span data-ttu-id="5569d-118">Имя процесса</span><span class="sxs-lookup"><span data-stu-id="5569d-118">Name of the process</span></span>  
  
-   <span data-ttu-id="5569d-119">Имя компонента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5569d-119">Name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] feature</span></span>  
  
-   <span data-ttu-id="5569d-120">Тип процесса</span><span class="sxs-lookup"><span data-stu-id="5569d-120">Process type</span></span>  
  
-   <span data-ttu-id="5569d-121">Учетная запись, под которой выполняется процесс</span><span class="sxs-lookup"><span data-stu-id="5569d-121">Account under which the process is running</span></span>  
  
-   <span data-ttu-id="5569d-122">ИД процесса</span><span class="sxs-lookup"><span data-stu-id="5569d-122">Process ID</span></span>  
  
-   <span data-ttu-id="5569d-123">Имя заблокированного файла</span><span class="sxs-lookup"><span data-stu-id="5569d-123">Name of the file that is locked</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="5569d-124">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="5569d-124">UI element list</span></span>  
  
|<span data-ttu-id="5569d-125">Имя</span><span class="sxs-lookup"><span data-stu-id="5569d-125">Name</span></span>|<span data-ttu-id="5569d-126">Описание</span><span class="sxs-lookup"><span data-stu-id="5569d-126">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="5569d-127">Процесс</span><span class="sxs-lookup"><span data-stu-id="5569d-127">Process</span></span>|<span data-ttu-id="5569d-128">Отображает полное имя процесса, использующего файлы, которые будут обновлены.</span><span class="sxs-lookup"><span data-stu-id="5569d-128">Displays the full name of the process that is using the files to be updated.</span></span>|  
|<span data-ttu-id="5569d-129">Type</span><span class="sxs-lookup"><span data-stu-id="5569d-129">Type</span></span>|<span data-ttu-id="5569d-130">Отображает тип процесса.</span><span class="sxs-lookup"><span data-stu-id="5569d-130">Displays the type of process.</span></span>|  
|<span data-ttu-id="5569d-131">Учетная запись</span><span class="sxs-lookup"><span data-stu-id="5569d-131">Account</span></span>|<span data-ttu-id="5569d-132">Отображает учетную запись, под которой выполняется процесс.</span><span class="sxs-lookup"><span data-stu-id="5569d-132">Displays the account under which the process is running.</span></span>|  
|<span data-ttu-id="5569d-133">ИД процесса</span><span class="sxs-lookup"><span data-stu-id="5569d-133">Process ID</span></span>|<span data-ttu-id="5569d-134">Отображает идентификатор процесса.</span><span class="sxs-lookup"><span data-stu-id="5569d-134">Displays the process ID.</span></span>|  
  
  
