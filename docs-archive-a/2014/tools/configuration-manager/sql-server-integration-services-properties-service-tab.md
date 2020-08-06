---
title: Свойства служб SQL Server Integration Services (вкладка "Служба") | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 37f0acd9-c96f-48fd-9b53-2ca0097af242
author: stevestein
ms.author: sstein
ms.openlocfilehash: a752bdeab3c99ac97445e3281d3165a2d8f79866
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667975"
---
# <a name="sql-server-integration-services-properties-service-tab"></a><span data-ttu-id="d6f1f-102">Свойства служб SQL Server Integration Services (вкладка «Служба»)</span><span class="sxs-lookup"><span data-stu-id="d6f1f-102">SQL Server Integration Services Properties (Service Tab)</span></span>
  <span data-ttu-id="d6f1f-103">Используйте вкладку **Службы** в диалоговом окне [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]Свойства**в**, чтобы просмотреть или указать следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="d6f1f-103">Use the **Service**tab on the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] **Properties** dialog box to view or specify the following options.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d6f1f-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="d6f1f-104">Options</span></span>  
 <span data-ttu-id="d6f1f-105">**Путь к двоичным файлам**</span><span class="sxs-lookup"><span data-stu-id="d6f1f-105">**Binary Path**</span></span>  
 <span data-ttu-id="d6f1f-106">Отображает расположение программных файлов, используемых этой службой.</span><span class="sxs-lookup"><span data-stu-id="d6f1f-106">Displays the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="d6f1f-107">**Контроль ошибок**</span><span class="sxs-lookup"><span data-stu-id="d6f1f-107">**Error Control**</span></span>  
 <span data-ttu-id="d6f1f-108">1 означает `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="d6f1f-108">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="d6f1f-109">Если службе не удалось запуститься при запуске компьютера, программа запуска заносит в журнал сообщение об ошибке и выдает всплывающее сообщение об ошибке, но продолжает выполнять операцию запуска.</span><span class="sxs-lookup"><span data-stu-id="d6f1f-109">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="d6f1f-110">Это значение невозможно изменить.</span><span class="sxs-lookup"><span data-stu-id="d6f1f-110">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="d6f1f-111">**Код завершения**</span><span class="sxs-lookup"><span data-stu-id="d6f1f-111">**Exit Code**</span></span>  
 <span data-ttu-id="d6f1f-112">Код ошибки [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows определяет любые проблемы, возникшие при запуске или остановке службы.</span><span class="sxs-lookup"><span data-stu-id="d6f1f-112">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows error code defining any problems encountered in starting or stopping the service.</span></span> <span data-ttu-id="d6f1f-113">Этому свойству присваивается значение **ERROR_SERVICE_SPECIFIC_ERROR** (1066), если ошибка является уникальной для службы, представленной этим классом, а сведения об ошибке доступны в свойстве **ServiceSpecificExitCode** .</span><span class="sxs-lookup"><span data-stu-id="d6f1f-113">This property is set to **ERROR_SERVICE_SPECIFIC_ERROR** (1066) when the error is unique to the service represented by this class, and information about the error is available in the **ServiceSpecificExitCode** property.</span></span> <span data-ttu-id="d6f1f-114">Во время выполнения и после нормального завершения работы служба присваивает этому параметру значение NO_ERROR (0).</span><span class="sxs-lookup"><span data-stu-id="d6f1f-114">The service sets this value to NO_ERROR (0) when running, and again upon normal termination.</span></span>  
  
 <span data-ttu-id="d6f1f-115">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="d6f1f-115">**Host Name**</span></span>  
 <span data-ttu-id="d6f1f-116">Отображает имя компьютера или кластера, где запущена служба [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d6f1f-116">Displays the name of the computer or cluster running the [!INCLUDE[ssIS](../../includes/ssis-md.md)] service.</span></span>  
  
 <span data-ttu-id="d6f1f-117">**Название**</span><span class="sxs-lookup"><span data-stu-id="d6f1f-117">**Name**</span></span>  
 <span data-ttu-id="d6f1f-118">Указывает отображаемое имя службы.</span><span class="sxs-lookup"><span data-stu-id="d6f1f-118">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="d6f1f-119">**Идентификатор процесса**</span><span class="sxs-lookup"><span data-stu-id="d6f1f-119">**Process ID**</span></span>  
 <span data-ttu-id="d6f1f-120">Отображает идентификатор процесса Windows.</span><span class="sxs-lookup"><span data-stu-id="d6f1f-120">Displays the Windows process ID.</span></span>  
  
 <span data-ttu-id="d6f1f-121">**Тип службы SQL**</span><span class="sxs-lookup"><span data-stu-id="d6f1f-121">**SQL Service Type**</span></span>  
 <span data-ttu-id="d6f1f-122">Отображает тип службы, предоставленной для вызывающих процессов.</span><span class="sxs-lookup"><span data-stu-id="d6f1f-122">Displays the type of service provided to calling processes.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="d6f1f-123">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] устанавливает несколько служб.</span><span class="sxs-lookup"><span data-stu-id="d6f1f-123">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installs several services.</span></span>  
  
 <span data-ttu-id="d6f1f-124">**Режим запуска**</span><span class="sxs-lookup"><span data-stu-id="d6f1f-124">**Start Mode**</span></span>  
 <span data-ttu-id="d6f1f-125">Установите для этой службы один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="d6f1f-125">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="d6f1f-126">Вручную. Эта служба не запускается автоматически при запуске компьютера.</span><span class="sxs-lookup"><span data-stu-id="d6f1f-126">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="d6f1f-127">Необходимо запустить службу при помощи диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или другого средства.</span><span class="sxs-lookup"><span data-stu-id="d6f1f-127">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="d6f1f-128">Автоматически. Эта служба пытается запуститься при запуске компьютера.</span><span class="sxs-lookup"><span data-stu-id="d6f1f-128">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="d6f1f-129">Отключено. Служба не может быть запущена.</span><span class="sxs-lookup"><span data-stu-id="d6f1f-129">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="d6f1f-130">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="d6f1f-130">**State**</span></span>  
 <span data-ttu-id="d6f1f-131">Указывает, была ли служба запущена, остановлена или отключена.</span><span class="sxs-lookup"><span data-stu-id="d6f1f-131">Indicates whether this service is running, stopped, or disabled.</span></span> <span data-ttu-id="d6f1f-132">**…** указывает, что ожидается изменение состояния.</span><span class="sxs-lookup"><span data-stu-id="d6f1f-132">"**...**" indicates a state change is pending.</span></span>  
  
  
