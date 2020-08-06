---
title: Извлечение рефлексивных связей (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- drawing reflexive relationships
- reflexive relationships
- database diagrams [SQL Server], relationships
ms.assetid: e218363f-faec-46d5-9904-a537fbcc994d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8e5056b1a5d0d884edbc4fc818fe8c7ef5cc8ad4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665714"
---
# <a name="draw-reflexive-relationships-visual-database-tools"></a><span data-ttu-id="91464-102">Извлечение рефлексивных связей (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="91464-102">Draw Reflexive Relationships (Visual Database Tools)</span></span>
  <span data-ttu-id="91464-103">Чтобы связать столбец или столбцы в таблице с другим столбцом или столбцами в той же таблице, можно создать рефлексивные связи.</span><span class="sxs-lookup"><span data-stu-id="91464-103">You create a reflexive relationship to link a column or columns in a table with another column or columns in the same table.</span></span> <span data-ttu-id="91464-104">Например, в таблице `employee` имеется столбец `emp_id` и столбец `mgr_id` .</span><span class="sxs-lookup"><span data-stu-id="91464-104">For example, suppose the `employee` table has an `emp_id` column and a `mgr_id` column.</span></span> <span data-ttu-id="91464-105">Учитывая то, что менеджеры также являются сотрудниками, можно связать эти столбцы при помощи линии взаимосвязи в таблице.</span><span class="sxs-lookup"><span data-stu-id="91464-105">Because each manager is also an employee, you relate these two columns by drawing a relationship line from the table to itself.</span></span> <span data-ttu-id="91464-106">Такие связи гарантируют, что каждый идентификатор менеджера, добавляемый в таблицу, будет соответствовать существующему идентификатору сотрудника.</span><span class="sxs-lookup"><span data-stu-id="91464-106">This relationship ensures each manager ID that is added to the table matches an existing employee ID.</span></span>  
  
 <span data-ttu-id="91464-107">Перед тем как создавать связи, необходимо определить для таблицы первичный ключ или ограничение уникальности.</span><span class="sxs-lookup"><span data-stu-id="91464-107">Before you create a relationship, you must first define a primary key or unique constraint for your table.</span></span> <span data-ttu-id="91464-108">Затем необходимо связать первичный ключевой столбец с соответствующим столбцом.</span><span class="sxs-lookup"><span data-stu-id="91464-108">You then relate the primary key column to a matching column.</span></span> <span data-ttu-id="91464-109">После того как связь создана, соответствующий столбец становится внешним ключом таблицы.</span><span class="sxs-lookup"><span data-stu-id="91464-109">Once you create the relationship, the matching column becomes a foreign key of the table.</span></span>  
  
### <a name="to-draw-a-reflexive-relationship"></a><span data-ttu-id="91464-110">Извлечение рефлексивной связи</span><span class="sxs-lookup"><span data-stu-id="91464-110">To draw a reflexive relationship</span></span>  
  
1.  <span data-ttu-id="91464-111">В диаграмме базы данных щелкните переключатель строк для столбца базы данных, который необходимо связать с другим столбцом, и перетаскивайте указатель за пределы таблицы, пока не появится линия.</span><span class="sxs-lookup"><span data-stu-id="91464-111">In your database diagram, click the row selector for the database column that you want to relate to another column and drag the pointer outside the table until a line appears.</span></span>  
  
2.  <span data-ttu-id="91464-112">Перетащите линию назад к выбранной таблице.</span><span class="sxs-lookup"><span data-stu-id="91464-112">Drag the line back to the selected table.</span></span>  
  
3.  <span data-ttu-id="91464-113">Отпустите кнопку мыши.</span><span class="sxs-lookup"><span data-stu-id="91464-113">Release the mouse button.</span></span> <span data-ttu-id="91464-114">Появится диалоговое окно **Таблицы и столбцы** .</span><span class="sxs-lookup"><span data-stu-id="91464-114">The **Tables and Columns** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="91464-115">Выберите ключевой столбец внешнего ключа и таблицу первичного ключа, с которой необходимо установить связь.</span><span class="sxs-lookup"><span data-stu-id="91464-115">Select the foreign key column and the primary key table and column with which you want form a relationship.</span></span>  
  
5.  <span data-ttu-id="91464-116">Дважды нажмите кнопку **ОК** , чтобы создать связь.</span><span class="sxs-lookup"><span data-stu-id="91464-116">Choose **OK** twice to create the relationship.</span></span>  
  
 <span data-ttu-id="91464-117">При выполнении запросов в таблице для создания самосоединения можно использовать рефлексивные связи.</span><span class="sxs-lookup"><span data-stu-id="91464-117">When you run queries against a table, you can use a reflexive relationship to create a self-join.</span></span> <span data-ttu-id="91464-118">Дополнительные сведения о запросах к таблицам с соединениями см. в разделе [Запросы с соединениями (визуальные инструменты для баз данных)](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="91464-118">For information about querying tables with joins, see [Query with Joins &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91464-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="91464-119">See Also</span></span>  
 [<span data-ttu-id="91464-120">Запросы с соединениями (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="91464-120">Query with Joins &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
