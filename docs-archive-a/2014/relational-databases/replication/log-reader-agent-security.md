---
title: Защита агента чтения журнала | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.security.LRA.f1
helpviewer_keywords:
- Log Reader Agent Security dialog box
ms.assetid: d6981e74-ddb8-41b8-9ea1-56c2ece63b8a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4be41aa9135e20a334616b9cb9d76a773f8d0e9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739692"
---
# <a name="log-reader-agent-security"></a><span data-ttu-id="7d3f4-102">Безопасность агента чтения журнала</span><span class="sxs-lookup"><span data-stu-id="7d3f4-102">Log Reader Agent Security</span></span>
  <span data-ttu-id="7d3f4-103">С помощью диалогового окна **Безопасность агента чтения журнала** можно указать следующее.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-103">The **Log Reader Agent Security** dialog box allows you to specify:</span></span>  
  
-   <span data-ttu-id="7d3f4-104">Учетную запись [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, под которой запускается на распространителе агент чтения журнала.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-104">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the Log Reader Agent runs at the Distributor.</span></span> <span data-ttu-id="7d3f4-105">На учетную запись Windows можно также ссылаться как на *учетную запись процесса*, потому что процесс агента работает под этой учетной записью.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-105">The Windows account is also referred to as the *process account*, because the agent process runs under this account.</span></span>  
  
-   <span data-ttu-id="7d3f4-106">Контекст, в котором агент чтения журнала устанавливает соединения с издателем [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d3f4-106">The context under which the Log Reader Agent makes connections to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher.</span></span> <span data-ttu-id="7d3f4-107">Соединение может создаваться с помощью олицетворения учетной записи Windows или в контексте указанной учетной записи [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7d3f4-107">The connection can be made by impersonating the Windows account or under the context of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account you specify.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7d3f4-108">Агент чтения журнала устанавливает соединения с издателем, даже если издатель и распространитель находятся на одном и том же компьютере.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-108">The Log Reader Agent makes connections to the Publisher even if the Publisher and Distributor are on the same computer.</span></span> <span data-ttu-id="7d3f4-109">Агент чтения журнала также устанавливает соединения с распространителем, причем эти соединения всегда выполняются с помощью олицетворения учетной записи Windows, под которой работает агент.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-109">The Log Reader Agent also makes connections to the Distributor; these connections are always made by impersonating the Windows account under which the agent runs.</span></span>  
  
     <span data-ttu-id="7d3f4-110">Для издателей Oracle укажите контекст, в котором агент чтения журнала подключается к издателю, в диалоговом окне **Свойства издателя** (доступном из диалогового окна **Свойства распространителя** ).</span><span class="sxs-lookup"><span data-stu-id="7d3f4-110">For Oracle Publishers, specify the context under which the Log Reader Agent connects to the Publisher in the **Publisher Properties** dialog box (available from the **Distributor Properties** dialog box).</span></span> <span data-ttu-id="7d3f4-111">Дополнительные сведения см. в статье [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span><span class="sxs-lookup"><span data-stu-id="7d3f4-111">For more information, see [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span></span>  
  
 <span data-ttu-id="7d3f4-112">Все учетные записи должны быть допустимыми, а для каждой учетной записи должен быть указан правильный пароль.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-112">All accounts must be valid, with the correct password specified for each account.</span></span> <span data-ttu-id="7d3f4-113">Учетные записи и пароли могут быть проверены только после запуска агента.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-113">Accounts and passwords are not validated until an agent runs.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7d3f4-114">Параметры</span><span class="sxs-lookup"><span data-stu-id="7d3f4-114">Options</span></span>  
 <span data-ttu-id="7d3f4-115">**Учетная запись процесса**</span><span class="sxs-lookup"><span data-stu-id="7d3f4-115">**Process account**</span></span>  
 <span data-ttu-id="7d3f4-116">Введите учетную запись Windows, под которой запускается на распространителе агент чтения журнала.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-116">Enter a Windows account under which the Log Reader Agent runs at the Distributor.</span></span> <span data-ttu-id="7d3f4-117">Указанная учетная запись Windows должна быть, по меньшей мере, членом предопределенной роли базы данных **db_owner** в базе данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-117">The Windows account you specify must at minimum be a member of the **db_owner** fixed database role in the distribution database.</span></span>  
  
 <span data-ttu-id="7d3f4-118">**Пароль** и **Подтверждение пароля**</span><span class="sxs-lookup"><span data-stu-id="7d3f4-118">**Password** and **Confirm password**</span></span>  
 <span data-ttu-id="7d3f4-119">Введите пароль для учетной записи Windows.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-119">Enter the password for the Windows account.</span></span>  
  
 <span data-ttu-id="7d3f4-120">**Соединиться с издателем**</span><span class="sxs-lookup"><span data-stu-id="7d3f4-120">**Connect to the Publisher**</span></span>  
 <span data-ttu-id="7d3f4-121">Укажите, должен ли агент чтения журнала устанавливать соединения с издателем с помощью олицетворения учетной записи, указанной в текстовом поле **Учетная запись процесса** , или с помощью учетной записи [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7d3f4-121">Select whether the Log Reader Agent should make connections to the Publisher by impersonating the account specified in the **Process account** text box or by using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span> <span data-ttu-id="7d3f4-122">Если выбрано использование учетной записи [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , введите имя входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и пароль.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-122">If you select to use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account, enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and password.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="7d3f4-123">рекомендует выбирать олицетворение учетной записи Windows, а не учетную запись [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7d3f4-123">recommends that you select to impersonate the Windows account rather than using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span>  
  
 <span data-ttu-id="7d3f4-124">Учетная запись Windows или учетная запись [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , используемая для соединения, должна быть, как минимум, членом предопределенной роли базы данных **db_owner** в базе данных публикации.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-124">The Windows account or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account used for the connection must at minimum be a member of the **db_owner** fixed database role in the publication database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d3f4-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="7d3f4-125">See Also</span></span>  
 <span data-ttu-id="7d3f4-126">[Управление именами для входа и паролями при репликации](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span><span class="sxs-lookup"><span data-stu-id="7d3f4-126">[Manage Logins and Passwords in Replication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span></span>  
 <span data-ttu-id="7d3f4-127">[Replication Agent Security Model](security/replication-agent-security-model.md)  (Модель безопасности агента репликации)</span><span class="sxs-lookup"><span data-stu-id="7d3f4-127">[Replication Agent Security Model](security/replication-agent-security-model.md) </span></span>  
 <span data-ttu-id="7d3f4-128">[Обзор агентов репликации](agents/replication-agents-overview.md) </span><span class="sxs-lookup"><span data-stu-id="7d3f4-128">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 [<span data-ttu-id="7d3f4-129">Рекомендации по защите репликации</span><span class="sxs-lookup"><span data-stu-id="7d3f4-129">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
