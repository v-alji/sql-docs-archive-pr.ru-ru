---
title: Настройка предупреждений для уведомления администраторов политик об ошибках политик | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, configure alerts
ms.assetid: e8e60159-d5b0-49d5-91f3-af8e9cb994c1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9eb84ced3bb6313dd5920deaf479925556f08fc4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728217"
---
# <a name="configure-alerts-to-notify-policy-administrators-of-policy-failures"></a><span data-ttu-id="4e8fe-102">Настройка предупреждений для уведомления администраторов политик об ошибках политик</span><span class="sxs-lookup"><span data-stu-id="4e8fe-102">Configure Alerts to Notify Policy Administrators of Policy Failures</span></span>
  <span data-ttu-id="4e8fe-103">Если при управлении на основе политик в одном из трех автоматизированных режимов оценки возникает нарушение политики, то сообщение об этом записывается в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="4e8fe-103">When Policy-Based Management policies are executed in one of the three automated evaluation modes, if a policy violation occurs, a message is written to the event log.</span></span> <span data-ttu-id="4e8fe-104">Для уведомления о записи этого сообщения в журнал событий можно создать предупреждение, определяющее сообщение и выполняющее действие.</span><span class="sxs-lookup"><span data-stu-id="4e8fe-104">To be notified when this message is written to the event log, you can create an alert to detect the message and perform an action.</span></span> <span data-ttu-id="4e8fe-105">Предупреждение должно определять сообщения, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="4e8fe-105">The alert should detect the messages as shown in the following table.</span></span>  
  
|<span data-ttu-id="4e8fe-106">Режим выполнения</span><span class="sxs-lookup"><span data-stu-id="4e8fe-106">Execution mode</span></span>|<span data-ttu-id="4e8fe-107">Номер сообщения</span><span class="sxs-lookup"><span data-stu-id="4e8fe-107">Message number</span></span>|  
|--------------------|--------------------|  
|<span data-ttu-id="4e8fe-108">При изменении: запретить</span><span class="sxs-lookup"><span data-stu-id="4e8fe-108">On change: prevent</span></span><br /><br /> <span data-ttu-id="4e8fe-109">(если авто)</span><span class="sxs-lookup"><span data-stu-id="4e8fe-109">(if automatic)</span></span>|<span data-ttu-id="4e8fe-110">34050</span><span class="sxs-lookup"><span data-stu-id="4e8fe-110">34050</span></span>|  
|<span data-ttu-id="4e8fe-111">При изменении: запретить</span><span class="sxs-lookup"><span data-stu-id="4e8fe-111">On change: prevent</span></span><br /><br /> <span data-ttu-id="4e8fe-112">(если по запросу)</span><span class="sxs-lookup"><span data-stu-id="4e8fe-112">(if On demand)</span></span>|<span data-ttu-id="4e8fe-113">34051</span><span class="sxs-lookup"><span data-stu-id="4e8fe-113">34051</span></span>|  
|<span data-ttu-id="4e8fe-114">По расписанию</span><span class="sxs-lookup"><span data-stu-id="4e8fe-114">On schedule</span></span>|<span data-ttu-id="4e8fe-115">34052</span><span class="sxs-lookup"><span data-stu-id="4e8fe-115">34052</span></span>|  
|<span data-ttu-id="4e8fe-116">При изменении</span><span class="sxs-lookup"><span data-stu-id="4e8fe-116">On change</span></span>|<span data-ttu-id="4e8fe-117">34053</span><span class="sxs-lookup"><span data-stu-id="4e8fe-117">34053</span></span>|  
  
 <span data-ttu-id="4e8fe-118">Сведения о настройке предупреждений в ответ на сообщения об ошибках управления на основе политик см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="4e8fe-118">To set up an alert to respond to the Policy-Based Management error messages, see the following topics:</span></span>  
  
-   [<span data-ttu-id="4e8fe-119">Создание оператора</span><span class="sxs-lookup"><span data-stu-id="4e8fe-119">Create an Operator</span></span>](../../ssms/agent/create-an-operator.md)  
  
-   [<span data-ttu-id="4e8fe-120">Создание предупреждения по номеру сообщения</span><span class="sxs-lookup"><span data-stu-id="4e8fe-120">Create an Alert Using an Error Number</span></span>](../../ssms/agent/create-an-alert-using-an-error-number.md)  
  
-   [<span data-ttu-id="4e8fe-121">Назначение предупреждений оператору</span><span class="sxs-lookup"><span data-stu-id="4e8fe-121">Assign Alerts to an Operator</span></span>](../../ssms/agent/assign-alerts-to-an-operator.md)  
  
## <a name="permissions"></a><span data-ttu-id="4e8fe-122">Разрешения</span><span class="sxs-lookup"><span data-stu-id="4e8fe-122">Permissions</span></span>  
 <span data-ttu-id="4e8fe-123">Когда политики вычисляются по запросу, они выполняются в контексте безопасности пользователя.</span><span class="sxs-lookup"><span data-stu-id="4e8fe-123">When policies are evaluated on demand, they execute in the security context of the user.</span></span> <span data-ttu-id="4e8fe-124">Для записи в журнал ошибок пользователь должен иметь разрешения ALTER TRACE или быть членом предопределенной роли сервера sysadmin.</span><span class="sxs-lookup"><span data-stu-id="4e8fe-124">To write to the error log, the user must have ALTER TRACE permissions or be a member of the sysadmin fixed server role.</span></span> <span data-ttu-id="4e8fe-125">Политики, вычисляемые пользователем, обладающим меньшими правами доступа, не регистрируются в журнале событий и не формируют предупреждений.</span><span class="sxs-lookup"><span data-stu-id="4e8fe-125">Policies that are evaluated by a user that has less privileges will not write to the event log, and will not fire an alert.</span></span>  
  
 <span data-ttu-id="4e8fe-126">Автоматизированные режимы выполнения работают от имени члена роли sysadmin.</span><span class="sxs-lookup"><span data-stu-id="4e8fe-126">The automated execution modes execute as a member of the sysadmin role.</span></span> <span data-ttu-id="4e8fe-127">Это позволяет политике регистрировать ошибки в журнале ошибок и формировать предупреждение.</span><span class="sxs-lookup"><span data-stu-id="4e8fe-127">This allows the policy to write to the error log and raise an alert.</span></span>  
  
## <a name="additional-considerations-about-alerts"></a><span data-ttu-id="4e8fe-128">Дополнительные сведения о предупреждениях</span><span class="sxs-lookup"><span data-stu-id="4e8fe-128">Additional Considerations About Alerts</span></span>  
 <span data-ttu-id="4e8fe-129">Примите во внимание следующие дополнительные сведения о предупреждениях.</span><span class="sxs-lookup"><span data-stu-id="4e8fe-129">Be aware of the following additional considerations about alerts:</span></span>  
  
-   <span data-ttu-id="4e8fe-130">Предупреждения формируются только для включенных политик.</span><span class="sxs-lookup"><span data-stu-id="4e8fe-130">Alerts are raised only for policies that are enabled.</span></span> <span data-ttu-id="4e8fe-131">Так как политики **По запросу** нельзя включить, то для них предупреждения не формируются.</span><span class="sxs-lookup"><span data-stu-id="4e8fe-131">Because **On demand** policies cannot be enabled, alerts are not raised for policies that are executed on demand.</span></span>  
  
-   <span data-ttu-id="4e8fe-132">Если действие, которое необходимо предпринять, включает отправку сообщения по электронной почте, необходимо настроить учетную запись электронной почты.</span><span class="sxs-lookup"><span data-stu-id="4e8fe-132">If the action you want to take includes sending an e-mail message, you must configure a mail account.</span></span> <span data-ttu-id="4e8fe-133">Рекомендуется использовать компонент Database Mail.</span><span class="sxs-lookup"><span data-stu-id="4e8fe-133">We recommend that you use Database Mail.</span></span> <span data-ttu-id="4e8fe-134">Дополнительные сведения о настройке компонента Database Mail см. в разделе [Создание учетной записи компонента Database Mail](../database-mail/create-a-database-mail-account.md).</span><span class="sxs-lookup"><span data-stu-id="4e8fe-134">For more information about how to set up Database Mail, see [Create a Database Mail Account](../database-mail/create-a-database-mail-account.md).</span></span>  
  
  
