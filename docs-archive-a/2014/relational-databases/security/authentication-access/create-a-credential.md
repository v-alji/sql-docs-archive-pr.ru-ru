---
title: Создание учетных данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- credentials [SQL Server], creating
- authentication [SQL Server], credentials
- logins [SQL Server], credentials
ms.assetid: c1e77e91-2a69-40d9-b8b3-97cffc710586
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 23221424699449ac3775b0e805bb02ae0ad233f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730393"
---
# <a name="create-a-credential"></a><span data-ttu-id="3fbc8-102">Создание учетных данных</span><span class="sxs-lookup"><span data-stu-id="3fbc8-102">Create a Credential</span></span>
  <span data-ttu-id="3fbc8-103">В этом разделе описано, как создать учетные данные в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3fbc8-103">This topic describes how to create a credential in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="3fbc8-104">Учетные данные обеспечивают возможность проходить проверку подлинности [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] пользователям, имеющим удостоверение вне [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3fbc8-104">Credentials provide a way to allow [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication users to have an identity outside of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3fbc8-105">Это в первую очередь необходимо для выполнения программного кода в сборках с набором разрешений EXTERNAL_ACCESS.</span><span class="sxs-lookup"><span data-stu-id="3fbc8-105">This is primarily used to execute code in Assemblies with EXTERNAL_ACCESS permission set.</span></span> <span data-ttu-id="3fbc8-106">Учетные данные также применяются в случае, когда пользователям, использующим проверку подлинности [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , требуется доступ к ресурсам домена, например к хранилищу файлов для создания резервной копии.</span><span class="sxs-lookup"><span data-stu-id="3fbc8-106">Credentials can also be used when a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication user needs access to a domain resource, such as a file location to store a backup.</span></span>  
  
 <span data-ttu-id="3fbc8-107">Набор учетных данных может быть одновременно сопоставлен с несколькими именами входа [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3fbc8-107">A credential can be mapped to several [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logins at the same time.</span></span> <span data-ttu-id="3fbc8-108">С одним именем входа [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] может одновременно быть сопоставлен только один набор учетных данных.</span><span class="sxs-lookup"><span data-stu-id="3fbc8-108">A [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login can only be mapped to one credential at a time.</span></span> <span data-ttu-id="3fbc8-109">После создания учетных данных в окне **Свойства имени входа (страница "Общие")** сопоставьте их с именем входа.</span><span class="sxs-lookup"><span data-stu-id="3fbc8-109">After a credential is created, use the **Login Properties (General Page)** to map a login to a credential.</span></span>  
  
 <span data-ttu-id="3fbc8-110">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="3fbc8-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3fbc8-111">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="3fbc8-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3fbc8-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="3fbc8-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="3fbc8-113">Безопасность</span><span class="sxs-lookup"><span data-stu-id="3fbc8-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3fbc8-114">**Создание учетных данных с помощью:**</span><span class="sxs-lookup"><span data-stu-id="3fbc8-114">**To create a credential, using:**</span></span>  
  
     [<span data-ttu-id="3fbc8-115">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3fbc8-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="3fbc8-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3fbc8-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3fbc8-117">Перед началом</span><span class="sxs-lookup"><span data-stu-id="3fbc8-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="3fbc8-118">Ограничения</span><span class="sxs-lookup"><span data-stu-id="3fbc8-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="3fbc8-119">При отсутствии учетных данных для поставщика, сопоставленных с именем входа, используются учетные данные, сопоставленные с учетной записью службы [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3fbc8-119">If there is no login mapped credential for the provider, the credential mapped to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service account is used.</span></span>  
  
-   <span data-ttu-id="3fbc8-120">Имени входа может быть сопоставлено несколько учетных данных, если они используются для отдельных поставщиков.</span><span class="sxs-lookup"><span data-stu-id="3fbc8-120">A login can have multiple credentials mapped to it as long as they are used with distinctive providers.</span></span> <span data-ttu-id="3fbc8-121">У каждого поставщика должен быть только один набор учетных данных, сопоставленных одному имени входа.</span><span class="sxs-lookup"><span data-stu-id="3fbc8-121">There must be only one mapped credential per provider per login.</span></span> <span data-ttu-id="3fbc8-122">Одни и те же учетные данные могут быть сопоставлены нескольким именам входа.</span><span class="sxs-lookup"><span data-stu-id="3fbc8-122">The same credential can be mapped to other logins.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3fbc8-123">безопасность</span><span class="sxs-lookup"><span data-stu-id="3fbc8-123">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3fbc8-124">Permissions</span><span class="sxs-lookup"><span data-stu-id="3fbc8-124">Permissions</span></span>  
 <span data-ttu-id="3fbc8-125">Требует разрешения ALTER ANY CREDENTIAL для создания или изменения учетных данных и разрешения ALTER ANY LOGIN для сопоставления имени входа с учетными данными.</span><span class="sxs-lookup"><span data-stu-id="3fbc8-125">Requires ALTER ANY CREDENTIAL permission to create or modify a credential and ALTER ANY LOGIN permission to map a login to a credential.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3fbc8-126">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3fbc8-126">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-credential"></a><span data-ttu-id="3fbc8-127">Создание учетных данных</span><span class="sxs-lookup"><span data-stu-id="3fbc8-127">To create a credential</span></span>  
  
1.  <span data-ttu-id="3fbc8-128">В обозревателе объектов разверните папку **Безопасность** .</span><span class="sxs-lookup"><span data-stu-id="3fbc8-128">In Object Explorer, expand  the **Security** folder.</span></span>  
  
2.  <span data-ttu-id="3fbc8-129">Щелкните правой кнопкой мыши папку **Учетные данные** и выберите команду **Создать учетные данные...** .</span><span class="sxs-lookup"><span data-stu-id="3fbc8-129">Right-click the **Credentials** folder and select **New Credential...**.</span></span>  
  
3.  <span data-ttu-id="3fbc8-130">В диалоговом окне **Создание учетных данных** в поле **Учетное имя** введите имя для учетных данных.</span><span class="sxs-lookup"><span data-stu-id="3fbc8-130">In the **New Credential** dialog box, in the **Credential Name** box, type a name for the credential.</span></span>  
  
4.  <span data-ttu-id="3fbc8-131">В поле **Удостоверение** введите имя учетной записи, используемой для исходящих соединений (при выходе из контекста [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="3fbc8-131">In the **Identity** box, type the name of the account used for outgoing connections (when leaving the context of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]).</span></span> <span data-ttu-id="3fbc8-132">Как правило, это будет учетная запись пользователя Windows, но удостоверение может быть и учетной записью другого типа.</span><span class="sxs-lookup"><span data-stu-id="3fbc8-132">Typically, this will be a Windows user account, but the identity can be an account of another type.</span></span>  
  
     <span data-ttu-id="3fbc8-133">Либо нажмите кнопку с многоточием **(...)** , чтобы открыть диалоговое окно **Выбор пользователя или группы**.</span><span class="sxs-lookup"><span data-stu-id="3fbc8-133">Alternately, click the ellipsis **(...)** to open the **Select User or Group** dialog box.</span></span>  
  
5.  <span data-ttu-id="3fbc8-134">В полях **Пароль** и **Подтверждение пароля** введите пароль учетной записи, указанной в поле **Удостоверение** .</span><span class="sxs-lookup"><span data-stu-id="3fbc8-134">In the **Password** and **Confirm password** boxes, type the password of the account specified in the **Identity** box.</span></span> <span data-ttu-id="3fbc8-135">Если в поле **Удостоверение** указана учетная запись пользователя Windows, то это будет пароль Windows.</span><span class="sxs-lookup"><span data-stu-id="3fbc8-135">If **Identity** is a Windows user account, this is the Windows password.</span></span> <span data-ttu-id="3fbc8-136">Поле **Пароль** может быть пустым, если пароль не требуется.</span><span class="sxs-lookup"><span data-stu-id="3fbc8-136">The **Password** can be blank, if no password is required.</span></span>  
  
6.  <span data-ttu-id="3fbc8-137">Установите флажок **Использовать поставщика функций шифрования**, чтобы учетные данные проверялись поставщиком расширенного управления ключами.</span><span class="sxs-lookup"><span data-stu-id="3fbc8-137">Select **Use Encryption Provider** to set the credential to be verified by an Extensible Key Management (EKM) Provider.</span></span> <span data-ttu-id="3fbc8-138">Дополнительные сведения см. в разделе [Расширенное управление ключами (EKM)](../encryption/extensible-key-management-ekm.md).</span><span class="sxs-lookup"><span data-stu-id="3fbc8-138">For more information, see [Extensible Key Management &#40;EKM&#41;](../encryption/extensible-key-management-ekm.md)</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3fbc8-139">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3fbc8-139">Using Transact-SQL</span></span>  
  
###  <a name="to-create-a-credential"></a><a name="Credential"></a><span data-ttu-id="3fbc8-140">Создание учетных данных</span><span class="sxs-lookup"><span data-stu-id="3fbc8-140">To create a credential</span></span>  
  
1.  <span data-ttu-id="3fbc8-141">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3fbc8-141">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3fbc8-142">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="3fbc8-142">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3fbc8-143">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="3fbc8-143">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates the credential called "AlterEgo.".   
    -- The credential contains the Windows user "Mary5" and a password.  
    CREATE CREDENTIAL AlterEgo WITH IDENTITY = 'Mary5',   
        SECRET = '<EnterStrongPasswordHere>';  
    GO  
    ```  
  
 <span data-ttu-id="3fbc8-144">Дополнительные сведения см. в разделе [CREATE CREDENTIAL (Transact-SQL)](/sql/t-sql/statements/create-credential-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3fbc8-144">For more information, see [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span></span>  
  
  
