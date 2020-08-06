---
title: Изменение режима проверки подлинности сервера | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- sa account
- authentication [SQL Server], changing modes
- server authentication mode [SQL Server]
- modifying server authentication mode
ms.assetid: 79babcf8-19fd-4495-b8eb-453dc575cac0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8bda31ca7d0c5949173a9a3e5ea656c1757c04f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740454"
---
# <a name="change-server-authentication-mode"></a><span data-ttu-id="7a8dc-102">Изменение режима проверки подлинности сервера</span><span class="sxs-lookup"><span data-stu-id="7a8dc-102">Change Server Authentication Mode</span></span>
  <span data-ttu-id="7a8dc-103">В этом разделе описывается, как изменить режим проверки подлинности сервера в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a8dc-103">This topic describes how to change the server authentication mode in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="7a8dc-104">В процессе установки компонент [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] настраивается на использование **режима проверки подлинности Windows** или **режима проверки подлинности SQL Server и Windows**.</span><span class="sxs-lookup"><span data-stu-id="7a8dc-104">During installation, [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] is set to either **Windows Authentication mode** or **SQL Server and Windows Authentication mode**.</span></span> <span data-ttu-id="7a8dc-105">После установки вы можете изменить режим проверки подлинности в любое время.</span><span class="sxs-lookup"><span data-stu-id="7a8dc-105">After installation, you can change the authentication mode at any time.</span></span>  
  
 <span data-ttu-id="7a8dc-106">Если во время установки был выбран **Режим проверки подлинности Windows** , то имя входа sa отключено, а пароль присваивается программой установки.</span><span class="sxs-lookup"><span data-stu-id="7a8dc-106">If **Windows Authentication mode** is selected during installation, the sa login is disabled and a password is assigned by setup.</span></span> <span data-ttu-id="7a8dc-107">Если впоследствии изменить режим проверки подлинности на **проверку подлинности SQL Server и Windows**, то имя входа sa останется отключенным.</span><span class="sxs-lookup"><span data-stu-id="7a8dc-107">If you later change authentication mode to **SQL Server and Windows Authentication mode**, the sa login remains disabled.</span></span> <span data-ttu-id="7a8dc-108">Чтобы можно было пользоваться именем входа sa, включите его и присвойте ему новый пароль с помощью инструкции ALTER LOGIN.</span><span class="sxs-lookup"><span data-stu-id="7a8dc-108">To use the sa login, use the ALTER LOGIN statement to enable the sa login and assign a new password.</span></span> <span data-ttu-id="7a8dc-109">Имя входа sa может подключаться к серверу только с использованием проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7a8dc-109">The sa login can only connect to the server by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="7a8dc-110">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="7a8dc-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7a8dc-111">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="7a8dc-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7a8dc-112">Безопасность</span><span class="sxs-lookup"><span data-stu-id="7a8dc-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7a8dc-113">**Изменение режима проверки подлинности сервера с помощью:**</span><span class="sxs-lookup"><span data-stu-id="7a8dc-113">**To change server authentication mode, using:**</span></span>  
  
     [<span data-ttu-id="7a8dc-114">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7a8dc-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7a8dc-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7a8dc-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7a8dc-116">Перед началом</span><span class="sxs-lookup"><span data-stu-id="7a8dc-116">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7a8dc-117">безопасность</span><span class="sxs-lookup"><span data-stu-id="7a8dc-117">Security</span></span>  
 <span data-ttu-id="7a8dc-118">Учетная запись sa — хорошо известная учетная запись [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и часто становится мишенью злоумышленников.</span><span class="sxs-lookup"><span data-stu-id="7a8dc-118">The sa account is a well-known [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account and it is often targeted by malicious users.</span></span> <span data-ttu-id="7a8dc-119">Не включайте учетную запись sa, если это не требуется для работы приложения.</span><span class="sxs-lookup"><span data-stu-id="7a8dc-119">Do not enable the sa account unless your application requires it.</span></span> <span data-ttu-id="7a8dc-120">Для имени входа sa очень важно использовать надежный пароль.</span><span class="sxs-lookup"><span data-stu-id="7a8dc-120">It is very important that you use a strong password for the sa login.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7a8dc-121">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7a8dc-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-security-authentication-mode"></a><span data-ttu-id="7a8dc-122">Изменение режима проверки подлинности в целях безопасности</span><span class="sxs-lookup"><span data-stu-id="7a8dc-122">To change security authentication mode</span></span>  
  
1.  <span data-ttu-id="7a8dc-123">В обозревателе объектов среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] щелкните правой кнопкой мыши сервер и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7a8dc-123">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Object Explorer, right-click the server, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="7a8dc-124">На странице **Безопасность** , в разделе **Серверная проверка подлинности**выберите новый режим проверки подлинности сервера, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7a8dc-124">On the **Security** page, under **Server authentication**, select the new server authentication mode, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="7a8dc-125">В диалоговом окне среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] нажмите кнопку **ОК** , чтобы подтвердить необходимость перезапуска [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a8dc-125">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] dialog box, click **OK** to acknowledge the requirement to restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
4.  <span data-ttu-id="7a8dc-126">В обозревателе объектов щелкните правой кнопкой мыши сервер и выберите пункт **Перезапустить**.</span><span class="sxs-lookup"><span data-stu-id="7a8dc-126">In Object Explorer, right-click your server, and then click **Restart**.</span></span> <span data-ttu-id="7a8dc-127">Если работает агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , он тоже должен быть перезапущен.</span><span class="sxs-lookup"><span data-stu-id="7a8dc-127">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent is running, it must also be restarted.</span></span>  
  
#### <a name="to-enable-the-sa-login"></a><span data-ttu-id="7a8dc-128">Включение имени входа sa</span><span class="sxs-lookup"><span data-stu-id="7a8dc-128">To enable the sa login</span></span>  
  
1.  <span data-ttu-id="7a8dc-129">В обозревателе объектов разверните узел **Безопасность**, разверните узел имена входа, щелкните правой кнопкой мыши `sa` и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7a8dc-129">In Object Explorer, expand **Security**, expand Logins, right-click `sa`, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="7a8dc-130">На странице **Общие** , возможно, придется создать и подтвердить пароль для имени входа.</span><span class="sxs-lookup"><span data-stu-id="7a8dc-130">On the **General** page, you might have to create and confirm a password for the  login.</span></span>  
  
3.  <span data-ttu-id="7a8dc-131">На странице **Состояние** в разделе **Имя входа** щелкните **Включить**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7a8dc-131">On the **Status** page, in the **Login** section, click **Enabled**, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7a8dc-132">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7a8dc-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="7a8dc-133">**Включение имени входа sa**</span><span class="sxs-lookup"><span data-stu-id="7a8dc-133">**To enable the sa login**</span></span>  
  
1.  <span data-ttu-id="7a8dc-134">В обозревателе объектов установите соединение с экземпляром компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a8dc-134">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7a8dc-135">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="7a8dc-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7a8dc-136">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="7a8dc-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="7a8dc-137">В следующем примере включается имя входа sa и устанавливается новый пароль.</span><span class="sxs-lookup"><span data-stu-id="7a8dc-137">The following example enables the sa login and sets a new password.</span></span>  
  
    ```  
    ALTER LOGIN sa ENABLE ;  
    GO  
    ALTER LOGIN sa WITH PASSWORD = '<enterStrongPasswordHere>' ;  
    GO  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7a8dc-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="7a8dc-138">See Also</span></span>  
 <span data-ttu-id="7a8dc-139">[Надежные пароли](../../relational-databases/security/strong-passwords.md) </span><span class="sxs-lookup"><span data-stu-id="7a8dc-139">[Strong Passwords](../../relational-databases/security/strong-passwords.md) </span></span>  
 <span data-ttu-id="7a8dc-140">[Вопросы безопасности при установке SQL Server](../../sql-server/install/security-considerations-for-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="7a8dc-140">[Security Considerations for a SQL Server Installation](../../sql-server/install/security-considerations-for-a-sql-server-installation.md) </span></span>  
 <span data-ttu-id="7a8dc-141">[ALTER LOGIN (Transact-SQL)](/sql/t-sql/statements/alter-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7a8dc-141">[ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) </span></span>  
 [<span data-ttu-id="7a8dc-142">Подключение к SQL Server в случае, если доступ системных администраторов заблокирован</span><span class="sxs-lookup"><span data-stu-id="7a8dc-142">Connect to SQL Server When System Administrators Are Locked Out</span></span>](connect-to-sql-server-when-system-administrators-are-locked-out.md)  
  
  
