---
title: Регистрация базы данных в качестве приложения уровня данных | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.registerdacwizard.registerdac.f1
- sql12.swb.registerdacwizard.summary.f1
- sql12.swb.registerdacwizard.introduction.f1
- sql12.swb.registerdacwizard.setproperties.f1
helpviewer_keywords:
- wizard [DAC], register
- How to [DAC], register
- register DAC
- data-tier application [SQL Server], register
ms.assetid: 08e52aa6-12f3-41dd-a793-14b99a083fd5
author: stevestein
ms.author: sstein
ms.openlocfilehash: c4e8061362d013dbfbd6cbaba47d0f2cb4d8e83b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668899"
---
# <a name="register-a-database-as-a-dac"></a><span data-ttu-id="52baf-102">Регистрация базы данных в качестве приложения уровня данных</span><span class="sxs-lookup"><span data-stu-id="52baf-102">Register a Database As a DAC</span></span>
  <span data-ttu-id="52baf-103">Используйте **Мастер регистрации приложений уровня данных** или сценарий Windows PowerShell, чтобы создать определение приложения уровня данных (DAC), которое описывает объекты в существующей базе данных, и зарегистрируйте определение DAC в `msdb` системной базе данных (**master** в [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="52baf-103">Use either the **Register Data-tier Application Wizard** or a Windows PowerShell script to build a data-tier application (DAC) definition that describes the objects in an existing database, and register the DAC definition in the `msdb` system database (**master** in [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)]).</span></span>  
  
-   <span data-ttu-id="52baf-104">**Перед началом работы**  [ограничения](#LimitationsRestrictions), [разрешения](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="52baf-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="52baf-105">**Обновление приложения уровня данных с использованием:**  [Мастер регистрации приложения уровня данных](#UsingRegisterDACWizard), [PowerShell](#RegisterDACPowerShell)</span><span class="sxs-lookup"><span data-stu-id="52baf-105">**To upgrade a DAC, using:**  [The Register Data-tier Application Wizard](#UsingRegisterDACWizard), [PowerShell](#RegisterDACPowerShell)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="52baf-106">Перед началом</span><span class="sxs-lookup"><span data-stu-id="52baf-106">Before You Begin</span></span>  
 <span data-ttu-id="52baf-107">Процесс регистрации создает определение DAC, которое определяет объекты в базе данных.</span><span class="sxs-lookup"><span data-stu-id="52baf-107">The registration process creates a DAC definition that defines the objects in the database.</span></span> <span data-ttu-id="52baf-108">Сочетание определения DAC и базы данных образует экземпляр DAC.</span><span class="sxs-lookup"><span data-stu-id="52baf-108">The combination of the DAC definition and the database form a DAC instance.</span></span> <span data-ttu-id="52baf-109">Если база данных регистрируется как DAC на управляемом экземпляре компонента Database Engine, зарегистрированный компонент DAC будет включен в служебную программу SQL Server при следующей передаче набора элементов сбора программы с экземпляра в точку управления служебной программой.</span><span class="sxs-lookup"><span data-stu-id="52baf-109">If you register a database as a DAC on a managed instance of the Database Engine, the registered DAC will be incorporated into the SQL Server Utility the next time the utility collection set is sent from the instance to the Utility Control Point.</span></span> <span data-ttu-id="52baf-110">После этого приложение уровня данных появится в узле **Развернутые приложения уровня данных** в окне [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] **Проводник служебной программы**, а также на странице сведений **Развернутые приложения уровня данных**.</span><span class="sxs-lookup"><span data-stu-id="52baf-110">The DAC will then be present in the **Deployed Data-tier Applications** node of the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] **Utility Explorer** and reported in the **Deployed Data-tier Applications** details page.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="52baf-111">Ограничения</span><span class="sxs-lookup"><span data-stu-id="52baf-111">Limitations and Restrictions</span></span>  
 <span data-ttu-id="52baf-112">Регистрация приложения уровня данных может быть выполнена только для базы данных [!INCLUDE[ssSDS](../../includes/sssds-md.md)]или [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] с пакетом обновления 4 (SP4) или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="52baf-112">DAC registration can only be performed on a database in [!INCLUDE[ssSDS](../../includes/sssds-md.md)], or [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) or later.</span></span> <span data-ttu-id="52baf-113">Регистрация DAC не может быть выполнена, если приложение DAC уже зарегистрировано для базы данных.</span><span class="sxs-lookup"><span data-stu-id="52baf-113">DAC registration cannot be performed if a DAC is already registered for the database.</span></span> <span data-ttu-id="52baf-114">Например, если база данных создана при помощи развертывания DAC, нельзя запустить **Мастер регистрации приложения уровня данных**.</span><span class="sxs-lookup"><span data-stu-id="52baf-114">For example, if the database was created by deploying a DAC, you cannot run the **Register Data-tier Application Wizard**.</span></span>  
  
 <span data-ttu-id="52baf-115">Приложение DAC нельзя зарегистрировать, если база данных содержит объекты, которые не поддерживаются в DAC, или содержат пользователей.</span><span class="sxs-lookup"><span data-stu-id="52baf-115">You cannot register a DAC if the database has objects that are not supported in a DAC, or contained users.</span></span> <span data-ttu-id="52baf-116">Дополнительные сведения о типах объектов, поддерживаемых в DAC, см. в разделе [DAC Support For SQL Server Objects and Versions](dac-support-for-sql-server-objects-and-versions.md).</span><span class="sxs-lookup"><span data-stu-id="52baf-116">For more information about the types of objects supported in a DAC, see [DAC Support For SQL Server Objects and Versions](dac-support-for-sql-server-objects-and-versions.md).</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="52baf-117">Permissions</span><span class="sxs-lookup"><span data-stu-id="52baf-117">Permissions</span></span>  
 <span data-ttu-id="52baf-118">Для регистрации приложения уровня данных в экземпляре компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] требуются по меньшей мере разрешения ALTER ANY LOGIN, разрешения области базы данных VIEW DEFINITION, разрешения SELECT на представление каталога **sys.sql_expression_dependencies**и членство в предопределенной роли сервера **dbcreator** .</span><span class="sxs-lookup"><span data-stu-id="52baf-118">Registering a DAC in an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] requires at least ALTER ANY LOGIN and database scope VIEW DEFINITION permissions, SELECT permissions on **sys.sql_expression_dependencies**, and membership in the **dbcreator** fixed server role.</span></span> <span data-ttu-id="52baf-119">Члены предопределенной роли сервера **sysadmin** и встроенной учетной записи системного администратора SQL Server (с именем **sa** ) также могут регистрировать приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="52baf-119">Members of the **sysadmin** fixed server role or the built-in SQL Server system administrator account named **sa** can also register a DAC.</span></span> <span data-ttu-id="52baf-120">Для регистрации приложения уровня данных, не содержащего имен входа, в [!INCLUDE[ssSDS](../../includes/sssds-md.md)] требуется членство в ролях **dbmanager** или **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="52baf-120">Registering a DAC that does not contain logins in [!INCLUDE[ssSDS](../../includes/sssds-md.md)] requires membership in the **dbmanager** or **serveradmin** roles.</span></span> <span data-ttu-id="52baf-121">Для регистрации приложения уровня данных, содержащего имена входа, в [!INCLUDE[ssSDS](../../includes/sssds-md.md)] требуется членство в ролях **loginmanager** или **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="52baf-121">Registering a DAC that contains logins in [!INCLUDE[ssSDS](../../includes/sssds-md.md)] requires membership in the **loginmanager** or **serveradmin** roles.</span></span>  
  
##  <a name="using-the-register-data-tier-application-wizard"></a><a name="UsingRegisterDACWizard"></a> <span data-ttu-id="52baf-122">Использование мастера регистрации приложений уровня данных</span><span class="sxs-lookup"><span data-stu-id="52baf-122">Using the Register Data-tier Application Wizard</span></span>  
 <span data-ttu-id="52baf-123">**Регистрация приложения DAC с помощью мастера**</span><span class="sxs-lookup"><span data-stu-id="52baf-123">**To Register a DAC Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="52baf-124">В **обозревателе объектов**разверните узел экземпляра, содержащего базу данных, которую нужно зарегистрировать как DAC.</span><span class="sxs-lookup"><span data-stu-id="52baf-124">In **Object Explorer**, expand the node for the instance containing the database to be registered as a DAC.</span></span>  
  
2.  <span data-ttu-id="52baf-125">Разверните узел **Базы данных** .</span><span class="sxs-lookup"><span data-stu-id="52baf-125">Expand the **Databases** node.</span></span>  
  
3.  <span data-ttu-id="52baf-126">Щелкните правой кнопкой мыши базу данных, подлежащую регистрации, выберите пункт **Задачи**, затем пункт **Регистрация приложения уровня данных…**</span><span class="sxs-lookup"><span data-stu-id="52baf-126">Right-click the database to be registered, point to **Tasks**, and then select **Register As Data-tier Application...**</span></span>  
  
4.  <span data-ttu-id="52baf-127">Выполните шаги в диалоговых окнах мастера.</span><span class="sxs-lookup"><span data-stu-id="52baf-127">Complete the wizard dialogs:</span></span>  
  
    1.  [<span data-ttu-id="52baf-128">Вводная страница</span><span class="sxs-lookup"><span data-stu-id="52baf-128">Introduction Page</span></span>](#Introduction)  
  
    2.  [<span data-ttu-id="52baf-129">Страница «Задание свойств»</span><span class="sxs-lookup"><span data-stu-id="52baf-129">Set Properties Page</span></span>](#Set_properties)  
  
    3.  [<span data-ttu-id="52baf-130">Страница «Проверка и сводка»</span><span class="sxs-lookup"><span data-stu-id="52baf-130">Validation and Summary Page</span></span>](#Summary)  
  
    4.  [<span data-ttu-id="52baf-131">Страница «Регистрация DAC»</span><span class="sxs-lookup"><span data-stu-id="52baf-131">Register DAC Page</span></span>](#Register)  
  
##  <a name="introduction-page"></a><a name="Introduction"></a> <span data-ttu-id="52baf-132">Вводная страница</span><span class="sxs-lookup"><span data-stu-id="52baf-132">Introduction Page</span></span>  
 <span data-ttu-id="52baf-133">На этой странице описаны шаги регистрации приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="52baf-133">This page describes the steps for registering a data-tier application.</span></span>  
  
 <span data-ttu-id="52baf-134">**Больше не показывать эту страницу.**</span><span class="sxs-lookup"><span data-stu-id="52baf-134">**Do not show this page again.**</span></span> <span data-ttu-id="52baf-135">— щелкните этот флажок, чтобы предотвратить отображение этой страницы в будущем.</span><span class="sxs-lookup"><span data-stu-id="52baf-135">- Click the check box to stop the page from being displayed in the future.</span></span>  
  
 <span data-ttu-id="52baf-136">**Далее >** — переход к странице **Задание свойств**.</span><span class="sxs-lookup"><span data-stu-id="52baf-136">**Next >** - Proceeds to the **Set Properties** page.</span></span>  
  
 <span data-ttu-id="52baf-137">**Отмена** — работа мастера завершается без регистрации DAC.</span><span class="sxs-lookup"><span data-stu-id="52baf-137">**Cancel** - Terminates the wizard without registering a DAC.</span></span>  
  
##  <a name="set-properties-page"></a><a name="Set_properties"></a> <span data-ttu-id="52baf-138">Страница «Задание свойств»</span><span class="sxs-lookup"><span data-stu-id="52baf-138">Set Properties Page</span></span>  
 <span data-ttu-id="52baf-139">Используйте эту страницу, чтобы указать свойства уровня DAC, например имя и версию приложения.</span><span class="sxs-lookup"><span data-stu-id="52baf-139">Use this page to specify DAC-level properties such as the application name and version.</span></span>  
  
 <span data-ttu-id="52baf-140">**Имя приложения.**</span><span class="sxs-lookup"><span data-stu-id="52baf-140">**Application name.**</span></span> <span data-ttu-id="52baf-141">— Строка, указывающая имя, которое используется для идентификации определения DAC. В этом поле приводится имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="52baf-141">- A string that specifies the name used to identify the DAC definition, the field is been populated with the database name.</span></span>  
  
 <span data-ttu-id="52baf-142">**Версия.**</span><span class="sxs-lookup"><span data-stu-id="52baf-142">**Version.**</span></span> <span data-ttu-id="52baf-143">— числовое значение, определяющее версию DAC.</span><span class="sxs-lookup"><span data-stu-id="52baf-143">- A numeric value that identifies the version of the DAC.</span></span> <span data-ttu-id="52baf-144">Версия DAC используется в среде Visual Studio для определения версии DAC, над которой работают разработчики.</span><span class="sxs-lookup"><span data-stu-id="52baf-144">The DAC version is used in Visual Studio to identify the version of the DAC that developers are working on.</span></span> <span data-ttu-id="52baf-145">При развертывании DAC версия хранится в `msdb` базе данных и затем может быть просмотрена в узле **приложения уровня данных** в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="52baf-145">When deploying a DAC, the version is stored in the `msdb` database and can later be viewed under the **Data-tier Applications** node in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="52baf-146">**Описание.**</span><span class="sxs-lookup"><span data-stu-id="52baf-146">**Description.**</span></span> <span data-ttu-id="52baf-147">— необязательно.</span><span class="sxs-lookup"><span data-stu-id="52baf-147">- Optional.</span></span> <span data-ttu-id="52baf-148">Текст, поясняющий назначение DAC.</span><span class="sxs-lookup"><span data-stu-id="52baf-148">Text that explains the purpose of the DAC.</span></span> <span data-ttu-id="52baf-149">При развертывании DAC описание сохраняется в `msdb` базе данных и затем может быть просмотрено в узле **приложения уровня данных** в среде [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="52baf-149">When deploying a DAC, the description is stored in the `msdb` database and can later be viewed under the **Data-tier Applications** node in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="52baf-150">\*\* \< Назад\*\* — возврат на страницу **Введение** .</span><span class="sxs-lookup"><span data-stu-id="52baf-150">**\< Previous** - Returns you to the **Introduction** page.</span></span>  
  
 <span data-ttu-id="52baf-151">**Далее >** — выполняется проверка возможности сборки DAC из объектов базы данных, результаты отображаются на странице **Проверка и сводка**.</span><span class="sxs-lookup"><span data-stu-id="52baf-151">**Next >** - Verifies that a DAC can be built from the objects in the database, and displays the results in the **Validation and Summary** page.</span></span>  
  
 <span data-ttu-id="52baf-152">**Отмена** — работа мастера завершается без регистрации DAC.</span><span class="sxs-lookup"><span data-stu-id="52baf-152">**Cancel** - Terminates the wizard without registering the DAC.</span></span>  
  
##  <a name="validation-and-summary-page"></a><a name="Summary"></a> <span data-ttu-id="52baf-153">Страница «Проверка и сводка»</span><span class="sxs-lookup"><span data-stu-id="52baf-153">Validation and Summary Page</span></span>  
 <span data-ttu-id="52baf-154">На этой странице можно просмотреть действия, которые будут выполнены мастером при регистрации DAC.</span><span class="sxs-lookup"><span data-stu-id="52baf-154">Use this page to review the actions the wizard will take when registering the DAC.</span></span> <span data-ttu-id="52baf-155">Страница переходит через три состояния при проверке возможности построения DAC из объектов базы данных.</span><span class="sxs-lookup"><span data-stu-id="52baf-155">The page transitions through three states as it verifies that a DAC can be built from the objects in the database.</span></span>  
  
### <a name="retrieving-objects"></a><span data-ttu-id="52baf-156">Получение объектов</span><span class="sxs-lookup"><span data-stu-id="52baf-156">Retrieving Objects</span></span>  
 <span data-ttu-id="52baf-157">**Получение объектов сервера и базы данных.**</span><span class="sxs-lookup"><span data-stu-id="52baf-157">**Retrieving database and server objects.**</span></span> <span data-ttu-id="52baf-158">— отображается индикатор развития процесса получения мастером всех необходимых объектов из базы данных и экземпляра компонента Database Engine.</span><span class="sxs-lookup"><span data-stu-id="52baf-158">- Displays a progress bar as the wizard retrieves all of the required objects from the database and the instance of the Database Engine.</span></span>  
  
 <span data-ttu-id="52baf-159">\*\* \< Назад\*\* . Возврат на страницу " **Задание свойств** " для изменения записей.</span><span class="sxs-lookup"><span data-stu-id="52baf-159">**\< Previous** - Returns you to the **Set Properties** page to change your entries.</span></span>  
  
 <span data-ttu-id="52baf-160">**Далее >** — регистрация DAC и отображение результатов на странице **Регистрация выделенного административного соединения**.</span><span class="sxs-lookup"><span data-stu-id="52baf-160">**Next >** - Registers the DAC and displays the results in the **Register DAC** page.</span></span>  
  
 <span data-ttu-id="52baf-161">**Отмена** — работа мастера завершается без регистрации DAC.</span><span class="sxs-lookup"><span data-stu-id="52baf-161">**Cancel** - Terminates the wizard without registering the DAC.</span></span>  
  
### <a name="validating-objects"></a><span data-ttu-id="52baf-162">Проверка объектов</span><span class="sxs-lookup"><span data-stu-id="52baf-162">Validating Objects</span></span>  
 <span data-ttu-id="52baf-163">**Проверка** _SchemaName_ **.**</span><span class="sxs-lookup"><span data-stu-id="52baf-163">**Checking**  _SchemaName_ **.**</span></span> <span data-ttu-id="52baf-164">_ObjectName_ **.**</span><span class="sxs-lookup"><span data-stu-id="52baf-164">_ObjectName_ **.**</span></span> <span data-ttu-id="52baf-165">— отображает индикатор выполнения по мере того, как мастер проверяет зависимости полученных объектов и допустимость этих объектов для DAC.</span><span class="sxs-lookup"><span data-stu-id="52baf-165">- Displays a progress bar as the wizard verifies the dependencies of the retrieved objects, and verifies that they are all valid objects for a DAC.</span></span> <span data-ttu-id="52baf-166">_SchemaName_ **.** _ObjectName_ указывает, для какого объекта в данный момент выполняется проверка.</span><span class="sxs-lookup"><span data-stu-id="52baf-166">_SchemaName_**.**_ObjectName_ identify which object is currently being verified.</span></span>  
  
 <span data-ttu-id="52baf-167">\*\* \< Назад\*\* . Возврат на страницу " **Задание свойств** " для изменения записей.</span><span class="sxs-lookup"><span data-stu-id="52baf-167">**\< Previous** - Returns you to the **Set Properties** page to change your entries.</span></span>  
  
 <span data-ttu-id="52baf-168">**Далее >** — регистрация DAC и отображение результатов на странице **Регистрация выделенного административного соединения**.</span><span class="sxs-lookup"><span data-stu-id="52baf-168">**Next >** - Registers the DAC and displays the results in the **Register DAC** page.</span></span>  
  
 <span data-ttu-id="52baf-169">**Отмена** — работа мастера завершается без регистрации DAC.</span><span class="sxs-lookup"><span data-stu-id="52baf-169">**Cancel** - Terminates the wizard without registering the DAC.</span></span>  
  
### <a name="summary"></a><span data-ttu-id="52baf-170">Сводка</span><span class="sxs-lookup"><span data-stu-id="52baf-170">Summary</span></span>  
 <span data-ttu-id="52baf-171">**Следующий параметр будет использоваться для регистрации DAC.**</span><span class="sxs-lookup"><span data-stu-id="52baf-171">**The following setting will be used to register your DAC.**</span></span> <span data-ttu-id="52baf-172">— отображает отчет о свойствах и объектах, которые будут включены в DAC.</span><span class="sxs-lookup"><span data-stu-id="52baf-172">- Displays a report of the properties and objects that will be included in the DAC.</span></span>  
  
 <span data-ttu-id="52baf-173">**Сохранить отчет** — сохранить копию отчета о проверке в HTML-файл.</span><span class="sxs-lookup"><span data-stu-id="52baf-173">**Save Report** - Select this button to save a copy of the validation report to an HTML file.</span></span> <span data-ttu-id="52baf-174">Папка по умолчанию является папкой **SQL Server Management Studio\DAC Packages** , вложенной в папки Documents рабочего каталога учетной записи пользователя Windows.</span><span class="sxs-lookup"><span data-stu-id="52baf-174">The default folder is a **SQL Server Management Studio\DAC Packages** folder in the Documents folder of your Windows account.</span></span>  
  
 <span data-ttu-id="52baf-175">\*\* \< Назад\*\* . Возврат на страницу " **Задание свойств** " для изменения записей.</span><span class="sxs-lookup"><span data-stu-id="52baf-175">**\< Previous** - Returns you to the **Set Properties** page to change your entries.</span></span>  
  
 <span data-ttu-id="52baf-176">**Далее >** — регистрация DAC и отображение результатов на странице **Регистрация выделенного административного соединения**.</span><span class="sxs-lookup"><span data-stu-id="52baf-176">**Next >** - Registers the DAC and displays the results in the **Register DAC** page.</span></span>  
  
 <span data-ttu-id="52baf-177">**Отмена** — работа мастера завершается без регистрации DAC.</span><span class="sxs-lookup"><span data-stu-id="52baf-177">**Cancel** - Terminates the wizard without registering the DAC.</span></span>  
  
##  <a name="register-dac-page"></a><a name="Register"></a> <span data-ttu-id="52baf-178">Страница «Регистрация DAC»</span><span class="sxs-lookup"><span data-stu-id="52baf-178">Register DAC Page</span></span>  
 <span data-ttu-id="52baf-179">Эта страница сообщает об успешном или неуспешном завершении регистрации.</span><span class="sxs-lookup"><span data-stu-id="52baf-179">This page reports the success or failure of the registration.</span></span>  
  
 <span data-ttu-id="52baf-180">**Регистрация DAC** — сообщает об успешном или неуспешном завершении каждого действия, выполненного для регистрации DAC.</span><span class="sxs-lookup"><span data-stu-id="52baf-180">**Registering the DAC** - Reports the success or failure of each action taken to register the DAC.</span></span> <span data-ttu-id="52baf-181">Просмотрите эти сведения, чтобы выяснить результаты каждого действия.</span><span class="sxs-lookup"><span data-stu-id="52baf-181">Review the information to determine the success or failure of each action.</span></span> <span data-ttu-id="52baf-182">Для каждого действия, в котором обнаружена ошибка, предусмотрена ссылка в столбце **Результат** .</span><span class="sxs-lookup"><span data-stu-id="52baf-182">Any action that encountered an error will have a link in the **Result** column.</span></span> <span data-ttu-id="52baf-183">Выберите эту ссылку, чтобы просмотреть отчет об ошибках, относящихся данному действию.</span><span class="sxs-lookup"><span data-stu-id="52baf-183">Select the link to view a report of the error for that action.</span></span>  
  
 <span data-ttu-id="52baf-184">**Сохранить отчет** — сохранить отчет о регистрации в HTML-файл.</span><span class="sxs-lookup"><span data-stu-id="52baf-184">**Save Report** - Select this button to save the registration report to an HTML file.</span></span> <span data-ttu-id="52baf-185">В этом файле содержится отчет о состоянии каждого из действий, в том числе все выданные сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="52baf-185">The file reports the status of each action, including all errors generated by any of the actions.</span></span> <span data-ttu-id="52baf-186">Папка по умолчанию является папкой **SQL Server Management Studio\DAC Packages** , вложенной в папки Documents рабочего каталога учетной записи пользователя Windows.</span><span class="sxs-lookup"><span data-stu-id="52baf-186">The default folder is a **SQL Server Management Studio\DAC Packages** folder in the Documents folder of your Windows account.</span></span> <span data-ttu-id="52baf-187">Имя этого файла представлено в формате \<DACPackageName>_RegisterDACReport_yyyymmdd.html, где \<*DACPackageName*> — имя развертываемого пакета, *yyyy* — текущий год, *mm* — текущий месяц, а *dd* — текущий день.</span><span class="sxs-lookup"><span data-stu-id="52baf-187">The file name is in the format \<DACPackageName>_RegisterDACReport_yyyymmdd.html, where \<*DACPackageName*> is the name of the package being deployed, *yyyy* = the current year, *mm* = the current month, and *dd* = the current day.</span></span>  
  
 <span data-ttu-id="52baf-188">**Готово** — завершает работу мастера.</span><span class="sxs-lookup"><span data-stu-id="52baf-188">**Finish** - Terminates the wizard.</span></span>  
  
##  <a name="register-a-dac-using-powershell"></a><a name="RegisterDACPowerShell"></a> <span data-ttu-id="52baf-189">Регистрация приложения DAC с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="52baf-189">Register a DAC Using PowerShell</span></span>  
 <span data-ttu-id="52baf-190">**Регистрация базы данных в качестве приложения уровня данных с использованием метода Register() в скрипте PowerShell**</span><span class="sxs-lookup"><span data-stu-id="52baf-190">**To register a database as a DAC using the Register() method in a PowerShell script**</span></span>  
  
1.  <span data-ttu-id="52baf-191">Создайте объект SMO и настройте его на работу с экземпляром, содержащим базу данных, подлежащую регистрации как DAC.</span><span class="sxs-lookup"><span data-stu-id="52baf-191">Create a SMO Server object and set it to the instance that contains the database to be registered as a DAC.</span></span>  
  
2.  <span data-ttu-id="52baf-192">Добавьте переменную, указывающую имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="52baf-192">Add a variable that specifies the name of the database.</span></span>  
  
3.  <span data-ttu-id="52baf-193">Укажите метаданные для приложения уровня данных, такие как имя, версия и описание приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="52baf-193">Specify the metadata for the DAC, such as the DAC name, version, and description.</span></span>  
  
4.  <span data-ttu-id="52baf-194">Запустите метод Register с использованием указанных ранее данных.</span><span class="sxs-lookup"><span data-stu-id="52baf-194">Run the Register method with the information specified above.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="52baf-195">Пример (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="52baf-195">Example (PowerShell)</span></span>  
 <span data-ttu-id="52baf-196">В следующем примере база данных с именем MyDB регистрируется как DAC.</span><span class="sxs-lookup"><span data-stu-id="52baf-196">The following example registers a database named MyDB as a DAC.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Specify the database to register as a DAC.  
$dbname = "MyDB"  
  
## Specify the DAC metadata.  
$applicationname = "MyApplication"  
$version = "1.0.0.0"  
$description = "This DAC defines the database used by my application."  
  
## Register the DAC.  
$registerunit = New-Object Microsoft.SqlServer.Management.Dac.DacExtractionUnit($srv, $dbname, $applicationname, $version)  
$registerunit.Description = $description  
$registerunit.Register()  
```  
  
## <a name="see-also"></a><span data-ttu-id="52baf-197">См. также:</span><span class="sxs-lookup"><span data-stu-id="52baf-197">See Also</span></span>  
 [<span data-ttu-id="52baf-198">Приложения уровня данных</span><span class="sxs-lookup"><span data-stu-id="52baf-198">Data-tier Applications</span></span>](data-tier-applications.md)  
