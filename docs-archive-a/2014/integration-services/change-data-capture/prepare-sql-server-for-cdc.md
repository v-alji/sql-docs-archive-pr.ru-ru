---
title: Подготовка SQL Server для CDC | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- prepSqlSrv
ms.assetid: 20b51dbf-a545-4234-87ae-4228268a0fb2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dafa29d9bdb0c27decb605398a6d1cfe383427e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656528"
---
# <a name="prepare-sql-server-for-cdc"></a><span data-ttu-id="a7a52-102">Подготовка SQL Server для CDC</span><span class="sxs-lookup"><span data-stu-id="a7a52-102">Prepare SQL Server for CDC</span></span>
  <span data-ttu-id="a7a52-103">Для службы Oracle CDC требуется, чтобы все целевые экземпляры [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] содержали базу данных MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="a7a52-103">The Oracle CDC service requires all target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances to contain the MSXDBCDC database.</span></span> <span data-ttu-id="a7a52-104">Эта база данных создается с помощью операции «Подготовка SQL Server» в консоли конфигурации службы CDC.</span><span class="sxs-lookup"><span data-stu-id="a7a52-104">You create this database using the Prepare SQL Server action in the CDC Service Configuration Console.</span></span> <span data-ttu-id="a7a52-105">Операция формирует специальный скрипт, который выполняется для создания необходимых таблиц, хранимых процедур и других требуемых объектов базы данных.</span><span class="sxs-lookup"><span data-stu-id="a7a52-105">This creates a special script that is run to create the required tables, stored procedures, and other required artifacts for this database.</span></span> <span data-ttu-id="a7a52-106">Эта задача выполняется только один раз для каждого целевого экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a7a52-106">This task is done one time only for each target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
 <span data-ttu-id="a7a52-107">Дополнительные сведения о базе данных MSXDBCDC см. в разделе «База данных MSXDBCDC».</span><span class="sxs-lookup"><span data-stu-id="a7a52-107">For more information about the MSXDBCDC database, see The MSXDBCDC Database.</span></span>  
  
 <span data-ttu-id="a7a52-108">В консоли конфигурации службы CDC щелкните **Подготовка SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="a7a52-108">In the CDC Service Configuration Console, click **Prepare SQL Server**.</span></span> <span data-ttu-id="a7a52-109">Если эта команда недоступна, проверьте, выбран ли элемент **Локальные службы CDC** на левой панели консоли.</span><span class="sxs-lookup"><span data-stu-id="a7a52-109">If this option is not available, make sure that **Local CDC Services** is selected in the left pane of the console.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a7a52-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="a7a52-110">Options</span></span>  
  
### <a name="server-name"></a><span data-ttu-id="a7a52-111">Имя сервера</span><span class="sxs-lookup"><span data-stu-id="a7a52-111">Server Name</span></span>  
 <span data-ttu-id="a7a52-112">Введите имя сервера, на котором находится экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a7a52-112">Type the name of the server where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is located.</span></span>  
  
### <a name="authentication"></a><span data-ttu-id="a7a52-113">Аутентификация</span><span class="sxs-lookup"><span data-stu-id="a7a52-113">Authentication</span></span>  
 <span data-ttu-id="a7a52-114">Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="a7a52-114">Select one of the following:</span></span>  
  
-   <span data-ttu-id="a7a52-115">**Проверка подлинности Windows.**</span><span class="sxs-lookup"><span data-stu-id="a7a52-115">**Windows Authentication**</span></span>  
  
-   <span data-ttu-id="a7a52-116">**Аутентификация SQL Server**: если вы выберете этот вариант, необходимо будет ввести **Имя пользователя** и **Пароль** в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], к которому вы подключаетесь.</span><span class="sxs-lookup"><span data-stu-id="a7a52-116">**SQL Server Authentication**: If you select this option, you must type the **User Name** and **Password** for the user in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you are connecting to.</span></span>  
  
 <span data-ttu-id="a7a52-117">Для подготовки экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для Oracle CDC имя входа должно иметь разрешение на запись в базе данных MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="a7a52-117">To prepare the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance for Oracle CDC, the login must have write permission to the MSXDBCDC database.</span></span> <span data-ttu-id="a7a52-118">Введите учетные данные для имени входа, имеющего разрешение на запись в базу данных MSXDBCDC. Это может быть член роли `sysasmin` .</span><span class="sxs-lookup"><span data-stu-id="a7a52-118">Enter the credentials for a login that has write permission to the MSXDBCDC database, such as a member of the `sysasmin` role.</span></span>  
  
### <a name="options"></a><span data-ttu-id="a7a52-119">Параметры</span><span class="sxs-lookup"><span data-stu-id="a7a52-119">Options</span></span>  
 <span data-ttu-id="a7a52-120">Чтобы просмотреть доступные для настройки параметры, щелкните стрелку.</span><span class="sxs-lookup"><span data-stu-id="a7a52-120">Click the arrow to view available options to be configured.</span></span> <span data-ttu-id="a7a52-121">Для них можно оставить значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a7a52-121">You can choose to leave these options with their default value.</span></span> <span data-ttu-id="a7a52-122">Доступные параметры:</span><span class="sxs-lookup"><span data-stu-id="a7a52-122">The available options are:</span></span>  
  
-   <span data-ttu-id="a7a52-123">**Время ожидания соединения**: Введите время (в секундах), в течение которого служба CDC для Oracle ожидает установления соединения с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Значение по умолчанию ― **15**.</span><span class="sxs-lookup"><span data-stu-id="a7a52-123">**Connection Timeout**: Type the time (in seconds) that the CDC Service for Oracle waits for a connection to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before timing out. The default value is **15**.</span></span>  
  
-   <span data-ttu-id="a7a52-124">**Время ожидания выполнения**: Введите время (в секундах), в течение которого служба Windows CDC Oracle ожидает выполнения команды. Значение по умолчанию — **30**.</span><span class="sxs-lookup"><span data-stu-id="a7a52-124">**Execution Timeout**: Type the time (in seconds) that the Oracle CDC Windows Service waits for a command to execute before timing out. The default value is **30**.</span></span>  
  
-   <span data-ttu-id="a7a52-125">**Шифровать соединение**: выберите параметр **Шифровать соединение**, чтобы обмен данными между службой Oracle CDC Service и целевым экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выполнялся по зашифрованному соединению.</span><span class="sxs-lookup"><span data-stu-id="a7a52-125">**Encrypt Connection**: Select **Encrypt Connection** for communication between the Oracle CDC Service and the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance using an encrypted connection.</span></span>  
  
-   <span data-ttu-id="a7a52-126">**Дополнительно**: При необходимости введите любые дополнительные свойства подключения.</span><span class="sxs-lookup"><span data-stu-id="a7a52-126">**Advanced**: Type any additional connection properties, if necessary.</span></span>  
  
### <a name="view-script"></a><span data-ttu-id="a7a52-127">Просмотреть скрипт</span><span class="sxs-lookup"><span data-stu-id="a7a52-127">View Script</span></span>  
 <span data-ttu-id="a7a52-128">Щелкните **Просмотреть скрипт** для просмотра скрипта установки (он будет доступен только для чтения).</span><span class="sxs-lookup"><span data-stu-id="a7a52-128">Click **View Script** to view a read-only version of the setup script.</span></span> <span data-ttu-id="a7a52-129">Системный администратор [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] при необходимости может скопировать этот скрипт в консоль управления SQL Server и отредактировать его.</span><span class="sxs-lookup"><span data-stu-id="a7a52-129">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator can copy this script into the SQL Server Management Console to edit it, if necessary.</span></span> <span data-ttu-id="a7a52-130">Дополнительные сведения о подготовке скрипта SQL Server см. в разделе [Подготовка SQL Server для скрипта представления CDC Oracle](prepare-sql-server-for-oracle-cdc-view-script.md).</span><span class="sxs-lookup"><span data-stu-id="a7a52-130">For more information about the Prepare SQL Server Script, see [Prepare SQL Server for Oracle CDC-View Script](prepare-sql-server-for-oracle-cdc-view-script.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7a52-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="a7a52-131">See Also</span></span>  
 <span data-ttu-id="a7a52-132">[Как работать со службами CDC](work-with-cdc-services.md) </span><span class="sxs-lookup"><span data-stu-id="a7a52-132">[How to Work with CDC Services](work-with-cdc-services.md) </span></span>  
 [<span data-ttu-id="a7a52-133">Как подготовить SQL Server для CDC</span><span class="sxs-lookup"><span data-stu-id="a7a52-133">How to Prepare SQL Server for CDC</span></span>](prepare-sql-server-for-cdc.md)  
  
  
