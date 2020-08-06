---
title: Политика паролей | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- ALTER LOGIN statement
- passwords [SQL Server], policy enforcement
- logins [SQL Server], passwords
- CHECK_EXPIRATION option
- complex passwords [SQL Server]
- passwords [SQL Server], expiration
- manual bad password count resets
- MUST_CHANGE option
- expiration [SQL Server]
- expired password [SQL Server]
- symbols [SQL Server]
- NetValidatePasswordPolicy() API
- passwords [SQL Server]
- password policy [SQL Server]
- resetting bad password counts
- security [SQL Server], passwords
- CHECK_POLICY option
- passwords [SQL Server], symbols
- bad password counts
- passwords [SQL Server], complexity
- characters [SQL Server], password policies
ms.assetid: c0040c0a-a18f-45b9-9c40-0625685649b1
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 902c46b4609a32139450843414a3c4d97b52fcf7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656272"
---
# <a name="password-policy"></a><span data-ttu-id="13eef-102">Политика паролей</span><span class="sxs-lookup"><span data-stu-id="13eef-102">Password Policy</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="13eef-103">поддерживается использование механизмов политики паролей Windows.</span><span class="sxs-lookup"><span data-stu-id="13eef-103">can use Windows password policy mechanisms.</span></span> <span data-ttu-id="13eef-104">Политика паролей применяется к имени входа, которое использует проверку подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , и к пользователю автономной базы данных с паролем.</span><span class="sxs-lookup"><span data-stu-id="13eef-104">The password policy applies to a login that uses [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] authentication, and to a contained database user with password.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="13eef-105">могут применяться политики сложности и истечения срока действия, которые применяются в Windows к паролям, используемым в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="13eef-105">can apply the same complexity and expiration policies used in Windows to passwords used inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="13eef-106">Эти возможности построены на API-интерфейсе `NetValidatePasswordPolicy` .</span><span class="sxs-lookup"><span data-stu-id="13eef-106">This functionality depends on the `NetValidatePasswordPolicy` API.</span></span>  
  
## <a name="password-complexity"></a><span data-ttu-id="13eef-107">Сложность пароля</span><span class="sxs-lookup"><span data-stu-id="13eef-107">Password Complexity</span></span>  
 <span data-ttu-id="13eef-108">Политика сложности паролей позволяет отражать атаки, использующие простой перебор, путем увеличения числа возможных паролей.</span><span class="sxs-lookup"><span data-stu-id="13eef-108">Password complexity policies are designed to deter brute force attacks by increasing the number of possible passwords.</span></span> <span data-ttu-id="13eef-109">Если применяется политика сложности паролей, новые пароли должны удовлетворять следующим требованиям.</span><span class="sxs-lookup"><span data-stu-id="13eef-109">When password complexity policy is enforced, new passwords must meet the following guidelines:</span></span>  
  
-   <span data-ttu-id="13eef-110">Пароль не содержит имя учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="13eef-110">The password does not contain the account name of the user.</span></span>  
  
-   <span data-ttu-id="13eef-111">Длина пароля составляет не менее восьми символов.</span><span class="sxs-lookup"><span data-stu-id="13eef-111">The password is at least eight characters long.</span></span>  
  
-   <span data-ttu-id="13eef-112">Пароль содержит символы, соответствующие трем из следующих четырех категорий:</span><span class="sxs-lookup"><span data-stu-id="13eef-112">The password contains characters from three of the following four categories:</span></span>  
  
    -   <span data-ttu-id="13eef-113">прописные латинские буквы (А-Z)</span><span class="sxs-lookup"><span data-stu-id="13eef-113">Latin uppercase letters (A through Z)</span></span>  
  
    -   <span data-ttu-id="13eef-114">строчные латинские буквы (a-z)</span><span class="sxs-lookup"><span data-stu-id="13eef-114">Latin lowercase letters (a through z)</span></span>  
  
    -   <span data-ttu-id="13eef-115">цифры (0-9)</span><span class="sxs-lookup"><span data-stu-id="13eef-115">Base 10 digits (0 through 9)</span></span>  
  
    -   <span data-ttu-id="13eef-116">Символы, отличные от буквенно-цифровых: восклицательный знак (!), знак доллара ($), решетка (#) или знак процента (%).</span><span class="sxs-lookup"><span data-stu-id="13eef-116">Non-alphanumeric characters such as: exclamation point (!), dollar sign ($), number sign (#), or percent (%).</span></span>  
  
 <span data-ttu-id="13eef-117">Пароли могут иметь длину до 128 символов.</span><span class="sxs-lookup"><span data-stu-id="13eef-117">Passwords can be up to 128 characters long.</span></span> <span data-ttu-id="13eef-118">Рекомендуется использовать максимально длинные и сложные пароли.</span><span class="sxs-lookup"><span data-stu-id="13eef-118">You should use passwords that are as long and complex as possible.</span></span>  
  
## <a name="password-expiration"></a><span data-ttu-id="13eef-119">Истечение срока действия пароля</span><span class="sxs-lookup"><span data-stu-id="13eef-119">Password Expiration</span></span>  
 <span data-ttu-id="13eef-120">Политика истечения срока действия паролей используется для управления продолжительностью действия пароля.</span><span class="sxs-lookup"><span data-stu-id="13eef-120">Password expiration policies are used to manage the lifespan of a password.</span></span> <span data-ttu-id="13eef-121">Когда [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] применяет политику истечения срока действия паролей, пользователи получают уведомления о необходимости изменения старых паролей, а учетные записи с истекшим сроком действия пароля отключаются.</span><span class="sxs-lookup"><span data-stu-id="13eef-121">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] enforces password expiration policy, users are reminded to change old passwords, and accounts that have expired passwords are disabled.</span></span>  
  
## <a name="policy-enforcement"></a><span data-ttu-id="13eef-122">Применение политики</span><span class="sxs-lookup"><span data-stu-id="13eef-122">Policy Enforcement</span></span>  
 <span data-ttu-id="13eef-123">Применение политики паролей можно настроить отдельно для каждого имени входа SQL Server.</span><span class="sxs-lookup"><span data-stu-id="13eef-123">The enforcement of password policy can be configured separately for each SQL Server login.</span></span> <span data-ttu-id="13eef-124">Чтобы настроить параметры политики паролей для имени входа SQL Server, выполните инструкцию [ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="13eef-124">Use [ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) to configure the password policy options of a SQL Server login.</span></span> <span data-ttu-id="13eef-125">Для настройки принудительного применения политики паролей действуют следующие правила.</span><span class="sxs-lookup"><span data-stu-id="13eef-125">The following rules apply to the configuration of password policy enforcement:</span></span>  
  
-   <span data-ttu-id="13eef-126">При переключении параметра CHECK_POLICY на значение ON происходит следующее:</span><span class="sxs-lookup"><span data-stu-id="13eef-126">When CHECK_POLICY is changed to ON, the following behaviors occur:</span></span>  
  
    -   <span data-ttu-id="13eef-127">параметр CHECK_EXPIRATION также изменяется на ON, если он не будет прямо изменен на OFF;</span><span class="sxs-lookup"><span data-stu-id="13eef-127">CHECK_EXPIRATION is also set to ON unless it is explicitly set to OFF.</span></span>  
  
    -   <span data-ttu-id="13eef-128">Журнал паролей инициализируется значением хэша текущего пароля.</span><span class="sxs-lookup"><span data-stu-id="13eef-128">The password history is initialized with the value of the current password hash.</span></span>  
  
    -   <span data-ttu-id="13eef-129">Включены также параметры**продолжительность существования блокировки учетной записи**, **пороговое значение блокировки учетной записи**и **сброс счетчика блокировки учетной записи после** .</span><span class="sxs-lookup"><span data-stu-id="13eef-129">**Account lockout duration**, **account lockout threshold**, and **reset account lockout counter after** are also enabled.</span></span>  
  
-   <span data-ttu-id="13eef-130">При переключении параметра CHECK_POLICY в значение OFF происходит следующее:</span><span class="sxs-lookup"><span data-stu-id="13eef-130">When CHECK_POLICY is changed to OFF, the following behaviors occur:</span></span>  
  
    -   <span data-ttu-id="13eef-131">Параметр CHECK_EXPIRATION также получает значение OFF.</span><span class="sxs-lookup"><span data-stu-id="13eef-131">CHECK_EXPIRATION is also set to OFF.</span></span>  
  
    -   <span data-ttu-id="13eef-132">Журнал паролей очищается.</span><span class="sxs-lookup"><span data-stu-id="13eef-132">The password history is cleared.</span></span>  
  
    -   <span data-ttu-id="13eef-133">Значение параметра `lockout_time` сбрасывается.</span><span class="sxs-lookup"><span data-stu-id="13eef-133">The value of `lockout_time` is reset.</span></span>  
  
 <span data-ttu-id="13eef-134">Некоторые сочетания параметров политик не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="13eef-134">Some combinations of policy options are not supported.</span></span>  
  
-   <span data-ttu-id="13eef-135">Если задан параметр MUST_CHANGE, то параметры CHECK_EXPIRATION и CHECK_POLICY должны иметь значение ON.</span><span class="sxs-lookup"><span data-stu-id="13eef-135">If MUST_CHANGE is specified, CHECK_EXPIRATION and CHECK_POLICY must be set to ON.</span></span> <span data-ttu-id="13eef-136">В противном случае выполнение инструкции приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="13eef-136">Otherwise, the statement will fail.</span></span>  
  
-   <span data-ttu-id="13eef-137">Если значение параметра CHECK_POLICY установлено равным OFF, то параметр CHECK_EXPIRATION не может иметь значения ON.</span><span class="sxs-lookup"><span data-stu-id="13eef-137">If CHECK_POLICY is set to OFF, CHECK_EXPIRATION cannot be set to ON.</span></span> <span data-ttu-id="13eef-138">Выполнение инструкции ALTER LOGIN с таким сочетанием параметров завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="13eef-138">An ALTER LOGIN statement that has this combination of options will fail.</span></span>  
  
 <span data-ttu-id="13eef-139">При установке параметра CHECK_POLICY = ON блокируется создание следующих паролей:</span><span class="sxs-lookup"><span data-stu-id="13eef-139">Setting CHECK_POLICY = ON will prevent the creation of passwords that are:</span></span>  
  
-   <span data-ttu-id="13eef-140">пустых или неопределенных;</span><span class="sxs-lookup"><span data-stu-id="13eef-140">Null or empty</span></span>  
  
-   <span data-ttu-id="13eef-141">совпадающих с именем компьютера или именем входа;</span><span class="sxs-lookup"><span data-stu-id="13eef-141">Same as name of computer or login</span></span>  
  
-   <span data-ttu-id="13eef-142">представляющих собой любую из следующих строк: "password", "admin", "administrator", "sa", "sysadmin".</span><span class="sxs-lookup"><span data-stu-id="13eef-142">Any of the following: "password", "admin", "administrator", "sa", "sysadmin"</span></span>  
  
 <span data-ttu-id="13eef-143">Политика безопасности может быть настроена в Windows или получена из домена.</span><span class="sxs-lookup"><span data-stu-id="13eef-143">The security policy might be set in Windows, or might be received from the domain.</span></span> <span data-ttu-id="13eef-144">Для просмотра политики паролей на компьютере используется оснастка консоли управления "Локальная политика безопасности" (**secpol.msc**).</span><span class="sxs-lookup"><span data-stu-id="13eef-144">To view the password policy on the computer, use the Local Security Policy MMC snap-in (**secpol.msc**).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="13eef-145">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="13eef-145">Related Tasks</span></span>  
 [<span data-ttu-id="13eef-146">CREATE LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="13eef-146">CREATE LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-login-transact-sql)  
  
 [<span data-ttu-id="13eef-147">ALTER LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="13eef-147">ALTER LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-login-transact-sql)  
  
 [<span data-ttu-id="13eef-148">CREATE USER (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="13eef-148">CREATE USER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-user-transact-sql)  
  
 [<span data-ttu-id="13eef-149">ALTER USER (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="13eef-149">ALTER USER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-user-transact-sql)  
  
 [<span data-ttu-id="13eef-150">Создание имени входа</span><span class="sxs-lookup"><span data-stu-id="13eef-150">Create a Login</span></span>](authentication-access/create-a-login.md)  
  
 [<span data-ttu-id="13eef-151">Создание пользователя базы данных</span><span class="sxs-lookup"><span data-stu-id="13eef-151">Create a Database User</span></span>](authentication-access/create-a-database-user.md)  
  
## <a name="related-content"></a><span data-ttu-id="13eef-152">См. также</span><span class="sxs-lookup"><span data-stu-id="13eef-152">Related Content</span></span>  
 [<span data-ttu-id="13eef-153">Надежные пароли</span><span class="sxs-lookup"><span data-stu-id="13eef-153">Strong Passwords</span></span>](strong-passwords.md)  
  
  
