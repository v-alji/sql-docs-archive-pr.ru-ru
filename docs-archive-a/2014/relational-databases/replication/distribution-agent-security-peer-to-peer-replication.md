---
title: Безопасность агента распространителя (одноранговая репликация) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.p2pwizard.DA.f1
ms.assetid: def6bf26-c640-4caf-ad30-05d1e649541d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 72b5a52fbb3ddc11d0ea6f2c0b26786463e08eaf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655639"
---
# <a name="distribution-agent-security-peer-to-peer-replication"></a><span data-ttu-id="7c8de-102">Безопасность агента распространителя (одноранговая репликация)</span><span class="sxs-lookup"><span data-stu-id="7c8de-102">Distribution Agent Security (Peer-to-Peer Replication)</span></span>
  <span data-ttu-id="7c8de-103">На странице **Безопасность агента распространителя** можно указать учетные записи, с которыми агент распространителя будет выполняться и устанавливать соединения с компьютерами в одноранговой топологии.</span><span class="sxs-lookup"><span data-stu-id="7c8de-103">The **Distribution Agent Security** page allows you to specify the accounts under which the Distribution Agent runs and makes connections to the computers in a peer-to-peer topology.</span></span> <span data-ttu-id="7c8de-104">Сведения о разрешениях, требуемых агентами, и об оптимальных методах защиты репликации см. в статьях [Модель безопасности агента репликации](security/replication-agent-security-model.md) и [Рекомендации по защите репликации](security/replication-security-best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="7c8de-104">For information on permissions required by agents and best practices for replication security, see [Replication Agent Security Model](security/replication-agent-security-model.md) and [Replication Security Best Practices](security/replication-security-best-practices.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7c8de-105">Если агент распространителя для подписки уже был настроен во время предыдущего запуска мастера, в этом мастере нельзя изменить используемые агентом учетные данные.</span><span class="sxs-lookup"><span data-stu-id="7c8de-105">If the Distribution Agent for a subscription has already been configured in a previous run of this wizard, you cannot change the credentials it uses in this wizard.</span></span> <span data-ttu-id="7c8de-106">При указании новых учетных данных они будут проигнорированы.</span><span class="sxs-lookup"><span data-stu-id="7c8de-106">If you specify new credentials, they are ignored.</span></span> <span data-ttu-id="7c8de-107">Чтобы изменить учетные данные, используйте диалоговое окно **Свойства подписки** .</span><span class="sxs-lookup"><span data-stu-id="7c8de-107">To change credentials, use the **Subscription Properties** dialog box.</span></span> <span data-ttu-id="7c8de-108">Дополнительные сведения см. в статье [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span><span class="sxs-lookup"><span data-stu-id="7c8de-108">For more information, see [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="7c8de-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="7c8de-109">Options</span></span>  
 <span data-ttu-id="7c8de-110">Чтобы открыть диалоговое окно**Безопасность агента распространителя**, в строке для каждого подписчика нажмите кнопку свойств ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="7c8de-110">Click the properties button (**...**) in the row for each Subscriber to access the **Distribution Agent Security** dialog box.</span></span> <span data-ttu-id="7c8de-111">Чтобы получить дополнительные сведения о разрешениях, необходимых для учетных записей, используемых агентами, нажмите кнопку **Справка** в открывшемся диалоговом окне **Безопасность агента распространителя** .</span><span class="sxs-lookup"><span data-stu-id="7c8de-111">Click **Help** on the **Distribution Agent Security** dialog box that is launched for more information on the permissions required for accounts used by the agents.</span></span>  
  
 <span data-ttu-id="7c8de-112">После ввода параметров в одном из диалоговых окон в сетке будут отображены сведения о соединении для подписчика.</span><span class="sxs-lookup"><span data-stu-id="7c8de-112">After settings have been entered in one of the dialog boxes, connection information for the Subscriber is displayed in the grid.</span></span>  
  
 <span data-ttu-id="7c8de-113">**Агент для подписчика**</span><span class="sxs-lookup"><span data-stu-id="7c8de-113">**Agent for Subscriber**</span></span>  
 <span data-ttu-id="7c8de-114">Имя каждого узла одноранговой сети.</span><span class="sxs-lookup"><span data-stu-id="7c8de-114">The name of each peer.</span></span>  
  
 <span data-ttu-id="7c8de-115">**Одноранговая база данных**</span><span class="sxs-lookup"><span data-stu-id="7c8de-115">**Peer Database**</span></span>  
 <span data-ttu-id="7c8de-116">База данных узла одноранговой сети, которая будет служить одновременно базой данных публикации и подписки.</span><span class="sxs-lookup"><span data-stu-id="7c8de-116">The database at the peer that will serve as both a publication database and subscription database.</span></span>  
  
 <span data-ttu-id="7c8de-117">**Соединение с распространителем**</span><span class="sxs-lookup"><span data-stu-id="7c8de-117">**Connection to Distributor**</span></span>  
 <span data-ttu-id="7c8de-118">Контекст, в котором устанавливается соединение с распространителем.</span><span class="sxs-lookup"><span data-stu-id="7c8de-118">The context under which the connection to the Distributor is made.</span></span> <span data-ttu-id="7c8de-119">Локальные соединения всегда осуществляются с использованием контекста учетной записи Windows, с которой запущен агент.</span><span class="sxs-lookup"><span data-stu-id="7c8de-119">Local connections are always made using the context of the Windows account under which the agent runs.</span></span> <span data-ttu-id="7c8de-120">Этот мастер создает принудительные подписки (локальное соединение является соединением с распространителем), поэтому в этом поле всегда будет отображаться одна из следующих строк: **Выполнить олицетворение '\<Domain>\\<Login\>'** или **Выполнить олицетворение '\<Computer>\\<Login\>'** .</span><span class="sxs-lookup"><span data-stu-id="7c8de-120">This wizard creates push subscriptions (the local connection is the connection to the Distributor), so this field will always display: **Impersonate '\<Domain>\\<Login\>'** or **Impersonate '\<Computer>\\<Login\>'**.</span></span>  
  
 <span data-ttu-id="7c8de-121">**Соединение с подписчиком**</span><span class="sxs-lookup"><span data-stu-id="7c8de-121">**Connection to Subscriber**</span></span>  
 <span data-ttu-id="7c8de-122">Контекст, в котором устанавливается соединение с подписчиком.</span><span class="sxs-lookup"><span data-stu-id="7c8de-122">The context under which the connection to the Subscriber is made.</span></span> <span data-ttu-id="7c8de-123">Соединение может устанавливаться в контексте учетной записи Windows, с которой работает агент, либо в контексте имени входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7c8de-123">The connection can be made using the context of the Windows account under which the agent runs or under the context of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span> <span data-ttu-id="7c8de-124">В поле отображается одна из следующих строк: **Использовать имя для входа '\<Login>'** , **Выполнить олицетворение '\<Domain>\\<Login\>'** или **Выполнить олицетворение '\<Computer>\\<Login\>'** .</span><span class="sxs-lookup"><span data-stu-id="7c8de-124">The field displays one of the following: **Use login '\<Login>'**, **Impersonate '\<Domain>\\<Login\>'** or **Impersonate '\<Computer>\\<Login\>'**.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="7c8de-125">рекомендует выполнять соединение в контексте учетной записи Windows.</span><span class="sxs-lookup"><span data-stu-id="7c8de-125">recommends that all connections be made using the context of the Windows account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c8de-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="7c8de-126">See Also</span></span>  
 <span data-ttu-id="7c8de-127">[Администрирование одноранговой топологии (программирование репликации на языке Transact-SQL)](administration/administer-a-peer-to-peer-topology-replication-transact-sql-programming.md) </span><span class="sxs-lookup"><span data-stu-id="7c8de-127">[Administer a Peer-to-Peer Topology &#40;Replication Transact-SQL Programming&#41;](administration/administer-a-peer-to-peer-topology-replication-transact-sql-programming.md) </span></span>  
 [<span data-ttu-id="7c8de-128">Peer-to-Peer Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="7c8de-128">Peer-to-Peer Transactional Replication</span></span>](transactional/peer-to-peer-transactional-replication.md)  
  
  
