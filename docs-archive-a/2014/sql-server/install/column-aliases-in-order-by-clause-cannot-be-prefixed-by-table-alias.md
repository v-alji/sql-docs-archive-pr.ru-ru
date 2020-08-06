---
title: Псевдонимы столбцов в предложении ORDER BY не могут предваряться псевдонимом таблицы | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- aliases [SQL Server], columns
ms.assetid: fee7328f-6e8d-4005-930b-56fb6f17e0b2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 44333d778753a2f8761d32d181681b798e3bc409
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659207"
---
# <a name="column-aliases-in-order-by-clause-cannot-be-prefixed-by-table-alias"></a><span data-ttu-id="4e9e6-102">Псевдонимы столбцов в предложении ORDER BY не могут предваряться псевдонимом таблицы</span><span class="sxs-lookup"><span data-stu-id="4e9e6-102">Column aliases in ORDER BY clause cannot be prefixed by table alias</span></span>
  <span data-ttu-id="4e9e6-103">В [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] и более поздних версиях псевдонимы столбцов в предложении ORDER BY не должны предваряться псевдонимами таблицы.</span><span class="sxs-lookup"><span data-stu-id="4e9e6-103">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later, column aliases in the ORDER BY clause cannot be prefixed by the table alias.</span></span>  
  
## <a name="component"></a><span data-ttu-id="4e9e6-104">Компонент</span><span class="sxs-lookup"><span data-stu-id="4e9e6-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="4e9e6-105">Описание</span><span class="sxs-lookup"><span data-stu-id="4e9e6-105">Description</span></span>  
 <span data-ttu-id="4e9e6-106">Например, следующий запрос успешно выполняется в [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], но в [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="4e9e6-106">For example, the following query executes in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], but returns an error in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT FirstName AS f, LastName AS l  
FROM Person.Contact p  
ORDER BY p.l  
```  
  
 <span data-ttu-id="4e9e6-107">Компонент [!INCLUDE[ssDEversion10](../../includes/ssdeversion10-md.md)] не сопоставляет `p.l` в предложении `ORDER BY` допустимому столбцу в таблице.</span><span class="sxs-lookup"><span data-stu-id="4e9e6-107">The [!INCLUDE[ssDEversion10](../../includes/ssdeversion10-md.md)] does not match `p.l` in the `ORDER BY` clause to a valid column in the table.</span></span>  
  
### <a name="exception"></a><span data-ttu-id="4e9e6-108">Исключение</span><span class="sxs-lookup"><span data-stu-id="4e9e6-108">Exception</span></span>  
 <span data-ttu-id="4e9e6-109">Если псевдоним таблицы с префиксом, заданный предложением ORDER BY, представляет собой допустимое имя столбца в указанной таблице, то запрос выполняется без ошибки; в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] семантика инструкции может быть иной.</span><span class="sxs-lookup"><span data-stu-id="4e9e6-109">If the prefixed column alias that is specified in the ORDER BY clause is a valid column name in the specified table, the query executes without error; in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], the semantics of the statement might be different.</span></span> <span data-ttu-id="4e9e6-110">Например, псевдоним столбца (`id`), заданный в следующей инструкции, представляет собой допустимое имя столбца в таблице `sysobjects`.</span><span class="sxs-lookup"><span data-stu-id="4e9e6-110">For example, the column alias (`id`) specified in the following statement is a valid column name in the `sysobjects` table.</span></span> <span data-ttu-id="4e9e6-111">При выполнении инструкции в [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], операция `CAST` выполняется после сортировки результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="4e9e6-111">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], when the statement executes, the `CAST` operation is performed after the result set is sorted.</span></span> <span data-ttu-id="4e9e6-112">Это значит, что столбец `name` используется в операции сортировки.</span><span class="sxs-lookup"><span data-stu-id="4e9e6-112">This means the `name` column is used in the sort operation.</span></span> <span data-ttu-id="4e9e6-113">В [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] операция `CAST` выполняется перед операцией сортировки.</span><span class="sxs-lookup"><span data-stu-id="4e9e6-113">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], the `CAST` operation occurs before the sort operation.</span></span> <span data-ttu-id="4e9e6-114">Это означает, что столбец `id` в таблице используется в операции сортировки и возвращает результирующий набор в непредвиденном порядке.</span><span class="sxs-lookup"><span data-stu-id="4e9e6-114">This means the `id` column in the table is used in the sort operation and returns the result set in an unexpected order.</span></span>  
  
```  
SELECT CAST (o.name AS char(128)) AS id  
FROM sysobjects AS o  
ORDER BY o.id;  
```  
  
## <a name="corrective-action"></a><span data-ttu-id="4e9e6-115">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="4e9e6-115">Corrective Action</span></span>  
 <span data-ttu-id="4e9e6-116">Измените запросы, которые используют псевдонимы столбцов, предваряемые псевдонимами таблиц в предложении ORDER BY, одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="4e9e6-116">Modify queries that use column aliases prefixed by table aliases in the ORDER BY clause in either of the following ways:</span></span>  
  
-   <span data-ttu-id="4e9e6-117">При возможности не указывайте префикс перед псевдонимом столбца в предложении ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="4e9e6-117">Do not prefix the column alias in the ORDER BY clause, if possible.</span></span>  
  
-   <span data-ttu-id="4e9e6-118">Замените псевдоним столбца именем столбца.</span><span class="sxs-lookup"><span data-stu-id="4e9e6-118">Replace the column alias with the column name.</span></span>  
  
 <span data-ttu-id="4e9e6-119">Например, оба следующих запроса выполняются без ошибки в [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e9e6-119">For example, both of the following queries execute without error in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT FirstName AS f, LastName AS l  
FROM Person.Contact p  
ORDER BY l  
  
USE AdventureWorks2012;  
GO  
SELECT FirstName AS f, LastName AS l  
FROM Person.Contact p  
ORDER BY p.LastName  
```  
  
## <a name="see-also"></a><span data-ttu-id="4e9e6-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="4e9e6-120">See Also</span></span>  
 <span data-ttu-id="4e9e6-121">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="4e9e6-121">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="4e9e6-122">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="4e9e6-122">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
