---
title: Определение таблиц и столбцов определяемого пользователем типа | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
helpviewer_keywords:
- user-defined types [CLR integration], columns
- UDTs [CLR integration], columns
- columns [CLR integration]
- user-defined types [CLR integration], tables
- tables [CLR integration]
- UDTs [CLR integration], tables
- UDTs [CLR integration], indexes
- user-defined types [CLR integration], indexes
- indexes [CLR integration]
ms.assetid: aea495f4-ce26-4952-b019-38f012625f3f
author: rothja
ms.author: jroth
ms.openlocfilehash: aa9596629ed8b4877b1793fa0c56956c52989499
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669430"
---
# <a name="defining-udt-tables-and-columns"></a><span data-ttu-id="676d4-102">Определение таблиц и столбцов определяемых пользователем типов</span><span class="sxs-lookup"><span data-stu-id="676d4-102">Defining UDT Tables and Columns</span></span>
  <span data-ttu-id="676d4-103">После регистрации в базе данных сборки, содержащей определение определяемого пользователем типа (UDT) [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ее можно использовать в определении столбца.</span><span class="sxs-lookup"><span data-stu-id="676d4-103">Once the assembly containing the user-defined type (UDT) definition has been registered in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, it can be used in a column definition.</span></span>  
  
## <a name="creating-tables-with-udts"></a><span data-ttu-id="676d4-104">Создание таблиц с использованием определяемых пользователем типов</span><span class="sxs-lookup"><span data-stu-id="676d4-104">Creating Tables with UDTs</span></span>  
 <span data-ttu-id="676d4-105">Не существует специального синтаксиса для создания в таблице столбца определяемого пользователем типа.</span><span class="sxs-lookup"><span data-stu-id="676d4-105">There is no special syntax for creating a UDT column in a table.</span></span> <span data-ttu-id="676d4-106">Можно использовать в определении столбца имя определяемого пользователем типа, как если бы он был одним из внутренних типов данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="676d4-106">You can use the name of the UDT in a column definition as though it were one of the intrinsic [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types.</span></span> <span data-ttu-id="676d4-107">Следующая инструкция CREATE TABLE [!INCLUDE[tsql](../../includes/tsql-md.md)] создает таблицу с именем **points**и столбцом с именем **ID,** который определен как `int` столбец идентификаторов и является первичным ключом для таблицы.</span><span class="sxs-lookup"><span data-stu-id="676d4-107">The following CREATE TABLE [!INCLUDE[tsql](../../includes/tsql-md.md)] statement creates a table named **Points**, with a column named **ID,** which is defined as an `int` identity column and \ the primary key for the table.</span></span> <span data-ttu-id="676d4-108">Второй столбец называется **PointValue**и имеет тип данных **Point**.</span><span class="sxs-lookup"><span data-stu-id="676d4-108">The second column is named **PointValue**, with a data type of **Point**.</span></span> <span data-ttu-id="676d4-109">В этом примере используется имя схемы **dbo**.</span><span class="sxs-lookup"><span data-stu-id="676d4-109">The schema name used in this example is **dbo**.</span></span> <span data-ttu-id="676d4-110">Обратите внимание, что требуется иметь соответствующие разрешения на указание имени схемы.</span><span class="sxs-lookup"><span data-stu-id="676d4-110">Note that you must have the necessary permissions to specify a schema name.</span></span> <span data-ttu-id="676d4-111">Если имя схемы опущено, используется схема по умолчанию для пользователя базы данных.</span><span class="sxs-lookup"><span data-stu-id="676d4-111">If you omit the schema name, the default schema for the database user is used.</span></span>  
  
```  
CREATE TABLE dbo.Points   
(ID int IDENTITY(1,1) PRIMARY KEY, PointValue Point)  
```  
  
## <a name="creating-indexes-on-udt-columns"></a><span data-ttu-id="676d4-112">Создание индексов по столбцам определяемых пользователем типов</span><span class="sxs-lookup"><span data-stu-id="676d4-112">Creating Indexes on UDT Columns</span></span>  
 <span data-ttu-id="676d4-113">Существует два параметра для индексирования столбца определяемого пользователем типа:</span><span class="sxs-lookup"><span data-stu-id="676d4-113">There are two options for indexing a UDT column:</span></span>  
  
-   <span data-ttu-id="676d4-114">Индекс полного значения.</span><span class="sxs-lookup"><span data-stu-id="676d4-114">Index the full value.</span></span> <span data-ttu-id="676d4-115">В этом случае, если определяемый пользователем тип поддерживает двоичный режим упорядочивания, можно создать индекс для всего столбца определяемого пользователем типа при помощи инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE INDEX.</span><span class="sxs-lookup"><span data-stu-id="676d4-115">In this case, if the UDT is binary ordered, you can create an index over the entire UDT column by using the CREATE INDEX [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
-   <span data-ttu-id="676d4-116">Индекс выражений определяемого пользователем типа.</span><span class="sxs-lookup"><span data-stu-id="676d4-116">Index UDT expressions.</span></span> <span data-ttu-id="676d4-117">Можно создать индексы материализованных вычисляемых столбцов при помощи выражений определяемого пользователем типа.</span><span class="sxs-lookup"><span data-stu-id="676d4-117">You can create indexes on persisted computed columns over UDT expressions.</span></span> <span data-ttu-id="676d4-118">Выражение определяемого пользователем типа может быть полем, методом или свойством определяемого пользователем типа.</span><span class="sxs-lookup"><span data-stu-id="676d4-118">The UDT expression can be a field, method, or property of a UDT.</span></span> <span data-ttu-id="676d4-119">Выражение должно быть детерминированным и не осуществлять доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="676d4-119">The expression must be deterministic and must not perform data access.</span></span>  
  
 <span data-ttu-id="676d4-120">Дополнительные сведения см. в статьях [определяемые пользователем типы данных CLR](clr-user-defined-types.md) и [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="676d4-120">For more information, see [CLR User-Defined Types](clr-user-defined-types.md) and [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="676d4-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="676d4-121">See Also</span></span>  
 [<span data-ttu-id="676d4-122">Работа с определяемыми пользователем типами в SQL Server</span><span class="sxs-lookup"><span data-stu-id="676d4-122">Working with User-Defined Types in SQL Server</span></span>](working-with-user-defined-types-in-sql-server.md)  
  
  
