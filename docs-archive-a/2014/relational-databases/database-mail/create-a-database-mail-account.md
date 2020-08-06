---
title: Создание учетной записи компонента Database Mail | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Database Mail [SQL Server], accounts
- accounts [Database Mail]
ms.assetid: c07abbc6-fc6a-470b-8fa3-532f2e06b16a
author: stevestein
ms.author: sstein
ms.openlocfilehash: ec7d1c9147998b5a19cc0e6af13220bd64e165fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657815"
---
# <a name="create-a-database-mail-account"></a><span data-ttu-id="021a6-102">Создание учетной записи компонента Database Mail</span><span class="sxs-lookup"><span data-stu-id="021a6-102">Create a Database Mail Account</span></span>
  <span data-ttu-id="021a6-103">Для создания учетной записи компонента Database Mail применяется **мастер настройки компонента Database Mail** или [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="021a6-103">Use either the **Database Mail Configuration Wizard** or [!INCLUDE[tsql](../../includes/tsql-md.md)] to create a Database Mail account.</span></span>  
  
-   <span data-ttu-id="021a6-104">**Перед началом работы**  [Предварительные требования](#Prerequisites)</span><span class="sxs-lookup"><span data-stu-id="021a6-104">**Before you begin:**  [Prerequisites](#Prerequisites)</span></span>  
  
-   <span data-ttu-id="021a6-105">**Создание учетной записи компонента Database Mail с использованием:**  [мастера настройки компонента Database Mail](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="021a6-105">**To Create a Database Mail Account, using:**  [Database Mail Configuration Wizard](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
-   <span data-ttu-id="021a6-106">**Дальнейшие действия.**  [Следующие действия по настройке компонента Database Mail](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="021a6-106">**Follow Up:**  [Next Steps to Configure the Database Mail](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="021a6-107">Перед началом</span><span class="sxs-lookup"><span data-stu-id="021a6-107">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="021a6-108">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="021a6-108">Prerequisites</span></span>  
  
-   <span data-ttu-id="021a6-109">Определите имя сервера и номер порта для сервера протокола SMTP, который используется для отправки электронной почты. Если SMTP-сервер требует проверки подлинности, определите имя пользователя и пароль для SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="021a6-109">Determine the server name and port number for the Simple Mail Transfer Protocol (SMTP) server you use to send e-mail.If the SMTP server requires authentication, determine the user name and password for the SMTP server.</span></span>  
  
-   <span data-ttu-id="021a6-110">Также можно указать тип сервера и номер его порта.</span><span class="sxs-lookup"><span data-stu-id="021a6-110">Optionally, you may also specify the type of the server and the port number for the server.</span></span> <span data-ttu-id="021a6-111">Для исходящих сообщений всегда используется тип сервера «SMTP».</span><span class="sxs-lookup"><span data-stu-id="021a6-111">The server type is always 'SMTP' for outgoing mail.</span></span> <span data-ttu-id="021a6-112">Большинство SMTP-серверов по умолчанию используют порт 25.</span><span class="sxs-lookup"><span data-stu-id="021a6-112">Most SMTP servers use port 25, the default.</span></span>  
  
##  <a name="using-database-mail-configuration-wizard"></a><a name="SSMSProcedure"></a> <span data-ttu-id="021a6-113">Использование мастера настройки компонента Database Mail</span><span class="sxs-lookup"><span data-stu-id="021a6-113">Using Database Mail Configuration Wizard</span></span>  
 <span data-ttu-id="021a6-114">**Создание учетной записи компонента Database Mail с использованием мастера**</span><span class="sxs-lookup"><span data-stu-id="021a6-114">**To create a Database Mail account using a Wizard**</span></span>  
  
-   <span data-ttu-id="021a6-115">В обозревателе объектов подключитесь к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , для которого необходимо настроить компонент Database Mail, и разверните дерево сервера.</span><span class="sxs-lookup"><span data-stu-id="021a6-115">In Object Explorer, connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you want to configure Database Mail on, and expand the server tree.</span></span>  
  
-   <span data-ttu-id="021a6-116">Разверните узел **Управление**</span><span class="sxs-lookup"><span data-stu-id="021a6-116">Expand the **Management** node</span></span>  
  
-   <span data-ttu-id="021a6-117">Дважды щелкните компонент Database Mail, чтобы открыть мастер настройки компонента Database Mail.</span><span class="sxs-lookup"><span data-stu-id="021a6-117">Double Click Database Mail to open the Database Mail Configuration Wizard.</span></span>  
  
-   <span data-ttu-id="021a6-118">На странице **Выбор задачи настройки** выберите **Управление учетными записями и профилями компонента Database Mail**и нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="021a6-118">On the **Select Configuration Task** page, select **Manage Database Mail accounts and profiles**, and click **Next**.</span></span>  
  
-   <span data-ttu-id="021a6-119">На странице **Управление учетными записями и профилями** выберите **Создать новую учетную запись** и нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="021a6-119">On the **Manage Profiles and Accounts** page, select **Create a new account** and click **Next**.</span></span>  
  
-   <span data-ttu-id="021a6-120">На странице **Создать учетную запись** задайте имя учетной записи, описание, сведения о почтовом сервере и тип проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="021a6-120">On the **New Account** page, specify the account name, description, mail server information, and authentication type.</span></span> <span data-ttu-id="021a6-121">Нажмите кнопку **Далее**</span><span class="sxs-lookup"><span data-stu-id="021a6-121">Click **Next**</span></span>  
  
-   <span data-ttu-id="021a6-122">На странице **Завершение работы мастера** просмотрите действия, подлежащие выполнению, и нажмите **Готово** , чтобы завершить создание новой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="021a6-122">On the **Complete the Wizard** page, review the actions to be performed and click **Finish** to complete creating the new account.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="021a6-123">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="021a6-123">Using Transact-SQL</span></span>  
 <span data-ttu-id="021a6-124">**Создание учетной записи компонента Database Mail с помощью инструкций Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="021a6-124">**To Create a Database Mail account using Transact-SQL**</span></span>  
  
 <span data-ttu-id="021a6-125">Выполните хранимую процедуру **msdb.dbo.sysmail_add_account_sp** , чтобы создать учетную запись, и задайте следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="021a6-125">Execute the stored procedure **msdb.dbo.sysmail_add_account_sp** to create the account and specify the following information:</span></span>  
  
-   <span data-ttu-id="021a6-126">Имя создаваемой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="021a6-126">The name of the account to create.</span></span>  
  
-   <span data-ttu-id="021a6-127">Необязательное описание учетной записи.</span><span class="sxs-lookup"><span data-stu-id="021a6-127">An optional description of the account.</span></span>  
  
-   <span data-ttu-id="021a6-128">Обратный адрес электронной почты, который будет вставляться в исходящие электронные сообщения.</span><span class="sxs-lookup"><span data-stu-id="021a6-128">The e-mail address to show on outgoing e-mail messages.</span></span>  
  
-   <span data-ttu-id="021a6-129">Имя отправителя, которое будет отображаться в исходящих электронных сообщениях.</span><span class="sxs-lookup"><span data-stu-id="021a6-129">The display name to show on outgoing e-mail messages.</span></span>  
  
-   <span data-ttu-id="021a6-130">Имя SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="021a6-130">The server name of the SMTP server.</span></span>  
  
-   <span data-ttu-id="021a6-131">Имя пользователя для входа на SMTP-сервер, если этот сервер требует проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="021a6-131">The user name to use to log on to the SMTP server, if the SMTP server requires authentication.</span></span>  
  
-   <span data-ttu-id="021a6-132">Пароль для входа на SMTP-сервер, если этот сервер требует проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="021a6-132">The password to use to log on to the SMTP server, if the SMTP server requires authentication.</span></span>  
  
 <span data-ttu-id="021a6-133">В следующем примере создается новая учетная запись компонента Database Mail.</span><span class="sxs-lookup"><span data-stu-id="021a6-133">The following example creates a new Database Mail account.</span></span>  
  
```  
EXECUTE msdb.dbo.sysmail_add_account_sp  
    @account_name = 'AdventureWorks Administrator',  
    @description = 'Mail account for administrative e-mail.',  
    @email_address = 'dba@Adventure-Works.com',  
    @display_name = 'AdventureWorks Automated Mailer',  
    @mailserver_name = 'smtp.Adventure-Works.com' ;  
```  
  
##  <a name="follow-up-next-steps-to-configuring-the-database-mail"></a><a name="FollowUp"></a> <span data-ttu-id="021a6-134">Дальнейшие действия. Следующие действия по настройке компонента Database Mail</span><span class="sxs-lookup"><span data-stu-id="021a6-134">Follow Up: Next Steps to Configuring the Database Mail</span></span>  
  
-   [<span data-ttu-id="021a6-135">Создание профиля компонента Database Mail</span><span class="sxs-lookup"><span data-stu-id="021a6-135">Create a Database Mail Profile</span></span>](create-a-database-mail-profile.md)  
  
  
