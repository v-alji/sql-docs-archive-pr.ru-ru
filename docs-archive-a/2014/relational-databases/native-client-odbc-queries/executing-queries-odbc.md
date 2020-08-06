---
title: Исполнение запросов (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC applications, executing queries
- SQL Server Native Client ODBC driver, statements
- ODBC applications, statements
- SQL Server Native Client ODBC driver, queries
- queries [ODBC]
ms.assetid: d935bcba-8ce6-4159-8395-6c86431602ad
author: rothja
ms.author: jroth
ms.openlocfilehash: adc51186803148056401f58f1207d3e9a7abf9c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655129"
---
# <a name="executing-queries-odbc"></a><span data-ttu-id="f10d3-102">Выполнение запросов (ODBC)</span><span class="sxs-lookup"><span data-stu-id="f10d3-102">Executing Queries (ODBC)</span></span>
  <span data-ttu-id="f10d3-103">После того, как приложение ODBC инициализирует дескриптор соединения и подключается к источнику данных, оно выделяет один или несколько дескрипторов инструкций на дескриптор соединения.</span><span class="sxs-lookup"><span data-stu-id="f10d3-103">After an ODBC application initializes a connection handle and connects with a data source, it allocates one or more statement handles on the connection handle.</span></span> <span data-ttu-id="f10d3-104">Приложение может затем выполнять [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] инструкции в обработчике инструкций.</span><span class="sxs-lookup"><span data-stu-id="f10d3-104">The application can then execute [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] statements on the statement handle.</span></span> <span data-ttu-id="f10d3-105">Общая последовательность событий при выполнении инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="f10d3-105">The general sequence of events in executing an SQL statement is:</span></span>  
  
1.  <span data-ttu-id="f10d3-106">Установите необходимые атрибуты инструкции.</span><span class="sxs-lookup"><span data-stu-id="f10d3-106">Set any required statement attributes.</span></span>  
  
2.  <span data-ttu-id="f10d3-107">Сформируйте инструкцию.</span><span class="sxs-lookup"><span data-stu-id="f10d3-107">Construct the statement.</span></span>  
  
3.  <span data-ttu-id="f10d3-108">Выполните инструкцию.</span><span class="sxs-lookup"><span data-stu-id="f10d3-108">Execute the statement.</span></span>  
  
4.  <span data-ttu-id="f10d3-109">Получите результирующие наборы.</span><span class="sxs-lookup"><span data-stu-id="f10d3-109">Retrieve any result sets.</span></span>  
  
 <span data-ttu-id="f10d3-110">После того, как приложение получит все строки во всех результирующих наборах, возвращенных инструкцией SQL, оно может выполнить другой запрос на том же дескрипторе инструкции.</span><span class="sxs-lookup"><span data-stu-id="f10d3-110">After an application retrieves all the rows in all of the result sets returned by the SQL statement, it can execute another query on the same statement handle.</span></span> <span data-ttu-id="f10d3-111">Если приложение определяет, что не требуется извлекать все строки в определенном результирующем наборе, он может отменить оставшуюся часть результирующего набора, вызвав либо [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) , либо [SQLCloseCursor](../native-client-odbc-api/sqlclosecursor.md).</span><span class="sxs-lookup"><span data-stu-id="f10d3-111">If an application determines that it is not required to retrieve all the rows in a particular result set, it can cancel the rest of the result set by calling either [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) or [SQLCloseCursor](../native-client-odbc-api/sqlclosecursor.md).</span></span>  
  
 <span data-ttu-id="f10d3-112">Если в приложении ODBC необходимо несколько раз выполнить одну инструкцию SQL с различными данными, используйте маркер параметра, обозначенный вопросительным знаком (?) при построении инструкции SQL:</span><span class="sxs-lookup"><span data-stu-id="f10d3-112">If, in an ODBC application, you must execute the same SQL statement multiple times with different data, use a parameter marker denoted by a question mark (?) in the construction of an SQL statement:</span></span>  
  
```  
INSERT INTO MyTable VALUES (?, ?, ?)  
```  
  
 <span data-ttu-id="f10d3-113">Затем каждый маркер параметра может быть привязан к программной переменной путем вызова [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md).</span><span class="sxs-lookup"><span data-stu-id="f10d3-113">Each parameter marker can then be bound to a program variable by calling [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md).</span></span>  
  
 <span data-ttu-id="f10d3-114">После того, как будут вызваны все инструкции SQL и обработаны их результирующие наборы, приложение освобождает дескриптор инструкции.</span><span class="sxs-lookup"><span data-stu-id="f10d3-114">After all SQL statements execute and their result sets process, the application frees the statement handle.</span></span>  
  
 <span data-ttu-id="f10d3-115">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Драйвер ODBC для собственного клиента поддерживает несколько дескрипторов инструкций для каждого дескриптора соединения.</span><span class="sxs-lookup"><span data-stu-id="f10d3-115">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports multiple statement handles per connection handle.</span></span> <span data-ttu-id="f10d3-116">Управление транзакциями осуществляется на уровне соединения, поэтому вся работа, выполняемая со всеми дескрипторами инструкций на одном дескрипторе соединения, управляется как часть одной транзакции.</span><span class="sxs-lookup"><span data-stu-id="f10d3-116">Transactions are managed at the connection level, so that all work performed on all statement handles on a single connection handle are managed as part of the same transaction.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f10d3-117">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="f10d3-117">In This Section</span></span>  
  
-   [<span data-ttu-id="f10d3-118">Выделение дескриптора инструкции</span><span class="sxs-lookup"><span data-stu-id="f10d3-118">Allocating a Statement Handle</span></span>](allocating-a-statement-handle.md)  
  
-   [<span data-ttu-id="f10d3-119">Создание инструкции SQL &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="f10d3-119">Constructing an SQL Statement &#40;ODBC&#41;</span></span>](constructing-an-sql-statement-odbc.md)  
  
-   [<span data-ttu-id="f10d3-120">Конструирование инструкций SQL для курсоров</span><span class="sxs-lookup"><span data-stu-id="f10d3-120">Constructing SQL Statements for Cursors</span></span>](constructing-sql-statements-for-cursors.md)  
  
-   [<span data-ttu-id="f10d3-121">Использование параметров инструкции</span><span class="sxs-lookup"><span data-stu-id="f10d3-121">Using Statement Parameters</span></span>](using-statement-parameters.md)  
  
-   [<span data-ttu-id="f10d3-122">Исполнение инструкций &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="f10d3-122">Executing Statements &#40;ODBC&#41;</span></span>](executing-statements/executing-statements-odbc.md)  
  
-   [<span data-ttu-id="f10d3-123">Освобождение дескриптора инструкции</span><span class="sxs-lookup"><span data-stu-id="f10d3-123">Freeing a Statement Handle</span></span>](freeing-a-statement-handle.md)  
  
## <a name="see-also"></a><span data-ttu-id="f10d3-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="f10d3-124">See Also</span></span>  
 [<span data-ttu-id="f10d3-125">SQL Server Native Client (ODBC)</span><span class="sxs-lookup"><span data-stu-id="f10d3-125">SQL Server Native Client &#40;ODBC&#41;</span></span>](../native-client/odbc/sql-server-native-client-odbc.md)  
  
  
