---
title: Служба системы отслеживания измененных данных для Oracle компании Attunity | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 22ec8a5c-9550-4d38-8a4a-485ec3e53ea8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 68e68e9edd91bd1d0c718b32e29c3b29f74778c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665080"
---
# <a name="change-data-capture-service-for-oracle-by-attunity"></a><span data-ttu-id="214b3-102">Служба системы отслеживания измененных данных для Oracle компании Attunity</span><span class="sxs-lookup"><span data-stu-id="214b3-102">Change Data Capture Service for Oracle by Attunity</span></span>
  <span data-ttu-id="214b3-103">Служба CDC Service для Oracle ― это служба Windows, которая просматривает журналы транзакций Oracle и регистрирует изменения выбранных таблиц Oracle в таблицах изменений [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="214b3-103">The CDC Service for Oracle is a Windows service that scans Oracle transaction logs and captures changes to Oracle tables of interest into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] change tables.</span></span> <span data-ttu-id="214b3-104">Таблицы изменений SQL, где хранятся отслеженные изменения из базы данных Oracle, принадлежат к тому же типу, что и таблицы изменений, используемые в собственной системе отслеживания изменений [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="214b3-104">The SQL change tables where the changes captured from Oracle are stored are the same type of change tables used in the native [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Change Data Capture feature.</span></span> <span data-ttu-id="214b3-105">Поэтому использовать эти изменения так же легко, как и изменения баз данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="214b3-105">This makes consuming these changes as easy as consuming changes made to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases.</span></span>  
  
## <a name="installation"></a><span data-ttu-id="214b3-106">Установка</span><span class="sxs-lookup"><span data-stu-id="214b3-106">Installation</span></span>  
 <span data-ttu-id="214b3-107">Службу CDC Service для Oracle можно установить на любой поддерживаемый компьютер с ОС Windows с доступом к исходным базам данных Oracle, изменения в которых отслеживаются, и к целевому экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , где находится целевая база данных CDC.</span><span class="sxs-lookup"><span data-stu-id="214b3-107">The CDC Service for Oracle can be installed on any supported Windows computer with access to the source Oracle database(s) being captured and the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance where the target CDC database resides.</span></span> <span data-ttu-id="214b3-108">Службе CDC Service не нужны локально установленные базы данных Oracle или [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , а только их поддерживаемые клиенты.</span><span class="sxs-lookup"><span data-stu-id="214b3-108">The CDC Service does not need a local installation of the Oracle database or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, only their supported clients.</span></span> <span data-ttu-id="214b3-109">Сведения о месте установки необходимых компонентов базы данных см. в подразделе **Предварительные требования базы данных** в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="214b3-109">For information about where to install the required database components, see **Database Prerequisites** in this topic.</span></span>  
  
 <span data-ttu-id="214b3-110">Установка службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC Service для Oracle помещает в выбранном месте графический интерфейс пользователя для настройки службы и служебную программу.</span><span class="sxs-lookup"><span data-stu-id="214b3-110">The installation of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC Service for Oracle places the service configuration UI and the service program in the selected location.</span></span> <span data-ttu-id="214b3-111">Служба CDC Service для Oracle настраивается отдельно с помощью консоли конфигурации службы Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="214b3-111">The CDC Service for Oracle is configured separately using the Oracle CDC Service Configuration Console.</span></span> <span data-ttu-id="214b3-112">Дополнительные сведения о настройке службы Oracle CDC Service см. в разделе [Справка F1 по службе системы отслеживания информации об изменениях данных для Oracle компании Attunity](change-data-capture-service-for-oracle-by-attunity-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="214b3-112">For more information on configuring the Oracle CDC Service, see [Change Data Capture Service for Oracle by Attunity F1 Help](change-data-capture-service-for-oracle-by-attunity-f1-help.md).</span></span>  
  
 <span data-ttu-id="214b3-113">Чтобы установить службу CDC для Oracle, вручную запустите **AttunityOracleCdcService.msi** с установочного носителя SQL Server.</span><span class="sxs-lookup"><span data-stu-id="214b3-113">To install the CDC Service for Oracle, manually run **AttunityOracleCdcService.msi** from the SQL Server installation media.</span></span> <span data-ttu-id="214b3-114">Пакеты установки для x86 и x64 находятся в \*\*.\тулс\аттунитикдкоракле \\ \*\* на установочном носителе SQL Server.</span><span class="sxs-lookup"><span data-stu-id="214b3-114">Installation packages for x86 and x64 are located in **.\Tools\AttunityCDCOracle\\** on the SQL Server installation media.</span></span>  
  
 <span data-ttu-id="214b3-115">Службу CDC Service для Oracle можно установить на любой поддерживаемый компьютер с ОС Windows, на котором установлен собственный клиент Native Client [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] ; он не обязательно должен быть установлен на том же компьютере, что и целевая база данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="214b3-115">The CDC Service for Oracle can be installed on any supported Windows computer where the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Native Client is installed; it does not need to be installed on the same computer where the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed.</span></span>  
  
## <a name="supported-windows-environments"></a><span data-ttu-id="214b3-116">Поддерживаемые среды Windows</span><span class="sxs-lookup"><span data-stu-id="214b3-116">Supported Windows Environments</span></span>  
 <span data-ttu-id="214b3-117">Служба системы отслеживания измененных данных для Oracle от Attunity может работать в следующих средах Windows:</span><span class="sxs-lookup"><span data-stu-id="214b3-117">The Change Data Capture Service for Oracle by Attunity can run in the following Windows environments:</span></span>  
  
-   <span data-ttu-id="214b3-118">Windows 8</span><span class="sxs-lookup"><span data-stu-id="214b3-118">Windows 8</span></span>  
  
-   <span data-ttu-id="214b3-119">Windows 7, 32-разрядная (x86) и 64-разрядная (x64) версии</span><span class="sxs-lookup"><span data-stu-id="214b3-119">Windows 7 32-bit (x86) and 64-bit (x64)</span></span>  
  
-   <span data-ttu-id="214b3-120">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="214b3-120">Windows Server 2012</span></span>  
  
-   <span data-ttu-id="214b3-121">Windows Server 2008 R2 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="214b3-121">Windows Server 2008 R2 with Service Pack 1</span></span>  
  
-   <span data-ttu-id="214b3-122">Windows Server 2008, 32-разрядная (x86) и 64-разрядная (x64) версии с пакетом обновления 2 (SP2)</span><span class="sxs-lookup"><span data-stu-id="214b3-122">Windows Server 2008 32-bit (x86) and 64-bit (x64) with Service Pack 2</span></span>  
  
## <a name="database-prerequisites"></a><span data-ttu-id="214b3-123">Предварительные требования базы данных</span><span class="sxs-lookup"><span data-stu-id="214b3-123">Database Prerequisites</span></span>  
 <span data-ttu-id="214b3-124">Для работы со службой CDC Service для Oracle следует установить программное обеспечения собственного клиента Native Client Oracle [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="214b3-124">To work with the CDC Service for Oracle you must install the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Native Client Oracle software.</span></span> <span data-ttu-id="214b3-125">Это обязательный компонент, который нужно получить у Oracle и установить до установки службы Oracle CDC Service.</span><span class="sxs-lookup"><span data-stu-id="214b3-125">This is a prerequisite that should be obtained from Oracle and installed before installing the Oracle CDC Service.</span></span> <span data-ttu-id="214b3-126">Кроме того, необходимо установить клиент ODBC для SQL Server, используя процесс установки SQL Server.</span><span class="sxs-lookup"><span data-stu-id="214b3-126">Additionally, you need to install the SQL Server ODBC Client using SQL Server Setup.</span></span>  
  
 <span data-ttu-id="214b3-127">Служба CDC для Oracle поддерживает следующие версии:</span><span class="sxs-lookup"><span data-stu-id="214b3-127">The CDC Service for Oracle supports the following versions:</span></span>  
  
### <a name="source-oracle-database"></a><span data-ttu-id="214b3-128">Исходная база данных Oracle</span><span class="sxs-lookup"><span data-stu-id="214b3-128">Source Oracle Database</span></span>  
  
-   <span data-ttu-id="214b3-129">База данных Oracle 11x, любая версия</span><span class="sxs-lookup"><span data-stu-id="214b3-129">Oracle Database 11x, any version</span></span>  
  
-   <span data-ttu-id="214b3-130">База данных Oracle 10x, любая версия</span><span class="sxs-lookup"><span data-stu-id="214b3-130">Oracle Database 10x, any version</span></span>  
  
### <a name="target-sql-server-database"></a><span data-ttu-id="214b3-131">Целевая база данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="214b3-131">Target SQL Server Database</span></span>  
 <span data-ttu-id="214b3-132">Перечень функций, поддерживаемых в разных выпусках [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], см. в разделе [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="214b3-132">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="running-the-installation-program"></a><span data-ttu-id="214b3-133">Запуск программы установки</span><span class="sxs-lookup"><span data-stu-id="214b3-133">Running the Installation Program</span></span>  
 <span data-ttu-id="214b3-134">Чтобы установить службу CDC Service для Oracle, откройте мастер установки для используемой платформы Windows (32-/64-разрядной) и следуйте инструкциям на экране.</span><span class="sxs-lookup"><span data-stu-id="214b3-134">To install the CDC Service for Oracle, open the installation wizard for the Windows platform you are using (32/64-bit) and follow the directions on the screen.</span></span>  
  
## <a name="uninstalling-change-data-capture-service-for-oracle-by-attunity"></a><span data-ttu-id="214b3-135">Удаление службы системы отслеживания измененных данных для Oracle от Attunity</span><span class="sxs-lookup"><span data-stu-id="214b3-135">Uninstalling Change Data Capture Service for Oracle by Attunity</span></span>  
 <span data-ttu-id="214b3-136">Служба CDC Service для Oracle удаляется с помощью пункта панели управления «Программы и компоненты».</span><span class="sxs-lookup"><span data-stu-id="214b3-136">You uninstall the CDC Service for Oracle using Control Panel, Programs and Features.</span></span>  
  
 <span data-ttu-id="214b3-137">При удалении службы CDC Service созданные базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не удаляются.</span><span class="sxs-lookup"><span data-stu-id="214b3-137">Uninstalling the CDC Service does not delete the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases created.</span></span> <span data-ttu-id="214b3-138">Для полного удаления этого средства нужно удалить базу данных MSXDBCDC и конкретные базы данных CDC, созданные в целевом экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , с которым производилась работа.</span><span class="sxs-lookup"><span data-stu-id="214b3-138">For complete removal of the tool, you must remove the MSXDBCDC database and the specific CDC databases that were created in the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you worked with.</span></span>  
  
 <span data-ttu-id="214b3-139">Если программное обеспечение службы CDC Service удаляется с одного компьютера и устанавливается на другой, нужно задать только следующие данные:</span><span class="sxs-lookup"><span data-stu-id="214b3-139">If you uninstall the CDC Service software from one machine and install it on another computer, you only need to provide the following definitions:</span></span>  
  
-   <span data-ttu-id="214b3-140">Учетная запись службы</span><span class="sxs-lookup"><span data-stu-id="214b3-140">Service account</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="214b3-141">и учетные данные</span><span class="sxs-lookup"><span data-stu-id="214b3-141">connect string and credentials</span></span>  
  
-   <span data-ttu-id="214b3-142">Главный пароль</span><span class="sxs-lookup"><span data-stu-id="214b3-142">The master password</span></span>  
  
 <span data-ttu-id="214b3-143">Все прочие определения хранятся в базе данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и доступны из предыдущей установки на другом компьютере.</span><span class="sxs-lookup"><span data-stu-id="214b3-143">All the other definitions are stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and are available from the previous installation on another computer.</span></span>  
  
## <a name="in-this-documentation"></a><span data-ttu-id="214b3-144">В этой документации</span><span class="sxs-lookup"><span data-stu-id="214b3-144">In This Documentation</span></span>  
  
-   [<span data-ttu-id="214b3-145">Архитектура службы системы отслеживания измененных данных для Oracle компании Attunity</span><span class="sxs-lookup"><span data-stu-id="214b3-145">Change Data Capture Service for Oracle by Attunity System Architecture</span></span>](change-data-capture-service-for-oracle-by-attunity-system-architecture.md)  
  
-   [<span data-ttu-id="214b3-146">Служба CDC Oracle</span><span class="sxs-lookup"><span data-stu-id="214b3-146">The Oracle CDC Service</span></span>](the-oracle-cdc-service.md)  
  
-   [<span data-ttu-id="214b3-147">Справка F1 службы системы отслеживания измененных данных для Oracle компании Attunity</span><span class="sxs-lookup"><span data-stu-id="214b3-147">Change Data Capture Service for Oracle by Attunity F1 Help</span></span>](change-data-capture-service-for-oracle-by-attunity-f1-help.md)  
  
-   [<span data-ttu-id="214b3-148">Руководство по службе системы отслеживания измененных данных для Oracle компании Attunity</span><span class="sxs-lookup"><span data-stu-id="214b3-148">Change Data Capture Service for Oracle by Attunity How to Guide</span></span>](change-data-capture-service-for-oracle-by-attunity-how-to-guide.md)  
  
## <a name="see-also"></a><span data-ttu-id="214b3-149">См. также:</span><span class="sxs-lookup"><span data-stu-id="214b3-149">See Also</span></span>  
 [<span data-ttu-id="214b3-150">Работа со службой CDC Oracle</span><span class="sxs-lookup"><span data-stu-id="214b3-150">Working with the Oracle CDC Service</span></span>](working-with-the-oracle-cdc-service.md)  
  
  
