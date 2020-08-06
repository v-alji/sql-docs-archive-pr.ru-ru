---
title: Программа sqlps | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- sqlps utility
- PowerShell [SQL Server], sqlps utility
ms.assetid: 4b2515a6-12c3-44fb-b263-1c567681cd2b
author: stevestein
ms.author: sstein
ms.openlocfilehash: b445366b3fb99ad4beebdf7b203ada77afe90c8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727533"
---
# <a name="sqlps-utility"></a><span data-ttu-id="5a6eb-102">программа sqlps</span><span class="sxs-lookup"><span data-stu-id="5a6eb-102">sqlps Utility</span></span>
  <span data-ttu-id="5a6eb-103">Программа `sqlps` запускает сеанс Windows PowerShell 2.0 с помощью поставщика [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell, а также загруженных и зарегистрированных командлетов.</span><span class="sxs-lookup"><span data-stu-id="5a6eb-103">The `sqlps` utility starts a Windows PowerShell 2.0 session with the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell provider and cmdlets loaded and registered.</span></span> <span data-ttu-id="5a6eb-104">Можно вводить команды или скрипты PowerShell, в которых используются компоненты [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell для работы с экземплярами [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] и их объектами.</span><span class="sxs-lookup"><span data-stu-id="5a6eb-104">You can enter PowerShell commands or scripts that use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell components to work with instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] and their objects.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../includes/ssnotedepfutureavoid-md.md)] <span data-ttu-id="5a6eb-105">Вместо этого используйте модуль `sqlps` PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5a6eb-105">Use the `sqlps` PowerShell module instead.</span></span> <span data-ttu-id="5a6eb-106">Дополнительные сведения о `sqlps` модуле см. в разделе [Импорт модуля sqlps](../database-engine/import-the-sqlps-module.md).</span><span class="sxs-lookup"><span data-stu-id="5a6eb-106">For more information about the `sqlps` module, see [Import the SQLPS Module](../database-engine/import-the-sqlps-module.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a6eb-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5a6eb-107">Syntax</span></span>  
  
```  
  
      sqlps   
[ [ [ -NoLogo ][ -NoExit ][ -NoProfile ]  
    [ -OutPutFormat { Text | XML } ] [ -InPutFormat { Text | XML } ]  
  ]  
  [ -Command { -  
             | script_block [ -argsargument_array ]  
             | string [ command_parameters ]  
             }  
  ]  
]  
[ -? | -Help ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="5a6eb-108">Аргументы</span><span class="sxs-lookup"><span data-stu-id="5a6eb-108">Arguments</span></span>  
 <span data-ttu-id="5a6eb-109">**-NoLogo**</span><span class="sxs-lookup"><span data-stu-id="5a6eb-109">**-NoLogo**</span></span>  
 <span data-ttu-id="5a6eb-110">Указывает, что программа `sqlps` не должна отображать баннер со сведениями об авторских правах при запуске.</span><span class="sxs-lookup"><span data-stu-id="5a6eb-110">Specifies that the `sqlps` utility hide the copyright banner when it starts.</span></span>  
  
 <span data-ttu-id="5a6eb-111">**-NoExit**</span><span class="sxs-lookup"><span data-stu-id="5a6eb-111">**-NoExit**</span></span>  
 <span data-ttu-id="5a6eb-112">Указывает, что программа `sqlps` должна продолжать выполняться после выполнения команд запуска.</span><span class="sxs-lookup"><span data-stu-id="5a6eb-112">Specifies that the `sqlps` utility continue running after the startup commands have completed.</span></span>  
  
 <span data-ttu-id="5a6eb-113">**-NoProfile**</span><span class="sxs-lookup"><span data-stu-id="5a6eb-113">**-NoProfile**</span></span>  
 <span data-ttu-id="5a6eb-114">Указывает программе `sqlps` не загружать профиль пользователя.</span><span class="sxs-lookup"><span data-stu-id="5a6eb-114">Specifies that the `sqlps` utility not load a user profile.</span></span> <span data-ttu-id="5a6eb-115">В профилях пользователей записываются часто используемые псевдонимы, функции и переменные для использования в различных сеансах PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5a6eb-115">User profiles record commonly used aliases, functions, and variables for use across PowerShell sessions.</span></span>  
  
 <span data-ttu-id="5a6eb-116">**-OutPutFormat** { **Text** | **XML** }</span><span class="sxs-lookup"><span data-stu-id="5a6eb-116">**-OutPutFormat** { **Text** | **XML** }</span></span>  
 <span data-ttu-id="5a6eb-117">Указывает, что `sqlps` выходные данные служебной программы должны быть форматированы как текстовые строки (**текст**) или в сериализованном формате CLIXML (**XML**).</span><span class="sxs-lookup"><span data-stu-id="5a6eb-117">Specifies that the `sqlps` utility output be formatted as either text strings (**Text**) or in a serialized CLIXML format (**XML**).</span></span>  
  
 <span data-ttu-id="5a6eb-118">**-InPutFormat** { **Text** | **XML** }</span><span class="sxs-lookup"><span data-stu-id="5a6eb-118">**-InPutFormat** { **Text** | **XML** }</span></span>  
 <span data-ttu-id="5a6eb-119">Указывает, что входные данные для `sqlps` служебной программы форматируются как текстовые строки (**текст**) или в сериализованном формате CLIXML (**XML**).</span><span class="sxs-lookup"><span data-stu-id="5a6eb-119">Specifies that input to the `sqlps` utility is formatted as either text strings (**Text**) or in a serialized CLIXML format (**XML**).</span></span>  
  
 <span data-ttu-id="5a6eb-120">**-Command**</span><span class="sxs-lookup"><span data-stu-id="5a6eb-120">**-Command**</span></span>  
 <span data-ttu-id="5a6eb-121">Указывает команду для запуска программой `sqlps`.</span><span class="sxs-lookup"><span data-stu-id="5a6eb-121">Specifies the command for the `sqlps` utility to run.</span></span> <span data-ttu-id="5a6eb-122">`sqlps`Программа выполняет команду, а затем завершает работу, если не задан параметр **-Exit** .</span><span class="sxs-lookup"><span data-stu-id="5a6eb-122">The `sqlps` utility runs the command and then exits, unless **-NoExit** is also specified.</span></span> <span data-ttu-id="5a6eb-123">После параметра **-Command**не следует указывать какие-либо иные параметры, так как они будут интерпретироваться как параметры команды.</span><span class="sxs-lookup"><span data-stu-id="5a6eb-123">Do not specify any other switches after **-Command**, they will be read as command parameters.</span></span>  
  
 **-**  
 <span data-ttu-id="5a6eb-124">**-Command —** указывает, что `sqlps` Программа считывает входные данные из стандартного ввода.</span><span class="sxs-lookup"><span data-stu-id="5a6eb-124">**-Command-** specifies that the `sqlps` utility read the input from the standard input.</span></span>  
  
 <span data-ttu-id="5a6eb-125">*script_block* [ **-args**_argument_array_ ]</span><span class="sxs-lookup"><span data-stu-id="5a6eb-125">*script_block* [ **-args**_argument_array_ ]</span></span>  
 <span data-ttu-id="5a6eb-126">Указывает блок команд PowerShell для выполнения, который должен быть заключен в фигурные скобки: {}.</span><span class="sxs-lookup"><span data-stu-id="5a6eb-126">Specifies a block of PowerShell commands to run, the block must be enclosed in braces: {}.</span></span> <span data-ttu-id="5a6eb-127">*Script_block* можно указать только при `sqlps` вызове служебной программы из **PowerShell** или из другого `sqlps` сеанса программы.</span><span class="sxs-lookup"><span data-stu-id="5a6eb-127">*Script_block* can only be specified when the `sqlps` utility is called from either **PowerShell** or another `sqlps` utility session.</span></span> <span data-ttu-id="5a6eb-128">Параметр *массив_аргументов* представляет собой массив переменных PowerShell, содержащий аргументы для команд PowerShell из параметра *блок_скрипта*.</span><span class="sxs-lookup"><span data-stu-id="5a6eb-128">The *argument_array* is an array of PowerShell variables containing the arguments for the PowerShell commands in the *script_block*.</span></span>  
  
 <span data-ttu-id="5a6eb-129">*string* [ *параметры_команды* ]</span><span class="sxs-lookup"><span data-stu-id="5a6eb-129">*string* [ *command_parameters* ]</span></span>  
 <span data-ttu-id="5a6eb-130">Указывает строку, содержащую команды PowerShell для запуска.</span><span class="sxs-lookup"><span data-stu-id="5a6eb-130">Specifies a string that contains the PowerShell commands to be run.</span></span> <span data-ttu-id="5a6eb-131">Используйте формат **"& { *`command`* }"**.</span><span class="sxs-lookup"><span data-stu-id="5a6eb-131">Use the format **"&{*`command`*}"**.</span></span> <span data-ttu-id="5a6eb-132">Кавычки обозначают строку, а оператор Invoke (&) заставляет `sqlps` программу выполнить команду.</span><span class="sxs-lookup"><span data-stu-id="5a6eb-132">The quotation marks indicate a string, and the invoke operator (&) causes the `sqlps` utility to run the command.</span></span>  
  
 <span data-ttu-id="5a6eb-133">[ **-?**</span><span class="sxs-lookup"><span data-stu-id="5a6eb-133">[ **-?**</span></span><span data-ttu-id="5a6eb-134"> |  **-Help** ]</span><span class="sxs-lookup"><span data-stu-id="5a6eb-134"> | **-Help** ]</span></span>  
 <span data-ttu-id="5a6eb-135">Показывает синтаксис параметров программы `sqlps`.</span><span class="sxs-lookup"><span data-stu-id="5a6eb-135">Shows the syntax summary of the `sqlps` utility options.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a6eb-136">Remarks</span><span class="sxs-lookup"><span data-stu-id="5a6eb-136">Remarks</span></span>  
 <span data-ttu-id="5a6eb-137">`sqlps`Программа запускает среду PowerShell (PowerShell.exe) и загружает [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] модуль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5a6eb-137">The `sqlps` utility starts the PowerShell environment (PowerShell.exe) and loads the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell module.</span></span> <span data-ttu-id="5a6eb-138">Модуль, также именуемый `sqlps` , загружает и регистрирует следующие [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] оснастки PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5a6eb-138">The module, also named `sqlps`, loads and registers these [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell snap-ins:</span></span>  
  
-   <span data-ttu-id="5a6eb-139">Microsoft.SqlServer.Management.PSProvider.dll</span><span class="sxs-lookup"><span data-stu-id="5a6eb-139">Microsoft.SqlServer.Management.PSProvider.dll</span></span>  
  
     <span data-ttu-id="5a6eb-140">Реализует поставщик [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell и связанные с ним командлеты, такие как **Encode-SqlName** и **Decode-SqlName**.</span><span class="sxs-lookup"><span data-stu-id="5a6eb-140">Implements the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell provider and associated cmdlets such as **Encode-SqlName** and **Decode-SqlName**.</span></span>  
  
-   <span data-ttu-id="5a6eb-141">Microsoft.SqlServer.Management.PSSnapin.dll</span><span class="sxs-lookup"><span data-stu-id="5a6eb-141">Microsoft.SqlServer.Management.PSSnapin.dll</span></span>  
  
     <span data-ttu-id="5a6eb-142">Реализует командлеты **Invoke-Sqlcmd** и **Invoke-PolicyEvaluation** .</span><span class="sxs-lookup"><span data-stu-id="5a6eb-142">Implements the **Invoke-Sqlcmd** and **Invoke-PolicyEvaluation** cmdlets.</span></span>  
  
 <span data-ttu-id="5a6eb-143">С помощью программы `sqlps` можно делать следующее.</span><span class="sxs-lookup"><span data-stu-id="5a6eb-143">You can use the `sqlps` utility to do the following:</span></span>  
  
-   <span data-ttu-id="5a6eb-144">Вводить команды PowerShell в интерактивном режиме.</span><span class="sxs-lookup"><span data-stu-id="5a6eb-144">Interactively run PowerShell commands.</span></span>  
  
-   <span data-ttu-id="5a6eb-145">Запускать файлы скриптов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5a6eb-145">Run PowerShell script files.</span></span>  
  
-   <span data-ttu-id="5a6eb-146">Запускать командлеты служб [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5a6eb-146">Run [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cmdlets.</span></span>  
  
-   <span data-ttu-id="5a6eb-147">Использовать пути поставщика служб [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] для передвижения по иерархии объектов среды служб [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5a6eb-147">Use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider paths to navigate through the hierarchy of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects.</span></span>  
  
 <span data-ttu-id="5a6eb-148">По умолчанию `sqlps` программа запускается с политикой выполнения скриптов, для которой задано значение " **ограничено**".</span><span class="sxs-lookup"><span data-stu-id="5a6eb-148">By default, the `sqlps` utility runs with the scripting execution policy set to **Restricted**.</span></span> <span data-ttu-id="5a6eb-149">Это предотвращает запуск любых скриптов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5a6eb-149">This prevents running any PowerShell scripts.</span></span> <span data-ttu-id="5a6eb-150">Командлет **Set-ExecutionPolicy** обеспечивает возможность запуска как подписанных, так и любых других скриптов.</span><span class="sxs-lookup"><span data-stu-id="5a6eb-150">You can use the **Set-ExecutionPolicy** cmdlet to enable running signed scripts, or any scripts.</span></span> <span data-ttu-id="5a6eb-151">Запускать следует только скрипты из надежных источников, а также рекомендуется защитить все входные и выходные файлы соответствующими разрешениями NTFS.</span><span class="sxs-lookup"><span data-stu-id="5a6eb-151">Only run scripts from trusted sources, and secure all input and output files by using the appropriate NTFS permissions.</span></span> <span data-ttu-id="5a6eb-152">Дополнительные сведения о включении скриптов PowerShell см. в разделе [Запуск скриптов Windows PowerShell](https://www.tech-recipes.com/rx/2513/powershell_enable_script_support/).</span><span class="sxs-lookup"><span data-stu-id="5a6eb-152">For more information about enabling PowerShell scripts, see [Running Windows PowerShell Scripts](https://www.tech-recipes.com/rx/2513/powershell_enable_script_support/).</span></span>  
  
 <span data-ttu-id="5a6eb-153">Версия программы `sqlps` в [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] и [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] была реализована как мини-оболочка Windows PowerShell 1.0.</span><span class="sxs-lookup"><span data-stu-id="5a6eb-153">The version of the `sqlps` utility in [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] and [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] was implemented as a Windows PowerShell 1.0 mini-shell.</span></span> <span data-ttu-id="5a6eb-154">Мини-оболочки имеют определенные ограничения, такие как запрет на загрузку пользователями других оснасток, помимо загруженных мини-оболочкой.</span><span class="sxs-lookup"><span data-stu-id="5a6eb-154">Mini-shells have certain restrictions, such as not allowing users to load snap-ins other than those loaded by the mini-shell.</span></span> <span data-ttu-id="5a6eb-155">Эти ограничения не относятся к [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] и более поздним версиям программы, где изменилось использование модуля `sqlps`.</span><span class="sxs-lookup"><span data-stu-id="5a6eb-155">These restrictions do not apply to the [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] and higher versions of the utility, which have been changed to use the `sqlps` module.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="5a6eb-156">Примеры</span><span class="sxs-lookup"><span data-stu-id="5a6eb-156">Examples</span></span>  

### <a name="a-run-the-sqlps-utility-in-default-interactive-mode-without-the-copyright-banner"></a><span data-ttu-id="5a6eb-157">A.</span><span class="sxs-lookup"><span data-stu-id="5a6eb-157">A.</span></span> <span data-ttu-id="5a6eb-158">Запуск служебной программы sqlps в режиме по умолчанию (интерактивном) без баннера со сведениями об авторских правах</span><span class="sxs-lookup"><span data-stu-id="5a6eb-158">Run the sqlps utility in default, interactive mode without the copyright banner</span></span>
  
```cmd
sqlps -NoLogo  
```  
  
### <a name="b-run-a-sql-server-powershell-script-from-the-command-prompt"></a><span data-ttu-id="5a6eb-159">Б.</span><span class="sxs-lookup"><span data-stu-id="5a6eb-159">B.</span></span> <span data-ttu-id="5a6eb-160">Запуск скрипта SQL Server PowerShell из командной строки</span><span class="sxs-lookup"><span data-stu-id="5a6eb-160">Run a SQL Server PowerShell script from the command prompt</span></span>
  
```cmd
sqlps -Command "&{.\MyFolder.MyScript.ps1}"  
```  
  
### <a name="c-run-a-sql-server-powershell-script-from-the-command-prompt-and-keep-running-after-the-script-completes"></a><span data-ttu-id="5a6eb-161">В.</span><span class="sxs-lookup"><span data-stu-id="5a6eb-161">C.</span></span> <span data-ttu-id="5a6eb-162">Запуск скрипта SQL Server PowerShell из командной строки с продолжением выполнения после завершения скрипта</span><span class="sxs-lookup"><span data-stu-id="5a6eb-162">Run a SQL Server PowerShell script from the command prompt, and keep running after the script completes</span></span>
  
```cmd
sqlps -NoExit -Command "&{.\MyFolder.MyScript.ps1}"  
```  
  
## <a name="see-also"></a><span data-ttu-id="5a6eb-163">См. также:</span><span class="sxs-lookup"><span data-stu-id="5a6eb-163">See Also</span></span>  
 <span data-ttu-id="5a6eb-164">[Включение или отключение сетевого протокола сервера](../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="5a6eb-164">[Enable or Disable a Server Network Protocol](../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md) </span></span>  
 [<span data-ttu-id="5a6eb-165">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a6eb-165">SQL Server PowerShell</span></span>](../powershell/sql-server-powershell.md)  
