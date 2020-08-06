---
title: Защита агента чтения очереди | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.security.QRA.f1
helpviewer_keywords:
- Queue Reader Agent Security dialog box
ms.assetid: 77938da0-2afd-4455-8826-f4a6a9440cb3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 22a5e5751184b626ab1af86f01782a42028b5ced
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667692"
---
# <a name="queue-reader-agent-security"></a><span data-ttu-id="8214c-102">Безопасность агента чтения очереди</span><span class="sxs-lookup"><span data-stu-id="8214c-102">Queue Reader Agent Security</span></span>
  <span data-ttu-id="8214c-103">Диалоговое окно **Безопасность агента чтения очереди** позволяет указать учетную запись [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, с которой агент чтения очереди запускается и создает локальные соединения с распространителем.</span><span class="sxs-lookup"><span data-stu-id="8214c-103">The **Queue Reader Agent Security** dialog box allows you to specify the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the Queue Reader Agent runs and makes local connections to the Distributor.</span></span> <span data-ttu-id="8214c-104">Агент устанавливает соединение с издателем, используя учетную запись, указанную в диалоговом окне **Свойства издателя** (доступном из диалогового окна **Свойства распространителя** ). Агент устанавливает соединение с подписчиком, используя тот же контекст, что и агент распространителя для подписки.</span><span class="sxs-lookup"><span data-stu-id="8214c-104">The agent connects to the Publisher using the account specified in the **Publisher Properties** dialog box (available from the **Distributor Properties** dialog box); the agent connects to the Subscriber using the same context as the Distribution Agent for the subscription.</span></span> <span data-ttu-id="8214c-105">Дополнительные сведения см. в статье [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span><span class="sxs-lookup"><span data-stu-id="8214c-105">For more information, see [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span></span>  
  
 <span data-ttu-id="8214c-106">Учетная запись должна быть действительной, а указанный для нее пароль — верным.</span><span class="sxs-lookup"><span data-stu-id="8214c-106">The account must be valid with the correct password specified.</span></span> <span data-ttu-id="8214c-107">Учетные записи и пароли могут быть проверены только после запуска агента.</span><span class="sxs-lookup"><span data-stu-id="8214c-107">Accounts and passwords are not validated until an agent runs.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8214c-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="8214c-108">Options</span></span>  
 <span data-ttu-id="8214c-109">**Учетная запись процесса**</span><span class="sxs-lookup"><span data-stu-id="8214c-109">**Process account**</span></span>  
 <span data-ttu-id="8214c-110">Введите учетную запись Windows, с которой агент чтения очереди работает на распространителе.</span><span class="sxs-lookup"><span data-stu-id="8214c-110">Enter a Windows account under which the Queue Reader Agent runs at the Distributor.</span></span> <span data-ttu-id="8214c-111">Указанная учетная запись Windows должна быть, по меньшей мере, членом предопределенной роли базы данных **db_owner** в базе данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="8214c-111">The Windows account you specify must at minimum be a member of the **db_owner** fixed database role in the distribution database.</span></span>  
  
 <span data-ttu-id="8214c-112">**Пароль** и **Подтверждение пароля**</span><span class="sxs-lookup"><span data-stu-id="8214c-112">**Password** and **Confirm password**</span></span>  
 <span data-ttu-id="8214c-113">Введите пароль для учетной записи Windows.</span><span class="sxs-lookup"><span data-stu-id="8214c-113">Enter the password for the Windows account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8214c-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="8214c-114">See Also</span></span>  
 <span data-ttu-id="8214c-115">[Управление именами для входа и паролями при репликации](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span><span class="sxs-lookup"><span data-stu-id="8214c-115">[Manage Logins and Passwords in Replication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span></span>  
 <span data-ttu-id="8214c-116">[Replication Agent Security Model](security/replication-agent-security-model.md)  (Модель безопасности агента репликации)</span><span class="sxs-lookup"><span data-stu-id="8214c-116">[Replication Agent Security Model](security/replication-agent-security-model.md) </span></span>  
 <span data-ttu-id="8214c-117">[Обзор агентов репликации](agents/replication-agents-overview.md) </span><span class="sxs-lookup"><span data-stu-id="8214c-117">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 [<span data-ttu-id="8214c-118">Рекомендации по защите репликации</span><span class="sxs-lookup"><span data-stu-id="8214c-118">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
