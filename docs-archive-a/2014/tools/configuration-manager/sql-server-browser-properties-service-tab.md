---
title: Свойства обозревателя SQL Server (вкладка "Служба") | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 98ace9b0-72d5-4b72-9b7b-11fbc490981a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 200e45648b94e26c5e808e9a817cfe01866e6a65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655509"
---
# <a name="sql-server-browser-properties-service-tab"></a><span data-ttu-id="3693e-102">Свойства браузер SQL Server (вкладка «Службы»)</span><span class="sxs-lookup"><span data-stu-id="3693e-102">SQL Server Browser Properties (Service Tab)</span></span>
  <span data-ttu-id="3693e-103">Программа браузера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] работает в качестве службы на сервере.</span><span class="sxs-lookup"><span data-stu-id="3693e-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser program runs as a service on the server.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="3693e-104">прослушивает входящие запросы к ресурсам [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и предоставляет сведения об экземплярах [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], установленных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3693e-104">Browser listens for incoming requests for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resources and provides information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances installed on the computer.</span></span>  
  
 <span data-ttu-id="3693e-105">Используйте вкладку **Службы** в диалоговом окне **Свойства браузера SQL Server** , чтобы просмотреть следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="3693e-105">Use the **Service** tab on the **SQL Server Browser Properties** dialog box to view the following options.</span></span> <span data-ttu-id="3693e-106">Все свойства, кроме свойства **Режим запуска** , доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="3693e-106">All properties except **Start Mode** are read-only.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3693e-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="3693e-107">Options</span></span>  
 <span data-ttu-id="3693e-108">**Путь к двоичным файлам**</span><span class="sxs-lookup"><span data-stu-id="3693e-108">**Binary Path**</span></span>  
 <span data-ttu-id="3693e-109">Отображает расположение программных файлов, используемых этой службой.</span><span class="sxs-lookup"><span data-stu-id="3693e-109">Displays the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="3693e-110">**Контроль ошибок**</span><span class="sxs-lookup"><span data-stu-id="3693e-110">**Error Control**</span></span>  
 <span data-ttu-id="3693e-111">1 означает `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="3693e-111">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="3693e-112">Если службе не удалось запуститься при запуске компьютера, программа запуска заносит в журнал сообщение об ошибке и выдает всплывающее сообщение об ошибке, но продолжает выполнять операцию запуска.</span><span class="sxs-lookup"><span data-stu-id="3693e-112">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="3693e-113">Это значение невозможно изменить.</span><span class="sxs-lookup"><span data-stu-id="3693e-113">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="3693e-114">**Код завершения**</span><span class="sxs-lookup"><span data-stu-id="3693e-114">**Exit Code**</span></span>  
 <span data-ttu-id="3693e-115">При возникновении ошибки ее номер выводится в этом окне.</span><span class="sxs-lookup"><span data-stu-id="3693e-115">When an error occurs, the error number appears in this box.</span></span> <span data-ttu-id="3693e-116">Этот номер обеспечивает возможность устранения ошибок, используйте его для поиска в базе знаний [!INCLUDE[msCoName](../../includes/msconame-md.md)] или сообщите его службе технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="3693e-116">Use this number to troubleshoot failures by searching for the number in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base or provide the number to your technical support staff.</span></span>  
  
 <span data-ttu-id="3693e-117">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="3693e-117">**Host Name**</span></span>  
 <span data-ttu-id="3693e-118">Отображает имя компьютера или кластера, где запущена служба браузера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3693e-118">Displays the name of the computer or cluster running the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
 <span data-ttu-id="3693e-119">**Название**</span><span class="sxs-lookup"><span data-stu-id="3693e-119">**Name**</span></span>  
 <span data-ttu-id="3693e-120">Указывает отображаемое имя службы.</span><span class="sxs-lookup"><span data-stu-id="3693e-120">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="3693e-121">**Идентификатор процесса**</span><span class="sxs-lookup"><span data-stu-id="3693e-121">**Process ID**</span></span>  
 <span data-ttu-id="3693e-122">Отображает идентификатор процесса Windows.</span><span class="sxs-lookup"><span data-stu-id="3693e-122">Displays the Windows process ID.</span></span>  
  
 <span data-ttu-id="3693e-123">**Тип службы**</span><span class="sxs-lookup"><span data-stu-id="3693e-123">**Service Type**</span></span>  
 <span data-ttu-id="3693e-124">Отображает тип службы, предоставленной для вызывающих процессов.</span><span class="sxs-lookup"><span data-stu-id="3693e-124">Displays the type of service provided to calling processes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="3693e-125">устанавливает несколько служб.</span><span class="sxs-lookup"><span data-stu-id="3693e-125">installs several services.</span></span>  
  
 <span data-ttu-id="3693e-126">**Режим запуска**</span><span class="sxs-lookup"><span data-stu-id="3693e-126">**Start Mode**</span></span>  
 <span data-ttu-id="3693e-127">Установите для этой службы один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="3693e-127">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="3693e-128">Вручную. Эта служба не запускается автоматически при запуске компьютера.</span><span class="sxs-lookup"><span data-stu-id="3693e-128">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="3693e-129">Необходимо запустить службу при помощи диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или другого средства.</span><span class="sxs-lookup"><span data-stu-id="3693e-129">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="3693e-130">Автоматически. Эта служба пытается запуститься при запуске компьютера.</span><span class="sxs-lookup"><span data-stu-id="3693e-130">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="3693e-131">Отключено. Служба не может быть запущена.</span><span class="sxs-lookup"><span data-stu-id="3693e-131">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="3693e-132">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="3693e-132">**State**</span></span>  
 <span data-ttu-id="3693e-133">Указывает, была ли служба запущена, остановлена или отключена.</span><span class="sxs-lookup"><span data-stu-id="3693e-133">Indicates whether this service is running, stopped, or disabled.</span></span> <span data-ttu-id="3693e-134">**…** указывает, что ожидается изменение состояния.</span><span class="sxs-lookup"><span data-stu-id="3693e-134">"**...**" indicates a state change is pending.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3693e-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="3693e-135">See Also</span></span>  
 [<span data-ttu-id="3693e-136">Служба обозревателя SQL Server</span><span class="sxs-lookup"><span data-stu-id="3693e-136">SQL Server Browser Service</span></span>](../../../2014/tools/configuration-manager/sql-server-browser-service.md)  
  
  
