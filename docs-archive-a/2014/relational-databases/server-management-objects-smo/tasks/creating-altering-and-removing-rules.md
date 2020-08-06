---
title: Создание, изменение и удаление правил | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- rules [SMO]
ms.assetid: 16981459-524e-4b39-a899-4370eaf763cc
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7742a9cb718bdde4f268d5226c45eba475f44ddd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666475"
---
# <a name="creating-altering-and-removing-rules"></a><span data-ttu-id="7f032-102">Создание, изменение и удаление правил</span><span class="sxs-lookup"><span data-stu-id="7f032-102">Creating, Altering, and Removing Rules</span></span>
  <span data-ttu-id="7f032-103">В SMO правила представлены объектом <xref:Microsoft.SqlServer.Management.Smo.Rule>.</span><span class="sxs-lookup"><span data-stu-id="7f032-103">In SMO, rules are represented by the <xref:Microsoft.SqlServer.Management.Smo.Rule> object.</span></span> <span data-ttu-id="7f032-104">Правило определяется свойством <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A>, которое является текстовой строкой, содержащей выражение условия, использующее операторы или предикаты, например IN, LIKE или BETWEEN.</span><span class="sxs-lookup"><span data-stu-id="7f032-104">The rule is defined by the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A> property, which is a text string that contains a condition expression that uses operators or predicates, such as IN, LIKE, or BETWEEN.</span></span> <span data-ttu-id="7f032-105">Правило не может ссылаться на столбцы или другие объекты базы данных.</span><span class="sxs-lookup"><span data-stu-id="7f032-105">A rule cannot reference columns or other database objects.</span></span> <span data-ttu-id="7f032-106">В правило могут входить встроенные функции, не ссылающиеся на объекты базы данных.</span><span class="sxs-lookup"><span data-stu-id="7f032-106">Built-in functions that do not reference database objects can be included.</span></span>  
  
 <span data-ttu-id="7f032-107">Определение в свойстве <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A> должно содержать переменную, ссылающуюся на введенное значение данных.</span><span class="sxs-lookup"><span data-stu-id="7f032-107">The definition in the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A> property must contain a variable that refers to the data value entered.</span></span> <span data-ttu-id="7f032-108">Любое имя или символ можно использовать для представления значения при создании правила, но первым символом должен быть \@ символ.</span><span class="sxs-lookup"><span data-stu-id="7f032-108">Any name or symbol can be used to represent the value when creating the rule, but the first character must be the \@ symbol.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f032-109">Пример</span><span class="sxs-lookup"><span data-stu-id="7f032-109">Example</span></span>  
 <span data-ttu-id="7f032-110">Чтобы использовать какой-либо из представленных примеров кода, нужно выбрать среду, шаблон и язык программирования, с помощью которых будет создаваться приложение.</span><span class="sxs-lookup"><span data-stu-id="7f032-110">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="7f032-111">Дополнительные сведения см. в статьях [Создание проекта Visual Basic SMO в Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) или [Создание проекта Visual C&#35; SMO в Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="7f032-111">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-altering-and-removing-a-rule-in-visual-basic"></a><span data-ttu-id="7f032-112">Создание, изменение и удаление правила на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7f032-112">Creating, Altering, and Removing a Rule in Visual Basic</span></span>  
 <span data-ttu-id="7f032-113">Данный образец кода показывает, как создать правило, добавить его в столбец, изменить свойства объекта <xref:Microsoft.SqlServer.Management.Smo.Rule>, отсоединить его от столбца и удалить его.</span><span class="sxs-lookup"><span data-stu-id="7f032-113">This code sample shows how to create a rule, attach it to a column, modify properties of the <xref:Microsoft.SqlServer.Management.Smo.Rule> object, detach it from the column, and then drop it.</span></span>  
  
 <span data-ttu-id="7f032-114">Инструкция `Dim` для объекта <xref:Microsoft.SqlServer.Management.Smo.Rule> указывается с полным путем к сборке, чтобы избежать неоднозначности с объектом <xref:Microsoft.SqlServer.Management.Smo.Rule> в сборке System.Data.</span><span class="sxs-lookup"><span data-stu-id="7f032-114">The `Dim` statement for the <xref:Microsoft.SqlServer.Management.Smo.Rule> object is specified with the full assembly path to avoid ambiguity with a <xref:Microsoft.SqlServer.Management.Smo.Rule> object in the System.Data assembly.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBRules1](SMO How to#SMO_VBRules1)]  -->  
  
## <a name="creating-altering-and-removing-a-rule-in-visual-c"></a><span data-ttu-id="7f032-115">Создание, изменение и удаление правила на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="7f032-115">Creating, Altering, and Removing a Rule in Visual C#</span></span>  
 <span data-ttu-id="7f032-116">Данный образец кода показывает, как создать правило, добавить его в столбец, изменить свойства объекта <xref:Microsoft.SqlServer.Management.Smo.Rule>, отсоединить его от столбца и удалить его.</span><span class="sxs-lookup"><span data-stu-id="7f032-116">This code sample shows how to create a rule, attach it to a column, modify properties of the <xref:Microsoft.SqlServer.Management.Smo.Rule> object, detach it from the column, and then drop it.</span></span>  
  
 <span data-ttu-id="7f032-117">Инструкция `Dim` для объекта <xref:Microsoft.SqlServer.Management.Smo.Rule> указывается с полным путем к сборке, чтобы избежать неоднозначности с объектом <xref:Microsoft.SqlServer.Management.Smo.Rule> в сборке System.Data.</span><span class="sxs-lookup"><span data-stu-id="7f032-117">The `Dim` statement for the <xref:Microsoft.SqlServer.Management.Smo.Rule> object is specified with the full assembly path to avoid ambiguity with a <xref:Microsoft.SqlServer.Management.Smo.Rule> object in the System.Data assembly.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
            Server srv;  
            srv = new Server();  
            //Reference the AdventureWorks2012 database.   
            Database db;  
            db = srv.Databases["AdventureWorks2012"];  
  
            //Define a Rule object variable by supplying the parent database, name and schema in the constructor.   
            //Note that the full namespace must be given for the Rule type to differentiate it from other Rule types.   
            Microsoft.SqlServer.Management.Smo.Rule ru;  
            ru = new Rule(db, "TestRule", "Production");  
            //Set the TextHeader and TextBody properties to define the rule.   
            ru.TextHeader = "CREATE RULE [Production].[TestRule] AS";  
            ru.TextBody = "@value BETWEEN GETDATE() AND DATEADD(year,4,GETDATE())";  
            //Create the rule on the instance of SQL Server.   
            ru.Create();  
            //Bind the rule to a column in the Product table by supplying the table, schema, and   
            //column as arguments in the BindToColumn method.   
            ru.BindToColumn("Product", "SellEndDate", "Production");  
            //Unbind from the column before removing the rule from the database.   
            ru.UnbindFromColumn("Product", "SellEndDate", "Production");  
            ru.Drop();  
  
        }  
```  
  
## <a name="creating-altering-and-removing-a-rule-in-powershell"></a><span data-ttu-id="7f032-118">Создание, изменение и удаление правила в PowerShell</span><span class="sxs-lookup"><span data-stu-id="7f032-118">Creating, Altering, and Removing a Rule in PowerShell</span></span>  
 <span data-ttu-id="7f032-119">Данный образец кода показывает, как создать правило, добавить его в столбец, изменить свойства объекта <xref:Microsoft.SqlServer.Management.Smo.Rule>, отсоединить его от столбца и удалить его.</span><span class="sxs-lookup"><span data-stu-id="7f032-119">This code sample shows how to create a rule, attach it to a column, modify properties of the <xref:Microsoft.SqlServer.Management.Smo.Rule> object, detach it from the column, and then drop it.</span></span>  
  
 <span data-ttu-id="7f032-120">Инструкция `Dim` для объекта <xref:Microsoft.SqlServer.Management.Smo.Rule> указывается с полным путем к сборке, чтобы избежать неоднозначности с объектом <xref:Microsoft.SqlServer.Management.Smo.Rule> в сборке System.Data.</span><span class="sxs-lookup"><span data-stu-id="7f032-120">The `Dim` statement for the <xref:Microsoft.SqlServer.Management.Smo.Rule> object is specified with the full assembly path to avoid ambiguity with a <xref:Microsoft.SqlServer.Management.Smo.Rule> object in the System.Data assembly.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server and get a reference to AdventureWorks2012  
CD \sql\localhost\default\databases  
$db = Get-Item Adventureworks2012  
  
# Define a Rule object variable by supplying the parent database, name and schema in the constructor.
$ru = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Rule -argumentlist $db, "TestRule", "Production"  
  
#Set the TextHeader and TextBody properties to define the rule.
$ru.TextHeader = "CREATE RULE [Production].[TestRule] AS"  
$ru.TextBody = "@value BETWEEN GETDATE() AND DATEADD(year,4,GETDATE())"  
  
#Create the rule on the instance of SQL Server.
$ru.Create()  
  
# Bind the rule to a column in the Product table by supplying the table, schema, and column as arguments in the BindToColumn method.
$ru.BindToColumn("Product", "SellEndDate", "Production")  
  
#Unbind from the column before removing the rule from the database.
$ru.UnbindFromColumn("Product", "SellEndDate", "Production")  
$ru.Drop()  
```  
  
## <a name="see-also"></a><span data-ttu-id="7f032-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="7f032-121">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.Rule>  
