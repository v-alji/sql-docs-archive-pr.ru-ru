---
title: Реализация дочерних пакетов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- child packages
ms.assetid: ab0c09d7-ce2e-487d-a1ed-a4b5adb6cc01
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f4fa4fa7c523c55c595341c7aee6a530c5918a34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730842"
---
# <a name="implementation-of-child-packages"></a><span data-ttu-id="91bcd-102">Осуществление дочерних пакетов</span><span class="sxs-lookup"><span data-stu-id="91bcd-102">Implementation of Child Packages</span></span>
  <span data-ttu-id="91bcd-103">При реализации балансировки нагрузки с помощью служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]дочерние пакеты устанавливаются на другие серверы для получения преимуществ от доступного времени ЦП или сервера.</span><span class="sxs-lookup"><span data-stu-id="91bcd-103">When you implement load balancing using [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], child packages are installed on other servers to take advantage of the available CPU or server time.</span></span> <span data-ttu-id="91bcd-104">Чтобы создать и запустить дочерние пакеты, требуется выполнить следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="91bcd-104">To create and run the child packages requires the following steps:</span></span>  
  
-   <span data-ttu-id="91bcd-105">Разработка дочерних пакетов.</span><span class="sxs-lookup"><span data-stu-id="91bcd-105">Designing the child packages.</span></span>  
  
-   <span data-ttu-id="91bcd-106">Перемещение пакетов на удаленный сервер.</span><span class="sxs-lookup"><span data-stu-id="91bcd-106">Moving the packages to the remote server.</span></span>  
  
-   <span data-ttu-id="91bcd-107">Создание задания агента SQL Server, содержащего шаг запуска дочернего пакета, на удаленном сервере.</span><span class="sxs-lookup"><span data-stu-id="91bcd-107">Creating a SQL Server Agent Job on the remote server that contains a step that runs the child package.</span></span>  
  
-   <span data-ttu-id="91bcd-108">Тестирование и отладка задания агента SQL Server и дочерних пакетов.</span><span class="sxs-lookup"><span data-stu-id="91bcd-108">Testing and debugging the SQL Server Agent Job and child packages.</span></span>  
  
 <span data-ttu-id="91bcd-109">При разработке дочерних пакетов нет никаких ограничений, и в них можно заложить любую функциональность.</span><span class="sxs-lookup"><span data-stu-id="91bcd-109">When you design the child packages, the packages have no limitations in their design, and you can put in any functionality you desire.</span></span> <span data-ttu-id="91bcd-110">Однако если пакет получает доступ к данным, необходимо быть уверенным в том, что сервер, который запускает пакет, имеет доступ к этим данным.</span><span class="sxs-lookup"><span data-stu-id="91bcd-110">However, if the package accesses data, you must ensure that the server that runs the package has access to the data.</span></span>  
  
 <span data-ttu-id="91bcd-111">Чтобы определить родительский пакет, который выполняет дочерние пакеты, в [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] щелкните пакет правой кнопкой мыши в обозревателе решений и выберите команду **Пакет точки входа**.</span><span class="sxs-lookup"><span data-stu-id="91bcd-111">To identify the parent package that executes child packages, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] right click the package in Solution Explorer and then click **Entry-point Package**.</span></span>  
  
 <span data-ttu-id="91bcd-112">После разработки дочернего пакета следующий шаг состоит в его развертывании на удаленных серверах.</span><span class="sxs-lookup"><span data-stu-id="91bcd-112">After the child packages have been designed, the next step is to deploy them on the remote servers.</span></span>  
  
## <a name="moving-the-child-package-to-the-remote-instance"></a><span data-ttu-id="91bcd-113">Перемещение дочернего пакета на удаленный экземпляр сервера</span><span class="sxs-lookup"><span data-stu-id="91bcd-113">Moving the Child Package to the Remote Instance</span></span>  
 <span data-ttu-id="91bcd-114">Существует несколько способов перемещения пакетов на другие серверы.</span><span class="sxs-lookup"><span data-stu-id="91bcd-114">There are multiple ways to move packages to other servers.</span></span> <span data-ttu-id="91bcd-115">Вот два рекомендуемых метода.</span><span class="sxs-lookup"><span data-stu-id="91bcd-115">The two suggested methods are:</span></span>  
  
-   <span data-ttu-id="91bcd-116">Экспорт пакетов с помощью среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="91bcd-116">Exporting packages by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="91bcd-117">Развертывание пакетов путем построения программы развертывания для проекта, содержащего необходимые пакеты, с последующим запуском мастера установки пакета для размещения пакетов в файловой системе или на экземпляре [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="91bcd-117">Deploying packages by building a deployment utility for the project that contains the packages you want to deploy, and then running the Package Installation Wizard to install the packages to the file system or to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="91bcd-118">Дополнительные сведения см. в разделе [Развертывание пакетов &#40;SSIS&#41;](packages/legacy-package-deployment-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="91bcd-118">For more information, see [Package Deployment &#40;SSIS&#41;](packages/legacy-package-deployment-ssis.md).</span></span>  
  
 <span data-ttu-id="91bcd-119">Развертывание необходимо повторить на каждом используемом удаленном сервере.</span><span class="sxs-lookup"><span data-stu-id="91bcd-119">You must repeat the deployment to each remote server you want to use.</span></span>  
  
## <a name="creating-the-sql-server-agent-jobs"></a><span data-ttu-id="91bcd-120">Создание задания агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="91bcd-120">Creating the SQL Server Agent Jobs</span></span>  
 <span data-ttu-id="91bcd-121">После того как дочерние пакеты были развернуты на различных серверах, создайте задание агента SQL Server на каждом сервере, содержащем дочерний пакет.</span><span class="sxs-lookup"><span data-stu-id="91bcd-121">After the child packages have been deployed to the various servers, create a SQL Server Agent job on each server that contains a child package.</span></span> <span data-ttu-id="91bcd-122">Задание агента SQL Server содержит шаг, который запускает дочерний пакет при вызове агента задания.</span><span class="sxs-lookup"><span data-stu-id="91bcd-122">The SQL Server Agent job contains a step that runs the child package when the job agent is called.</span></span> <span data-ttu-id="91bcd-123">Задания агента SQL Server не являются запланированными заданиями. Они запускают дочерние пакеты только тогда, когда они вызываются родительским пакетом.</span><span class="sxs-lookup"><span data-stu-id="91bcd-123">The SQL Server Agent jobs are not scheduled jobs; they run the child packages only when they are called by the parent package.</span></span> <span data-ttu-id="91bcd-124">Уведомления об успешном или неуспешном выполнении задания возвращаются в родительский пакет, отражая успешное или неуспешное выполнение задания агента SQL Server и факт его успешного вызова, а не результат или факт выполнения дочернего пакета.</span><span class="sxs-lookup"><span data-stu-id="91bcd-124">Notification of success or failure of the job back to the parent package reflects the success or failure of the SQL Server Agent job and whether it was called successfully, not the success or failure of the child package or whether it was executed.</span></span>  
  
## <a name="debugging-the-sql-server-agent-jobs-and-child-packages"></a><span data-ttu-id="91bcd-125">Отладка задания агента SQL Server и дочерних пакетов</span><span class="sxs-lookup"><span data-stu-id="91bcd-125">Debugging the SQL Server Agent Jobs and Child Packages</span></span>  
 <span data-ttu-id="91bcd-126">Протестировать задания агента SQL Server и их дочерние пакеты можно с помощью одного из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="91bcd-126">You can test the SQL Server Agent jobs and their child packages by using one of the following methods:</span></span>  
  
-   <span data-ttu-id="91bcd-127">Запуск каждого дочернего пакета в конструкторе служб SSIS путем нажатия кнопки **Отладка**  /  **Запуск без отладки**.</span><span class="sxs-lookup"><span data-stu-id="91bcd-127">Running each child package in SSIS Designer, by clicking **Debug** / **Start Without Debugging**.</span></span>  
  
-   <span data-ttu-id="91bcd-128">выполняя индивидуальное задание агента SQL Server на удаленном компьютере, используя среду [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], чтобы убедиться в том, что пакет запущен.</span><span class="sxs-lookup"><span data-stu-id="91bcd-128">Running the individual SQL Server Agent job on the remote computer by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], to make sure that the package runs.</span></span>  
  
 <span data-ttu-id="91bcd-129">Сведения о решении проблем с пакетами, запускаемыми из заданий агента [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] см. в статье [Пакет служб SSIS не запускается при вызове пакета служб SSIS на шаге задания агента SQL Server](https://support.microsoft.com/kb/918760) в базе знаний поддержки [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="91bcd-129">For information about how to troubleshoot packages that you run from [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs, see [An SSIS package does not run when you call the SSIS package from a SQL Server Agent job step](https://support.microsoft.com/kb/918760) in the [!INCLUDE[msCoName](../includes/msconame-md.md)] Support Knowledge Base.</span></span>  
  
 <span data-ttu-id="91bcd-130">Агент SQL Server проверяет действительность доступа к подсистеме учетной записи-посредника и предоставляет ей доступ при каждом выполнении шага задания.</span><span class="sxs-lookup"><span data-stu-id="91bcd-130">The SQL Server Agent checks subsystem access for a proxy and gives access to the proxy every time the job step runs.</span></span>  
  
 <span data-ttu-id="91bcd-131">Создать прокси-сервер можно в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="91bcd-131">You can create a proxy in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="91bcd-132">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="91bcd-132">Related Tasks</span></span>  
  
-   [<span data-ttu-id="91bcd-133">Выполнение пакета на сервере служб SSIS с использованием среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="91bcd-133">Run a Package on the SSIS Server Using SQL Server Management Studio</span></span>](run-a-package-on-the-ssis-server-using-sql-server-management-studio.md)  
  
## <a name="related-content"></a><span data-ttu-id="91bcd-134">См. также</span><span class="sxs-lookup"><span data-stu-id="91bcd-134">Related Content</span></span>  
  
-   <span data-ttu-id="91bcd-135">Запись в блоге [службы SSIS: доступ к переменным в родительском пакете](https://andyleonard.blog/2015/08/ssis-design-pattern-access-parent-variables-from-a-child-package-in-the-ssis-catalog/)в андилеонард. blog.</span><span class="sxs-lookup"><span data-stu-id="91bcd-135">Blog entry, [SSIS: Accessing variables in a parent package](https://andyleonard.blog/2015/08/ssis-design-pattern-access-parent-variables-from-a-child-package-in-the-ssis-catalog/), on andyleonard.blog.</span></span>  
  
-   <span data-ttu-id="91bcd-136">Статья, [задача «Выполнение пакета](../integration-services/control-flow/execute-package-task.md)».</span><span class="sxs-lookup"><span data-stu-id="91bcd-136">Article, [Execute Package Task](../integration-services/control-flow/execute-package-task.md).</span></span>  
  
  
