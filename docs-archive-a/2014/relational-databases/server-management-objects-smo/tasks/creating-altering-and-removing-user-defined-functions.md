---
title: Создание, изменение и удаление определяемых пользователем функций | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- user-defined functions [SMO]
ms.assetid: 0ebebd3b-0775-41c2-989d-aa4cf81af12a
author: stevestein
ms.author: sstein
ms.openlocfilehash: b9ff6d1b6e675d41e96f26fc24e6e0dd4ba69454
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668198"
---
# <a name="creating-altering-and-removing-user-defined-functions"></a><span data-ttu-id="395c7-102">Создание, изменение и удаление определяемых пользователем функций</span><span class="sxs-lookup"><span data-stu-id="395c7-102">Creating, Altering, and Removing User-Defined Functions</span></span>
  <span data-ttu-id="395c7-103"><xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction>Объект предоставляет функциональные возможности, позволяющие пользователям программно управлять определяемыми пользователем функциями в [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="395c7-103">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction> object provides functionality that lets users programmatically manage user-defined functions in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="395c7-104">Определяемые пользователем функции поддерживают входные и выходные параметры, а также прямые ссылки на столбцы таблицы.</span><span class="sxs-lookup"><span data-stu-id="395c7-104">User-defined functions support input and output parameters, and also support direct references to table columns.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="395c7-105">требует, чтобы сборки были зарегистрированы внутри базы данных до того, как их можно будет использовать внутри хранимых процедур, определяемых пользователем функций и типов данных.</span><span class="sxs-lookup"><span data-stu-id="395c7-105">requires assemblies to be registered within a database before these can be used inside stored procedures, user defined functions, triggers, and user defined data types.</span></span> <span data-ttu-id="395c7-106">SMO поддерживает эту функцию при помощи объекта <xref:Microsoft.SqlServer.Management.Smo.SqlAssembly>.</span><span class="sxs-lookup"><span data-stu-id="395c7-106">SMO supports this feature with the <xref:Microsoft.SqlServer.Management.Smo.SqlAssembly> object.</span></span>  
  
 <span data-ttu-id="395c7-107">Объект <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction> указывает на сборку .NET со свойствами <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.AssemblyName%2A>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.ClassName%2A> и <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.MethodName%2A>.</span><span class="sxs-lookup"><span data-stu-id="395c7-107">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction> object references the .NET assembly with the <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.AssemblyName%2A>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.ClassName%2A>, and <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.MethodName%2A> properties.</span></span>  
  
 <span data-ttu-id="395c7-108">Когда объект <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction> указывает на сборку .NET, необходимо ее зарегистрировать путем создания объекта <xref:Microsoft.SqlServer.Management.Smo.SqlAssembly> и его добавления в объект <xref:Microsoft.SqlServer.Management.Smo.SqlAssemblyCollection>, принадлежащий объекту <xref:Microsoft.SqlServer.Management.Smo.Database>.</span><span class="sxs-lookup"><span data-stu-id="395c7-108">When the <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction> object references a .NET assembly, you must register the assembly by creating a <xref:Microsoft.SqlServer.Management.Smo.SqlAssembly> object and adding it to the <xref:Microsoft.SqlServer.Management.Smo.SqlAssemblyCollection> object, which belongs to the <xref:Microsoft.SqlServer.Management.Smo.Database> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="395c7-109">Пример</span><span class="sxs-lookup"><span data-stu-id="395c7-109">Example</span></span>  
 <span data-ttu-id="395c7-110">Чтобы использовать какой-либо из представленных примеров кода, нужно выбрать среду, шаблон и язык программирования, с помощью которых будет создаваться приложение.</span><span class="sxs-lookup"><span data-stu-id="395c7-110">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="395c7-111">Дополнительные сведения см. в статьях [Создание проекта Visual Basic SMO в Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) или [Создание проекта Visual C&#35; SMO в Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="395c7-111">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-a-scalar-user-defined-function-in-visual-basic"></a><span data-ttu-id="395c7-112">Создание определяемой пользователем скалярной функции на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="395c7-112">Creating a Scalar User-Defined Function in Visual Basic</span></span>  
 <span data-ttu-id="395c7-113">Данный пример кода показывает, как на языке [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] создать и удалить определяемую пользователем скалярную функцию, имеющую входной параметр объекта <xref:System.DateTime> и возвращаемый тип integer.</span><span class="sxs-lookup"><span data-stu-id="395c7-113">This code example shows how to create and remove a scalar user-defined function that has an input <xref:System.DateTime> object parameter and an integer return type in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)].</span></span> <span data-ttu-id="395c7-114">Функция, определяемая пользователем, создается в базе данных [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="395c7-114">The user-defined function is created on the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="395c7-115">Пример создает определяемую пользователем функцию ISOweek, которая получает в качестве аргумента дату и вычисляет номер недели по ISO.</span><span class="sxs-lookup"><span data-stu-id="395c7-115">The example creates a user-defined function, ISOweek, which takes a date argument and calculates the ISO week number.</span></span> <span data-ttu-id="395c7-116">Для правильной работы этой функции перед ее вызовом параметр базы данных DATEFIRST должен быть установлен в значение 1.</span><span class="sxs-lookup"><span data-stu-id="395c7-116">For this function to calculate correctly, the database DATEFIRST option must be set to 1 before the function is called.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBUserDefFuncs1](SMO How to#SMO_VBUserDefFuncs1)]  -->  
  
## <a name="creating-a-scalar-user-defined-function-in-visual-c"></a><span data-ttu-id="395c7-117">Создание определяемой пользователем скалярной функции на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="395c7-117">Creating a Scalar User-Defined Function in Visual C#</span></span>  
 <span data-ttu-id="395c7-118">Данный пример кода показывает, как на языке [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] создать и удалить определяемую пользователем скалярную функцию, имеющую входной параметр объекта <xref:System.DateTime> и возвращаемый тип integer.</span><span class="sxs-lookup"><span data-stu-id="395c7-118">This code example shows how to create and remove a scalar user-defined function that has an input <xref:System.DateTime> object parameter and an integer return type in [!INCLUDE[csprcs](../../../includes/csprcs-md.md)].</span></span> <span data-ttu-id="395c7-119">Функция, определяемая пользователем, создается в базе данных [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="395c7-119">The user-defined function is created on the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="395c7-120">В примере показано создание определяемой пользователем функции</span><span class="sxs-lookup"><span data-stu-id="395c7-120">The example creates the user-defined function.</span></span> <span data-ttu-id="395c7-121">`ISOweek`.</span><span class="sxs-lookup"><span data-stu-id="395c7-121">`ISOweek`.</span></span> <span data-ttu-id="395c7-122">которая получает в качестве аргумента дату и вычисляет номер недели по ISO.</span><span class="sxs-lookup"><span data-stu-id="395c7-122">This function takes a date argument and calculates the ISO week number.</span></span> <span data-ttu-id="395c7-123">Для правильной работы этой функции перед ее вызовом параметр базы данных `DATEFIRST` должен быть установлен в значение `1` .</span><span class="sxs-lookup"><span data-stu-id="395c7-123">For this function to calculate correctly, the database `DATEFIRST` option must be set to `1` before the function is called.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
           Server srv = new Server();  
            //Reference the AdventureWorks2012 database.   
           Database db = srv.Databases["AdventureWorks2012"];  
  
            //Define a UserDefinedFunction object variable by supplying the parent database and the name arguments in the constructor.   
            UserDefinedFunction udf = new UserDefinedFunction(db, "IsOWeek");  
  
            //Set the TextMode property to false and then set the other properties.   
            udf.TextMode = false;  
            udf.DataType = DataType.Int;  
            udf.ExecutionContext = ExecutionContext.Caller;  
            udf.FunctionType = UserDefinedFunctionType.Scalar;  
            udf.ImplementationType = ImplementationType.TransactSql;  
  
            //Add a parameter.   
  
     UserDefinedFunctionParameter par = new UserDefinedFunctionParameter(udf, "@DATE", DataType.DateTime);  
            udf.Parameters.Add(par);  
  
            //Set the TextBody property to define the user-defined function.   
            udf.TextBody = "BEGIN DECLARE @ISOweek int SET @ISOweek= DATEPART(wk,@DATE)+1 -DATEPART(wk,CAST(DATEPART(yy,@DATE) as CHAR(4))+'0104') IF (@ISOweek=0) SET @ISOweek=dbo.ISOweek(CAST(DATEPART(yy,@DATE)-1 AS CHAR(4))+'12'+ CAST(24+DATEPART(DAY,@DATE) AS CHAR(2)))+1 IF ((DATEPART(mm,@DATE)=12) AND ((DATEPART(dd,@DATE)-DATEPART(dw,@DATE))>= 28)) SET @ISOweek=1 RETURN(@ISOweek) END;";  
  
            //Create the user-defined function on the instance of SQL Server.   
            udf.Create();  
  
            //Remove the user-defined function.   
            udf.Drop();  
        }  
```  
  
## <a name="creating-a-scalar-user-defined-function-in-powershell"></a><span data-ttu-id="395c7-124">Создание определяемой пользователем скалярной функции в PowerShell</span><span class="sxs-lookup"><span data-stu-id="395c7-124">Creating a Scalar User-Defined Function in PowerShell</span></span>  
 <span data-ttu-id="395c7-125">Данный пример кода показывает, как на языке [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] создать и удалить определяемую пользователем скалярную функцию, имеющую входной параметр объекта <xref:System.DateTime> и возвращаемый тип integer.</span><span class="sxs-lookup"><span data-stu-id="395c7-125">This code example shows how to create and remove a scalar user-defined function that has an input <xref:System.DateTime> object parameter and an integer return type in [!INCLUDE[csprcs](../../../includes/csprcs-md.md)].</span></span> <span data-ttu-id="395c7-126">Функция, определяемая пользователем, создается в базе данных [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="395c7-126">The user-defined function is created on the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="395c7-127">В примере показано создание определяемой пользователем функции</span><span class="sxs-lookup"><span data-stu-id="395c7-127">The example creates the user-defined function.</span></span> <span data-ttu-id="395c7-128">`ISOweek`.</span><span class="sxs-lookup"><span data-stu-id="395c7-128">`ISOweek`.</span></span> <span data-ttu-id="395c7-129">которая получает в качестве аргумента дату и вычисляет номер недели по ISO.</span><span class="sxs-lookup"><span data-stu-id="395c7-129">This function takes a date argument and calculates the ISO week number.</span></span> <span data-ttu-id="395c7-130">Для правильной работы этой функции перед ее вызовом параметр базы данных `DATEFIRST` должен быть установлен в значение `1` .</span><span class="sxs-lookup"><span data-stu-id="395c7-130">For this function to calculate correctly, the database `DATEFIRST` option must be set to `1` before the function is called.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server and get a reference to AdventureWorks2012  
CD \sql\localhost\default\databases  
$db = Get-Item Adventureworks2012  
  
# Define a user defined function object variable by supplying the parent database and name arguments in the constructor.
$udf  = New-Object -TypeName Microsoft.SqlServer.Management.SMO.UserDefinedFunction -argumentlist $db, "IsOWeek"  
  
# Set the TextMode property to false and then set the other properties.
$udf.TextMode = $false  
$udf.DataType = [Microsoft.SqlServer.Management.SMO.DataType]::Int
$udf.ExecutionContext = [Microsoft.SqlServer.Management.SMO.ExecutionContext]::Caller  
$udf.FunctionType = [Microsoft.SqlServer.Management.SMO.UserDefinedFunctionType]::Scalar  
$udf.ImplementationType = [Microsoft.SqlServer.Management.SMO.ImplementationType]::TransactSql  
  
# Define a Parameter object variable by supplying the parent function, name and type arguments in the constructor.  
$type = [Microsoft.SqlServer.Management.SMO.DataType]::DateTime  
$par  = New-Object -TypeName Microsoft.SqlServer.Management.SMO.UserDefinedFunctionParameter -argumentlist $udf, "@DATE",$type  
  
# Add the parameter to the function  
$udf.Parameters.Add($par)  
  
#Set the TextBody property to define the user-defined function.
$udf.TextBody = "BEGIN DECLARE @ISOweek int SET @ISOweek= DATEPART(wk,@DATE)+1 -DATEPART(wk,CAST(DATEPART(yy,@DATE) as CHAR(4))+'0104') IF (@ISOweek=0) SET @ISOweek=dbo.ISOweek(CAST(DATEPART(yy,@DATE)-1 AS CHAR(4))+'12'+ CAST(24+DATEPART(DAY,@DATE) AS CHAR(2)))+1 IF ((DATEPART(mm,@DATE)=12) AND ((DATEPART(dd,@DATE)-DATEPART(dw,@DATE))>= 28)) SET @ISOweek=1 RETURN(@ISOweek) END;"  
  
# Create the user-defined function on the instance of SQL Server.
$udf.Create()  
  
# Remove the user-defined function.
$udf.Drop()  
```  
  
## <a name="see-also"></a><span data-ttu-id="395c7-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="395c7-131">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction>  
