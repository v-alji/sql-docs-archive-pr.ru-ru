---
title: Свойства NS $ &lt; Service Name &gt; (вкладка "службы") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 57c6b791-1663-4a01-9de2-cf1bdd8adb2c
author: stevestein
ms.author: sstein
ms.openlocfilehash: ddd80cf1c84e3fe7acc538e6aa65230b45870219
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737295"
---
# <a name="nsltservice-namegt-properties-service-tab"></a><span data-ttu-id="bf938-102">Свойства NS$&lt;имя службы&gt; (вкладка "Службы")</span><span class="sxs-lookup"><span data-stu-id="bf938-102">NS$&lt;service name&gt; Properties (Service Tab)</span></span>
  <span data-ttu-id="bf938-103">Эта служба представляет собой службу [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNS](../../includes/ssns-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf938-103">This service is the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNS](../../includes/ssns-md.md)] service.</span></span> <span data-ttu-id="bf938-104">Значения свойств, окрашенные в светло-серый цвет, нельзя изменить при помощи этого приложения.</span><span class="sxs-lookup"><span data-stu-id="bf938-104">The property values in light gray cannot be changed using this application.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bf938-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bf938-105">Options</span></span>  
 <span data-ttu-id="bf938-106">**Путь к двоичным файлам**</span><span class="sxs-lookup"><span data-stu-id="bf938-106">**Binary Path**</span></span>  
 <span data-ttu-id="bf938-107">Отображает расположение программных файлов, используемых этой службой.</span><span class="sxs-lookup"><span data-stu-id="bf938-107">Displays the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="bf938-108">**Контроль ошибок**</span><span class="sxs-lookup"><span data-stu-id="bf938-108">**Error Control**</span></span>  
 <span data-ttu-id="bf938-109">1 означает `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="bf938-109">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="bf938-110">Если службе не удалось запуститься при запуске компьютера, программа запуска заносит в журнал сообщение об ошибке и выдает всплывающее сообщение об ошибке, но продолжает выполнять операцию запуска.</span><span class="sxs-lookup"><span data-stu-id="bf938-110">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="bf938-111">Это значение невозможно изменить.</span><span class="sxs-lookup"><span data-stu-id="bf938-111">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="bf938-112">**Код завершения**</span><span class="sxs-lookup"><span data-stu-id="bf938-112">**Exit Code**</span></span>  
 <span data-ttu-id="bf938-113">При возникновении ошибки ее номер выводится в этом окне.</span><span class="sxs-lookup"><span data-stu-id="bf938-113">When an error occurs, the error number appears in this box.</span></span> <span data-ttu-id="bf938-114">Этот номер обеспечивает возможность устранения ошибок, используйте его для поиска в базе знаний [!INCLUDE[msCoName](../../includes/msconame-md.md)] или сообщите его службе технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="bf938-114">Use this number to troubleshoot failures by searching for the number in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base or provide the number to your technical support staff.</span></span>  
  
 <span data-ttu-id="bf938-115">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="bf938-115">**Host Name**</span></span>  
 <span data-ttu-id="bf938-116">Отображает имя компьютера или кластера, где запущен полнотекстовый поиск.</span><span class="sxs-lookup"><span data-stu-id="bf938-116">Displays the name of the computer or cluster running the full text search.</span></span>  
  
 <span data-ttu-id="bf938-117">**Название**</span><span class="sxs-lookup"><span data-stu-id="bf938-117">**Name**</span></span>  
 <span data-ttu-id="bf938-118">Указывает отображаемое имя службы.</span><span class="sxs-lookup"><span data-stu-id="bf938-118">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="bf938-119">**Идентификатор процесса**</span><span class="sxs-lookup"><span data-stu-id="bf938-119">**Process ID**</span></span>  
 <span data-ttu-id="bf938-120">Отображает идентификатор процесса [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="bf938-120">Displays the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows process ID.</span></span>  
  
 <span data-ttu-id="bf938-121">**Тип службы SQL**</span><span class="sxs-lookup"><span data-stu-id="bf938-121">**SQL Service Type**</span></span>  
 <span data-ttu-id="bf938-122">Тип службы, предоставленной для вызывающих процессов.</span><span class="sxs-lookup"><span data-stu-id="bf938-122">Type of service provided to calling processes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="bf938-123">устанавливает несколько служб.</span><span class="sxs-lookup"><span data-stu-id="bf938-123">installs several services.</span></span>  
  
 <span data-ttu-id="bf938-124">**Режим запуска**</span><span class="sxs-lookup"><span data-stu-id="bf938-124">**Start Mode**</span></span>  
 <span data-ttu-id="bf938-125">Установите для этой службы один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="bf938-125">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="bf938-126">Вручную. Эта служба не запускается автоматически при запуске компьютера.</span><span class="sxs-lookup"><span data-stu-id="bf938-126">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="bf938-127">Необходимо запустить службу при помощи диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или другого средства.</span><span class="sxs-lookup"><span data-stu-id="bf938-127">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="bf938-128">Автоматически. Эта служба пытается запуститься при запуске компьютера.</span><span class="sxs-lookup"><span data-stu-id="bf938-128">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="bf938-129">Отключено. Служба не может быть запущена.</span><span class="sxs-lookup"><span data-stu-id="bf938-129">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="bf938-130">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="bf938-130">**State**</span></span>  
 <span data-ttu-id="bf938-131">Указывает, была ли служба запущена, остановлена или отключена.</span><span class="sxs-lookup"><span data-stu-id="bf938-131">Indicates whether this service is running, stopped, or disabled.</span></span>  
  
  
