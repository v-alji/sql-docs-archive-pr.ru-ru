---
title: Свойства SQL Server (вкладка "Вход в систему") | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 405073fc-eaa3-43c6-bf82-2cd58cacc1c3
author: stevestein
ms.author: sstein
ms.openlocfilehash: adec9ed7c69023218baa96ab8f8edbb6f2b365bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664628"
---
# <a name="sql-server-properties-log-on-tab"></a><span data-ttu-id="d6286-102">Свойства SQL Server (вкладка «Вход в систему»)</span><span class="sxs-lookup"><span data-stu-id="d6286-102">SQL Server Properties (Log On Tab)</span></span>
  <span data-ttu-id="d6286-103">Используйте вкладку **Вход** в диалоговом окне **Свойства SQL Server** для указания учетной записи, используемой службой сервера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , чтобы изменить пароль учетной записи и запустить или остановить службу.</span><span class="sxs-lookup"><span data-stu-id="d6286-103">Use the **Log On** tab of the **SQL Server Properties** dialog box to specify the account used by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service, to change the password of an account, and to start and stop the service.</span></span> <span data-ttu-id="d6286-104">Изменение пароля учетной записи вступает в силу немедленно.</span><span class="sxs-lookup"><span data-stu-id="d6286-104">Changing the password of an account takes effect immediately.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d6286-105">При изменении имени учетной записи, используемой службой в кластеризованном экземпляре, новая учетная запись должна быть членом группы домена, заданной во время установки изменяемой службы, или же текущий пользователь должен иметь разрешение на добавление членов в эту группу.</span><span class="sxs-lookup"><span data-stu-id="d6286-105">When changing the account name used by a service on a clustered instance, the new account must be a member of the domain group specified during setup for the service being changed, or you must have permission to add members to that group.</span></span> <span data-ttu-id="d6286-106">Если нет разрешения на изменение состава группы, свяжитесь с администратором домена.</span><span class="sxs-lookup"><span data-stu-id="d6286-106">If you do not have permission to modify group membership, contact the domain administrator.</span></span>  
>   
>  <span data-ttu-id="d6286-107">Дополнительные сведения о выборе учетной записи для выполнения службы приводятся в разделе «Настройка учетных записей служб Windows» электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d6286-107">For more information about selecting an account to run the service, see "Setting Up Windows Service Accounts" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d6286-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="d6286-108">Options</span></span>  
 <span data-ttu-id="d6286-109">**Встроенная учетная запись**</span><span class="sxs-lookup"><span data-stu-id="d6286-109">**Built-in account**</span></span>  
 <span data-ttu-id="d6286-110">**Локальная система**</span><span class="sxs-lookup"><span data-stu-id="d6286-110">**Local System**</span></span>  
 -   <span data-ttu-id="d6286-111">Укажите учетную запись локальной системы.</span><span class="sxs-lookup"><span data-stu-id="d6286-111">Specify the local system account.</span></span> <span data-ttu-id="d6286-112">Для этой учетной записи пароль не нужен.</span><span class="sxs-lookup"><span data-stu-id="d6286-112">This account does not require a password.</span></span> <span data-ttu-id="d6286-113">Однако локальная системная учетная запись может препятствовать взаимодействию служб с другими серверами, в зависимости от прав доступа, предоставленных этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="d6286-113">However, the local system account may prevent the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="d6286-114">**Локальная служба.**</span><span class="sxs-lookup"><span data-stu-id="d6286-114">**Local Service**</span></span>  
 -   <span data-ttu-id="d6286-115">Укажите учетную запись локальной службы.</span><span class="sxs-lookup"><span data-stu-id="d6286-115">Specify the local service account.</span></span> <span data-ttu-id="d6286-116">Для этой учетной записи пароль не нужен.</span><span class="sxs-lookup"><span data-stu-id="d6286-116">This account does not require a password.</span></span> <span data-ttu-id="d6286-117">Однако учетная запись локальной службы может препятствовать взаимодействию служб с другими серверами, в зависимости от прав доступа, предоставленных этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="d6286-117">However, the local service account may prevent the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="d6286-118">**Сетевая служба.**</span><span class="sxs-lookup"><span data-stu-id="d6286-118">**Network Service**</span></span>  
 -   <span data-ttu-id="d6286-119">Не рекомендуется использовать учетную запись сетевой службы для служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d6286-119">We recommend that you do not use the Network Service account for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent services.</span></span> <span data-ttu-id="d6286-120">Для этих служб больше подходят учетные записи «Локальный пользователь» или «Пользователь домена».</span><span class="sxs-lookup"><span data-stu-id="d6286-120">Local User or Domain User accounts are more appropriate for these services.</span></span>  
  
 <span data-ttu-id="d6286-121">**Эта учетная запись**</span><span class="sxs-lookup"><span data-stu-id="d6286-121">**This account**</span></span>  
 <span data-ttu-id="d6286-122">Укажите локальную или доменную учетную запись, использующую аутентификацию Windows.</span><span class="sxs-lookup"><span data-stu-id="d6286-122">Specify a local or domain user account that uses Windows Authentication.</span></span> <span data-ttu-id="d6286-123">Для служб рекомендуется использовать доменную учетную запись с минимальными правами.</span><span class="sxs-lookup"><span data-stu-id="d6286-123">We recommend that you use a domain user account that has minimal rights for services.</span></span>  
  
 <span data-ttu-id="d6286-124">**Account Name** (Имя учетной записи)</span><span class="sxs-lookup"><span data-stu-id="d6286-124">**Account Name**</span></span>  
 <span data-ttu-id="d6286-125">Укажите имя локальной или доменной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="d6286-125">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="d6286-126">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="d6286-126">**Password**</span></span>  
 <span data-ttu-id="d6286-127">Введите пароль для учетной записи.</span><span class="sxs-lookup"><span data-stu-id="d6286-127">Type the password of the account.</span></span>  
  
 <span data-ttu-id="d6286-128">**Подтверждение пароля**</span><span class="sxs-lookup"><span data-stu-id="d6286-128">**Confirm password**</span></span>  
 <span data-ttu-id="d6286-129">Введите пароль для учетной записи еще раз.</span><span class="sxs-lookup"><span data-stu-id="d6286-129">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="d6286-130">**Начало**</span><span class="sxs-lookup"><span data-stu-id="d6286-130">**Start**</span></span>  
 <span data-ttu-id="d6286-131">Запускает службу.</span><span class="sxs-lookup"><span data-stu-id="d6286-131">Start the service.</span></span>  
  
 <span data-ttu-id="d6286-132">**Остановить**</span><span class="sxs-lookup"><span data-stu-id="d6286-132">**Stop**</span></span>  
 <span data-ttu-id="d6286-133">Остановить службу.</span><span class="sxs-lookup"><span data-stu-id="d6286-133">Stop the service.</span></span>  
  
 <span data-ttu-id="d6286-134">**Приостановить**</span><span class="sxs-lookup"><span data-stu-id="d6286-134">**Pause**</span></span>  
 <span data-ttu-id="d6286-135">Приостановить службу.</span><span class="sxs-lookup"><span data-stu-id="d6286-135">Pause the service.</span></span>  
  
 <span data-ttu-id="d6286-136">**Возобновить**</span><span class="sxs-lookup"><span data-stu-id="d6286-136">**Resume**</span></span>  
 <span data-ttu-id="d6286-137">Возобновить приостановленную работу службы.</span><span class="sxs-lookup"><span data-stu-id="d6286-137">Resume a paused service.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d6286-138">По умолчанию только участники локальной группы «Администраторы» могут запускать, останавливать, приостанавливать, возобновлять или перезапускать службу.</span><span class="sxs-lookup"><span data-stu-id="d6286-138">By default, only members of the local administrators group can start, stop, pause, resume or restart a service.</span></span> <span data-ttu-id="d6286-139">При необходимости предоставить возможность управления службой для пользователей, не обладающих правами администратора, см. раздел [Как предоставить пользователям права для управления службами в Windows Server 2003](https://support.microsoft.com/kb/325349).</span><span class="sxs-lookup"><span data-stu-id="d6286-139">To grant non-administrators the ability to manage services, see [How to grant users rights to manage services in Windows Server 2003](https://support.microsoft.com/kb/325349).</span></span> <span data-ttu-id="d6286-140">(Процесс такой же, как и в других версиях Windows.)</span><span class="sxs-lookup"><span data-stu-id="d6286-140">(The process is similar on other versions of Windows.)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d6286-141">При запуске [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ошибка инструментария WMI, содержащая фразу «не реализовано [0x80004001]», может указывать на то, что на целевом компьютере [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не установлен.</span><span class="sxs-lookup"><span data-stu-id="d6286-141">When starting [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a WMI error containing the phrase "not implemented [0x80004001]" may indicate that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not installed on the target computer.</span></span>  
  
  
