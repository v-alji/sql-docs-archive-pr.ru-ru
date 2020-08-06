---
title: Создание имени для входа | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.LOGIN.SERVERROLES.F1
- sql12.swb.login.databaseaccess.f1
- sql12.swb.login.general.f1
- sql12.swb.login.effectivepermissions.f1
- sql12.swb.login.status.f1
helpviewer_keywords:
- authentication [SQL Server], logins
- logins [SQL Server], creating
- creating logins with Management Studio
- Create login [SQL Server]
- SQL Server logins
ms.assetid: fb163e47-1546-4682-abaa-8c9494e9ddc7
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: e476880103a69ae016c6720f36e26ef884db6f5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730378"
---
# <a name="create-a-login"></a><span data-ttu-id="8c2b4-102">Создание имени входа</span><span class="sxs-lookup"><span data-stu-id="8c2b4-102">Create a Login</span></span>
  <span data-ttu-id="8c2b4-103">В этом разделе описано, как создать имя входа в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c2b4-103">This topic describes how to create a login in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="8c2b4-104">Имя входа представляет собой идентификатор пользователя или процесса, выполняющего соединение с экземпляром [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c2b4-104">A login is the identity of the person or process that is connecting to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="8c2b4-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="8c2b4-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8c2b4-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="8c2b4-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8c2b4-107">Фон</span><span class="sxs-lookup"><span data-stu-id="8c2b4-107">Background</span></span>](#Background)  
  
     [<span data-ttu-id="8c2b4-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="8c2b4-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8c2b4-109">**Создание имени входа**</span><span class="sxs-lookup"><span data-stu-id="8c2b4-109">**To create a login, using:**</span></span>  
  
     [<span data-ttu-id="8c2b4-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8c2b4-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8c2b4-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8c2b4-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="8c2b4-112">**Дальнейшие действия.**  [Действия, выполняемые после создания имени входа](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="8c2b4-112">**Follow Up:**  [Steps to take after you create a login](#FollowUp)</span></span>  
  
##  <a name="background"></a><a name="Background"></a> <span data-ttu-id="8c2b4-113">Историческая справка</span><span class="sxs-lookup"><span data-stu-id="8c2b4-113">Background</span></span>  
 <span data-ttu-id="8c2b4-114">Имя входа — это субъект безопасности, с помощью которого система безопасности может проверить подлинность лица или сущности.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-114">A login is a security principal, or an entity that can be authenticated by a secure system.</span></span> <span data-ttu-id="8c2b4-115">Имя входа необходимо пользователю для соединения с [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c2b4-115">Users need a login to connect to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8c2b4-116">Вы можете создать имя входа на основе участника Windows (например, пользователя или группы домена Windows), либо на основе пользователя, не являющегося участником Windows (например, имени входа [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="8c2b4-116">You can create a login based on a Windows principal (such as a domain user or a Windows domain group) or you can create a login that is not based on a Windows principal (such as an [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8c2b4-117">Для использования проверки подлинности компонент [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../../includes/ssde-md.md)] должен использовать режим смешанной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-117">To use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] must use mixed mode authentication.</span></span> <span data-ttu-id="8c2b4-118">Дополнительные сведения см. в разделе [Выбор режима проверки подлинности](../choose-an-authentication-mode.md).</span><span class="sxs-lookup"><span data-stu-id="8c2b4-118">For more information, see [Choose an Authentication Mode](../choose-an-authentication-mode.md).</span></span>  
  
 <span data-ttu-id="8c2b4-119">Как субъекты безопасности, разрешения могут быть предоставлены именам входов.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-119">As a security principal, permissions can be granted to logins.</span></span> <span data-ttu-id="8c2b4-120">Областью имени входа является весь компонент [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c2b4-120">The scope of a login is the whole [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span> <span data-ttu-id="8c2b4-121">Для подключения к определенной базе данных на экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] имя входа должно быть сопоставлено с пользователем базы данных.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-121">To connect to a specific database on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], a login must be mapped to a database user.</span></span> <span data-ttu-id="8c2b4-122">Разрешения внутри базы данных предоставляются и запрещаются для пользователя базы данных, а не имени входа.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-122">Permissions inside the database are granted and denied to the database user, not the login.</span></span> <span data-ttu-id="8c2b4-123">Разрешения, областью которых является весь экземпляр [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (например, разрешение `CREATE ENDPOINT`), могут предоставляться именам входов.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-123">Permissions that have the scope of the whole instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (for example, the `CREATE ENDPOINT` permission) can be granted to a login.</span></span>  
  
##  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8c2b4-124">безопасность</span><span class="sxs-lookup"><span data-stu-id="8c2b4-124">Security</span></span>  
  
### <a name="permissions"></a><span data-ttu-id="8c2b4-125">Разрешения</span><span class="sxs-lookup"><span data-stu-id="8c2b4-125">Permissions</span></span>  
 <span data-ttu-id="8c2b4-126">Необходимо разрешение `ALTER ANY LOGIN` или `ALTER LOGIN` на сервере.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-126">Requires `ALTER ANY LOGIN` or `ALTER LOGIN` permission on the server.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8c2b4-127">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8c2b4-127">Using SQL Server Management Studio</span></span>  
  
##### <a name="to-create-a-sql-server-login"></a><span data-ttu-id="8c2b4-128">Создание имени входа SQL Server</span><span class="sxs-lookup"><span data-stu-id="8c2b4-128">To create a SQL Server login</span></span>  
  
1.  <span data-ttu-id="8c2b4-129">В обозревателе объектов раскройте папку экземпляра сервера, в котором необходимо создать имя входа.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-129">In Object Explorer, expand the folder of the server instance in which you want to create the new login.</span></span>  
  
2.  <span data-ttu-id="8c2b4-130">Правой кнопкой мыши щелкните папку **Безопасность** и выберите пункт **Создать**, а затем — **Имя входа...** .</span><span class="sxs-lookup"><span data-stu-id="8c2b4-130">Right-click the **Security** folder, point to **New**, and select **Login...**.</span></span>  
  
3.  <span data-ttu-id="8c2b4-131">В диалоговом окне **Имя входа — создание** на странице **Общие** введите имя пользователя в поле **Имя для входа**.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-131">In the **Login - New** dialog box, on the **General** page, enter the name of a user in the **Login name** box.</span></span> <span data-ttu-id="8c2b4-132">Также можно нажать кнопку **Поиск...** , чтобы открыть диалоговое окно **Выбор пользователя или группы**.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-132">Alternately, click **Search...** to open the **Select User or Group** dialog box.</span></span>  
  
     <span data-ttu-id="8c2b4-133">Если нажата кнопка **Поиск...**</span><span class="sxs-lookup"><span data-stu-id="8c2b4-133">If you click **Search...**:</span></span>  
  
    1.  <span data-ttu-id="8c2b4-134">В разделе **Выбор этого типа объекта** щелкните **Типы объектов…** , чтобы открыть диалоговое окно **Типы объектов**, и выберите любой или все следующие варианты. **Встроенные субъекты безопасности**, **группы** и **пользователи**.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-134">Under **Select this object type**, click **Object Types...** to open the **Object Types** dialog box and select any or all of the following: **Built-in security principals**, **Groups**, and **Users**.</span></span> <span data-ttu-id="8c2b4-135">**Встроенные субъекты безопасности** и **Пользователи** выбираются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-135">**Built-in security principals** and **Users** are selected by default.</span></span> <span data-ttu-id="8c2b4-136">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-136">When finished, click **OK**.</span></span>  
  
    2.  <span data-ttu-id="8c2b4-137">В списке **Из этого расположения** щелкните **Расположение...** , чтобы открыть диалоговое окно **Расположение**, и выберите одно из следующих доступных расположений сервера.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-137">Under **From this location**, click **Locations...** to open the **Locations** dialog box and select one of the available server locations.</span></span> <span data-ttu-id="8c2b4-138">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-138">When finished, click **OK**.</span></span>  
  
    3.  <span data-ttu-id="8c2b4-139">В диалоговом окне **Введите имена объектов для выбора (примеры)** введите пользователя или имя группы, которые необходимо найти.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-139">Under **Enter the object name to select (examples)**, enter the user or group name that you want to find.</span></span> <span data-ttu-id="8c2b4-140">Дополнительные сведения см. в статье [Диалоговое окно выбора пользователей, компьютеров или групп](https://technet.microsoft.com/library/cc771712.aspx).</span><span class="sxs-lookup"><span data-stu-id="8c2b4-140">For more information, see [Select Users, Computers, or Groups Dialog Box](https://technet.microsoft.com/library/cc771712.aspx).</span></span>  
  
    4.  <span data-ttu-id="8c2b4-141">Нажмите кнопку **Дополнительно...** для настройки дополнительных параметров поиска.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-141">Click **Advanced...** for more advanced search options.</span></span> <span data-ttu-id="8c2b4-142">Дополнительные сведения см. в статье [Выбор диалогового окна "Пользователи", "Компьютеры" или "Группы" — страница "Дополнительно"](https://technet.microsoft.com/library/cc733110.aspx).</span><span class="sxs-lookup"><span data-stu-id="8c2b4-142">For more information, see [Select Users, Computers, or Groups Dialog Box - Advanced Page](https://technet.microsoft.com/library/cc733110.aspx).</span></span>  
  
    5.  <span data-ttu-id="8c2b4-143">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-143">Click **OK**.</span></span>  
  
4.  <span data-ttu-id="8c2b4-144">Чтобы создать имя входа на основе участника Windows, выберите параметр **Проверка подлинности Windows**.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-144">To create a login based on a Windows principal, select **Windows authentication**.</span></span> <span data-ttu-id="8c2b4-145">Это параметр выбирается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-145">This is the default selection.</span></span>  
  
5.  <span data-ttu-id="8c2b4-146">Чтобы создать имя входа, которое сохраняется в базе данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , выберите **Проверка подлинности SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-146">To create a login that is saved on a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database, select **SQL Server authentication**.</span></span>  
  
    1.  <span data-ttu-id="8c2b4-147">В поле **Пароль** введите пароль для нового пользователя.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-147">In the **Password** box, enter a password for the new user.</span></span> <span data-ttu-id="8c2b4-148">Повторно введите пароль в поле **Подтверждение пароля** .</span><span class="sxs-lookup"><span data-stu-id="8c2b4-148">Enter that password again into the **Confirm Password** box.</span></span>  
  
    2.  <span data-ttu-id="8c2b4-149">Если изменяется существующий пароль, выберите пункт **Указать старый пароль**и введите старый пароль в поле **Старый пароль** .</span><span class="sxs-lookup"><span data-stu-id="8c2b4-149">When changing an existing password, select **Specify old password**, and then type the old password in the **Old password** box.</span></span>  
  
    3.  <span data-ttu-id="8c2b4-150">Чтобы обеспечить использование паролей в соответствии с политиками паролей, выберите параметр **Требовать использование политики паролей**.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-150">To enforce password policy options for complexity and enforcement, select **Enforce password policy**.</span></span> <span data-ttu-id="8c2b4-151">Дополнительные сведения см. в разделе [Политика паролей](../password-policy.md).</span><span class="sxs-lookup"><span data-stu-id="8c2b4-151">For more information, see [Password Policy](../password-policy.md).</span></span> <span data-ttu-id="8c2b4-152">Это значение по умолчанию при выборе параметра **Проверка подлинности SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="8c2b4-152">This is a default option when **SQL Server authentication** is selected.</span></span>  
  
    4.  <span data-ttu-id="8c2b4-153">Чтобы обеспечить использование паролей в соответствии с политиками окончания срока действия паролей, выберите параметр **Задать срок окончания действия пароля**.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-153">To enforce password policy options for expiration, select **Enforce password expiration**.</span></span> <span data-ttu-id="8c2b4-154">Чтобы этот флажок был доступен, должен быть установлен параметр**Требовать использование политики паролей** .</span><span class="sxs-lookup"><span data-stu-id="8c2b4-154">**Enforce password policy** must be selected to enable this checkbox.</span></span> <span data-ttu-id="8c2b4-155">Это значение по умолчанию при выборе параметра **Проверка подлинности SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="8c2b4-155">This is a default option when **SQL Server authentication** is selected.</span></span>  
  
    5.  <span data-ttu-id="8c2b4-156">Чтобы пользователь мог создать новый пароль при первом входе в систему, выберите пункт **Пользователь должен сменить пароль при следующем входе**.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-156">To force the user to create a new password after the first time the login is used, select **User must change password at next login**.</span></span> <span data-ttu-id="8c2b4-157">Чтобы этот флажок был доступен, необходимо установить параметр**Принудительно применить срок окончания действия пароля** .</span><span class="sxs-lookup"><span data-stu-id="8c2b4-157">**Enforce password expiration** must be selected to enable this checkbox.</span></span> <span data-ttu-id="8c2b4-158">Это значение по умолчанию при выборе параметра **Проверка подлинности SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="8c2b4-158">This is a default option when **SQL Server authentication** is selected.</span></span>  
  
6.  <span data-ttu-id="8c2b4-159">Чтобы связать имя входа с изолированным сертификатом безопасности, выберите **Сопоставлен с сертификатом** , после чего выберите имя существующего сертификата из списка.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-159">To associate the login with a stand-alone security certificate, select **Mapped to certificate** and then select the name of an existing certificate from the list.</span></span>  
  
7.  <span data-ttu-id="8c2b4-160">Чтобы связать имя входа с изолированным асимметричным ключом, выберите **Сопоставлен с асимметричным ключом** , после чего выберите имя существующего ключа из списка.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-160">To associate the login with a stand-alone asymmetric key, select **Mapped to asymmetric key** to, and then select the name of an existing key from the list.</span></span>  
  
8.  <span data-ttu-id="8c2b4-161">Чтобы связать имя входа с сочетанием имени входа и пароля, выберите флажок **Сопоставлено с именем входа и паролем** , а затем либо выберите существующую комбинацию из списка, либо нажмите кнопку **Добавить** , чтобы создать новое сочетание.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-161">To associate the login with a security credential, select the **Mapped to Credential** check box, and then either select an existing credential from the list or click **Add** to create a new credential.</span></span> <span data-ttu-id="8c2b4-162">Чтобы удалить сопоставление с сочетанием имени входа и пароля, выберите сочетание из списка **Сопоставленные сочетания** и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-162">To remove a mapping to a security credential from the login, select the credential from **Mapped Credentials** and click **Remove**.</span></span> <span data-ttu-id="8c2b4-163">Дополнительные сведения об учетных данных см. в разделе [Учетные данные (компонент Database Engine)](credentials-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="8c2b4-163">For more information about credentials in general, see [Credentials &#40;Database Engine&#41;](credentials-database-engine.md).</span></span>  
  
9. <span data-ttu-id="8c2b4-164">В списке **База данных по умолчанию** выберите базу данных по умолчанию для нужного имени входа.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-164">From the **Default database** list, select a default database for the login.</span></span> <span data-ttu-id="8c2b4-165">По умолчанию этот параметр имеет значение**Master** .</span><span class="sxs-lookup"><span data-stu-id="8c2b4-165">**Master** is the default for this option.</span></span>  
  
10. <span data-ttu-id="8c2b4-166">В списке **Язык по умолчанию** выберите язык по умолчанию для входа.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-166">From the **Default language** list, select a default language for the login.</span></span>  
  
11. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="additional-options"></a><span data-ttu-id="8c2b4-167">Дополнительные параметры</span><span class="sxs-lookup"><span data-stu-id="8c2b4-167">Additional Options</span></span>  
 <span data-ttu-id="8c2b4-168">Диалоговое окно **Имя входа — создание** также предлагает варианты на четырех дополнительных страницах: **Роли сервера**, **Сопоставления пользователей**, **Защищаемые объекты** и **Состояние**.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-168">The **Login - New** dialog box also offers options on four additional pages: **Server Roles**, **User Mapping**, **Securables**, and **Status**.</span></span>  
  
### <a name="server-roles"></a><span data-ttu-id="8c2b4-169">Роли сервера</span><span class="sxs-lookup"><span data-stu-id="8c2b4-169">Server Roles</span></span>  
 <span data-ttu-id="8c2b4-170">На странице **Роли сервера** перечислены все возможные роли, которые могут быть назначены с новым именем входа.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-170">The **Server Roles** page lists all possible roles that can be assigned to the new login.</span></span> <span data-ttu-id="8c2b4-171">Доступны следующие варианты:</span><span class="sxs-lookup"><span data-stu-id="8c2b4-171">The following options are available:</span></span>  
  
 <span data-ttu-id="8c2b4-172">Флажок**bulkadmin**</span><span class="sxs-lookup"><span data-stu-id="8c2b4-172">**bulkadmin** check box</span></span>  
 <span data-ttu-id="8c2b4-173">Элементы предопределенной роли сервера **bulkadmin** могут выполнять инструкцию BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-173">Members of the **bulkadmin** fixed server role can run the BULK INSERT statement.</span></span>  
  
 <span data-ttu-id="8c2b4-174">Флажок**dbcreator**</span><span class="sxs-lookup"><span data-stu-id="8c2b4-174">**dbcreator** check box</span></span>  
 <span data-ttu-id="8c2b4-175">Члены предопределенной роли сервера **dbcreator** могут создавать, изменять, удалять и восстанавливать любые базы данных.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-175">Members of the **dbcreator** fixed server role can create, alter, drop, and restore any database.</span></span>  
  
 <span data-ttu-id="8c2b4-176">Флажок**diskadmin**</span><span class="sxs-lookup"><span data-stu-id="8c2b4-176">**diskadmin** check box</span></span>  
 <span data-ttu-id="8c2b4-177">Элементы предопределенной роли сервера **diskadmin** могут управлять дисковыми файлами.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-177">Members of the **diskadmin** fixed server role can manage disk files.</span></span>  
  
 <span data-ttu-id="8c2b4-178">Флажок**processadmin**</span><span class="sxs-lookup"><span data-stu-id="8c2b4-178">**processadmin** check box</span></span>  
 <span data-ttu-id="8c2b4-179">Элементы предопределенной роли сервера **processadmin** могут завершать процессы, запущенные в экземпляре компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c2b4-179">Members of the **processadmin** fixed server role can terminate processes running in an instance of the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="8c2b4-180">Флажок**Public**</span><span class="sxs-lookup"><span data-stu-id="8c2b4-180">**public** check box</span></span>  
 <span data-ttu-id="8c2b4-181">Все пользователи, группы и роли SQL Server по умолчанию принадлежат предопределенной роли сервера **public** .</span><span class="sxs-lookup"><span data-stu-id="8c2b4-181">All SQL Server users, groups, and roles belong to the **public** fixed server role by default.</span></span>  
  
 <span data-ttu-id="8c2b4-182">Флажок**securityadmin**</span><span class="sxs-lookup"><span data-stu-id="8c2b4-182">**securityadmin** check box</span></span>  
 <span data-ttu-id="8c2b4-183">Элементы предопределенной роли сервера **securityadmin** управляют именами входа и их свойствами.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-183">Members of the **securityadmin** fixed server role manage logins and their properties.</span></span> <span data-ttu-id="8c2b4-184">Они могут предоставлять, запрещать и отменять разрешения на уровне сервера (инструкции GRANT, DENY и REVOKE).</span><span class="sxs-lookup"><span data-stu-id="8c2b4-184">They can GRANT, DENY, and REVOKE server-level permissions.</span></span> <span data-ttu-id="8c2b4-185">Они также могут предоставлять, запрещать и отменять разрешения на уровне базы данных (инструкции GRANT, DENY и REVOKE).</span><span class="sxs-lookup"><span data-stu-id="8c2b4-185">They can also GRANT, DENY, and REVOKE database-level permissions.</span></span> <span data-ttu-id="8c2b4-186">Кроме того, они могут сбрасывать пароли для имен входа [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8c2b4-186">Additionally, they can reset passwords for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logins.</span></span>  
  
 <span data-ttu-id="8c2b4-187">Флажок**serveradmin**</span><span class="sxs-lookup"><span data-stu-id="8c2b4-187">**serveradmin** check box</span></span>  
 <span data-ttu-id="8c2b4-188">Элементы предопределенной роли сервера **serveradmin** могут изменять параметры конфигурации на уровне сервера, а также выключать сервер.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-188">Members of the **serveradmin** fixed server role can change server-wide configuration options and shut down the server.</span></span>  
  
 <span data-ttu-id="8c2b4-189">Флажок**setupadmin**</span><span class="sxs-lookup"><span data-stu-id="8c2b4-189">**setupadmin** check box</span></span>  
 <span data-ttu-id="8c2b4-190">Элементы предопределенной роли сервера **setupadmin** могут добавлять и удалять связанные серверы, а также выполнять некоторые системные хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-190">Members of the **setupadmin** fixed server role can add and remove linked servers, and they can execute some system stored procedures.</span></span>  
  
 <span data-ttu-id="8c2b4-191">Флажок**sysadmin**</span><span class="sxs-lookup"><span data-stu-id="8c2b4-191">**sysadmin** check box</span></span>  
 <span data-ttu-id="8c2b4-192">Элементы предопределенной роли сервера **sysadmin** могут выполнять любые действия в компоненте [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c2b4-192">Members of the **sysadmin** fixed server role can perform any activity in the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
### <a name="user-mapping"></a><span data-ttu-id="8c2b4-193">Сопоставление пользователей</span><span class="sxs-lookup"><span data-stu-id="8c2b4-193">User Mapping</span></span>  
 <span data-ttu-id="8c2b4-194">На странице **Сопоставление пользователей** приведен список всех возможных баз данных и ролей баз данных, которые могут применяться в момент входа.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-194">The **User Mapping** page lists all possible databases and the database role memberships on those databases that can be applied to the login.</span></span> <span data-ttu-id="8c2b4-195">Выбранные базы данных определят членство в ролях, которые доступны для этого имени входа.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-195">The databases selected determine the role memberships that are available for the login.</span></span> <span data-ttu-id="8c2b4-196">На этой странице доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-196">The following options are available on this page:</span></span>  
  
 <span data-ttu-id="8c2b4-197">**Пользователи, сопоставленные с этим именем входа**</span><span class="sxs-lookup"><span data-stu-id="8c2b4-197">**Users mapped to this login**</span></span>  
 <span data-ttu-id="8c2b4-198">Выберите базы данных, к которым может подключаться это имя входа.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-198">Select the databases that this login can access.</span></span> <span data-ttu-id="8c2b4-199">При выборе базы данных допустимые для нее роли отображаются в области **Членство в роли базы данных для:** _имя_базы_ данных_.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-199">When you select a database, its valid database roles are displayed in the **Database role membership for:** _database_name_ pane.</span></span>  
  
 <span data-ttu-id="8c2b4-200">**Схема**</span><span class="sxs-lookup"><span data-stu-id="8c2b4-200">**Map**</span></span>  
 <span data-ttu-id="8c2b4-201">Разрешает имени входа доступ к перечисленным ниже базам данных.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-201">Allow the login to access the databases listed below.</span></span>  
  
 <span data-ttu-id="8c2b4-202">**База данных**</span><span class="sxs-lookup"><span data-stu-id="8c2b4-202">**Database**</span></span>  
 <span data-ttu-id="8c2b4-203">Список баз данных, доступных на этом сервере.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-203">Lists the databases available on the server.</span></span>  
  
 <span data-ttu-id="8c2b4-204">**Пользователь**</span><span class="sxs-lookup"><span data-stu-id="8c2b4-204">**User**</span></span>  
 <span data-ttu-id="8c2b4-205">Укажите пользователя базы данных, сопоставляемого с этим именем входа.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-205">Specify a database user to map to the login.</span></span> <span data-ttu-id="8c2b4-206">По умолчанию, у пользователя базы данных такое же имя, как и имя входа.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-206">By default, the database user has the same name as the login.</span></span>  
  
 <span data-ttu-id="8c2b4-207">**Схема по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="8c2b4-207">**Default Schema**</span></span>  
 <span data-ttu-id="8c2b4-208">Указывает схему по умолчанию для данного пользователя.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-208">Specifies the default schema of the user.</span></span> <span data-ttu-id="8c2b4-209">При создании пользователя его схемой по умолчанию является **dbo**.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-209">When a user is first created, its default schema is **dbo**.</span></span> <span data-ttu-id="8c2b4-210">Можно указать схему по умолчанию, которая еще не существует.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-210">It is possible to specify a default schema that does not yet exist.</span></span> <span data-ttu-id="8c2b4-211">Нельзя указать схему по умолчанию для пользователя, сопоставленного с группой Windows, сертификатом или асимметричным ключом.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-211">You cannot specify a default schema for a user that is mapped to a Windows group, a certificate, or an asymmetric key.</span></span>  
  
 <span data-ttu-id="8c2b4-212">**Учетная запись гостя, включенная для:** _имя_базы_данных_</span><span class="sxs-lookup"><span data-stu-id="8c2b4-212">**Guest account enabled for:**  _database_name_</span></span>  
 <span data-ttu-id="8c2b4-213">Атрибут только для чтения, означающий, что учетная запись Guest включена в выбранной базе данных.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-213">Read-only attribute indicating whether the Guest account is enabled on the selected database.</span></span> <span data-ttu-id="8c2b4-214">Страница **Состояние** диалогового окна **Свойства входа в систему** для учетной записи Guest позволяет включать и отключать эту учетную запись.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-214">Use the **Status** page of the **Login Properties** dialog box of the Guest account to enable or disable the Guest account.</span></span>  
  
 <span data-ttu-id="8c2b4-215">**Членство в роли базы данных для:** _имя_базы_данных_</span><span class="sxs-lookup"><span data-stu-id="8c2b4-215">**Database role membership for:**  _database_name_</span></span>  
 <span data-ttu-id="8c2b4-216">Выберите роли для этого пользователя в указанной базе данных.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-216">Select the roles for the user in the specified database.</span></span> <span data-ttu-id="8c2b4-217">Все пользователи входят в роль **public** во всех базах данных, и удалить их оттуда нельзя.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-217">All users are members of the **public** role in every database and cannot be removed.</span></span> <span data-ttu-id="8c2b4-218">Дополнительные сведения о ролях баз данных см. в разделе [Роли уровня базы данных](database-level-roles.md).</span><span class="sxs-lookup"><span data-stu-id="8c2b4-218">For more information about database roles, see [Database-Level Roles](database-level-roles.md).</span></span>  
  
### <a name="securables"></a><span data-ttu-id="8c2b4-219">Защищаемые объекты</span><span class="sxs-lookup"><span data-stu-id="8c2b4-219">Securables</span></span>  
 <span data-ttu-id="8c2b4-220">На странице **Защищаемые объекты** перечислены все возможные защищаемые объекты и разрешения на эти объекты, которые могут быть предоставлены для имени входа.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-220">The **Securables** page lists all possible securables and the permissions on those securables that can be granted to the login.</span></span> <span data-ttu-id="8c2b4-221">На этой странице доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-221">The following options are available on this page:</span></span>  
  
 <span data-ttu-id="8c2b4-222">**Верхняя сетка**</span><span class="sxs-lookup"><span data-stu-id="8c2b4-222">**Upper Grid**</span></span>  
 <span data-ttu-id="8c2b4-223">Содержит один или несколько элементов, для которых могут быть установлены разрешения.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-223">Contains one or more items for which permissions can be set.</span></span> <span data-ttu-id="8c2b4-224">Отображаемые в верхней сетке столбцы меняются в зависимости от участника или защищаемого объекта.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-224">The columns that are displayed in the upper grid vary depending on the principal or securable.</span></span>  
  
 <span data-ttu-id="8c2b4-225">Добавление элементов в верхнюю сетку:</span><span class="sxs-lookup"><span data-stu-id="8c2b4-225">To add items to the upper grid:</span></span>  
  
1.  <span data-ttu-id="8c2b4-226">Нажмите кнопку **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-226">Click **Search**.</span></span>  
  
2.  <span data-ttu-id="8c2b4-227">В диалоговом окне **Добавление объектов** выберите один из следующих параметров: **определенные объекты..**., **все объекты типов...** или_server_name_ **сервера**.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-227">In the **Add Objects** dialog box, select one of the following options: **Specific objects...**, **All objects of the types...**, or **The server**_server_name_.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
    > [!NOTE]  
    >  <span data-ttu-id="8c2b4-228">Выбор **сервера**_server_name_ автоматически заполняет верхнюю сетку всеми защищаемыми объектами этих серверов.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-228">Selecting **The server**_server_name_ automatically fills the upper grid with all of that servers' securable objects.</span></span>  
  
3.  <span data-ttu-id="8c2b4-229">При выборе параметра **Конкретные объекты...**</span><span class="sxs-lookup"><span data-stu-id="8c2b4-229">If you select **Specific objects...**:</span></span>  
  
    1.  <span data-ttu-id="8c2b4-230">В диалоговом окне **Выбор объектов** в разделе **Выбрать эти типы объектов** нажмите кнопку **Типы объектов…** .</span><span class="sxs-lookup"><span data-stu-id="8c2b4-230">In the **Select Objects** dialog box, under **Select these object types**, click **Object Types...**.</span></span>  
  
    2.  <span data-ttu-id="8c2b4-231">В диалоговом окне **Выбор типов объектов** выберите любые или все из следующих типов объектов: **Конечные точки**, **Имена входа**, **Серверы**, **Группы доступности** и **Роли сервера**.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-231">In the **Select Object Types** dialog box, select any or all of the following object types: **Endpoints**, **Logins**, **Servers**, **Availability Groups**, and **Server roles**.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
    3.  <span data-ttu-id="8c2b4-232">В разделе **Введите имена объектов для выбора (примеры)** нажмите кнопку **Обзор...** .</span><span class="sxs-lookup"><span data-stu-id="8c2b4-232">Under **Enter the object names to select (examples)**, click **Browse...**.</span></span>  
  
    4.  <span data-ttu-id="8c2b4-233">В диалоговом окне **Просмотр объектов** , выберите доступные объекты тех типов, которые вы выбрали в диалоговом окне **Выбранные типы объектов** , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-233">In the **Browse for Objects** dialog box, select any of the available objects of the type that you selected in the **Select Object Types** dialog box, and then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="8c2b4-234">В диалоговом окне **Выбор объектов** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-234">In the **Select Objects** dialog box, click **OK**.</span></span>  
  
4.  <span data-ttu-id="8c2b4-235">При выборе параметра **Все объекты типов…** в диалоговом окне **Выбор типов объектов** выберите любые или все из следующих типов объектов: **Конечные точки**, **Имена входа**, **Серверы**, **Группы доступности** и **Роли сервера**.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-235">If you select **All objects of the types...**, in the **Select Object Types** dialog box, select any or all of the following object types: **Endpoints**, **Logins**, **Servers**, **Availability Groups**, and **Server roles**.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
 <span data-ttu-id="8c2b4-236">**имя**;</span><span class="sxs-lookup"><span data-stu-id="8c2b4-236">**Name**</span></span>  
 <span data-ttu-id="8c2b4-237">Имя каждого участника или защищаемого объекта, добавляемого в сетку.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-237">The name of each principal or securable that is added to the grid.</span></span>  
  
 <span data-ttu-id="8c2b4-238">**Тип**</span><span class="sxs-lookup"><span data-stu-id="8c2b4-238">**Type**</span></span>  
 <span data-ttu-id="8c2b4-239">Описывает тип каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-239">Describes the type of each item.</span></span>  
  
 <span data-ttu-id="8c2b4-240">**Вкладка «Явное»**</span><span class="sxs-lookup"><span data-stu-id="8c2b4-240">**Explicit Tab**</span></span>  
 <span data-ttu-id="8c2b4-241">Содержит возможные разрешения для защищаемого объекта, выбранного в верхней сетке.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-241">Lists the possible permissions for the securable that are selected in the upper grid.</span></span> <span data-ttu-id="8c2b4-242">Не все эти параметры доступны для всех явно указанных разрешений.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-242">Not all options are available for all explicit permissions.</span></span>  
  
 <span data-ttu-id="8c2b4-243">**Разрешения**</span><span class="sxs-lookup"><span data-stu-id="8c2b4-243">**Permissions**</span></span>  
 <span data-ttu-id="8c2b4-244">Имя разрешения.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-244">The name of the permission.</span></span>  
  
 <span data-ttu-id="8c2b4-245">**Grantor**</span><span class="sxs-lookup"><span data-stu-id="8c2b4-245">**Grantor**</span></span>  
 <span data-ttu-id="8c2b4-246">Участник, предоставивший разрешение.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-246">The principal that granted the permission.</span></span>  
  
 <span data-ttu-id="8c2b4-247">**Право предоставил**</span><span class="sxs-lookup"><span data-stu-id="8c2b4-247">**Grant**</span></span>  
 <span data-ttu-id="8c2b4-248">Выберите, чтобы предоставить имени входа данное разрешение.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-248">Select to grant this permission to the login.</span></span> <span data-ttu-id="8c2b4-249">Снимите флажок, чтобы отменить это разрешение.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-249">Clear to revoke this permission.</span></span>  
  
 <span data-ttu-id="8c2b4-250">**Право передачи**</span><span class="sxs-lookup"><span data-stu-id="8c2b4-250">**With Grant**</span></span>  
 <span data-ttu-id="8c2b4-251">Отражает состояние параметра WITH GRANT для разрешения, указанного в списке.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-251">Reflects the state of the WITH GRANT option for the listed permission.</span></span> <span data-ttu-id="8c2b4-252">Поле доступно только для чтения.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-252">This box is read-only.</span></span> <span data-ttu-id="8c2b4-253">Для применения данного разрешения используйте инструкцию [GRANT](/sql/t-sql/statements/grant-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="8c2b4-253">To apply this permission, use the [GRANT](/sql/t-sql/statements/grant-transact-sql) statement.</span></span>  
  
 <span data-ttu-id="8c2b4-254">**Запретить**</span><span class="sxs-lookup"><span data-stu-id="8c2b4-254">**Deny**</span></span>  
 <span data-ttu-id="8c2b4-255">Выберите, чтобы запретить имени входа в данном разрешении.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-255">Select to deny this permission to the login.</span></span> <span data-ttu-id="8c2b4-256">Снимите флажок, чтобы отменить это разрешение.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-256">Clear to revoke this permission.</span></span>  
  
### <a name="status"></a><span data-ttu-id="8c2b4-257">Состояние</span><span class="sxs-lookup"><span data-stu-id="8c2b4-257">Status</span></span>  
 <span data-ttu-id="8c2b4-258">На странице **Состояние** приведен список некоторых параметров проверки подлинности и авторизации, которые можно настроить для выбранного имени входа [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8c2b4-258">The **Status** page lists some of the authentication and authorization options that can be configured on the selected [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login.</span></span>  
  
 <span data-ttu-id="8c2b4-259">На этой странице доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-259">The following options are available on this page:</span></span>  
  
 <span data-ttu-id="8c2b4-260">**Разрешение на подключение к ядру СУБД**</span><span class="sxs-lookup"><span data-stu-id="8c2b4-260">**Permission to connect to database engine**</span></span>  
 <span data-ttu-id="8c2b4-261">При работе с этим параметром выбранное имя входа нужно представлять как участника, которому можно предоставить или не предоставить разрешение на защищаемый объект.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-261">When you work with this setting, you should think of the selected login as a principal that can be granted or denied permission on a securable.</span></span>  
  
 <span data-ttu-id="8c2b4-262">Выберите **Предоставить** , чтобы предоставить имени входа разрешение CONNECT SQL.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-262">Select **Grant** to grant CONNECT SQL permission to the login.</span></span> <span data-ttu-id="8c2b4-263">Выберите **Запретить** , чтобы запретить имени входа разрешение CONNECT SQL.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-263">Select **Deny** to deny CONNECT SQL to the login.</span></span>  
  
 <span data-ttu-id="8c2b4-264">**Имя входа**</span><span class="sxs-lookup"><span data-stu-id="8c2b4-264">**Login**</span></span>  
 <span data-ttu-id="8c2b4-265">При работе с этим параметром выбранное имя входа нужно представлять как запись в таблице.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-265">When you work with this setting, you should think of the selected login as a record in a table.</span></span> <span data-ttu-id="8c2b4-266">Ей будут присваиваться приведенные здесь значения.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-266">Changes to the values listed here will be applied to the record.</span></span>  
  
 <span data-ttu-id="8c2b4-267">Отключенное имя входа продолжает существовать в виде записи.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-267">A login that has been disabled continues to exist as a record.</span></span> <span data-ttu-id="8c2b4-268">Но если имя входа пытается соединиться с [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], оно не будет авторизовано.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-268">But if it tries to connect to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the login will not be authenticated.</span></span>  
  
 <span data-ttu-id="8c2b4-269">Выберите этот параметр для включения или отключения имени входа.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-269">Select this option to enable or disable this login.</span></span> <span data-ttu-id="8c2b4-270">Этот параметр использует инструкцию ALTER LOGIN с параметром ENABLE или DISABLE.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-270">This option uses the ALTER LOGIN statement with the either ENABLE or DISABLE option.</span></span>  
  
 <span data-ttu-id="8c2b4-271">**Проверка подлинности SQL Server**</span><span class="sxs-lookup"><span data-stu-id="8c2b4-271">**SQL Server Authentication**</span></span>  
 <span data-ttu-id="8c2b4-272">Флажок **Имя входа заблокировано** доступен только в том случае, если выбранное имя входа использует проверку подлинности [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] и заблокировано. Настройка доступна только для чтения.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-272">The check box **Login is locked out** is only available if the selected login connects using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication and the login has been locked out. This setting is read-only.</span></span> <span data-ttu-id="8c2b4-273">Чтобы разблокировать блокированное имя входа, выполните инструкцию ALTER LOGIN с параметром UNLOCK.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-273">To unlock a login that is locked out, execute ALTER LOGIN with the UNLOCK option.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8c2b4-274">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8c2b4-274">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-login-using-windows-authentication"></a><span data-ttu-id="8c2b4-275">Создание имени входа при использовании проверки подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="8c2b4-275">To create a login using Windows Authentication</span></span>  
  
1.  <span data-ttu-id="8c2b4-276">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c2b4-276">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8c2b4-277">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-277">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8c2b4-278">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-278">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Create a login for SQL Server by specifying a server name and a Windows domain account name.  
  
    CREATE LOGIN [<domainName>\<loginName>] FROM WINDOWS;  
    GO  
  
    ```  
  
#### <a name="to-create-a-login-using-sql-server-authentication"></a><span data-ttu-id="8c2b4-279">Создание имени входа при использовании проверки подлинности SQL Server</span><span class="sxs-lookup"><span data-stu-id="8c2b4-279">To create a login using SQL Server Authentication</span></span>  
  
1.  <span data-ttu-id="8c2b4-280">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c2b4-280">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8c2b4-281">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-281">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8c2b4-282">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-282">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates the user "shcooper" for SQL Server using the security credential "RestrictedFaculty"   
    -- The user login starts with the password "Baz1nga," but that password must be changed after the first login.  
  
    CREATE LOGIN shcooper   
       WITH PASSWORD = 'Baz1nga' MUST_CHANGE,  
       CREDENTIAL = RestrictedFaculty;  
    GO  
  
    ```  
  
 <span data-ttu-id="8c2b4-283">Дополнительные сведения см. в разделе [CREATE LOGIN (Transact-SQL)](/sql/t-sql/statements/create-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8c2b4-283">For more information, see [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span></span>  
  
##  <a name="follow-up-steps-to-take-after-you-create-a-login"></a><a name="FollowUp"></a> <span data-ttu-id="8c2b4-284">Дальнейшие действия. Действия, выполняемые после создания имени входа</span><span class="sxs-lookup"><span data-stu-id="8c2b4-284">Follow Up: Steps to take after you create a login</span></span>  
 <span data-ttu-id="8c2b4-285">После создания имени входа его можно использовать для соединения с [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], но у него может не быть разрешений, необходимых для выполнения требуемых задач.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-285">After creating a login, the login can connect to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], but does not necessarily have sufficient permission to perform any useful work.</span></span> <span data-ttu-id="8c2b4-286">В следующем списке представлены ссылки на основные действия имени входа.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-286">The following list provides links to common login actions.</span></span>  
  
-   <span data-ttu-id="8c2b4-287">Дополнительные сведения о присоединении имени входа к роли см. в разделе [Присоединение к роли](join-a-role.md).</span><span class="sxs-lookup"><span data-stu-id="8c2b4-287">To have the login join a role, see [Join a Role](join-a-role.md).</span></span>  
  
-   <span data-ttu-id="8c2b4-288">Дополнительные сведения об авторизации имени входа для использования базы данных см. в разделе [Создание пользователя базы данных](../authentication-access/create-a-database-user.md).</span><span class="sxs-lookup"><span data-stu-id="8c2b4-288">To authorize a login to use a database, see [Create a Database User](../authentication-access/create-a-database-user.md).</span></span>  
  
-   <span data-ttu-id="8c2b4-289">Сведения о предоставлении разрешения для имени входа см. в разделе [Предоставление разрешения для участника](grant-a-permission-to-a-principal.md).</span><span class="sxs-lookup"><span data-stu-id="8c2b4-289">To grant a permission to a login, see [Grant a Permission to a Principal](grant-a-permission-to-a-principal.md).</span></span>  
  
  
