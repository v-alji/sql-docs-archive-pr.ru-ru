---
title: Просмотр журнала приложений Windows | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- application logs [SQL Server]
- Windows application logs [SQL Server]
- viewing Windows application logs
- errors [SQL Server], logs
- system logs [SQL Server]
- security logs [SQL Server]
- displaying Windows application logs
- logs [SQL Server], Windows application logs
ms.assetid: f9853b74-7db7-47cc-b957-e49ed5bc0a1a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 22f900a0b203e652bbc9cc6e9638711d138756c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659042"
---
# <a name="viewing-the-windows-application-log"></a><span data-ttu-id="e87af-102">Просмотр журнала приложений Windows</span><span class="sxs-lookup"><span data-stu-id="e87af-102">Viewing the Windows Application Log</span></span>
  <span data-ttu-id="e87af-103">Если настройками [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] предусмотрено использование журнала приложений Microsoft Windows, каждый сеанс [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] записывает новые события в этот журнал.</span><span class="sxs-lookup"><span data-stu-id="e87af-103">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured to use the Microsoft Windows application log, each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] session writes new events to that log.</span></span> <span data-ttu-id="e87af-104">В отличие от журнала ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , новый журнал приложений не создается заново каждый раз при запуске экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e87af-104">Unlike the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log, a new application log is not created each time you start an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="e87af-105">Просмотр и управление журналом приложений Windows осуществляется с помощью средства просмотра событий Windows или средства просмотра журналов в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e87af-105">View and manage the Windows application log by using Windows Event Viewer or the Log Viewer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="e87af-106">С помощью средства просмотра событий можно просмотреть три журнала.</span><span class="sxs-lookup"><span data-stu-id="e87af-106">There are three logs that can be viewed with Event Viewer.</span></span>  
  
|<span data-ttu-id="e87af-107">Тип журнала Windows</span><span class="sxs-lookup"><span data-stu-id="e87af-107">Windows log type</span></span>|<span data-ttu-id="e87af-108">Description</span><span class="sxs-lookup"><span data-stu-id="e87af-108">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="e87af-109">Системный журнал</span><span class="sxs-lookup"><span data-stu-id="e87af-109">System log</span></span>|<span data-ttu-id="e87af-110">Регистрирует события, записанные компонентами операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="e87af-110">Records events logged by the Windows operating system components.</span></span> <span data-ttu-id="e87af-111">Например, отказ загрузки драйвера или другого системного компонента при запуске записывается в системный журнал.</span><span class="sxs-lookup"><span data-stu-id="e87af-111">For example, the failure of a driver or other system component to load during startup is recorded in the system log.</span></span>|  
|<span data-ttu-id="e87af-112">Журнал безопасности</span><span class="sxs-lookup"><span data-stu-id="e87af-112">Security log</span></span>|<span data-ttu-id="e87af-113">Регистрирует события безопасности, например неудавшиеся попытки входа в систему.</span><span class="sxs-lookup"><span data-stu-id="e87af-113">Records security events, such as failed login attempts.</span></span> <span data-ttu-id="e87af-114">Это помогает отследить изменения в системе безопасности и идентифицировать возможные «дыры».</span><span class="sxs-lookup"><span data-stu-id="e87af-114">This helps track changes to the security system and identify possible breaches to security.</span></span> <span data-ttu-id="e87af-115">Например, попытка войти в систему регистрируется в журнале безопасности в зависимости от параметров аудита в диспетчере пользователей.</span><span class="sxs-lookup"><span data-stu-id="e87af-115">For example, attempts to log on to the system may be recorded in the security log, depending on the audit settings in the User Manager.</span></span><br /><br /> <span data-ttu-id="e87af-116">Только члены предопределенной роли сервера **sysadmin** могут просматривать журнал безопасности.</span><span class="sxs-lookup"><span data-stu-id="e87af-116">Only members of the **sysadmin** fixed server role can view the security log.</span></span>|  
|<span data-ttu-id="e87af-117">Журнал приложений</span><span class="sxs-lookup"><span data-stu-id="e87af-117">Application log</span></span>|<span data-ttu-id="e87af-118">Регистрирует события, записываемые приложениями.</span><span class="sxs-lookup"><span data-stu-id="e87af-118">Records events that are logged by applications.</span></span> <span data-ttu-id="e87af-119">Например, приложение базы данных может записать в журнал приложений ошибку файла.</span><span class="sxs-lookup"><span data-stu-id="e87af-119">For example, a database application might record a file error in the application log.</span></span>|  
  
 <span data-ttu-id="e87af-120">Дополнительные сведения о средстве просмотра событий, управлении журналом приложений и данных, которые он представляет, см. в документации Windows.</span><span class="sxs-lookup"><span data-stu-id="e87af-120">For more information about using Event Viewer, managing the application log, and understanding the information it presents, see the Windows documentation.</span></span>  
  
 <span data-ttu-id="e87af-121">**Просмотр журнала приложений Windows**</span><span class="sxs-lookup"><span data-stu-id="e87af-121">**To view the Windows application log**</span></span>  
  
 [<span data-ttu-id="e87af-122">Просмотр журнала приложений Windows (Windows)</span><span class="sxs-lookup"><span data-stu-id="e87af-122">View the Windows Application Log &#40;Windows&#41;</span></span>](../../relational-databases/performance/view-the-windows-application-log-windows-10.md)  
  
  
