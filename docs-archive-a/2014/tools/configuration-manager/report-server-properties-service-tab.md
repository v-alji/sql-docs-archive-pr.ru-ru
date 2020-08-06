---
title: Свойства сервера отчетов (вкладка "Службы") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 2a2e1dbf-02b9-4893-aaf0-c0e4a2c9b4f9
author: stevestein
ms.author: sstein
ms.openlocfilehash: a8d223234e5f53eb087650d0634eb09b520cd21e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665685"
---
# <a name="report-server-properties-service-tab"></a><span data-ttu-id="9b66b-102">Свойства сервера отчетов (вкладка «Службы»)</span><span class="sxs-lookup"><span data-stu-id="9b66b-102">Report Server Properties (Service Tab)</span></span>
  <span data-ttu-id="9b66b-103">Это служба сервера отчетов [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b66b-103">This service is the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Report Server service.</span></span> <span data-ttu-id="9b66b-104">Значения свойств, выделенные светло-серым цветом, с помощью этого приложения изменить нельзя.</span><span class="sxs-lookup"><span data-stu-id="9b66b-104">The property values in light gray cannot be changed by using this application.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9b66b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9b66b-105">Options</span></span>  
 <span data-ttu-id="9b66b-106">**Путь к двоичным файлам**</span><span class="sxs-lookup"><span data-stu-id="9b66b-106">**Binary Path**</span></span>  
 <span data-ttu-id="9b66b-107">Отображает расположение программных файлов, используемых этой службой.</span><span class="sxs-lookup"><span data-stu-id="9b66b-107">Displays the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="9b66b-108">**Контроль ошибок**</span><span class="sxs-lookup"><span data-stu-id="9b66b-108">**Error Control**</span></span>  
 <span data-ttu-id="9b66b-109">1 означает SERVICE_ERROR_NORMAL.</span><span class="sxs-lookup"><span data-stu-id="9b66b-109">1 indicates "SERVICE_ERROR_NORMAL".</span></span> <span data-ttu-id="9b66b-110">Если службе не удалось запуститься при запуске компьютера, программа запуска заносит в журнал сообщение об ошибке и выдает всплывающее сообщение об ошибке, но продолжает выполнять операцию запуска.</span><span class="sxs-lookup"><span data-stu-id="9b66b-110">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="9b66b-111">Это значение невозможно изменить.</span><span class="sxs-lookup"><span data-stu-id="9b66b-111">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="9b66b-112">**Код завершения**</span><span class="sxs-lookup"><span data-stu-id="9b66b-112">**Exit Code**</span></span>  
 <span data-ttu-id="9b66b-113">При возникновении ошибки ее номер выводится в этом окне.</span><span class="sxs-lookup"><span data-stu-id="9b66b-113">When an error occurs, the error number appears in this box.</span></span> <span data-ttu-id="9b66b-114">Этот номер обеспечивает возможность устранения ошибок, используйте его для поиска в базе знаний [!INCLUDE[msCoName](../../includes/msconame-md.md)] или сообщите его службе технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="9b66b-114">Use this number to troubleshoot failures by searching for the number in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base or provide the number to your technical support staff.</span></span>  
  
 <span data-ttu-id="9b66b-115">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="9b66b-115">**Host Name**</span></span>  
 <span data-ttu-id="9b66b-116">Отображает имя компьютера или кластера, где запущен полнотекстовый поиск.</span><span class="sxs-lookup"><span data-stu-id="9b66b-116">Displays the name of the computer or cluster running the full text search.</span></span>  
  
 <span data-ttu-id="9b66b-117">**Название**</span><span class="sxs-lookup"><span data-stu-id="9b66b-117">**Name**</span></span>  
 <span data-ttu-id="9b66b-118">Указывает отображаемое имя службы.</span><span class="sxs-lookup"><span data-stu-id="9b66b-118">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="9b66b-119">**Идентификатор процесса**</span><span class="sxs-lookup"><span data-stu-id="9b66b-119">**Process ID**</span></span>  
 <span data-ttu-id="9b66b-120">Отображает идентификатор процесса [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="9b66b-120">Displays the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows process ID.</span></span>  
  
 <span data-ttu-id="9b66b-121">**Тип службы SQL**</span><span class="sxs-lookup"><span data-stu-id="9b66b-121">**SQL Service Type**</span></span>  
 <span data-ttu-id="9b66b-122">Тип службы, предоставленной для вызывающих процессов.</span><span class="sxs-lookup"><span data-stu-id="9b66b-122">Type of service provided to calling processes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9b66b-123">устанавливает несколько служб.</span><span class="sxs-lookup"><span data-stu-id="9b66b-123">installs several services.</span></span>  
  
 <span data-ttu-id="9b66b-124">**Режим запуска**</span><span class="sxs-lookup"><span data-stu-id="9b66b-124">**Start Mode**</span></span>  
 <span data-ttu-id="9b66b-125">Установите для этой службы один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="9b66b-125">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="9b66b-126">Вручную. Эта служба не запускается автоматически при запуске компьютера.</span><span class="sxs-lookup"><span data-stu-id="9b66b-126">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="9b66b-127">Необходимо запустить службу при помощи диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или другого средства.</span><span class="sxs-lookup"><span data-stu-id="9b66b-127">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="9b66b-128">Автоматически. Эта служба пытается запуститься при запуске компьютера.</span><span class="sxs-lookup"><span data-stu-id="9b66b-128">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="9b66b-129">Отключено. Служба не может быть запущена.</span><span class="sxs-lookup"><span data-stu-id="9b66b-129">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="9b66b-130">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="9b66b-130">**State**</span></span>  
 <span data-ttu-id="9b66b-131">Указывает, была ли служба запущена, остановлена или отключена.</span><span class="sxs-lookup"><span data-stu-id="9b66b-131">Indicates whether this service is running, stopped, or disabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b66b-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="9b66b-132">See Also</span></span>  
 [<span data-ttu-id="9b66b-133">Службы SQL Server</span><span class="sxs-lookup"><span data-stu-id="9b66b-133">SQL Server Services</span></span>](../../../2014/tools/configuration-manager/sql-server-services.md)  
  
  
