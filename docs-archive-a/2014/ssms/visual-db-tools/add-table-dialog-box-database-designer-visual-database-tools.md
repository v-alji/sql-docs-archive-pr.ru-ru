---
title: Диалоговое окно "Добавление таблицы" в конструкторе базы данных (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:65555
- vdt.dlgbox.schema.addtable
ms.assetid: 3c0b1b30-795c-4240-91d6-890b8348014a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6ae9d3763ef66c0a7580cc516169c2f273f36528
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657469"
---
# <a name="add-table-dialog-box-database-designer-visual-database-tools"></a><span data-ttu-id="d0fda-102">Диалоговое окно «Добавление таблицы» (конструктор базы данных) (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="d0fda-102">Add Table Dialog Box (Database Designer) (Visual Database Tools)</span></span>
  <span data-ttu-id="d0fda-103">Позволяет добавлять таблицы в конструкторе базы данных.</span><span class="sxs-lookup"><span data-stu-id="d0fda-103">Lets you add tables in Database Designer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d0fda-104">Если таблица опубликована для репликации, то изменения схемы следует проводить при помощи инструкции языка Transact-SQL [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) или объектов SMO.</span><span class="sxs-lookup"><span data-stu-id="d0fda-104">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="d0fda-105">При изменении схемы с помощью конструктора таблиц или конструктора диаграмм баз данных конструктор пытается удалить и затем вновь создать таблицу.</span><span class="sxs-lookup"><span data-stu-id="d0fda-105">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="d0fda-106">Но поскольку удалять опубликованные объекты нельзя, изменения схемы не будут применены.</span><span class="sxs-lookup"><span data-stu-id="d0fda-106">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="d0fda-107">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="d0fda-107">UI element list</span></span>  
 <span data-ttu-id="d0fda-108">**Обновить**</span><span class="sxs-lookup"><span data-stu-id="d0fda-108">**Refresh**</span></span>  
 <span data-ttu-id="d0fda-109">Обновляет список таблиц для соответствия текущему состоянию базы данных.</span><span class="sxs-lookup"><span data-stu-id="d0fda-109">Refreshed the list of tables to match the current state of the database.</span></span>  
  
 <span data-ttu-id="d0fda-110">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="d0fda-110">**Add**</span></span>  
 <span data-ttu-id="d0fda-111">Добавляет выбранную таблицу или таблицы.</span><span class="sxs-lookup"><span data-stu-id="d0fda-111">Adds the selected table or tables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d0fda-112">Если нужно добавить несколько таблиц к диаграмме, можно выбрать их все, а затем нажать кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d0fda-112">If you want to add several tables to the diagram, you can select them all before clicking **Add**.</span></span> <span data-ttu-id="d0fda-113">Или можно дважды щелкнуть каждую таблицу, которую нужно добавить, а затем, по окончании, нажать кнопку **Закрыть** .</span><span class="sxs-lookup"><span data-stu-id="d0fda-113">Alternatively, you can double-click each table you want to add, then click **Close** when you are finished.</span></span>  
  
 <span data-ttu-id="d0fda-114">**Закрыть**</span><span class="sxs-lookup"><span data-stu-id="d0fda-114">**Close**</span></span>  
 <span data-ttu-id="d0fda-115">Закрывает диалоговое окно без дальнейшего добавления таблиц.</span><span class="sxs-lookup"><span data-stu-id="d0fda-115">Closes the dialog box without adding further tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0fda-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="d0fda-116">See Also</span></span>  
 [<span data-ttu-id="d0fda-117">Добавление таблиц в диаграммы (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="d0fda-117">Add Tables to Diagrams &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
