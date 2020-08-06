---
title: Доступ к текущей транзакции | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- current transaction access
- Current property
- Transaction class
ms.assetid: 1a4e2ce5-f627-4c81-8960-6a9968cefda2
author: rothja
ms.author: jroth
ms.openlocfilehash: 34b7e67d30cb9d89a02eb918fcd03651b2915955
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751200"
---
# <a name="accessing-the-current-transaction"></a><span data-ttu-id="7918b-102">Доступ к текущей транзакции</span><span class="sxs-lookup"><span data-stu-id="7918b-102">Accessing the Current Transaction</span></span>
  <span data-ttu-id="7918b-103">Если транзакция является активной в той точке, в которой вызывается код среды CLR, применяемой в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], то транзакция становится доступной через класс `System.Transactions.Transaction`.</span><span class="sxs-lookup"><span data-stu-id="7918b-103">If a transaction is active at the point at which common language runtime (CLR) code running on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is entered, the transaction is exposed through the `System.Transactions.Transaction` class.</span></span> <span data-ttu-id="7918b-104">Для доступа к текущей транзакции используется свойство `Transaction.Current`.</span><span class="sxs-lookup"><span data-stu-id="7918b-104">The `Transaction.Current` property is used to access the current transaction.</span></span> <span data-ttu-id="7918b-105">В большинстве случаев в получении явного доступа к транзакции нет необходимости.</span><span class="sxs-lookup"><span data-stu-id="7918b-105">In most cases it is not necessary to access the transaction explicitly.</span></span> <span data-ttu-id="7918b-106">Что касается подключений к базам данных, то в ADO.NET автоматически происходят проверка `Transaction.Current` при вызове метода `Connection.Open` и явное прикрепление соединения к этой транзакции (если только в строке соединения ключевое слово `Enlist` не задано равным false).</span><span class="sxs-lookup"><span data-stu-id="7918b-106">For database connections, ADO.NET checks `Transaction.Current` automatically when the `Connection.Open` method is called, and transparently enlists the connection in that transaction (unless the `Enlist` keyword is set to false in the connection string).</span></span>  
  
 <span data-ttu-id="7918b-107">Необходимость в непосредственном использовании объекта `Transaction` может возникнуть в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="7918b-107">You might want to use the `Transaction` object directly in the following scenarios:</span></span>  
  
-   <span data-ttu-id="7918b-108">если необходимо прикрепить ресурс, для которого не осуществляется автоматическое прикрепление, или который по какой-либо причине не был прикреплен во время инициализации;</span><span class="sxs-lookup"><span data-stu-id="7918b-108">If you want to enlist a resource that does not do automatic enlistment, or that for some reason was not enlisted during initialization.</span></span>  
  
-   <span data-ttu-id="7918b-109">если необходимо явно прикрепить ресурс в транзакции;</span><span class="sxs-lookup"><span data-stu-id="7918b-109">If you want to explicitly enlist a resource in the transaction.</span></span>  
  
-   <span data-ttu-id="7918b-110">если необходимо завершить внешнюю транзакцию внутри хранимой процедуры или функции.</span><span class="sxs-lookup"><span data-stu-id="7918b-110">If you want to terminate the external transaction from within your stored procedure or function.</span></span> <span data-ttu-id="7918b-111">В этом случае используется <xref:System.Transactions.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="7918b-111">In this case, you use <xref:System.Transactions.TransactionScope>.</span></span> <span data-ttu-id="7918b-112">Например, выполнение следующего кода приведет к откату текущей транзакции:</span><span class="sxs-lookup"><span data-stu-id="7918b-112">For example, the following code will rollback the current transaction:</span></span>  
  
    ```  
    using(TransactionScope transactionScope = new TransactionScope(TransactionScopeOptions.Required)) { }  
    ```  
  
 <span data-ttu-id="7918b-113">В остальной части раздела рассматриваются другие способы отмены внешней транзакции.</span><span class="sxs-lookup"><span data-stu-id="7918b-113">The rest of this topic describes other ways to cancel an external transaction.</span></span>  
  
## <a name="canceling-an-external-transaction"></a><span data-ttu-id="7918b-114">Отмена внешней транзакции</span><span class="sxs-lookup"><span data-stu-id="7918b-114">Canceling an External Transaction</span></span>  
 <span data-ttu-id="7918b-115">Внешнюю транзакцию можно отменить из управляемой процедуры или функции следующими способами.</span><span class="sxs-lookup"><span data-stu-id="7918b-115">You can cancel external transactions from a managed procedure or function in the following ways:</span></span>  
  
-   <span data-ttu-id="7918b-116">Управляемая процедура или функция может возвратить какое-либо значение с помощью выходного параметра.</span><span class="sxs-lookup"><span data-stu-id="7918b-116">The managed procedure or function can return a value by using an output parameter.</span></span> <span data-ttu-id="7918b-117">В вызове процедуры [!INCLUDE[tsql](../../includes/tsql-md.md)] может быть предусмотрена проверка возвращаемого значения, и, в случае необходимости, выполнение `ROLLBACK TRANSACTION`.</span><span class="sxs-lookup"><span data-stu-id="7918b-117">The calling [!INCLUDE[tsql](../../includes/tsql-md.md)] procedure can check the returned value and, if appropriate, execute `ROLLBACK TRANSACTION`.</span></span>  
  
-   <span data-ttu-id="7918b-118">Управляемая процедура или функция может активизировать пользовательское исключение.</span><span class="sxs-lookup"><span data-stu-id="7918b-118">The managed procedure or function can throw a custom exception.</span></span> <span data-ttu-id="7918b-119">Вызывающая [!INCLUDE[tsql](../../includes/tsql-md.md)] процедура может перехватить исключение, созданное управляемой процедурой или функцией в блоке try/catch, и выполнить `ROLLBACK TRANSACTION` .</span><span class="sxs-lookup"><span data-stu-id="7918b-119">The calling [!INCLUDE[tsql](../../includes/tsql-md.md)] procedure can catch the exception thrown by the managed procedure or function in a try/catch block and execute `ROLLBACK TRANSACTION`.</span></span>  
  
-   <span data-ttu-id="7918b-120">Управляемая процедура или функция может отменить текущую транзакцию путем вызова метода `Transaction.Rollback`, если соблюдается определенное условие.</span><span class="sxs-lookup"><span data-stu-id="7918b-120">The managed procedure or function can cancel the current transaction by calling the `Transaction.Rollback` method if a certain condition is met.</span></span>  
  
 <span data-ttu-id="7918b-121">При вызове в управляемой процедуре или функции метод `Transaction.Rollback` активизирует исключение с неоднозначным сообщением об ошибке и может быть заключен в блок try-catch.</span><span class="sxs-lookup"><span data-stu-id="7918b-121">When it is called within a managed procedure or function, the `Transaction.Rollback` method throws an exception with an ambiguous error message and can be wrapped in a try/catch block.</span></span> <span data-ttu-id="7918b-122">Сообщение об ошибке подобно следующему:</span><span class="sxs-lookup"><span data-stu-id="7918b-122">The error message thresembles similar to the following:</span></span>  
  
```  
Msg 3994, Level 16, State 1, Procedure uspRollbackFromProc, Line 0  
Transaction is not allowed to roll back inside a user defined routine, trigger or aggregate because the transaction is not started in that CLR level. Change application logic to enforce strict transaction nesting.  
```  
  
 <span data-ttu-id="7918b-123">Это ожидаемое исключение, поэтому для продолжения выполнения кода необходим блок try-catch.</span><span class="sxs-lookup"><span data-stu-id="7918b-123">This exception is expected and the try/catch block is necessary for code execution to continue.</span></span> <span data-ttu-id="7918b-124">Без блока try-catch в вызывающей процедуре [!INCLUDE[tsql](../../includes/tsql-md.md)] будет немедленно активизировано исключение, и выполнение управляемого кода завершится.</span><span class="sxs-lookup"><span data-stu-id="7918b-124">Without the try/catch block, the exception will be immediately thrown to the calling [!INCLUDE[tsql](../../includes/tsql-md.md)] procedure and managed code execution will finish.</span></span> <span data-ttu-id="7918b-125">Если выполнение управляемого кода завершается, то вызывается другое исключение:</span><span class="sxs-lookup"><span data-stu-id="7918b-125">When the managed code finishes execution, another exception is raised:</span></span>  
  
```  
Msg 3991, Level 16, State 1, Procedure uspRollbackFromProc, Line 1   
The context transaction which was active before entering user defined routine, trigger or aggregate " uspRollbackFromProc " has been ended inside of it, which is not allowed. Change application logic to enforce strict transaction nesting. The statement has been terminated.  
```  
  
 <span data-ttu-id="7918b-126">Это исключение также является ожидаемым, и чтобы обеспечить дальнейшее выполнение, необходимо заключить в блок try-catch инструкцию [!INCLUDE[tsql](../../includes/tsql-md.md)] , которая выполняет действие, вызывающее запуск триггера.</span><span class="sxs-lookup"><span data-stu-id="7918b-126">This exception is also expected, and for execution to continue, you must have a try/catch block around the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that performs the action that fires the trigger.</span></span> <span data-ttu-id="7918b-127">Несмотря на два активизированных исключения, происходит откат транзакции, а изменения не фиксируются.</span><span class="sxs-lookup"><span data-stu-id="7918b-127">Despite the two exceptions thrown, the transaction is rolled back and the changes are not committed.</span></span>  
  
### <a name="example"></a><span data-ttu-id="7918b-128">Пример</span><span class="sxs-lookup"><span data-stu-id="7918b-128">Example</span></span>  
 <span data-ttu-id="7918b-129">Ниже приведен пример транзакции, откат которой осуществляется из управляемой процедуры с помощью метода `Transaction.Rollback`.</span><span class="sxs-lookup"><span data-stu-id="7918b-129">The following is an example of a transaction being rolled back from a managed procedure by using the `Transaction.Rollback` method.</span></span> <span data-ttu-id="7918b-130">Обратите внимание на то, что метод `Transaction.Rollback` в управляемом коде заключен в блок try-catch.</span><span class="sxs-lookup"><span data-stu-id="7918b-130">Notice the try/catch block around the `Transaction.Rollback` method in the managed code.</span></span> <span data-ttu-id="7918b-131">В скрипте [!INCLUDE[tsql](../../includes/tsql-md.md)] создаются сборка и управляемая хранимая процедура.</span><span class="sxs-lookup"><span data-stu-id="7918b-131">The [!INCLUDE[tsql](../../includes/tsql-md.md)] script creates an assembly and managed stored procedure.</span></span> <span data-ttu-id="7918b-132">Имейте в виду, что `EXEC uspRollbackFromProc` инструкция упаковывается в блок try/catch, поэтому перехвачено исключение, возникающее при завершении выполнения управляемой процедуры.</span><span class="sxs-lookup"><span data-stu-id="7918b-132">Be aware that the `EXEC uspRollbackFromProc` statement is wrapped in a try/catch block, so that the exception thrown when the managed procedure completes execution is caught.</span></span>  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
using System.Transactions;  
  
public partial class StoredProcedures  
{  
[Microsoft.SqlServer.Server.SqlProcedure]  
public static void uspRollbackFromProc()  
{  
   using (SqlConnection connection = new SqlConnection(@"context connection=true"))  
   {  
      // Open the connection.  
      connection.Open();  
  
      bool successCondition = true;  
  
      // Success condition is met.  
      if (successCondition)  
      {  
         SqlContext.Pipe.Send("Success condition met in procedure.");   
         // Perform other actions here.  
      }  
  
      //  Success condition is not met, the transaction will be rolled back.  
      else  
      {  
         SqlContext.Pipe.Send("Success condition not met in managed procedure. Transaction rolling back...");  
         try  
         {  
               // Get the current transaction and roll it back.  
               Transaction trans = Transaction.Current;  
               trans.Rollback();  
         }  
         catch (SqlException ex)  
         {  
            // Catch the expected exception.   
            // This allows the connection to close correctly.                      
         }    
      }  
  
      // Close the connection.  
      connection.Close();  
   }  
}  
};  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Transactions  
  
Partial Public Class StoredProcedures  
<Microsoft.SqlServer.Server.SqlProcedure()> _  
Public Shared Sub  uspRollbackFromProc ()  
   Using connection As New SqlConnection("context connection=true")  
  
   ' Open the connection.  
   connection.Open()  
  
   Dim successCondition As Boolean  
   successCondition = False  
  
   ' Success condition is met.  
   If successCondition Then  
  
      SqlContext.Pipe.Send("Success condition met in procedure.")  
  
      ' Success condition is not met, the transaction will be rolled back.  
  
   Else  
      SqlContext.Pipe.Send("Success condition not met in managed procedure. Transaction rolling back...")  
      Try  
         ' Get the current transaction and roll it back.  
         Dim trans As Transaction  
         trans = Transaction.Current  
         trans.Rollback()  
  
      Catch ex As SqlException  
         ' Catch the exception instead of throwing it.    
         ' This allows the connection to close correctly.                      
      End Try  
  
   End If  
  
   ' Close the connection.  
   connection.Close()  
  
End Using  
End Sub  
End Class  
```  
  
 <span data-ttu-id="7918b-133">**Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="7918b-133">**Transact-SQL**</span></span>  
  
```  
--Register assembly.  
CREATE ASSEMBLY TestProcs FROM 'C:\Programming\TestProcs.dll'   
Go  
CREATE PROCEDURE uspRollbackFromProc AS EXTERNAL NAME TestProcs.StoredProcedures.uspRollbackFromProc  
Go  
  
-- Execute procedure.  
BEGIN TRY  
BEGIN TRANSACTION   
-- Perform other actions.  
Exec uspRollbackFromProc  
-- Perform other actions.  
PRINT N'Commiting transaction...'  
COMMIT TRANSACTION  
END TRY  
  
BEGIN CATCH  
SELECT ERROR_NUMBER() AS ErrorNum, ERROR_MESSAGE() AS ErrorMessage  
PRINT N'Exception thrown, rolling back transaction.'  
ROLLBACK TRANSACTION  
PRINT N'Transaction rolled back.'   
END CATCH  
Go  
  
-- Clean up.  
DROP Procedure uspRollbackFromProc;  
Go  
DROP ASSEMBLY TestProcs;  
Go  
```  
  
## <a name="see-also"></a><span data-ttu-id="7918b-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="7918b-134">See Also</span></span>  
 [<span data-ttu-id="7918b-135">Интеграция со средой CLR и транзакции</span><span class="sxs-lookup"><span data-stu-id="7918b-135">CLR Integration and Transactions</span></span>](../native-client-ole-db-transactions/transactions.md)  
  
  
