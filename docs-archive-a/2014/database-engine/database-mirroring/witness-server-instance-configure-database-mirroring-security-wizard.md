---
title: Экземпляр следящего сервера (мастер настройки безопасности зеркального отображения баз данных) | Документы Майкрософт
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configdbmsecurwiz.witnsrvr.f1
ms.assetid: b5763663-984a-473b-93a3-6cd3322ad41c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fcea7d39e1bc2c6161b5c6e1edd4852d9fdeb073
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657280"
---
# <a name="witness-server-instance-configure-database-mirroring-security-wizard"></a><span data-ttu-id="785c0-102">Экземпляр следящего сервера (мастер настройки безопасности зеркального отображения баз данных)</span><span class="sxs-lookup"><span data-stu-id="785c0-102">Witness Server Instance (Configure Database Mirroring Security Wizard)</span></span>
  <span data-ttu-id="785c0-103">Эта страница используется для задания сведений об экземпляре сервера, служащего в качестве средства слежения за сеансом.</span><span class="sxs-lookup"><span data-stu-id="785c0-103">Use this page to specify information about the server instance that is to serve as the witness for the session.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="785c0-104">Экземпляр следящего сервера доступен не во всех выпусках [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="785c0-104">A witness server instance is not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="785c0-105">Перечень функций, поддерживаемых в разных выпусках [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], см. в разделе [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="785c0-105">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
 <span data-ttu-id="785c0-106">**Настройка зеркального отображения базы данных в среде SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="785c0-106">**To configure database mirroring by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="785c0-107">Создание сеанса зеркального отображения базы данных с использованием проверки подлинности Windows (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="785c0-107">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="785c0-108">Запуск мастера настройки безопасности зеркального отображения баз данных (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="785c0-108">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="785c0-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="785c0-109">Options</span></span>  
 <span data-ttu-id="785c0-110">**Экземпляр следящего сервера**</span><span class="sxs-lookup"><span data-stu-id="785c0-110">**Witness server instance**</span></span>  
 <span data-ttu-id="785c0-111">Если экземпляр следящего сервера уже задан (на странице **Зеркальное отображение** диалогового окна **Свойства базы данных** ), то он отображается. Дополнительные сведения см. в разделе [Свойства базы данных (страница "Зеркальное отображение")](../../relational-databases/databases/database-properties-mirroring-page.md).</span><span class="sxs-lookup"><span data-stu-id="785c0-111">If a witness server instance is already specified (on the **Mirroring** page of the **Database Properties** dialog box), that instance is displayed (for more information, see [Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md)).</span></span>  
  
 <span data-ttu-id="785c0-112">В противном случае в этом списке отображается имя текущего сервера.</span><span class="sxs-lookup"><span data-stu-id="785c0-112">Otherwise, this list box displays the name of the current server.</span></span> <span data-ttu-id="785c0-113">Обратите внимание, что экземпляр следящего сервера не может одновременно быть экземпляром основного или зеркального сервера.</span><span class="sxs-lookup"><span data-stu-id="785c0-113">Be aware that the witness server instance cannot be the same as the principal or mirror server instances.</span></span>  
  
 <span data-ttu-id="785c0-114">**Подключить**</span><span class="sxs-lookup"><span data-stu-id="785c0-114">**Connect**</span></span>  
 <span data-ttu-id="785c0-115">Если экземпляр следящего сервера не задан, нажмите **Соединить**.</span><span class="sxs-lookup"><span data-stu-id="785c0-115">If a witness server instance has not been specified, click **Connect**.</span></span> <span data-ttu-id="785c0-116">При этом выводится диалоговое окно **Соединение с сервером** , в котором можно указать экземпляр сервера и установить с ним соединение.</span><span class="sxs-lookup"><span data-stu-id="785c0-116">This displays the **Connect to Server** dialog box in which you can specify the server instance and establish a connection.</span></span>  
  
 <span data-ttu-id="785c0-117">Если экземпляр был указан, но мастер не смог установить соединение с разрешениями, достаточными для проверки существования конечной точки, нажмите **Соединить**.</span><span class="sxs-lookup"><span data-stu-id="785c0-117">If the instance has been specified, but the wizard lacks a connection with sufficient permission to check for the existence of the endpoint, click **Connect**.</span></span> <span data-ttu-id="785c0-118">При этом выводится диалоговое окно **Соединение с сервером** с предварительно заданным и неизменяемым экземпляром сервера.</span><span class="sxs-lookup"><span data-stu-id="785c0-118">This displays the **Connect to Server** dialog box with the server instance pre-selected and unchangeable.</span></span> <span data-ttu-id="785c0-119">Укажите учетную запись домена, имеющую достаточные разрешения, и установите соединение с экземпляром сервера.</span><span class="sxs-lookup"><span data-stu-id="785c0-119">Specify a domain account with sufficient permission, and connect to the server instance.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="785c0-120">При подключении к экземпляру сервера мастер настройки безопасности зеркального отображения баз данных использует учетные данные, представленные в диалоговом окне **Соединение с сервером** .</span><span class="sxs-lookup"><span data-stu-id="785c0-120">When connecting to the server instance, the Configure Database Mirroring Security Wizard uses the credentials provided in the **Connect to Server** dialog box.</span></span> <span data-ttu-id="785c0-121">Эти учетные данные отличаются от учетных данных сеанса зеркального отображения, использующего учетные данные стартовой учетной записи, в которой экземпляр сервера выполняется как служба.</span><span class="sxs-lookup"><span data-stu-id="785c0-121">These are different from the credentials of a mirroring session, which uses the credentials of the startup account where the server instance is running as a service.</span></span>  
  
 <span data-ttu-id="785c0-122">**Listener Port** (Порт прослушивателя)</span><span class="sxs-lookup"><span data-stu-id="785c0-122">**Listener Port**</span></span>  
 <span data-ttu-id="785c0-123">Поведение этого параметра зависит от того, существует ли конечная точка зеркального отображения для этого экземпляра сервера.</span><span class="sxs-lookup"><span data-stu-id="785c0-123">The behavior of this option depends on whether the mirroring endpoint exists for this server instance, as follows:</span></span>  
  
-   <span data-ttu-id="785c0-124">Если в экземпляре сервера нет средства прослушивания, в текстовом поле **Порт** в качестве порта отображается порт с номером 5022.</span><span class="sxs-lookup"><span data-stu-id="785c0-124">If the listener port does not exist for the server instance, port number 5022 is displayed in the **Port** text box.</span></span> <span data-ttu-id="785c0-125">Можно ввести любой доступный номер порта, например 7022.</span><span class="sxs-lookup"><span data-stu-id="785c0-125">You can enter any available port number, such as, 7022.</span></span>  
  
-   <span data-ttu-id="785c0-126">Если конечная точка зеркального отображения уже существует, отображается номер порта конечной точки.</span><span class="sxs-lookup"><span data-stu-id="785c0-126">When the mirroring endpoint already exists, the port number from the endpoint is displayed.</span></span> <span data-ttu-id="785c0-127">Если необходимо изменить этот порт, используйте инструкцию ALTER ENDPOINT.</span><span class="sxs-lookup"><span data-stu-id="785c0-127">If you need to change that port, use an ALTER ENDPOINT statement.</span></span> <span data-ttu-id="785c0-128">Дополнительные сведения см. в статье [ALTER ENDPOINT (Transact-SQL)](/sql/t-sql/statements/alter-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="785c0-128">For more information, see [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="785c0-129">Номер порта обязателен.</span><span class="sxs-lookup"><span data-stu-id="785c0-129">A port number is required.</span></span>  
  
 <span data-ttu-id="785c0-130">**Имя конечной точки**</span><span class="sxs-lookup"><span data-stu-id="785c0-130">**Endpoint name**</span></span>  
 <span data-ttu-id="785c0-131">Если для данного экземпляра сервера существует конечная точка зеркального отображения, то здесь отображается имя конечной точки.</span><span class="sxs-lookup"><span data-stu-id="785c0-131">If the mirroring endpoint exists for this server instance, the endpoint name is displayed here.</span></span> <span data-ttu-id="785c0-132">Если конечная точка отсутствует, можно задать имя конечной точки.</span><span class="sxs-lookup"><span data-stu-id="785c0-132">If the endpoint does not exist, you can specify the name of the endpoint.</span></span>  
  
 <span data-ttu-id="785c0-133">**Шифровать данные, проходящие через эту конечную точку**</span><span class="sxs-lookup"><span data-stu-id="785c0-133">**Encrypt data sent through this endpoint**</span></span>  
 <span data-ttu-id="785c0-134">По умолчанию шифрование включено.</span><span class="sxs-lookup"><span data-stu-id="785c0-134">By default, encryption is enabled.</span></span> <span data-ttu-id="785c0-135">Если этот параметр включен, шифрование обязательно (а не просто поддерживается), а для всех параметров шифрования используются значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="785c0-135">When enabled, encryption is required (not merely supported) and uses the default values for all of the encryption options.</span></span> <span data-ttu-id="785c0-136">Дополнительные сведения см. в разделе [CREATE ENDPOINT (Transact-SQL)](/sql/t-sql/statements/create-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="785c0-136">For more information, see [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span></span>  
  
 <span data-ttu-id="785c0-137">Снимите этот флажок для выключения шифрования.</span><span class="sxs-lookup"><span data-stu-id="785c0-137">To disable encryption, clear the check box.</span></span> <span data-ttu-id="785c0-138">Установите этот флажок, чтобы вновь включить шифрование.</span><span class="sxs-lookup"><span data-stu-id="785c0-138">To re-enable encryption, select the check box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="785c0-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="785c0-139">See Also</span></span>  
 <span data-ttu-id="785c0-140">[Конечная точка зеркального отображения базы данных (SQL Server)](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="785c0-140">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="785c0-141">[Свойства базы данных (страница "Зеркальное отображение")](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="785c0-141">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="785c0-142">[Создание конечной точки зеркального отображения базы данных с проверкой подлинности Windows (Transact-SQL)](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="785c0-142">[Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span></span>  
 <span data-ttu-id="785c0-143">[Запуск монитора зеркального отображения баз данных (среда SQL Server Management Studio)](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="785c0-143">[Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="785c0-144">[Зеркальное отображение базы данных (SQL Server)](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="785c0-144">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="785c0-145">Следящий сервер зеркального отображения базы данных</span><span class="sxs-lookup"><span data-stu-id="785c0-145">Database Mirroring Witness</span></span>](database-mirroring-witness.md)  
  
  
