---
title: Справка по PowerShell (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Help [PowerShell]
- Help [SQL Server], PowerShell
- PowerShell [SQL Server], help
ms.assetid: 968c316d-db83-4c24-8ea6-9f18736842f7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f1d97a3b694eebb924f9e1ff228d4d38da4f45ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732930"
---
# <a name="get-help-sql-server-powershell"></a><span data-ttu-id="8d8e9-102">Get Help SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d8e9-102">Get Help SQL Server PowerShell</span></span>
  <span data-ttu-id="8d8e9-103">Сведения об использовании поставщика и командлетов [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] для Windows PowerShell можно получить из нескольких источников.</span><span class="sxs-lookup"><span data-stu-id="8d8e9-103">There are several sources of information about using the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider for Windows PowerShell and cmdlets.</span></span> <span data-ttu-id="8d8e9-104">К ним относится справка, доступная в среде Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d8e9-104">This includes the help that is available in the Windows PowerShell environment.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="8d8e9-105">Перед началом</span><span class="sxs-lookup"><span data-stu-id="8d8e9-105">Before You Begin</span></span>  
 <span data-ttu-id="8d8e9-106">Дополнительные сведения о Windows PowerShell см. в разделе [Приступая к работе с Windows PowerShell](https://technet.microsoft.com/library/hh857337.aspx).</span><span class="sxs-lookup"><span data-stu-id="8d8e9-106">To learn about Windows PowerShell, see [Windows PowerShell Getting Started Guide](https://technet.microsoft.com/library/hh857337.aspx).</span></span>  
  
 <span data-ttu-id="8d8e9-107">Общие сведения о поставщике и командлетах [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] см. в статье [SQL Server PowerShell](../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="8d8e9-107">For an overview of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cmdlets and provider, see [SQL Server PowerShell](../powershell/sql-server-powershell.md).</span></span>  
  
### <a name="help-in-the-windows-powershell-environment"></a><span data-ttu-id="8d8e9-108">Справка в среде Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d8e9-108">Help in the Windows PowerShell Environment</span></span>  
 <span data-ttu-id="8d8e9-109">Командлет **Get-Help** позволяет получить справку в среде Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d8e9-109">Use the **Get-Help** cmdlet to get help in the Windows PowerShell environment.</span></span> <span data-ttu-id="8d8e9-110">Командлет**Get-Help** предоставляет основную справку по языку Windows PowerShell и различным командлетам и поставщикам, доступным в среде Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d8e9-110">**Get-Help** provides basic help for the Windows PowerShell language and the various cmdlets and providers available in Windows PowerShell.</span></span>  
  
 <span data-ttu-id="8d8e9-111">Дополнительные сведения о способах использования командлета **Get-Help**см. в документации по [получению справки с помощью командлета Get-Help](https://go.microsoft.com/fwlink/?LinkId=102136).</span><span class="sxs-lookup"><span data-stu-id="8d8e9-111">For more information on the ways you can use **Get-Help**, see [Get-Help: Getting Help](https://go.microsoft.com/fwlink/?LinkId=102136).</span></span>  
  
### <a name="sql-server-powershell-provider-help"></a><span data-ttu-id="8d8e9-112">Справка поставщика SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d8e9-112">SQL Server PowerShell Provider Help</span></span>  
 <span data-ttu-id="8d8e9-113">Поставщик [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell создает несколько папок на виртуальном диске SQLSERVER, среди них папки SQLSERVER:\SQL и SQLSERVER:\DAC.</span><span class="sxs-lookup"><span data-stu-id="8d8e9-113">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell provider implements several folders on a SQLSERVER virtual drive, such as the SQLSERVER:\SQL and SQLSERVER:\DAC folders.</span></span> <span data-ttu-id="8d8e9-114">Каждая папка связана с одной из объектных моделей управляемости SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8d8e9-114">Each folder is associated with one of the SQL Server manageability object models.</span></span> <span data-ttu-id="8d8e9-115">Пользователь может перечислять методы и свойства, связанные с каждым узлом в пути SQL Server, однако он не может получить справку по ним в среде PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d8e9-115">While you can list the methods and properties associated with each node in a SQL Server path, you cannot get help for them in the PowerShell environment.</span></span> <span data-ttu-id="8d8e9-116">Таблица папок со ссылками на соответствующие разделы справочника по программированию приведена в статье [SQL Server PowerShell, поставщик](../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="8d8e9-116">For a table of the folders with links to the associated programming reference, see [SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md).</span></span>  
  
### <a name="invoke-sqlcmd-help"></a><span data-ttu-id="8d8e9-117">Справка Invoke-Sqlcmd</span><span class="sxs-lookup"><span data-stu-id="8d8e9-117">Invoke-Sqlcmd Help</span></span>  
 <span data-ttu-id="8d8e9-118">Командлет **Invoke-Sqlcmd** принимает в качестве входных данных любой файл запроса или скрипта, который можно запустить с помощью программы **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="8d8e9-118">The **Invoke-Sqlcmd** cmdlet takes as input any query or script file that can be run by the **sqlcmd** utility.</span></span> <span data-ttu-id="8d8e9-119">**Get-Help** можно использовать для получения сведений о командлете **Invoke-Sqlcmd** и его параметрах, но **Get-Help** не охватывает запросы **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="8d8e9-119">You can use **Get-Help** to get information about **Invoke-Sqlcmd** and its parameters, but there is no **Get-Help** coverage for the **sqlcmd** queries.</span></span>  
  
 <span data-ttu-id="8d8e9-120">Параметр *-Query* или *-QueryFromFile* может содержать следующее:</span><span class="sxs-lookup"><span data-stu-id="8d8e9-120">The *-Query* or *-QueryFromFile* input can contain:</span></span>  
  
-   <span data-ttu-id="8d8e9-121">Переменные и команды**sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="8d8e9-121">**sqlcmd** variables and commands.</span></span> <span data-ttu-id="8d8e9-122">Сведения об этих переменных и командах см. в разделе "Примечания" статьи [Программа sqlcmd](../tools/sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="8d8e9-122">For information about these variables and commands, see the Remarks section of [sqlcmd Utility](../tools/sqlcmd-utility.md).</span></span>  
  
-   <span data-ttu-id="8d8e9-123">Инструкции[!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8d8e9-123">[!INCLUDE[tsql](../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="8d8e9-124">Дополнительные сведения о языке [!INCLUDE[tsql](../includes/tsql-md.md)] см. в [Справочнике по Transact-SQL (компонент Database Engine)](/sql/t-sql/language-reference).</span><span class="sxs-lookup"><span data-stu-id="8d8e9-124">For more information about the [!INCLUDE[tsql](../includes/tsql-md.md)] language, see [Transact-SQL Reference &#40;Database Engine&#41;](/sql/t-sql/language-reference).</span></span>  
  
-   <span data-ttu-id="8d8e9-125">Инструкции XQuery.</span><span class="sxs-lookup"><span data-stu-id="8d8e9-125">XQuery statements.</span></span> <span data-ttu-id="8d8e9-126">Сведения о языке XQuery, поддерживаемом [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], см. в [Справочнике по языку XQuery (SQL Server)](/sql/xquery/xquery-language-reference-sql-server).</span><span class="sxs-lookup"><span data-stu-id="8d8e9-126">For more information about the XQuery language supported by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [XQuery Language Reference &#40;SQL Server&#41;](/sql/xquery/xquery-language-reference-sql-server).</span></span>  
  
## <a name="get-help-for-a-sql-server-cmdlet"></a><span data-ttu-id="8d8e9-127">Получение справки по командлету SQL Server</span><span class="sxs-lookup"><span data-stu-id="8d8e9-127">Get Help for a SQL Server cmdlet</span></span>  
 <span data-ttu-id="8d8e9-128">**Справка по командлетам**</span><span class="sxs-lookup"><span data-stu-id="8d8e9-128">**To get help for a cmdlet**</span></span>  
  
-   <span data-ttu-id="8d8e9-129">Запустите командлет Get-Help, указав имя командлета и уровень справочных данных, которые должны быть возвращены.</span><span class="sxs-lookup"><span data-stu-id="8d8e9-129">Run Get-Help specifying the name of the cmdlet and the level of help to be returned.</span></span>  
  
### <a name="example-cmdlet-get-help"></a><span data-ttu-id="8d8e9-130">Пример: командлет Get-Help</span><span class="sxs-lookup"><span data-stu-id="8d8e9-130">Example: cmdlet Get-Help</span></span>  
 <span data-ttu-id="8d8e9-131">Следующие примеры возвращают справочные данные по командлету **Invoke-Sqlcmd**разного уровня.</span><span class="sxs-lookup"><span data-stu-id="8d8e9-131">The following examples return various levels of help for **Invoke-Sqlcmd**:</span></span>  
  
```powershell
## Get the basic help.  
Get-Help Invoke-Sqlcmd  
  
## Get the full help.  
Get-Help Invoke-Sqlcmd -Full  
  
## Get the parameter descriptions.  
Get-Help Invoke-Sqlcmd -Parameter *  
  
## Get the code examples.  
Get-Help Invoke-Sqlcmd -Examples  
  
## Get the syntax diagram.  
Get-Help Invoke-Sqlcmd -Syntax  
```  
  
## <a name="get-a-list-of-providers"></a><span data-ttu-id="8d8e9-132">Получение списка поставщиков</span><span class="sxs-lookup"><span data-stu-id="8d8e9-132">Get a List of Providers</span></span>  

### <a name="to-get-a-list-of-active-providers"></a><span data-ttu-id="8d8e9-133">Получение списка активных поставщиков</span><span class="sxs-lookup"><span data-stu-id="8d8e9-133">To get a list of active providers</span></span>
  
1.  <span data-ttu-id="8d8e9-134">Запустите командлет Get-Help, указав категорию поставщиков.</span><span class="sxs-lookup"><span data-stu-id="8d8e9-134">Run Get-Help specifying the provider category.</span></span>  
  
 <span data-ttu-id="8d8e9-135">Дополнительные сведения о получении справки поставщика в среде Windows PowerShell см. в разделе [Диски и поставщики](https://go.microsoft.com/fwlink/?LinkId=102137).</span><span class="sxs-lookup"><span data-stu-id="8d8e9-135">For more information about getting provider help in Windows PowerShell, see [Drives and Providers](https://go.microsoft.com/fwlink/?LinkId=102137).</span></span>  
  
### <a name="example-get-a-list-of-providers"></a><span data-ttu-id="8d8e9-136">Пример: получение списка поставщиков</span><span class="sxs-lookup"><span data-stu-id="8d8e9-136">Example: Get a List of Providers</span></span>  
 <span data-ttu-id="8d8e9-137">Следующий код возвращает список поставщиков, которые включены в текущем сеансе Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8d8e9-137">This code returns a list of the providers currently enabled in your Windows PowerShell session:</span></span>  
  
```powershell
Get-Help -Category provider  
```  
  
## <a name="get-help-about-the-sql-server-provider"></a><span data-ttu-id="8d8e9-138">Получение справки о поставщике SQL Server</span><span class="sxs-lookup"><span data-stu-id="8d8e9-138">Get Help About the SQL Server Provider</span></span>  
 <span data-ttu-id="8d8e9-139">**Получение справки о поставщике**</span><span class="sxs-lookup"><span data-stu-id="8d8e9-139">**To get help about the provider**</span></span>  
  
1.  <span data-ttu-id="8d8e9-140">Запустите командлет Get-Help, указав имя SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8d8e9-140">Run Get-Help specifying the name SQLServer</span></span>  
  
### <a name="example-get-sql-server-provider-help"></a><span data-ttu-id="8d8e9-141">Пример: получение справки о поставщике SQL Server</span><span class="sxs-lookup"><span data-stu-id="8d8e9-141">Example: Get SQL Server Provider Help</span></span>  
 <span data-ttu-id="8d8e9-142">Код, приведенные в этом примере, возвращает основные сведения о поставщике [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="8d8e9-142">This example returns basic information about the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider:</span></span>  
  
```powershell
Get-Help SQLServer  
```  
  
## <a name="list-methods-and-properties"></a><span data-ttu-id="8d8e9-143">Список методов и свойств</span><span class="sxs-lookup"><span data-stu-id="8d8e9-143">List Methods and Properties</span></span>  
 <span data-ttu-id="8d8e9-144">**Формирование списка методов и свойств узла из пути поставщика SQL Server**</span><span class="sxs-lookup"><span data-stu-id="8d8e9-144">**To list the methods and properties for a node in a SQL Server provider path**</span></span>  
  
1.  <span data-ttu-id="8d8e9-145">Перейдите в узел из пути SQL Server или создайте набор переменных к этому расположению.</span><span class="sxs-lookup"><span data-stu-id="8d8e9-145">Either CD to a node in the SQL Server path, or create a variable set to that location.</span></span>  
  
2.  <span data-ttu-id="8d8e9-146">Выполните командлет **Get-Member** с параметром-Type, для которого задано значение либо методы, либо свойства.</span><span class="sxs-lookup"><span data-stu-id="8d8e9-146">Run the **Get-Member** cmdlet with the -Type parameter set to either Methods or Properties</span></span>  
  
### <a name="examples-listing-methods-and-properties"></a><span data-ttu-id="8d8e9-147">Примеры: список методов и свойств</span><span class="sxs-lookup"><span data-stu-id="8d8e9-147">Examples: Listing Methods and Properties</span></span>  
 <span data-ttu-id="8d8e9-148">Этот пример формирует список методов, поддерживаемых для узла Databases.</span><span class="sxs-lookup"><span data-stu-id="8d8e9-148">This example lists the methods supported for the Databases node:</span></span>  
  
```powershell
Set-Location SQL:\MyComputer\DEFAULT\Databases  
Get-Item . | Get-Member -Type Methods  
```  
  
 <span data-ttu-id="8d8e9-149">Этот пример формирует список свойств для переменной, заданной объекту таблицы SMO.</span><span class="sxs-lookup"><span data-stu-id="8d8e9-149">This example lists the properties for a variable that has been set to an SMO Table object:</span></span>  
  
```powershell
$MyVar = New-Object Microsoft.SqlServer.Management.SMO.Table  
$MyVar | Get-Member -Type Properties  
```  
  
## <a name="see-also"></a><span data-ttu-id="8d8e9-150">См. также:</span><span class="sxs-lookup"><span data-stu-id="8d8e9-150">See Also</span></span>  
 <span data-ttu-id="8d8e9-151">[Поставщик SQL Server PowerShell](../powershell/sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="8d8e9-151">[SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="8d8e9-152">Использование командлетов компонента Database Engine</span><span class="sxs-lookup"><span data-stu-id="8d8e9-152">Use the Database Engine cmdlets</span></span>](../../2014/database-engine/use-the-database-engine-cmdlets.md)  
