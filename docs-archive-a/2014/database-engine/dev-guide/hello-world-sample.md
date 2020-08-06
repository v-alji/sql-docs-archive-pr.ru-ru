---
title: Пример Hello World | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
ms.assetid: fed6c358-f5ee-4d4c-9ad6-089778383ba7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0d5616c1d4ef6428a011c8e36be3757931039c9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751403"
---
# <a name="hello-world-sample"></a><span data-ttu-id="4c98c-102">Образец «Hello World»</span><span class="sxs-lookup"><span data-stu-id="4c98c-102">Hello World Sample</span></span>
  <span data-ttu-id="4c98c-103">Образец Hello World демонстрирует основные операции, применяемые при создании, развертывании и тестировании простых хранимых процедур на основе интеграции со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="4c98c-103">The Hello World sample demonstrates the basic operations that are involved in creating, deploying, and testing a simple common language runtime (CLR) integration-based stored procedure.</span></span> <span data-ttu-id="4c98c-104">Этот образец также демонстрирует способы возврата данных при помощи выходного параметра и записи, которая динамически создается хранимой процедурой и возвращается вызывающему.</span><span class="sxs-lookup"><span data-stu-id="4c98c-104">This sample also demonstrates how to return data through a record, which is dynamically constructed by the stored procedure and returned to the caller.</span></span>  
  
 <span data-ttu-id="4c98c-105">`HelloWorld`Хранимая процедура возвращает строку "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="4c98c-105">The `HelloWorld` stored procedure returns the string "Hello world!"</span></span> <span data-ttu-id="4c98c-106">в результирующем наборе, состоящем из одной строки.</span><span class="sxs-lookup"><span data-stu-id="4c98c-106">in a result set consisting of one row.</span></span> <span data-ttu-id="4c98c-107">В этом примере показаны некоторые варианты использования классов [Microsoft. SqlServer. Server. склметадата](https://go.microsoft.com/fwlink/?LinkID=193572), [Microsoft. SqlServer. Server. SqlDataRecord](https://go.microsoft.com/fwlink/?LinkID=193573) и [Microsoft. SqlServer. Server. pipe](https://go.microsoft.com/fwlink/?LinkID=193571).</span><span class="sxs-lookup"><span data-stu-id="4c98c-107">This example illustrates some uses for the classes [Microsoft.SqlServer.Server.SqlMetaData](https://go.microsoft.com/fwlink/?LinkID=193572), [Microsoft.SqlServer.Server.SqlDataRecord](https://go.microsoft.com/fwlink/?LinkID=193573) and [Microsoft.SqlServer.Server.Pipe](https://go.microsoft.com/fwlink/?LinkID=193571).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4c98c-108">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="4c98c-108">Prerequisites</span></span>  
 <span data-ttu-id="4c98c-109">Для создания и запуска этого проекта должно быть установлено следующее программное обеспечение:</span><span class="sxs-lookup"><span data-stu-id="4c98c-109">To create and run this project the following the following software must be installed:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="4c98c-110">или [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span><span class="sxs-lookup"><span data-stu-id="4c98c-110">or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span></span> <span data-ttu-id="4c98c-111">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express можно получить бесплатно на [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] веб-сайте [с документацией и примерами по](https://www.microsoft.com/sql-server/sql-server-editions-express)Express.</span><span class="sxs-lookup"><span data-stu-id="4c98c-111">You can obtain [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express free of charge from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express Documentation and Samples [Web site](https://www.microsoft.com/sql-server/sql-server-editions-express)</span></span>  
  
-   <span data-ttu-id="4c98c-112">База данных AdventureWorks, доступная на [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] веб-сайте [разработки](https://go.microsoft.com/fwlink/?linkid=62796).</span><span class="sxs-lookup"><span data-stu-id="4c98c-112">The AdventureWorks database that is available at the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Developer [Web site](https://go.microsoft.com/fwlink/?linkid=62796)</span></span>  
  
-   <span data-ttu-id="4c98c-113">Пакет SDK 2.0 для платформы .NET Framework или более поздняя версия либо среда Microsoft Visual Studio 2005 или более поздняя версия.</span><span class="sxs-lookup"><span data-stu-id="4c98c-113">.NET Framework SDK 2.0 or later or Microsoft Visual Studio 2005 or later.</span></span> <span data-ttu-id="4c98c-114">Пакет SDK для платформы .NET Framework можно получить бесплатно.</span><span class="sxs-lookup"><span data-stu-id="4c98c-114">You can obtain .NET Framework SDK free of charge.</span></span>  
  
-   <span data-ttu-id="4c98c-115">Кроме того, должны выполняться следующие условия.</span><span class="sxs-lookup"><span data-stu-id="4c98c-115">In addition, the following conditions must be met:</span></span>  
  
-   <span data-ttu-id="4c98c-116">Для используемого экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] должна быть включена интеграция со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="4c98c-116">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using must have CLR integration enabled.</span></span>  
  
-   <span data-ttu-id="4c98c-117">Чтобы включить интеграцию со средой CLR, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="4c98c-117">In order to enable CLR integration, perform the following steps:</span></span>  
  
    #### <a name="enabling-clr-integration"></a><span data-ttu-id="4c98c-118">Включение интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="4c98c-118">Enabling CLR Integration</span></span>  
  
    -   <span data-ttu-id="4c98c-119">Выполните следующие команды [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="4c98c-119">Execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] commands:</span></span>  
  
     `sp_configure 'clr enabled', 1`  
  
     `GO`  
  
     `RECONFIGURE`  
  
     `GO`  
  
    > [!NOTE]  
    >  <span data-ttu-id="4c98c-120">Чтобы включить CLR, необходимо иметь разрешение `ALTER SETTINGS` на уровне сервера, которое неявно предоставляется членам предопределенных ролей сервера `sysadmin` и `serveradmin`.</span><span class="sxs-lookup"><span data-stu-id="4c98c-120">To enable CLR, you must have `ALTER SETTINGS` server level permission, which is implicitly held by members of the `sysadmin` and `serveradmin` fixed server roles.</span></span>  
  
-   <span data-ttu-id="4c98c-121">На используемом экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] должна быть установлена база данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="4c98c-121">The AdventureWorks database must be installed on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using.</span></span>  
  
-   <span data-ttu-id="4c98c-122">Если вы не являетесь администратором используемого экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , то для завершения установки необходимо, чтобы администратор предоставил разрешение **CreateAssembly** .</span><span class="sxs-lookup"><span data-stu-id="4c98c-122">If you are not an administrator for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using, you must have an administrator grant you **CreateAssembly** permission to complete the installation.</span></span>  
  
## <a name="building-the-sample"></a><span data-ttu-id="4c98c-123">Построение образца</span><span class="sxs-lookup"><span data-stu-id="4c98c-123">Building the Sample</span></span>  
  
#### <a name="create-and-run-the-sample-by-using-the-following-instructions"></a><span data-ttu-id="4c98c-124">Создайте и запустите образец в соответствии со следующими инструкциями.</span><span class="sxs-lookup"><span data-stu-id="4c98c-124">Create and run the sample by using the following instructions:</span></span>  
  
1.  <span data-ttu-id="4c98c-125">Откройте командную строку Visual Studio или .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4c98c-125">Open a Visual Studio or .NET Framework command prompt.</span></span>  
  
2.  <span data-ttu-id="4c98c-126">Если необходимо, создайте каталог для своего образца.</span><span class="sxs-lookup"><span data-stu-id="4c98c-126">If necessary, create a directory for your sample.</span></span> <span data-ttu-id="4c98c-127">В данном примере будет использоваться каталог C:\MySample.</span><span class="sxs-lookup"><span data-stu-id="4c98c-127">For this example, we will use C:\MySample.</span></span>  
  
3.  <span data-ttu-id="4c98c-128">В каталоге c:\MySample создайте файл `HelloWorld.vb` (для образца на языке Visual Basic) или `HelloWorld.cs` (для образца на языке C#) и скопируйте в него соответствующий образец кода на языке Visual Basic или C#, приведенный ниже.</span><span class="sxs-lookup"><span data-stu-id="4c98c-128">In c:\MySample, create `HelloWorld.vb` (for the Visual Basic sample) or `HelloWorld.cs` (for the C# sample) and copy the appropriate Visual Basic or C# sample code (below) into the file.</span></span>  
  
4.  <span data-ttu-id="4c98c-129">Скомпилируйте образец кода из командной строки, выполнив одну из следующих команд, в зависимости от выбранного языка.</span><span class="sxs-lookup"><span data-stu-id="4c98c-129">Compile the sample code from the command line prompt by executing one of the following, depending on your choice of language.</span></span>  
  
    -   `vbc C:HelloWorld.vb /target:library`  
  
    -   `csc /target:library HelloWorld.cs`  
  
5.  <span data-ttu-id="4c98c-130">Скопируйте код установки [!INCLUDE[tsql](../../includes/tsql-md.md)] в файл и сохраните его в файле `Install.sql` в том же каталоге.</span><span class="sxs-lookup"><span data-stu-id="4c98c-130">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation code into a file and save it as `Install.sql` in the sample directory.</span></span>  
  
6.  <span data-ttu-id="4c98c-131">Разверните сборку и хранимую процедуру, выполнив</span><span class="sxs-lookup"><span data-stu-id="4c98c-131">Deploy the assembly and stored procedure by executing</span></span>  
  
    -   `sqlcmd -E -I -i install.sql -v root = "C:\MySample\"`  
  
7.  <span data-ttu-id="4c98c-132">Скопируйте скрипт проверки [!INCLUDE[tsql](../../includes/tsql-md.md)] в файл и сохраните его в файле `test.sql` в том же каталоге.</span><span class="sxs-lookup"><span data-stu-id="4c98c-132">Copy [!INCLUDE[tsql](../../includes/tsql-md.md)] test command script into a file and save it as `test.sql` in the sample directory.</span></span>  
  
8.  <span data-ttu-id="4c98c-133">Выполните скрипт проверки следующей командой</span><span class="sxs-lookup"><span data-stu-id="4c98c-133">Execute the test script with the following command</span></span>  
  
    -   `sqlcmd -E -I -i test.sql`  
  
9. <span data-ttu-id="4c98c-134">Скопируйте скрипт очистки [!INCLUDE[tsql](../../includes/tsql-md.md)] в файл и сохраните его в файле `cleanup.sql` в том же каталоге.</span><span class="sxs-lookup"><span data-stu-id="4c98c-134">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] cleanup script into a file and save it as `cleanup.sql` in the sample directory.</span></span>  
  
10. <span data-ttu-id="4c98c-135">Выполните скрипт следующей командой</span><span class="sxs-lookup"><span data-stu-id="4c98c-135">Execute the script with the  following command</span></span>  
  
    -   `sqlcmd -E -I -i cleanup.sql`  
  
## <a name="sample-code"></a><span data-ttu-id="4c98c-136">Пример кода</span><span class="sxs-lookup"><span data-stu-id="4c98c-136">Sample Code</span></span>  
 <span data-ttu-id="4c98c-137">Ниже приведены листинги кода для данного образца.</span><span class="sxs-lookup"><span data-stu-id="4c98c-137">The following are the code listings for this sample.</span></span>  
  
 <span data-ttu-id="4c98c-138">C#</span><span class="sxs-lookup"><span data-stu-id="4c98c-138">C#</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
public partial class StoredProcedures  
{  
    [Microsoft.SqlServer.Server.SqlProcedure]  
    public static void HelloWorld()  
    {  
        Microsoft.SqlServer.Server.SqlMetaData columnInfo  
                = new Microsoft.SqlServer.Server.SqlMetaData("Column1", SqlDbType.NVarChar, 12);  
        SqlDataRecord greetingRecord  
            = new SqlDataRecord(new Microsoft.SqlServer.Server.SqlMetaData[] { columnInfo });  
        greetingRecord.SetString(0, "Hello world!");  
        SqlContext.Pipe.Send(greetingRecord);  
    }  
};  
  
```  
  
 <span data-ttu-id="4c98c-139">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4c98c-139">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
  
Partial Public NotInheritable Class StoredProcedures  
    <Microsoft.SqlServer.Server.SqlProcedure()> _  
    Public Shared Sub HelloWorld()  
        Dim columnInfo As New Microsoft.SqlServer.Server.SqlMetaData("Column1", _  
            SqlDbType.NVarChar, 12)  
        Dim greetingRecord As New SqlDataRecord(New  _  
            Microsoft.SqlServer.Server.SqlMetaData() {columnInfo})  
        greetingRecord.SetString(0, "Hello World!")  
        SqlContext.Pipe.Send(greetingRecord)  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="4c98c-140">Это скрипт установки [!INCLUDE[tsql](../../includes/tsql-md.md)] (`Install.sql`), который выполняет развертывание сборки и создает в базе данных хранимую процедуру.</span><span class="sxs-lookup"><span data-stu-id="4c98c-140">This is the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation script (`Install.sql`), which deploys the assembly and creates the stored procedure in the database.</span></span>  
  
```  
USE AdventureWorks  
GO  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = 'usp_HelloWorld')  
DROP PROCEDURE usp_HelloWorld;  
GO  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorld')  
DROP ASSEMBLY HelloWorld;  
GO  
DECLARE @SamplesPath nvarchar(1024)  
set @SamplesPath = '$(root)'  
CREATE ASSEMBLY HelloWorld   
FROM @SamplesPath + 'HelloWorld.dll'  
WITH permission_set = Safe;  
GO  
  
CREATE PROCEDURE usp_HelloWorld  
--(  
--    @Greeting nvarchar(12) OUTPUT  
--)  
AS EXTERNAL NAME HelloWorld.[StoredProcedures].HelloWorld;  
GO  
```  
  
 <span data-ttu-id="4c98c-141">Это файл `test.sql`, который проверяет образец, выполняя хранимую процедуру.</span><span class="sxs-lookup"><span data-stu-id="4c98c-141">This is `test.sql`, which tests the sample by executing the stored procedure.</span></span>  
  
```  
use AdventureWorks  
go  
execute usp_HelloWorld  
  
USE AdventureWorks;  
GO  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = 'usp_HelloWorld')  
DROP PROCEDURE usp_HelloWorld;  
GO  
```  
  
 <span data-ttu-id="4c98c-142">В следующем образце [!INCLUDE[tsql](../../includes/tsql-md.md)] сборка и хранимая процедура удаляются из базы данных.</span><span class="sxs-lookup"><span data-stu-id="4c98c-142">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] removes the assembly and stored procedure from the database.</span></span>  
  
```  
USE AdventureWorks  
GO  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = 'usp_HelloWorld')  
DROP PROCEDURE usp_HelloWorld;  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorld')  
DROP ASSEMBLY HelloWorld;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="4c98c-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="4c98c-143">See Also</span></span>  
 [<span data-ttu-id="4c98c-144">Сценарии использования и примеры интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="4c98c-144">Usage Scenarios and Examples for Common Language Runtime &#40;CLR&#41; Integration</span></span>](../../../2014/database-engine/dev-guide/usage-scenarios-and-examples-for-common-language-runtime-clr-integration.md)  
  
  
