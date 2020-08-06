---
title: Средство запуска управляющей программы полнотекстовой фильтрации SQL (вкладка "Вход") | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 13e260f9-a75f-430b-88a3-959ddcead8fe
author: stevestein
ms.author: sstein
ms.openlocfilehash: cb3f23907e96214929617bf2923e46148c0ab1f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667982"
---
# <a name="sql-full-text-filter-daemon-launcher-log-on-tab"></a><span data-ttu-id="02651-102">Средство запуска управляющей программы полнотекстовой фильтрации SQL (вкладка «Вход»)</span><span class="sxs-lookup"><span data-stu-id="02651-102">SQL Full-text Filter Daemon Launcher (Log On Tab)</span></span>
  <span data-ttu-id="02651-103">Начиная с версии [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], в полнотекстовом поиске [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] используется средство запуска управляющей программы полнотекстовой фильтрации SQL (средство запуска FDHOST).</span><span class="sxs-lookup"><span data-stu-id="02651-103">Beginning in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], the SQL Full-text Filter Daemon Launcher (FDHOST Launcher) service is used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] full-text search.</span></span> <span data-ttu-id="02651-104">Эта служба должна быть запущена при использовании полнотекстового поиска.</span><span class="sxs-lookup"><span data-stu-id="02651-104">This service must be running if you use full-text search.</span></span> <span data-ttu-id="02651-105">Сведения о хост-процессах управляющей программы фильтрации см. в разделе «Архитектура компонента Full-Text Search» электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="02651-105">For information about the filter daemon host processes, see "Full-Text Search Architecture" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="02651-106">Используйте вкладку **Вход** в диалоговом окне **Свойства запуска управляющей программы полнотекстовой фильтрации (SQL)** , чтобы указать учетную запись, используемую полнотекстовой службой [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , изменить пароль учетной записи и запустить или остановить службу.</span><span class="sxs-lookup"><span data-stu-id="02651-106">Use the **Log On** tab of the **SQL Full-text Filter Daemon Launcher  Properties** dialog box to specify the account used by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] full-text service, to change the password of an account, and to start and stop the service.</span></span> <span data-ttu-id="02651-107">Изменение пароля учетной записи вступает в силу после перезапуска службы.</span><span class="sxs-lookup"><span data-stu-id="02651-107">Changing the password of an account takes affect after restarting the service.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="02651-108">При изменении имени учетной записи, используемой службой в кластеризованном экземпляре, новая учетная запись должна быть членом группы домена, заданной во время установки службы, или же текущий пользователь должен иметь разрешение на добавление членов в эту группу.</span><span class="sxs-lookup"><span data-stu-id="02651-108">When changing the account name used by a service on a clustered instance, either the new account must be a member of the domain group specified during setup for the service, or you must have permission to add members to that group.</span></span> <span data-ttu-id="02651-109">Если нет разрешения на изменение состава группы, свяжитесь с администратором домена.</span><span class="sxs-lookup"><span data-stu-id="02651-109">If you do not have permission to modify group membership, contact the domain administrator.</span></span>  
>   
>  <span data-ttu-id="02651-110">Дополнительные сведения о выборе учетной записи для выполнения службы приводятся в разделе «Настройка учетных записей служб Windows» электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="02651-110">For more information about selecting an account to run the service, see "Setting Up Windows Service Accounts" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="options"></a><span data-ttu-id="02651-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="02651-111">Options</span></span>  
 <span data-ttu-id="02651-112">**Встроенная учетная запись**</span><span class="sxs-lookup"><span data-stu-id="02651-112">**Built-in account**</span></span>  
 <span data-ttu-id="02651-113">**Локальная система**</span><span class="sxs-lookup"><span data-stu-id="02651-113">**Local System**</span></span>  
 <span data-ttu-id="02651-114">Укажите учетную запись локальной системы.</span><span class="sxs-lookup"><span data-stu-id="02651-114">Specify the local system account.</span></span> <span data-ttu-id="02651-115">Для этой учетной записи пароль не нужен.</span><span class="sxs-lookup"><span data-stu-id="02651-115">This account does not require a password.</span></span> <span data-ttu-id="02651-116">Однако локальная системная учетная запись может препятствовать взаимодействию служб с другими серверами, в зависимости от прав доступа, предоставленных этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="02651-116">However, the local system account may prevent the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="02651-117">**Локальная служба.**</span><span class="sxs-lookup"><span data-stu-id="02651-117">**Local Service**</span></span>  
 <span data-ttu-id="02651-118">Укажите учетную запись локальной службы.</span><span class="sxs-lookup"><span data-stu-id="02651-118">Specify the local service account.</span></span> <span data-ttu-id="02651-119">Для этой учетной записи пароль не нужен.</span><span class="sxs-lookup"><span data-stu-id="02651-119">This account does not require a password.</span></span> <span data-ttu-id="02651-120">Однако учетная запись локальной службы может препятствовать взаимодействию служб с другими серверами, в зависимости от прав доступа, предоставленных этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="02651-120">However, the local service account may prevent the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="02651-121">**Сетевая служба.**</span><span class="sxs-lookup"><span data-stu-id="02651-121">**Network Service**</span></span>  
 <span data-ttu-id="02651-122">Не рекомендуется использовать учетную запись «Сетевая служба» для служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="02651-122">We recommend that you do not use the Network Service account for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent services.</span></span> <span data-ttu-id="02651-123">Для этих служб больше подходят учетные записи «Локальный пользователь» или «Пользователь домена».</span><span class="sxs-lookup"><span data-stu-id="02651-123">Local User or Domain User accounts are more appropriate for these services.</span></span>  
  
 <span data-ttu-id="02651-124">**Эта учетная запись**</span><span class="sxs-lookup"><span data-stu-id="02651-124">**This account**</span></span>  
 <span data-ttu-id="02651-125">Укажите локальную или доменную учетную запись, использующую аутентификацию Windows.</span><span class="sxs-lookup"><span data-stu-id="02651-125">Specify a local or domain user account that uses Windows Authentication.</span></span> <span data-ttu-id="02651-126">Для служб рекомендуется использовать доменную учетную запись с минимальными правами.</span><span class="sxs-lookup"><span data-stu-id="02651-126">We recommend that you use a domain user account that has minimal rights for services.</span></span>  
  
 <span data-ttu-id="02651-127">**Account Name** (Имя учетной записи)</span><span class="sxs-lookup"><span data-stu-id="02651-127">**Account Name**</span></span>  
 <span data-ttu-id="02651-128">Укажите имя локальной или доменной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="02651-128">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="02651-129">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="02651-129">**Password**</span></span>  
 <span data-ttu-id="02651-130">Введите пароль для учетной записи.</span><span class="sxs-lookup"><span data-stu-id="02651-130">Type the password of the account.</span></span>  
  
 <span data-ttu-id="02651-131">**Подтверждение пароля**</span><span class="sxs-lookup"><span data-stu-id="02651-131">**Confirm password**</span></span>  
 <span data-ttu-id="02651-132">Введите пароль для учетной записи еще раз.</span><span class="sxs-lookup"><span data-stu-id="02651-132">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="02651-133">**Начало**</span><span class="sxs-lookup"><span data-stu-id="02651-133">**Start**</span></span>  
 <span data-ttu-id="02651-134">Запускает службу.</span><span class="sxs-lookup"><span data-stu-id="02651-134">Start the service.</span></span>  
  
 <span data-ttu-id="02651-135">**Остановить**</span><span class="sxs-lookup"><span data-stu-id="02651-135">**Stop**</span></span>  
 <span data-ttu-id="02651-136">Остановить службу.</span><span class="sxs-lookup"><span data-stu-id="02651-136">Stop the service.</span></span>  
  
 <span data-ttu-id="02651-137">**Приостановить**</span><span class="sxs-lookup"><span data-stu-id="02651-137">**Pause**</span></span>  
 <span data-ttu-id="02651-138">Приостановить службу.</span><span class="sxs-lookup"><span data-stu-id="02651-138">Pause the service.</span></span> <span data-ttu-id="02651-139">Недоступно для этой службы.</span><span class="sxs-lookup"><span data-stu-id="02651-139">Not available for this service.</span></span>  
  
 <span data-ttu-id="02651-140">**Возобновить**</span><span class="sxs-lookup"><span data-stu-id="02651-140">**Resume**</span></span>  
 <span data-ttu-id="02651-141">Возобновить приостановленную работу службы.</span><span class="sxs-lookup"><span data-stu-id="02651-141">Resume a paused service.</span></span>  
  
  
