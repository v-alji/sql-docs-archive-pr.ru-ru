---
title: Получение сведений об уведомлениях о событиях | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- event notifications [SQL Server], metadata
- status information [SQL Server], event notifications
- metadata [SQL Server], event notifications
ms.assetid: 8bc10867-66d6-4f57-ac32-a6c29f3327cd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c8d8271b6279910321058d01c7b2f96b1df62bd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732482"
---
# <a name="get-information-about-event-notifications"></a><span data-ttu-id="3aa0c-102">Получение сведений об уведомлениях о событиях</span><span class="sxs-lookup"><span data-stu-id="3aa0c-102">Get Information About Event Notifications</span></span>
  <span data-ttu-id="3aa0c-103">Следующие представления каталога доступны для запроса метаданных об уведомлениях о событиях.</span><span class="sxs-lookup"><span data-stu-id="3aa0c-103">The following catalog views are available to query metadata about event notifications.</span></span>  
  
 <span data-ttu-id="3aa0c-104">**Получение сведений об уведомлениях о событиях несерверного уровня**</span><span class="sxs-lookup"><span data-stu-id="3aa0c-104">**To get information about nonserver-level event notifications**</span></span>  
  
-   [<span data-ttu-id="3aa0c-105">sys.event_notifications (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3aa0c-105">sys.event_notifications &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-event-notifications-transact-sql)  
  
> [!NOTE]  
>  <span data-ttu-id="3aa0c-106">Необходимые минимальные требования для просмотра метаданных о любом уведомлении в **sys.event_notifications** , созданном на уровне базы данных: иметь разрешение CONTROL, ALTER, TAKE OWNERSHIP или VIEW DEFINITION для базы данных, быть владельцем уведомления о событии или иметь разрешение ALTER ANY DATABASE EVENT NOTIFICATION.</span><span class="sxs-lookup"><span data-stu-id="3aa0c-106">To view metadata about any event notification in **sys.event_notifications** created at the database level, at the minimum you must have the following: CONTROL, ALTER, TAKE OWNERSHIP, or VIEW DEFINITION permission on the database, be the owner of the event notification, or have ALTER ANY DATABASE EVENT NOTIFICATION permission.</span></span> <span data-ttu-id="3aa0c-107">Необходимые минимальные требования для уведомлений о событиях, созданных в определенной очереди: иметь разрешение CONTROL, ALTER, TAKE OWNERSHIP или VIEW DEFINITION для объекта, быть владельцем уведомления о событии или иметь разрешение ALTER ANY DATABASE EVENT NOTIFICATION.</span><span class="sxs-lookup"><span data-stu-id="3aa0c-107">For event notifications created on a specific queue, at the minimum you must have the following: CONTROL, ALTER, TAKE OWNERSHIP, or VIEW DEFINITION permission on the object, be the owner of the event notification, or have ALTER ANY DATABASE EVENT NOTIFICATION permission.</span></span>  
  
 <span data-ttu-id="3aa0c-108">**Получение сведений об уведомлениях о событиях серверного уровня**</span><span class="sxs-lookup"><span data-stu-id="3aa0c-108">**To get information about server-level event notifications**</span></span>  
  
-   [<span data-ttu-id="3aa0c-109">sys.server_event_notifications (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3aa0c-109">sys.server_event_notifications &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-event-notifications-transact-sql)  
  
> [!NOTE]  
>  <span data-ttu-id="3aa0c-110">Необходимые минимальные требования для просмотра метаданных любого уведомления о событии в представлении каталога **sys.server_event_notifications**: иметь разрешение CONTROL или VIEW ANY DEFINITION для сервера, быть именем входа или владельцем уведомления о событии или иметь разрешение ALTER ANY EVENT NOTIFICATION.</span><span class="sxs-lookup"><span data-stu-id="3aa0c-110">At the minimum, you must have the following: CONTROL or VIEW ANY DEFINITION permission on the server, be the logon or owner of the event notification, or have ALTER ANY EVENT NOTIFICATION permission to view metadata about any event notification in **sys.server_event_notifications**.</span></span>  
  
 <span data-ttu-id="3aa0c-111">**Получение сведений обо всех событиях, которые могут создать уведомления**</span><span class="sxs-lookup"><span data-stu-id="3aa0c-111">**To get information about all events that can fire event notifications**</span></span>  
  
-   [<span data-ttu-id="3aa0c-112">sys.event_notification_event_types (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3aa0c-112">sys.event_notification_event_types &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-event-notification-event-types-transact-sql)  
  
> [!NOTE]  
>  <span data-ttu-id="3aa0c-113">Это представление каталога не возвращает группы событий.</span><span class="sxs-lookup"><span data-stu-id="3aa0c-113">This catalog view does not return event groups.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3aa0c-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="3aa0c-114">See Also</span></span>  
 [<span data-ttu-id="3aa0c-115">Уведомления о событиях</span><span class="sxs-lookup"><span data-stu-id="3aa0c-115">Event Notifications</span></span>](event-notifications.md)  
  
  
