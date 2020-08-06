---
title: Защита агента моментальных снимков | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.security.SSA.f1
helpviewer_keywords:
- Snapshot Agent Security dialog box
ms.assetid: 64e84c67-acc6-4906-98d4-3451767363fe
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 288dc294b7ace9ea5cb098c8deec53c3ae4569a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668761"
---
# <a name="snapshot-agent-security"></a><span data-ttu-id="456c6-102">Безопасность агента моментальных снимков</span><span class="sxs-lookup"><span data-stu-id="456c6-102">Snapshot Agent Security</span></span>
  <span data-ttu-id="456c6-103">Диалоговое окно **Безопасность агента моментальных снимков** позволяет указать следующее:</span><span class="sxs-lookup"><span data-stu-id="456c6-103">The **Snapshot Agent Security** dialog box allows you to specify:</span></span>  
  
-   <span data-ttu-id="456c6-104">Учетную запись [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, под которой агент моментальных снимков работает в качестве распространителя.</span><span class="sxs-lookup"><span data-stu-id="456c6-104">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the Snapshot Agent runs at the Distributor.</span></span> <span data-ttu-id="456c6-105">На учетную запись Windows можно также ссылаться как на *учетную запись процесса*, потому что процесс агента работает под этой учетной записью.</span><span class="sxs-lookup"><span data-stu-id="456c6-105">The Windows account is also referred to as the *process account*, because the agent process runs under this account.</span></span>  
  
-   <span data-ttu-id="456c6-106">Контекст, в котором агент моментальных снимков устанавливает соединения с издателем [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="456c6-106">The context under which the Snapshot Agent makes connections to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher.</span></span> <span data-ttu-id="456c6-107">Соединение может создаваться с помощью олицетворения учетной записи Windows или в контексте указанной учетной записи [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="456c6-107">The connection can be made by impersonating the Windows account or under the context of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account you specify.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="456c6-108">Агент моментальных снимков устанавливает соединение с издателем, даже если издатель и распространитель находятся на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="456c6-108">The Snapshot Agent makes connections to the Publisher even if the Publisher and Distributor are on the same computer.</span></span> <span data-ttu-id="456c6-109">Кроме того, агент моментальных снимков подключается к распространителю. Эти соединения всегда устанавливаются путем олицетворения учетной записи Windows, под которой запущен агент.</span><span class="sxs-lookup"><span data-stu-id="456c6-109">The Snapshot Agent also makes connections to the Distributor; these connections are always made by impersonating the Windows account under which the agent runs.</span></span>  
  
     <span data-ttu-id="456c6-110">Для издателей Oracle укажите в диалоговом окне **Свойства издателя** контекст, в котором агент моментальных снимков подключается к издателю (это окно находится в окне **Свойства распространителя** ).</span><span class="sxs-lookup"><span data-stu-id="456c6-110">For Oracle Publishers, specify the context under which the Snapshot Agent connects to the Publisher in the **Publisher Properties** dialog box (available from the **Distributor Properties** dialog box).</span></span> <span data-ttu-id="456c6-111">Дополнительные сведения см. в статье [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span><span class="sxs-lookup"><span data-stu-id="456c6-111">For more information, see [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span></span>  
  
 <span data-ttu-id="456c6-112">Все учетные записи должны быть допустимыми, а для каждой учетной записи должен быть указан правильный пароль.</span><span class="sxs-lookup"><span data-stu-id="456c6-112">All accounts must be valid, with the correct password specified for each account.</span></span> <span data-ttu-id="456c6-113">Учетные записи и пароли могут быть проверены только после запуска агента.</span><span class="sxs-lookup"><span data-stu-id="456c6-113">Accounts and passwords are not validated until an agent runs.</span></span>  
  
## <a name="options"></a><span data-ttu-id="456c6-114">Параметры</span><span class="sxs-lookup"><span data-stu-id="456c6-114">Options</span></span>  
 <span data-ttu-id="456c6-115">**Учетная запись процесса**</span><span class="sxs-lookup"><span data-stu-id="456c6-115">**Process account**</span></span>  
 <span data-ttu-id="456c6-116">Введите учетную запись Windows, под которой агент моментальных снимков работает в качестве распространителя.</span><span class="sxs-lookup"><span data-stu-id="456c6-116">Enter a Windows account under which the Snapshot Agent runs at the Distributor.</span></span> <span data-ttu-id="456c6-117">Необходимо, чтобы эта учетная запись Windows удовлетворяла следующим условиям:</span><span class="sxs-lookup"><span data-stu-id="456c6-117">The Windows account you specify must:</span></span>  
  
-   <span data-ttu-id="456c6-118">Она должна быть как минимум членом предопределенной роли базы данных **db_owner** в базе данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="456c6-118">At minimum be a member of the **db_owner** fixed database role in the distribution database.</span></span>  
  
-   <span data-ttu-id="456c6-119">Она должна обладать разрешениями на запись в хранилище моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="456c6-119">Have write permissions on the snapshot share.</span></span>  
  
 <span data-ttu-id="456c6-120">**Пароль** и **Подтверждение пароля**</span><span class="sxs-lookup"><span data-stu-id="456c6-120">**Password** and **Confirm password**</span></span>  
 <span data-ttu-id="456c6-121">Введите пароль для учетной записи Windows.</span><span class="sxs-lookup"><span data-stu-id="456c6-121">Enter the password for the Windows account.</span></span>  
  
 <span data-ttu-id="456c6-122">**Соединиться с издателем**</span><span class="sxs-lookup"><span data-stu-id="456c6-122">**Connect to the Publisher**</span></span>  
 <span data-ttu-id="456c6-123">Укажите, следует ли агенту моментальных снимков подключаться к издателю путем олицетворения учетной записи, указанной в текстовом поле **Учетная запись процесса** , либо через учетную запись [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="456c6-123">Select whether the Snapshot Agent should make connections to the Publisher by impersonating the account specified in the **Process account** text box or by using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span> <span data-ttu-id="456c6-124">Если выбрано использование учетной записи [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , введите имя входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и пароль.</span><span class="sxs-lookup"><span data-stu-id="456c6-124">If you select to use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account, enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and password.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="456c6-125">Рекомендуется использовать олицетворение учетной записи Windows вместо учетной записи [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="456c6-125">It is recommended that you select to impersonate the Windows account rather than using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span>  
  
 <span data-ttu-id="456c6-126">Учетная запись Windows или учетная запись [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , используемая для соединения, должна быть, как минимум, членом предопределенной роли базы данных **db_owner** в базе данных публикации.</span><span class="sxs-lookup"><span data-stu-id="456c6-126">The Windows account or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account used for the connection must at minimum be a member of the **db_owner** fixed database role in the publication database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="456c6-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="456c6-127">See Also</span></span>  
 <span data-ttu-id="456c6-128">[Управление именами для входа и паролями при репликации](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span><span class="sxs-lookup"><span data-stu-id="456c6-128">[Manage Logins and Passwords in Replication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span></span>  
 <span data-ttu-id="456c6-129">[Replication Agent Security Model](security/replication-agent-security-model.md)  (Модель безопасности агента репликации)</span><span class="sxs-lookup"><span data-stu-id="456c6-129">[Replication Agent Security Model](security/replication-agent-security-model.md) </span></span>  
 <span data-ttu-id="456c6-130">[Обзор агентов репликации](agents/replication-agents-overview.md) </span><span class="sxs-lookup"><span data-stu-id="456c6-130">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 [<span data-ttu-id="456c6-131">Рекомендации по защите репликации</span><span class="sxs-lookup"><span data-stu-id="456c6-131">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
