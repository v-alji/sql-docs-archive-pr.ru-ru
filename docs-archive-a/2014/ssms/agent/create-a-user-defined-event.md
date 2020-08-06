---
title: Создание пользовательского события | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent alerts, user-defined events
- user-defined events [SQL Server]
- multiple language support [SQL Server], alerts
- languages [SQL Server], alerts
- severity levels [SQL Server]
- global considerations [SQL Server], alerts
- events [SQL Server], user-defined
- SQL Server Agent alerts, multiple-language environments
- alerts [SQL Server], user-defined events
- alerts [SQL Server], multiple-language environments
- custom events [SQL Server Agent]
- international considerations [SQL Server], alerts
ms.assetid: 03d71a35-97fa-4bba-aa9a-23ac9c9cf879
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2323dc4da3d1a8a67dad41ea189877ade25eff0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751643"
---
# <a name="create-a-user-defined-event"></a><span data-ttu-id="556f6-102">Создание пользовательского события</span><span class="sxs-lookup"><span data-stu-id="556f6-102">Create a User-Defined Event</span></span>
  <span data-ttu-id="556f6-103">Можно создать пользовательское событие, если нужно производить мониторинг событий, отличных от предопределенных системой [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="556f6-103">You can create user-defined events if you want to monitor events other than events that are predefined by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="556f6-104">Можно назначить уровень серьезности для каждого пользовательского события.</span><span class="sxs-lookup"><span data-stu-id="556f6-104">You can also assign a severity level to each user-defined event.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="556f6-105">При использовании среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]выберите параметр **Записать журнал событий приложений Windows** для каждого сообщения определяемого пользователем события, чтобы регистрировать данные сообщения.</span><span class="sxs-lookup"><span data-stu-id="556f6-105">When using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the **Write to Windows application event log** option for each user-defined event message, to ensure that the messages are logged.</span></span> <span data-ttu-id="556f6-106">По умолчанию после возникновения определяемые пользователем сообщения с уровнем серьезности, меньшим 19, не отправляются в журнал приложений [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="556f6-106">By default, user-defined messages of severity lower than 19 are not sent to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application log when they occur.</span></span> <span data-ttu-id="556f6-107">Определяемые пользователем сообщения с уровнем серьезности, меньшим 19, не приводят к возникновению предупреждения агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="556f6-107">User-defined messages of severity lower than 19 therefore do not trigger SQL Server Agent alerts.</span></span>  
  
 <span data-ttu-id="556f6-108">Определяемые пользователем события должны обладать уникальными номерами сообщений.</span><span class="sxs-lookup"><span data-stu-id="556f6-108">User-defined events must have a unique message number.</span></span> <span data-ttu-id="556f6-109">Номера сообщений для определяемых пользователем событий должны превышать 50 000.</span><span class="sxs-lookup"><span data-stu-id="556f6-109">Message numbers for a user-defined event must be greater than 50,000.</span></span> <span data-ttu-id="556f6-110">Можно определить сообщения для событий на нескольких языках.</span><span class="sxs-lookup"><span data-stu-id="556f6-110">You can define messages for the event in multiple languages.</span></span> <span data-ttu-id="556f6-111">Однако перед добавлением сообщений на других языках должно быть создано сообщение об ошибке **En-US** .</span><span class="sxs-lookup"><span data-stu-id="556f6-111">However, an **En-US** error message must exist before messages in other languages can be added.</span></span>  
  
 <span data-ttu-id="556f6-112">При управлении многоязыковым окружением [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] необходимо создать пользовательские сообщения на всех поддерживаемых языках.</span><span class="sxs-lookup"><span data-stu-id="556f6-112">If you administer a multiple-language [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] environment, create user-defined messages in each of the languages that are supported.</span></span> <span data-ttu-id="556f6-113">Например, если создается новое сообщение события, которое будет использоваться и на английском, и на немецком сервере, то необходимо использовать один и тот же номер сообщения и один и тот же уровень серьезности для обоих серверов, но на каждый из них назначить сообщение на соответствующем языке.</span><span class="sxs-lookup"><span data-stu-id="556f6-113">For example, if you are creating a new event message to be used on both an English and a German server, use the same message number and severity for both, but assign a different language to each.</span></span>  
  
 <span data-ttu-id="556f6-114">В следующих задачах приводятся сведения о том, как создавать пользовательские события и реагирующие на них предупреждения.</span><span class="sxs-lookup"><span data-stu-id="556f6-114">The following tasks provide information about how to create user-defined events and alerts that respond to them:</span></span>  
  
 <span data-ttu-id="556f6-115">**Создание предупреждения по номеру сообщения**</span><span class="sxs-lookup"><span data-stu-id="556f6-115">**To create an alert based on a message number**</span></span>  
  
-   [<span data-ttu-id="556f6-116">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="556f6-116">SQL Server Management Studio</span></span>](create-an-alert-using-an-error-number.md)  
  
-   [<span data-ttu-id="556f6-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="556f6-117">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql)  
  
 <span data-ttu-id="556f6-118">**Создание предупреждения по уровню серьезности**</span><span class="sxs-lookup"><span data-stu-id="556f6-118">**To create an alert based on severity levels**</span></span>  
  
-   [<span data-ttu-id="556f6-119">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="556f6-119">SQL Server Management Studio</span></span>](create-an-alert-using-severity-level.md)  
  
-   [<span data-ttu-id="556f6-120">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="556f6-120">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql)  
  
 <span data-ttu-id="556f6-121">**Определение ответа на предупреждение**</span><span class="sxs-lookup"><span data-stu-id="556f6-121">**To define the response to an alert**</span></span>  
  
-   [<span data-ttu-id="556f6-122">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="556f6-122">SQL Server Management Studio</span></span>](../sql-server-management-studio-ssms.md)  
  
-   [<span data-ttu-id="556f6-123">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="556f6-123">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql)  
  
 <span data-ttu-id="556f6-124">**Создание сообщения об ошибке пользовательского события**</span><span class="sxs-lookup"><span data-stu-id="556f6-124">**To create a user-defined event error message**</span></span>  
  
-   [<span data-ttu-id="556f6-125">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="556f6-125">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-addmessage-transact-sql)  
  
 <span data-ttu-id="556f6-126">**Изменение сообщения об ошибке пользовательского события**</span><span class="sxs-lookup"><span data-stu-id="556f6-126">**To modify a user-defined event error message**</span></span>  
  
-   [<span data-ttu-id="556f6-127">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="556f6-127">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-altermessage-transact-sql)  
  
 <span data-ttu-id="556f6-128">**Удаление сообщения об ошибке пользовательского события**</span><span class="sxs-lookup"><span data-stu-id="556f6-128">**To delete a user-defined event error message**</span></span>  
  
-   [<span data-ttu-id="556f6-129">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="556f6-129">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-dropmessage-transact-sql)  
  
 <span data-ttu-id="556f6-130">**Отключение или повторное включение предупреждения**</span><span class="sxs-lookup"><span data-stu-id="556f6-130">**To disable or reactivate an alert**</span></span>  
  
-   [<span data-ttu-id="556f6-131">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="556f6-131">SQL Server Management Studio</span></span>](disable-or-reactivate-an-alert.md)  
  
-   [<span data-ttu-id="556f6-132">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="556f6-132">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="556f6-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="556f6-133">See Also</span></span>  
 [<span data-ttu-id="556f6-134">sp_update_alert &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="556f6-134">sp_update_alert &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql)  
  
  
