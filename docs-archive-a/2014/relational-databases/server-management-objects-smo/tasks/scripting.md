---
title: Написание скриптов | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- dependencies [SMO]
- scripts [SMO]
ms.assetid: 13a35511-3987-426b-a3b7-3b2e83900dc7
author: stevestein
ms.author: sstein
ms.openlocfilehash: bf46798597de021976cefa943a17500e773f9274
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732493"
---
# <a name="scripting"></a><span data-ttu-id="a53af-102">Скрипты</span><span class="sxs-lookup"><span data-stu-id="a53af-102">Scripting</span></span>
  <span data-ttu-id="a53af-103">Создание скрипта в SMO управляется объектом <xref:Microsoft.SqlServer.Management.Smo.Scripter> и его дочерними объектами или методом `Script` на отдельных объектах.</span><span class="sxs-lookup"><span data-stu-id="a53af-103">Scripting in SMO is controlled by the <xref:Microsoft.SqlServer.Management.Smo.Scripter> object and its child objects, or the `Script` method on individual objects.</span></span> <span data-ttu-id="a53af-104"><xref:Microsoft.SqlServer.Management.Smo.Scripter>Объект управляет сопоставлением из отношений зависимости для объектов в экземпляре [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a53af-104">The <xref:Microsoft.SqlServer.Management.Smo.Scripter> object controls the mapping out of dependency relationships for objects on an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="a53af-105">Расширенное создание сценария с помощью объекта <xref:Microsoft.SqlServer.Management.Smo.Scripter> и его дочерних объектов является процессом из трех фаз.</span><span class="sxs-lookup"><span data-stu-id="a53af-105">Advanced scripting by using the <xref:Microsoft.SqlServer.Management.Smo.Scripter> object and its child objects is a three phase process:</span></span>  
  
1.  <span data-ttu-id="a53af-106">Обнаружение</span><span class="sxs-lookup"><span data-stu-id="a53af-106">Discovery</span></span>  
  
2.  <span data-ttu-id="a53af-107">Создание списка</span><span class="sxs-lookup"><span data-stu-id="a53af-107">List generation</span></span>  
  
3.  <span data-ttu-id="a53af-108">Создание скрипта</span><span class="sxs-lookup"><span data-stu-id="a53af-108">Script generation</span></span>  
  
 <span data-ttu-id="a53af-109">Фаза обнаружения использует объект <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker>.</span><span class="sxs-lookup"><span data-stu-id="a53af-109">The discovery phase uses the <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker> object.</span></span> <span data-ttu-id="a53af-110">Учитывая URN-список объектов, метод <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker.DiscoverDependencies%2A> объекта <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker> возвращает объект <xref:Microsoft.SqlServer.Management.Smo.DependencyTree> объектам в URN-списке.</span><span class="sxs-lookup"><span data-stu-id="a53af-110">Given an URN list of objects, the <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker.DiscoverDependencies%2A> method of the <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker> object returns a <xref:Microsoft.SqlServer.Management.Smo.DependencyTree> object for the objects in the URN list.</span></span> <span data-ttu-id="a53af-111">Параметр логического *фпарентс* используется для выбора того, должны ли быть обнаружены родители или дочерние элементы указанного объекта.</span><span class="sxs-lookup"><span data-stu-id="a53af-111">The Boolean *fParents* parameter is used to select whether the parents or the children of the specified object are to be discovered.</span></span> <span data-ttu-id="a53af-112">На данном этапе можно изменить дерево зависимостей.</span><span class="sxs-lookup"><span data-stu-id="a53af-112">The dependency tree can be modified at this stage.</span></span>  
  
 <span data-ttu-id="a53af-113">На фазе создания списка передается дерево и возвращается результирующий список.</span><span class="sxs-lookup"><span data-stu-id="a53af-113">In the list generation phase, the tree is passed in and the resulting list is returned.</span></span> <span data-ttu-id="a53af-114">Данный список объекта существует в порядке создания сценария, и им можно управлять.</span><span class="sxs-lookup"><span data-stu-id="a53af-114">This object list is in scripting order and can be manipulated.</span></span>  
  
 <span data-ttu-id="a53af-115">Фазы создания списка используют метод <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker.WalkDependencies%2A> для возвращения объекта <xref:Microsoft.SqlServer.Management.Smo.DependencyTree>.</span><span class="sxs-lookup"><span data-stu-id="a53af-115">The list generation phases use the <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker.WalkDependencies%2A> method to return a <xref:Microsoft.SqlServer.Management.Smo.DependencyTree>.</span></span> <span data-ttu-id="a53af-116">На данной фазе можно изменить объект <xref:Microsoft.SqlServer.Management.Smo.DependencyTree>.</span><span class="sxs-lookup"><span data-stu-id="a53af-116">The <xref:Microsoft.SqlServer.Management.Smo.DependencyTree> can be modified at this stage.</span></span>  
  
 <span data-ttu-id="a53af-117">В третьей и последней фазе сценарий формируется с указанным списком и параметрами создания скриптов.</span><span class="sxs-lookup"><span data-stu-id="a53af-117">In the third and final phase, a script is generated with the specified list and scripting options.</span></span> <span data-ttu-id="a53af-118">Этот результат возвращается в виде системного объекта <xref:System.Collections.Specialized.StringCollection>.</span><span class="sxs-lookup"><span data-stu-id="a53af-118">The result is returned as a <xref:System.Collections.Specialized.StringCollection> system object.</span></span> <span data-ttu-id="a53af-119">На этой фазе имена зависимых объектов извлекаются из коллекции Items объекта <xref:Microsoft.SqlServer.Management.Smo.DependencyTree> и свойств, таких как <xref:Microsoft.SqlServer.Management.Smo.DependencyTree.NumberOfSiblings%2A> и <xref:Microsoft.SqlServer.Management.Smo.DependencyTree.FirstChild%2A>.</span><span class="sxs-lookup"><span data-stu-id="a53af-119">In this phase the dependent object names are then extracted from the Items collection of the <xref:Microsoft.SqlServer.Management.Smo.DependencyTree> object and properties such as <xref:Microsoft.SqlServer.Management.Smo.DependencyTree.NumberOfSiblings%2A> and <xref:Microsoft.SqlServer.Management.Smo.DependencyTree.FirstChild%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a53af-120">Пример</span><span class="sxs-lookup"><span data-stu-id="a53af-120">Example</span></span>  
 <span data-ttu-id="a53af-121">Чтобы использовать какой-либо из представленных примеров кода, нужно выбрать среду, шаблон и язык программирования, с помощью которых будет создаваться приложение.</span><span class="sxs-lookup"><span data-stu-id="a53af-121">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="a53af-122">Дополнительные сведения см. в статьях [Создание проекта Visual Basic SMO в Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) или [Создание проекта Visual C&#35; SMO в Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="a53af-122">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
 <span data-ttu-id="a53af-123">Данный пример кода требует инструкцию `Imports` для пространства имен System.Collections.Specialized.</span><span class="sxs-lookup"><span data-stu-id="a53af-123">This code example requires an `Imports` statement for the System.Collections.Specialized namespace.</span></span> <span data-ttu-id="a53af-124">Вставьте инструкцию с другими инструкциями Imports и перед любыми декларациями в приложении.</span><span class="sxs-lookup"><span data-stu-id="a53af-124">Insert this with the other Imports statements, before any declarations in the application.</span></span>  
  
```vb
Imports Microsoft.SqlServer.Management.Smo  
Imports Microsoft.SqlServer.Management.Common  
Imports System.Collections.Specialized  
```  
  
## <a name="scripting-out-the-dependencies-for-a-database-in-visual-basic"></a><span data-ttu-id="a53af-125">Создание сценария зависимостей для базы данных на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a53af-125">Scripting Out the Dependencies for a Database in Visual Basic</span></span>  
 <span data-ttu-id="a53af-126">Данный пример кода показывает, как обнаруживать зависимости и просматривать список для отображения результатов.</span><span class="sxs-lookup"><span data-stu-id="a53af-126">This code example shows how to discover the dependencies and iterate through the list to display the results.</span></span>  
  
```vb
' compile with:   
' /r:Microsoft.SqlServer.Smo.dll   
' /r:Microsoft.SqlServer.ConnectionInfo.dll   
' /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll   
  
Imports Microsoft.SqlServer.Management.Smo  
Imports Microsoft.SqlServer.Management.Sdk.Sfc  
  
Public Class A  
   Public Shared Sub Main()  
      ' database name  
      Dim dbName As [String] = "AdventureWorksLT2012"   ' database name  
  
      ' Connect to the local, default instance of SQL Server.   
      Dim srv As New Server()  
  
      ' Reference the database.    
      Dim db As Database = srv.Databases(dbName)  
  
      ' Define a Scripter object and set the required scripting options.   
      Dim scrp As New Scripter(srv)  
      scrp.Options.ScriptDrops = False  
      scrp.Options.WithDependencies = True  
      scrp.Options.Indexes = True   ' To include indexes  
      scrp.Options.DriAllConstraints = True   ' to include referential constraints in the script  
  
      ' Iterate through the tables in database and script each one. Display the script.  
      For Each tb As Table In db.Tables  
         ' check if the table is not a system table  
         If tb.IsSystemObject = False Then  
            Console.WriteLine("-- Scripting for table " + tb.Name)  
  
            ' Generating script for table tb  
            Dim sc As System.Collections.Specialized.StringCollection = scrp.Script(New Urn() {tb.Urn})  
            For Each st As String In sc  
               Console.WriteLine(st)  
            Next  
            Console.WriteLine("--")  
         End If  
      Next  
   End Sub  
End Class  
```  
  
## <a name="scripting-out-the-dependencies-for-a-database-in-visual-c"></a><span data-ttu-id="a53af-127">Создание сценария зависимостей для базы данных на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="a53af-127">Scripting Out the Dependencies for a Database in Visual C#</span></span>  
 <span data-ttu-id="a53af-128">Данный пример кода показывает, как обнаруживать зависимости и просматривать список для отображения результатов.</span><span class="sxs-lookup"><span data-stu-id="a53af-128">This code example shows how to discover the dependencies and iterate through the list to display the results.</span></span>  
  
```csharp
// compile with:   
// /r:Microsoft.SqlServer.Smo.dll   
// /r:Microsoft.SqlServer.ConnectionInfo.dll   
// /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll   
  
using System;  
using Microsoft.SqlServer.Management.Smo;  
using Microsoft.SqlServer.Management.Sdk.Sfc;  
  
public class A {  
   public static void Main() {   
      String dbName = "AdventureWorksLT2012"; // database name  
  
      // Connect to the local, default instance of SQL Server.   
      Server srv = new Server();  
  
      // Reference the database.    
      Database db = srv.Databases[dbName];  
  
      // Define a Scripter object and set the required scripting options.   
      Scripter scrp = new Scripter(srv);  
      scrp.Options.ScriptDrops = false;  
      scrp.Options.WithDependencies = true;  
      scrp.Options.Indexes = true;   // To include indexes  
      scrp.Options.DriAllConstraints = true;   // to include referential constraints in the script  
  
      // Iterate through the tables in database and script each one. Display the script.     
      foreach (Table tb in db.Tables) {   
         // check if the table is not a system table  
         if (tb.IsSystemObject == false) {  
            Console.WriteLine("-- Scripting for table " + tb.Name);  
  
            // Generating script for table tb  
            System.Collections.Specialized.StringCollection sc = scrp.Script(new Urn[]{tb.Urn});  
            foreach (string st in sc) {  
               Console.WriteLine(st);  
            }  
            Console.WriteLine("--");  
         }  
      }   
   }  
}  
```  
  
## <a name="scripting-out-the-dependencies-for-a-database-in-powershell"></a><span data-ttu-id="a53af-129">Создание сценария зависимостей для базы данных в PowerShell</span><span class="sxs-lookup"><span data-stu-id="a53af-129">Scripting Out the Dependencies for a Database in PowerShell</span></span>  
 <span data-ttu-id="a53af-130">Данный пример кода показывает, как обнаруживать зависимости и просматривать список для отображения результатов.</span><span class="sxs-lookup"><span data-stu-id="a53af-130">This code example shows how to discover the dependencies and iterate through the list to display the results.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\default  
  
# Create a Scripter object and set the required scripting options.  
$scrp = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Scripter -ArgumentList (Get-Item .)  
$scrp.Options.ScriptDrops = $false  
$scrp.Options.WithDependencies = $true  
$scrp.Options.IncludeIfNotExists = $true  
  
# Set the path context to the tables in AdventureWorks2012.  
CD Databases\AdventureWorks2012\Tables  
  
foreach ($Item in Get-ChildItem)  
 {    
 $scrp.Script($Item)  
 }  
```  
