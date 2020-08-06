---
title: Работа с таблицами в схемах базы данных (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- database diagrams [SQL Server], tables
- Table Designer, database diagrams
- tables [SQL Server], database diagrams
- database diagrams [SQL Server], Table Designer
ms.assetid: ee2c5d84-22bf-4597-ac70-a27ed8cc94f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: f648cd5fd08ed47c6670491ad5b7f3d75b7ead47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665709"
---
# <a name="work-with-tables-in-database-diagram-visual-database-tools"></a><span data-ttu-id="491d6-102">Работа с таблицами в диаграммах базы данных (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="491d6-102">Work with Tables in Database Diagram (Visual Database Tools)</span></span>
  <span data-ttu-id="491d6-103">Можно изменять и создавать таблицы баз данных либо в конструкторе таблиц, либо в конструкторе диаграмм баз данных.</span><span class="sxs-lookup"><span data-stu-id="491d6-103">You can modify and create database tables in either Table Designer or Database Diagram Designer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="491d6-104">Если таблица опубликована для репликации, то изменения схемы следует проводить при помощи инструкции языка Transact-SQL [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) или объектов SMO.</span><span class="sxs-lookup"><span data-stu-id="491d6-104">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="491d6-105">При изменении схемы с помощью конструктора таблиц или конструктора диаграмм баз данных конструктор пытается удалить и затем вновь создать таблицу.</span><span class="sxs-lookup"><span data-stu-id="491d6-105">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="491d6-106">Но поскольку удалять опубликованные объекты нельзя, изменения схемы не будут применены.</span><span class="sxs-lookup"><span data-stu-id="491d6-106">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="491d6-107">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="491d6-107">In This Section</span></span>  
 [<span data-ttu-id="491d6-108">Добавление таблиц в диаграммы (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="491d6-108">Add Tables to Diagrams &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
 [<span data-ttu-id="491d6-109">Добавление связанных таблиц в диаграммы (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="491d6-109">Add Related Tables to Diagrams &#40;Visual Database Tools&#41;</span></span>](add-related-tables-to-diagrams-visual-database-tools.md)  
  
 [<span data-ttu-id="491d6-110">Сохранение выбранных таблиц в диаграмме (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="491d6-110">Save Selected Tables on a Diagram &#40;Visual Database Tools&#41;</span></span>](save-selected-tables-on-a-diagram-visual-database-tools.md)  
  
 [<span data-ttu-id="491d6-111">Копирование таблиц из одних диаграмм базы данных в другие (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="491d6-111">Copy Tables from One Database Diagrams to Another &#40;Visual Database Tools&#41;</span></span>](copy-tables-from-one-database-diagrams-to-another-visual-database-tools.md)  
  
 [<span data-ttu-id="491d6-112">Удаление таблицы из диаграмм базы данных (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="491d6-112">Remove Tables from Database Diagrams &#40;Visual Database Tools&#41;</span></span>](remove-tables-from-database-diagrams-visual-database-tools.md)  
  
 [<span data-ttu-id="491d6-113">Построение связи "многие ко многим" (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="491d6-113">Map Many-to-Many Relationships &#40;Visual Database Tools&#41;</span></span>](map-many-to-many-relationships-visual-database-tools.md)  
  
 [<span data-ttu-id="491d6-114">Извлечение рефлексивных связей (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="491d6-114">Draw Reflexive Relationships &#40;Visual Database Tools&#41;</span></span>](draw-reflexive-relationships-visual-database-tools.md)  
  
## <a name="reference"></a><span data-ttu-id="491d6-115">Справочник</span><span class="sxs-lookup"><span data-stu-id="491d6-115">Reference</span></span>  
 [<span data-ttu-id="491d6-116">Диалоговое окно "Добавление таблицы" (конструктор базы данных) (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="491d6-116">Add Table Dialog Box &#40;Database Designer&#41; &#40;Visual Database Tools&#41;</span></span>](add-table-dialog-box-database-designer-visual-database-tools.md)  
  
## <a name="related-sections"></a><span data-ttu-id="491d6-117">См. также</span><span class="sxs-lookup"><span data-stu-id="491d6-117">Related Sections</span></span>  
  