---
title: Идентификатор и контроль доступа (репликация) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- access controls [SQL Server replication]
- security [SQL Server replication], identity and access control
- authentication [SQL Server replication]
- identity [Replication]
ms.assetid: 4da0e793-1ee4-4f69-a80b-45c6732a238d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0ae16d0908efa211a773b278fc8e86b1bf1966d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732569"
---
# <a name="identity-and-access-control-replication"></a><span data-ttu-id="3c6bb-102">Идентификатор и управление доступом (репликация)</span><span class="sxs-lookup"><span data-stu-id="3c6bb-102">Identity and Access Control (Replication)</span></span>
  <span data-ttu-id="3c6bb-103">Проверка подлинности представляет собой процесс проверки сущностью (в данном контексте, как правило, компьютером) другой сущности, также называемой *участником*(как правило, это другой компьютер или пользователь).</span><span class="sxs-lookup"><span data-stu-id="3c6bb-103">Authentication is the process by which an entity (typically a computer in this context) verifies that another entity, also called a *principal*, (typically another computer or user) is who or what it claims to be.</span></span> <span data-ttu-id="3c6bb-104">Авторизация — это процесс, с помощью которого авторизованный участник получает доступ к ресурсам, например к файлу в файловой системе или таблице в базе данных.</span><span class="sxs-lookup"><span data-stu-id="3c6bb-104">Authorization is the process by which an authenticated principal is given access to resources, such as a file in the file system, or a table in a database.</span></span>  
  
 <span data-ttu-id="3c6bb-105">Система безопасности репликации использует проверку подлинности и авторизацию для контроля доступа к реплицируемым объектам базы данных, к компьютерам и агентам, участвующим в процессе репликации.</span><span class="sxs-lookup"><span data-stu-id="3c6bb-105">Replication security uses authentication and authorization to control access to replicated database objects and to the computers and agents involved in replication processing.</span></span> <span data-ttu-id="3c6bb-106">Эти действия выполняются с помощью трех механизмов.</span><span class="sxs-lookup"><span data-stu-id="3c6bb-106">This is accomplished through three mechanisms:</span></span>  
  
-   <span data-ttu-id="3c6bb-107">Безопасность агентов. модель безопасности агента репликации позволяет точно контролировать учетные записи, в которых агенты репликации запускаются и выполняют подключения.</span><span class="sxs-lookup"><span data-stu-id="3c6bb-107">Agent security:  The replication agent security model allows fine-grained control over the accounts under which replication agents run and make connections.</span></span> <span data-ttu-id="3c6bb-108">Подробные сведения о модели безопасности агентов см. в разделе [Replication Agent Security Model](replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="3c6bb-108">For detailed information about the agent security model, see [Replication Agent Security Model](replication-agent-security-model.md).</span></span> <span data-ttu-id="3c6bb-109">Сведения о настройке имен для входа и паролей агентов см. в статье [Управление именами для входа и паролями при репликации](identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication).</span><span class="sxs-lookup"><span data-stu-id="3c6bb-109">For information about setting logins and passwords for agents, see [Manage Logins and Passwords in Replication](identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication).</span></span>  
  
-   <span data-ttu-id="3c6bb-110">Роли администрирования. Убедитесь, что для настройки, обслуживания и обработки репликации используются правильные роли сервера и базы данных.</span><span class="sxs-lookup"><span data-stu-id="3c6bb-110">Administration roles:  Ensure that the correct server and database roles are used for replication setup, maintenance, and processing.</span></span> <span data-ttu-id="3c6bb-111">Дополнительные сведения см. в статье [Security Role Requirements for Replication](security-role-requirements-for-replication.md).</span><span class="sxs-lookup"><span data-stu-id="3c6bb-111">For more information, see [Security Role Requirements for Replication](security-role-requirements-for-replication.md).</span></span>  
  
-   <span data-ttu-id="3c6bb-112">Список доступа к публикации (PAL): предоставление доступа к публикациям через список доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="3c6bb-112">The publication access list (PAL): Grant access to publications through the PAL.</span></span> <span data-ttu-id="3c6bb-113">Он работает так же, как и список управления доступом [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="3c6bb-113">The PAL functions similarly to a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows access control list.</span></span> <span data-ttu-id="3c6bb-114">Когда подписчик подключается к издателю или распространителю и запрашивает доступ к публикации, данные для проверки подлинности, переданные агентом, проверяются согласно списку доступа к публикации.</span><span class="sxs-lookup"><span data-stu-id="3c6bb-114">When a Subscriber connects to the Publisher or Distributor and requests access to a publication, the authentication information passed by the agent is checked against the PAL.</span></span> <span data-ttu-id="3c6bb-115">Дополнительные сведения и рекомендации по использованию списков доступа к публикации см. в [этой статье](secure-the-publisher.md).</span><span class="sxs-lookup"><span data-stu-id="3c6bb-115">For more information and best practices for the PAL, see [Secure the Publisher](secure-the-publisher.md).</span></span>  
  
## <a name="filtering-published-data"></a><span data-ttu-id="3c6bb-116">Фильтрование опубликованных данных</span><span class="sxs-lookup"><span data-stu-id="3c6bb-116">Filtering Published Data</span></span>  
 <span data-ttu-id="3c6bb-117">В дополнение к использованию проверки подлинности и авторизации для контроля доступа к реплицируемым данным и объектам репликация имеет два параметра для управления доступными данными на подписчике: фильтрация по столбцам и строкам.</span><span class="sxs-lookup"><span data-stu-id="3c6bb-117">In addition to using authentication and authorization to control access to replicated data and objects, replication includes two options to control what data is available at a Subscriber: column filtering and row filtering.</span></span> <span data-ttu-id="3c6bb-118">Дополнительные сведения о фильтрации см. в статье [Фильтрация опубликованных данных](../publish/filter-published-data.md).</span><span class="sxs-lookup"><span data-stu-id="3c6bb-118">For more information about filtering, see [Filter Published Data](../publish/filter-published-data.md).</span></span>  
  
 <span data-ttu-id="3c6bb-119">При определении статьи можно опубликовать только те столбцы, которые необходимы для публикации, и пропустить несущественные столбцы или столбцы, которые содержат конфиденциальные данные.</span><span class="sxs-lookup"><span data-stu-id="3c6bb-119">When you define an article, you can publish only those columns that are necessary for the publication, and omit those that are unnecessary or contain sensitive data.</span></span> <span data-ttu-id="3c6bb-120">Например, при публикации таблицы **Заказчик** из базы данных Adventure Works для продавцов на выезде можно пропустить столбец **AnnualSales** , который может быть важен лишь для администрации компании.</span><span class="sxs-lookup"><span data-stu-id="3c6bb-120">For example, when publishing the **Customer** table from the Adventure Works database to sales representatives in the field, you can omit the **AnnualSales** column, which might be relevant only to executives at the company.</span></span>  
  
 <span data-ttu-id="3c6bb-121">Фильтрация опубликованных данных позволяет ограничить доступ к данным и указать данные, доступные на подписчике.</span><span class="sxs-lookup"><span data-stu-id="3c6bb-121">Filtering published data allows you to restrict access to data and allows you to specify the data that is available at the Subscriber.</span></span> <span data-ttu-id="3c6bb-122">Например, можно отфильтровать таблицу **Заказчик** так, чтобы партнеры компании получали сведения только о тех заказчиках, для которых в столбце **ShareInfo** имеется значение «да».</span><span class="sxs-lookup"><span data-stu-id="3c6bb-122">For example, you can filter the **Customer** table so that corporate partners only receive information about those customers whose **ShareInfo** column has a value of "yes."</span></span> <span data-ttu-id="3c6bb-123">При репликации слиянием может возникать проблема безопасности, если используется параметризованный фильтр, содержащий HOST_NAME().</span><span class="sxs-lookup"><span data-stu-id="3c6bb-123">For merge replication, there are security considerations if you use a parameterized filter that includes HOST_NAME().</span></span> <span data-ttu-id="3c6bb-124">Дополнительные сведения см. в подразделе «Фильтрация с использованием HOST_NAME()» раздела [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="3c6bb-124">For more, see the section "Filtering with HOST_NAME()" in [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span></span>  

## <a name="manage-logins-and-passwords-in-replication"></a><span data-ttu-id="3c6bb-125">Управление именами входа и паролями в репликации</span><span class="sxs-lookup"><span data-stu-id="3c6bb-125">Manage Logins and Passwords in Replication</span></span>
  <span data-ttu-id="3c6bb-126">При настройке репликации укажите имена входа и пароли для агентов репликации.</span><span class="sxs-lookup"><span data-stu-id="3c6bb-126">Specify the logins and passwords for replication agents when you configure replication.</span></span> <span data-ttu-id="3c6bb-127">После настройки репликации можно изменить имена входа и пароли.</span><span class="sxs-lookup"><span data-stu-id="3c6bb-127">After configuring replication, you can change logins and passwords.</span></span> <span data-ttu-id="3c6bb-128">Дополнительные сведения см. в статье [View and Modify Replication Security Settings](view-and-modify-replication-security-settings.md).</span><span class="sxs-lookup"><span data-stu-id="3c6bb-128">For more information, see [View and Modify Replication Security Settings](view-and-modify-replication-security-settings.md).</span></span> <span data-ttu-id="3c6bb-129">Если вы измените пароль для учетной записи, которая используется агентом репликации, выполните процедуру [sp_changereplicationserverpasswords &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changereplicationserverpasswords-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3c6bb-129">If you change the password for an account used by a replication agent, execute [sp_changereplicationserverpasswords &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changereplicationserverpasswords-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c6bb-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="3c6bb-130">See Also</span></span>  
 <span data-ttu-id="3c6bb-131">[Replication Agent Security Model](replication-agent-security-model.md)  (Модель безопасности агента репликации)</span><span class="sxs-lookup"><span data-stu-id="3c6bb-131">[Replication Agent Security Model](replication-agent-security-model.md) </span></span>  
 <span data-ttu-id="3c6bb-132">[Replication Security Best Practices](replication-security-best-practices.md) </span><span class="sxs-lookup"><span data-stu-id="3c6bb-132">[Replication Security Best Practices](replication-security-best-practices.md) </span></span>  
 <span data-ttu-id="3c6bb-133">[Безопасность Репликация SQL Server](view-and-modify-replication-security-settings.md) </span><span class="sxs-lookup"><span data-stu-id="3c6bb-133">[SQL Server Replication Security](view-and-modify-replication-security-settings.md) </span></span>  
 [<span data-ttu-id="3c6bb-134">Угроза репликации и устранение уязвимостей</span><span class="sxs-lookup"><span data-stu-id="3c6bb-134">Replication Threat and Vulnerability Mitigation</span></span>](threat-and-vulnerability-mitigation-replication.md)   

  
  