---
title: Свойства агента SQL Server (страница "Система предупреждений") | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.alert.f1
ms.assetid: 3e6d3bfd-20ee-4593-86cc-f65b1c08c69d
author: stevestein
ms.author: sstein
ms.openlocfilehash: ff203be21efbd99b90f02261cfe94dd49bd0d849
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667529"
---
# <a name="sql-server-agent-properties-alert-system-page"></a><span data-ttu-id="5d77c-102">Свойства агента SQL Server (страница «Система предупреждений»)</span><span class="sxs-lookup"><span data-stu-id="5d77c-102">SQL Server Agent Properties (Alert System Page)</span></span>
  <span data-ttu-id="5d77c-103">Эта страница используется для просмотра и изменения параметров сообщений, отправляемых предупреждениями агента [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d77c-103">Use this page to view and modify the settings for messages sent by [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5d77c-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="5d77c-104">Options</span></span>  
 <span data-ttu-id="5d77c-105">**Почтовый сеанс**</span><span class="sxs-lookup"><span data-stu-id="5d77c-105">**Mail session**</span></span>  
 <span data-ttu-id="5d77c-106">Параметры в данном разделе предназначены для настройки почты агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5d77c-106">The options in this section configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Mail.</span></span>  
  
 <span data-ttu-id="5d77c-107">**Включить почтовый профиль**</span><span class="sxs-lookup"><span data-stu-id="5d77c-107">**Enable mail profile**</span></span>  
 <span data-ttu-id="5d77c-108">Включает почту агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5d77c-108">Enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Mail.</span></span> <span data-ttu-id="5d77c-109">По умолчанию почта агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не включена.</span><span class="sxs-lookup"><span data-stu-id="5d77c-109">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Mail is not enabled.</span></span>  
  
 <span data-ttu-id="5d77c-110">**Почтовая система**</span><span class="sxs-lookup"><span data-stu-id="5d77c-110">**Mail System**</span></span>  
 <span data-ttu-id="5d77c-111">Устанавливает почтовую систему для использования агентом [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5d77c-111">Sets the mail system for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to use.</span></span> <span data-ttu-id="5d77c-112">Database Mail</span><span class="sxs-lookup"><span data-stu-id="5d77c-112">Database Mail</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5d77c-113">После изменений системы электронной почты необходимо перезапустить службу агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , чтобы эти изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="5d77c-113">After changing the e-mail system, you must restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service for the change to take effect.</span></span>  
  
 <span data-ttu-id="5d77c-114">**Профиль электронной почты**</span><span class="sxs-lookup"><span data-stu-id="5d77c-114">**Mail Profile**</span></span>  
 <span data-ttu-id="5d77c-115">Устанавливает профиль для использования агентом [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5d77c-115">Sets the profile for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to use.</span></span> <span data-ttu-id="5d77c-116">Можно также выбрать **\<new Database Mail profile...>** , чтобы создать новый профиль.</span><span class="sxs-lookup"><span data-stu-id="5d77c-116">You may also select **\<new Database Mail profile...>** to create a new profile.</span></span>  
  
 <span data-ttu-id="5d77c-117">**Электронные сообщения на пейджер**</span><span class="sxs-lookup"><span data-stu-id="5d77c-117">**Pager e-mails**</span></span>  
 <span data-ttu-id="5d77c-118">Параметры в этом разделе позволяют настроить электронные сообщения, отправляемые на адреса пейджеров для работы с вашей пейджинговой системой.</span><span class="sxs-lookup"><span data-stu-id="5d77c-118">The options in this section allow you to configure e-mail messages sent to pager addresses to work with your paging system.</span></span>  
  
 <span data-ttu-id="5d77c-119">**Форматирование адреса для электронных сообщений на пейджер**</span><span class="sxs-lookup"><span data-stu-id="5d77c-119">**Address formatting for pager e-mails**</span></span>  
 <span data-ttu-id="5d77c-120">Данный раздел позволяет задать формат адресов и темы, включаемые в электронные сообщения на пейджер.</span><span class="sxs-lookup"><span data-stu-id="5d77c-120">This section allows you to specify the format of the addresses and the subject line included in pager e-mails.</span></span>  
  
 <span data-ttu-id="5d77c-121">**Поле «Кому»**</span><span class="sxs-lookup"><span data-stu-id="5d77c-121">**To line**</span></span>  
 <span data-ttu-id="5d77c-122">Задает параметры для строки сообщения **Кому** .</span><span class="sxs-lookup"><span data-stu-id="5d77c-122">Specifies the options for the **To** line of the message</span></span>  
  
 <span data-ttu-id="5d77c-123">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="5d77c-123">**Prefix**</span></span>  
 <span data-ttu-id="5d77c-124">Введите любой фиксированный текст, требуемый системой в начале строки **Кому** сообщений, отправляемых на пейджер.</span><span class="sxs-lookup"><span data-stu-id="5d77c-124">Type any fixed text that your system requires at the beginning of the **To** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="5d77c-125">**Пейджер**</span><span class="sxs-lookup"><span data-stu-id="5d77c-125">**Pager**</span></span>  
 <span data-ttu-id="5d77c-126">Содержит адрес электронной почты для сообщения между префиксом и суффиксом.</span><span class="sxs-lookup"><span data-stu-id="5d77c-126">Includes the e-mail address for the message between the prefix and the suffix.</span></span>  
  
 <span data-ttu-id="5d77c-127">**Суффикс**</span><span class="sxs-lookup"><span data-stu-id="5d77c-127">**Suffix**</span></span>  
 <span data-ttu-id="5d77c-128">Введите любой фиксированный текст, требуемый пейджинговой системой в конце строки **Кому** сообщений, отправляемых на пейджер.</span><span class="sxs-lookup"><span data-stu-id="5d77c-128">Type any fixed text that your paging system requires at the end of the **To** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="5d77c-129">**Поле «Копия»**</span><span class="sxs-lookup"><span data-stu-id="5d77c-129">**Cc line**</span></span>  
 <span data-ttu-id="5d77c-130">Задает параметры для строки сообщения **Копия** .</span><span class="sxs-lookup"><span data-stu-id="5d77c-130">Specifies options for the **Cc** line of the message.</span></span>  
  
 <span data-ttu-id="5d77c-131">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="5d77c-131">**Prefix**</span></span>  
 <span data-ttu-id="5d77c-132">Введите любой фиксированный текст, требуемый системой в начале строки **Копия** сообщений, отправляемых на пейджер.</span><span class="sxs-lookup"><span data-stu-id="5d77c-132">Type any fixed text that your system requires at the beginning of the **Cc** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="5d77c-133">**Пейджер**</span><span class="sxs-lookup"><span data-stu-id="5d77c-133">**Pager**</span></span>  
 <span data-ttu-id="5d77c-134">Содержит адрес электронной почты для сообщения между префиксом и суффиксом.</span><span class="sxs-lookup"><span data-stu-id="5d77c-134">Includes the e-mail address for the message between the prefix and the suffix.</span></span>  
  
 <span data-ttu-id="5d77c-135">**Суффикс**</span><span class="sxs-lookup"><span data-stu-id="5d77c-135">**Suffix**</span></span>  
 <span data-ttu-id="5d77c-136">Введите любой фиксированный текст, требуемый пейджинговой системой в конце строки **Копия** сообщений, отправляемых на пейджер.</span><span class="sxs-lookup"><span data-stu-id="5d77c-136">Type any fixed text that your paging system requires at the end of the **Cc** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="5d77c-137">**Тема**</span><span class="sxs-lookup"><span data-stu-id="5d77c-137">**Subject**</span></span>  
 <span data-ttu-id="5d77c-138">Задает параметры для строки темы сообщения.</span><span class="sxs-lookup"><span data-stu-id="5d77c-138">Specifies the options for the subject of the message.</span></span>  
  
 <span data-ttu-id="5d77c-139">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="5d77c-139">**Prefix**</span></span>  
 <span data-ttu-id="5d77c-140">Введите любой фиксированный текст, требуемый системой в начале строки **Тема** сообщений, отправляемых на пейджер.</span><span class="sxs-lookup"><span data-stu-id="5d77c-140">Type any fixed text that your paging system requires at the beginning of the **Subject** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="5d77c-141">**Суффикс**</span><span class="sxs-lookup"><span data-stu-id="5d77c-141">**Suffix**</span></span>  
 <span data-ttu-id="5d77c-142">Введите любой фиксированный текст, требуемый системой в конце строки **Тема** сообщений, отправляемых на пейджер.</span><span class="sxs-lookup"><span data-stu-id="5d77c-142">Type any fixed text that your paging system requires at the end of the **Subject** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="5d77c-143">**Включить тело электронного письма в сообщение уведомления**</span><span class="sxs-lookup"><span data-stu-id="5d77c-143">**Include body of e-mail in notification message**</span></span>  
 <span data-ttu-id="5d77c-144">Включает тело электронного письма в сообщение, отправляемое на пейджер.</span><span class="sxs-lookup"><span data-stu-id="5d77c-144">Includes the body of the e-mail message in the message sent to the pager.</span></span>  
  
 <span data-ttu-id="5d77c-145">**Резервный оператор**</span><span class="sxs-lookup"><span data-stu-id="5d77c-145">**Fail-safe operator**</span></span>  
 <span data-ttu-id="5d77c-146">Данный раздел позволяет задать параметры для резервного оператора.</span><span class="sxs-lookup"><span data-stu-id="5d77c-146">This section allows you to specify the options for the fail-safe operator.</span></span>  
  
 <span data-ttu-id="5d77c-147">**Включить резервный оператор**</span><span class="sxs-lookup"><span data-stu-id="5d77c-147">**Enable fail-safe operator**</span></span>  
 <span data-ttu-id="5d77c-148">Задает резервный оператор.</span><span class="sxs-lookup"><span data-stu-id="5d77c-148">Specifies a fail safe operator.</span></span>  
  
 <span data-ttu-id="5d77c-149">**Оператор**</span><span class="sxs-lookup"><span data-stu-id="5d77c-149">**Operator**</span></span>  
 <span data-ttu-id="5d77c-150">Устанавливает имя оператора для получения уведомлений об отказах.</span><span class="sxs-lookup"><span data-stu-id="5d77c-150">Sets the name of the operator to receive fail-safe notifications.</span></span>  
  
 <span data-ttu-id="5d77c-151">**Уведомлять с помощью**</span><span class="sxs-lookup"><span data-stu-id="5d77c-151">**Notify using**</span></span>  
 <span data-ttu-id="5d77c-152">Устанавливает метод для использования при уведомлении резервного оператора.</span><span class="sxs-lookup"><span data-stu-id="5d77c-152">Sets the method to use for notifying the fail-safe operator.</span></span>  
  
 <span data-ttu-id="5d77c-153">**Замена токенов**</span><span class="sxs-lookup"><span data-stu-id="5d77c-153">**Token Replacement**</span></span>  
 <span data-ttu-id="5d77c-154">Данный раздел позволяет включить токены шагов заданий, которые могут использоваться в заданиях, выполняемых предупреждениями агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5d77c-154">This section allows you to enable job step tokens that can be used in jobs run by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts.</span></span> <span data-ttu-id="5d77c-155">Дополнительные сведения о токенах шагов заданий см. в разделе [Использование токенов в шагах задания](use-tokens-in-job-steps.md).</span><span class="sxs-lookup"><span data-stu-id="5d77c-155">For more information about job step tokens, see [Use Tokens in Job Steps](use-tokens-in-job-steps.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5d77c-156">Все пользователи Windows с разрешением на запись в журнал событий Windows могут получить доступ к шагам заданий, которые активированы предупреждениями агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5d77c-156">Any Windows user with write permissions on the Windows Event Log may be able to access job steps that are activated by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts.</span></span> <span data-ttu-id="5d77c-157">Чтобы избежать этого нарушения безопасности, в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] токены агента, которые могут использоваться в заданиях, активированных предупреждениями, по умолчанию отключены.</span><span class="sxs-lookup"><span data-stu-id="5d77c-157">To avoid this security risk, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent tokens that can be used in jobs activated by alerts are disabled by default.</span></span> <span data-ttu-id="5d77c-158">К этим токенам относятся: **$(A-DBN)** , **$(A-SVR)** , **$(A-ERR)** , **$(A-SEV)** и **$(A-MSG)** .</span><span class="sxs-lookup"><span data-stu-id="5d77c-158">These tokens are: **$(A-DBN)**, **$(A-SVR)**, **$(A-ERR)**, **$(A-SEV)**, and **$(A-MSG)**.</span></span>  
>   
>  <span data-ttu-id="5d77c-159">При необходимости использовать эти токены перед их включением убедитесь, что только члены доверенных групп безопасности Windows, таких как группа «Администраторы», обладают разрешением на работу с журналом событий компьютера, на котором находится [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5d77c-159">If you need to use these tokens, ensure that only members of trusted Windows security groups, such as the Administrators group, have write permissions on the Event Log of the computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resides before enabling them.</span></span>  
  
 <span data-ttu-id="5d77c-160">**Заменить токенами всех ответов заданий на предупреждения**</span><span class="sxs-lookup"><span data-stu-id="5d77c-160">**Replace tokens for all job responses to alerts**</span></span>  
 <span data-ttu-id="5d77c-161">Установите этот флажок, чтобы включить замену токенов для заданий, активизированных предупреждениями [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5d77c-161">Select this check box to enable token replacement for jobs that are activated by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alerts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d77c-162">См. также:</span><span class="sxs-lookup"><span data-stu-id="5d77c-162">See Also</span></span>  
 <span data-ttu-id="5d77c-163">[Операторы](operators.md) </span><span class="sxs-lookup"><span data-stu-id="5d77c-163">[Operators](operators.md) </span></span>  
 <span data-ttu-id="5d77c-164">[Настройка агент SQL Server почты для использования Database Mail](../../relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail.md) </span><span class="sxs-lookup"><span data-stu-id="5d77c-164">[Configure SQL Server Agent Mail to Use Database Mail](../../relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail.md) </span></span>  
 [<span data-ttu-id="5d77c-165">Database Mail</span><span class="sxs-lookup"><span data-stu-id="5d77c-165">Database Mail</span></span>](../../relational-databases/database-mail/database-mail.md)  
  
  
