---
title: Извлечение приложения уровня данных из базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.extractdacwizard.buildandsave.f1
- sql12.swb.extractdacwizard.setdacproperties.f1
- sql12.swb.extractdacwizard.validationandsummary.f1
- sql12.swb.extractdacwizard.introduction.f1
- sql12.swb.extractdacwizard.selectdatapage.f1
helpviewer_keywords:
- extract DAC
- How to [DAC], extract
- data-tier application [SQL Server], extract
- wizard [DAC], extract
ms.assetid: ae52a723-91c4-43fd-bcc7-f8de1d1f90e5
author: stevestein
ms.author: sstein
ms.openlocfilehash: bd024af9c201563773e20bae7e5fded1985abbe1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668386"
---
# <a name="extract-a-dac-from-a-database"></a><span data-ttu-id="36cc2-102">Извлечение приложения уровня данных из базы данных</span><span class="sxs-lookup"><span data-stu-id="36cc2-102">Extract a DAC From a Database</span></span>
  <span data-ttu-id="36cc2-103">Извлечение пакета приложения уровня данных из существующей базы данных SQL Server можно с помощью **мастера извлечения приложения уровня данных** или скрипта Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="36cc2-103">Use either the **Extract Data-tier Application Wizard** or a Windows PowerShell script to extract a data-tier application (DAC) package from an existing SQL Server database.</span></span> <span data-ttu-id="36cc2-104">В результате извлечения будет создан файл пакета DAC, содержащий определения объектов базы данных и связанные элементы уровня экземпляра.</span><span class="sxs-lookup"><span data-stu-id="36cc2-104">The extraction process creates a DAC package file that contains definitions of the database objects and their related instance-level elements.</span></span> <span data-ttu-id="36cc2-105">Например, файл пакета DAC содержит все таблицы базы данных, хранимые процедуры, представления, пользователей и имена входа, сопоставленные с пользователями базы данных.</span><span class="sxs-lookup"><span data-stu-id="36cc2-105">For example, a DAC package file contains the database tables, stored procedures, views, and users, along with the logins that map to the database users.</span></span>  
  
-   <span data-ttu-id="36cc2-106">**Перед началом работы**  [ограничения](#LimitationsRestrictions), [разрешения](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="36cc2-106">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="36cc2-107">**Извлечение DAC с помощью:**  [Мастер извлечения приложения уровня данных](#UsingDACExtractWizard), [PowerShell](#ExtractDACPowerShell)</span><span class="sxs-lookup"><span data-stu-id="36cc2-107">**To extract a DAC, using:**  [The Extract Data-tier Application Wizard](#UsingDACExtractWizard), [PowerShell](#ExtractDACPowerShell)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="36cc2-108">Перед началом</span><span class="sxs-lookup"><span data-stu-id="36cc2-108">Before You Begin</span></span>  
 <span data-ttu-id="36cc2-109">Предусмотрена возможность извлечения приложения уровня данных из баз данных, находящихся на экземплярах [!INCLUDE[ssSDS](../../includes/sssds-md.md)]или [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] с пакетом обновления 4 (SP4) или более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="36cc2-109">You can extract a DAC from databases residing on instances of [!INCLUDE[ssSDS](../../includes/sssds-md.md)], or [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] Service Pack 4 or later.</span></span> <span data-ttu-id="36cc2-110">Если процесс извлечения запущен для базы данных, которая была развернута из приложения уровня данных, то происходит извлечение только определений объектов в базе данных.</span><span class="sxs-lookup"><span data-stu-id="36cc2-110">If the extraction process is run against a database that was deployed from a DAC, only the definitions of the objects in the database are extracted.</span></span> <span data-ttu-id="36cc2-111">Этот процесс не ссылается на приложение уровня данных, зарегистрированное в `msdb` (**master** в [!INCLUDE[ssSDS](../../includes/sssds-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="36cc2-111">The process does not reference the DAC registered in `msdb` (**master** in [!INCLUDE[ssSDS](../../includes/sssds-md.md)]).</span></span> <span data-ttu-id="36cc2-112">Процесс извлечения не регистрирует определение приложения уровня данных в текущем экземпляре компонента Database Engine.</span><span class="sxs-lookup"><span data-stu-id="36cc2-112">The extraction process does not register the DAC definition in the current instance of the Database Engine.</span></span> <span data-ttu-id="36cc2-113">Дополнительные сведения о регистрации приложения уровня данных см. в разделе [Register a Database As a DAC](register-a-database-as-a-dac.md).</span><span class="sxs-lookup"><span data-stu-id="36cc2-113">For more information about registering a DAC, see [Register a Database As a DAC](register-a-database-as-a-dac.md).</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="36cc2-114">Ограничения</span><span class="sxs-lookup"><span data-stu-id="36cc2-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="36cc2-115">Приложение уровня данных может быть извлечено только из базы данных в [!INCLUDE[ssSDS](../../includes/sssds-md.md)], либо в [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] с пакетом обновления 4 (SP4) и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="36cc2-115">A DAC can only be extracted from a database in [!INCLUDE[ssSDS](../../includes/sssds-md.md)], or [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) or later.</span></span> <span data-ttu-id="36cc2-116">Извлечь приложение уровня данных нельзя, если в базе данных имеются объекты, не поддерживаемые в приложении уровня данных, или содержащиеся пользователи.</span><span class="sxs-lookup"><span data-stu-id="36cc2-116">You cannot extract a DAC if the database has objects that are not supported in a DAC, or contained users.</span></span> <span data-ttu-id="36cc2-117">Дополнительные сведения о типах объектов, поддерживаемых в DAC, см. в разделе [DAC Support For SQL Server Objects and Versions](dac-support-for-sql-server-objects-and-versions.md).</span><span class="sxs-lookup"><span data-stu-id="36cc2-117">For more information about the types of objects supported in a DAC, see [DAC Support For SQL Server Objects and Versions](dac-support-for-sql-server-objects-and-versions.md).</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="36cc2-118">Permissions</span><span class="sxs-lookup"><span data-stu-id="36cc2-118">Permissions</span></span>  
 <span data-ttu-id="36cc2-119">Чтобы извлечь DAC, необходимы по крайней мере разрешение ALTER ANY LOGIN и разрешение VIEW DEFINITION на уровне базы данных, а также разрешения SELECT для представления каталога **sys.sql_expression_dependencies**.</span><span class="sxs-lookup"><span data-stu-id="36cc2-119">Extracting a DAC requires at least ALTER ANY LOGIN and database scope VIEW DEFINITION permissions, as well as SELECT permissions on **sys.sql_expression_dependencies**.</span></span> <span data-ttu-id="36cc2-120">Извлечение DAC может выполняться членами предопределенной роли сервера securityadmin, которые также обладают правами предопределенной роли базы данных database_owner в базе данных, из которой извлекается DAC.</span><span class="sxs-lookup"><span data-stu-id="36cc2-120">Extracting a DAC can be done by members of the securityadmin fixed server role who are also members of the database_owner fixed database role in the database from which the DAC is extracted.</span></span> <span data-ttu-id="36cc2-121">Приложения уровня данных могут также извлекать члены предопределенной роли сервера sysadmin или встроенной учетной записи системного администратора SQL Server с именем **sa** .</span><span class="sxs-lookup"><span data-stu-id="36cc2-121">Members of the sysadmin fixed server role or the built-in SQL Server system administrator account named **sa** can also extract a DAC.</span></span>  
  
##  <a name="using-the-extract-data-tier-application-wizard"></a><a name="UsingDACExtractWizard"></a> <span data-ttu-id="36cc2-122">Использование мастера извлечения приложения уровня данных</span><span class="sxs-lookup"><span data-stu-id="36cc2-122">Using the Extract Data-tier Application Wizard</span></span>  
 <span data-ttu-id="36cc2-123">**Извлечение приложения уровня данных с помощью мастера**</span><span class="sxs-lookup"><span data-stu-id="36cc2-123">**To Extract a DAC Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="36cc2-124">В **обозревателе объектов**разверните узел, относящийся к экземпляру, содержащему базу данных, из которой должно быть извлечено приложение уровня данных.</span><span class="sxs-lookup"><span data-stu-id="36cc2-124">In **Object Explorer**, expand the node for the instance containing the database from which the DAC is to be extracted.</span></span>  
  
2.  <span data-ttu-id="36cc2-125">Разверните узел **Базы данных** .</span><span class="sxs-lookup"><span data-stu-id="36cc2-125">Expand the **Databases** node.</span></span>  
  
3.  <span data-ttu-id="36cc2-126">Щелкните правой кнопкой мыши узел, относящийся к базе данных, из которой должно быть извлечено приложение уровня данных, укажите пункт **Задачи**, а затем выберите **Извлечение приложения уровня данных…**.</span><span class="sxs-lookup"><span data-stu-id="36cc2-126">Right-click the node for the database from which the DAC is to be extracted, point to **Tasks**, and then select **Extract Data-tier Application...**</span></span>  
  
4.  <span data-ttu-id="36cc2-127">Выполните шаги в диалоговых окнах мастера.</span><span class="sxs-lookup"><span data-stu-id="36cc2-127">Complete the wizard dialogs:</span></span>  
  
    1.  [<span data-ttu-id="36cc2-128">Вводная страница</span><span class="sxs-lookup"><span data-stu-id="36cc2-128">Introduction Page</span></span>](#Introduction)  
  
    2.  [<span data-ttu-id="36cc2-129">Страница выбора данных</span><span class="sxs-lookup"><span data-stu-id="36cc2-129">Select Data Page</span></span>](#SelectData)  
  
    3.  [<span data-ttu-id="36cc2-130">Страница «Задание свойств»</span><span class="sxs-lookup"><span data-stu-id="36cc2-130">Set Properties Page</span></span>](#SetProperties)  
  
    4.  [<span data-ttu-id="36cc2-131">Страница «Проверка и сводка»</span><span class="sxs-lookup"><span data-stu-id="36cc2-131">Validation and Summary Page</span></span>](#ValidateSummary)  
  
    5.  [<span data-ttu-id="36cc2-132">Страница построения пакета</span><span class="sxs-lookup"><span data-stu-id="36cc2-132">Build Package Page</span></span>](#BuildPackage)  
  
###  <a name="introduction-page"></a><a name="Introduction"></a> <span data-ttu-id="36cc2-133">Вводная страница</span><span class="sxs-lookup"><span data-stu-id="36cc2-133">Introduction Page</span></span>  
 <span data-ttu-id="36cc2-134">На этой странице описаны шаги извлечения приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="36cc2-134">This page describes the steps for extracting a data-tier application.</span></span>  
  
 <span data-ttu-id="36cc2-135">**Больше не показывать эту страницу.**</span><span class="sxs-lookup"><span data-stu-id="36cc2-135">**Do not show this page again.**</span></span> <span data-ttu-id="36cc2-136">— щелкните этот флажок, чтобы предотвратить отображение этой страницы в будущем.</span><span class="sxs-lookup"><span data-stu-id="36cc2-136">- Click the check box to stop the page from being displayed in the future.</span></span>  
  
 <span data-ttu-id="36cc2-137">**Далее >** — переход к странице **Выбор метода**.</span><span class="sxs-lookup"><span data-stu-id="36cc2-137">**Next >** - Proceeds to the **Choose Method** page.</span></span>  
  
 <span data-ttu-id="36cc2-138">**Отмена** — завершает работу мастера без извлечения приложения уровня данных из базы данных.</span><span class="sxs-lookup"><span data-stu-id="36cc2-138">**Cancel** - Ends the wizard without extracting a data-tier application from the database.</span></span>  
  
###  <a name="select-data-page"></a><a name="SelectData"></a><span data-ttu-id="36cc2-139">Страница «Выбор данных»</span><span class="sxs-lookup"><span data-stu-id="36cc2-139">Select Data Page</span></span>  
 <span data-ttu-id="36cc2-140">На этой странице мастера можно выбрать эталонные данные, которые нужно включить в файл пакета приложения уровня данных (пакет DAC).</span><span class="sxs-lookup"><span data-stu-id="36cc2-140">Use this page of the wizard to select the reference data that you want to include in your data-tier application (DAC) package file.</span></span> <span data-ttu-id="36cc2-141">Включать данные в пакет DAC не обязательно.</span><span class="sxs-lookup"><span data-stu-id="36cc2-141">Including data in your DAC package is optional.</span></span> <span data-ttu-id="36cc2-142">Пакет DAC уже включает схему всех поддерживаемых объектов базы данных и объекты экземпляров, связанные с базой данных.</span><span class="sxs-lookup"><span data-stu-id="36cc2-142">The DAC package will already include the schema of all supported database objects and instance objects related to your database.</span></span>  
  
 <span data-ttu-id="36cc2-143">В файл пакета DAC можно включать до 10 МБ эталонных данных.</span><span class="sxs-lookup"><span data-stu-id="36cc2-143">You can include up to 10 MB of reference data in your DAC package file.</span></span> <span data-ttu-id="36cc2-144">Однако таблицы, включаемые в пакет DAC, не должны содержать типы данных больших двоичных объектов (BLOB), такие как **image** или **varchar(max)**.</span><span class="sxs-lookup"><span data-stu-id="36cc2-144">However, for tables to be included in the DAC, they may not contain binary large object (BLOB) data types such as **image** or **varchar(max)**.</span></span> <span data-ttu-id="36cc2-145">Чтобы извлечь данные большего объема для передачи в другую базу данных, используйте службы SQL Server Integration Services, программу массового копирования или один из многих других методов переноса данных.</span><span class="sxs-lookup"><span data-stu-id="36cc2-145">To extract larger amounts of data for transferring to another database, use SQL Server Integration Services, the bulk copy utility, or one of many other data migration techniques.</span></span>  
  
 <span data-ttu-id="36cc2-146">**Таблица базы данных** — установите флажок рядом для тех таблиц в базе данных, где находятся данные, которые необходимо включить в пакет приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="36cc2-146">**Database table** - Select the check box next to the database tables which contain the data that you want to include in your DAC package.</span></span> <span data-ttu-id="36cc2-147">Можно выбрать до десяти таблиц, число строк в которых не превышает 10 000.</span><span class="sxs-lookup"><span data-stu-id="36cc2-147">You can select up to ten tables that have 10,000 rows or less.</span></span>  
  
###  <a name="set-properties-page"></a><a name="SetProperties"></a> <span data-ttu-id="36cc2-148">Страница «Задание свойств»</span><span class="sxs-lookup"><span data-stu-id="36cc2-148">Set Properties Page</span></span>  
 <span data-ttu-id="36cc2-149">Эта страница мастера содержит описание приложения уровня данных (DAC).</span><span class="sxs-lookup"><span data-stu-id="36cc2-149">Use this page of the wizard to describe the data-tier application (DAC).</span></span> <span data-ttu-id="36cc2-150">Данные свойства используются для определения DAC и помогают отличать его от других приложений.</span><span class="sxs-lookup"><span data-stu-id="36cc2-150">These properties are used to identify the DAC and help distinguish it from others.</span></span>  
  
 <span data-ttu-id="36cc2-151">**Имя** — имя приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="36cc2-151">**Name** - This name identifies the DAC.</span></span> <span data-ttu-id="36cc2-152">Оно может отличаться от имени файла пакета DAC и должно описывать приложение.</span><span class="sxs-lookup"><span data-stu-id="36cc2-152">It can be different than the name of the DAC package file and should describe your application.</span></span> <span data-ttu-id="36cc2-153">Например, если база данных используется для финансового приложения, то можно назвать ее «Финансы DAC».</span><span class="sxs-lookup"><span data-stu-id="36cc2-153">For example, if the database is used for a finance application, you may wish to name the DAC Finance.</span></span>  
  
 <span data-ttu-id="36cc2-154">**Версия (в формате xx.xx.xx.xx, где x — цифра)** — числовое значение, которое указывает версию приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="36cc2-154">**Version (use xx.xx.xx.xx, where x is a number)** - A numeric value that identifies the version of the DAC.</span></span> <span data-ttu-id="36cc2-155">Версия DAC используется в среде Visual Studio для определения версии DAC, над которой работают разработчики.</span><span class="sxs-lookup"><span data-stu-id="36cc2-155">The DAC version is used in Visual Studio to identify the version of the DAC that developers are working on.</span></span> <span data-ttu-id="36cc2-156">При развертывании DAC версия хранится в `msdb` базе данных и затем может быть просмотрена в узле **приложения уровня данных** в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="36cc2-156">When deploying a DAC, the version is stored in the `msdb` database and can later be viewed under the **Data-tier Applications** node in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="36cc2-157">**Описание:** — необязательно.</span><span class="sxs-lookup"><span data-stu-id="36cc2-157">**Description:** - Optional.</span></span> <span data-ttu-id="36cc2-158">Описывает DAC.</span><span class="sxs-lookup"><span data-stu-id="36cc2-158">Describes the DAC.</span></span> <span data-ttu-id="36cc2-159">При развертывании DAC описание сохраняется в `msdb` базе данных и затем может быть просмотрено в узле **приложения уровня данных** в среде [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="36cc2-159">When deploying a DAC, the description is stored in the `msdb` database and can later be viewed under the **Data-tier Applications** node in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="36cc2-160">**Сохранить в файл пакета выделенного административного соединения (укажите имя файла с расширением .dacpac)** — сохраняет приложение уровня данных в файле пакета приложения уровня данных с расширением DACPAC.</span><span class="sxs-lookup"><span data-stu-id="36cc2-160">**Save to DAC package file (include .dacpac extension with file name):** - Saves the DAC to a DAC package file, with a .dacpac extension.</span></span> <span data-ttu-id="36cc2-161">Нажмите кнопку **Обзор** , чтобы задать имя и выбрать местоположение файла.</span><span class="sxs-lookup"><span data-stu-id="36cc2-161">Click the **Browse** button to specify a name and location for the file.</span></span>  
  
 <span data-ttu-id="36cc2-162">**Перезапись существующего файла** — выберите этот флажок, чтобы заменить файл пакета приложения уровня данных с тем же именем, если он уже существует.</span><span class="sxs-lookup"><span data-stu-id="36cc2-162">**Overwrite existing file** - Select this check box to replace the DAC package file if one already exists with the same name.</span></span>  
  
###  <a name="validation-and-summary-page"></a><a name="ValidateSummary"></a> <span data-ttu-id="36cc2-163">Страница «Проверка и сводка»</span><span class="sxs-lookup"><span data-stu-id="36cc2-163">Validation and Summary Page</span></span>  
 <span data-ttu-id="36cc2-164">На этой странице мастер проверяет, все ли объекты базы данных поддерживаются приложением уровня данных.</span><span class="sxs-lookup"><span data-stu-id="36cc2-164">On this page, the wizard validates that all database objects are supported by a data-tier application (DAC).</span></span> <span data-ttu-id="36cc2-165">На ней также проверяются зависимости между объектами базы данных, чтобы определить набор объектов, которые могут быть успешно включены в DAC.</span><span class="sxs-lookup"><span data-stu-id="36cc2-165">It also checks dependencies across database objects to determine the set of objects that can be successfully included in the DAC.</span></span> <span data-ttu-id="36cc2-166">После этого отображается отчет о проверке, содержащий сводку параметров, выбранных в этом мастере.</span><span class="sxs-lookup"><span data-stu-id="36cc2-166">After that, it displays the validation report and summarizes the options that you have selected in this wizard.</span></span> <span data-ttu-id="36cc2-167">Чтобы изменить параметр, нажмите кнопку **Назад**.</span><span class="sxs-lookup"><span data-stu-id="36cc2-167">To change an option, click **Previous**.</span></span> <span data-ttu-id="36cc2-168">Чтобы начать извлечение DAC, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="36cc2-168">To begin extracting a DAC, click **Next**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="36cc2-169">Если один или несколько объектов не поддерживаются приложением уровня данных, то кнопка **Далее** будет неактивна и процесс извлечения продолжить нельзя.</span><span class="sxs-lookup"><span data-stu-id="36cc2-169">If one or more objects are not supported by a DAC, then the **Next** button is disabled and the extraction process may not continue.</span></span> <span data-ttu-id="36cc2-170">В таком случае рекомендуется удалить неподдерживаемые объекты и вновь запустить данный мастер.</span><span class="sxs-lookup"><span data-stu-id="36cc2-170">In such cases, it is recommended to remove the non-supported objects and then run this wizard again.</span></span>  
  
 <span data-ttu-id="36cc2-171">**Сводка** — сводка выбранных параметров перечисляется в разделе **Свойства приложения уровня данных**.</span><span class="sxs-lookup"><span data-stu-id="36cc2-171">**Summary** - A summary of the options you have selected are listed under **DAC properties**.</span></span> <span data-ttu-id="36cc2-172">Результаты проверки отображаются в разделе **Объекты DAC**.</span><span class="sxs-lookup"><span data-stu-id="36cc2-172">The results of the validation are listed under **DAC objects**.</span></span> <span data-ttu-id="36cc2-173">Существует три типа результатов проверки:</span><span class="sxs-lookup"><span data-stu-id="36cc2-173">There are three types of results from the validation:</span></span>  
  
-   <span data-ttu-id="36cc2-174">**Объекты, успешно включенные в DAC**: эти объекты и их зависимости поддерживаются и могут быть включены в DAC.</span><span class="sxs-lookup"><span data-stu-id="36cc2-174">**Objects included in DAC successfully**: these objects and their dependencies are supported, and can be included in the DAC successfully.</span></span>  
  
-   <span data-ttu-id="36cc2-175">**Объекты, включенные в DAC с предупреждениями**: эти объекты поддерживаются, но зависят от других объектов, которые не поддерживаются DAC.</span><span class="sxs-lookup"><span data-stu-id="36cc2-175">**Objects included in DAC with warnings**: these objects are supported, but depend on other objects that are not supported in a DAC.</span></span>  
  
-   <span data-ttu-id="36cc2-176">**Объекты, не включенные в DAC**: эти объекты не поддерживаются, и перед извлечением DAC их необходимо удалить из базы данных.</span><span class="sxs-lookup"><span data-stu-id="36cc2-176">**Objects not included in DAC**: these objects are not supported and must be removed from the database before successfully extracting a DAC.</span></span>  
  
 <span data-ttu-id="36cc2-177">Процесс проверки выполняется на нескольких уровнях зависимости.</span><span class="sxs-lookup"><span data-stu-id="36cc2-177">The validation process checks multiple levels of dependencies.</span></span> <span data-ttu-id="36cc2-178">Например, если хранимая процедура зависит от таблицы, использующей неподдерживаемый тип данных CLR, то хранимая процедура будет отображена в разделе **Объекты, включенные в DAC с предупреждениями**.</span><span class="sxs-lookup"><span data-stu-id="36cc2-178">For example, if a stored procedure depends on a table that uses the unsupported CLR data type, the stored procedure will be listed under **Objects included in DAC with warnings**.</span></span>  
  
 <span data-ttu-id="36cc2-179">Если один или несколько объектов не поддерживаются DAC, то кнопка **Далее** отключена и процесс извлечения не может быть продолжен.</span><span class="sxs-lookup"><span data-stu-id="36cc2-179">If one or more objects are not supported by a DAC, then the **Next** button is disabled and the extraction process will not continue.</span></span> <span data-ttu-id="36cc2-180">В таком случае рекомендуется удалить неподдерживаемые объекты и вновь запустить данный мастер.</span><span class="sxs-lookup"><span data-stu-id="36cc2-180">In such cases, it is recommended to remove the objects that are not supported and then run this wizard again.</span></span>  
  
 <span data-ttu-id="36cc2-181">**Сохранение отчета** — позволяет сохранить HTML-файл, в котором перечислены все объекты, находящиеся под узлом **Объекты приложения уровня данных** , в виде сводки.</span><span class="sxs-lookup"><span data-stu-id="36cc2-181">**Save Report** - Enables you to save an HTML-based file that lists all of the objects under the **DAC Objects** node in the summary.</span></span> <span data-ttu-id="36cc2-182">Этот отчет особенно полезен в тех случаях, когда некоторые из объектов базы данных не поддерживаются DAC.</span><span class="sxs-lookup"><span data-stu-id="36cc2-182">This report can be useful when some of your database objects are not supported in a DAC.</span></span> <span data-ttu-id="36cc2-183">Отчет поможет изменить или удалить неподдерживаемые объекты, прежде чем предпринять новую попытку извлечения DAC.</span><span class="sxs-lookup"><span data-stu-id="36cc2-183">Use the report to change or remove objects that are not supported, before trying to extract the DAC again.</span></span>  
  
###  <a name="build-package-page"></a><a name="BuildPackage"></a><span data-ttu-id="36cc2-184">Страница «сборка пакета»</span><span class="sxs-lookup"><span data-stu-id="36cc2-184">Build Package Page</span></span>  
 <span data-ttu-id="36cc2-185">Эта страница позволяет наблюдать за ходом выполнения мастером извлечения приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="36cc2-185">Use this page to monitor the progress of the wizard as it extracts the data-tier application (DAC).</span></span>  
  
 <span data-ttu-id="36cc2-186">**Действие** — во время выполнения действия **Создать и сохранить файл пакета приложения уровня данных** мастер извлекает приложение уровня данных из базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="36cc2-186">**Action** - During the **Create and save DAC package file** action, the wizard extracts a DAC from your SQL Server database.</span></span> <span data-ttu-id="36cc2-187">Затем пакет DAC создается в памяти и сохраняется в заданном местоположении.</span><span class="sxs-lookup"><span data-stu-id="36cc2-187">Then, a DAC package is created in memory and saved to the location you specified.</span></span> <span data-ttu-id="36cc2-188">Перейдите по ссылке в столбце **Результат** , чтобы просмотреть результат выполнения соответствующего шага.</span><span class="sxs-lookup"><span data-stu-id="36cc2-188">Click on the links in the **Result** column to see the outcome of the corresponding step.</span></span>  
  
 <span data-ttu-id="36cc2-189">**Сохранить отчет** — щелкните, чтобы сохранить результаты работы мастера в файле.</span><span class="sxs-lookup"><span data-stu-id="36cc2-189">**Save Report** - Click to save the results of the wizard's progress to a file.</span></span>  
  
 <span data-ttu-id="36cc2-190">**Готово** — закрыть мастер после завершения обработки или возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="36cc2-190">**Finish** - Click to close the wizard after processing has completed, or if an error occurs.</span></span>  
  
##  <a name="extract-a-dac-using-powershell"></a><a name="ExtractDACPowerShell"></a><span data-ttu-id="36cc2-191">Извлечение приложения уровня данных с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="36cc2-191">Extract a DAC Using PowerShell</span></span>  
 <span data-ttu-id="36cc2-192">**Извлечение приложения уровня данных из базы данных с помощью метода Extract() в скрипте PowerShell**</span><span class="sxs-lookup"><span data-stu-id="36cc2-192">**To extract a DAC from a database using the Extract() method in a PowerShell script**</span></span>  
  
1.  <span data-ttu-id="36cc2-193">Создайте объект SMO для сервера и присвойте ему экземпляр, где находится база данных, из которой должно быть извлечено приложение уровня данных.</span><span class="sxs-lookup"><span data-stu-id="36cc2-193">Create a SMO Server object and set it to the instance that contains the database from which the DAC is to be extracted.</span></span>  
  
2.  <span data-ttu-id="36cc2-194">Добавьте переменную, указывающую имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="36cc2-194">Add a variable that specifies the name of the database.</span></span>  
  
3.  <span data-ttu-id="36cc2-195">Укажите метаданные для приложения уровня данных, такие как имя, версия и описание приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="36cc2-195">Specify the metadata for the DAC, such as the DAC name, version, and description.</span></span>  
  
4.  <span data-ttu-id="36cc2-196">Укажите путь и имя файла извлеченного пакета DAC.</span><span class="sxs-lookup"><span data-stu-id="36cc2-196">Specify the path and file name for the extracted DAC package file.</span></span>  
  
5.  <span data-ttu-id="36cc2-197">Запустите метод Extract, передав ему вышеперечисленные данные.</span><span class="sxs-lookup"><span data-stu-id="36cc2-197">Run the Extract method with the information specified above.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="36cc2-198">Пример (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="36cc2-198">Example (PowerShell)</span></span>  
 <span data-ttu-id="36cc2-199">В следующем примере показано, как извлечь приложение уровня данных MyApplication из базы данных MyDB.</span><span class="sxs-lookup"><span data-stu-id="36cc2-199">The following example extracts a DAC named MyApplication from a database named MyDB.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Specify the database to extract to a DAC.  
$dbname = "MyDB"  
  
## Specify the DAC metadata.  
$applicationname = "MyApplication"  
$version = "1.0.0.0"  
$description = "This DAC defines the database used by my application."  
  
## Specify the location and name for the extracted DAC package.  
$dacpacPath = "C:\MyDACs\MyApplication.dacpac"  
  
## Extract the DAC.  
$extractionunit = New-Object Microsoft.SqlServer.Management.Dac.DacExtractionUnit($srv, $dbname, $applicationname, $version)  
$extractionunit.Description = $description  
$extractionunit.Extract($dacpacPath)  
```  
  
## <a name="see-also"></a><span data-ttu-id="36cc2-200">См. также:</span><span class="sxs-lookup"><span data-stu-id="36cc2-200">See Also</span></span>  
 [<span data-ttu-id="36cc2-201">Приложения уровня данных</span><span class="sxs-lookup"><span data-stu-id="36cc2-201">Data-tier Applications</span></span>](data-tier-applications.md)  
