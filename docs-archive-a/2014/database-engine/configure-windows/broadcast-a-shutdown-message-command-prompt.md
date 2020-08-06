---
title: Рассылка сообщения о завершении работы (командная строка) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server, stopping
- named instances [SQL Server], broadcasting shutdown messages
- shutdown message broadcast
- broadcasting shutdown message
- command prompt [SQL Server], broadcasting shutdown messages
- default instances [SQL Server], broadcasting shutdown messages
- stopping SQL Server
ms.assetid: 9f20ccd5-d952-431d-ba12-339911af9430
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 540baada4a78d7b5caf54cbabb9196ce5a79780e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733129"
---
# <a name="broadcast-a-shutdown-message-command-prompt"></a><span data-ttu-id="eeca5-102">Рассылка сообщения о завершении работы (командная строка)</span><span class="sxs-lookup"><span data-stu-id="eeca5-102">Broadcast a Shutdown Message (Command Prompt)</span></span>
  <span data-ttu-id="eeca5-103">В этой статье описывается широковещательная передача сообщения о завершении работы в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью команды **net send** .</span><span class="sxs-lookup"><span data-stu-id="eeca5-103">This topic describes how to broadcast a shutdown message in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using the **net send** command.</span></span> <span data-ttu-id="eeca5-104">В этом сообщении должно быть указано время остановки экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , чтобы пользователи могли к этому времени завершить выполнение своих задач.</span><span class="sxs-lookup"><span data-stu-id="eeca5-104">In the message, include the time the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will be stopped so that users can finish their tasks.</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-broadcast-a-shutdown-message"></a><span data-ttu-id="eeca5-105">Рассылка сообщения о завершении работы</span><span class="sxs-lookup"><span data-stu-id="eeca5-105">To broadcast a shutdown message</span></span>  
  
1.  <span data-ttu-id="eeca5-106">В командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="eeca5-106">From a command prompt, enter:</span></span>  
  
     <span data-ttu-id="eeca5-107">**net send /users "message"**</span><span class="sxs-lookup"><span data-stu-id="eeca5-107">**net send /users "message"**</span></span>  
  
     <span data-ttu-id="eeca5-108">Параметр **/users** указывает, что сообщение будет отправлено всем пользователям, поддерживающим соединение с сервером.</span><span class="sxs-lookup"><span data-stu-id="eeca5-108">The **/users** option specifies that the message be sent to all users connected to the server</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eeca5-109">Команда **net send** требует, чтобы служба была запущена как на компьютере отправителя, так и на компьютерах получателей.</span><span class="sxs-lookup"><span data-stu-id="eeca5-109">The **net send** command requires the messenger service to be running on both the sending and the receiving computers.</span></span> <span data-ttu-id="eeca5-110">Служба сообщений по умолчанию отключена в Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="eeca5-110">The messenger service is disabled by default on Windows Server 2003.</span></span> <span data-ttu-id="eeca5-111">Дополнительные сведения о команде **net send**см. в документации по Windows.</span><span class="sxs-lookup"><span data-stu-id="eeca5-111">For information about **net send**, see the Windows documentation.</span></span>  
  
 <span data-ttu-id="eeca5-112">В сети может оказаться более удобным использовать для связи с пользователями электронную почту или телефон.</span><span class="sxs-lookup"><span data-stu-id="eeca5-112">On your network, it may be more appropriate to contact users by e-mail or the telephone.</span></span> <span data-ttu-id="eeca5-113">Чтобы определить, какие пользователи в настоящий момент подключены к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], используйте монитор активности.</span><span class="sxs-lookup"><span data-stu-id="eeca5-113">To determine which users are currently connected to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], use the Activity Monitor.</span></span> <span data-ttu-id="eeca5-114">Сведения о мониторе активности см. в статье [Монитор активности](../../relational-databases/performance-monitor/activity-monitor.md) и [Открытие монитора активности (среда SQL Server Management Studio)](../../relational-databases/performance-monitor/open-activity-monitor-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="eeca5-114">For information on the Activity Monitor, see [Activity Monitor](../../relational-databases/performance-monitor/activity-monitor.md) and [Open Activity Monitor &#40;SQL Server Management Studio&#41;](../../relational-databases/performance-monitor/open-activity-monitor-sql-server-management-studio.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeca5-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="eeca5-115">See Also</span></span>  
 [<span data-ttu-id="eeca5-116">Запуск, остановка, приостановка, возобновление и перезапуск компонента Database Engine, агента SQL и службы браузера SQL Server</span><span class="sxs-lookup"><span data-stu-id="eeca5-116">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>](start-stop-pause-resume-restart-sql-server-services.md)  
  
  
