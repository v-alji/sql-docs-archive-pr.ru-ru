---
title: Экземпляр зеркального сервера (мастер настройки безопасности зеркального отображения баз данных) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configdbmsecurwiz.mirrorsrvr.f1
ms.assetid: 53223432-615e-440f-904d-925d33ec2144
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 889e62af592d8d23f2aca0d752f1c7f535df883a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751452"
---
# <a name="mirror-server-instance-configure-database-mirroring-security-wizard"></a><span data-ttu-id="d8ad2-102">Экземпляр зеркального сервера (мастер настройки безопасности зеркального отображения баз данных)</span><span class="sxs-lookup"><span data-stu-id="d8ad2-102">Mirror Server Instance (Configure Database Mirroring Security Wizard)</span></span>
  <span data-ttu-id="d8ad2-103">Используйте данную страницу для задания информации об экземпляре сервера с зеркальной базой данных.</span><span class="sxs-lookup"><span data-stu-id="d8ad2-103">Use this page to specify information about the server instance with the mirror database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d8ad2-104">На экземпляре зеркального сервера должен работать тот же выпуск [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)](Standard или Enterprise), что и на экземпляре основного сервера.</span><span class="sxs-lookup"><span data-stu-id="d8ad2-104">The mirror server instance must be running the same edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], either Standard or Enterprise, as the principal server instance.</span></span> <span data-ttu-id="d8ad2-105">Кроме того, настоятельно рекомендуется размещать серверы в системах со сравнимой производительностью, которые могут справляться с одинаковой рабочей нагрузкой.</span><span class="sxs-lookup"><span data-stu-id="d8ad2-105">Also, we strongly recommend that they run on comparable systems that can handle identical workloads.</span></span>  
  
 <span data-ttu-id="d8ad2-106">**Настройка зеркального отображения базы данных в среде SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="d8ad2-106">**To configure database mirroring by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="d8ad2-107">Создание сеанса зеркального отображения базы данных с использованием проверки подлинности Windows (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="d8ad2-107">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="d8ad2-108">Запуск мастера настройки безопасности зеркального отображения баз данных (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="d8ad2-108">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="d8ad2-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="d8ad2-109">Options</span></span>  
 <span data-ttu-id="d8ad2-110">**Экземпляр зеркального сервера**</span><span class="sxs-lookup"><span data-stu-id="d8ad2-110">**Mirror server instance**</span></span>  
 <span data-ttu-id="d8ad2-111">Если экземпляр зеркального сервера уже задан (на странице **Зеркальное отображение** диалогового окна **Свойства базы данных** ), то он отображается. Дополнительные сведения см. в разделе [Свойства базы данных (страница "Зеркальное отображение")](../../relational-databases/databases/database-properties-mirroring-page.md).</span><span class="sxs-lookup"><span data-stu-id="d8ad2-111">If a mirror server instance is already specified (on the **Mirroring** page of the **Database Properties** dialog box), that instance is displayed; for more information, see [Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md).</span></span>  
  
 <span data-ttu-id="d8ad2-112">В противном случае введите имя экземпляра зеркального сервера.</span><span class="sxs-lookup"><span data-stu-id="d8ad2-112">Otherwise, enter the name of the mirror server instance.</span></span> <span data-ttu-id="d8ad2-113">Помните, что экземпляр зеркального сервера не может быть тем же самым, что и экземпляр основного сервера.</span><span class="sxs-lookup"><span data-stu-id="d8ad2-113">Note that the mirror server instance cannot be the same as the principal server instance.</span></span>  
  
 <span data-ttu-id="d8ad2-114">**Подключить**</span><span class="sxs-lookup"><span data-stu-id="d8ad2-114">**Connect**</span></span>  
 <span data-ttu-id="d8ad2-115">Если экземпляр зеркального сервера не указан, нажмите кнопку **Подключиться**.</span><span class="sxs-lookup"><span data-stu-id="d8ad2-115">If a mirror server instance has not been specified, click **Connect**.</span></span> <span data-ttu-id="d8ad2-116">При этом выводится диалоговое окно **Соединение с сервером** , в котором можно указать экземпляр сервера и установить с ним соединение.</span><span class="sxs-lookup"><span data-stu-id="d8ad2-116">This displays the **Connect to Server** dialog box in which you can specify the server instance and establish a connection.</span></span>  
  
 <span data-ttu-id="d8ad2-117">Если экземпляр был указан, но мастер не смог установить соединение с разрешениями, достаточными для проверки существования конечной точки, нажмите **Соединить**.</span><span class="sxs-lookup"><span data-stu-id="d8ad2-117">If the instance has been specified, but the wizard lacks a connection with sufficient permission to check for the existence of the endpoint, click **Connect**.</span></span> <span data-ttu-id="d8ad2-118">При этом выводится диалоговое окно **Соединение с сервером** с предварительно заданным и неизменяемым экземпляром сервера.</span><span class="sxs-lookup"><span data-stu-id="d8ad2-118">This displays the **Connect to Server** dialog box with the server instance pre-selected and unchangeable.</span></span> <span data-ttu-id="d8ad2-119">Укажите учетную запись домена, имеющую достаточные разрешения, и установите соединение с экземпляром сервера.</span><span class="sxs-lookup"><span data-stu-id="d8ad2-119">Specify a domain account with sufficient permission, and connect to the server instance.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d8ad2-120">При подключении к экземпляру сервера мастер настройки безопасности зеркального отображения баз данных использует учетные данные, представленные в диалоговом окне **Соединение с сервером** .</span><span class="sxs-lookup"><span data-stu-id="d8ad2-120">When connecting to the server instance, the Configure Database Mirroring Security Wizard uses the credentials provided in the **Connect to Server** dialog box.</span></span> <span data-ttu-id="d8ad2-121">Эти учетные данные отличаются от учетных данных сеанса зеркального отображения, использующего учетные данные стартовой учетной записи, в которой экземпляр сервера выполняется как служба.</span><span class="sxs-lookup"><span data-stu-id="d8ad2-121">These are different from the credentials of a mirroring session, which uses the credentials of the startup account where the server instance is running as a service.</span></span>  
  
 <span data-ttu-id="d8ad2-122">**Listener Port** (Порт прослушивателя)</span><span class="sxs-lookup"><span data-stu-id="d8ad2-122">**Listener Port**</span></span>  
 <span data-ttu-id="d8ad2-123">Поведение этого параметра зависит от того, существует ли конечная точка зеркального отображения для этого экземпляра сервера.</span><span class="sxs-lookup"><span data-stu-id="d8ad2-123">The behavior of this option depends on whether the mirroring endpoint exists for this server instance, as follows:</span></span>  
  
-   <span data-ttu-id="d8ad2-124">Если прослушиваемый порт не существует на экземпляре сервера, то в текстовом поле **Порт** отображается номер порта 5022.</span><span class="sxs-lookup"><span data-stu-id="d8ad2-124">If a listener port does not exist for the server instance, port number 5022 is displayed in the **Port** text box.</span></span> <span data-ttu-id="d8ad2-125">Можно использовать любой доступный порт, например 7022.</span><span class="sxs-lookup"><span data-stu-id="d8ad2-125">You can use any available port number, such as 7022.</span></span>  
  
-   <span data-ttu-id="d8ad2-126">Если конечная точка зеркального отображения уже существует, отображается номер порта от этой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="d8ad2-126">When the mirroring endpoint already exists, the port number from that endpoint is displayed.</span></span> <span data-ttu-id="d8ad2-127">Если необходимо изменить порт, используйте команду ALTER ENDPOINT.</span><span class="sxs-lookup"><span data-stu-id="d8ad2-127">If you need to change the port, use an ALTER ENDPOINT command.</span></span> <span data-ttu-id="d8ad2-128">Дополнительные сведения см. в статье [ALTER ENDPOINT (Transact-SQL)](/sql/t-sql/statements/alter-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d8ad2-128">For more information, see [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d8ad2-129">Номер порта обязателен.</span><span class="sxs-lookup"><span data-stu-id="d8ad2-129">A port number is required.</span></span>  
  
 <span data-ttu-id="d8ad2-130">**Имя конечной точки**</span><span class="sxs-lookup"><span data-stu-id="d8ad2-130">**Endpoint name**</span></span>  
 <span data-ttu-id="d8ad2-131">Если для данного экземпляра сервера существует конечная точка зеркального отображения, то здесь отображается имя конечной точки.</span><span class="sxs-lookup"><span data-stu-id="d8ad2-131">If the mirroring endpoint exists for this server instance, the endpoint name is displayed here.</span></span> <span data-ttu-id="d8ad2-132">Если конечная точка отсутствует, можно задать имя конечной точки.</span><span class="sxs-lookup"><span data-stu-id="d8ad2-132">If the endpoint does not exist, you can specify the name of the endpoint.</span></span>  
  
 <span data-ttu-id="d8ad2-133">**Шифровать данные, проходящие через эту конечную точку**</span><span class="sxs-lookup"><span data-stu-id="d8ad2-133">**Encrypt data sent through this endpoint**</span></span>  
 <span data-ttu-id="d8ad2-134">По умолчанию шифрование включено.</span><span class="sxs-lookup"><span data-stu-id="d8ad2-134">By default, encryption is enabled.</span></span> <span data-ttu-id="d8ad2-135">Если этот параметр включен, шифрование обязательно (а не просто поддерживается), а для всех параметров шифрования используются значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d8ad2-135">When enabled, encryption is required (not merely supported) and uses the default values for all of the encryption options.</span></span> <span data-ttu-id="d8ad2-136">Дополнительные сведения см. в разделе [CREATE ENDPOINT (Transact-SQL)](/sql/t-sql/statements/create-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d8ad2-136">For more information, see [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span></span>  
  
 <span data-ttu-id="d8ad2-137">Снимите этот флажок для выключения шифрования.</span><span class="sxs-lookup"><span data-stu-id="d8ad2-137">To disable encryption, clear the check box.</span></span> <span data-ttu-id="d8ad2-138">Установите этот флажок, чтобы вновь включить шифрование.</span><span class="sxs-lookup"><span data-stu-id="d8ad2-138">To re-enable encryption, select the check box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8ad2-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="d8ad2-139">See Also</span></span>  
 <span data-ttu-id="d8ad2-140">[Конечная точка зеркального отображения базы данных (SQL Server)](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d8ad2-140">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="d8ad2-141">[Свойства базы данных (страница "Зеркальное отображение")](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="d8ad2-141">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="d8ad2-142">[Создание конечной точки зеркального отображения базы данных с проверкой подлинности Windows (Transact-SQL)](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="d8ad2-142">[Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span></span>  
 <span data-ttu-id="d8ad2-143">[Запуск монитора зеркального отображения баз данных (среда SQL Server Management Studio)](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="d8ad2-143">[Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="d8ad2-144">Зеркальное отображение базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d8ad2-144">Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
  
