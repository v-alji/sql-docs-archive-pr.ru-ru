---
title: Создание пользователя базы данных | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.DATABASEUSER.GENERAL.F1
- sql12.swb.user.securables.f1
helpviewer_keywords:
- database users, creating
- creating users with Management Studio
- mapping users
- users [SQL Server], creating
- database user additions [SQL Server]
- database users, mapping
- CREATE USER [Management Studio]
- users [SQL Server], adding
- mapping database users
ms.assetid: 782798d3-9552-4514-9f58-e87be4b264e4
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 97fc758c754f5fc8803e988d55147670fc3ff45b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730382"
---
# <a name="create-a-database-user"></a><span data-ttu-id="9f13c-102">Создание пользователя базы данных</span><span class="sxs-lookup"><span data-stu-id="9f13c-102">Create a Database User</span></span>
  <span data-ttu-id="9f13c-103">В этом разделе описано, как в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] создать пользователя базы данных, сопоставленного с именем входа, с помощью среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f13c-103">This topic describes how to create a database user mapped to a login in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="9f13c-104">Пользователь базы данных — это идентификатор имени входа при подключении к базе данных.</span><span class="sxs-lookup"><span data-stu-id="9f13c-104">The database user is the identity of the login when it is connected to a database.</span></span> <span data-ttu-id="9f13c-105">Имя пользователя базы данных может совпадать с именем входа, но это не является обязательным требованием.</span><span class="sxs-lookup"><span data-stu-id="9f13c-105">The database user can use the same name as the login, but that is not required.</span></span> <span data-ttu-id="9f13c-106">Этот раздел предполагает наличие имени входа в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f13c-106">This topic assumes that a login already exists in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9f13c-107">Дополнительные сведения о создании имени входа см. в разделе [Создание имени входа](create-a-login.md).</span><span class="sxs-lookup"><span data-stu-id="9f13c-107">For information about how to create a login, see [Create a Login](create-a-login.md).</span></span>  
  
 <span data-ttu-id="9f13c-108">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="9f13c-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9f13c-109">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="9f13c-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9f13c-110">Фон</span><span class="sxs-lookup"><span data-stu-id="9f13c-110">Background</span></span>](#Restrictions)  
  
     [<span data-ttu-id="9f13c-111">Безопасность</span><span class="sxs-lookup"><span data-stu-id="9f13c-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9f13c-112">**Создание пользователя базы данных с помощью:**</span><span class="sxs-lookup"><span data-stu-id="9f13c-112">**To create a database user, using:**</span></span>  
  
     [<span data-ttu-id="9f13c-113">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9f13c-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9f13c-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9f13c-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9f13c-115">Перед началом</span><span class="sxs-lookup"><span data-stu-id="9f13c-115">Before You Begin</span></span>  
  
###  <a name="background"></a><a name="Restrictions"></a> <span data-ttu-id="9f13c-116">Историческая справка</span><span class="sxs-lookup"><span data-stu-id="9f13c-116">Background</span></span>  
 <span data-ttu-id="9f13c-117">Пользователь является субъектом безопасности уровня базы данных.</span><span class="sxs-lookup"><span data-stu-id="9f13c-117">A user is a database level security principal.</span></span> <span data-ttu-id="9f13c-118">Для соединения с базой данных имя входа должно быть сопоставлено с пользователем базы данных.</span><span class="sxs-lookup"><span data-stu-id="9f13c-118">Logins must be mapped to a database user to connect to a database.</span></span> <span data-ttu-id="9f13c-119">Имя входа может быть сопоставлено с различными базами данных в качестве разных пользователей, но в каждой базе данных ему может быть сопоставлен только один пользователь.</span><span class="sxs-lookup"><span data-stu-id="9f13c-119">A login can be mapped to different databases as different users but can only be mapped as one user in each database.</span></span> <span data-ttu-id="9f13c-120">В частично автономной базе данных можно создать пользователя, не имеющего имени входа.</span><span class="sxs-lookup"><span data-stu-id="9f13c-120">In a partially contained database, a user can be created that does not have a login.</span></span> <span data-ttu-id="9f13c-121">Дополнительные сведения о пользователях автономной базы данных см. в статье [CREATE USER (Transact-SQL)](/sql/t-sql/statements/create-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9f13c-121">For more information about contained database users, see [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span></span> <span data-ttu-id="9f13c-122">Если в базе данных включена учетная запись гостя, то под именем входа, не сопоставленным с пользователем базы данных, можно войти от пользователя guest.</span><span class="sxs-lookup"><span data-stu-id="9f13c-122">If the guest user in a database is enabled, a login that is not mapped to a database user can enter the database as the guest user.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9f13c-123">Как правило, пользователь guest отключен.</span><span class="sxs-lookup"><span data-stu-id="9f13c-123">The guest user is ordinarily disabled.</span></span> <span data-ttu-id="9f13c-124">Не используйте пользователя guest без крайней необходимости.</span><span class="sxs-lookup"><span data-stu-id="9f13c-124">Do not enable the guest user unless it is necessary.</span></span>  
  
 <span data-ttu-id="9f13c-125">Как субъектам безопасности, пользователям могут предоставляться разрешения.</span><span class="sxs-lookup"><span data-stu-id="9f13c-125">As a security principal, permissions can be granted to users.</span></span> <span data-ttu-id="9f13c-126">Областью действия пользователя является база данных.</span><span class="sxs-lookup"><span data-stu-id="9f13c-126">The scope of a user is the database.</span></span> <span data-ttu-id="9f13c-127">Для подключения к определенной базе данных на экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] имя входа должно быть сопоставлено с пользователем базы данных.</span><span class="sxs-lookup"><span data-stu-id="9f13c-127">To connect to a specific database on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], a login must be mapped to a database user.</span></span> <span data-ttu-id="9f13c-128">Разрешения внутри базы данных предоставляются и запрещаются для пользователя базы данных, а не имени входа.</span><span class="sxs-lookup"><span data-stu-id="9f13c-128">Permissions inside the database are granted and denied to the database user, not the login.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9f13c-129">безопасность</span><span class="sxs-lookup"><span data-stu-id="9f13c-129">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9f13c-130">Permissions</span><span class="sxs-lookup"><span data-stu-id="9f13c-130">Permissions</span></span>  
 <span data-ttu-id="9f13c-131">Необходимо разрешение `ALTER ANY USER` на базу данных.</span><span class="sxs-lookup"><span data-stu-id="9f13c-131">Requires `ALTER ANY USER` permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9f13c-132">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9f13c-132">Using SQL Server Management Studio</span></span>  
  
##### <a name="to-create-a-database-user"></a><span data-ttu-id="9f13c-133">Создание пользователя базы данных</span><span class="sxs-lookup"><span data-stu-id="9f13c-133">To create a database user</span></span>  
  
1.  <span data-ttu-id="9f13c-134">В обозревателе объектов раскройте папку **Базы данных** .</span><span class="sxs-lookup"><span data-stu-id="9f13c-134">In Object Explorer, expand the **Databases** folder.</span></span>  
  
2.  <span data-ttu-id="9f13c-135">Разверните базу данных, в которой создается новый пользователь базы данных.</span><span class="sxs-lookup"><span data-stu-id="9f13c-135">Expand the database in which to create the new database user.</span></span>  
  
3.  <span data-ttu-id="9f13c-136">Щелкните правой кнопкой мыши папку **Безопасность**, выберите пункт **Создать**, а затем **Пользователь...** .</span><span class="sxs-lookup"><span data-stu-id="9f13c-136">Right-click the **Security** folder, point to **New**, and select **User...**.</span></span>  
  
4.  <span data-ttu-id="9f13c-137">В диалоговом окне **Создание пользователя базы данных** на странице **Общие** выберите один из следующих типов пользователей из списка **Тип пользователя** : **пользователь SQL с именем для входа**, **пользователь SQL без имени входа**, пользователь, сопоставленный с **сертификатом**, **пользователь, сопоставленный с асимметричным ключом**или **пользователь Windows**.</span><span class="sxs-lookup"><span data-stu-id="9f13c-137">In the **Database User - New** dialog box, on the **General** page, select one of the following user types from the **User type** list: **SQL user with login**, **SQL user without login**, **User mapped to a certificate**, **User mapped to an asymmetric key**, or **Windows user**.</span></span>  
  
5.  <span data-ttu-id="9f13c-138">В поле **Имя пользователя** введите имя для нового пользователя.</span><span class="sxs-lookup"><span data-stu-id="9f13c-138">In the **User name** box, enter a name for the new user.</span></span> <span data-ttu-id="9f13c-139">Если выбрать элемент **Пользователь Windows** в списке **Тип пользователя**, вы можете также щелкнуть многоточие **(...)** и открыть диалоговое окно **Выбор пользователя или группы**.</span><span class="sxs-lookup"><span data-stu-id="9f13c-139">If you have chosen **Windows user** from the **User type** list, you can also click the ellipsis **(...)** to open the **Select User or Group** dialog box.</span></span>  
  
6.  <span data-ttu-id="9f13c-140">В поле **Имя входа** введите имя входа для пользователя.</span><span class="sxs-lookup"><span data-stu-id="9f13c-140">In the **Login name** box, enter the login for the user.</span></span> <span data-ttu-id="9f13c-141">Также можно щелкнуть многоточие **(...)** , чтобы открыть диалоговое окно **Выбор имени входа**.</span><span class="sxs-lookup"><span data-stu-id="9f13c-141">Alternately, click the ellipsis **(...)** to open the **Select Login** dialog box.</span></span> <span data-ttu-id="9f13c-142">**Имя входа** доступно, если выбрать элемент **SQL-пользователь с именем входа** или **Пользователь Windows** в списке **Тип пользователя** .</span><span class="sxs-lookup"><span data-stu-id="9f13c-142">**Login name** is available if you select either **SQL user with login** or **Windows user** from the **User type** list.</span></span>  
  
7.  <span data-ttu-id="9f13c-143">Укажите схему, которая будет владеть объектами, созданными пользователем, в поле **Схема по умолчанию** .</span><span class="sxs-lookup"><span data-stu-id="9f13c-143">In the **Default schema** box, specifies the schema that will own objects created by this user.</span></span> <span data-ttu-id="9f13c-144">Также можно щелкнуть многоточие **(...)** , чтобы открыть диалоговое окно **Выбор схемы**.</span><span class="sxs-lookup"><span data-stu-id="9f13c-144">Alternately, click the ellipsis **(...)** to open the **Select Schema** dialog box.</span></span> <span data-ttu-id="9f13c-145">**Схема по умолчанию** доступна, если выбрать элемент **SQL-пользователь с именем входа**, **SQL-пользователь без имени входа**или **Пользователь Windows** в списке **Тип пользователя** .</span><span class="sxs-lookup"><span data-stu-id="9f13c-145">**Default schema** is available if you select either **SQL user with login**, **SQL user without login**, or **Windows user** from the **User type** list.</span></span>  
  
8.  <span data-ttu-id="9f13c-146">Введите сертификат для пользователя базы данных в поле **Имя сертификата** .</span><span class="sxs-lookup"><span data-stu-id="9f13c-146">In the **Certificate name** box, enter the certificate to be used for the database user.</span></span> <span data-ttu-id="9f13c-147">Также можно щелкнуть многоточие **(...)** , чтобы открыть диалоговое окно **Выбор сертификата**.</span><span class="sxs-lookup"><span data-stu-id="9f13c-147">Alternately, click the ellipsis **(...)** to open the **Select Certificate** dialog box.</span></span> <span data-ttu-id="9f13c-148">**Имя сертификата** доступно, если выбрать элемент **Пользователь, сопоставленный с сертификатом** в списке **Тип пользователя** .</span><span class="sxs-lookup"><span data-stu-id="9f13c-148">**Certificate name** is available if you select **User mapped to a certificate** from the **User type** list.</span></span>  
  
9. <span data-ttu-id="9f13c-149">Введите ключ для пользователя базы данных в поле **Имя асимметричного ключа**  .</span><span class="sxs-lookup"><span data-stu-id="9f13c-149">In the **Asymmetric key name**  box, enter the key to be used for the database user.</span></span> <span data-ttu-id="9f13c-150">Также можно щелкнуть многоточие **(...)** , чтобы открыть диалоговое окно **Выбор асимметричного ключа**.</span><span class="sxs-lookup"><span data-stu-id="9f13c-150">Alternately, click the ellipsis **(...)** to open the **Select Asymmetric Key** dialog box.</span></span> <span data-ttu-id="9f13c-151">**Имя асимметричного ключа** доступно, если выбрать элемент **Пользователь, сопоставленный с асимметричным ключом** в списке **Тип пользователя** .</span><span class="sxs-lookup"><span data-stu-id="9f13c-151">**Asymmetric key name** is available if you select **User mapped to an asymmetric key** from the **User type** list.</span></span>  
  
10. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="additional-options"></a><span data-ttu-id="9f13c-152">Дополнительные параметры</span><span class="sxs-lookup"><span data-stu-id="9f13c-152">Additional Options</span></span>  
 <span data-ttu-id="9f13c-153">Диалоговое окно **Пользователь базы данных — создание** также содержит параметры на четырех дополнительных страницах: **Собственные схемы**, **Членство**, **Защищаемые объекты** и **Расширенные свойства**.</span><span class="sxs-lookup"><span data-stu-id="9f13c-153">The **Database User - New** dialog box also offers options on four additional pages: **Owned Schemas**, **Membership**, **Securables**, and **Extended Properties**.</span></span>  
  
-   <span data-ttu-id="9f13c-154">На странице **Собственные схемы** перечислены все возможные схемы, которые принадлежат новому пользователю базы данных.</span><span class="sxs-lookup"><span data-stu-id="9f13c-154">The **Owned Schemas** page lists all possible schemas that can be owned by the new database user.</span></span> <span data-ttu-id="9f13c-155">Чтобы добавить схему для пользователя базы данных или удалить ее, на вкладке **Схемы, принадлежащие этому пользователю**установите или снимите флажки для соответствующей схемы.</span><span class="sxs-lookup"><span data-stu-id="9f13c-155">To add schemas to or remove them from a database user, under **Schemas owned by this user**, select or clear the check boxes next to the schemas.</span></span>  
  
-   <span data-ttu-id="9f13c-156">На странице **Членство** приведен список всех ролей, к которым может принадлежать новый пользователь базы данных.</span><span class="sxs-lookup"><span data-stu-id="9f13c-156">The **Membership** page lists all possible database membership roles that can be owned by the new database user.</span></span> <span data-ttu-id="9f13c-157">Чтобы добавить роль для пользователя базы данных или удалить ее, на вкладке **Членство ролей базы данных**установите или снимите флажки для соответствующей роли.</span><span class="sxs-lookup"><span data-stu-id="9f13c-157">To add roles to or remove them from a database user, under **Database role membership**, select or clear the check boxes next to the roles.</span></span>  
  
-   <span data-ttu-id="9f13c-158">На странице **Защищаемые объекты** перечислены все возможные защищаемые объекты и разрешения на эти объекты, которые могут быть предоставлены для имени входа.</span><span class="sxs-lookup"><span data-stu-id="9f13c-158">The **Securables** page lists all possible securables and the permissions on those securables that can be granted to the login.</span></span>  
  
-   <span data-ttu-id="9f13c-159">Страница **Расширенные свойства** позволяет добавлять пользовательские свойства пользователям базы данных.</span><span class="sxs-lookup"><span data-stu-id="9f13c-159">The **Extended properties** page allows you to add custom properties to database users.</span></span> <span data-ttu-id="9f13c-160">На этой странице доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="9f13c-160">The following options are available on this page.</span></span>  
  
     <span data-ttu-id="9f13c-161">**База данных**</span><span class="sxs-lookup"><span data-stu-id="9f13c-161">**Database**</span></span>  
     <span data-ttu-id="9f13c-162">Отображает имя выбранной базы данных.</span><span class="sxs-lookup"><span data-stu-id="9f13c-162">Displays the name of the selected database.</span></span> <span data-ttu-id="9f13c-163">Это поле доступно только для чтения.</span><span class="sxs-lookup"><span data-stu-id="9f13c-163">This field is read-only.</span></span>  
  
     <span data-ttu-id="9f13c-164">**Параметры сортировки**</span><span class="sxs-lookup"><span data-stu-id="9f13c-164">**Collation**</span></span>  
     <span data-ttu-id="9f13c-165">Отображает параметры сортировки, используемые для выбранной базы данных.</span><span class="sxs-lookup"><span data-stu-id="9f13c-165">Displays the collation used for the selected database.</span></span> <span data-ttu-id="9f13c-166">Это поле доступно только для чтения.</span><span class="sxs-lookup"><span data-stu-id="9f13c-166">This field is read-only.</span></span>  
  
     <span data-ttu-id="9f13c-167">**Свойства**</span><span class="sxs-lookup"><span data-stu-id="9f13c-167">**Properties**</span></span>  
     <span data-ttu-id="9f13c-168">Просмотрите или укажите расширенные свойства объекта.</span><span class="sxs-lookup"><span data-stu-id="9f13c-168">View or specify the extended properties for the object.</span></span> <span data-ttu-id="9f13c-169">Каждое расширенное свойство состоит из пары имя/значение метаданных, связанных с объектом.</span><span class="sxs-lookup"><span data-stu-id="9f13c-169">Each extended property consists of a name/value pair of metadata associated with the object.</span></span>  
  
     <span data-ttu-id="9f13c-170">**Кнопка с многоточием (...)**</span><span class="sxs-lookup"><span data-stu-id="9f13c-170">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="9f13c-171">Нажмите многоточие **(...)** рядом с полем **Значение**, чтобы открыть диалоговое окно **Значение для расширенного свойства**.</span><span class="sxs-lookup"><span data-stu-id="9f13c-171">Click the ellipsis **(...)** after **Value** to open the **Value for Extended Property** dialog box.</span></span> <span data-ttu-id="9f13c-172">Введите или просмотрите значение расширенного свойства в этом более просторном окне.</span><span class="sxs-lookup"><span data-stu-id="9f13c-172">Type or view the value of the extended property in this larger location.</span></span> <span data-ttu-id="9f13c-173">Дополнительные сведения см. в разделе [Диалоговое окно «Значение для расширенного свойства»](../../databases/value-for-extended-property-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="9f13c-173">For more information, see [Value for Extended Property Dialog Box](../../databases/value-for-extended-property-dialog-box.md).</span></span>  
  
     <span data-ttu-id="9f13c-174">**Удаление**</span><span class="sxs-lookup"><span data-stu-id="9f13c-174">**Delete**</span></span>  
     <span data-ttu-id="9f13c-175">Удаляет выбранное расширенное свойство.</span><span class="sxs-lookup"><span data-stu-id="9f13c-175">Removes the selected extended property.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9f13c-176">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9f13c-176">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-database-user"></a><span data-ttu-id="9f13c-177">Создание пользователя базы данных</span><span class="sxs-lookup"><span data-stu-id="9f13c-177">To create a database user</span></span>  
  
1.  <span data-ttu-id="9f13c-178">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f13c-178">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9f13c-179">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="9f13c-179">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9f13c-180">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="9f13c-180">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates the login AbolrousHazem with password '340$Uuxwp7Mcxo7Khy'.  
    CREATE LOGIN AbolrousHazem   
        WITH PASSWORD = '340$Uuxwp7Mcxo7Khy';  
    GO  
  
    -- Creates a database user for the login created above.  
    CREATE USER AbolrousHazem FOR LOGIN AbolrousHazem;  
    GO  
    ```  
  
 <span data-ttu-id="9f13c-181">Дополнительные сведения см. в разделе [CREATE USER (Transact-SQL)](/sql/t-sql/statements/create-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9f13c-181">For more information, see [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f13c-182">См. также:</span><span class="sxs-lookup"><span data-stu-id="9f13c-182">See Also</span></span>  
 [<span data-ttu-id="9f13c-183">Участники (компонент Database Engine)</span><span class="sxs-lookup"><span data-stu-id="9f13c-183">Principals &#40;Database Engine&#41;</span></span>](principals-database-engine.md)  
  
  
