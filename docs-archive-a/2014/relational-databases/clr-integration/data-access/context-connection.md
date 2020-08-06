---
title: Контекстное соединение | Документация Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- context connections [CLR integration]
- database objects [CLR integration], connections
- connections [CLR integration]
- context [CLR integration]
ms.assetid: 67dd1925-d672-4986-a85f-bce4fe832ef7
author: rothja
ms.author: jroth
ms.openlocfilehash: 82c739aa9c1952c71e9a16aaa68ec999851b3202
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658832"
---
# <a name="context-connection"></a><span data-ttu-id="95195-102">Контекстное соединение</span><span class="sxs-lookup"><span data-stu-id="95195-102">Context Connection</span></span>
  <span data-ttu-id="95195-103">Проблема внутреннего доступа к данным встречается довольно часто.</span><span class="sxs-lookup"><span data-stu-id="95195-103">The problem of internal data access is a fairly common scenario.</span></span> <span data-ttu-id="95195-104">Речь идет о тех ситуациях, когда необходимо получить доступ к тому же серверу, на котором выполняется конкретная хранимая процедура или функция среды CLR.</span><span class="sxs-lookup"><span data-stu-id="95195-104">That is, you wish to access the same server on which your common language runtime (CLR) stored procedure or function is executing.</span></span> <span data-ttu-id="95195-105">Один из вариантов состоит в том, чтобы создать соединение с использованием `System.Data.SqlClient.SqlConnection`, задать строку соединения, в которой указан локальный сервер, и открыть соединение.</span><span class="sxs-lookup"><span data-stu-id="95195-105">One option is to create a connection using `System.Data.SqlClient.SqlConnection`, specify a connection string that points to the local server, and open the connection.</span></span> <span data-ttu-id="95195-106">В этом случае требуется указать учетные данные для входа в систему.</span><span class="sxs-lookup"><span data-stu-id="95195-106">This requires specifying credentials for logging in.</span></span> <span data-ttu-id="95195-107">Кроме того, соединение устанавливается в другом сеансе базы данных, отличном от сеанса хранимой процедуры или функции, поэтому оно может иметь другие параметры `SET`, находится в отдельной транзакции, не позволяет обращаться к используемым временным таблицам и т. д.</span><span class="sxs-lookup"><span data-stu-id="95195-107">The connection is in a different database session than the stored procedure or function, it may have different `SET` options, it is in a separate transaction, it does not see your temporary tables, and so on.</span></span> <span data-ttu-id="95195-108">Если управляемая хранимая процедура или функция выполняется в процессе SQL Server, причина этого состоит в том, что кто-то соединился с этим сервером и выполнил инструкцию SQL для вызова соответствующего процедуры или функции.</span><span class="sxs-lookup"><span data-stu-id="95195-108">If your managed stored procedure or function code is executing in the SQL Server process, it is because someone connected to that server and executed a SQL statement to invoke it.</span></span> <span data-ttu-id="95195-109">В этой ситуации наверняка следует обеспечить выполнение хранимой процедуры или функции в контексте данного соединения вместе с осуществляемыми в нем транзакцией, параметрами `SET` и т. д.</span><span class="sxs-lookup"><span data-stu-id="95195-109">You probably want the stored procedure or function to execute in the context of that connection, along with its transaction, `SET` options, and so on.</span></span> <span data-ttu-id="95195-110">В этом состоит так называемое контекстное соединение.</span><span class="sxs-lookup"><span data-stu-id="95195-110">This is called the context connection.</span></span>  
  
 <span data-ttu-id="95195-111">Контекстное соединение позволяет выполнять инструкции Transact-SQL в том же контексте, в каком первоначально был вызван конкретный код.</span><span class="sxs-lookup"><span data-stu-id="95195-111">The context connection lets you execute Transact-SQL statements in the same context that your code was invoked in the first place.</span></span> <span data-ttu-id="95195-112">Для получения контекстного соединения необходимо использовать ключевое слово «context connection» строки соединения, как в примере ниже:</span><span class="sxs-lookup"><span data-stu-id="95195-112">In order to obtain the context connection, you must use the "context connection" connection string keyword, as in the example below:</span></span>  
  
 <span data-ttu-id="95195-113">[C#]</span><span class="sxs-lookup"><span data-stu-id="95195-113">[C#]</span></span>  
  
```  
using(SqlConnection connection = new SqlConnection("context connection=true"))   
{  
    connection.Open();  
    // Use the connection  
}  
```  
  
 <span data-ttu-id="95195-114">[Visual Basic]</span><span class="sxs-lookup"><span data-stu-id="95195-114">[Visual Basic]</span></span>  
  
```  
Using connection as new SqlConnection("context connection=true")  
    connection.Open()  
    ' Use the connection  
End Using  
  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="95195-115">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="95195-115">In This Section</span></span>  
 [<span data-ttu-id="95195-116">Обычные и Контекстные соединения</span><span class="sxs-lookup"><span data-stu-id="95195-116">Regular vs. Context Connections</span></span>](context-connections-vs-regular-connections.md)  
 <span data-ttu-id="95195-117">Описывает разницу между регулярными и контекстными соединениями.</span><span class="sxs-lookup"><span data-stu-id="95195-117">Describes the differences between regular and context connections.</span></span>  
  
 [<span data-ttu-id="95195-118">Ограничения обычных и контекстных соединений</span><span class="sxs-lookup"><span data-stu-id="95195-118">Restrictions on Regular and Context Connections</span></span>](context-connections-and-regular-connections-restrictions.md)  
 <span data-ttu-id="95195-119">Описывает ограничения регулярных и контекстных соединений.</span><span class="sxs-lookup"><span data-stu-id="95195-119">Describes the restrictions on regular and context connections.</span></span>  
  
  
