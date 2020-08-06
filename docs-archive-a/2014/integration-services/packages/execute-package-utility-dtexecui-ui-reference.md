---
title: Справочник по пользовательскому интерфейсу служебная программа для запуска пакетов (DtExecUI) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.dtexecui.general.f1
- sql12.dts.dtexecui.executionoptions.f1
- sql12.dts.dtexecui.configuration.f1
- sql12.dts.dtexecui.setvalues.f1
- sql12.dts.dtexecui.commandline.f1
- sql12.dts.dtexecui.commandfiles.f1
- sql12.dts.dtexecui.verification.f1
- sql12.dts.dtexecui.datasources.f1
- sql12.dts.dtexecui.reporting.f1
- sql12.dts.dtexecui.logging.f1
helpviewer_keywords:
- DTExecUI utility
ms.assetid: 3d71df39-126b-4c8e-bd77-128bbd5b0887
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 13601983a4ab841a2b64ff8e4fc722fcf5ae496c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665417"
---
# <a name="execute-package-utility-dtexecui-ui-reference"></a><span data-ttu-id="dad31-102">Программа выполнения пакетов справочника по пользовательскому интерфейсу (DtExecUI)</span><span class="sxs-lookup"><span data-stu-id="dad31-102">Execute Package Utility (DtExecUI) UI Reference</span></span>
  <span data-ttu-id="dad31-103">**Программа выполнения пакетов** используется для запуска пакетов служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dad31-103">Use the **Execute Package Utility** to run [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="dad31-104">Служебная программа запускает пакеты, которые хранятся в одном из трех расположений: в базе данных [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], хранилище пакетов [!INCLUDE[ssIS](../../includes/ssis-md.md)] и файловой системе.</span><span class="sxs-lookup"><span data-stu-id="dad31-104">The utility runs packages that are stored in one of three locations: [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Store, and the file system.</span></span> <span data-ttu-id="dad31-105">Этот пользовательский интерфейс, который можно открыть [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или ввести `dtexecui` в командной строке, является альтернативой запуску пакетов с помощью программы командной строки **dtexec** .</span><span class="sxs-lookup"><span data-stu-id="dad31-105">This user interface, which can be opened from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or by typing `dtexecui` at a command prompt, is an alternative to running packages by using the **DTExec** command prompt tool.</span></span>  
  
 <span data-ttu-id="dad31-106">Пакеты выполняются в том же процессе, что и служебная программа **dtexecui.exe** .</span><span class="sxs-lookup"><span data-stu-id="dad31-106">Packages execute in the same process as the **dtexecui.exe** utility.</span></span> <span data-ttu-id="dad31-107">Так как эта служебная программа является 32-разрядной, пакеты, запускаемые с помощью **dtexecui.exe** в 64-разрядной среде, выполняются в режиме WOW (Windows на платформе Win32).</span><span class="sxs-lookup"><span data-stu-id="dad31-107">Because this utility is a 32-bit tool, packages run by using **dtexecui.exe** in a 64-bit environment run in Windows on Win32 (WOW).</span></span> <span data-ttu-id="dad31-108">Занимаясь разработкой и отладкой команд на 64-разрядном компьютере с использованием программы dtexecui.exe, необходимо проверять эти команды в 64-разрядном режиме с помощью 64-разрядной версии программы **dtexec.exe** , прежде чем развертывать эти команды или включать их в расписание на рабочем сервере.</span><span class="sxs-lookup"><span data-stu-id="dad31-108">When developing and testing commands by using the dtexecui.exe utility on a 64-bit computer, you should test the commands in 64-bit mode by using the 64-bit version of **dtexec.exe** before deploying or scheduling the commands on a production server.</span></span>  
  
 <span data-ttu-id="dad31-109">**Программа выполнения пакетов** — это графический пользовательский интерфейс для программы командной строки **DTExec** .</span><span class="sxs-lookup"><span data-stu-id="dad31-109">The **Execute Package Utility** is a graphical user interface for the **DTExec** command prompt tool.</span></span> <span data-ttu-id="dad31-110">Пользовательский интерфейс позволяет легко настраивать параметры и автоматически формировать командную строку, которая передается в программу командной строки **DTExec** после указания требуемых параметров и запуска пакета.</span><span class="sxs-lookup"><span data-stu-id="dad31-110">The user interface makes it easy to configure options and it automatically assembles the command line that is passed to the **DTExec** command prompt tool when you run the package from the specified options.</span></span>  
  
 <span data-ttu-id="dad31-111">**Служебная программа для запуска пакетов** может также служить для формирования командных строк, используемых непосредственно в **DTExec** .</span><span class="sxs-lookup"><span data-stu-id="dad31-111">The **Execute Package Utility** can also be used to assemble command lines that you use when running **DTExec** directly.</span></span>  
  
### <a name="to-open-execute-package-utility-in-sql-server-management-studio"></a><span data-ttu-id="dad31-112">Открытие программы выполнения пакетов в SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dad31-112">To open Execute Package Utility in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="dad31-113">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]в меню **Вид** выберите команду **Обозреватель объектов**.</span><span class="sxs-lookup"><span data-stu-id="dad31-113">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Object Explorer**.</span></span>  
  
2.  <span data-ttu-id="dad31-114">В обозревателе объектов нажмите кнопку **Соединить**, затем **Службы Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="dad31-114">In Object Explorer, click **Connect**, and then click **Integration Services**.</span></span>  
  
3.  <span data-ttu-id="dad31-115">В диалоговом окне **Соединение с сервером** введите имя сервера в списке **Имя сервера** , а затем щелкните **Подключиться**.</span><span class="sxs-lookup"><span data-stu-id="dad31-115">In the **Connect to Server** dialog box, enter the server name in the **Server name** list, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="dad31-116">Разверните папку **Сохраненные пакеты**и вложенные папки, щелкните правой кнопкой мыши пакет, который необходимо запустить, и выберите **Выполнить пакет**.</span><span class="sxs-lookup"><span data-stu-id="dad31-116">Expand the **Stored Package**s folder and subfolders, right-click the package you want to run, and then click **Run Package**.</span></span>  
  
### <a name="to-open-the-execute-package-utility-at-the-command-prompt"></a><span data-ttu-id="dad31-117">Открытие программы выполнения пакетов в командной строке</span><span class="sxs-lookup"><span data-stu-id="dad31-117">To open the Execute Package Utility at the Command Prompt</span></span>  
  
-   <span data-ttu-id="dad31-118">В окне командной строки вызовите на выполнение `dtexecui`.</span><span class="sxs-lookup"><span data-stu-id="dad31-118">In a command prompt window, run `dtexecui`.</span></span>  
  
 <span data-ttu-id="dad31-119">В следующих разделах описаны страницы диалогового окна **Программа выполнения пакетов** .</span><span class="sxs-lookup"><span data-stu-id="dad31-119">The following sections describe pages of the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="general-page"></a><span data-ttu-id="dad31-120">Страница «Общие»</span><span class="sxs-lookup"><span data-stu-id="dad31-120">General Page</span></span>  
 <span data-ttu-id="dad31-121">Страница **Общие** диалогового окна **Программа выполнения пакетов** позволяет задать имя и расположение пакета.</span><span class="sxs-lookup"><span data-stu-id="dad31-121">Use the **General** page of the **Execute Package Utility** dialog box to specify a package name and location.</span></span>  
  
 <span data-ttu-id="dad31-122">Программа выполнения пакетов (dtexecui.exe) всегда запускает пакет на локальном компьютере, даже если пакет сохранен на удаленном сервере.</span><span class="sxs-lookup"><span data-stu-id="dad31-122">The Execute Package utility (dtexecui.exe) always runs a package on the local computer, even if the package is saved on a remote server.</span></span> <span data-ttu-id="dad31-123">Если удаленный пакет использует файлы конфигурации, также сохраненные на удаленном сервере, программа выполнения пакетов может не найти эти файлы и пакет не будет выполнен.</span><span class="sxs-lookup"><span data-stu-id="dad31-123">If the remote package uses configuration files that also are saved on the remote server, then the Execute Package utility may not locate the configurations and the package fails.</span></span> <span data-ttu-id="dad31-124">Во избежание подобной проблемы необходимо ссылаться на файлы конфигурации по имени общего ресурса в формате UNC, например \\\сервер\файл.</span><span class="sxs-lookup"><span data-stu-id="dad31-124">To avoid this problem, the configurations must be referenced by using a Universal Naming Convention (UNC) share name like \\\myserver\myfile.</span></span>  
  
### <a name="static-options"></a><span data-ttu-id="dad31-125">Статические параметры</span><span class="sxs-lookup"><span data-stu-id="dad31-125">Static Options</span></span>  
 <span data-ttu-id="dad31-126">**Источник пакета**</span><span class="sxs-lookup"><span data-stu-id="dad31-126">**Package source**</span></span>  
 <span data-ttu-id="dad31-127">Расположение выполняемого пакета с использованием следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="dad31-127">Specify the location of the package to run, using the following options:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dad31-128">Значение</span><span class="sxs-lookup"><span data-stu-id="dad31-128">Value</span></span>|<span data-ttu-id="dad31-129">Description</span><span class="sxs-lookup"><span data-stu-id="dad31-129">Description</span></span>|  
|<span data-ttu-id="dad31-130">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="dad31-130">**SQL Server**</span></span>|<span data-ttu-id="dad31-131">Выберите этот параметр, если пакет находится на [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dad31-131">Select this option when the package resides in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="dad31-132">Укажите экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и введите имя пользователя и пароль для проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dad31-132">Specify an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and provide a user name and password for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="dad31-133">Указание каждого имени пользователя и пароля приводит к добавлению в командную строку параметров **/USER** _имя_пользователя_ и **/PASSWORD** _пароль_.</span><span class="sxs-lookup"><span data-stu-id="dad31-133">Each user name and password adds the **/USER** _username_ and **/PASSWORD** _password_ options to the command prompt.</span></span>|  
|<span data-ttu-id="dad31-134">**Файловая система**</span><span class="sxs-lookup"><span data-stu-id="dad31-134">**File system**</span></span>|<span data-ttu-id="dad31-135">Выберите этот параметр, если пакет находится в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="dad31-135">Select this option when the package resides in the file system.</span></span>|  
|<span data-ttu-id="dad31-136">**Хранилище пакетов служб SSIS**</span><span class="sxs-lookup"><span data-stu-id="dad31-136">**SSIS Package Store**</span></span>|<span data-ttu-id="dad31-137">Выберите этот параметр, если пакет находится в хранилище пакетов [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dad31-137">Select this option when the package resides in the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Store.</span></span>|  
  
 <span data-ttu-id="dad31-138">Для каждого из этих режимов существует следующий набор параметров:</span><span class="sxs-lookup"><span data-stu-id="dad31-138">Each of these selections has the following set of options.</span></span>  
  
 <span data-ttu-id="dad31-139">**Execute**</span><span class="sxs-lookup"><span data-stu-id="dad31-139">**Execute**</span></span>  
 <span data-ttu-id="dad31-140">Нажмите для выполнения пакета.</span><span class="sxs-lookup"><span data-stu-id="dad31-140">Click to run the package.</span></span>  
  
 <span data-ttu-id="dad31-141">**Закрыть**</span><span class="sxs-lookup"><span data-stu-id="dad31-141">**Close**</span></span>  
 <span data-ttu-id="dad31-142">Нажмите эту кнопку, чтобы закрыть диалоговое окно **Программа выполнения пакетов** .</span><span class="sxs-lookup"><span data-stu-id="dad31-142">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
### <a name="dynamic-options"></a><span data-ttu-id="dad31-143">Динамические параметры</span><span class="sxs-lookup"><span data-stu-id="dad31-143">Dynamic Options</span></span>  
  
#### <a name="package-source--sql-server"></a><span data-ttu-id="dad31-144">Источник пакета = SQL Server</span><span class="sxs-lookup"><span data-stu-id="dad31-144">Package Source = SQL Server</span></span>  
 <span data-ttu-id="dad31-145">**Server**</span><span class="sxs-lookup"><span data-stu-id="dad31-145">**Server**</span></span>  
 <span data-ttu-id="dad31-146">Введите имя сервера, содержащего пакет, или выберите сервер из списка.</span><span class="sxs-lookup"><span data-stu-id="dad31-146">Type the name of the server where the package resides, or select a server from the list.</span></span>  
  
 <span data-ttu-id="dad31-147">**Вход на сервер**</span><span class="sxs-lookup"><span data-stu-id="dad31-147">**Log on to the server**</span></span>  
 <span data-ttu-id="dad31-148">Укажите, нужна ли пакету проверка подлинности Windows или [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для подключения к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dad31-148">Specify whether the package should use Windows Authentication or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="dad31-149">Для лучшей защиты рекомендуется использовать проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="dad31-149">Windows Authentication is recommended for better security.</span></span> <span data-ttu-id="dad31-150">При использовании системы проверки подлинности Windows не нужно вводить имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="dad31-150">With Windows Authentication you do not have to specify a user name and password.</span></span>  
  
 <span data-ttu-id="dad31-151">**Использовать проверку подлинности Windows**</span><span class="sxs-lookup"><span data-stu-id="dad31-151">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="dad31-152">Выберите этот параметр, чтобы использовать проверку подлинности Windows и входить в систему с пользовательской учетной записью [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="dad31-152">Select this option to use Windows Authentication and log on using a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows user account.</span></span>  
  
 <span data-ttu-id="dad31-153">**Использовать проверку подлинности SQL Server**</span><span class="sxs-lookup"><span data-stu-id="dad31-153">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="dad31-154">Выберите данный параметр, чтобы использовать проверку подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dad31-154">Select this option to use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="dad31-155">При подключении пользователя с указанным именем и паролем из ненадежных соединений [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выполняет проверку подлинности, сравнивая настройки учетной записи входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и указанный пароль с записанным ранее.</span><span class="sxs-lookup"><span data-stu-id="dad31-155">When a user connects with a specified login name and password from a non-trusted connection, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs the authentication by checking to see if a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login account has been set up and if the specified password matches the one previously recorded.</span></span> <span data-ttu-id="dad31-156">Если [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не может найти такое имя входа, проверка подлинности прекращается, и пользователь получает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="dad31-156">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot find the login account, authentication fails, and the user receives an error message.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="dad31-157">По возможности используйте аутентификацию Windows.</span><span class="sxs-lookup"><span data-stu-id="dad31-157">When possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="dad31-158">**Пакет**</span><span class="sxs-lookup"><span data-stu-id="dad31-158">**Package**</span></span>  
 <span data-ttu-id="dad31-159">Введите имя пакета или нажмите кнопку с многоточием **(...)** для определения расположения пакета в диалоговом окне **Выбор пакета служб SSIS**.</span><span class="sxs-lookup"><span data-stu-id="dad31-159">Type the name of the package, or click the ellipsis button **(...)** to locate a package using the **Select an SSIS Package** dialog box.</span></span>  
  
#### <a name="package-source--file-system"></a><span data-ttu-id="dad31-160">Источник пакета = файловая система</span><span class="sxs-lookup"><span data-stu-id="dad31-160">Package Source = File System</span></span>  
 <span data-ttu-id="dad31-161">**Пакет**</span><span class="sxs-lookup"><span data-stu-id="dad31-161">**Package**</span></span>  
 <span data-ttu-id="dad31-162">Введите имя пакета или нажмите кнопку с многоточием **(...)** для определения расположения пакета в диалоговом окне "Открыть".</span><span class="sxs-lookup"><span data-stu-id="dad31-162">Type the name of the package, or click the ellipsis button **(...)** to locate a package using the Open dialog box.</span></span> <span data-ttu-id="dad31-163">По умолчанию это диалоговое окно выводит только список файлов с расширением DTSX.</span><span class="sxs-lookup"><span data-stu-id="dad31-163">By default, the dialog box lists only files that have the .dtsx extension.</span></span>  
  
#### <a name="package-source--ssis-package-store"></a><span data-ttu-id="dad31-164">Источник пакета = хранилище пакетов служб SSIS</span><span class="sxs-lookup"><span data-stu-id="dad31-164">Package Source = SSIS Package Store</span></span>  
 <span data-ttu-id="dad31-165">**Server**</span><span class="sxs-lookup"><span data-stu-id="dad31-165">**Server**</span></span>  
 <span data-ttu-id="dad31-166">Введите имя компьютера, содержащего пакет, или выберите компьютер из списка.</span><span class="sxs-lookup"><span data-stu-id="dad31-166">Type the name of the computer where the package resides, or select a computer from the list.</span></span>  
  
 <span data-ttu-id="dad31-167">**Вход на сервер**</span><span class="sxs-lookup"><span data-stu-id="dad31-167">**Log on to the server**</span></span>  
 <span data-ttu-id="dad31-168">Укажите, должен ли пакет использовать проверку подлинности Microsoft Windows для подключения к источнику пакета.</span><span class="sxs-lookup"><span data-stu-id="dad31-168">Specify whether the package should use Microsoft Windows Authentication to connect to the package source.</span></span> <span data-ttu-id="dad31-169">Для лучшей защиты рекомендуется использовать проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="dad31-169">Windows Authentication is recommended for better security.</span></span> <span data-ttu-id="dad31-170">При использовании системы проверки подлинности Windows не нужно вводить имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="dad31-170">With Windows Authentication you do not have to specify a user name and password.</span></span>  
  
 <span data-ttu-id="dad31-171">**Использовать проверку подлинности Windows**</span><span class="sxs-lookup"><span data-stu-id="dad31-171">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="dad31-172">Выберите этот параметр, чтобы использовать проверку подлинности Windows и войти в систему с учетной записью Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="dad31-172">Select this option to use Windows Authentication and log on using a Microsoft Windows user account.</span></span>  
  
 <span data-ttu-id="dad31-173">**Использовать проверку подлинности SQL Server**</span><span class="sxs-lookup"><span data-stu-id="dad31-173">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="dad31-174">Этот режим недоступен при запуске пакета, сохраненного в **Хранилище пакетов служб SSIS**.</span><span class="sxs-lookup"><span data-stu-id="dad31-174">This option is not available when you run a package stored in the **SSIS Package Store**.</span></span>  
  
 <span data-ttu-id="dad31-175">**Пакет**</span><span class="sxs-lookup"><span data-stu-id="dad31-175">**Package**</span></span>  
 <span data-ttu-id="dad31-176">Введите имя пакета или нажмите кнопку с многоточием **(...)** для определения расположения пакета в диалоговом окне **Выбор пакета служб SSIS**.</span><span class="sxs-lookup"><span data-stu-id="dad31-176">Type the name of the package, or click the ellipsis button **(...)** to locate a package using the **Select an SSIS Package** dialog box.</span></span>  
  
## <a name="configurations-page"></a><span data-ttu-id="dad31-177">Страница конфигураций</span><span class="sxs-lookup"><span data-stu-id="dad31-177">Configurations Page</span></span>  
 <span data-ttu-id="dad31-178">Страница **Конфигурации** диалогового окна **Программа выполнения пакетов** используется для выбора файлов конфигурации для загрузки во время выполнения и для указания порядка, в котором они загружаются.</span><span class="sxs-lookup"><span data-stu-id="dad31-178">Use the **Configurations** page of the **Execute Package Utility** dialog box to select the configuration files to load at run time, and to specify the order in which they load.</span></span>  
  
### <a name="options"></a><span data-ttu-id="dad31-179">Параметры</span><span class="sxs-lookup"><span data-stu-id="dad31-179">Options</span></span>  
 <span data-ttu-id="dad31-180">**Файлы конфигурации**</span><span class="sxs-lookup"><span data-stu-id="dad31-180">**Configuration files**</span></span>  
 <span data-ttu-id="dad31-181">Перечисляются используемые пакетом конфигурации.</span><span class="sxs-lookup"><span data-stu-id="dad31-181">Lists the configurations that the package uses.</span></span> <span data-ttu-id="dad31-182">Применение каждого файла конфигурации приводит к добавлению в командную строку параметра **/CONFIGFILE имя_файла** .</span><span class="sxs-lookup"><span data-stu-id="dad31-182">Each configuration file adds a **/CONFIGFILE filename** option to the command prompt.</span></span>  
  
 <span data-ttu-id="dad31-183">**Клавиши со стрелками**</span><span class="sxs-lookup"><span data-stu-id="dad31-183">**Arrow keys**</span></span>  
 <span data-ttu-id="dad31-184">Выберите в списке файл конфигурации и с помощью расположенных справа клавиш со стрелками измените порядок загрузки.</span><span class="sxs-lookup"><span data-stu-id="dad31-184">Select a configuration file in the list, and use the arrow keys at right to change the loading order.</span></span> <span data-ttu-id="dad31-185">Конфигурации загружаются, начиная с верхней части списка.</span><span class="sxs-lookup"><span data-stu-id="dad31-185">Configurations load in order starting from the top of the list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dad31-186">Если несколько конфигураций изменяют одно и то же свойство, применяется конфигурация, загружаемая последней.</span><span class="sxs-lookup"><span data-stu-id="dad31-186">If multiple configurations modify the same property, the configuration that loads last is used.</span></span>  
  
 <span data-ttu-id="dad31-187">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="dad31-187">**Add**</span></span>  
 <span data-ttu-id="dad31-188">Щелкните для добавления конфигураций с помощью диалогового окна **Открыть** .</span><span class="sxs-lookup"><span data-stu-id="dad31-188">Click to add configurations using the **Open** dialog box.</span></span> <span data-ttu-id="dad31-189">По умолчанию в диалоговом окне указываются только файлы, имеющие расширение DTSCONFIG.</span><span class="sxs-lookup"><span data-stu-id="dad31-189">By default, the dialog box lists only files that have the .dtsconfig extension.</span></span>  
  
 <span data-ttu-id="dad31-190">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="dad31-190">**Remove**</span></span>  
 <span data-ttu-id="dad31-191">Выберите из списка файл конфигурации, затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="dad31-191">Select a configuration file in the list and then click **Remove**.</span></span>  
  
 <span data-ttu-id="dad31-192">**Execute**</span><span class="sxs-lookup"><span data-stu-id="dad31-192">**Execute**</span></span>  
 <span data-ttu-id="dad31-193">Нажмите для выполнения пакета.</span><span class="sxs-lookup"><span data-stu-id="dad31-193">Click to run the package.</span></span>  
  
 <span data-ttu-id="dad31-194">**Закрыть**</span><span class="sxs-lookup"><span data-stu-id="dad31-194">**Close**</span></span>  
 <span data-ttu-id="dad31-195">Нажмите эту кнопку, чтобы закрыть диалоговое окно **Программа выполнения пакетов** .</span><span class="sxs-lookup"><span data-stu-id="dad31-195">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="command-files-page"></a><span data-ttu-id="dad31-196">Страница «Командные файлы»</span><span class="sxs-lookup"><span data-stu-id="dad31-196">Command Files Page</span></span>  
 <span data-ttu-id="dad31-197">Страница **Командные файлы** диалогового окна **Программа выполнения пакетов** используется для выбора командных файлов, которые будут загружаться во время исполнения.</span><span class="sxs-lookup"><span data-stu-id="dad31-197">Use the **Command Files** page of the **Execute Package Utility** dialog box to select the command files to load at run time.</span></span>  
  
### <a name="options"></a><span data-ttu-id="dad31-198">Параметры</span><span class="sxs-lookup"><span data-stu-id="dad31-198">Options</span></span>  
 <span data-ttu-id="dad31-199">**Командные файлы**</span><span class="sxs-lookup"><span data-stu-id="dad31-199">**Command files**</span></span>  
 <span data-ttu-id="dad31-200">Выводит список командных файлов, которые использует пакет.</span><span class="sxs-lookup"><span data-stu-id="dad31-200">Lists the command files that the package uses.</span></span> <span data-ttu-id="dad31-201">Для установки параметров командной строки пакет может использовать несколько файлов.</span><span class="sxs-lookup"><span data-stu-id="dad31-201">A package can use multiple files to set command-line options.</span></span>  
  
 <span data-ttu-id="dad31-202">**Клавиши со стрелками**</span><span class="sxs-lookup"><span data-stu-id="dad31-202">**Arrow keys**</span></span>  
 <span data-ttu-id="dad31-203">Выберите из списка командный файл и с помощью клавиш-стрелок справа определите порядок их загрузки.</span><span class="sxs-lookup"><span data-stu-id="dad31-203">Select a command file in the list, and use the arrow keys at right to change the loading order.</span></span> <span data-ttu-id="dad31-204">Командные файлы загружаются по порядку, начиная с первого файла в списке.</span><span class="sxs-lookup"><span data-stu-id="dad31-204">Command files load in order, starting from the top of the list.</span></span>  
  
 <span data-ttu-id="dad31-205">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="dad31-205">**Add**</span></span>  
 <span data-ttu-id="dad31-206">Нажмите, чтобы добавить командный файл с помощью диалогового окна **Открыть** .</span><span class="sxs-lookup"><span data-stu-id="dad31-206">Click to add a command file, using the **Open** dialog box.</span></span>  
  
 <span data-ttu-id="dad31-207">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="dad31-207">**Remove**</span></span>  
 <span data-ttu-id="dad31-208">Выберите в текстовом поле командный файл и удалите его с помощью кнопки **Удалить** .</span><span class="sxs-lookup"><span data-stu-id="dad31-208">Select a command file in the text box, and then remove it using the **Remove** button.</span></span>  
  
 <span data-ttu-id="dad31-209">**Execute**</span><span class="sxs-lookup"><span data-stu-id="dad31-209">**Execute**</span></span>  
 <span data-ttu-id="dad31-210">Нажмите для выполнения пакета.</span><span class="sxs-lookup"><span data-stu-id="dad31-210">Click to run the package.</span></span>  
  
 <span data-ttu-id="dad31-211">**Закрыть**</span><span class="sxs-lookup"><span data-stu-id="dad31-211">**Close**</span></span>  
 <span data-ttu-id="dad31-212">Нажмите эту кнопку, чтобы закрыть диалоговое окно **Программа выполнения пакетов** .</span><span class="sxs-lookup"><span data-stu-id="dad31-212">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="connection-managers-page"></a><span data-ttu-id="dad31-213">Страница «Диспетчеры соединений»</span><span class="sxs-lookup"><span data-stu-id="dad31-213">Connection Managers Page</span></span>  
 <span data-ttu-id="dad31-214">Используйте страницу **Диспетчеры соединений** диалогового окна **Программа выполнения пакетов** для редактирования строк соединений диспетчеров соединений, используемых пакетом.</span><span class="sxs-lookup"><span data-stu-id="dad31-214">Use the **Connection Managers** page of the **Execute Package Utility** dialog box to edit the connection strings of the connection managers that the package uses.</span></span>  
  
### <a name="options"></a><span data-ttu-id="dad31-215">Параметры</span><span class="sxs-lookup"><span data-stu-id="dad31-215">Options</span></span>  
 <span data-ttu-id="dad31-216">**Диспетчер соединений**</span><span class="sxs-lookup"><span data-stu-id="dad31-216">**Connection Manager**</span></span>  
 <span data-ttu-id="dad31-217">Установите флажок данного диспетчера, чтобы столбец **Строка подключения** можно быть редактировать.</span><span class="sxs-lookup"><span data-stu-id="dad31-217">Select its check box to make the **Connection String** column editable.</span></span>  
  
 <span data-ttu-id="dad31-218">**Описание**</span><span class="sxs-lookup"><span data-stu-id="dad31-218">**Description**</span></span>  
 <span data-ttu-id="dad31-219">Просмотрите описания для каждого диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="dad31-219">View a description for each connection manager.</span></span> <span data-ttu-id="dad31-220">Описания нельзя редактировать.</span><span class="sxs-lookup"><span data-stu-id="dad31-220">Descriptions cannot be edited.</span></span>  
  
 <span data-ttu-id="dad31-221">**Строка подключения**</span><span class="sxs-lookup"><span data-stu-id="dad31-221">**Connection String**</span></span>  
 <span data-ttu-id="dad31-222">Отредактируйте строку соединения для диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="dad31-222">Edit the connection string for a connection manager.</span></span> <span data-ttu-id="dad31-223">Это поле можно редактировать, только если установлен флажок **Диспетчер соединений** .</span><span class="sxs-lookup"><span data-stu-id="dad31-223">This field is editable only when the **Connection Manager** check box is selected.</span></span>  
  
 <span data-ttu-id="dad31-224">**Execute**</span><span class="sxs-lookup"><span data-stu-id="dad31-224">**Execute**</span></span>  
 <span data-ttu-id="dad31-225">Нажмите для выполнения пакета.</span><span class="sxs-lookup"><span data-stu-id="dad31-225">Click to run the package.</span></span>  
  
 <span data-ttu-id="dad31-226">**Закрыть**</span><span class="sxs-lookup"><span data-stu-id="dad31-226">**Close**</span></span>  
 <span data-ttu-id="dad31-227">Нажмите эту кнопку, чтобы закрыть диалоговое окно **Программа выполнения пакетов** .</span><span class="sxs-lookup"><span data-stu-id="dad31-227">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="execution-options-page"></a><span data-ttu-id="dad31-228">Страница «Параметры выполнения»</span><span class="sxs-lookup"><span data-stu-id="dad31-228">Execution Options Page</span></span>  
 <span data-ttu-id="dad31-229">Используйте страницу **Параметры выполнения** диалогового окна **Программа выполнения пакетов** , чтобы указать параметры времени выполнения пакета.</span><span class="sxs-lookup"><span data-stu-id="dad31-229">Use the **Execution Options** page of the **Execute Package Utility** dialog box to specify run-time options for the package.</span></span>  
  
### <a name="options"></a><span data-ttu-id="dad31-230">Параметры</span><span class="sxs-lookup"><span data-stu-id="dad31-230">Options</span></span>  
 <span data-ttu-id="dad31-231">**Завершить работу с ошибкой при предупреждениях проверки**</span><span class="sxs-lookup"><span data-stu-id="dad31-231">**Fail package on validation warnings**</span></span>  
 <span data-ttu-id="dad31-232">Определяет, будет ли пакет аварийно завершен при возникновении предупреждений в процессе проверки.</span><span class="sxs-lookup"><span data-stu-id="dad31-232">Indicate whether the package fails if a validation warning occurs.</span></span>  
  
 <span data-ttu-id="dad31-233">**Проверить пакет без выполнения**</span><span class="sxs-lookup"><span data-stu-id="dad31-233">**Validate package without executing**</span></span>  
 <span data-ttu-id="dad31-234">Показывает, будет ли выполнена только проверка пакета.</span><span class="sxs-lookup"><span data-stu-id="dad31-234">Indicate whether the package is validated only.</span></span>  
  
 <span data-ttu-id="dad31-235">**Максимальное число одновременно исполняемых объектов**</span><span class="sxs-lookup"><span data-stu-id="dad31-235">**Maximum concurrent executables**</span></span>  
 <span data-ttu-id="dad31-236">Определяет, нужно ли задавать максимальное количество исполняемых объектов, которые могут быть запущены в пакете одновременно.</span><span class="sxs-lookup"><span data-stu-id="dad31-236">Indicate whether you want to specify the maximum number of executables that can run in the package at the same time.</span></span> <span data-ttu-id="dad31-237">После установки этого флажка используйте счетчик для задания максимального количества исполняемых объектов.</span><span class="sxs-lookup"><span data-stu-id="dad31-237">After you select this check box, use the spin box to specify the maximum number of executables.</span></span>  
  
 <span data-ttu-id="dad31-238">**Включить контрольные точки пакета**</span><span class="sxs-lookup"><span data-stu-id="dad31-238">**Enable package checkpoints**</span></span>  
 <span data-ttu-id="dad31-239">Определяет, будут ли включены контрольные точки пакета.</span><span class="sxs-lookup"><span data-stu-id="dad31-239">Indicate whether to enable package checkpoints.</span></span>  
  
 <span data-ttu-id="dad31-240">**Файл контрольных точек**</span><span class="sxs-lookup"><span data-stu-id="dad31-240">**Checkpoint file**</span></span>  
 <span data-ttu-id="dad31-241">Содержит файл контрольных точек, используемый пакетом, если в пакете включены контрольные точки.</span><span class="sxs-lookup"><span data-stu-id="dad31-241">List the checkpoint file the package uses, if you enable package checkpoints.</span></span>  
  
 <span data-ttu-id="dad31-242">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="dad31-242">**Browse**</span></span>  
 <span data-ttu-id="dad31-243">Нажмите кнопку обзора **(...)** для нахождения файла контрольных точек с помощью диалогового окна **Открыть**, если в пакете включены контрольные точки.</span><span class="sxs-lookup"><span data-stu-id="dad31-243">Click the browse button **(...)** to locate the checkpoint file using the **Open** dialog box, if you enable package checkpoints.</span></span> <span data-ttu-id="dad31-244">Если файл контрольных точек уже определен, он замещается выбранным файлом.</span><span class="sxs-lookup"><span data-stu-id="dad31-244">If a checkpoint file is already specified, it is replaced by the selected file.</span></span>  
  
 <span data-ttu-id="dad31-245">**Переопределить режим перезапуска**</span><span class="sxs-lookup"><span data-stu-id="dad31-245">**Override restart options**</span></span>  
 <span data-ttu-id="dad31-246">Определяет, будут ли переопределены параметры перезапуска, если в пакете включены контрольные точки.</span><span class="sxs-lookup"><span data-stu-id="dad31-246">Indicate whether to override restart options, if you enable package checkpoints.</span></span>  
  
 <span data-ttu-id="dad31-247">**Параметр перезапуска**</span><span class="sxs-lookup"><span data-stu-id="dad31-247">**Restart option**</span></span>  
 <span data-ttu-id="dad31-248">Выбор способа использования контрольных точек при переопределении параметров перезапуска.</span><span class="sxs-lookup"><span data-stu-id="dad31-248">Select how to use checkpoints, if you override restart options.</span></span>  
  
 <span data-ttu-id="dad31-249">**Execute**</span><span class="sxs-lookup"><span data-stu-id="dad31-249">**Execute**</span></span>  
 <span data-ttu-id="dad31-250">Нажмите для выполнения пакета.</span><span class="sxs-lookup"><span data-stu-id="dad31-250">Click to run the package.</span></span>  
  
 <span data-ttu-id="dad31-251">**Закрыть**</span><span class="sxs-lookup"><span data-stu-id="dad31-251">**Close**</span></span>  
 <span data-ttu-id="dad31-252">Нажмите эту кнопку, чтобы закрыть диалоговое окно **Программа выполнения пакетов** .</span><span class="sxs-lookup"><span data-stu-id="dad31-252">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="reporting-page"></a><span data-ttu-id="dad31-253">Страница «Отчеты»</span><span class="sxs-lookup"><span data-stu-id="dad31-253">Reporting Page</span></span>  
 <span data-ttu-id="dad31-254">Для задания событий и сведений о пакете, записываемых в журнал консоли при выполнении пакета, используется страница **Отчеты** диалогового окна **Программа выполнения пакетов** .</span><span class="sxs-lookup"><span data-stu-id="dad31-254">Use the **Reporting** page of the **Execute Package Utility** dialog box to specify the events and information about the package to log to the console when the package runs.</span></span>  
  
### <a name="options"></a><span data-ttu-id="dad31-255">Параметры</span><span class="sxs-lookup"><span data-stu-id="dad31-255">Options</span></span>  
 <span data-ttu-id="dad31-256">**События консоли**</span><span class="sxs-lookup"><span data-stu-id="dad31-256">**Console events**</span></span>  
 <span data-ttu-id="dad31-257">Укажите события и типы сообщений для вывода.</span><span class="sxs-lookup"><span data-stu-id="dad31-257">Indicate the events and types of messages to report.</span></span>  
  
 <span data-ttu-id="dad31-258">**None**</span><span class="sxs-lookup"><span data-stu-id="dad31-258">**None**</span></span>  
 <span data-ttu-id="dad31-259">Выберите для отсутствия сообщений.</span><span class="sxs-lookup"><span data-stu-id="dad31-259">Select for no reporting.</span></span>  
  
 <span data-ttu-id="dad31-260">**ошибки**</span><span class="sxs-lookup"><span data-stu-id="dad31-260">**Errors**</span></span>  
 <span data-ttu-id="dad31-261">Выберите этот параметр для вывода сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="dad31-261">Select to report error messages.</span></span>  
  
 <span data-ttu-id="dad31-262">**Предупреждения**</span><span class="sxs-lookup"><span data-stu-id="dad31-262">**Warnings**</span></span>  
 <span data-ttu-id="dad31-263">Выберите этот параметр для вывода предупреждений.</span><span class="sxs-lookup"><span data-stu-id="dad31-263">Select to report warning messages.</span></span>  
  
 <span data-ttu-id="dad31-264">**Пользовательские события**</span><span class="sxs-lookup"><span data-stu-id="dad31-264">**Custom Events**</span></span>  
 <span data-ttu-id="dad31-265">Выберите этот параметр для вывода сообщений о пользовательских событиях.</span><span class="sxs-lookup"><span data-stu-id="dad31-265">Select to report custom event messages.</span></span>  
  
 <span data-ttu-id="dad31-266">**События конвейера**</span><span class="sxs-lookup"><span data-stu-id="dad31-266">**Pipeline Events**</span></span>  
 <span data-ttu-id="dad31-267">Выберите этот параметр для вывода сообщений о событиях потока данных.</span><span class="sxs-lookup"><span data-stu-id="dad31-267">Select to report data flow events messages.</span></span>  
  
 <span data-ttu-id="dad31-268">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="dad31-268">**Information**</span></span>  
 <span data-ttu-id="dad31-269">Выберите этот параметр для вывода информационных сообщений.</span><span class="sxs-lookup"><span data-stu-id="dad31-269">Select to report information messages.</span></span>  
  
 <span data-ttu-id="dad31-270">**Подробный**</span><span class="sxs-lookup"><span data-stu-id="dad31-270">**Verbose**</span></span>  
 <span data-ttu-id="dad31-271">Выберите этот параметр для использования подробных отчетов.</span><span class="sxs-lookup"><span data-stu-id="dad31-271">Select to use verbose reporting.</span></span>  
  
 <span data-ttu-id="dad31-272">**Журнал консоли**</span><span class="sxs-lookup"><span data-stu-id="dad31-272">**Console logging**</span></span>  
 <span data-ttu-id="dad31-273">Задайте сведения, которые необходимо записывать в журнал при возникновении выбранного события.</span><span class="sxs-lookup"><span data-stu-id="dad31-273">Specify the information that you want written to the log when the selected event occurs.</span></span>  
  
 <span data-ttu-id="dad31-274">**Название**</span><span class="sxs-lookup"><span data-stu-id="dad31-274">**Name**</span></span>  
 <span data-ttu-id="dad31-275">Выберите этот параметр для сообщения имени лица, создавшего пакет.</span><span class="sxs-lookup"><span data-stu-id="dad31-275">Select to report the name of the person who created the package.</span></span>  
  
 <span data-ttu-id="dad31-276">**Компьютер**</span><span class="sxs-lookup"><span data-stu-id="dad31-276">**Computer**</span></span>  
 <span data-ttu-id="dad31-277">Выберите этот параметр для сообщения имени компьютера, на котором выполняется пакет.</span><span class="sxs-lookup"><span data-stu-id="dad31-277">Select to report the name of the computer the package is running on.</span></span>  
  
 <span data-ttu-id="dad31-278">**Оператор**</span><span class="sxs-lookup"><span data-stu-id="dad31-278">**Operator**</span></span>  
 <span data-ttu-id="dad31-279">Выберите этот параметр для сообщения имени лица, запустившего пакет.</span><span class="sxs-lookup"><span data-stu-id="dad31-279">Select to report the name of the person who started the package.</span></span>  
  
 <span data-ttu-id="dad31-280">**Имя источника**</span><span class="sxs-lookup"><span data-stu-id="dad31-280">**Source name**</span></span>  
 <span data-ttu-id="dad31-281">Выберите этот параметр для сообщения имени пакета.</span><span class="sxs-lookup"><span data-stu-id="dad31-281">Select to report the package name.</span></span>  
  
 <span data-ttu-id="dad31-282">**Идентификатор GUID источника**</span><span class="sxs-lookup"><span data-stu-id="dad31-282">**Source GUID**</span></span>  
 <span data-ttu-id="dad31-283">Выберите этот параметр для сообщения идентификатора GUID пакета.</span><span class="sxs-lookup"><span data-stu-id="dad31-283">Select to report the package GUID.</span></span>  
  
 <span data-ttu-id="dad31-284">**Идентификатор GUID процесса выполнения**</span><span class="sxs-lookup"><span data-stu-id="dad31-284">**Execution GUID**</span></span>  
 <span data-ttu-id="dad31-285">Выберите этот параметр для сообщения идентификатора GUID экземпляра, выполняющего пакет.</span><span class="sxs-lookup"><span data-stu-id="dad31-285">Select to report the GUID of the package execution instance.</span></span>  
  
 <span data-ttu-id="dad31-286">**Сообщение**</span><span class="sxs-lookup"><span data-stu-id="dad31-286">**Message**</span></span>  
 <span data-ttu-id="dad31-287">Выберите этот параметр для вывода сообщений.</span><span class="sxs-lookup"><span data-stu-id="dad31-287">Select to report messages.</span></span>  
  
 <span data-ttu-id="dad31-288">**Время начала и окончания**</span><span class="sxs-lookup"><span data-stu-id="dad31-288">**Start time and end time**</span></span>  
 <span data-ttu-id="dad31-289">Выберите этот параметр для сообщения времени начала и окончания выполнения пакета.</span><span class="sxs-lookup"><span data-stu-id="dad31-289">Select to report when the package began and finished.</span></span>  
  
 <span data-ttu-id="dad31-290">**Execute**</span><span class="sxs-lookup"><span data-stu-id="dad31-290">**Execute**</span></span>  
 <span data-ttu-id="dad31-291">Нажмите для выполнения пакета.</span><span class="sxs-lookup"><span data-stu-id="dad31-291">Click to run the package.</span></span>  
  
 <span data-ttu-id="dad31-292">**Закрыть**</span><span class="sxs-lookup"><span data-stu-id="dad31-292">**Close**</span></span>  
 <span data-ttu-id="dad31-293">Нажмите эту кнопку, чтобы закрыть диалоговое окно **Программа выполнения пакетов** .</span><span class="sxs-lookup"><span data-stu-id="dad31-293">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="logging-page"></a><span data-ttu-id="dad31-294">Страница «Ведение журналов»</span><span class="sxs-lookup"><span data-stu-id="dad31-294">Logging Page</span></span>  
 <span data-ttu-id="dad31-295">Страница **Регистрация** диалогового окна **Программа выполнения пакетов** используется для обеспечения доступа пакета к регистраторам во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="dad31-295">Use the **Logging** page of the **Execute Package Utility** dialog box to make log providers available to the package at run time.</span></span> <span data-ttu-id="dad31-296">Введите тип регистратора пакета и строку соединения с журналом.</span><span class="sxs-lookup"><span data-stu-id="dad31-296">Provide the package log provider type and the connection string for connecting to the log.</span></span> <span data-ttu-id="dad31-297">Применение каждой записи регистратора приводит к добавлению в командную строку параметра **/LOGGER**_ИД_класса_ .</span><span class="sxs-lookup"><span data-stu-id="dad31-297">Each log provider entry adds a **/LOGGER**_classid_ option to the command prompt.</span></span>  
  
### <a name="options"></a><span data-ttu-id="dad31-298">Параметры</span><span class="sxs-lookup"><span data-stu-id="dad31-298">Options</span></span>  
 <span data-ttu-id="dad31-299">**Регистратор**</span><span class="sxs-lookup"><span data-stu-id="dad31-299">**Log Provider**</span></span>  
 <span data-ttu-id="dad31-300">Выберите регистратор из списка.</span><span class="sxs-lookup"><span data-stu-id="dad31-300">Select a log provider from the list.</span></span>  
  
 <span data-ttu-id="dad31-301">**Строка конфигурации**</span><span class="sxs-lookup"><span data-stu-id="dad31-301">**Configuration String**</span></span>  
 <span data-ttu-id="dad31-302">Выберите имя диспетчера соединений из пакета, указывающего расположение журнала, или введите строку соединения с регистратором.</span><span class="sxs-lookup"><span data-stu-id="dad31-302">Select the name of the connection manager from the package that points to the log location, or type the connection string for connecting to the log provider.</span></span>  
  
 <span data-ttu-id="dad31-303">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="dad31-303">**Remove**</span></span>  
 <span data-ttu-id="dad31-304">Выберите регистратор и нажмите эту кнопку для его удаления.</span><span class="sxs-lookup"><span data-stu-id="dad31-304">Select a log provider and click to remove it.</span></span>  
  
 <span data-ttu-id="dad31-305">**Execute**</span><span class="sxs-lookup"><span data-stu-id="dad31-305">**Execute**</span></span>  
 <span data-ttu-id="dad31-306">Нажмите для выполнения пакета.</span><span class="sxs-lookup"><span data-stu-id="dad31-306">Click to run the package.</span></span>  
  
 <span data-ttu-id="dad31-307">**Закрыть**</span><span class="sxs-lookup"><span data-stu-id="dad31-307">**Close**</span></span>  
 <span data-ttu-id="dad31-308">Нажмите эту кнопку, чтобы закрыть диалоговое окно **Программа выполнения пакетов** .</span><span class="sxs-lookup"><span data-stu-id="dad31-308">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="set-values-page"></a><span data-ttu-id="dad31-309">Страница «Установка значений»</span><span class="sxs-lookup"><span data-stu-id="dad31-309">Set Values Page</span></span>  
 <span data-ttu-id="dad31-310">На странице **Установленные значения** диалогового окна **Программа выполнения пакетов** можно определить значения свойств пакетов, исполняемых объектов, подключений, переменных и поставщиков журналов, задав пути к свойствам и значения свойств.</span><span class="sxs-lookup"><span data-stu-id="dad31-310">Use the **Set Values** page of the **Execute Package Utility** dialog box to set the property values of packages, executables, connections, variables, and log providers by typing the paths of properties and the property values.</span></span> <span data-ttu-id="dad31-311">Применение каждой новой записи пути приводит к добавлению в командной строке параметра **/SET**_путь_свойства;значение_ .</span><span class="sxs-lookup"><span data-stu-id="dad31-311">Each path entry adds a **/SET**_propertypath;value_ option to the command prompt.</span></span>  
  
### <a name="options"></a><span data-ttu-id="dad31-312">Параметры</span><span class="sxs-lookup"><span data-stu-id="dad31-312">Options</span></span>  
 <span data-ttu-id="dad31-313">**Путь к свойству**</span><span class="sxs-lookup"><span data-stu-id="dad31-313">**Property Path**</span></span>  
 <span data-ttu-id="dad31-314">Введите путь к свойству.</span><span class="sxs-lookup"><span data-stu-id="dad31-314">Type the path of the property.</span></span> <span data-ttu-id="dad31-315">В синтаксисе пути обратная косая черта (\\) указывает, что следующий за ней элемент является контейнером, точка (.) — что следующий элемент является свойством, а скобки обозначают элемент коллекции.</span><span class="sxs-lookup"><span data-stu-id="dad31-315">The path syntax uses a backslash (\\) to indicate that the following item is a container, the period (.) to indicate the following item is a property, and brackets to indicate a collection member.</span></span> <span data-ttu-id="dad31-316">Элемент может быть идентифицирован по индексу или по имени.</span><span class="sxs-lookup"><span data-stu-id="dad31-316">The member can be identified by its index or its name.</span></span> <span data-ttu-id="dad31-317">Например путь к свойству переменной пакета выглядит как \Пакет.Переменные[Переменная].Значение.</span><span class="sxs-lookup"><span data-stu-id="dad31-317">For example, the property path of a package variable is \Package.Variables[MyVariable].Value.</span></span>  
  
 <span data-ttu-id="dad31-318">**Value**</span><span class="sxs-lookup"><span data-stu-id="dad31-318">**Value**</span></span>  
 <span data-ttu-id="dad31-319">Введите путь к свойству.</span><span class="sxs-lookup"><span data-stu-id="dad31-319">Type the value of the property.</span></span>  
  
 <span data-ttu-id="dad31-320">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="dad31-320">**Remove**</span></span>  
 <span data-ttu-id="dad31-321">Удаление выбранного пути к свойству.</span><span class="sxs-lookup"><span data-stu-id="dad31-321">Select a property path and click to remove it.</span></span>  
  
 <span data-ttu-id="dad31-322">**Execute**</span><span class="sxs-lookup"><span data-stu-id="dad31-322">**Execute**</span></span>  
 <span data-ttu-id="dad31-323">Нажмите для выполнения пакета.</span><span class="sxs-lookup"><span data-stu-id="dad31-323">Click to run the package.</span></span>  
  
 <span data-ttu-id="dad31-324">**Закрыть**</span><span class="sxs-lookup"><span data-stu-id="dad31-324">**Close**</span></span>  
 <span data-ttu-id="dad31-325">Нажмите эту кнопку, чтобы закрыть диалоговое окно **Программа выполнения пакетов** .</span><span class="sxs-lookup"><span data-stu-id="dad31-325">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="verification-page"></a><span data-ttu-id="dad31-326">Страница «Проверка»</span><span class="sxs-lookup"><span data-stu-id="dad31-326">Verification Page</span></span>  
 <span data-ttu-id="dad31-327">Используйте страницу **Проверка** диалогового окна **Выполнить пакет** для установки критерия версификации пакета.</span><span class="sxs-lookup"><span data-stu-id="dad31-327">Use the **Verification** page of the **Execute Package** dialog box to set criteria for verifying the package.</span></span>  
  
### <a name="options"></a><span data-ttu-id="dad31-328">Параметры</span><span class="sxs-lookup"><span data-stu-id="dad31-328">Options</span></span>  
 <span data-ttu-id="dad31-329">**Выполнять только подписанные пакеты**</span><span class="sxs-lookup"><span data-stu-id="dad31-329">**Execute only signed packages**</span></span>  
 <span data-ttu-id="dad31-330">Выберите для выполнения только подписанные пакеты.</span><span class="sxs-lookup"><span data-stu-id="dad31-330">Select to execute only packages that have been signed.</span></span>  
  
 <span data-ttu-id="dad31-331">**Проверить номер сборки пакета**</span><span class="sxs-lookup"><span data-stu-id="dad31-331">**Verify package build**</span></span>  
 <span data-ttu-id="dad31-332">Выберите, чтобы проверить сборку пакета.</span><span class="sxs-lookup"><span data-stu-id="dad31-332">Select to verify the package build.</span></span>  
  
 <span data-ttu-id="dad31-333">Сборка</span><span class="sxs-lookup"><span data-stu-id="dad31-333">Build</span></span>  
 <span data-ttu-id="dad31-334">Определите последовательный номер сборки, связанный с построением.</span><span class="sxs-lookup"><span data-stu-id="dad31-334">Specify the sequential Build number associated with the build.</span></span>  
  
 <span data-ttu-id="dad31-335">**Проверить идентификатор пакета**</span><span class="sxs-lookup"><span data-stu-id="dad31-335">**Verify package ID**</span></span>  
 <span data-ttu-id="dad31-336">Выберите, чтобы проверить идентификатор пакета.</span><span class="sxs-lookup"><span data-stu-id="dad31-336">Select to verify the package ID.</span></span>  
  
 <span data-ttu-id="dad31-337">Идентификатор пакета</span><span class="sxs-lookup"><span data-stu-id="dad31-337">Package ID</span></span>  
 <span data-ttu-id="dad31-338">Определите идентификационный номер пакета.</span><span class="sxs-lookup"><span data-stu-id="dad31-338">Specify the package identification number.</span></span>  
  
 <span data-ttu-id="dad31-339">**Проверить идентификатор версии**</span><span class="sxs-lookup"><span data-stu-id="dad31-339">**Verify version ID**</span></span>  
 <span data-ttu-id="dad31-340">Выберите, чтобы проверить версию идентификатора.</span><span class="sxs-lookup"><span data-stu-id="dad31-340">Select to verify the version ID.</span></span>  
  
 <span data-ttu-id="dad31-341">Идентификатор версии</span><span class="sxs-lookup"><span data-stu-id="dad31-341">Version ID</span></span>  
 <span data-ttu-id="dad31-342">Определите идентификационный номер версии.</span><span class="sxs-lookup"><span data-stu-id="dad31-342">Specify the version identification number.</span></span>  
  
 <span data-ttu-id="dad31-343">**Execute**</span><span class="sxs-lookup"><span data-stu-id="dad31-343">**Execute**</span></span>  
 <span data-ttu-id="dad31-344">Нажмите для выполнения пакета.</span><span class="sxs-lookup"><span data-stu-id="dad31-344">Click to run the package.</span></span>  
  
 <span data-ttu-id="dad31-345">**Закрыть**</span><span class="sxs-lookup"><span data-stu-id="dad31-345">**Close**</span></span>  
 <span data-ttu-id="dad31-346">Нажмите эту кнопку, чтобы закрыть диалоговое окно **Программа выполнения пакетов** .</span><span class="sxs-lookup"><span data-stu-id="dad31-346">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="command-line-page"></a><span data-ttu-id="dad31-347">Страница «Командная строка»</span><span class="sxs-lookup"><span data-stu-id="dad31-347">Command Line Page</span></span>  
 <span data-ttu-id="dad31-348">Узел **Командная строка** диалогового окна **Программа выполнения пакетов** служит для редактирования командной строки, сформированной с помощью параметров, задаваемых в различных диалоговых окнах.</span><span class="sxs-lookup"><span data-stu-id="dad31-348">Use the **Command Line** node of the **Execute Package Utility** dialog box to edit the command line that has been generated by the options created by the various dialogs.</span></span>  
  
### <a name="options"></a><span data-ttu-id="dad31-349">Параметры</span><span class="sxs-lookup"><span data-stu-id="dad31-349">Options</span></span>  
 <span data-ttu-id="dad31-350">**Восстановить первоначальные значения параметров**</span><span class="sxs-lookup"><span data-stu-id="dad31-350">**Restore the original options**</span></span>  
 <span data-ttu-id="dad31-351">Щелкните для восстановления командной строки до ее исходного состояния.</span><span class="sxs-lookup"><span data-stu-id="dad31-351">Click to restore the command line to its original state.</span></span> <span data-ttu-id="dad31-352">Этот параметр используется, если были произведены изменения с помощью параметра **Изменить командную строку вручную** и необходимо восстановить исходные параметры командной строки.</span><span class="sxs-lookup"><span data-stu-id="dad31-352">Use this option if you have made modifications using the **Edit the command line manually** option and want to restore the original command-line options.</span></span>  
  
 <span data-ttu-id="dad31-353">**Изменить командную строку вручную**</span><span class="sxs-lookup"><span data-stu-id="dad31-353">**Edit the command line manually**</span></span>  
 <span data-ttu-id="dad31-354">Нажмите для изменения командной строки в текстовом поле **Командная строка** .</span><span class="sxs-lookup"><span data-stu-id="dad31-354">Click to edit the command line in the **Command line** text box.</span></span>  
  
 <span data-ttu-id="dad31-355">**Командная строка**</span><span class="sxs-lookup"><span data-stu-id="dad31-355">**Command line**</span></span>  
 <span data-ttu-id="dad31-356">Отображается текущая командная строка.</span><span class="sxs-lookup"><span data-stu-id="dad31-356">Displays the current command line.</span></span> <span data-ttu-id="dad31-357">Она может редактироваться, если выбран параметр ручного изменения командной строки.</span><span class="sxs-lookup"><span data-stu-id="dad31-357">Editable if you selected the option to edit the command line manually.</span></span>  
  
 <span data-ttu-id="dad31-358">**Execute**</span><span class="sxs-lookup"><span data-stu-id="dad31-358">**Execute**</span></span>  
 <span data-ttu-id="dad31-359">Нажмите для выполнения пакета.</span><span class="sxs-lookup"><span data-stu-id="dad31-359">Click to run the package.</span></span>  
  
 <span data-ttu-id="dad31-360">**Закрыть**</span><span class="sxs-lookup"><span data-stu-id="dad31-360">**Close**</span></span>  
 <span data-ttu-id="dad31-361">Нажмите эту кнопку, чтобы закрыть диалоговое окно **Программа выполнения пакетов** .</span><span class="sxs-lookup"><span data-stu-id="dad31-361">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dad31-362">См. также:</span><span class="sxs-lookup"><span data-stu-id="dad31-362">See Also</span></span>  
 [<span data-ttu-id="dad31-363">Программа dtexec</span><span class="sxs-lookup"><span data-stu-id="dad31-363">dtexec Utility</span></span>](dtexec-utility.md)  
  
  
