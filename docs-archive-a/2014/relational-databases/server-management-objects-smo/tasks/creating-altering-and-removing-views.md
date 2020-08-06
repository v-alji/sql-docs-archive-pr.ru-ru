---
title: Создание, изменение и удаление представлений | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- views [SMO]
ms.assetid: 7d445c0e-77ef-4734-993b-e022de31df23
author: stevestein
ms.author: sstein
ms.openlocfilehash: fd8d75e413b1871ce4b8784f5087cb08ed08da73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668197"
---
# <a name="creating-altering-and-removing-views"></a><span data-ttu-id="cbd6c-102">Создание, изменение и удаление представлений</span><span class="sxs-lookup"><span data-stu-id="cbd6c-102">Creating, Altering, and Removing Views</span></span>
  <span data-ttu-id="cbd6c-103">В [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] SMO представления [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] представлены объектом <xref:Microsoft.SqlServer.Management.Smo.View>.</span><span class="sxs-lookup"><span data-stu-id="cbd6c-103">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO), [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] views are represented by the <xref:Microsoft.SqlServer.Management.Smo.View> object.</span></span>  
  
 <span data-ttu-id="cbd6c-104">Свойство <xref:Microsoft.SqlServer.Management.Smo.View.TextBody%2A> объекта <xref:Microsoft.SqlServer.Management.Smo.View> определяет представление.</span><span class="sxs-lookup"><span data-stu-id="cbd6c-104">The <xref:Microsoft.SqlServer.Management.Smo.View.TextBody%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.View> object defines the view.</span></span> <span data-ttu-id="cbd6c-105">Это эквивалентно использованию инструкции [!INCLUDE[tsql](../../../includes/tsql-md.md)] SELECT для создания представления.</span><span class="sxs-lookup"><span data-stu-id="cbd6c-105">It is the equivalent of the [!INCLUDE[tsql](../../../includes/tsql-md.md)] SELECT statement for creating a view.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbd6c-106">Пример</span><span class="sxs-lookup"><span data-stu-id="cbd6c-106">Example</span></span>  
 <span data-ttu-id="cbd6c-107">Чтобы использовать какой-либо из представленных примеров кода, нужно выбрать среду, шаблон и язык программирования, с помощью которых будет создаваться приложение.</span><span class="sxs-lookup"><span data-stu-id="cbd6c-107">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="cbd6c-108">Дополнительные сведения см. в статьях [Создание проекта Visual Basic SMO в Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) или [Создание проекта Visual C&#35; SMO в Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="cbd6c-108">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-altering-and-removing-a-view-in-visual-basic"></a><span data-ttu-id="cbd6c-109">Создание, изменение и удаление представления на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cbd6c-109">Creating, Altering, and Removing a View in Visual Basic</span></span>  
 <span data-ttu-id="cbd6c-110">В этом образце кода показано создание представления двух таблиц с использованием внутреннего соединения.</span><span class="sxs-lookup"><span data-stu-id="cbd6c-110">This code sample shows how to create a view of two tables by using an inner join.</span></span> <span data-ttu-id="cbd6c-111">Представление создается с использованием текстового режима, поэтому для него необходимо задать свойство <xref:Microsoft.SqlServer.Management.Smo.View.TextHeader%2A>.</span><span class="sxs-lookup"><span data-stu-id="cbd6c-111">The view is created by using text mode, so the <xref:Microsoft.SqlServer.Management.Smo.View.TextHeader%2A> property must be set.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBViews1](SMO How to#SMO_VBViews1)]  -->  
  
## <a name="creating-altering-and-removing-a-view-in-visual-c"></a><span data-ttu-id="cbd6c-112">Создание, изменение и удаление представления на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="cbd6c-112">Creating, Altering, and Removing a View in Visual C#</span></span>  
 <span data-ttu-id="cbd6c-113">В этом образце кода показано создание представления двух таблиц с использованием внутреннего соединения.</span><span class="sxs-lookup"><span data-stu-id="cbd6c-113">This code sample shows how to create a view of two tables by using an inner join.</span></span> <span data-ttu-id="cbd6c-114">Представление создается с использованием текстового режима, поэтому для него необходимо задать свойство <xref:Microsoft.SqlServer.Management.Smo.View.TextHeader%2A>.</span><span class="sxs-lookup"><span data-stu-id="cbd6c-114">The view is created by using text mode, so the <xref:Microsoft.SqlServer.Management.Smo.View.TextHeader%2A> property must be set.</span></span>  
  
```csharp
{  
        //Connect to the local, default instance of SQL Server.   
        Server srv;   
        srv = new Server();   
        //Reference the AdventureWorks2012 database.   
        Database db;   
        db = srv.Databases["AdventureWorks2012"];   
        //Define a View object variable by supplying the parent database, view name and schema in the constructor.   
        View myview;   
        myview = new View(db, "Test_View", "Sales");   
        //Set the TextHeader and TextBody property to define the view.   
        myview.TextHeader = "CREATE VIEW [Sales].[Test_View] AS";   
        myview.TextBody = "SELECT h.SalesOrderID, d.OrderQty FROM Sales.SalesOrderHeader AS h INNER JOIN Sales.SalesOrderDetail AS d ON h.SalesOrderID = d.SalesOrderID";   
        //Create the view on the instance of SQL Server.   
        myview.Create();   
        //Remove the view.   
        myview.Drop();   
        }  
```  
  
## <a name="creating-altering-and-removing-a-view-in-powershell"></a><span data-ttu-id="cbd6c-115">Создание, изменение и удаление представления в PowerShell</span><span class="sxs-lookup"><span data-stu-id="cbd6c-115">Creating, Altering, and Removing a View in PowerShell</span></span>  
 <span data-ttu-id="cbd6c-116">В этом образце кода показано создание представления двух таблиц с использованием внутреннего соединения.</span><span class="sxs-lookup"><span data-stu-id="cbd6c-116">This code sample shows how to create a view of two tables by using an inner join.</span></span> <span data-ttu-id="cbd6c-117">Представление создается с использованием текстового режима, поэтому для него необходимо задать свойство <xref:Microsoft.SqlServer.Management.Smo.View.TextHeader%2A>.</span><span class="sxs-lookup"><span data-stu-id="cbd6c-117">The view is created by using text mode, so the <xref:Microsoft.SqlServer.Management.Smo.View.TextHeader%2A> property must be set.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server and get a reference to AdventureWorks2012  
CD \sql\localhost\default\databases  
$db = Get-Item Adventureworks2012  
  
# Define a View object variable by supplying the parent database, view name and schema in the constructor.
$myview  = New-Object -TypeName Microsoft.SqlServer.Management.SMO.View -argumentlist $db, "Test_View", "Sales"  
  
# Set the TextHeader and TextBody property to define the view.
$myview.TextHeader = "CREATE VIEW [Sales].[Test_View] AS"  
$myview.TextBody ="SELECT h.SalesOrderID, d.OrderQty FROM Sales.SalesOrderHeader AS h INNER JOIN Sales.SalesOrderDetail AS d ON h.SalesOrderID = d.SalesOrderID"  
  
# Create the view on the instance of SQL Server.
$myview.Create()  
  
# Remove the view
$myview.Drop();  
```  
  
## <a name="see-also"></a><span data-ttu-id="cbd6c-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="cbd6c-118">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.View>  
