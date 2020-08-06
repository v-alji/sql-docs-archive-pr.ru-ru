---
title: Мониторинг журналов ошибок | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server]
- database performance [SQL Server], errors
- Windows application logs [SQL Server]
- monitoring performance [SQL Server], errors
- server performance [SQL Server], errors
- comparing error and application log output
- errors [SQL Server], logs
- tuning databases [SQL Server], errors
- database monitoring [SQL Server], errors
- SQL Server error log
- logs [SQL Server], SQL Server error logs
- error logs [SQL Server]
- logs [SQL Server], Windows application logs
ms.assetid: e250336b-0695-44f6-a42f-23222f94e377
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2a47891599dbe735bd437f5239c73bfd34c422ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659052"
---
# <a name="monitoring-the-error-logs"></a><span data-ttu-id="6ee4b-102">Контроль за журналом ошибок</span><span class="sxs-lookup"><span data-stu-id="6ee4b-102">Monitoring the Error Logs</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6ee4b-103">заносит сведения об определенных событиях системы и пользовательских операциях в журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и журнал приложений [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="6ee4b-103">logs certain system events and user-defined events to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application log.</span></span> <span data-ttu-id="6ee4b-104">Оба журнала автоматически фиксируют отметки времени всех зарегистрированных событий.</span><span class="sxs-lookup"><span data-stu-id="6ee4b-104">Both logs automatically timestamp all recorded events.</span></span> <span data-ttu-id="6ee4b-105">Сведения из журнала ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] используются для устранения неполадок, связанных с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6ee4b-105">Use the information in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to troubleshoot problems related to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="6ee4b-106">Журнал приложений Windows предоставляет общую картину событий, произошедших в операционной системе Windows, а также всех событий [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6ee4b-106">The Windows application log provides an overall picture of events that occur on the Windows operating system, as well as events in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="6ee4b-107">Для просмотра журнала приложений Windows и фильтрации сведений используется программа просмотра событий Windows.</span><span class="sxs-lookup"><span data-stu-id="6ee4b-107">Use the Windows Event Viewer to view the Windows application log and to filter the information.</span></span> <span data-ttu-id="6ee4b-108">Например, можно отфильтровать такие события, как сведения, предупреждения, ошибки, успешный аудит и неуспешный аудит.</span><span class="sxs-lookup"><span data-stu-id="6ee4b-108">For example, you can filter events, such as information, warning, error, success audit, and failure audit.</span></span>  
  
## <a name="comparing-error-and-application-log-output"></a><span data-ttu-id="6ee4b-109">сравнение содержимого журнала ошибок и приложений</span><span class="sxs-lookup"><span data-stu-id="6ee4b-109">Comparing Error and Application Log Output</span></span>  
 <span data-ttu-id="6ee4b-110">Чтобы определить причину проблемы, можно использовать как журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , так и журнал приложений Windows.</span><span class="sxs-lookup"><span data-stu-id="6ee4b-110">You can use both the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and the Windows application log to identify the cause of problems.</span></span> <span data-ttu-id="6ee4b-111">Например, в журнале ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] могут встречаться сообщения, не несущие в себе сведений о причине проблемы.</span><span class="sxs-lookup"><span data-stu-id="6ee4b-111">For example, while monitoring the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log, you may encounter error messages that do not contain cause information.</span></span> <span data-ttu-id="6ee4b-112">Сравнивая даты и время событий в этих журналах, можно сузить список потенциальных причин.</span><span class="sxs-lookup"><span data-stu-id="6ee4b-112">By comparing the dates and times for events between these logs, you can narrow the list of probable causes.</span></span> <span data-ttu-id="6ee4b-113">Программа просмотра файла журнала среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] позволяет объединить журналы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и Windows в общий список, облегчая понимание событий, связанных с сервером и событий [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6ee4b-113">The [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Log File Viewer lets you integrate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, and the Windows logs into a single list, making it easy to understand related server events and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] events.</span></span> <span data-ttu-id="6ee4b-114">Дополнительные сведения см. в разделе «Средство просмотра журнала» электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6ee4b-114">For more information, see the topic "Log File Viewer" in SQL Server Books Online.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6ee4b-115">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="6ee4b-115">In This Section</span></span>  
  
|<span data-ttu-id="6ee4b-116">Раздел</span><span class="sxs-lookup"><span data-stu-id="6ee4b-116">Topic</span></span>|<span data-ttu-id="6ee4b-117">Description</span><span class="sxs-lookup"><span data-stu-id="6ee4b-117">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="6ee4b-118">Просмотр журнала ошибок SQL Server</span><span class="sxs-lookup"><span data-stu-id="6ee4b-118">Viewing the SQL Server Error Log</span></span>](../../../2014/tools/configuration-manager/viewing-the-sql-server-error-log.md)|<span data-ttu-id="6ee4b-119">Содержит сведения о журнале ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и способах его просмотра.</span><span class="sxs-lookup"><span data-stu-id="6ee4b-119">Contains information about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and how to view it.</span></span>|  
|[<span data-ttu-id="6ee4b-120">Просмотр журнала приложений Windows</span><span class="sxs-lookup"><span data-stu-id="6ee4b-120">Viewing the Windows Application Log</span></span>](viewing-the-windows-application-log.md)|<span data-ttu-id="6ee4b-121">Содержит сведения о журнале приложений Windows и способах его просмотра.</span><span class="sxs-lookup"><span data-stu-id="6ee4b-121">Contains information about the Windows application log and how to view it.</span></span>|  
  
  
