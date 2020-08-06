---
title: Построение связи "многие ко многим" (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- relationships [SQL Server], many-to-many
- junction tables [SQL Server]
- many-to-many relationships [SQL Server]
- mapping many-to-many relationships [SQL Server]
- database diagrams [SQL Server], relationships
ms.assetid: 2977cf92-98b5-48b2-b0fd-8fbc7040f2b4
author: stevestein
ms.author: sstein
ms.openlocfilehash: cbcbdbdf8d8371baa2a817e43b831535723be7ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668018"
---
# <a name="map-many-to-many-relationships-visual-database-tools"></a><span data-ttu-id="8bdbe-102">Построение связи «многие ко многим» (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="8bdbe-102">Map Many-to-Many Relationships (Visual Database Tools)</span></span>
  <span data-ttu-id="8bdbe-103">Отношения «многие ко многим» позволяют связать каждую строку одной таблицы с несколькими строками другой таблицы и наоборот.</span><span class="sxs-lookup"><span data-stu-id="8bdbe-103">Many-to-many relationships let you relate each row in one table to many rows in another table, and vice versa.</span></span> <span data-ttu-id="8bdbe-104">Например, отношение «многие ко многим» можно создать для таблиц `authors` и `titles` , чтобы связать каждого автора с его книгами и сопоставить каждой книге ее автора.</span><span class="sxs-lookup"><span data-stu-id="8bdbe-104">For example, you could create a many-to-many relationship between the `authors` table and the `titles` table to match each author to all of his or her books and to match each book to all of its authors.</span></span> <span data-ttu-id="8bdbe-105">Если создать связь «один ко многим» в любой таблице, получится, что каждая книга сможет иметь только одного автора или каждый автор — только одну книгу.</span><span class="sxs-lookup"><span data-stu-id="8bdbe-105">Creating a one-to-many relationship from either table would incorrectly indicate that every book can have only one author, or that every author can write only one book.</span></span>  
  
 <span data-ttu-id="8bdbe-106">Для осуществления связей «многие ко многим» между таблицами базы данных применяются связующие таблицы.</span><span class="sxs-lookup"><span data-stu-id="8bdbe-106">Many-to-many relationships between tables are accommodated in databases by means of junction tables.</span></span> <span data-ttu-id="8bdbe-107">Они содержат первичные ключевые столбцы двух таблиц, которые необходимо связать.</span><span class="sxs-lookup"><span data-stu-id="8bdbe-107">A junction table contains the primary key columns of the two tables you want to relate.</span></span> <span data-ttu-id="8bdbe-108">После этого можно создать связи между первичными ключевыми столбцами каждой таблицы и соответствующими столбцами в связующей таблице.</span><span class="sxs-lookup"><span data-stu-id="8bdbe-108">You then create a relationship from the primary key columns of each of those two tables to the matching columns in the junction table.</span></span> <span data-ttu-id="8bdbe-109">В базе данных pubs связующей является таблица `titleauthor` .</span><span class="sxs-lookup"><span data-stu-id="8bdbe-109">In the pubs database, the `titleauthor` table is a junction table.</span></span>  
  
### <a name="to-create-a-many-to-many-relationship-between-tables"></a><span data-ttu-id="8bdbe-110">Для создания связи «многие ко многим» между таблицами</span><span class="sxs-lookup"><span data-stu-id="8bdbe-110">To create a many-to-many relationship between tables</span></span>  
  
1.  <span data-ttu-id="8bdbe-111">Добавьте таблицы, которые должны обладать связью «многие ко многим» в диаграмму базы данных.</span><span class="sxs-lookup"><span data-stu-id="8bdbe-111">In your database diagram, add the tables that you want to create a many-to-many relationship between.</span></span>  
  
2.  <span data-ttu-id="8bdbe-112">Создайте третью таблицу, щелкнув диаграмму правой кнопкой мыши и выбрав **Создать таблицу** .</span><span class="sxs-lookup"><span data-stu-id="8bdbe-112">Create a third table by right-clicking the diagram and choosing **New Table** from the shortcut menu.</span></span> <span data-ttu-id="8bdbe-113">Эта таблица станет связующей.</span><span class="sxs-lookup"><span data-stu-id="8bdbe-113">This will become the junction table.</span></span>  
  
3.  <span data-ttu-id="8bdbe-114">В диалоговом окне **Выбор имени** измените имя, назначенное системой.</span><span class="sxs-lookup"><span data-stu-id="8bdbe-114">In the **Choose Name** dialog box, change the system-assigned table name.</span></span> <span data-ttu-id="8bdbe-115">Например, связующую таблицу для таблиц `titles` и `authors` можно назвать `titleauthors`.</span><span class="sxs-lookup"><span data-stu-id="8bdbe-115">For example, the junction table between the `titles` table and the `authors` table is now named `titleauthors`.</span></span>  
  
4.  <span data-ttu-id="8bdbe-116">Скопируйте первичные ключевые столбцы обеих таблиц в связующую таблицу.</span><span class="sxs-lookup"><span data-stu-id="8bdbe-116">Copy the primary key columns from each of the other two tables to the junction table.</span></span> <span data-ttu-id="8bdbe-117">В эту таблицу можно добавить другие столбцы, как в любую другую таблицу.</span><span class="sxs-lookup"><span data-stu-id="8bdbe-117">You can add other columns to this table, just as you can to any other table.</span></span>  
  
5.  <span data-ttu-id="8bdbe-118">Создайте первичный ключ в связующей таблице так, чтобы он содержал все первичные ключевые столбцы исходных таблиц.</span><span class="sxs-lookup"><span data-stu-id="8bdbe-118">In the junction table, set the primary key to include all the primary key columns from the other two tables.</span></span> <span data-ttu-id="8bdbe-119">Дополнительные сведения см. в разделе [Создание первичных ключей](../../relational-databases/tables/create-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="8bdbe-119">For details, see [Create Primary Keys](../../relational-databases/tables/create-primary-keys.md).</span></span>  
  
6.  <span data-ttu-id="8bdbe-120">Определите отношение «один ко многим» между каждой из первоначальных таблиц и связующей таблицей.</span><span class="sxs-lookup"><span data-stu-id="8bdbe-120">Define a one-to-many relationship between each of the two primary tables and the junction table.</span></span> <span data-ttu-id="8bdbe-121">Связующая таблица должна находиться на стороне «многих» обоих отношений.</span><span class="sxs-lookup"><span data-stu-id="8bdbe-121">The junction table should be at the "many" side of both of the relationships you create.</span></span> <span data-ttu-id="8bdbe-122">Дополнительные сведения см. в разделе [Создание связей по внешнему ключу](../../relational-databases/tables/create-foreign-key-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="8bdbe-122">For details, see [Create Foreign Key Relationships](../../relational-databases/tables/create-foreign-key-relationships.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8bdbe-123">Создание связующей таблицы в диаграмме базы данных не подразумевает ее заполнение данными из связанных таблиц.</span><span class="sxs-lookup"><span data-stu-id="8bdbe-123">The creation of a junction table in a database diagram does not insert data from the related tables into the junction table.</span></span> <span data-ttu-id="8bdbe-124">Дополнительные сведения о вставке данных в эту таблицу см. в разделе [Создание запросов вставки результатов (визуальные инструменты для баз данных)](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8bdbe-124">For information about inserting data into a table, see [Create Insert Results Queries &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bdbe-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="8bdbe-125">See Also</span></span>  
 [<span data-ttu-id="8bdbe-126">Работа с диаграммами баз данных (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="8bdbe-126">Work with Database Diagrams &#40;Visual Database Tools&#41;</span></span>](work-with-database-diagrams-visual-database-tools.md)  
  
  
