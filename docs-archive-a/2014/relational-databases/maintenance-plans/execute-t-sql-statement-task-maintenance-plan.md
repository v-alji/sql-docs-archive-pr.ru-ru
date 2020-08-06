---
title: Задача "Выполнение инструкции T-SQL" (план обслуживания) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.tsql.f1
helpviewer_keywords:
- Execute T-SQL Statement Task dialog box
ms.assetid: fef3e259-0c47-4f6e-ade0-aee95e3d6c1a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 63738758ce228a51ab6c75eb11a681eec3b27352
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666574"
---
# <a name="execute-t-sql-statement-task-maintenance-plan"></a><span data-ttu-id="8089a-102">Задача «Выполнение инструкции T-SQL» (план обслуживания)</span><span class="sxs-lookup"><span data-stu-id="8089a-102">Execute T-SQL Statement Task (Maintenance Plan)</span></span>
  <span data-ttu-id="8089a-103">Для настройки своего плана обслуживания путем добавления выбранных инструкций **к этому плану используйте диалоговое окно** Задача "Выполнение инструкции T-SQL" [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8089a-103">Use the **Execute T-SQL Statement Task** dialog to customize your maintenance plan by adding [!INCLUDE[tsql](../../includes/tsql-md.md)] statements of your choice to this maintenance plan.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8089a-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="8089a-104">Options</span></span>  
 <span data-ttu-id="8089a-105">**Соединение**</span><span class="sxs-lookup"><span data-stu-id="8089a-105">**Connection**</span></span>  
 <span data-ttu-id="8089a-106">Выберите соединение с сервером, которое будет использоваться для выполнения этой задачи.</span><span class="sxs-lookup"><span data-stu-id="8089a-106">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="8089a-107">**Создать**</span><span class="sxs-lookup"><span data-stu-id="8089a-107">**New**</span></span>  
 <span data-ttu-id="8089a-108">Создать новое соединение с сервером для его использования при выполнении этой задачи.</span><span class="sxs-lookup"><span data-stu-id="8089a-108">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="8089a-109">Диалоговое окно **Создание соединения** описано ниже.</span><span class="sxs-lookup"><span data-stu-id="8089a-109">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="8089a-110">**Время ожидания выполнения**</span><span class="sxs-lookup"><span data-stu-id="8089a-110">**Execution time out**</span></span>  
 <span data-ttu-id="8089a-111">Время (в секундах) ожидания завершения выполнения задачи (завершения задачи).</span><span class="sxs-lookup"><span data-stu-id="8089a-111">Time (seconds) to wait for task completion before timing out (terminating task).</span></span>  
  
 <span data-ttu-id="8089a-112">**Инструкция Т-SQL**</span><span class="sxs-lookup"><span data-stu-id="8089a-112">**T-SQL statement**</span></span>  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="8089a-113">подлежащие выполнению инструкции.</span><span class="sxs-lookup"><span data-stu-id="8089a-113">statements to execute.</span></span>  
  
 <span data-ttu-id="8089a-114">**Просмотр T-SQL**</span><span class="sxs-lookup"><span data-stu-id="8089a-114">**View T-SQL**</span></span>  
 <span data-ttu-id="8089a-115">Просмотрите инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] , выполняемые для данной задачи по отношению к серверу, на основе выбранных параметров.</span><span class="sxs-lookup"><span data-stu-id="8089a-115">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8089a-116">Если количество затронутых объектов велико, построение этого отображения может занять значительное время.</span><span class="sxs-lookup"><span data-stu-id="8089a-116">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="8089a-117">Диалоговое окно «Создание соединения»</span><span class="sxs-lookup"><span data-stu-id="8089a-117">New Connection Dialog Box</span></span>  
 <span data-ttu-id="8089a-118">**Имя соединения**</span><span class="sxs-lookup"><span data-stu-id="8089a-118">**Connection name**</span></span>  
 <span data-ttu-id="8089a-119">Введите имя нового соединения.</span><span class="sxs-lookup"><span data-stu-id="8089a-119">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="8089a-120">**Выберите или введите имя сервера**</span><span class="sxs-lookup"><span data-stu-id="8089a-120">**Select or enter a server name**</span></span>  
 <span data-ttu-id="8089a-121">Выберите сервер для подключения при выполнении этой задачи.</span><span class="sxs-lookup"><span data-stu-id="8089a-121">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="8089a-122">**Обновить**</span><span class="sxs-lookup"><span data-stu-id="8089a-122">**Refresh**</span></span>  
 <span data-ttu-id="8089a-123">Обновите список доступных серверов.</span><span class="sxs-lookup"><span data-stu-id="8089a-123">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="8089a-124">**Введите данные для входа на сервер**</span><span class="sxs-lookup"><span data-stu-id="8089a-124">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="8089a-125">Укажите способ проверки подлинности на сервере.</span><span class="sxs-lookup"><span data-stu-id="8089a-125">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="8089a-126">**Использовать встроенную безопасность Windows**</span><span class="sxs-lookup"><span data-stu-id="8089a-126">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="8089a-127">Подключиться к экземпляру компонента [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] c проверкой подлинности [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="8089a-127">Connect to an instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="8089a-128">**Использовать указанные имя пользователя и пароль**</span><span class="sxs-lookup"><span data-stu-id="8089a-128">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="8089a-129">Подключиться к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] с использованием проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8089a-129">Connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="8089a-130">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="8089a-130">This option is not available.</span></span>  
  
 <span data-ttu-id="8089a-131">**User name**</span><span class="sxs-lookup"><span data-stu-id="8089a-131">**User name**</span></span>  
 <span data-ttu-id="8089a-132">Укажите имя входа, используемое при проверке подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8089a-132">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="8089a-133">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="8089a-133">This option is not available.</span></span>  
  
 <span data-ttu-id="8089a-134">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="8089a-134">**Password**</span></span>  
 <span data-ttu-id="8089a-135">Укажите используемый при проверке подлинности пароль.</span><span class="sxs-lookup"><span data-stu-id="8089a-135">Provide a password to use when authenticating.</span></span> <span data-ttu-id="8089a-136">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="8089a-136">This option is not available.</span></span>  
  
  
