---
title: Свойства сервера (страница "Безопасность") | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.serverproperties.security.f1
ms.assetid: b8a131c7-e7bd-4203-bf26-234f1ebfe622
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5f45c0a04a0d7cc627901d8de24175f1d63a99fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669101"
---
# <a name="server-properties-security-page"></a><span data-ttu-id="c5114-102">Свойства сервера (страница «Безопасность»)</span><span class="sxs-lookup"><span data-stu-id="c5114-102">Server Properties (Security Page)</span></span>
  <span data-ttu-id="c5114-103">Эта страница используется для просмотра или изменения параметров безопасности сервера.</span><span class="sxs-lookup"><span data-stu-id="c5114-103">Use this page to view or modify your server security options.</span></span>  
  
## <a name="server-authentication"></a><span data-ttu-id="c5114-104">Проверка подлинности сервера</span><span class="sxs-lookup"><span data-stu-id="c5114-104">Server Authentication</span></span>  
 <span data-ttu-id="c5114-105">**Режим проверки подлинности Windows**</span><span class="sxs-lookup"><span data-stu-id="c5114-105">**Windows Authentication mode**</span></span>  
 <span data-ttu-id="c5114-106">Используется проверка подлинности Windows для проверки допустимости попыток соединения.</span><span class="sxs-lookup"><span data-stu-id="c5114-106">Uses Windows Authentication to validate attempted connections.</span></span> <span data-ttu-id="c5114-107">Если при изменении режима безопасности пароль **sa** пуст, пользователю предлагается ввести пароль **sa** .</span><span class="sxs-lookup"><span data-stu-id="c5114-107">If the **sa** password is blank when the security mode is being changed, the user is prompted to enter an **sa** password.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c5114-108">Проверка подлинности Windows намного надежней, чем проверка подлинности SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c5114-108">Windows Authentication is much more secure than SQL Server Authentication.</span></span> <span data-ttu-id="c5114-109">При возможности используйте проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="c5114-109">When possible, you should use Windows Authentication.</span></span>  
  
 <span data-ttu-id="c5114-110">**Режим проверки подлинности SQL Server и Windows**</span><span class="sxs-lookup"><span data-stu-id="c5114-110">**SQL Server and Windows Authentication mode**</span></span>  
 <span data-ttu-id="c5114-111">Используется смешанная проверка подлинности при соединениях для обратной совместимости с более ранними версиями [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5114-111">Uses mixed mode authentication to verify attempted connections, for backward compatibility with earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c5114-112">Если при изменении режима безопасности пароль **sa** пуст, пользователю предлагается ввести пароль **sa** .</span><span class="sxs-lookup"><span data-stu-id="c5114-112">If the **sa** password is blank when the security mode is being changed, the user is prompted to enter an **sa** password.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c5114-113">При изменении конфигурации безопасности необходимо перезапустить службу.</span><span class="sxs-lookup"><span data-stu-id="c5114-113">Changing the security configuration requires a restart of the service.</span></span> <span data-ttu-id="c5114-114">При изменении режима проверки подлинности сервера на режим проверки подлинности SQL Server и Windows учетная запись проверки подлинности сервера автоматически не включается.</span><span class="sxs-lookup"><span data-stu-id="c5114-114">When changing the Server Authentication to SQL Server and Windows Authentication mode the SA account is not automatically enabled.</span></span> <span data-ttu-id="c5114-115">Для использования учетной записи SA выполните [ALTER LOGIN](/sql/t-sql/statements/alter-login-transact-sql) с параметром ENABLE.</span><span class="sxs-lookup"><span data-stu-id="c5114-115">To use the SA account, execute [ALTER LOGIN](/sql/t-sql/statements/alter-login-transact-sql) with the ENABLE option.</span></span>  
  
## <a name="login-auditing"></a><span data-ttu-id="c5114-116">Аудит входа</span><span class="sxs-lookup"><span data-stu-id="c5114-116">Login Auditing</span></span>  
 <span data-ttu-id="c5114-117">**None**</span><span class="sxs-lookup"><span data-stu-id="c5114-117">**None**</span></span>  
 <span data-ttu-id="c5114-118">Аудит входа не производится.</span><span class="sxs-lookup"><span data-stu-id="c5114-118">Turns off login auditing.</span></span>  
  
 <span data-ttu-id="c5114-119">**Только неуспешные попытки входа**</span><span class="sxs-lookup"><span data-stu-id="c5114-119">**Failed logins only**</span></span>  
 <span data-ttu-id="c5114-120">Производится аудит только неудачных попыток входа.</span><span class="sxs-lookup"><span data-stu-id="c5114-120">Audits unsuccessful logins only.</span></span>  
  
 <span data-ttu-id="c5114-121">**Только успешные попытки входа**</span><span class="sxs-lookup"><span data-stu-id="c5114-121">**Successful logins only**</span></span>  
 <span data-ttu-id="c5114-122">Производится аудит только удачных попыток входа.</span><span class="sxs-lookup"><span data-stu-id="c5114-122">Audits successful logins only.</span></span>  
  
 <span data-ttu-id="c5114-123">**Все попытки входа**</span><span class="sxs-lookup"><span data-stu-id="c5114-123">**Both failed and successful logins**</span></span>  
 <span data-ttu-id="c5114-124">Производится аудит всех попыток входа.</span><span class="sxs-lookup"><span data-stu-id="c5114-124">Audits all login attempts.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c5114-125">При изменении уровня аудита необходимо перезапустить службу.</span><span class="sxs-lookup"><span data-stu-id="c5114-125">Changing the audit level requires restarting the service.</span></span>  
  
## <a name="server-proxy-account"></a><span data-ttu-id="c5114-126">Серверная учетная запись-посредник</span><span class="sxs-lookup"><span data-stu-id="c5114-126">Server Proxy Account</span></span>  
 <span data-ttu-id="c5114-127">**Включить серверную учетную запись-посредник**</span><span class="sxs-lookup"><span data-stu-id="c5114-127">**Enable server proxy account**</span></span>  
 <span data-ttu-id="c5114-128">Включается учетная запись для использования **xp_cmdshell**.</span><span class="sxs-lookup"><span data-stu-id="c5114-128">Enables an account for use by **xp_cmdshell**.</span></span> <span data-ttu-id="c5114-129">Учетные записи-посредники позволяют осуществлять олицетворение имен входа, ролей сервера и ролей базы данных при выполнении команды операционной системы.</span><span class="sxs-lookup"><span data-stu-id="c5114-129">Proxy accounts allow for the impersonation of logins, server roles, and database roles when an operating system command is being executed.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="c5114-130">Имя входа, используемое учетной записью-посредником сервера, должно иметь минимально возможные права доступа, необходимые для выполнения намеченной работы.</span><span class="sxs-lookup"><span data-stu-id="c5114-130">The login used by the server proxy account should have the least privileges required to perform the intended work.</span></span> <span data-ttu-id="c5114-131">Излишние права доступа учетной записи-посредника могут быть использованы злоумышленниками для нарушения безопасности системы.</span><span class="sxs-lookup"><span data-stu-id="c5114-131">Excessive privileges for the proxy account could be used by a malicious user to compromise your system security.</span></span>  
  
 <span data-ttu-id="c5114-132">**Учетная запись-посредник**</span><span class="sxs-lookup"><span data-stu-id="c5114-132">**Proxy account**</span></span>  
 <span data-ttu-id="c5114-133">Задайте используемую учетную запись-посредник.</span><span class="sxs-lookup"><span data-stu-id="c5114-133">Specify the proxy account used.</span></span>  
  
 <span data-ttu-id="c5114-134">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="c5114-134">**Password**</span></span>  
 <span data-ttu-id="c5114-135">Задайте пароль для учетной записи-посредника.</span><span class="sxs-lookup"><span data-stu-id="c5114-135">Specify the password for the proxy account.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c5114-136">Параметры</span><span class="sxs-lookup"><span data-stu-id="c5114-136">Options</span></span>  
 <span data-ttu-id="c5114-137">**Включить трассировку аудита C2**</span><span class="sxs-lookup"><span data-stu-id="c5114-137">**Enable C2 audit tracing**</span></span>  
 <span data-ttu-id="c5114-138">Выполняется аудит всех попыток доступа к инструкциям и объектам и их запись в файл в каталоге \MSSQL\Data для экземпляров по умолчанию [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]или в каталоге \MSSQL$*имя_экземпляра*\Data для именованных экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5114-138">Audits all attempts to access statements and objects and records them to a file in the \MSSQL\Data directory for default instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or the \MSSQL$*instancename*\Data directory for named instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c5114-139">Дополнительные сведения см. в статье [Параметр конфигурации сервера "c2 audit mode"](c2-audit-mode-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="c5114-139">For more information, see [c2 audit mode Server Configuration Option](c2-audit-mode-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="c5114-140">**Формировать межбазовую цепочку владения**</span><span class="sxs-lookup"><span data-stu-id="c5114-140">**Cross database ownership chaining**</span></span>  
 <span data-ttu-id="c5114-141">Выберите этот пункт, чтобы база данных могла быть источником или назначением межбазовой цепочки владения.</span><span class="sxs-lookup"><span data-stu-id="c5114-141">Select to allow the database to be the source or target of a cross-database ownership chain.</span></span> <span data-ttu-id="c5114-142">Дополнительные сведения см. в статье [Параметр конфигурации сервера "cross db ownership chaining"](cross-db-ownership-chaining-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="c5114-142">For more information, see [cross db ownership chaining Server Configuration Option](cross-db-ownership-chaining-server-configuration-option.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5114-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="c5114-143">See Also</span></span>  
 [<span data-ttu-id="c5114-144">Параметры конфигурации сервера (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c5114-144">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
