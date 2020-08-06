---
title: Журнал ошибок агента SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], SQL Server Agent
- messages [SQL Server], SQL Server Agent
- errors [SQL Server], logs
- SQL Server Agent, errors
ms.assetid: 0b2d6e6e-cd2d-4b8b-9fa2-2bbd2fc0da41
author: stevestein
ms.author: sstein
ms.openlocfilehash: ea9a723695c6993f4f07897f49d8014a86ce78b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731318"
---
# <a name="sql-server-agent-error-log"></a><span data-ttu-id="693bf-102">Журнал ошибок агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="693bf-102">SQL Server Agent Error Log</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="693bf-103">Агент создает журнал ошибок, в который по умолчанию записываются предупреждения и ошибки.</span><span class="sxs-lookup"><span data-stu-id="693bf-103">Agent creates an error log that records warnings and errors by default.</span></span> <span data-ttu-id="693bf-104">В журнале отображаются следующие предупреждения и ошибки:</span><span class="sxs-lookup"><span data-stu-id="693bf-104">The following warnings and errors are displayed in the log:</span></span>  
  
-   <span data-ttu-id="693bf-105">Предупреждающие сообщения, содержащие сведения о потенциальных проблемах, например "задание \<*job_name*> было удалено во время его выполнения".</span><span class="sxs-lookup"><span data-stu-id="693bf-105">Warning messages that provide information about potential problems, such as "Job \<*job_name*> was deleted while it was running."</span></span>  
  
-   <span data-ttu-id="693bf-106">Сообщения об ошибках, обычно требующих вмешательства системного администратора, например «Невозможно начать почтовый сеанс».</span><span class="sxs-lookup"><span data-stu-id="693bf-106">Error messages that usually require intervention by a system administrator, such as "Unable to start mail session."</span></span> <span data-ttu-id="693bf-107">Сообщения об ошибках могут отправляться конкретному пользователю или на конкретный компьютер с помощью команды **net send**.</span><span class="sxs-lookup"><span data-stu-id="693bf-107">Error messages can be sent to a specific user or computer by **net send**.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="693bf-108">поддерживает до девяти журналов ошибок агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="693bf-108">maintains up to nine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error logs.</span></span> <span data-ttu-id="693bf-109">Каждый архивируемый журнал снабжается расширением, указывающим относительный срок давности журнала.</span><span class="sxs-lookup"><span data-stu-id="693bf-109">Each archived log has an extension that indicates the relative age of the log.</span></span> <span data-ttu-id="693bf-110">Например, расширение .1 указывает на новейший архивированный журнал ошибок, а расширение .9 — на наиболее старый.</span><span class="sxs-lookup"><span data-stu-id="693bf-110">For example, an extension of .1 indicates the newest archived error log and an extension of .9 indicates the oldest archived error log.</span></span>  
  
 <span data-ttu-id="693bf-111">По умолчанию сообщения трассировки выполнения не записываются в журнал ошибок агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , так как они могут его переполнить.</span><span class="sxs-lookup"><span data-stu-id="693bf-111">By default, execution trace messages are not written to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log, because they can fill it.</span></span> <span data-ttu-id="693bf-112">При заполнении журнала ошибок снижается возможность выбора и анализа более сложных ошибок.</span><span class="sxs-lookup"><span data-stu-id="693bf-112">When the error log is full, your ability to select and analyze more difficult errors is reduced.</span></span> <span data-ttu-id="693bf-113">Так как ведение журнала увеличивает нагрузку на сервер, важно правильно оценить эффект, получаемый при захвате сообщений трассировки выполнения в журнал ошибок.</span><span class="sxs-lookup"><span data-stu-id="693bf-113">Because the log adds to the server's processing load, it is important to consider carefully what value you obtain by capturing execution trace messages to the error log.</span></span> <span data-ttu-id="693bf-114">В общем случае захват всех сообщений будет наилучшим вариантом только при отладке конкретной проблемы.</span><span class="sxs-lookup"><span data-stu-id="693bf-114">Generally, it is best to capture all messages only when you are debugging a specific problem.</span></span>  
  
 <span data-ttu-id="693bf-115">Когда агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] остановлен, размещение журнала ошибок агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] можно изменить.</span><span class="sxs-lookup"><span data-stu-id="693bf-115">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent is stopped, you can modify the location of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log.</span></span> <span data-ttu-id="693bf-116">Если журнал ошибок пустой, открыть его невозможно.</span><span class="sxs-lookup"><span data-stu-id="693bf-116">When the error log is empty, the log cannot be opened.</span></span> <span data-ttu-id="693bf-117">Журнал агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] можно в любое время циклически перезаписывать без остановки агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="693bf-117">You can cycle the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent log at any time without stopping [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
 <span data-ttu-id="693bf-118">**Просмотр журнала ошибок агента SQL Server**</span><span class="sxs-lookup"><span data-stu-id="693bf-118">**To view the SQL Server Agent error log**</span></span>  
  
-   [<span data-ttu-id="693bf-119">Просмотр журнала ошибок агента SQL Server (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="693bf-119">View SQL Server Agent Error Log &#40;SQL Server Management Studio&#41;</span></span>](view-sql-server-agent-error-log-sql-server-management-studio.md) 
  
 <span data-ttu-id="693bf-120">**Переименование журнала ошибок агента SQL Server**</span><span class="sxs-lookup"><span data-stu-id="693bf-120">**To rename a SQL Server Agent error log**</span></span>  
  
-   [<span data-ttu-id="693bf-121">Переименование журнала ошибок агента SQL Server (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="693bf-121">Rename a SQL Server Agent Error Log &#40;SQL Server Management Studio&#41;</span></span>](rename-a-sql-server-agent-error-log-sql-server-management-studio.md)  
  
 <span data-ttu-id="693bf-122">**Отправка сообщений об ошибках агента SQL Server**</span><span class="sxs-lookup"><span data-stu-id="693bf-122">**To send SQL Server Agent error messages**</span></span>  
  
-   [<span data-ttu-id="693bf-123">Send SQL Server Agent Error Messages</span><span class="sxs-lookup"><span data-stu-id="693bf-123">Send SQL Server Agent Error Messages</span></span>](send-sql-server-agent-error-messages.md)  
  
 <span data-ttu-id="693bf-124">**Запись сообщений трассировки выполнения в журнал ошибок агента SQL Server**</span><span class="sxs-lookup"><span data-stu-id="693bf-124">**To write execution trace messages to the SQL Server Agent error log**</span></span>  
  
-   [<span data-ttu-id="693bf-125">Запись сообщений трассировки выполнения в журнал ошибок агента SQL Server (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="693bf-125">Write Execution Trace Messages to the SQL Server Agent Error Log &#40;SQL Server Management Studio&#41;</span></span>](write-execution-trace-messages-to-sql-server-agent-log-ssms.md)  
  
  
