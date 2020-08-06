---
title: Запросы FOR XML AUTO возвращают ссылки на производные таблицы в режиме совместимости 90 или более поздней версии | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- FOR XML AUTO [SQL Server]
ms.assetid: 10c32f06-f7e1-40e0-8f79-6d921f2bef1d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 702cb2ca1d437dff03cee09c98d72082500709d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669265"
---
# <a name="for-xml-auto-queries-return-derived-table-references-in-90-or-later-compatibility-modes"></a><span data-ttu-id="04f03-102">Запросы в режиме FOR XML AUTO возвращают ссылки на производные таблицы в режиме совместимости 90 и выше</span><span class="sxs-lookup"><span data-stu-id="04f03-102">FOR XML AUTO queries return derived table references in 90 or later compatibility modes</span></span>
  <span data-ttu-id="04f03-103">В режиме совместимости базы данных 90 и выше запросы FOR XML, выполняемые в режиме AUTO, возвращают ссылки на псевдонимы производных таблиц.</span><span class="sxs-lookup"><span data-stu-id="04f03-103">When the database compatibility level is set to 90 or later, FOR XML queries that execute in AUTO mode return references to derived table aliases.</span></span> <span data-ttu-id="04f03-104">В режиме совместимости базы данных 80 запросы FOR XML AUTO возвращают ссылки на базовые таблицы, определяющие производную таблицу.</span><span class="sxs-lookup"><span data-stu-id="04f03-104">When the compatibility level is set to 80, FOR XML AUTO queries return references to the base tables that define a derived table.</span></span>  
  
## <a name="component"></a><span data-ttu-id="04f03-105">Компонент</span><span class="sxs-lookup"><span data-stu-id="04f03-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="04f03-106">Описание</span><span class="sxs-lookup"><span data-stu-id="04f03-106">Description</span></span>  
 <span data-ttu-id="04f03-107">Например, рассмотрим следующую таблицу.</span><span class="sxs-lookup"><span data-stu-id="04f03-107">For example, consider the following table:</span></span>  
  
```  
CREATE TABLE Test(id int);  
INSERT INTO Test VALUES(1);  
INSERT INTO Test VALUES(2);  
```  
  
 <span data-ttu-id="04f03-108">Следующий запрос, содержащий производную таблицу, при уровнях совместимости 80, 90 и выше вернет разные результаты.</span><span class="sxs-lookup"><span data-stu-id="04f03-108">The following query, which includes a derived table, produces different results under compatibility levels 80, 90, or later:</span></span>  
  
```  
SELECT * FROM   
   (SELECT a.id AS a, b.id AS b   
    FROM Test a JOIN Test b ON a.id=b.id)  
AS DerivedTest   
FOR XML AUTO;  
```  
  
 <span data-ttu-id="04f03-109">При уровне совместимости 80 запрос возвращает следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="04f03-109">Under compatibility level 80, the query returns the following results.</span></span> <span data-ttu-id="04f03-110">Результат содержит ссылки на псевдонимы базовой таблицы `a` и `b` производной таблицы, а не на псевдоним производной таблицы.</span><span class="sxs-lookup"><span data-stu-id="04f03-110">The results reference the base table aliases `a` and `b` of the derived table instead of the derived table alias.</span></span>  
  
```  
<a a="1"><b b="1"/></a><a a="2"><b b="2"/></a>  
```  
  
 <span data-ttu-id="04f03-111">При уровне совместимости 90 и выше запрос возвращает ссылки на псевдоним производной таблицы `DerivedTest`, а не на базовую таблицу.</span><span class="sxs-lookup"><span data-stu-id="04f03-111">Under compatibility level 90 or later, the query returns references to the derived table alias `DerivedTest` instead of to the derived table's base tables.</span></span>  
  
```  
<DerivedTest a="1" b="1"/><DerivedTest a="2" b="2"/>  
```  
  
## <a name="corrective-action"></a><span data-ttu-id="04f03-112">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="04f03-112">Corrective Action</span></span>  
 <span data-ttu-id="04f03-113">Внесите в приложения необходимые изменения, чтобы учесть изменения в результатах запросов FOR XML AUTO, содержащих производные таблицы и выполняемых на уровне совместимости 90 и выше.</span><span class="sxs-lookup"><span data-stu-id="04f03-113">Modify your application as required to account for the changes in results of FOR XML AUTO queries that include derived tables and that run under compatibility level 90 or later.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04f03-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="04f03-114">See Also</span></span>  
 <span data-ttu-id="04f03-115">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="04f03-115">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="04f03-116">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="04f03-116">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
