---
title: Соединение с сервером (ядро СУБД) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.connectoserverunknownservertype.f1
- sql12.swb.connection.login.sqlserver.f1
- sql12.swb.connection.login.sqlce.f1
- sql12.swb.manageSS2k.f1
- sql12.swb.connecttoce.f1
- sql12.swb.connecttoce.connectionproperties.f1
ms.assetid: ee9017b4-8a19-4360-9003-9e6484082d41
author: stevestein
ms.author: sstein
ms.openlocfilehash: ca227d1a3bbc13160962ba2fcad23ff011c950f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733481"
---
# <a name="connect-to-server-database-engine"></a><span data-ttu-id="fc5fe-102">Соединение с сервером (ядро СУБД)</span><span class="sxs-lookup"><span data-stu-id="fc5fe-102">Connect to Server (Database Engine)</span></span>
  <span data-ttu-id="fc5fe-103">Используйте это диалоговое окно для просмотра или настройки параметров при подключении к [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fc5fe-103">Use this dialog to view or specify options when connecting to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="fc5fe-104">В большинстве случаев при подключении в поле **Имя сервера** нужно ввести имя компьютера, на котором расположена база данных, а затем нажать кнопку **Соединить**.</span><span class="sxs-lookup"><span data-stu-id="fc5fe-104">In most cases, you can connect by entering the computer name of the database server in the **Server name** box and then clicking **Connect**.</span></span> <span data-ttu-id="fc5fe-105">Если выполняется соединение с [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], введите имя компьютера, а после него — **\sqlexpress**.</span><span class="sxs-lookup"><span data-stu-id="fc5fe-105">If you are connecting to [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], use the computer name followed by **\sqlexpress**.</span></span>  
  
 <span data-ttu-id="fc5fe-106">На возможность подключиться к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]влияют многие факторы.</span><span class="sxs-lookup"><span data-stu-id="fc5fe-106">Many factors can affect your ability to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="fc5fe-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="fc5fe-107">Options</span></span>  
 <span data-ttu-id="fc5fe-108">**Тип сервера**</span><span class="sxs-lookup"><span data-stu-id="fc5fe-108">**Server type**</span></span>  
 <span data-ttu-id="fc5fe-109">При регистрации сервера из обозревателя объектов выберите тип сервера для подключения: [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]или [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fc5fe-109">When registering a server from Object Explorer, select the type of server to connect to: [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], or [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="fc5fe-110">В остальной части диалогового окна показаны параметры, которые применяются только к выбранному типу сервера.</span><span class="sxs-lookup"><span data-stu-id="fc5fe-110">The rest of the dialog shows only the options that apply to the selected server type.</span></span> <span data-ttu-id="fc5fe-111">При регистрации сервера c панели "Зарегистрированные серверы" поле **Тип сервера** не может быть изменено и совпадает с типом сервера, показанного в компоненте "Зарегистрированные серверы".</span><span class="sxs-lookup"><span data-stu-id="fc5fe-111">When registering a server from Registered Servers, the **Server type** box is read-only, and matches the type of server displayed in the Registered Servers component.</span></span> <span data-ttu-id="fc5fe-112">Чтобы зарегистрировать другой тип сервера, выберите компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)], службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], [!INCLUDE[ssEW](../../includes/ssew-md.md)]или службы [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на панели инструментов «Зарегистрированные серверы», прежде чем начать регистрацию нового сервера.</span><span class="sxs-lookup"><span data-stu-id="fc5fe-112">To register a different type of server, select [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], [!INCLUDE[ssEW](../../includes/ssew-md.md)], or [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] from the Registered Servers toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="fc5fe-113">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="fc5fe-113">**Server name**</span></span>  
 <span data-ttu-id="fc5fe-114">Выберите экземпляр сервера для подключения.</span><span class="sxs-lookup"><span data-stu-id="fc5fe-114">Select the server instance to connect to.</span></span> <span data-ttu-id="fc5fe-115">По умолчанию выводится экземпляр сервера, к которому подключение выполнялось в последний раз.</span><span class="sxs-lookup"><span data-stu-id="fc5fe-115">The server instance last connected to is displayed by default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fc5fe-116">Для подключения к активному экземпляру [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] выполните подключение с использованием протокола именованных каналов, указав имя канала, например "\\\\.\pipe\3C3DF6B1-2262-47\tsql\query". Дополнительные сведения см. в документации по [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fc5fe-116">To connect to an active user instance of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] connect using named pipes protocol specifying the pipe name, such as np:\\\\.\pipe\3C3DF6B1-2262-47\tsql\query For more information, see the [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] documentation.</span></span>  
  
 <span data-ttu-id="fc5fe-117">**Аутентификация**</span><span class="sxs-lookup"><span data-stu-id="fc5fe-117">**Authentication**</span></span>  
 <span data-ttu-id="fc5fe-118">При подключении к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] доступны два режима проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="fc5fe-118">Two authentication modes are available when connecting to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="fc5fe-119">**Режим проверки подлинности Windows (проверка подлинности Windows)**</span><span class="sxs-lookup"><span data-stu-id="fc5fe-119">**Windows Authentication Mode (Windows Authentication)**</span></span>  
 [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="fc5fe-120">Режим проверки подлинности Windows позволяет подключаться с учетной записью Windows.</span><span class="sxs-lookup"><span data-stu-id="fc5fe-120">Windows Authentication mode allows a user to connect through a Windows user account.</span></span>  
  
 <span data-ttu-id="fc5fe-121">**Проверка подлинности SQL Server**</span><span class="sxs-lookup"><span data-stu-id="fc5fe-121">**SQL Server Authentication**</span></span>  
 <span data-ttu-id="fc5fe-122">При подключении пользователя с указанным именем входа и паролем не через доверенное соединение [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выполняет проверку подлинности самостоятельно по наличию учетной записи входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и совпадения указанного пароля с ранее сохраненным.</span><span class="sxs-lookup"><span data-stu-id="fc5fe-122">When a user connects with a specified login name and password from a non-trusted connection, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs the authentication itself by checking to see if a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login account has been set up and if the specified password matches the one previously recorded.</span></span> <span data-ttu-id="fc5fe-123">Если в службе [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не задана учетная запись входа, проверка подлинности завершается ошибкой, о которой пользователь получит сообщение.</span><span class="sxs-lookup"><span data-stu-id="fc5fe-123">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not have a login account set, authentication fails, and the user receives an error message.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fc5fe-124">По возможности используйте аутентификацию Windows.</span><span class="sxs-lookup"><span data-stu-id="fc5fe-124">When possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="fc5fe-125">**User name**</span><span class="sxs-lookup"><span data-stu-id="fc5fe-125">**User name**</span></span>  
 <span data-ttu-id="fc5fe-126">Введите имя пользователя для соединения.</span><span class="sxs-lookup"><span data-stu-id="fc5fe-126">Enter the user name to connect with.</span></span> <span data-ttu-id="fc5fe-127">Этот параметр доступен только при соединении с использованием метода проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="fc5fe-127">This option is only available if you have selected to connect using Windows Authentication.</span></span>  
  
 <span data-ttu-id="fc5fe-128">**Имя входа**</span><span class="sxs-lookup"><span data-stu-id="fc5fe-128">**Login**</span></span>  
 <span data-ttu-id="fc5fe-129">Введите имя входа для подключения.</span><span class="sxs-lookup"><span data-stu-id="fc5fe-129">Enter the login to connect with.</span></span> <span data-ttu-id="fc5fe-130">Этот параметр доступен только в том случае, если выбрано соединение с использованием проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fc5fe-130">This option is only available if you have selected to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="fc5fe-131">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="fc5fe-131">**Password**</span></span>  
 <span data-ttu-id="fc5fe-132">Введите пароль для этого имени входа.</span><span class="sxs-lookup"><span data-stu-id="fc5fe-132">Enter the password for the login.</span></span> <span data-ttu-id="fc5fe-133">Этот параметр доступен для редактирования только при подключении с проверкой подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fc5fe-133">This option is only editable if you have selected to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="fc5fe-134">**Подключить**</span><span class="sxs-lookup"><span data-stu-id="fc5fe-134">**Connect**</span></span>  
 <span data-ttu-id="fc5fe-135">Нажмите, чтобы подключиться к выбранному выше серверу.</span><span class="sxs-lookup"><span data-stu-id="fc5fe-135">Click to connect to the server selected above.</span></span>  
  
 <span data-ttu-id="fc5fe-136">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="fc5fe-136">**Options**</span></span>  
 <span data-ttu-id="fc5fe-137">Нажмите, чтобы вывести дополнительные параметры соединения с сервером, такие как регистрация сервера и запоминание пароля.</span><span class="sxs-lookup"><span data-stu-id="fc5fe-137">Click to display additional server connection options, such as registering a server and remembering the password.</span></span>  
  
  
