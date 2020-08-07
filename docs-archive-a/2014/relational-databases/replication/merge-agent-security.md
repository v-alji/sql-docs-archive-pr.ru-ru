---
title: Защита агента слияния | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.security.MA.f1
helpviewer_keywords:
- Merge Agent Security dialog box
ms.assetid: 9b86171a-4381-4b39-869a-cdc161e7cd15
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ecbb044ca87ccfc74c5cb39a016667d15cf7a859
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734014"
---
# <a name="merge-agent-security"></a><span data-ttu-id="76cd2-102">Безопасность агента слияния</span><span class="sxs-lookup"><span data-stu-id="76cd2-102">Merge Agent Security</span></span>
  <span data-ttu-id="76cd2-103">При помощи диалогового окна **Безопасность агента слияния** можно указать учетную запись Windows [!INCLUDE[msCoName](../../includes/msconame-md.md)] , под которой необходимо запускать агент слияния.</span><span class="sxs-lookup"><span data-stu-id="76cd2-103">The **Merge Agent Security** dialog box allows you to specify the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the Merge Agent runs.</span></span> <span data-ttu-id="76cd2-104">Агент слияния запускается на распространителе для принудительных подписок и на подписчике для подписок по запросу.</span><span class="sxs-lookup"><span data-stu-id="76cd2-104">The Merge Agent runs at the Distributor for push subscriptions and at the Subscriber for pull subscriptions.</span></span> <span data-ttu-id="76cd2-105">На учетную запись Windows можно также ссылаться как на *учетную запись процесса*, потому что процесс агента работает под этой учетной записью.</span><span class="sxs-lookup"><span data-stu-id="76cd2-105">The Windows account is also referred to as the *process account*, because the agent process runs under this account.</span></span> <span data-ttu-id="76cd2-106">Дополнительные параметры в этом диалоговом окне зависят от метода доступа к нему.</span><span class="sxs-lookup"><span data-stu-id="76cd2-106">Additional options available in the dialog box depend on how you access it:</span></span>  
  
-   <span data-ttu-id="76cd2-107">Если это диалоговое окно вызывается из мастера создания подписки, можно указать контекст, при котором агент слияния устанавливает соединение с сервером подписчика (для принудительных подписок) или с серверами издателя и распространителя (для подписок по запросу).</span><span class="sxs-lookup"><span data-stu-id="76cd2-107">If the dialog box is accessed from the New Subscription Wizard, it also allows you to specify the context under which the Merge Agent makes connections to the Subscriber (for push subscriptions) or the Publisher and Distributor (for pull subscriptions).</span></span> <span data-ttu-id="76cd2-108">Соединение можно установить с помощью учетной записи Windows или в контексте указанной учетной записи [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76cd2-108">The connection can be made using the Windows account or under the context of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account you specify.</span></span>  
  
-   <span data-ttu-id="76cd2-109">Если это диалоговое окно вызывается из диалогового окна **Свойства подписки** , нажмите кнопку свойств ( **...** ) в строке **Соединение с подписчиком** или **Соединение с издателем** этого диалогового окна, чтобы определить контекст, при котором агент слияния будет устанавливать соединение.</span><span class="sxs-lookup"><span data-stu-id="76cd2-109">If the dialog box is accessed from the **Subscription Properties** dialog box, specify the context under which the Merge Agent makes connections by clicking the properties button (**...**) in the **Subscriber Connection** or **Publisher Connection** row of that dialog box.</span></span> <span data-ttu-id="76cd2-110">Дополнительные сведения о доступе к диалоговому окну **Свойства подписки** см. в статьях [Просмотр и изменение свойств принудительной подписки](view-and-modify-push-subscription-properties.md) и [Просмотр и изменение свойств подписки по запросу](view-and-modify-pull-subscription-properties.md).</span><span class="sxs-lookup"><span data-stu-id="76cd2-110">For more information about accessing the **Subscription Properties** dialog box, see [View and Modify Push Subscription Properties](view-and-modify-push-subscription-properties.md) and how to: [View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md).</span></span>  
  
 <span data-ttu-id="76cd2-111">Все учетные записи должны быть допустимыми, а для каждой учетной записи должен быть указан правильный пароль.</span><span class="sxs-lookup"><span data-stu-id="76cd2-111">All accounts must be valid, with the correct password specified for each account.</span></span> <span data-ttu-id="76cd2-112">Учетные записи и пароли могут быть проверены только после запуска агента.</span><span class="sxs-lookup"><span data-stu-id="76cd2-112">Accounts and passwords are not validated until an agent runs.</span></span>  
  
## <a name="options"></a><span data-ttu-id="76cd2-113">Параметры</span><span class="sxs-lookup"><span data-stu-id="76cd2-113">Options</span></span>  
 <span data-ttu-id="76cd2-114">**Process Account**</span><span class="sxs-lookup"><span data-stu-id="76cd2-114">**Process Account**</span></span>  
 <span data-ttu-id="76cd2-115">Введите учетную запись Windows, под которой будет запускаться агент слияния.</span><span class="sxs-lookup"><span data-stu-id="76cd2-115">Enter a Windows account under which the Merge Agent runs.</span></span>  
  
-   <span data-ttu-id="76cd2-116">Для принудительных подписок учетная запись должна удовлетворять следующим условиям:</span><span class="sxs-lookup"><span data-stu-id="76cd2-116">For push subscriptions, the account must:</span></span>  
  
    -   <span data-ttu-id="76cd2-117">Она должна быть как минимум членом предопределенной роли базы данных **db_owner** в базе данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="76cd2-117">At minimum be a member of the **db_owner** fixed database role in the distribution database.</span></span>  
  
    -   <span data-ttu-id="76cd2-118">Она должна входить в список доступа к публикации.</span><span class="sxs-lookup"><span data-stu-id="76cd2-118">Be a member of the PAL.</span></span>  
  
    -   <span data-ttu-id="76cd2-119">Она должна иметь имя входа, связанное с пользователем в базе данных публикации.</span><span class="sxs-lookup"><span data-stu-id="76cd2-119">Be a login associated with a user in the publication database.</span></span>  
  
    -   <span data-ttu-id="76cd2-120">Она должна иметь разрешение на чтение хранилища моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="76cd2-120">Have read permissions on the snapshot share.</span></span>  
  
-   <span data-ttu-id="76cd2-121">Для принудительных подписок эта учетная запись должна как минимум быть членом предопределенной роли базы данных **db_owner** в базе данных подписки.</span><span class="sxs-lookup"><span data-stu-id="76cd2-121">For pull subscriptions, the account must at minimum be a member of the **db_owner** fixed database role in the subscription database.</span></span>  
  
 <span data-ttu-id="76cd2-122">Если при установке соединений производится олицетворение учетной записи процесса, требуются дополнительные разрешения.</span><span class="sxs-lookup"><span data-stu-id="76cd2-122">Additional permissions are required if the process account is impersonated when connections are made.</span></span> <span data-ttu-id="76cd2-123">См. разделы **Соединиться с распространителем и издателем** и **Соединиться с подписчиком** , приведенные ниже.</span><span class="sxs-lookup"><span data-stu-id="76cd2-123">See the **Connect to the Publisher and Distributor** and **Connect to the Subscriber** sections below.</span></span>  
  
 <span data-ttu-id="76cd2-124">Невозможно указать**Учетную запись процесса** для подписок по запросу на [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], потому что агент слияния не работает на экземплярах [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76cd2-124">**Process Account** cannot be specified for pull subscriptions to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], because the Merge Agent does not run on instances of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span>  
  
 <span data-ttu-id="76cd2-125">**Пароль** и **Подтверждение пароля**</span><span class="sxs-lookup"><span data-stu-id="76cd2-125">**Password** and **Confirm Password**</span></span>  
 <span data-ttu-id="76cd2-126">Введите пароль для учетной записи Windows.</span><span class="sxs-lookup"><span data-stu-id="76cd2-126">Enter the password for the Windows account.</span></span>  
  
 <span data-ttu-id="76cd2-127">**Соединиться с распространителем и издателем**</span><span class="sxs-lookup"><span data-stu-id="76cd2-127">**Connect to the Publisher and Distributor**</span></span>  
 <span data-ttu-id="76cd2-128">Для принудительных подписок соединения с издателем и распространителем всегда выполняются с помощью олицетворения учетной записи, указанной в текстовом поле **Учетная запись процесса** .</span><span class="sxs-lookup"><span data-stu-id="76cd2-128">For push subscriptions, connections to the Publisher and Distributor are always made by impersonating the account specified in the **Process account** text box.</span></span>  
  
 <span data-ttu-id="76cd2-129">Для подписок по запросу укажите, должен ли агент слияния устанавливать соединения с издателем и распространителем при помощи олицетворения учетной записи, указанной в текстовом поле **Учетная запись процесса** , или при помощи учетной записи [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="76cd2-129">For pull subscriptions, select whether the Merge Agent should make connections to the Publisher and Distributor by impersonating the account specified in the **Process account** text box or by using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span> <span data-ttu-id="76cd2-130">Если выбрано использование учетной записи [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , введите имя входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и пароль.</span><span class="sxs-lookup"><span data-stu-id="76cd2-130">If you select to use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account, enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and password.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="76cd2-131">рекомендует выбирать олицетворение учетной записи Windows, а не учетную запись [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="76cd2-131">recommends that you select to impersonate the Windows account rather than using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span>  
  
 <span data-ttu-id="76cd2-132">Учетная запись Windows или учетная запись [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которые используются для соединения, должны удовлетворять следующим условиям.</span><span class="sxs-lookup"><span data-stu-id="76cd2-132">The Windows account or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account used for the connection must:</span></span>  
  
-   <span data-ttu-id="76cd2-133">Она должна входить в список доступа к публикации.</span><span class="sxs-lookup"><span data-stu-id="76cd2-133">Be a member of the PAL.</span></span>  
  
-   <span data-ttu-id="76cd2-134">Она должна иметь имя входа, связанное с пользователем в базе данных публикации.</span><span class="sxs-lookup"><span data-stu-id="76cd2-134">Be a login associated with a user in the publication database.</span></span>  
  
-   <span data-ttu-id="76cd2-135">быть именем входа, связанным с пользователем в базе данных распространителя (этот пользователь может быть гостем);</span><span class="sxs-lookup"><span data-stu-id="76cd2-135">Be a login associated with a user in the distribution database (the user can be the Guest user).</span></span>  
  
-   <span data-ttu-id="76cd2-136">Она должна иметь разрешение на чтение хранилища моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="76cd2-136">Have read permissions on the snapshot share.</span></span>  
  
 <span data-ttu-id="76cd2-137">**Соединение с подписчиком**</span><span class="sxs-lookup"><span data-stu-id="76cd2-137">**Connect to the Subscriber**</span></span>  
 <span data-ttu-id="76cd2-138">Для подписок по запросу соединения с подписчиком всегда устанавливаются с помощью олицетворения учетной записи, указанной в текстовом поле **Учетная запись процесса** .</span><span class="sxs-lookup"><span data-stu-id="76cd2-138">For pull subscriptions, connections to the Subscriber are always made by impersonating the account specified in the **Process account** text box.</span></span>  
  
 <span data-ttu-id="76cd2-139">Для принудительных подписок укажите, должен ли агент слияния устанавливать соединения с издателем и распространителем путем олицетворения учетной записи, указанной в текстовом поле **Учетная запись процесса** , или при помощи учетной записи [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="76cd2-139">For push subscriptions, select whether the Merge Agent should make connections to the Publisher and Distributor by impersonating the account specified in the **Process account** text box or by using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span> <span data-ttu-id="76cd2-140">Если выбрано использование учетной записи [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , введите имя входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и пароль.</span><span class="sxs-lookup"><span data-stu-id="76cd2-140">If you select to use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account, enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and password.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="76cd2-141">Рекомендуется использовать олицетворение учетной записи Windows вместо учетной записи [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="76cd2-141">It is recommended that you select to impersonate the Windows account rather than using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span>  
  
 <span data-ttu-id="76cd2-142">Учетная запись Windows или учетная запись [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которые используются для соединения с подписчиком, должны по меньшей мере быть членами предопределенной роли базы данных **db_owner** в базе данных подписки.</span><span class="sxs-lookup"><span data-stu-id="76cd2-142">The Windows account or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account used for the connection to the Subscriber must at minimum be a member of the **db_owner** fixed database role in the subscription database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76cd2-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="76cd2-143">See Also</span></span>  
 <span data-ttu-id="76cd2-144">[Управление именами для входа и паролями при репликации](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span><span class="sxs-lookup"><span data-stu-id="76cd2-144">[Manage Logins and Passwords in Replication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span></span>  
 <span data-ttu-id="76cd2-145">[Replication Agent Security Model](security/replication-agent-security-model.md)  (Модель безопасности агента репликации)</span><span class="sxs-lookup"><span data-stu-id="76cd2-145">[Replication Agent Security Model](security/replication-agent-security-model.md) </span></span>  
 <span data-ttu-id="76cd2-146">[Обзор агентов репликации](agents/replication-agents-overview.md) </span><span class="sxs-lookup"><span data-stu-id="76cd2-146">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 <span data-ttu-id="76cd2-147">[Replication Security Best Practices](security/replication-security-best-practices.md) </span><span class="sxs-lookup"><span data-stu-id="76cd2-147">[Replication Security Best Practices](security/replication-security-best-practices.md) </span></span>  
 [<span data-ttu-id="76cd2-148">Подписка на публикации</span><span class="sxs-lookup"><span data-stu-id="76cd2-148">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
