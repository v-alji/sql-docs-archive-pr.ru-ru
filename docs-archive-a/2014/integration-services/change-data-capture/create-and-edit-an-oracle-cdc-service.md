---
title: Создание и изменение Oracle CDC Service​ | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- createSrv
ms.assetid: 10cd612e-d8f1-4af2-97d3-a0c22e1e2326
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3325e272285895e813f01d50a1c312e75472919b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657852"
---
# <a name="create-and-edit-an-oracle-cdc-service"></a><span data-ttu-id="1bd21-102">Создание и изменение службы CDC Oracle</span><span class="sxs-lookup"><span data-stu-id="1bd21-102">Create and Edit an Oracle CDC Service</span></span>
  <span data-ttu-id="1bd21-103">Новые службы Windows для Oracle CDC создаются и изменяются из консоли конфигурации службы CDC.</span><span class="sxs-lookup"><span data-stu-id="1bd21-103">You create and edit a new Oracle CDC Windows Service from the CDC Service Configuration Console.</span></span>  
  
 <span data-ttu-id="1bd21-104">Чтобы создать новую службу Windows для Oracle CDC, на панели слева выберите **Локальные службы CDC** , а затем щелкните **Создать службу** на панели **Действия** .</span><span class="sxs-lookup"><span data-stu-id="1bd21-104">To create a new Oracle CDC Windows service, select **Local CDC Services** from the left pane, then click **New Service** from the **Actions** pane.</span></span> <span data-ttu-id="1bd21-105">Можно также щелкнуть правой кнопкой **Локальные службы CDC** и выбрать **Создать службу**.</span><span class="sxs-lookup"><span data-stu-id="1bd21-105">You can also right-click **Local CDC Services** and select **New Service**.</span></span> <span data-ttu-id="1bd21-106">Откроется диалоговое окно создания службы Windows для Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="1bd21-106">The New Oracle CDC Windows Service dialog box opens.</span></span>  
  
 <span data-ttu-id="1bd21-107">**OR**</span><span class="sxs-lookup"><span data-stu-id="1bd21-107">**OR**</span></span>  
  
 <span data-ttu-id="1bd21-108">Для изменения свойств службы CDC выберите нужную службу и щелкните **Свойства** на панели **Действия** .</span><span class="sxs-lookup"><span data-stu-id="1bd21-108">To edit the CDC service properties, select the service that you want to edit the properties for and click **Properties** from the **Actions** pane.</span></span> <span data-ttu-id="1bd21-109">Можно также щелкнуть правой кнопкой мыши нужную службу и выбрать пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="1bd21-109">You can also right-click the service you are working with and select **Properties**.</span></span> <span data-ttu-id="1bd21-110">Откроется диалоговое окно «Свойства службы CDC».</span><span class="sxs-lookup"><span data-stu-id="1bd21-110">The CDC Service Properties dialog box opens.</span></span>  
  
 <span data-ttu-id="1bd21-111">Введите следующие сведения в диалоговом окне «Новая служба Windows для Oracle CDC» или «Свойства службы CDC».</span><span class="sxs-lookup"><span data-stu-id="1bd21-111">Enter the following information in the New Oracle CDC Windows Service dialog box or the CDC Service Properties dialog box.</span></span>  
  
 <span data-ttu-id="1bd21-112">Имя службы</span><span class="sxs-lookup"><span data-stu-id="1bd21-112">Service Name</span></span>  
 <span data-ttu-id="1bd21-113">Введите имя новой службы Windows для Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="1bd21-113">Type the name of the new Oracle CDC Windows Service.</span></span> <span data-ttu-id="1bd21-114">По возможности не следует использовать длинные имена.</span><span class="sxs-lookup"><span data-stu-id="1bd21-114">You should not use long names, if possible.</span></span> <span data-ttu-id="1bd21-115">В имени службы также нельзя использовать символы «/» и «\».</span><span class="sxs-lookup"><span data-stu-id="1bd21-115">The characters / and \ cannot be used in the service name.</span></span>  
  
> [!NOTE]  
> <span data-ttu-id="1bd21-116">Этот параметр недоступен при изменении свойств службы.</span><span class="sxs-lookup"><span data-stu-id="1bd21-116">This option is not available when editing the service.</span></span> <span data-ttu-id="1bd21-117">Невозможно изменить имя службы Windows, которая уже существует.</span><span class="sxs-lookup"><span data-stu-id="1bd21-117">You cannot change the name of a Windows service that already exists.</span></span>  
  
 <span data-ttu-id="1bd21-118">**Описание**</span><span class="sxs-lookup"><span data-stu-id="1bd21-118">**Description**</span></span>  
 <span data-ttu-id="1bd21-119">Введите описание службы, чтобы упростить ее идентификацию.</span><span class="sxs-lookup"><span data-stu-id="1bd21-119">Type a description of the service to help identify it.</span></span>  
  
 <span data-ttu-id="1bd21-120">**Учетная запись службы**</span><span class="sxs-lookup"><span data-stu-id="1bd21-120">**Service Account**</span></span>  
 <span data-ttu-id="1bd21-121">Выберите один из следующих вариантов, чтобы определить, какую учетную запись будет использовать служба.</span><span class="sxs-lookup"><span data-stu-id="1bd21-121">Select one of the following to determine under which account to run the service:</span></span>  
  
-   <span data-ttu-id="1bd21-122">**Учетная запись Local System**</span><span class="sxs-lookup"><span data-stu-id="1bd21-122">**Local System Account**</span></span>  
  
     <span data-ttu-id="1bd21-123">Этот вариант не рекомендуется, потому что он дает службе слишком много разрешений.</span><span class="sxs-lookup"><span data-stu-id="1bd21-123">This is not recommended because it gives too many permissions to the service.</span></span>  
  
-   <span data-ttu-id="1bd21-124">**Эта учетная запись**</span><span class="sxs-lookup"><span data-stu-id="1bd21-124">**This Account**</span></span>  
  
     <span data-ttu-id="1bd21-125">В Windows Vista и Windows Server 2008 в качестве учетной записи службы по умолчанию используется NETWORK SERVICE.</span><span class="sxs-lookup"><span data-stu-id="1bd21-125">On Windows Vista or Windows Server 2008, the default service account is the NETWORK SERVICE account.</span></span>  
  
     <span data-ttu-id="1bd21-126">В Windows 7, Windows Server 2008 R2 и более поздних версиях в качестве учетной записи службы по умолчанию используется NT Service\\<имя-службы>.</span><span class="sxs-lookup"><span data-stu-id="1bd21-126">On Windows 7, Windows Server 2008 R2 and later, the default service account is NT Service\\<service-name>.</span></span>  
  
     <span data-ttu-id="1bd21-127">Использование этих учетных записей позволяет работать без использования паролей, так как пароль не является необходимым для этих учетных записей.</span><span class="sxs-lookup"><span data-stu-id="1bd21-127">Using these accounts lets you work without using passwords because a password is not necessary for these accounts.</span></span> <span data-ttu-id="1bd21-128">Кроме того, эти учетные записи предоставляют только разрешения, необходимые для запуска службы Oracle CDC Service.</span><span class="sxs-lookup"><span data-stu-id="1bd21-128">In addition these accounts provide only the necessary permissions required for the Oracle CDC Service to run.</span></span>  
  
     <span data-ttu-id="1bd21-129">В качестве учетной записи службы можно использовать учетную запись локального пользователя Windows либо пользователя домена.</span><span class="sxs-lookup"><span data-stu-id="1bd21-129">You can use a local or domain Windows account for the service account.</span></span> <span data-ttu-id="1bd21-130">В таком случае необходимо ввести **пароль** этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="1bd21-130">In this case, you must enter the **Password** for that account.</span></span> <span data-ttu-id="1bd21-131">Эта учетная запись может быть для локального компьютера или домена.</span><span class="sxs-lookup"><span data-stu-id="1bd21-131">This account can be for the local host or a domain account.</span></span> <span data-ttu-id="1bd21-132">Не забудьте обновить пароль, когда он изменяется с помощью управления локальными службами на панели управления Windows.</span><span class="sxs-lookup"><span data-stu-id="1bd21-132">Be sure to update the password when it is changed using Local Services in the Windows Control Panel.</span></span>  
  
 <span data-ttu-id="1bd21-133">**Имя сервера**: выберите целевой экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], с которым устанавливается соединение (например, **\\\\<имя_компьютера>\\<имя_экземпляра>** ).</span><span class="sxs-lookup"><span data-stu-id="1bd21-133">**Server name**: Select the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance to connect to (for example, **\\\\<computer_name>\\<instance_name>**).</span></span> <span data-ttu-id="1bd21-134">По умолчанию выводится экземпляр сервера, к которому подключение выполнялось в последний раз.</span><span class="sxs-lookup"><span data-stu-id="1bd21-134">The server instance last connected to is displayed by default.</span></span>  
  
 <span data-ttu-id="1bd21-135">**Аутентификация**</span><span class="sxs-lookup"><span data-stu-id="1bd21-135">**Authentication**</span></span>  
 <span data-ttu-id="1bd21-136">Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="1bd21-136">Select one of the following:</span></span>  
  
-   <span data-ttu-id="1bd21-137">**Проверка подлинности Windows**. В этом случае служба Oracle CDC будет подключаться к целевому экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], используя учетную запись службы.</span><span class="sxs-lookup"><span data-stu-id="1bd21-137">**Windows Authentication**: If you select this option, the Oracle CDC service connects to the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance using the service account identity.</span></span> <span data-ttu-id="1bd21-138">Если экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] работает на другом компьютере, проверку подлинности Windows необходимо использовать с учетными записями домена.</span><span class="sxs-lookup"><span data-stu-id="1bd21-138">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance is running on a different computer, Windows Authentication must be used with domain accounts.</span></span>  
  
-   <span data-ttu-id="1bd21-139">**Аутентификация SQL Server**: при выборе этого варианта необходимо будет ввести **Имя пользователя** и **Пароль** для имени входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], которое вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="1bd21-139">**SQL Server Authentication**: If you select this option, you must type the **User Name** and **Password** for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login you want to use.</span></span> <span data-ttu-id="1bd21-140">Служба Oracle CDC использует эти учетные данные при подключении к целевому экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1bd21-140">The Oracle CDC service uses these credentials when connecting to the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
 <span data-ttu-id="1bd21-141">Имени входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , используемому службой Oracle CDC Service, достаточно быть членом предопределенной роли сервера public. Других разрешений не требуется.</span><span class="sxs-lookup"><span data-stu-id="1bd21-141">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login used by the Oracle CDC Service only needs to be a member of the public fixed-server role, no other privileges are needed.</span></span> <span data-ttu-id="1bd21-142">Когда добавляются новые экземпляры Oracle CDC, это имя входа получает доступ **db_owner** к соответствующим базам данных CDC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1bd21-142">Once new Oracle CDC Instances are added, that login will gain **db_owner** access to the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC databases.</span></span>  
  
 <span data-ttu-id="1bd21-143">Чтобы создать определение службы Windows для Oracle CDC, программе требуется доступ с возможностью обновления к базе данных MSXDBCDC в соответствующем экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1bd21-143">To create the Oracle CDC Windows Service definition, the program needs update access to the MSXDBCDC database in the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="1bd21-144">При нажатии кнопки **OK**появляется диалоговое окно с приглашением ввести имя входа, имеющее доступ [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с возможностью обновления к базе данных MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="1bd21-144">When you click **OK**, a dialog box prompts the user to enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login with an update access to the MSXDBCDC database.</span></span>  
  
 <span data-ttu-id="1bd21-145">Дополнительные сведения о вводе данных в диалоговое окно «Подключение к SQL Server» см. в разделе [Connection to SQL Server](connection-to-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1bd21-145">For information about the data you must type into the Connect to SQL Server dialog box, see [Connection to SQL Server](connection-to-sql-server.md).</span></span>  
  
 <span data-ttu-id="1bd21-146">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="1bd21-146">**Options**</span></span>  
 <span data-ttu-id="1bd21-147">Чтобы просмотреть доступные для настройки параметры, щелкните стрелку.</span><span class="sxs-lookup"><span data-stu-id="1bd21-147">Click the arrow to view available options to be configured.</span></span> <span data-ttu-id="1bd21-148">Для них можно оставить значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1bd21-148">You can choose to leave these options with their default value.</span></span> <span data-ttu-id="1bd21-149">Доступные параметры:</span><span class="sxs-lookup"><span data-stu-id="1bd21-149">The available options are:</span></span>  
  
-   <span data-ttu-id="1bd21-150">**Время ожидания соединения**: Введите время (в секундах), в течение которого служба CDC для Oracle ожидает установления соединения с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Значение по умолчанию ― **15**.</span><span class="sxs-lookup"><span data-stu-id="1bd21-150">**Connection Timeout**: Type the time (in seconds) that the CDC Service for Oracle waits for a connection to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before timing out. The default value is **15**.</span></span>  
  
-   <span data-ttu-id="1bd21-151">**Время ожидания выполнения**: Введите время (в секундах), в течение которого служба Windows CDC Oracle ожидает выполнения команды. Значение по умолчанию — **30**.</span><span class="sxs-lookup"><span data-stu-id="1bd21-151">**Execution Timeout**: Type the time (in seconds) that the Oracle CDC Windows Service waits for a command to execute before timing out. The default value is **30**.</span></span>  
  
-   <span data-ttu-id="1bd21-152">**Шифровать соединение**: выберите параметр **Шифровать соединение**, чтобы обмен данными между службой Oracle CDC Service и целевым экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выполнялся по зашифрованному соединению.</span><span class="sxs-lookup"><span data-stu-id="1bd21-152">**Encrypt Connection**: Select **Encrypt Connection** for communication between the Oracle CDC Service and the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance using an encrypted connection.</span></span>  
  
-   <span data-ttu-id="1bd21-153">**Дополнительно**: При необходимости введите любые дополнительные свойства подключения.</span><span class="sxs-lookup"><span data-stu-id="1bd21-153">**Advanced**: Type any additional connection properties, if necessary.</span></span>  
  
 <span data-ttu-id="1bd21-154">**Главный пароль**</span><span class="sxs-lookup"><span data-stu-id="1bd21-154">**Master Password**</span></span>  
 <span data-ttu-id="1bd21-155">Введите пароль, который будет использоваться службой Windows Oracle CDC для защиты учетных данных средства интеллектуального анализа журнала.</span><span class="sxs-lookup"><span data-stu-id="1bd21-155">Enter a password to be used by the Oracle CDC Windows Service to protect the Oracle log-mining credentials.</span></span>  
  
 <span data-ttu-id="1bd21-156">Тот же главный пароль будет использоваться при настройке других экземпляров той же службы на других узлах кластера конфигурации с высокой доступностью.</span><span class="sxs-lookup"><span data-stu-id="1bd21-156">The same master password must also be used when other instances of the same service are configured on other nodes on a cluster in high-availability configuration.</span></span> <span data-ttu-id="1bd21-157">При потере или изменении главного пароля все пароли для интеллектуального анализа журнала, хранящиеся в базах данных экземпляра Oracle CDC, следует ввести заново с помощью консоли конструктора CDC.</span><span class="sxs-lookup"><span data-stu-id="1bd21-157">If you lose or modify the master password, all log mining passwords stored in Oracle CDC Instance databases must be re-entered using the CDC Designer console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bd21-158">См. также:</span><span class="sxs-lookup"><span data-stu-id="1bd21-158">See Also</span></span>  
 [<span data-ttu-id="1bd21-159">Создание и изменение службы CDC</span><span class="sxs-lookup"><span data-stu-id="1bd21-159">How to Create and Edit a CDC Service</span></span>](how-to-create-and-edit-a-cdc-service.md)  
  
  
