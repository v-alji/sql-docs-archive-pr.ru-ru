---
title: Доступ к машинному коду из определяемой пользователем функции CLR | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
ms.assetid: 161afa9d-74a1-40f5-af17-162e355e7a46
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d36e93fc39e9231a4d8677535c6e13c905d55a4f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657264"
---
# <a name="accessing-native-code-from-a-clr-udf"></a><span data-ttu-id="d0e7d-102">доступ к машинному коду из определяемой пользователем функции CLR</span><span class="sxs-lookup"><span data-stu-id="d0e7d-102">Accessing Native Code from a CLR UDF</span></span>
  <span data-ttu-id="d0e7d-103">В этом примере показано, как в базе данных вызвать функцию в собственном (неуправляемом) коде C++ из определяемой пользователем функции в сборке.</span><span class="sxs-lookup"><span data-stu-id="d0e7d-103">This example shows how to invoke a function in native (unmanaged) C++ code from a user-defined function in an assembly, in your database.</span></span>  
  
 <span data-ttu-id="d0e7d-104">В этом примере рабочий каталог должен иметь значение `c:\test` .</span><span class="sxs-lookup"><span data-stu-id="d0e7d-104">For this example, the working directory should be `c:\test`.</span></span>  
  
 <span data-ttu-id="d0e7d-105">Сначала скомпилируйте код C++:</span><span class="sxs-lookup"><span data-stu-id="d0e7d-105">First compile the C++ code:</span></span>  
  
```  
// Win32Sleep.cpp  
// compile with: /LD /link /noentry kernel32.lib  
#include <windows.h>  
  
extern "C"  
__declspec( dllexport ) void _cdecl SleepyLoop(DWORD sleep_interval) {  
   Sleep(sleep_interval);  
}  
```  
  
 <span data-ttu-id="d0e7d-106">Затем скомпилируйте код C# в сборку:</span><span class="sxs-lookup"><span data-stu-id="d0e7d-106">Next, compile the C# code to an assembly:</span></span>  
  
```  
// proc.cs  
// compile with: /target:library  
using System;  
using System.Threading;  
using System.Data.Sql;  
using System.Runtime.InteropServices;  
  
public class StoreProcedures {  
  
   public static readonly uint SLEEP_LOOP_TIMES = 10;  
   public static readonly uint SLEEP_DURATION = 1000;  
  
   [DllImport(@"c:\test\Win32Sleep.dll")]  
   internal static extern void SleepyLoop(uint sleepInterval);  
  
   public static void SleepInProcedure(int loopTimes) {  
      for ( int i = 0 ; i < loopTimes ; i++ ) {  
         // invoke the unmanaged routine  
         SleepyLoop(SLEEP_DURATION);  
      }  
   }  
}  
```  
  
 <span data-ttu-id="d0e7d-107">Наконец, выполните следующие команды [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="d0e7d-107">Finally, execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span></span>  
  
```  
USE MASTER  
GO  
  
IF DB_ID('testdb') IS NOT NULL  
DROP DATABASE testdb  
GO  
  
CREATE DATABASE testdb  
GO  
  
USE testdb  
GO  
  
ALTER DATABASE testdb SET TRUSTWORTHY ON   
GO  
  
sp_configure 'show advanced options', 1  
GO  
RECONFIGURE  
GO  
sp_configure 'clr enabled', 1  
GO  
RECONFIGURE  
GO  
  
CREATE ASSEMBLY myasm FROM 'c:\test\proc.dll' WITH PERMISSION_SET=UNSAFE   
go  
  
CREATE PROCEDURE SleepProc(@loopTimes INT)  
AS EXTERNAL NAME myasm.[StoreProcedures].[SleepInProcedure]  
go  
  
-- sleep 5 seconds  
EXEC SleepProc 5  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="d0e7d-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="d0e7d-108">See Also</span></span>  
 [<span data-ttu-id="d0e7d-109">Сценарии использования и примеры интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="d0e7d-109">Usage Scenarios and Examples for Common Language Runtime &#40;CLR&#41; Integration</span></span>](../../../2014/database-engine/dev-guide/usage-scenarios-and-examples-for-common-language-runtime-clr-integration.md)  
  
  
