---
title: Установка изолированной версии построитель отчетов (построитель отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6b2291bb-1d20-4d08-81cb-a16dd8e01faf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2ba8c132125f56ad833a71a1c82221e2bf28d13e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665849"
---
# <a name="install-the-stand-alone-version-of-report-builder-report-builder"></a><span data-ttu-id="5caa1-102">Установка изолированной версии построителя отчетов (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="5caa1-102">Install the Stand-Alone Version of Report Builder (Report Builder)</span></span>
  <span data-ttu-id="5caa1-103">Вы можете установить построитель отчетов из [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] пакета дополнительных компонентов в [центре загрузки Майкрософт](https://www.microsoft.com/download/details.aspx?id=53613) или в папку, например общую папку, в которую ReportBuilder3_x86.msi, пакет установщик Windows для построитель отчетов, загружен.</span><span class="sxs-lookup"><span data-stu-id="5caa1-103">You can install Report Builder from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] feature pack on the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53613) or a location such as public folder to which the ReportBuilder3_x86.msi, the Windows Installer Package for Report Builder, has been downloaded.</span></span>  
  
 <span data-ttu-id="5caa1-104">Также можно установить построитель отчетов из командной строки, задав аргументы для настройки установки.</span><span class="sxs-lookup"><span data-stu-id="5caa1-104">You can also perform a command line installation of Report Builder and provide arguments to customize the installation.</span></span> <span data-ttu-id="5caa1-105">Помимо стандартных встроенных параметров MSI можно использовать пользовательские параметры, которые построитель отчетов предоставляет: RBINSTALLDIR и REPORTSERVERURL.</span><span class="sxs-lookup"><span data-stu-id="5caa1-105">In addition to the standard MSI intrinsic parameters, you can use the custom parameters that Report Builder provides: RBINSTALLDIR and REPORTSERVERURL.</span></span> <span data-ttu-id="5caa1-106">RBINSTALLDIR указывает корневой каталог установки для построителя отчетов.</span><span class="sxs-lookup"><span data-stu-id="5caa1-106">RBINSTALLDIR specifies the root installation folder for Report Builder.</span></span> <span data-ttu-id="5caa1-107">REPORTSERVERURL указывает сервер отчетов по умолчанию, используемый построителем отчетов для сохранения отчетов на сервере.</span><span class="sxs-lookup"><span data-stu-id="5caa1-107">REPORTSERVERURL specifies the default report server that Report Builder uses to save reports on the server.</span></span>  
  
 <span data-ttu-id="5caa1-108">Если необходимо произвести установку в полностью автоматическом режиме, без какого-либо взаимодействия с пользовательским интерфейсом, укажите параметр **/quiet** .</span><span class="sxs-lookup"><span data-stu-id="5caa1-108">If you want a completely silent installation, with no user interface interaction at all, specify the **/quiet** option.</span></span> <span data-ttu-id="5caa1-109">Флаг параметра подавляет сообщения об ошибках установки.</span><span class="sxs-lookup"><span data-stu-id="5caa1-109">By design, the quiet option flag suppresses installation errors.</span></span> <span data-ttu-id="5caa1-110">В связи с этим при использовании автоматической установки рекомендуется включить параметр **/l** , указывающий необходимость ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="5caa1-110">It is therefore recommended that you include the **/l** option, which specifies logging, when you use the quiet option.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5caa1-111">Для запуска операций из командной строки в Windows Vista и Windows 7 требуются повышенные разрешения безопасности; эти ОС будут запрашивать разрешения на выполнение командной строки.</span><span class="sxs-lookup"><span data-stu-id="5caa1-111">Windows Vista and Windows 7 security features require elevated permissions to run command line operations and will prompt for permission to run the command line.</span></span> <span data-ttu-id="5caa1-112">Эта установка выполняется не автоматически.</span><span class="sxs-lookup"><span data-stu-id="5caa1-112">The installation is not silent.</span></span> <span data-ttu-id="5caa1-113">Для проведения автоматической установки необходимо запустить командную строку от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="5caa1-113">To make the installation silent, you need to run the command line as an administrator.</span></span>  
  
### <a name="to-install-report-builder-from-the-download-site"></a><span data-ttu-id="5caa1-114">Установка построителя отчетов с сайта загрузки</span><span class="sxs-lookup"><span data-stu-id="5caa1-114">To install Report Builder from the download site</span></span>  
  
1.  <span data-ttu-id="5caa1-115">Перейдите в [Microsoft SQL Server 2012 построитель отчетов](https://go.microsoft.com/fwlink/?LinkID=219138) и найдите раздел построитель отчетов на веб-странице.</span><span class="sxs-lookup"><span data-stu-id="5caa1-115">Go to [Microsoft SQL Server 2012 Report Builder](https://go.microsoft.com/fwlink/?LinkID=219138) and locate the Report Builder section of the Web page.</span></span>  
  
2.  <span data-ttu-id="5caa1-116">Щелкните **пакет x86**.</span><span class="sxs-lookup"><span data-stu-id="5caa1-116">Click **X86 Package**.</span></span>  
  
3.  <span data-ttu-id="5caa1-117">В диалоговом окне **Загрузка файла** нажмите кнопку **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="5caa1-117">In the **File Download** dialog box, click **Run**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="5caa1-118">Файлы следует загружать только из доверенных источников.</span><span class="sxs-lookup"><span data-stu-id="5caa1-118">Download only files from trusted sources.</span></span>  
  
4.  <span data-ttu-id="5caa1-119">В диалоговом окне Internet Explorer нажмите кнопку **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="5caa1-119">In the Internet Explorer dialog box, click **Run**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="5caa1-120">Файлы следует запускать только из доверенных источников.</span><span class="sxs-lookup"><span data-stu-id="5caa1-120">Run only files from trusted sources.</span></span>  
  
5.  <span data-ttu-id="5caa1-121">Будет запущен мастер построителя отчетов Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5caa1-121">The Microsoft SQL Server Report Builder Wizard is launched.</span></span>  
  
6.  <span data-ttu-id="5caa1-122">На странице **приветствия мастера установки** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5caa1-122">On the **Welcome to the Installation Wizard** page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="5caa1-123">На странице **лицензионное соглашение** прочтите соглашение и выберите параметр **я принимаю условия лицензионного соглашения** .</span><span class="sxs-lookup"><span data-stu-id="5caa1-123">On the **License Agreement** page, read the agreement and then select the **I accept the terms in the license agreement** option.</span></span> <span data-ttu-id="5caa1-124">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5caa1-124">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="5caa1-125">Приведите свое личное имя и имя компании.</span><span class="sxs-lookup"><span data-stu-id="5caa1-125">Provide your personal name and company name.</span></span> <span data-ttu-id="5caa1-126">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5caa1-126">Click **Next**.</span></span>  
  
9. <span data-ttu-id="5caa1-127">На странице **Выбор компонентов** при необходимости нажмите кнопку **Обзор** или **Стоимость диска**.</span><span class="sxs-lookup"><span data-stu-id="5caa1-127">On the **Feature Selection** page, optionally click **Browse** or **Disk Cost**.</span></span> <span data-ttu-id="5caa1-128">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5caa1-128">Click **Next**.</span></span>  
  
    -   <span data-ttu-id="5caa1-129">Нажмите кнопку **Обзор** , чтобы просмотреть расположение построитель отчетов по умолчанию и обновите его.</span><span class="sxs-lookup"><span data-stu-id="5caa1-129">Click **Browse** to see the default location of Report Builder and update it.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="5caa1-130">Папка установки по умолчанию для построитель отчетов — \<drive> Program Files\Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5caa1-130">The default installation folder for Report Builder is \<drive>Program Files\Microsoft SQL Server.</span></span>  
  
    -   <span data-ttu-id="5caa1-131">Щелкните **затраты на диск** , чтобы узнать, сколько места на диске построитель отчетов потребляется.</span><span class="sxs-lookup"><span data-stu-id="5caa1-131">Click **Disk Cost** to learn how much disk space Report Builder consumes.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="5caa1-132">Если на томе недостаточно свободного места, то он будет выделен.</span><span class="sxs-lookup"><span data-stu-id="5caa1-132">If a volume does not have sufficient amount of free disk space, the volume is highlighted.</span></span>  
  
10. <span data-ttu-id="5caa1-133">На странице **Целевой сервер по умолчанию** можно по желанию привести URL-адрес целевого сервера отчетов, если он отличается от адреса по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5caa1-133">On the **Default Target Server** page, optionally provide the URL to the target report server if it is different from the default.</span></span> <span data-ttu-id="5caa1-134">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5caa1-134">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5caa1-135">Если планируется работать с построителем отчетов в соединении с сервером отчетов, то будет удобнее предоставить URL-адрес сервера на данном этапе.</span><span class="sxs-lookup"><span data-stu-id="5caa1-135">If you plan to work with Report Builder when it is connected to a report server, it is convenient to provide the URL to the server at this time.</span></span> <span data-ttu-id="5caa1-136">Однако это можно также сделать в диалоговом окне " **Параметры** " при работе в построитель отчетов.</span><span class="sxs-lookup"><span data-stu-id="5caa1-136">However, you can also do this from the **Options** dialog box when you are working in Report Builder.</span></span>  
  
11. <span data-ttu-id="5caa1-137">Нажмите кнопку **установить** , чтобы завершить установку построитель отчетов.</span><span class="sxs-lookup"><span data-stu-id="5caa1-137">Click **Install** to complete the installation of Report Builder.</span></span>  
  
### <a name="to-install-report-builder-from-a-share"></a><span data-ttu-id="5caa1-138">Установка построителя отчетов из общей папки</span><span class="sxs-lookup"><span data-stu-id="5caa1-138">To install Report Builder from a share</span></span>  
  
1.  <span data-ttu-id="5caa1-139">Свяжитесь с администратором, чтобы узнать расположение файла ReportBuilder3_x86.msi.msi, который нужно запустить для установки построителя отчетов на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5caa1-139">Contact your administrator for the location of ReportBuilder3_x86.msi.msi that you run to install Report Builder on your local computer.</span></span>  
  
2.  <span data-ttu-id="5caa1-140">Перейдите к файлу ReportBuilder3_x86.msi.msi, который представляет собой пакет установщика Windows (MSI) для построителя отчетов, и щелкните его.</span><span class="sxs-lookup"><span data-stu-id="5caa1-140">Browse to locate the ReportBuilder3_x86.msi.msi, the Windows Installer Package (MSI) for Report Builder, and click it.</span></span>  
  
     <span data-ttu-id="5caa1-141">Будет запущен мастер построителя отчетов Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5caa1-141">The Microsoft SQL Server Report Builder Wizard is launched.</span></span>  
  
3.  <span data-ttu-id="5caa1-142">На странице **приветствия мастера установки** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5caa1-142">On the **Welcome to the Installation Wizard** page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="5caa1-143">На странице **лицензионное соглашение** прочтите соглашение и выберите параметр **я принимаю условия лицензионного соглашения** .</span><span class="sxs-lookup"><span data-stu-id="5caa1-143">On the **License Agreement** page, read the agreement and then select the **I accept the terms in the license agreement** option.</span></span> <span data-ttu-id="5caa1-144">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5caa1-144">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="5caa1-145">Приведите свое личное имя и имя компании.</span><span class="sxs-lookup"><span data-stu-id="5caa1-145">Provide your personal name and company name.</span></span> <span data-ttu-id="5caa1-146">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5caa1-146">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="5caa1-147">На странице **Выбор компонентов** при необходимости нажмите кнопку **Обзор** или **Стоимость диска**.</span><span class="sxs-lookup"><span data-stu-id="5caa1-147">On the **Feature Selection** page, optionally click **Browse** or **Disk Cost**.</span></span> <span data-ttu-id="5caa1-148">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5caa1-148">Click **Next**.</span></span>  
  
    -   <span data-ttu-id="5caa1-149">Нажмите кнопку **Обзор** , чтобы просмотреть расположение построитель отчетов по умолчанию и обновите его.</span><span class="sxs-lookup"><span data-stu-id="5caa1-149">Click **Browse** to see the default location of Report Builder and update it.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="5caa1-150">Папка установки по умолчанию для построитель отчетов — \<drive> Program Files\Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5caa1-150">The default installation folder for Report Builder is \<drive>Program Files\Microsoft SQL Server.</span></span>  
  
    -   <span data-ttu-id="5caa1-151">Щелкните **затраты на диск** , чтобы узнать, сколько места на диске построитель отчетов потребляется.</span><span class="sxs-lookup"><span data-stu-id="5caa1-151">Click **Disk Cost** to learn how much disk space Report Builder consumes.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="5caa1-152">Если на томе недостаточно свободного места, то он будет выделен.</span><span class="sxs-lookup"><span data-stu-id="5caa1-152">If a volume does not have sufficient amount of free disk space, the volume is highlighted.</span></span>  
  
7.  <span data-ttu-id="5caa1-153">На странице **Целевой сервер по умолчанию** можно по желанию привести URL-адрес целевого сервера отчетов, если он отличается от адреса по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5caa1-153">On the **Default Target Server** page, optionally provide the URL to the target report server if it is different from the default.</span></span> <span data-ttu-id="5caa1-154">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5caa1-154">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5caa1-155">Если планируется работать с построителем отчетов в соединении с сервером отчетов, то будет удобнее предоставить URL-адрес сервера на данном этапе.</span><span class="sxs-lookup"><span data-stu-id="5caa1-155">If you plan to work with Report Builder when it is connected to a report server, it is convenient to provide the URL to the server at this time.</span></span> <span data-ttu-id="5caa1-156">Однако это можно также сделать в диалоговом окне " **Параметры** " при работе в построитель отчетов.</span><span class="sxs-lookup"><span data-stu-id="5caa1-156">However, you can also do this from the **Options** dialog box when you are working in Report Builder.</span></span>  
  
8.  <span data-ttu-id="5caa1-157">Нажмите кнопку **установить** , чтобы завершить установку построитель отчетов.</span><span class="sxs-lookup"><span data-stu-id="5caa1-157">Click **Install** to complete the installation of Report Builder.</span></span>  
  
### <a name="to-install-report-builder-from-the-command-line"></a><span data-ttu-id="5caa1-158">Установка построителя отчетов из командной строки</span><span class="sxs-lookup"><span data-stu-id="5caa1-158">To install Report Builder from the command line</span></span>  
  
1.  <span data-ttu-id="5caa1-159">Перейдите по адресу [Microsoft SQL Server 2012 построитель отчетов](https://go.microsoft.com/fwlink/?LinkID=219138) и найдите раздел построитель отчетов.</span><span class="sxs-lookup"><span data-stu-id="5caa1-159">Go to [Microsoft SQL Server 2012 Report Builder](https://go.microsoft.com/fwlink/?LinkID=219138) and locate the Report Builder section.</span></span>  
  
2.  <span data-ttu-id="5caa1-160">Щелкните **пакет x86**.</span><span class="sxs-lookup"><span data-stu-id="5caa1-160">Click **X86 Package**.</span></span>  
  
3.  <span data-ttu-id="5caa1-161">Нажмите кнопку «Сохранить».</span><span class="sxs-lookup"><span data-stu-id="5caa1-161">Click Save.</span></span>  
  
4.  <span data-ttu-id="5caa1-162">При необходимости перейдите в расположение для сохранения, убедитесь, что выбран параметр **Сохранить как** **установщик Windows пакет**, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="5caa1-162">Optionally, browse to the location to save to, verify the **Save as** option is **Windows Installer Package**, and then click **Save**.</span></span>  
  
5.  <span data-ttu-id="5caa1-163">В меню **Пуск** выберите команду **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="5caa1-163">On the **Start** menu, click **Run**.</span></span>  
  
6.  <span data-ttu-id="5caa1-164">В текстовом поле Открыть введите .`cmd.`</span><span class="sxs-lookup"><span data-stu-id="5caa1-164">In the Open text box, type `cmd.`</span></span>  
  
7.  <span data-ttu-id="5caa1-165">В окне командной строки перейдите к папке, в которой был сохранен файл ReportBuilder3_x86.msi.</span><span class="sxs-lookup"><span data-stu-id="5caa1-165">In the Command Prompt window, navigate to the folder where you saved ReportBuilder3_x86.msi.</span></span>  
  
8.  <span data-ttu-id="5caa1-166">Введите команду в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="5caa1-166">Type a command with the following format:</span></span>  
  
     `msiexec/i ReportBuilder3_.msi /option [value] [/option [value]]`  
  
     <span data-ttu-id="5caa1-167">Для установки построитель отчетов доступны два варианта: RBINSTALLDIR и REPORTSERVERURL.</span><span class="sxs-lookup"><span data-stu-id="5caa1-167">The two options specific to installing Report Builder are: RBINSTALLDIR and REPORTSERVERURL.</span></span> <span data-ttu-id="5caa1-168">Присутствие этих аргументов в командной строке необязательно.</span><span class="sxs-lookup"><span data-stu-id="5caa1-168">It not required that you include these arguments in the command line.</span></span> <span data-ttu-id="5caa1-169">Ниже приведена базовая команда:</span><span class="sxs-lookup"><span data-stu-id="5caa1-169">The following is the baseline command:</span></span>  
  
     `msiexec /i ReportBuilder3_x86.msi /quiet`  
  
9. <span data-ttu-id="5caa1-170">Нажмите клавишу ВВОД, чтобы выполнить команду.</span><span class="sxs-lookup"><span data-stu-id="5caa1-170">To run the command, press Enter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5caa1-171">См. также:</span><span class="sxs-lookup"><span data-stu-id="5caa1-171">See Also</span></span>  
 <span data-ttu-id="5caa1-172">[Поддержка установки, удаления и построитель отчетов](../install-uninstall-and-report-builder-support.md) </span><span class="sxs-lookup"><span data-stu-id="5caa1-172">[Install, Uninstall, and Report Builder Support](../install-uninstall-and-report-builder-support.md) </span></span>  
 [<span data-ttu-id="5caa1-173">Удалите изолированную версию построитель отчетов &#40;построитель отчетов&#41;</span><span class="sxs-lookup"><span data-stu-id="5caa1-173">Uninstall the Stand-Alone Version of Report Builder &#40;Report Builder&#41;</span></span>](install-report-builder.md)  
  
  
