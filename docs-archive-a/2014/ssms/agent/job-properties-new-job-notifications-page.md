---
title: 'Свойства задания: создание задания (страница "уведомления") | Документация Майкрософт'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.notifications.f1
ms.assetid: ed393cbd-4496-4399-a177-e5baa92fb689
author: stevestein
ms.author: sstein
ms.openlocfilehash: 30eca88943b48bd81bd38e236711d19ee7ec4503
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655514"
---
# <a name="job-properties-new-job-notifications-page"></a><span data-ttu-id="00ab9-102">Свойства задания: создание задания (страница "Уведомления")</span><span class="sxs-lookup"><span data-stu-id="00ab9-102">Job Properties: New Job (Notifications Page)</span></span>
  <span data-ttu-id="00ab9-103">Используйте эту страницу, чтобы задать действия, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выполняемые агентом при завершении задания.</span><span class="sxs-lookup"><span data-stu-id="00ab9-103">Use this page to set actions for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to perform when the job completes.</span></span>  
  
## <a name="options"></a><span data-ttu-id="00ab9-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="00ab9-104">Options</span></span>  
 <span data-ttu-id="00ab9-105">**Электронных**</span><span class="sxs-lookup"><span data-stu-id="00ab9-105">**E-mail**</span></span>  
 <span data-ttu-id="00ab9-106">Установите этот параметр для отправки электронной почты после завершения задания.</span><span class="sxs-lookup"><span data-stu-id="00ab9-106">Select this option to send e-mail when the job completes.</span></span> <span data-ttu-id="00ab9-107">Выбрав этот параметр, выберите оператора, которому будет направлено уведомление, и состояние, вызывающее его: **При успешном завершении задания**; **При ошибке задания**или **При завершении задания**.</span><span class="sxs-lookup"><span data-stu-id="00ab9-107">After selecting this option, choose the operator to notify and the condition that will trigger the notification: **When the job succeeds**; **When the job fails**; or **When the job completes**.</span></span>  
  
 <span data-ttu-id="00ab9-108">**Страница**</span><span class="sxs-lookup"><span data-stu-id="00ab9-108">**Page**</span></span>  
 <span data-ttu-id="00ab9-109">Установите этот параметр для отправки электронной почты на пейджер оператора после завершения задания.</span><span class="sxs-lookup"><span data-stu-id="00ab9-109">Select this option to send e-mail to an operator's pager when the job completes.</span></span> <span data-ttu-id="00ab9-110">Выбрав этот параметр, выберите оператора, которому будет направлено уведомление, и состояние, вызывающее его: **При успешном завершении задания**, **При ошибке задания**или **При завершении задания**.</span><span class="sxs-lookup"><span data-stu-id="00ab9-110">After selecting this option, specify the operator to notify and the condition that will trigger the notification: **When the job succeeds**; **When the job fails**; or **When the job completes**.</span></span>  
  
 <span data-ttu-id="00ab9-111">**NET SEND**</span><span class="sxs-lookup"><span data-stu-id="00ab9-111">**Net send**</span></span>  
 <span data-ttu-id="00ab9-112">Выберите этот параметр для использования команды NET SEND для оповещения оператора о завершении задания.</span><span class="sxs-lookup"><span data-stu-id="00ab9-112">Select this option to use net send to notify an operator when the job completes.</span></span> <span data-ttu-id="00ab9-113">Выбрав этот параметр, выберите оператора, которому будет направлено уведомление, и состояние, вызывающее его: **При успешном завершении задания**, **При ошибке задания**или **При завершении задания**.</span><span class="sxs-lookup"><span data-stu-id="00ab9-113">After selecting this option, specify the operator to notify and the condition that will trigger the notification: **When the job succeeds**; **When the job fails**; or **When the job completes**.</span></span>  
  
 <span data-ttu-id="00ab9-114">**Использовать журнал событий приложений Windows**</span><span class="sxs-lookup"><span data-stu-id="00ab9-114">**Write to the Windows Application event log**</span></span>  
 <span data-ttu-id="00ab9-115">Выберите этот параметр для создания записи в журнале событий приложений при завершении выполнения задания.</span><span class="sxs-lookup"><span data-stu-id="00ab9-115">Select this option to write an entry in the application event log when the job completes.</span></span> <span data-ttu-id="00ab9-116">Выбрав этот параметр, выберите состояние, вызывающее запись в журнал: **При успешном завершении задания**, **При ошибке задания**или **При завершении задания**.</span><span class="sxs-lookup"><span data-stu-id="00ab9-116">After selecting this option, specify the condition that will cause the entry to be written: **When the job succeeds**; **When the job fails**; or **When the job completes**.</span></span>  
  
 <span data-ttu-id="00ab9-117">**Автоматически удалить задание**</span><span class="sxs-lookup"><span data-stu-id="00ab9-117">**Automatically delete job**</span></span>  
 <span data-ttu-id="00ab9-118">Выберите этот параметр для автоматического удаления задания после его завершения.</span><span class="sxs-lookup"><span data-stu-id="00ab9-118">Select this option to delete the job when the job completes.</span></span> <span data-ttu-id="00ab9-119">Выбрав этот параметр, выберите состояние, которое вызовет удаление задания: **При успешном завершении задания**, **При ошибке задания**или **При завершении задания**.</span><span class="sxs-lookup"><span data-stu-id="00ab9-119">After selecting this option, specify the condition that will trigger deletion of the job: **When the job succeeds**; **When the job fails**; or **When the job completes**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00ab9-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="00ab9-120">See Also</span></span>  
 <span data-ttu-id="00ab9-121">[Реализация заданий](implement-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="00ab9-121">[Implement Jobs](implement-jobs.md) </span></span>  
 [<span data-ttu-id="00ab9-122">Настройка почты агента SQL Server на использование компонента Database Mail</span><span class="sxs-lookup"><span data-stu-id="00ab9-122">Configure SQL Server Agent Mail to Use Database Mail</span></span>](../../relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail.md)  
  
  
