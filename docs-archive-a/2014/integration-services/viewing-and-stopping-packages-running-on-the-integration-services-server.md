---
title: Просмотр и остановка пакетов, выполняющихся на сервере Integration Services | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- packages [Integration Services], managing
- managing running packages [Integration Services]
- packages [Integration Services], running
- running package [Integration Services], managing
ms.assetid: 11bf44e6-f6b0-475f-b816-40e914dbac80
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6e63839d4ab5d8d50f7d86eea05c8d58107d6799
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667786"
---
# <a name="viewing-and-stopping-packages-running-on-the-integration-services-server"></a><span data-ttu-id="70a16-102">Просмотр и остановка пакетов, выполняющихся на сервере служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="70a16-102">Viewing and Stopping Packages Running on the Integration Services Server</span></span>
  <span data-ttu-id="70a16-103">В базе данных служб `SSISDB` хранится журнал выполнения во внутренних таблицах, невидимых для пользователей.</span><span class="sxs-lookup"><span data-stu-id="70a16-103">The `SSISDB` database stores execution history in internal tables that are not visible to users.</span></span> <span data-ttu-id="70a16-104">Однако сведения, которые она предоставляет, можно получить с помощью запросов к общим представлениям.</span><span class="sxs-lookup"><span data-stu-id="70a16-104">However it exposes the information that you need through public views that you can query.</span></span> <span data-ttu-id="70a16-105">Также она предоставляет хранимые процедуры, которые можно вызвать для выполнения стандартных задач, связанных с пакетами.</span><span class="sxs-lookup"><span data-stu-id="70a16-105">It also provides stored procedures that you can call to perform common tasks related to packages.</span></span>  
  
 <span data-ttu-id="70a16-106">Обычно управление объектами служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] на сервере выполняется в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="70a16-106">Typically you manage [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] objects on the server in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="70a16-107">Но также можно создать запросы к представлениям базы данных и вызывать хранимые процедуры напрямую, либо написать специальный код, вызывающий управляемый API-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="70a16-107">However you can also query the database views and call the stored procedures directly, or write custom code that calls the managed API.</span></span> [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="70a16-108">и управляемый API-интерфейс для выполнения многих задач отправляют запросы к представлениям и вызывают хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="70a16-108">and the managed API query the views and call the stored procedures to perform many of their tasks.</span></span> <span data-ttu-id="70a16-109">Например, можно просмотреть список пакетов служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , выполняющихся в данный момент на сервере, и запросить остановку их выполнения при необходимости.</span><span class="sxs-lookup"><span data-stu-id="70a16-109">For example, you can view the list of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages that are currently running on the server, and request packages to stop if you have to.</span></span>  
  
## <a name="viewing-the-list-of-running-packages"></a><span data-ttu-id="70a16-110">Просмотр списка выполняемых пакетов</span><span class="sxs-lookup"><span data-stu-id="70a16-110">Viewing the List of Running Packages</span></span>  
 <span data-ttu-id="70a16-111">Можно просмотреть список пакетов, которые в данный момент выполняются на сервере, в диалоговом окне **Активные операции** .</span><span class="sxs-lookup"><span data-stu-id="70a16-111">You can view the list of packages that are currently running on the server in the **Active Operations** dialog box.</span></span> <span data-ttu-id="70a16-112">Дополнительные сведения см. в статье [Active Operations Dialog Box](../../2014/integration-services/active-operations-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="70a16-112">For more information, see [Active Operations Dialog Box](../../2014/integration-services/active-operations-dialog-box.md).</span></span>  
  
 <span data-ttu-id="70a16-113">Дополнительные сведения о других методах, которые можно использовать для просмотра списка запущенных пакетов, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="70a16-113">For information about the other methods that you can use to view the list of running packages, see the following topics.</span></span>  
  
 [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="70a16-114">доступ</span><span class="sxs-lookup"><span data-stu-id="70a16-114">access</span></span>  
 <span data-ttu-id="70a16-115">Чтобы просмотреть список пакетов, запущенных на сервере, создайте запрос к представлению [catalog.executions (база данных SSISDB)](/sql/integration-services/system-views/catalog-executions-ssisdb-database) для пакетов со значением состояния 2.</span><span class="sxs-lookup"><span data-stu-id="70a16-115">To view the list of packages that are running on the server, query the view, [catalog.executions &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-executions-ssisdb-database) for packages that have a status of 2.</span></span>  
  
 <span data-ttu-id="70a16-116">Программный доступ с использованием управляемого API-интерфейса</span><span class="sxs-lookup"><span data-stu-id="70a16-116">Programmatic access through the managed API</span></span>  
 <span data-ttu-id="70a16-117">См. пространство имен <xref:Microsoft.SqlServer.Management.IntegrationServices> и его классы.</span><span class="sxs-lookup"><span data-stu-id="70a16-117">See the <xref:Microsoft.SqlServer.Management.IntegrationServices> namespace and its classes.</span></span>  
  
## <a name="stopping-a-running-package"></a><span data-ttu-id="70a16-118">Остановка выполнения пакета</span><span class="sxs-lookup"><span data-stu-id="70a16-118">Stopping a Running Package</span></span>  
 <span data-ttu-id="70a16-119">Можно запросить остановку выполняющегося пакета в диалоговом окне **Активные операции** .</span><span class="sxs-lookup"><span data-stu-id="70a16-119">You can request a running package to stop in the **Active Operations** dialog box.</span></span> <span data-ttu-id="70a16-120">Дополнительные сведения см. в статье [Active Operations Dialog Box](../../2014/integration-services/active-operations-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="70a16-120">For more information, see [Active Operations Dialog Box](../../2014/integration-services/active-operations-dialog-box.md).</span></span>  
  
 <span data-ttu-id="70a16-121">Дополнительные сведения о других методах, которые можно использовать для остановки запущенного пакета, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="70a16-121">For information about the other methods that you can use to stop a running package, see the following topics.</span></span>  
  
 [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="70a16-122">доступ</span><span class="sxs-lookup"><span data-stu-id="70a16-122">access</span></span>  
 <span data-ttu-id="70a16-123">Чтобы остановить выполняемый на сервере пакет, следует вызвать хранимую процедуру [catalog.stop_operation (база данных SSISDB)](/sql/integration-services/system-stored-procedures/catalog-stop-operation-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="70a16-123">To stop a package that is running on the server, call the stored procedure, [catalog.stop_operation &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-stop-operation-ssisdb-database).</span></span>  
  
 <span data-ttu-id="70a16-124">Программный доступ с использованием управляемого API-интерфейса</span><span class="sxs-lookup"><span data-stu-id="70a16-124">Programmatic access through the managed API</span></span>  
 <span data-ttu-id="70a16-125">См. пространство имен <xref:Microsoft.SqlServer.Management.IntegrationServices> и его классы.</span><span class="sxs-lookup"><span data-stu-id="70a16-125">See the <xref:Microsoft.SqlServer.Management.IntegrationServices> namespace and its classes.</span></span>  
  
## <a name="viewing-the-history-of-packages-that-have-run"></a><span data-ttu-id="70a16-126">Просмотр журнала выполненных пакетов</span><span class="sxs-lookup"><span data-stu-id="70a16-126">Viewing the History of Packages That Have Run</span></span>  
 <span data-ttu-id="70a16-127">Для просмотра журнала пакетов, выполнявшихся в среде [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], используйте отчет **Все выполнения** .</span><span class="sxs-lookup"><span data-stu-id="70a16-127">To view the history of packages that have run in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], use the **All Executions** report.</span></span> <span data-ttu-id="70a16-128">Дополнительные сведения об отчете **Все выполнения** и других стандартных отчетах см. в разделе [Отчеты для сервера служб Integration Services](../../2014/integration-services/reports-for-the-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="70a16-128">For more information on the **All Executions** report and other standard reports, see [Reports for the Integration Services Server](../../2014/integration-services/reports-for-the-integration-services-server.md).</span></span>  
  
 <span data-ttu-id="70a16-129">Сведения о других методах, которые можно использовать для просмотра журнала выполняющихся пакетов, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="70a16-129">For information about the other methods that you can use to view the history of running packages, see the following topics.</span></span>  
  
 [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="70a16-130">доступ</span><span class="sxs-lookup"><span data-stu-id="70a16-130">access</span></span>  
 <span data-ttu-id="70a16-131">Для просмотра сведений о выполнявшихся пакетах запросите представление [catalog.executions (база данных SSISDB)](/sql/integration-services/system-views/catalog-executions-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="70a16-131">To view information about packages that have run, query the view, [catalog.executions &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-executions-ssisdb-database).</span></span>  
  
 <span data-ttu-id="70a16-132">Программный доступ с использованием управляемого API-интерфейса</span><span class="sxs-lookup"><span data-stu-id="70a16-132">Programmatic access through the managed API</span></span>  
 <span data-ttu-id="70a16-133">См. пространство имен <xref:Microsoft.SqlServer.Management.IntegrationServices> и его классы.</span><span class="sxs-lookup"><span data-stu-id="70a16-133">See the <xref:Microsoft.SqlServer.Management.IntegrationServices> namespace and its classes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70a16-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="70a16-134">See Also</span></span>  
 <span data-ttu-id="70a16-135">[Запуск проектов и пакетов](packages/run-integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="70a16-135">[Execution of Projects and Packages](packages/run-integration-services-ssis-packages.md) </span></span>  
 [<span data-ttu-id="70a16-136">Отчеты по устранению неполадок для выполнения пакетов</span><span class="sxs-lookup"><span data-stu-id="70a16-136">Troubleshooting Reports for Package Execution</span></span>](troubleshooting/troubleshooting-reports-for-package-execution.md)  
  
  
