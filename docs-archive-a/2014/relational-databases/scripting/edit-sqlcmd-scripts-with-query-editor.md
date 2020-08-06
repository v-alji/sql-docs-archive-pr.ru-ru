---
title: Изменение скриптов SQLCMD при помощи редактора запросов
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- scripts [SQL Server], SQLCMD scripts
- SQLCMD scripts
- modifying scripts
- Query Editor [Database Engine], SQLCMD scripts
- scripts [SQL Server], SQL Server Management Studio
ms.assetid: f77b866d-c330-47c9-9e74-0b8d8dff4b31
author: rothja
ms.author: jroth
ms.openlocfilehash: a3466cfc15ea2f4f0c8de5da42f4a1c24c28a575
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664843"
---
# <a name="edit-sqlcmd-scripts-with-query-editor"></a><span data-ttu-id="a393e-102">Изменение скриптов SQLCMD при помощи редактора запросов</span><span class="sxs-lookup"><span data-stu-id="a393e-102">Edit SQLCMD Scripts with Query Editor</span></span>
  <span data-ttu-id="a393e-103">Используя редактор запросов [!INCLUDE[ssDE](../../includes/ssde-md.md)] в [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] можно записывать и редактировать запросы в виде скриптов SQLMD.</span><span class="sxs-lookup"><span data-stu-id="a393e-103">By using the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] you can write and edit queries as SQLCMD scripts.</span></span> <span data-ttu-id="a393e-104">Скрипты SQLCMD применяются в тех случаях, когда необходимо обработать системные команды Windows и инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] в одном и том же скрипте.</span><span class="sxs-lookup"><span data-stu-id="a393e-104">You use SQLCMD scripts when you have to process Windows System commands and [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the same script.</span></span>  
  
## <a name="sqlcmd-mode"></a><span data-ttu-id="a393e-105">Режим SQLCMD</span><span class="sxs-lookup"><span data-stu-id="a393e-105">SQLCMD Mode</span></span>  
 <span data-ttu-id="a393e-106">Чтобы при помощи редактора запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] писать и изменять скрипты SQLCMD, необходимо включить режим скриптов SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="a393e-106">To use the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor to write or edit SQLCMD scripts, you must enable the SQLCMD scripting mode.</span></span> <span data-ttu-id="a393e-107">По умолчанию режим скриптов SQLCMD в редакторе запросов отключен.</span><span class="sxs-lookup"><span data-stu-id="a393e-107">By default, SQLCMD mode is not enabled in the Query Editor.</span></span> <span data-ttu-id="a393e-108">Режим скриптов можно включить, нажав кнопку **Режим SQLCMD** на панели инструментов или выбрав пункт **Режим SQLCMD** в меню **Запрос** .</span><span class="sxs-lookup"><span data-stu-id="a393e-108">You can enable scripting mode by clicking the **SQLCMD Mode** icon in the toolbar or by selecting **SQLCMD Mode** from the **Query** menu.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a393e-109">При включении режима скриптов SQLCMD отключается функция IntelliSense и отладчик [!INCLUDE[tsql](../../includes/tsql-md.md)] в редакторе запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a393e-109">Enabling SQLCMD mode turns off IntelliSense and the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor.</span></span>  
  
 <span data-ttu-id="a393e-110">В скриптах SQLCMD в редакторе запросов можно использовать те же возможности, что и в любых других скриптах [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a393e-110">SQLCMD scripts in the Query Editor can use the same features that all [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts use.</span></span> <span data-ttu-id="a393e-111">К таким средствам относятся:</span><span class="sxs-lookup"><span data-stu-id="a393e-111">These features include the following:</span></span>  
  
-   <span data-ttu-id="a393e-112">выделение цветом;</span><span class="sxs-lookup"><span data-stu-id="a393e-112">Color Coding</span></span>  
  
-   <span data-ttu-id="a393e-113">выполнение скриптов;</span><span class="sxs-lookup"><span data-stu-id="a393e-113">Executing Scripts</span></span>  
  
-   <span data-ttu-id="a393e-114">Система управления версиями</span><span class="sxs-lookup"><span data-stu-id="a393e-114">Source Control</span></span>  
  
-   <span data-ttu-id="a393e-115">синтаксический анализ скриптов;</span><span class="sxs-lookup"><span data-stu-id="a393e-115">Parsing Scripts</span></span>  
  
-   <span data-ttu-id="a393e-116">Showplan</span><span class="sxs-lookup"><span data-stu-id="a393e-116">Showplan</span></span>  
  
## <a name="enable-sqlcmd-scripting-in-query-editor"></a><span data-ttu-id="a393e-117">Включение режима скриптов SQLCMD в редакторе запросов</span><span class="sxs-lookup"><span data-stu-id="a393e-117">Enable SQLCMD Scripting in Query Editor</span></span>  
 <span data-ttu-id="a393e-118">Включить режим скриптов SQLCMD для активного окна редактора запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] можно при помощи следующей процедуры.</span><span class="sxs-lookup"><span data-stu-id="a393e-118">To turn SQLCMD scripting on for an active [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window, use the following procedure.</span></span>  
  
#### <a name="to-switch-a-database-engine-query-editor-window-to-sqlcmd-mode"></a><span data-ttu-id="a393e-119">Переключение окна редактора запросов компонента Database Engine в режим скриптов SQLCMD</span><span class="sxs-lookup"><span data-stu-id="a393e-119">To switch a Database Engine Query Editor window to SQLCMD mode</span></span>  
  
1.  <span data-ttu-id="a393e-120">В обозревателе объектов щелкните сервер правой кнопкой мыши и выберите команду **Создать запрос**, чтобы открыть новое окно редактора запросов [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a393e-120">In Object Explorer, right-click the server, and then click **New Query**, to open a new [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window.</span></span>  
  
2.  <span data-ttu-id="a393e-121">В меню **Запрос** выберите команду **Режим SQLCMD**.</span><span class="sxs-lookup"><span data-stu-id="a393e-121">On the **Query** menu, click **SQLCMD Mode**.</span></span>  
  
     <span data-ttu-id="a393e-122">Редактор запросов выполняет инструкции **sqlcmd** в контексте редактора запросов.</span><span class="sxs-lookup"><span data-stu-id="a393e-122">The Query Editor executes **sqlcmd** statements in the context of the Query Editor.</span></span>  
  
3.  <span data-ttu-id="a393e-123">На панели инструментов **Редактора SQL** в списке **Доступные базы данных** выберите пункт [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a393e-123">On the **SQL Editor** toolbar, in the **Available Databases** list, select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
4.  <span data-ttu-id="a393e-124">В окне редактора запросов введите две следующие инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] и инструкцию `!!DIR` **sqlcmd**.</span><span class="sxs-lookup"><span data-stu-id="a393e-124">In the Query Editor window, type the following two [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and the `!!DIR` **sqlcmd** statement:</span></span>  
  
    ```  
    SELECT DISTINCT Type FROM Sales.SpecialOffer;  
    GO  
    !!DIR  
    GO  
    SELECT ProductCategoryID, Name FROM Production.ProductCategory;  
    GO  
    ```  
  
5.  <span data-ttu-id="a393e-125">Нажмите клавишу F5, чтобы выполнить весь раздел, составленный из инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] и MS-DOS.</span><span class="sxs-lookup"><span data-stu-id="a393e-125">Press F5 to execute the whole section of mixed [!INCLUDE[tsql](../../includes/tsql-md.md)] and MS-DOS statements.</span></span>  
  
     <span data-ttu-id="a393e-126">Обратите внимание на две панели с результатами выполнения первой и третьей инструкций SQL.</span><span class="sxs-lookup"><span data-stu-id="a393e-126">Notice the two SQL result panes from the first and third statements.</span></span>  
  
6.  <span data-ttu-id="a393e-127">На панели **Результаты** перейдите на вкладку **Сообщения** , чтобы просмотреть сообщения всех трех инструкций.</span><span class="sxs-lookup"><span data-stu-id="a393e-127">In the **Results** pane, click the **Messages** tab to see the messages from all three statements:</span></span>  
  
    -   <span data-ttu-id="a393e-128">(Обработано строк: 6)</span><span class="sxs-lookup"><span data-stu-id="a393e-128">(6 row(s) affected)</span></span>  
  
    -   \<The directory information>  
  
    -   <span data-ttu-id="a393e-129">(Обработано строк: 4)</span><span class="sxs-lookup"><span data-stu-id="a393e-129">(4 row(s) affected)</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a393e-130">При выполнении из командной строки служебная программа **sqlcmd** позволяет добиться полного взаимодействия с операционной системой.</span><span class="sxs-lookup"><span data-stu-id="a393e-130">When executed from the command line, the **sqlcmd** utility permits full interaction with the operating system.</span></span> <span data-ttu-id="a393e-131">Используя редактор запросов в **Режиме SQLCMD**, будьте внимательны, чтобы не запустить интерактивные инструкции.</span><span class="sxs-lookup"><span data-stu-id="a393e-131">When you use the Query Editor in **SQLCMD Mode**, you must be careful not to execute interactive statements.</span></span> <span data-ttu-id="a393e-132">Редактор запросов не может моментально ответить операционной системе.</span><span class="sxs-lookup"><span data-stu-id="a393e-132">The Query Editor cannot respond to operating system prompts.</span></span>  
  
 <span data-ttu-id="a393e-133">Дополнительные сведения о выполнении инструкции SQLCMD см. в разделе [Служебная программа sqlcmd](../../tools/sqlcmd-utility.md)или изучите учебник по SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="a393e-133">For more information about how to run SQLCMD, see [sqlcmd Utility](../../tools/sqlcmd-utility.md), or take the SQLCMD tutorial.</span></span>  
  
## <a name="enable-sqlcmd-scripting-by-default"></a><span data-ttu-id="a393e-134">Включение режима скриптов SQLCMD по умолчанию</span><span class="sxs-lookup"><span data-stu-id="a393e-134">Enable SQLCMD Scripting by Default</span></span>  
 <span data-ttu-id="a393e-135">Чтобы режим скриптов SQLCMD включался по умолчанию, в меню **Сервис** выберите пункт **Параметры**, раскройте узлы **Выполнение запроса**и **SQL Server**, перейдите на страницу **Общие** и установите флажок **Открывать новые запросы в режиме SQLCMD** .</span><span class="sxs-lookup"><span data-stu-id="a393e-135">To turn SQLCMD scripting on by default, on the **Tools** menu select **Options**, expand **Query Execution**, and **SQL Server**, click the **General** page, and then check the **By default open new queries in SQLCMD Mode** box.</span></span>  
  
## <a name="writing-and-editing-sqlcmd-scripts"></a><span data-ttu-id="a393e-136">Создание и изменение скриптов SQLCMD</span><span class="sxs-lookup"><span data-stu-id="a393e-136">Writing and Editing SQLCMD Scripts</span></span>  
 <span data-ttu-id="a393e-137">После включения режима скриптов можно писать команды SQLCMD и инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a393e-137">After enabling scripting mode you may write SQLCMD commands and [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="a393e-138">Применяются следующие правила.</span><span class="sxs-lookup"><span data-stu-id="a393e-138">The following rules apply:</span></span>  
  
-   <span data-ttu-id="a393e-139">команда SQLCMD должна быть первой инструкцией в строке;</span><span class="sxs-lookup"><span data-stu-id="a393e-139">SQLCMD commands must be the first statement on a line.</span></span>  
  
-   <span data-ttu-id="a393e-140">в каждой строке разрешается только одна команда SQLCMD;</span><span class="sxs-lookup"><span data-stu-id="a393e-140">Only one SQLCMD command is permitted on each line.</span></span>  
  
-   <span data-ttu-id="a393e-141">перед командами SQLCMD могут идти комментарии или пробелы;</span><span class="sxs-lookup"><span data-stu-id="a393e-141">SQLCMD commands can be preceded by comments or white space.</span></span>  
  
-   <span data-ttu-id="a393e-142">команды SQLCMD внутри символов комментария не выполняются;</span><span class="sxs-lookup"><span data-stu-id="a393e-142">SQLCMD commands within comment characters are not executed.</span></span>  
  
-   <span data-ttu-id="a393e-143">символами однострочных комментариев являются два дефиса (`--)` , они должны находиться в начале строки;</span><span class="sxs-lookup"><span data-stu-id="a393e-143">Single line comment characters are two hyphens (`--)` and must appear at the beginning of a line.</span></span>  
  
-   <span data-ttu-id="a393e-144">перед командами операционной системы должны стоять два восклицательных знака (`!!`).</span><span class="sxs-lookup"><span data-stu-id="a393e-144">Operating system commands must be preceded by two exclamation points (`!!`).</span></span> <span data-ttu-id="a393e-145">Два восклицательных знака означают, что следующая за ними команда должна выполняться с помощью командного процессора `cmd.exe` .</span><span class="sxs-lookup"><span data-stu-id="a393e-145">The double-exclamation points command causes the statement that follows the exclamation points to be executed using the `cmd.exe` command processor.</span></span> <span data-ttu-id="a393e-146">Текст, следующий после `!!` , передается как параметр в `cmd.exe`, поэтому полная командная строка будет иметь следующий вид: `"%SystemRoot%\system32\cmd.exe /c <text after !!>"`.</span><span class="sxs-lookup"><span data-stu-id="a393e-146">The text after `!!` is passed in as a parameter to `cmd.exe`, so the final command line will execute as: `"%SystemRoot%\system32\cmd.exe /c <text after !!>"`.</span></span>  
  
-   <span data-ttu-id="a393e-147">чтобы четко различать команды SQLCMD и [!INCLUDE[tsql](../../includes/tsql-md.md)], ко всем командам SQLCMD необходимо добавлять префикс в виде двоеточия (`:`);</span><span class="sxs-lookup"><span data-stu-id="a393e-147">To make a clear distinction between SQLCMD commands and [!INCLUDE[tsql](../../includes/tsql-md.md)], all SQLCMD commands, need to be prefixed with a colon (`:`).</span></span>  
  
-   <span data-ttu-id="a393e-148">Команда `GO` может использоваться без вводной части. Кроме того, ей может предшествовать `!!:`</span><span class="sxs-lookup"><span data-stu-id="a393e-148">The `GO` command may be used without preface, or preceded by `!!:`</span></span>  
  
-   <span data-ttu-id="a393e-149">Редактор запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] поддерживает переменные среды и переменные, определенные в скрипте SQLCMD, однако не поддерживает встроенные переменные SQLCMD и **osql** .</span><span class="sxs-lookup"><span data-stu-id="a393e-149">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor supports environment variables and variables that are defined as part of a SQLCMD script, but does not support built-in SQLCMD or **osql** variables.</span></span> <span data-ttu-id="a393e-150">Обрабатываемый код SQLCMD среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] чувствителен к регистру переменных.</span><span class="sxs-lookup"><span data-stu-id="a393e-150">SQLCMD processing by [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] is case sensitive for variables.</span></span> <span data-ttu-id="a393e-151">Например, PRINT '$(COMPUTERNAME)' выдаст правильный результат, а PRINT '$(ComputerName)' приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="a393e-151">For example, PRINT '$(COMPUTERNAME)' produces the correct result, but PRINT '$(ComputerName)' returns an error.</span></span>  
  
> [!CAUTION]  
>  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="a393e-152">использует [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]SqlClient для выполнения в обычном режиме и в режиме SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="a393e-152">uses [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]SqlClient for execution in regular and SQLCMD mode.</span></span> <span data-ttu-id="a393e-153">При вызове из командной строки SQLCMD использует поставщика OLE DB.</span><span class="sxs-lookup"><span data-stu-id="a393e-153">When run from the command line, SQLCMD uses the OLE DB provider.</span></span> <span data-ttu-id="a393e-154">Так как могут применяться различные параметры по умолчанию, выполнение одного и того же запроса в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] в режиме SQLCMD и в программе SQLCMD может проходить по-разному.</span><span class="sxs-lookup"><span data-stu-id="a393e-154">Because different default options may apply, it is possible to get different behavior while executing the same query in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] SQLCMD Mode, and in the SQLCMD utility.</span></span>  
  
## <a name="supported-sqlcmd-syntax"></a><span data-ttu-id="a393e-155">Поддерживаемый синтаксис SQLCMD</span><span class="sxs-lookup"><span data-stu-id="a393e-155">Supported SQLCMD Syntax</span></span>  
 <span data-ttu-id="a393e-156">Редактор запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] поддерживает следующие ключевые слова сценариев SQLCMD:</span><span class="sxs-lookup"><span data-stu-id="a393e-156">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor supports the following SQLCMD script keywords:</span></span>  
  
 `[!!:]GO[count]`  
  
 `!! <command>`  
  
 `:exit(statement)`  
  
 `:Quit`  
  
 `:r <filename>`  
  
 `:setvar <var> <value>`  
  
 `:connect server[\instance] [-l login_timeout] [-U user [-P password]]`  
  
 `:on error [ignore|exit]`  
  
 `:error <filename>|stderr|stdout`  
  
 `:out <filename>|stderr|stdout`  
  
> [!NOTE]  
>  <span data-ttu-id="a393e-157">Для `:error` и `:out`, `stderr` и `stdout` вывод направляется на вкладку сообщений.</span><span class="sxs-lookup"><span data-stu-id="a393e-157">For both `:error` and `:out`, `stderr` and `stdout` send output to the messages tab.</span></span>  
  
 <span data-ttu-id="a393e-158">Команды SQLCMD, не перечисленные выше, редактором запросов не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="a393e-158">SQLCMD commands not listed above are not supported in Query Editor.</span></span> <span data-ttu-id="a393e-159">При выполнении скрипта, содержащего ключевые слова SQLCMD, которые не поддерживаются, редактор запросов отправит в назначение сообщение «команда пропускается», чтобы не поддерживаемое \<ignored command*> ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="a393e-159">When a script containing SQLCMD keywords that are not supported is executed, the Query Editor will send an "Ignoring command \*\<ignored command*>" message to the destination for each unsupported keyword.</span></span> <span data-ttu-id="a393e-160">Скрипт будет выполнен успешно, но неподдерживаемые команды не будут учитываться.</span><span class="sxs-lookup"><span data-stu-id="a393e-160">The script will execute successfully, but the unsupported commands will be ignored.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="a393e-161">Так как команды SQLCMD запускаются не из командной строки, при запуске редактора запросов в режиме SQLCMD действуют некоторые ограничения.</span><span class="sxs-lookup"><span data-stu-id="a393e-161">Because you are not starting SQLCMD from the command line, there are some limitations when running Query Editor in SQLCMD Mode.</span></span> <span data-ttu-id="a393e-162">Нельзя передавать параметры командной строки, например переменные. Кроме того, поскольку редактор запросов не поддерживает возможности реагировать на приглашения операционной системы, не следует выполнять интерактивные инструкции.</span><span class="sxs-lookup"><span data-stu-id="a393e-162">You cannot pass in command-line parameters such as variables, and, because the Query Editor does not have the ability to respond to operating system prompts, you must be careful not to execute interactive statements.</span></span>  
  
## <a name="color-coding-in-sqlcmd-scripts"></a><span data-ttu-id="a393e-163">Выделение цветом в скриптах SQLCMD</span><span class="sxs-lookup"><span data-stu-id="a393e-163">Color Coding in SQLCMD Scripts</span></span>  
 <span data-ttu-id="a393e-164">В режиме скриптов SQLCMD программный код скрипта выделяется разными цветами.</span><span class="sxs-lookup"><span data-stu-id="a393e-164">With SQLCMD scripting enabled, scripts will be color coded.</span></span> <span data-ttu-id="a393e-165">Выделение цветом ключевых слов [!INCLUDE[tsql](../../includes/tsql-md.md)] остается таким же.</span><span class="sxs-lookup"><span data-stu-id="a393e-165">The color coding for [!INCLUDE[tsql](../../includes/tsql-md.md)] keywords will remain the same.</span></span> <span data-ttu-id="a393e-166">Команды SQLCMD представлены с затененным фоном.</span><span class="sxs-lookup"><span data-stu-id="a393e-166">SQLCMD commands are presented with a shaded background.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a393e-167">Пример</span><span class="sxs-lookup"><span data-stu-id="a393e-167">Example</span></span>  
 <span data-ttu-id="a393e-168">В следующем примере используется инструкция **sqlcmd** . Чтобы создать выходной файл с именем testoutput.txt, выполняются две инструкции SELECT [!INCLUDE[tsql](../../includes/tsql-md.md)] и одна команда операционной системы (вывод содержимого текущего каталога).</span><span class="sxs-lookup"><span data-stu-id="a393e-168">The following example uses a **sqlcmd** statement to create an output file called testoutput.txt, executes two [!INCLUDE[tsql](../../includes/tsql-md.md)] SELECT statements along with one operating system command (to print out the current directory).</span></span> <span data-ttu-id="a393e-169">Итоговый файл содержит информацию о результатах выполнения инструкции `DIR` , которая следует за результатами выполнения инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a393e-169">The resultant file contains the message output from the `DIR` statement, followed by the results output from the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
```  
:out C:\testoutput.txt  
SELECT @@VERSION As 'Server Version'  
!!DIR  
!!:GO  
SELECT @@SERVERNAME AS 'Server Name'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="a393e-170">См. также:</span><span class="sxs-lookup"><span data-stu-id="a393e-170">See Also</span></span>  
 [<span data-ttu-id="a393e-171">Программа sqlcmd</span><span class="sxs-lookup"><span data-stu-id="a393e-171">sqlcmd Utility</span></span>](../../tools/sqlcmd-utility.md)  
  
  
