---
title: Перемещение по путям PowerShell (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: d68aca48-d161-45ed-9f4f-14122ed30218
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0a605479991c3e907cd9dcae254cc1bc04a49392
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749996"
---
# <a name="navigate-sql-server-powershell-paths"></a><span data-ttu-id="e5cff-102">Перемещение путей SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5cff-102">Navigate SQL Server PowerShell Paths</span></span>
  <span data-ttu-id="e5cff-103">Поставщик компонента [!INCLUDE[ssDE](../includes/ssde-md.md)] PowerShell представляет набор объектов в экземпляре SQL Server в структуре, аналогичной пути к файлу.</span><span class="sxs-lookup"><span data-stu-id="e5cff-103">The [!INCLUDE[ssDE](../includes/ssde-md.md)] PowerShell provider exposes the set of objects in an instance of SQL Server in a structure similar to a file path.</span></span> <span data-ttu-id="e5cff-104">Командлеты Windows PowerShell можно использовать для навигации по пути поставщика и для создания нестандартных дисков, укорачивающих путь, который требуется ввести.</span><span class="sxs-lookup"><span data-stu-id="e5cff-104">You can use Windows PowerShell cmdlets to navigate the provider path, and create custom drives to shorten the path you have to type.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="e5cff-105">Перед началом</span><span class="sxs-lookup"><span data-stu-id="e5cff-105">Before You Begin</span></span>  
 <span data-ttu-id="e5cff-106">В Windows PowerShell предусмотрены командлеты для навигации по структуре пути, которая представляет иерархию объектов, поддерживаемых поставщиком PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e5cff-106">Windows PowerShell implements cmdlets to navigate the path structure that represent the hierarchy of objects supported by a PowerShell provider.</span></span> <span data-ttu-id="e5cff-107">После перехода к нужному узлу можно использовать другие командлеты для выполнения основных операций с текущим объектом.</span><span class="sxs-lookup"><span data-stu-id="e5cff-107">When you have navigated to a node in the path, you can use other cmdlets to perform basic operations on the current object.</span></span> <span data-ttu-id="e5cff-108">Поскольку командлеты используются часто, они обладают краткими каноническими псевдонимами.</span><span class="sxs-lookup"><span data-stu-id="e5cff-108">Because the cmdlets are used frequently, they have short, canonical aliases.</span></span> <span data-ttu-id="e5cff-109">Также существует один набор псевдонимов, сопоставляющий командлеты с похожими командами командной строки, и другой набор для команд оболочки UNIX.</span><span class="sxs-lookup"><span data-stu-id="e5cff-109">There is also one set of aliases that maps the cmdlets to similar command prompt commands, and another set for UNIX shell commands.</span></span>  
  
 <span data-ttu-id="e5cff-110">Поставщик [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] реализует подмножество командлетов поставщика, приведенных в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="e5cff-110">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider implements a subset of the provider cmdlets, shown in the following table.</span></span>  
  
|<span data-ttu-id="e5cff-111">командлет</span><span class="sxs-lookup"><span data-stu-id="e5cff-111">cmdlet</span></span>|<span data-ttu-id="e5cff-112">Канонический псевдоним</span><span class="sxs-lookup"><span data-stu-id="e5cff-112">Canonical alias</span></span>|<span data-ttu-id="e5cff-113">Псевдоним командной строки</span><span class="sxs-lookup"><span data-stu-id="e5cff-113">cmd alias</span></span>|<span data-ttu-id="e5cff-114">Псевдоним оболочки UNIX</span><span class="sxs-lookup"><span data-stu-id="e5cff-114">UNIX shell alias</span></span>|<span data-ttu-id="e5cff-115">Описание</span><span class="sxs-lookup"><span data-stu-id="e5cff-115">Description</span></span>|  
|------------|---------------------|---------------|----------------------|-----------------|  
|<span data-ttu-id="e5cff-116">**Get-Location**</span><span class="sxs-lookup"><span data-stu-id="e5cff-116">**Get-Location**</span></span>|<span data-ttu-id="e5cff-117">**gl**</span><span class="sxs-lookup"><span data-stu-id="e5cff-117">**gl**</span></span>|<span data-ttu-id="e5cff-118">**PWD**</span><span class="sxs-lookup"><span data-stu-id="e5cff-118">**pwd**</span></span>|<span data-ttu-id="e5cff-119">**PWD**</span><span class="sxs-lookup"><span data-stu-id="e5cff-119">**pwd**</span></span>|<span data-ttu-id="e5cff-120">Возвращает текущий узел.</span><span class="sxs-lookup"><span data-stu-id="e5cff-120">Gets the current node.</span></span>|  
|`Set-Location`|<span data-ttu-id="e5cff-121">**SL**</span><span class="sxs-lookup"><span data-stu-id="e5cff-121">**sl**</span></span>|<span data-ttu-id="e5cff-122">**cd, chdir**</span><span class="sxs-lookup"><span data-stu-id="e5cff-122">**cd, chdir**</span></span>|<span data-ttu-id="e5cff-123">**cd, chdir**</span><span class="sxs-lookup"><span data-stu-id="e5cff-123">**cd, chdir**</span></span>|<span data-ttu-id="e5cff-124">Изменяет текущий узел.</span><span class="sxs-lookup"><span data-stu-id="e5cff-124">Changes the current node.</span></span>|  
|<span data-ttu-id="e5cff-125">**Get-ChildItem**</span><span class="sxs-lookup"><span data-stu-id="e5cff-125">**Get-ChildItem**</span></span>|<span data-ttu-id="e5cff-126">**gci**</span><span class="sxs-lookup"><span data-stu-id="e5cff-126">**gci**</span></span>|<span data-ttu-id="e5cff-127">**dir**</span><span class="sxs-lookup"><span data-stu-id="e5cff-127">**dir**</span></span>|<span data-ttu-id="e5cff-128">**Местоположение**</span><span class="sxs-lookup"><span data-stu-id="e5cff-128">**ls**</span></span>|<span data-ttu-id="e5cff-129">Перечисляет объекты, хранящиеся в текущем узле.</span><span class="sxs-lookup"><span data-stu-id="e5cff-129">Lists the objects stored at the current node.</span></span>|  
|<span data-ttu-id="e5cff-130">**Get-Item**</span><span class="sxs-lookup"><span data-stu-id="e5cff-130">**Get-Item**</span></span>|<span data-ttu-id="e5cff-131">**gi**</span><span class="sxs-lookup"><span data-stu-id="e5cff-131">**gi**</span></span>|||<span data-ttu-id="e5cff-132">Возвращает свойства текущего элемента.</span><span class="sxs-lookup"><span data-stu-id="e5cff-132">Returns the properties of the current item.</span></span>|  
|<span data-ttu-id="e5cff-133">**Rename-Item**</span><span class="sxs-lookup"><span data-stu-id="e5cff-133">**Rename-Item**</span></span>|<span data-ttu-id="e5cff-134">**rni**</span><span class="sxs-lookup"><span data-stu-id="e5cff-134">**rni**</span></span>|<span data-ttu-id="e5cff-135">**RN**</span><span class="sxs-lookup"><span data-stu-id="e5cff-135">**rn**</span></span>|<span data-ttu-id="e5cff-136">**ren**</span><span class="sxs-lookup"><span data-stu-id="e5cff-136">**ren**</span></span>|<span data-ttu-id="e5cff-137">Переименовывает объект.</span><span class="sxs-lookup"><span data-stu-id="e5cff-137">Renames an object.</span></span>|  
|<span data-ttu-id="e5cff-138">**Remove-Item**</span><span class="sxs-lookup"><span data-stu-id="e5cff-138">**Remove-Item**</span></span>|<span data-ttu-id="e5cff-139">**ri**</span><span class="sxs-lookup"><span data-stu-id="e5cff-139">**ri**</span></span>|<span data-ttu-id="e5cff-140">**del, rd**</span><span class="sxs-lookup"><span data-stu-id="e5cff-140">**del, rd**</span></span>|<span data-ttu-id="e5cff-141">**rm, rmdir**</span><span class="sxs-lookup"><span data-stu-id="e5cff-141">**rm, rmdir**</span></span>|<span data-ttu-id="e5cff-142">Удаляет объект.</span><span class="sxs-lookup"><span data-stu-id="e5cff-142">Removes an object.</span></span>|  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e5cff-143">Некоторые идентификаторы [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] (имена объектов) содержат символы, которые не поддерживаются в именах путей Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e5cff-143">Some [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] identifiers (object names) contain characters that Windows PowerShell does not support in path names.</span></span> <span data-ttu-id="e5cff-144">Дополнительные сведения об использовании имен, содержащих такие символы, см. в разделе [SQL Server Identifiers in PowerShell](sql-server-identifiers-in-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="e5cff-144">For more information about how to use names that contain these characters, see [SQL Server Identifiers in PowerShell](sql-server-identifiers-in-powershell.md).</span></span>  
  
### <a name="sql-server-information-returned-by-get-childitem"></a><span data-ttu-id="e5cff-145">SQL Server сведения, возвращаемые командлетом Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="e5cff-145">SQL Server Information Returned by Get-ChildItem</span></span>  
 <span data-ttu-id="e5cff-146">Данные, возвращаемые командлетом **Get-ChildItem** (или его псевдонимами **dir** и **ls** ), зависят от текущего расположения на диске SQLSERVER.</span><span class="sxs-lookup"><span data-stu-id="e5cff-146">The information returned by **Get-ChildItem** (or its **dir** and **ls** aliases) depends on your location in a SQLSERVER: path.</span></span>  
  
|<span data-ttu-id="e5cff-147">Положение на пути</span><span class="sxs-lookup"><span data-stu-id="e5cff-147">Path location</span></span>|<span data-ttu-id="e5cff-148">Результаты выполнения Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="e5cff-148">Get-ChildItem results</span></span>|  
|-------------------|----------------------------|  
|<span data-ttu-id="e5cff-149">SQLSERVER:\SQL</span><span class="sxs-lookup"><span data-stu-id="e5cff-149">SQLSERVER:\SQL</span></span>|<span data-ttu-id="e5cff-150">Возвращает имя локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="e5cff-150">Returns the name of the local computer.</span></span> <span data-ttu-id="e5cff-151">Если соединения с экземплярами компонента [!INCLUDE[ssDE](../includes/ssde-md.md)] на других компьютерах устанавливалось с помощью объектов SMO или инструментария WMI, также будут приведены имена этих компьютеров.</span><span class="sxs-lookup"><span data-stu-id="e5cff-151">If you have used the SMO or WMI to connect to instances of the [!INCLUDE[ssDE](../includes/ssde-md.md)] on other computers, those computers are also listed.</span></span>|  
|<span data-ttu-id="e5cff-152">SQLSERVER:\SQL\\*ИмяКомпьютера*</span><span class="sxs-lookup"><span data-stu-id="e5cff-152">SQLSERVER:\SQL\\*ComputerName*</span></span>|<span data-ttu-id="e5cff-153">Список экземпляров компонента [!INCLUDE[ssDE](../includes/ssde-md.md)] на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e5cff-153">The list of instances of the [!INCLUDE[ssDE](../includes/ssde-md.md)] on the computer.</span></span>|  
|<span data-ttu-id="e5cff-154">SQLServer: \ SQL \\ *ComputerName* \\ *имя_экземпляра*</span><span class="sxs-lookup"><span data-stu-id="e5cff-154">SQLSERVER:\SQL\\*ComputerName*\\*InstanceName*</span></span>|<span data-ttu-id="e5cff-155">Список типов объектов верхнего уровня в экземпляре, таких как «Конечные точки», «Сертификаты» и «Базы данных».</span><span class="sxs-lookup"><span data-stu-id="e5cff-155">The list of top-level object types in the instance, such as Endpoints, Certificates, and Databases.</span></span>|  
|<span data-ttu-id="e5cff-156">Узел класса объектов, например «Базы данных»</span><span class="sxs-lookup"><span data-stu-id="e5cff-156">Object class node, such as Databases</span></span>|<span data-ttu-id="e5cff-157">Список объектов этого типа, например список баз данных: master, model, AdventureWorks20008R2.</span><span class="sxs-lookup"><span data-stu-id="e5cff-157">The list of objects of that type, such as the list of databases: master, model, AdventureWorks20008R2.</span></span>|  
|<span data-ttu-id="e5cff-158">Узел имени объекта, например AdventureWorks2012</span><span class="sxs-lookup"><span data-stu-id="e5cff-158">Object name node, such as AdventureWorks2012</span></span>|<span data-ttu-id="e5cff-159">Список типов объектов, содержащихся в этом объекте.</span><span class="sxs-lookup"><span data-stu-id="e5cff-159">The list of object types contained within the object.</span></span> <span data-ttu-id="e5cff-160">Например, для базы данных будет выведен список типов объектов, таких как таблицы и представления.</span><span class="sxs-lookup"><span data-stu-id="e5cff-160">For example, a database would list object types such as tables and views.</span></span>|  
  
 <span data-ttu-id="e5cff-161">По умолчанию командлет **Get-ChildItem** не выводит системные объекты.</span><span class="sxs-lookup"><span data-stu-id="e5cff-161">By default, **Get-ChildItem** does not list any system objects.</span></span> <span data-ttu-id="e5cff-162">Воспользуйтесь параметром *Force* для просмотра таких системных объектов, как объекты в схеме **sys**</span><span class="sxs-lookup"><span data-stu-id="e5cff-162">Use the *Force* parameter to see system objects, such as the objects in the **sys** schema.</span></span>  
  
### <a name="custom-drives"></a><span data-ttu-id="e5cff-163">Определение нестандартных дисков</span><span class="sxs-lookup"><span data-stu-id="e5cff-163">Custom Drives</span></span>  
 <span data-ttu-id="e5cff-164">Windows PowerShell позволяет определять виртуальные диски, которые называются дисками PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e5cff-164">Windows PowerShell lets users define virtual drives, which are referred to as PowerShell drives.</span></span> <span data-ttu-id="e5cff-165">Они сопоставляются начальным узлам в указании пути.</span><span class="sxs-lookup"><span data-stu-id="e5cff-165">These map over the starting nodes of a path statement.</span></span> <span data-ttu-id="e5cff-166">Обычно они используются в качестве краткой записи для часто используемых путей.</span><span class="sxs-lookup"><span data-stu-id="e5cff-166">They are typically used to shorten paths that are typed frequently.</span></span> <span data-ttu-id="e5cff-167">Пути диска SQLSERVER: могут оказаться длинными, занимать много места в окне Windows PowerShell и требовать много времени на ввод с клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="e5cff-167">SQLSERVER: paths can get long, taking space in the Windows PowerShell window and requiring a lot of typing.</span></span> <span data-ttu-id="e5cff-168">Если планируется выполнить большой объем работы для некоторого узла пути, для него можно определить нестандартный диск Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e5cff-168">If you are going to do a lot of work at a particular path node, you can define a custom Windows PowerShell drive that maps to that node.</span></span>  
  
## <a name="use-powershell-cmdlet-aliases"></a><span data-ttu-id="e5cff-169">Использование псевдонимов командлетов PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5cff-169">Use PowerShell Cmdlet Aliases</span></span>  
 <span data-ttu-id="e5cff-170">**Использование псевдонима командлета**</span><span class="sxs-lookup"><span data-stu-id="e5cff-170">**Use a cmdlet alias**</span></span>  
  
-   <span data-ttu-id="e5cff-171">Вместо полного имени командлета введите более короткий псевдоним или псевдоним, сопоставленный с известной командной строки.</span><span class="sxs-lookup"><span data-stu-id="e5cff-171">Instead of typing a full cmdlet name, type a shorter alias, or one that maps to a familiar commend prompt command.</span></span>  
  
### <a name="alias-example-powershell"></a><span data-ttu-id="e5cff-172">Пример псевдонима (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="e5cff-172">Alias Example (PowerShell)</span></span>  
 <span data-ttu-id="e5cff-173">Например, чтобы получить список экземпляров [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , доступных путем перехода к папке SQLSERVER:\SQL и запроса списка дочерних элементов для папки, можно использовать один из следующих наборов командлетов или псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="e5cff-173">For example, you can use one of the following sets of cmdlets or aliases to retrieve a listing of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instances available to you by navigating to the SQLSERVER:\SQL folder and requesting the list of child items for the folder:</span></span>  
  
```powershell
## Shows using the full cmdet name.  
Set-Location SQLSERVER:\SQL  
Get-ChildItem  
  
## Shows using canonical aliases.  
sl SQLSERVER:\SQL  
gci  
  
## Shows using command prompt aliases.  
cd SQLSERVER:\SQL  
dir  
  
## Shows using Unix shell aliases.  
cd SQLSERVER:\SQL  
ls  
```  
  
## <a name="use-get-childitem"></a><span data-ttu-id="e5cff-174">Использование Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="e5cff-174">Use Get-ChildItem</span></span>  

### <a name="return-information-by-using-get-childitem"></a><span data-ttu-id="e5cff-175">Получение сведений с помощью командлета Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="e5cff-175">Return information by using Get-Childitem</span></span>
  
1.  <span data-ttu-id="e5cff-176">Перейдите на узел, для которого хотите получить список потомков</span><span class="sxs-lookup"><span data-stu-id="e5cff-176">Navigate to the node for which you want a list of childrem</span></span>  
  
2.  <span data-ttu-id="e5cff-177">Выполните командлет Get-Childitem для получения списка.</span><span class="sxs-lookup"><span data-stu-id="e5cff-177">Run Get-Childitem to get the list.</span></span>  
  
### <a name="get-childitem-example-powershell"></a><span data-ttu-id="e5cff-178">Пример командлета Get-ChildItem пример (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="e5cff-178">Get-ChildItem Example (PowerShell)</span></span>  
 <span data-ttu-id="e5cff-179">Эти примеры показывают сведения, возвращаемые командлетом Get-ChildItem для различных узлов на пути поставщика SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e5cff-179">These examples illustrate the information returned by Get-Childitem for different nodes in a SQL Server provider path.</span></span>  
  
```powershell
## Return the current computer and any computer  
## to which you have made a SQL or WMI connection.  
Set-Location SQLSERVER:\SQL  
Get-ChildItem  
  
## List the instances of the Database Engine on the local computer.  
Set-Location SQLSERVER:\SQL\localhost  
Get-ChildItem  
  
## Lists the categories of objects available in the  
## default instance on the local computer.  
Set-Location SQLSERVER:\SQL\localhost\DEFAULT  
Get-ChildItem  
  
## Lists the databases from the local default instance.  
## The force parameter is used to include the system databases.  
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases  
Get-ChildItem -force  
```  
  
## <a name="create-a-custom-drive"></a><span data-ttu-id="e5cff-180">Создание пользовательского диска</span><span class="sxs-lookup"><span data-stu-id="e5cff-180">Create a Custom Drive</span></span>  

### <a name="create-and-use-a-custom-drive"></a><span data-ttu-id="e5cff-181">Создание и использование пользовательского диска</span><span class="sxs-lookup"><span data-stu-id="e5cff-181">Create and use a custom drive</span></span>
  
1.  <span data-ttu-id="e5cff-182">Использование `New-PSDrive` для определения пользовательского диска.</span><span class="sxs-lookup"><span data-stu-id="e5cff-182">Use `New-PSDrive` to define a custom drive.</span></span> <span data-ttu-id="e5cff-183">Используйте параметр `Root` для указания пути, представляемого именем пользовательского диска.</span><span class="sxs-lookup"><span data-stu-id="e5cff-183">Use the `Root` parameter to specify the path that is represented by the custom drive name.</span></span>  
  
2.  <span data-ttu-id="e5cff-184">Используйте имя пользовательского диска в таких командлетах прохождения пути, как `Set-Location`.</span><span class="sxs-lookup"><span data-stu-id="e5cff-184">Reference the custom drive name in path navigation cmdlets such as `Set-Location`.</span></span>  
  
### <a name="custom-drive-example-powershell"></a><span data-ttu-id="e5cff-185">Пример пользовательского диска (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="e5cff-185">Custom Drive Example (PowerShell)</span></span>  
 <span data-ttu-id="e5cff-186">В приведенном ниже примере создается виртуальный диск AWDB, сопоставленный с узлом для развернутой копии образца базы данных AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="e5cff-186">This example creates a virtual drive named AWDB that maps to the node for a deployed copy of the AdventureWorks2012 sample database.</span></span> <span data-ttu-id="e5cff-187">Виртуальный диск затем используется для перехода к таблице в базе данных.</span><span class="sxs-lookup"><span data-stu-id="e5cff-187">The virtual drive is then used to navigate to a table in the database.</span></span>  
  
```powershell
## Create a new virtual drive.  
New-PSDrive -Name AWDB -Root SQLSERVER:\SQL\localhost\DEFAULT\Databases\AdventureWorks2012  
  
## Use AWDB: to navigate to a specific table.  
Set-Location AWDB:\Tables\Purchasing.Vendor  
```  
  
## <a name="see-also"></a><span data-ttu-id="e5cff-188">См. также:</span><span class="sxs-lookup"><span data-stu-id="e5cff-188">See Also</span></span>  
 <span data-ttu-id="e5cff-189">[Поставщик SQL Server PowerShell](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="e5cff-189">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 <span data-ttu-id="e5cff-190">[Работа с путями SQL Server PowerShell](work-with-sql-server-powershell-paths.md) </span><span class="sxs-lookup"><span data-stu-id="e5cff-190">[Work With SQL Server PowerShell Paths](work-with-sql-server-powershell-paths.md) </span></span>  
 <span data-ttu-id="e5cff-191">[Преобразование URN в пути поставщика SQL Server](../database-engine/convert-urns-to-sql-server-provider-paths.md) </span><span class="sxs-lookup"><span data-stu-id="e5cff-191">[Convert URNs to SQL Server Provider Paths](../database-engine/convert-urns-to-sql-server-provider-paths.md) </span></span>  
 [<span data-ttu-id="e5cff-192">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5cff-192">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
