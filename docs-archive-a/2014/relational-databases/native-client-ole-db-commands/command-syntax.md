---
title: Синтаксис команд | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, commands
- commands [OLE DB]
- SQL Server Native Client OLE DB provider, stored procedures
- stored procedures [OLE DB], command syntax
ms.assetid: d463d3d7-e5cb-426d-8e92-aa29980356b6
author: rothja
ms.author: jroth
ms.openlocfilehash: da5ddb75a5c6fc10db031707b7d97ead71363e9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750807"
---
# <a name="command-syntax"></a><span data-ttu-id="f2d6c-102">Синтаксис команды</span><span class="sxs-lookup"><span data-stu-id="f2d6c-102">Command Syntax</span></span>
  <span data-ttu-id="f2d6c-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента распознает синтаксис команд, указанный в макросе DBGUID_SQL.</span><span class="sxs-lookup"><span data-stu-id="f2d6c-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider recognizes command syntax specified by the DBGUID_SQL macro.</span></span> <span data-ttu-id="f2d6c-104">Для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщика OLE DB собственного клиента описатель указывает, что АМАЛГАМ ODBC SQL, ISO и [!INCLUDE[tsql](../../includes/tsql-md.md)] является допустимым синтаксисом.</span><span class="sxs-lookup"><span data-stu-id="f2d6c-104">For the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the specifier indicates that an amalgam of ODBC SQL, ISO, and [!INCLUDE[tsql](../../includes/tsql-md.md)] is valid syntax.</span></span> <span data-ttu-id="f2d6c-105">Например, следующая инструкция SQL использует escape-последовательность ODBC SQL, чтобы указать строковую функцию LCASE.</span><span class="sxs-lookup"><span data-stu-id="f2d6c-105">For example, the following SQL statement uses an ODBC SQL escape sequence to specify the LCASE string function:</span></span>  
  
```  
SELECT customerid={fn LCASE(CustomerID)} FROM Customers  
```  
  
 <span data-ttu-id="f2d6c-106">Функция LCASE возвращает строковое выражение, в котором все символы приведены к нижнему регистру.</span><span class="sxs-lookup"><span data-stu-id="f2d6c-106">LCASE returns a character string, converting all uppercase characters to their lowercase equivalents.</span></span> <span data-ttu-id="f2d6c-107">Строковая функция LOWER стандарта ISO выполняет ту же операцию, поэтому следующая инструкция SQL является эквивалентом ISO для представленной выше инструкции ODBC.</span><span class="sxs-lookup"><span data-stu-id="f2d6c-107">The ISO string function LOWER performs the same operation, so the following SQL statement is a ISO equivalent to the ODBC statement presented above:</span></span>  
  
```  
SELECT customerid=LOWER(CustomerID) FROM Customers  
```  
  
 <span data-ttu-id="f2d6c-108">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента обрабатывает любую форму инструкции, если она указана как текст для команды.</span><span class="sxs-lookup"><span data-stu-id="f2d6c-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider processes either form of the statement successfully when specified as text for a command.</span></span>  
  
## <a name="stored-procedures"></a><span data-ttu-id="f2d6c-109">Хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="f2d6c-109">Stored Procedures</span></span>  
 <span data-ttu-id="f2d6c-110">При выполнении [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] хранимой процедуры с помощью [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] команды поставщика OLE DB Native Client используйте escape-последовательность ODBC CALL в тексте команды.</span><span class="sxs-lookup"><span data-stu-id="f2d6c-110">When executing a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedure using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider command, use the ODBC CALL escape sequence in the command text.</span></span> <span data-ttu-id="f2d6c-111">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента использует механизм удаленного вызова процедур [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для оптимизации обработки команд.</span><span class="sxs-lookup"><span data-stu-id="f2d6c-111">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider then uses the remote procedure call mechanism of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to optimize command processing.</span></span> <span data-ttu-id="f2d6c-112">Например, следующая инструкция ODBC SQL является более предпочтительным текстом команды, нежели форма [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2d6c-112">For example, the following ODBC SQL statement is preferred command text over the [!INCLUDE[tsql](../../includes/tsql-md.md)] form:</span></span>  
  
-   <span data-ttu-id="f2d6c-113">ODBC SQL</span><span class="sxs-lookup"><span data-stu-id="f2d6c-113">ODBC SQL</span></span>  
  
    ```  
    {call SalesByCategory('Produce', '1995')}  
    ```  
  
-   <span data-ttu-id="f2d6c-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f2d6c-114">Transact-SQL</span></span>  
  
    ```  
    EXECUTE SalesByCategory 'Produce', '1995'  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f2d6c-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="f2d6c-115">See Also</span></span>  
 [<span data-ttu-id="f2d6c-116">Команды</span><span class="sxs-lookup"><span data-stu-id="f2d6c-116">Commands</span></span>](commands.md)  
  
  
