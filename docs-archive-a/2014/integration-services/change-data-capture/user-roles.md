---
title: Роли пользователей для Change Data Capture Service для Oracle по Attunity | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: be0ec384-e03b-4483-96ca-02b289804d6a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e694da0cfd8645fe594b049b6dc2394b55d1bb55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735505"
---
# <a name="user-roles-for-change-data-capture-service-for-oracle-by-attunity"></a><span data-ttu-id="4845e-102">Роли пользователя для изменения служб отслеживания данных для Oracle от Attunity.</span><span class="sxs-lookup"><span data-stu-id="4845e-102">User Roles for Change Data Capture Service for Oracle by Attunity</span></span>
  <span data-ttu-id="4845e-103">В этом разделе описываются роли пользователей для службы системы отслеживания измененных данных для Oracle компании Attunity.</span><span class="sxs-lookup"><span data-stu-id="4845e-103">This section describes the user roles for the Change Data Capture Service for Oracle by Attunity.</span></span> <span data-ttu-id="4845e-104">Описываемые роли — это роли базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , роли Windows или роли базы данных Oracle.</span><span class="sxs-lookup"><span data-stu-id="4845e-104">The roles described are [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database roles, Windows roles, or Oracle database roles.</span></span>  
  
## <a name="windows-user-roles"></a><span data-ttu-id="4845e-105">Роли пользователей Windows</span><span class="sxs-lookup"><span data-stu-id="4845e-105">Windows User Roles</span></span>  
 <span data-ttu-id="4845e-106">Ниже описываются роли пользователей Windows, которые используются службой Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="4845e-106">The following describes the Windows user roles used by the Oracle CDC Service.</span></span>  
  
### <a name="computer-administrator-oracle-cdc-service"></a><span data-ttu-id="4845e-107">Администратор компьютера: служба Oracle CDC Service</span><span class="sxs-lookup"><span data-stu-id="4845e-107">Computer Administrator: Oracle CDC Service</span></span>  
 <span data-ttu-id="4845e-108">Администратор компьютера — это пользователь Windows, который отвечает за создание и поддержание службы CDC на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4845e-108">The computer administrator is a Windows user responsible for creating and maintaining the CDC Service on the computer.</span></span> <span data-ttu-id="4845e-109">Этот пользователь должен принадлежать к группе администраторов локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="4845e-109">This user must belong to the group of local machine administrators.</span></span>  
  
 <span data-ttu-id="4845e-110">Задачи, выполняемые администратором компьютера, на котором запущены службы Oracle CDC, включают в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="4845e-110">The tasks performed by the Oracle CDC Service Computer Administrator include:</span></span>  
  
-   <span data-ttu-id="4845e-111">Установка службы CDC для программного обеспечения Oracle</span><span class="sxs-lookup"><span data-stu-id="4845e-111">Installing the CDC Service for Oracle software</span></span>  
  
-   <span data-ttu-id="4845e-112">Создание службы Oracle CDC для Windows</span><span class="sxs-lookup"><span data-stu-id="4845e-112">Creating an Oracle CDC Windows service</span></span>  
  
-   <span data-ttu-id="4845e-113">Установка подключения службы CDC к целевому экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (строка подключения и учетные данные)</span><span class="sxs-lookup"><span data-stu-id="4845e-113">Setting up the CDC Service connection to the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance (connection string and credentials)</span></span>  
  
-   <span data-ttu-id="4845e-114">Обеспечение защиты главного пароля службы CDC, используемого для интеллектуального анализа журнала Oracle</span><span class="sxs-lookup"><span data-stu-id="4845e-114">Ensuring that the CDC Service Master Password with which Oracle log mining credentials are protected</span></span>  
  
-   <span data-ttu-id="4845e-115">Удаление службы CDC в Windows</span><span class="sxs-lookup"><span data-stu-id="4845e-115">Deleting a CDC Service Windows service</span></span>  
  
-   <span data-ttu-id="4845e-116">Удаление программного обеспечения службы CDC для Oracle</span><span class="sxs-lookup"><span data-stu-id="4845e-116">Uninstalling the CDC Service for Oracle software</span></span>  
  
-   <span data-ttu-id="4845e-117">Поддержка службы CDC для ПО Oracle (например, установка обновлений)</span><span class="sxs-lookup"><span data-stu-id="4845e-117">Maintaining the CDC Service for Oracle software (for example, installing updates)</span></span>  
  
-   <span data-ttu-id="4845e-118">Запуск и остановка службы Windows CDC</span><span class="sxs-lookup"><span data-stu-id="4845e-118">Starting and stopping a CDC Service Windows service</span></span>  
  
 <span data-ttu-id="4845e-119">При работе с конфигурациями, обеспечивающими высокий уровень доступности, например с отказоустойчивыми кластерами Microsoft, администратор компьютера должен обладать дополнительными разрешениями, а также на него возлагаются дополнительные задачи, такие как:</span><span class="sxs-lookup"><span data-stu-id="4845e-119">When working with high-availability configurations, such as Microsoft failover clusters, the computer administrator must have additional responsibilities and permissions such as:</span></span>  
  
-   <span data-ttu-id="4845e-120">Установка и сопровождение службы CDC для программного обеспечения Oracle на всех узлах кластера.</span><span class="sxs-lookup"><span data-stu-id="4845e-120">Installation and maintenance of the CDC Service for Oracle software on all cluster nodes.</span></span>  
  
-   <span data-ttu-id="4845e-121">Определение ресурсов службы общих кластеров для службы CDC в Windows на различных узлах кластера.</span><span class="sxs-lookup"><span data-stu-id="4845e-121">Defining generic cluster service resources for the CDC Service' Windows service on the various cluster nodes.</span></span>  
  
-   <span data-ttu-id="4845e-122">Выполнение действий администратора компьютера, прошедшего проверку подлинности в качестве администратора на компьютере, на котором установлена служба CDC для Oracle.</span><span class="sxs-lookup"><span data-stu-id="4845e-122">Acting as the computer administrator authorized as an administrator on the computer where the CDC Service for Oracle is installed.</span></span> <span data-ttu-id="4845e-123">Это лицо устанавливает службу CDC для Oracle и использует консоль конфигурации службы CDC для настройки службы CDC для Oracle на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="4845e-123">This person installs the CDC Service for Oracle and uses the CDC Service Configuration Console to configure a CDC Service for Oracle on a local computer.</span></span>  
  
### <a name="service-account-oracle-cdc-service"></a><span data-ttu-id="4845e-124">Учетная запись службы: служба Oracle CDC Service</span><span class="sxs-lookup"><span data-stu-id="4845e-124">Service Account: Oracle CDC Service</span></span>  
 <span data-ttu-id="4845e-125">Это учетная запись службы Windows для службы Oracle CDC, которая является учетной записью Windows, используемой для запуска службы Oracle CDC (учетная запись службы).</span><span class="sxs-lookup"><span data-stu-id="4845e-125">This is Oracle CDC Service Windows Service Account is a Windows account used for running the Oracle CDC Service (the Service Account).</span></span>  
  
 <span data-ttu-id="4845e-126">Единственные необходимые права для этой учетной записи службы заключаются в разрешении на использование клиента Oracle и собственного клиента Native Client источника данных ODBC для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4845e-126">The only required privilege necessary for the service account is to be able to use the Oracle client and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native client ODBC provider.</span></span> <span data-ttu-id="4845e-127">Этой учетной записи не нужен доступ к файлам, если это не требуется для конкретных поставщиков (например, если строка подключения клиента Oracle обращается к экземплярам базы данных Oracle в файле **tnsnames.ora** , то к этому файлу необходим доступ учетной записи службы для чтения).</span><span class="sxs-lookup"><span data-stu-id="4845e-127">This account does not need to access files unless required by specific providers (for example, if the Oracle client connection string references Oracle database instances in a **tnsnames.ora** file, then that file must be read-accessible to the service account).</span></span>  
  
 <span data-ttu-id="4845e-128">При создании службы Oracle CDC в среде Windows Vista или Windows Server 2008 учетной записью службы по умолчанию является NETWORK SERVICE.</span><span class="sxs-lookup"><span data-stu-id="4845e-128">When creating an Oracle CDC Service on Windows Vista or Windows Server 2008, the default service account is the NETWORK SERVICE account.</span></span>  
  
 <span data-ttu-id="4845e-129">В Windows 7, Windows Server 2008 R2 и более поздних версиях в качестве учетной записи службы по умолчанию используется NT Service\\<имя-службы>.</span><span class="sxs-lookup"><span data-stu-id="4845e-129">On Windows 7, Windows Server 2008 R2 and later, the default service account is NT Service\\<service-name>.</span></span>  
  
 <span data-ttu-id="4845e-130">Если [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] запущен на другом компьютере или является кластеризованным экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , для которого необходимо подключение службы к целевому экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] при использовании проверки подлинности Windows, то учетная запись службы должна быть доменной учетной записью.</span><span class="sxs-lookup"><span data-stu-id="4845e-130">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] runs on another machine or is a clustered [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance and there the service needs to connect to the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Windows authentication, then the service account should be a domain account.</span></span>  
  
## <a name="sql-server-user-roles"></a><span data-ttu-id="4845e-131">Роли пользователей SQL Server</span><span class="sxs-lookup"><span data-stu-id="4845e-131">SQL Server User Roles</span></span>  
 <span data-ttu-id="4845e-132">Ниже описываются роли пользователей [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которые используются службой Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="4845e-132">The following describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user roles used by the Oracle CDC Service.</span></span>  
  
### <a name="oracle-cdc-service-administrator"></a><span data-ttu-id="4845e-133">Администратор службы Oracle CDC</span><span class="sxs-lookup"><span data-stu-id="4845e-133">Oracle CDC Service Administrator</span></span>  
 <span data-ttu-id="4845e-134">Администратор службы CDC — это пользователь [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , обладающий правами полного доступа к артефактам службы Oracle CDC в целевом экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4845e-134">The CDC Service Administrator is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user with full control over the Oracle CDC Service artifacts in the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="4845e-135">Администратор службы CDC использует консоль конструктора Oracle CDC для разработки экземпляров Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="4845e-135">The CDC Service Administrator uses the Oracle CDC Designer Console to design Oracle CDC Instances.</span></span>  
  
 <span data-ttu-id="4845e-136">Администратору службы CDC необходимо предоставить предопределенные роли сервера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**public** и **dbcreator**.</span><span class="sxs-lookup"><span data-stu-id="4845e-136">The CDC Service Administrator should be granted the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fixed server roles **public** and **dbcreator**.</span></span>  
  
 <span data-ttu-id="4845e-137">Среди задач, выполняемых администратором службы CDC, имеются следующие:</span><span class="sxs-lookup"><span data-stu-id="4845e-137">The tasks performed by the CDC Service Administrator include:</span></span>  
  
-   <span data-ttu-id="4845e-138">Подготовка экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для размещения экземпляров Oracle CDC (представляющих собой базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="4845e-138">Preparing a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance to host Oracle CDC Instances (which are [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases).</span></span> <span data-ttu-id="4845e-139">Для решения этой задачи на экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] создается специальная база данных с именем MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="4845e-139">In this task, a special database called MSXDBCDC is created in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
-   <span data-ttu-id="4845e-140">Создание базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] экземпляра Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="4845e-140">Creating an Oracle CDC Instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="4845e-141">Задача включает использование созданной базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для CDC, для чего необходима роль системного администратора [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (**sysadmin**).</span><span class="sxs-lookup"><span data-stu-id="4845e-141">Task includes enabling the newly created [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database for CDC, which requires a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator (**sysadmin**).</span></span>  
  
-   <span data-ttu-id="4845e-142">Проектирование экземпляра Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="4845e-142">Designing an Oracle CDC Instance.</span></span> <span data-ttu-id="4845e-143">Эта задача включает в себя предоставление информации об исходной базе данных Oracle и отслеживаемых таблицах, а для этого необходима роль администратора базы данных Oracle.</span><span class="sxs-lookup"><span data-stu-id="4845e-143">This task includes providing information about the source Oracle database and captured tables, which requires an Oracle database administrator.</span></span>  
  
-   <span data-ttu-id="4845e-144">Поддержка экземпляра Oracle CDC в течение длительного периода, которая подразумевает добавление/удаление отслеживаемых экземпляров и обновление конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4845e-144">Maintaining the Oracle CDC Instance over time, which includes adding/removing capture instances and updating configuration.</span></span>  
  
-   <span data-ttu-id="4845e-145">Включение или отключение экземпляра Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="4845e-145">Enabling or disabling an Oracle CDC Instance.</span></span>  
  
-   <span data-ttu-id="4845e-146">Мониторинг состояния экземпляра Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="4845e-146">Monitoring the state of an Oracle CDC Instance.</span></span>  
  
-   <span data-ttu-id="4845e-147">Устранение неполадок, которые влияют на экземпляр CDC Oracle.</span><span class="sxs-lookup"><span data-stu-id="4845e-147">Troubleshooting issues that affect the Oracle CDC Instance.</span></span>  
  
 <span data-ttu-id="4845e-148">Администратор службы CDC обладает, по крайней мере первоначально, предопределенной ролью базы данных **db_owner** в базе данных CDC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , связанной с экземпляром Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="4845e-148">The CDC Service Administrator is, at least initially, in the **db_owner** fixed database role for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC database associated with the Oracle CDC Instance.</span></span> <span data-ttu-id="4845e-149">Это дает администратору службы CDC необходимый доступ к информации об изменениях, хранящихся в базе CDC.</span><span class="sxs-lookup"><span data-stu-id="4845e-149">This gives the CDC Service Administrator access to the change data stored in the CDC database.</span></span> <span data-ttu-id="4845e-150">Роль **db_owner** для базы данных CDC после создания можно назначить другому пользователю, который может выполнять все указанные выше задачи, кроме подготовки экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и создания другого экземпляра Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="4845e-150">Once created, the **db_owner** role of the CDC database can be assigned to a different user who can carry out all of the tasks listed above except for preparing a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance and creating another Oracle CDC Instance).</span></span>  
  
 <span data-ttu-id="4845e-151">Администратору службы CDC не обязательно знать главный пароль, создаваемый одновременно со службой Windows для Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="4845e-151">The CDC Service Administrator does not need to know the master password specified with the creation of the Oracle CDC Windows service.</span></span>  
  
### <a name="system-administrator"></a><span data-ttu-id="4845e-152">Системный администратор</span><span class="sxs-lookup"><span data-stu-id="4845e-152">System Administrator</span></span>  
 <span data-ttu-id="4845e-153">Системный администратор [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] — это пользователь [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которому необходимо назначить предопределенную роль сервера **sysadmin** в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , связанном со службами Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="4845e-153">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user and should be granted the fixed server **sysadmin** role on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance associated with the Oracle CDC Service(s).</span></span>  
  
 <span data-ttu-id="4845e-154">Существует только одна специальная задача Oracle CDC, которая должна выполняться системным администратором [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , и она состоит в том, чтобы включить базу данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для взаимодействия с экземпляром Oracle CDC для CDC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4845e-154">There is only one Oracle CDC specific task that carried out with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] System Administrator and that is to enable the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database for an Oracle CDC Instance for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC.</span></span> <span data-ttu-id="4845e-155">Эта задача выполняется с помощью консоли конструктора Oracle CDC при создании нового экземпляра Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="4845e-155">This task is performed using the Oracle CDC Designer console when creating a new Oracle CDC Instance.</span></span>  
  
### <a name="oracle-cdc-service-user"></a><span data-ttu-id="4845e-156">Пользователь службы Oracle CDC</span><span class="sxs-lookup"><span data-stu-id="4845e-156">Oracle CDC Service User</span></span>  
 <span data-ttu-id="4845e-157">Пользователь службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC — это имя входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , используемое службой Oracle CDC для выполнения задач при взаимодействии с MSXDBCDC и всеми экземплярами Oracle CDC (базами данных CDC), обрабатываемыми этой службой.</span><span class="sxs-lookup"><span data-stu-id="4845e-157">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC Service user is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login which is used by the Oracle CDC Service to perform its work against the MSXDBCDC and all of the Oracle CDC Instances (CDC databases) handled by this service.</span></span>  
  
 <span data-ttu-id="4845e-158">Пользователю службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC необходимо предоставить следующие права:</span><span class="sxs-lookup"><span data-stu-id="4845e-158">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC Service user should be granted the following:</span></span>  
  
-   <span data-ttu-id="4845e-159">Членство в предопределенных ролях **db_dlladmin**, **db_datareader**и **db_datawriter** для всех баз данных CDC, обрабатываемых этим сервером.</span><span class="sxs-lookup"><span data-stu-id="4845e-159">Member of the fixed database roles **db_dlladmin**, **db_datareader**, and **db_datawriter** for all CDC databases handled by the server.</span></span>  
  
-   <span data-ttu-id="4845e-160">Членство в предопределенных ролях баз данных **db_datareader** и **db_datawriter** для базы данных MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="4845e-160">Member of the fixed database roles **db_datareader** and **db_datawriter** for the MSXDBCDC database.</span></span>  
  
 <span data-ttu-id="4845e-161">Поскольку служба Oracle CDC использует одно имя входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для работы со всеми базами данных CDC и базы данных MSXDBCDC, это имя входа необходимо назначить для всех этих баз данных.</span><span class="sxs-lookup"><span data-stu-id="4845e-161">Because the Oracle CDC Service uses a single [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to work with all CDC databases and the MSXDBCDC database, this login should be mapped in all of these databases.</span></span>  
  
### <a name="oracle-cdc-change-consumer"></a><span data-ttu-id="4845e-162">Потребитель изменений Oracle CDC</span><span class="sxs-lookup"><span data-stu-id="4845e-162">Oracle CDC Change Consumer</span></span>  
 <span data-ttu-id="4845e-163">Потребитель изменений Oracle CDC Change Consumer — это пользователь [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , который потребляет изменения, сохраняемые в таблицах CDC в базе данных экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="4845e-163">The Oracle CDC Change Consumer is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user that consumes changes stored in the CDC tables in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC Instance database.</span></span>  
  
 <span data-ttu-id="4845e-164">Этот пользователь определяет роль пользователя, необходимую для доступа к каждой из таблиц CDC при помощи функций CDC, создаваемых в пределах инфраструктуры [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC.</span><span class="sxs-lookup"><span data-stu-id="4845e-164">This user determines the user role that is required for accessing each of the CDC tables through the CDC functions generated by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC infrastructure.</span></span> <span data-ttu-id="4845e-165">Если роль пользователя не задана, а отслеживаемый экземпляр указан, доступ к изменениям ограничен только членами предопределенной роли базы данных **db_owner** в базе данных CDC.</span><span class="sxs-lookup"><span data-stu-id="4845e-165">If no user role is specified when a capture instance is specified, access to the changes is limited to the member of the **db_owner** fixed database role of the CDC database.</span></span>  
  
## <a name="oracle-user-roles"></a><span data-ttu-id="4845e-166">Роли пользователей Oracle</span><span class="sxs-lookup"><span data-stu-id="4845e-166">Oracle User Roles</span></span>  
 <span data-ttu-id="4845e-167">Ниже описываются роли пользователей Oracle, которые используются службой Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="4845e-167">The following describes the Oracle user roles used by the Oracle CDC Service.</span></span>  
  
### <a name="database-administrator-dba"></a><span data-ttu-id="4845e-168">Администратор базы данных (DBA)</span><span class="sxs-lookup"><span data-stu-id="4845e-168">Database Administrator (DBA)</span></span>  
 <span data-ttu-id="4845e-169">Администратор базы данных Oracle (DBA) — это пользователь базы данных Oracle.</span><span class="sxs-lookup"><span data-stu-id="4845e-169">The Oracle database administrator (DBA) is an Oracle database user.</span></span> <span data-ttu-id="4845e-170">Среди задач, выполняемых администратором базы данных Oracle, имеются следующие:</span><span class="sxs-lookup"><span data-stu-id="4845e-170">The tasks performed by the Oracle DBA include:</span></span>  
  
-   <span data-ttu-id="4845e-171">Настройка исходной базы данных Oracle для работы в режиме ARCHIVELOG.</span><span class="sxs-lookup"><span data-stu-id="4845e-171">Setting the source Oracle database to work in ARCHIVELOG mode.</span></span>  
  
-   <span data-ttu-id="4845e-172">Настройка пользователя интеллектуального анализа журнала с необходимыми разрешениями.</span><span class="sxs-lookup"><span data-stu-id="4845e-172">Setting up a log mining user with the required permissions.</span></span>  
  
-   <span data-ttu-id="4845e-173">Установка дополнительного ведения журнала для отслеживаемых таблиц.</span><span class="sxs-lookup"><span data-stu-id="4845e-173">Setting supplemental logging for captured tables.</span></span>  
  
-   <span data-ttu-id="4845e-174">Помощь в восстановлении архивированных файлов журнала транзакций, которые больше не доступны, для последующей обработки.</span><span class="sxs-lookup"><span data-stu-id="4845e-174">Helping to restore archived transaction log files no longer available so they can be processed.</span></span>  
  
 <span data-ttu-id="4845e-175">Администратор базы данных Oracle может извлекать скрипты Oracle SQL, которые необходимо запустить для оценки перед их запуском.</span><span class="sxs-lookup"><span data-stu-id="4845e-175">The Oracle database administrator can get Oracle SQL scripts that need to run so they can be evaluated before running them.</span></span> <span data-ttu-id="4845e-176">Администратор базы данных Oracle может также непосредственно запускать скрипты Oracle SQL при помощи консоли конструктора Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="4845e-176">The Oracle database administrator can also directly run Oracle SQL scripts from the Oracle CDC Designer console.</span></span>  
  
 <span data-ttu-id="4845e-177">Если администратор базы данных Oracle решит использовать консоль конструктора Oracle CDC, учетные данные администратора не будут сохраняться, кроме как в контексте (диалоге), в котором они используются.</span><span class="sxs-lookup"><span data-stu-id="4845e-177">If the Oracle database administrator chooses to use the Oracle CDC Designer console, administrator's credentials are not kept except for the context (dialog) in which they were used.</span></span>  
  
 <span data-ttu-id="4845e-178">Администратор базы данных Oracle работает над конфигурацией экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC, координируя свои действия с администратором службы Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="4845e-178">The Oracle database administrator works in coordination with the Oracle CDC Service administrator on the configuration of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC Instances.</span></span>  
  
### <a name="log-mining-user"></a><span data-ttu-id="4845e-179">Пользователь интеллектуального анализа журнала</span><span class="sxs-lookup"><span data-stu-id="4845e-179">Log Mining User</span></span>  
 <span data-ttu-id="4845e-180">Пользователь средства интеллектуального анализа журнала Oracle — это особый пользователь базы данных Oracle, которому предоставлены привилегии, необходимые для доступа и обработки журналов транзакций Oracle.</span><span class="sxs-lookup"><span data-stu-id="4845e-180">The Oracle Log Miner user is a special Oracle database user that is granted the required privileges for accessing and processing the Oracle transaction logs.</span></span>  
  
 <span data-ttu-id="4845e-181">Учетные данные для этого пользователя сохраняются в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC с использованием асимметричного ключа шифрования.</span><span class="sxs-lookup"><span data-stu-id="4845e-181">The credentials for this user are stored in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC Instance database using asymmetric key encryption.</span></span> <span data-ttu-id="4845e-182">Они доступны только для службы Oracle CDC, но недоступны для владельца экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="4845e-182">They are accessible only to the Oracle CDC Service but not to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Oracle CDC Instance database owner.</span></span>  
  
 <span data-ttu-id="4845e-183">В следующем списке описаны необходимые привилегии пользователя функции интеллектуального анализа журнала:</span><span class="sxs-lookup"><span data-stu-id="4845e-183">The following list describes the required privileges of the log mining user should be granted:</span></span>  
  
-   <span data-ttu-id="4845e-184">SELECT на \<any-captured-table></span><span class="sxs-lookup"><span data-stu-id="4845e-184">SELECT on \<any-captured-table></span></span>  
  
-   <span data-ttu-id="4845e-185">SELECT ANY TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="4845e-185">SELECT ANY TRANSACTION</span></span>  
  
-   <span data-ttu-id="4845e-186">EXECUTE на DBMS_LOGMNR</span><span class="sxs-lookup"><span data-stu-id="4845e-186">EXECUTE on DBMS_LOGMNR</span></span>  
  
-   <span data-ttu-id="4845e-187">SELECT на V$LOGMNR_CONTENTS</span><span class="sxs-lookup"><span data-stu-id="4845e-187">SELECT on V$LOGMNR_CONTENTS</span></span>  
  
-   <span data-ttu-id="4845e-188">SELECT на V$ARCHIVED_LOG</span><span class="sxs-lookup"><span data-stu-id="4845e-188">SELECT on V$ARCHIVED_LOG</span></span>  
  
-   <span data-ttu-id="4845e-189">SELECT на V$LOG</span><span class="sxs-lookup"><span data-stu-id="4845e-189">SELECT on V$LOG</span></span>  
  
-   <span data-ttu-id="4845e-190">SELECT на V$LOGFILE</span><span class="sxs-lookup"><span data-stu-id="4845e-190">SELECT on V$LOGFILE</span></span>  
  
-   <span data-ttu-id="4845e-191">SELECT на V$DATABASE</span><span class="sxs-lookup"><span data-stu-id="4845e-191">SELECT on V$DATABASE</span></span>  
  
-   <span data-ttu-id="4845e-192">SELECT на V$THREAD</span><span class="sxs-lookup"><span data-stu-id="4845e-192">SELECT on V$THREAD</span></span>  
  
-   <span data-ttu-id="4845e-193">SELECT на V$PARAMETER</span><span class="sxs-lookup"><span data-stu-id="4845e-193">SELECT on V$PARAMETER</span></span>  
  
-   <span data-ttu-id="4845e-194">SELECT на DBA_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="4845e-194">SELECT on DBA_REGISTRY</span></span>  
  
-   <span data-ttu-id="4845e-195">SELECT на ALL_INDEXES</span><span class="sxs-lookup"><span data-stu-id="4845e-195">SELECT on ALL_INDEXES</span></span>  
  
-   <span data-ttu-id="4845e-196">SELECT на ALL_OBJECTS</span><span class="sxs-lookup"><span data-stu-id="4845e-196">SELECT on ALL_OBJECTS</span></span>  
  
-   <span data-ttu-id="4845e-197">SELECT на DBA_OBJECTS</span><span class="sxs-lookup"><span data-stu-id="4845e-197">SELECT on DBA_OBJECTS</span></span>  
  
-   <span data-ttu-id="4845e-198">SELECT на ALL_TABLES</span><span class="sxs-lookup"><span data-stu-id="4845e-198">SELECT on ALL_TABLES</span></span>  
  
 <span data-ttu-id="4845e-199">Если какие-либо из прав доступа нельзя предоставить для V$xxx, то их необходимо предоставить для V $xxx.</span><span class="sxs-lookup"><span data-stu-id="4845e-199">If any of these privileges cannot be granted to a V$xxx, then they should be granted to the V $xxx.</span></span>  
  
### <a name="schema-user"></a><span data-ttu-id="4845e-200">Пользователь схемы</span><span class="sxs-lookup"><span data-stu-id="4845e-200">Schema User</span></span>  
 <span data-ttu-id="4845e-201">Пользователь схемы Oracle — это пользователь Oracle, обладающий правами доступа для чтения к схемам таблиц Oracle, которые должны отслеживаться.</span><span class="sxs-lookup"><span data-stu-id="4845e-201">The Oracle Schema User is an Oracle user with read access to the schema of the Oracle tables to be captured.</span></span> <span data-ttu-id="4845e-202">Создание этого пользователя необходимо при работе с консолью конструктора Oracle CDC для извлечения списка схем Oracle, таблиц для отслеживания и их столбцов, индексов и ключей.</span><span class="sxs-lookup"><span data-stu-id="4845e-202">This user is necessary when working with the Oracle CDC Designer console to retrieve the list of Oracle schema, tables to be captured and their columns, indexes and keys.</span></span>  
  
 <span data-ttu-id="4845e-203">Учетные данные этого пользователя никогда не сохраняются.</span><span class="sxs-lookup"><span data-stu-id="4845e-203">The credentials for this user are never stored.</span></span> <span data-ttu-id="4845e-204">Их при необходимости запрашивает консоль конструктора CDC, и они хранятся до завершения сеансов пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="4845e-204">They are requested by the CDC Designer console each time they are needed and they are kept for the rest of the UI sessions.</span></span>  
  
  
