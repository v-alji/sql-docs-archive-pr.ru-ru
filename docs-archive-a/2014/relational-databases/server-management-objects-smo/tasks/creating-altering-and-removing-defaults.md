---
title: Создание, изменение и удаление значений по умолчанию | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- defaults [SMO]
ms.assetid: c30ac3b9-8150-4264-ba4c-c549f44261ab
author: stevestein
ms.author: sstein
ms.openlocfilehash: 747f7ff60122c5265cd68060063946a3e22d0301
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739644"
---
# <a name="creating-altering-and-removing-defaults"></a><span data-ttu-id="7e2c8-102">Создание, изменение и удаление используемых по умолчанию значений</span><span class="sxs-lookup"><span data-stu-id="7e2c8-102">Creating, Altering, and Removing Defaults</span></span>
  <span data-ttu-id="7e2c8-103">В управляющих объектах [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (SMO) значение по умолчанию представлено объектом <xref:Microsoft.SqlServer.Management.Smo.Default>.</span><span class="sxs-lookup"><span data-stu-id="7e2c8-103">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO), the default constraint is represented by the <xref:Microsoft.SqlServer.Management.Smo.Default> object.</span></span>  
  
 <span data-ttu-id="7e2c8-104">Свойство <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A> объекта <xref:Microsoft.SqlServer.Management.Smo.Default> используется, чтобы установить вставляемое значение.</span><span class="sxs-lookup"><span data-stu-id="7e2c8-104">The <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Default> object is used to set the value to be inserted.</span></span> <span data-ttu-id="7e2c8-105">Это может быть константа или инструкция [!INCLUDE[tsql](../../../includes/tsql-md.md)] , возвращающая значение константы, такая как GETDATE().</span><span class="sxs-lookup"><span data-stu-id="7e2c8-105">This can be a constant or a [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement that returns a constant value, such as GETDATE().</span></span> <span data-ttu-id="7e2c8-106">Свойство <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A> не может быть изменено методом <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A>.</span><span class="sxs-lookup"><span data-stu-id="7e2c8-106">The <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A> property cannot be modified by using the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> method.</span></span> <span data-ttu-id="7e2c8-107">Вместо этого объект <xref:Microsoft.SqlServer.Management.Smo.Default> необходимо удалить и создать заново.</span><span class="sxs-lookup"><span data-stu-id="7e2c8-107">Instead, the <xref:Microsoft.SqlServer.Management.Smo.Default> object must be dropped and re-created.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e2c8-108">Пример</span><span class="sxs-lookup"><span data-stu-id="7e2c8-108">Example</span></span>  
 <span data-ttu-id="7e2c8-109">Чтобы использовать какой-либо из представленных примеров кода, нужно выбрать среду, шаблон и язык программирования, с помощью которых будет создаваться приложение.</span><span class="sxs-lookup"><span data-stu-id="7e2c8-109">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="7e2c8-110">Дополнительные сведения см. в статьях [Создание проекта Visual Basic SMO в Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) или [Создание проекта Visual C&#35; SMO в Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="7e2c8-110">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-altering-and-removing-a-default-in-visual-basic"></a><span data-ttu-id="7e2c8-111">Создание, изменение и удаление значения по умолчанию на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7e2c8-111">Creating, Altering, and Removing a Default in Visual Basic</span></span>  
 <span data-ttu-id="7e2c8-112">Этот пример кода показывает, как создать одно значение по умолчанию, являющееся простым текстом, и другое значение по умолчанию, представляющее собой инструкцию [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7e2c8-112">This code example shows how to create one default that is simple text, and another default that is a [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="7e2c8-113">Значение по умолчанию необходимо присоединять к столбцу с помощью метода <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.BindToColumn%2A> и отсоединять с помощью метода <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.UnbindFromColumn%2A>.</span><span class="sxs-lookup"><span data-stu-id="7e2c8-113">The default must be attached to the column by using the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.BindToColumn%2A> method and detached by using the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.UnbindFromColumn%2A> method.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBDefaults1](SMO How to#SMO_VBDefaults1)]  -->  
  
## <a name="creating-altering-and-removing-a-default-in-visual-c"></a><span data-ttu-id="7e2c8-114">Создание, изменение и удаление значения по умолчанию на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="7e2c8-114">Creating, Altering, and Removing a Default in Visual C#</span></span>  
 <span data-ttu-id="7e2c8-115">Этот пример кода показывает, как создать одно значение по умолчанию, являющееся простым текстом, и другое значение по умолчанию, представляющее собой инструкцию [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7e2c8-115">This code example shows how to create one default that is simple text, and another default that is a [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="7e2c8-116">Значение по умолчанию необходимо присоединять к столбцу с помощью метода <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.BindToColumn%2A> и отсоединять с помощью метода <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.UnbindFromColumn%2A>.</span><span class="sxs-lookup"><span data-stu-id="7e2c8-116">The default must be attached to the column by using the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.BindToColumn%2A> method and detached by using the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.UnbindFromColumn%2A> method.</span></span>  
  
```csharp
{
          Server srv = new Server();  
  
            //Reference the AdventureWorks2012 database.   
            Database  db = srv.Databases["AdventureWorks2012"];  
  
            //Define a Default object variable by supplying the parent database and the default name   
            //in the constructor.   
            Default def = new Default(db, "Test_Default2");  
  
            //Set the TextHeader and TextBody properties that define the default.   
            def.TextHeader = "CREATE DEFAULT [Test_Default2] AS";  
            def.TextBody = "GetDate()";  
  
            //Create the default on the instance of SQL Server.   
            def.Create();  
  
            //Bind the default to a column in a table in AdventureWorks2012  
            def.BindToColumn("SpecialOffer", "StartDate", "Sales");  
  
            //Unbind the default from the column and remove it from the database.   
            def.UnbindFromColumn("SpecialOffer", "StartDate", "Sales");  
            def.Drop();  
        }  
```  
  
## <a name="creating-altering-and-removing-a-default-in-powershell"></a><span data-ttu-id="7e2c8-117">Создание, изменение и удаление значения по умолчанию в PowerShell</span><span class="sxs-lookup"><span data-stu-id="7e2c8-117">Creating, Altering, and Removing a Default in PowerShell</span></span>  
 <span data-ttu-id="7e2c8-118">Этот пример кода показывает, как создать одно значение по умолчанию, являющееся простым текстом, и другое значение по умолчанию, представляющее собой инструкцию [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7e2c8-118">This code example shows how to create one default that is simple text, and another default that is a [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="7e2c8-119">Значение по умолчанию необходимо присоединять к столбцу с помощью метода <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.BindToColumn%2A> и отсоединять с помощью метода <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.UnbindFromColumn%2A>.</span><span class="sxs-lookup"><span data-stu-id="7e2c8-119">The default must be attached to the column by using the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.BindToColumn%2A> method and detached by using the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.UnbindFromColumn%2A> method.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server and get a reference to AdventureWorks2012  
CD \sql\localhost\default\databases  
$db = Get-Item Adventureworks2012  
  
#Define a Default object variable by supplying the parent database and the default name in the constructor.  
$def = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Default `  
-argumentlist $db, "Test_Default2"  
  
#Set the TextHeader and TextBody properties that define the default.   
$def.TextHeader = "CREATE DEFAULT [Test_Default2] AS"  
$def.TextBody = "GetDate()"  
  
#Create the default on the instance of SQL Server.   
$def.Create()  
  
#Bind the default to the column.   
$def.BindToColumn("SpecialOffer", "StartDate", "Sales")  
  
#Unbind the default from the column and remove it from the database.   
$def.UnbindFromColumn("SpecialOffer", "StartDate", "Sales")  
$def.Drop()  
```  
  
## <a name="see-also"></a><span data-ttu-id="7e2c8-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="7e2c8-120">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.Default>  
