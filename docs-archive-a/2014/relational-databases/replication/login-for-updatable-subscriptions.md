---
title: Имя входа для обновляемых подписок | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.updatablesubscriptionslogin.f1
ms.assetid: 301ea227-0455-40ba-9009-d38f8676b325
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6a5cc9190c77f506b13ba8b5fba0e32d5a925570
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739686"
---
# <a name="login-for-updatable-subscriptions"></a><span data-ttu-id="80f52-102">Имя входа для обновляемых подписок</span><span class="sxs-lookup"><span data-stu-id="80f52-102">Login for Updatable Subscriptions</span></span>
  <span data-ttu-id="80f52-103">Если выбрано **Репликация** на странице **Обновляемые подписки** данного мастера, то требуется задать учетную запись на подписчике, под которой будут устанавливаться соединения с издателем для подписок, обновляемых немедленно.</span><span class="sxs-lookup"><span data-stu-id="80f52-103">If you selected **Replicate** on the **Updatable Subscriptions** page of this wizard, you must specify an account at the Subscriber under which connections to the Publisher are made for immediate updating subscriptions.</span></span> <span data-ttu-id="80f52-104">Соединения используются триггерами, которые запускаются на подписчике и распространяют изменения на издатель.</span><span class="sxs-lookup"><span data-stu-id="80f52-104">Connections are used by the triggers that fire at the Subscriber and propagate changes to the Publisher.</span></span> <span data-ttu-id="80f52-105">Эта учетная запись необходима, даже если выбран пункт **Ставить изменения в очередь и фиксировать по возможности** на странице **Обновляемые подписки** , так как по умолчанию мастер создания подписки настраивает обновление посредством очередей с возможностью переключения на немедленное обновление при необходимости.</span><span class="sxs-lookup"><span data-stu-id="80f52-105">This account is required even if you selected **Queue changes and commit when possible** on the **Updatable Subscriptions** page, because by default the New Subscription Wizard configures queued updating with the ability to switch to immediate updating if required.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="80f52-106">Учетная запись, заданная для соединения, должна предоставлять только разрешения для вставки, обновления и удаления данных в представлениях, которые репликация создает в базе данных публикации. Она не должна иметь никаких дополнительных разрешений.</span><span class="sxs-lookup"><span data-stu-id="80f52-106">The account specified for the connection should only be granted permission to insert, update, and delete data on the views that replication creates in the publication database; it should not be given any additional permissions.</span></span> <span data-ttu-id="80f52-107">Предоставьте разрешения на представления в базе данных публикации, которые имеют имена в виде **syncobj_** _\<HexadecimalNumber>_ , для учетной записи, настроенной на каждом подписчике.</span><span class="sxs-lookup"><span data-stu-id="80f52-107">Grant permissions on views in the publication database that are named in the form **syncobj_**_\<HexadecimalNumber>_ to the account you configured at each Subscriber.</span></span>  
  
 <span data-ttu-id="80f52-108">Для этого типа соединения имеются следующие три параметра.</span><span class="sxs-lookup"><span data-stu-id="80f52-108">There are three options available for the type of connection:</span></span>  
  
-   <span data-ttu-id="80f52-109">Уже определенный связанный или удаленный сервер.</span><span class="sxs-lookup"><span data-stu-id="80f52-109">A linked server or remote server that you have already defined.</span></span>  
  
-   <span data-ttu-id="80f52-110">Связанный сервер, создаваемый репликацией; соединение устанавливается с использованием учетных данных, заданных в данном мастере.</span><span class="sxs-lookup"><span data-stu-id="80f52-110">A linked server that replication creates; the connection is made with the credentials you specify in this wizard.</span></span>  
  
-   <span data-ttu-id="80f52-111">Связанный сервер, создаваемый репликацией; соединение устанавливается с использованием учетных данных пользователя, который вносит изменения на подписчике.</span><span class="sxs-lookup"><span data-stu-id="80f52-111">A linked server that replication creates; the connection is made with the credentials of the user making the change at the Subscriber.</span></span>  
  
 <span data-ttu-id="80f52-112">Первые два параметра можно задать в данном мастере.</span><span class="sxs-lookup"><span data-stu-id="80f52-112">The first two options can be specified in this wizard.</span></span> <span data-ttu-id="80f52-113">Последний параметр можно указать только с помощью [sp_link_publication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-link-publication-transact-sql). Укажите значение **1** для параметра **@security_mode** .</span><span class="sxs-lookup"><span data-stu-id="80f52-113">The last option can only be specified using [sp_link_publication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-link-publication-transact-sql); specify a value of **1** for the parameter **@security_mode**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="80f52-114">Параметры</span><span class="sxs-lookup"><span data-stu-id="80f52-114">Options</span></span>  
 <span data-ttu-id="80f52-115">**Создание связанного сервера, который подключается с использованием следующей проверки подлинности имени входа SQL Server:**</span><span class="sxs-lookup"><span data-stu-id="80f52-115">**Create a linked server that connects using the following SQL Server Authentication login:**</span></span>  
 <span data-ttu-id="80f52-116">Репликация создает связанный сервер с использованием учетных данных, заданных в полях **Имя входа** и **Пароль** .</span><span class="sxs-lookup"><span data-stu-id="80f52-116">Replication creates a linked server using the credentials specified in the **Login** and **Password** fields.</span></span>  
  
 <span data-ttu-id="80f52-117">**Имя входа**</span><span class="sxs-lookup"><span data-stu-id="80f52-117">**Login**</span></span>  
 <span data-ttu-id="80f52-118">Введите имя входа [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], которое обладает только разрешениями, описанными в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="80f52-118">Enter a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login that has only the permissions described in this topic.</span></span>  
  
 <span data-ttu-id="80f52-119">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="80f52-119">**Password**</span></span>  
 <span data-ttu-id="80f52-120">Введите надежный пароль для имени входа, заданного в поле **Имя входа**.</span><span class="sxs-lookup"><span data-stu-id="80f52-120">Enter a strong password for the login specified in **Login**.</span></span>  
  
 <span data-ttu-id="80f52-121">**Подтвердите пароль**</span><span class="sxs-lookup"><span data-stu-id="80f52-121">**Confirm Password**</span></span>  
 <span data-ttu-id="80f52-122">Повторно введите пароль для подтверждения того, что он был введен правильно.</span><span class="sxs-lookup"><span data-stu-id="80f52-122">Re-enter the password to confirm that it was entered correctly.</span></span>  
  
 <span data-ttu-id="80f52-123">**Использовать уже указанный связанный или удаленный сервер**</span><span class="sxs-lookup"><span data-stu-id="80f52-123">**Use a linked server or remote server that you have already defined.**</span></span>  
 <span data-ttu-id="80f52-124">Для данного параметра необходим уже определенный связанный или удаленный сервер.</span><span class="sxs-lookup"><span data-stu-id="80f52-124">This option requires a linked server or remote server that you have already defined.</span></span> <span data-ttu-id="80f52-125">Дополнительные сведения см. в статьях [Linked Servers (Database Engine)](../linked-servers/linked-servers-database-engine.md) (Связанные серверы (ядро СУБД)) и [Remote Servers](../../database-engine/configure-windows/remote-servers.md) (Удаленные серверы).</span><span class="sxs-lookup"><span data-stu-id="80f52-125">For more information, see [Linked Servers &#40;Database Engine&#41;](../linked-servers/linked-servers-database-engine.md) and [Remote Servers](../../database-engine/configure-windows/remote-servers.md).</span></span> <span data-ttu-id="80f52-126">Убедитесь в том, что имя входа, используемое для связанного сервера или удаленного сервера, имеет надежный пароль и обладает только разрешениями, описанными в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="80f52-126">Ensure that the login used for the linked server or remote server has a strong password and has only the permissions described in this topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80f52-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="80f52-127">See Also</span></span>  
 <span data-ttu-id="80f52-128">[Create an Updatable Subscription to a Transactional Publication](publish/create-an-updatable-subscription-to-a-transactional-publication.md) </span><span class="sxs-lookup"><span data-stu-id="80f52-128">[Create an Updatable Subscription to a Transactional Publication](publish/create-an-updatable-subscription-to-a-transactional-publication.md) </span></span>  
 <span data-ttu-id="80f52-129">[Просмотр и изменение параметров безопасности репликации](security/view-and-modify-replication-security-settings.md) </span><span class="sxs-lookup"><span data-stu-id="80f52-129">[View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md) </span></span>  
 <span data-ttu-id="80f52-130">[Updatable Subscriptions for Transactional Replication](transactional/updatable-subscriptions-for-transactional-replication.md) </span><span class="sxs-lookup"><span data-stu-id="80f52-130">[Updatable Subscriptions for Transactional Replication](transactional/updatable-subscriptions-for-transactional-replication.md) </span></span>  
 [<span data-ttu-id="80f52-131">Подписка на публикации</span><span class="sxs-lookup"><span data-stu-id="80f52-131">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
