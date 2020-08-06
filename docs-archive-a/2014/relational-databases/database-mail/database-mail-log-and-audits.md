---
title: Ведение журнала и аудит компонента Database Mail | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- auditing [SQL Server]
- Database Mail [SQL Server], auditing
- logs [Database Mail]
- audits [SQL Server], Database Mail
- Database Mail [SQL Server], logging
ms.assetid: 846589ee-5fe5-4ab3-b335-0c253e569f99
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6267389f187b955982ec1c18c411f703b4562f3c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751151"
---
# <a name="database-mail-log-and-audits"></a><span data-ttu-id="519ab-102">Ведение журнала и аудит компонента Database Mail</span><span class="sxs-lookup"><span data-stu-id="519ab-102">Database Mail Log and Audits</span></span>
  <span data-ttu-id="519ab-103">Регистрация в Database Mail спроектирована таким образом, чтобы обеспечить способ локализации и исправления неполадок.</span><span class="sxs-lookup"><span data-stu-id="519ab-103">The Database Mail logging functionality is designed to provide a way to isolate and correct problems.</span></span> <span data-ttu-id="519ab-104">Компонент Database Mail хранит сведения о регистрации в базе данных **msdb** .</span><span class="sxs-lookup"><span data-stu-id="519ab-104">Database Mail stores the log information in the **msdb** database.</span></span> <span data-ttu-id="519ab-105">Сведения о содержимом сообщений электронной почты Database Mail, их состояниях, а также о любых полученных сообщениях, например сообщениях об ошибках, регистрируются в Database Mail и могут использоваться для аудита или обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="519ab-105">Information about Database Mail e-mail content, status of e-mails, and any messages received, such as errors  are logged by Database Mail and can be used for troubleshooting and auditing purposes.</span></span>  
  
## <a name="database-mail-logs"></a><span data-ttu-id="519ab-106">Журналы компонента Database Mail</span><span class="sxs-lookup"><span data-stu-id="519ab-106">Database Mail Logs</span></span>  
 <span data-ttu-id="519ab-107">Таблицы в базе данных **msdb** записывают журнал из [Database Mail External Program](database-mail-external-program.md).</span><span class="sxs-lookup"><span data-stu-id="519ab-107">Tables in the **msdb** database log information from the [Database Mail External Program](database-mail-external-program.md).</span></span> <span data-ttu-id="519ab-108">[Представления компонента Database Mail (Transact-SQL)](/sql/relational-databases/system-catalog-views/database-mail-views-transact-sql) позволяют устранять неполадки в таблицах.</span><span class="sxs-lookup"><span data-stu-id="519ab-108">[Database Mail Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/database-mail-views-transact-sql) expose the tables for troubleshooting purposes.</span></span> <span data-ttu-id="519ab-109">В представлении [sysmail_event_log (Transact-SQL)](/sql/relational-databases/system-catalog-views/sysmail-event-log-transact-sql) отображаются ошибки, если компонент Service Broker не может запустить внешнюю программу, если в этой внешней программе возникли ошибки при работе с сетью или сервер SMTP отказался принять сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="519ab-109">Errors appear in the [sysmail_event_log &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sysmail-event-log-transact-sql) view if Service Broker cannot activate the external program, if the external program encounters networking errors or if the Simple Mail Transport Protocol (SMTP) server refuses an e-mail message.</span></span> <span data-ttu-id="519ab-110">В случае события, которое внешняя программа не может записать в таблицы **msdb** , она записывает ошибки в журнал событий приложений Windows.</span><span class="sxs-lookup"><span data-stu-id="519ab-110">In the event that the external program cannot log to the **msdb** tables, the program logs errors to the Windows application event log.</span></span>  
  
 <span data-ttu-id="519ab-111">Внутренние таблицы в базе данных **msdb** содержат электронные сообщения и вложения, присланные компонентом Database Mail, а также текущее состояние каждого сообщения.</span><span class="sxs-lookup"><span data-stu-id="519ab-111">Internal tables in the **msdb** database contain the e-mail messages and attachments sent from Database Mail, together with the current status of each message.</span></span> <span data-ttu-id="519ab-112">Компонент Database Mail обновляет эти таблицы при каждом обработанном сообщении.</span><span class="sxs-lookup"><span data-stu-id="519ab-112">Database Mail updates these tables as each message is processed.</span></span>  
  
## <a name="database-mail-auditing-tasks"></a><span data-ttu-id="519ab-113">Задачи аудита компонента Database Mail</span><span class="sxs-lookup"><span data-stu-id="519ab-113">Database Mail Auditing tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="519ab-114">**Обзор журналов компонента Database Mail и управление ими**</span><span class="sxs-lookup"><span data-stu-id="519ab-114">**Reviewing and managing Database Mail logs**</span></span>|<span data-ttu-id="519ab-115">**Ссылка на раздел**</span><span class="sxs-lookup"><span data-stu-id="519ab-115">**Link to Topic**</span></span>|  
|<span data-ttu-id="519ab-116">Проверьте состояние доставки отдельного сообщения</span><span class="sxs-lookup"><span data-stu-id="519ab-116">Check the delivery status of an individual message</span></span>|[<span data-ttu-id="519ab-117">Проверка состояния сообщений электронной почты, отправленных с помощью компонента Database Mail</span><span class="sxs-lookup"><span data-stu-id="519ab-117">Check the Status of E-Mail Messages Sent With Database Mail</span></span>](check-the-status-of-e-mail-messages-sent-with-database-mail.md)|  
|<span data-ttu-id="519ab-118">Очистите сообщения, вложения и записи журнала компонента Database Mail</span><span class="sxs-lookup"><span data-stu-id="519ab-118">Clean up Database Mail messages, attachments, and log entries</span></span>|[<span data-ttu-id="519ab-119">sysmail_delete_mailitems_sp (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="519ab-119">sysmail_delete_mailitems_sp &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sysmail-delete-mailitems-sp-transact-sql)<br /><br /> [<span data-ttu-id="519ab-120">sysmail_delete_log_sp (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="519ab-120">sysmail_delete_log_sp &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sysmail-delete-log-sp-transact-sql)|  
|<span data-ttu-id="519ab-121">Заархивируйте сообщения и журналы компонента Database Mail</span><span class="sxs-lookup"><span data-stu-id="519ab-121">Archive the Database Email Messages and Logs</span></span>|[<span data-ttu-id="519ab-122">Создание задания агента SQL Server по архивации сообщений и журналов событий компонента Database Mail</span><span class="sxs-lookup"><span data-stu-id="519ab-122">Create a SQL Server Agent Job to Archive Database Mail Messages and Event Logs</span></span>](create-a-sql-server-agent-job-to-archive-database-mail-messages-and-event-logs.md)|  
  
## <a name="see-also"></a><span data-ttu-id="519ab-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="519ab-123">See Also</span></span>  
 [<span data-ttu-id="519ab-124">Наблюдение за использованием ресурсов (системный монитор)</span><span class="sxs-lookup"><span data-stu-id="519ab-124">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](../performance-monitor/monitor-resource-usage-system-monitor.md)  
  
  
