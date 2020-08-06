---
title: начало работы с интеграцией со средой CLR | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
- VB
- CSharp
helpviewer_keywords:
- database objects [CLR integration]
- namespaces [CLR integration]
- database objects [CLR integration], about CLR integration
- stored procedures [CLR integration]
- common language runtime [SQL Server], about CLR integration
- building database objects [CLR integration], about CLR integration
- common language runtime [SQL Server], stored procedures
- common language runtime [SQL Server], namespaces
- Hello World example [CLR integration]
- library [CLR integration]
ms.assetid: c73e628a-f54a-411a-bfe3-6dae519316cc
author: rothja
ms.author: jroth
ms.openlocfilehash: 43c97e411a4d74aa48b88f2edbbe420ae17f3534
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654342"
---
# <a name="getting-started-with-clr-integration"></a><span data-ttu-id="8e0d0-102">Приступая к работе с интеграцией со средой CLR</span><span class="sxs-lookup"><span data-stu-id="8e0d0-102">Getting Started with CLR Integration</span></span>
  <span data-ttu-id="8e0d0-103">В этом разделе приводятся общие сведения о пространствах имен и библиотеках, необходимых для компиляции объектов базы данных с помощью [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] интеграции с .NET Framework среды CLR.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-103">This topic provides an overview of the namespaces and libraries required to compile database objects using the [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] integration with the .NET Framework common language runtime (CLR).</span></span> <span data-ttu-id="8e0d0-104">В этом разделе также показано, как написать, скомпилировать и выполнить простую хранимую процедуру CLR на языке [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-104">The topic also shows you how to write, compile, and run a simple CLR stored procedure written in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span></span>  
  
## <a name="required-namespaces"></a><span data-ttu-id="8e0d0-105">Необходимые пространства имен</span><span class="sxs-lookup"><span data-stu-id="8e0d0-105">Required Namespaces</span></span>  
 <span data-ttu-id="8e0d0-106">Начиная с [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8e0d0-106">Beginning with [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8e0d0-107">Функции интеграции со средой CLR доступны через сборку под названием system.data.dll, которая является частью платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-107">CLR integration functionality is exposed in an assembly called system.data.dll, which is part of the .NET Framework.</span></span> <span data-ttu-id="8e0d0-108">Эту сборку можно найти в глобальном кэше сборок (GAC), а также в каталоге .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-108">This assembly can be found in the Global Assembly Cache (GAC) as well as in the .NET Framework directory.</span></span> <span data-ttu-id="8e0d0-109">Ссылка на эту сборку обычно добавляется автоматически и при использовании инструментов с интерфейсом командной строки, и при работе в среде [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio, поэтому нет необходимости добавлять ее вручную.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-109">A reference to this assembly is typically added automatically by both command line tools and [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio, so there is no need to add it manually.</span></span>  
  
 <span data-ttu-id="8e0d0-110">Сборка system.data.dll содержит следующие пространства имен, необходимые для компиляции объектов базы данных среды CLR:</span><span class="sxs-lookup"><span data-stu-id="8e0d0-110">The system.data.dll assembly contains the following namespaces, which are required for compiling CLR database objects:</span></span>  
  
 `System.Data`  
  
 `System.Data.Sql`  
  
 `Microsoft.SqlServer.Server`  
  
 `System.Data.SqlTypes`  
  
## <a name="writing-a-simple-hello-world-stored-procedure"></a><span data-ttu-id="8e0d0-111">Создание простой хранимой процедуры «Hello World»</span><span class="sxs-lookup"><span data-stu-id="8e0d0-111">Writing A Simple "Hello World" Stored Procedure</span></span>  
 <span data-ttu-id="8e0d0-112">Скопируйте и вставьте следующий код Visual C# или [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic в текстовом редакторе и сохраните его в файле с именем «helloworld.cs» или «helloworld.vb».</span><span class="sxs-lookup"><span data-stu-id="8e0d0-112">Copy and paste the following Visual C# or [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic code into a text editor, and save it in a file named "helloworld.cs" or "helloworld.vb".</span></span>  
  
```csharp  
using System;  
using System.Data;  
using Microsoft.SqlServer.Server;  
using System.Data.SqlTypes;  
  
public class HelloWorldProc  
{  
    [Microsoft.SqlServer.Server.SqlProcedure]  
    public static void HelloWorld(out string text)  
    {  
        SqlContext.Pipe.Send("Hello world!" + Environment.NewLine);  
        text = "Hello world!";  
    }  
}  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlTypes  
Imports System.Runtime.InteropServices  
  
Public Class HelloWorldProc  
    <Microsoft.SqlServer.Server.SqlProcedure> _   
    Public Shared  Sub HelloWorld(<Out()> ByRef text as String)  
        SqlContext.Pipe.Send("Hello world!" & Environment.NewLine)  
        text = "Hello world!"  
    End Sub  
End Class  
  
```  
  
 <span data-ttu-id="8e0d0-113">Эта простая программа содержит единственный статический метод общего класса.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-113">This simple program contains a single static method on a public class.</span></span> <span data-ttu-id="8e0d0-114">В методе используются два новых класса, `SqlContext` и `SqlPipe`, позволяющие создать управляемые объекты базы данных для вывода простого текстового сообщения.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-114">This method uses two new classes, `SqlContext` and `SqlPipe`, for creating managed database objects to output a simple text message.</span></span> <span data-ttu-id="8e0d0-115">Метод также назначает строку "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="8e0d0-115">The method also assigns the string "Hello world!"</span></span> <span data-ttu-id="8e0d0-116">в качестве значения параметра out.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-116">as the value of an out parameter.</span></span> <span data-ttu-id="8e0d0-117">Этот метод может быть объявлен как хранимая процедура в [!INCLUDE[ssNoVersion](../../../includes/tsql-md.md)] хранимой процедуре.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-117">This method can be declared as a stored procedure in [!INCLUDE[ssNoVersion](../../../includes/tsql-md.md)] stored procedure.</span></span>  
  
 <span data-ttu-id="8e0d0-118">После этого достаточно скомпилировать эту программу как библиотеку, загрузить ее в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] и выполнить как хранимую процедуру.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-118">We will now compile this program as a library, load it into [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], and run it as a stored procedure.</span></span>  
  
## <a name="compiling-the-hello-world-stored-procedure"></a><span data-ttu-id="8e0d0-119">Компилирование хранимой процедуры «Hello World»</span><span class="sxs-lookup"><span data-stu-id="8e0d0-119">Compiling the "Hello World" Stored Procedure</span></span>  
 [!INCLUDE[ssNoVersion](../../../includes/msconame-md.md)]<span data-ttu-id="8e0d0-120">.NET Framework файлы распространения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-120">.NET Framework redistribution files by default.</span></span> <span data-ttu-id="8e0d0-121">Эти файлы включают csc.exe и vbc.exe, компиляторы командной строки для программ Visual C# и Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-121">These files include csc.exe and vbc.exe, the command-line compilers for Visual C# and Visual Basic programs.</span></span> <span data-ttu-id="8e0d0-122">Чтобы скомпилировать приведенный образец, измените используемую системную переменную пути и укажите в ней путь к каталогу, содержащему файл csc.exe или vbc.exe.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-122">In order to compile our sample, you must modify your path variable to point to the directory containing csc.exe or vbc.exe.</span></span> <span data-ttu-id="8e0d0-123">Ниже приведен используемый по умолчанию путь установки .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-123">The following is the default installation path of the .NET Framework.</span></span>  
  
```  
C:\Windows\Microsoft.NET\Framework\(version)  
```  
  
 <span data-ttu-id="8e0d0-124">Версия содержит номер версии установленной платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-124">Version contains the version number of the installed .NET Framework redistributable.</span></span> <span data-ttu-id="8e0d0-125">Пример:</span><span class="sxs-lookup"><span data-stu-id="8e0d0-125">For example:</span></span>  
  
```  
C:\Windows\Microsoft.NET\Framework\v2.0.31113  
```  
  
 <span data-ttu-id="8e0d0-126">После добавления каталога .NET Framework к пути можно скомпилировать образец хранимой процедуры с созданием сборки с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-126">Once you have added the .NET Framework directory to your path, you can compile the sample stored procedure into an assembly with the following command.</span></span> <span data-ttu-id="8e0d0-127">Параметр `/target` позволяет скомпилировать код в виде сборки.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-127">The `/target` option allows you to compile it into an assembly.</span></span>  
  
 <span data-ttu-id="8e0d0-128">Для файлов с исходным кодом Visual C#:</span><span class="sxs-lookup"><span data-stu-id="8e0d0-128">For Visual C# source files:</span></span>  
  
```  
csc /target:library helloworld.cs   
```  
  
 <span data-ttu-id="8e0d0-129">Для файлов с исходным кодом Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="8e0d0-129">For Visual Basic source files:</span></span>  
  
```  
vbc /target:library helloworld.vb  
```  
  
 <span data-ttu-id="8e0d0-130">Эти команды запускают компилятор Visual C# или Visual Basic с использованием параметра /target, задающего построение библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-130">These commands launch the Visual C# or Visual Basic compiler using the /target option to specify building a library DLL.</span></span>  
  
## <a name="loading-and-running-the-hello-world-stored-procedure-in-sql-server"></a><span data-ttu-id="8e0d0-131">Загрузка и выполнение хранимой процедуры «Hello World» в SQL Server</span><span class="sxs-lookup"><span data-stu-id="8e0d0-131">Loading and Running the "Hello World" Stored Procedure in SQL Server</span></span>  
 <span data-ttu-id="8e0d0-132">После успешной компиляции образца процедуры можно протестировать ее в [!INCLUDE[ssNoVersion](../../../includes/ssmanstudiofull-md.md)] и создать новый запрос, подключившись к подходящей тестовой базе данных (например, образцу базы данных AdventureWorks).</span><span class="sxs-lookup"><span data-stu-id="8e0d0-132">Once the sample procedure has successfully compiled, you can test it in [!INCLUDE[ssNoVersion](../../../includes/ssmanstudiofull-md.md)] and create a new query, connecting to a suitable test database (for example, the AdventureWorks sample database).</span></span>  
  
 <span data-ttu-id="8e0d0-133">По умолчанию возможность выполнять код среды CLR в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] отключена.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-133">The ability to execute common language runtime (CLR) code is set to OFF by default in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8e0d0-134">Код CLR можно включить с помощью системной хранимой процедуры **sp_configure** .</span><span class="sxs-lookup"><span data-stu-id="8e0d0-134">The CLR code can be enabled by using the **sp_configure** system stored procedure.</span></span> <span data-ttu-id="8e0d0-135">Дополнительные сведения см. в статье [Enabling CLR Integration](../clr-integration-enabling.md).</span><span class="sxs-lookup"><span data-stu-id="8e0d0-135">For more information, see [Enabling CLR Integration](../clr-integration-enabling.md).</span></span>  
  
 <span data-ttu-id="8e0d0-136">Создание сборки требуется для того, чтобы можно было получить доступ к хранимой процедуре.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-136">We will need to create the assembly so we can access the stored procedure.</span></span> <span data-ttu-id="8e0d0-137">В этом примере предполагается, что была создана сборка helloworld.dll в каталоге C:\.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-137">For this example, we will assume that you have created the helloworld.dll assembly in the C:\ directory.</span></span> <span data-ttu-id="8e0d0-138">Добавьте к запросу следующую инструкцию [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e0d0-138">Add the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement to your query.</span></span>  
  
```  
CREATE ASSEMBLY helloworld from 'c:\helloworld.dll' WITH PERMISSION_SET = SAFE  
```  
  
 <span data-ttu-id="8e0d0-139">После создания сборки появляется возможность получить доступ к методу HelloWorld с помощью инструкции создания процедуры.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-139">Once the assembly has been created, we can now access our HelloWorld method by using the create procedure statement.</span></span> <span data-ttu-id="8e0d0-140">Назовем создаваемую хранимую процедуру «hello»:</span><span class="sxs-lookup"><span data-stu-id="8e0d0-140">We will call our stored procedure "hello":</span></span>  
  
```  
  
CREATE PROCEDURE hello  
@i nchar(25) OUTPUT  
AS  
EXTERNAL NAME helloworld.HelloWorldProc.HelloWorld  
-- if the HelloWorldProc class is inside a namespace (called MyNS),  
-- the last line in the create procedure statement would be  
-- EXTERNAL NAME helloworld.[MyNS.HelloWorldProc].HelloWorld  
```  
  
 <span data-ttu-id="8e0d0-141">После создания процедуры ее можно выполнить как обычную хранимую процедуру на языке [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e0d0-141">Once the procedure has been created, it can be run just like a normal stored procedure written in [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="8e0d0-142">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8e0d0-142">Execute the following command:</span></span>  
  
```  
DECLARE @J nchar(25)  
EXEC hello @J out  
PRINT @J  
```  
  
 <span data-ttu-id="8e0d0-143">Это должно привести к появлению следующего вывода в окне сообщений среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e0d0-143">This should result in the following output in the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] messages window.</span></span>  
  
```  
Hello world!  
Hello world!  
```  
  
## <a name="removing-the-hello-world-stored-procedure-sample"></a><span data-ttu-id="8e0d0-144">Удаление образца хранимой процедуры «Hello World»</span><span class="sxs-lookup"><span data-stu-id="8e0d0-144">Removing the "Hello World" Stored Procedure Sample</span></span>  
 <span data-ttu-id="8e0d0-145">После завершения выполнения образца хранимой процедуры эту процедуру и сборку можно удалить из тестовой базы данных.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-145">When you are finished running the sample stored procedure, you can remove the procedure and the assembly from your test database.</span></span>  
  
 <span data-ttu-id="8e0d0-146">Вначале удалите процедуру с помощью команды drop procedure.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-146">First, remove the procedure using the drop procedure command.</span></span>  
  
```  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'hello')  
   drop procedure hello  
```  
  
 <span data-ttu-id="8e0d0-147">После удаления процедуры можно удалить сборку, содержащую образец кода.</span><span class="sxs-lookup"><span data-stu-id="8e0d0-147">Once the procedure has been dropped, you can remove the assembly containing your sample code.</span></span>  
  
```  
IF EXISTS (SELECT name FROM sys.assemblies WHERE name = 'helloworld')  
   drop assembly helloworld  
```  
  
## <a name="see-also"></a><span data-ttu-id="8e0d0-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="8e0d0-148">See Also</span></span>  
 <span data-ttu-id="8e0d0-149">[Хранимые процедуры CLR](../../../database-engine/dev-guide/clr-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="8e0d0-149">[CLR Stored Procedures](../../../database-engine/dev-guide/clr-stored-procedures.md) </span></span>  
 <span data-ttu-id="8e0d0-150">[SQL Server встроенных расширений ADO.NET](../../clr-integration-data-access-in-process-ado-net/sql-server-in-process-specific-extensions-to-ado-net.md) </span><span class="sxs-lookup"><span data-stu-id="8e0d0-150">[SQL Server In-Process Specific Extensions to ADO.NET](../../clr-integration-data-access-in-process-ado-net/sql-server-in-process-specific-extensions-to-ado-net.md) </span></span>  
 <span data-ttu-id="8e0d0-151">[Отладка объектов базы данных CLR](../debugging-clr-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="8e0d0-151">[Debugging CLR Database Objects](../debugging-clr-database-objects.md) </span></span>  
 [<span data-ttu-id="8e0d0-152">Безопасность интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="8e0d0-152">CLR Integration Security</span></span>](../security/clr-integration-security.md)  
  
  
