---
title: Диалоговое окно "Свойства соединения" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connectionproperties.f1
helpviewer_keywords:
- Connection Properties dialog box
ms.assetid: 6df812ad-4d80-4503-8a23-47719ce85624
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: db2817ebaf3f1655f146c060fcb79d550ad0cc8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740346"
---
# <a name="connection-properties-dialog-box"></a><span data-ttu-id="dd394-102">диалоговое окно «Свойства соединения»</span><span class="sxs-lookup"><span data-stu-id="dd394-102">Connection Properties Dialog Box</span></span>
  <span data-ttu-id="dd394-103">Используйте это диалоговое окно, чтобы просмотреть свойства текущего соединения.</span><span class="sxs-lookup"><span data-stu-id="dd394-103">Use this dialog box to view the current connection properties.</span></span> <span data-ttu-id="dd394-104">Доступ к этому диалоговому окну можно получить, щелкнув на пункте **Просмотреть свойства соединений** в различных диалоговых окнах обозревателя объектов.</span><span class="sxs-lookup"><span data-stu-id="dd394-104">This dialog box is available when you click **View connection properties** in various Object Explorer dialog boxes.</span></span> <span data-ttu-id="dd394-105">Свойства, отображаемые на этой странице, имеют статус «только для чтения».</span><span class="sxs-lookup"><span data-stu-id="dd394-105">The properties displayed on this page are read-only.</span></span>  
  
 <span data-ttu-id="dd394-106">Чтобы изменить значение свойства **База данных**и других свойств, прежде чем открывать диалоговое окно **Свойства соединения** , установите соединение с базой данных через обозреватель объектов.</span><span class="sxs-lookup"><span data-stu-id="dd394-106">To change properties such as **Database**, connect to the desired database with Object Explorer before opening the **Connection Properties** dialog box.</span></span>  
  
 <span data-ttu-id="dd394-107">Обратите внимание, что время ожидания запроса для SQL Azure составляет 30 минут.</span><span class="sxs-lookup"><span data-stu-id="dd394-107">Note that the query time-out period for SQL Azure is 30 minutes.</span></span>  
  
## <a name="authentication"></a><span data-ttu-id="dd394-108">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="dd394-108">Authentication</span></span>  
 <span data-ttu-id="dd394-109">Просмотрите свойства проверки подлинности для текущего соединения.</span><span class="sxs-lookup"><span data-stu-id="dd394-109">View authentication properties for the current connection.</span></span> <span data-ttu-id="dd394-110">Свойства проверки подлинности — это входное имя и метод проверки подлинности при установке соединения.</span><span class="sxs-lookup"><span data-stu-id="dd394-110">Authentication properties are the login and authentication method when the connection was established.</span></span> <span data-ttu-id="dd394-111">Чтобы изменить свойства проверки подлинности, отключитесь от [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] и снова подключите обозреватель объектов к серверу, используя необходимые параметры соединения.</span><span class="sxs-lookup"><span data-stu-id="dd394-111">To change the authentication properties, disconnect from [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], and then connect Object Explorer to the server again, using the desired connection options.</span></span>  
  
 <span data-ttu-id="dd394-112">**Метод проверки подлинности**</span><span class="sxs-lookup"><span data-stu-id="dd394-112">**Authentication Method**</span></span>  
 <span data-ttu-id="dd394-113">Метод проверки подлинности, используемый для текущего соединения.</span><span class="sxs-lookup"><span data-stu-id="dd394-113">The authentication method used for the current connection.</span></span>  
  
 <span data-ttu-id="dd394-114">**Имя пользователя**</span><span class="sxs-lookup"><span data-stu-id="dd394-114">**User Name**</span></span>  
 <span data-ttu-id="dd394-115">Имя пользователя для имени входа, используемого для проверки подлинности при установке соединения.</span><span class="sxs-lookup"><span data-stu-id="dd394-115">The name of the user of login used for the connection authentication.</span></span>  
  
## <a name="connection-category"></a><span data-ttu-id="dd394-116">Категория соединения</span><span class="sxs-lookup"><span data-stu-id="dd394-116">Connection Category</span></span>  
 <span data-ttu-id="dd394-117">Просмотрите свойства соединения для текущего соединения.</span><span class="sxs-lookup"><span data-stu-id="dd394-117">View connection properties for the current connection.</span></span> <span data-ttu-id="dd394-118">Большинство свойств соединения были указаны на вкладке **Свойства соединения** диалогового окна **Соединение с сервером** в процессе установки соединения.</span><span class="sxs-lookup"><span data-stu-id="dd394-118">Most connection properties were selected on the **Connection Properties** tab of the **Connect to server** dialog box during the connection process.</span></span>  
  
 <span data-ttu-id="dd394-119">**База данных**</span><span class="sxs-lookup"><span data-stu-id="dd394-119">**Database**</span></span>  
 <span data-ttu-id="dd394-120">Имя базы данных, с которой установлено текущее соединение.</span><span class="sxs-lookup"><span data-stu-id="dd394-120">The name of the database currently connected to.</span></span> <span data-ttu-id="dd394-121">Чтобы изменить этот параметр, используйте панель инструментов «Редактор SQL».</span><span class="sxs-lookup"><span data-stu-id="dd394-121">To change this use, the SQL Editor toolbar.</span></span>  
  
 <span data-ttu-id="dd394-122">**SPID**</span><span class="sxs-lookup"><span data-stu-id="dd394-122">**SPID**</span></span>  
 <span data-ttu-id="dd394-123">Идентификатор системного процесса, присваиваемый сервером соединению.</span><span class="sxs-lookup"><span data-stu-id="dd394-123">The system process ID assigned by the server to the connection.</span></span> <span data-ttu-id="dd394-124">Этот параметр не может быть изменен для данного соединения.</span><span class="sxs-lookup"><span data-stu-id="dd394-124">This cannot be changed for this connection.</span></span>  
  
 <span data-ttu-id="dd394-125">**Сетевой протокол**</span><span class="sxs-lookup"><span data-stu-id="dd394-125">**Network Protocol**</span></span>  
 <span data-ttu-id="dd394-126">Сетевой протокол соединения среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dd394-126">The network protocol of the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] connection.</span></span> <span data-ttu-id="dd394-127">Чтобы изменить этот параметр, установите соединение заново с нужными параметрами.</span><span class="sxs-lookup"><span data-stu-id="dd394-127">To change this, connect again with the desired connection properties.</span></span>  
  
 <span data-ttu-id="dd394-128">**Размер сетевого пакета**</span><span class="sxs-lookup"><span data-stu-id="dd394-128">**Network Packet Size**</span></span>  
 <span data-ttu-id="dd394-129">Размер пакетов, используемых при обмене данными с сервером.</span><span class="sxs-lookup"><span data-stu-id="dd394-129">The packet size used when communicating with the server.</span></span> <span data-ttu-id="dd394-130">Чтобы изменить этот параметр, установите соединение заново с нужными параметрами.</span><span class="sxs-lookup"><span data-stu-id="dd394-130">To change this, connect again with the desired connection properties.</span></span>  
  
 <span data-ttu-id="dd394-131">**Время ожидания подключения**</span><span class="sxs-lookup"><span data-stu-id="dd394-131">**Connection Timeout**</span></span>  
 <span data-ttu-id="dd394-132">При попытке установить соединение с [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] — время ожидания в секундах, по истечении которого пользователю возвращается уведомление об ошибке соединения.</span><span class="sxs-lookup"><span data-stu-id="dd394-132">The amount of time is seconds to wait when connecting to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] before timing out and returning a failure to connect error to the user.</span></span> <span data-ttu-id="dd394-133">Чтобы изменить этот параметр, установите соединение заново с нужными параметрами.</span><span class="sxs-lookup"><span data-stu-id="dd394-133">To change this, connect again with the desired connection properties.</span></span>  
  
 <span data-ttu-id="dd394-134">**Время ожидания выполнения**</span><span class="sxs-lookup"><span data-stu-id="dd394-134">**Execution Timeout**</span></span>  
 <span data-ttu-id="dd394-135">Время ожидания в секундах, истекающее прежде, чем выполнение задачи на сервере, завершено.</span><span class="sxs-lookup"><span data-stu-id="dd394-135">The amount of time in seconds to wait before execution of a task is completed on the server.</span></span> <span data-ttu-id="dd394-136">Чтобы изменить этот параметр, установите соединение заново с нужными параметрами.</span><span class="sxs-lookup"><span data-stu-id="dd394-136">To change this, connect again with the desired connection properties.</span></span>  
  
 <span data-ttu-id="dd394-137">**Зашифрована**</span><span class="sxs-lookup"><span data-stu-id="dd394-137">**Encrypted**</span></span>  
 <span data-ttu-id="dd394-138">Указывает на то, что текущее соединение зашифровано.</span><span class="sxs-lookup"><span data-stu-id="dd394-138">Whether the current connection is encrypted.</span></span> <span data-ttu-id="dd394-139">Чтобы изменить этот параметр, установите соединение заново с нужными параметрами.</span><span class="sxs-lookup"><span data-stu-id="dd394-139">To change this, connect again with the desired connection properties.</span></span>  
  
## <a name="product-category"></a><span data-ttu-id="dd394-140">Категория продуктов</span><span class="sxs-lookup"><span data-stu-id="dd394-140">Product Category</span></span>  
 <span data-ttu-id="dd394-141">Просмотрите свойства продукта для текущего соединения.</span><span class="sxs-lookup"><span data-stu-id="dd394-141">View product properties for the current connection.</span></span> <span data-ttu-id="dd394-142">Эти свойства описывают серверный продукт, версию, имя экземпляра и параметры сортировки.</span><span class="sxs-lookup"><span data-stu-id="dd394-142">These properties describe the server product, version, instance name, and collation.</span></span> <span data-ttu-id="dd394-143">Указанные свойства определяются в процессе установки [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dd394-143">The properties are set during [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] installation.</span></span>  
  
 <span data-ttu-id="dd394-144">**Название продукта**</span><span class="sxs-lookup"><span data-stu-id="dd394-144">**Product Name**</span></span>  
 <span data-ttu-id="dd394-145">Имя продукта [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dd394-145">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] product name.</span></span>  
  
 <span data-ttu-id="dd394-146">**Версия продукта**</span><span class="sxs-lookup"><span data-stu-id="dd394-146">**Product Version**</span></span>  
 <span data-ttu-id="dd394-147">Номер версии продукта [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dd394-147">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] product version.</span></span>  
  
 <span data-ttu-id="dd394-148">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="dd394-148">**Server Name**</span></span>  
 <span data-ttu-id="dd394-149">Имя компьютера, на котором работает [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd394-149">The name of the computer running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="dd394-150">**Имя экземпляра**</span><span class="sxs-lookup"><span data-stu-id="dd394-150">**Instance Name**</span></span>  
 <span data-ttu-id="dd394-151">Имя экземпляра сервера.</span><span class="sxs-lookup"><span data-stu-id="dd394-151">The instance name of the server.</span></span> <span data-ttu-id="dd394-152">По умолчанию имя экземпляра не указывается.</span><span class="sxs-lookup"><span data-stu-id="dd394-152">The default instance is blank.</span></span>  
  
 <span data-ttu-id="dd394-153">**Язык**</span><span class="sxs-lookup"><span data-stu-id="dd394-153">**Language**</span></span>  
 <span data-ttu-id="dd394-154">Языковая версия продукта [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dd394-154">The language version of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] product.</span></span>  
  
 <span data-ttu-id="dd394-155">**Параметры сортировки**</span><span class="sxs-lookup"><span data-stu-id="dd394-155">**Collation**</span></span>  
 <span data-ttu-id="dd394-156">Параметры сортировки сервера.</span><span class="sxs-lookup"><span data-stu-id="dd394-156">The collation of the server.</span></span>  
  
## <a name="server-environment-category"></a><span data-ttu-id="dd394-157">Категория серверной среды</span><span class="sxs-lookup"><span data-stu-id="dd394-157">Server Environment Category</span></span>  
 <span data-ttu-id="dd394-158">Просмотрите свойства серверной среды для текущего соединения, связанные с оборудованием сервера и его операционной системой.</span><span class="sxs-lookup"><span data-stu-id="dd394-158">View server environment properties for the current connection related to the server hardware and operating system.</span></span> <span data-ttu-id="dd394-159">Эти свойства не могут быть изменены [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd394-159">The properties cannot be configured by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="dd394-160">**Имя компьютера**</span><span class="sxs-lookup"><span data-stu-id="dd394-160">**Computer Name**</span></span>  
 <span data-ttu-id="dd394-161">Имя серверного компьютера, на котором работает [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd394-161">The name of the server computer that is running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="dd394-162">**Платформа**</span><span class="sxs-lookup"><span data-stu-id="dd394-162">**Platform**</span></span>  
 <span data-ttu-id="dd394-163">Имя операционной системы, имя изготовителя и семейство, к которому принадлежит процессор сервера.</span><span class="sxs-lookup"><span data-stu-id="dd394-163">The operating system name, manufacturer name, and CPU family of the server.</span></span>  
  
 <span data-ttu-id="dd394-164">**Операционная система**</span><span class="sxs-lookup"><span data-stu-id="dd394-164">**Operating System**</span></span>  
 <span data-ttu-id="dd394-165">Версия [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows, установленная на сервере.</span><span class="sxs-lookup"><span data-stu-id="dd394-165">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows version installed on the server.</span></span>  
  
 <span data-ttu-id="dd394-166">**Процессоры**</span><span class="sxs-lookup"><span data-stu-id="dd394-166">**Processors**</span></span>  
 <span data-ttu-id="dd394-167">Количество процессоров в сервере.</span><span class="sxs-lookup"><span data-stu-id="dd394-167">The number of processors on the server.</span></span>  
  
 <span data-ttu-id="dd394-168">**Память операционной системы**</span><span class="sxs-lookup"><span data-stu-id="dd394-168">**Operating System Memory**</span></span>  
 <span data-ttu-id="dd394-169">Общий объем физической памяти сервера, в мегабайтах.</span><span class="sxs-lookup"><span data-stu-id="dd394-169">The total amount of physical memory on the server, in megabytes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd394-170">См. также:</span><span class="sxs-lookup"><span data-stu-id="dd394-170">See Also</span></span>  
 <span data-ttu-id="dd394-171">[Страницы свойств в SQL Server Management Studio](../ssms/property-pages-in-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="dd394-171">[Property Pages in SQL Server Management Studio](../ssms/property-pages-in-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="dd394-172">Соединение с сервером (страница входа) — ядро СУБД</span><span class="sxs-lookup"><span data-stu-id="dd394-172">Connect to Server &#40;Login Page&#41; Database Engine</span></span>](../ssms/f1-help/connect-to-server-login-page-database-engine.md)  
  
  
