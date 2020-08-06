---
title: MSSQLSERVER_18456 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 18456 (Database Engine error)
ms.assetid: c417631d-be1f-42e0-8844-9f92c77e11f7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f5addb6bfb9d056d9f1796749ae629d4150102a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731670"
---
# <a name="mssqlserver_18456"></a><span data-ttu-id="28dba-102">MSSQLSERVER_18456</span><span class="sxs-lookup"><span data-stu-id="28dba-102">MSSQLSERVER_18456</span></span>
    
## <a name="details"></a><span data-ttu-id="28dba-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="28dba-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="28dba-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="28dba-104">Product Name</span></span>|<span data-ttu-id="28dba-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="28dba-105">SQL Server</span></span>|  
|<span data-ttu-id="28dba-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="28dba-106">Event ID</span></span>|<span data-ttu-id="28dba-107">18456</span><span class="sxs-lookup"><span data-stu-id="28dba-107">18456</span></span>|  
|<span data-ttu-id="28dba-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="28dba-108">Event Source</span></span>|<span data-ttu-id="28dba-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="28dba-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="28dba-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="28dba-110">Component</span></span>|<span data-ttu-id="28dba-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="28dba-111">SQLEngine</span></span>|  
|<span data-ttu-id="28dba-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="28dba-112">Symbolic Name</span></span>|<span data-ttu-id="28dba-113">LOGON_FAILED</span><span class="sxs-lookup"><span data-stu-id="28dba-113">LOGON_FAILED</span></span>|  
|<span data-ttu-id="28dba-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="28dba-114">Message Text</span></span>|<span data-ttu-id="28dba-115">Ошибка входа пользователя '%.\*ls'.%.\*ls</span><span class="sxs-lookup"><span data-stu-id="28dba-115">Login failed for user '%.\*ls'.%.\*ls</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="28dba-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="28dba-116">Explanation</span></span>  
 <span data-ttu-id="28dba-117">Если попытка соединения отклоняется в результате сбоя проверки подлинности из-за неправильного имени или пароля, клиенту выдается сообщение, подобное следующему:  "Ошибка входа пользователя <имя_пользователя>.</span><span class="sxs-lookup"><span data-stu-id="28dba-117">When a connection attempt is rejected because of an authentication failure that involves a bad password or user name, a message similar to the following is returned to the client:  "Login failed for user '<user_name>'.</span></span> <span data-ttu-id="28dba-118">(Microsoft SQL Server, ошибка: 18456)".</span><span class="sxs-lookup"><span data-stu-id="28dba-118">(Microsoft SQL Server, Error: 18456)".</span></span>  
  
 <span data-ttu-id="28dba-119">Дополнительные сведения, возвращаемые клиенту, включают в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="28dba-119">Additional information returned to the client includes the following:</span></span>  
  
 <span data-ttu-id="28dba-120">"Ошибка входа пользователя <имя_пользователя>.</span><span class="sxs-lookup"><span data-stu-id="28dba-120">"Login failed for user '<user_name>'.</span></span> <span data-ttu-id="28dba-121">(.Net SqlClient Data Provider)"</span><span class="sxs-lookup"><span data-stu-id="28dba-121">(.Net SqlClient Data Provider)"</span></span>  
  
 -----------------------------\-  
  
 <span data-ttu-id="28dba-122">"Имя сервера: <имя_компьютера>"</span><span class="sxs-lookup"><span data-stu-id="28dba-122">"Server Name: <computer_name>"</span></span>  
  
 <span data-ttu-id="28dba-123">"Номер ошибки: 18456"</span><span class="sxs-lookup"><span data-stu-id="28dba-123">"Error Number: 18456"</span></span>  
  
 <span data-ttu-id="28dba-124">"Серьезность: 14"</span><span class="sxs-lookup"><span data-stu-id="28dba-124">"Severity: 14"</span></span>  
  
 <span data-ttu-id="28dba-125">"Состояние: 1"</span><span class="sxs-lookup"><span data-stu-id="28dba-125">"State: 1"</span></span>  
  
 <span data-ttu-id="28dba-126">"Номер строки: 65536"</span><span class="sxs-lookup"><span data-stu-id="28dba-126">"Line Number: 65536"</span></span>  
  
 <span data-ttu-id="28dba-127">Может также возвращаться следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="28dba-127">The following message might also be returned:</span></span>  
  
 <span data-ttu-id="28dba-128">"Сообщение 18456, уровень 14, состояние 1, сервер <имя_компьютера>, строка 1"</span><span class="sxs-lookup"><span data-stu-id="28dba-128">"Msg 18456, Level 14, State 1, Server <computer_name>, Line 1"</span></span>  
  
 <span data-ttu-id="28dba-129">"Ошибка входа пользователя <имя_пользователя>".</span><span class="sxs-lookup"><span data-stu-id="28dba-129">"Login failed for user '<user_name>'."</span></span>  
  
## <a name="additional-error-information"></a><span data-ttu-id="28dba-130">Дополнительные сведения об ошибке</span><span class="sxs-lookup"><span data-stu-id="28dba-130">Additional Error Information</span></span>  
 <span data-ttu-id="28dba-131">В целях повышения безопасности сообщение об ошибке, возвращаемое клиенту, намеренно скрывает природу ошибки проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="28dba-131">To increase security, the error message that is returned to the client deliberately hides the nature of the authentication error.</span></span> <span data-ttu-id="28dba-132">Однако в журнале ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для соответствующей ошибки указано состояние, которое можно сопоставить с условиями сбоя проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="28dba-132">However, in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log, a corresponding error contains an error state that maps to an authentication failure condition.</span></span> <span data-ttu-id="28dba-133">Сравните состояние ошибки со следующим списком, чтобы определить причину ошибки входа.</span><span class="sxs-lookup"><span data-stu-id="28dba-133">Compare the error state to the following list to determine the reason for the login failure.</span></span>  
  
|<span data-ttu-id="28dba-134">Состояние</span><span class="sxs-lookup"><span data-stu-id="28dba-134">State</span></span>|<span data-ttu-id="28dba-135">Описание</span><span class="sxs-lookup"><span data-stu-id="28dba-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="28dba-136">1</span><span class="sxs-lookup"><span data-stu-id="28dba-136">1</span></span>|<span data-ttu-id="28dba-137">Сведения об ошибке недоступны.</span><span class="sxs-lookup"><span data-stu-id="28dba-137">Error information is not available.</span></span> <span data-ttu-id="28dba-138">Это состояние обычно означает отсутствие разрешений на получение сведений об ошибке.</span><span class="sxs-lookup"><span data-stu-id="28dba-138">This state usually means you do not have permission to receive the error details.</span></span> <span data-ttu-id="28dba-139">За дополнительными сведениями обратитесь к администратору [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28dba-139">Contact your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administrator for more information.</span></span>|  
|<span data-ttu-id="28dba-140">2</span><span class="sxs-lookup"><span data-stu-id="28dba-140">2</span></span>|<span data-ttu-id="28dba-141">Недопустимый идентификатор пользователя.</span><span class="sxs-lookup"><span data-stu-id="28dba-141">User ID is not valid.</span></span>|  
|<span data-ttu-id="28dba-142">5</span><span class="sxs-lookup"><span data-stu-id="28dba-142">5</span></span>|<span data-ttu-id="28dba-143">Недопустимый идентификатор пользователя.</span><span class="sxs-lookup"><span data-stu-id="28dba-143">User ID is not valid.</span></span>|  
|<span data-ttu-id="28dba-144">6</span><span class="sxs-lookup"><span data-stu-id="28dba-144">6</span></span>|<span data-ttu-id="28dba-145">Предпринята попытка использовать имя входа Windows при использовании проверки подлинности SQL Server.</span><span class="sxs-lookup"><span data-stu-id="28dba-145">An attempt was made to use a Windows login name with SQL Server Authentication.</span></span>|  
|<span data-ttu-id="28dba-146">7</span><span class="sxs-lookup"><span data-stu-id="28dba-146">7</span></span>|<span data-ttu-id="28dba-147">Имя входа отключено, и пароль неверный.</span><span class="sxs-lookup"><span data-stu-id="28dba-147">Login is disabled, and the password is incorrect.</span></span>|  
|<span data-ttu-id="28dba-148">8</span><span class="sxs-lookup"><span data-stu-id="28dba-148">8</span></span>|<span data-ttu-id="28dba-149">Пароль неверный.</span><span class="sxs-lookup"><span data-stu-id="28dba-149">The password is incorrect.</span></span>|  
|<span data-ttu-id="28dba-150">9</span><span class="sxs-lookup"><span data-stu-id="28dba-150">9</span></span>|<span data-ttu-id="28dba-151">Недопустимый пароль.</span><span class="sxs-lookup"><span data-stu-id="28dba-151">Password is not valid.</span></span>|  
|<span data-ttu-id="28dba-152">11</span><span class="sxs-lookup"><span data-stu-id="28dba-152">11</span></span>|<span data-ttu-id="28dba-153">Допустимое имя входа, но доступ к серверу не удался.</span><span class="sxs-lookup"><span data-stu-id="28dba-153">Login is valid, but server access failed.</span></span> <span data-ttu-id="28dba-154">Одна из возможных причин этой ошибки: пользователь Windows имеет доступ к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в качестве члена группы локальных администраторов, но Windows не предоставляет учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="28dba-154">One possible cause of this error is when the Windows user has access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as a member of the local administrators group, but Windows is not providing administrator credentials.</span></span> <span data-ttu-id="28dba-155">Чтобы установить соединение, запустите программу подключения **от имени администратора**, а затем добавьте имя пользователя Windows в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в качестве определенного имени входа.|</span><span class="sxs-lookup"><span data-stu-id="28dba-155">To connect, start the connecting program using the **Run as administrator** option, and then add the Windows user to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as a specific login.</span></span>|  
|<span data-ttu-id="28dba-156">12</span><span class="sxs-lookup"><span data-stu-id="28dba-156">12</span></span>|<span data-ttu-id="28dba-157">Допустимое имя входа, но доступ к серверу не удался.</span><span class="sxs-lookup"><span data-stu-id="28dba-157">Login is valid login, but server access failed.</span></span>|  
|<span data-ttu-id="28dba-158">18</span><span class="sxs-lookup"><span data-stu-id="28dba-158">18</span></span>|<span data-ttu-id="28dba-159">Пароль должен быть изменен.</span><span class="sxs-lookup"><span data-stu-id="28dba-159">Password must be changed.</span></span>|  
  
 <span data-ttu-id="28dba-160">Есть другие коды ошибок, которые означают непредвиденные внутренние ошибки обработки.</span><span class="sxs-lookup"><span data-stu-id="28dba-160">Other error states exist and signify an unexpected internal processing error.</span></span>  
  
 <span data-ttu-id="28dba-161">**Еще одна, менее распространенная, возможная причина**</span><span class="sxs-lookup"><span data-stu-id="28dba-161">**An additional unusual possible cause**</span></span>  
  
 <span data-ttu-id="28dba-162">Причина ошибки **Попытка входа с помощью проверки подлинности SQL завершилась ошибкой. Конфигурация сервера поддерживает только проверку подлинности Windows.**</span><span class="sxs-lookup"><span data-stu-id="28dba-162">The error reason **An attempt to login using SQL authentication failed. Server is configured for Windows authentication only.**</span></span> <span data-ttu-id="28dba-163">Это сообщение возвращается в следующих ситуациях.</span><span class="sxs-lookup"><span data-stu-id="28dba-163">can be returned in the following situations.</span></span>  
  
-   <span data-ttu-id="28dba-164">Когда на сервере настроена проверка подлинности в смешанном режиме, подключение ODBC использует протокол TCP, а подключение не указывает явно, что оно должно быть доверительным.</span><span class="sxs-lookup"><span data-stu-id="28dba-164">When the server is configured for mixed mode authentication, and an ODBC connection uses the TCP protocol, and the connection does not explicitly specify that the connection should use a trusted connection.</span></span>  
  
-   <span data-ttu-id="28dba-165">Когда на сервере настроена проверка подлинности в смешанном режиме, подключение ODBC использует именованные каналы, учетные данные, которые клиент использовал для открытия именованного канала, используются для автоматического олицетворения пользователя, а подключение не указывает явно, что оно должно быть доверительным.</span><span class="sxs-lookup"><span data-stu-id="28dba-165">When the server is configured for mixed mode authentication, and an ODBC connection uses named pipes, and the credentials the client used to open the named pipe are used to automatically impersonate the user, and the connection does not explicitly specify that the connection should use a trusted connection.</span></span>  
  
 <span data-ttu-id="28dba-166">Чтобы решить эту проблему, включите в строку подключения параметр `TRUSTED_CONNECTION = TRUE`.</span><span class="sxs-lookup"><span data-stu-id="28dba-166">To resolve this issue, include `TRUSTED_CONNECTION = TRUE` in the connection string.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="28dba-167">Примеры</span><span class="sxs-lookup"><span data-stu-id="28dba-167">Examples</span></span>  
 <span data-ttu-id="28dba-168">В этом примере состояние ошибки проверки подлинности равно 8.</span><span class="sxs-lookup"><span data-stu-id="28dba-168">In this example, the authentication error state is 8.</span></span> <span data-ttu-id="28dba-169">Это означает, что пароль неверный.</span><span class="sxs-lookup"><span data-stu-id="28dba-169">This indicates that the password is incorrect.</span></span>  
  
|<span data-ttu-id="28dba-170">Дата</span><span class="sxs-lookup"><span data-stu-id="28dba-170">Date</span></span>|<span data-ttu-id="28dba-171">Источник</span><span class="sxs-lookup"><span data-stu-id="28dba-171">Source</span></span>|<span data-ttu-id="28dba-172">Сообщение</span><span class="sxs-lookup"><span data-stu-id="28dba-172">Message</span></span>|  
|----------|------------|-------------|  
|<span data-ttu-id="28dba-173">2007-12-05 20:12:56.34</span><span class="sxs-lookup"><span data-stu-id="28dba-173">2007-12-05 20:12:56.34</span></span>|<span data-ttu-id="28dba-174">Вход в систему</span><span class="sxs-lookup"><span data-stu-id="28dba-174">Logon</span></span>|<span data-ttu-id="28dba-175">Ошибка: 18456, серьезность: 14, состояние: 8.</span><span class="sxs-lookup"><span data-stu-id="28dba-175">Error: 18456, Severity: 14, State: 8.</span></span>|  
|<span data-ttu-id="28dba-176">2007-12-05 20:12:56.34</span><span class="sxs-lookup"><span data-stu-id="28dba-176">2007-12-05 20:12:56.34</span></span>|<span data-ttu-id="28dba-177">Вход в систему</span><span class="sxs-lookup"><span data-stu-id="28dba-177">Logon</span></span>|<span data-ttu-id="28dba-178">"Ошибка входа пользователя <имя_пользователя>".</span><span class="sxs-lookup"><span data-stu-id="28dba-178">Login failed for user '<user_name>'.</span></span> <span data-ttu-id="28dba-179">[КЛИЕНТ: \<ip address>]</span><span class="sxs-lookup"><span data-stu-id="28dba-179">[CLIENT: \<ip address>]</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="28dba-180">Если [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] устанавливается в режиме аутентификации Windows, а затем переключается на аутентификацию [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и Windows, то имя входа **sa** будет по умолчанию отключено.</span><span class="sxs-lookup"><span data-stu-id="28dba-180">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed using Windows Authentication mode and is later changed to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows Authentication mode, the **sa** login is initially disabled.</span></span> <span data-ttu-id="28dba-181">Это приводит к ошибке с состоянием 7: "Ошибка входа для пользователя sa". Чтобы включить имя для входа **sa**, выполните инструкции из статьи об [изменении режима проверки подлинности сервера](../../database-engine/configure-windows/change-server-authentication-mode.md).</span><span class="sxs-lookup"><span data-stu-id="28dba-181">This causes the state 7 error: "Login failed for user 'sa'." To enable the **sa** login, see [Change Server Authentication Mode](../../database-engine/configure-windows/change-server-authentication-mode.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="28dba-182">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="28dba-182">User Action</span></span>  
 <span data-ttu-id="28dba-183">При попытке подключения с использованием проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] убедитесь, что [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] настроен в режиме смешанной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="28dba-183">If you are trying to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, verify that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured in Mixed Authentication Mode.</span></span>  
  
 <span data-ttu-id="28dba-184">При попытке подключения с использованием проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] убедитесь, что имя входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] существует и введено верно.</span><span class="sxs-lookup"><span data-stu-id="28dba-184">If you are trying to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, verify that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login exists and that you have spelled it properly.</span></span>  
  
 <span data-ttu-id="28dba-185">При попытке подключения с использованием проверки подлинности Windows убедитесь, что выполнен правильный вход в нужный домен.</span><span class="sxs-lookup"><span data-stu-id="28dba-185">If you are trying to connect using Windows Authentication, verify that you are properly logged into the correct domain.</span></span>  
  
 <span data-ttu-id="28dba-186">Если ошибка указывает состояние 1, обратитесь к администратору [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28dba-186">If your error indicates state 1, contact your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administrator.</span></span>  
  
 <span data-ttu-id="28dba-187">Для подключения с учетными данными администратора запустите приложение **от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="28dba-187">If you are trying to connect using your administrator credentials, start you application by using the **Run as Administrator** option.</span></span> <span data-ttu-id="28dba-188">После подключения добавьте пользователя Windows в качестве отдельного имени входа.</span><span class="sxs-lookup"><span data-stu-id="28dba-188">When connected, add your Windows user as an individual login.</span></span>  
  
 <span data-ttu-id="28dba-189">Если компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] поддерживает автономные базы данных, подтвердите, что имя входа не удалено после преобразования в пользователя автономной базы данных.</span><span class="sxs-lookup"><span data-stu-id="28dba-189">If the [!INCLUDE[ssDE](../../includes/ssde-md.md)] supports contained databases, confirm that the login was not deleted after migration to a contained database user.</span></span>  
  
 <span data-ttu-id="28dba-190">Службы, запущенные от имени **NT AUTHORITY\NETWORK SERVICE**, должны использовать для локального соединения с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] аутентификацию по полному доменному имени компьютера.</span><span class="sxs-lookup"><span data-stu-id="28dba-190">When connecting locally to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], connections from services running under **NT AUTHORITY\NETWORK SERVICE** must authenticate using the computers fully qualified domain name.</span></span> <span data-ttu-id="28dba-191">Дополнительные сведения см. в разделе [Как использовать учетную запись сетевой службы для доступа к ресурсам в ASP.NET](https://msdn.microsoft.com/library/ff647402.aspx)</span><span class="sxs-lookup"><span data-stu-id="28dba-191">For more information, see [How To: Use the Network Service Account to Access Resources in ASP.NET](https://msdn.microsoft.com/library/ff647402.aspx)</span></span>  
  
  
