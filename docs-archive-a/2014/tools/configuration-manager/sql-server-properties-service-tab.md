---
title: Свойства SQL Server (вкладка "службы") | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: e4ae0c6b-6fd8-4325-b54e-1758fc659958
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5822a02d5631e0d0e9318b20a1dcee87b8a4ded1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740631"
---
# <a name="sql-server-properties-service-tab"></a><span data-ttu-id="1fd6c-102">Свойства SQL Server (вкладка «Службы»)</span><span class="sxs-lookup"><span data-stu-id="1fd6c-102">SQL Server Properties (Service Tab)</span></span>
  <span data-ttu-id="1fd6c-103">Используйте вкладку **Службы**в диалоговом окне **Свойства MSSQLSERVER** , чтобы просмотреть или указать следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="1fd6c-103">Use the **Service**tab on the **MSSQLSERVER Properties** dialog box to view or specify the following options.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1fd6c-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="1fd6c-104">Options</span></span>  
 <span data-ttu-id="1fd6c-105">**Путь к двоичным файлам**</span><span class="sxs-lookup"><span data-stu-id="1fd6c-105">**Binary Path**</span></span>  
 <span data-ttu-id="1fd6c-106">Отображает расположение программных файлов, используемых этой службой.</span><span class="sxs-lookup"><span data-stu-id="1fd6c-106">Lists the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="1fd6c-107">**Контроль ошибок**</span><span class="sxs-lookup"><span data-stu-id="1fd6c-107">**Error Control**</span></span>  
 <span data-ttu-id="1fd6c-108">1 означает `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="1fd6c-108">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="1fd6c-109">Если службе не удалось запуститься при запуске компьютера, программа запуска заносит в журнал сообщение об ошибке и выдает всплывающее сообщение об ошибке, но продолжает выполнять операцию запуска.</span><span class="sxs-lookup"><span data-stu-id="1fd6c-109">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="1fd6c-110">Это значение невозможно изменить.</span><span class="sxs-lookup"><span data-stu-id="1fd6c-110">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="1fd6c-111">**Код завершения**</span><span class="sxs-lookup"><span data-stu-id="1fd6c-111">**Exit Code**</span></span>  
 <span data-ttu-id="1fd6c-112">При возникновении ошибки ее номер выводится в этом окне.</span><span class="sxs-lookup"><span data-stu-id="1fd6c-112">When an error occurs, the error number appears in this box.</span></span> <span data-ttu-id="1fd6c-113">Этот номер обеспечивает возможность устранения ошибок, используйте его для поиска в базе знаний [!INCLUDE[msCoName](../../includes/msconame-md.md)] или сообщите его службе технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="1fd6c-113">Use this number to troubleshoot failures by searching for the number in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base or provide the number to your technical support staff.</span></span>  
  
 <span data-ttu-id="1fd6c-114">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="1fd6c-114">**Host Name**</span></span>  
 <span data-ttu-id="1fd6c-115">Отображает имя компьютера или кластера, где запущена служба [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1fd6c-115">Displays the name of the computer or cluster running the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
 <span data-ttu-id="1fd6c-116">**Название**</span><span class="sxs-lookup"><span data-stu-id="1fd6c-116">**Name**</span></span>  
 <span data-ttu-id="1fd6c-117">Указывает отображаемое имя службы.</span><span class="sxs-lookup"><span data-stu-id="1fd6c-117">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="1fd6c-118">**Идентификатор процесса**</span><span class="sxs-lookup"><span data-stu-id="1fd6c-118">**Process ID**</span></span>  
 <span data-ttu-id="1fd6c-119">Отображает идентификатор процесса Windows.</span><span class="sxs-lookup"><span data-stu-id="1fd6c-119">Displays the Windows process ID.</span></span>  
  
 <span data-ttu-id="1fd6c-120">**Тип службы**</span><span class="sxs-lookup"><span data-stu-id="1fd6c-120">**Service Type**</span></span>  
 <span data-ttu-id="1fd6c-121">Отображает тип службы, предоставленной для вызывающих процессов.</span><span class="sxs-lookup"><span data-stu-id="1fd6c-121">Displays the type of service provided to calling processes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1fd6c-122">устанавливает несколько служб.</span><span class="sxs-lookup"><span data-stu-id="1fd6c-122">installs several services.</span></span>  
  
 <span data-ttu-id="1fd6c-123">**Режим запуска**</span><span class="sxs-lookup"><span data-stu-id="1fd6c-123">**Start Mode**</span></span>  
 <span data-ttu-id="1fd6c-124">Установите для этой службы один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="1fd6c-124">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="1fd6c-125">Вручную. Эта служба не запускается автоматически при запуске компьютера.</span><span class="sxs-lookup"><span data-stu-id="1fd6c-125">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="1fd6c-126">Необходимо запустить службу при помощи диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или другого средства.</span><span class="sxs-lookup"><span data-stu-id="1fd6c-126">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="1fd6c-127">Автоматически. Эта служба пытается запуститься при запуске компьютера.</span><span class="sxs-lookup"><span data-stu-id="1fd6c-127">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="1fd6c-128">Отключено. Служба не может быть запущена.</span><span class="sxs-lookup"><span data-stu-id="1fd6c-128">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="1fd6c-129">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="1fd6c-129">**State**</span></span>  
 <span data-ttu-id="1fd6c-130">Указывает, была ли служба запущена, остановлена или отключена.</span><span class="sxs-lookup"><span data-stu-id="1fd6c-130">Indicates whether this service is running, stopped, or disabled.</span></span> <span data-ttu-id="1fd6c-131">**…** указывает, что ожидается изменение состояния.</span><span class="sxs-lookup"><span data-stu-id="1fd6c-131">"**...**" indicates a state change is pending.</span></span>  
  
  
