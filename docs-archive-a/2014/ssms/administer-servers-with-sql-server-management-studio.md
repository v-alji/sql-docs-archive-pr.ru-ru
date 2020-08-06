---
title: Администрирование серверов при помощи среды SQL Server Management Studio | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], servers
- servers [SQL Server], administering
ms.assetid: 938bb035-e07a-4082-9f93-229d9feb6b06
author: stevestein
ms.author: sstein
ms.openlocfilehash: fb2a6b9afba7d838cf71144f88ed7866c54ad796
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737520"
---
# <a name="administer-servers-with-sql-server-management-studio"></a><span data-ttu-id="a616d-102">Администрирование серверов при помощи среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a616d-102">Administer Servers with SQL Server Management Studio</span></span>
  [!INCLUDE[msCoName](../includes/msconame-md.md)]<span data-ttu-id="a616d-103">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]— это многофункциональный интегрированный административный клиент, предназначенный для удовлетворения [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] требований к управлению сервером администратора.</span><span class="sxs-lookup"><span data-stu-id="a616d-103">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] is a rich, integrated administrative client designed to meet the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] administrator's server management requirements.</span></span> <span data-ttu-id="a616d-104">В среде [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]задачи администрирования выполняются при помощи обозревателя объектов, который позволяет подключиться к любому серверу семейства [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] и просматривать его содержимое при помощи графических средств.</span><span class="sxs-lookup"><span data-stu-id="a616d-104">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], administrative tasks are accomplished using Object Explorer, which allows you to connect to any server in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] family and graphically browse its contents.</span></span> <span data-ttu-id="a616d-105">Сервер может быть экземпляром компонента [!INCLUDE[ssDE](../includes/ssde-md.md)], службами [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] или службами [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a616d-105">A server can be an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], or [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="a616d-106">В число средств среды [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] входят зарегистрированные серверы, обозреватель объектов, обозреватель решений, обозреватель шаблонов, страница сводки и окно документа.</span><span class="sxs-lookup"><span data-stu-id="a616d-106">The tool components of [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] include Registered Servers, Object Explorer, Solution Explorer, Template Explorer, the Object Explorer Details page, and the document window.</span></span> <span data-ttu-id="a616d-107">Чтобы отобразить средство, в меню **Вид** выберите его название.</span><span class="sxs-lookup"><span data-stu-id="a616d-107">To display a tool, on the **View** menu, click the tool name.</span></span> <span data-ttu-id="a616d-108">Для отображения редактора запросов нажмите кнопку **Создать запрос** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="a616d-108">To display the Query Editor tool, click the **New Query** button on the toolbar.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a616d-109">По умолчанию сетевой трафик между [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] и [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] не шифруется.</span><span class="sxs-lookup"><span data-stu-id="a616d-109">Network traffic between [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is unencrypted by default.</span></span> <span data-ttu-id="a616d-110">Не работайте в среде [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] с конфиденциальными данными (включая пароли), не установив шифруемого соединения.</span><span class="sxs-lookup"><span data-stu-id="a616d-110">Do not work with sensitive data (including passwords) in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] unless you have established an encrypted connection.</span></span> <span data-ttu-id="a616d-111">Дополнительные сведения см. в разделе [Включение шифрования соединений в компоненте Database Engine (диспетчер конфигураций SQL Server)](../database-engine/configure-windows/enable-encrypted-connections-to-the-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="a616d-111">For more information, see [Enable Encrypted Connections to the Database Engine &#40;SQL Server Configuration Manager&#41;](../database-engine/configure-windows/enable-encrypted-connections-to-the-database-engine.md).</span></span>  
  
 <span data-ttu-id="a616d-112">Используйте среду [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] для выполнения следующих действий:</span><span class="sxs-lookup"><span data-stu-id="a616d-112">Use [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] to:</span></span>  
  
-   <span data-ttu-id="a616d-113">регистрации серверов;</span><span class="sxs-lookup"><span data-stu-id="a616d-113">Register servers.</span></span>  
  
-   <span data-ttu-id="a616d-114">соединения с экземпляром компонента [!INCLUDE[ssDE](../includes/ssde-md.md)], службами [!INCLUDE[ssAS](../includes/ssas-md.md)], службами [!INCLUDE[ssRS](../includes/ssrs.md)] или службами [!INCLUDE[ssIS](../includes/ssis-md.md)];</span><span class="sxs-lookup"><span data-stu-id="a616d-114">Connect to an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)], [!INCLUDE[ssAS](../includes/ssas-md.md)], [!INCLUDE[ssRS](../includes/ssrs.md)], or [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
-   <span data-ttu-id="a616d-115">настройки свойств сервера;</span><span class="sxs-lookup"><span data-stu-id="a616d-115">Configure server properties.</span></span>  
  
-   <span data-ttu-id="a616d-116">управления объектами базы данных и службами [!INCLUDE[ssAS](../includes/ssas-md.md)] , такими как кубы, измерения и сборки;</span><span class="sxs-lookup"><span data-stu-id="a616d-116">Manage database and [!INCLUDE[ssAS](../includes/ssas-md.md)] objects such as cubes, dimensions, and assemblies.</span></span>  
  
-   <span data-ttu-id="a616d-117">создания таких объектов, как базы данных, таблицы, кубы, пользователи базы данных и имена входа;</span><span class="sxs-lookup"><span data-stu-id="a616d-117">Create objects, such as databases, tables, cubes, database users, and logins.</span></span>  
  
-   <span data-ttu-id="a616d-118">управления файлами и группами файлов;</span><span class="sxs-lookup"><span data-stu-id="a616d-118">Manage files and filegroups.</span></span>  
  
-   <span data-ttu-id="a616d-119">присоединения или отсоединения баз данных;</span><span class="sxs-lookup"><span data-stu-id="a616d-119">Attach or detach databases.</span></span>  
  
-   <span data-ttu-id="a616d-120">запуска средств для работы со сценариями;</span><span class="sxs-lookup"><span data-stu-id="a616d-120">Launch scripting tools.</span></span>  
  
-   <span data-ttu-id="a616d-121">управления безопасностью;</span><span class="sxs-lookup"><span data-stu-id="a616d-121">Manage security.</span></span>  
  
-   <span data-ttu-id="a616d-122">просмотра системных журналов;</span><span class="sxs-lookup"><span data-stu-id="a616d-122">View system logs.</span></span>  
  
-   <span data-ttu-id="a616d-123">контроля текущей активности;</span><span class="sxs-lookup"><span data-stu-id="a616d-123">Monitor current activity.</span></span>  
  
-   <span data-ttu-id="a616d-124">настройки репликации;</span><span class="sxs-lookup"><span data-stu-id="a616d-124">Configure replication.</span></span>  
  
-   <span data-ttu-id="a616d-125">управления полнотекстовыми индексами.</span><span class="sxs-lookup"><span data-stu-id="a616d-125">Manage full-text indexes.</span></span>  
  
 <span data-ttu-id="a616d-126">Для запуска и остановки [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] или агента [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] следует использовать диспетчер конфигурации [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a616d-126">To start and stop [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent, use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a616d-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="a616d-127">See Also</span></span>  
 <span data-ttu-id="a616d-128">[Использование SQL Server Management Studio](../database-engine/use-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="a616d-128">[Use SQL Server Management Studio](../database-engine/use-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="a616d-129">Просмотр или изменение свойств сервера (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a616d-129">View or Change Server Properties &#40;SQL Server&#41;</span></span>](../database-engine/configure-windows/view-or-change-server-properties-sql-server.md)  
  
  
