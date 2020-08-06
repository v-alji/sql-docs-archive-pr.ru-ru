---
title: Использование программы sqlcmd с переменными скрипта
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- scripts [SQL Server], sqlcmd utility
- variables [SQL Server], scripts
- scripting variables [SQL Server]
- sqlcmd utility, scripts
- setvar command
ms.assetid: 793495ca-cfc9-498d-8276-c44a5d09a92c
author: rothja
ms.author: jroth
ms.openlocfilehash: 8443cb400dc099726ba75bfcec2d38cee4ee2dff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667027"
---
# <a name="use-sqlcmd-with-scripting-variables"></a><span data-ttu-id="7841b-102">Использование программы sqlcmd с переменными скрипта</span><span class="sxs-lookup"><span data-stu-id="7841b-102">Use sqlcmd with Scripting Variables</span></span>
  <span data-ttu-id="7841b-103">Переменные, которые используются в скриптах, называются переменными скрипта.</span><span class="sxs-lookup"><span data-stu-id="7841b-103">Variables that are used in scripts are called scripting variables.</span></span> <span data-ttu-id="7841b-104">Переменные скрипта позволяют использовать один скрипт в различных обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="7841b-104">Scripting variables enable one script to be used in multiple scenarios.</span></span> <span data-ttu-id="7841b-105">Например, если нужно выполнить один скрипт на нескольких серверах, вместо изменения скрипта для каждого сервера можно указать для имени сервера соответствующую переменную скрипта.</span><span class="sxs-lookup"><span data-stu-id="7841b-105">For example, if you want to run one script against multiple servers, instead of modifying the script for each server, you can use a scripting variable for the server name.</span></span> <span data-ttu-id="7841b-106">Изменяя имя сервера, указываемое в переменной скрипта, можно выполнять один и тот же скрипт на разных серверах.</span><span class="sxs-lookup"><span data-stu-id="7841b-106">By changing the server name supplied to the scripting variable, the same script can be executed on different servers.</span></span>  
  
 <span data-ttu-id="7841b-107">Переменные сценариев можно определить явно с помощью команды **setvar** или неявно с помощью параметра **sqlcmd-v** .</span><span class="sxs-lookup"><span data-stu-id="7841b-107">Scripting variables can be defined explicitly by using the **setvar** command, or implicitly by using the **sqlcmd-v** option.</span></span>  
  
 <span data-ttu-id="7841b-108">Кроме того, этот раздел содержит примеры определения переменных среды в командной строке Cmd.exe с помощью инструкции **SET**.</span><span class="sxs-lookup"><span data-stu-id="7841b-108">This topic also includes examples defining environmental variables at the Cmd.exe command prompt by using **SET**.</span></span>  
  
## <a name="setting-scripting-variables-by-using-the-setvar-command"></a><span data-ttu-id="7841b-109">Настройка переменных скрипта с помощью команды setvar</span><span class="sxs-lookup"><span data-stu-id="7841b-109">Setting Scripting Variables by Using the setvar Command</span></span>  
 <span data-ttu-id="7841b-110">Команда **setvar** используется для определения переменных сценария.</span><span class="sxs-lookup"><span data-stu-id="7841b-110">The **setvar** command is used to define scripting variables.</span></span> <span data-ttu-id="7841b-111">Переменные, определенные с помощью команды **setvar** , предназначены для внутреннего хранения.</span><span class="sxs-lookup"><span data-stu-id="7841b-111">Variables that are defined by using the **setvar** command are stored internally.</span></span> <span data-ttu-id="7841b-112">Переменные сценария не следует путать с переменными среды, которые определяются в командной строке с помощью инструкции **SET**.</span><span class="sxs-lookup"><span data-stu-id="7841b-112">Scripting variables should not be confused with environment variables that are defined at the command prompt by using **SET**.</span></span> <span data-ttu-id="7841b-113">Если сценарий ссылается на переменную, которая не является переменной среды или не определена с помощью команды **setvar**, то возвращается сообщение об ошибке, и выполнение сценария останавливается.</span><span class="sxs-lookup"><span data-stu-id="7841b-113">If a script references a variable that is not an environment variable or is not defined by using **setvar**, an error message is returned and the execution of the script will stop.</span></span> <span data-ttu-id="7841b-114">Дополнительные сведения см. в разделе о параметре **-b** статьи [Служебная программа sqlcmd](../../tools/sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="7841b-114">For more information, see the **-b** option in [sqlcmd Utility](../../tools/sqlcmd-utility.md).</span></span>  
  
## <a name="variable-precedence-low-to-high"></a><span data-ttu-id="7841b-115">Приоритет переменных (от низкого к высокому)</span><span class="sxs-lookup"><span data-stu-id="7841b-115">Variable Precedence (Low to High)</span></span>  
 <span data-ttu-id="7841b-116">Если несколько переменных имеют одинаковое имя, то используется переменная с более высоким приоритетом.</span><span class="sxs-lookup"><span data-stu-id="7841b-116">If more than one type of variable has the same name, the variable with the highest precedence is used.</span></span>  
  
1.  <span data-ttu-id="7841b-117">Системные переменные среды.</span><span class="sxs-lookup"><span data-stu-id="7841b-117">System level environmental variables</span></span>  
  
2.  <span data-ttu-id="7841b-118">Пользовательские переменные среды.</span><span class="sxs-lookup"><span data-stu-id="7841b-118">User level environmental variables</span></span>  
  
3.  <span data-ttu-id="7841b-119">Командная оболочка (**SET X=Y**), заданная в командной строке перед запуском **sqlcmd**</span><span class="sxs-lookup"><span data-stu-id="7841b-119">Command shell (**SET X=Y**) set at command prompt before starting **sqlcmd**</span></span>  
  
4.  <span data-ttu-id="7841b-120">**sqlcmd-v** X=Y</span><span class="sxs-lookup"><span data-stu-id="7841b-120">**sqlcmd-v** X=Y</span></span>  
  
5.  <span data-ttu-id="7841b-121">**:Setvar** X Y</span><span class="sxs-lookup"><span data-stu-id="7841b-121">**:Setvar** X Y</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7841b-122">Чтобы просмотреть переменные среды, на **панели управления**откройте компонент **Система**и перейдите на вкладку **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="7841b-122">To view the environmental variables, in **Control Panel**, open **System**, and then click the **Advanced** tab.</span></span>  
  
## <a name="implicitly-setting-scripting-variables"></a><span data-ttu-id="7841b-123">Неявное задание переменных скрипта</span><span class="sxs-lookup"><span data-stu-id="7841b-123">Implicitly Setting Scripting Variables</span></span>  
 <span data-ttu-id="7841b-124">При запуске программы **sqlcmd** с параметром, с которым связана переменная **sqlcmd** , переменной **sqlcmd** неявно присваивается значение, заданное для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="7841b-124">When you start **sqlcmd** with an option that has a related **sqlcmd** variable, the **sqlcmd** variable is set implicitly to the value that is specified by using the option.</span></span> <span data-ttu-id="7841b-125">В следующем примере программа `sqlcmd` запускается с параметром `-l` .</span><span class="sxs-lookup"><span data-stu-id="7841b-125">In the following example, `sqlcmd` is started with the `-l` option.</span></span> <span data-ttu-id="7841b-126">Этим неявно определяется переменная SQLLOGINTIMEOUT.</span><span class="sxs-lookup"><span data-stu-id="7841b-126">This implicitly sets the SQLLOGINTIMEOUT variable.</span></span>  
  
 `c:\> sqlcmd -l 60`  
  
 <span data-ttu-id="7841b-127">Кроме того, переменные сценария, которые в нем содержатся, задаются с помощью параметра **-v** .</span><span class="sxs-lookup"><span data-stu-id="7841b-127">You can also use the **-v** option to set a scripting variable that exists in a script.</span></span> <span data-ttu-id="7841b-128">В следующем скрипте (имя файла `testscript.sql`) `ColumnName` является переменной скрипта.</span><span class="sxs-lookup"><span data-stu-id="7841b-128">In the following script (the file name is `testscript.sql`), `ColumnName` is a scripting variable.</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `SELECT x.$(ColumnName)`  
  
 `FROM Person.Person x`  
  
 <span data-ttu-id="7841b-129">`WHERE c.`BusinessEntityID`< 5;`</span><span class="sxs-lookup"><span data-stu-id="7841b-129">`WHERE c.`BusinessEntityID `< 5;`</span></span>  
  
 <span data-ttu-id="7841b-130">Кроме того, с помощью параметра `-v` можно указать имя возвращаемого столбца:</span><span class="sxs-lookup"><span data-stu-id="7841b-130">You can then specify the name of the column that you want returned by using the `-v` option:</span></span>  
  
 `sqlcmd -v ColumnName ="FirstName" -i c:\testscript.sql`  
  
 <span data-ttu-id="7841b-131">Чтобы возвратить другой столбец с помощью того же скрипта, измените значение переменной скрипта `ColumnName` .</span><span class="sxs-lookup"><span data-stu-id="7841b-131">To return a different column by using the same script, change the value of the `ColumnName` scripting variable.</span></span>  
  
 `sqlcmd -v ColumnName ="LastName" -i c:\testscript.sql`  
  
## <a name="guidelines-for-scripting-variable-names-and-values"></a><span data-ttu-id="7841b-132">Правила выбора имен и значений переменных скрипта</span><span class="sxs-lookup"><span data-stu-id="7841b-132">Guidelines for Scripting Variable Names and Values</span></span>  
 <span data-ttu-id="7841b-133">Присваивая имена переменным скрипта, необходимо придерживаться следующих правил.</span><span class="sxs-lookup"><span data-stu-id="7841b-133">Consider the following guidelines when you name scripting variables:</span></span>  
  
-   <span data-ttu-id="7841b-134">Имена переменных не должны содержать символов пробела и кавычек.</span><span class="sxs-lookup"><span data-stu-id="7841b-134">Variable names must not contain white space characters or quotation marks.</span></span>  
  
-   <span data-ttu-id="7841b-135">Имена переменных не должны иметь такую же форму, как у выражений переменных *$(var)*.</span><span class="sxs-lookup"><span data-stu-id="7841b-135">Variable names must not have the same form as a variable expression, such as *$(var)*.</span></span>  
  
-   <span data-ttu-id="7841b-136">В переменных скрипта регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="7841b-136">Scripting variables are case-insensitive</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7841b-137">Если переменной среды **sqlcmd** не присвоено никакое значение, то она удаляется.</span><span class="sxs-lookup"><span data-stu-id="7841b-137">If no value is assigned to a **sqlcmd** environment variable, the variable is removed.</span></span> <span data-ttu-id="7841b-138">При использовании **:setvar VarName** без значения переменная очищается.</span><span class="sxs-lookup"><span data-stu-id="7841b-138">Using **:setvar VarName** without a value clears the variable.</span></span>  
  
 <span data-ttu-id="7841b-139">Присваивая значения переменным скрипта, необходимо придерживаться следующих правил.</span><span class="sxs-lookup"><span data-stu-id="7841b-139">Consider the following guidelines when you specify values for scripting variables:</span></span>  
  
-   <span data-ttu-id="7841b-140">Переменную, заданную с помощью параметра **setvar** или **-v** , необходимо заключать в кавычки, если строковое значение содержит пробелы.</span><span class="sxs-lookup"><span data-stu-id="7841b-140">Variable values that are defined by using **setvar** or the **-v** option must be enclosed by quotation marks if the string value contains spaces.</span></span>  
  
-   <span data-ttu-id="7841b-141">Если кавычки — часть значения переменной, то их необходимо экранировать.</span><span class="sxs-lookup"><span data-stu-id="7841b-141">If quotation marks are part of the variable value, they must be escaped.</span></span> <span data-ttu-id="7841b-142">Например,`setvar MyVar "spac""e"`.</span><span class="sxs-lookup"><span data-stu-id="7841b-142">For example: :`setvar MyVar "spac""e"`.</span></span>  
  
## <a name="guidelines-for-cmdexe-set-variable-values-and-names"></a><span data-ttu-id="7841b-143">Правила присваивания значений и имен переменным с помощью команды Cmd.exe SET</span><span class="sxs-lookup"><span data-stu-id="7841b-143">Guidelines for Cmd.exe SET Variable Values and Names</span></span>  
 <span data-ttu-id="7841b-144">Переменные, заданные с помощью инструкции SET, являются частью среды Cmd.exe, и на них может ссылаться программа **sqlcmd**.</span><span class="sxs-lookup"><span data-stu-id="7841b-144">Variables that are defined by using SET are part of the Cmd.exe environment and can be referenced by **sqlcmd**.</span></span> <span data-ttu-id="7841b-145">Ознакомьтесь со следующими рекомендациями:</span><span class="sxs-lookup"><span data-stu-id="7841b-145">Consider the following guidelines:</span></span>  
  
-   <span data-ttu-id="7841b-146">Имена переменных не должны содержать символов пробела и кавычек.</span><span class="sxs-lookup"><span data-stu-id="7841b-146">Variable names must not contain white space characters or quotation marks.</span></span>  
  
-   <span data-ttu-id="7841b-147">Значения переменных могут содержать символы пробела и кавычки.</span><span class="sxs-lookup"><span data-stu-id="7841b-147">Variable values may contain spaces or quotation marks.</span></span>  
  
## <a name="sqlcmd-scripting-variables"></a><span data-ttu-id="7841b-148">Переменные скрипта sqlcmd</span><span class="sxs-lookup"><span data-stu-id="7841b-148">sqlcmd Scripting Variables</span></span>  
 <span data-ttu-id="7841b-149">Переменные, которые определяются программой **sqlcmd** , называются переменными сценария.</span><span class="sxs-lookup"><span data-stu-id="7841b-149">Variables that are defined by **sqlcmd** are known as scripting variables.</span></span> <span data-ttu-id="7841b-150">В следующей таблице приведен список переменных сценария программы **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="7841b-150">The following table lists **sqlcmd** scripting variables.</span></span>  
  
|<span data-ttu-id="7841b-151">Переменная</span><span class="sxs-lookup"><span data-stu-id="7841b-151">Variable</span></span>|<span data-ttu-id="7841b-152">Связанный параметр</span><span class="sxs-lookup"><span data-stu-id="7841b-152">Related option</span></span>|<span data-ttu-id="7841b-153">Чтение-запись</span><span class="sxs-lookup"><span data-stu-id="7841b-153">R/W</span></span>|<span data-ttu-id="7841b-154">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="7841b-154">Default</span></span>|  
|--------------|--------------------|----------|-------------|  
|<span data-ttu-id="7841b-155">SQLCMDUSER\*</span><span class="sxs-lookup"><span data-stu-id="7841b-155">SQLCMDUSER\*</span></span>|<span data-ttu-id="7841b-156">-U</span><span class="sxs-lookup"><span data-stu-id="7841b-156">-U</span></span>|<span data-ttu-id="7841b-157">R</span><span class="sxs-lookup"><span data-stu-id="7841b-157">R</span></span>|<span data-ttu-id="7841b-158">""</span><span class="sxs-lookup"><span data-stu-id="7841b-158">""</span></span>|  
|<span data-ttu-id="7841b-159">SQLCMDPASSWORD\*</span><span class="sxs-lookup"><span data-stu-id="7841b-159">SQLCMDPASSWORD\*</span></span>|<span data-ttu-id="7841b-160">-P</span><span class="sxs-lookup"><span data-stu-id="7841b-160">-P</span></span>|--|<span data-ttu-id="7841b-161">""</span><span class="sxs-lookup"><span data-stu-id="7841b-161">""</span></span>|  
|<span data-ttu-id="7841b-162">SQLCMDSERVER\*</span><span class="sxs-lookup"><span data-stu-id="7841b-162">SQLCMDSERVER\*</span></span>|<span data-ttu-id="7841b-163">-S</span><span class="sxs-lookup"><span data-stu-id="7841b-163">-S</span></span>|<span data-ttu-id="7841b-164">R</span><span class="sxs-lookup"><span data-stu-id="7841b-164">R</span></span>|<span data-ttu-id="7841b-165">"DefaultLocalInstance"</span><span class="sxs-lookup"><span data-stu-id="7841b-165">"DefaultLocalInstance"</span></span>|  
|<span data-ttu-id="7841b-166">SQLCMDWORKSTATION</span><span class="sxs-lookup"><span data-stu-id="7841b-166">SQLCMDWORKSTATION</span></span>|<span data-ttu-id="7841b-167">-H</span><span class="sxs-lookup"><span data-stu-id="7841b-167">-H</span></span>|<span data-ttu-id="7841b-168">R</span><span class="sxs-lookup"><span data-stu-id="7841b-168">R</span></span>|<span data-ttu-id="7841b-169">"ComputerName"</span><span class="sxs-lookup"><span data-stu-id="7841b-169">"ComputerName"</span></span>|  
|<span data-ttu-id="7841b-170">SQLCMDDBNAME</span><span class="sxs-lookup"><span data-stu-id="7841b-170">SQLCMDDBNAME</span></span>|<span data-ttu-id="7841b-171">-d</span><span class="sxs-lookup"><span data-stu-id="7841b-171">-d</span></span>|<span data-ttu-id="7841b-172">R</span><span class="sxs-lookup"><span data-stu-id="7841b-172">R</span></span>|<span data-ttu-id="7841b-173">""</span><span class="sxs-lookup"><span data-stu-id="7841b-173">""</span></span>|  
|<span data-ttu-id="7841b-174">SQLCMDLOGINTIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7841b-174">SQLCMDLOGINTIMEOUT</span></span>|<span data-ttu-id="7841b-175">-l</span><span class="sxs-lookup"><span data-stu-id="7841b-175">-l</span></span>|<span data-ttu-id="7841b-176">Чтение-запись</span><span class="sxs-lookup"><span data-stu-id="7841b-176">R/W</span></span>|<span data-ttu-id="7841b-177">"8" (секунд)</span><span class="sxs-lookup"><span data-stu-id="7841b-177">"8" (seconds)</span></span>|  
|<span data-ttu-id="7841b-178">SQLCMDSTATTIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7841b-178">SQLCMDSTATTIMEOUT</span></span>|<span data-ttu-id="7841b-179">-T</span><span class="sxs-lookup"><span data-stu-id="7841b-179">-t</span></span>|<span data-ttu-id="7841b-180">Чтение-запись</span><span class="sxs-lookup"><span data-stu-id="7841b-180">R/W</span></span>|<span data-ttu-id="7841b-181">"0" = неограниченное время ожидания</span><span class="sxs-lookup"><span data-stu-id="7841b-181">"0" = wait indefinitely</span></span>|  
|<span data-ttu-id="7841b-182">SQLCMDHEADERS</span><span class="sxs-lookup"><span data-stu-id="7841b-182">SQLCMDHEADERS</span></span>|<span data-ttu-id="7841b-183">-H</span><span class="sxs-lookup"><span data-stu-id="7841b-183">-h</span></span>|<span data-ttu-id="7841b-184">Чтение-запись</span><span class="sxs-lookup"><span data-stu-id="7841b-184">R/W</span></span>|<span data-ttu-id="7841b-185">"0"</span><span class="sxs-lookup"><span data-stu-id="7841b-185">"0"</span></span>|  
|<span data-ttu-id="7841b-186">SQLCMDCOLSEP</span><span class="sxs-lookup"><span data-stu-id="7841b-186">SQLCMDCOLSEP</span></span>|<span data-ttu-id="7841b-187">-S</span><span class="sxs-lookup"><span data-stu-id="7841b-187">-s</span></span>|<span data-ttu-id="7841b-188">Чтение-запись</span><span class="sxs-lookup"><span data-stu-id="7841b-188">R/W</span></span>|<span data-ttu-id="7841b-189">" "</span><span class="sxs-lookup"><span data-stu-id="7841b-189">" "</span></span>|  
|<span data-ttu-id="7841b-190">SQLCMDCOLWIDTH</span><span class="sxs-lookup"><span data-stu-id="7841b-190">SQLCMDCOLWIDTH</span></span>|<span data-ttu-id="7841b-191">-w</span><span class="sxs-lookup"><span data-stu-id="7841b-191">-w</span></span>|<span data-ttu-id="7841b-192">Чтение-запись</span><span class="sxs-lookup"><span data-stu-id="7841b-192">R/W</span></span>|<span data-ttu-id="7841b-193">"0"</span><span class="sxs-lookup"><span data-stu-id="7841b-193">"0"</span></span>|  
|<span data-ttu-id="7841b-194">SQLCMDPACKETSIZE</span><span class="sxs-lookup"><span data-stu-id="7841b-194">SQLCMDPACKETSIZE</span></span>|<span data-ttu-id="7841b-195">-a</span><span class="sxs-lookup"><span data-stu-id="7841b-195">-a</span></span>|<span data-ttu-id="7841b-196">R</span><span class="sxs-lookup"><span data-stu-id="7841b-196">R</span></span>|<span data-ttu-id="7841b-197">"4096"</span><span class="sxs-lookup"><span data-stu-id="7841b-197">"4096"</span></span>|  
|<span data-ttu-id="7841b-198">SQLCMDERRORLEVEL</span><span class="sxs-lookup"><span data-stu-id="7841b-198">SQLCMDERRORLEVEL</span></span>|<span data-ttu-id="7841b-199">-M</span><span class="sxs-lookup"><span data-stu-id="7841b-199">-m</span></span>|<span data-ttu-id="7841b-200">Чтение-запись</span><span class="sxs-lookup"><span data-stu-id="7841b-200">R/W</span></span>|<span data-ttu-id="7841b-201">"0"</span><span class="sxs-lookup"><span data-stu-id="7841b-201">"0"</span></span>|  
|<span data-ttu-id="7841b-202">SQLCMDMAXVARTYPEWIDTH</span><span class="sxs-lookup"><span data-stu-id="7841b-202">SQLCMDMAXVARTYPEWIDTH</span></span>|<span data-ttu-id="7841b-203">-y</span><span class="sxs-lookup"><span data-stu-id="7841b-203">-y</span></span>|<span data-ttu-id="7841b-204">Чтение-запись</span><span class="sxs-lookup"><span data-stu-id="7841b-204">R/W</span></span>|<span data-ttu-id="7841b-205">«256»</span><span class="sxs-lookup"><span data-stu-id="7841b-205">"256"</span></span>|  
|<span data-ttu-id="7841b-206">SQLCMDMAXFIXEDTYPEWIDTH</span><span class="sxs-lookup"><span data-stu-id="7841b-206">SQLCMDMAXFIXEDTYPEWIDTH</span></span>|<span data-ttu-id="7841b-207">-y</span><span class="sxs-lookup"><span data-stu-id="7841b-207">-Y</span></span>|<span data-ttu-id="7841b-208">Чтение-запись</span><span class="sxs-lookup"><span data-stu-id="7841b-208">R/W</span></span>|<span data-ttu-id="7841b-209">"0" = неограниченное время ожидания</span><span class="sxs-lookup"><span data-stu-id="7841b-209">"0" = unlimited</span></span>|  
|<span data-ttu-id="7841b-210">SQLCMDEDITOR</span><span class="sxs-lookup"><span data-stu-id="7841b-210">SQLCMDEDITOR</span></span>||<span data-ttu-id="7841b-211">Чтение-запись</span><span class="sxs-lookup"><span data-stu-id="7841b-211">R/W</span></span>|<span data-ttu-id="7841b-212">"edit.com"</span><span class="sxs-lookup"><span data-stu-id="7841b-212">"edit.com"</span></span>|  
|<span data-ttu-id="7841b-213">SQLCMDINI</span><span class="sxs-lookup"><span data-stu-id="7841b-213">SQLCMDINI</span></span>||<span data-ttu-id="7841b-214">R</span><span class="sxs-lookup"><span data-stu-id="7841b-214">R</span></span>|<span data-ttu-id="7841b-215">""</span><span class="sxs-lookup"><span data-stu-id="7841b-215">""</span></span>|  
  
 <span data-ttu-id="7841b-216">\*SQLCMDUSER, SQLCMDPASSWORD и SQLCMDSERVER устанавливаются, когда используется **: Connect** .</span><span class="sxs-lookup"><span data-stu-id="7841b-216">\* SQLCMDUSER, SQLCMDPASSWORD and SQLCMDSERVER are set when **:Connect** is used.</span></span>  
  
 <span data-ttu-id="7841b-217">Пометка «Чтение» означает, что значение может быть задано только один раз в процессе инициализации программы.</span><span class="sxs-lookup"><span data-stu-id="7841b-217">R indicates the value can only be set one time during program initialization.</span></span>  
  
 <span data-ttu-id="7841b-218">Пометка "Чтение и запись" означает, что переменная может быть изменена командой **setvar** , и все последующие команды будут использовать новое значение.</span><span class="sxs-lookup"><span data-stu-id="7841b-218">R/W indicates that the value can be reset by using the **setvar** command and subsequent commands will use the new value.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="7841b-219">Примеры</span><span class="sxs-lookup"><span data-stu-id="7841b-219">Examples</span></span>  
  
### <a name="a-using-the-setvar-command-in-a-script"></a><span data-ttu-id="7841b-220">A.</span><span class="sxs-lookup"><span data-stu-id="7841b-220">A.</span></span> <span data-ttu-id="7841b-221">Использование команды setvar в скрипте</span><span class="sxs-lookup"><span data-stu-id="7841b-221">Using the setvar command in a script</span></span>  
 <span data-ttu-id="7841b-222">Команда **setvar** позволяет управлять многими параметрами программы **sqlcmd** в сценарии.</span><span class="sxs-lookup"><span data-stu-id="7841b-222">Many **sqlcmd** options can be controlled in a script by using the **setvar** command.</span></span> <span data-ttu-id="7841b-223">В следующем примере создается скрипт `test.sql` , в котором переменной `SQLCMDLOGINTIMEOUT` присваивается значение `60` , а другой переменной скрипта, `server`, присваивается значение `testserver`.</span><span class="sxs-lookup"><span data-stu-id="7841b-223">In the following example, the script `test.sql` is created in which the `SQLCMDLOGINTIMEOUT` variable is set to `60` seconds and another scripting variable, `server`, is set to `testserver`.</span></span> <span data-ttu-id="7841b-224">Следующий код входит в скрипт `test.sql`.</span><span class="sxs-lookup"><span data-stu-id="7841b-224">The following code is in `test.sql`.</span></span>  
  
 `:setvar SQLCMDLOGINTIMEOUT 60`  
  
 `:setvar server "testserver"`  
  
 `:connect $(server) -l $(SQLCMDLOGINTIMEOUT)`  
  
 `USE AdventureWorks2012;`  
  
 `SELECT FirstName, LastName`  
  
 `FROM Person.Person;`  
  
 `The script is then called by using sqlcmd:`  
  
 `sqlcmd -i c:\test.sql`  
  
### <a name="b-using-the-setvar-command-interactively"></a><span data-ttu-id="7841b-225">Б.</span><span class="sxs-lookup"><span data-stu-id="7841b-225">B.</span></span> <span data-ttu-id="7841b-226">Интерактивное использование команды setvar</span><span class="sxs-lookup"><span data-stu-id="7841b-226">Using the setvar command interactively</span></span>  
 <span data-ttu-id="7841b-227">В следующем примере показана интерактивная установка переменной сценария с помощью команды `setvar` .</span><span class="sxs-lookup"><span data-stu-id="7841b-227">The following example shows how to set a scripting variable interactively by using the `setvar` command.</span></span>  
  
 `sqlcmd`  
  
 `:setvar  MYDATABASE AdventureWorks2012`  
  
 `USE $(MYDATABASE);`  
  
 `GO`  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `Changed database context to 'AdventureWorks2012'`  
  
 `1>`  
  
### <a name="c-using-command-prompt-environment-variables-within-sqlcmd"></a><span data-ttu-id="7841b-228">В.</span><span class="sxs-lookup"><span data-stu-id="7841b-228">C.</span></span> <span data-ttu-id="7841b-229">Использование переменных среды командной строки в программе sqlcmd</span><span class="sxs-lookup"><span data-stu-id="7841b-229">Using command prompt environment variables within sqlcmd</span></span>  
 <span data-ttu-id="7841b-230">В следующем примере устанавливаются четыре переменные среды `are` , которые затем вызываются из `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="7841b-230">In the following example, four environment variables `are` set and then called from `sqlcmd`.</span></span>  
  
 `C:\>SET tablename=Person.Person`  
  
 `C:\>SET col1=FirstName`  
  
 `C:\>SET col2=LastName`  
  
 `C:\>SET title=Ms.`  
  
 `C:\>sqlcmd -d AdventureWorks2012`  
  
 `1> SELECT TOP 5 $(col1) + ' ' + $(col2) AS Name`  
  
 `2> FROM $(tablename)`  
  
 `3> WHERE Title ='$(title)'`  
  
 `4> GO`  
  
### <a name="d-using-user-level-environment-variables-within-sqlcmd"></a><span data-ttu-id="7841b-231">Г.</span><span class="sxs-lookup"><span data-stu-id="7841b-231">D.</span></span> <span data-ttu-id="7841b-232">Использование переменных среды уровня пользователя в программе sqlcmd</span><span class="sxs-lookup"><span data-stu-id="7841b-232">Using user-level environment variables within sqlcmd</span></span>  
 <span data-ttu-id="7841b-233">В следующем примере пользовательская переменная среды `%Temp%` устанавливается в командной строке и передается входному файлу `sqlcmd` .</span><span class="sxs-lookup"><span data-stu-id="7841b-233">In the following example the user-level environmental variable `%Temp%` is set at the command prompt and passed to the `sqlcmd` input file.</span></span> <span data-ttu-id="7841b-234">Чтобы просмотреть пользовательские переменные среды, на **панели управления**дважды щелкните компонент **Система**.</span><span class="sxs-lookup"><span data-stu-id="7841b-234">To obtain the user-level environment variable, in **Control Panel**, double-click **System**.</span></span> <span data-ttu-id="7841b-235">Перейдите на вкладку **Дополнительно** и щелкните **Переменные среды**.</span><span class="sxs-lookup"><span data-stu-id="7841b-235">Click the **Advance** tab, and then click **Environment Variables**.</span></span>  
  
 <span data-ttu-id="7841b-236">Следующий программный код является частью входного файла `c:\testscript.txt`:</span><span class="sxs-lookup"><span data-stu-id="7841b-236">The following code is in the input file `c:\testscript.txt`:</span></span>  
  
 `:OUT $(MyTempDirectory)`  
  
 `USE AdventureWorks2012;`  
  
 `SELECT FirstName`  
  
 `FROM AdventureWorks2012.Person.Person`  
  
 <span data-ttu-id="7841b-237">`WHERE BusinessEntityID` `< 5;`</span><span class="sxs-lookup"><span data-stu-id="7841b-237">`WHERE BusinessEntityID` `< 5;`</span></span>  
  
 <span data-ttu-id="7841b-238">Следующий программный код вводится в командной строке:</span><span class="sxs-lookup"><span data-stu-id="7841b-238">This following code is entered at the command prompt:</span></span>  
  
 `C:\ >SET MyTempDirectory=%Temp%\output.txt`  
  
 `C:\ >sqlcmd -i C:\testscript.txt`  
  
 <span data-ttu-id="7841b-239">Следующий результат передается выходному файлу C:\Documents and Settings\\<пользователь\>\Local Settings\Temp\output.txt.</span><span class="sxs-lookup"><span data-stu-id="7841b-239">The following result is sent to the output file C:\Documents and Settings\\<user\>\Local Settings\Temp\output.txt.</span></span>  
  
 `Changed database context to 'AdventureWorks2012'.`  
  
 `FirstName`  
  
 `--------------------------------------------------`  
  
 `Gustavo`  
  
 `Catherine`  
  
 `Kim`  
  
 `Humberto`  
  
 `(4 rows affected)`  
  
### <a name="e-using-a-startup-script"></a><span data-ttu-id="7841b-240">Д.</span><span class="sxs-lookup"><span data-stu-id="7841b-240">E.</span></span> <span data-ttu-id="7841b-241">Использование скрипта запуска</span><span class="sxs-lookup"><span data-stu-id="7841b-241">Using a startup script</span></span>  
 <span data-ttu-id="7841b-242">Сценарий запуска **sqlcmd** выполняется при запуске программы **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="7841b-242">A **sqlcmd** startup script is executed when **sqlcmd** is started.</span></span> <span data-ttu-id="7841b-243">В следующем примере задается переменная среды `SQLCMDINI`.</span><span class="sxs-lookup"><span data-stu-id="7841b-243">The following example sets the environment variable `SQLCMDINI`.</span></span> <span data-ttu-id="7841b-244">Ниже приведено содержимое сценария `init.sql.`</span><span class="sxs-lookup"><span data-stu-id="7841b-244">This is the contents of `init.sql.`</span></span>  
  
 `SET NOCOUNT ON`  
  
 `GO`  
  
 `DECLARE @nt_username nvarchar(128)`  
  
 `SET @nt_username = (SELECT rtrim(convert(nvarchar(128), nt_username))`  
  
 `FROM sys.dm_exec_sessions WHERE spid = @@SPID)`  
  
 `SELECT  @nt_username + ' is connected to ' +`  
  
 `rtrim(CONVERT(nvarchar(20), SERVERPROPERTY('servername'))) +`  
  
 `' (' +`  
  
 `rtrim(CONVERT(nvarchar(20), SERVERPROPERTY('productversion'))) +`  
  
 `')'`  
  
 `:setvar SQLCMDMAXFIXEDTYPEWIDTH 100`  
  
 `SET NOCOUNT OFF`  
  
 `GO`  
  
 `:setvar SQLCMDMAXFIXEDTYPEWIDTH`  
  
 <span data-ttu-id="7841b-245">Таким образом файл `init.sql` вызывается при запуске `sqlcmd` .</span><span class="sxs-lookup"><span data-stu-id="7841b-245">This calls the `init.sql` file when `sqlcmd` is started.</span></span>  
  
 `C:\> SET sqlcmdini=c:\init.sql`  
  
 `>1 Sqlcmd`  
  
 <span data-ttu-id="7841b-246">Результат.</span><span class="sxs-lookup"><span data-stu-id="7841b-246">This is the output.</span></span>  
  
 `>1 < user > is connected to < server > (9.00.2047.00)`  
  
> [!NOTE]  
>  <span data-ttu-id="7841b-247">Параметр **-X** отключает функцию сценария запуска.</span><span class="sxs-lookup"><span data-stu-id="7841b-247">The **-X** option disables the startup script feature.</span></span>  
  
### <a name="f-variable-expansion"></a><span data-ttu-id="7841b-248">Е.</span><span class="sxs-lookup"><span data-stu-id="7841b-248">F.</span></span> <span data-ttu-id="7841b-249">Расширение переменной</span><span class="sxs-lookup"><span data-stu-id="7841b-249">Variable expansion</span></span>  
 <span data-ttu-id="7841b-250">В следующем примере показана работа с данными в форме переменной **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="7841b-250">The following example shows working with data in the form of a **sqlcmd** variable.</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `CREATE TABLE AdventureWorks2012.dbo.VariableTest`  
  
 `(`  
  
 `Col1 nvarchar(50)`  
  
 `);`  
  
 `GO`  
  
 <span data-ttu-id="7841b-251">Вставляет одну строку в столбец `Col1` объекта базы данных `dbo.VariableTest` , содержащего значение `$(tablename)`.</span><span class="sxs-lookup"><span data-stu-id="7841b-251">Insert one row into `Col1` of `dbo.VariableTest` that contains the value `$(tablename)`.</span></span>  
  
 `INSERT INTO AdventureWorks2012.dbo.VariableTest(Col1)`  
  
 `VALUES('$(tablename)');`  
  
 `GO`  
  
 <span data-ttu-id="7841b-252">В командной строке `sqlcmd` , если ни одна переменная не равна `$(tablename)`, следующие инструкции возвращают эту строку.</span><span class="sxs-lookup"><span data-stu-id="7841b-252">At the `sqlcmd` prompt, when no variable is set equal to `$(tablename)`, the following statements return the row.</span></span>  
  
 `C:\> sqlcmd`  
  
 `>1 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = '$(tablename)';`  
  
 `>2 GO`  
  
 `>3 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = N'$(tablename)';`  
  
 `>4 GO`  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `>1 Col1`  
  
 `>2 ------------------`  
  
 `>3 $(tablename)`  
  
 `>4`  
  
 `>5 (1 rows affected)`  
  
 <span data-ttu-id="7841b-253">При условии, что переменная `MyVar` равна `$(tablename)`.</span><span class="sxs-lookup"><span data-stu-id="7841b-253">Given the variable `MyVar` is set to `$(tablename)`.</span></span>  
  
 `>6 :setvar MyVar $(tablename)`  
  
 <span data-ttu-id="7841b-254">Эти инструкции возвращают строку и сообщение «Переменная сценария "tablename" не определена».</span><span class="sxs-lookup"><span data-stu-id="7841b-254">These statements return the row and also return the message "'tablename' scripting variable not defined."</span></span>  
  
 `>6 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = '$(tablename)';`  
  
 `>7 GO`  
  
 `>1 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = N'$(tablename)';`  
  
 `>2 GO`  
  
 <span data-ttu-id="7841b-255">Эти инструкции возвращают строку.</span><span class="sxs-lookup"><span data-stu-id="7841b-255">These statements return the row.</span></span>  
  
 `>1 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = '$(MyVar)';`  
  
 `>2 GO`  
  
 `>1 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = N'$(MyVar)';`  
  
 `>2 GO`  
  
## <a name="see-also"></a><span data-ttu-id="7841b-256">См. также:</span><span class="sxs-lookup"><span data-stu-id="7841b-256">See Also</span></span>  
 <span data-ttu-id="7841b-257">[Использование программы sqlcmd](sqlcmd-use-the-utility.md) </span><span class="sxs-lookup"><span data-stu-id="7841b-257">[Use the sqlcmd Utility](sqlcmd-use-the-utility.md) </span></span>  
 <span data-ttu-id="7841b-258">[sqlcmd Utility](../../tools/sqlcmd-utility.md) </span><span class="sxs-lookup"><span data-stu-id="7841b-258">[sqlcmd Utility](../../tools/sqlcmd-utility.md) </span></span>  
 [<span data-ttu-id="7841b-259">Справочник по программе командной строки (Database Engine)</span><span class="sxs-lookup"><span data-stu-id="7841b-259">Command Prompt Utility Reference &#40;Database Engine&#41;</span></span>](../../tools/command-prompt-utility-reference-database-engine.md)  
  
  
