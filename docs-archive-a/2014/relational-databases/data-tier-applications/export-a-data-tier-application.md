---
title: Экспорт приложения уровня данных | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.exportdac.settings.f1
- sql12.swb. exportdac.settings.f1
- sql12.swb.exportdac.welcome.f1
- sql12.swb. exportdac.summary.f1
- sql12.swb.exportdac.progress.f1
- sql12.swb.exportdac.summary.f1
- sql12.swb.exportdac.results.f1
- sql12.swb. exportdac.results.f1
helpviewer_keywords:
- How to [DAC], export
- wizard [DAC], export
- export DAC
- data-tier application [SQL Server], export
ms.assetid: 61915bc5-0f5f-45ac-8cfe-3452bc185558
author: stevestein
ms.author: sstein
ms.openlocfilehash: d5e1bbfc5c38dee5e7f29598086d87b680880641
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667206"
---
# <a name="export-a-data-tier-application"></a><span data-ttu-id="e6b4a-102">Экспорт приложения уровня данных</span><span class="sxs-lookup"><span data-stu-id="e6b4a-102">Export a Data-tier Application</span></span>
  <span data-ttu-id="e6b4a-103">При экспорте развернутого приложения уровня данных (DAC) или базы данных создается файл экспорта, содержащий определения объектов в базе данных и все данные, содержащиеся в таблицах.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-103">Exporting a deployed data-tier application (DAC) or database creates an export file that includes both the definitions of the objects in the database and all of the data contained in the tables.</span></span> <span data-ttu-id="e6b4a-104">Файл экспорта затем можно импортировать в другой экземпляр компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)]или в [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6b4a-104">The export file can then be imported to another instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], or to [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)].</span></span> <span data-ttu-id="e6b4a-105">Операции экспорта-импорта могут быть совмещены для переноса приложения уровня данных с одного экземпляра на другой, а также для создания логической резервной копии или создания находящейся на предприятии копии базы данных, развернутой в службах [!INCLUDE[ssSDS](../../includes/sssds-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6b4a-105">The export-import operations can be combined to migrate a DAC between instances, to create a logical backup, or to create an on-premise copy of a database deployed in [!INCLUDE[ssSDS](../../includes/sssds-md.md)].</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="e6b4a-106">Перед началом</span><span class="sxs-lookup"><span data-stu-id="e6b4a-106">Before You Begin</span></span>  
 <span data-ttu-id="e6b4a-107">Процедура экспорта создает файл приложения уровня данных в два этапа.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-107">The export process builds a DAC export file in two stages.</span></span>  
  
1.  <span data-ttu-id="e6b4a-108">При экспорте создается определение приложения уровня данных в файле экспорта (BACPAC) аналогично тому, как извлечение приложения уровня данных создает определение приложения уровня данных в файле пакета приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-108">The export builds a DAC definition in the export file - BACPAC file - in the same way a DAC extract builds a DAC definition in a DAC package file.</span></span> <span data-ttu-id="e6b4a-109">Экспортируемое определение приложения уровня данных включает все объекты в текущей базе данных.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-109">The exported DAC definition includes all of the objects in the current database.</span></span> <span data-ttu-id="e6b4a-110">Если процесс экспорта выполняется в базе данных, которая была первоначально развернута из приложения уровня данных, а все изменения были внесены непосредственно в базу данных после развертывания, то экспортируемое определение соответствует заданному в базе данных объекту, а не объекту, определенному в исходном приложении уровня данных.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-110">If the export process is run against a database that was originally deployed from a DAC, and changes were made directly to the database after deployment, the exported definition matches the object set in the database, not what was defined in the original DAC.</span></span>  
  
2.  <span data-ttu-id="e6b4a-111">При экспорте выполняется массовое копирование данных из всех таблиц в базе данных; эти данные включаются в файл экспорта.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-111">The export bulk copies out the data from all of the tables in the database and incorporates the data into the export file.</span></span>  
  
 <span data-ttu-id="e6b4a-112">В процессе экспорта устанавливается версия приложения уровня данных 1.0.0.0, а описание приложения уровня данных в файле экспорта устанавливается в пустую строку.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-112">The export process sets the DAC version to 1.0.0.0 and the DAC description in the export file to an empty string.</span></span> <span data-ttu-id="e6b4a-113">Если база данных была развернута из приложения уровня данных, то определение приложения уровня данных в файле экспорта содержит имя, заданное для исходного приложения уровня данных; в противном случае имя приложения уровня данных устанавливается равным имени базы данных.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-113">If the database was deployed from a DAC, the DAC definition in the export file contains the name given to the original DAC, otherwise the DAC name is set to the database name.</span></span>  
  

###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="e6b4a-114">Ограничения</span><span class="sxs-lookup"><span data-stu-id="e6b4a-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="e6b4a-115">Приложение уровня данных или база данных могут экспортироваться только из базы данных в [!INCLUDE[ssSDS](../../includes/sssds-md.md)]или [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] с пакетом обновления 4 (SP4) и выше.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-115">A DAC or database can only be exported from a database in [!INCLUDE[ssSDS](../../includes/sssds-md.md)], or [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) or later.</span></span>  
  
 <span data-ttu-id="e6b4a-116">Если база данных содержит объекты, не поддерживаемые в приложениях уровня данных, или автономных пользователей, то экспортировать такую базу данных будет невозможно.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-116">You cannot export a database that has objects that are not supported in a DAC, or contained users.</span></span> <span data-ttu-id="e6b4a-117">Дополнительные сведения о типах объектов, поддерживаемых в DAC, см. в разделе [DAC Support For SQL Server Objects and Versions](dac-support-for-sql-server-objects-and-versions.md).</span><span class="sxs-lookup"><span data-stu-id="e6b4a-117">For more information about the types of objects supported in a DAC, see [DAC Support For SQL Server Objects and Versions](dac-support-for-sql-server-objects-and-versions.md).</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e6b4a-118">Permissions</span><span class="sxs-lookup"><span data-stu-id="e6b4a-118">Permissions</span></span>  
 <span data-ttu-id="e6b4a-119">Для экспорта приложения уровня данных необходимы по крайней мере разрешения ALTER ANY LOGIN и VIEW DEFINITION на уровне базы данных, а также разрешение SELECT на представление каталога **sys.sql_expression_dependencies**.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-119">Exporting a DAC requires at least ALTER ANY LOGIN and database scope VIEW DEFINITION permissions, as well as SELECT permissions on **sys.sql_expression_dependencies**.</span></span> <span data-ttu-id="e6b4a-120">Экспорт приложения уровня данных может выполняться членами предопределенной роли сервера securityadmin, которые также входят в предопределенную роль базы данных database_owner для базы данных, из которой экспортируется приложение уровня данных.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-120">Exporting a DAC can be done by members of the securityadmin fixed server role who are also members of the database_owner fixed database role in the database from which the DAC is exported.</span></span> <span data-ttu-id="e6b4a-121">Экспортировать приложение уровня данных могут также члены предопределенной роли сервера sysadmin или встроенной роли системного администратора SQL Server с названием **sa** .</span><span class="sxs-lookup"><span data-stu-id="e6b4a-121">Members of the sysadmin fixed server role or the built-in SQL Server system administrator account named **sa** can also export a DAC.</span></span>  
  
##  <a name="using-the-export-data-tier-application-wizard"></a><a name="UsingDeployDACWizard"></a><span data-ttu-id="e6b4a-122">Использование мастера экспорта приложения уровня данных</span><span class="sxs-lookup"><span data-stu-id="e6b4a-122">Using the Export Data-tier Application Wizard</span></span>  
 <span data-ttu-id="e6b4a-123">**Экспорт приложения уровня данных с помощью мастера**</span><span class="sxs-lookup"><span data-stu-id="e6b4a-123">**To Export a DAC Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="e6b4a-124">Подключитесь к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]на предприятии или в службах [!INCLUDE[ssSDS](../../includes/sssds-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6b4a-124">Connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], whether on-premise or in [!INCLUDE[ssSDS](../../includes/sssds-md.md)].</span></span>  
  
2.  <span data-ttu-id="e6b4a-125">В **обозревателе объектов**раскройте узел экземпляра, из которого будет производиться экспорт приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-125">In **Object Explorer**, expand the node for the instance from which you want to export the DAC.</span></span>  
  
3.  <span data-ttu-id="e6b4a-126">Щелкните правой кнопкой мыши имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-126">Right-click the database name.</span></span>  
  
4.  <span data-ttu-id="e6b4a-127">Щелкните **задачи** и выберите **Экспорт приложения уровня данных...**</span><span class="sxs-lookup"><span data-stu-id="e6b4a-127">Click **Tasks** and then select **Export Data-tier Application...**</span></span>  
  
5.  <span data-ttu-id="e6b4a-128">Выполните шаги в диалоговых окнах мастера.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-128">Complete the wizard dialogs:</span></span>  
  
    -   [<span data-ttu-id="e6b4a-129">Вводная страница</span><span class="sxs-lookup"><span data-stu-id="e6b4a-129">Introduction Page</span></span>](#Introduction)  
  
    -   [<span data-ttu-id="e6b4a-130">Страница «Параметры экспорта»</span><span class="sxs-lookup"><span data-stu-id="e6b4a-130">Export Settings Page</span></span>](#Export_settings)  
  
    -   [<span data-ttu-id="e6b4a-131">Страница «Проверка»</span><span class="sxs-lookup"><span data-stu-id="e6b4a-131">Validation Page</span></span>](#Validation)  
  
    -   [<span data-ttu-id="e6b4a-132">Страница «Сводка»</span><span class="sxs-lookup"><span data-stu-id="e6b4a-132">Summary Page</span></span>](#Summary)  
  
    -   [<span data-ttu-id="e6b4a-133">Страница "выполнение"</span><span class="sxs-lookup"><span data-stu-id="e6b4a-133">Progress Page</span></span>](#Progress)  
  
    -   [<span data-ttu-id="e6b4a-134">Страница «Результаты»</span><span class="sxs-lookup"><span data-stu-id="e6b4a-134">Results Page</span></span>](#Results)  
  
##  <a name="introduction-page"></a><a name="Introduction"></a> <span data-ttu-id="e6b4a-135">Вводная страница</span><span class="sxs-lookup"><span data-stu-id="e6b4a-135">Introduction Page</span></span>  
 <span data-ttu-id="e6b4a-136">На этой странице описаны шаги мастера экспорта приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-136">This page describes the steps for the Export Data-tier Application Wizard.</span></span>  
  
 <span data-ttu-id="e6b4a-137">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="e6b4a-137">**Options**</span></span>  
  
 <span data-ttu-id="e6b4a-138">**Больше не показывать эту страницу.**</span><span class="sxs-lookup"><span data-stu-id="e6b4a-138">**Do not show this page again.**</span></span> <span data-ttu-id="e6b4a-139">— установите этот флажок, чтобы предотвратить отображение страницы «Введение» в будущем.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-139">- Click the check box to stop the Introduction page from being displayed in the future.</span></span>  
  
 <span data-ttu-id="e6b4a-140">**Далее &gt;** — переход на страницу **Выбор пакета приложения уровня данных** .</span><span class="sxs-lookup"><span data-stu-id="e6b4a-140">**Next** - Proceeds to the **Select DAC Package** page.</span></span>  
  
 <span data-ttu-id="e6b4a-141">**Отмена** — отмена операции и закрытие мастера.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-141">**Cancel** - Cancels the operation and closes the Wizard.</span></span>  
  
##  <a name="export-settings-page"></a><a name="Export_settings"></a><span data-ttu-id="e6b4a-142">Страница параметров экспорта</span><span class="sxs-lookup"><span data-stu-id="e6b4a-142">Export Settings Page</span></span>  
 <span data-ttu-id="e6b4a-143">Используйте эту страницу, чтобы указать место, где нужно создать BACPAC-файл.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-143">Use this page to specify the location where you want the BACPAC file to be created.</span></span>  
  
-   <span data-ttu-id="e6b4a-144">**Сохранить на локальный диск** — создает BACPAC-файл в каталоге на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-144">**Save to local disk** - Creates a BACPAC file in a directory on the local computer.</span></span> <span data-ttu-id="e6b4a-145">Нажмите кнопку **Обзор…** для навигации по локальному компьютеру или укажите путь в соответствующем поле.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-145">Click **Browse...** to navigate the local computer, or specify the path in the space provided.</span></span> <span data-ttu-id="e6b4a-146">Имя пути должно включать имя файла и расширение BACPAC.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-146">The path name must include a file name and the .bacpac extension.</span></span>  
  
-   <span data-ttu-id="e6b4a-147">**Сохранить в Azure** — создает BACPAC-файл в контейнере Azure.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-147">**Save to Azure** - Creates a BACPAC file in an Azure container.</span></span> <span data-ttu-id="e6b4a-148">Чтобы проверить этот параметр, необходимо подключиться к контейнеру Azure.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-148">You must connect to an Azure container in order to validate this option.</span></span> <span data-ttu-id="e6b4a-149">Обратите внимание, что для этого параметра также необходимо указать локальный каталог для временного файла.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-149">Note that this option also requires that you specify a local directory for the temporary file.</span></span> <span data-ttu-id="e6b4a-150">Примите к сведению, что временный файл будет создан в указанном месте и останется там после завершения операции.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-150">Note that the temporary file will be created at the specified location and will remain there after the operation completes.</span></span>  
  
 <span data-ttu-id="e6b4a-151">Чтобы задать подмножество таблиц для экспорта, используйте параметр **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="e6b4a-151">To specify a subset of tables to export, use the **Advanced** option.</span></span>  
  
##  <a name="validation-page"></a><a name="Validation"></a><span data-ttu-id="e6b4a-152">Страница проверки</span><span class="sxs-lookup"><span data-stu-id="e6b4a-152">Validation Page</span></span>  
 <span data-ttu-id="e6b4a-153">Используйте страницу «Проверка» для поиска любых проблем, блокирующих операцию.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-153">Use the validation page to review any issues that block the operation.</span></span> <span data-ttu-id="e6b4a-154">Для продолжения устраните критические препятствия, приводящие к блокированию, и нажмите кнопку **Повторная проверка** для обеспечения успешного завершения проверки.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-154">To continue, resolve blocking issues and then click **Re-run Validation** to ensure that validation is successful.</span></span>  
  
 <span data-ttu-id="e6b4a-155">Чтобы продолжить, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-155">To continue, click **Next**.</span></span>  
  
##  <a name="summary-page"></a><a name="Summary"></a> <span data-ttu-id="e6b4a-156">Страница «Сводка»</span><span class="sxs-lookup"><span data-stu-id="e6b4a-156">Summary Page</span></span>  
 <span data-ttu-id="e6b4a-157">Воспользуйтесь этой страницей для просмотра указанного источника и целевых параметров операции.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-157">Use this page to review the specified source and target settings for the operation.</span></span> <span data-ttu-id="e6b4a-158">Для завершения экспорта с использованием заданных параметров нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-158">To complete the export operation using the specified settings, click **Finish**.</span></span> <span data-ttu-id="e6b4a-159">Чтобы отменить операцию экспорта и выйти из мастера, нажмите кнопку **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-159">To cancel the export operation and exit the Wizard, click **Cancel**.</span></span>  
  
##  <a name="progress-page"></a><a name="Progress"></a> <span data-ttu-id="e6b4a-160">Страница «Ход выполнения»</span><span class="sxs-lookup"><span data-stu-id="e6b4a-160">Progress Page</span></span>  
 <span data-ttu-id="e6b4a-161">На этой странице отображается индикатор выполнения, который определяет состояние операции.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-161">This page displays a progress bar that indicates the status of the operation.</span></span> <span data-ttu-id="e6b4a-162">Чтобы просмотреть подробности состояния, выберите параметр **Просмотр сведений** .</span><span class="sxs-lookup"><span data-stu-id="e6b4a-162">To view detailed status, click the **View details** option.</span></span>  
  
##  <a name="results-page"></a><a name="Results"></a><span data-ttu-id="e6b4a-163">Страница «результаты»</span><span class="sxs-lookup"><span data-stu-id="e6b4a-163">Results Page</span></span>  
 <span data-ttu-id="e6b4a-164">На этой странице отображаются сведения об успешности завершения экспорта по результатам каждого действия.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-164">This page reports the success or failure of the export operation, showing the results of each action.</span></span> <span data-ttu-id="e6b4a-165">Для каждого действия, в котором обнаружена ошибка, предусмотрена ссылка в столбце **Результат** .</span><span class="sxs-lookup"><span data-stu-id="e6b4a-165">Any action that encountered an error will have a link in the **Result** column.</span></span> <span data-ttu-id="e6b4a-166">Щелкните эту ссылку, чтобы просмотреть отчет об ошибках, относящихся к данному действию.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-166">Click the link to view a report of the error for that action.</span></span>  
  
 <span data-ttu-id="e6b4a-167">Нажмите кнопку **Готово** , чтобы закрыть мастер.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-167">Click **Finish** to close the Wizard.</span></span>  
  
##  <a name="using-a-net-framework-application"></a><a name="NetApp"></a><span data-ttu-id="e6b4a-168">Использование приложения .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e6b4a-168">Using a .Net Framework Application</span></span>  
 <span data-ttu-id="e6b4a-169">**Экспорт приложения уровня данных с использованием метода Export () в приложении .NET Framework.**</span><span class="sxs-lookup"><span data-stu-id="e6b4a-169">**To export a DAC using the Export() method in a .Net Framework application.**</span></span>  
  
 <span data-ttu-id="e6b4a-170">Чтобы просмотреть пример кода, загрузите пример приложения DAC на сайте [Codeplex](https://go.microsoft.com/fwlink/?LinkId=219575)</span><span class="sxs-lookup"><span data-stu-id="e6b4a-170">To view a code example, download the DAC sample application on [Codeplex](https://go.microsoft.com/fwlink/?LinkId=219575)</span></span>  
  
1.  <span data-ttu-id="e6b4a-171">Создайте объект SMO Server и установите его в экземпляр, содержащий экспортируемое приложение уровня данных.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-171">Create a SMO Server object and set it to the instance that contains the DAC to be exported.</span></span>  
  
2.  <span data-ttu-id="e6b4a-172">Откройте объект `ServerConnection` и подключитесь к тому же экземпляру.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-172">Open a `ServerConnection` object and connect to the same instance.</span></span>  
  
3.  <span data-ttu-id="e6b4a-173">Используйте метод `Export` типа `Microsoft.SqlServer.Management.Dac.DacStore` для экспорта приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-173">Use the `Export` method of the `Microsoft.SqlServer.Management.Dac.DacStore` type to export the DAC.</span></span> <span data-ttu-id="e6b4a-174">Укажите имя экспортируемого приложения уровня данных и путь к папке, в которой будет размещен файл экспорта.</span><span class="sxs-lookup"><span data-stu-id="e6b4a-174">Specify the name of the DAC to be exported, and the path to the folder where the export file is to be placed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6b4a-175">См. также:</span><span class="sxs-lookup"><span data-stu-id="e6b4a-175">See Also</span></span>  
 <span data-ttu-id="e6b4a-176">[Приложения уровня данных](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="e6b4a-176">[Data-tier Applications](data-tier-applications.md) </span></span>  
 [<span data-ttu-id="e6b4a-177">Извлечение DAC из базы данных</span><span class="sxs-lookup"><span data-stu-id="e6b4a-177">Extract a DAC From a Database</span></span>](extract-a-dac-from-a-database.md)  
  
  
