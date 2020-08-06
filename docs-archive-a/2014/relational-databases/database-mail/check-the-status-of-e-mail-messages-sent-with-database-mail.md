---
title: Проверка состояния сообщений электронной почты, отправленных с помощью компонента Database Mail | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- e-mail [SQL Server], status information
- mail [SQL Server], status information
- Database Mail [SQL Server], message status
- status information [Database Mail]
ms.assetid: eb290f24-b52f-46bc-84eb-595afee6a5f3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1642c456cd64484dede64f8127ff2f979f2242e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668890"
---
# <a name="check-the-status-of-e-mail-messages-sent-with-database-mail"></a><span data-ttu-id="3b222-102">Проверка состояния сообщений электронной почты, отправленных при помощи компонента Database Mail</span><span class="sxs-lookup"><span data-stu-id="3b222-102">Check the Status of E-Mail Messages Sent With Database Mail</span></span>
  <span data-ttu-id="3b222-103">В этом разделе описывается порядок проверки с помощью [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] состояния сообщений электронной почты, отправленных компонентом Database Mail в [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b222-103">This topic describes how to check the status of the e-mail message sent using Database Mail  in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="3b222-104">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="3b222-104">**Before you begin:**</span></span>  
  
-   <span data-ttu-id="3b222-105">**Проверка состояния сообщений электронной почты, отправленных компонентом Database Mail с помощью:**  [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="3b222-105">**To view the status of the e-mail sent using Database Mail, using:**  [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3b222-106">Перед началом</span><span class="sxs-lookup"><span data-stu-id="3b222-106">Before You Begin</span></span>  
 <span data-ttu-id="3b222-107">Компонент Database Mail хранит копии исходящих сообщений электронной почты и отображает их в представлениях **sysmail_allitems**, **sysmail_sentitems**, **sysmail_unsentitems**и **sysmail_faileditems** базы данных **msdb** .</span><span class="sxs-lookup"><span data-stu-id="3b222-107">Database Mail keeps copies of outgoing e-mail messages and displays them in the **sysmail_allitems**, **sysmail_sentitems**, **sysmail_unsentitems**, **sysmail_faileditems** views of the **msdb** database.</span></span> <span data-ttu-id="3b222-108">Внешняя программа компонента Database Mail протоколирует активность и отображает журнал при помощи компонента Windows Application Event Log и представления **sysmail_event_log** базы данных **msdb** .</span><span class="sxs-lookup"><span data-stu-id="3b222-108">The Database Mail external program logs activity and displays the log through the Windows Application Event Log and the **sysmail_event_log** view in the **msdb** database.</span></span> <span data-ttu-id="3b222-109">Для проверки состояния сообщений электронной почты запустите запрос для данного представления.</span><span class="sxs-lookup"><span data-stu-id="3b222-109">To check the status of an e-mail message, run a query against this view.</span></span> <span data-ttu-id="3b222-110">У сообщений электронной почты может быть одно из следующих четырех состояний: **отправлено**, **не отправлено**, **попытка отправки**и **ошибка при отправке**.</span><span class="sxs-lookup"><span data-stu-id="3b222-110">E-mail messages have one of four possible statuses: **sent**, **unsent**, **retrying**, and **failed**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3b222-111">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3b222-111">Using Transact-SQL</span></span>  
 <span data-ttu-id="3b222-112">**Проверка состояния сообщений электронной почты, отправленных компонентом Database Mail**</span><span class="sxs-lookup"><span data-stu-id="3b222-112">**To view the status of the e-mail sent using Database Mail**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3b222-113">Пример этой процедуры см. в подразделе [Примеры (Transact-SQL)](#TsqlExample)далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="3b222-113">For an example of this procedure, see [Example (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="3b222-114">Выберите из таблицы **sysmail_allitems** важные сообщения, используя поля **mailitem_id** или **sent_status**.</span><span class="sxs-lookup"><span data-stu-id="3b222-114">Select from the **sysmail_allitems** table, specifying the messages of interest by **mailitem_id** or **sent_status**.</span></span>  
  
2.  <span data-ttu-id="3b222-115">Чтобы проверить состояние сообщений электронной почты, возвращенных из внешней программы, соединение **sysmail_allitems** с представлением **sysmail_event_log** столбца **mailitem_id** , как показано в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="3b222-115">To check the status returned from the external program for the e-mail messages, join **sysmail_allitems** to **sysmail_event_log** view on the **mailitem_id** column, as shown in the following section.</span></span>  
  
     <span data-ttu-id="3b222-116">По умолчанию внешняя программа не протоколирует сведения об успешно посланных сообщениях.</span><span class="sxs-lookup"><span data-stu-id="3b222-116">By default, the external program does not log information about messages that were successfully sent.</span></span> <span data-ttu-id="3b222-117">Для протоколирования всех сообщений установите детализированный уровень ведения журнала на странице **Установка параметров системы** окна **Мастер настройки компонента Database Mail**.</span><span class="sxs-lookup"><span data-stu-id="3b222-117">To log all messages, set the logging level to verbose using the **Configure System Parameters** page of the **Database Mail Configuration Wizard.**</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="3b222-118">Примеры (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3b222-118">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="3b222-119">В следующем примере приводятся данные о любых сообщениях электронной почты, отправленных `danw` , которые внешняя программа не смогла успешно отправить.</span><span class="sxs-lookup"><span data-stu-id="3b222-119">The following example lists information about any e-mail messages sent to `danw` that the external program could not send successfully.</span></span> <span data-ttu-id="3b222-120">Инструкция выдает тему, дату и время попытки отправки сообщения, при отправке которого внешней программой произошла ошибка, а также текст сообщения об ошибке из журнала компонента Database Mail.</span><span class="sxs-lookup"><span data-stu-id="3b222-120">The statement lists the subject, the date and time that the external program failed to send the message, and the error message from the Database Mail log.</span></span>  
  
```  
USE msdb ;  
GO  
  
-- Show the subject, the time that the mail item row was last  
-- modified, and the log information.  
-- Join sysmail_faileditems to sysmail_event_log   
-- on the mailitem_id column.  
-- In the WHERE clause list items where danw was in the recipients,  
-- copy_recipients, or blind_copy_recipients.  
-- These are the items that would have been sent  
-- to danw.  
  
SELECT items.subject,  
    items.last_mod_date  
    ,l.description FROM dbo.sysmail_faileditems as items  
INNER JOIN dbo.sysmail_event_log AS l  
    ON items.mailitem_id = l.mailitem_id  
WHERE items.recipients LIKE '%danw%'    
    OR items.copy_recipients LIKE '%danw%'   
    OR items.blind_copy_recipients LIKE '%danw%'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="3b222-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="3b222-121">See Also</span></span>  
 [<span data-ttu-id="3b222-122">Ведение журнала и аудит компонента Database Mail</span><span class="sxs-lookup"><span data-stu-id="3b222-122">Database Mail Log and Audits</span></span>](database-mail-log-and-audits.md)  
  
  
