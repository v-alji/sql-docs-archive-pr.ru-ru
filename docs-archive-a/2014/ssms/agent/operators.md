---
title: Операторы | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- operators (users) [Database Engine]
- fail-safe operator [SQL Server]
- aliases [SQL Server], operators
- SQL Server Agent alerts, operators
- contact information [SQL Server Agent]
- net send [SQL Server]
- e-mail [SQL Server], SQL Server Agent operators
- pager notifications [SQL Server Agent]
- mail [SQL Server], SQL Server Agent operators
- operators (users) [Database Engine], defining
- jobs [SQL Server Agent], operators
- alerts [SQL Server], operators
ms.assetid: 38e8488f-2669-4cea-b9c3-5f394a663678
author: stevestein
ms.author: sstein
ms.openlocfilehash: d141a2db9a69603701200bc50dcac57ef402968a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735837"
---
# <a name="operators"></a><span data-ttu-id="f936f-102">Операторы</span><span class="sxs-lookup"><span data-stu-id="f936f-102">Operators</span></span>
  <span data-ttu-id="f936f-103">Операторы — это псевдонимы людей или групп, которые могут получать электронные уведомления о завершении заданий или предупреждения.</span><span class="sxs-lookup"><span data-stu-id="f936f-103">Operators are aliases for people or groups that can receive electronic notification when jobs have completed or alerts have been raised.</span></span> <span data-ttu-id="f936f-104">Служба агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] обеспечивает уведомление администраторов через операторов.</span><span class="sxs-lookup"><span data-stu-id="f936f-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service supports the notification of administrators through operators.</span></span> <span data-ttu-id="f936f-105">Операторы включают уведомления и мониторинг возможностей агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f936f-105">Operators enable notification and monitoring capabilities of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
## <a name="operator-attributes-and-concepts"></a><span data-ttu-id="f936f-106">Атрибуты и основные понятия, касающиеся операторов</span><span class="sxs-lookup"><span data-stu-id="f936f-106">Operator Attributes and Concepts</span></span>  
 <span data-ttu-id="f936f-107">Главные атрибуты оператора:</span><span class="sxs-lookup"><span data-stu-id="f936f-107">The primary attributes of an operator are:</span></span>  
  
-   <span data-ttu-id="f936f-108">имя оператора;</span><span class="sxs-lookup"><span data-stu-id="f936f-108">Operator name</span></span>  
  
-   <span data-ttu-id="f936f-109">Контактные данные</span><span class="sxs-lookup"><span data-stu-id="f936f-109">Contact information</span></span>  
  
### <a name="naming-an-operator"></a><span data-ttu-id="f936f-110">Присвоение имени оператору</span><span class="sxs-lookup"><span data-stu-id="f936f-110">Naming an Operator</span></span>  
 <span data-ttu-id="f936f-111">Каждый оператор должен иметь имя.</span><span class="sxs-lookup"><span data-stu-id="f936f-111">Every operator must have a name.</span></span> <span data-ttu-id="f936f-112">Имена операторов должны быть уникальны в пределах экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и не могут иметь длину более **128** символов.</span><span class="sxs-lookup"><span data-stu-id="f936f-112">Operator names must be unique within the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance and can be no longer than **128** characters.</span></span>  
  
### <a name="contact-information"></a><span data-ttu-id="f936f-113">контактная информация.</span><span class="sxs-lookup"><span data-stu-id="f936f-113">Contact Information</span></span>  
 <span data-ttu-id="f936f-114">Контактная информация оператора определяет способ уведомления оператора.</span><span class="sxs-lookup"><span data-stu-id="f936f-114">An operator's contact information defines how the operator is notified.</span></span> <span data-ttu-id="f936f-115">Операторы могут получать уведомления по электронной почте, по пейджинговой связи или с помощью команды **net send** .</span><span class="sxs-lookup"><span data-stu-id="f936f-115">Operators can be notified by e-mail, pager, or through the **net send** command:</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f936f-116">Режимы отправки уведомлений с помощью пейджера и команды **net send** будут удалены из агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в следующей версии [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f936f-116">The Pager and **net send** options will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f936f-117">Старайтесь не использовать эти функции в новых разработках и предусмотрите соответствующие изменения в приложениях, которые используют их в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="f936f-117">Avoid using these features in new development work, and plan to modify applications that currently use these features.</span></span>  
  
-   <span data-ttu-id="f936f-118">**Уведомление по электронной почте.**</span><span class="sxs-lookup"><span data-stu-id="f936f-118">**E-mail notification**</span></span>  
  
     <span data-ttu-id="f936f-119">Средства уведомления по электронной почте направляют оператору почтовое сообщение.</span><span class="sxs-lookup"><span data-stu-id="f936f-119">E-mail notification sends an e-mail message to the operator.</span></span> <span data-ttu-id="f936f-120">Для уведомлений по электронной почте необходимо предоставить адрес электронной почты оператора.</span><span class="sxs-lookup"><span data-stu-id="f936f-120">For e-mail notification, you provide the e-mail address for the operator.</span></span>  
  
-   <span data-ttu-id="f936f-121">**Уведомление по пейджеру**</span><span class="sxs-lookup"><span data-stu-id="f936f-121">**Pager notification**</span></span>  
  
     <span data-ttu-id="f936f-122">Пейджинговая связь осуществляется по каналам электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f936f-122">Paging is implemented by e-mail.</span></span> <span data-ttu-id="f936f-123">Для уведомления по пейджинговой связи необходимо предоставить адрес электронной почты, по которому оператор будет получать пейджинговые сообщения.</span><span class="sxs-lookup"><span data-stu-id="f936f-123">For pager notification, you provide the e-mail address where the operator receives pager messages.</span></span> <span data-ttu-id="f936f-124">Для организации уведомлений по пейджинговой связи необходимо установить на почтовом сервере программные средства, которые будут обрабатывать входящую почту и преобразовывать ее в пейджинговые сообщения.</span><span class="sxs-lookup"><span data-stu-id="f936f-124">To set up pager notification, you must install software on the mail server that processes inbound mail and converts it to a pager message.</span></span> <span data-ttu-id="f936f-125">Программные средства могут передавать сообщения одним из способов, перечисленных ниже.</span><span class="sxs-lookup"><span data-stu-id="f936f-125">The software can take one of several approaches, including:</span></span>  
  
    -   <span data-ttu-id="f936f-126">Переадресуя почту на удаленный почтовый сервер на веб-сайте оператора пейджинговой связи.</span><span class="sxs-lookup"><span data-stu-id="f936f-126">Forwarding the mail to a remote mail server at the site of the pager provider.</span></span>  
  
         <span data-ttu-id="f936f-127">Эту услугу должен оказывать оператор пейджинговой связи, хотя необходимые программные средства обычно входят в состав локальной почтовой системы.</span><span class="sxs-lookup"><span data-stu-id="f936f-127">The pager provider must offer this service, although the software required is generally available as part of the local mail system.</span></span> <span data-ttu-id="f936f-128">Дополнительные сведения см. в документации по пейджерам.</span><span class="sxs-lookup"><span data-stu-id="f936f-128">For more information, see your pager documentation.</span></span>  
  
    -   <span data-ttu-id="f936f-129">Направляя электронную почту по каналам Интернета на почтовый сервер веб-сайта оператора пейджинговой связи.</span><span class="sxs-lookup"><span data-stu-id="f936f-129">Routing the e-mail by way of the Internet to an e-mail server at the pager provider's site.</span></span>  
  
         <span data-ttu-id="f936f-130">Данный метод — одна из разновидностей первого метода.</span><span class="sxs-lookup"><span data-stu-id="f936f-130">This is a variation on the first approach.</span></span>  
  
    -   <span data-ttu-id="f936f-131">Обрабатывая входящую электронную почту и связываясь с пейджером по коммутируемым линиям связи с помощью присоединенного модема.</span><span class="sxs-lookup"><span data-stu-id="f936f-131">Processing the inbound e-mail and dialing the pager by using an attached modem.</span></span>  
  
         <span data-ttu-id="f936f-132">Эти программные средства разрабатываются поставщиками услуг пейджинговой связи.</span><span class="sxs-lookup"><span data-stu-id="f936f-132">This software is proprietary to pager service providers.</span></span> <span data-ttu-id="f936f-133">Эти программы выступают в качестве клиентов электронной почты, которые периодически обрабатывают содержимое своих папок входящих сообщений, либо интерпретируя все или часть сведений, содержащихся в почтовых адресах как номера пейджеров, либо определяя соответствие адреса электронной почты тому или иному номеру пейджера с помощью таблиц преобразования.</span><span class="sxs-lookup"><span data-stu-id="f936f-133">The software acts as a e-mail client that periodically processes its inbox either by interpreting all or part of the e-mail address information as a pager number, or by matching the e-mail name to a pager number in a translation table.</span></span>  
  
         <span data-ttu-id="f936f-134">Если все операторы обслуживаются одним оператором услуг пейджинговой связи, можно с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] указывать все особые элементы форматирования электронной почты, необходимые для функционирования системы преобразования пейджинговых сообщений в сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f936f-134">If all of the operators share a pager provider, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to specify any special e-mail formatting that is required by the pager-to-e-mail system.</span></span> <span data-ttu-id="f936f-135">Этими особыми элементами форматирования могут быть префиксы или суффиксы, которые могут быть включены в следующие строки сообщения электронной почты:</span><span class="sxs-lookup"><span data-stu-id="f936f-135">The special formatting can be a prefix or a suffix and can be included in the following lines of the e-mail:</span></span>  
  
         <span data-ttu-id="f936f-136">**Subject**:</span><span class="sxs-lookup"><span data-stu-id="f936f-136">**Subject:**</span></span>  
  
         <span data-ttu-id="f936f-137">**Копия**:</span><span class="sxs-lookup"><span data-stu-id="f936f-137">**Cc**:</span></span>  
  
         <span data-ttu-id="f936f-138">**Кому**.</span><span class="sxs-lookup"><span data-stu-id="f936f-138">**To**:</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f936f-139">Пользователи маломощных буквенно-цифровых пейджинговых систем могут сократить объем пересылаемых текстов за счет исключения из пейджинговых уведомлений текстов об ошибках.</span><span class="sxs-lookup"><span data-stu-id="f936f-139">If you use a low-capacity alphanumeric paging system, you can shorten the text that is sent by excluding the error text from the pager notification.</span></span> <span data-ttu-id="f936f-140">Примером маломощной буквенно-цифровой пейджинговой системы может служить система, ограниченная 64 символами на страницу.</span><span class="sxs-lookup"><span data-stu-id="f936f-140">An example of a low-capacity alphanumeric paging system is one that is limited to 64 characters per page.</span></span>  
  
-   <span data-ttu-id="f936f-141">**net sendnotification**</span><span class="sxs-lookup"><span data-stu-id="f936f-141">**net sendnotification**</span></span>  
  
     <span data-ttu-id="f936f-142">Так сообщение передается оператору с помощью команды **net send** .</span><span class="sxs-lookup"><span data-stu-id="f936f-142">This sends a message to the operator by means of the **net send** command.</span></span> <span data-ttu-id="f936f-143">Чтобы передать сообщение средствами **net send**, нужно указать получателя (компьютер или пользователя) сетевого сообщения.</span><span class="sxs-lookup"><span data-stu-id="f936f-143">For **net send**, specify the recipient (computer or user) of a network message.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f936f-144">Команда **net send** использует средства Microsoft Windows Messenger.</span><span class="sxs-lookup"><span data-stu-id="f936f-144">The **net send** command uses Microsoft Windows Messenger.</span></span> <span data-ttu-id="f936f-145">Для успешной передачи предупреждений требуется, чтобы эта служба была запущена как на компьютере, на котором выполняется [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , так и на компьютере, используемом оператором.</span><span class="sxs-lookup"><span data-stu-id="f936f-145">To successfully send alerts, this service must be running on both the computer on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running and the computer that the operator uses.</span></span>  
  
## <a name="alerting-and-fail-safe-operators"></a><span data-ttu-id="f936f-146">Предупреждающие и резервные операторы</span><span class="sxs-lookup"><span data-stu-id="f936f-146">Alerting and Fail-Safe Operators</span></span>  
 <span data-ttu-id="f936f-147">Можно выбрать, какие операторы должны получать уведомления при появлении предупреждения.</span><span class="sxs-lookup"><span data-stu-id="f936f-147">You can choose which operators are to be notified in response to an alert.</span></span> <span data-ttu-id="f936f-148">Например, запланировав предупреждения, можно распределить ответственность при уведомлении операторов.</span><span class="sxs-lookup"><span data-stu-id="f936f-148">For example, you can assign rotating responsibilities for operator notification by scheduling alerts.</span></span> <span data-ttu-id="f936f-149">Например, оператор А получает уведомления о предупреждениях, появляющихся в понедельник, среду или пятницу, а оператор Б получает уведомления о предупреждениях, появляющихся во вторник, четверг или субботу.</span><span class="sxs-lookup"><span data-stu-id="f936f-149">For example, Individual A is notified of alerts that occur on Monday, Wednesday, or Friday, and Individual B is notified of alerts that occur on Tuesday, Thursday, or Saturday.</span></span>  
  
 <span data-ttu-id="f936f-150">Резервный оператор получает все предупреждения после того, как все пейджинговые уведомления нужным операторам не возымели действия.</span><span class="sxs-lookup"><span data-stu-id="f936f-150">The fail-safe operator receives an alert notification after all pager notifications to the designated operators have failed.</span></span> <span data-ttu-id="f936f-151">К примеру, если было определено три оператора для уведомления по пейджинговой связи и ни один из этих операторов недоступен, уведомление направляется резервному оператору.</span><span class="sxs-lookup"><span data-stu-id="f936f-151">For example, if you have defined three operators for pager notifications and none of the designated operators can be paged, the fail-safe operator is notified.</span></span>  
  
 <span data-ttu-id="f936f-152">Резервный оператор уведомляется в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="f936f-152">The fail-safe operator is notified when:</span></span>  
  
-   <span data-ttu-id="f936f-153">Если операторы, которые должны получать данное предупреждение, недоступны.</span><span class="sxs-lookup"><span data-stu-id="f936f-153">The operators responsible for the alert could not be paged.</span></span>  
  
     <span data-ttu-id="f936f-154">В числе причин, препятствующих доставке предупреждений основным операторам, — неверно указанные адреса пейджеров и то обстоятельство, что операторы находятся не при исполнении служебных обязанностей или не включены.</span><span class="sxs-lookup"><span data-stu-id="f936f-154">Reasons for failure to reach primary operators include incorrect pager addresses and off-duty operators.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f936f-155">Если агент не может обратиться к системным таблицам в базе данных **msdb** .</span><span class="sxs-lookup"><span data-stu-id="f936f-155">Agent cannot access system tables in the **msdb** database.</span></span>  
  
     <span data-ttu-id="f936f-156">Обязанности операторов, связанные с получением предупреждений, указаны в системной таблице **sysnotifications** .</span><span class="sxs-lookup"><span data-stu-id="f936f-156">The **sysnotifications** system table specifies operator responsibilities for alerts.</span></span>  
  
 <span data-ttu-id="f936f-157">Резервный оператор является функцией защиты.</span><span class="sxs-lookup"><span data-stu-id="f936f-157">The fail-safe operator is a security feature.</span></span> <span data-ttu-id="f936f-158">Невозможно ни удаление оператора, назначенного для выполнения резервной функции (если только эта функция не переназначена другому оператору), ни удаление самой функции резервного оператора.</span><span class="sxs-lookup"><span data-stu-id="f936f-158">You cannot delete the operator assigned to fail-safe duty without reassigning fail-safe duty to another operator, or deleting the fail-safe assignment altogether.</span></span>  
  
## <a name="notifying-an-operator"></a><span data-ttu-id="f936f-159">Уведомление оператора</span><span class="sxs-lookup"><span data-stu-id="f936f-159">Notifying an Operator</span></span>  
 <span data-ttu-id="f936f-160">Для уведомления оператора необходимо выполнить одно или несколько следующих требований.</span><span class="sxs-lookup"><span data-stu-id="f936f-160">You must set up one or more of the following in order to notify an operator:</span></span>  
  
-   <span data-ttu-id="f936f-161">Чтобы направить сообщение электронной почты с функциями компонента Database Mail, необходимо иметь доступ к почтовому серверу, поддерживающему SMTP.</span><span class="sxs-lookup"><span data-stu-id="f936f-161">To send e-mail with Database Mail functionality, you must have access to an e-mail server that supports SMTP.</span></span>  
  
-   <span data-ttu-id="f936f-162">Для передачи пейджинговых сообщений необходимо иметь программные или аппаратные средства от независимых операторов для преобразования пейджинговых сообщений в сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f936f-162">For paging, you must have third-party pager-to-e-mail software and/or hardware.</span></span>  
  
-   <span data-ttu-id="f936f-163">Для выполнения команды **net send**оператор должен быть зарегистрирован на указанном компьютере, а указанный компьютер должен принимать сообщения от Windows Messenger.</span><span class="sxs-lookup"><span data-stu-id="f936f-163">To use **net send**, the operator must be logged on to the specified computer, and the specified computer must allow messages from Windows Messenger.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="f936f-164">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="f936f-164">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f936f-165">**Задачи**</span><span class="sxs-lookup"><span data-stu-id="f936f-165">**Tasks**</span></span>|<span data-ttu-id="f936f-166">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="f936f-166">**Topic**</span></span>|  
|<span data-ttu-id="f936f-167">Задачи, связанные с созданием оператора</span><span class="sxs-lookup"><span data-stu-id="f936f-167">Tasks related to creating an operator</span></span>|[<span data-ttu-id="f936f-168">Создание оператора</span><span class="sxs-lookup"><span data-stu-id="f936f-168">Create an Operator</span></span>](create-an-operator.md)<br /><br /> [<span data-ttu-id="f936f-169">Designate a Fail-Safe Operator</span><span class="sxs-lookup"><span data-stu-id="f936f-169">Designate a Fail-Safe Operator</span></span>](designate-a-fail-safe-operator.md)|  
|<span data-ttu-id="f936f-170">Задачи, связанные с назначением предупреждений</span><span class="sxs-lookup"><span data-stu-id="f936f-170">Tasks related to assigning alerts</span></span>|[<span data-ttu-id="f936f-171">Назначение предупреждений оператору</span><span class="sxs-lookup"><span data-stu-id="f936f-171">Assign Alerts to an Operator</span></span>](assign-alerts-to-an-operator.md)<br /><br /> [<span data-ttu-id="f936f-172">Определение реакция на предупреждение (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="f936f-172">Define the Response to an Alert &#40;SQL Server Management Studio&#41;</span></span>](define-the-response-to-an-alert-sql-server-management-studio.md)<br /><br /> [<span data-ttu-id="f936f-173">sp_add_notification &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f936f-173">sp_add_notification &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql)<br /><br /> [<span data-ttu-id="f936f-174">Назначение предупреждений оператору</span><span class="sxs-lookup"><span data-stu-id="f936f-174">Assign Alerts to an Operator</span></span>](assign-alerts-to-an-operator.md)|  
  
## <a name="see-also"></a><span data-ttu-id="f936f-175">См. также:</span><span class="sxs-lookup"><span data-stu-id="f936f-175">See Also</span></span>  
 [<span data-ttu-id="f936f-176">Database Mail</span><span class="sxs-lookup"><span data-stu-id="f936f-176">Database Mail</span></span>](../../relational-databases/database-mail/database-mail.md)  
  
  
