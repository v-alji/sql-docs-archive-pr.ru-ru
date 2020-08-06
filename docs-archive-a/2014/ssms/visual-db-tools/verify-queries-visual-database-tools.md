---
title: Проверка запросов (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:100644
helpviewer_keywords:
- verifying queries
- queries [SQL Server], verifying
- checking queries
ms.assetid: 1382c0c0-46dc-45f9-ab38-9bba1d347eea
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7bf24de9bdc0e8b7b7ceb33bb881812b180ce112
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665181"
---
# <a name="verify-queries-visual-database-tools"></a><span data-ttu-id="45a4f-102">Проверка запросов (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="45a4f-102">Verify Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="45a4f-103">Чтобы избежать проблем, можно проверить созданный запрос, чтобы гарантировать правильность его синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="45a4f-103">To avoid problems, you can check the query you have built to ensure its syntax is correct.</span></span> <span data-ttu-id="45a4f-104">Эта возможность особенно полезна при вводе инструкций на [панели SQL](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="45a4f-104">This option is especially useful when you enter statements in the [SQL pane](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="45a4f-105">Некоторые особенности, которые нужно иметь в виду при проверке запросов:</span><span class="sxs-lookup"><span data-stu-id="45a4f-105">Some notes to keep in mind about verifying queries:</span></span>  
  
-   <span data-ttu-id="45a4f-106">Инструкция может быть правильной, и поэтому успешно проверяться, даже если она не может быть представлена на **панели диаграммы** и **панели критериев**.</span><span class="sxs-lookup"><span data-stu-id="45a4f-106">A statement can be valid, and therefore be verified successfully, even if it cannot be represented in the **Diagram Pane** and **Criteria Pane**.</span></span>  
  
-   <span data-ttu-id="45a4f-107">Проверка SQL может обнаружить некоторые, но не все ошибки языка SQL.</span><span class="sxs-lookup"><span data-stu-id="45a4f-107">SQL Verification can detect some, but not all SQL errors.</span></span> <span data-ttu-id="45a4f-108">Если запрос будет содержать ошибку, не обнаруженную в ходе проверки синтаксиса SQL, то база данных обнаружит ошибку при выполнении запроса.</span><span class="sxs-lookup"><span data-stu-id="45a4f-108">If a query contains an error not detected during SQL verification, the database will detect the error when you run the query.</span></span>  
  
-   <span data-ttu-id="45a4f-109">Запросы, содержащие параметры, не могут быть проверены.</span><span class="sxs-lookup"><span data-stu-id="45a4f-109">Queries that contain parameters cannot be verified.</span></span>  
  
### <a name="to-verify-an-sql-statement"></a><span data-ttu-id="45a4f-110">Проверка инструкции SQL</span><span class="sxs-lookup"><span data-stu-id="45a4f-110">To verify an SQL statement</span></span>  
  
-   <span data-ttu-id="45a4f-111">Щелкните правой кнопкой мыши любое место на **панели SQL**и выберите из контекстного меню пункт **Проверить синтаксис SQL** .</span><span class="sxs-lookup"><span data-stu-id="45a4f-111">Right-click in the **SQL Pane**, and select **Verify SQL Syntax** from the shortcut menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45a4f-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="45a4f-112">See Also</span></span>  
 <span data-ttu-id="45a4f-113">[Выполнение запросов &#40;визуальных инструментов для баз данных&#41;](run-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="45a4f-113">[Run Queries &#40;Visual Database Tools&#41;](run-queries-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="45a4f-114">Выполнение основных операций с запросами (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="45a4f-114">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
