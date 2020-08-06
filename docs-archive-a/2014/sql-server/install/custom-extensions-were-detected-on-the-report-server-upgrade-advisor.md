---
title: На сервере отчетов обнаружены пользовательские расширения (советник по переходу) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- rendering extensions [Reporting Services], custom extensions
- security extensions [Reporting Services]
- custom extensions [Reporting Services]
- data processing extensions [Reporting Services], custom extensions
- delivery extensions [Reporting Services]
ms.assetid: fa184bd7-11d6-4ea3-9249-bc1b13db49e5
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: e4be596ff0f110515155f2aa14dc00aceaf85efd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657484"
---
# <a name="custom-extensions-were-detected-on-the-report-server-upgrade-advisor"></a><span data-ttu-id="b56fe-102">На сервере отчетов обнаружены пользовательские расширения (советник по переходу)</span><span class="sxs-lookup"><span data-stu-id="b56fe-102">Custom extensions were detected on the report server (Upgrade Advisor)</span></span>
  <span data-ttu-id="b56fe-103">Помощник по обновлению обнаружил параметры пользовательских модулей в файлах конфигурации, что свидетельствует о наличии в установке одного или нескольких пользовательских модулей для обработки данных, доставки, подготовки к просмотру, безопасности или проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b56fe-103">Upgrade Advisor detected custom extension settings in the configuration files, indicating that your installation includes one or more custom extensions for data processing, delivery, rendering, security, or authentication.</span></span> <span data-ttu-id="b56fe-104">Во время обновления настройки конфигурации модулей будут перемещены вместе с обновленным сервером отчетов.</span><span class="sxs-lookup"><span data-stu-id="b56fe-104">Upgrade will move the extension configuration settings with the upgraded report server.</span></span> <span data-ttu-id="b56fe-105">Однако если пользовательские модули установлены в существующую папку установки сервера отчетов, то файлы сборки для этих пользовательских модулей не будут перемещены в новую папку установки в ходе процесса обновления.</span><span class="sxs-lookup"><span data-stu-id="b56fe-105">However, if the custom extensions are installed in the existing report server installation folder, the assembly files for those custom extensions will not be moved to the new installation folder during the upgrade process.</span></span> <span data-ttu-id="b56fe-106">После завершения обновления необходимо вручную поместить файлы сборки в новую папку установки служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b56fe-106">After upgrade completes, you must move the assembly files to the new [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation folder.</span></span>  
  
||  
|-|  
|<span data-ttu-id="b56fe-107">**[!INCLUDE[applies](../../includes/applies-md.md)]** [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Собственный режим &#124; [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Режим интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b56fe-107">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode &#124; [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="b56fe-108">Компонент</span><span class="sxs-lookup"><span data-stu-id="b56fe-108">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="b56fe-109">Описание</span><span class="sxs-lookup"><span data-stu-id="b56fe-109">Description</span></span>  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]<span data-ttu-id="b56fe-110">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]предоставляет расширяемую архитектуру, позволяющую разработчикам создавать пользовательские расширения для обработки данных, доставки, подготовки к просмотру, безопасности и проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b56fe-110">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] provides an extensible architecture that allows developers to create custom extensions for data processing, delivery, rendering, security, and authentication.</span></span>  
  
 <span data-ttu-id="b56fe-111">Если в установке служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] используются пользовательские модули или сборки, для обновления можно использовать программу установки. В этом случае необходимо переместить модули в новую папку установки после завершения обновления, в обратном случае придется выполнить все шаги до обновления.</span><span class="sxs-lookup"><span data-stu-id="b56fe-111">If custom extensions or assemblies are used in your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation, you can use Setup to perform an upgrade, but you may need to move extensions to the new installation location after upgrade completes, or you may need to perform steps prior to upgrade.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b56fe-112">Помощник по обновлению не обнаруживает того, что пользовательские сборки кода настроены на использование в отчетах для расчета значений элементов, стилей и форматирования.</span><span class="sxs-lookup"><span data-stu-id="b56fe-112">Upgrade Advisor does not detect whether custom code assemblies are configured for use in reports to calculate item values, styles, and formatting.</span></span> <span data-ttu-id="b56fe-113">Дополнительные сведения см. в разделе [другие проблемы, связанные с обновлением Reporting Services](../../../2014/sql-server/install/other-reporting-services-upgrade-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b56fe-113">For more information, see [Other Reporting Services Upgrade Issues](../../../2014/sql-server/install/other-reporting-services-upgrade-issues.md).</span></span>  
  
 <span data-ttu-id="b56fe-114">Если были приобретены специализированные модули у поставщика программного обеспечения, запросите у этого поставщика дополнительные сведения об обновлении специальной функциональности.</span><span class="sxs-lookup"><span data-stu-id="b56fe-114">If you purchased custom extensions from a software vendor, check with the vendor for additional information about upgrading your custom functionality.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="b56fe-115">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="b56fe-115">Corrective Action</span></span>  
 <span data-ttu-id="b56fe-116">В следующих разделах приведены дополнительные шаги, которые необходимо выполнить до обновления служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="b56fe-116">Use the following sections to determine steps to perform in addition to or prior to performing an upgrade of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]:</span></span>  
  
 [<span data-ttu-id="b56fe-117">Пользовательские модули обработки данных или доставки</span><span class="sxs-lookup"><span data-stu-id="b56fe-117">Custom data processing or delivery extensions</span></span>](#dataprocdeliver)  
  
 [<span data-ttu-id="b56fe-118">Пользовательские модули подготовки отчетов к просмотру</span><span class="sxs-lookup"><span data-stu-id="b56fe-118">Custom rendering extensions</span></span>](#render)  
  
 [<span data-ttu-id="b56fe-119">Пользовательские модули безопасности или проверки подлинности на сервере отчетов SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="b56fe-119">Custom security or authentication extensions on a SQL Server 2000 report server</span></span>](#secauth2000)  
  
 [<span data-ttu-id="b56fe-120">Пользовательские модули для безопасности или проверки подлинности на сервере отчетов SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="b56fe-120">Custom security or authentication extensions on a SQL Server 2005 report server</span></span>](#secauth2005)  
  
 <span data-ttu-id="b56fe-121">После завершения обновления переместите сборки модулей в новую папку установки. Затем убедитесь, что пользовательские модули работают так, как положено.</span><span class="sxs-lookup"><span data-stu-id="b56fe-121">After upgrade completes, move the extension assemblies to the new installation folder and then verify that the custom extensions work as expected.</span></span> <span data-ttu-id="b56fe-122">Если модуль не работает, возможно, его необходимо перекомпилировать.</span><span class="sxs-lookup"><span data-stu-id="b56fe-122">If your extension does not work, you might have to recompile it.</span></span>  
  
#### <a name="to-recompile-an-extension"></a><span data-ttu-id="b56fe-123">Перекомпилирование модуля</span><span class="sxs-lookup"><span data-stu-id="b56fe-123">To recompile an extension</span></span>  
  
1.  <span data-ttu-id="b56fe-124">скопируйте файл Microsoft.ReportingServices.Interfaces.dll в папку, содержащую пользовательский исходный текст;</span><span class="sxs-lookup"><span data-stu-id="b56fe-124">Copy the Microsoft.ReportingServices.Interfaces.dll file to the folder that contains your source code.</span></span>  
  
2.  <span data-ttu-id="b56fe-125">откройте проект, содержащий исходные файлы, и добавьте ссылку на файл Microsoft.ReportingServices.Interfaces.dll;</span><span class="sxs-lookup"><span data-stu-id="b56fe-125">Open the project that contains your source files and add a reference to the Microsoft.ReportingServices.Interfaces.dll file.</span></span>  
  
3.  <span data-ttu-id="b56fe-126">перестройте решение, чтобы привязать модуль.</span><span class="sxs-lookup"><span data-stu-id="b56fe-126">Rebuild the solution to bind the extension.</span></span>  
  
 <span data-ttu-id="b56fe-127">Если принято решение не продолжать обновление, вместо этого можно предпринять миграцию на службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b56fe-127">If you decide not to continue with upgrade, you might decide to migrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instead.</span></span> <span data-ttu-id="b56fe-128">Инструкции по переносу пользовательских расширений см. в разделе [Миграция пользовательских расширений](#migrcustext) этого раздела.</span><span class="sxs-lookup"><span data-stu-id="b56fe-128">For steps on migrating custom extensions, see [Migrating custom extensions](#migrcustext) in this topic.</span></span>  
  
###  <a name="custom-data-processing-or-delivery-extensions"></a><a name="dataprocdeliver"></a><span data-ttu-id="b56fe-129">Пользовательские модули обработки данных или доставки</span><span class="sxs-lookup"><span data-stu-id="b56fe-129">Custom data processing or delivery extensions</span></span>  
 <span data-ttu-id="b56fe-130">Если помощник по обновлению обнаруживает пользовательские модули для обработки данных или доставки, то процесс обновления не блокируется.</span><span class="sxs-lookup"><span data-stu-id="b56fe-130">If Upgrade Advisor detects custom data processing or delivery extensions, the upgrade process is not blocked.</span></span> <span data-ttu-id="b56fe-131">Однако после завершения обновления, вероятно, придется выполнить дополнительные шаги до того, как пользовательские функции этих модулей начнут работать.</span><span class="sxs-lookup"><span data-stu-id="b56fe-131">However, after upgrade completes, you might need to perform additional steps before the custom functionality provided by these extensions will work.</span></span> <span data-ttu-id="b56fe-132">Например, дополнительные шаги необходимо выполнить, если файлы пользовательских модулей установлены в папку установки служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b56fe-132">For example, you must perform additional steps when the custom extension files are installed in the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation folder.</span></span>  
  
##### <a name="post-upgrade-steps-for-custom-data-processing-or-delivery-extensions"></a><span data-ttu-id="b56fe-133">Шаги для пользовательских модулей обработки данных или доставки, следующие за обновлением</span><span class="sxs-lookup"><span data-stu-id="b56fe-133">Post-upgrade steps for custom data processing or delivery extensions</span></span>  
  
1.  <span data-ttu-id="b56fe-134">Переместите файлы модуля в новую программную папку для сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="b56fe-134">Move the extension file or files to the new program folder for the report server.</span></span> <span data-ttu-id="b56fe-135">По умолчанию папка программы сервера отчетов находится в папке \Program Files\Microsoft SQL Server \ MSRS10_50. \<*instance_name*> сервер папке \Report.</span><span class="sxs-lookup"><span data-stu-id="b56fe-135">By default, the report server program folder is in \Program Files\Microsoft SQL Server\MSRS10_50.\<*instance_name*>\report server.</span></span>  
  
 <span data-ttu-id="b56fe-136">Дополнительные сведения см. в разделах «Развертывание модуля обработки данных» и «Применение модуля доставки» в электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b56fe-136">For more information, see "Deploying a Data Processing Extension" and "Implementing a Delivery Extension" in SQL Server Books Online.</span></span>  
  
###  <a name="custom-rendering-extensions"></a><a name="render"></a><span data-ttu-id="b56fe-137">Пользовательские модули подготовки отчетов</span><span class="sxs-lookup"><span data-stu-id="b56fe-137">Custom rendering extensions</span></span>  
 <span data-ttu-id="b56fe-138">Если помощник по обновлению обнаруживает пользовательские модули подготовки отчетов к просмотру, процесс обновления блокируется.</span><span class="sxs-lookup"><span data-stu-id="b56fe-138">If Upgrade Advisor detects custom rendering extensions, the upgrade process is blocked.</span></span> <span data-ttu-id="b56fe-139">Процесс обновления можно продолжить, удалив записи конфигурации пользовательского модуля из файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b56fe-139">You can continue with the upgrade process by removing the custom extension configuration entries from the configuration file.</span></span> <span data-ttu-id="b56fe-140">Однако это приведет к тому, что после завершения обновления пользовательский модуль станет недоступен для пользователей.</span><span class="sxs-lookup"><span data-stu-id="b56fe-140">However, this will cause the custom extensions to be unavailable to users after upgrade completes.</span></span> <span data-ttu-id="b56fe-141">Если потребность в пользовательских модулях подготовки отчетов к просмотру остается после обновления, необходимо создать пользовательские модули подготовки отчетов к просмотру или получить обновленные пользовательские модули подготовки отчетов у поставщика этих модулей.</span><span class="sxs-lookup"><span data-stu-id="b56fe-141">If you need custom rendering extensions after upgrade, you must build updated rendering extensions or obtain updated rendering extensions from a custom extension vendor.</span></span>  
  
 <span data-ttu-id="b56fe-142">Для проведения обновления необходимо выполнить определенные шаги либо вместо этого провести миграцию на службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b56fe-142">You must perform steps to enable an upgrade or you may chose to migrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instead.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b56fe-143">Не выполняйте обновление или миграцию сервера отчетов до тех пор, пока не убедитесь и не проверите, что обновленные модули подготовки отчетов работают должным образом.</span><span class="sxs-lookup"><span data-stu-id="b56fe-143">Do not upgrade or migrate your report server until you have tested and verified that the updated rendering extension works as expected.</span></span>  
  
##### <a name="to-upgrade-custom-rendering-extensions"></a><span data-ttu-id="b56fe-144">Обновление пользовательских модулей подготовки отчетов к просмотру</span><span class="sxs-lookup"><span data-stu-id="b56fe-144">To upgrade custom rendering extensions</span></span>  
  
1.  <span data-ttu-id="b56fe-145">Получите модули подготовки отчетов к просмотру с последними версиями интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b56fe-145">Obtain rendering extensions with the latest interfaces.</span></span>  
  
2.  <span data-ttu-id="b56fe-146">Удалите старые записи пользовательского модуля подготовки отчетов к просмотру из файла конфигурации RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="b56fe-146">Remove the old custom rendering extension entry or entries from RSReportServer.config.</span></span>  
  
3.  <span data-ttu-id="b56fe-147">Обновите сервер отчетов.</span><span class="sxs-lookup"><span data-stu-id="b56fe-147">Upgrade the report server.</span></span>  
  
4.  <span data-ttu-id="b56fe-148">После завершения обновления установите обновленные модули на сервер отчетов.</span><span class="sxs-lookup"><span data-stu-id="b56fe-148">After upgrade completes, install the updated extensions on the report server.</span></span>  
  
 <span data-ttu-id="b56fe-149">Дополнительные сведения см. в разделе «Применение модуля подготовки отчетов к просмотру» в электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b56fe-149">For more information, see "Implementing a Rendering Extension" in SQL Server Books Online.</span></span>  
  
###  <a name="custom-security-or-authentication-extensions-on-a-sql-server-2000-report-server"></a><a name="secauth2000"></a><span data-ttu-id="b56fe-150">Пользовательские модули безопасности или проверки подлинности на сервере отчетов SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="b56fe-150">Custom security or authentication extensions on a SQL Server 2000 report server</span></span>  
 <span data-ttu-id="b56fe-151">Если помощник по обновлению обнаруживает пользовательские модули безопасности или проверки подлинности на сервере отчетов [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], процесс обновления блокируется.</span><span class="sxs-lookup"><span data-stu-id="b56fe-151">If Upgrade Advisor detects custom security or authentication extensions on a [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] report server, the upgrade process is blocked.</span></span> <span data-ttu-id="b56fe-152">Для проведения обновления необходимо выполнить определенные шаги либо вместо этого провести миграцию на службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b56fe-152">You must perform steps to enable an upgrade or you may chose to migrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instead.</span></span> <span data-ttu-id="b56fe-153">В противном случае необходимо обновить и перекомпилировать модули с использованием последних версий интерфейсов в файле Microsoft.ReportingServices.Interfaces.dll, т. к. интерфейсы в [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] изменились с версии [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b56fe-153">In either case, you must update and recompile the extensions with the latest interfaces in Microsoft.ReportingServices.Interfaces.dll, because the interfaces have changed between [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b56fe-154">Не выполняйте обновление или миграцию сервера отчетов до тех пор, пока не убедитесь и не проверите, что обновленные модули безопасности и проверки подлинности работают должным образом.</span><span class="sxs-lookup"><span data-stu-id="b56fe-154">Do not upgrade or migrate your report server until you have tested and verified that the updated security or authentication extension works as expected.</span></span>  
  
 <span data-ttu-id="b56fe-155">Если используется нестандартный модуль проверки подлинности, созданный для служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2000 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], необходимо изменить исходный текст для поддержки новых классов и элементов, введенных для отчетов на основе модели.</span><span class="sxs-lookup"><span data-stu-id="b56fe-155">If you are using a custom authentication extension that you created for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2000 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you must modify the source code to support new classes and members introduced for model-driven reporting.</span></span>  
  
##### <a name="to-upgrade-custom-security-or-authentication-extensions-from-a-sql-server-2000-report-server"></a><span data-ttu-id="b56fe-156">Обновление пользовательских модулей безопасности или проверки подлинности с сервера отчетов SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="b56fe-156">To upgrade custom security or authentication extensions from a SQL Server 2000 report server</span></span>  
  
1.  <span data-ttu-id="b56fe-157">Обновите и перекомпилируйте все модули безопасности или проверки подлинности с использованием последних версий интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="b56fe-157">Update and recompile any security or authentication extensions with the latest interfaces.</span></span>  
  
2.  <span data-ttu-id="b56fe-158">Удалите записи модулей безопасности или проверки подлинности из файла конфигурации RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="b56fe-158">Remove the security or authentication extension entry or entries from RSReportServer.config.</span></span>  
  
3.  <span data-ttu-id="b56fe-159">Обновите сервер отчетов.</span><span class="sxs-lookup"><span data-stu-id="b56fe-159">Upgrade the report server.</span></span>  
  
4.  <span data-ttu-id="b56fe-160">После завершения обновления установите обновленные модули на сервер отчетов.</span><span class="sxs-lookup"><span data-stu-id="b56fe-160">After upgrade completes, install the updated extensions on the report server.</span></span>  
  
 <span data-ttu-id="b56fe-161">Дополнительные сведения см. в разделе «Применение модуля безопасности» в электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b56fe-161">For more information, see "Implementing a Security Extension" in SQL Server Books Online.</span></span>  
  
###  <a name="custom-security-or-authentication-extensions-on-a-sql-server-2005-report-server"></a><a name="secauth2005"></a><span data-ttu-id="b56fe-162">Пользовательские модули безопасности или проверки подлинности на сервере отчетов SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="b56fe-162">Custom security or authentication extensions on a SQL Server 2005 report server</span></span>  
 <span data-ttu-id="b56fe-163">Если помощник по обновлению обнаруживает пользовательские модули безопасности или проверки подлинности на сервере отчетов [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], процесс обновления блокируется.</span><span class="sxs-lookup"><span data-stu-id="b56fe-163">If Upgrade Advisor detects custom security or authentication extensions on a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] report server, the upgrade process is blocked.</span></span> <span data-ttu-id="b56fe-164">Для проведения обновления необходимо выполнить определенные шаги либо вместо этого провести миграцию на службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b56fe-164">You must perform steps to enable an upgrade or you may chose to migrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instead.</span></span>  
  
##### <a name="to-upgrade-custom-security-or-authentication-extensions-from-a-sql-server-2005-report-server"></a><span data-ttu-id="b56fe-165">Обновление пользовательских модулей безопасности или проверки подлинности на сервере отчетов SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="b56fe-165">To upgrade custom security or authentication extensions from a SQL Server 2005 report server</span></span>  
  
1.  <span data-ttu-id="b56fe-166">Удалите записи конфигурации модуля безопасности или проверки подлинности из файла конфигурации RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="b56fe-166">Remove the security or authentication extension configuration entries from RSReportServer.config.</span></span>  
  
2.  <span data-ttu-id="b56fe-167">Обновите сервер отчетов.</span><span class="sxs-lookup"><span data-stu-id="b56fe-167">Upgrade the report server.</span></span>  
  
3.  <span data-ttu-id="b56fe-168">После завершения обновления заново добавьте записи конфигурации в файл конфигурации RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="b56fe-168">After upgrade completes, add the configuration entries back in RSReportServer.config.</span></span>  
  
4.  <span data-ttu-id="b56fe-169">Если сборки модулей установлены в старую папку установки служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], переместите их в новую папку установки.</span><span class="sxs-lookup"><span data-stu-id="b56fe-169">If the extension assemblies were installed in the old [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation folder, move then to the new installation folder.</span></span>  
  
 <span data-ttu-id="b56fe-170">Дополнительные сведения см. в разделе «Применение модуля безопасности» в электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b56fe-170">For more information, see "Implementing a Security Extension" in SQL Server Books Online.</span></span>  
  
###  <a name="migrating-custom-extensions"></a><a name="migrcustext"></a><span data-ttu-id="b56fe-171">Миграция пользовательских расширений</span><span class="sxs-lookup"><span data-stu-id="b56fe-171">Migrating custom extensions</span></span>  
 <span data-ttu-id="b56fe-172">Если принято решение провести миграцию на службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] вместо обновления, выполните определенные шаги, чтобы провести миграцию пользовательских модулей в новый экземпляр служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b56fe-172">If you decide to migrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instead performing an upgrade, use the steps to migrate custom extensions to the new [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance.</span></span>  
  
##### <a name="to-migrate-custom-extensions-to-a-new-reporting-services-instance"></a><span data-ttu-id="b56fe-173">Миграция пользовательских модулей в новый экземпляр служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="b56fe-173">To migrate custom extensions to a new Reporting Services instance</span></span>  
  
1.  <span data-ttu-id="b56fe-174">Создайте или получите обновленные модули с последними версиями интерфейсов служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b56fe-174">Build or obtain updated extensions with the latest [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] interfaces.</span></span>  
  
2.  <span data-ttu-id="b56fe-175">Проведите миграцию сервера отчетов в новый экземпляр.</span><span class="sxs-lookup"><span data-stu-id="b56fe-175">Migrate the report server to a new instance.</span></span>  
  
3.  <span data-ttu-id="b56fe-176">Настройте модули в новом экземпляре.</span><span class="sxs-lookup"><span data-stu-id="b56fe-176">Configure the extensions on the new instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b56fe-177">См. также:</span><span class="sxs-lookup"><span data-stu-id="b56fe-177">See Also</span></span>  
 [<span data-ttu-id="b56fe-178">Reporting Services проблем обновления &#40;советник по переходу&#41;</span><span class="sxs-lookup"><span data-stu-id="b56fe-178">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
