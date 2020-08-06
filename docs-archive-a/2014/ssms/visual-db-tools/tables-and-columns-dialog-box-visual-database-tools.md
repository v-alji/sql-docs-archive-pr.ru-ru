---
title: Диалоговое окно "Таблицы и столбцы" (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.tablesandcolumns
ms.assetid: 8cf27be1-e66d-4735-a428-9ab4b33af4f5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 28e0c52b74413a3a5a4122412c6028b34e974b09
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667515"
---
# <a name="tables-and-columns-dialog-box-visual-database-tools"></a><span data-ttu-id="f70c2-102">Диалоговое окно «Таблицы и столбцы» (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="f70c2-102">Tables and Columns Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="f70c2-103">Это диалоговое окно используется для сопоставления первичного ключа одной таблицы с внешним ключом другой.</span><span class="sxs-lookup"><span data-stu-id="f70c2-103">Use this dialog box to map a primary key in one table to a foreign key in another.</span></span> <span data-ttu-id="f70c2-104">Для доступа к этому диалоговому окну из меню **Конструктор таблиц** щелкните **Связи**.</span><span class="sxs-lookup"><span data-stu-id="f70c2-104">To access this dialog box, from the **Table Designer** menu, click **Relationships**.</span></span> <span data-ttu-id="f70c2-105">В диалоговом окне **Связи по внешнему ключу** щелкните поле **Спецификация таблиц и столбцов**, а затем щелкните многоточие **(…)** справа от свойства.</span><span class="sxs-lookup"><span data-stu-id="f70c2-105">In the **Foreign Key Relationships** dialog box, click the **Tables and Columns Specification** field, and then click the ellipses **(...)** to the right of the property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f70c2-106">Если таблица опубликована для репликации, то изменения схемы следует проводить при помощи инструкции языка Transact-SQL [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) или объектов SMO.</span><span class="sxs-lookup"><span data-stu-id="f70c2-106">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="f70c2-107">При изменении схемы с помощью конструктора таблиц или конструктора диаграмм баз данных конструктор пытается удалить и затем вновь создать таблицу.</span><span class="sxs-lookup"><span data-stu-id="f70c2-107">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="f70c2-108">Но поскольку удалять опубликованные объекты нельзя, изменения схемы не будут применены.</span><span class="sxs-lookup"><span data-stu-id="f70c2-108">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f70c2-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="f70c2-109">Options</span></span>  
 <span data-ttu-id="f70c2-110">**Имя связи**</span><span class="sxs-lookup"><span data-stu-id="f70c2-110">**Relationship name**</span></span>  
 <span data-ttu-id="f70c2-111">Показывает имя связи.</span><span class="sxs-lookup"><span data-stu-id="f70c2-111">Shows the name of the relationship.</span></span>  
  
 <span data-ttu-id="f70c2-112">**Таблица первичного ключа**</span><span class="sxs-lookup"><span data-stu-id="f70c2-112">**Primary Key Table**</span></span>  
 <span data-ttu-id="f70c2-113">Содержит список таблиц базы данных.</span><span class="sxs-lookup"><span data-stu-id="f70c2-113">Lists the tables in the database.</span></span> <span data-ttu-id="f70c2-114">Выберите таблицу, которая будет включена в связь со стороны первичного ключа.</span><span class="sxs-lookup"><span data-stu-id="f70c2-114">Choose the table that will be on the primary-key side of the relationship.</span></span>  
  
 <span data-ttu-id="f70c2-115">**Таблица внешнего ключа**</span><span class="sxs-lookup"><span data-stu-id="f70c2-115">**Foreign Key Table**</span></span>  
 <span data-ttu-id="f70c2-116">Показывает таблицу, включаемую в связь на стороне внешнего ключа.</span><span class="sxs-lookup"><span data-stu-id="f70c2-116">Shows the table on the foreign key side of the relationship.</span></span> <span data-ttu-id="f70c2-117">Это таблица, выбранная в данный момент в конструкторе таблиц.</span><span class="sxs-lookup"><span data-stu-id="f70c2-117">This is the table currently selected in Table Designer.</span></span>  
  
 <span data-ttu-id="f70c2-118">**Сетка под таблицей с первичным ключом**</span><span class="sxs-lookup"><span data-stu-id="f70c2-118">**Grid beneath Primary Key Table**</span></span>  
 <span data-ttu-id="f70c2-119">Содержит список столбцов таблицы, выбранной в списке **Таблица первичного ключа** .</span><span class="sxs-lookup"><span data-stu-id="f70c2-119">List the columns of the table selected in the **Primary Key Table** list.</span></span> <span data-ttu-id="f70c2-120">Введите столбцы, относящиеся к первичному ключу этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="f70c2-120">Enter the columns contributing to that table's primary key.</span></span>  
  
 <span data-ttu-id="f70c2-121">**Сетка под таблицей с внешним ключом**</span><span class="sxs-lookup"><span data-stu-id="f70c2-121">**Grid beneath Foreign Key Table**</span></span>  
 <span data-ttu-id="f70c2-122">Содержит список столбцов таблицы, выбранной в списке **Таблица внешнего ключа** .</span><span class="sxs-lookup"><span data-stu-id="f70c2-122">List the columns of the table selected in the **Foreign Key Table** list.</span></span> <span data-ttu-id="f70c2-123">Введите внешний ключевой столбец таблицы внешнего ключа, соответствующий первичному ключевому столбцу.</span><span class="sxs-lookup"><span data-stu-id="f70c2-123">Enter the foreign-key column of the foreign-key table that corresponds to the primary key column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f70c2-124">Столбцы, выбранные для внешнего ключа, должны иметь одинаковый тип данных с первичными столбцами, которым они соответствуют.</span><span class="sxs-lookup"><span data-stu-id="f70c2-124">The columns you choose for the foreign key must have the same data type of the primary columns they correspond to.</span></span> <span data-ttu-id="f70c2-125">Каждый ключ должен включать одинаковое число столбцов.</span><span class="sxs-lookup"><span data-stu-id="f70c2-125">There must be an equal number of columns in each of the keys.</span></span> <span data-ttu-id="f70c2-126">Например, если первичный ключ на первичной стороне связи состоит из двух столбцов, необходимо сопоставить каждому из этих столбцов столбец таблицы на стороне внешнего ключа связи.</span><span class="sxs-lookup"><span data-stu-id="f70c2-126">For example, if the primary key of the table on the primary side of the relationship is made up of two columns, you will need to match each of those columns with a column in the table for the foreign key side of the relationship.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f70c2-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="f70c2-127">See Also</span></span>  
 [<span data-ttu-id="f70c2-128">Создание связей по внешнему ключу</span><span class="sxs-lookup"><span data-stu-id="f70c2-128">Create Foreign Key Relationships</span></span>](../../relational-databases/tables/create-foreign-key-relationships.md)  
  
  
