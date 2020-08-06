---
title: Настройка контактной зоны | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- reducing attackable surface area
- upgrading SQL Server, security
- surface area configuration [SQL Server]
- surface area configuration [SQL Server], about surface area configuration
- attackable surface area [SQL Server]
- installing SQL Server, security
ms.assetid: f741169c-1453-4ad2-830b-bf2be27d712f
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: ef64fbbeb2b8953ff3816db63572b499d42f012e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730301"
---
# <a name="surface-area-configuration"></a><span data-ttu-id="02f16-102">Настройка контактной зоны</span><span class="sxs-lookup"><span data-stu-id="02f16-102">Surface Area Configuration</span></span>
  <span data-ttu-id="02f16-103">В конфигурации по умолчанию для новых установок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]многие из функций отключены.</span><span class="sxs-lookup"><span data-stu-id="02f16-103">In the default configuration of new installations of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], many features are not enabled.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="02f16-104">выборочно устанавливает и запускает только ключевые службы и функции, чтобы свести к минимуму количество функций, которые могут подвергнуться атаке злоумышленника.</span><span class="sxs-lookup"><span data-stu-id="02f16-104">selectively installs and starts only key services and features, to minimize the number of features that can be attacked by a malicious user.</span></span> <span data-ttu-id="02f16-105">Системный администратор может изменить эти значения по умолчанию в ходе установки, а также включать или отключать функции работающего экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]по своему выбору.</span><span class="sxs-lookup"><span data-stu-id="02f16-105">A system administrator can change these defaults at installation time and also selectively enable or disable features of a running instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="02f16-106">Кроме того, при подключении с других компьютеров определенные компоненты могут быть недоступны до настройки протоколов.</span><span class="sxs-lookup"><span data-stu-id="02f16-106">Additionally, some components may not be available when connecting from other computers until protocols are configured.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="02f16-107">В отличие от новых установок, во время обновления существующие службы или функции не отключаются, но после его завершения могут быть применены дополнительные параметры конфигурации контактной зоны.</span><span class="sxs-lookup"><span data-stu-id="02f16-107">Unlike new installations, no existing services or features are turned off during an upgrade, but additional surface area configuration options can be applied after the upgrade is completed.</span></span>  
  
## <a name="protocols-connection-and-startup-options"></a><span data-ttu-id="02f16-108">Протоколы, соединение и параметры запуска</span><span class="sxs-lookup"><span data-stu-id="02f16-108">Protocols, Connection, and Startup Options</span></span>  
 <span data-ttu-id="02f16-109">С помощью диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] можно запускать и останавливать службы, настраивать параметры запуска и включать протоколы и другие параметры соединения.</span><span class="sxs-lookup"><span data-stu-id="02f16-109">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to start and stop services, configure the startup options, and enable protocols and other connection options.</span></span>  
  
#### <a name="to-start-sql-server-configuration-manager"></a><span data-ttu-id="02f16-110">Запуск диспетчера конфигурации SQL Server</span><span class="sxs-lookup"><span data-stu-id="02f16-110">To start SQL Server Configuration Manager</span></span>  
  
1.  <span data-ttu-id="02f16-111">В меню **Пуск** последовательно выберите пункты **Все программы**, [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], **Средства настройки**и щелкните **Диспетчер конфигурации SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="02f16-111">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
    -   <span data-ttu-id="02f16-112">Для запуска компонентов и настройки автоматического запуска используйте область **Службы SQL Server** диспетчера конфигурации.</span><span class="sxs-lookup"><span data-stu-id="02f16-112">Use the **SQL Server Services** area to start components and configure the automatic starting options.</span></span>  
  
    -   <span data-ttu-id="02f16-113">Используйте область **Сетевая конфигурация SQL Server** для включения протоколов и параметров соединения, таких как фиксированные порты TCP/IP или принудительное шифрование.</span><span class="sxs-lookup"><span data-stu-id="02f16-113">Use the **SQL Server Network Configuration** area to enable connection protocols, and connection options such as fixed TCP/IP ports, or forcing encryption.</span></span>  
  
 <span data-ttu-id="02f16-114">Дополнительные сведения см. в разделе [SQL Server Configuration Manager](../sql-server-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="02f16-114">For more information, see [SQL Server Configuration Manager](../sql-server-configuration-manager.md).</span></span> <span data-ttu-id="02f16-115">Возможность удаленного подключения также зависит от правильной настройки брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="02f16-115">Remote connectivity can also depend upon the correct configuration of a firewall.</span></span> <span data-ttu-id="02f16-116">Дополнительные сведения см. в статье [Настройка брандмауэра Windows для разрешения доступа к SQL Server](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="02f16-116">For more information, see [Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span></span>  
  
## <a name="enabling-and-disabling-features"></a><span data-ttu-id="02f16-117">Включение и отключение функций</span><span class="sxs-lookup"><span data-stu-id="02f16-117">Enabling and Disabling Features</span></span>  
 <span data-ttu-id="02f16-118">Включение и отключение функций [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] можно настроить с помощью аспектов в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02f16-118">Enabling and disabling [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] features can be configured using facets in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-configure-surface-area-using-facets"></a><span data-ttu-id="02f16-119">Настройка контактной зоны с помощью аспектов</span><span class="sxs-lookup"><span data-stu-id="02f16-119">To configure surface area using facets</span></span>  
  
1.  <span data-ttu-id="02f16-120">В [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] выполните соединение с компонентом [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02f16-120">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] connect to a component of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="02f16-121">В обозревателе объектов щелкните правой кнопкой мыши сервер и выберите пункт **Аспекты**.</span><span class="sxs-lookup"><span data-stu-id="02f16-121">In Object Explorer, right-click the server, and then click **Facets**.</span></span>  
  
3.  <span data-ttu-id="02f16-122">В диалоговом окне **Просмотр аспектов** разверните список **Аспекты** , выберите соответствующий аспект **Настройка контактной зоны** (**Настройка контактной зоны**, **Настройка контактной зоны для служб Analysis Services**или **Настройка контактной зоны для служб Reporting Services**).</span><span class="sxs-lookup"><span data-stu-id="02f16-122">In the **View Facets** dialog box, expand the **Facet** list, and select the appropriate **Surface Area Configuration** facet (**Surface Area Configuration**, **Surface Area Configuration for Analysis Services**, or **Surface Area Configuration for Reporting Services**).</span></span>  
  
4.  <span data-ttu-id="02f16-123">В области **Свойства аспектов** выберите необходимые значения для всех свойств.</span><span class="sxs-lookup"><span data-stu-id="02f16-123">In the **Facet properties** area, select the values that you want for each property.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="02f16-124">Для периодической проверки конфигурации аспекта используйте управление на основе политик.</span><span class="sxs-lookup"><span data-stu-id="02f16-124">To periodically check the configuration of a facet, use Policy-Based Management.</span></span> <span data-ttu-id="02f16-125">Дополнительные сведения об управлении на основе политик см. в статье [Администрирование серверов с помощью управления на основе политик](../policy-based-management/administer-servers-by-using-policy-based-management.md).</span><span class="sxs-lookup"><span data-stu-id="02f16-125">For more information about Policy-Based Management, see [Administer Servers by Using Policy-Based Management](../policy-based-management/administer-servers-by-using-policy-based-management.md).</span></span>  
  
 <span data-ttu-id="02f16-126">Также можно задать параметры компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] при помощи хранимой процедуры `sp_configure`.</span><span class="sxs-lookup"><span data-stu-id="02f16-126">You can also set [!INCLUDE[ssDE](../../includes/ssde-md.md)] options using the `sp_configure` stored procedure.</span></span> <span data-ttu-id="02f16-127">Дополнительные сведения см. в разделе [Параметры конфигурации сервера (SQL Server)](../../database-engine/configure-windows/server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="02f16-127">For more information, see [Server Configuration Options &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md).</span></span>  
  
 <span data-ttu-id="02f16-128">Чтобы изменить свойство **Включить встроенную безопасность**[!INCLUDE[ssRS](../../includes/ssrs.md)], используйте настройки свойств в службах [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02f16-128">To change the **EnableIntegrated Security** property of [!INCLUDE[ssRS](../../includes/ssrs.md)], use the property settings in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="02f16-129">Чтобы изменить свойство **Планирование событий и доставка отчетов** и свойство **Доступ к веб-службам и HTTP** , измените файл конфигурации **RSReportServer.config** .</span><span class="sxs-lookup"><span data-stu-id="02f16-129">To change the **Schedule events and report delivery** property and the **Web service and HTTP access** property, edit the **RSReportServer.config** configuration file.</span></span>  
  
## <a name="command-prompt-options"></a><span data-ttu-id="02f16-130">Параметры командной строки</span><span class="sxs-lookup"><span data-stu-id="02f16-130">Command-prompt Options</span></span>  
 <span data-ttu-id="02f16-131">Используйте командлет PowerShell **Invoke-PolicyEvaluation**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для вызова политик конфигурации контактной зоны.</span><span class="sxs-lookup"><span data-stu-id="02f16-131">Use the **Invoke-PolicyEvaluation**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell cmdlet to invoke Surface Area Configuration Policies.</span></span> <span data-ttu-id="02f16-132">Дополнительные сведения см. в разделе [Использование командлетов компонента Database Engine](../../database-engine/use-the-database-engine-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="02f16-132">For more information, see [Use the Database Engine cmdlets](../../database-engine/use-the-database-engine-cmdlets.md).</span></span>  
  
## <a name="soap-and-service-broker-endpoints"></a><span data-ttu-id="02f16-133">Конечные точки SOAP и Service Broker</span><span class="sxs-lookup"><span data-stu-id="02f16-133">SOAP and Service Broker Endpoints</span></span>  
 <span data-ttu-id="02f16-134">Для отключения конечных точек используйте управление на основе политик.</span><span class="sxs-lookup"><span data-stu-id="02f16-134">To turn endpoints off, use Policy-Based Management.</span></span> <span data-ttu-id="02f16-135">Для создания и изменения свойств конечных точек используйте инструкции [CREATE ENDPOINT (Transact-SQL)](/sql/t-sql/statements/create-endpoint-transact-sql) и [ALTER ENDPOINT (Transact-SQL)](/sql/t-sql/statements/alter-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="02f16-135">To create and alter the properties of endpoints, use [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) and [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="02f16-136">См. также</span><span class="sxs-lookup"><span data-stu-id="02f16-136">Related Content</span></span>  
 [<span data-ttu-id="02f16-137">Центр безопасности для ядра СУБД SQL Server и Базы данных Azure SQL</span><span class="sxs-lookup"><span data-stu-id="02f16-137">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
 [<span data-ttu-id="02f16-138">sp_configure (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="02f16-138">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
