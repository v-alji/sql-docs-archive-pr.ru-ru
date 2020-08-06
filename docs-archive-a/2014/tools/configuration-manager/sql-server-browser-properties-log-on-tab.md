---
title: Свойства браузера SQL Server (вкладка "Вход в систему") | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: c77871ec-c2f4-4e4a-9a10-5aeb4ae70507
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0c1f7d0cfd9e9b05a2a04f3c3e9efba687522298
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727698"
---
# <a name="sql-server-browser-properties-log-on-tab"></a><span data-ttu-id="54f2f-102">Свойства браузера SQL Server (вкладка «Вход в систему»)</span><span class="sxs-lookup"><span data-stu-id="54f2f-102">SQL Server Browser Properties (Log On Tab)</span></span>
  <span data-ttu-id="54f2f-103">Программа браузера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] работает в качестве службы на сервере.</span><span class="sxs-lookup"><span data-stu-id="54f2f-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser program runs as a service on the server.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="54f2f-104">прослушивает входящие запросы к ресурсам [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и предоставляет сведения об экземплярах [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], установленных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="54f2f-104">Browser listens for incoming requests for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resources and provides information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances installed on the computer.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="54f2f-105">Браузер прослушивает UDP-порт и принимает запросы без проверки подлинности с использованием протокола разрешения [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SSRP).</span><span class="sxs-lookup"><span data-stu-id="54f2f-105">Browser listens on a UDP port and accepts unauthenticated requests using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Resolution Protocol (SSRP).</span></span>  
  
 <span data-ttu-id="54f2f-106">Изменение пароля учетной записи вступает в силу немедленно, без перезапуска службы.</span><span class="sxs-lookup"><span data-stu-id="54f2f-106">Changing the password of an account takes effect immediately without restarting the service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="54f2f-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="54f2f-107">Options</span></span>  
 <span data-ttu-id="54f2f-108">**Локальная системная учетная запись**</span><span class="sxs-lookup"><span data-stu-id="54f2f-108">**Local System account**</span></span>  
 <span data-ttu-id="54f2f-109">Запустите службу « [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , браузер» в контексте безопасности локальной системной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="54f2f-109">Run the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service in the security context of the Local System account.</span></span> <span data-ttu-id="54f2f-110">По возможности используйте учетную запись с небольшим набором прав.</span><span class="sxs-lookup"><span data-stu-id="54f2f-110">When possible, use a low-permission account instead.</span></span>  
  
 <span data-ttu-id="54f2f-111">**Эта учетная запись**</span><span class="sxs-lookup"><span data-stu-id="54f2f-111">**This account**</span></span>  
 <span data-ttu-id="54f2f-112">Укажите локальную или доменную учетную запись, использующую аутентификацию Windows.</span><span class="sxs-lookup"><span data-stu-id="54f2f-112">Specify a local or domain user account that uses Windows Authentication.</span></span> <span data-ttu-id="54f2f-113">Для служб рекомендуется использовать доменную учетную запись с минимальными правами.</span><span class="sxs-lookup"><span data-stu-id="54f2f-113">We recommend using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="54f2f-114">Дополнительные сведения о выборе учетной записи см. в разделе «Настройка учетных записей служб Windows» электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="54f2f-114">For information about selecting an account, see "Setting Up Windows Service Accounts" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="54f2f-115">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="54f2f-115">**Browse**</span></span>  
 <span data-ttu-id="54f2f-116">Выберите пользователя или встроенного субъекта безопасности.</span><span class="sxs-lookup"><span data-stu-id="54f2f-116">Browse for a user or built-in security principal.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="54f2f-117">Используйте учетную запись с минимальными правами.</span><span class="sxs-lookup"><span data-stu-id="54f2f-117">Use a low-permission account.</span></span> <span data-ttu-id="54f2f-118">Дополнительные сведения о разрешениях, необходимых для службы браузера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , см. в разделе "Безопасность" статьи [Служба обозревателя SQL Server](../../../2014/tools/configuration-manager/sql-server-browser-service.md).</span><span class="sxs-lookup"><span data-stu-id="54f2f-118">For information about the permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser Service, see the Security section of [SQL Server Browser Service](../../../2014/tools/configuration-manager/sql-server-browser-service.md).</span></span>  
  
 <span data-ttu-id="54f2f-119">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="54f2f-119">**Password**</span></span>  
 <span data-ttu-id="54f2f-120">Введите пароль субъекта безопасности.</span><span class="sxs-lookup"><span data-stu-id="54f2f-120">Enter the password of the security principal.</span></span>  
  
 <span data-ttu-id="54f2f-121">**Подтверждение пароля**</span><span class="sxs-lookup"><span data-stu-id="54f2f-121">**Confirm password**</span></span>  
 <span data-ttu-id="54f2f-122">Подтвердите пароль субъекта безопасности.</span><span class="sxs-lookup"><span data-stu-id="54f2f-122">Confirm the password of the security principal.</span></span>  
  
 <span data-ttu-id="54f2f-123">**Состояние службы**</span><span class="sxs-lookup"><span data-stu-id="54f2f-123">**Service status**</span></span>  
 <span data-ttu-id="54f2f-124">Указывает, была ли служба запущена, остановлена или отключена.</span><span class="sxs-lookup"><span data-stu-id="54f2f-124">Indicates whether this service is running, stopped, or disabled.</span></span> <span data-ttu-id="54f2f-125">**…** указывает, что ожидается изменение состояния.</span><span class="sxs-lookup"><span data-stu-id="54f2f-125">"**...**" indicates a state change is pending.</span></span>  
  
 <span data-ttu-id="54f2f-126">**Начало**</span><span class="sxs-lookup"><span data-stu-id="54f2f-126">**Start**</span></span>  
 <span data-ttu-id="54f2f-127">Запустить службу браузера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="54f2f-127">Start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
 <span data-ttu-id="54f2f-128">**Остановить**</span><span class="sxs-lookup"><span data-stu-id="54f2f-128">**Stop**</span></span>  
 <span data-ttu-id="54f2f-129">Остановить службу браузера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="54f2f-129">Stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
 <span data-ttu-id="54f2f-130">**Приостановить**</span><span class="sxs-lookup"><span data-stu-id="54f2f-130">**Pause**</span></span>  
 <span data-ttu-id="54f2f-131">Приостановить службу браузера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="54f2f-131">Pause the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
 <span data-ttu-id="54f2f-132">**Возобновить**</span><span class="sxs-lookup"><span data-stu-id="54f2f-132">**Resume**</span></span>  
 <span data-ttu-id="54f2f-133">Возобновить работу приостановленной службы браузера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="54f2f-133">Resume a paused [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54f2f-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="54f2f-134">See Also</span></span>  
 [<span data-ttu-id="54f2f-135">Служба обозревателя SQL Server</span><span class="sxs-lookup"><span data-stu-id="54f2f-135">SQL Server Browser Service</span></span>](../../../2014/tools/configuration-manager/sql-server-browser-service.md)  
  
  
