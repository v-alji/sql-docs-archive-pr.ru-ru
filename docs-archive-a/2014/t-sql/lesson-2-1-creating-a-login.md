---
title: Создание имени для входа | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- creating a login
ms.assetid: a2512310-bdb6-41dc-858a-e866b2b58afc
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 400a57693fbea10270a51f5735a19b9639112ce9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737355"
---
# <a name="creating-a-login"></a><span data-ttu-id="81532-102">Создание имени входа</span><span class="sxs-lookup"><span data-stu-id="81532-102">Creating a Login</span></span>
  <span data-ttu-id="81532-103">Чтобы получить доступ к компоненту [!INCLUDE[ssDE](../includes/ssde-md.md)], необходимо иметь имя входа.</span><span class="sxs-lookup"><span data-stu-id="81532-103">To access the [!INCLUDE[ssDE](../includes/ssde-md.md)], users require a login.</span></span> <span data-ttu-id="81532-104">Имя входа может идентифицировать пользователя как учетную запись Windows или как члена группы Windows, или имя входа может быть именем входа [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , которое существует только в [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81532-104">The login can represent the user's identity as a Windows account or as a member of a Windows group, or the login can be a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login that exists only in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="81532-105">При возможности используйте проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="81532-105">Whenever possible you should use Windows Authentication.</span></span>  
  
 <span data-ttu-id="81532-106">По умолчанию администраторы компьютера имеют полный доступ к [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81532-106">By default, administrators on your computer have full access to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="81532-107">Для этого занятия нужно иметь пользователя с меньшим правом доступа; следовательно, вы создадите новую локальную учетную запись проверки подлинности Windows на компьютере.</span><span class="sxs-lookup"><span data-stu-id="81532-107">For this lesson, we want to have a less privileged user; therefore, you will create a new local Windows Authentication account on your computer.</span></span> <span data-ttu-id="81532-108">Чтобы сделать это, нужно быть администратором на своем компьютере.</span><span class="sxs-lookup"><span data-stu-id="81532-108">To do this, you must be an administrator on your computer.</span></span> <span data-ttu-id="81532-109">После этого нужно предоставить новому пользователю доступ к [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81532-109">Then you will grant that new user access to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
### <a name="to-create-a-new-windows-account"></a><span data-ttu-id="81532-110">Создание новой учетной записи Windows</span><span class="sxs-lookup"><span data-stu-id="81532-110">To create a new Windows account</span></span>  
  
1.  <span data-ttu-id="81532-111">Нажмите кнопку **Пуск**, выберите пункт **выполнить**, в поле **Открыть** введите `%SystemRoot%\system32\compmgmt.msc /s` , а затем нажмите кнопку **ОК** , чтобы открыть программу управления компьютером.</span><span class="sxs-lookup"><span data-stu-id="81532-111">Click **Start**, click **Run**, in the **Open** box, type `%SystemRoot%\system32\compmgmt.msc /s`, and then click **OK** to open the Computer Management program.</span></span>  
  
2.  <span data-ttu-id="81532-112">В пункте **Служебные программы**откройте **Локальные пользователи и группы**, щелкните правой кнопкой мыши элемент **Пользователи**и выберите пункт **Новый пользователь**.</span><span class="sxs-lookup"><span data-stu-id="81532-112">Under **System Tools**, expand **Local Users and Groups**, right-click **Users**, and then click **New User**.</span></span>  
  
3.  <span data-ttu-id="81532-113">В поле **Имя пользователя** введите **Mary**.</span><span class="sxs-lookup"><span data-stu-id="81532-113">In the **User name** box type **Mary**.</span></span>  
  
4.  <span data-ttu-id="81532-114">В полях **Пароль** и **Подтверждение пароля** введите надежный пароль и нажмите кнопку **Создать** , чтобы создать нового локального пользователя Windows.</span><span class="sxs-lookup"><span data-stu-id="81532-114">In the **Password** and **Confirm password** box, type a strong password, and then click **Create** to create a new local Windows user.</span></span>  
  
### <a name="to-create-a-login"></a><span data-ttu-id="81532-115">Создание имени входа</span><span class="sxs-lookup"><span data-stu-id="81532-115">To create a login</span></span>  
  
1.  <span data-ttu-id="81532-116">В окне редактора запросов среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]введите и выполните следующий исходный код, заменив `computer_name` на имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="81532-116">In a Query Editor window of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], type and execute the following code replacing `computer_name` with the name of your computer.</span></span> <span data-ttu-id="81532-117">`FROM WINDOWS` указывает, что Windows проверит подлинность пользователя.</span><span class="sxs-lookup"><span data-stu-id="81532-117">`FROM WINDOWS` indicates that Windows will authenticate the user.</span></span> <span data-ttu-id="81532-118">Необязательный аргумент `DEFAULT_DATABASE` соединяет `Mary` с базой данных `TestData` , если только в ее строке соединения не указана другая база данных.</span><span class="sxs-lookup"><span data-stu-id="81532-118">The optional `DEFAULT_DATABASE` argument connects `Mary` to the `TestData` database, unless her connection string indicates another database.</span></span> <span data-ttu-id="81532-119">Эта инструкция рассматривает точку с запятой в виде необязательного завершения инструкции языка [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="81532-119">This statement introduces the semicolon as an optional termination for a [!INCLUDE[tsql](../includes/tsql-md.md)] statement.</span></span>  
  
    ```  
    CREATE LOGIN [computer_name\Mary]  
        FROM WINDOWS  
        WITH DEFAULT_DATABASE = [TestData];  
    GO  
    ```  
  
     <span data-ttu-id="81532-120">Этим авторизируется имя пользователя `Mary`, проверенное компьютером, чтобы получить доступ к экземпляру [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81532-120">This authorizes a user name `Mary`, authenticated by your computer, to access this instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="81532-121">Если на компьютере находится более одного экземпляра [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , нужно создать имя входа для каждого экземпляра, к которому `Mary` должна иметь доступ.</span><span class="sxs-lookup"><span data-stu-id="81532-121">If there is more than one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on the computer, you must create the login on each instance that `Mary` must access.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="81532-122">Поскольку `Mary` не является доменной учетной записью, это имя пользователя может быть принято только на данном компьютере.</span><span class="sxs-lookup"><span data-stu-id="81532-122">Because `Mary` is not a domain account, this user name can only be authenticated on this computer.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="81532-123">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="81532-123">Next Task in Lesson</span></span>  
 [<span data-ttu-id="81532-124">Предоставление доступа к базе данных</span><span class="sxs-lookup"><span data-stu-id="81532-124">Granting Access to a Database</span></span>](lesson-2-2-granting-access-to-a-database.md)  
  
## <a name="see-also"></a><span data-ttu-id="81532-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="81532-125">See Also</span></span>  
 <span data-ttu-id="81532-126">[CREATE LOGIN (Transact-SQL)](/sql/t-sql/statements/create-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="81532-126">[CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql) </span></span>  
 [<span data-ttu-id="81532-127">Выбор режима проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="81532-127">Choose an Authentication Mode</span></span>](../relational-databases/security/choose-an-authentication-mode.md)  
  
  
