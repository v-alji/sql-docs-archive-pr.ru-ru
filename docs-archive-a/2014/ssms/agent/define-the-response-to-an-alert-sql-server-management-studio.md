---
title: Определение действий в ответ на предупреждение (среда SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, alerts
- alerts [SQL Server], responding to
- responding to alerts
ms.assetid: c86ca6eb-c59f-46e9-bc32-d474e7c3b170
author: stevestein
ms.author: sstein
ms.openlocfilehash: c14e5adf43602b57697483b9ce4c2cdf20ff8e10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731353"
---
# <a name="define-the-response-to-an-alert-sql-server-management-studio"></a><span data-ttu-id="93946-102">Define the Response to an Alert (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="93946-102">Define the Response to an Alert (SQL Server Management Studio)</span></span>
  <span data-ttu-id="93946-103">В этом разделе описывается, как определить [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] реакцию на [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] предупреждения агента в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="93946-103">This topic describes how to define how [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] responds to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="93946-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="93946-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="93946-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="93946-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="93946-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="93946-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="93946-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="93946-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="93946-108">**Определение ответа на предупреждение**</span><span class="sxs-lookup"><span data-stu-id="93946-108">**To define the response to an alert, using:**</span></span>  
  
     [<span data-ttu-id="93946-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="93946-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="93946-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="93946-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="93946-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="93946-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="93946-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="93946-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="93946-113">Режимы отправки уведомлений с помощью пейджера и команды **net send** будут удалены из агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в следующей версии [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93946-113">The Pager and **net send** options will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="93946-114">Старайтесь не использовать эти функции в новых разработках и предусмотрите соответствующие изменения в приложениях, которые используют их в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="93946-114">Avoid using these features in new development work, and plan to modify applications that currently use these features.</span></span>  
  
-   <span data-ttu-id="93946-115">Обратите внимание, что для использования компонента Database Mail для отправки операторам уведомлений по электронной почте и на пейджер агент SQL Server необходимо настроить для использования компонента Database Mail.</span><span class="sxs-lookup"><span data-stu-id="93946-115">Note that SQL Server Agent must be configured to use Database Mail to send e-mail and pager notifications to operators.</span></span> <span data-ttu-id="93946-116">Дополнительные сведения см. в разделе [Назначить предупреждения для оператора](assign-alerts-to-an-operator.md).</span><span class="sxs-lookup"><span data-stu-id="93946-116">For more information, see [Assign Alerts to an Operator](assign-alerts-to-an-operator.md).</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="93946-117">обеспечивает доступный графический способ управления заданиями и рекомендуется для создания и управления инфраструктурой заданий.</span><span class="sxs-lookup"><span data-stu-id="93946-117">provides an easy, graphical way to manage jobs, and is the recommended way to create and manage the job infrastructure.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="93946-118">безопасность</span><span class="sxs-lookup"><span data-stu-id="93946-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="93946-119">Permissions</span><span class="sxs-lookup"><span data-stu-id="93946-119">Permissions</span></span>  
 <span data-ttu-id="93946-120">Только члены предопределенной роли сервера **sysadmin** могут задавать отклик на предупреждение.</span><span class="sxs-lookup"><span data-stu-id="93946-120">Only members of the **sysadmin** fixed server role can define the response to an alert.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="93946-121">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="93946-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-define-the-response-to-an-alert"></a><span data-ttu-id="93946-122">Определение ответа на предупреждение</span><span class="sxs-lookup"><span data-stu-id="93946-122">To define the response to an alert</span></span>  
  
1.  <span data-ttu-id="93946-123">В **обозревателе объектов**щелкните значок «плюс», чтобы развернуть сервер, содержащий предупреждение, для которого необходимо задать отклик.</span><span class="sxs-lookup"><span data-stu-id="93946-123">In **Object Explorer**, click the plus sign to expand the server that contains the alert on which you want to define a response.</span></span>  
  
2.  <span data-ttu-id="93946-124">Щелкните знак "плюс", чтобы развернуть **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="93946-124">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="93946-125">Чтобы развернуть папку **Предупреждения** , щелкните значок "плюс".</span><span class="sxs-lookup"><span data-stu-id="93946-125">Click the plus sign to expand the **Alerts** folder.</span></span>  
  
4.  <span data-ttu-id="93946-126">Щелкните правой кнопкой предупреждение, для которого необходимо определить отклик, и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="93946-126">Right-click the alert on which you want to define a response and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="93946-127">В диалоговом окне**Свойства предупреждения** _Alert_name_в разделе **Выбор страницы**выберите **ответ**.</span><span class="sxs-lookup"><span data-stu-id="93946-127">In the _alert_name_**alert properties** dialog box, under **Select a page**, select **Response**.</span></span>  
  
6.  <span data-ttu-id="93946-128">Выберите флажок **Выполнить задание** и из списка под пунктом **Выполнить задание** выберите задание, которое необходимо выполнить при возникновении предупреждения.</span><span class="sxs-lookup"><span data-stu-id="93946-128">Select the **Execute job** check box and, from the list below the **Execute job** check box, select a job to execute when the alert occurs.</span></span> <span data-ttu-id="93946-129">Чтобы выбрать новое задание, нажмите кнопку **Создать задание**.</span><span class="sxs-lookup"><span data-stu-id="93946-129">You can create a new job by clicking **New Job**.</span></span> <span data-ttu-id="93946-130">Для получения дополнительных сведений о заданиях нажмите кнопку **Просмотр заданий**.</span><span class="sxs-lookup"><span data-stu-id="93946-130">You can view more information about the job by clicking **View Job**.</span></span> <span data-ttu-id="93946-131">Дополнительные сведения о доступных параметрах в диалоговых окнах **Создание задания** и **Свойства задания**_Job_name_ см. в разделе [Создание задания](create-a-job.md) и [Просмотр задания](view-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="93946-131">For more information about the available options in the **New Job** and **Job Properties**_job_name_ dialog boxes, see [Create a Job](create-a-job.md) and [View a Job](view-a-job.md).</span></span>  
  
7.  <span data-ttu-id="93946-132">Выберите флажок **Уведомлять операторов** , если необходимо уведомлять операторов в момент активации предупреждения.</span><span class="sxs-lookup"><span data-stu-id="93946-132">Select the **Notify Operators** check box if you want to notify operators when the alert is activated.</span></span> <span data-ttu-id="93946-133">В списке **Список операторов**выберите один или несколько из следующих методов оповещения оператора или операторов: **Электронная почта**, **Пейджер**или **Net send**.</span><span class="sxs-lookup"><span data-stu-id="93946-133">In the **Operator list**, select one or more of the following methods for notifying the operator or operators: **E-mail**, **Pager**, or **Net Send**.</span></span> <span data-ttu-id="93946-134">Вы можете создать нового оператора, нажав кнопку **Создать оператора**.</span><span class="sxs-lookup"><span data-stu-id="93946-134">You can create a new operator by clicking **New Operator**.</span></span> <span data-ttu-id="93946-135">Вы можете просмотреть дополнительные сведения об операторе, нажав кнопку **Просмотр оператора**.</span><span class="sxs-lookup"><span data-stu-id="93946-135">You can view more information about an operator by clicking **View Operator**.</span></span> <span data-ttu-id="93946-136">Дополнительные сведения о доступных параметрах в диалоговых окнах **Создать оператора** и **Просмотр свойств оператора** см. в разделах [Create an Operator](create-an-operator.md) и [View Information About an Operator](view-information-about-an-operator.md).</span><span class="sxs-lookup"><span data-stu-id="93946-136">For more information about the available options in the **New Operator** and **View Operator Properties** dialog boxes, see [Create an Operator](create-an-operator.md) and [View Information About an Operator](view-information-about-an-operator.md).</span></span>  
  
8.  <span data-ttu-id="93946-137">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="93946-137">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="93946-138">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="93946-138">Using Transact-SQL</span></span>  
  
#### <a name="to-define-the-response-to-an-alert"></a><span data-ttu-id="93946-139">Определение ответа на предупреждение</span><span class="sxs-lookup"><span data-stu-id="93946-139">To define the response to an alert</span></span>  
  
1.  <span data-ttu-id="93946-140">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93946-140">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="93946-141">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="93946-141">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="93946-142">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="93946-142">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- adds an e-mail notification for Test Alert.  
    -- assumes that Test Alert already exists and that Fran??ois Ajenstat is a valid operator name   
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_notification  
     @alert_name = N'Test Alert',  
     @operator_name = N'Fran??ois Ajenstat',  
     @notification_method = 1 ;  
    GO  
    ```  
  
 <span data-ttu-id="93946-143">Дополнительные сведения см. в разделе [sp_add_notification &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="93946-143">For more information, see [sp_add_notification &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span></span>  
  
  
