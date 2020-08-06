---
title: Диспетчер подключений OLE DB | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- OLE DB connection manager
- data sources [Integration Services], connections
- connection managers [Integration Services], OLE DB
- connections [Integration Services], OLE DB
ms.assetid: 91e3622e-4b1a-439a-80c7-a00b90d66979
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5431de956a1039c2978688982792f190b0abc544
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665484"
---
# <a name="ole-db-connection-manager"></a><span data-ttu-id="70aff-102">диспетчер соединений OLE DB</span><span class="sxs-lookup"><span data-stu-id="70aff-102">OLE DB Connection Manager</span></span>
  <span data-ttu-id="70aff-103">Диспетчер соединений OLE DB позволяет пакету подключаться к источнику данных с помощью поставщика OLE DB.</span><span class="sxs-lookup"><span data-stu-id="70aff-103">An OLE DB connection manager enables a package to connect to a data source by using an OLE DB provider.</span></span> <span data-ttu-id="70aff-104">Например, диспетчер соединений OLE DB, который подключается к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , может использовать поставщик [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="70aff-104">For example, an OLE DB connection manager that connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can use the [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70aff-105">Собственный поставщик OLE DB [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] версии 11.0 не поддерживает новые ключевые слова строки соединения (MultiSubnetFailover=True) для отказоустойчивых кластеров с несколькими подсетями.</span><span class="sxs-lookup"><span data-stu-id="70aff-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client 11.0 OLEDB provider does not support the new connection string key words (MultiSubnetFailover=True) for Multi-Subnet Failover Clustering.</span></span> <span data-ttu-id="70aff-106">Дополнительные сведения см. в [заметках о Выпуске SQL Server](https://go.microsoft.com/fwlink/?LinkId=247824) и в записи блога, [отработке отказа в нескольких подсетях AlwaysOn и службах SSIS](https://www.mattmasson.com/2012/03/alwayson-multi-subnet-failover-and-ssis/)на www.mattmasson.com.</span><span class="sxs-lookup"><span data-stu-id="70aff-106">For more information, see the [SQL Server Release  Notes](https://go.microsoft.com/fwlink/?LinkId=247824) and the blog post, [AlwaysOn Multi-Subnet Failover and SSIS](https://www.mattmasson.com/2012/03/alwayson-multi-subnet-failover-and-ssis/), on www.mattmasson.com.</span></span>  
  
 <span data-ttu-id="70aff-107">Несколько [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] задач и компонентов потока данных используют диспетчер соединений OLE DB.</span><span class="sxs-lookup"><span data-stu-id="70aff-107">Several [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] tasks and data flow components use an OLE DB connection manager.</span></span> <span data-ttu-id="70aff-108">Например, источник OLE DB и назначение «OLE DB» применяют диспетчер соединений для извлечения и загрузки данных, а задача «Выполнение SQL» может применять его для подключения к базе данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , чтобы выполнять запросы.</span><span class="sxs-lookup"><span data-stu-id="70aff-108">For example, the OLE DB source and OLE DB destination use this connection manager to extract and load data, and the Execute SQL task can use this connection manager to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database to run queries.</span></span>  
  
 <span data-ttu-id="70aff-109">Кроме того, диспетчер соединений OLE DB применяется для доступа к источникам данных OLE DB в пользовательских задачах, написанных неуправляемым кодом на языке, подобном C++.</span><span class="sxs-lookup"><span data-stu-id="70aff-109">The OLE DB connection manager is also used to access OLE DB data sources in custom tasks written in unmanaged code that uses a language such as C++.</span></span>  
  
 <span data-ttu-id="70aff-110">При добавлении к пакету диспетчера соединений OLE DB службы [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] создают диспетчер соединений, который будет решать задачи соединений OLE DB во время выполнения, устанавливает свойства диспетчера соединений и добавляет его к коллекции `Connections` пакета.</span><span class="sxs-lookup"><span data-stu-id="70aff-110">When you add an OLE DB connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an OLE DB connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span>  
  
 <span data-ttu-id="70aff-111">Свойству `ConnectionManagerType` диспетчера соединений присваивается значение `OLEDB`.</span><span class="sxs-lookup"><span data-stu-id="70aff-111">The `ConnectionManagerType` property of the connection manager is set to `OLEDB`.</span></span>  
  
 <span data-ttu-id="70aff-112">Диспетчер соединений OLE DB можно настроить следующими способами:</span><span class="sxs-lookup"><span data-stu-id="70aff-112">The OLE DB connection manager can be configured in the following ways:</span></span>  
  
-   <span data-ttu-id="70aff-113">Укажите конкретную строку соединения, соответствующую требованиям конфигурации выбранного поставщика.</span><span class="sxs-lookup"><span data-stu-id="70aff-113">Provide a specific connection string configured to meet the requirements of the selected provider.</span></span>  
  
-   <span data-ttu-id="70aff-114">В зависимости от поставщика предоставьте имя источника данных, к которому производится подключение.</span><span class="sxs-lookup"><span data-stu-id="70aff-114">Depending on the provider, include the name of the data source to connect to.</span></span>  
  
-   <span data-ttu-id="70aff-115">Предоставьте безопасные учетные данные, соответствующие выбранному поставщику.</span><span class="sxs-lookup"><span data-stu-id="70aff-115">Provide security credentials as appropriate for the selected provider.</span></span>  
  
-   <span data-ttu-id="70aff-116">Обозначает, будет ли соединение, созданное из диспетчера соединений, сохранено во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="70aff-116">Indicate whether the connection that is created from the connection manager is retained at run time.</span></span>  
  
## <a name="logging"></a><span data-ttu-id="70aff-117">Ведение журнала</span><span class="sxs-lookup"><span data-stu-id="70aff-117">Logging</span></span>  
 <span data-ttu-id="70aff-118">В журнал можно записывать вызовы, сделанные диспетчером соединений OLE DB к внешним поставщикам данных.</span><span class="sxs-lookup"><span data-stu-id="70aff-118">You can log the calls that the OLE DB connection manager makes to external data providers.</span></span> <span data-ttu-id="70aff-119">Эта возможность ведения журнала может быть использована для устранения неполадок соединений, которые выполняются диспетчером соединений OLE DB к внешним источникам данных.</span><span class="sxs-lookup"><span data-stu-id="70aff-119">You can use this logging capability to troubleshoot the connections that the OLE DB connection manager makes to external data sources.</span></span> <span data-ttu-id="70aff-120">Чтобы зарегистрировать вызовы, которые диспетчер соединений OLE DB делает внешними поставщиками данных, включите ведение журнала пакета и выберите событие **диагностики** на уровне пакета.</span><span class="sxs-lookup"><span data-stu-id="70aff-120">To log the calls that the OLE DB connection manager makes to external data providers, enable package logging and select the **Diagnostic** event at the package level.</span></span> <span data-ttu-id="70aff-121">Дополнительные сведения см. в разделе [Инструменты устранения неполадок при выполнении пакетов](../troubleshooting/troubleshooting-tools-for-package-execution.md).</span><span class="sxs-lookup"><span data-stu-id="70aff-121">For more information, see [Troubleshooting Tools for Package Execution](../troubleshooting/troubleshooting-tools-for-package-execution.md).</span></span>  
  
## <a name="configuration-of-the-oledb-connection-manager"></a><span data-ttu-id="70aff-122">Настройка диспетчера соединений OLE DB</span><span class="sxs-lookup"><span data-stu-id="70aff-122">Configuration of the OLEDB Connection Manager</span></span>  
 <span data-ttu-id="70aff-123">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="70aff-123">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span> <span data-ttu-id="70aff-124">Дополнительные сведения о свойствах, которые можно задавать в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] , см. в разделе [Настройка диспетчера соединений OLE DB](../configure-ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="70aff-124">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [Configure OLE DB Connection Manager](../configure-ole-db-connection-manager.md).</span></span> <span data-ttu-id="70aff-125">Дополнительные сведения о настройке диспетчера соединений программными средствами см. в документации по классу **T:Microsoft.SqlServer.Dts.Runtime.ConnectionManager** в руководстве для разработчиков.</span><span class="sxs-lookup"><span data-stu-id="70aff-125">For information about configuring a connection manager programmatically, see the documentation for **T:Microsoft.SqlServer.Dts.Runtime.ConnectionManager** class in the Developer Guide.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="70aff-126">См. также</span><span class="sxs-lookup"><span data-stu-id="70aff-126">Related Content</span></span>  
  
-   <span data-ttu-id="70aff-127">Вики-статья, [службы SSIS с соединителями Oracle](https://go.microsoft.com/fwlink/?LinkId=220670) на Social.TechNet.Microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="70aff-127">Wiki article, [SSIS with Oracle Connectors](https://go.microsoft.com/fwlink/?LinkId=220670) on social.technet.microsoft.com.</span></span>  
  
-   <span data-ttu-id="70aff-128">Техническая статья [Connection Strings for OLE DB Providers](https://go.microsoft.com/fwlink/?LinkId=220744)(Строки подключения для поставщиков OLE DB) на сайте carlprothman.net.</span><span class="sxs-lookup"><span data-stu-id="70aff-128">Technical article, [Connection Strings for OLE DB Providers](https://go.microsoft.com/fwlink/?LinkId=220744), on carlprothman.net.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70aff-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="70aff-129">See Also</span></span>  
 <span data-ttu-id="70aff-130">[Источник OLE DB](../data-flow/ole-db-source.md) </span><span class="sxs-lookup"><span data-stu-id="70aff-130">[OLE DB Source](../data-flow/ole-db-source.md) </span></span>  
 <span data-ttu-id="70aff-131">[Назначение OLE DB](../data-flow/ole-db-destination.md) </span><span class="sxs-lookup"><span data-stu-id="70aff-131">[OLE DB Destination](../data-flow/ole-db-destination.md) </span></span>  
 <span data-ttu-id="70aff-132">[Задача «Выполнение SQL»](../control-flow/execute-sql-task.md) </span><span class="sxs-lookup"><span data-stu-id="70aff-132">[Execute SQL Task](../control-flow/execute-sql-task.md) </span></span>  
 [<span data-ttu-id="70aff-133">Соединения в службах Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="70aff-133">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
