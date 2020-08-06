---
title: Настройка хранилища данных управления (среда SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dc.datacollection.wizard_finish.f1
- sql12.swb.dc.datacollection.wizard_maploginuser.f1
- sql12.swb.dc.datacollection.wizard_welcome.f1
- sql12.swb.dc.datacollection.wizard_choosemdw.f1
- sql12.swb.dc.datacollection.wizard_completecfg.f1
- sql12.swb.dc.datacollection.wizard_config.f1
- sql12.swb.dc.datacollection.wizard_createmdw.f1
helpviewer_keywords:
- data warehouse [SQL Server], multiple instances
- data warehouse [SQL Server], configuring
- Configure Management Data Warehouse Wizard
- management data warehouse, configuring
ms.assetid: 23a584f3-c5e1-414c-9afe-73cd7efbda4b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1ef4ddd518343a3076c72ecc41f9b15ddf092dc0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669429"
---
# <a name="configure-the-management-data-warehouse-sql-server-management-studio"></a><span data-ttu-id="e6721-102">Настройка хранилища данных управления (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="e6721-102">Configure the Management Data Warehouse (SQL Server Management Studio)</span></span>
  <span data-ttu-id="e6721-103">В этом разделе описано, как настроить склад данных управления для поддержки хранилища данных управления на одном интерфейсе или на нескольких экземплярах [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , использующих сборщик данных.</span><span class="sxs-lookup"><span data-stu-id="e6721-103">This topic describes how to configure the management data warehouse to support data storage on a single instance or multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are using the data collector.</span></span> <span data-ttu-id="e6721-104">Эти экземпляры могут быть на одном или на разных серверах.</span><span class="sxs-lookup"><span data-stu-id="e6721-104">These instances can be on the same server or on different servers.</span></span> <span data-ttu-id="e6721-105">Здесь также приведены описания пользовательского интерфейса диалогового окна [мастера настройки хранилища данных управления](#Wizard) .</span><span class="sxs-lookup"><span data-stu-id="e6721-105">This topic also provides descriptions of the user interface for the [Configure Data Management Warehouse Wizard](#Wizard) dialog box.</span></span> <span data-ttu-id="e6721-106">Сведения о настройке сборщика данных см. в разделе [Configure Properties of a Data Collector](configure-properties-of-a-data-collector.md).</span><span class="sxs-lookup"><span data-stu-id="e6721-106">For information about configuring a data collector, see [Configure Properties of a Data Collector](configure-properties-of-a-data-collector.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e6721-107">Если агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] настроен для работы под одной из системных учетных записей (Local System, Network Service или Local Service), а хранилище данных управления создано на другом (нежели сборщик данных) экземпляре, то необходимо настроить наборы элементов сбора на использование учетной записи-посредника для передачи данных в хранилище данных управления.</span><span class="sxs-lookup"><span data-stu-id="e6721-107">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent is configured to run using one of the System service accounts (Local System, Network Service, or Local Service), and the management data warehouse is created on a different instance from the data collector, you must configure collection sets to use a proxy for uploading data to the management data warehouse.</span></span>  
  
### <a name="configure-the-management-data-warehouse-on-a-single-instance-or-multiple-instances-of-ssnoversion"></a><span data-ttu-id="e6721-108">Настройте хранилище данных управления на одном экземпляре или нескольких экземплярах [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6721-108">Configure the management data warehouse on a single instance or multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
1.  <span data-ttu-id="e6721-109">Убедитесь, что запущен агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e6721-109">Ensure that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent is running.</span></span>  
  
2.  <span data-ttu-id="e6721-110">В обозревателе объектов раскройте узел **Управление** .</span><span class="sxs-lookup"><span data-stu-id="e6721-110">In Object Explorer, expand the **Management** node.</span></span>  
  
3.  <span data-ttu-id="e6721-111">Щелкните правой кнопкой мыши элемент **Сбор данных**, разверните пункт **Задачи**и выберите **Настройка хранилища управляющих данных**.</span><span class="sxs-lookup"><span data-stu-id="e6721-111">Right-click **Data Collection**, expand **Tasks**, and then click **Configure Management Data Warehouse**.</span></span>  
  
4.  <span data-ttu-id="e6721-112">[Мастер настройки хранилища данных управления](#Wizard) предназначен для создания хранилища данных , настройки имен входа, включения сбора данных и запуска **наборов элементов сбора системных данных**.</span><span class="sxs-lookup"><span data-stu-id="e6721-112">Use the [Configure Management Data Warehouse Wizard](#Wizard) to create a management data warehouse, configure logins, enable data collection, and start the **System Data Collection Sets**.</span></span>  
  
     <span data-ttu-id="e6721-113">Чтобы настроить несколько экземпляров, перейдите к шагу 5.</span><span class="sxs-lookup"><span data-stu-id="e6721-113">To configure multiple instances, continue with step 5.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e6721-114">В развертываниях, в которых сборщик данных устанавливается на нескольких экземплярах [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , использующих одно хранилище данных управления, рекомендуется пользоваться посредниками.</span><span class="sxs-lookup"><span data-stu-id="e6721-114">It is considered best practice to use proxies in deployments where the data collector is installed on multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are using the same management data warehouse.</span></span>  
  
5.  <span data-ttu-id="e6721-115">Откройте среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] на другом экземпляре и выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="e6721-115">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] on another instance and do either of the following:</span></span>  
  
    -   <span data-ttu-id="e6721-116">Используйте мастер настройки хранилища данных управления, чтобы настроить сбор данных для существующего хранилища управляющих данных.</span><span class="sxs-lookup"><span data-stu-id="e6721-116">Use the Configure Management Data Warehouse wizard to configure data collection for the existing management data warehouse.</span></span>  
  
    -   <span data-ttu-id="e6721-117">Щелкните правой кнопкой мыши элемент **Сбор данных**и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="e6721-117">Right-click **Data Collection**, and then click **Properties**.</span></span> <span data-ttu-id="e6721-118">На вкладке **Общие** укажите существующее хранилище данных управления и сервер, на котором оно установлено.</span><span class="sxs-lookup"><span data-stu-id="e6721-118">On the **General** tab, specify the existing management data warehouse and the server that it is installed on.</span></span>  
  
6.  <span data-ttu-id="e6721-119">Повторяйте шаг 5 до тех пор, пока все экземпляры базы данных, в которых используется сборщик данных, не будут настроены для передачи данных в общее хранилище управляющих данных.</span><span class="sxs-lookup"><span data-stu-id="e6721-119">Repeat step 5 until all the database instances that use the data collector are configured to upload data to the shared management data warehouse.</span></span>  
  
####  <a name="configure-management-data-warehouse-wizard"></a><a name="Wizard"></a> <span data-ttu-id="e6721-120">Мастер настройки хранилища управляющих данных</span><span class="sxs-lookup"><span data-stu-id="e6721-120">Configure Management Data Warehouse Wizard</span></span>  
 <span data-ttu-id="e6721-121">**Страница приветствия**</span><span class="sxs-lookup"><span data-stu-id="e6721-121">**Welcome Page**</span></span>  
  
 <span data-ttu-id="e6721-122">Страница «Приветствие» — начальная страница мастера настройки сбора данных.</span><span class="sxs-lookup"><span data-stu-id="e6721-122">The Welcome page is the starting page of the Configure Data Collection Wizard.</span></span> <span data-ttu-id="e6721-123">Отображение этой страницы необязательно.</span><span class="sxs-lookup"><span data-stu-id="e6721-123">Displaying this page is optional.</span></span>  
  
 <span data-ttu-id="e6721-124">**Больше не показывать это окно.**</span><span class="sxs-lookup"><span data-stu-id="e6721-124">**Do not show this starting page again.**</span></span>  
 <span data-ttu-id="e6721-125">Отмените запуск этой страницы при следующих запусках мастера настройки сбора данных.</span><span class="sxs-lookup"><span data-stu-id="e6721-125">Select to suppress this page the next time you launch the Configure Data Collection Wizard.</span></span>  
  
 <span data-ttu-id="e6721-126">**Страница хранения мастера настройки хранилища данных управления**</span><span class="sxs-lookup"><span data-stu-id="e6721-126">**Configure Management Data Warehouse Storage Page**</span></span>  
  
 <span data-ttu-id="e6721-127">На этой странице выберите сервер базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и хранилище данных управления.</span><span class="sxs-lookup"><span data-stu-id="e6721-127">Use this page to select a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database server and management data warehouse.</span></span> <span data-ttu-id="e6721-128">Хранилище управляющих данных — это реляционная база данных, содержащая собранные данные.</span><span class="sxs-lookup"><span data-stu-id="e6721-128">The management data warehouse is a relational database that will store collected data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e6721-129">Необходим соответствующий уровень разрешений, чтобы создать на сервере хранилище управляющих данных.</span><span class="sxs-lookup"><span data-stu-id="e6721-129">You must have the appropriate level of permissions in order to create the management data warehouse on the server.</span></span> <span data-ttu-id="e6721-130">Дополнительные сведения см. в разделе [CREATE DATABASE (SQL Server Transact-SQL)](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e6721-130">For more information, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span> <span data-ttu-id="e6721-131">Необходим также соответствующий уровень разрешений, чтобы создать имена входа для хранилища управляющих данных.</span><span class="sxs-lookup"><span data-stu-id="e6721-131">You also must have the appropriate level of permissions to create logins for management data warehouse roles.</span></span>  
  
 <span data-ttu-id="e6721-132">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="e6721-132">**Server name**</span></span>  
 <span data-ttu-id="e6721-133">Указывает имя сервера, на котором будет размещено хранилище управляющих данных.</span><span class="sxs-lookup"><span data-stu-id="e6721-133">Specifies the name of the server that will host the management data warehouse.</span></span>  
  
 <span data-ttu-id="e6721-134">При настройке хранилища данных управления **Имя сервера** всегда представляет имя локального сервера и не может быть изменено.</span><span class="sxs-lookup"><span data-stu-id="e6721-134">When configuring a management data warehouse, **Server name** is always the name of the local server and cannot be modified.</span></span>  
  
 <span data-ttu-id="e6721-135">**Имя базы данных**</span><span class="sxs-lookup"><span data-stu-id="e6721-135">**Database name**</span></span>  
 <span data-ttu-id="e6721-136">Указывает реляционную базу данных для хранения собранных данных.</span><span class="sxs-lookup"><span data-stu-id="e6721-136">Specifies the relational database that will store collected data.</span></span> <span data-ttu-id="e6721-137">Выберите существующую базу данных из списка или щелкните **Создать** , чтобы создать новую базу данных с использованием диалогового окна **Создание базы данных** .</span><span class="sxs-lookup"><span data-stu-id="e6721-137">Use the list to select an existing database or click **New** to create a new database using the **New Database** dialog.</span></span>  
  
 <span data-ttu-id="e6721-138">Параметр **Создать** доступен только при настройке набора коллекций данных.</span><span class="sxs-lookup"><span data-stu-id="e6721-138">The **New** option is available only when configuring a data collection set</span></span>  
  
 <span data-ttu-id="e6721-139">**Карта имен входа и пользователей страницы**</span><span class="sxs-lookup"><span data-stu-id="e6721-139">**Map Logins and Users Page**</span></span>  
  
 <span data-ttu-id="e6721-140">Используйте эту страницу, чтобы сопоставить имена входа с ролями пользователя базы данных для хранилища данных управления.</span><span class="sxs-lookup"><span data-stu-id="e6721-140">Use this page to map logins to database user roles for the management data warehouse.</span></span>  
  
 <span data-ttu-id="e6721-141">**Пользователи, сопоставленные с этим именем входа**</span><span class="sxs-lookup"><span data-stu-id="e6721-141">**Users mapped to this login**</span></span>  
 <span data-ttu-id="e6721-142">Отображает существующие имена входа на сервере, на котором будет размещено хранилище управляющих данных.</span><span class="sxs-lookup"><span data-stu-id="e6721-142">Displays the existing logins on the server that will host the management data warehouse.</span></span> <span data-ttu-id="e6721-143">Каждая строка содержит редактируемый флажок **Сопоставление** , **Имя входа** и **Тип** имени входа.</span><span class="sxs-lookup"><span data-stu-id="e6721-143">Each row contains an editable **Map** check box, a **Login** name, and a **Type** of login.</span></span>  
  
 <span data-ttu-id="e6721-144">Укажите имя входа, выбрав флажок **Сопоставление** для имени входа.</span><span class="sxs-lookup"><span data-stu-id="e6721-144">Specify a login by selecting the **Map** checkbox for the login.</span></span>  
  
 <span data-ttu-id="e6721-145">**Членство в роли базы данных для:**  *\<data warehouse name>*</span><span class="sxs-lookup"><span data-stu-id="e6721-145">**Database role membership for:**  *\<data warehouse name>*</span></span>  
 <span data-ttu-id="e6721-146">Выберите роль хранилища управляющих данных, с которой сопоставлено имя входа, щелкнув флажок одного или нескольких из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="e6721-146">Select the management data warehouse role that the login is mapped to by clicking the checkbox by one or more of the following options:</span></span>  
  
-   <span data-ttu-id="e6721-147">**mdw_admin**</span><span class="sxs-lookup"><span data-stu-id="e6721-147">**mdw_admin**</span></span>  
  
-   <span data-ttu-id="e6721-148">**mdw_reader**</span><span class="sxs-lookup"><span data-stu-id="e6721-148">**mdw_reader**</span></span>  
  
-   <span data-ttu-id="e6721-149">**mdw_writer**</span><span class="sxs-lookup"><span data-stu-id="e6721-149">**mdw_writer**</span></span>  
  
 <span data-ttu-id="e6721-150">**Создать имя входа**</span><span class="sxs-lookup"><span data-stu-id="e6721-150">**New Login**</span></span>  
 <span data-ttu-id="e6721-151">Откройте диалоговое окно **Создание имени входа** и создайте имя входа для хранилища данных управления.</span><span class="sxs-lookup"><span data-stu-id="e6721-151">Open the **Login - New** dialog box and create a new login for the management data warehouse.</span></span>  
  
 <span data-ttu-id="e6721-152">**Страница завершения мастера**</span><span class="sxs-lookup"><span data-stu-id="e6721-152">**Complete the Wizard Page**</span></span>  
  
 <span data-ttu-id="e6721-153">Используйте эту страницу, чтобы проверить или завершить настройку сбора данных.</span><span class="sxs-lookup"><span data-stu-id="e6721-153">Use this page to verify and complete data collection configuration.</span></span> <span data-ttu-id="e6721-154">Дерево, отображаемое в окне просмотра, показывает применяемые конфигурации и действия, предпринимаемые после нажатия кнопки **Готово**.</span><span class="sxs-lookup"><span data-stu-id="e6721-154">The tree displayed in the viewing window shows what configurations will applied as well as what actions will take place when you click **Finish**.</span></span>  
  
 <span data-ttu-id="e6721-155">**Страница отображения хода настройки мастера сбора данных**</span><span class="sxs-lookup"><span data-stu-id="e6721-155">**Configure Data Collection Wizard Progress Page**</span></span>  
  
 <span data-ttu-id="e6721-156">Эта страница используется для просмотра результатов каждого шага настройки.</span><span class="sxs-lookup"><span data-stu-id="e6721-156">Use this page to view the results of each configuration step.</span></span>  
  
 <span data-ttu-id="e6721-157">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="e6721-157">**Details**</span></span>  
 <span data-ttu-id="e6721-158">Отображает каждый шаг настройки как строку в сетке **Сведения** .</span><span class="sxs-lookup"><span data-stu-id="e6721-158">Displays each configuration step as a row in the **Details** grid.</span></span> <span data-ttu-id="e6721-159">Каждая строка содержит столбец **Действие** , который описывает шаг, и столбец **Состояние** , который отображает успешное выполнение или ошибку шага.</span><span class="sxs-lookup"><span data-stu-id="e6721-159">Each row contains an **Action** column that describes the step, and a **Status** column that indicates the success or failure of the step.</span></span> <span data-ttu-id="e6721-160">При возникновении ошибки сообщение появляется в столбце **Сообщение** .</span><span class="sxs-lookup"><span data-stu-id="e6721-160">If there is an error, a message appears in the **Message** column.</span></span>  
  
 <span data-ttu-id="e6721-161">**Остановить**</span><span class="sxs-lookup"><span data-stu-id="e6721-161">**Stop**</span></span>  
 <span data-ttu-id="e6721-162">Останавливает работу мастера.</span><span class="sxs-lookup"><span data-stu-id="e6721-162">Stop wizard processing.</span></span>  
  
 <span data-ttu-id="e6721-163">**Отчет**</span><span class="sxs-lookup"><span data-stu-id="e6721-163">**Report**</span></span>  
 <span data-ttu-id="e6721-164">Просмотр отчета о конфигурации сбора данных.</span><span class="sxs-lookup"><span data-stu-id="e6721-164">View a report of the data collection configuration.</span></span> <span data-ttu-id="e6721-165">Предоставляются следующие параметры отчета.</span><span class="sxs-lookup"><span data-stu-id="e6721-165">The following report options are provided:</span></span>  
  
-   <span data-ttu-id="e6721-166">Просмотр отчета</span><span class="sxs-lookup"><span data-stu-id="e6721-166">View Report</span></span>  
  
-   <span data-ttu-id="e6721-167">Сохранить отчет в файл</span><span class="sxs-lookup"><span data-stu-id="e6721-167">Save Report to File</span></span>  
  
-   <span data-ttu-id="e6721-168">Копировать отчет в буфер обмена</span><span class="sxs-lookup"><span data-stu-id="e6721-168">Copy Report to Clipboard</span></span>  
  
-   <span data-ttu-id="e6721-169">Отправить отчет по электронной почте</span><span class="sxs-lookup"><span data-stu-id="e6721-169">Send Report as E-mail</span></span>  
  
 <span data-ttu-id="e6721-170">**Закрыть**</span><span class="sxs-lookup"><span data-stu-id="e6721-170">**Close**</span></span>  
 <span data-ttu-id="e6721-171">Завершение работы мастера.</span><span class="sxs-lookup"><span data-stu-id="e6721-171">Close the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6721-172">См. также:</span><span class="sxs-lookup"><span data-stu-id="e6721-172">See Also</span></span>  
 <span data-ttu-id="e6721-173">[sp_syscollector_enable_collector (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-syscollector-enable-collector-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e6721-173">[sp_syscollector_enable_collector &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syscollector-enable-collector-transact-sql) </span></span>  
 <span data-ttu-id="e6721-174">[sp_syscollector_disable_collector (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-syscollector-disable-collector-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e6721-174">[sp_syscollector_disable_collector &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syscollector-disable-collector-transact-sql) </span></span>  
 <span data-ttu-id="e6721-175">[Сбор данных](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="e6721-175">[Data Collection](data-collection.md) </span></span>  
 [<span data-ttu-id="e6721-176">Управление сбором данных</span><span class="sxs-lookup"><span data-stu-id="e6721-176">Manage Data Collection</span></span>](manage-data-collection.md)  
  
  
