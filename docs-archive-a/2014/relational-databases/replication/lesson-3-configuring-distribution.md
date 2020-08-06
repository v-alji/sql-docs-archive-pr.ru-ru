---
title: Занятие 3. Настройка распространения | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: f248984a-0b59-4c2f-a56d-31f8dafe72b5
author: rothja
ms.author: jroth
ms.openlocfilehash: 52b284b6186e599b7afe73bd37ab0a8348ec38da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739701"
---
# <a name="lesson-3-configuring-distribution"></a><span data-ttu-id="23da1-102">Урок 3. Настройка распространения</span><span class="sxs-lookup"><span data-stu-id="23da1-102">Lesson 3: Configuring Distribution</span></span>
  <span data-ttu-id="23da1-103">На этом занятии предстоит настроить распространение на издателе и установить необходимые разрешения на базу данных публикации и распространителя.</span><span class="sxs-lookup"><span data-stu-id="23da1-103">In this lesson, you will configure distribution at the Publisher and set the required permissions on the publication and distribution databases.</span></span> <span data-ttu-id="23da1-104">Если распространитель уже настроен, необходимо отключить публикацию и распространение перед тем, как приступить к занятию.</span><span class="sxs-lookup"><span data-stu-id="23da1-104">If you have already configured the Distributor, you must first disable publishing and distribution before you begin this lesson.</span></span> <span data-ttu-id="23da1-105">Не следует этого выполнять в случае, если необходимо сохранить существующую топологию репликации.</span><span class="sxs-lookup"><span data-stu-id="23da1-105">Do not do this if you must retain an existing replication topology.</span></span>  
  
 <span data-ttu-id="23da1-106">Настройка издателя с удаленным распространителем не рассматривается в этом учебнике.</span><span class="sxs-lookup"><span data-stu-id="23da1-106">Configuring a Publisher with a remote Distributor is outside the scope of this tutorial.</span></span>  
  
### <a name="configuring-distribution-at-the-publisher"></a><span data-ttu-id="23da1-107">Настройка распространителя на издателе</span><span class="sxs-lookup"><span data-stu-id="23da1-107">Configuring distribution at the Publisher</span></span>  
  
1.  <span data-ttu-id="23da1-108">Подключитесь к издателю в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], а затем раскройте узел сервера.</span><span class="sxs-lookup"><span data-stu-id="23da1-108">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="23da1-109">Щелкните правой кнопкой мыши папку **Репликация** и выберите пункт **Настройка распространения**.</span><span class="sxs-lookup"><span data-stu-id="23da1-109">Right-click the **Replication** folder and click **Configure Distribution**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="23da1-110">Если подключение к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] установлено с помощью **localhost** , а не фактического имени сервера, на экране появится предупреждение о том, что [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не может подключиться к серверу **'localhost'**.</span><span class="sxs-lookup"><span data-stu-id="23da1-110">If you have connected to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using **localhost** rather than the actual server name you will be prompted with a warning that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is unable to connect to server **'localhost'**.</span></span> <span data-ttu-id="23da1-111">В диалоговом окне предупреждения нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="23da1-111">Click **OK** on the warning dialog.</span></span> <span data-ttu-id="23da1-112">В диалоговом окне **Соединение с сервером** измените значение в поле **Имя сервера** с **localhost** на имя своего сервера.</span><span class="sxs-lookup"><span data-stu-id="23da1-112">In the **Connect to Server** dialog change the **Server name** from **localhost** to the name of your server.</span></span> <span data-ttu-id="23da1-113">Нажмите кнопку **Подключиться**.</span><span class="sxs-lookup"><span data-stu-id="23da1-113">Click **Connect**.</span></span>  
  
     <span data-ttu-id="23da1-114">Будет запущен мастер настройки распространителя.</span><span class="sxs-lookup"><span data-stu-id="23da1-114">The Distribution Configuration Wizard launches.</span></span>  
  
3.  <span data-ttu-id="23da1-115">На странице **распространитель** выберите **"** _\<ServerName>_ **", будет работать как собственный распространитель; SQL Server создаст базу данных распространителя и журнал**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23da1-115">On the **Distributor** page, select **'**_\<ServerName>_**' will act as its own Distributor; SQL Server will create a distribution database and log**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="23da1-116">Если служба [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не запущена, на странице [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**Запуск агента** выберите **Да**и настройте автоматический запуск службы агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="23da1-116">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not running, on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**Agent Start** page, select **Yes**, configure the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service to start automatically.</span></span> <span data-ttu-id="23da1-117">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23da1-117">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="23da1-118">**\\\\** \<_Machine_Name> В текстовое поле **Папка моментальных снимков** введите _**\repldata** , где \<*Machine_Name> \* — это имя издателя, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23da1-118">Enter **\\\\**\<_Machine_Name>_**\repldata** in the **Snapshot folder** text box, where \<*Machine_Name>\* is the name of the Publisher, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="23da1-119">Примите значения по умолчанию на оставшихся страницах мастера.</span><span class="sxs-lookup"><span data-stu-id="23da1-119">Accept the default values on the remaining pages of the wizard.</span></span>  
  
7.  <span data-ttu-id="23da1-120">Чтобы включить распространение, нажмите кнопку **Готово** .</span><span class="sxs-lookup"><span data-stu-id="23da1-120">Click **Finish** to enable distribution.</span></span>  
  
### <a name="setting-database-permissions-at-the-publisher"></a><span data-ttu-id="23da1-121">Установка разрешений базы данных на издателе</span><span class="sxs-lookup"><span data-stu-id="23da1-121">Setting database permissions at the Publisher</span></span>  
  
1.  <span data-ttu-id="23da1-122">В [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] разверните узел **Безопасность**, щелкните правой кнопкой мыши элемент **имена входа**и выберите **создать имя входа**.</span><span class="sxs-lookup"><span data-stu-id="23da1-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand **Security**, right-click **Logins**, and then select **New Login**.</span></span>  
  
2.  <span data-ttu-id="23da1-123">На странице **Общие** нажмите кнопку **Поиск**, введите \<_Machine_Name> _**\ repl_snapshot** в поле **введите имя объекта** , где \<*Machine_Name> \* — это имя локального сервера издателя, щелкните **Проверить имена**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="23da1-123">On the **General** page, click **Search**, enter \<_Machine_Name>_**\repl_snapshot** in the **Enter the object name to select** box, where \<*Machine_Name>\* is the name of the local Publisher server, click **Check Names**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="23da1-124">На странице **Сопоставление пользователей** в списке Пользователи, **сопоставленные с этим именем входа** выберите **распределение** и [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] базы данных.</span><span class="sxs-lookup"><span data-stu-id="23da1-124">On the **User Mapping** page, in the **Users mapped to this login** list select both the **distribution** and [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] databases.</span></span>  
  
     <span data-ttu-id="23da1-125">В списке **членство в роли базы данных** выберите `db_owner` роль для имени входа для обеих баз данных.</span><span class="sxs-lookup"><span data-stu-id="23da1-125">In the **Database role membership** list select the `db_owner` role for the login for both databases.</span></span>  
  
4.  <span data-ttu-id="23da1-126">Нажмите кнопку **ОК** , чтобы создать имя входа.</span><span class="sxs-lookup"><span data-stu-id="23da1-126">Click **OK** to create the login.</span></span>  
  
5.  <span data-ttu-id="23da1-127">Для создания имени входа для локальной учетной записи repl_logreader повторите шаги 1-4.</span><span class="sxs-lookup"><span data-stu-id="23da1-127">Repeat steps 1-4 to create a login for the local repl_logreader account.</span></span> <span data-ttu-id="23da1-128">Это имя входа также должно быть сопоставлено с пользователями, которые являются членами `db_owner` предопределенной роли базы данных в базах данных **Distribution** и **AdventureWorks** .</span><span class="sxs-lookup"><span data-stu-id="23da1-128">This login must also be mapped to users that are members of the `db_owner` fixed database role in the **distribution** and **AdventureWorks** databases.</span></span>  
  
6.  <span data-ttu-id="23da1-129">Для создания имени входа для локальной учетной записи repl_distribution повторите шаги 1-4.</span><span class="sxs-lookup"><span data-stu-id="23da1-129">Repeat steps 1-4 to create a login for the local repl_distribution account.</span></span> <span data-ttu-id="23da1-130">Это имя входа должно быть сопоставлено с пользователем, который является членом `db_owner` предопределенной роли базы данных в базе данных **распространителя** .</span><span class="sxs-lookup"><span data-stu-id="23da1-130">This login must be mapped to a user that is a member of the `db_owner` fixed database role in the **distribution** database.</span></span>  
  
7.  <span data-ttu-id="23da1-131">Для создания имени входа для локальной учетной записи repl_merge повторите шаги 1-4.</span><span class="sxs-lookup"><span data-stu-id="23da1-131">Repeat steps 1-4 to create a login for the local repl_merge account.</span></span> <span data-ttu-id="23da1-132">С этим именем входа должны быть сопоставлены пользователи в базах данных **distribution** и **AdventureWorks** .</span><span class="sxs-lookup"><span data-stu-id="23da1-132">This login must have user mappings in the **distribution** and **AdventureWorks** databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23da1-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="23da1-133">See Also</span></span>  
 <span data-ttu-id="23da1-134">[Настройка распространения](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="23da1-134">[Configure Distribution](configure-distribution.md) </span></span>  
 <span data-ttu-id="23da1-135">[Replication Agent Security Model](security/replication-agent-security-model.md) (Модель безопасности агента репликации)</span><span class="sxs-lookup"><span data-stu-id="23da1-135">[Replication Agent Security Model](security/replication-agent-security-model.md)</span></span>  
  
  
