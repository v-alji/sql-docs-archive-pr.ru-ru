---
title: MSSQLSERVER_21879 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21879 (Database Engine error)
ms.assetid: fcfab735-05ca-423a-89f1-fdee7e2ed8c0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 08c5d4f45faf94d555ed7acedd90cc55ec4791ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734105"
---
# <a name="mssqlserver_21879"></a><span data-ttu-id="f16dd-102">MSSQLSERVER_21879</span><span class="sxs-lookup"><span data-stu-id="f16dd-102">MSSQLSERVER_21879</span></span>
    
## <a name="details"></a><span data-ttu-id="f16dd-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="f16dd-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f16dd-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="f16dd-104">Product Name</span></span>|<span data-ttu-id="f16dd-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f16dd-105">SQL Server</span></span>|  
|<span data-ttu-id="f16dd-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="f16dd-106">Event ID</span></span>|<span data-ttu-id="f16dd-107">21879</span><span class="sxs-lookup"><span data-stu-id="f16dd-107">21879</span></span>|  
|<span data-ttu-id="f16dd-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="f16dd-108">Event Source</span></span>|<span data-ttu-id="f16dd-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f16dd-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f16dd-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="f16dd-110">Component</span></span>|<span data-ttu-id="f16dd-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f16dd-111">SQLEngine</span></span>|  
|<span data-ttu-id="f16dd-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="f16dd-112">Symbolic Name</span></span>|<span data-ttu-id="f16dd-113">SQLErrorNum21879</span><span class="sxs-lookup"><span data-stu-id="f16dd-113">SQLErrorNum21879</span></span>|  
|<span data-ttu-id="f16dd-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="f16dd-114">Message Text</span></span>|<span data-ttu-id="f16dd-115">Не удалось выполнить запрос к перенаправленному серверу «%s» исходного издателя «%s» и базы данных издателя «%s», чтобы определить имя удаленного сервера. Ошибка %d, сообщение об ошибке «%s».</span><span class="sxs-lookup"><span data-stu-id="f16dd-115">Unable to query the redirected server '%s' for original publisher '%s' and publisher database '%s' to determine the name of the remote server; Error %d, Error message '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f16dd-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="f16dd-116">Explanation</span></span>  
 <span data-ttu-id="f16dd-117">`sp_validate_redirected_publisher` использует временно связанный сервер, создаваемый для подключения к перенаправленному издателю, чтобы обнаружить имя удаленного сервера.</span><span class="sxs-lookup"><span data-stu-id="f16dd-117">`sp_validate_redirected_publisher` uses a temporary linked server that it creates to connect to the redirected publisher in order to discover the name of the remote server.</span></span> <span data-ttu-id="f16dd-118">Ошибка 21879 возвращается при неудачном выполнении запроса к связанному серверу.</span><span class="sxs-lookup"><span data-stu-id="f16dd-118">Error 21879 is returned when the linked server query fails.</span></span> <span data-ttu-id="f16dd-119">Вызов для запроса имени удаленного сервера обычно является первым обращением ко временно связанному серверу, поэтому при наличии проблем с соединением они, скорее всего, проявятся при этом вызове.</span><span class="sxs-lookup"><span data-stu-id="f16dd-119">The call to request the remote server name is typically the first use of the temporary linked server, so if there are connectivity problems they are likely to appear first with this call.</span></span> <span data-ttu-id="f16dd-120">Этот удаленный вызов просто выполняет «select `@@servername`» на удаленном сервере.</span><span class="sxs-lookup"><span data-stu-id="f16dd-120">This remote call simply executes select `@@servername` at the remote server.</span></span>  
  
 <span data-ttu-id="f16dd-121">Связанный сервер, используемый для выполнения запроса перенаправляемого издателя, применяет режим безопасности, имя входа и пароль, заданные при вызове хранимой процедуры `sp_adddistpublisher` для исходного издателя.</span><span class="sxs-lookup"><span data-stu-id="f16dd-121">The linked server used to query the redirected publisher uses the security mode, login, and password supplied when `sp_adddistpublisher` was called for the original publisher.</span></span>  
  
-   <span data-ttu-id="f16dd-122">Если использовалась проверка подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (режим безопасности 0), то для подключения к удаленному серверу используются указанные имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="f16dd-122">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] authentication was used (security mode 0) then the login and password specified are used to connect to the remote server.</span></span>  
  
-   <span data-ttu-id="f16dd-123">Если используется проверка подлинности Windows (режим безопасности 1), то для соединения используется доверительное соединение.</span><span class="sxs-lookup"><span data-stu-id="f16dd-123">If Windows authentication was used (security mode 1) a trusted connection is used for the connection.</span></span>  
  
    -   <span data-ttu-id="f16dd-124">Если хранимая процедура `sp_validate_redirected_publisher` явно вызывается пользователем, то для соединения используется имя входа Windows, с помощью которого пользователь вошел в систему.</span><span class="sxs-lookup"><span data-stu-id="f16dd-124">If `sp_validate_redirected_publisher` is called explicitly by a user, the Windows login that the user is running under is used for the connection.</span></span>  
  
    -   <span data-ttu-id="f16dd-125">Если издатель хранимой процедуры `sp_validate_redirected_` вызывается агентом репликации из `sp_get_redirected_publisher`, то используется связанное с агентом имя входа Windows.</span><span class="sxs-lookup"><span data-stu-id="f16dd-125">If `sp_validate_redirected_`publisher is called by a replication agent from `sp_get_redirected_publisher`, the Windows login associated with the agent is used.</span></span>  
  
 <span data-ttu-id="f16dd-126">Ошибка 21879 может указывать, что хранимая процедура `sp_validate_redirected_publisher` была вызвана с именем входа, неизвестным на перенаправленном целевом издателе.</span><span class="sxs-lookup"><span data-stu-id="f16dd-126">Error 21879 can indicate that `sp_validate_redirected_publisher` was called using a login that is not known at the redirected target publisher.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f16dd-127">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="f16dd-127">User Action</span></span>  
 <span data-ttu-id="f16dd-128">Убедитесь, что имя входа, используемое для проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], или имя входа проверки подлинности Windows действительно на всех репликах группы доступности и имеет авторизацию для доступа к таблицам метаданных подписок (syssubscriptions и sysmergesubscriptions) в базе данных издателя.</span><span class="sxs-lookup"><span data-stu-id="f16dd-128">Make certain that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] authentication login or the Windows authentication login is valid at all of the availability group replicas and has sufficient authorization to access the subscription metadata tables (syssubscriptions and sysmergesubscriptions) in the publisher database.</span></span>  
  
 <span data-ttu-id="f16dd-129">Необходимо учитывать следующее, если ошибка 21879 возвращается из вызова хранимой процедуры `sp_get_redirected_publisher`, инициированного агентом репликации, который выполняется на отличном от распространителя узле, например когда агент слияния выполняется на подписчике.</span><span class="sxs-lookup"><span data-stu-id="f16dd-129">There are special considerations when error 21879 is returned from a call to `sp_get_redirected_publisher` that is initiated by a replication agent running on a node other that the distributor; such as a merge agent running at a subscriber.</span></span> <span data-ttu-id="f16dd-130">Если для соединения с перенаправленным издателем используется проверка подлинности Windows, то для успешной установки соединения необходимо настроить [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для проверки подлинности Kerberos.</span><span class="sxs-lookup"><span data-stu-id="f16dd-130">If Windows authentication is used for the connection to the redirected publisher, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be configured for Kerberos authentication for the connection to be successfully established.</span></span> <span data-ttu-id="f16dd-131">Когда используется проверка подлинности Windows, а [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не настроен для проверки подлинности Kerberos, выполняющийся на подписчике агент слияния получает ошибку 18456, указывающую на невозможность выполнения входа от имени «NT AUTHORITY\ANONYMOUS LOGON».</span><span class="sxs-lookup"><span data-stu-id="f16dd-131">When Windows authentication is used and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not configured for Kerberos authentication, error 18456 indicating that the 'NT AUTHORITY\ANONYMOUS LOGON' login failed, is received by a merge agent running at a subscriber.</span></span> <span data-ttu-id="f16dd-132">Существует три способа решения этой проблемы:</span><span class="sxs-lookup"><span data-stu-id="f16dd-132">There are three possible ways to address this issue:</span></span>  
  
-   <span data-ttu-id="f16dd-133">Настройка [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для проверки подлинности Kerberos.</span><span class="sxs-lookup"><span data-stu-id="f16dd-133">Configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for Kerberos authentication.</span></span> <span data-ttu-id="f16dd-134">Ознакомьтесь со статьей **Kerberos Authentication and SQL Server** (Проверка подлинности Kerberos и SQL Server) в электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f16dd-134">See **Kerberos Authentication and SQL Server** in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
-   <span data-ttu-id="f16dd-135">Используйте `sp_changedistpublisher` для изменения режима безопасности, связанного с исходным издателем в MSdistpublishers, а также для указания имени входа и пароля, используемых для соединения.</span><span class="sxs-lookup"><span data-stu-id="f16dd-135">Use `sp_changedistpublisher` to change the security mode associated with the original publisher in MSdistpublishers, as well as to specify a login and password to use for the connection.</span></span>  
  
-   <span data-ttu-id="f16dd-136">Укажите параметр командной строки *BypassPublisherValidation* в командной строке агента слияния, чтобы пропустить проверку при `sp_get_redirected_publisher` вызове на распространителе.</span><span class="sxs-lookup"><span data-stu-id="f16dd-136">Specify the command line parameter *BypassPublisherValidation* on the merge agent command line to bypass validation when `sp_get_redirected_publisher` is called at the distributor.</span></span>  
  
  
