---
title: Задача уведомления оператора (план обслуживания) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.notifyoperator.f1
helpviewer_keywords:
- Notify Operator Task dialog box
ms.assetid: 39c0797c-ad2b-4591-85c9-a23a7f902895
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4feb59622c2a42de67193c75d545a6b8a2a08863
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665334"
---
# <a name="notify-operator-task-maintenance-plan"></a><span data-ttu-id="ba400-102">Задача уведомления оператора (план обслуживания)</span><span class="sxs-lookup"><span data-stu-id="ba400-102">Notify Operator Task (Maintenance Plan)</span></span>
  <span data-ttu-id="ba400-103">Диалоговое окно **Задача уведомления оператора** используется для добавления автоматического уведомления к данному плану обслуживания.</span><span class="sxs-lookup"><span data-stu-id="ba400-103">Use the **Notify Operators Task** dialog to add an automatic notification to this maintenance plan.</span></span> <span data-ttu-id="ba400-104">Для использования этой задачи необходимо включить и надлежащим образом настроить компонент Database Mail в MSDB в качестве базы данных обслуживания почты, а также иметь оператора агента [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с действующим адресом электронной почты.</span><span class="sxs-lookup"><span data-stu-id="ba400-104">To use this task you must have Database Mail enabled and properly configured with MSDB as a Mail Host Database, and have a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent operator with a valid e-mail address.</span></span>  
  
 <span data-ttu-id="ba400-105">Данная задача использует хранимую процедуру sp_notify_operator.</span><span class="sxs-lookup"><span data-stu-id="ba400-105">This task uses the sp_notify_operator stored procedure.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ba400-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ba400-106">Options</span></span>  
 <span data-ttu-id="ba400-107">**Соединение**</span><span class="sxs-lookup"><span data-stu-id="ba400-107">**Connection**</span></span>  
 <span data-ttu-id="ba400-108">Выберите соединение с сервером, которое будет использоваться для выполнения этой задачи.</span><span class="sxs-lookup"><span data-stu-id="ba400-108">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="ba400-109">**Создать**</span><span class="sxs-lookup"><span data-stu-id="ba400-109">**New**</span></span>  
 <span data-ttu-id="ba400-110">Создать новое соединение с сервером для его использования при выполнении этой задачи.</span><span class="sxs-lookup"><span data-stu-id="ba400-110">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="ba400-111">Диалоговое окно **Создание соединения** описано ниже.</span><span class="sxs-lookup"><span data-stu-id="ba400-111">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="ba400-112">**Уведомить операторов**</span><span class="sxs-lookup"><span data-stu-id="ba400-112">**Operators to notify**</span></span>  
 <span data-ttu-id="ba400-113">Указать получателя электронного письма.</span><span class="sxs-lookup"><span data-stu-id="ba400-113">Specify the recipient of the e-mail.</span></span>  
  
 <span data-ttu-id="ba400-114">**Тема сообщения уведомления**</span><span class="sxs-lookup"><span data-stu-id="ba400-114">**Notification message subject**</span></span>  
 <span data-ttu-id="ba400-115">Укажите текст для строки темы в сообщении уведомления.</span><span class="sxs-lookup"><span data-stu-id="ba400-115">Specify the text to include in the notification message subject line.</span></span>  
  
 <span data-ttu-id="ba400-116">**Текст сообщения уведомления**</span><span class="sxs-lookup"><span data-stu-id="ba400-116">**Notification message body**</span></span>  
 <span data-ttu-id="ba400-117">Укажите текст сообщения уведомления.</span><span class="sxs-lookup"><span data-stu-id="ba400-117">Specify the text to include in the notification message body.</span></span>  
  
 <span data-ttu-id="ba400-118">**Просмотр T-SQL**</span><span class="sxs-lookup"><span data-stu-id="ba400-118">**View T-SQL**</span></span>  
 <span data-ttu-id="ba400-119">Просмотрите инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] , выполняемые для данной задачи по отношению к серверу, на основе выбранных параметров.</span><span class="sxs-lookup"><span data-stu-id="ba400-119">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ba400-120">Если количество затронутых объектов велико, построение этого отображения может занять значительное время.</span><span class="sxs-lookup"><span data-stu-id="ba400-120">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="ba400-121">Диалоговое окно «Создание соединения»</span><span class="sxs-lookup"><span data-stu-id="ba400-121">New Connection Dialog Box</span></span>  
 <span data-ttu-id="ba400-122">**Имя соединения**</span><span class="sxs-lookup"><span data-stu-id="ba400-122">**Connection name**</span></span>  
 <span data-ttu-id="ba400-123">Введите имя нового соединения.</span><span class="sxs-lookup"><span data-stu-id="ba400-123">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="ba400-124">**Выберите или введите имя сервера**</span><span class="sxs-lookup"><span data-stu-id="ba400-124">**Select or enter a server name**</span></span>  
 <span data-ttu-id="ba400-125">Выберите сервер для подключения при выполнении этой задачи.</span><span class="sxs-lookup"><span data-stu-id="ba400-125">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="ba400-126">**Обновить**</span><span class="sxs-lookup"><span data-stu-id="ba400-126">**Refresh**</span></span>  
 <span data-ttu-id="ba400-127">Обновите список доступных серверов.</span><span class="sxs-lookup"><span data-stu-id="ba400-127">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="ba400-128">**Введите данные для входа на сервер**</span><span class="sxs-lookup"><span data-stu-id="ba400-128">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="ba400-129">Укажите способ проверки подлинности на сервере.</span><span class="sxs-lookup"><span data-stu-id="ba400-129">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="ba400-130">**Использовать встроенную безопасность Windows**</span><span class="sxs-lookup"><span data-stu-id="ba400-130">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="ba400-131">Подключиться к экземпляру компонента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] c проверкой подлинности [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="ba400-131">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="ba400-132">**Использовать указанные имя пользователя и пароль**</span><span class="sxs-lookup"><span data-stu-id="ba400-132">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="ba400-133">Подключиться к экземпляру компонента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] с использованием проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ba400-133">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="ba400-134">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="ba400-134">This option is not available.</span></span>  
  
 <span data-ttu-id="ba400-135">**User name**</span><span class="sxs-lookup"><span data-stu-id="ba400-135">**User name**</span></span>  
 <span data-ttu-id="ba400-136">Укажите имя входа, используемое при проверке подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ba400-136">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="ba400-137">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="ba400-137">This option is not available.</span></span>  
  
 <span data-ttu-id="ba400-138">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="ba400-138">**Password**</span></span>  
 <span data-ttu-id="ba400-139">Укажите используемый при проверке подлинности пароль.</span><span class="sxs-lookup"><span data-stu-id="ba400-139">Provide a password to use when authenticating.</span></span> <span data-ttu-id="ba400-140">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="ba400-140">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba400-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="ba400-141">See Also</span></span>  
 <span data-ttu-id="ba400-142">[Database Mail](../database-mail/database-mail.md) </span><span class="sxs-lookup"><span data-stu-id="ba400-142">[Database Mail](../database-mail/database-mail.md) </span></span>  
 [<span data-ttu-id="ba400-143">sp_notify_operator (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="ba400-143">sp_notify_operator &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-notify-operator-transact-sql)  
  
  
