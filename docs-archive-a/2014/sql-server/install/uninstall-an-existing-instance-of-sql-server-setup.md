---
title: Удаление существующего экземпляра SQL Server (программа установки) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- removing instances of SQL Server
- uninstalling instances of SQL Server
- removing SQL Server
- instances of SQL Server, uninstalling
- uninstalling SQL Server
ms.assetid: 3c64b29d-61d7-4b86-961c-0de62261c6a1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 51d426a12a2f7f1b7bedbfb7770c4d9cb369f12b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659153"
---
# <a name="uninstall-an-existing-instance-of-sql-server-setup"></a><span data-ttu-id="caa28-102">Удаление существующего экземпляра SQL Server (программа установки)</span><span class="sxs-lookup"><span data-stu-id="caa28-102">Uninstall an Existing Instance of SQL Server (Setup)</span></span>
  <span data-ttu-id="caa28-103">В данной статье описан процесс удаления изолированного экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="caa28-103">This article describes how to uninstall a stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="caa28-104">Шаги, перечисленные в этом разделе, помогут подготовить систему для повторной установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="caa28-104">By following the steps in this topic, you also prepare the system so that you can reinstall [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="caa28-105">Удаление экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]должно производиться локальным администратором, имеющим разрешение на вход в систему в качестве службы.</span><span class="sxs-lookup"><span data-stu-id="caa28-105">To uninstall an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must be a local administrator with permission to log on as a service.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="caa28-106">Для удаления отказоустойчивого кластера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] используется функция удаления узла, предоставляемая программой установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которая удаляет каждый узел по отдельности.</span><span class="sxs-lookup"><span data-stu-id="caa28-106">To uninstall a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, use the Remove Node functionality provided by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup to remove each node individually.</span></span> <span data-ttu-id="caa28-107">Дополнительные сведения см. на странице [Добавление и удаление узлов в отказоустойчивом кластере SQL Server (настройка)](../failover-clusters/install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md).</span><span class="sxs-lookup"><span data-stu-id="caa28-107">For more information, see [Add or Remove Nodes in a SQL Server Failover Cluster &#40;Setup&#41;](../failover-clusters/install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md)</span></span>  
  
 <span data-ttu-id="caa28-108">Перед удалением [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с помощью данной процедуры следует учесть следующие обстоятельства.</span><span class="sxs-lookup"><span data-stu-id="caa28-108">Consider the following important information before you uninstall [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="caa28-109">Прежде чем производить удаление компонентов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с компьютера, на котором установлен минимально необходимый объем оперативной памяти, необходимо удостовериться, что файл подкачки имеет достаточный размер.</span><span class="sxs-lookup"><span data-stu-id="caa28-109">Before you remove [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components from a computer that has the minimum required amount of physical memory, make sure that the page file size is sufficient.</span></span> <span data-ttu-id="caa28-110">Он должен вдвое превышать размер физической памяти.</span><span class="sxs-lookup"><span data-stu-id="caa28-110">The page file size must be equal to two times the amount of physical memory.</span></span> <span data-ttu-id="caa28-111">Нехватка виртуальной памяти может привести к неполному удалению [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="caa28-111">Insufficient virtual memory can cause an incomplete removal of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="caa28-112">Если существует несколько экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], браузер [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] будет автоматически удален при удалении последнего экземпляра [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="caa28-112">If you have multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser uninstalls automatically when the last instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] is uninstalled.</span></span>  
  
     <span data-ttu-id="caa28-113">Если необходимо удалить все компоненты [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], необходимо вручную удалить браузер [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] из списка **Программы и компоненты** в оснастке **Панель управления**.</span><span class="sxs-lookup"><span data-stu-id="caa28-113">If you want to uninstall all components of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you must uninstall the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser component manually from **Programs and Features** in **Control Panel**.</span></span>  
  
### <a name="before-you-uninstall"></a><span data-ttu-id="caa28-114">Перед началом удаления</span><span class="sxs-lookup"><span data-stu-id="caa28-114">Before You Uninstall</span></span>  
  
1.  <span data-ttu-id="caa28-115">**Создайте резервную копию данных.**</span><span class="sxs-lookup"><span data-stu-id="caa28-115">**Back up your data.**</span></span> <span data-ttu-id="caa28-116">Хотя это не является обязательным действием, могут быть базы данных, которые нужно сохранить в текущем состоянии.</span><span class="sxs-lookup"><span data-stu-id="caa28-116">Although this is not a required step, you might have databases that you want to save in their present state.</span></span> <span data-ttu-id="caa28-117">Кроме того, может потребоваться сохранить изменения, внесенные в системные базы данных.</span><span class="sxs-lookup"><span data-stu-id="caa28-117">You might also want to save changes that were made to the system databases.</span></span> <span data-ttu-id="caa28-118">В этих случаях перед удалением [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]необходимо создать резервную копию данных.</span><span class="sxs-lookup"><span data-stu-id="caa28-118">If either situation is true, make sure that back up the data before you uninstall [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="caa28-119">В качестве альтернативного решения можно сохранить копию файлов данных и файлов журналов в папке с именем, отличным от MSSQL.</span><span class="sxs-lookup"><span data-stu-id="caa28-119">Alternatively, save a copy of all the data and log files in a folder other than the MSSQL folder.</span></span> <span data-ttu-id="caa28-120">Папка MSSQL будет удалена в ходе удаления SQL Server.</span><span class="sxs-lookup"><span data-stu-id="caa28-120">The MSSQL folder is deleted during uninstallation.</span></span>  
  
     <span data-ttu-id="caa28-121">Необходимо сохранить следующие файлы баз данных.</span><span class="sxs-lookup"><span data-stu-id="caa28-121">The files that you must save include the following database files:</span></span>  
  
    -   <span data-ttu-id="caa28-122">Master.mdf</span><span class="sxs-lookup"><span data-stu-id="caa28-122">Master.mdf</span></span>  
  
    -   <span data-ttu-id="caa28-123">Mastlog.ldf</span><span class="sxs-lookup"><span data-stu-id="caa28-123">Mastlog.ldf</span></span>  
  
    -   <span data-ttu-id="caa28-124">Model.mdf</span><span class="sxs-lookup"><span data-stu-id="caa28-124">Model.mdf</span></span>  
  
    -   <span data-ttu-id="caa28-125">Modellog.ldf</span><span class="sxs-lookup"><span data-stu-id="caa28-125">Modellog.ldf</span></span>  
  
    -   <span data-ttu-id="caa28-126">Msdbdata.mdf</span><span class="sxs-lookup"><span data-stu-id="caa28-126">Msdbdata.mdf</span></span>  
  
    -   <span data-ttu-id="caa28-127">Msdblog.ldf</span><span class="sxs-lookup"><span data-stu-id="caa28-127">Msdblog.ldf</span></span>  
  
    -   <span data-ttu-id="caa28-128">Mssqlsystemresource.mdf</span><span class="sxs-lookup"><span data-stu-id="caa28-128">Mssqlsystemresource.mdf</span></span>  
  
    -   <span data-ttu-id="caa28-129">Mssqlsustemresource.ldf</span><span class="sxs-lookup"><span data-stu-id="caa28-129">Mssqlsustemresource.ldf</span></span>  
  
    -   <span data-ttu-id="caa28-130">Tempdb.mdf</span><span class="sxs-lookup"><span data-stu-id="caa28-130">Tempdb.mdf</span></span>  
  
    -   <span data-ttu-id="caa28-131">Templog.ldf</span><span class="sxs-lookup"><span data-stu-id="caa28-131">Templog.ldf</span></span>  
  
    -   <span data-ttu-id="caa28-132">`ReportServer[$InstanceName]`(Это [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] база данных по умолчанию.)</span><span class="sxs-lookup"><span data-stu-id="caa28-132">`ReportServer[$InstanceName]` (Thisis the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] default database.)</span></span>  
  
    -   <span data-ttu-id="caa28-133">ReportServer[$ИмяЭкземпляра]TempDB (временная база данных по умолчанию для служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="caa28-133">ReportServer[$InstanceName]TempDB (This is the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] default temporary database.)</span></span>  
  
2.  <span data-ttu-id="caa28-134">**Удалите локальные группы безопасности.**</span><span class="sxs-lookup"><span data-stu-id="caa28-134">**Delete the local security groups.**</span></span> <span data-ttu-id="caa28-135">Перед удалением [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]удалите локальные группы безопасности для компонентов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="caa28-135">Before you uninstall [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], delete the local security groups for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components.</span></span>  
  
3.  <span data-ttu-id="caa28-136">**Остановите все**  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **службы**.</span><span class="sxs-lookup"><span data-stu-id="caa28-136">**Stop all**  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **services.**</span></span> <span data-ttu-id="caa28-137">Перед удалением компонентов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] рекомендуется остановить все службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="caa28-137">We recommend that you stop all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services before you uninstall [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components.</span></span> <span data-ttu-id="caa28-138">Наличие активных соединений может помешать удалению компонентов.</span><span class="sxs-lookup"><span data-stu-id="caa28-138">Active connections can prevent successful uninstallation.</span></span>  
  
4.  <span data-ttu-id="caa28-139">**Выбор учетной записи с необходимыми разрешениями.**</span><span class="sxs-lookup"><span data-stu-id="caa28-139">**Use an account that has the appropriate permissions.**</span></span> <span data-ttu-id="caa28-140">Выполните вход на сервер с учетной записью службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или с учетной записью, обладающей аналогичным набором разрешений.</span><span class="sxs-lookup"><span data-stu-id="caa28-140">Log on to the server by using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account or by using an account that has equivalent permissions.</span></span> <span data-ttu-id="caa28-141">Например, можно войти на сервер с учетной записью, входящей в локальную группу администраторов.</span><span class="sxs-lookup"><span data-stu-id="caa28-141">For example, you can log on to the server by using an account that is a member of the local Administrators group.</span></span>  
  
### <a name="to-uninstall-an-instance-of-ssnoversion"></a><span data-ttu-id="caa28-142">To Uninstall an Instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="caa28-142">To Uninstall an Instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
1.  <span data-ttu-id="caa28-143">Чтобы начать процесс удаления, перейдите на страницу **Панель управления** , а затем на страницу **Программы и компоненты**.</span><span class="sxs-lookup"><span data-stu-id="caa28-143">To begin the uninstall process, go to **Control Panel** and then **Programs and Features**.</span></span>  
  
2.  <span data-ttu-id="caa28-144">Щелкните правой кнопкой мыши **[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]** и выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="caa28-144">Right click **[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]** and select **Uninstall**.</span></span> <span data-ttu-id="caa28-145">Нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="caa28-145">Then click **Remove**.</span></span> <span data-ttu-id="caa28-146">Будет запущен мастер установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="caa28-146">This starts the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard.</span></span>  
  
     <span data-ttu-id="caa28-147">Для проверки конфигурации компьютера будут выполнены правила поддержки установки.</span><span class="sxs-lookup"><span data-stu-id="caa28-147">Setup Support Rules runs to verify your computer configuration.</span></span> <span data-ttu-id="caa28-148">Чтобы продолжить, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="caa28-148">To continue, click **Next**.</span></span>  
  
3.  <span data-ttu-id="caa28-149">На странице «Выбор экземпляра» воспользуйтесь раскрывающимся списком, чтобы указать удаляемый экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , или укажите параметр для удаления только общих компонентов и средств управления [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="caa28-149">On the Select Instance page, use the drop-down box to specify an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to remove, or specify the option to remove only the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] shared features and management tools.</span></span> <span data-ttu-id="caa28-150">Чтобы продолжить, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="caa28-150">To continue, click **Next**.</span></span>  
  
4.  <span data-ttu-id="caa28-151">На странице «Выбор компонентов» укажите компоненты, которые нужно удалить из указанного экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="caa28-151">On the Select Features page, specify the features to remove from the specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="caa28-152">Для проверки успешного завершения операции запустятся правила удаления.</span><span class="sxs-lookup"><span data-stu-id="caa28-152">Removal rules runs to verify that the operation can complete successfully.</span></span>  
  
5.  <span data-ttu-id="caa28-153">На странице **Все готово** для удаления просмотрите список компонентов и функций, подлежащих удалению.</span><span class="sxs-lookup"><span data-stu-id="caa28-153">On the **Ready to Remove** page, review the list of components and features that will be uninstalled.</span></span> <span data-ttu-id="caa28-154">Нажмите кнопку **Удалить** , чтобы начать удаление</span><span class="sxs-lookup"><span data-stu-id="caa28-154">Click **Remove** to begin uninstalling</span></span>  
  
6.  <span data-ttu-id="caa28-155">Сразу после удаления последнего экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] другие программы, связанные с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , по-прежнему будут отображаться в списке программ на странице **Программы и компоненты**.</span><span class="sxs-lookup"><span data-stu-id="caa28-155">Immediately after you uninstall the last [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance, the other programs associated with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will still be visible in the list of programs in **Programs and Features**.</span></span> <span data-ttu-id="caa28-156">Однако, если закрыть страницу **Установка и удаление программ**, при последующем открытии **Установка и удаление программ**список будет обновлен и будет содержать только установленные программы.</span><span class="sxs-lookup"><span data-stu-id="caa28-156">However, if you close **Programs and Features**, the next time you open **Programs and Features**, it will refresh the list of programs, to show only the ones that are actually still installed.</span></span>  
  
### <a name="if-the-uninstallation-fails"></a><span data-ttu-id="caa28-157">Если удаление не было выполнено успешно</span><span class="sxs-lookup"><span data-stu-id="caa28-157">If the Uninstallation Fails</span></span>  
  
1.  <span data-ttu-id="caa28-158">Если процесс удаления не завершился успешно, попробуйте исправить проблему, вызвавшую сбой.</span><span class="sxs-lookup"><span data-stu-id="caa28-158">If the uninstallation process does not complete successfully, attempt to fix the problem that caused the uninstallation to fail.</span></span> <span data-ttu-id="caa28-159">В следующих статьях приводятся сведения, которые помогут понять причину неудавшегося удаления.</span><span class="sxs-lookup"><span data-stu-id="caa28-159">The following articles can help you understand the cause of the failed uninstallation:</span></span>  
  
    -   [<span data-ttu-id="caa28-160">Как определить проблемы установки SQL Server 2008, используя файлы журнала установки</span><span class="sxs-lookup"><span data-stu-id="caa28-160">How to identify SQL Server 2008 setup issues in the setup log files</span></span>](https://support.microsoft.com/kb/955396/en-us)  
  
    -   [<span data-ttu-id="caa28-161">Просмотр и чтение файлов журналов программы установки SQL Server</span><span class="sxs-lookup"><span data-stu-id="caa28-161">View and Read SQL Server Setup Log Files</span></span>](../../database-engine/install-windows/view-and-read-sql-server-setup-log-files.md)  
  
2.  <span data-ttu-id="caa28-162">Если вам не удалось исправить проблему, вы можете связаться с поддержкой [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="caa28-162">If you are unable to fix the cause of the uninstallation failure, you can contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Support.</span></span> <span data-ttu-id="caa28-163">В некоторых случаях, например при неумышленном удалении важных файлов, перед переустановкой на компьютере [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] может потребоваться переустановка операционной системы.</span><span class="sxs-lookup"><span data-stu-id="caa28-163">In some cases, such as unintentional deletion of important files, reinstalling the operating system may be required before reinstalling [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on the computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caa28-164">См. также:</span><span class="sxs-lookup"><span data-stu-id="caa28-164">See Also</span></span>  
 [<span data-ttu-id="caa28-165">Просмотр и чтение файлов журналов программы установки SQL Server</span><span class="sxs-lookup"><span data-stu-id="caa28-165">View and Read SQL Server Setup Log Files</span></span>](../../database-engine/install-windows/view-and-read-sql-server-setup-log-files.md)  
  
  
