---
title: Свойства сервера анализа данных (вкладка "Служба") | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 8dbe4bc5-6aa9-48ee-857e-0b4ea764b9cb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 91200120d87224c8e7733b0ff41ed423d3086c34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750408"
---
# <a name="analysis-server-properties-service-tab"></a><span data-ttu-id="a067c-102">Свойства сервера анализа данных (вкладка «Службы»)</span><span class="sxs-lookup"><span data-stu-id="a067c-102">Analysis Server Properties (Service Tab)</span></span>
  <span data-ttu-id="a067c-103">Эта служба представляет собой среду [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a067c-103">This service is the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="a067c-104">Она должна быть запущена для правильной работы служб [!INCLUDE[ssAS](../../includes/ssas-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a067c-104">This service must be running for [!INCLUDE[ssAS](../../includes/ssas-md.md)] to work properly.</span></span> <span data-ttu-id="a067c-105">Значения свойств, окрашенные в светло-серый цвет, нельзя изменить при помощи этого приложения.</span><span class="sxs-lookup"><span data-stu-id="a067c-105">The property values in light gray cannot be changed using this application.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a067c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a067c-106">Options</span></span>  
 <span data-ttu-id="a067c-107">**Путь к двоичным файлам**</span><span class="sxs-lookup"><span data-stu-id="a067c-107">**Binary Path**</span></span>  
 <span data-ttu-id="a067c-108">Отображает расположение программных файлов, используемых этой службой.</span><span class="sxs-lookup"><span data-stu-id="a067c-108">Displays the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="a067c-109">**Контроль ошибок**</span><span class="sxs-lookup"><span data-stu-id="a067c-109">**Error Control**</span></span>  
 <span data-ttu-id="a067c-110">1 означает `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="a067c-110">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="a067c-111">Если службе не удалось запуститься при запуске компьютера, программа запуска заносит в журнал сообщение об ошибке и выдает всплывающее сообщение об ошибке, но продолжает выполнять операцию запуска.</span><span class="sxs-lookup"><span data-stu-id="a067c-111">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="a067c-112">Это значение невозможно изменить.</span><span class="sxs-lookup"><span data-stu-id="a067c-112">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="a067c-113">**Код завершения**</span><span class="sxs-lookup"><span data-stu-id="a067c-113">**Exit Code**</span></span>  
 <span data-ttu-id="a067c-114">При возникновении ошибки ее номер выводится в этом окне.</span><span class="sxs-lookup"><span data-stu-id="a067c-114">When an error occurs, the error number appears in this box.</span></span> <span data-ttu-id="a067c-115">Этот номер обеспечивает возможность устранения ошибок, используйте его для поиска в базе знаний [!INCLUDE[msCoName](../../includes/msconame-md.md)] или сообщите его службе технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="a067c-115">Use this number to troubleshoot failures by searching for the number in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base or provide the number to your technical support staff.</span></span>  
  
 <span data-ttu-id="a067c-116">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="a067c-116">**Host Name**</span></span>  
 <span data-ttu-id="a067c-117">Отображает имя компьютера или кластера, где запущены службы [!INCLUDE[ssAS](../../includes/ssas-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a067c-117">Displays the name of the computer or cluster running [!INCLUDE[ssAS](../../includes/ssas-md.md)].</span></span>  
  
 <span data-ttu-id="a067c-118">**Название**</span><span class="sxs-lookup"><span data-stu-id="a067c-118">**Name**</span></span>  
 <span data-ttu-id="a067c-119">Указывает отображаемое имя службы.</span><span class="sxs-lookup"><span data-stu-id="a067c-119">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="a067c-120">**Идентификатор процесса**</span><span class="sxs-lookup"><span data-stu-id="a067c-120">**Process ID**</span></span>  
 <span data-ttu-id="a067c-121">Отображает номер, используемый [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows для отслеживания процессов этой программы.</span><span class="sxs-lookup"><span data-stu-id="a067c-121">Displays the number used by [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows to keep track of this program's processes.</span></span>  
  
 <span data-ttu-id="a067c-122">**Тип службы SQL**</span><span class="sxs-lookup"><span data-stu-id="a067c-122">**SQL Service Type**</span></span>  
 <span data-ttu-id="a067c-123">Отображает тип службы, предоставленной для вызывающих процессов.</span><span class="sxs-lookup"><span data-stu-id="a067c-123">Displays the type of service provided to calling processes.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="a067c-124">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] устанавливает несколько служб.</span><span class="sxs-lookup"><span data-stu-id="a067c-124">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installs several services.</span></span>  
  
 <span data-ttu-id="a067c-125">**Режим запуска**</span><span class="sxs-lookup"><span data-stu-id="a067c-125">**Start Mode**</span></span>  
 <span data-ttu-id="a067c-126">Установите для этой службы один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="a067c-126">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="a067c-127">Вручную. Эта служба не запускается автоматически при запуске компьютера.</span><span class="sxs-lookup"><span data-stu-id="a067c-127">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="a067c-128">Необходимо запустить службу при помощи диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или другого средства.</span><span class="sxs-lookup"><span data-stu-id="a067c-128">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="a067c-129">Автоматически. Эта служба пытается запуститься при запуске компьютера.</span><span class="sxs-lookup"><span data-stu-id="a067c-129">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="a067c-130">Отключено. Служба не может быть запущена.</span><span class="sxs-lookup"><span data-stu-id="a067c-130">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="a067c-131">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="a067c-131">**State**</span></span>  
 <span data-ttu-id="a067c-132">Указывает, была ли служба запущена, остановлена или отключена.</span><span class="sxs-lookup"><span data-stu-id="a067c-132">Indicates whether this service is running, stopped, or disabled.</span></span>  
  
  
