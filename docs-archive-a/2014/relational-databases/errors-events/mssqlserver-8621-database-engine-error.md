---
title: MSSQLSERVER_8621 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8621 (Database Engine error)
ms.assetid: 67f59865-becd-4999-8bb0-90aedd7effbf
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 48c36cf936475e3deea37a172c7dc59f88d0a31a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666076"
---
# <a name="mssqlserver_8621"></a><span data-ttu-id="53ffc-102">MSSQLSERVER_8621</span><span class="sxs-lookup"><span data-stu-id="53ffc-102">MSSQLSERVER_8621</span></span>
    
## <a name="details"></a><span data-ttu-id="53ffc-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="53ffc-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="53ffc-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="53ffc-104">Product Name</span></span>|<span data-ttu-id="53ffc-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="53ffc-105">SQL Server</span></span>|  
|<span data-ttu-id="53ffc-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="53ffc-106">Event ID</span></span>|<span data-ttu-id="53ffc-107">8621</span><span class="sxs-lookup"><span data-stu-id="53ffc-107">8621</span></span>|  
|<span data-ttu-id="53ffc-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="53ffc-108">Event Source</span></span>|<span data-ttu-id="53ffc-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="53ffc-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="53ffc-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="53ffc-110">Component</span></span>|<span data-ttu-id="53ffc-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="53ffc-111">SQLEngine</span></span>|  
|<span data-ttu-id="53ffc-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="53ffc-112">Symbolic Name</span></span>|<span data-ttu-id="53ffc-113">OPTIMIZER_STACK_OVERFLOW_ERR</span><span class="sxs-lookup"><span data-stu-id="53ffc-113">OPTIMIZER_STACK_OVERFLOW_ERR</span></span>|  
|<span data-ttu-id="53ffc-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="53ffc-114">Message Text</span></span>|<span data-ttu-id="53ffc-115">При оптимизации запроса обработчик запросов исчерпал пространство стека.</span><span class="sxs-lookup"><span data-stu-id="53ffc-115">The query processor ran out of stack space during query optimization.</span></span> <span data-ttu-id="53ffc-116">Упростите запрос.</span><span class="sxs-lookup"><span data-stu-id="53ffc-116">Please simplify the query.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="53ffc-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="53ffc-117">Explanation</span></span>  
 <span data-ttu-id="53ffc-118">Наиболее вероятной причиной ошибки является размер расширенного запроса.</span><span class="sxs-lookup"><span data-stu-id="53ffc-118">The size of the expanded query is the most likely cause of the error.</span></span> <span data-ttu-id="53ffc-119">Расширенный запрос получается при подстановке в основной запрос определений каждого из представлений, вычисляемых столбцов, функций [!INCLUDE[tsql](../../includes/tsql-md.md)] и обобщенных табличных выражений, на которые он ссылается, а также каскадных действий, таких как обновление вторичных индексов, представлений и триггеров.</span><span class="sxs-lookup"><span data-stu-id="53ffc-119">The expanded query substitutes into the original query the definitions of each of the views, computed columns, [!INCLUDE[tsql](../../includes/tsql-md.md)] functions, and common table expressions it references, as well as cascading actions like updating secondary indexes, views, and triggers.</span></span>  
  
 <span data-ttu-id="53ffc-120">Наиболее вероятно, что размер запроса велик по определенным измерениям, например числу таблиц, на которые ссылаются определения представления, или очень большому скалярному выражению.</span><span class="sxs-lookup"><span data-stu-id="53ffc-120">Most likely the query is large in some dimension; for example, the number of tables referenced by view definitions, or a very large scalar expression.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="53ffc-121">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="53ffc-121">User Action</span></span>  
 <span data-ttu-id="53ffc-122">Упростите запрос, разбив его на несколько запросов по наибольшему измерению.</span><span class="sxs-lookup"><span data-stu-id="53ffc-122">Simplify the query by breaking the query into multiple queries along the largest dimension.</span></span> <span data-ttu-id="53ffc-123">Первым делом удалите все необязательные элементы запроса, затем попытайтесь добавить временную таблицу и разбить запрос на две части.</span><span class="sxs-lookup"><span data-stu-id="53ffc-123">First remove any query elements that are not really necessary, then try adding a temp table and splitting the query in two.</span></span>  <span data-ttu-id="53ffc-124">Простого выделения части запроса во вложенный запрос, функцию или обобщенное табличное выражение недостаточно, поскольку они будут объединены компилятором [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="53ffc-124">Merely moving a part of the query to a subquery, function, or common table expression is insufficient because they get recombined by the [!INCLUDE[tsql](../../includes/tsql-md.md)] compiler.</span></span>  
  
  
