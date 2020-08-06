---
title: Отладка обработчика бизнес-логики | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- merge replication business logic handlers [SQL Server replication]
- business logic handlers [SQL Server replication]
- BusinessLogicModule class
ms.assetid: edd0d17a-0e9c-4c28-8395-a7d47e8ce3d6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7b255407783b1e52a376e562ec910f8b123e42c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655654"
---
# <a name="debug-a-business-logic-handler-replication-programming"></a><span data-ttu-id="c9baf-102">выполнить отладку обработчика бизнес-логики (программирование репликации)</span><span class="sxs-lookup"><span data-stu-id="c9baf-102">Debug a Business Logic Handler (Replication Programming)</span></span>
  <span data-ttu-id="c9baf-103">Используйте обработчик бизнес-логики для вызова пользовательской бизнес-логики во время синхронизации подписки на публикацию слиянием.</span><span class="sxs-lookup"><span data-stu-id="c9baf-103">Use a business logic handler to invoke custom business logic when a merge subscription is synchronized.</span></span> <span data-ttu-id="c9baf-104">Дополнительные сведения см. в статье [Выполнение бизнес-логики при синхронизации слиянием](merge/execute-business-logic-during-merge-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="c9baf-104">For more information, see [Execute Business Logic During Merge Synchronization](merge/execute-business-logic-during-merge-synchronization.md).</span></span>  
  
 <span data-ttu-id="c9baf-105">Посредник репликации слиянием (replrec.dll) осуществляет вызов сборки управляемого кода, содержащей бизнес-логику.</span><span class="sxs-lookup"><span data-stu-id="c9baf-105">The Merge Replication Reconciler (replrec.dll) calls the managed code assembly containing the business logic.</span></span> <span data-ttu-id="c9baf-106">В большинстве случаев файл replrec.dll и пользовательская бизнес-логика выполняются на компьютере с запущенным агентом слияния (на сервере подписчика для подписки по запросу или на сервере распространителя для принудительной подписки).</span><span class="sxs-lookup"><span data-stu-id="c9baf-106">In most cases, replrec.dll and the custom business logic is executed on the computer where the Merge Agent runs (at the Subscriber for a pull subscription or at the Distributor for a push subscription).</span></span> <span data-ttu-id="c9baf-107">При веб-синхронизации или для подписчика [!INCLUDE[ssEW](../../includes/ssew-md.md)] посредник и пользовательская бизнес-логика выполняются на веб-сервере.</span><span class="sxs-lookup"><span data-stu-id="c9baf-107">In the case of Web synchronization, or in the case of a [!INCLUDE[ssEW](../../includes/ssew-md.md)] Subscriber, the reconciler and the custom business logic is executed on the Web server.</span></span>  
  
### <a name="to-debug-a-business-logic-handler-on-a-local-computer"></a><span data-ttu-id="c9baf-108">Отладка обработчика бизнес-логики на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="c9baf-108">To debug a business logic handler on a local computer</span></span>  
  
1.  <span data-ttu-id="c9baf-109">Настройте публикацию и распространение, создайте новую публикацию, а затем подписку на нее.</span><span class="sxs-lookup"><span data-stu-id="c9baf-109">Configure publishing and distribution, create a publication, and create a subscription to the publication.</span></span> <span data-ttu-id="c9baf-110">Дополнительные сведения см. в статьях [Настройка публикации и распространения](configure-publishing-and-distribution.md) и [Создание публикации](publish/create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="c9baf-110">For more information, see [Configure Publishing and Distribution](configure-publishing-and-distribution.md) and [Create a Publication](publish/create-a-publication.md).</span></span>  
  
2.  <span data-ttu-id="c9baf-111">Создайте и зарегистрируйте обработчик бизнес-логики.</span><span class="sxs-lookup"><span data-stu-id="c9baf-111">Create and register a business logic handler.</span></span> <span data-ttu-id="c9baf-112">Дополнительные сведения см. в статье [Реализация обработчика бизнес-логики для статьи публикации слиянием](implement-a-business-logic-handler-for-a-merge-article.md).</span><span class="sxs-lookup"><span data-stu-id="c9baf-112">For more information, see [Implement a Business Logic Handler for a Merge Article](implement-a-business-logic-handler-for-a-merge-article.md).</span></span>  
  
3.  <span data-ttu-id="c9baf-113">В среде [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio создайте проект объектов RMO, который программным путем производит синхронный запуск агента слияния.</span><span class="sxs-lookup"><span data-stu-id="c9baf-113">Create a Replication Management Objects (RMO) project in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio that programmatically starts the Merge Agent synchronously.</span></span> <span data-ttu-id="c9baf-114">Дополнительные сведения см. в статье [Synchronize a Pull Subscription](synchronize-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="c9baf-114">For more information, see [Synchronize a Pull Subscription](synchronize-a-pull-subscription.md).</span></span>  
  
4.  <span data-ttu-id="c9baf-115">Установите точку останова в коде обработчика бизнес-логики — в методе, проходящем отладку, или в конструкторе класса.</span><span class="sxs-lookup"><span data-stu-id="c9baf-115">Set a breakpoint in the business logic handler code, either in the method being debugged or in the class constructor.</span></span> <span data-ttu-id="c9baf-116">Дополнительные сведения о методах, которые можно реализовать в обработчике бизнес-логики, см. в разделе о методах <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule> .</span><span class="sxs-lookup"><span data-stu-id="c9baf-116">For more information about the methods that can be implemented in a business logic handler, see the <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule> methods topic.</span></span>  
  
5.  <span data-ttu-id="c9baf-117">Откройте обработчик бизнес-логики в режиме отладки и произведите развертывание сборки и файла отладки (PDB) в папке, заданной на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="c9baf-117">Build the business logic handler in debug mode and deploy the assembly and debugging symbol file (.pdb) in the location registered in step 1.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c9baf-118">Чтобы упростить процесс отладки, создайте решение Visual Studio .NET, содержащее проект обработчика бизнес-логики и проект, осуществляющий синхронизацию подписки.</span><span class="sxs-lookup"><span data-stu-id="c9baf-118">To simplify debugging, create a single Visual Studio .NET solution that contains both the business logic handler project and the project that synchronizes the subscription.</span></span> <span data-ttu-id="c9baf-119">В данном случае проект синхронизации должен быть задан как стартовый, а среда разработки должна быть настроена для развертывания сборки бизнес-логики в папку, которая была задана на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="c9baf-119">In this case, set the synchronization project as the startup project, and configure the build environment to deploy the business logic assembly to the location registered in step 1 during debugging.</span></span>  
  
6.  <span data-ttu-id="c9baf-120">Выполните команды вставки, обновления или удаления в базе данных подписки или публикации.</span><span class="sxs-lookup"><span data-stu-id="c9baf-120">Execute insert, update, or delete commands against the subscription or publication database.</span></span> <span data-ttu-id="c9baf-121">Используемая команда и место выполнения зависят от метода, проходящего отладку.</span><span class="sxs-lookup"><span data-stu-id="c9baf-121">The command and execution location depends on the method being debugged.</span></span>  
  
7.  <span data-ttu-id="c9baf-122">Чтобы синхронизировать подписку, запустите проект в режиме отладки, начиная с шага 3.</span><span class="sxs-lookup"><span data-stu-id="c9baf-122">Start the project from step 3 in debug mode to synchronize the subscription.</span></span>  
  
8.  <span data-ttu-id="c9baf-123">Если не заданы другие точки останова и репликацию проходят нужные команды, выполнение будет остановлено по достижении точки останова в обработчике бизнес-логики.</span><span class="sxs-lookup"><span data-stu-id="c9baf-123">Assuming that no other breakpoints are set and the proper commands are replicated, the execution stops when it reaches the breakpoint in the business logic handler.</span></span>  
  
### <a name="to-debug-a-business-logic-handler-on-a-web-server-using-web-synchronization-or-for-a-sql-server-compact-subscriber"></a><span data-ttu-id="c9baf-124">Отладка обработчика бизнес-логики на веб-сервере в режиме веб-синхронизации либо при использовании подписчика SQL Server Compact</span><span class="sxs-lookup"><span data-stu-id="c9baf-124">To debug a business logic handler on a Web server using Web synchronization, or for a SQL Server Compact Subscriber</span></span>  
  
1.  <span data-ttu-id="c9baf-125">Настройте публикацию и распространение, создайте публикацию по запросу и подписку на нее.</span><span class="sxs-lookup"><span data-stu-id="c9baf-125">Configure publishing and distribution, create a publication, and create a pull subscription to the publication.</span></span> <span data-ttu-id="c9baf-126">Публикация должна поддерживать веб-синхронизации или подписчиков [!INCLUDE[ssEW](../../includes/ssew-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c9baf-126">The publication must support Web synchronization or [!INCLUDE[ssEW](../../includes/ssew-md.md)] Subscribers.</span></span>  
  
2.  <span data-ttu-id="c9baf-127">Создайте и зарегистрируйте обработчик бизнес-логики.</span><span class="sxs-lookup"><span data-stu-id="c9baf-127">Create and register a business logic handler.</span></span> <span data-ttu-id="c9baf-128">Дополнительные сведения см. в статье [Реализация обработчика бизнес-логики для статьи публикации слиянием](implement-a-business-logic-handler-for-a-merge-article.md).</span><span class="sxs-lookup"><span data-stu-id="c9baf-128">For more information, see [Implement a Business Logic Handler for a Merge Article](implement-a-business-logic-handler-for-a-merge-article.md).</span></span>  
  
3.  <span data-ttu-id="c9baf-129">Установите точку останова в коде обработчика бизнес-логики — в методе, проходящем отладку, или в конструкторе класса.</span><span class="sxs-lookup"><span data-stu-id="c9baf-129">Set a breakpoint in the business logic handler code, either in the method being debugged or in the class constructor.</span></span> <span data-ttu-id="c9baf-130">Дополнительные сведения о методах, которые можно реализовать в обработчике бизнес-логики, см. в разделе о методах <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule> .</span><span class="sxs-lookup"><span data-stu-id="c9baf-130">For more information about the methods that can be implemented in a business logic handler, see the <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule> methods topic.</span></span>  
  
4.  <span data-ttu-id="c9baf-131">Откройте обработчик бизнес-логики в режиме отладки и произведите развертывание сборки и файла отладки (PDB) на сервере, заданном на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="c9baf-131">Build the business logic handler in debug mode and deploy the assembly and debugging symbol file (.pdb) at the Web server in the location registered in step 1.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c9baf-132">В том случае, если построение обработчика бизнес-логики завершилось ошибкой по причине того, что сборка занята, необходимо перезагрузить веб-сервер командой `iisreset` из командной строки.</span><span class="sxs-lookup"><span data-stu-id="c9baf-132">If the business logic handler fails to build because the assembly is in use, type the command `iisreset` on the Web server at the command prompt to reset the Web server.</span></span>  
  
5.  <span data-ttu-id="c9baf-133">Произведите синхронизацию подписки в режиме веб-синхронизации.</span><span class="sxs-lookup"><span data-stu-id="c9baf-133">Synchronize the subscription with Web synchronization enabled.</span></span> <span data-ttu-id="c9baf-134">В процессе ее выполнения веб-сервер загрузит зарегистрированную сборку.</span><span class="sxs-lookup"><span data-stu-id="c9baf-134">During synchronization, the Web server loads the registered assembly.</span></span>  
  
6.  <span data-ttu-id="c9baf-135">С помощью отладчика Visual Studio .NET подключитесь к одному из следующих процессов на веб-сервере.</span><span class="sxs-lookup"><span data-stu-id="c9baf-135">Using the Visual Studio .NET debugger, attach to the one of the following processes on the Web server:</span></span>  
  
    -   <span data-ttu-id="c9baf-136">w3wp.exe — Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="c9baf-136">w3wp.exe - Windows Server 2003.</span></span>  
  
    -   <span data-ttu-id="c9baf-137">inetinfo.exe — Windows 2000 и Windows XP.</span><span class="sxs-lookup"><span data-stu-id="c9baf-137">inetinfo.exe - Windows 2000 and Windows XP.</span></span>  
  
7.  <span data-ttu-id="c9baf-138">В окне **Выход** проверьте режим отладки выходного столбца и убедитесь, что символы зарегистрированной сборки были загружены правильно.</span><span class="sxs-lookup"><span data-stu-id="c9baf-138">In the **Output** window, check the debug output to verify that the symbols for the registered assembly loaded properly.</span></span> <span data-ttu-id="c9baf-139">В том случае, если символы не загружены, убедитесь, что PDB-файл на шаге 4 был скопирован правильно, после чего повторите шаг 5.</span><span class="sxs-lookup"><span data-stu-id="c9baf-139">If the symbols were not loaded, ensure that the correct .pdb file was copied in step 4, and repeat step 5.</span></span>  
  
8.  <span data-ttu-id="c9baf-140">Выполните команды вставки, обновления или удаления в базе данных подписки или публикации.</span><span class="sxs-lookup"><span data-stu-id="c9baf-140">Execute insert, update, or delete commands against the subscription or publication database.</span></span> <span data-ttu-id="c9baf-141">Используемая команда и место выполнения зависят от метода, проходящего отладку.</span><span class="sxs-lookup"><span data-stu-id="c9baf-141">The command and execution location depends on the method being debugged.</span></span>  
  
9. <span data-ttu-id="c9baf-142">В среде Visual Studio подключитесь к процессу w3wp.exe.</span><span class="sxs-lookup"><span data-stu-id="c9baf-142">Using the Visual Studio debugger, attach to the w3wp.exe process.</span></span>  
  
10. <span data-ttu-id="c9baf-143">Произведите повторную синхронизацию подписки в режиме веб-синхронизации.</span><span class="sxs-lookup"><span data-stu-id="c9baf-143">Synchronize the subscription again, using Web synchronization.</span></span>  
  
11. <span data-ttu-id="c9baf-144">Если не заданы другие точки останова и репликацию проходят нужные команды, выполнение будет остановлено по достижении точки останова в обработчике бизнес-логики.</span><span class="sxs-lookup"><span data-stu-id="c9baf-144">Assuming that no other breakpoints are set and the proper commands are replicated, the execution stops when it reaches the breakpoint in the business logic handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9baf-145">См. также:</span><span class="sxs-lookup"><span data-stu-id="c9baf-145">See Also</span></span>  
 [<span data-ttu-id="c9baf-146">Реализация обработчика бизнес-логики для статьи публикации слиянием</span><span class="sxs-lookup"><span data-stu-id="c9baf-146">Implement a Business Logic Handler for a Merge Article</span></span>](implement-a-business-logic-handler-for-a-merge-article.md)  
  
  
