---
title: Работа с путями SQL Server PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: f31d8e2c-8d59-4fee-ac2a-324668e54262
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6d2647251eb1c8843d4ab7a95d2c439e47f5bb6a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731773"
---
# <a name="work-with-sql-server-powershell-paths"></a><span data-ttu-id="0f893-102">Работа с  путями SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f893-102">Work With SQL Server PowerShell Paths</span></span>
  <span data-ttu-id="0f893-103">После перехода к узлу в пути поставщика компонента [!INCLUDE[ssDE](../includes/ssde-md.md)] можно выполнять действия или с помощью методов и свойств извлекать информацию из управляющих объектов компонента [!INCLUDE[ssDE](../includes/ssde-md.md)] , связанных с этим узлом.</span><span class="sxs-lookup"><span data-stu-id="0f893-103">After you have navigated to a node in a [!INCLUDE[ssDE](../includes/ssde-md.md)] provider path, you can perform work or retrieve information by using the methods and properties from the [!INCLUDE[ssDE](../includes/ssde-md.md)] management object associated with the node.</span></span>  
  
1.  [<span data-ttu-id="0f893-104">Перед началом</span><span class="sxs-lookup"><span data-stu-id="0f893-104">Before You Begin</span></span>](#BeforeYouBegin)  
  
2.  <span data-ttu-id="0f893-105">**To work on a path node:**  [Listing Methods and Properties](#ListPropMeth), [Using Methods and Properties](#UsePropMeth)</span><span class="sxs-lookup"><span data-stu-id="0f893-105">**To work on a path node:**  [Listing Methods and Properties](#ListPropMeth), [Using Methods and Properties](#UsePropMeth)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0f893-106">Перед началом</span><span class="sxs-lookup"><span data-stu-id="0f893-106">Before You Begin</span></span>  
 <span data-ttu-id="0f893-107">После того как выбран узел в пути поставщика компонента [!INCLUDE[ssDE](../includes/ssde-md.md)] , можно выполнять действия двух типов.</span><span class="sxs-lookup"><span data-stu-id="0f893-107">After you have navigated to a node in a [!INCLUDE[ssDE](../includes/ssde-md.md)] provider path, you can perform two types of actions:</span></span>  
  
-   <span data-ttu-id="0f893-108">Можно запускать командлеты Windows PowerShell, работающие с узлами, такие как **Rename-Item**.</span><span class="sxs-lookup"><span data-stu-id="0f893-108">You can run Windows PowerShell cmdlets that operate on nodes, such as **Rename-Item**.</span></span>  
  
-   <span data-ttu-id="0f893-109">Можно вызывать методы из соответствующей модели управляющих объектов [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , например SMO.</span><span class="sxs-lookup"><span data-stu-id="0f893-109">You can call the methods from the associated [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] management object model, such as SMO.</span></span> <span data-ttu-id="0f893-110">Например, если перейти в пути к узлу Databases, то можно использовать методы и свойства класса <xref:Microsoft.SqlServer.Management.Smo.Database> .</span><span class="sxs-lookup"><span data-stu-id="0f893-110">For example, if you navigate to the Databases node in a path, you can use the methods and properties of the <xref:Microsoft.SqlServer.Management.Smo.Database> class.</span></span>  
  
 <span data-ttu-id="0f893-111">Поставщик [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] используется для управления объектами в экземпляре компонента [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f893-111">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider is used to manage the objects in an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="0f893-112">Он не предназначен для работы с данными в базах данных.</span><span class="sxs-lookup"><span data-stu-id="0f893-112">It is not used to work with the data in databases.</span></span> <span data-ttu-id="0f893-113">Если выбрана таблица или представление, нельзя использовать поставщик для выбора, вставки, обновления или удаления данных.</span><span class="sxs-lookup"><span data-stu-id="0f893-113">If you have navigated to a table or view, you cannot use the provider to select, insert, update, or delete data.</span></span> <span data-ttu-id="0f893-114">Чтобы запросить или изменить данные в таблицах и представлениях из среды Windows PowerShell, воспользуйтесь командлетом **Invoke-Sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="0f893-114">Use the **Invoke-Sqlcmd** cmdlet to query or change data in tables and views from the Windows PowerShell environment.</span></span> <span data-ttu-id="0f893-115">Дополнительные сведения см. в разделе [Invoke-Sqlcmd, командлет](../database-engine/invoke-sqlcmd-cmdlet.md).</span><span class="sxs-lookup"><span data-stu-id="0f893-115">For more information, see [Invoke-Sqlcmd cmdlet](../database-engine/invoke-sqlcmd-cmdlet.md).</span></span>  
  
##  <a name="listing-methods-and-properties"></a><a name="ListPropMeth"></a><span data-ttu-id="0f893-116">Вывод списка методов и свойств</span><span class="sxs-lookup"><span data-stu-id="0f893-116">Listing Methods and Properties</span></span>
  
 <span data-ttu-id="0f893-117">Командлет **Get-Member** используется для просмотра методов и свойств, доступных для определенных объектов или классов объектов.</span><span class="sxs-lookup"><span data-stu-id="0f893-117">To view the methods and properties available for specific objects or object classes, use the **Get-Member** cmdlet.</span></span>  
  
### <a name="examples-listing-methods-and-properties"></a><span data-ttu-id="0f893-118">Примеры: список методов и свойств</span><span class="sxs-lookup"><span data-stu-id="0f893-118">Examples: Listing Methods and Properties</span></span>  
 <span data-ttu-id="0f893-119">В этом примере задается переменная Windows PowerShell для класса <xref:Microsoft.SqlServer.Management.Smo.Database> модели SMO и перечисляются методы и свойства:</span><span class="sxs-lookup"><span data-stu-id="0f893-119">This example sets a Windows PowerShell variable to the SMO <xref:Microsoft.SqlServer.Management.Smo.Database> class and lists the methods and properties:</span></span>  
  
```powershell
$MyDBVar = New-Object Microsoft.SqlServer.Management.SMO.Database  
$MyDBVar | Get-Member -Type Methods  
$MyDBVar | Get-Member -Type Properties  
```  
  
 <span data-ttu-id="0f893-120">Командлет **Get-Member** также можно использовать для вывода методов и свойств, связанных с конечным узлом пути Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f893-120">You can also use **Get-Member** to list the methods and properties that are associated with the end node of a Windows PowerShell path.</span></span>  
  
 <span data-ttu-id="0f893-121">В этом примере выполняется переход к узлу Databases на диске SQLSERVER и перечисление свойства коллекции.</span><span class="sxs-lookup"><span data-stu-id="0f893-121">This example navigates to the Databases node in a SQLSERVER: path and lists the collection properties:</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases  
Get-Item . | Get-Member -Type Properties  
```  
  
 <span data-ttu-id="0f893-122">В этом примере выполняется переход к узлу AdventureWorks2012 по пути SQLSERVER: и перечисление свойства объектов.</span><span class="sxs-lookup"><span data-stu-id="0f893-122">This example navigates to the AdventureWorks2012 node in a SQLSERVER: path and lists the object properties:</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases\AdventureWorks2012  
Get-Item . | Get-Member -Type Properties  
```  
  
##  <a name="using-smo-methods-and-properties"></a><a name="UsePropMeth"></a><span data-ttu-id="0f893-123">Использование методов и свойств объектов SMO</span><span class="sxs-lookup"><span data-stu-id="0f893-123">Using SMO Methods and Properties</span></span>  
  
 <span data-ttu-id="0f893-124">Для выполнения действий с объектами из пути поставщика компонента [!INCLUDE[ssDE](../includes/ssde-md.md)] можно использовать методы и свойства объектов SMO.</span><span class="sxs-lookup"><span data-stu-id="0f893-124">To perform work on objects from a [!INCLUDE[ssDE](../includes/ssde-md.md)] provider path, you can use SMO methods and properties.</span></span>  
  
### <a name="examples-using-methods-and-properties"></a><span data-ttu-id="0f893-125">Примеры: использование методов и свойств</span><span class="sxs-lookup"><span data-stu-id="0f893-125">Examples: Using Methods and Properties</span></span>  
 <span data-ttu-id="0f893-126">В этом примере свойство **Schema** объекта SMO служит для получения списка таблиц из схемы Sales в базе данных AdventureWorks2012:</span><span class="sxs-lookup"><span data-stu-id="0f893-126">This example uses the SMO **Schema** property to get a list of the tables from the Sales schema in AdventureWorks2012:</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases\AdventureWorks2012\Tables  
Get-ChildItem | Where {$_.Schema -eq "Sales"}  
```  
  
 <span data-ttu-id="0f893-127">В этом примере используется метод **скрипта** SMO для создания скрипта, содержащего инструкции, которые необходимо `CREATE VIEW` выполнить для повторного создания представлений в AdventureWorks2012:</span><span class="sxs-lookup"><span data-stu-id="0f893-127">This example uses the SMO **Script** method to generate a script that contains the `CREATE VIEW` statements you must have to re-create the views in AdventureWorks2012:</span></span>  
  
```powershell
Remove-Item C:\PowerShell\CreateViews.sql  
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases\AdventureWorks2012\Views  
foreach ($Item in Get-ChildItem) { $Item.Script() | Out-File -Filepath C:\PowerShell\CreateViews.sql -append }  
```  
  
 <span data-ttu-id="0f893-128">В этом примере используется метод **Create** модели SMO, чтобы создать базу данных, а затем используется свойство **State** , чтобы показать, существует ли эта база данных:</span><span class="sxs-lookup"><span data-stu-id="0f893-128">This example uses the SMO **Create** method to create a database, and then uses the **State** property to show whether the database exists:</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases  
$MyDBVar = New-Object Microsoft.SqlServer.Management.SMO.Database  
$MyDBVar.Parent = (Get-Item ..)  
$MyDBVar.Name = "NewDB"  
$MyDBVar.Create()  
$MyDBVar.State  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f893-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="0f893-129">See Also</span></span>  
 <span data-ttu-id="0f893-130">[Поставщик SQL Server PowerShell](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="0f893-130">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 <span data-ttu-id="0f893-131">[Навигация по путям SQL Server PowerShell](navigate-sql-server-powershell-paths.md) </span><span class="sxs-lookup"><span data-stu-id="0f893-131">[Navigate SQL Server PowerShell Paths](navigate-sql-server-powershell-paths.md) </span></span>  
 <span data-ttu-id="0f893-132">[Преобразование URN в пути поставщика SQL Server](../database-engine/convert-urns-to-sql-server-provider-paths.md) </span><span class="sxs-lookup"><span data-stu-id="0f893-132">[Convert URNs to SQL Server Provider Paths](../database-engine/convert-urns-to-sql-server-provider-paths.md) </span></span>  
 [<span data-ttu-id="0f893-133">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f893-133">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
  
  
