---
title: Создание роли приложения | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.approle.general.f1
helpviewer_keywords:
- application roles [SQL Server], creating
ms.assetid: 6b8da1f5-3d8e-4f88-b111-b915788b06f1
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 51272dad57558cdb771f9b98a2f5e5b3da7609cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667001"
---
# <a name="create-an-application-role"></a><span data-ttu-id="99d58-102">Создание роли приложения</span><span class="sxs-lookup"><span data-stu-id="99d58-102">Create an Application Role</span></span>
  <span data-ttu-id="99d58-103">В этом разделе описывается создание роли приложения в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99d58-103">This topic describes how to create an application role in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="99d58-104">Роли приложения ограничивают доступ пользователя к базе данных за исключением указанных приложений.</span><span class="sxs-lookup"><span data-stu-id="99d58-104">Application roles restrict user access to a database except through specific applications.</span></span> <span data-ttu-id="99d58-105">Роли приложения не имеют пользователей: список **Члены роли** не отображается, когда выбран пункт **Роль приложения** .</span><span class="sxs-lookup"><span data-stu-id="99d58-105">Application roles have no users, so the **Role Members** list is not displayed when **Application role** is selected.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="99d58-106">Сложность пароля проверяется при установке паролей для роли приложения.</span><span class="sxs-lookup"><span data-stu-id="99d58-106">Password complexity is checked when application role passwords are set.</span></span> <span data-ttu-id="99d58-107">Приложения, которые используют роли приложения, должны хранить свои пароли.</span><span class="sxs-lookup"><span data-stu-id="99d58-107">Applications that invoke application roles must store their passwords.</span></span> <span data-ttu-id="99d58-108">Пароли ролей приложения всегда должны храниться в зашифрованном виде.</span><span class="sxs-lookup"><span data-stu-id="99d58-108">Application role passwords should always be stored encrypted.</span></span>  
  
 <span data-ttu-id="99d58-109">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="99d58-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="99d58-110">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="99d58-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="99d58-111">Безопасность</span><span class="sxs-lookup"><span data-stu-id="99d58-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="99d58-112">**Создание роли приложения с помощью:**</span><span class="sxs-lookup"><span data-stu-id="99d58-112">**To create an application role, using:**</span></span>  
  
     [<span data-ttu-id="99d58-113">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="99d58-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="99d58-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="99d58-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="99d58-115">Перед началом</span><span class="sxs-lookup"><span data-stu-id="99d58-115">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="99d58-116">безопасность</span><span class="sxs-lookup"><span data-stu-id="99d58-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="99d58-117">Permissions</span><span class="sxs-lookup"><span data-stu-id="99d58-117">Permissions</span></span>  
 <span data-ttu-id="99d58-118">Необходимо наличие разрешения ALTER ANY APPLICATION ROLE для этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="99d58-118">Requires ALTER ANY APPLICATION ROLE permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="99d58-119">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="99d58-119">Using SQL Server Management Studio</span></span>  
  
##### <a name="to-create-an-application-role"></a><span data-ttu-id="99d58-120">Создание роли приложения</span><span class="sxs-lookup"><span data-stu-id="99d58-120">To create an application role</span></span>  
  
1.  <span data-ttu-id="99d58-121">В обозревателе объектов разверните базу данных, в которой необходимо создать роль приложения.</span><span class="sxs-lookup"><span data-stu-id="99d58-121">In Object Explorer, expand the database where you want to create an application role.</span></span>  
  
2.  <span data-ttu-id="99d58-122">Разверните папку **Безопасность** .</span><span class="sxs-lookup"><span data-stu-id="99d58-122">Expand the **Security** folder.</span></span>  
  
3.  <span data-ttu-id="99d58-123">Разверните папку **Роли** .</span><span class="sxs-lookup"><span data-stu-id="99d58-123">Expand the **Roles** folder.</span></span>  
  
4.  <span data-ttu-id="99d58-124">Щелкните правой кнопкой мыши папку **Роли приложения** и выберите пункт **Создать роль приложения...** .</span><span class="sxs-lookup"><span data-stu-id="99d58-124">Right-click the **Application Roles** folder and select **New Application Role...**.</span></span>  
  
5.  <span data-ttu-id="99d58-125">В диалоговом окне **Application Role - New** (Роль приложения — создание) на странице **Общие** введите новое имя для новой роли приложения в поле **Имя роли**.</span><span class="sxs-lookup"><span data-stu-id="99d58-125">In the **Application Role - New** dialog box, on the **General Page**, enter the new name of the new application role in the **Role name** box.</span></span>  
  
6.  <span data-ttu-id="99d58-126">В поле **Схема по умолчанию** укажите схему, к которой будут принадлежать объекты, создаваемые этой ролью, введя имена объектов.</span><span class="sxs-lookup"><span data-stu-id="99d58-126">In the **Default Schema** box, specify the schema that will own objects created by this role by entering the object names.</span></span> <span data-ttu-id="99d58-127">Или щелкните кнопку с многоточием **(…)** , чтобы открыть диалоговое окно **Поиск схемы**.</span><span class="sxs-lookup"><span data-stu-id="99d58-127">Alternately, click the ellipsis **(...)** to open the **Locate Schema** dialog box.</span></span>  
  
7.  <span data-ttu-id="99d58-128">В поле **Пароль** введите пароль для новой роли.</span><span class="sxs-lookup"><span data-stu-id="99d58-128">In the **Password** box, enter a password for the new role.</span></span> <span data-ttu-id="99d58-129">Повторно введите пароль в поле **Подтверждение пароля** .</span><span class="sxs-lookup"><span data-stu-id="99d58-129">Enter that password again into the **Confirm Password** box.</span></span>  
  
8.  <span data-ttu-id="99d58-130">В поле **Схемы, принадлежащие данной роли**выберите или просмотрите схемы, которые будут принадлежать этой роли.</span><span class="sxs-lookup"><span data-stu-id="99d58-130">Under **Schemas owned by this role**, select or view schemas that will be owned by this role.</span></span> <span data-ttu-id="99d58-131">Схема может принадлежать только одной схеме или роли.</span><span class="sxs-lookup"><span data-stu-id="99d58-131">A schema can be owned by only one schema or role.</span></span>  
  
9. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="additional-options"></a><span data-ttu-id="99d58-132">Дополнительные параметры</span><span class="sxs-lookup"><span data-stu-id="99d58-132">Additional Options</span></span>  
 <span data-ttu-id="99d58-133">Кроме того, в диалоговом окне **Роль приложения — создать** имеются параметры на двух дополнительных страницах: **Защищаемые объекты** и **Расширенные свойства**.</span><span class="sxs-lookup"><span data-stu-id="99d58-133">The **Application Role - New** dialog box also offers options on two additional pages: **Securables** and **Extended Properties**.</span></span>  
  
-   <span data-ttu-id="99d58-134">На странице **Защищаемые объекты** перечислены все возможные защищаемые объекты и разрешения на эти объекты, которые могут быть предоставлены для имени входа.</span><span class="sxs-lookup"><span data-stu-id="99d58-134">The **Securables** page lists all possible securables and the permissions on those securables that can be granted to the login.</span></span>  
  
-   <span data-ttu-id="99d58-135">Страница **Расширенные свойства** позволяет добавлять пользовательские свойства пользователям базы данных.</span><span class="sxs-lookup"><span data-stu-id="99d58-135">The **Extended properties** page allows you to add custom properties to database users.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="99d58-136">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="99d58-136">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-application-role"></a><span data-ttu-id="99d58-137">Создание роли приложения</span><span class="sxs-lookup"><span data-stu-id="99d58-137">To create an application role</span></span>  
  
1.  <span data-ttu-id="99d58-138">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99d58-138">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="99d58-139">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="99d58-139">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="99d58-140">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="99d58-140">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates an application role called "weekly_receipts" that has the password "987Gbv876sPYY5m23" and "Sales" as its default schema.  
  
    CREATE APPLICATION ROLE weekly_receipts   
        WITH PASSWORD = '987G^bv876sPY)Y5m23'   
        , DEFAULT_SCHEMA = Sales;  
    GO  
    ```  
  
 <span data-ttu-id="99d58-141">Дополнительные сведения см. в разделе [CREATE APPLICATION ROLE (Transact-SQL)](/sql/t-sql/statements/create-application-role-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="99d58-141">For more information, see [CREATE APPLICATION ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-application-role-transact-sql).</span></span>  
  
  
