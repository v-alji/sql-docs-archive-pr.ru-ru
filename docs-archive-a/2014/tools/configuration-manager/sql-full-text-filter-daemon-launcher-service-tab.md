---
title: Средство запуска управляющей программы полнотекстовой фильтрации SQL (вкладка "Служба") | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 6aad7ebe-c4be-4d37-8536-61502f51faa2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8f0d9c76d7d92947dd17fe2ed6e912e3d6baa6bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667980"
---
# <a name="sql-full-text-filter-daemon-launcher-service-tab"></a><span data-ttu-id="c114e-102">Средство запуска управляющей программы полнотекстовой фильтрации SQL (вкладка «Служба»)</span><span class="sxs-lookup"><span data-stu-id="c114e-102">SQL Full-text Filter Daemon Launcher (Service Tab)</span></span>
  <span data-ttu-id="c114e-103">Начиная с версии [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], в полнотекстовом поиске [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] используется средство запуска управляющей программы полнотекстовой фильтрации SQL (средство запуска FDHOST).</span><span class="sxs-lookup"><span data-stu-id="c114e-103">Beginning in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], the SQL Full-text Filter Daemon Launcher (FDHOST Launcher) service is used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] full-text.</span></span> <span data-ttu-id="c114e-104">Эта служба должна быть запущена при использовании полнотекстового поиска.</span><span class="sxs-lookup"><span data-stu-id="c114e-104">This service must be running if you use full-text search.</span></span> <span data-ttu-id="c114e-105">Сведения о хост-процессах управляющей программы фильтрации см. в разделе «Архитектура компонента Full-Text Search» электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c114e-105">For information about the filter daemon host processes, see "Full-Text Search Architecture" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="c114e-106">Используйте вкладку **Служба**в диалоговом окне **Свойства запуска управляющей программы полнотекстовой фильтрации (SQL)** , чтобы просмотреть или указать следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="c114e-106">Use the **Service**tab on the **SQL Full-text Filter Daemon LauncherProperties** dialog box to view or specify the following options.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c114e-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="c114e-107">Options</span></span>  
 <span data-ttu-id="c114e-108">**Путь к двоичным файлам**</span><span class="sxs-lookup"><span data-stu-id="c114e-108">**Binary Path**</span></span>  
 <span data-ttu-id="c114e-109">Отображает расположение программных файлов, используемых этой службой.</span><span class="sxs-lookup"><span data-stu-id="c114e-109">Lists the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="c114e-110">**Контроль ошибок**</span><span class="sxs-lookup"><span data-stu-id="c114e-110">**Error Control**</span></span>  
 <span data-ttu-id="c114e-111">1 означает `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="c114e-111">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="c114e-112">Если службе не удалось запуститься при запуске компьютера, программа запуска заносит в журнал сообщение об ошибке и выдает всплывающее сообщение об ошибке, но продолжает выполнять операцию запуска.</span><span class="sxs-lookup"><span data-stu-id="c114e-112">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="c114e-113">Это значение невозможно изменить.</span><span class="sxs-lookup"><span data-stu-id="c114e-113">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="c114e-114">**Код завершения**</span><span class="sxs-lookup"><span data-stu-id="c114e-114">**Exit Code**</span></span>  
 <span data-ttu-id="c114e-115">При возникновении ошибки ее номер выводится в этом окне.</span><span class="sxs-lookup"><span data-stu-id="c114e-115">When an error occurs, the error number appears in this box.</span></span> <span data-ttu-id="c114e-116">Этот номер обеспечивает возможность устранения ошибок, используйте его для поиска в базе знаний [!INCLUDE[msCoName](../../includes/msconame-md.md)] или сообщите его службе технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="c114e-116">Use this number to troubleshoot failures by searching for the number in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base or provide the number to your technical support staff.</span></span>  
  
 <span data-ttu-id="c114e-117">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="c114e-117">**Host Name**</span></span>  
 <span data-ttu-id="c114e-118">Отображает имя компьютера или кластера, где запущена служба [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c114e-118">Displays the name of the computer or cluster running the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
 <span data-ttu-id="c114e-119">**Название**</span><span class="sxs-lookup"><span data-stu-id="c114e-119">**Name**</span></span>  
 <span data-ttu-id="c114e-120">Указывает отображаемое имя службы.</span><span class="sxs-lookup"><span data-stu-id="c114e-120">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="c114e-121">**Идентификатор процесса**</span><span class="sxs-lookup"><span data-stu-id="c114e-121">**Process ID**</span></span>  
 <span data-ttu-id="c114e-122">Отображает идентификатор процесса Windows.</span><span class="sxs-lookup"><span data-stu-id="c114e-122">Displays the Windows process ID.</span></span>  
  
 <span data-ttu-id="c114e-123">**Тип службы SQL**</span><span class="sxs-lookup"><span data-stu-id="c114e-123">**SQL Service Type**</span></span>  
 <span data-ttu-id="c114e-124">Отображает тип службы, предоставленной для вызывающих процессов.</span><span class="sxs-lookup"><span data-stu-id="c114e-124">Displays the type of service provided to calling processes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c114e-125">устанавливает несколько служб.</span><span class="sxs-lookup"><span data-stu-id="c114e-125">installs several services.</span></span>  
  
 <span data-ttu-id="c114e-126">**Режим запуска**</span><span class="sxs-lookup"><span data-stu-id="c114e-126">**Start Mode**</span></span>  
 <span data-ttu-id="c114e-127">Установите для этой службы один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="c114e-127">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="c114e-128">Вручную. Эта служба не запускается автоматически при запуске компьютера.</span><span class="sxs-lookup"><span data-stu-id="c114e-128">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="c114e-129">Необходимо запустить службу при помощи диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или другого средства.</span><span class="sxs-lookup"><span data-stu-id="c114e-129">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="c114e-130">Автоматически. Эта служба пытается запуститься при запуске компьютера.</span><span class="sxs-lookup"><span data-stu-id="c114e-130">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="c114e-131">Отключено. Служба не может быть запущена.</span><span class="sxs-lookup"><span data-stu-id="c114e-131">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="c114e-132">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="c114e-132">**State**</span></span>  
 <span data-ttu-id="c114e-133">Указывает, была ли служба запущена, остановлена или отключена.</span><span class="sxs-lookup"><span data-stu-id="c114e-133">Indicates whether this service is running, stopped, or disabled.</span></span> <span data-ttu-id="c114e-134">**…** указывает, что ожидается изменение состояния.</span><span class="sxs-lookup"><span data-stu-id="c114e-134">"**...**" indicates a state change is pending.</span></span>  
  
  
