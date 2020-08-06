---
title: Автоматическое соединение самосоединения (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- automatic joins
- self-joins
- joins [SQL Server], self
ms.assetid: f9ec90e8-3aad-415c-a5c4-8dfa9540e37f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4a428a44d33b5990e849772b43841df472ca7f6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654711"
---
# <a name="create-self-joins-automatically-visual-database-tools"></a><span data-ttu-id="faa62-102">Автоматическое создание самосоединения (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="faa62-102">Create Self-Joins Automatically (Visual Database Tools)</span></span>
  <span data-ttu-id="faa62-103">Если таблица имеет рефлексивную связь в базе данных, можно автоматически создать самосоединение.</span><span class="sxs-lookup"><span data-stu-id="faa62-103">If a table has a reflexive relationship in the database, you can join it to itself automatically.</span></span>  
  
### <a name="to-create-a-self-join-automatically"></a><span data-ttu-id="faa62-104">Автоматическое создание самосоединения</span><span class="sxs-lookup"><span data-stu-id="faa62-104">To create a self-join automatically</span></span>  
  
1.  <span data-ttu-id="faa62-105">Добавьте на [панель диаграмм](visual-database-tools.md) нужную таблицу.</span><span class="sxs-lookup"><span data-stu-id="faa62-105">Add to the [Diagram pane](visual-database-tools.md) the table you want to work with.</span></span>  
  
2.  <span data-ttu-id="faa62-106">Еще раз добавьте эту таблицу, чтобы на панели диаграмм эта таблица была показана дважды.</span><span class="sxs-lookup"><span data-stu-id="faa62-106">Add the same table again, so that the Diagram pane shows the same table twice within the Diagram pane.</span></span>  
  
     <span data-ttu-id="faa62-107">[Конструктор запросов и представлений](query-and-view-designer-tools-visual-database-tools.md) присваивает второму экземпляру псевдоним, добавляя порядковый номер к имени таблицы.</span><span class="sxs-lookup"><span data-stu-id="faa62-107">The [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) assigns an alias to the second instance by adding a sequential number to the table name.</span></span> <span data-ttu-id="faa62-108">Кроме того, конструктор запросов и представлений создает линию соединения между двумя прямоугольниками, представляющими два разных способа, которыми таблица участвует в запросе.</span><span class="sxs-lookup"><span data-stu-id="faa62-108">In addition, the Query and View Designer creates a join line between the two rectangles representing the two different ways the table participates in the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faa62-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="faa62-109">See Also</span></span>  
 [<span data-ttu-id="faa62-110">Запросы с соединениями (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="faa62-110">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
