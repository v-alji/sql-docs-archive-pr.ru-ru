---
title: Использование коллекций | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQL Server Management Objects, collections
- SMO [SQL Server], collections
- collections [SMO]
ms.assetid: 209eb175-2514-4de1-bc32-b2e6a469d945
author: stevestein
ms.author: sstein
ms.openlocfilehash: 288f2110952a85d2aab610c0f1da40d433882400
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656269"
---
# <a name="using-collections"></a><span data-ttu-id="c98d3-102">Использование коллекций</span><span class="sxs-lookup"><span data-stu-id="c98d3-102">Using Collections</span></span>
  <span data-ttu-id="c98d3-103">Коллекция — это список объектов одного и того же класса с одним и тем же родительским объектом.</span><span class="sxs-lookup"><span data-stu-id="c98d3-103">A collection is a list of objects that have been constructed from the same object class and that share the same parent object.</span></span> <span data-ttu-id="c98d3-104">Объект коллекции всегда содержит имя типа объекта с суффиксом Collection.</span><span class="sxs-lookup"><span data-stu-id="c98d3-104">The collection object always contains the name of the object type with the Collection suffix.</span></span> <span data-ttu-id="c98d3-105">Например, для доступа к столбцам заданной таблицы используется тип <xref:Microsoft.SqlServer.Management.Smo.ColumnCollection>.</span><span class="sxs-lookup"><span data-stu-id="c98d3-105">For example, to access the columns in a specified table, use the <xref:Microsoft.SqlServer.Management.Smo.ColumnCollection> object type.</span></span> <span data-ttu-id="c98d3-106">Он содержит все объекты <xref:Microsoft.SqlServer.Management.Smo.Column>, принадлежащие одному и тому же объекту <xref:Microsoft.SqlServer.Management.Smo.Table>.</span><span class="sxs-lookup"><span data-stu-id="c98d3-106">It contains all the <xref:Microsoft.SqlServer.Management.Smo.Column> objects that belong to the same <xref:Microsoft.SqlServer.Management.Smo.Table> object.</span></span>  
  
 <span data-ttu-id="c98d3-107">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] `For...Each` Оператор или [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] `foreach` оператор можно использовать для итерации по каждому элементу коллекции.</span><span class="sxs-lookup"><span data-stu-id="c98d3-107">The [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] `For...Each` statement or the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] `foreach` statement can be used to iterate through each member of the collection.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c98d3-108">Примеры</span><span class="sxs-lookup"><span data-stu-id="c98d3-108">Examples</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="referencing-an-object-by-using-a-collection-in-visual-basic"></a><span data-ttu-id="c98d3-109">Ссылка на объект с помощью коллекции в языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c98d3-109">Referencing an Object by Using a Collection in Visual Basic</span></span>  
 <span data-ttu-id="c98d3-110">В данном примере кода демонстрируется задание свойства столбца с помощью свойств <xref:Microsoft.SqlServer.Management.Smo.TableViewTableTypeBase.Columns%2A>, <xref:Microsoft.SqlServer.Management.Smo.Database.Tables%2A> и <xref:Microsoft.SqlServer.Management.Smo.Server.Databases%2A>.</span><span class="sxs-lookup"><span data-stu-id="c98d3-110">This code example shows how to set a column property by using the <xref:Microsoft.SqlServer.Management.Smo.TableViewTableTypeBase.Columns%2A>, <xref:Microsoft.SqlServer.Management.Smo.Database.Tables%2A>, and <xref:Microsoft.SqlServer.Management.Smo.Server.Databases%2A> properties.</span></span> <span data-ttu-id="c98d3-111">Эти свойства представляют собой коллекции, с помощью которых можно указать на конкретный объект при их использовании с именем объекта в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="c98d3-111">These properties represent collections, which can be used to identify a particular object when they are used with a parameter that specifies the name of the object.</span></span> <span data-ttu-id="c98d3-112">Для свойства объекта коллекции <xref:Microsoft.SqlServer.Management.Smo.Database.Tables%2A> требуются имя и схема.</span><span class="sxs-lookup"><span data-stu-id="c98d3-112">The name and the schema are required for the <xref:Microsoft.SqlServer.Management.Smo.Database.Tables%2A> collection object property.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBCollections1](SMO How to#SMO_VBCollections1)]  -->  
  
## <a name="referencing-an-object-by-using-a-collection-in-visual-c"></a><span data-ttu-id="c98d3-113">Ссылка на объект с помощью коллекции в языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="c98d3-113">Referencing an Object by Using a Collection in Visual C#</span></span>  
 <span data-ttu-id="c98d3-114">В данном примере кода демонстрируется задание свойства столбца с помощью свойств <xref:Microsoft.SqlServer.Management.Smo.TableViewTableTypeBase.Columns%2A>, <xref:Microsoft.SqlServer.Management.Smo.Database.Tables%2A> и <xref:Microsoft.SqlServer.Management.Smo.Server.Databases%2A>.</span><span class="sxs-lookup"><span data-stu-id="c98d3-114">This code example shows how to set a column property by using the <xref:Microsoft.SqlServer.Management.Smo.TableViewTableTypeBase.Columns%2A>, <xref:Microsoft.SqlServer.Management.Smo.Database.Tables%2A>, and <xref:Microsoft.SqlServer.Management.Smo.Server.Databases%2A> properties.</span></span> <span data-ttu-id="c98d3-115">Эти свойства представляют собой коллекции, с помощью которых можно указать на конкретный объект при их использовании с именем объекта в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="c98d3-115">These properties represent collections, which can be used to identify a particular object when they are used with a parameter that specifies the name of the object.</span></span> <span data-ttu-id="c98d3-116">Для свойства объекта коллекции <xref:Microsoft.SqlServer.Management.Smo.Database.Tables%2A> требуются имя и схема.</span><span class="sxs-lookup"><span data-stu-id="c98d3-116">The name and the schema are required for the <xref:Microsoft.SqlServer.Management.Smo.Database.Tables%2A> collection object property.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Modify a property using the Databases, Tables, and Columns collections to reference a column.   
srv.Databases("AdventureWorks2012").Tables("Person", "Person").Columns("LastName").Nullable = true;   
//Call the Alter method to make the change on the instance of SQL Server.   
srv.Databases("AdventureWorks2012").Tables("Person", "Person").Columns("LastName").Alter();   
}  
```  
  
## <a name="iterating-through-the-members-of-a-collection-in-visual-basic"></a><span data-ttu-id="c98d3-117">Последовательный перебор элементов коллекции на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c98d3-117">Iterating Through the Members of a Collection in Visual Basic</span></span>  
 <span data-ttu-id="c98d3-118">В данном примере кода выполняется итерация по коллекции <xref:Microsoft.AnalysisServices.Server.Databases%2A> и отображаются все подключения базы данных к экземпляру [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c98d3-118">This code example iterates through the <xref:Microsoft.AnalysisServices.Server.Databases%2A> collection property and displays all database connections to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBCollections2](SMO How to#SMO_VBCollections2)]  -->  
  
## <a name="iterating-through-the-members-of-a-collection-in-visual-c"></a><span data-ttu-id="c98d3-119">Последовательный перебор элементов коллекции на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="c98d3-119">Iterating Through the Members of a Collection in Visual C#</span></span>  
 <span data-ttu-id="c98d3-120">В данном примере кода выполняется итерация по коллекции <xref:Microsoft.AnalysisServices.Server.Databases%2A> и отображаются все подключения базы данных к экземпляру [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c98d3-120">This code example iterates through the <xref:Microsoft.AnalysisServices.Server.Databases%2A> collection property and displays all database connections to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
```  
//Connect to the local, default instance of SQL Server.   
{   
Server srv = default(Server);   
srv = new Server();   
int count = 0;   
int total = 0;   
//Iterate through the databases and call the GetActiveDBConnectionCount method.   
Database db = default(Database);   
foreach ( db in srv.Databases) {   
  count = srv.GetActiveDBConnectionCount(db.Name);   
  total = total + count;   
  //Display the number of connections for each database.   
  Console.WriteLine(count + " connections on " + db.Name);   
}   
//Display the total number of connections on the instance of SQL Server.   
Console.WriteLine("Total connections =" + total);   
}   
```  
  
  
